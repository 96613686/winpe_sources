# MAPIUnknown::COReallocate(ulong,void *,void * *)

- ea: `0x18006b8b8`
- end: `0x18006b982`
- name: `?COReallocate@MAPIUnknown@@QEAAJKPEAXPEAPEAX@Z`
- size: `202`
- prototype: `int(MAPIUnknown *__hidden this, unsigned int, void *, void **)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180020ca0`
- `0x180022218`
- `0x180023d20`

## callees

- `0x18006b8b8`

## import_xrefs

- `KERNEL32!HeapReAlloc` at `0x18006b96a`
- `KERNEL32!HeapReAlloc` at `0x18006b96a`
- `KERNEL32!EnterCriticalSection` at `0x18006b8ec`
- `KERNEL32!EnterCriticalSection` at `0x18006b8ec`
- `KERNEL32!LeaveCriticalSection` at `0x18006b930`
- `KERNEL32!LeaveCriticalSection` at `0x18006b930`
- `KERNEL32!HeapAlloc` at `0x18006b955`
- `KERNEL32!HeapAlloc` at `0x18006b955`
- `KERNEL32!HeapCreate` at `0x18006b903`
- `KERNEL32!HeapCreate` at `0x18006b903`

## pseudocode

```c
__int64 __fastcall MAPIUnknown::COReallocate(MAPIUnknown *this, unsigned int a2, void *a3, void **a4)
{
  SIZE_T v5; // r14
  HANDLE v6; // rcx
  unsigned int v7; // ebx
  void *v10; // rax

  v5 = a2;
  v6 = (HANDLE)*((_QWORD *)this + 77);
  v7 = 0;
  if ( v6 )
  {
LABEL_10:
    if ( a3 )
      v10 = HeapReAlloc(v6, 0, a3, v5);
    else
      v10 = HeapAlloc(v6, 0, v5);
    if ( v10 )
      *a4 = v10;
    else
      return (unsigned int)-2147024882;
    return v7;
  }
  if ( fGlobalCSValid )
    EnterCriticalSection(&csUnkobjInit);
  v6 = MAPIUnknown::hClassHeap;
  if ( !MAPIUnknown::hClassHeap )
  {
    v6 = HeapCreate(0, 0, 0);
    MAPIUnknown::hClassHeap = v6;
    v7 = v6 == 0 ? 0x8007000E : 0;
  }
  if ( fGlobalCSValid )
  {
    LeaveCriticalSection(&csUnkobjInit);
    v6 = MAPIUnknown::hClassHeap;
  }
  if ( (v7 & 0x80000000) == 0 )
  {
    *((_QWORD *)this + 77) = v6;
    goto LABEL_10;
  }
  return v7;
}

```

## disassembly

```asm
0x18006b8b8  push    rbx
0x18006b8ba  push    rbp
0x18006b8bb  push    rsi
0x18006b8bc  push    rdi
0x18006b8bd  push    r14
0x18006b8bf  sub     rsp, 20h
0x18006b8c3  mov     rsi, rcx
0x18006b8c6  mov     r14d, edx
0x18006b8c9  mov     rcx, [rcx+268h]
0x18006b8d0  xor     ebx, ebx
0x18006b8d2  mov     rdi, r9
0x18006b8d5  mov     rbp, r8
0x18006b8d8  test    rcx, rcx
0x18006b8db  jnz     short loc_18006B948
0x18006b8dd  cmp     cs:fGlobalCSValid, ebx
0x18006b8e3  jz      short loc_18006B8F2
0x18006b8e5  lea     rcx, csUnkobjInit; lpCriticalSection
0x18006b8ec  call    cs:__imp_EnterCriticalSection
0x18006b8f2  mov     rcx, cs:?hClassHeap@MAPIUnknown@@0PEAXEA; flOptions
0x18006b8f9  test    rcx, rcx
0x18006b8fc  jnz     short loc_18006B920
0x18006b8fe  xor     r8d, r8d; dwMaximumSize
0x18006b901  xor     edx, edx; dwInitialSize
0x18006b903  call    cs:__imp_HeapCreate
0x18006b909  mov     rcx, rax
0x18006b90c  mov     cs:?hClassHeap@MAPIUnknown@@0PEAXEA, rax; void * MAPIUnknown::hClassHeap
0x18006b913  neg     rax
0x18006b916  sbb     ebx, ebx
0x18006b918  not     ebx
0x18006b91a  and     ebx, 8007000Eh
0x18006b920  cmp     cs:fGlobalCSValid, 0
0x18006b927  jz      short loc_18006B93D
0x18006b929  lea     rcx, csUnkobjInit; lpCriticalSection
0x18006b930  call    cs:__imp_LeaveCriticalSection
0x18006b936  mov     rcx, cs:?hClassHeap@MAPIUnknown@@0PEAXEA; hHeap
0x18006b93d  test    ebx, ebx
0x18006b93f  js      short loc_18006B975
0x18006b941  mov     [rsi+268h], rcx
0x18006b948  xor     edx, edx; dwFlags
0x18006b94a  mov     r9, r14; dwBytes
0x18006b94d  test    rbp, rbp
0x18006b950  jnz     short loc_18006B967
0x18006b952  mov     r8, r14; dwBytes
0x18006b955  call    cs:__imp_HeapAlloc
0x18006b95b  test    rax, rax
0x18006b95e  jnz     short loc_18006B972
0x18006b960  mov     ebx, 8007000Eh
0x18006b965  jmp     short loc_18006B975
0x18006b967  mov     r8, rbp; lpMem
0x18006b96a  call    cs:__imp_HeapReAlloc
0x18006b970  jmp     short loc_18006B95B
0x18006b972  mov     [rdi], rax
0x18006b975  mov     eax, ebx
0x18006b977  add     rsp, 20h
0x18006b97b  pop     r14
0x18006b97d  pop     rdi
0x18006b97e  pop     rsi
0x18006b97f  pop     rbp
0x18006b980  pop     rbx
0x18006b981  retn
```
