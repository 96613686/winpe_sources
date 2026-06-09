# __scrt_dllmain_exception_filter

- ea: `0x180006824`
- end: `0x18000686c`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180006494`

## callees

- `0x180006824`
- `0x180006df8`
- `0x180006eaa`
- `0x180018010`

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
0x180006824  push    rbx
0x180006826  push    rbp
0x180006827  push    rsi
0x180006828  push    rdi
0x180006829  sub     rsp, 28h
0x18000682d  mov     rdi, r9
0x180006830  mov     rsi, r8
0x180006833  mov     ebx, edx
0x180006835  mov     rbp, rcx
0x180006838  call    __scrt_is_ucrt_dll_in_use
0x18000683d  test    eax, eax
0x18000683f  jnz     short loc_180006856
0x180006841  cmp     ebx, 1
0x180006844  jnz     short loc_180006856
0x180006846  mov     r8, rsi
0x180006849  xor     edx, edx
0x18000684b  mov     rcx, rbp
0x18000684e  mov     rax, rdi
0x180006851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006856  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x18000685b  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x18000685f  add     rsp, 28h
0x180006863  pop     rdi
0x180006864  pop     rsi
0x180006865  pop     rbp
0x180006866  pop     rbx
0x180006867  jmp     _o__seh_filter_dll_0
```
