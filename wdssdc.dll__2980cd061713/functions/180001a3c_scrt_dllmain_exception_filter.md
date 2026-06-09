# __scrt_dllmain_exception_filter

- ea: `0x180001a3c`
- end: `0x180001a9b`
- name: `__scrt_dllmain_exception_filter`
- size: `95`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000141c`

## callees

- `0x180001a3c`
- `0x1800024f0`
- `0x180002628`
- `0x18000d010`

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
0x180001a3c  mov     [rsp+arg_0], rbx
0x180001a41  mov     [rsp+arg_8], rbp
0x180001a46  mov     [rsp+arg_10], rsi
0x180001a4b  push    rdi
0x180001a4c  sub     rsp, 20h
0x180001a50  mov     rdi, r9
0x180001a53  mov     rsi, r8
0x180001a56  mov     ebx, edx
0x180001a58  mov     rbp, rcx
0x180001a5b  call    __scrt_is_ucrt_dll_in_use
0x180001a60  test    eax, eax
0x180001a62  jnz     short loc_180001A79
0x180001a64  cmp     ebx, 1
0x180001a67  jnz     short loc_180001A79
0x180001a69  mov     r8, rsi
0x180001a6c  xor     edx, edx
0x180001a6e  mov     rcx, rbp
0x180001a71  mov     rax, rdi
0x180001a74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a79  mov     rdx, [rsp+28h+ExceptionPtr]; ExceptionPtr
0x180001a7e  mov     ecx, [rsp+28h+ExceptionNum]; ExceptionNum
0x180001a82  mov     rbx, [rsp+28h+arg_0]
0x180001a87  mov     rbp, [rsp+28h+arg_8]
0x180001a8c  mov     rsi, [rsp+28h+arg_10]
0x180001a91  add     rsp, 20h
0x180001a95  pop     rdi
0x180001a96  jmp     _o__seh_filter_dll_0
```
