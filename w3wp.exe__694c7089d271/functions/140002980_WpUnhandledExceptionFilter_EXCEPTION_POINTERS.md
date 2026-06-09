# WpUnhandledExceptionFilter(_EXCEPTION_POINTERS *)

- ea: `0x140002980`
- end: `0x140002a39`
- name: `?WpUnhandledExceptionFilter@@YAJPEAU_EXCEPTION_POINTERS@@@Z`
- size: `185`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140002980`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x1400029e2`
- `api-ms-win-core-errorhandling-l1-1-0!UnhandledExceptionFilter` at `0x1400029e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x1400029d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x1400029f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x1400029d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x1400029f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140002996`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140002996`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1400029b3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1400029b3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x140002a0e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x140002a0e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1400029c5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1400029c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002a1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002a1f`

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
0x140002980  mov     [rsp+arg_0], rbx
0x140002985  push    rdi
0x140002986  sub     rsp, 20h
0x14000298a  mov     rbx, rcx
0x14000298d  mov     [rsp+28h+TokenHandle], 0
0x140002996  call    cs:__imp_GetCurrentThread
0x14000299d  nop     dword ptr [rax+rax+00h]
0x1400029a2  mov     edx, 4; DesiredAccess
0x1400029a7  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x1400029ac  mov     rcx, rax; ThreadHandle
0x1400029af  lea     r8d, [rdx-3]; OpenAsSelf
0x1400029b3  call    cs:__imp_OpenThreadToken
0x1400029ba  nop     dword ptr [rax+rax+00h]
0x1400029bf  mov     edi, eax
0x1400029c1  test    eax, eax
0x1400029c3  jz      short loc_1400029D1
0x1400029c5  call    cs:__imp_RevertToSelf
0x1400029cc  nop     dword ptr [rax+rax+00h]
0x1400029d1  xor     ecx, ecx; lpTopLevelExceptionFilter
0x1400029d3  call    cs:__imp_SetUnhandledExceptionFilter
0x1400029da  nop     dword ptr [rax+rax+00h]
0x1400029df  mov     rcx, rbx; ExceptionInfo
0x1400029e2  call    cs:__imp_UnhandledExceptionFilter
0x1400029e9  nop     dword ptr [rax+rax+00h]
0x1400029ee  lea     rcx, ?WpUnhandledExceptionFilter@@YAJPEAU_EXCEPTION_POINTERS@@@Z; lpTopLevelExceptionFilter
0x1400029f5  mov     ebx, eax
0x1400029f7  call    cs:__imp_SetUnhandledExceptionFilter
0x1400029fe  nop     dword ptr [rax+rax+00h]
0x140002a03  test    edi, edi
0x140002a05  jz      short loc_140002A2B
0x140002a07  mov     rdx, [rsp+28h+TokenHandle]; Token
0x140002a0c  xor     ecx, ecx; Thread
0x140002a0e  call    cs:__imp_SetThreadToken
0x140002a15  nop     dword ptr [rax+rax+00h]
0x140002a1a  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x140002a1f  call    cs:__imp_CloseHandle
0x140002a26  nop     dword ptr [rax+rax+00h]
0x140002a2b  mov     eax, ebx
0x140002a2d  mov     rbx, [rsp+28h+arg_0]
0x140002a32  add     rsp, 20h
0x140002a36  pop     rdi
0x140002a37  retn
```
