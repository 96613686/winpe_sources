# GetThreadToken(void * *)

- ea: `0x140009958`
- end: `0x1400099ba`
- name: `?GetThreadToken@@YAJPEAPEAX@Z`
- size: `98`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14005d470`
- `0x140063bc0`
- `0x14006f1b8`

## callees

- `0x140007bdc`
- `0x140009958`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009986`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009986`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140009974`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1400099a6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140009974`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1400099a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140009961`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140009991`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140009961`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140009991`

## pseudocode

```c
__int64 __fastcall GetThreadToken(PHANDLE TokenHandle)
{
  HANDLE CurrentThread; // rax
  HANDLE v4; // rax

  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xEu, 0, TokenHandle) )
    return 0;
  if ( GetLastError() == 5 && (v4 = GetCurrentThread(), OpenThreadToken(v4, 0xEu, 1, TokenHandle)) )
    return 0;
  else
    return GetLastErrorAsHResult();
}

```

## disassembly

```asm
0x140009958  push    rbx
0x14000995a  sub     rsp, 20h
0x14000995e  mov     rbx, rcx
0x140009961  call    cs:__imp_GetCurrentThread
0x140009967  xor     r8d, r8d; OpenAsSelf
0x14000996a  mov     r9, rbx; TokenHandle
0x14000996d  mov     rcx, rax; ThreadHandle
0x140009970  lea     edx, [r8+0Eh]; DesiredAccess
0x140009974  call    cs:__imp_OpenThreadToken
0x14000997a  test    eax, eax
0x14000997c  jz      short loc_140009986
0x14000997e  xor     eax, eax
0x140009980  add     rsp, 20h
0x140009984  pop     rbx
0x140009985  retn
0x140009986  call    cs:__imp_GetLastError
0x14000998c  cmp     eax, 5
0x14000998f  jnz     short loc_1400099B0
0x140009991  call    cs:__imp_GetCurrentThread
0x140009997  mov     edx, 0Eh; DesiredAccess
0x14000999c  mov     r9, rbx; TokenHandle
0x14000999f  mov     rcx, rax; ThreadHandle
0x1400099a2  lea     r8d, [rdx-0Dh]; OpenAsSelf
0x1400099a6  call    cs:__imp_OpenThreadToken
0x1400099ac  test    eax, eax
0x1400099ae  jnz     short loc_14000997E
0x1400099b0  add     rsp, 20h
0x1400099b4  pop     rbx
0x1400099b5  jmp     GetLastErrorAsHResult
```
