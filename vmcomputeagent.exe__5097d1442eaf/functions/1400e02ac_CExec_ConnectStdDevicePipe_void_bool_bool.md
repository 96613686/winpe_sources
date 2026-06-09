# CExec::ConnectStdDevicePipe(void *,bool,bool)

- ea: `0x1400e02ac`
- end: `0x1400e042a`
- name: `?ConnectStdDevicePipe@CExec@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEAX_N1@Z`
- size: `382`
- prototype: `__int64 __fastcall(LPHANDLE lpTargetHandle, HANDLE hSourceHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400e0b10`

## callees

- `0x140005360`
- `0x14000ddac`
- `0x1400e02ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400e03c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400e03c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400e03ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400e03ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400e02fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400e0303`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400e02fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400e0303`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1400e032d`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1400e032d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400e03b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400e03b9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400e0398`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400e0398`

## string_xrefs

- `0x1400e03fe`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x1400e0418`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
LPHANDLE __fastcall CExec::ConnectStdDevicePipe(
        LPHANDLE lpTargetHandle,
        HANDLE hSourceHandle,
        unsigned __int8 a3,
        unsigned __int8 a4)
{
  DWORD v6; // esi
  HANDLE CurrentProcess; // rbx
  HANDLE v8; // rax
  const char *v9; // r9
  HANDLE v10; // rsi
  const char *v11; // r9
  HANDLE v12; // rbp
  DWORD LastError; // ebx
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+50h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  *lpTargetHandle = (HANDLE)-1LL;
  v6 = (a3 + 1) << 30;
  if ( hSourceHandle )
  {
    *lpTargetHandle = (HANDLE)-1LL;
    CurrentProcess = GetCurrentProcess();
    v8 = GetCurrentProcess();
    if ( !DuplicateHandle(v8, hSourceHandle, CurrentProcess, lpTargetHandle, v6 | 0x100000, 1, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x71,
        (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
        v9);
  }
  else
  {
    *(_OWORD *)&SecurityAttributes.nLength = 0;
    *(&SecurityAttributes.bInheritHandle + 1) = 0;
    SecurityAttributes.nLength = 24;
    SecurityAttributes.bInheritHandle = 1;
    v10 = CreateFileW(L"nul", v6, 0, &SecurityAttributes, 3u, (a4 << 30) | ((a3 ^ 1u) << 31), 0);
    v12 = *lpTargetHandle;
    if ( (char *)*lpTargetHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      LastError = GetLastError();
      CloseHandle(v12);
      SetLastError(LastError);
    }
    *lpTargetHandle = v10;
    if ( (((unsigned __int64)v10 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x86,
        (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
        v11);
  }
  return lpTargetHandle;
}

```

## disassembly

