# __scrt_dllmain_exception_filter

- ea: `0x18000232c`
- end: `0x180002374`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800020a4`

## callees

- `0x18000232c`
- `0x180002a8c`
- `0x180002b52`
- `0x18000a010`

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
0x18000232c  push    rbx
0x18000232e  push    rbp
0x18000232f  push    rsi
0x180002330  push    rdi
0x180002331  sub     rsp, 28h
0x180002335  mov     rdi, r9
0x180002338  mov     rsi, r8
0x18000233b  mov     ebx, edx
0x18000233d  mov     rbp, rcx
0x180002340  call    __scrt_is_ucrt_dll_in_use
0x180002345  test    eax, eax
0x180002347  jnz     short loc_18000235E
0x180002349  cmp     ebx, 1
0x18000234c  jnz     short loc_18000235E
0x18000234e  mov     r8, rsi
0x180002351  xor     edx, edx
0x180002353  mov     rcx, rbp
0x180002356  mov     rax, rdi
0x180002359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000235e  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180002363  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180002367  add     rsp, 28h
0x18000236b  pop     rdi
0x18000236c  pop     rsi
0x18000236d  pop     rbp
0x18000236e  pop     rbx
0x18000236f  jmp     _o__seh_filter_dll_0
```
