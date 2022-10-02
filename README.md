# Migration
## Легенда
нужно смигрировать ваше приложение на сервлетах, написанное в предыдущих ДЗ на Spring Web MVC с Embed Tomcat.

## Задача
Создайте новый проект на базе Spring MVC и Embed Tomcat и перенесите реализованную в предыдущих ДЗ функциональность.

Ваш контроллер должен выглядеть именно так, как в лекции:

``` @RestController
@RequestMapping("/api/posts")
public class PostController {
  private final PostService service;

  public PostController(PostService service) {
    this.service = service;
  }

  @GetMapping
  public List<Post> all() {
    return service.all();
  }

  @GetMapping("/{id}")
  public Post getById(@PathVariable long id) {
    return service.getById(id);
  }

  @PostMapping
  public Post save(@RequestBody Post post) {
    return service.save(post);
  }

  @DeleteMapping("/{id}")
  public void removeById(long id) {
    service.removeById(id);
  }
}
```

Обратите внимание, что вся функциональность (CRUD), реализованная до этого, должна по-прежнему работать.
