# CreateTlgAggregateSession

- ea: `0x18009550c`
- end: `0x1800955e2`
- name: `CreateTlgAggregateSession`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180096038`

## callees

- `0x180095270`
- `0x18009550c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180095554`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180095554`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800955c7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800955c7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009553a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009553a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180095526`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800955b9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180095526`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800955b9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180095576`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180095576`

## pseudocode

```c
RTL_SRWLOCK *__fastcall CreateTlgAggregateSession(char a1)
{
  char v2; // di
  HANDLE ProcessHeap; // rax
  RTL_SRWLOCK *v4; // rax
  RTL_SRWLOCK *v5; // rbx
  HANDLE v6; // rax

  v2 = 0;
  ProcessHeap = GetProcessHeap();
  v4 = (RTL_SRWLOCK *)HeapAlloc(ProcessHeap, 8u, 0x168u);
  v5 = v4;
  if ( v4 )
  {
    InitializeSRWLock(v4 + 33);
    if ( !a1 || !dword_1800BEDFC && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
      v2 = 1;
  }
  if ( !v2 )
  {
    if ( v5 )
    {
      CancelTimerCallbacksAndDeleteTimer((__int64)v5);
      v6 = GetProcessHeap();
      HeapFree(v6, 0, v5);
    }
    return 0;
  }
  return v5;
}

```

## disassembly

```asm
0x18009550c  mov     [rsp+arg_0], rbx
0x180095511  mov     [rsp+arg_18], rsi
0x180095516  push    rdi
0x180095517  sub     rsp, 20h
0x18009551b  mov     sil, cl
0x18009551e  xor     dil, dil
0x180095521  mov     [rsp+28h+arg_8], dil
0x180095526  call    cs:__imp_GetProcessHeap
0x18009552c  mov     rcx, rax; hHeap
0x18009552f  mov     edx, 8; dwFlags
0x180095534  mov     r8d, 168h; dwBytes
0x18009553a  call    cs:__imp_HeapAlloc
0x180095540  mov     rbx, rax
0x180095543  mov     [rsp+28h+arg_10], rax
0x180095548  test    rax, rax
0x18009554b  jz      short loc_1800955A7
0x18009554d  lea     rcx, [rax+108h]; SRWLock
0x180095554  call    cs:__imp_InitializeSRWLock
0x18009555a  test    sil, sil
0x18009555d  jz      short loc_1800955A4
0x18009555f  mov     ecx, cs:dword_1800BEDFC
0x180095565  test    ecx, ecx
0x180095567  jnz     short loc_1800955A7
0x180095569  xor     r8d, r8d; pcbe
0x18009556c  mov     rdx, rbx; pv
0x18009556f  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x180095576  call    cs:__imp_CreateThreadpoolTimer
0x18009557c  mov     [rbx+158h], rax
0x180095583  jmp     short loc_18009559A
0x180095585  mov     eax, 1
0x18009558a  xchg    eax, cs:dword_1800BEDFC
0x180095590  mov     dil, [rsp+28h+arg_8]
0x180095595  mov     rbx, [rsp+28h+arg_10]
0x18009559a  cmp     qword ptr [rbx+158h], 0
0x1800955a2  jz      short loc_1800955A7
0x1800955a4  mov     dil, 1
0x1800955a7  test    dil, dil
0x1800955aa  jnz     short loc_1800955CF
0x1800955ac  test    rbx, rbx
0x1800955af  jz      short loc_1800955CD
0x1800955b1  mov     rcx, rbx
0x1800955b4  call    CancelTimerCallbacksAndDeleteTimer
0x1800955b9  call    cs:__imp_GetProcessHeap
0x1800955bf  mov     rcx, rax; hHeap
0x1800955c2  mov     r8, rbx; lpMem
0x1800955c5  xor     edx, edx; dwFlags
0x1800955c7  call    cs:__imp_HeapFree
0x1800955cd  xor     ebx, ebx
0x1800955cf  mov     rax, rbx
0x1800955d2  mov     rbx, [rsp+28h+arg_0]
0x1800955d7  mov     rsi, [rsp+28h+arg_18]
0x1800955dc  add     rsp, 20h
0x1800955e0  pop     rdi
0x1800955e1  retn
0x18009baf9  push    rbp
0x18009bafb  sub     rsp, 20h
0x18009baff  mov     rbp, rdx
0x18009bb02  mov     rax, [rcx]
0x18009bb05  xor     ecx, ecx
0x18009bb07  cmp     dword ptr [rax], 0C000000Dh
0x18009bb0d  setz    cl
0x18009bb10  mov     eax, ecx
0x18009bb12  add     rsp, 20h
0x18009bb16  pop     rbp
0x18009bb17  retn
```
