# __scrt_dllmain_exception_filter

- ea: `0x180002690`
- end: `0x1800026d8`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180002274`

## callees

- `0x180002690`
- `0x180002d30`
- `0x180002e32`
- `0x180011010`

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
0x180002690  push    rbx
0x180002692  push    rbp
0x180002693  push    rsi
0x180002694  push    rdi
0x180002695  sub     rsp, 28h
0x180002699  mov     rdi, r9
0x18000269c  mov     rsi, r8
0x18000269f  mov     ebx, edx
0x1800026a1  mov     rbp, rcx
0x1800026a4  call    __scrt_is_ucrt_dll_in_use
0x1800026a9  test    eax, eax
0x1800026ab  jnz     short loc_1800026C2
0x1800026ad  cmp     ebx, 1
0x1800026b0  jnz     short loc_1800026C2
0x1800026b2  mov     r8, rsi
0x1800026b5  xor     edx, edx
0x1800026b7  mov     rcx, rbp
0x1800026ba  mov     rax, rdi
0x1800026bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026c2  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x1800026c7  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x1800026cb  add     rsp, 28h
0x1800026cf  pop     rdi
0x1800026d0  pop     rsi
0x1800026d1  pop     rbp
0x1800026d2  pop     rbx
0x1800026d3  jmp     _o__seh_filter_dll_0
```
