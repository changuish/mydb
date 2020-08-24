# mydb
使用方法示例：

PageCut pageCut = new PageCut();

pageCut.setCurPage(curPage);

pageCut.setRowPerPage(rowPerPage);

BaseFacade baseFacade = new BaseFacade();

baseFacade.setTableName("mm_material");

Collection<MmMaterialModel> col = baseFacade.findByPageCut(MmMaterialModel.class, pageCut, null, null, "objectRrn desc");

pageCut.setResultCol(col);

-----------------------
BaseFacade方法介绍
	/**
	 * 主键查询,返回查询结果收条记录
	 * @param objClass 实体类
	 * @param condition 查询条件 field1=? and field2=?
	 * @param values 条件值
	 * @return
	 * @throws Exception
	 */
	public <T> T findByPrimaryKey(Class<T> objClass,String condition,Object[] values) throws Exception
	/**
	 * 条件查询
	 * @param <T>
	 * @param objClass 实体类
	 * @param columnCondition 条件 field1=? and field2=?
	 * @param values 条件值数组
	 * @return
	 * @throws Exception
	 */
	public <T> Collection<T> findByCondition(Class<T> objClass,String columnCondition,Object[] values) throws Exception
	
	/**
	 * 按sql查询，映射到实体类
	 * @param <T>
	 * @param objClass 实体类
	 * @param sql sql语句 select * from ...... where field 1=? and field2=? ...
	 * @param values 条件值数组
	 * @return
	 * @throws Exception
	 */
	public <T> Collection<T> findByConditionBySql(Class<T> objClass, String sql,Object[] values) throws Exception
	
	/**
	 * 按sql查询，返回Map
	 * @param sql sql语句 select * from ...... where field 1=? and field2=? ...
	 * @param values 条件值数组
	 * @return Map集合
	 * @throws Exception
	 */
	public Collection<Map<String, Object>> findByConditionBySql(String sql,Object[] values) throws Exception
	/**
	 * 批量更新数据
	 * @param prepareSql 更新sql，预编译
	 * @param prepareValuesCol 预编译数据集合
	 * @return
	 * @throws Exception
	 */
	public int update(String prepareSql,Collection<Object[]> prepareValuesCol) throws Exception
	
	/**
	 * 实体类更新
	 * @param obj 实体类
	 * @param condition 条件
	 * @param values 条件值数组
	 * @return 更新条数
	 * @throws Exception
	 */
	public int update(Object obj,String condition,Object[] values) throws Exception
	
	/**
	 * 单条sql更新
	 * @param sql 预编译sql，待条件
	 * @param values 条件值数组
	 * @return 更新数量
	 * @throws Exception
	 */
	public int update(String sql,Object[] values) throws Exception
	/**
	 * 实体类插入
	 * @param obj 实体类数据
	 * @return 返回自增id
	 * @throws Exception
	 */
	public Object insert(Object obj) throws Exception
	/**
	 * 批量添加数据
	 * @param objCol 实体类集合
	 * @return
	 * @throws Exception
	 */
	public int insertCol(Collection<?> objCol) throws Exception
	/**
	 * 获取实体类记录数量
	 * @param objClass 实体类
	 * @param columnCondition 条件
	 * @param values 条件值数组
	 * @return
	 * @throws Exception
	 */
	public int getRecordCount(Class<?> objClass,String columnCondition,Object[] values) throws Exception
	/**
	 * 根据sql查询记录数
	 * @param sql sql语句，包含预编译条件
	 * @param values 条件值数组
	 * @return
	 * @throws Exception
	 */
	public int getRecordCountBySql(String sql,Object[] values) throws Exception

	/**
	 * 实体类分页查询
	 * @param <T>
	 * @param objClass 实体类
	 * @param pageCut 分页信息，会被更新回写
	 * @param columnCondition 预编译条件
	 * @param values 条件值
	 * @param orderCondition 排序信息
	 * @return
	 * @throws Exception
	 */
	public <T> Collection<T> findByPageCut(Class<T> objClass,PageCut pageCut,String columnCondition, Object[] values,String orderCondition) throws Exception
	
