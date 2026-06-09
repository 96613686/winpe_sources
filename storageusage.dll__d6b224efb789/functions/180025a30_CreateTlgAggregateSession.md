# CreateTlgAggregateSession

- ea: `0x180025a30`
- end: `0x180025aed`
- name: `CreateTlgAggregateSession`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180026620`

## callees

- `0x180025a30`
- `0x180025af4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180025a78`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180025a78`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025a4a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025a4a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180025a5e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180025a5e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180025a9a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180025a9a`

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
    if ( !a1 || !dword_180040614 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
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
0x180025a30  mov     [rsp+arg_0], rbx
0x180025a35  mov     [rsp+arg_18], rsi
0x180025a3a  push    rdi
0x180025a3b  sub     rsp, 20h
0x180025a3f  mov     sil, cl
0x180025a42  xor     dil, dil
0x180025a45  mov     [rsp+28h+arg_8], dil
0x180025a4a  call    cs:__imp_GetProcessHeap
0x180025a50  mov     rcx, rax; hHeap
0x180025a53  mov     edx, 8; dwFlags
0x180025a58  mov     r8d, 168h; dwBytes
0x180025a5e  call    cs:__imp_HeapAlloc
0x180025a64  mov     rbx, rax
0x180025a67  mov     [rsp+28h+arg_10], rax
0x180025a6c  test    rax, rax
0x180025a6f  jz      short loc_180025ACB
0x180025a71  lea     rcx, [rax+108h]; SRWLock
0x180025a78  call    cs:__imp_InitializeSRWLock
0x180025a7e  test    sil, sil
0x180025a81  jz      short loc_180025AC8
0x180025a83  mov     ecx, cs:dword_180040614
0x180025a89  test    ecx, ecx
0x180025a8b  jnz     short loc_180025ACB
0x180025a8d  xor     r8d, r8d; pcbe
0x180025a90  mov     rdx, rbx; pv
0x180025a93  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x180025a9a  call    cs:__imp_CreateThreadpoolTimer
0x180025aa0  mov     [rbx+158h], rax
0x180025aa7  jmp     short loc_180025ABE
0x180025aa9  mov     eax, 1
0x180025aae  xchg    eax, cs:dword_180040614
0x180025ab4  mov     dil, [rsp+28h+arg_8]
0x180025ab9  mov     rbx, [rsp+28h+arg_10]
0x180025abe  cmp     qword ptr [rbx+158h], 0
0x180025ac6  jz      short loc_180025ACB
0x180025ac8  mov     dil, 1
0x180025acb  test    dil, dil
0x180025ace  jnz     short loc_180025ADA
0x180025ad0  mov     rcx, rbx; lpMem
0x180025ad3  call    DestroyAggregateSession
0x180025ad8  xor     ebx, ebx
0x180025ada  mov     rax, rbx
0x180025add  mov     rbx, [rsp+28h+arg_0]
0x180025ae2  mov     rsi, [rsp+28h+arg_18]
0x180025ae7  add     rsp, 20h
0x180025aeb  pop     rdi
0x180025aec  retn
0x18002bc32  push    rbp
0x18002bc34  sub     rsp, 20h
0x18002bc38  mov     rbp, rdx
0x18002bc3b  mov     rax, [rcx]
0x18002bc3e  xor     ecx, ecx
0x18002bc40  cmp     dword ptr [rax], 0C000000Dh
0x18002bc46  setz    cl
0x18002bc49  mov     eax, ecx
0x18002bc4b  add     rsp, 20h
0x18002bc4f  pop     rbp
0x18002bc50  retn
```
