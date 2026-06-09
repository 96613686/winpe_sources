# __scrt_dllmain_exception_filter

- ea: `0x180004e84`
- end: `0x180004ecc`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180004af4`

## callees

- `0x180004e84`
- `0x18000544c`
- `0x1800054ee`
- `0x180008010`

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
0x180004e84  push    rbx
0x180004e86  push    rbp
0x180004e87  push    rsi
0x180004e88  push    rdi
0x180004e89  sub     rsp, 28h
0x180004e8d  mov     rdi, r9
0x180004e90  mov     rsi, r8
0x180004e93  mov     ebx, edx
0x180004e95  mov     rbp, rcx
0x180004e98  call    __scrt_is_ucrt_dll_in_use
0x180004e9d  test    eax, eax
0x180004e9f  jnz     short loc_180004EB6
0x180004ea1  cmp     ebx, 1
0x180004ea4  jnz     short loc_180004EB6
0x180004ea6  mov     r8, rsi
0x180004ea9  xor     edx, edx
0x180004eab  mov     rcx, rbp
0x180004eae  mov     rax, rdi
0x180004eb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004eb6  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180004ebb  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180004ebf  add     rsp, 28h
0x180004ec3  pop     rdi
0x180004ec4  pop     rsi
0x180004ec5  pop     rbp
0x180004ec6  pop     rbx
0x180004ec7  jmp     _o__seh_filter_dll_0
```
