# UniversalOrchestrator::~UniversalOrchestrator(void)

- ea: `0x180070bcc`
- end: `0x180070c57`
- name: `??1UniversalOrchestrator@@UEAA@XZ`
- size: `139`
- prototype: `void __fastcall(UniversalOrchestrator *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180070b90`

## callees

- `0x180008ea8`
- `0x1800352d4`
- `0x1800616ac`
- `0x180070bcc`
- `0x180074a6c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180070bfc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180070bfc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070c14`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070c27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070c14`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070c27`

## pseudocode

```c
void __fastcall UniversalOrchestrator::~UniversalOrchestrator(UniversalOrchestrator *this)
{
  void *v2; // rcx
  unsigned int v3; // r8d
  const char *v4; // r9
  void *v5; // rcx
  unsigned int v6; // r8d
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *(_QWORD *)this = &UniversalOrchestrator::`vftable'{for `IUniversalOrchestrator'};
  *((_QWORD *)this + 1) = &UniversalOrchestrator::`vftable'{for `IUniversalOrchestratorInternal'};
  SvcRelease();
  std::vector<std::wstring>::_Tidy((char *)this + 120);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  std::vector<Updater>::~vector<Updater>((char *)this + 32);
  v2 = (void *)*((_QWORD *)this + 3);
  if ( v2 && !CloseHandle(v2) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v3, v4);
  v5 = (void *)*((_QWORD *)this + 2);
  if ( v5 )
  {
    if ( !CloseHandle(v5) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v6, v7);
  }
}

```

## disassembly

```asm
0x180070bcc  push    rbx
0x180070bce  sub     rsp, 20h
0x180070bd2  mov     rbx, rcx
0x180070bd5  lea     rax, ??_7UniversalOrchestrator@@6BIUniversalOrchestrator@@@; const UniversalOrchestrator::`vftable'{for `IUniversalOrchestrator'}
0x180070bdc  mov     [rcx], rax
0x180070bdf  lea     rax, ??_7UniversalOrchestrator@@6BIUniversalOrchestratorInternal@@@; const UniversalOrchestrator::`vftable'{for `IUniversalOrchestratorInternal'}
0x180070be6  mov     [rcx+8], rax
0x180070bea  call    ?SvcRelease@@YAXXZ; SvcRelease(void)
0x180070bef  lea     rcx, [rbx+78h]
0x180070bf3  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180070bf8  lea     rcx, [rbx+38h]; lpCriticalSection
0x180070bfc  call    cs:__imp_DeleteCriticalSection
0x180070c02  lea     rcx, [rbx+20h]
0x180070c06  call    ??1?$vector@VUpdater@@V?$allocator@VUpdater@@@std@@@std@@QEAA@XZ; std::vector<Updater>::~vector<Updater>(void)
0x180070c0b  mov     rcx, [rbx+18h]; hObject
0x180070c0f  test    rcx, rcx
0x180070c12  jz      short loc_180070C1E
0x180070c14  call    cs:__imp_CloseHandle
0x180070c1a  test    eax, eax
0x180070c1c  jz      short loc_180070C47
0x180070c1e  mov     rcx, [rbx+10h]; hObject
0x180070c22  test    rcx, rcx
0x180070c25  jz      short loc_180070C31
0x180070c27  call    cs:__imp_CloseHandle
0x180070c2d  test    eax, eax
0x180070c2f  jz      short loc_180070C37
0x180070c31  add     rsp, 20h
0x180070c35  pop     rbx
0x180070c36  retn
0x180070c37  mov     rcx, [rsp+28h]; this
0x180070c3c  mov     edx, 9D1h; void *
0x180070c41  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180070c47  mov     rcx, [rsp+28h]; this
0x180070c4c  mov     edx, 9D1h; void *
0x180070c51  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
