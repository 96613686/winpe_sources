# PfsRecordCombineStats

- ea: `0x180086bf4`
- end: `0x180086ca4`
- name: `PfsRecordCombineStats`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180055f70`

## callees

- `0x180086bf4`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180086c37`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180086c37`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180086c7d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180086c7d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180086c0a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180086c1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180086c88`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180086c0a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180086c1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180086c88`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x180086c13`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x180086c13`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180086c26`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180086c93`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180086c26`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180086c93`

## pseudocode

```c
int __fastcall PfsRecordCombineStats(__int64 a1, unsigned int a2, unsigned int a3, int a4)
{
  HANDLE CurrentThread; // rax
  int ThreadPriority; // ebx
  HANDLE v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rcx
  int result; // eax
  HANDLE v15; // rax

  CurrentThread = GetCurrentThread();
  ThreadPriority = GetThreadPriority(CurrentThread);
  v10 = GetCurrentThread();
  SetThreadPriority(v10, 0);
  RtlAcquireSRWLockExclusive(*(_QWORD *)(a1 + 64) + 1736LL);
  v11 = *(_QWORD *)(a1 + 64);
  v12 = *(unsigned int *)(v11 + 568);
  if ( (unsigned int)v12 < 0x60 )
  {
    v13 = 3 * v12;
    *(_DWORD *)(v11 + 4 * v13 + 572) = a2 >> 8;
    *(_DWORD *)(v11 + 4 * v13 + 576) = a3 >> 8;
    *(_DWORD *)(v11 + 4 * v13 + 580) = a4;
    ++*(_DWORD *)(v11 + 568);
  }
  result = RtlReleaseSRWLockExclusive(*(_QWORD *)(a1 + 64) + 1736LL);
  if ( ThreadPriority != 32 )
  {
    v15 = GetCurrentThread();
    return SetThreadPriority(v15, ThreadPriority);
  }
  return result;
}

```

## disassembly

```asm
0x180086bf4  push    rbx
0x180086bf6  push    rbp
0x180086bf7  push    rsi
0x180086bf8  push    rdi
0x180086bf9  push    r14
0x180086bfb  sub     rsp, 20h
0x180086bff  mov     r14d, r9d
0x180086c02  mov     edi, r8d
0x180086c05  mov     esi, edx
0x180086c07  mov     rbp, rcx
0x180086c0a  call    cs:__imp_GetCurrentThread
0x180086c10  mov     rcx, rax; hThread
0x180086c13  call    cs:__imp_GetThreadPriority
0x180086c19  mov     ebx, eax
0x180086c1b  call    cs:__imp_GetCurrentThread
0x180086c21  mov     rcx, rax; hThread
0x180086c24  xor     edx, edx; nPriority
0x180086c26  call    cs:__imp_SetThreadPriority
0x180086c2c  mov     rcx, [rbp+40h]
0x180086c30  add     rcx, 6C8h
0x180086c37  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180086c3d  mov     rdx, [rbp+40h]
0x180086c41  mov     eax, [rdx+238h]
0x180086c47  cmp     eax, 60h ; '`'
0x180086c4a  jnb     short loc_180086C72
0x180086c4c  lea     rcx, [rax+rax*2]
0x180086c50  shr     esi, 8
0x180086c53  shr     edi, 8
0x180086c56  mov     [rdx+rcx*4+23Ch], esi
0x180086c5d  mov     [rdx+rcx*4+240h], edi
0x180086c64  mov     [rdx+rcx*4+244h], r14d
0x180086c6c  inc     dword ptr [rdx+238h]
0x180086c72  mov     rcx, [rbp+40h]
0x180086c76  add     rcx, 6C8h
0x180086c7d  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180086c83  cmp     ebx, 20h ; ' '
0x180086c86  jz      short loc_180086C99
0x180086c88  call    cs:__imp_GetCurrentThread
0x180086c8e  mov     rcx, rax; hThread
0x180086c91  mov     edx, ebx; nPriority
0x180086c93  call    cs:__imp_SetThreadPriority
0x180086c99  add     rsp, 20h
0x180086c9d  pop     r14
0x180086c9f  pop     rdi
0x180086ca0  pop     rsi
0x180086ca1  pop     rbp
0x180086ca2  pop     rbx
0x180086ca3  retn
```
