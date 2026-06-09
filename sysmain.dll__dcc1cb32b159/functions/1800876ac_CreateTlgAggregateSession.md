# CreateTlgAggregateSession

- ea: `0x1800876ac`
- end: `0x180087769`
- name: `CreateTlgAggregateSession`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180087ed0`

## callees

- `0x1800876ac`
- `0x180087770`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800876f4`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800876f4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800876da`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800876da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800876c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800876c6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180087716`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180087716`

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
    if ( !a1 || !dword_1800D33F0 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
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
0x1800876ac  mov     [rsp+arg_0], rbx
0x1800876b1  mov     [rsp+arg_18], rsi
0x1800876b6  push    rdi
0x1800876b7  sub     rsp, 20h
0x1800876bb  mov     sil, cl
0x1800876be  xor     dil, dil
0x1800876c1  mov     [rsp+28h+arg_8], dil
0x1800876c6  call    cs:__imp_GetProcessHeap
0x1800876cc  mov     rcx, rax; hHeap
0x1800876cf  mov     edx, 8; dwFlags
0x1800876d4  mov     r8d, 168h; dwBytes
0x1800876da  call    cs:__imp_HeapAlloc
0x1800876e0  mov     rbx, rax
0x1800876e3  mov     [rsp+28h+arg_10], rax
0x1800876e8  test    rax, rax
0x1800876eb  jz      short loc_180087747
0x1800876ed  lea     rcx, [rax+108h]; SRWLock
0x1800876f4  call    cs:__imp_InitializeSRWLock
0x1800876fa  test    sil, sil
0x1800876fd  jz      short loc_180087744
0x1800876ff  mov     ecx, cs:dword_1800D33F0
0x180087705  test    ecx, ecx
0x180087707  jnz     short loc_180087747
0x180087709  xor     r8d, r8d; pcbe
0x18008770c  mov     rdx, rbx; pv
0x18008770f  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x180087716  call    cs:__imp_CreateThreadpoolTimer
0x18008771c  mov     [rbx+158h], rax
0x180087723  jmp     short loc_18008773A
0x180087725  mov     eax, 1
0x18008772a  xchg    eax, cs:dword_1800D33F0
0x180087730  mov     dil, [rsp+28h+arg_8]
0x180087735  mov     rbx, [rsp+28h+arg_10]
0x18008773a  cmp     qword ptr [rbx+158h], 0
0x180087742  jz      short loc_180087747
0x180087744  mov     dil, 1
0x180087747  test    dil, dil
0x18008774a  jnz     short loc_180087756
0x18008774c  mov     rcx, rbx; lpMem
0x18008774f  call    DestroyAggregateSession
0x180087754  xor     ebx, ebx
0x180087756  mov     rax, rbx
0x180087759  mov     rbx, [rsp+28h+arg_0]
0x18008775e  mov     rsi, [rsp+28h+arg_18]
0x180087763  add     rsp, 20h
0x180087767  pop     rdi
0x180087768  retn
0x1800b69b8  push    rbp
0x1800b69ba  sub     rsp, 20h
0x1800b69be  mov     rbp, rdx
0x1800b69c1  mov     rax, [rcx]
0x1800b69c4  xor     ecx, ecx
0x1800b69c6  cmp     dword ptr [rax], 0C000000Dh
0x1800b69cc  setz    cl
0x1800b69cf  mov     eax, ecx
0x1800b69d1  add     rsp, 20h
0x1800b69d5  pop     rbp
0x1800b69d6  retn
```
