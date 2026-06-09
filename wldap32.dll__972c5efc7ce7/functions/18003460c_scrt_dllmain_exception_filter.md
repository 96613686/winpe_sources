# __scrt_dllmain_exception_filter

- ea: `0x18003460c`
- end: `0x180034654`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180034384`

## callees

- `0x18003460c`
- `0x180034d48`
- `0x180034e48`
- `0x18004d010`

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
0x18003460c  push    rbx
0x18003460e  push    rbp
0x18003460f  push    rsi
0x180034610  push    rdi
0x180034611  sub     rsp, 28h
0x180034615  mov     rdi, r9
0x180034618  mov     rsi, r8
0x18003461b  mov     ebx, edx
0x18003461d  mov     rbp, rcx
0x180034620  call    __scrt_is_ucrt_dll_in_use
0x180034625  test    eax, eax
0x180034627  jnz     short loc_18003463E
0x180034629  cmp     ebx, 1
0x18003462c  jnz     short loc_18003463E
0x18003462e  mov     r8, rsi
0x180034631  xor     edx, edx
0x180034633  mov     rcx, rbp
0x180034636  mov     rax, rdi
0x180034639  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003463e  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180034643  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180034647  add     rsp, 28h
0x18003464b  pop     rdi
0x18003464c  pop     rsi
0x18003464d  pop     rbp
0x18003464e  pop     rbx
0x18003464f  jmp     _o__seh_filter_dll_0
```
