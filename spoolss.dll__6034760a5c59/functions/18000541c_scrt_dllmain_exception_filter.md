# __scrt_dllmain_exception_filter

- ea: `0x18000541c`
- end: `0x180005464`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180005194`

## callees

- `0x18000541c`
- `0x180005b78`
- `0x180005c88`
- `0x180016010`

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
0x18000541c  push    rbx
0x18000541e  push    rbp
0x18000541f  push    rsi
0x180005420  push    rdi
0x180005421  sub     rsp, 28h
0x180005425  mov     rdi, r9
0x180005428  mov     rsi, r8
0x18000542b  mov     ebx, edx
0x18000542d  mov     rbp, rcx
0x180005430  call    __scrt_is_ucrt_dll_in_use
0x180005435  test    eax, eax
0x180005437  jnz     short loc_18000544E
0x180005439  cmp     ebx, 1
0x18000543c  jnz     short loc_18000544E
0x18000543e  mov     r8, rsi
0x180005441  xor     edx, edx
0x180005443  mov     rcx, rbp
0x180005446  mov     rax, rdi
0x180005449  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000544e  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180005453  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180005457  add     rsp, 28h
0x18000545b  pop     rdi
0x18000545c  pop     rsi
0x18000545d  pop     rbp
0x18000545e  pop     rbx
0x18000545f  jmp     _o__seh_filter_dll_0
```
