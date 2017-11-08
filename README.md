# wiki

GET запросы
===========

>\* - вроде как не нужно


/getDecomposition(skillId)
--------------------------
    
Параметры:

    skillId - id корневого скилла (int)

Формат возвращаемого json:

    {
      'rootId': rootId,
      'adjacencyList': [{parentId: childId}...],
      'skillName': skillName
    }
        
Значения:

    rootId - id корневого скилла (int)
    adjacencyList - список смежности (Pair<int, int>[])
    skillName - имя скилла (String)
    
/getDecompositions()
--------------------------
    
Параметры:

Формат возвращаемого json:

    {
      decompositions: [{rootId: skillName}...]
    }
        
Значения:

    decompositions - список корневых скиллов в виде пар {skillId, skillName} (Pair<int, String>[])
  
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
    
/insertSkill(afterSkillId, name)
------------------

Параметры:

    afterSkillId - id родителя нового скилла 
    
Формат возвращаемого json:

    {
      'skillId': skillId,
      'adjacencyList': [{parentId: childId}...],
      'name': name
    }
