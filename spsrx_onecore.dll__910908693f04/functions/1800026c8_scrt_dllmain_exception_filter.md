# __scrt_dllmain_exception_filter

- ea: `0x1800026c8`
- end: `0x180002710`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800023e4`

## callees

- `0x1800026c8`
- `0x180002dd4`
- `0x180002ea8`
- `0x180010010`

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
0x1800026c8  push    rbx
0x1800026ca  push    rbp
0x1800026cb  push    rsi
0x1800026cc  push    rdi
0x1800026cd  sub     rsp, 28h
0x1800026d1  mov     rdi, r9
0x1800026d4  mov     rsi, r8
0x1800026d7  mov     ebx, edx
0x1800026d9  mov     rbp, rcx
0x1800026dc  call    __scrt_is_ucrt_dll_in_use
0x1800026e1  test    eax, eax
0x1800026e3  jnz     short loc_1800026FA
0x1800026e5  cmp     ebx, 1
0x1800026e8  jnz     short loc_1800026FA
0x1800026ea  mov     r8, rsi
0x1800026ed  xor     edx, edx
0x1800026ef  mov     rcx, rbp
0x1800026f2  mov     rax, rdi
0x1800026f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026fa  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x1800026ff  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180002703  add     rsp, 28h
0x180002707  pop     rdi
0x180002708  pop     rsi
0x180002709  pop     rbp
0x18000270a  pop     rbx
0x18000270b  jmp     _o__seh_filter_dll_0
```
