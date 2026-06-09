# __scrt_dllmain_exception_filter

- ea: `0x180001638`
- end: `0x180001680`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001374`

## callees

- `0x180001638`
- `0x180001db4`
- `0x1800020e2`
- `0x180006010`

## pseudocode

```c
int __fastcall _scrt_dllmain_exception_filter(
        __int64 a1,
        int a2,
        __int64 a3,
        void (__fastcall *a4)(__int64, _QWORD, __int64),
        unsigned int ExceptionNum,
        struct _EXCEPTION_POINTERS *ExceptionPtr)
{
  if ( !(unsigned int)_scrt_is_ucrt_dll_in_use() && a2 == 1 )
    a4(a1, 0, a3);
  return o__seh_filter_dll_0(ExceptionNum, ExceptionPtr);
}

```

## disassembly

```asm
0x180001638  push    rbx
0x18000163a  push    rbp
0x18000163b  push    rsi
0x18000163c  push    rdi
0x18000163d  sub     rsp, 28h
0x180001641  mov     rdi, r9
0x180001644  mov     rsi, r8
0x180001647  mov     ebx, edx
0x180001649  mov     rbp, rcx
0x18000164c  call    __scrt_is_ucrt_dll_in_use
0x180001651  test    eax, eax
0x180001653  jnz     short loc_18000166A
0x180001655  cmp     ebx, 1
0x180001658  jnz     short loc_18000166A
0x18000165a  mov     r8, rsi
0x18000165d  xor     edx, edx
0x18000165f  mov     rcx, rbp
0x180001662  mov     rax, rdi
0x180001665  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000166a  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x18000166f  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180001673  add     rsp, 28h
0x180001677  pop     rdi
0x180001678  pop     rsi
0x180001679  pop     rbp
0x18000167a  pop     rbx
0x18000167b  jmp     _o__seh_filter_dll_0
```
