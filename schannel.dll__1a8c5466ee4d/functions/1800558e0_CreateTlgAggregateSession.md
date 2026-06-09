# CreateTlgAggregateSession

- ea: `0x1800558e0`
- end: `0x18005599d`
- name: `CreateTlgAggregateSession`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180055730`

## callees

- `0x1800558e0`
- `0x1800559a4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005590e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005590e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800558fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800558fa`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180055928`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180055928`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18005594a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18005594a`

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
    if ( !a1 || !dword_1800AE418 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
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
0x1800558e0  mov     [rsp+arg_0], rbx
0x1800558e5  mov     [rsp+arg_18], rsi
0x1800558ea  push    rdi
0x1800558eb  sub     rsp, 20h
0x1800558ef  mov     sil, cl
0x1800558f2  xor     dil, dil
0x1800558f5  mov     [rsp+28h+arg_8], dil
0x1800558fa  call    cs:__imp_GetProcessHeap
0x180055900  mov     rcx, rax; hHeap
0x180055903  mov     edx, 8; dwFlags
0x180055908  mov     r8d, 168h; dwBytes
0x18005590e  call    cs:__imp_HeapAlloc
0x180055914  mov     rbx, rax
0x180055917  mov     [rsp+28h+arg_10], rax
0x18005591c  test    rax, rax
0x18005591f  jz      short loc_18005597B
0x180055921  lea     rcx, [rax+108h]; SRWLock
0x180055928  call    cs:__imp_InitializeSRWLock
0x18005592e  test    sil, sil
0x180055931  jz      short loc_180055978
0x180055933  mov     ecx, cs:dword_1800AE418
0x180055939  test    ecx, ecx
0x18005593b  jnz     short loc_18005597B
0x18005593d  xor     r8d, r8d; pcbe
0x180055940  mov     rdx, rbx; pv
0x180055943  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x18005594a  call    cs:__imp_CreateThreadpoolTimer
0x180055950  mov     [rbx+158h], rax
0x180055957  jmp     short loc_18005596E
0x180055959  mov     eax, 1
0x18005595e  xchg    eax, cs:dword_1800AE418
0x180055964  mov     dil, [rsp+28h+arg_8]
0x180055969  mov     rbx, [rsp+28h+arg_10]
0x18005596e  cmp     qword ptr [rbx+158h], 0
0x180055976  jz      short loc_18005597B
0x180055978  mov     dil, 1
0x18005597b  test    dil, dil
0x18005597e  jnz     short loc_18005598A
0x180055980  mov     rcx, rbx; lpMem
0x180055983  call    DestroyAggregateSession
0x180055988  xor     ebx, ebx
0x18005598a  mov     rax, rbx
0x18005598d  mov     rbx, [rsp+28h+arg_0]
0x180055992  mov     rsi, [rsp+28h+arg_18]
0x180055997  add     rsp, 20h
0x18005599b  pop     rdi
0x18005599c  retn
0x180088b42  push    rbp
0x180088b44  sub     rsp, 20h
0x180088b48  mov     rbp, rdx
0x180088b4b  mov     rax, [rcx]
0x180088b4e  xor     ecx, ecx
0x180088b50  cmp     dword ptr [rax], 0C000000Dh
0x180088b56  setz    cl
0x180088b59  mov     eax, ecx
0x180088b5b  add     rsp, 20h
0x180088b5f  pop     rbp
0x180088b60  retn
```
