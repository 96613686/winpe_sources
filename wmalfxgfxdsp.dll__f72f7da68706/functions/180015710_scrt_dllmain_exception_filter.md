# __scrt_dllmain_exception_filter

- ea: `0x180015710`
- end: `0x180015758`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800153a4`

## callees

- `0x180015710`
- `0x180015d20`
- `0x180015de8`
- `0x180086010`

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
0x180015710  push    rbx
0x180015712  push    rbp
0x180015713  push    rsi
0x180015714  push    rdi
0x180015715  sub     rsp, 28h
0x180015719  mov     rdi, r9
0x18001571c  mov     rsi, r8
0x18001571f  mov     ebx, edx
0x180015721  mov     rbp, rcx
0x180015724  call    __scrt_is_ucrt_dll_in_use
0x180015729  test    eax, eax
0x18001572b  jnz     short loc_180015742
0x18001572d  cmp     ebx, 1
0x180015730  jnz     short loc_180015742
0x180015732  mov     r8, rsi
0x180015735  xor     edx, edx
0x180015737  mov     rcx, rbp
0x18001573a  mov     rax, rdi
0x18001573d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015742  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180015747  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x18001574b  add     rsp, 28h
0x18001574f  pop     rdi
0x180015750  pop     rsi
0x180015751  pop     rbp
0x180015752  pop     rbx
0x180015753  jmp     _o__seh_filter_dll_0
```
