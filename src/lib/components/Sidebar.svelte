<script lang="ts">
    import DonateButton from '$lib/components/DonateButton.svelte';
    import NavLink from '$lib/components/NavLink.svelte';

    const navLinks = {
        classes: [
            { href: '/classes/ndk', linkText: 'NDK' },
            { href: '/classes/ndkEvent', linkText: 'NDKEvent' },
            { href: '/classes/ndkUser', linkText: 'NDKUser' },
            { href: '/classes/ndkUserProfile', linkText: 'NDKUserProfile' }
        ],
        guides: [{ href: '/', linkText: 'Getting started' }],
        pages: [{ href: 'https://nostr.how', linkText: 'What is Nostr?' }]
    };
</script>

<a href="/" class="hidden md:flex flex-row gap-6 items-center text-3xl ml-4 no-underline">
    <!-- <span class="font-extrabold leading-tight gradientText">Nostr Dev Kit</span> -->
    <div class="w-1/2 text-3xl font-extrabold leading-none">
        <span class="text-[#6d0593]">N</span>ostr<br />Dev<br />Kit
    </div>
</a>

<div class="navWrapper guides md:mt-10 ml-4">
    <h2 class="mb-2 font-semibold">Guides</h2>
    <ul class="nav text-base">
        {#each navLinks.guides as link}
            <li>
                <NavLink on:navLinkClicked href={link.href} linkText={link.linkText} />
            </li>
        {/each}
    </ul>
</div>

<div class="navWrapper classes md:mt-10 ml-4">
    <h2 class="mb-2 font-semibold">Classes</h2>
    <ul class="nav text-base">
        {#each navLinks.classes as link}
            <li>
                <NavLink on:navLinkClicked href={link.href} linkText={link.linkText} />
            </li>
        {/each}
    </ul>
</div>

<div class="navWrapper resources mt-10 mb-10 ml-4">
    <h2 class="mb-2 font-semibold">Resources</h2>
    <ul class="nav text-base">
        {#each navLinks.pages as link}
            <li>
                <NavLink on:navLinkClicked href={link.href} linkText={link.linkText} />
            </li>
        {/each}
    </ul>
</div>

<div class="flex flex-col items-center mx-auto">
    <DonateButton variant="primary" classes="text-sm" />
    <div class="colophon text-zinc-500 dark:text-zinc-400 mt-4 text-sm text-center px-8">
        <div>Made with 💜 & ⚡ by</div>
        <a
            href="https://snort.social/p/npub1l2vyh47mk2p0qlsku7hg0vn29faehy9hy34ygaclpn66ukqp3afqutajft"
            target="_blank"
            class="underline hover:text-zinc-600 dark:hover:text-zinc-200">PABLOF7z</a
        >,
        <a
            href="https://snort.social/p/npub1zuuajd7u3sx8xu92yav9jwxpr839cs0kc3q6t56vd5u9q033xmhsk6c2uc"
            target="_blank"
            class="underline hover:text-zinc-600 dark:hover:text-zinc-200">JeffG</a
        >, and
        <a
            href="https://github.com/nostr-dev-kit/ndk/graphs/contributors"
            target="_blank"
            class="underline hover:text-zinc-600 dark:hover:text-zinc-200"
            >many other contributors</a
        >.
    </div>
</div>
