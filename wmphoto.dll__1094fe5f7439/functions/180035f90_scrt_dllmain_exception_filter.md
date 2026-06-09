# __scrt_dllmain_exception_filter

- ea: `0x180035f90`
- end: `0x180035fd8`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180035cc4`

## callees

- `0x180035f90`
- `0x180036a40`
- `0x180036b68`
- `0x180044010`

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
0x180035f90  push    rbx
0x180035f92  push    rbp
0x180035f93  push    rsi
0x180035f94  push    rdi
0x180035f95  sub     rsp, 28h
0x180035f99  mov     rdi, r9
0x180035f9c  mov     rsi, r8
0x180035f9f  mov     ebx, edx
0x180035fa1  mov     rbp, rcx
0x180035fa4  call    __scrt_is_ucrt_dll_in_use
0x180035fa9  test    eax, eax
0x180035fab  jnz     short loc_180035FC2
0x180035fad  cmp     ebx, 1
0x180035fb0  jnz     short loc_180035FC2
0x180035fb2  mov     r8, rsi
0x180035fb5  xor     edx, edx
0x180035fb7  mov     rcx, rbp
0x180035fba  mov     rax, rdi
0x180035fbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035fc2  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180035fc7  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180035fcb  add     rsp, 28h
0x180035fcf  pop     rdi
0x180035fd0  pop     rsi
0x180035fd1  pop     rbp
0x180035fd2  pop     rbx
0x180035fd3  jmp     _o__seh_filter_dll_0
```
