# GetThreadToken(void * *)

- ea: `0x14000a724`
- end: `0x14000a7a5`
- name: `?GetThreadToken@@YAJPEAPEAX@Z`
- size: `129`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140063080`
- `0x140069d94`
- `0x140075ff4`

## callees

- `0x1400087c8`
- `0x14000a724`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a75f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a75f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14000a746`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14000a78b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14000a746`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14000a78b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14000a72d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14000a770`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14000a72d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14000a770`

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
0x14000a724  push    rbx
0x14000a726  sub     rsp, 20h
0x14000a72a  mov     rbx, rcx
0x14000a72d  call    cs:__imp_GetCurrentThread
0x14000a734  nop     dword ptr [rax+rax+00h]
0x14000a739  xor     r8d, r8d; OpenAsSelf
0x14000a73c  mov     r9, rbx; TokenHandle
0x14000a73f  mov     rcx, rax; ThreadHandle
0x14000a742  lea     edx, [r8+0Eh]; DesiredAccess
0x14000a746  call    cs:__imp_OpenThreadToken
0x14000a74d  nop     dword ptr [rax+rax+00h]
0x14000a752  test    eax, eax
0x14000a754  jz      short loc_14000A75F
0x14000a756  xor     eax, eax
0x14000a758  add     rsp, 20h
0x14000a75c  pop     rbx
0x14000a75d  retn
0x14000a75f  call    cs:__imp_GetLastError
0x14000a766  nop     dword ptr [rax+rax+00h]
0x14000a76b  cmp     eax, 5
0x14000a76e  jnz     short loc_14000A79B
0x14000a770  call    cs:__imp_GetCurrentThread
0x14000a777  nop     dword ptr [rax+rax+00h]
0x14000a77c  mov     edx, 0Eh; DesiredAccess
0x14000a781  mov     r9, rbx; TokenHandle
0x14000a784  mov     rcx, rax; ThreadHandle
0x14000a787  lea     r8d, [rdx-0Dh]; OpenAsSelf
0x14000a78b  call    cs:__imp_OpenThreadToken
0x14000a792  nop     dword ptr [rax+rax+00h]
0x14000a797  test    eax, eax
0x14000a799  jnz     short loc_14000A756
0x14000a79b  add     rsp, 20h
0x14000a79f  pop     rbx
0x14000a7a0  jmp     GetLastErrorAsHResult
```
