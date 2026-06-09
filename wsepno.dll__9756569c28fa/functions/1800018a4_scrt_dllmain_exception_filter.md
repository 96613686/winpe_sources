# __scrt_dllmain_exception_filter

- ea: `0x1800018a4`
- end: `0x1800018ec`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800015d4`

## callees

- `0x1800018a4`
- `0x180002068`
- `0x1800021b8`
- `0x18000f010`

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
  if ( !_scrt_is_ucrt_dll_in_use() && a2 == 1 )
    a4(a1, 0, a3);
  return o__seh_filter_dll_0(ExceptionNum, ExceptionPtr);
}

```

## disassembly

```asm
0x1800018a4  push    rbx
0x1800018a6  push    rbp
0x1800018a7  push    rsi
0x1800018a8  push    rdi
0x1800018a9  sub     rsp, 28h
0x1800018ad  mov     rdi, r9
0x1800018b0  mov     rsi, r8
0x1800018b3  mov     ebx, edx
0x1800018b5  mov     rbp, rcx
0x1800018b8  call    __scrt_is_ucrt_dll_in_use
0x1800018bd  test    eax, eax
0x1800018bf  jnz     short loc_1800018D6
0x1800018c1  cmp     ebx, 1
0x1800018c4  jnz     short loc_1800018D6
0x1800018c6  mov     r8, rsi
0x1800018c9  xor     edx, edx
0x1800018cb  mov     rcx, rbp
0x1800018ce  mov     rax, rdi
0x1800018d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800018d6  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x1800018db  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x1800018df  add     rsp, 28h
0x1800018e3  pop     rdi
0x1800018e4  pop     rsi
0x1800018e5  pop     rbp
0x1800018e6  pop     rbx
0x1800018e7  jmp     _o__seh_filter_dll_0
```
