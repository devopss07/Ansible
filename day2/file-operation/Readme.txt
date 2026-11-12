Goal: To send out index.html to Nginx Path
search copy modules here: https://docs.ansible.com/projects/ansible/latest/search.html?q=copy&check_keywords=yes&area=default
#IN VS code use indentation correction: Click anywhere on that line and press Ctrl + ]
# ansible-playbook -i hosts.ini nginx_playbook.yml

Yes! Ansible's copy module replaces the existing index.html file if the source file has different content.

# For example:
# - name: Copy custom HTML file
#   ansible.builtin.copy:
#     src: ./index.html
#     dest: /var/www/html/index.html

#Ansible sysntax check:
#nsible-playbook --syntax-check nginx.yml