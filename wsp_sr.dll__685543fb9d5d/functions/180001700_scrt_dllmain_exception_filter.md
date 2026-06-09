# __scrt_dllmain_exception_filter

- ea: `0x180001700`
- end: `0x180001748`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001354`

## callees

- `0x180001700`
- `0x180001d10`
- `0x180001e08`
- `0x18002d010`

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
0x180001700  push    rbx
0x180001702  push    rbp
0x180001703  push    rsi
0x180001704  push    rdi
0x180001705  sub     rsp, 28h
0x180001709  mov     rdi, r9
0x18000170c  mov     rsi, r8
0x18000170f  mov     ebx, edx
0x180001711  mov     rbp, rcx
0x180001714  call    __scrt_is_ucrt_dll_in_use
0x180001719  test    eax, eax
0x18000171b  jnz     short loc_180001732
0x18000171d  cmp     ebx, 1
0x180001720  jnz     short loc_180001732
0x180001722  mov     r8, rsi
0x180001725  xor     edx, edx
0x180001727  mov     rcx, rbp
0x18000172a  mov     rax, rdi
0x18000172d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001732  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001737  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x18000173b  add     rsp, 28h
0x18000173f  pop     rdi
0x180001740  pop     rsi
0x180001741  pop     rbp
0x180001742  pop     rbx
0x180001743  jmp     _o__seh_filter_dll_0
```
