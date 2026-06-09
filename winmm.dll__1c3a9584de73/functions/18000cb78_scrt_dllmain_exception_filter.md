# __scrt_dllmain_exception_filter

- ea: `0x18000cb78`
- end: `0x18000cbc0`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000c804`

## callees

- `0x18000cb78`
- `0x18000d344`
- `0x18000d428`
- `0x18001b010`

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
0x18000cb78  push    rbx
0x18000cb7a  push    rbp
0x18000cb7b  push    rsi
0x18000cb7c  push    rdi
0x18000cb7d  sub     rsp, 28h
0x18000cb81  mov     rdi, r9
0x18000cb84  mov     rsi, r8
0x18000cb87  mov     ebx, edx
0x18000cb89  mov     rbp, rcx
0x18000cb8c  call    __scrt_is_ucrt_dll_in_use
0x18000cb91  test    eax, eax
0x18000cb93  jnz     short loc_18000CBAA
0x18000cb95  cmp     ebx, 1
0x18000cb98  jnz     short loc_18000CBAA
0x18000cb9a  mov     r8, rsi
0x18000cb9d  xor     edx, edx
0x18000cb9f  mov     rcx, rbp
0x18000cba2  mov     rax, rdi
0x18000cba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbaa  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x18000cbaf  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x18000cbb3  add     rsp, 28h
0x18000cbb7  pop     rdi
0x18000cbb8  pop     rsi
0x18000cbb9  pop     rbp
0x18000cbba  pop     rbx
0x18000cbbb  jmp     _o__seh_filter_dll_0
```