```asm
0x1400e02ac  mov     [rsp+arg_10], rbx
0x1400e02b1  push    rbp
0x1400e02b2  push    rsi
0x1400e02b3  push    rdi
0x1400e02b4  sub     rsp, 70h
0x1400e02b8  mov     rax, cs:__security_cookie
0x1400e02bf  xor     rax, rsp
0x1400e02c2  mov     [rsp+88h+var_20], rax
0x1400e02c7  mov     rbp, rdx
0x1400e02ca  mov     rdi, rcx
0x1400e02cd  mov     [rsp+88h+var_40], rcx
0x1400e02d2  mov     [rsp+88h+var_48], 0
0x1400e02da  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400e02de  mov     [rcx], rax
0x1400e02e1  mov     [rsp+88h+var_48], 1
0x1400e02e9  movzx   esi, r8b
0x1400e02ed  inc     esi
0x1400e02ef  shl     esi, 1Eh
0x1400e02f2  test    rdx, rdx
0x1400e02f5  jz      short loc_1400E0340
0x1400e02f7  mov     [rcx], rax
0x1400e02fa  call    cs:__imp_GetCurrentProcess
0x1400e0300  mov     rbx, rax
0x1400e0303  call    cs:__imp_GetCurrentProcess
0x1400e0309  bts     esi, 14h
0x1400e030d  mov     [rsp+88h+dwOptions], 0; dwOptions
0x1400e0315  mov     [rsp+88h+bInheritHandle], 1; bInheritHandle
0x1400e031d  mov     [rsp+88h+dwDesiredAccess], esi; dwDesiredAccess
0x1400e0321  mov     r9, rdi; lpTargetHandle
0x1400e0324  mov     r8, rbx; hTargetProcessHandle
0x1400e0327  mov     rdx, rbp; hSourceHandle
0x1400e032a  mov     rcx, rax; hSourceProcessHandle
0x1400e032d  call    cs:__imp_DuplicateHandle
0x1400e0333  test    eax, eax
0x1400e0335  jz      loc_1400E0410
0x1400e033b  jmp     loc_1400E03D6
0x1400e0340  xorps   xmm0, xmm0
0x1400e0343  xor     eax, eax
0x1400e0345  movups  xmmword ptr [rsp+88h+SecurityAttributes.nLength], xmm0
0x1400e034a  mov     qword ptr [rsp+88h+SecurityAttributes.bInheritHandle], rax
0x1400e034f  mov     [rsp+88h+SecurityAttributes.nLength], 18h
0x1400e0357  mov     [rsp+88h+SecurityAttributes.bInheritHandle], 1
0x1400e035f  movzx   ecx, r8b
0x1400e0363  xor     ecx, 1
0x1400e0366  shl     ecx, 1Fh
0x1400e0369  movzx   eax, r9b
0x1400e036d  shl     eax, 1Eh
0x1400e0370  or      ecx, eax
0x1400e0372  mov     qword ptr [rsp+88h+dwOptions], 0; hTemplateFile
0x1400e037b  mov     [rsp+88h+bInheritHandle], ecx; dwFlagsAndAttributes
0x1400e037f  mov     [rsp+88h+dwDesiredAccess], 3; dwCreationDisposition
0x1400e0387  lea     r9, [rsp+88h+SecurityAttributes]; lpSecurityAttributes
0x1400e038c  xor     r8d, r8d; dwShareMode
0x1400e038f  mov     edx, esi; dwDesiredAccess
0x1400e0391  lea     rcx, aNul; "nul"
0x1400e0398  call    cs:__imp_CreateFileW
0x1400e039e  mov     rsi, rax
0x1400e03a1  mov     rbp, [rdi]
0x1400e03a4  lea     rax, [rbp-1]
0x1400e03a8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400e03ac  ja      short loc_1400E03C7
0x1400e03ae  call    cs:__imp_GetLastError
0x1400e03b4  mov     ebx, eax
0x1400e03b6  mov     rcx, rbp; hObject
0x1400e03b9  call    cs:__imp_CloseHandle
0x1400e03bf  mov     ecx, ebx; dwErrCode
0x1400e03c1  call    cs:__imp_SetLastError
0x1400e03c7  mov     [rdi], rsi
0x1400e03ca  lea     rax, [rsi+1]
0x1400e03ce  test    rax, 0FFFFFFFFFFFFFFFEh
0x1400e03d4  jz      short loc_1400E03F6
0x1400e03d6  mov     rax, rdi
0x1400e03d9  mov     rcx, [rsp+88h+var_20]
0x1400e03de  xor     rcx, rsp; StackCookie
0x1400e03e1  call    __security_check_cookie
0x1400e03e6  mov     rbx, [rsp+88h+arg_10]
0x1400e03ee  add     rsp, 70h
0x1400e03f2  pop     rdi
0x1400e03f3  pop     rsi
0x1400e03f4  pop     rbp
0x1400e03f5  retn
0x1400e03f6  mov     rcx, [rsp+88h]; this
0x1400e03fe  lea     r8, aOnecoreVmCompu_27; "onecore\\vm\\compute\\service\\cexec\\l"...
0x1400e0405  mov     edx, 86h; void *
0x1400e040a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400e0410  mov     rcx, [rsp+88h]; this
0x1400e0418  lea     r8, aOnecoreVmCompu_27; "onecore\\vm\\compute\\service\\cexec\\l"...
0x1400e041f  mov     edx, 71h ; 'q'; void *
0x1400e0424  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
