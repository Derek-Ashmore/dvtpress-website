# Command templates

> Command prompt base
```
npx claude-flow swarm "" --claude
```

> Plan instruction
```
npx claude-flow swarm "What information do you need to add a book to the static website in the site folder? Put the information in the plans folder. Don't change the website yet. What format would it be easiest for you to accept the information about the new book?" --claude
```

> Plan implementation
```
npx claude-flow swarm "Please add book documented in Mastering-the-Shift.md to the website. Please make the new book the default book displayed on the Home page. Follow the plan you outlined in implementation-guide.md and execute steps 3, 4, and 5. Please let me know if you need additional information." --claude
```

```
npx claude-flow swarm "Please changed the book documented in Mastering-the-Shift.md to the website. Please reflect those changes in the website. Please let me know if you need additional information." --claude
```
