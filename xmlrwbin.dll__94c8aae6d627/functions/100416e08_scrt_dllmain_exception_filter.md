# __scrt_dllmain_exception_filter

- ea: `0x100416e08`
- end: `0x100416e68`
- name: `__scrt_dllmain_exception_filter`
- size: `96`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1004167c0`

## callees

- `0x100416e08`
- `0x10041730c`
- `0x100419fa0`
- `0x100424580`

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
0x100416e08  mov     [rsp+arg_0], rbx
0x100416e0d  mov     [rsp+arg_8], rbp
0x100416e12  mov     [rsp+arg_10], rsi
0x100416e17  push    rdi
0x100416e18  sub     rsp, 20h
0x100416e1c  mov     rdi, r9
0x100416e1f  mov     rsi, r8
0x100416e22  mov     ebx, edx
0x100416e24  mov     rbp, rcx
0x100416e27  call    __scrt_is_ucrt_dll_in_use
0x100416e2c  test    eax, eax
0x100416e2e  jnz     short loc_100416E46
0x100416e30  cmp     ebx, 1
0x100416e33  jnz     short loc_100416E46
0x100416e35  mov     r8, rsi
0x100416e38  xor     edx, edx
0x100416e3a  mov     rcx, rbp
0x100416e3d  mov     rax, rdi
0x100416e40  call    cs:__guard_dispatch_icall_fptr
0x100416e46  mov     rdx, [rsp+28h+ExceptionPtr]; ExceptionPtr
0x100416e4b  mov     ecx, [rsp+28h+ExceptionNum]; ExceptionNum
0x100416e4f  mov     rbx, [rsp+28h+arg_0]
0x100416e54  mov     rbp, [rsp+28h+arg_8]
0x100416e59  mov     rsi, [rsp+28h+arg_10]
0x100416e5e  add     rsp, 20h
0x100416e62  pop     rdi
0x100416e63  jmp     _seh_filter_dll
```
