# CBridgeWindow::_GetHostId(unsigned __int64 *)

- ea: `0x180052dfc`
- end: `0x180052fcf`
- name: `?_GetHostId@CBridgeWindow@@AEAAJPEA_K@Z`
- size: `467`
- prototype: `int(CBridgeWindow *__hidden this, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x18005ddc0`
- `0x180060760`

## callees

- `0x18002bd44`
- `0x180036c2c`
- `0x18003729c`
- `0x18004c9a0`
- `0x180052dfc`
- `0x1800605a0`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052eb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052eb6`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180052f35`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180052f35`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180052e98`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180052ed2`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180052e98`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180052ed2`
- `ntdll!RtlQueryTokenHostIdAsUlong64` at `0x180052f63`
- `ntdll!RtlQueryTokenHostIdAsUlong64` at `0x180052f63`
- `USER32!GetWindowThreadProcessId` at `0x180052e81`
- `USER32!GetWindowThreadProcessId` at `0x180052e81`

## pseudocode

```c
__int64 __fastcall CBridgeWindow::_GetHostId(CBridgeWindow *this, unsigned __int64 *a2)
{
  unsigned __int64 v2; // rax
  __int64 v5; // rcx
  int v6; // eax
  unsigned int v7; // esi
  HWND v9; // rcx
  HANDLE v10; // rsi
  const char *v11; // r9
  HANDLE v12; // rax
  unsigned int LastError; // ebx
  const char *v14; // r9
  int v15; // eax
  int TokenHostIdAsUlong64; // eax
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  DWORD dwProcessId; // [rsp+40h] [rbp+20h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp+28h] BYREF
  HANDLE v21; // [rsp+50h] [rbp+30h] BYREF

  v2 = *((_QWORD *)this + 50);
  *a2 = v2;
  if ( v2 != -1 )
    return 0;
  v5 = *((_QWORD *)this + 43);
  if ( v5 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 72LL))(v5);
    v7 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x65E,
        (unsigned int)"shell\\windowsuiimmersive\\applicationhost\\bridgewindow.cpp",
        (const char *)(unsigned int)v6,
        savedregs);
      return v7;
    }
    goto LABEL_18;
  }
  v9 = (HWND)*((_QWORD *)this + 24);
  if ( v9 )
  {
    dwProcessId = 0;
    GetWindowThreadProcessId(v9, &dwProcessId);
    v10 = OpenProcess(0x101000u, 0, dwProcessId);
    v21 = v10;
    if ( (((unsigned __int64)v10 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 && GetLastError() == 5 )
    {
      v12 = OpenProcess(0x100400u, 0, dwProcessId);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &v21,
        v12);
      v10 = v21;
    }
    if ( (((unsigned __int64)v10 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x674,
                    (unsigned int)"shell\\windowsuiimmersive\\applicationhost\\bridgewindow.cpp",
                    v11);
LABEL_16:
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v21);
      return LastError;
    }
    TokenHandle = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &TokenHandle,
      0);
    if ( !OpenProcessToken(v10, 8u, &TokenHandle) )
    {
      v15 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x677,
              (unsigned int)"shell\\windowsuiimmersive\\applicationhost\\bridgewindow.cpp",
              v14);
LABEL_15:
      LastError = v15;
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      goto LABEL_16;
    }
    TokenHostIdAsUlong64 = RtlQueryTokenHostIdAsUlong64(TokenHandle, a2);
    if ( TokenHostIdAsUlong64 < 0 )
    {
      v15 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x678,
              (unsigned int)"shell\\windowsuiimmersive\\applicationhost\\bridgewindow.cpp",
              (const char *)(unsigned int)TokenHostIdAsUlong64,
              savedregs);
      goto LABEL_15;
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v21);
  }
LABEL_18:
  *((_QWORD *)this + 50) = *a2;
  return 0;
}

