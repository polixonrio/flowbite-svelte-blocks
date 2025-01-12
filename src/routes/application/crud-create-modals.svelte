<script lang="ts">
  import { Section } from '$lib';
  import { ExampleDiv, SectionHeader, EditOnGithub, MetaTag, DocsLink } from '../utils';
  import {
    Breadcrumb,
    BreadcrumbItem,
    Label,
    Input,
    Button,
    Checkbox,
    Heading,
    P,
    A, Modal, Textarea, Select
  } from 'flowbite-svelte';
  const breadcrumb_title = 'Create Modals (CRUD)';
  const title = 'Crud Create Modals';
  const dir = 'application';
  const description =
    'Get started with a collection of modal components with form input elements to create new data models inside your dashboard based on Tailwind CSS.';
  let defaultModal = false;
  const handleSubmit = () =>{
    alert('Form submited.')
  }
  let selected;
  let countries = [
    {value:"tv", name: "TV/Monitors"},
    {value:"pc", name: "PC"},
    {value:"phone", name: "Phones"},
  ]
</script>

<MetaTag {breadcrumb_title} {title} {dir} {description} />

<SectionHeader>
  <Breadcrumb navClass="flex mb-3">
    <BreadcrumbItem href="/" home>Blocks</BreadcrumbItem>
    <BreadcrumbItem href="/application">Application</BreadcrumbItem>
    <BreadcrumbItem>{breadcrumb_title}</BreadcrumbItem>
  </Breadcrumb>
  <svelte:fragment slot="h1"
    >Tailwind CSS {breadcrumb_title} - Flowbite Blocks in Svelte</svelte:fragment
  >
  <svelte:fragment slot="paragraph">{description}</svelte:fragment>
</SectionHeader>

<Section name="none" classSection="py-6 sm:py-10" classDiv="px-4 mx-auto max-w-8xl">
  <div class="grid lg:grid-cols-2">
    <div>
      <Heading tag="h2" customSize="text-2xl font-semibold" class="mb-1"
        >Default modal</Heading
      >
      <P size="lg" color="text-gray-500 dark:text-gray-400" class="lg:mb-0  lg:max-w-2xl">
        Use this free example to show a modal component with a form inside when creating a new instance of a product inside your application.
      </P>
      <EditOnGithub
        size="18"
        href="https://github.com/shinokada/flowbite-svelte-blocks/blob/main/src/routes/application/crud-create-modals.svelte"
        iconClass="text-gray-500"
      />
      <DocsLink page="{title.toLowerCase().replace(/\s+/g, '-')}" target="_blank"/>
    </div>
  </div>
</Section>

<ExampleDiv>
  <Section classSection='h-96'>
    <div class="flex justify-center m-5">
      <Button on:click={() => defaultModal = true}>Create product</Button>
    </div>
    <Modal title="Add Product" bind:open={defaultModal} autoclose class='min-w-full'>
      <form on:submit={handleSubmit}>
        <div class="grid gap-4 mb-4 sm:grid-cols-2">
          <div>
            <Label for='name' class="mb-2">Name</Label>
            <Input type='text' id='name' placeholder='Type product name' required/>
          </div>
          <div>
            <Label for='brand' class='mb-2'>Brand</Label>
            <Input type='text' id='brand' placeholder='Product brand' required/>
          </div>
          <div>
            <Label for='price' class='mb-2'>Price</Label>
            <Input type='text' id='price' placeholder='$29999' required/>
          </div>
          <div>
            <Label>Category
              <Select class="mt-2" items={countries} bind:value={selected} required/>
            </Label>
          </div>
          <div class="sm:col-span-2">
            <Label for="description" class="mb-2">Description</Label>
            <Textarea id="description" placeholder="Your description here" rows="4" name="description" required />
          </div>
          <Button type='submit' class='w-52'>
            <svg class="mr-1 -ml-1 w-6 h-6" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path fill-rule="evenodd" d="M10 5a1 1 0 011 1v3h3a1 1 0 110 2h-3v3a1 1 0 11-2 0v-3H6a1 1 0 110-2h3V6a1 1 0 011-1z" clip-rule="evenodd"></path></svg>
              Add new product
          </Button>
        </div>
      </form>
    </Modal>
  </Section>
</ExampleDiv>
