# CSpp::~CSpp(void)

- ea: `0x1800028c0`
- end: `0x18000298c`
- name: `??1CSpp@@AEAA@XZ`
- size: `204`
- prototype: `void __fastcall(CSpp *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800022cc`

## callees

- `0x180002344`
- `0x1800028c0`
- `0x1800044d0`
- `0x180007a74`
- `0x1800081dc`
- `0x180008e0c`
- `0x18000e000`
- `0x18000e2c8`
- `0x18000e48c`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800028db`
- `KERNEL32!LocalFree` at `0x1800028db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000290d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000290d`

## pseudocode

```c
void __fastcall CSpp::~CSpp(CSpp *this)
{
  __int64 v2; // rcx
  CVolumeEntryMap *v3; // rcx
  CSxDiagnostics *v4; // rcx
  void *v5; // rcx

  *(_QWORD *)this = &CSpp::`vftable';
  LocalFree(*((HLOCAL *)this + 8));
  *((_QWORD *)this + 8) = 0;
  if ( *((_QWORD *)this + 10) )
    ATL::AtlComPtrAssign((struct IUnknown **)this + 10, 0);
  Free_SPP_COMPONENT_PROP_Array(*((_DWORD *)this + 22), *((struct _SPP_COMPONENT_PROP **)this + 12));
  CoTaskMemFree(*((LPVOID *)this + 12));
  v2 = *((_QWORD *)this + 4);
  *((_QWORD *)this + 12) = 0;
  if ( v2 )
    CSxArrayBuilder<_SPP_WRITER_ERROR_INFO,&void Free_SPP_BAD_WRITER_INFO(_SPP_WRITER_ERROR_INFO *),&void SxDefaultInit<_SPP_WRITER_ERROR_INFO>(_SPP_WRITER_ERROR_INFO *),&void SxDefaultTransfer<_SPP_WRITER_ERROR_INFO>(_SPP_WRITER_ERROR_INFO *,_SPP_WRITER_ERROR_INFO *)>::Dispose();
  if ( *((_QWORD *)this + 14) )
    CSxRefMap<CVolumeEntryMap,CVolumeEntry>::DeleteAll();
  v3 = (CVolumeEntryMap *)*((_QWORD *)this + 14);
  if ( v3 )
  {
    *((_QWORD *)this + 14) = 0;
    CVolumeEntryMap::Release(v3);
  }
  v4 = (CSxDiagnostics *)*((_QWORD *)this + 13);
  if ( v4 )
  {
    *((_QWORD *)this + 13) = 0;
    CSxDiagnostics::Release(v4);
  }
  ATL::CComPtrBase<IVssEnumObject>::~CComPtrBase<IVssEnumObject>((__int64 *)this + 10);
  v5 = (void *)*((_QWORD *)this + 4);
  if ( v5 )
  {
    *((_QWORD *)this + 4) = 0;
    CSxArrayBuilder<_SPP_WRITER_ERROR_INFO,&void Free_SPP_BAD_WRITER_INFO(_SPP_WRITER_ERROR_INFO *),&void SxDefaultInit<_SPP_WRITER_ERROR_INFO>(_SPP_WRITER_ERROR_INFO *),&void SxDefaultTransfer<_SPP_WRITER_ERROR_INFO>(_SPP_WRITER_ERROR_INFO *,_SPP_WRITER_ERROR_INFO *)>::Release(v5);
  }
}

```

## disassembly

```asm
0x1800028c0  mov     [rsp+arg_0], rbx
0x1800028c5  push    rdi
0x1800028c6  sub     rsp, 20h
0x1800028ca  lea     rax, ??_7CSpp@@6B@; const CSpp::`vftable'
0x1800028d1  mov     rbx, rcx
0x1800028d4  mov     [rcx], rax
0x1800028d7  mov     rcx, [rcx+40h]; hMem
0x1800028db  call    cs:__imp_LocalFree
0x1800028e1  lea     rdi, [rbx+50h]
0x1800028e5  mov     qword ptr [rbx+40h], 0
0x1800028ed  cmp     qword ptr [rdi], 0
0x1800028f1  jz      short loc_1800028FD
0x1800028f3  xor     edx, edx; struct IUnknown *
0x1800028f5  mov     rcx, rdi; struct IUnknown **
0x1800028f8  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800028fd  mov     rdx, [rbx+60h]; struct _SPP_COMPONENT_PROP *
0x180002901  mov     ecx, [rbx+58h]; unsigned int
0x180002904  call    ?Free_SPP_COMPONENT_PROP_Array@@YAXKPEAU_SPP_COMPONENT_PROP@@@Z; Free_SPP_COMPONENT_PROP_Array(ulong,_SPP_COMPONENT_PROP *)
0x180002909  mov     rcx, [rbx+60h]; pv
0x18000290d  call    cs:__imp_CoTaskMemFree
0x180002913  mov     rcx, [rbx+20h]
0x180002917  mov     qword ptr [rbx+60h], 0
0x18000291f  test    rcx, rcx
0x180002922  jz      short loc_180002929
0x180002924  call    ?Dispose@?$CSxArrayBuilder@U_SPP_WRITER_ERROR_INFO@@$1?Free_SPP_BAD_WRITER_INFO@@YAXPEAU1@@Z$1??$SxDefaultInit@U_SPP_WRITER_ERROR_INFO@@@@YAX0@Z$1??$SxDefaultTransfer@U_SPP_WRITER_ERROR_INFO@@@@YAX00@Z@@QEAAXXZ; CSxArrayBuilder<_SPP_WRITER_ERROR_INFO,&Free_SPP_BAD_WRITER_INFO(_SPP_WRITER_ERROR_INFO *),&SxDefaultInit<_SPP_WRITER_ERROR_INFO>(_SPP_WRITER_ERROR_INFO *),&SxDefaultTransfer<_SPP_WRITER_ERROR_INFO>(_SPP_WRITER_ERROR_INFO *,_SPP_WRITER_ERROR_INFO *)>::Dispose(void)
0x180002929  mov     rcx, [rbx+70h]
0x18000292d  test    rcx, rcx
0x180002930  jz      short loc_180002937
0x180002932  call    ?DeleteAll@?$CSxRefMap@VCVolumeEntryMap@@VCVolumeEntry@@@@QEAAXXZ; CSxRefMap<CVolumeEntryMap,CVolumeEntry>::DeleteAll(void)
0x180002937  mov     rcx, [rbx+70h]; this
0x18000293b  test    rcx, rcx
0x18000293e  jz      short loc_18000294D
0x180002940  mov     qword ptr [rbx+70h], 0
0x180002948  call    ?Release@CVolumeEntryMap@@QEAAKXZ; CVolumeEntryMap::Release(void)
0x18000294d  mov     rcx, [rbx+68h]; this
0x180002951  test    rcx, rcx
0x180002954  jz      short loc_180002963
0x180002956  mov     qword ptr [rbx+68h], 0
0x18000295e  call    ?Release@CSxDiagnostics@@QEAAKXZ; CSxDiagnostics::Release(void)
0x180002963  mov     rcx, rdi
0x180002966  call    ??1?$CComPtrBase@UIVssEnumObject@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IVssEnumObject>::~CComPtrBase<IVssEnumObject>(void)
0x18000296b  mov     rcx, [rbx+20h]; Block
0x18000296f  test    rcx, rcx
0x180002972  jz      short loc_180002981
0x180002974  mov     qword ptr [rbx+20h], 0
0x18000297c  call    ?Release@?$CSxArrayBuilder@U_SPP_WRITER_ERROR_INFO@@$1?Free_SPP_BAD_WRITER_INFO@@YAXPEAU1@@Z$1??$SxDefaultInit@U_SPP_WRITER_ERROR_INFO@@@@YAX0@Z$1??$SxDefaultTransfer@U_SPP_WRITER_ERROR_INFO@@@@YAX00@Z@@QEAAKXZ; CSxArrayBuilder<_SPP_WRITER_ERROR_INFO,&Free_SPP_BAD_WRITER_INFO(_SPP_WRITER_ERROR_INFO *),&SxDefaultInit<_SPP_WRITER_ERROR_INFO>(_SPP_WRITER_ERROR_INFO *),&SxDefaultTransfer<_SPP_WRITER_ERROR_INFO>(_SPP_WRITER_ERROR_INFO *,_SPP_WRITER_ERROR_INFO *)>::Release(void)
0x180002981  mov     rbx, [rsp+28h+arg_0]
0x180002986  add     rsp, 20h
0x18000298a  pop     rdi
0x18000298b  retn
```
