---
title: <variable>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 46cc8cbc-10ec-4625-8813-3f5cd6c6afde
ms.openlocfilehash: 5878720f51f4b5cfe3163abf316a867ccda31342
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/06/2020
ms.locfileid: "70397768"
---
# \<variable>
表示与此活动查询关联的变量的集合。  
  
 有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)。  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQuery>**](activitystatequery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<variables>**](variables.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<variable>**  
  
## <a name="syntax"></a>语法  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <variables>
          <variable name="String" />
        </variables>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|属性|说明|  
|---------------|-----------------|  
|name|一个字符串，指定变量的名称。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<variable>](variable.md)|与活动状态查询相关联的变量。|  
  
## <a name="remarks"></a>注解  
 ActivityStateQuery 的一项独特功能是能够在跟踪工作流的执行时提取数据。 这在访问跟踪记录后续执行时可提供其他上下文。 您可以使用 [\<arguments>](arguments.md) 、 [\<states>](states.md) 和 [\<states>](states.md) 元素从工作流中的任何活动提取任何变量或参数。 下面的示例演示用于在发出活动的 `Closed` 跟踪记录时提取变量和自变量的活动状态查询。 变量和参数只能通过 ActivityStateRecord 提取，因此使用在跟踪配置文件内进行订阅 [\<activityStateQuery>](activitystatequery.md) 。  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <variables>  
    <variable name="FromAddress"/>  
  </variables>  
  <arguments>  
    <argument name="Result"/>  
  </arguments>  
</activityStateQuery>  
```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [工作流跟踪](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)
