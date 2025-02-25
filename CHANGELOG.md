# v0.0.19 (Thu Jul 15 2021)

### Release Notes

#### feat: support CSF3 format ([#37](https://github.com/storybookjs/testing-react/pull/37))

### Features

Storybook released [CSF3](https://storybook.js.org/blog/component-story-format-3-0/), where the story can also be an object. This is now supported in @storybook/testing-react. CSF3 also brings a new function called `play`, where you can write automated interactions to the story.

In @storybook/testing-react, the `play` does not run automatically for you, but rather comes in the returned component, and you can execute it as you please.

Consider the following example:

```tsx
export const InputFieldFilled: Story<InputFieldProps> = {
  play: async () => {
    await userEvent.type(screen.getByRole('textbox'), 'Hello world!');
  },
};
```

You can use the play function like this:

```tsx
const { InputFieldFilled } = composeStories(stories);

test('renders with play function', async () => {
  render(<InputFieldFilled />);

  // play an interaction that fills the input
  await InputFieldFilled.play!();

  const input = screen.getByRole('textbox') as HTMLInputElement;
  expect(input.value).toEqual('Hello world!');
});
```

---

#### 🐛 Bug Fix

- feat: support CSF3 format [#37](https://github.com/storybookjs/testing-react/pull/37) ([@yannbf](https://github.com/yannbf))

#### Authors: 1

- Yann Braga ([@yannbf](https://github.com/yannbf))

---

# v0.0.18 (Fri Jun 25 2021)

#### 🐛 Bug Fix

- Update TS information [#33](https://github.com/storybookjs/testing-react/pull/33) ([@eric-burel](https://github.com/eric-burel))

#### ⚠️ Pushed to `main`

- json -> jsonc into tsconfig code block ([@eric-burel](https://github.com/eric-burel))

#### Authors: 1

- Eric Burel ([@eric-burel](https://github.com/eric-burel))

---

# v0.0.17 (Thu Jun 03 2021)

#### 🐛 Bug Fix

- Widen peer dependency range to include prereleases [#26](https://github.com/storybookjs/testing-react/pull/26) ([@IanVS](https://github.com/IanVS))

#### Authors: 1

- Ian VanSchooten ([@IanVS](https://github.com/IanVS))

---

# v0.0.16 (Mon May 24 2021)

#### 🐛 Bug Fix

- fix: move storybook libs as peer deps [#23](https://github.com/storybookjs/testing-react/pull/23) ([@yannbf](https://github.com/yannbf))

#### Authors: 1

- Yann Braga ([@yannbf](https://github.com/yannbf))

---

# v0.0.15 (Sun May 23 2021)

#### 🐛 Bug Fix

- feat: add args as a result from composed story [#19](https://github.com/storybookjs/testing-react/pull/19) ([@yannbf](https://github.com/yannbf))

#### Authors: 1

- Yann Braga ([@yannbf](https://github.com/yannbf))

---

# v0.0.14 (Sun May 23 2021)

#### 🐛 Bug Fix

- fix: Remove deep import StoryFnReactReturnType from @storybook/react [#20](https://github.com/storybookjs/testing-react/pull/20) ([@ljcl](https://github.com/ljcl))

#### Authors: 1

- Luke Clark ([@ljcl](https://github.com/ljcl))

---

# v0.0.13 (Fri May 21 2021)

#### 🐛 Bug Fix

- fix: ignore __esModules flag when composing stories [#22](https://github.com/storybookjs/testing-react/pull/22) ([@yannbf](https://github.com/yannbf))

#### Authors: 1

- Yann Braga ([@yannbf](https://github.com/yannbf))

---

# v0.0.13 (Fri May 21 2021)

#### 🐛 Bug Fix

- fix: ignore __esModules flag when composing stories [#22](https://github.com/storybookjs/testing-react/pull/22) ([@yannbf](https://github.com/yannbf))

#### Authors: 1

- Yann Braga ([@yannbf](https://github.com/yannbf))

---

# v0.0.12 (Wed May 12 2021)

#### 🐛 Bug Fix

- fix: module field should point to a real file [#21](https://github.com/storybookjs/testing-react/pull/21) ([@elevatebart](https://github.com/elevatebart))

#### Authors: 1

- Barthélémy Ledoux ([@elevatebart](https://github.com/elevatebart))

---

# v0.0.11 (Sat May 08 2021)

#### 🐛 Bug Fix

- fix: throw error on unsupported formats [#18](https://github.com/storybookjs/testing-react/pull/18) ([@yannbf](https://github.com/yannbf))

#### Authors: 1

- Yann Braga ([@yannbf](https://github.com/yannbf))

---

# v0.0.10 (Mon Apr 05 2021)

#### 🐛 Bug Fix

- fix: support addons that use channel api [#14](https://github.com/storybookjs/testing-react/pull/14) ([@yannbf](https://github.com/yannbf))

#### Authors: 1

- Yann Braga ([@yannbf](https://github.com/yannbf))

---

# v0.0.9 (Tue Mar 30 2021)

#### 🐛 Bug Fix

- Fix: properly handle global types support [#11](https://github.com/storybookjs/testing-react/pull/11) ([@yannbf](https://github.com/yannbf))

#### Authors: 1

- Yann Braga ([@yannbf](https://github.com/yannbf))

---

# v0.0.8 (Tue Mar 30 2021)

#### 🐛 Bug Fix

- chore: update package url [#10](https://github.com/storybookjs/testing-react/pull/10) ([@yannbf](https://github.com/yannbf))

#### Authors: 1

- Yann Braga ([@yannbf](https://github.com/yannbf))

---

# v0.0.7 (Tue Mar 30 2021)

#### 🐛 Bug Fix

- Fix: compose stories with partial props [#9](https://github.com/storybookjs/testing-react/pull/9) ([@yannbf](https://github.com/yannbf))
- Update Button.stories.tsx [#6](https://github.com/storybookjs/testing-react/pull/6) ([@nativedone](https://github.com/nativedone))

#### Authors: 2

- AD Amorim ([@nativedone](https://github.com/nativedone))
- Yann Braga ([@yannbf](https://github.com/yannbf))

---

# v0.0.6 (Mon Mar 22 2021)

#### 🐛 Bug Fix

- Update README.md [#5](https://github.com/storybookjs/testing-react/pull/5) ([@diegohaz](https://github.com/diegohaz))

#### Authors: 1

- Haz ([@diegohaz](https://github.com/diegohaz))

---

# v0.0.5 (Fri Mar 19 2021)

#### 🐛 Bug Fix

- docs: fix wrong import in instructions [#3](https://github.com/storybookjs/testing-react/pull/3) ([@yannbf](https://github.com/yannbf))

#### Authors: 1

- Yann Braga ([@yannbf](https://github.com/yannbf))

---

# v0.0.4 (Fri Mar 19 2021)

#### 🐛 Bug Fix

- chore: update package name [#2](https://github.com/storybookjs/react-testing/pull/2) ([@yannbf](https://github.com/yannbf))

#### Authors: 1

- Yann Braga ([@yannbf](https://github.com/yannbf))

---

# v0.0.3 (Wed Mar 17 2021)

#### ⚠️ Pushed to `main`

- chore: add .env to gitignore (yannbf@gmail.com)
- fix(docs): use correct lib name in tsdoc (yannbf@gmail.com)
- chore(package): update project meta (yannbf@gmail.com)
- docs(README): add project description (yannbf@gmail.com)

#### Authors: 1

- Yann Braga ([@yannbf](https://github.com/yannbf))

---

# v0.0.2 (Tue Mar 16 2021)

#### ⚠️ Pushed to `main`

- Rename to react-testing ([@shilman](https://github.com/shilman))
- Initial version ([@yannbf](https://github.com/yannbf))

#### Authors: 2

- Michael Shilman ([@shilman](https://github.com/shilman))
- Yann Braga ([@yannbf](https://github.com/yannbf))

---

# 0.0.1

Initial version
