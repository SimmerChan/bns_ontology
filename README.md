按照类,类之间的关系和类的属性来进行设计。利用Protege打开本项目中的owl文件可以查看具体结构。

# 1.人物(Person)
子类：佛教徒(Buddhist)
## 1.1 对象属性(object properties)
1. 亲属关系(hasKinship)，性质：transitive、symmetric，领域：人物，范围：人物，描述：disjoint with 'hasNonKinshipAssoication, hasBirthPlace'。
    1. 双亲(hasParent)，性质：asymmetric，领域：人物，范围：人物，描述：inverse of 'hasChild'，disjoint with 'hasChild, hasWifeOrConcubine, hasHusband, hasSibling'。
        1. 父亲(hasFather)，性质：functional，领域：人物，范围：人物，描述：disjoint with 'hasMother'。
        2. 母亲(hasMother)，性质：functional，领域：人物，范围：人物，描述：disjoint with 'hasFather'。
    2. 子女(hasChild)，性质：asymmetric，领域：人物，范围：人物，描述：inverse of 'hasParent'。
        1. 儿子(hasSon)，领域：人物，范围：人物，描述：disjoint with 'hasDaughter'。
        2. 女儿(hasDaughter)，领域：人物，范围：人物，描述：disjoint with 'hasSon'。
    3. 丈夫(husband)，性质：asymmetric，领域：人物，范围：人物，描述：inverse of 'hasWifeOrConcubine'。
    4. 妻妾(hasWifeOrConcubine)，性质：asymmetric，领域：人物，范围：人物，描述：inverse of 'hasHusband'。
        1. 妻子(hasWife) ，领域：人物，范围：人物，描述：disjoint with 'hasConcubine'。
        2. 妾室(hasConcubine) ，领域：人物，范围：人物，描述：disjoint with 'hasWife'。
    5. 兄弟姐妹(hasSibling)，性质：symmetric，领域：人物，范围：人物。
        1. 姐妹(hasSister)，领域：人物，范围：人物, disjoint with 'hasBrother'。
            - 姐姐(hasElderSister) ，领域：人物，范围：人物，描述：disjoint with 'hasYoungerSister'。
            - 妹妹(hasYoungerSister) ，领域：人物，范围：人物，描述：disjoint with 'hasElderSister'。
        2. 兄弟(hasBrother)，领域：人物，范围：人物, disjoint with 'hasSister'。。
            - 哥哥(hasElderBrother) ，领域：人物，范围：人物，描述：disjoint with 'hasYoungerBrother'。
            - 弟弟(hasYoungerBrother) ，领域：人物，范围：人物，描述：disjoint with 'hasElderBrother'。

2. 任职(hasPosting)，领域：人物，范围：任职。
3. 作品(hasText)，领域：人物，范围：作品
4. 人与事件的关系(hasRelationWithEvent)，领域：人物，范围：人与事件的关系。
5. 非亲属关系(hasNonKinshipAssociation)，领域：人物，范围：非亲属关系。
6. 人与行政地理之间的关系(hasRelationWithPlace)，领域：人物，范围：人与地点的关系
7. 人与社会机构之间的关系(hasRelationWithSocialInstitution)，领域：人物，范围：人与机构的关系
8. 身份(hasStatus)，领域：人物，范围：身份
9. 入仕(hasEntry)，领域：人物，范围：入仕方式

## 1.2 数据属性(data properties)
1. 姓名(personName)
2. 姓(personSurname)
3. 名字(personMingzi)
4. 称谓(personAppellation)
    1. 别名、曾用名(alternateNameOrPreviouslyUsedName)
    2. 字(courtesyName)
    3. 室名、别号(StudioNameOrStyleName)
    4. 谥号(posthumousName)
    5. 封爵(enfeoffmentTitle)
    6. 小名(childhoodName)
    7. 小字(childhoodCourtesyName)
    8. 赐号(bestowedName)
    9. 俗姓(secularSurname)
    10. 俗名(secularPersonalName)
    11. 庙号(templeName)
    12. 尊号(honorificName)
    13. 庙额(templeTitle)
    14. 其他译名(otherTransliteratedName)
    15. 本姓(originalSurname)
    16. 法号(dharmaName)
    17. 行第(birthOrder)
5. 性别(personGender)
6. 享年(personDeathAge)
7. 种族(personEthnicity)
8. 郡望(personChoronym)
9. 朝代(dynasty)
10. 出生年份(personBirthYear)
11. 死亡年份(personDeathYear)
12. 出生月份(personBirthMonth)
13. 死亡月份(personDeathMonth)
14. 出生日(personBirthDay)
15. 死亡日(personDeathDay)
16. 出生年号(personBirthNianhao)
17. 死亡年号(personDeathNianhao)
18. 出生年号年(personBirthNianhaoYear)
19. 死亡年号年(personDeathNianhaoYear)
20. 出生日干支(personBirthDayGanzhi)
21. 死亡日干支(personDeathDayGanzhi)
22. 最早出现年份(personFloruitEarliestYear)
23. 最晚出现年份(personFloruitLatestYear)
24. 最早出现年号(personFloruitEarliestNianhao)
25. 最晚出现年号(personFloruitLatestNianhao)
26. 最早出现年号年(personFloruitEarliestNianhaoYear)
27. 最晚出现年号年(personFloruitLatestNianhaoYear)

