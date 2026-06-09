# SLUninstallPackage

- ea: `0x180059c80`
- end: `0x180059cad`
- name: `SLUninstallPackage`
- size: `45`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180016498`

## callees

- `0x18005835c`

## pseudocode

```c
__int64 __fastcall SLUninstallPackage(
        void *a1,
        unsigned int a2,
        __int64 a3,
        __int64 (__fastcall *a4)(_QWORD, _QWORD, __int64, int *),
        __int64 a5)
{
  return sub_18005835C(a1, 0xFFFF, 0, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x180059c80  sub     rsp, 48h
0x180059c84  mov     rax, [rsp+48h+arg_20]
0x180059c89  mov     [rsp+48h+var_18], rax
0x180059c8e  mov     [rsp+48h+var_20], r9
0x180059c93  mov     r9d, edx
0x180059c96  mov     [rsp+48h+var_28], r8
0x180059c9b  mov     edx, 0FFFFh
0x180059ca0  xor     r8d, r8d
0x180059ca3  call    sub_18005835C
0x180059ca8  add     rsp, 48h
0x180059cac  retn
```
