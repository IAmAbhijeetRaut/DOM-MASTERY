Centering a `div` (or any other HTML element) is a common task in web design, and there are several ways to achieve it, depending on whether you want to center it horizontally, vertically, or both. Below are the various methods you can use to center a `div`.

### 1. **Centering a `div` Horizontally**

#### A. **Using `text-align: center;` (Inline or Inline-Block Elements Only)**
- **Description**: This method centers inline or inline-block elements horizontally inside a block-level container.
- **Code Example**:
  ```html
  <div style="text-align: center;">
    <div style="display: inline-block;">Centered Div</div>
  </div>
  ```

#### B. **Using `margin: 0 auto;`**
- **Description**: This method works when the `div` has a fixed width. It sets the left and right margins to `auto`, centering the `div` horizontally within its container.
- **Code Example**:
  ```html
  <div style="width: 50%; margin: 0 auto;">Centered Div</div>
  ```

#### C. **Using Flexbox**
- **Description**: With Flexbox, centering is straightforward and does not require a fixed width.
- **Code Example**:
  ```html
  <div style="display: flex; justify-content: center;">
    <div>Centered Div</div>
  </div>
  ```

### 2. **Centering a `div` Vertically**

#### A. **Using Flexbox**
- **Description**: Flexbox is one of the easiest ways to vertically center a `div`.
- **Code Example**:
  ```html
  <div style="display: flex; align-items: center; height: 100vh;">
    <div>Centered Div</div>
  </div>
  ```

#### B. **Using CSS Grid**
- **Description**: CSS Grid can center elements both horizontally and vertically.
- **Code Example**:
  ```html
  <div style="display: grid; height: 100vh; place-items: center;">
    <div>Centered Div</div>
  </div>
  ```

#### C. **Using `position: absolute;` and `transform`**
- **Description**: This method involves absolutely positioning the `div` and using the `transform` property to shift it by 50% of its width and height.
- **Code Example**:
  ```html
  <div style="position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%);">
    Centered Div
  </div>
  ```

### 3. **Centering a `div` Both Horizontally and Vertically**

#### A. **Using Flexbox**
- **Description**: Flexbox can easily center a `div` both horizontally and vertically.
- **Code Example**:
  ```html
  <div style="display: flex; justify-content: center; align-items: center; height: 100vh;">
    <div>Centered Div</div>
  </div>
  ```

#### B. **Using CSS Grid**
- **Description**: CSS Grid simplifies the centering of a `div` in both directions.
- **Code Example**:
  ```html
  <div style="display: grid; height: 100vh; place-items: center;">
    <div>Centered Div</div>
  </div>
  ```

#### C. **Using `position: absolute;` and `transform`**
- **Description**: This method is useful when you cannot use Flexbox or CSS Grid.
- **Code Example**:
  ```html
  <div style="position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%);">
    Centered Div
  </div>
  ```

#### D. **Using Table Display**
- **Description**: This older method involves setting the container to behave like a table cell and the `div` as its content.
- **Code Example**:
  ```html
  <div style="display: table; width: 100%; height: 100vh;">
    <div style="display: table-cell; text-align: center; vertical-align: middle;">
      Centered Div
    </div>
  </div>
  ```

#### E. **Using Inline Block and Vertical Align**
- **Description**: This method uses `inline-block` elements with `vertical-align` but requires additional wrappers.
- **Code Example**:
  ```html
  <div style="height: 100vh; text-align: center;">
    <span style="display: inline-block; height: 100%; vertical-align: middle;"></span>
    <div style="display: inline-block; vertical-align: middle;">Centered Div</div>
  </div>
  ```

### Summary

- **Horizontal Centering**: Use `margin: 0 auto;`, `text-align: center;`, or Flexbox (`justify-content: center`).
- **Vertical Centering**: Use Flexbox (`align-items: center`), CSS Grid (`place-items: center`), or `position: absolute;` with `transform`.
- **Both Horizontal and Vertical Centering**: Flexbox, CSS Grid, or `position: absolute;` with `transform` are the most modern and flexible approaches.

These methods give you a variety of tools to center a `div` based on your specific needs and the layout context you're working within.
