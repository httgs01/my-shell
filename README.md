# my-shell

Ansible setup for Ubuntu: zsh, Oh My Zsh, Starship, fzf, autosuggestions, and syntax highlighting.

Configures existing login users and `/etc/skel` for new users. Requires Ansible and SSH access with root or sudo privileges.

```bash
cp -n inventory.example.ini inventory.ini
# Edit inventory.ini with your hosts.
ansible-playbook setup.yml
```

Use `-K` if sudo requires a password. Customize `vars.yml` and the configs in `files/`.
