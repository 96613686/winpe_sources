# __scrt_dllmain_exception_filter

- ea: `0x180002264`
- end: `0x1800022ac`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001f44`

## callees

- `0x180002264`
- `0x1800029fc`
- `0x180002b08`
- `0x180017010`

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
0x180002264  push    rbx
0x180002266  push    rbp
0x180002267  push    rsi
0x180002268  push    rdi
0x180002269  sub     rsp, 28h
0x18000226d  mov     rdi, r9
0x180002270  mov     rsi, r8
0x180002273  mov     ebx, edx
0x180002275  mov     rbp, rcx
0x180002278  call    __scrt_is_ucrt_dll_in_use
0x18000227d  test    eax, eax
0x18000227f  jnz     short loc_180002296
0x180002281  cmp     ebx, 1
0x180002284  jnz     short loc_180002296
0x180002286  mov     r8, rsi
0x180002289  xor     edx, edx
0x18000228b  mov     rcx, rbp
0x18000228e  mov     rax, rdi
0x180002291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002296  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x18000229b  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x18000229f  add     rsp, 28h
0x1800022a3  pop     rdi
0x1800022a4  pop     rsi
0x1800022a5  pop     rbp
0x1800022a6  pop     rbx
0x1800022a7  jmp     _o__seh_filter_dll_0
```