# 2.地点(Place)
## 2.1 对象属性(object properties)
1. 上级行政区(isPartOf)，性质：transitive，领域：地点，范围：地点，描述：inverse of 'hasContained'。
2. 下级行政区(hasContained)，性质：transitive，领域：地点，范围：地点，描述：inverse of 'isPartOf'。

## 2.2 数据属性(data properties)
1. 地址名称(placeAddress)
2. 行政类别(placeAdminType)
3. x坐标(placeXCoordinate)
4. y坐标(placeYCoordinate)
5. 地址始年(placeFirstYear)
6. 地址终年(placeLastYear)


# 3.作品(Text)
## 3.1 对象属性(object properties)
1. 作者(hasAuthor)，领域：作品，范围：人物。

## 3.2 数据属性(data properties)
1. 标题(textTitle)
2. 流派(textGenre)
3. 著作年代(textCompositionYear)
4. 著作年号(textCompositionNianhao)
5. 著作年号年(textCompositionNianhaoYear)
6. 朝代(dynasty)
7. 存佚情况(textExtant)

# 4.事件(Event)
## 4.1 对象属性(object properties)
1. 发生地点(hasEventAddress)，领域：事件，范围：地点。

## 4.2 数据属性(data properties)
1. 事件内容(eventContent)
2. 首年(firstYear)
3. 末年(lastYear)
4. 首年月份(firstYearMonth)
5. 末年月份(lastYearMonth)
6. 首年日(firstYearDay)
7. 末年日(lastYearDay)
8. 首年年号(firstYearNianhao)
9. 末年年号(lastYearNianhao)
10. 首年年号年(firstYearNianhaoYear)
11. 末年年号年(lastYearNianhaoYear)
12. 首年日干支(firstYearDayGanzhi)
13. 末年日干支(lastYearDayGanzhi)
14. 事件类型(eventType)


# 5.机构(SocialInstitution)
## 5.1 对象属性(object properties)
1. 机构地址(hasInstitutionAddress)，领域：机构，范围：地点。

## 5.2 数据属性(data properties)
1. 机构名称(institutionName)
2. 机构类型(institutionType)
3. 机构存在初始朝代(institutionBeginDynasty)
4. 机构存在最后朝代(institutionEndDynasty)
5. 机构存在朝代(institutionFloruitDynasty)
6. 机构被知首年(institutionFirstKnownYear)
7. 机构被知末年(institutionLastKnownYear)
8. 首年(firstYear)
9. 末年(lastYear)
10. 首年年号(firstYearNianhao)
11. 末年年号(lastYearNianhao)
12. 首年年号年(firstYearNianhaoYear)
13. 末年年号年(lastYearNianhaoYear)

# 6.非亲属关系(NonKinshipAssociation)
子类：
1. 社会关系(SocialAssociation)
2. 学术关系(ScholarshipAssociation)
3. 朋友关系(FriendshipAssociation)
4. 政治关系(PoliticsAssociation)
5. 著述关系(WritingsAssociation)
6. 军事关系(MilitaryAssociation)
7. 医疗关系(MedicineAssociation)
8. 宗教关系(ReligionAssociation)
9. 家庭关系(FamilyAssociation)
10. 财务关系(FinanceAssociation)
11. 其他关系(OtherAssociation)

## 6.1 对象属性(object properties)
1. 关系人(hasAssociatedPerson)，领域：非亲属关系，范围：人物。
2. 关系地址(hasAssociationAddress)，领域：非亲属关系，范围：地点。

## 6.2 数据属性(data properties)
1. 确立关系的场合(associationOccasion)
2. 关系次序(associationSequence)
3. 相关文本内容(associationText)
4. 关系确立年份(associationYear)
5. 关系确立年号(associationNianhao)
6. 关系确立年号年(associationNianhaoYear)
7. 关系确立月份(associationMonth)
8. 关系确立日(associationDay)
9. 关系确立日干支(associationDayGanzhi)

# 7.身份(Status)
## 7.1 对象属性(object properties)
无
## 7.2 数据属性(data properties)
1. 身份名称(statusName)
2. 身份次序(statusSequence)
3. 首年(firstYear)
4. 末年(lastYear)
5. 首年年号(firstYearNianhao)
6. 末年年号(lastYearNianhao)
7. 首年年号年(firstYearNianhaoYear)
8. 末年年号年(lastYearNianhaoYear)

