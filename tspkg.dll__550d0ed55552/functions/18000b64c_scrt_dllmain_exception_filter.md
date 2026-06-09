# __scrt_dllmain_exception_filter

- ea: `0x18000b64c`
- end: `0x18000b694`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000b3c4`

## callees

- `0x18000b64c`
- `0x18000bdd0`
- `0x18000c138`
- `0x18001d010`

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
0x18000b64c  push    rbx
0x18000b64e  push    rbp
0x18000b64f  push    rsi
0x18000b650  push    rdi
0x18000b651  sub     rsp, 28h
0x18000b655  mov     rdi, r9
0x18000b658  mov     rsi, r8
0x18000b65b  mov     ebx, edx
0x18000b65d  mov     rbp, rcx
0x18000b660  call    __scrt_is_ucrt_dll_in_use
0x18000b665  test    eax, eax
0x18000b667  jnz     short loc_18000B67E
0x18000b669  cmp     ebx, 1
0x18000b66c  jnz     short loc_18000B67E
0x18000b66e  mov     r8, rsi
0x18000b671  xor     edx, edx
0x18000b673  mov     rcx, rbp
0x18000b676  mov     rax, rdi
0x18000b679  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b67e  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x18000b683  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x18000b687  add     rsp, 28h
0x18000b68b  pop     rdi
0x18000b68c  pop     rsi
0x18000b68d  pop     rbp
0x18000b68e  pop     rbx
0x18000b68f  jmp     _o__seh_filter_dll_0
```
