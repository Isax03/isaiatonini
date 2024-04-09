<script lang="ts">
</script>

<section class="flex flex-col w-full items-start justify-start px-8 sm:px-16 py-10 text-xl text-primary-foreground flex-grow">
    <h2 class="text-3xl font-semibold text-left w-full text-secondary-foreground">Contact Me</h2>
    <div class="mt-5">
        <!-- potete contattarmi tramite i canali -->
        <div>You can send me an email at <a href="mailto:isaia.tonini@gmail.com" class="text-secondary-foreground">isaia.tonini@gmail.com</a> or visit my <a href="mailto:isaia.tonini@gmail.com" class="text-secondary-foreground">Linkedin</a> profile.<br/></div>
        <div class="mt-2">You can also reach me through <a href="https://www.instagram.com/isa.toni03/" class="text-secondary-foreground">Instagram</a> or <a href="https://t.me/Isax73" class="text-secondary-foreground">Telegram</a>.<br/></div>

        <!-- oppure compilando il form sottostante -->
        <div class="mt-5">If you prefer, you can fill out the form below:</div>
        <form class="self-center" action="https://api.staticforms.xyz/submit" method="post">
            <div class="mt-5">
                <label for="name" class="text-secondary-foreground">Name</label>
                <input type="text" id="name" name="name" class="w-full h-10 rounded-md border border-input bg-zinc-700 px-3 py-2 text-sm mt-1">
            </div>
            <div class="mt-5">
                <label for="email" class="text-secondary-foreground">Email</label>
                <input type="email" id="email" name="email" class="w-full h-10 rounded-md border border-input bg-zinc-700 px-3 py-2 text-sm mt-1">
            </div>
            <div class="mt-5">
                <label for="message" class="text-secondary-foreground">Message</label>
                <textarea id="message" name="message" class="w-full h-32 rounded-md border border-input bg-zinc-700 px-3 py-2 text-sm mt-1"></textarea>
            </div>
            <input type="hidden" name="accessKey" value="e61553cc-b4fa-44f6-ad66-4196bc31401e">
            <input type="hidden" name="redirectTo" value="https://isaiatonini.com/contact">
            <div class="mt-5">
                <button type="submit" class="w-full text-zinc-900 font-bold h-10 rounded-md bg-secondary-foreground px-3 py-2 text-base">Send</button>
            </div>
        </form>
    </div>
</section>