<script>
    import { accessToken } from "./stores.js"

    let payloadB64 = $accessToken.split(".")[1]

    let fullname = JSON.parse(window.atob(payloadB64)).user_name
    let username = JSON.parse(window.atob(payloadB64)).user_username
    let email = JSON.parse(window.atob(payloadB64)).user_email
</script>

<div class="container mx-auto w-1/3 shadow">
    <div class="bg-white rounded-t-lg">
        <div class="px-7 py-5">
            <h3 class="text-lg leading-6 font-medium text-gray-900">
                User Profile
            </h3>
            <p class="mt-1 text-sm text-gray-500">
                Edit your profile and account information here.
            </p>
        </div>
    </div>
    <div class="border-t border-gray-200">
        <form action="submit">
            <div class="bg-gray-50 px-7 py-5 flex flex-row justify-between">
                <h4 class="text-base text-gray-500 font-medium mr-52 self-center">
                    Full Name
                </h4>
                <input type="text" value={fullname} class="text-base py-2 flex-grow max-w-sm">
            </div>
            <div class="bg-white px-7 py-5 flex flex-row justify-between">
                <h4 class="text-base text-gray-500 font-medium mr-52 self-center">
                    Username
                </h4>
                <p class="text-base py-2 max-w-sm text-gray-500">{username}</p>
            </div>
            <div class="bg-gray-50 px-7 py-5 flex flex-row justify-between">
                <h4 class="text-base text-gray-500 font-medium mr-52 self-center">
                    Email
                </h4>
                <input type="password" value={email} class="text-base py-2 flex-grow max-w-sm">
            </div>
            <div class="bg-white px-7 py-5 flex flex-row justify-between">
                <h4 class="text-base text-gray-500 font-medium mr-52 self-center">
                    Password
                </h4>
                <input type="text" class="text-base py-2 flex-grow max-w-sm">
            </div>
            <div class="bg-gray-50 px-7 py-5 flex flex-row justify-end">
                <button type="submit" class="inline-flex items-center bg-blue-400 border rounded-lg text-base">
                    <span class="mx-3 my-2 text-white">Save changes</span>
                </button>
                <button type="button" class="inline-flex items-center ml-5 border border-gray-500 rounded-lg">
                    <span class="mx-3 my-2">Return to home</span>
                </button>
            </div>
        </form>
    </div>
</div>