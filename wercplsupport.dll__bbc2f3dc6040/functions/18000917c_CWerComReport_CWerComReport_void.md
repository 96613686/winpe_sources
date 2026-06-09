# CWerComReport::~CWerComReport(void)

- ea: `0x18000917c`
- end: `0x18000923e`
- name: `??1CWerComReport@@UEAA@XZ`
- size: `194`
- prototype: `void __fastcall(CWerComReport *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009ac0`

## callees

- `0x180002850`
- `0x180007624`
- `0x180007d20`
- `0x180007fe0`
- `0x18000917c`
- `0x180013010`

## import_xrefs

- `wer!WerReportCloseHandle` at `0x1800091ef`
- `wer!WerReportCloseHandle` at `0x18000921d`
- `wer!WerReportCloseHandle` at `0x1800091ef`
- `wer!WerReportCloseHandle` at `0x18000921d`

## pseudocode

```c
void __fastcall CWerComReport::~CWerComReport(CWerComReport *this)
{
  void *v2; // rcx
  __int64 v3; // rcx
  void *v4; // rcx
  int v5; // [rsp+30h] [rbp+8h] BYREF

  v5 = 2;
  *(_QWORD *)this = &CWerComReport::`vftable'{for `CManagedObj'};
  *((_QWORD *)this + 3) = &CWerComReport::`vftable'{for `IWerReport'};
  if ( (int)CAutoImpersonate::ImpersonateUserHighestPrivs((CAutoImpersonate *)&v5) < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids);
  }
  v2 = (void *)*((_QWORD *)this + 4);
  *((_QWORD *)this + 4) = 0;
  if ( v2 )
    WerReportCloseHandle(v2);
  v3 = *((_QWORD *)this + 5);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  CAutoImpersonate::~CAutoImpersonate((CAutoImpersonate *)&v5);
  v4 = (void *)*((_QWORD *)this + 4);
  if ( v4 )
    WerReportCloseHandle(v4);
  *(_QWORD *)this = &CManagedObj::`vftable';
  CObjectManager::UnLockServer((CObjectManager *)&CObjectManager::ms_instance);
}

```

## disassembly

```asm
0x18000917c  push    rbx
0x18000917e  sub     rsp, 20h
0x180009182  lea     rax, ??_7CWerComReport@@6BCManagedObj@@@; const CWerComReport::`vftable'{for `CManagedObj'}
0x180009189  mov     [rsp+28h+arg_0], 2
0x180009191  mov     [rcx], rax
0x180009194  mov     rbx, rcx
0x180009197  lea     rax, ??_7CWerComReport@@6BIWerReport@@@; const CWerComReport::`vftable'{for `IWerReport'}
0x18000919e  mov     [rcx+18h], rax
0x1800091a2  lea     rcx, [rsp+28h+arg_0]; this
0x1800091a7  call    ?ImpersonateUserHighestPrivs@CAutoImpersonate@@QEAAJXZ; CAutoImpersonate::ImpersonateUserHighestPrivs(void)
0x1800091ac  test    eax, eax
0x1800091ae  jns     short loc_1800091DE
0x1800091b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800091b7  lea     rax, WPP_GLOBAL_Control
0x1800091be  cmp     rcx, rax
0x1800091c1  jz      short loc_1800091DE
0x1800091c3  test    byte ptr [rcx+1Ch], 1
0x1800091c7  jz      short loc_1800091DE
0x1800091c9  mov     rcx, [rcx+10h]
0x1800091cd  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x1800091d4  mov     edx, 19h
0x1800091d9  call    WPP_SF_
0x1800091de  mov     rcx, [rbx+20h]; hReportHandle
0x1800091e2  mov     qword ptr [rbx+20h], 0
0x1800091ea  test    rcx, rcx
0x1800091ed  jz      short loc_1800091F5
0x1800091ef  call    cs:__imp_WerReportCloseHandle
0x1800091f5  mov     rcx, [rbx+28h]
0x1800091f9  test    rcx, rcx
0x1800091fc  jz      short loc_18000920A
0x1800091fe  mov     rax, [rcx]
0x180009201  mov     rax, [rax+10h]
0x180009205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000920a  lea     rcx, [rsp+28h+arg_0]; this
0x18000920f  call    ??1CAutoImpersonate@@QEAA@XZ; CAutoImpersonate::~CAutoImpersonate(void)
0x180009214  mov     rcx, [rbx+20h]; hReportHandle
0x180009218  test    rcx, rcx
0x18000921b  jz      short loc_180009223
0x18000921d  call    cs:__imp_WerReportCloseHandle
0x180009223  lea     rax, ??_7CManagedObj@@6B@; const CManagedObj::`vftable'
0x18000922a  lea     rcx, ?ms_instance@CObjectManager@@1V1@A; this
0x180009231  mov     [rbx], rax
0x180009234  add     rsp, 20h
0x180009238  pop     rbx
0x180009239  jmp     ?UnLockServer@CObjectManager@@QEAAXXZ; CObjectManager::UnLockServer(void)
```
