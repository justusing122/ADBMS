1) Update a document into collection
    db. Teacher_info.update( { sal: { $gt: 25000 } }, { $set: { Dept_name: “ETC" } }, { multi: true } ) 
    db. Teacher_info.update( { status: "A" } , { $inc: { sal: 10000 } }, { multi: true } ) 

2) Remove a document from collection
    db.Teacher_info.remove({Teacher_id: "pic001"});
    db. Teacher_info.remove({})

3) Retrieve a document in ascending or descending order using 1 for ascending and -1 for descendingfrom collection in mongodb
    >db. Teacher_info.find( { status: "A" } ).sort( {sal: -1 } ) 
    >db.audit.find().sort( { $natural: -1 } ).limit ( 10 )
    >db.Employee.find().sort({_id:-1})
