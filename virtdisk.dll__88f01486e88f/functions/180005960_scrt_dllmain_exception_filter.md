# __scrt_dllmain_exception_filter

- ea: `0x180005960`
- end: `0x1800059a8`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800055a4`

## callees

- `0x180005960`
- `0x180005f10`
- `0x180005fbe`
- `0x18000c010`

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
0x180005960  push    rbx
0x180005962  push    rbp
0x180005963  push    rsi
0x180005964  push    rdi
0x180005965  sub     rsp, 28h
0x180005969  mov     rdi, r9
0x18000596c  mov     rsi, r8
0x18000596f  mov     ebx, edx
0x180005971  mov     rbp, rcx
0x180005974  call    __scrt_is_ucrt_dll_in_use
0x180005979  test    eax, eax
0x18000597b  jnz     short loc_180005992
0x18000597d  cmp     ebx, 1
0x180005980  jnz     short loc_180005992
0x180005982  mov     r8, rsi
0x180005985  xor     edx, edx
0x180005987  mov     rcx, rbp
0x18000598a  mov     rax, rdi
0x18000598d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005992  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180005997  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x18000599b  add     rsp, 28h
0x18000599f  pop     rdi
0x1800059a0  pop     rsi
0x1800059a1  pop     rbp
0x1800059a2  pop     rbx
0x1800059a3  jmp     _o__seh_filter_dll_0
```
