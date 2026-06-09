# __scrt_dllmain_exception_filter

- ea: `0x180001fd0`
- end: `0x180002018`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001ca4`

## callees

- `0x180001fd0`
- `0x18000276c`
- `0x180002878`
- `0x18001b010`

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
0x180001fd0  push    rbx
0x180001fd2  push    rbp
0x180001fd3  push    rsi
0x180001fd4  push    rdi
0x180001fd5  sub     rsp, 28h
0x180001fd9  mov     rdi, r9
0x180001fdc  mov     rsi, r8
0x180001fdf  mov     ebx, edx
0x180001fe1  mov     rbp, rcx
0x180001fe4  call    __scrt_is_ucrt_dll_in_use
0x180001fe9  test    eax, eax
0x180001feb  jnz     short loc_180002002
0x180001fed  cmp     ebx, 1
0x180001ff0  jnz     short loc_180002002
0x180001ff2  mov     r8, rsi
0x180001ff5  xor     edx, edx
0x180001ff7  mov     rcx, rbp
0x180001ffa  mov     rax, rdi
0x180001ffd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002002  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180002007  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x18000200b  add     rsp, 28h
0x18000200f  pop     rdi
0x180002010  pop     rsi
0x180002011  pop     rbp
0x180002012  pop     rbx
0x180002013  jmp     _o__seh_filter_dll_0
```
