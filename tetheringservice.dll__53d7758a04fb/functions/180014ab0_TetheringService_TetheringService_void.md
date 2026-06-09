# TetheringService::~TetheringService(void)

- ea: `0x180014ab0`
- end: `0x180014bbe`
- name: `??1TetheringService@@QEAA@XZ`
- size: `270`
- prototype: `void __fastcall(TetheringService *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x18001b810`

## callees

- `0x18000bf4c`
- `0x18000f920`
- `0x18000ff48`
- `0x180014ab0`
- `0x180024818`
- `0x180026930`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014afc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014b09`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014b16`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014b23`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014b30`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014b3d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014b4a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014b7e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014afc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014b09`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014b16`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014b23`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014b30`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014b3d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014b4a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014b7e`

## pseudocode

```c
void __fastcall TetheringService::~TetheringService(TetheringService *this)
{
  *(_QWORD *)this = &TetheringService::`vftable';
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 272));
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 34);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1304));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1408));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1448));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1488));
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1752));
  CNsiInterfaceMonitor::StopMonitor((TetheringService *)((char *)this + 1712));
  BtPanHandler::~BtPanHandler((TetheringService *)((char *)this + 1184));
  EntitlementMgr::Uninitialize((TetheringService *)((char *)this + 568));
  InterfaceMgr::~InterfaceMgr((TetheringService *)((char *)this + 352));
}

```

## disassembly

```asm
0x180014ab0  mov     [rsp+arg_0], rbx
0x180014ab5  push    rdi
0x180014ab6  sub     rsp, 20h
0x180014aba  lea     rax, ??_7TetheringService@@6B@; const TetheringService::`vftable'
0x180014ac1  mov     rbx, rcx
0x180014ac4  mov     [rcx], rax
0x180014ac7  mov     rcx, cs:WPP_GLOBAL_Control
0x180014ace  lea     rdi, WPP_GLOBAL_Control
0x180014ad5  cmp     rcx, rdi
0x180014ad8  jz      short loc_180014AF5
0x180014ada  test    byte ptr [rcx+1Ch], 8
0x180014ade  jz      short loc_180014AF5
0x180014ae0  mov     rcx, [rcx+10h]
0x180014ae4  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x180014aeb  mov     edx, 0Ch
0x180014af0  call    WPP_SF_
0x180014af5  lea     rcx, [rbx+0E8h]; lpCriticalSection
0x180014afc  call    cs:__imp_DeleteCriticalSection
0x180014b02  lea     rcx, [rbx+110h]; lpCriticalSection
0x180014b09  call    cs:__imp_DeleteCriticalSection
0x180014b0f  lea     rcx, [rbx+550h]; lpCriticalSection
0x180014b16  call    cs:__imp_DeleteCriticalSection
0x180014b1c  lea     rcx, [rbx+518h]; lpCriticalSection
0x180014b23  call    cs:__imp_DeleteCriticalSection
0x180014b29  lea     rcx, [rbx+580h]; lpCriticalSection
0x180014b30  call    cs:__imp_DeleteCriticalSection
0x180014b36  lea     rcx, [rbx+5A8h]; lpCriticalSection
0x180014b3d  call    cs:__imp_DeleteCriticalSection
0x180014b43  lea     rcx, [rbx+5D0h]; lpCriticalSection
0x180014b4a  call    cs:__imp_DeleteCriticalSection
0x180014b50  mov     rcx, cs:WPP_GLOBAL_Control
0x180014b57  cmp     rcx, rdi
0x180014b5a  jz      short loc_180014B77
0x180014b5c  test    byte ptr [rcx+1Ch], 8
0x180014b60  jz      short loc_180014B77
0x180014b62  mov     rcx, [rcx+10h]
0x180014b66  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x180014b6d  mov     edx, 0Dh
0x180014b72  call    WPP_SF_
0x180014b77  lea     rcx, [rbx+6D8h]; lpCriticalSection
0x180014b7e  call    cs:__imp_DeleteCriticalSection
0x180014b84  lea     rcx, [rbx+6B0h]; this
0x180014b8b  call    ?StopMonitor@CNsiInterfaceMonitor@@QEAAXXZ; CNsiInterfaceMonitor::StopMonitor(void)
0x180014b90  lea     rcx, [rbx+4A0h]; this
0x180014b97  call    ??1BtPanHandler@@QEAA@XZ; BtPanHandler::~BtPanHandler(void)
0x180014b9c  lea     rcx, [rbx+238h]; this
0x180014ba3  call    ?Uninitialize@EntitlementMgr@@QEAAXXZ; EntitlementMgr::Uninitialize(void)
0x180014ba8  lea     rcx, [rbx+160h]; this
0x180014baf  mov     rbx, [rsp+28h+arg_0]
0x180014bb4  add     rsp, 20h
0x180014bb8  pop     rdi
0x180014bb9  jmp     ??1InterfaceMgr@@QEAA@XZ; InterfaceMgr::~InterfaceMgr(void)
```
