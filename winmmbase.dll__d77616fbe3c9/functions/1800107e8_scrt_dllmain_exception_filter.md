# __scrt_dllmain_exception_filter

- ea: `0x1800107e8`
- end: `0x180010830`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180010534`

## callees

- `0x1800107e8`
- `0x180010f34`
- `0x180010fee`
- `0x180021010`

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
0x1800107e8  push    rbx
0x1800107ea  push    rbp
0x1800107eb  push    rsi
0x1800107ec  push    rdi
0x1800107ed  sub     rsp, 28h
0x1800107f1  mov     rdi, r9
0x1800107f4  mov     rsi, r8
0x1800107f7  mov     ebx, edx
0x1800107f9  mov     rbp, rcx
0x1800107fc  call    __scrt_is_ucrt_dll_in_use
0x180010801  test    eax, eax
0x180010803  jnz     short loc_18001081A
0x180010805  cmp     ebx, 1
0x180010808  jnz     short loc_18001081A
0x18001080a  mov     r8, rsi
0x18001080d  xor     edx, edx
0x18001080f  mov     rcx, rbp
0x180010812  mov     rax, rdi
0x180010815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001081a  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x18001081f  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180010823  add     rsp, 28h
0x180010827  pop     rdi
0x180010828  pop     rsi
0x180010829  pop     rbp
0x18001082a  pop     rbx
0x18001082b  jmp     _o__seh_filter_dll_0
```
