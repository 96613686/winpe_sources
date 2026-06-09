# CreateTlgAggregateSession

- ea: `0x180009dfc`
- end: `0x180009eb9`
- name: `CreateTlgAggregateSession`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180009bf0`

## callees

- `0x180009dfc`
- `0x180009ec0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009e2a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009e2a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009e16`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009e16`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180009e44`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180009e44`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180009e66`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180009e66`

## pseudocode

```c
RTL_SRWLOCK *__fastcall CreateTlgAggregateSession(char a1)
{
  char v2; // di
  HANDLE ProcessHeap; // rax
  RTL_SRWLOCK *v4; // rax
  RTL_SRWLOCK *v5; // rbx

  v2 = 0;
  ProcessHeap = GetProcessHeap();
  v4 = (RTL_SRWLOCK *)HeapAlloc(ProcessHeap, 8u, 0x168u);
  v5 = v4;
  if ( v4 )
  {
    InitializeSRWLock(v4 + 33);
    if ( !a1 || !dword_180084EC8 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
      v2 = 1;
  }
  if ( !v2 )
  {
    DestroyAggregateSession(v5);
    return 0;
  }
  return v5;
}

```

## disassembly

```asm
0x180009dfc  mov     [rsp+arg_0], rbx
0x180009e01  mov     [rsp+arg_18], rsi
0x180009e06  push    rdi
0x180009e07  sub     rsp, 20h
0x180009e0b  mov     sil, cl
0x180009e0e  xor     dil, dil
0x180009e11  mov     [rsp+28h+arg_8], dil
0x180009e16  call    cs:__imp_GetProcessHeap
0x180009e1c  mov     rcx, rax; hHeap
0x180009e1f  mov     edx, 8; dwFlags
0x180009e24  mov     r8d, 168h; dwBytes
0x180009e2a  call    cs:__imp_HeapAlloc
0x180009e30  mov     rbx, rax
0x180009e33  mov     [rsp+28h+arg_10], rax
0x180009e38  test    rax, rax
0x180009e3b  jz      short loc_180009E97
0x180009e3d  lea     rcx, [rax+108h]; SRWLock
0x180009e44  call    cs:__imp_InitializeSRWLock
0x180009e4a  test    sil, sil
0x180009e4d  jz      short loc_180009E94
0x180009e4f  mov     ecx, cs:dword_180084EC8
0x180009e55  test    ecx, ecx
0x180009e57  jnz     short loc_180009E97
0x180009e59  xor     r8d, r8d; pcbe
0x180009e5c  mov     rdx, rbx; pv
0x180009e5f  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x180009e66  call    cs:__imp_CreateThreadpoolTimer
0x180009e6c  mov     [rbx+158h], rax
0x180009e73  jmp     short loc_180009E8A
0x180009e75  mov     eax, 1
0x180009e7a  xchg    eax, cs:dword_180084EC8
0x180009e80  mov     dil, [rsp+28h+arg_8]
0x180009e85  mov     rbx, [rsp+28h+arg_10]
0x180009e8a  cmp     qword ptr [rbx+158h], 0
0x180009e92  jz      short loc_180009E97
0x180009e94  mov     dil, 1
0x180009e97  test    dil, dil
0x180009e9a  jnz     short loc_180009EA6
0x180009e9c  mov     rcx, rbx; lpMem
0x180009e9f  call    DestroyAggregateSession
0x180009ea4  xor     ebx, ebx
0x180009ea6  mov     rax, rbx
0x180009ea9  mov     rbx, [rsp+28h+arg_0]
0x180009eae  mov     rsi, [rsp+28h+arg_18]
0x180009eb3  add     rsp, 20h
0x180009eb7  pop     rdi
0x180009eb8  retn
0x1800604d2  push    rbp
0x1800604d4  sub     rsp, 20h
0x1800604d8  mov     rbp, rdx
0x1800604db  mov     rax, [rcx]
0x1800604de  xor     ecx, ecx
0x1800604e0  cmp     dword ptr [rax], 0C000000Dh
0x1800604e6  setz    cl
0x1800604e9  mov     eax, ecx
0x1800604eb  add     rsp, 20h
0x1800604ef  pop     rbp
0x1800604f0  retn
```
