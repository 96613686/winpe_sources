# __scrt_dllmain_exception_filter

- ea: `0x18000c450`
- end: `0x18000c498`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000c0b4`

## callees

- `0x18000c450`
- `0x18000ca78`
- `0x18000cb48`
- `0x180017010`

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
0x18000c450  push    rbx
0x18000c452  push    rbp
0x18000c453  push    rsi
0x18000c454  push    rdi
0x18000c455  sub     rsp, 28h
0x18000c459  mov     rdi, r9
0x18000c45c  mov     rsi, r8
0x18000c45f  mov     ebx, edx
0x18000c461  mov     rbp, rcx
0x18000c464  call    __scrt_is_ucrt_dll_in_use
0x18000c469  test    eax, eax
0x18000c46b  jnz     short loc_18000C482
0x18000c46d  cmp     ebx, 1
0x18000c470  jnz     short loc_18000C482
0x18000c472  mov     r8, rsi
0x18000c475  xor     edx, edx
0x18000c477  mov     rcx, rbp
0x18000c47a  mov     rax, rdi
0x18000c47d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c482  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x18000c487  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x18000c48b  add     rsp, 28h
0x18000c48f  pop     rdi
0x18000c490  pop     rsi
0x18000c491  pop     rbp
0x18000c492  pop     rbx
0x18000c493  jmp     _o__seh_filter_dll_0
```
