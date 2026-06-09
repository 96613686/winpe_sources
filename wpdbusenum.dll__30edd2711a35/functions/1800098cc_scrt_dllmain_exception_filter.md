# __scrt_dllmain_exception_filter

- ea: `0x1800098cc`
- end: `0x180009914`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180009644`

## callees

- `0x1800098cc`
- `0x18000a050`
- `0x18000a14a`
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
  if ( !(unsigned int)_scrt_is_ucrt_dll_in_use() && a2 == 1 )
    a4(a1, 0, a3);
  return o__seh_filter_dll_0(ExceptionNum, ExceptionPtr);
}

```

## disassembly

```asm
0x1800098cc  push    rbx
0x1800098ce  push    rbp
0x1800098cf  push    rsi
0x1800098d0  push    rdi
0x1800098d1  sub     rsp, 28h
0x1800098d5  mov     rdi, r9
0x1800098d8  mov     rsi, r8
0x1800098db  mov     ebx, edx
0x1800098dd  mov     rbp, rcx
0x1800098e0  call    __scrt_is_ucrt_dll_in_use
0x1800098e5  test    eax, eax
0x1800098e7  jnz     short loc_1800098FE
0x1800098e9  cmp     ebx, 1
0x1800098ec  jnz     short loc_1800098FE
0x1800098ee  mov     r8, rsi
0x1800098f1  xor     edx, edx
0x1800098f3  mov     rcx, rbp
0x1800098f6  mov     rax, rdi
0x1800098f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098fe  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180009903  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180009907  add     rsp, 28h
0x18000990b  pop     rdi
0x18000990c  pop     rsi
0x18000990d  pop     rbp
0x18000990e  pop     rbx
0x18000990f  jmp     _o__seh_filter_dll_0
```
