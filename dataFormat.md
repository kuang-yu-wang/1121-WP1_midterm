### Table 創立。

上面是SQL指令，下面是JSON回傳的格式。
```SQL
CREATE TABLE blog (
	id	int,
	categories	text,
	title	text,
	img		text,
	img_local	text,
	content		text
);
```
```JSON
{
  "id": 0,
  "categories": "",
  "title":"",
  "img":"",
  "img_local":"",
  "content":""
}
```

### 測資。

```
我要總共12筆資料。
需求如下。
資料格式為JSON格式，全部以英文撰寫。
主題有四種，分別是“Life Style”、"Tech"、"Self Improvement"、"News"。
格式如下：
1. ID，欄位名稱為"id"，格式使用整數。
2. 主題，欄位名稱為"categories"，格式使用字串，從上面主題隨機選擇，但必須保證每個主題約等量。
3. 標題，欄位名稱為“title”，格式使用字串，從選擇的主題發想並下標。
4. 圖片，欄位名稱為"img"，格式使用字串，根據選擇的標題去Unsplash進行查找。
5. 本地圖片，欄位名稱為"img_local"，格式使用字串，保持內容空值即可。
6. 內容，欄位名稱為"content"，格式使用字串。根據選擇的標題進行撰寫，保持25字左右。
```

```JSON
[
  {
    "id": 1,
    "categories": "Life Style",
    "title": "5 Tips for a Healthier Lifestyle",
    "img": "https://unsplash.com/photos/woman-doing-yoga-meditation-on-brown-parquet-flooring-NTyBbu66_SI",
    "img_local": "./DataImages/img-01.jpg",
    "content": "Drink more water, eat more fruits and vegetables, exercise regularly, get enough sleep, and reduce stress."
  },
  {
    "id": 2,
    "categories": "Tech",
    "title": "The Future of Artificial Intelligence",
    "img": "https://unsplash.com/photos/vintage-gray-game-console-and-joystick-p0j-mE6mGo4",
    "img_local": "./DataImages/img-02.jpg",
    "content": "Artificial intelligence will continue to advance and become more integrated into our daily lives, from self-driving cars to personalized healthcare."
  },
  {
    "id": 3,
    "categories": "Self Improvement",
    "title": "5 Habits of Highly Successful People",
    "img": "https://unsplash.com/photos/person-holding-photo-of-person-sitting-near-tree-xVtP6azF-jk",
    "img_local": "./DataImages/img-03.jpg",
    "content": "Wake up early, set goals, prioritize tasks, learn continuously, and take action."
  },
  {
    "id": 4,
    "categories": "News",
    "title": "COVID-19 Vaccines: What You Need to Know",
    "img": "https://unsplash.com/photos/man-sitting-on-chair-holding-newspaper-on-fire-FPNnKfjcbNU",
    "img_local": "./DataImages/img-04.jpg",
    "content": "COVID-19 vaccines are safe and effective, and getting vaccinated is an important step in ending the pandemic."
  },
  {
    "id": 5,
    "categories": "Life Style",
    "title": "How to Stay Motivated to Exercise",
    "img": "https://unsplash.com/photos/woman-on-hammock-near-to-river-KYTT8L5JLDs",
    "img_local": "./DataImages/img-05.jpg",
    "content": "Find a workout buddy, set achievable goals, mix up your routine, reward yourself, and track your progress."
  },
  {
    "id": 6,
    "categories": "Tech",
    "title": "The Benefits of Cloud Computing",
    "img": "https://unsplash.com/photos/person-using-macbook-pro-npxXWgQ33ZQ",
    "img_local": "./DataImages/img-06.jpg",
    "content": "Cloud computing allows for greater flexibility, scalability, and cost savings for businesses of all sizes."
  },
  {
    "id": 7,
    "categories": "Self Improvement",
    "title": "The Power of Positive Thinking",
    "img": "https://unsplash.com/photos/flowers-on-persons-hand-R9rIQVa1wWA",
    "img_local": "./DataImages/img-07.jpg",
    "content": "Positive thinking can improve your mental and physical health, increase your resilience, and help you achieve your goals."
  },
  {
    "id": 8,
    "categories": "News",
    "title": "Climate Change: What You Need to Know",
    "img": "https://unsplash.com/photos/person-holding-black-ipad-iFSvn82XfGo",
    "img_local": "./DataImages/img-08.jpg",
    "content": "Climate change is a global crisis that requires urgent action to reduce greenhouse gas emissions and protect the planet."
  },
  {
    "id": 9,
    "categories": "Life Style",
    "title": "Healthy Eating on a Budget",
    "img": "https://unsplash.com/photos/two-man-carrying-backpacks-during-daytime-M1aegHe2j6g",
    "img_local": "./DataImages/img-09.jpg",
    "content": "Plan your meals, buy in bulk, cook at home, and choose whole foods over processed foods to eat healthy on a budget."
  },
  {
    "id": 10,
    "categories": "Tech",
    "title": "The Rise of 5G Technology",
    "img": "https://unsplash.com/photos/black-and-white-robot-toy-on-red-wooden-table-zwd435-ewb4",
    "img_local": "./DataImages/img-10.jpg",
    "content": "5G technology will revolutionize the way we connect and communicate, enabling faster speeds, lower latency, and greater reliability."
  },
  {
    "id": 11,
    "categories": "Self Improvement",
    "title": "The Importance of Time Management",
    "img": "https://unsplash.com/photos/shallow-focus-photography-of-camera-len-bY3mrCYI2KM",
    "img_local": "./DataImages/img-11.jpg",
    "content": "Effective time management can reduce stress, increase productivity, and help you achieve your goals."
  },
  {
    "id": 12,
    "categories": "News",
    "title": "The Future of Work: Remote vs. In-Person",
    "img": "https://unsplash.com/photos/magazines-displayed-on-a-rack-2G8mnFvH8xk",
    "img_local": "./DataImages/img-12.jpg",
    "content": "The COVID-19 pandemic has accelerated the shift towards remote work, but in-person work will still have a place in the future of work."
  }
]
```

