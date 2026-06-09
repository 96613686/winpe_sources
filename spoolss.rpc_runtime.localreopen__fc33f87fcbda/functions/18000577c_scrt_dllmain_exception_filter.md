# __scrt_dllmain_exception_filter

- ea: `0x18000577c`
- end: `0x1800057c4`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800054f4`

## callees

- `0x18000577c`
- `0x180005ed8`
- `0x180005ff8`
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
  if ( !_scrt_is_ucrt_dll_in_use() && a2 == 1 )
    a4(a1, 0, a3);
  return o__seh_filter_dll_0(ExceptionNum, ExceptionPtr);
}

```

## disassembly

```asm
0x18000577c  push    rbx
0x18000577e  push    rbp
0x18000577f  push    rsi
0x180005780  push    rdi
0x180005781  sub     rsp, 28h
0x180005785  mov     rdi, r9
0x180005788  mov     rsi, r8
0x18000578b  mov     ebx, edx
0x18000578d  mov     rbp, rcx
0x180005790  call    __scrt_is_ucrt_dll_in_use
0x180005795  test    eax, eax
0x180005797  jnz     short loc_1800057AE
0x180005799  cmp     ebx, 1
0x18000579c  jnz     short loc_1800057AE
0x18000579e  mov     r8, rsi
0x1800057a1  xor     edx, edx
0x1800057a3  mov     rcx, rbp
0x1800057a6  mov     rax, rdi
0x1800057a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057ae  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x1800057b3  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x1800057b7  add     rsp, 28h
0x1800057bb  pop     rdi
0x1800057bc  pop     rsi
0x1800057bd  pop     rbp
0x1800057be  pop     rbx
0x1800057bf  jmp     _o__seh_filter_dll_0
```
