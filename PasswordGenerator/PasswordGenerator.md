## Password Generator Code
```markdown
import string
import random

def pw_gen(size = 8, chars=string.ascii_letters + string.digits + string.punctuation):
	return ''.join(random.choice(chars) for _ in range(size))

print(pw_gen(int(input('How many characters in your password?'))))
```

>  <a href="https://theresiap.github.io/Personal-Project/PasswordGenerator/">Return To Previous Page</a>
