---
title: "CComContainedObject Class"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CComContainedObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "aggregate objects [C++], in ATL"
  - "aggregation [C++], ATL objects"
  - "CComContainedObject class"
ms.assetid: e8616b41-c200-47b8-bf2c-fb9f713ebdad
caps.latest.revision: 15
ms.author: "mblome"
manager: "ghogen"
translation.priority.ht: 
  - "cs-cz"
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "pl-pl"
  - "pt-br"
  - "ru-ru"
  - "tr-tr"
  - "zh-cn"
  - "zh-tw"
---
# CComContainedObject Class
This class implements [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) by delegating to the owner object's **IUnknown**.  
  
> [!IMPORTANT]
>  This class and its members cannot be used in applications that execute in the Windows Runtime.  
  
## Syntax  
  
```
template<class Base>  class CComContainedObject :  public Base
```  
  
#### Parameters  
 `Base`  
 Your class, derived from [CComObjectRoot](../atl/ccomobjectroot-class.md) or [CComObjectRootEx](../atl/ccomobjectrootex-class.md).  
  
## Members  
  
### Public Constructors  
  
|Name|Description|  
|----------|-----------------|  
|[CComContainedObject::CComContainedObject](../Topic/CComContainedObject::CComContainedObject.md)|The constructor. Initializes the member pointer to the owner object's `IUnknown`.|  
|[CComContainedObject::~CComContainedObject](../Topic/CComContainedObject::~CComContainedObject.md)|The destructor.|  
  
### Public Methods  
  
|Name|Description|  
|----------|-----------------|  
|[CComContainedObject::AddRef](../Topic/CComContainedObject::AddRef.md)|Increments the reference count on the owner object.|  
|[CComContainedObject::GetControllingUnknown](../Topic/CComContainedObject::GetControllingUnknown.md)|Retrieves the owner object's `IUnknown`.|  
|[CComContainedObject::QueryInterface](../Topic/CComContainedObject::QueryInterface.md)|Retrieves a pointer to the interface requested on the owner object.|  
|[CComContainedObject::Release](../Topic/CComContainedObject::Release.md)|Decrements the reference count on the owner object.|  
  
## Remarks  
 ATL uses `CComContainedObject` in classes [CComAggObject](../atl/ccomaggobject-class.md), [CComPolyObject](../atl/ccompolyobject-class.md), and [CComCachedTearOffObject](../atl/ccomcachedtearoffobject-class.md). `CComContainedObject` implements [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) by delegating to the owner object's **IUnknown**. (The owner is either the outer object of an aggregation, or the object for which a tear-off interface is being created.) `CComContainedObject` calls `CComObjectRootEx`'s `OuterQueryInterface`, `OuterAddRef`, and `OuterRelease`, all inherited through `Base`.  
  
## Inheritance Hierarchy  
 `Base`  
  
 `CComContainedObject`  
  
## Requirements  
 **Header:** atlcom.h  
  
##  <a name="ccomcontainedobject__addref"></a>  CComContainedObject::AddRef  
 Increments the reference count on the owner object.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### Return Value  
 A value that may be useful for diagnostics or testing.  
  
##  <a name="ccomcontainedobject__ccomcontainedobject"></a>  CComContainedObject::CComContainedObject  
 The constructor.  
  
```
CComContainedObject(void* pv);
```  
  
### Parameters  
 `pv`  
 [in] The owner object's **IUnknown**.  
  
### Remarks  
 Sets the `m_pOuterUnknown` member pointer (inherited through the `Base` class) to `pv`.  
  
##  <a name="ccomcontainedobject___dtorccomcontainedobject"></a>  CComContainedObject::~CComContainedObject  
 The destructor.  
  
```
~CComContainedObject();
```  
  
### Remarks  
 Frees all allocated resources.  
  
##  <a name="ccomcontainedobject__getcontrollingunknown"></a>  CComContainedObject::GetControllingUnknown  
 Returns the `m_pOuterUnknown` member pointer (inherited through the *Base* class) that holds the owner object's **IUnknown**.  
  
```
IUnknown* GetControllingUnknown();
```  
  
### Return Value  
 The owner object's **IUnknown**.  
  
### Remarks  
 This method may be virtual if `Base` has declared the [DECLARE_GET_CONTROLLING_UNKNOWN](../Topic/DECLARE_GET_CONTROLLING_UNKNOWN.md) macro.  
  
##  <a name="ccomcontainedobject__queryinterface"></a>  CComContainedObject::QueryInterface  
 Retrieves a pointer to the interface requested on the owner object.  
  
```
STDMETHOD(QueryInterface)(REFIID iid,
    void**  ppvObject);

    template  <class Q>  HRESULT STDMETHODCALLTYPE QueryInterface(
    Q**  pp);
```  
  
### Parameters  
 `iid`  
 [in] The identifier of the interface being requested.  
  
 `ppvObject`  
 [out] A pointer to the interface pointer identified by `iid`. If the object does not support this interface, `ppvObject` is set to **NULL**.  
  
 `pp`  
 [out] A pointer to the interface pointer identified by type `Q`. If the object does not support this interface, `pp` is set to **NULL**.  
  
### Return Value  
 A standard `HRESULT` value.  
  
##  <a name="ccomcontainedobject__release"></a>  CComContainedObject::Release  
 Decrements the reference count on the owner object.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### Return Value  
 In debug builds, **Release** returns a value that may be useful for diagnostics or testing. In non-debug builds, **Release** always returns 0.  
  
## See Also  
 [Class Overview](../atl/atl-class-overview.md)
