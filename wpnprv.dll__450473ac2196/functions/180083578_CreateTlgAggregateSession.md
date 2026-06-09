# CreateTlgAggregateSession

- ea: `0x180083578`
- end: `0x180083635`
- name: `CreateTlgAggregateSession`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180084170`

## callees

- `0x180083578`
- `0x18008363c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800835c0`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800835c0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800835a6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800835a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180083592`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180083592`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800835e2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800835e2`

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
    if ( !a1 || !dword_1800AFF98 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
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
0x180083578  mov     [rsp+arg_0], rbx
0x18008357d  mov     [rsp+arg_18], rsi
0x180083582  push    rdi
0x180083583  sub     rsp, 20h
0x180083587  mov     sil, cl
0x18008358a  xor     dil, dil
0x18008358d  mov     [rsp+28h+arg_8], dil
0x180083592  call    cs:__imp_GetProcessHeap
0x180083598  mov     rcx, rax; hHeap
0x18008359b  mov     edx, 8; dwFlags
0x1800835a0  mov     r8d, 168h; dwBytes
0x1800835a6  call    cs:__imp_HeapAlloc
0x1800835ac  mov     rbx, rax
0x1800835af  mov     [rsp+28h+arg_10], rax
0x1800835b4  test    rax, rax
0x1800835b7  jz      short loc_180083613
0x1800835b9  lea     rcx, [rax+108h]; SRWLock
0x1800835c0  call    cs:__imp_InitializeSRWLock
0x1800835c6  test    sil, sil
0x1800835c9  jz      short loc_180083610
0x1800835cb  mov     ecx, cs:dword_1800AFF98
0x1800835d1  test    ecx, ecx
0x1800835d3  jnz     short loc_180083613
0x1800835d5  xor     r8d, r8d; pcbe
0x1800835d8  mov     rdx, rbx; pv
0x1800835db  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x1800835e2  call    cs:__imp_CreateThreadpoolTimer
0x1800835e8  mov     [rbx+158h], rax
0x1800835ef  jmp     short loc_180083606
0x1800835f1  mov     eax, 1
0x1800835f6  xchg    eax, cs:dword_1800AFF98
0x1800835fc  mov     dil, [rsp+28h+arg_8]
0x180083601  mov     rbx, [rsp+28h+arg_10]
0x180083606  cmp     qword ptr [rbx+158h], 0
0x18008360e  jz      short loc_180083613
0x180083610  mov     dil, 1
0x180083613  test    dil, dil
0x180083616  jnz     short loc_180083622
0x180083618  mov     rcx, rbx; lpMem
0x18008361b  call    DestroyAggregateSession
0x180083620  xor     ebx, ebx
0x180083622  mov     rax, rbx
0x180083625  mov     rbx, [rsp+28h+arg_0]
0x18008362a  mov     rsi, [rsp+28h+arg_18]
0x18008362f  add     rsp, 20h
0x180083633  pop     rdi
0x180083634  retn
0x1800951eb  push    rbp
0x1800951ed  sub     rsp, 20h
0x1800951f1  mov     rbp, rdx
0x1800951f4  mov     rax, [rcx]
0x1800951f7  xor     ecx, ecx
0x1800951f9  cmp     dword ptr [rax], 0C000000Dh
0x1800951ff  setz    cl
0x180095202  mov     eax, ecx
0x180095204  add     rsp, 20h
0x180095208  pop     rbp
0x180095209  retn
```
