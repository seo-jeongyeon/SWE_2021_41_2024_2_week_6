# SWE_2021_41_2024_2_week_6

## Week 4 Assignment
- https://github.com/seo-jeongyeon/-SWE_2021_41_2024_2_week_4
```
  def isHappy(n):
    def get_next_number(num):
        sum = 0
        while num > 0:
            digit = num % 10
            sum += digit * digit
            num //= 10
        return sum

    repeat_num_set = set()

    while n != 1 and n not in repeat_num_set:
        repeat_num_set.add(n)
        n = get_next_number(n)

    return n == 1
```
- The function **isHappy(n)** checks if a given number n is a happy number. A happy number is defined as a number where repeatedly summing the squares of its digits eventually leads to 1.
  1. **get_next_number(num)**: This helper function takes a number, squares each of its digits, and returns their sum.
  2. The isHappy function keeps track of numbers encountered during the process in a set called repeat_num_set to avoid infinite loops.
  3. The loop continues until either the number becomes 1 (which means it's a happy number) or a cycle is detected, in which case it returns False, indicating the number is not happy.

## Week 5 Assignment
> ```
> docker exec ossp-container cat /etc/os-release
> ```
> This command runs **cat /etc/os-release** inside the Docker container named **ossp-container**. It displays the contents of the **/etc/os-release** file, and it provides information about the operating system running inside the container.
> - output
> ```
> PRETTY_NAME="Ubuntu 24.04.1 LTS"
> NAME="Ubuntu"
> VERSION_ID="24.04"
> VERSION="24.04.1 LTS (Noble Numbat)"
> VERSION CODENAME=noble
> ID=ubuntu
> ID LIKE=debian
> HOME_URL="https://www.ubuntu.com/"
> SUPPORT_URL="https://help.ubuntu.com/"
> BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
> PRIVACY _POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
> UBUNTU CODENAME=noble
> LOGO=ubuntu-logo
> ```

> ```
> docker exec ossp-container git --version
> ```
> This command runs **git --version** inside the Docker container named **ossp-container**. It displays the version of Git installed in the container.
> - output
> ```
> \git version 2.43.0
> ```

> ```
> docker exec ossp-container python3 --version
> ```
> This command runs **python3 --version** inside the Docker container named **ossp-container**. It displays the version of Python 3 installed in the container.
> ```
> Python 3.12.3
> ```

> ```
> docker inspect --format=" {{ .HostConfig.Binds }}" ossp-container
> ```
> This command shows the bind mounts (host-to-container file/directory mappings) for the **ossp-container** using Docker’s inspect command.
> - output
> ```
> [/Users/seojeong-yeon/ossp_host_dir:/mnt/ossp_container_dir]
> ```
