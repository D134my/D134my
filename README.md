```cpp
#include <algorithm>
#include <format>
#include <iostream>
#include <ranges>
#include <vector>

using namespace std::string_literals;

auto main() -> int {

  auto const about_me =
      [](std::vector<std::string> &&technologies) noexcept -> std::nullptr_t {
    std::cout << "I'm learning : ";
    std::ranges::copy(technologies,
                      std::ostream_iterator<std::string>(std::cout, " "));
    return {};
  }([](int age) noexcept {
    std::cout << "I am " << age << " years old." << '\n';
    return std::vector{"C++"s, "Qt"s};
  }([](std::string const &name) {
    std::cout << std::format("Hi my name is {} <3\n", name);
    return 20;
  }([]() noexcept { return std::string("Dreamy"); }()

        )));

  return 0;
}
```
