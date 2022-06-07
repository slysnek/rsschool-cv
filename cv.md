# Kirill Volkov
## Contacts
* **E-mail:** bloodwingest@gmail.com
* **Telegram:** @screwpassenger
## Skills
* **HTML, CSS, Bootstrap**
* **Javascript**
* **Python, Flask**
* **Adobe Photoshop, Figma**
* **SQL**
* **Git**
## Code example
*A small part of the code from my web-project written on Flask describing the innerworkings of signing up:*
```
@auth.route("/sign-up", methods=['GET', 'POST'])
def sign_up():
    if request.method == "POST":
        email = request.form.get("email")
        username = request.form.get("username")
        password1 = request.form.get("password1")
        password2 = request.form.get("password2")

        email_exists = User.query.filter_by(email=email).first()
        username_exists = User.query.filter_by(username=username).first()

        if email_exists:
            flash('Email is already in use', category='error')
        elif username_exists:
            flash('Username is already in use', category='error')
        elif password1 != password2:
            flash('Password don\'t match', category='error')
        elif len(username) < 2:
            flash('Username is too short.', category = 'error')
        elif len(password1) < 6:
            flash('Password is too short.', category = 'error')
        elif len(email) < 4:
            flash("Email is invalid", category='error')
        else:
            new_user = User(email=email, username=username, password=generate_password_hash(password1, method='sha256'))
            db.session.add(new_user)
            db.session.commit()
            login_user(new_user, remember=True)
            flash('User created!')
            return redirect(url_for('views.home'))

    return render_template("signup.html", user = current_user)
```
## Education
Graduated with honors from **LUNN** (Linguistic University of Nizhniy Novgorod)
## Courses
* **CS50X 2022**
* **RSSchool Front-end course**
* **Hexlet Courses**
* **Innumerable tutorials on YouTube, Udemy, etc.**
## Languages
* **English:** C1 (also worked as a private tutor, therefore I have solid teaching experience and language practice)
* **German:** A2-B1
* **Russian:** Native

