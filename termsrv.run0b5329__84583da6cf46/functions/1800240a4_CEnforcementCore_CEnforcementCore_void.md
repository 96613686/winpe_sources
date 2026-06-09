# CEnforcementCore::~CEnforcementCore(void)

- ea: `0x1800240a4`
- end: `0x18002419e`
- name: `??1CEnforcementCore@@UEAA@XZ`
- size: `250`
- prototype: `void __fastcall(CEnforcementCore *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180093d00`

## callees

- `0x180008980`
- `0x180013150`
- `0x1800240a4`
- `0x1800241a4`
- `0x1800241c8`

## import_xrefs

- `ntdll!RtlDeleteResource` at `0x180024100`
- `ntdll!RtlDeleteResource` at `0x18002411d`
- `ntdll!RtlDeleteResource` at `0x180024100`
- `ntdll!RtlDeleteResource` at `0x18002411d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800240c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800240c7`

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
0x1800240a4  mov     [rsp+arg_0], rbx
0x1800240a9  push    rdi
0x1800240aa  sub     rsp, 20h
0x1800240ae  mov     rbx, rcx
0x1800240b1  lea     rax, ??_7CEnforcementCore@@6B@; const CEnforcementCore::`vftable'
0x1800240b8  mov     [rcx], rax
0x1800240bb  mov     rcx, [rcx+750h]; hObject
0x1800240c2  test    rcx, rcx
0x1800240c5  jz      short loc_1800240D8
0x1800240c7  call    cs:__imp_CloseHandle
0x1800240cd  mov     qword ptr [rbx+750h], 0
0x1800240d8  mov     cs:?g_pEnfCore@@3PEAVCEnforcementCore@@EA, 0; CEnforcementCore * g_pEnfCore
0x1800240e3  lea     rcx, [rbx+760h]
0x1800240ea  call    ??1?$CTSPrivateObject@UITSNotifySink@@@@UEAA@XZ; CTSPrivateObject<ITSNotifySink>::~CTSPrivateObject<ITSNotifySink>(void)
0x1800240ef  nop
0x1800240f0  lea     rdi, [rbx+6D8h]
0x1800240f7  cmp     dword ptr [rdi+60h], 0
0x1800240fb  jz      short loc_180024106
0x1800240fd  mov     rcx, rdi; Resource
0x180024100  call    cs:__imp_RtlDeleteResource
0x180024106  mov     dword ptr [rdi+60h], 0
0x18002410d  lea     rdi, [rbx+670h]
0x180024114  cmp     dword ptr [rdi+60h], 0
0x180024118  jz      short loc_180024123
0x18002411a  mov     rcx, rdi; Resource
0x18002411d  call    cs:__imp_RtlDeleteResource
0x180024123  mov     dword ptr [rdi+60h], 0
0x18002412a  lea     rcx, [rbx+668h]; void *
0x180024131  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180024136  lea     rcx, [rbx+660h]
0x18002413d  call    ??1?$SmartPtr@VITSLicensePolicy@@@@QEAA@XZ; SmartPtr<ITSLicensePolicy>::~SmartPtr<ITSLicensePolicy>(void)
0x180024142  lea     rcx, [rbx+658h]
0x180024149  call    ??1?$SmartPtr@VITSLicensePolicy@@@@QEAA@XZ; SmartPtr<ITSLicensePolicy>::~SmartPtr<ITSLicensePolicy>(void)
0x18002414e  lea     rcx, [rbx+650h]
0x180024155  call    ??1?$SmartPtr@VITSLicensePolicy@@@@QEAA@XZ; SmartPtr<ITSLicensePolicy>::~SmartPtr<ITSLicensePolicy>(void)
0x18002415a  lea     rcx, [rbx+648h]
0x180024161  call    ??1?$SmartPtr@VITSLicensePolicy@@@@QEAA@XZ; SmartPtr<ITSLicensePolicy>::~SmartPtr<ITSLicensePolicy>(void)
0x180024166  lea     rcx, [rbx+640h]; void *
0x18002416d  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180024172  lea     rcx, [rbx+638h]; void *
0x180024179  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18002417e  lea     rax, ??_7?$CTSPrivateObject@VIEnforcementCore@@@@6B@; const CTSPrivateObject<IEnforcementCore>::`vftable'
0x180024185  mov     [rbx], rax
0x180024188  lea     rcx, [rbx+628h]; struct _LIST_ENTRY *
0x18002418f  mov     rbx, [rsp+28h+arg_0]
0x180024194  add     rsp, 20h
0x180024198  pop     rdi
0x180024199  jmp     ?RemoveTrackingObject@@YAXPEAU_LIST_ENTRY@@@Z; RemoveTrackingObject(_LIST_ENTRY *)
```
