# WpUnhandledExceptionFilter(_EXCEPTION_POINTERS *)

- ea: `0x140002720`
- end: `0x1400027a8`
- name: `?WpUnhandledExceptionFilter@@YAJPEAU_EXCEPTION_POINTERS@@@Z`
- size: `136`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140002720`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x14000276a`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x14000276a`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x140002761`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x140002779`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x140002761`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x140002779`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140002736`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140002736`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14000274d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14000274d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x14000278a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x14000278a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140002759`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140002759`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002795`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002795`

## pseudocode

```c
__int64 __fastcall WpUnhandledExceptionFilter(struct _EXCEPTION_POINTERS *ExceptionInfo)
{
  HANDLE CurrentThread; // rax
  BOOL v3; // edi
  unsigned int v4; // ebx
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  v3 = OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle);
  if ( v3 )
    RevertToSelf();
  SetUnhandledExceptionFilter(0);
  v4 = UnhandledExceptionFilter(ExceptionInfo);
  SetUnhandledExceptionFilter(WpUnhandledExceptionFilter);
  if ( v3 )
  {
    SetThreadToken(0, TokenHandle);
    CloseHandle(TokenHandle);
  }
  return v4;
}

```

## disassembly

```asm
0x140002720  mov     [rsp+arg_0], rbx
0x140002725  push    rdi
0x140002726  sub     rsp, 20h
0x14000272a  mov     rbx, rcx
0x14000272d  mov     [rsp+28h+TokenHandle], 0
0x140002736  call    cs:__imp_GetCurrentThread
0x14000273c  mov     edx, 4; DesiredAccess
0x140002741  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x140002746  mov     rcx, rax; ThreadHandle
0x140002749  lea     r8d, [rdx-3]; OpenAsSelf
0x14000274d  call    cs:__imp_OpenThreadToken
0x140002753  mov     edi, eax
0x140002755  test    eax, eax
0x140002757  jz      short loc_14000275F
0x140002759  call    cs:__imp_RevertToSelf
0x14000275f  xor     ecx, ecx; lpTopLevelExceptionFilter
0x140002761  call    cs:__imp_SetUnhandledExceptionFilter
0x140002767  mov     rcx, rbx; ExceptionInfo
0x14000276a  call    cs:__imp_UnhandledExceptionFilter
0x140002770  lea     rcx, ?WpUnhandledExceptionFilter@@YAJPEAU_EXCEPTION_POINTERS@@@Z; lpTopLevelExceptionFilter
0x140002777  mov     ebx, eax
0x140002779  call    cs:__imp_SetUnhandledExceptionFilter
0x14000277f  test    edi, edi
0x140002781  jz      short loc_14000279B
0x140002783  mov     rdx, [rsp+28h+TokenHandle]; Token
0x140002788  xor     ecx, ecx; Thread
0x14000278a  call    cs:__imp_SetThreadToken
0x140002790  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x140002795  call    cs:__imp_CloseHandle
0x14000279b  mov     eax, ebx
0x14000279d  mov     rbx, [rsp+28h+arg_0]
0x1400027a2  add     rsp, 20h
0x1400027a6  pop     rdi
0x1400027a7  retn
```
