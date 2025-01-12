 # Contact Form

[Demo](https://flowbite-svelte-blocks.vercel.app/marketing/contact)

## Example usage

```html
<script lang="ts">
  import { Contact } from 'flowbite-svelte-blocks';
  import { Label, Input, Textarea, Button } from 'flowbite-svelte';
</script>

<Contact>
  <svelte:fragment slot="h2">Contact Us</svelte:fragment>
  <svelte:fragment slot="paragraph">
    Got a technical issue? Want to send feedback about a beta feature? Need details about our
    Business plan? Let us know.
  </svelte:fragment>
  <form class="space-y-8">
    <div>
      <Label for="email" class="block mb-2">Your email</Label>
      <Input id="email" name="email" placeholder="name@flowbite.com" required />
    </div>
    <div>
      <Label for="subject" class="block mb-2">Subject</Label>
      <Input
        id="subject"
        name="subject"
        placeholder="Let us know how we can help you"
        required
      />
    </div>
    <div>
      <Textarea
        id="subject"
        name="subject"
        placeholder="Leave a comment..."
        label="Your message"
      />
    </div>
    <Button>Send message</Button>
  </form>
</Contact>
```