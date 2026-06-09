# ___scrt_dllmain_exception_filter

- ea: `0x10003e70`
- end: `0x10003ea6`
- name: `___scrt_dllmain_exception_filter`
- size: `54`
- prototype: `int __cdecl(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x10003aa8`

## callees

- `0x10003e70`
- `0x10004190`
- `0x100044c5`
- `0x1000454f`

## pseudocode

```c
int __cdecl __scrt_dllmain_exception_filter(
        int a1,
        int a2,
        int a3,
        void (__thiscall *a4)(_DWORD, int, _DWORD, int),
        unsigned int ExceptionNum,
        struct _EXCEPTION_POINTERS *ExceptionPtr)
{
  if ( !__scrt_is_ucrt_dll_in_use() && a2 == 1 )
    a4(a4, a1, 0, a3);
  return _seh_filter_dll(ExceptionNum, ExceptionPtr);
}

```

## disassembly

```asm
0x10003e70  mov     edi, edi
0x10003e72  push    ebp
0x10003e73  mov     ebp, esp
0x10003e75  call    ___scrt_is_ucrt_dll_in_use
0x10003e7a  test    eax, eax
0x10003e7c  jnz     short loc_10003E97
0x10003e7e  cmp     [ebp+arg_4], 1
0x10003e82  jnz     short loc_10003E97
0x10003e84  push    [ebp+arg_8]
0x10003e87  mov     ecx, [ebp+arg_C]
0x10003e8a  push    eax
0x10003e8b  push    [ebp+arg_0]
0x10003e8e  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10003e94  call    [ebp+arg_C]
0x10003e97  push    [ebp+ExceptionPtr]; ExceptionPtr
0x10003e9a  push    [ebp+ExceptionNum]; ExceptionNum
0x10003e9d  call    __seh_filter_dll
0x10003ea2  pop     ecx
0x10003ea3  pop     ecx
0x10003ea4  pop     ebp
0x10003ea5  retn
```
