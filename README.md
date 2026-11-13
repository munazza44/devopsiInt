<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <meta name="theme-color" content="#f6f7fb">
  <title>Create your account</title>
  <style>
    :root {
      color-scheme: light;
      font-family: Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
      color: #172033;
      background: #f6f7fb;
      font-synthesis: none;
      text-rendering: optimizeLegibility;
    }

    * { box-sizing: border-box; }
    body {
      min-height: 100vh;
      margin: 0;
      display: grid;
      place-items: center;
      padding: 32px 16px;
      background: radial-gradient(circle at 12% 10%, #e8edff 0, transparent 32%), #f6f7fb;
    }

    .card {
      width: min(100%, 460px);
      padding: 40px;
      border: 1px solid #e8eaf1;
      border-radius: 20px;
      background: #fff;
      box-shadow: 0 20px 60px rgb(34 48 86 / 10%);
    }

    .brand {
      display: inline-flex;
      align-items: center;
      gap: 10px;
      margin-bottom: 30px;
      color: #263b91;
      font-size: 15px;
      font-weight: 750;
      letter-spacing: .02em;
    }

    .brand-mark {
      display: grid;
      width: 34px;
      height: 34px;
      place-items: center;
      border-radius: 10px;
      color: #fff;
      background: #5368d8;
      font-size: 18px;
    }

    h1 { margin: 0 0 8px; font-size: clamp(26px, 5vw, 32px); letter-spacing: -.04em; }
    .intro { margin: 0 0 28px; color: #697386; line-height: 1.55; }
    .field { margin-bottom: 18px; }
    label { display: block; margin-bottom: 7px; font-size: 14px; font-weight: 650; }
    input {
      width: 100%;
      min-height: 46px;
      padding: 11px 13px;
      border: 1px solid #d9deea;
      border-radius: 9px;
      outline: none;
      color: inherit;
      background: #fff;
      font: inherit;
      transition: border-color .15s, box-shadow .15s;
    }
    input::placeholder { color: #a0a7b5; }
    input:focus { border-color: #5368d8; box-shadow: 0 0 0 3px rgb(83 104 216 / 15%); }
    input[aria-invalid="true"] { border-color: #c83d4d; }

    .password-wrap { position: relative; }
    .password-wrap input { padding-right: 72px; }
    .toggle-password {
      position: absolute;
      top: 50%;
      right: 12px;
      padding: 4px;
      transform: translateY(-50%);
      border: 0;
      color: #5368d8;
      background: transparent;
      font: inherit;
      font-size: 13px;
      font-weight: 650;
      cursor: pointer;
    }

    .hint, .error { margin: 6px 0 0; font-size: 12px; line-height: 1.4; }
    .hint { color: #788195; }
    .error { color: #b42332; }
    .terms { display: flex; align-items: flex-start; gap: 10px; margin: 22px 0; color: #697386; font-size: 13px; line-height: 1.5; }
    .terms input { width: 16px; min-height: 16px; margin: 2px 0 0; accent-color: #5368d8; }
    a { color: #465bc7; text-decoration: none; }
    a:hover { text-decoration: underline; }

    .submit {
      width: 100%;
      min-height: 48px;
      border: 0;
      border-radius: 9px;
      color: #fff;
      background: #5368d8;
      font: inherit;
      font-weight: 700;
      cursor: pointer;
      transition: background .15s, transform .15s;
    }
    .submit:hover { background: #4055c4; }
    .submit:active { transform: translateY(1px); }
    .submit:focus-visible, .toggle-password:focus-visible, a:focus-visible { outline: 3px solid #aeb8ff; outline-offset: 3px; }
    .signin { margin: 22px 0 0; color: #697386; text-align: center; font-size: 14px; }
    .notice { display: none; margin: 0 0 18px; padding: 12px 14px; border-radius: 9px; color: #17613c; background: #eaf7ef; font-size: 14px; line-height: 1.45; }
    .notice.show { display: block; }

    @media (max-width: 480px) {
      .card { padding: 30px 22px; border-radius: 16px; }
      .brand { margin-bottom: 24px; }
    }
  </style>
</head>
<body>
  <main class="card">
    <a class="brand" href="#" aria-label="Devopint home">
      <span class="brand-mark" aria-hidden="true">D</span>
      <span>devopint</span>
    </a>

    <h1>Create your account</h1>
    <p class="intro">Get started with Devopint. It only takes a minute.</p>

    <p class="notice" id="success-notice" role="status" aria-live="polite"></p>

    <form id="signup-form" novalidate>
      <div class="field">
        <label for="name">Full name</label>
        <input id="name" name="name" type="text" autocomplete="name" placeholder="Jane Smith" required minlength="2">
        <p class="error" id="name-error" hidden></p>
      </div>

      <div class="field">
        <label for="email">Email address</label>
        <input id="email" name="email" type="email" autocomplete="email" placeholder="you@example.com" required>
        <p class="error" id="email-error" hidden></p>
      </div>

      <div class="field">
        <label for="password">Password</label>
        <div class="password-wrap">
          <input id="password" name="password" type="password" autocomplete="new-password" placeholder="Create a password" required minlength="8" aria-describedby="password-hint">
          <button class="toggle-password" type="button" aria-controls="password" aria-pressed="false">Show</button>
        </div>
        <p class="hint" id="password-hint">Use at least 8 characters.</p>
        <p class="error" id="password-error" hidden></p>
      </div>

      <div class="field">
        <label for="confirm-password">Confirm password</label>
        <input id="confirm-password" name="confirmPassword" type="password" autocomplete="new-password" placeholder="Enter your password again" required>
        <p class="error" id="confirm-password-error" hidden></p>
      </div>

      <label class="terms" for="terms">
        <input id="terms" name="terms" type="checkbox" required>
        <span>I agree to the <a href="#terms">Terms of Service</a> and <a href="#privacy">Privacy Policy</a>.</span>
      </label>
      <p class="error" id="terms-error" hidden></p>

      <button class="submit" type="submit">Create account</button>
    </form>

    <p class="signin">Already have an account? <a href="#login">Sign in</a></p>
  </main>

  <script>
    const form = document.querySelector('#signup-form');
    const notice = document.querySelector('#success-notice');
    const password = document.querySelector('#password');
    const confirmPassword = document.querySelector('#confirm-password');

    document.querySelector('.toggle-password').addEventListener('click', (event) => {
      const button = event.currentTarget;
      const showing = password.type === 'text';
      password.type = showing ? 'password' : 'text';
      button.textContent = showing ? 'Show' : 'Hide';
      button.setAttribute('aria-pressed', String(!showing));
    });

    function setError(input, message) {
      const error = document.querySelector(`#${input.id}-error`);
      error.textContent = message;
      error.hidden = !message;
      input.setAttribute('aria-invalid', String(Boolean(message)));
      return !message;
    }

    form.addEventListener('submit', (event) => {
      event.preventDefault();
      notice.classList.remove('show');

      const nameValid = setError(
        document.querySelector('#name'),
        document.querySelector('#name').value.trim().length >= 2 ? '' : 'Please enter your name.'
      );
      const email = document.querySelector('#email');
      const emailValid = setError(email, email.validity.valid ? '' : 'Enter a valid email address.');
      const passwordValid = setError(password, password.value.length >= 8 ? '' : 'Password must be at least 8 characters.');
      const confirmationValid = setError(confirmPassword, confirmPassword.value === password.value ? '' : 'Passwords do not match.');
      const terms = document.querySelector('#terms');
      const termsError = document.querySelector('#terms-error');
      termsError.textContent = terms.checked ? '' : 'Please accept the terms to continue.';
      termsError.hidden = terms.checked;

      if (!nameValid || !emailValid || !passwordValid || !confirmationValid || !terms.checked) return;

      notice.textContent = 'Your details are valid. Connect this form to a backend to create and save accounts.';
      notice.classList.add('show');
      form.reset();
      document.querySelectorAll('input[aria-invalid]').forEach((input) => input.removeAttribute('aria-invalid'));
    });
  </script>
</body>
</html>
