# __scrt_dllmain_exception_filter

- ea: `0x180036560`
- end: `0x1800365a8`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180036294`

## callees

- `0x180036560`
- `0x180037010`
- `0x180037138`
- `0x180045010`

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
0x180036560  push    rbx
0x180036562  push    rbp
0x180036563  push    rsi
0x180036564  push    rdi
0x180036565  sub     rsp, 28h
0x180036569  mov     rdi, r9
0x18003656c  mov     rsi, r8
0x18003656f  mov     ebx, edx
0x180036571  mov     rbp, rcx
0x180036574  call    __scrt_is_ucrt_dll_in_use
0x180036579  test    eax, eax
0x18003657b  jnz     short loc_180036592
0x18003657d  cmp     ebx, 1
0x180036580  jnz     short loc_180036592
0x180036582  mov     r8, rsi
0x180036585  xor     edx, edx
0x180036587  mov     rcx, rbp
0x18003658a  mov     rax, rdi
0x18003658d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036592  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180036597  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x18003659b  add     rsp, 28h
0x18003659f  pop     rdi
0x1800365a0  pop     rsi
0x1800365a1  pop     rbp
0x1800365a2  pop     rbx
0x1800365a3  jmp     _o__seh_filter_dll_0
```
