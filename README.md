# Dropdown Menu

This is a simple dropdown component where custom css is used to design the menu and the overall design.
Linearicons is used for the icon, and vue-3-click-outside is used to close the menu. It's written in Vue using the Options API.

## Steps to run the project
> The commands below can help to set up the project.

### This component is built using Vue ( Options API ),
######  To get Started all you have to do is:

1. Install Project Dependencies
   > `npm install`

2. Launch the project
   > `npm run dev`

# Example Usage
1. Inside a component, we can import Dropdown, DropdownTrigger, and DropdownItem component, then
   register it locally, after that, we're passing slot contents to 
   DropDown component. DropdownTrigger also expects a slot content, and
   DropdownItem also expects slot content.

   ```
   <Dropdown>
    <template v-slot:trigger-button="{ toggle }">
      <DropdownTrigger tag="button" @click="toggle">
        <template v-slot:button-content>
          <span>Pick One</span>
          <span class="lnr lnr-chevron-down"></span>
        </template>
      </DropdownTrigger>
    </template>
    <template v-slot:menu-content="{ toggle }">
      <DropdownItem @click.prevent="toggle">Web Development</DropdownItem>
      <DropdownItem @click.prevent="toggle">Mobile Development</DropdownItem>
      <DropdownItem @click.prevent="toggle">Database Design</DropdownItem>
      <DropdownItem @click.prevent="toggle">Data Science</DropdownItem>
    </template>
   </Dropdown>
   ```

2. DropdownTrigger has `tag` as a props whose value can either be `a` or `button` element.
   The reason `tag` is used as a props here is because we can treat `<a>button</a>` (i.e. anchor element) or `<button>button</button>` (i.e. button element) 
   as a button, so it's more of a way to style guidelines on which element to use.

3. `Dropdown` component has slot outlets, and for the slot with name `trigger-button`, We're utilizing scoped slots: `v-slot:trigger-button="{ toggle }"`,
   where we're destructuring the slot props `toggle`, and for `<DropdownTrigger>`, the `@click` event
   gets inherited to the `DropdownTrigger` component due to `@click="toggle"`, and the event applies to
   passed `tag` element ( here, `tags` is props and `button` is passed as tag, so click event gets applied to button as it's only one direct parent present inside the `DropdownTrigger` component ) .

4. `DropdownTrigger` also has slot outlet, so we're passing html content
   to named slot `button-content`, and below is the HTML content that's passed.
   ```
   <span>Pick One</span>
   <span class="lnr lnr-chevron-down"></span>
   ```
   
5. `Dropdown` component also has another named slot `menu-content` and we're
   utilizing `toggle` slot props which then gets attached to `anchor` element present inside
   `DropdownItem` through `$attrs` ( we're disabling attribute inheritance so that we can bind it to specified element ),
   and we bound it to the `anchor` element.