# 8.入仕方式(ModeOfEntry)
子类：
1. 宫廷门(Palace)
2. 血亲门(Kinship)
3. 姻亲门(Marriage)
4. 科举门(Examination)
5. 学校门(School)
6. 恩荫门(YinPrivilege)
7. 征召门(Recruitment)
8. 荐举门(Recoomendation)
9. 军功补授门(MilitaryMerit)
10. 技进门(SpecializedTalents)
11. 归降门(Surrender)
12. 进纳门(Purchase)
13. 特旨门(DecreeOfSpecialGrace)
14. 宗教门(Religion)
15. 求官不得门(FailedPursuitOfOffice)
16. 七色补官门(SevenSpecials)
17. 其他方式(OtherModes)

## 8.1 对象属性(object properties)
1. 入仕亲属关系(hasEntryKinship)，领域：入仕方式，范围：人物。
2. 入仕非亲属关系(hasEntryNonKinship)，领域：入仕方式，范围：非亲属关系。
3. 入仕地址(hasEntryAddress)，领域：入仕方式，范围：地点。

## 8.2 数据属性(data properties)
1. 入仕次序(entrySequence)
2. 入仕年龄(entryAge)
3. 科考名次(entryExamRank)
4. 入仕年份(entryYear)
5. 入仕年号(entryNianhao)
6. 入仕年号年(entryNianhaoYear)
7. 入仕亲属关系类型(entryKinshipType)
8. 入仕非亲属关系类型(entryNonKinshipType)


# 9.除授(Posting)
## 9.1 对象属性(object properties)
1. 任职地址(hasPostingAddress)，领域：除授，范围：地点。
2. 职位(hasPostingOffice)，领域：除授，范围：职位。

## 9.2 数据属性(data properties)
1. 除授次序(postingSequence)
2. 首年(firstYear)
3. 末年(lastYear)
4. 首年月份(firstYearMonth)
5. 末年月份(LastYearMonth)
6. 首年日(firstYearDay)
7. 末年日(LastYearDay)
8. 首年年号(firstYearNianhao)
9. 末年年号(lastYearNianhao)
10. 首年年号年(firstYearNianhaoYear)
11. 末年年号年(LastYearNianhaoYear)
12. 首年日干支(firstYearDayGanzhi)
13. 末年日干支(lastYearDayGanzhi)
14. 朝代(dynasty)


# 10.人与地点的关系(RelationBetweenPersonAndPlace)
子类：
1. 出生地(BirthPlace)
2. 籍贯(BasicAffiliation)
3. 迁往(MovedTo)
4. 前住地(FormerAddress)
5. 最后所知地(LastKnownAddress)
6. 祖籍(AncestralAddress)
6. 实际居住地(ActualResidence)
7. 原籍/本贯(HouseholdRegistration)
8. 葬地(BurialAddress)
9. 死所(DeathAddress)
10 游历/曾经到过(VisitedOrWentTo)
11. 另一籍贯(AlternateBasicAffiliation)
12. 户籍地(HouseholdAddress)
13. 其他(OtherAddressRelation)

## 10.1 对象属性(object properties)
1. 地址(hasAddress)，领域：人与地点的关系，范围：地点。

## 10.2 数据属性(data properties)
1. 地点次序(addressSequence)
2. 首年(firstYear)
3. 末年(lastYear)
4. 首年月份(firstYearMonth)
5. 末年月份(LastYearMonth)
6. 首年日(firstYearDay)
7. 末年日(LastYearDay)
8. 首年年号(firstYearNianhao)
9. 末年年号(lastYearNianhao)
10. 首年年号年(firstYearNianhaoYear)
11. 末年年号年(LastYearNianhaoYear)
12. 首年日干支(firstYearDayGanzhi)
13. 末年日干支(LirstYearDayGanzhi)


# 11.人与机构的关系(RelationBetweenPersonAndInstitution)
子类：
1. 任寺院住持/书院山长/院长于(Abbot)
2. 任佛僧/道士于(Cleric)
3. 其他(OtherInstitutionRelation)

## 11.1 对象属性(object properties)
1. 机构(hasInstitution)，领域：人与机构的关系，范围：机构。

## 11.2 数据属性(data properties)
1. 首年(firstYear)
2. 末年(lastYear)
3. 首年年号(firstYearNianhao)
4. 末年年号(lastYearNianhao)
5. 首年年号年(firstYearNianhaoYear)
6. 末年年号年(LastYearNianhaoYear)


# 12.人与事件的关系(RelationBetweenPersonAndEvent)
## 12.1 对象属性(object properties)
1. 事件(hasEvent)，领域：人与事件的关系，范围：事件。

## 12.2 数据属性(data properties)
1. 事件次序(eventSequence)

# 13.职位(Office)
## 13.1 对象属性(object properties)
无

## 13.2 数据属性(data properties)
1. 朝代(dynasty)
2. 职位名称(officeTitle)
3. 职位部门(officeType)