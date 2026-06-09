# __scrt_dllmain_exception_filter

- ea: `0x18000208c`
- end: `0x1800020d4`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001d24`

## callees

- `0x18000208c`
- `0x1800028c0`
- `0x180002a48`
- `0x180037010`

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
0x18000208c  push    rbx
0x18000208e  push    rbp
0x18000208f  push    rsi
0x180002090  push    rdi
0x180002091  sub     rsp, 28h
0x180002095  mov     rdi, r9
0x180002098  mov     rsi, r8
0x18000209b  mov     ebx, edx
0x18000209d  mov     rbp, rcx
0x1800020a0  call    __scrt_is_ucrt_dll_in_use
0x1800020a5  test    eax, eax
0x1800020a7  jnz     short loc_1800020BE
0x1800020a9  cmp     ebx, 1
0x1800020ac  jnz     short loc_1800020BE
0x1800020ae  mov     r8, rsi
0x1800020b1  xor     edx, edx
0x1800020b3  mov     rcx, rbp
0x1800020b6  mov     rax, rdi
0x1800020b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020be  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x1800020c3  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x1800020c7  add     rsp, 28h
0x1800020cb  pop     rdi
0x1800020cc  pop     rsi
0x1800020cd  pop     rbp
0x1800020ce  pop     rbx
0x1800020cf  jmp     _o__seh_filter_dll_0
```