```

## disassembly

```asm
0x180052dfc  mov     [rsp-18h+arg_18], rbx
0x180052e01  push    rbp
0x180052e02  push    rsi
0x180052e03  push    rdi; int
0x180052e04  mov     rbp, rsp
0x180052e07  sub     rsp, 20h
0x180052e0b  mov     rax, [rcx+190h]
0x180052e12  mov     rdi, rdx
0x180052e15  mov     [rdx], rax
0x180052e18  mov     rbx, rcx
0x180052e1b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180052e1f  jnz     loc_180052FBF
0x180052e25  mov     rcx, [rcx+158h]
0x180052e2c  test    rcx, rcx
0x180052e2f  jz      short loc_180052E66
0x180052e31  mov     rax, [rcx]
0x180052e34  mov     rax, [rax+48h]
0x180052e38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052e3d  mov     esi, eax
0x180052e3f  test    eax, eax
0x180052e41  jns     loc_180052FB5
0x180052e47  mov     rcx, [rbp+18h]; this
0x180052e4b  lea     r8, aShellWindowsui_14; "shell\\windowsuiimmersive\\applicationh"...
0x180052e52  mov     r9d, eax; char *
0x180052e55  mov     edx, 65Eh; void *
0x180052e5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052e5f  mov     eax, esi
0x180052e61  jmp     loc_180052FC1
0x180052e66  mov     rcx, [rbx+0C0h]; hWnd
0x180052e6d  test    rcx, rcx
0x180052e70  jz      loc_180052FB5
0x180052e76  lea     rdx, [rbp+dwProcessId]; lpdwProcessId
0x180052e7a  mov     [rbp+dwProcessId], 0
0x180052e81  call    cs:__imp_GetWindowThreadProcessId
0x180052e88  nop     dword ptr [rax+rax+00h]
0x180052e8d  mov     r8d, [rbp+dwProcessId]; dwProcessId
0x180052e91  xor     edx, edx; bInheritHandle
0x180052e93  mov     ecx, 101000h; dwDesiredAccess
0x180052e98  call    cs:__imp_OpenProcess
0x180052e9f  nop     dword ptr [rax+rax+00h]
0x180052ea4  mov     rsi, rax
0x180052ea7  mov     [rbp+arg_10], rax
0x180052eab  inc     rax
0x180052eae  test    rax, 0FFFFFFFFFFFFFFFEh
0x180052eb4  jnz     short loc_180052EEE
0x180052eb6  call    cs:__imp_GetLastError
0x180052ebd  nop     dword ptr [rax+rax+00h]
0x180052ec2  cmp     eax, 5
0x180052ec5  jnz     short loc_180052EEE
0x180052ec7  mov     r8d, [rbp+dwProcessId]; dwProcessId
0x180052ecb  xor     edx, edx; bInheritHandle
0x180052ecd  mov     ecx, 100400h; dwDesiredAccess
0x180052ed2  call    cs:__imp_OpenProcess
0x180052ed9  nop     dword ptr [rax+rax+00h]
0x180052ede  mov     rdx, rax
0x180052ee1  lea     rcx, [rbp+arg_10]
0x180052ee5  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180052eea  mov     rsi, [rbp+arg_10]
0x180052eee  lea     rax, [rsi+1]
0x180052ef2  test    rax, 0FFFFFFFFFFFFFFFEh
0x180052ef8  jnz     short loc_180052F16
0x180052efa  mov     rcx, [rbp+18h]; this
0x180052efe  lea     r8, aShellWindowsui_14; "shell\\windowsuiimmersive\\applicationh"...
0x180052f05  mov     edx, 674h; void *
0x180052f0a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180052f0f  mov     ebx, eax
0x180052f11  jmp     loc_180052F96
0x180052f16  xor     edx, edx
0x180052f18  mov     [rbp+TokenHandle], 0
0x180052f20  lea     rcx, [rbp+TokenHandle]
0x180052f24  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180052f29  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180052f2d  mov     edx, 8; DesiredAccess
0x180052f32  mov     rcx, rsi; ProcessHandle
0x180052f35  call    cs:__imp_OpenProcessToken
0x180052f3c  nop     dword ptr [rax+rax+00h]
0x180052f41  test    eax, eax
0x180052f43  jnz     short loc_180052F5C
0x180052f45  mov     rcx, [rbp+18h]; this
0x180052f49  lea     r8, aShellWindowsui_14; "shell\\windowsuiimmersive\\applicationh"...
0x180052f50  mov     edx, 677h; void *
0x180052f55  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180052f5a  jmp     short loc_180052F8B
0x180052f5c  mov     rcx, [rbp+TokenHandle]
0x180052f60  mov     rdx, rdi
0x180052f63  call    cs:__imp_RtlQueryTokenHostIdAsUlong64
0x180052f6a  nop     dword ptr [rax+rax+00h]
0x180052f6f  test    eax, eax
0x180052f71  jns     short loc_180052FA3
0x180052f73  mov     rcx, [rbp+18h]; this
0x180052f77  lea     r8, aShellWindowsui_14; "shell\\windowsuiimmersive\\applicationh"...
0x180052f7e  mov     r9d, eax; char *
0x180052f81  mov     edx, 678h; void *
0x180052f86  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180052f8b  lea     rcx, [rbp+TokenHandle]
0x180052f8f  mov     ebx, eax
0x180052f91  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180052f96  lea     rcx, [rbp+arg_10]
0x180052f9a  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180052f9f  mov     eax, ebx
0x180052fa1  jmp     short loc_180052FC1
0x180052fa3  lea     rcx, [rbp+TokenHandle]
0x180052fa7  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180052fac  lea     rcx, [rbp+arg_10]
0x180052fb0  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180052fb5  mov     rax, [rdi]
0x180052fb8  mov     [rbx+190h], rax
0x180052fbf  xor     eax, eax
0x180052fc1  mov     rbx, [rsp+20h+arg_18]
0x180052fc6  add     rsp, 20h
0x180052fca  pop     rdi
0x180052fcb  pop     rsi
0x180052fcc  pop     rbp
0x180052fcd  retn
```
