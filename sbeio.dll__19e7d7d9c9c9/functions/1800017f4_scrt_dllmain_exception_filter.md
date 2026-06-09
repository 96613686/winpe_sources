# __scrt_dllmain_exception_filter

- ea: `0x1800017f4`
- end: `0x18000183c`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001464`

## callees

- `0x1800017f4`
- `0x180001e1c`
- `0x180001ef8`
- `0x18002b010`

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
0x1800017f4  push    rbx
0x1800017f6  push    rbp
0x1800017f7  push    rsi
0x1800017f8  push    rdi
0x1800017f9  sub     rsp, 28h
0x1800017fd  mov     rdi, r9
0x180001800  mov     rsi, r8
0x180001803  mov     ebx, edx
0x180001805  mov     rbp, rcx
0x180001808  call    __scrt_is_ucrt_dll_in_use
0x18000180d  test    eax, eax
0x18000180f  jnz     short loc_180001826
0x180001811  cmp     ebx, 1
0x180001814  jnz     short loc_180001826
0x180001816  mov     r8, rsi
0x180001819  xor     edx, edx
0x18000181b  mov     rcx, rbp
0x18000181e  mov     rax, rdi
0x180001821  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001826  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x18000182b  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x18000182f  add     rsp, 28h
0x180001833  pop     rdi
0x180001834  pop     rsi
0x180001835  pop     rbp
0x180001836  pop     rbx
0x180001837  jmp     _o__seh_filter_dll_0
```
