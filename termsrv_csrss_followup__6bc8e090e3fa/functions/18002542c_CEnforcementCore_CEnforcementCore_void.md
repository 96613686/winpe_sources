# CEnforcementCore::~CEnforcementCore(void)

- ea: `0x18002542c`
- end: `0x180025538`
- name: `??1CEnforcementCore@@UEAA@XZ`
- size: `268`
- prototype: `void __fastcall(CEnforcementCore *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180097d30`

## callees

- `0x180007f40`
- `0x1800139c0`
- `0x18002542c`
- `0x180025540`
- `0x180025564`

## import_xrefs

- `ntdll!RtlDeleteResource` at `0x18002548e`
- `ntdll!RtlDeleteResource` at `0x1800254b1`
- `ntdll!RtlDeleteResource` at `0x18002548e`
- `ntdll!RtlDeleteResource` at `0x1800254b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002544f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002544f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CEnforcementCore::~CEnforcementCore(CEnforcementCore *this)
{
  void *v2; // rcx

  *(_QWORD *)this = &CEnforcementCore::`vftable';
  v2 = (void *)*((_QWORD *)this + 234);
  if ( v2 )
  {
    CloseHandle(v2);
    *((_QWORD *)this + 234) = 0;
  }
  g_pEnfCore = 0;
  CTSPrivateObject<ITSNotifySink>::~CTSPrivateObject<ITSNotifySink>((char *)this + 1888);
  if ( *((_DWORD *)this + 462) )
    RtlDeleteResource((PRTL_RESOURCE)((char *)this + 1752));
  *((_DWORD *)this + 462) = 0;
  if ( *((_DWORD *)this + 436) )
    RtlDeleteResource((PRTL_RESOURCE)((char *)this + 1648));
  *((_DWORD *)this + 436) = 0;
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>((char *)this + 1640);
  SmartPtr<ITSLicensePolicy>::~SmartPtr<ITSLicensePolicy>((char *)this + 1632);
  SmartPtr<ITSLicensePolicy>::~SmartPtr<ITSLicensePolicy>((char *)this + 1624);
  SmartPtr<ITSLicensePolicy>::~SmartPtr<ITSLicensePolicy>((char *)this + 1616);
  SmartPtr<ITSLicensePolicy>::~SmartPtr<ITSLicensePolicy>((char *)this + 1608);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>((char *)this + 1600);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>((char *)this + 1592);
  *(_QWORD *)this = &CTSPrivateObject<IEnforcementCore>::`vftable';
  RemoveTrackingObject((struct _LIST_ENTRY *)((char *)this + 1576));
}

```

## disassembly

```asm
0x18002542c  mov     [rsp+arg_0], rbx
0x180025431  push    rdi
0x180025432  sub     rsp, 20h
0x180025436  mov     rbx, rcx
0x180025439  lea     rax, ??_7CEnforcementCore@@6B@; const CEnforcementCore::`vftable'
0x180025440  mov     [rcx], rax
0x180025443  mov     rcx, [rcx+750h]; hObject
0x18002544a  test    rcx, rcx
0x18002544d  jz      short loc_180025466
0x18002544f  call    cs:__imp_CloseHandle
0x180025456  nop     dword ptr [rax+rax+00h]
0x18002545b  mov     qword ptr [rbx+750h], 0
0x180025466  mov     cs:?g_pEnfCore@@3PEAVCEnforcementCore@@EA, 0; CEnforcementCore * g_pEnfCore
0x180025471  lea     rcx, [rbx+760h]
0x180025478  call    ??1?$CTSPrivateObject@UITSNotifySink@@@@UEAA@XZ; CTSPrivateObject<ITSNotifySink>::~CTSPrivateObject<ITSNotifySink>(void)
0x18002547d  nop
0x18002547e  lea     rdi, [rbx+6D8h]
0x180025485  cmp     dword ptr [rdi+60h], 0
0x180025489  jz      short loc_18002549A
0x18002548b  mov     rcx, rdi; Resource
0x18002548e  call    cs:__imp_RtlDeleteResource
0x180025495  nop     dword ptr [rax+rax+00h]
0x18002549a  mov     dword ptr [rdi+60h], 0
0x1800254a1  lea     rdi, [rbx+670h]
0x1800254a8  cmp     dword ptr [rdi+60h], 0
0x1800254ac  jz      short loc_1800254BD
0x1800254ae  mov     rcx, rdi; Resource
0x1800254b1  call    cs:__imp_RtlDeleteResource
0x1800254b8  nop     dword ptr [rax+rax+00h]
0x1800254bd  mov     dword ptr [rdi+60h], 0
0x1800254c4  lea     rcx, [rbx+668h]; void *
0x1800254cb  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800254d0  lea     rcx, [rbx+660h]
0x1800254d7  call    ??1?$SmartPtr@VITSLicensePolicy@@@@QEAA@XZ; SmartPtr<ITSLicensePolicy>::~SmartPtr<ITSLicensePolicy>(void)
0x1800254dc  lea     rcx, [rbx+658h]
0x1800254e3  call    ??1?$SmartPtr@VITSLicensePolicy@@@@QEAA@XZ; SmartPtr<ITSLicensePolicy>::~SmartPtr<ITSLicensePolicy>(void)
0x1800254e8  lea     rcx, [rbx+650h]
0x1800254ef  call    ??1?$SmartPtr@VITSLicensePolicy@@@@QEAA@XZ; SmartPtr<ITSLicensePolicy>::~SmartPtr<ITSLicensePolicy>(void)
0x1800254f4  lea     rcx, [rbx+648h]
0x1800254fb  call    ??1?$SmartPtr@VITSLicensePolicy@@@@QEAA@XZ; SmartPtr<ITSLicensePolicy>::~SmartPtr<ITSLicensePolicy>(void)
0x180025500  lea     rcx, [rbx+640h]; void *
0x180025507  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18002550c  lea     rcx, [rbx+638h]; void *
0x180025513  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180025518  lea     rax, ??_7?$CTSPrivateObject@VIEnforcementCore@@@@6B@; const CTSPrivateObject<IEnforcementCore>::`vftable'
0x18002551f  mov     [rbx], rax
0x180025522  lea     rcx, [rbx+628h]; struct _LIST_ENTRY *
0x180025529  mov     rbx, [rsp+28h+arg_0]
0x18002552e  add     rsp, 20h
0x180025532  pop     rdi
0x180025533  jmp     ?RemoveTrackingObject@@YAXPEAU_LIST_ENTRY@@@Z; RemoveTrackingObject(_LIST_ENTRY *)
```
