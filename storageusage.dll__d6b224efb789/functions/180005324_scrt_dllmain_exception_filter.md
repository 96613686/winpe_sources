# __scrt_dllmain_exception_filter

- ea: `0x180005324`
- end: `0x18000536c`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180004f64`

## callees

- `0x180005324`
- `0x180005b20`
- `0x180005c28`
- `0x18002c010`

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
0x180005324  push    rbx
0x180005326  push    rbp
0x180005327  push    rsi
0x180005328  push    rdi
0x180005329  sub     rsp, 28h
0x18000532d  mov     rdi, r9
0x180005330  mov     rsi, r8
0x180005333  mov     ebx, edx
0x180005335  mov     rbp, rcx
0x180005338  call    __scrt_is_ucrt_dll_in_use
0x18000533d  test    eax, eax
0x18000533f  jnz     short loc_180005356
0x180005341  cmp     ebx, 1
0x180005344  jnz     short loc_180005356
0x180005346  mov     r8, rsi
0x180005349  xor     edx, edx
0x18000534b  mov     rcx, rbp
0x18000534e  mov     rax, rdi
0x180005351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005356  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x18000535b  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x18000535f  add     rsp, 28h
0x180005363  pop     rdi
0x180005364  pop     rsi
0x180005365  pop     rbp
0x180005366  pop     rbx
0x180005367  jmp     _o__seh_filter_dll_0
```
