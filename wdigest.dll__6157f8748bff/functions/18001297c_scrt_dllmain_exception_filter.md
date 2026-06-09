# __scrt_dllmain_exception_filter

- ea: `0x18001297c`
- end: `0x1800129c4`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800126f4`

## callees

- `0x18001297c`
- `0x180013120`
- `0x1800132c8`
- `0x180038010`

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
0x18001297c  push    rbx
0x18001297e  push    rbp
0x18001297f  push    rsi
0x180012980  push    rdi
0x180012981  sub     rsp, 28h
0x180012985  mov     rdi, r9
0x180012988  mov     rsi, r8
0x18001298b  mov     ebx, edx
0x18001298d  mov     rbp, rcx
0x180012990  call    __scrt_is_ucrt_dll_in_use
0x180012995  test    eax, eax
0x180012997  jnz     short loc_1800129AE
0x180012999  cmp     ebx, 1
0x18001299c  jnz     short loc_1800129AE
0x18001299e  mov     r8, rsi
0x1800129a1  xor     edx, edx
0x1800129a3  mov     rcx, rbp
0x1800129a6  mov     rax, rdi
0x1800129a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800129ae  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x1800129b3  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x1800129b7  add     rsp, 28h
0x1800129bb  pop     rdi
0x1800129bc  pop     rsi
0x1800129bd  pop     rbp
0x1800129be  pop     rbx
0x1800129bf  jmp     _o__seh_filter_dll_0
```
