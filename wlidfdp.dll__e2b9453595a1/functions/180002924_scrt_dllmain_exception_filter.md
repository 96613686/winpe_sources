# __scrt_dllmain_exception_filter

- ea: `0x180002924`
- end: `0x18000296c`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180002654`

## callees

- `0x180002924`
- `0x1800030e0`
- `0x180003378`
- `0x180012010`

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
0x180002924  push    rbx
0x180002926  push    rbp
0x180002927  push    rsi
0x180002928  push    rdi
0x180002929  sub     rsp, 28h
0x18000292d  mov     rdi, r9
0x180002930  mov     rsi, r8
0x180002933  mov     ebx, edx
0x180002935  mov     rbp, rcx
0x180002938  call    __scrt_is_ucrt_dll_in_use
0x18000293d  test    eax, eax
0x18000293f  jnz     short loc_180002956
0x180002941  cmp     ebx, 1
0x180002944  jnz     short loc_180002956
0x180002946  mov     r8, rsi
0x180002949  xor     edx, edx
0x18000294b  mov     rcx, rbp
0x18000294e  mov     rax, rdi
0x180002951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002956  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x18000295b  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x18000295f  add     rsp, 28h
0x180002963  pop     rdi
0x180002964  pop     rsi
0x180002965  pop     rbp
0x180002966  pop     rbx
0x180002967  jmp     _o__seh_filter_dll_0
```
