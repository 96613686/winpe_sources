# NetprPathCanonicalize

- ea: `0x180021000`
- end: `0x180021038`
- name: `NetprPathCanonicalize`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `reparse_path`

## import_xrefs

- `netutils!NetpwPathCanonicalize` at `0x18002102c`
- `netutils!NetpwPathCanonicalize` at `0x18002102c`

## pseudocode

```c
__int64 __fastcall NetprPathCanonicalize(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        __int64 a6,
        int a7)
{
  return NetpwPathCanonicalize(a2, a3, a4, a5, a6, a7);
}

```

## disassembly

```asm
0x180021000  push    rbx
0x180021002  sub     rsp, 30h
0x180021006  mov     eax, [rsp+38h+arg_30]
0x18002100a  mov     r10d, r9d
0x18002100d  mov     r9, [rsp+38h+arg_20]
0x180021012  mov     r11, r8
0x180021015  mov     [rsp+38h+var_10], eax
0x180021019  mov     rcx, rdx
0x18002101c  mov     rax, [rsp+38h+arg_28]
0x180021021  mov     r8d, r10d
0x180021024  mov     rdx, r11
0x180021027  mov     [rsp+38h+var_18], rax
0x18002102c  call    cs:__imp_NetpwPathCanonicalize
0x180021032  add     rsp, 30h
0x180021036  pop     rbx
0x180021037  retn
```