### Insert data into database
```
在下面將這12筆資料轉變成Postgres SQL Insert 語法，順序按照id排序。
```

```SQL
INSERT INTO blog (id, categories, title, img, img_local, content) VALUES
  (1, 'Life Style', '5 Tips for a Healthier Lifestyle', 'https://unsplash.com/photos/woman-doing-yoga-meditation-on-brown-parquet-flooring-NTyBbu66_SI', './DataImages/img-01.jpg', 'Drink more water, eat more fruits and vegetables, exercise regularly, get enough sleep, and reduce stress.'),
  (2, 'Tech', 'The Future of Artificial Intelligence', 'https://unsplash.com/photos/vintage-gray-game-console-and-joystick-p0j-mE6mGo4', './DataImages/img-02.jpg', 'Artificial intelligence will continue to advance and become more integrated into our daily lives, from self-driving cars to personalized healthcare.'),
  (3, 'Self Improvement', '5 Habits of Highly Successful People', 'https://unsplash.com/photos/person-holding-photo-of-person-sitting-near-tree-xVtP6azF-jk', './DataImages/img-03.jpg', 'Wake up early, set goals, prioritize tasks, learn continuously, and take action.'),
  (4, 'News', 'COVID-19 Vaccines: What You Need to Know', 'https://unsplash.com/photos/man-sitting-on-chair-holding-newspaper-on-fire-FPNnKfjcbNU', './DataImages/img-04.jpg', 'COVID-19 vaccines are safe and effective, and getting vaccinated is an important step in ending the pandemic.'),
  (5, 'Life Style', 'How to Stay Motivated to Exercise', 'https://unsplash.com/photos/woman-on-hammock-near-to-river-KYTT8L5JLDs', './DataImages/img-05.jpg', 'Find a workout buddy, set achievable goals, mix up your routine, reward yourself, and track your progress.'),
  (6, 'Tech', 'The Benefits of Cloud Computing', 'https://unsplash.com/photos/person-using-macbook-pro-npxXWgQ33ZQ', './DataImages/img-06.jpg', 'Cloud computing allows for greater flexibility, scalability, and cost savings for businesses of all sizes.'),
  (7, 'Self Improvement', 'The Power of Positive Thinking', 'https://unsplash.com/photos/flowers-on-persons-hand-R9rIQVa1wWA', './DataImages/img-07.jpg', 'Positive thinking can improve your mental and physical health, increase your resilience, and help you achieve your goals.'),
  (8, 'News', 'Climate Change: What You Need to Know', 'https://unsplash.com/photos/person-holding-black-ipad-iFSvn82XfGo', './DataImages/img-08.jpg', 'Climate change is a global crisis that requires urgent action to reduce greenhouse gas emissions and protect the planet.'),
  (9, 'Life Style', 'Healthy Eating on a Budget', 'https://unsplash.com/photos/two-man-carrying-backpacks-during-daytime-M1aegHe2j6g', './DataImages/img-09.jpg', 'Plan your meals, buy in bulk, cook at home, and choose whole foods over processed foods to eat healthy on a budget.'),
  (10, 'Tech', 'The Rise of 5G Technology', 'https://unsplash.com/photos/black-and-white-robot-toy-on-red-wooden-table-zwd435-ewb4', './DataImages/img-10.jpg', '5G technology will revolutionize the way we connect and communicate, enabling faster speeds, lower latency, and greater reliability.'),
  (11, 'Self Improvement', 'The Importance of Time Management', 'https://unsplash.com/photos/shallow-focus-photography-of-camera-len-bY3mrCYI2KM', './DataImages/img-11.jpg', 'Effective time management can reduce stress, increase productivity, and help you achieve your goals.'),
  (12, 'News', 'The Future of Work: Remote vs. In-Person', 'https://unsplash.com/photos/magazines-displayed-on-a-rack-2G8mnFvH8xk', './DataImages/img-12.jpg', 'The COVID-19 pandemic has accelerated the shift towards remote work, but in-person work will still have a place in the future of work.');
```
