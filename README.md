# wiki

GET запросы
===========

>\* - вроде как не нужно

>декомпозиция (фактически) - скилл без родителя


/getDecomposition(skillId)
--------------------------
    
Параметры:

    skillId - id корневого скилла (int)

Формат возвращаемого json:

    {
      'rootId': rootId,
      'adjacencyList': [{parentId: [{'childId': childId, 'childName': childName}...]}...],
      'skillName': skillName
    }
        
Значения:

    rootId - id корневого скилла (int)
    adjacencyList - список смежности (Pair<int, int>[])
    skillName - имя скилла (String)
    childName - имя класса-потомка
    
/getDecompositions()
--------------------------
    
Параметры:

Формат возвращаемого json:

    {
      'decompositions': [{rootId: skillName}...]
    }
        
Значения:

    decompositions - список корневых скиллов в виде пар {skillId, skillName} (Pair<int, String>[])
    
/getNotes(skillId)
------------------

Параметры:
    
    skillId - id скилла

Формат возвращаемого json:

    {
      'notes': [{'noteId': noteId, 'data': data, 'count': count, 'time': time}...]
    }
    
Значения:

    notes - список объектов заметок (List<Note>)
    noteId - id заметки (int)
    data - дата создания заметки (хер знает)
    count - количество задач (int)
    time - время, затраченное на решение задач (хер знает)
  
/getSkill(skillId)\*
------------------

Параметры:

    skillId - id скилла (int)
    
Формат возвращаемого json:

    {
      'skillId': skillId,
      'name': name
    }
    
Значения:

    skillId - id скилла (int)
    adjacencyList - список смежности (Pair<int, int>[])
    name - имя скилла (String)

/getSkills(skillId)\*
------------------

Параметры:

    skillId - id скилла (int)
    
Формат возвращаемого json:

    {
      'skillId': skillId,
      'adjacencyList': [{parentId: childId}...],
      'name': name
    }
    
POST запросы
============

/insertDecomposition(skillName)
-------------------------------

Параметры:

    skillName - имя скилла (String)
    
Описание:

    добавляет новую декомпозицию
    
/insertSkill(parentId, skillName)
------------------

Параметры:

    parentId - id родителя нового скилла (int)
    skillName - имя скилла (String)
    
Описание:

    добавляет новый скилл с именем skillName и родителем parentId

/updateSkill(skillName, skillId)
------------------

Параметры:

    skillName - новое имя скилла (String)
    skillId - id обновляемого скилла (int)
    
Описание:

    обновляет скилл с идентификатором skillId
    
/deleteSkill(skillId)
------------------

Параметры:

    skillId - id удаляемого скилла
    
Описание:

    обновляет скилл с идентификатором skillId
    
/addNote(skillId, count, time, date)
------------------------------------

Параметры:

    skillId - id скилла, которому добавляется новая заметка
    data - дата создания заметки (хер знает)
    count - количество задач (int)
    time - время, затраченное на решение задач (хер знает)

Описание:

    добавляет новую заметку скиллу с идентификатором skillId
    
/deleteNote(noteId)
-------------------

Параметры:

    noteId - id удаляемой заметки (int)
    
Описание:

    удаляет заметку с идентификатором noteId
    
/updateNote(noteId, time, count)
------------------------------------

Параметры:

    noteId - id изменяемой заметки (int)
    time - новое время
    count - количество решенных (int)
    
Описание:

    обновляет заметку с идентификатором noteId
    
/copyDecompositionFrom(skillId)
-------------------------------

Параметры:

    skillId - id корневого скилла
    
