# ATL::CComEnumOnSTL<IVssEnumMgmtObject,&__s_GUID const _GUID_01954e6b_9254_4e6e_808c_c9e05d007696,_VSS_MGMT_OBJECT_PROP,VSS_MGMT_OBJECT_PROP_Copy,VSS_MGMT_OBJECT_PROP_Array,ATL::CComMultiThreadModel>::~CComEnumOnSTL<IVssEnumMgmtObject,&__s_GUID const _GUID_01954e6b_9254_4e6e_808c_c9e05d007696,_VSS_MGMT_OBJECT_PROP,VSS_MGMT_OBJECT_PROP_Copy,VSS_MGMT_OBJECT_PROP_Array,ATL::CComMultiThreadModel>(void)

- ea: `0x1800176bc`
- end: `0x1800176e6`
- name: `??1?$CComEnumOnSTL@UIVssEnumMgmtObject@@$1?_GUID_01954e6b_9254_4e6e_808c_c9e05d007696@@3U__s_GUID@@BU_VSS_MGMT_OBJECT_PROP@@VVSS_MGMT_OBJECT_PROP_Copy@@VVSS_MGMT_OBJECT_PROP_Array@@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ`
- size: `42`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800176ec`
- `0x180025e64`

## callees

- `0x1800036c4`
- `0x180003790`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800176c9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800176c9`

## pseudocode

```c
__int64 __fastcall ATL::CComEnumOnSTL<IVssEnumMgmtObject,&__s_GUID const _GUID_01954e6b_9254_4e6e_808c_c9e05d007696,_VSS_MGMT_OBJECT_PROP,VSS_MGMT_OBJECT_PROP_Copy,VSS_MGMT_OBJECT_PROP_Array,ATL::CComMultiThreadModel>::~CComEnumOnSTL<IVssEnumMgmtObject,&__s_GUID const _GUID_01954e6b_9254_4e6e_808c_c9e05d007696,_VSS_MGMT_OBJECT_PROP,VSS_MGMT_OBJECT_PROP_Copy,VSS_MGMT_OBJECT_PROP_Array,ATL::CComMultiThreadModel>(
        __int64 a1)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  __int64 v4; // r9

  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 96));
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((ATL::CComSafeDeleteCriticalSection *)(a1 + 48));
  return ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(a1 + 8, v2, v3, v4);
}

```

## disassembly

```asm
0x1800176bc  push    rbx
0x1800176be  sub     rsp, 20h
0x1800176c2  mov     rbx, rcx
0x1800176c5  add     rcx, 60h ; '`'; lpCriticalSection
0x1800176c9  call    cs:__imp_DeleteCriticalSection
0x1800176cf  lea     rcx, [rbx+30h]; this
0x1800176d3  call    ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
0x1800176d8  lea     rcx, [rbx+8]
0x1800176dc  add     rsp, 20h
0x1800176e0  pop     rbx
0x1800176e1  jmp     ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
```
