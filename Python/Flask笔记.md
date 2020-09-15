1. 利用数据库表结构反向生成Model

   ```sql
   flask-sqlacodegen --flask 'mysql+pymysql://root:root1234@9.134.78.24/mock_sys'  --tables t_sys
   ```




2. flask_sqlalchemy model.query.filter的坑

   ```python
   SystemModel.query.filter_by(Ftag=tag).paginate(page_num, page_size, error_out=False)
   ```

   利用`model.query.filter`的方式进行查询，会有add commit增加记录后，实际db也已经增加了记录，但是却查询不到新增的数据的情况，所以这样情况要使用`db.session.query`的方式进行查询

   **//TODO 还是要研究下代码，看看为什么查询不到，google之后发现大家都踩过这个坑**

   

3. query like的一个坑

   ```python
   sys_detail = db.session.query(StrategyInfoModel).filter(StrategyInfoModel.Fsys_id ==sys_id,StrategyInfoModel.Fname.like('%'+name+'%')).order_by(StrategyInfoModel.Fmodify_time.desc()).paginate(page_num, page_size, error_out=False)
   ```

   这里的Fname.like会不能正确的搜索出name对应的记录，还不知道是为什么？2020年9月15日17:35:27

 