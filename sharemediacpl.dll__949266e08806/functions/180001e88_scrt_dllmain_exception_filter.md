# __scrt_dllmain_exception_filter

- ea: `0x180001e88`
- end: `0x180001ed0`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001bd4`

## callees

- `0x180001e88`
- `0x180002834`
- `0x1800028e2`
- `0x18001e010`

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
0x180001e88  push    rbx
0x180001e8a  push    rbp
0x180001e8b  push    rsi
0x180001e8c  push    rdi
0x180001e8d  sub     rsp, 28h
0x180001e91  mov     rdi, r9
0x180001e94  mov     rsi, r8
0x180001e97  mov     ebx, edx
0x180001e99  mov     rbp, rcx
0x180001e9c  call    __scrt_is_ucrt_dll_in_use
0x180001ea1  test    eax, eax
0x180001ea3  jnz     short loc_180001EBA
0x180001ea5  cmp     ebx, 1
0x180001ea8  jnz     short loc_180001EBA
0x180001eaa  mov     r8, rsi
0x180001ead  xor     edx, edx
0x180001eaf  mov     rcx, rbp
0x180001eb2  mov     rax, rdi
0x180001eb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001eba  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001ebf  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180001ec3  add     rsp, 28h
0x180001ec7  pop     rdi
0x180001ec8  pop     rsi
0x180001ec9  pop     rbp
0x180001eca  pop     rbx
0x180001ecb  jmp     _o__seh_filter_dll_0
```
