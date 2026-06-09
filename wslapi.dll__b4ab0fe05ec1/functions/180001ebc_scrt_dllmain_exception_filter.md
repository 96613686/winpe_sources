# __scrt_dllmain_exception_filter

- ea: `0x180001ebc`
- end: `0x180001f04`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001c34`

## callees

- `0x180001ebc`
- `0x180002928`
- `0x180002a78`
- `0x18000d010`

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
0x180001ebc  push    rbx
0x180001ebe  push    rbp
0x180001ebf  push    rsi
0x180001ec0  push    rdi
0x180001ec1  sub     rsp, 28h
0x180001ec5  mov     rdi, r9
0x180001ec8  mov     rsi, r8
0x180001ecb  mov     ebx, edx
0x180001ecd  mov     rbp, rcx
0x180001ed0  call    __scrt_is_ucrt_dll_in_use
0x180001ed5  test    eax, eax
0x180001ed7  jnz     short loc_180001EEE
0x180001ed9  cmp     ebx, 1
0x180001edc  jnz     short loc_180001EEE
0x180001ede  mov     r8, rsi
0x180001ee1  xor     edx, edx
0x180001ee3  mov     rcx, rbp
0x180001ee6  mov     rax, rdi
0x180001ee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001eee  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001ef3  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180001ef7  add     rsp, 28h
0x180001efb  pop     rdi
0x180001efc  pop     rsi
0x180001efd  pop     rbp
0x180001efe  pop     rbx
0x180001eff  jmp     _o__seh_filter_dll_0
```
