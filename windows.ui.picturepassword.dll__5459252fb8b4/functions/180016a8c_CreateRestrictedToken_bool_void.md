# _CreateRestrictedToken(bool,void * *)

- ea: `0x180016a8c`
- end: `0x180016afd`
- name: `?_CreateRestrictedToken@@YAJ_NPEAPEAX@Z`
- size: `113`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180016dfc`

## callees

- `0x1800092b8`
- `0x180016a8c`
- `0x180016b04`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180016abc`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180016abc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180016aa9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180016aa9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016aea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016aea`

## pseudocode

```c
__int64 __fastcall _CreateRestrictedToken(__int64 a1, void **a2)
{
  HANDLE CurrentProcess; // rax
  int RestrictedTokenFromSpecifiedToken; // ebx
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF

  *a2 = 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x8Bu, &TokenHandle)
    || (RestrictedTokenFromSpecifiedToken = ResultFromKnownLastError(), RestrictedTokenFromSpecifiedToken >= 0) )
  {
    RestrictedTokenFromSpecifiedToken = _CreateRestrictedTokenFromSpecifiedToken(0x2000u, TokenHandle, a2);
    CloseHandle(TokenHandle);
  }
  return (unsigned int)RestrictedTokenFromSpecifiedToken;
}

```

## disassembly

```asm
0x180016a8c  mov     [rsp+arg_0], rbx
0x180016a91  push    rdi
0x180016a92  sub     rsp, 20h
0x180016a96  mov     rdi, rdx
0x180016a99  mov     qword ptr [rdx], 0
0x180016aa0  mov     [rsp+28h+TokenHandle], 0
0x180016aa9  call    cs:__imp_GetCurrentProcess
0x180016aaf  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x180016ab4  mov     edx, 8Bh; DesiredAccess
0x180016ab9  mov     rcx, rax; ProcessHandle
0x180016abc  call    cs:__imp_OpenProcessToken
0x180016ac2  test    eax, eax
0x180016ac4  jnz     short loc_180016AD1
0x180016ac6  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180016acb  mov     ebx, eax
0x180016acd  test    eax, eax
0x180016acf  js      short loc_180016AF0
0x180016ad1  mov     rdx, [rsp+28h+TokenHandle]; ExistingTokenHandle
0x180016ad6  mov     r8, rdi; void **
0x180016ad9  mov     ecx, 2000h; nSubAuthority0
0x180016ade  call    ?_CreateRestrictedTokenFromSpecifiedToken@@YAJKPEAXPEAPEAX@Z; _CreateRestrictedTokenFromSpecifiedToken(ulong,void *,void * *)
0x180016ae3  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x180016ae8  mov     ebx, eax
0x180016aea  call    cs:__imp_CloseHandle
0x180016af0  mov     eax, ebx
0x180016af2  mov     rbx, [rsp+28h+arg_0]
0x180016af7  add     rsp, 20h
0x180016afb  pop     rdi
0x180016afc  retn
```
