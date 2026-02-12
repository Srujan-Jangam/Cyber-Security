### Event: ###

Multiple failed login attempts detected.

### Why Suspicious: ###

High frequency indicates password guessing.

### What I Checked: ###

Authentication logs via journalctl/lightdm.

### Risk: ###

Unauthorized access attempt.

### What If Success Followed? ###

Immediate escalation required.

### Recommended Response:

- Monitor login attempts
- Lock account
- Block source if remote
- Alert security team