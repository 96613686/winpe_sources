# CUtils::IsCallerAnonymous(void)

- ea: `0x18002d8d8`
- end: `0x18002d974`
- name: `?IsCallerAnonymous@CUtils@@SAJXZ`
- size: `156`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180060800`

## callees

- `0x18000a210`
- `0x18002d8d8`
- `0x18002e78c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d906`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d906`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002d8e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002d8e7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002d8fc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002d8fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d966`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d966`

## string_xrefs

- `0x18002d91e`: `IsCallerSystem: Could not open thread token %x`
- `0x18002d94b`: `IsTokenSid( Anonymous ) failed: 0x%x in %s`

## pseudocode

```c
__int64 CUtils::IsCallerAnonymous(void)
{
  HANDLE CurrentThread; // rax
  void *v1; // rdx
  signed int LastError; // eax
  unsigned int v3; // ebx
  int IsTokenSid; // eax
  void *TokenHandle; // [rsp+30h] [rbp+8h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
  {
    IsTokenSid = CUtils::IsTokenSid(TokenHandle, v1);
    v3 = IsTokenSid;
    if ( IsTokenSid < 0 )
      _DbgPrintMessage(8, "IsTokenSid( Anonymous ) failed: 0x%x in %s", IsTokenSid, "CUtils::IsCallerAnonymous");
  }
  else
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    _DbgPrintMessage(8, "IsCallerSystem: Could not open thread token %x", v3);
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v3;
}

```

## disassembly

```asm
0x18002d8d8  push    rbx
0x18002d8da  sub     rsp, 20h
0x18002d8de  mov     [rsp+28h+TokenHandle], 0
0x18002d8e7  call    cs:__imp_GetCurrentThread
0x18002d8ed  xor     r8d, r8d; OpenAsSelf
0x18002d8f0  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18002d8f5  mov     rcx, rax; ThreadHandle
0x18002d8f8  lea     edx, [r8+8]; DesiredAccess
0x18002d8fc  call    cs:__imp_OpenThreadToken
0x18002d902  test    eax, eax
0x18002d904  jnz     short loc_18002D931
0x18002d906  call    cs:__imp_GetLastError
0x18002d90c  mov     ebx, eax
0x18002d90e  test    eax, eax
0x18002d910  jle     short loc_18002D91B
0x18002d912  movzx   ebx, ax
0x18002d915  or      ebx, 80070000h
0x18002d91b  mov     r8d, ebx
0x18002d91e  lea     rdx, aIscallersystem_1; "IsCallerSystem: Could not open thread t"...
0x18002d925  mov     ecx, 8; int
0x18002d92a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002d92f  jmp     short loc_18002D95C
0x18002d931  mov     rcx, [rsp+28h+TokenHandle]; TokenHandle
0x18002d936  call    ?IsTokenSid@CUtils@@CAJPEAX0@Z; CUtils::IsTokenSid(void *,void *)
0x18002d93b  mov     ebx, eax
0x18002d93d  test    eax, eax
0x18002d93f  jns     short loc_18002D95C
0x18002d941  lea     r9, aCutilsIscaller; "CUtils::IsCallerAnonymous"
0x18002d948  mov     r8d, eax
0x18002d94b  lea     rdx, aIstokensidAnon; "IsTokenSid( Anonymous ) failed: 0x%x in"...
0x18002d952  mov     ecx, 8; int
0x18002d957  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002d95c  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x18002d961  test    rcx, rcx
0x18002d964  jz      short loc_18002D96C
0x18002d966  call    cs:__imp_CloseHandle
0x18002d96c  mov     eax, ebx
0x18002d96e  add     rsp, 20h
0x18002d972  pop     rbx
0x18002d973  retn
```
