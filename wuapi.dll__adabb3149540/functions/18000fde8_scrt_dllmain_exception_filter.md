# __scrt_dllmain_exception_filter

- ea: `0x18000fde8`
- end: `0x18000fe47`
- name: `__scrt_dllmain_exception_filter`
- size: `95`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18001037c`

## callees

- `0x18000fc78`
- `0x18000fde8`
- `0x18001094c`
- `0x180015a00`

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
0x18000fde8  mov     [rsp+arg_0], rbx
0x18000fded  mov     [rsp+arg_8], rbp
0x18000fdf2  mov     [rsp+arg_10], rsi
0x18000fdf7  push    rdi
0x18000fdf8  sub     rsp, 20h
0x18000fdfc  mov     rdi, r9
0x18000fdff  mov     rsi, r8
0x18000fe02  mov     ebx, edx
0x18000fe04  mov     rbp, rcx
0x18000fe07  call    __scrt_is_ucrt_dll_in_use
0x18000fe0c  test    eax, eax
0x18000fe0e  jnz     short loc_18000FE25
0x18000fe10  cmp     ebx, 1
0x18000fe13  jnz     short loc_18000FE25
0x18000fe15  mov     r8, rsi
0x18000fe18  xor     edx, edx
0x18000fe1a  mov     rcx, rbp
0x18000fe1d  mov     rax, rdi
0x18000fe20  call    _guard_dispatch_icall
0x18000fe25  mov     rdx, [rsp+28h+ExceptionPtr]; ExceptionPtr
0x18000fe2a  mov     ecx, [rsp+28h+ExceptionNum]; ExceptionNum
0x18000fe2e  mov     rbx, [rsp+28h+arg_0]
0x18000fe33  mov     rbp, [rsp+28h+arg_8]
0x18000fe38  mov     rsi, [rsp+28h+arg_10]
0x18000fe3d  add     rsp, 20h
0x18000fe41  pop     rdi
0x18000fe42  jmp     _o__seh_filter_dll_0
```
