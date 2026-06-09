# CUtils::IsCallerAnonymous(void)

- ea: `0x18002f2f0`
- end: `0x18002f3ac`
- name: `?IsCallerAnonymous@CUtils@@SAJXZ`
- size: `188`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180063870`

## callees

- `0x180009940`
- `0x18002f2f0`
- `0x18003028c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f32a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f32a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002f2ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002f2ff`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002f31a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002f31a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f397`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f397`

## string_xrefs

- `0x18002f348`: `IsCallerSystem: Could not open thread token %x`
- `0x18002f37c`: `IsTokenSid( Anonymous ) failed: 0x%x in %s`

## pseudocode

```c
__int64 CUtils::IsCallerAnonymous(void)
{
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  unsigned int v2; // ebx
  int IsTokenSid; // eax
  void *TokenHandle; // [rsp+30h] [rbp+8h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
  {
    IsTokenSid = CUtils::IsTokenSid(TokenHandle, CUtils::pAnonymousSid);
    v2 = IsTokenSid;
    if ( IsTokenSid < 0 )
      _DbgPrintMessage(8, "IsTokenSid( Anonymous ) failed: 0x%x in %s", IsTokenSid, "CUtils::IsCallerAnonymous");
  }
  else
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    _DbgPrintMessage(8, "IsCallerSystem: Could not open thread token %x", v2);
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v2;
}

```

## disassembly

```asm
0x18002f2f0  push    rbx
0x18002f2f2  sub     rsp, 20h
0x18002f2f6  mov     [rsp+28h+TokenHandle], 0
0x18002f2ff  call    cs:__imp_GetCurrentThread
0x18002f306  nop     dword ptr [rax+rax+00h]
0x18002f30b  xor     r8d, r8d; OpenAsSelf
0x18002f30e  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18002f313  mov     rcx, rax; ThreadHandle
0x18002f316  lea     edx, [r8+8]; DesiredAccess
0x18002f31a  call    cs:__imp_OpenThreadToken
0x18002f321  nop     dword ptr [rax+rax+00h]
0x18002f326  test    eax, eax
0x18002f328  jnz     short loc_18002F35B
0x18002f32a  call    cs:__imp_GetLastError
0x18002f331  nop     dword ptr [rax+rax+00h]
0x18002f336  mov     ebx, eax
0x18002f338  test    eax, eax
0x18002f33a  jle     short loc_18002F345
0x18002f33c  movzx   ebx, ax
0x18002f33f  or      ebx, 80070000h
0x18002f345  mov     r8d, ebx
0x18002f348  lea     rdx, aIscallersystem_1; "IsCallerSystem: Could not open thread t"...
0x18002f34f  mov     ecx, 8; int
0x18002f354  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002f359  jmp     short loc_18002F38D
0x18002f35b  mov     rdx, cs:?pAnonymousSid@CUtils@@0PEAXEA; Sid2
0x18002f362  mov     rcx, [rsp+28h+TokenHandle]; TokenHandle
0x18002f367  call    ?IsTokenSid@CUtils@@CAJPEAX0@Z; CUtils::IsTokenSid(void *,void *)
0x18002f36c  mov     ebx, eax
0x18002f36e  test    eax, eax
0x18002f370  jns     short loc_18002F38D
0x18002f372  lea     r9, aCutilsIscaller_0; "CUtils::IsCallerAnonymous"
0x18002f379  mov     r8d, eax
0x18002f37c  lea     rdx, aIstokensidAnon; "IsTokenSid( Anonymous ) failed: 0x%x in"...
0x18002f383  mov     ecx, 8; int
0x18002f388  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002f38d  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x18002f392  test    rcx, rcx
0x18002f395  jz      short loc_18002F3A3
0x18002f397  call    cs:__imp_CloseHandle
0x18002f39e  nop     dword ptr [rax+rax+00h]
0x18002f3a3  mov     eax, ebx
0x18002f3a5  add     rsp, 20h
0x18002f3a9  pop     rbx
0x18002f3aa  retn
```
