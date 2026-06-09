# CreateTlgAggregateSession

- ea: `0x1800429a4`
- end: `0x180042a61`
- name: `CreateTlgAggregateSession`
- size: `189`
- prototype: `RTL_SRWLOCK *__fastcall(char)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180043230`

## callees

- `0x1800429a4`
- `0x180042a68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800429ec`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800429ec`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180042a0e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180042a0e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800429be`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800429be`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800429d2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800429d2`

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
    if ( !a1 || !dword_18005C840 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
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
0x1800429a4  mov     [rsp+arg_0], rbx
0x1800429a9  mov     [rsp+arg_18], rsi
0x1800429ae  push    rdi
0x1800429af  sub     rsp, 20h
0x1800429b3  mov     sil, cl
0x1800429b6  xor     dil, dil
0x1800429b9  mov     [rsp+28h+arg_8], dil
0x1800429be  call    cs:__imp_GetProcessHeap
0x1800429c4  mov     rcx, rax; hHeap
0x1800429c7  mov     edx, 8; dwFlags
0x1800429cc  mov     r8d, 168h; dwBytes
0x1800429d2  call    cs:__imp_HeapAlloc
0x1800429d8  mov     rbx, rax
0x1800429db  mov     [rsp+28h+arg_10], rax
0x1800429e0  test    rax, rax
0x1800429e3  jz      short loc_180042A3F
0x1800429e5  lea     rcx, [rax+108h]; SRWLock
0x1800429ec  call    cs:__imp_InitializeSRWLock
0x1800429f2  test    sil, sil
0x1800429f5  jz      short loc_180042A3C
0x1800429f7  mov     ecx, cs:dword_18005C840
0x1800429fd  test    ecx, ecx
0x1800429ff  jnz     short loc_180042A3F
0x180042a01  xor     r8d, r8d; pcbe
0x180042a04  mov     rdx, rbx; pv
0x180042a07  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x180042a0e  call    cs:__imp_CreateThreadpoolTimer
0x180042a14  mov     [rbx+158h], rax
0x180042a1b  jmp     short loc_180042A32
0x180042a1d  mov     eax, 1
0x180042a22  xchg    eax, cs:dword_18005C840
0x180042a28  mov     dil, [rsp+28h+arg_8]
0x180042a2d  mov     rbx, [rsp+28h+arg_10]
0x180042a32  cmp     qword ptr [rbx+158h], 0
0x180042a3a  jz      short loc_180042A3F
0x180042a3c  mov     dil, 1
0x180042a3f  test    dil, dil
0x180042a42  jnz     short loc_180042A4E
0x180042a44  mov     rcx, rbx; lpMem
0x180042a47  call    DestroyAggregateSession
0x180042a4c  xor     ebx, ebx
0x180042a4e  mov     rax, rbx
0x180042a51  mov     rbx, [rsp+28h+arg_0]
0x180042a56  mov     rsi, [rsp+28h+arg_18]
0x180042a5b  add     rsp, 20h
0x180042a5f  pop     rdi
0x180042a60  retn
0x180043726  push    rbp
0x180043728  sub     rsp, 20h
0x18004372c  mov     rbp, rdx
0x18004372f  mov     rax, [rcx]
0x180043732  xor     ecx, ecx
0x180043734  cmp     dword ptr [rax], 0C000000Dh
0x18004373a  setz    cl
0x18004373d  mov     eax, ecx
0x18004373f  add     rsp, 20h
0x180043743  pop     rbp
0x180043744  retn
```
