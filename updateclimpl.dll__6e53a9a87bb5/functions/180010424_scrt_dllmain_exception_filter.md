# __scrt_dllmain_exception_filter

- ea: `0x180010424`
- end: `0x180010483`
- name: `__scrt_dllmain_exception_filter`
- size: `95`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18001093c`

## callees

- `0x180010208`
- `0x180010424`
- `0x180010f18`
- `0x1800148e0`

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
0x180010424  mov     [rsp+arg_0], rbx
0x180010429  mov     [rsp+arg_8], rbp
0x18001042e  mov     [rsp+arg_10], rsi
0x180010433  push    rdi
0x180010434  sub     rsp, 20h
0x180010438  mov     rdi, r9
0x18001043b  mov     rsi, r8
0x18001043e  mov     ebx, edx
0x180010440  mov     rbp, rcx
0x180010443  call    __scrt_is_ucrt_dll_in_use
0x180010448  test    eax, eax
0x18001044a  jnz     short loc_180010461
0x18001044c  cmp     ebx, 1
0x18001044f  jnz     short loc_180010461
0x180010451  mov     r8, rsi
0x180010454  xor     edx, edx
0x180010456  mov     rcx, rbp
0x180010459  mov     rax, rdi
0x18001045c  call    _guard_dispatch_icall
0x180010461  mov     rdx, [rsp+28h+ExceptionPtr]; ExceptionPtr
0x180010466  mov     ecx, [rsp+28h+ExceptionNum]; ExceptionNum
0x18001046a  mov     rbx, [rsp+28h+arg_0]
0x18001046f  mov     rbp, [rsp+28h+arg_8]
0x180010474  mov     rsi, [rsp+28h+arg_10]
0x180010479  add     rsp, 20h
0x18001047d  pop     rdi
0x18001047e  jmp     _o__seh_filter_dll_0
```
