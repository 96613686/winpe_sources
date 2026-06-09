# Windows::Power::Manager::CreatePowerRequest(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x1800b187c`
- end: `0x1800b196c`
- name: `?CreatePowerRequest@Manager@Power@Windows@@AEAAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `240`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800b1a50`

## callees

- `0x180010f24`
- `0x1800b187c`
- `0x1800dd930`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1904`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1904`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b1917`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b1917`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b190f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b190f`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerCreateRequest` at `0x1800b18d5`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerCreateRequest` at `0x1800b18d5`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerSetRequest` at `0x1800b18eb`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerSetRequest` at `0x1800b18eb`

## string_xrefs

- `0x1800b1943`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Power.cpp`
- `0x1800b195a`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Power.cpp`

## pseudocode

```c
void __fastcall Windows::Power::Manager::CreatePowerRequest(__int64 a1, HMODULE a2)
{
  bool v3; // cc
  HANDLE v4; // rax
  const char *v5; // r9
  HANDLE v6; // rsi
  const char *v7; // r9
  void *v8; // rdi
  DWORD LastError; // ebx
  _REASON_CONTEXT Context; // [rsp+20h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( *(_QWORD *)(a1 + 8) == -1 || !*(_QWORD *)(a1 + 8) )
  {
    v3 = *((_QWORD *)a2 + 3) <= 7u;
    *(_OWORD *)(&Context.Reason.SimpleReasonString + 1) = 0;
    Context.Version = 0;
    Context.Flags = 1;
    if ( !v3 )
      a2 = *(HMODULE *)a2;
    Context.Reason.Detailed.LocalizedReasonModule = a2;
    v4 = PowerCreateRequest(&Context);
    v6 = v4;
    if ( !v4 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x26,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Power.cpp",
        v5);
    if ( !PowerSetRequest(v4, PowerRequestExecutionRequired) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x27,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Power.cpp",
        v7);
    v8 = *(void **)(a1 + 8);
    if ( v8 != (void *)-1LL )
    {
      if ( v8 )
      {
        LastError = GetLastError();
        CloseHandle(v8);
        SetLastError(LastError);
      }
    }
    *(_QWORD *)(a1 + 8) = v6;
  }
}

```

## disassembly

```asm
0x1800b187c  mov     [rsp+arg_10], rbx
0x1800b1881  push    rbp
0x1800b1882  push    rsi
0x1800b1883  push    rdi
0x1800b1884  sub     rsp, 50h
0x1800b1888  mov     rax, cs:__security_cookie
0x1800b188f  xor     rax, rsp
0x1800b1892  mov     [rsp+68h+var_28], rax
0x1800b1897  cmp     qword ptr [rcx+8], 0FFFFFFFFFFFFFFFFh
0x1800b189c  mov     rbp, rcx
0x1800b189f  jz      short loc_1800B18A8
0x1800b18a1  cmp     qword ptr [rcx+8], 0
0x1800b18a6  jnz     short loc_1800B1921
0x1800b18a8  cmp     qword ptr [rdx+18h], 7
0x1800b18ad  xorps   xmm0, xmm0
0x1800b18b0  movdqu  xmmword ptr [rsp+68h+Context.Reason+8], xmm0
0x1800b18b6  mov     [rsp+68h+Context.Version], 0
0x1800b18be  mov     [rsp+68h+Context.Flags], 1
0x1800b18c6  jbe     short loc_1800B18CB
0x1800b18c8  mov     rdx, [rdx]
0x1800b18cb  lea     rcx, [rsp+68h+Context]; Context
0x1800b18d0  mov     qword ptr [rsp+68h+Context.Reason], rdx
0x1800b18d5  call    cs:__imp_PowerCreateRequest
0x1800b18db  mov     rsi, rax
0x1800b18de  test    rax, rax
0x1800b18e1  jz      short loc_1800B1955
0x1800b18e3  mov     edx, 3; RequestType
0x1800b18e8  mov     rcx, rax; PowerRequest
0x1800b18eb  call    cs:__imp_PowerSetRequest
0x1800b18f1  test    eax, eax
0x1800b18f3  jz      short loc_1800B193E
0x1800b18f5  mov     rdi, [rbp+8]
0x1800b18f9  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800b18fd  jz      short loc_1800B191D
0x1800b18ff  test    rdi, rdi
0x1800b1902  jz      short loc_1800B191D
0x1800b1904  call    cs:__imp_GetLastError
0x1800b190a  mov     rcx, rdi; hObject
0x1800b190d  mov     ebx, eax
0x1800b190f  call    cs:__imp_CloseHandle
0x1800b1915  mov     ecx, ebx; dwErrCode
0x1800b1917  call    cs:__imp_SetLastError
0x1800b191d  mov     [rbp+8], rsi
0x1800b1921  mov     rcx, [rsp+68h+var_28]
0x1800b1926  xor     rcx, rsp; StackCookie
0x1800b1929  call    __security_check_cookie
0x1800b192e  mov     rbx, [rsp+68h+arg_10]
0x1800b1936  add     rsp, 50h
0x1800b193a  pop     rdi
0x1800b193b  pop     rsi
0x1800b193c  pop     rbp
0x1800b193d  retn
0x1800b193e  mov     rcx, [rsp+68h]; this
0x1800b1943  lea     r8, aCW1SSrcOrchest_15; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1800b194a  mov     edx, 27h ; '''; void *
0x1800b194f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800b1955  mov     rcx, [rsp+68h]; this
0x1800b195a  lea     r8, aCW1SSrcOrchest_15; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1800b1961  mov     edx, 26h ; '&'; void *
0x1800b1966  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
