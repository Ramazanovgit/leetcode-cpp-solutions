 # Group Anagrams
  ## Исходные данные и условия
  Сложность: Medium
  
https://leetcode.com/problems/group-anagrams/description/
  ## Решение
  `unordered_map<string, vector<string>> groups;` - Создаем hash map
  
   ```
   for (string str : strs){
            string key = str;
            sort(key.begin(), key.end());
            groups[key].push_back(str);
        }
  ```
  Начинаем цикл, где `str` будет получать значения `string` из `strs`
  
  Создаем параметр `key` чтобы использовать её для группировки анаграмм и не изменять исходную `str`
  
  Сортируем `key`, чтобы у одинаковых анаграмм получался одинаковый ключ. Пример: "eat","tea" станет "aet","aet", т.е. один ключ.

  ```
   vector<vector<string>> result;
        for (auto& pair : groups){
            result.push_back(pair.second);
        }
  ```
  Создаем массив, который будем выводить `result`

  Начинаем цикл для значений pair для каждой пары ключ-значение

  Заносим в `result` значения без ключа `pair.second`
  
  `return(result);` - Выводим результат
