# __scrt_dllmain_exception_filter

- ea: `0x180001644`
- end: `0x18000168c`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001384`

## callees

- `0x180001644`
- `0x180001da4`
- `0x180002062`
- `0x180007010`

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
0x180001644  push    rbx
0x180001646  push    rbp
0x180001647  push    rsi
0x180001648  push    rdi
0x180001649  sub     rsp, 28h
0x18000164d  mov     rdi, r9
0x180001650  mov     rsi, r8
0x180001653  mov     ebx, edx
0x180001655  mov     rbp, rcx
0x180001658  call    __scrt_is_ucrt_dll_in_use
0x18000165d  test    eax, eax
0x18000165f  jnz     short loc_180001676
0x180001661  cmp     ebx, 1
0x180001664  jnz     short loc_180001676
0x180001666  mov     r8, rsi
0x180001669  xor     edx, edx
0x18000166b  mov     rcx, rbp
0x18000166e  mov     rax, rdi
0x180001671  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001676  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x18000167b  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x18000167f  add     rsp, 28h
0x180001683  pop     rdi
0x180001684  pop     rsi
0x180001685  pop     rbp
0x180001686  pop     rbx
0x180001687  jmp     _o__seh_filter_dll_0
```
