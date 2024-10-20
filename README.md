# HW-SQL-09.10.24
-- HW 09.10.24
-- -----------------------------------------------------------------

-- Создайте таблицу goods (id, title, quantity)

CREATE TABLE goods (
    id SERIAL PRIMARY KEY,
    title VARCHAR(255) NOT NULL,
    quantity INTEGER NOT NULL
);

SELECT
* 
FROM goods;

-- Добавьте несколько строк

INSERT INTO goods (title, quantity) VALUES 
('Product A', 10),
('Product B', 5),
('Product C', 8),
('Product D', 20),
('Product E', 15),
('Product F', 4),
('Product G', 3),
('Product I', 17);

-- Добавьте поле price (integer) со значением по умолчанию 0

ALTER TABLE goods
ADD COLUMN price INTEGER DEFAULT 0;

-- Проверьте содержимое таблицы

SELECT
* 
FROM goods;

-- Измените тип на numeric(8, 2)

ALTER TABLE goods
ALTER COLUMN price TYPE numeric(8, 2); -- вот тут не могу понять задание...

-- Измените тип обратно на integer

ALTER TABLE goods
ALTER COLUMN price TYPE integer USING price::integer; -- вот тут не могу понять задание...

-- Переименуйте поле на item_price

ALTER TABLE goods
RENAME COLUMN price TO item_price;

-- Удалите это поле

ALTER TABLE goods
DROP COLUMN item_price;
