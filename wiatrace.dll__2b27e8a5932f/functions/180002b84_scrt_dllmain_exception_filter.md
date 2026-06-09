# __scrt_dllmain_exception_filter

- ea: `0x180002b84`
- end: `0x180002bcc`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800027f4`

## callees

- `0x180002b84`
- `0x180003158`
- `0x1800031e2`
- `0x180004010`

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
0x180002b84  push    rbx
0x180002b86  push    rbp
0x180002b87  push    rsi
0x180002b88  push    rdi
0x180002b89  sub     rsp, 28h
0x180002b8d  mov     rdi, r9
0x180002b90  mov     rsi, r8
0x180002b93  mov     ebx, edx
0x180002b95  mov     rbp, rcx
0x180002b98  call    __scrt_is_ucrt_dll_in_use
0x180002b9d  test    eax, eax
0x180002b9f  jnz     short loc_180002BB6
0x180002ba1  cmp     ebx, 1
0x180002ba4  jnz     short loc_180002BB6
0x180002ba6  mov     r8, rsi
0x180002ba9  xor     edx, edx
0x180002bab  mov     rcx, rbp
0x180002bae  mov     rax, rdi
0x180002bb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bb6  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180002bbb  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180002bbf  add     rsp, 28h
0x180002bc3  pop     rdi
0x180002bc4  pop     rsi
0x180002bc5  pop     rbp
0x180002bc6  pop     rbx
0x180002bc7  jmp     _o__seh_filter_dll_0
```
