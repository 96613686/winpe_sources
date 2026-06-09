# __scrt_dllmain_exception_filter

- ea: `0x18000fd98`
- end: `0x18000fdf7`
- name: `__scrt_dllmain_exception_filter`
- size: `95`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18001032c`

## callees

- `0x18000fc28`
- `0x18000fd98`
- `0x1800108fc`
- `0x1800159b0`

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
0x18000fd98  mov     [rsp+arg_0], rbx
0x18000fd9d  mov     [rsp+arg_8], rbp
0x18000fda2  mov     [rsp+arg_10], rsi
0x18000fda7  push    rdi
0x18000fda8  sub     rsp, 20h
0x18000fdac  mov     rdi, r9
0x18000fdaf  mov     rsi, r8
0x18000fdb2  mov     ebx, edx
0x18000fdb4  mov     rbp, rcx
0x18000fdb7  call    __scrt_is_ucrt_dll_in_use
0x18000fdbc  test    eax, eax
0x18000fdbe  jnz     short loc_18000FDD5
0x18000fdc0  cmp     ebx, 1
0x18000fdc3  jnz     short loc_18000FDD5
0x18000fdc5  mov     r8, rsi
0x18000fdc8  xor     edx, edx
0x18000fdca  mov     rcx, rbp
0x18000fdcd  mov     rax, rdi
0x18000fdd0  call    _guard_dispatch_icall
0x18000fdd5  mov     rdx, [rsp+28h+ExceptionPtr]; ExceptionPtr
0x18000fdda  mov     ecx, [rsp+28h+ExceptionNum]; ExceptionNum
0x18000fdde  mov     rbx, [rsp+28h+arg_0]
0x18000fde3  mov     rbp, [rsp+28h+arg_8]
0x18000fde8  mov     rsi, [rsp+28h+arg_10]
0x18000fded  add     rsp, 20h
0x18000fdf1  pop     rdi
0x18000fdf2  jmp     _o__seh_filter_dll_0
```
