# Key store for NumPy

## Initial vault creation

```
./vpass init <your-gpg-id>
```

Ignore pathspec errors.

## Add/edit a new password

```
./vpass add "Name of Password"
./vpass edit "Name of Password"
```

See https://www.passwordstore.org/ for further detail.

## Add a new recipient

1. Find the GPG key ID of the recipient.  This will be a hexadecimal
   string similar to `79DFFEFC5EC506356B7BCF00E5FEBCA4A034DD65`, and
   can be found with:

   ```
   gpg --list-key user@email.com
   ```

2. Edit `vault/.gpg-id` and add the key UID to the list.

3. Re-encode the vault:

   ```
   ./vencrypt
   ```

4. Commit changes and push to GitHub

## List existing recipients

```
./vlist
```
