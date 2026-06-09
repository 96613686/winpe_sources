# __scrt_dllmain_exception_filter

- ea: `0x100426de8`
- end: `0x100426e48`
- name: `__scrt_dllmain_exception_filter`
- size: `96`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1004267b0`

## callees

- `0x100426de8`
- `0x1004272e0`
- `0x100429f30`
- `0x100439df0`

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
  return seh_filter_dll(ExceptionNum, ExceptionPtr);
}

```

## disassembly

```asm
0x100426de8  mov     [rsp+arg_0], rbx
0x100426ded  mov     [rsp+arg_8], rbp
0x100426df2  mov     [rsp+arg_10], rsi
0x100426df7  push    rdi
0x100426df8  sub     rsp, 20h
0x100426dfc  mov     rdi, r9
0x100426dff  mov     rsi, r8
0x100426e02  mov     ebx, edx
0x100426e04  mov     rbp, rcx
0x100426e07  call    __scrt_is_ucrt_dll_in_use
0x100426e0c  test    eax, eax
0x100426e0e  jnz     short loc_100426E26
0x100426e10  cmp     ebx, 1
0x100426e13  jnz     short loc_100426E26
0x100426e15  mov     r8, rsi
0x100426e18  xor     edx, edx
0x100426e1a  mov     rcx, rbp
0x100426e1d  mov     rax, rdi
0x100426e20  call    cs:__guard_dispatch_icall_fptr
0x100426e26  mov     rdx, [rsp+28h+ExceptionPtr]; ExceptionPtr
0x100426e2b  mov     ecx, [rsp+28h+ExceptionNum]; ExceptionNum
0x100426e2f  mov     rbx, [rsp+28h+arg_0]
0x100426e34  mov     rbp, [rsp+28h+arg_8]
0x100426e39  mov     rsi, [rsp+28h+arg_10]
0x100426e3e  add     rsp, 20h
0x100426e42  pop     rdi
0x100426e43  jmp     _seh_filter_dll
```
