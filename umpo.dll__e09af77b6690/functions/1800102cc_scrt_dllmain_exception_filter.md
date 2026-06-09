# __scrt_dllmain_exception_filter

- ea: `0x1800102cc`
- end: `0x180010314`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000fee4`

## callees

- `0x1800102cc`
- `0x180010880`
- `0x18001093a`
- `0x180019010`

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
0x1800102cc  push    rbx
0x1800102ce  push    rbp
0x1800102cf  push    rsi
0x1800102d0  push    rdi
0x1800102d1  sub     rsp, 28h
0x1800102d5  mov     rdi, r9
0x1800102d8  mov     rsi, r8
0x1800102db  mov     ebx, edx
0x1800102dd  mov     rbp, rcx
0x1800102e0  call    __scrt_is_ucrt_dll_in_use
0x1800102e5  test    eax, eax
0x1800102e7  jnz     short loc_1800102FE
0x1800102e9  cmp     ebx, 1
0x1800102ec  jnz     short loc_1800102FE
0x1800102ee  mov     r8, rsi
0x1800102f1  xor     edx, edx
0x1800102f3  mov     rcx, rbp
0x1800102f6  mov     rax, rdi
0x1800102f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102fe  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180010303  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180010307  add     rsp, 28h
0x18001030b  pop     rdi
0x18001030c  pop     rsi
0x18001030d  pop     rbp
0x18001030e  pop     rbx
0x18001030f  jmp     _o__seh_filter_dll_0
```
