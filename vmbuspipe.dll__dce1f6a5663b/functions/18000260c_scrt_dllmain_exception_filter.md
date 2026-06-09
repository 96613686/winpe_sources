# __scrt_dllmain_exception_filter

- ea: `0x18000260c`
- end: `0x180002654`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180002354`

## callees

- `0x18000260c`
- `0x180002de8`
- `0x180003072`
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
0x18000260c  push    rbx
0x18000260e  push    rbp
0x18000260f  push    rsi
0x180002610  push    rdi
0x180002611  sub     rsp, 28h
0x180002615  mov     rdi, r9
0x180002618  mov     rsi, r8
0x18000261b  mov     ebx, edx
0x18000261d  mov     rbp, rcx
0x180002620  call    __scrt_is_ucrt_dll_in_use
0x180002625  test    eax, eax
0x180002627  jnz     short loc_18000263E
0x180002629  cmp     ebx, 1
0x18000262c  jnz     short loc_18000263E
0x18000262e  mov     r8, rsi
0x180002631  xor     edx, edx
0x180002633  mov     rcx, rbp
0x180002636  mov     rax, rdi
0x180002639  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000263e  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180002643  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180002647  add     rsp, 28h
0x18000264b  pop     rdi
0x18000264c  pop     rsi
0x18000264d  pop     rbp
0x18000264e  pop     rbx
0x18000264f  jmp     _o__seh_filter_dll_0
```
