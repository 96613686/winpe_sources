# WapEtwGenerateActivityIdFromEnvironment

- ea: `0x18001f18c`
- end: `0x18001f1f8`
- name: `WapEtwGenerateActivityIdFromEnvironment`
- size: `108`
- prototype: ``
- caller_count: `10`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x18001e138`
- `0x18001e5b8`
- `0x18001eb50`
- `0x18001ec68`
- `0x18001fac8`
- `0x18001fc90`
- `0x18005db14`
- `0x18005eaa8`
- `0x18005ebf4`
- `0x18005ed58`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f1c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f1c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001f1d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001f1d4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001f1b5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001f1b5`

## pseudocode

```c
__int64 __fastcall WapEtwGenerateActivityIdFromEnvironment(__int64 a1)
{
  unsigned __int64 v2; // rsi
  DWORD TickCount; // edi
  DWORD v4; // ebx
  DWORD CurrentProcessId; // eax
  __int64 result; // rax
  unsigned __int64 retaddr; // [rsp+48h] [rbp+0h]

  v2 = retaddr ^ ((unsigned __int64)(unsigned int)WapEtwActivityIdCount++ << 32);
  TickCount = GetTickCount();
  v4 = GetCurrentThreadId() << 16;
  CurrentProcessId = GetCurrentProcessId();
  *(_QWORD *)a1 = v2;
  result = v4 ^ CurrentProcessId;
  *(_DWORD *)(a1 + 8) = TickCount;
  *(_DWORD *)(a1 + 12) = result;
  return result;
}

```

## disassembly

```asm
0x18001f18c  push    rbx
0x18001f18e  push    rsi
0x18001f18f  push    rdi
0x18001f190  push    r14
0x18001f192  sub     rsp, 28h
0x18001f196  mov     edx, cs:WapEtwActivityIdCount
0x18001f19c  mov     r14, rcx
0x18001f19f  mov     rax, [rsp+48h]
0x18001f1a4  mov     esi, edx
0x18001f1a6  inc     edx
0x18001f1a8  shl     rsi, 20h
0x18001f1ac  xor     rsi, rax
0x18001f1af  mov     cs:WapEtwActivityIdCount, edx
0x18001f1b5  call    cs:__imp_GetTickCount
0x18001f1bc  nop     dword ptr [rax+rax+00h]
0x18001f1c1  mov     edi, eax
0x18001f1c3  call    cs:__imp_GetCurrentThreadId
0x18001f1ca  nop     dword ptr [rax+rax+00h]
0x18001f1cf  mov     ebx, eax
0x18001f1d1  shl     ebx, 10h
0x18001f1d4  call    cs:__imp_GetCurrentProcessId
0x18001f1db  nop     dword ptr [rax+rax+00h]
0x18001f1e0  mov     [r14], rsi
0x18001f1e3  xor     eax, ebx
0x18001f1e5  mov     [r14+8], edi
0x18001f1e9  mov     [r14+0Ch], eax
0x18001f1ed  add     rsp, 28h
0x18001f1f1  pop     r14
0x18001f1f3  pop     rdi
0x18001f1f4  pop     rsi
0x18001f1f5  pop     rbx
0x18001f1f6  retn
```
