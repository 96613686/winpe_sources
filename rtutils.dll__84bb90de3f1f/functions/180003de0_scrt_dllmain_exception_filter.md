# __scrt_dllmain_exception_filter

- ea: `0x180003de0`
- end: `0x180003e28`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180003a24`

## callees

- `0x180003de0`
- `0x180004390`
- `0x18000444a`
- `0x18000b010`

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
0x180003de0  push    rbx
0x180003de2  push    rbp
0x180003de3  push    rsi
0x180003de4  push    rdi
0x180003de5  sub     rsp, 28h
0x180003de9  mov     rdi, r9
0x180003dec  mov     rsi, r8
0x180003def  mov     ebx, edx
0x180003df1  mov     rbp, rcx
0x180003df4  call    __scrt_is_ucrt_dll_in_use
0x180003df9  test    eax, eax
0x180003dfb  jnz     short loc_180003E12
0x180003dfd  cmp     ebx, 1
0x180003e00  jnz     short loc_180003E12
0x180003e02  mov     r8, rsi
0x180003e05  xor     edx, edx
0x180003e07  mov     rcx, rbp
0x180003e0a  mov     rax, rdi
0x180003e0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e12  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180003e17  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180003e1b  add     rsp, 28h
0x180003e1f  pop     rdi
0x180003e20  pop     rsi
0x180003e21  pop     rbp
0x180003e22  pop     rbx
0x180003e23  jmp     _o__seh_filter_dll_0
```
