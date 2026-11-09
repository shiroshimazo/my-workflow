Apply these UI/UX laws to every screen, component, and piece of text. When you propose a UI, keep the design simple and follow these rules without being asked.

## Jakob's Law: use familiar patterns

Users spend most of their time on other products, so they expect yours to work the same way.

- Use standard patterns: logo top-left links home, main navigation at the top or side, search in the header, standard icons (trash = delete, magnifier = search).
- Use common form and table conventions. Do not invent new interactions when a known one works.
- Put things where users expect them. Keep behavior consistent across the whole system.

## Miller's Law: don't overload memory

People can hold only a small number of items in working memory (about 5-9).

- Group related information into chunks with clear headings.
- Keep menus and tab bars short (about 5-7 items).
- Split long forms into sections or steps. Paginate or filter long lists.
- Show only what is needed for the current task.

## Peak-End Rule: make key moments and endings good

People judge an experience mostly by its most intense moment and its ending.

- Make important moments clear and satisfying: saving, finishing a task, completing a purchase.
- End every flow with a clear confirmation and the next step ("Product saved. Add another?").
- Make errors calm and helpful, never blaming. Always tell the user how to recover.

## Aesthetic-Usability Effect: look good, work good

Users see attractive interfaces as easier to use and forgive small problems more.

- Use consistent spacing, alignment, type scale, and color palette across the system.
- Use one UI library or design system and stay within it. No one-off styles.
- Keep enough whitespace. Make visual hierarchy obvious: the important thing looks important.
- Looks never replace usability. A good-looking screen that is hard to use is still wrong.

## Occam's Razor: choose the simplest design

When two designs solve the problem, pick the simpler one.

- Remove any element, field, step, or option that does not help the user's goal.
- Fewer clicks, fewer screens, fewer words.
- Do not add UI "just in case".

## Hick's Law: fewer choices, faster decisions

Decision time grows with the number and complexity of choices.

- Show one clear primary action per screen. Make secondary actions visually quieter.
- Limit options. Use sensible defaults so users decide less.
- Hide advanced options behind "More" or an expandable section (progressive disclosure).
- For long lists, give search and filters instead of showing everything at once.

## Fitts's Law: make targets easy to reach

The time to hit a target depends on its distance and size.

- Make primary actions large and easy to hit. Touch targets are at least 44x44 px.
- Place frequent actions close to where the user is already looking or working.
- Keep spacing between buttons so users do not click the wrong one. Keep destructive actions (delete) away from common ones and ask for confirmation.
- Do not make users aim at tiny icons, thin links, or crowded controls.

## Writing inside the system

All text in the interface must be **concise, short, and direct to the point**. This covers labels, buttons, descriptions, tags, tooltips, placeholders, empty states, and messages.

Rules:

- Lead with the point. Cut filler words ("please note that", "in order to", "simply").
- One idea per sentence. Use plain words and active voice.
- Labels and buttons: 1-3 words. Buttons start with a verb: `Save product`, not `Click here to save`.
- Tags and badges: 1-2 words (`Low stock`, `Archived`).
- Descriptions: one short sentence, ideally under 15 words.
- Error messages: say what happened and how to fix it. `Quantity must be 0 or more.`
- Use the same word for the same thing everywhere (match the naming in `01-introduction.md`).

|Instead of|Write|
|---|---|
|`Click here to add a new product to the inventory`|`Add product`|
|`This field is required and must not be left empty`|`Required`|
|`An error has occurred while saving your changes`|`Could not save. Try again.`|
|`Products that are running low on stock`|`Low stock`|
