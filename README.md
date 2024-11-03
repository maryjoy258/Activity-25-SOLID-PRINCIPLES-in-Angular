# Activity-25-SOLID-PRINCIPLES-in-Angular# SOLID Principles in Angular

## Introduction

The SOLID principles are a set of five design principles intended to make software designs more understandable, flexible, and maintainable. These principles are particularly valuable in Angular development, where modularity and reusability are essential.

## 1. Single Responsibility Principle (SRP)

### Definition
A class should have only one reason to change, meaning it should only have one job or responsibility.

### Application in Angular
In Angular, this principle can be applied by ensuring that each component or service has a single responsibility.

### Example Code
```typescript
// Bad Example
@Component({
  selector: 'app-user',
  templateUrl: './user.component.html',
})
export class UserComponent {
  constructor(private userService: UserService) {}

  getUser() {}
  saveUser() {}
}

// Good Example
@Component({
  selector: 'app-user',
  templateUrl: './user.component.html',
})
export class UserComponent {
  constructor(private userService: UserService) {}

  getUser() {
    return this.userService.fetchUser();
  }

  saveUser(user: User) {
    return this.userService.saveUser(user);
  }
}
