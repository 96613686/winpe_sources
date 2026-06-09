# __scrt_dllmain_exception_filter

- ea: `0x180001fc4`
- end: `0x18000200c`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001c34`

## callees

- `0x180001fc4`
- `0x180002598`
- `0x18000263c`
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
0x180001fc4  push    rbx
0x180001fc6  push    rbp
0x180001fc7  push    rsi
0x180001fc8  push    rdi
0x180001fc9  sub     rsp, 28h
0x180001fcd  mov     rdi, r9
0x180001fd0  mov     rsi, r8
0x180001fd3  mov     ebx, edx
0x180001fd5  mov     rbp, rcx
0x180001fd8  call    __scrt_is_ucrt_dll_in_use
0x180001fdd  test    eax, eax
0x180001fdf  jnz     short loc_180001FF6
0x180001fe1  cmp     ebx, 1
0x180001fe4  jnz     short loc_180001FF6
0x180001fe6  mov     r8, rsi
0x180001fe9  xor     edx, edx
0x180001feb  mov     rcx, rbp
0x180001fee  mov     rax, rdi
0x180001ff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ff6  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001ffb  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180001fff  add     rsp, 28h
0x180002003  pop     rdi
0x180002004  pop     rsi
0x180002005  pop     rbp
0x180002006  pop     rbx
0x180002007  jmp     _o__seh_filter_dll_0
```
