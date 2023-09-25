# cassandra fundamentals 

===========================================
```
INSERT INTO videos (video_id, added_date, title)
VALUES (1645ea59-14bd-11e5-a993-8138354b7e31 , '2014-01-29', 'Cassandra History');

INSERT INTO videos (video_id, added_date, title)
VALUES (245e8024-14bd-11e5-9743-8238356b7e32 , '2012-04-03', 'Cassandra & SSDs');

INSERT INTO videos (video_id, added_date, title)
VALUES (3452f7de-14bd-11e5-855e-8738355b7e3a , '2013-03-17', 'Cassandra Intro');

INSERT INTO videos (video_id, added_date, title)
VALUES (4845ed97-14bd-11e5-8a40-8338255b7e33 , '2013-10-16', 'DataStax DevCenter');

INSERT INTO videos (video_id, added_date, title)
VALUES (5645f8bd-14bd-11e5-af1a-8638355b8e3a, '2013-04-16', 'What is DataStax ?');
```
===========================================


```
INSERT INTO videos_by_tag (tag, video_id, added_date, title)
VALUES ('cassandra', 1645ea59-14bd-11e5-a993-8138354b7e31, '2014-01-29', 'Cassandra History');

INSERT INTO videos_by_tag (tag, video_id, added_date, title)
VALUES ('cassandra', 245e8024-14bd-11e5-9743-8238356b7e32, '2012-04-03', 'Cassandra & SSDs');

INSERT INTO videos_by_tag (tag, video_id, added_date, title)
VALUES ('cassandra', 3452f7de-14bd-11e5-855e-8738355b7e3a, '2013-03-17', 'Cassandra Intro');

INSERT INTO videos_by_tag (tag, video_id, added_date, title)
VALUES ('datastax', 4845ed97-14bd-11e5-8a40-8338255b7e33, '2013-10-16', 'DataStax Studio');

INSERT INTO videos_by_tag (tag, video_id, added_date, title)
VALUES ('datastax', 5645f8bd-14bd-11e5-af1a-8638355b8e3a, '2013-04-16', 'What is DataStax Enterprise?');
```
===========================================

```
CREATE TABLE videos_by_tag (
       tag text,
       video_id uuid,
       added_date timestamp,
       title text,
       PRIMARY KEY ((tag), added_date, video_id)
) WITH CLUSTERING ORDER BY(added_date DESC,video_id ASC);
```
===========================================
```
SELECT *
FROM videos_by_tag
where tag = 'cassandra'
ORDER BY added_date ASC;
```
===========================================
```
SELECT * FROM videos_by_tag
        ORDER BY added_date ASC;
```
===========================================
```
SELECT * FROM videos_by_tag
         where tag = 'cassandra'
        ORDER BY added_date ASC;
```
===========================================
