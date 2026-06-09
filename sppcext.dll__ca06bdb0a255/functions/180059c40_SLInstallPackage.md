# SLInstallPackage

- ea: `0x180059c40`
- end: `0x180059c70`
- name: `SLInstallPackage`
- size: `48`
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
__int64 __fastcall SLInstallPackage(
        void *a1,
        int a2,
        unsigned int a3,
        __int64 a4,
        __int64 (__fastcall *a5)(_QWORD, _QWORD, __int64, int *),
        __int64 a6)
{
  return sub_18005835C(a1, a2, 1, a3, a4, a5, a6);
}

```

## disassembly

```asm
0x180059c40  sub     rsp, 48h
0x180059c44  mov     rax, [rsp+48h+arg_28]
0x180059c49  mov     [rsp+48h+var_18], rax
0x180059c4e  mov     rax, [rsp+48h+arg_20]
0x180059c53  mov     [rsp+48h+var_20], rax
0x180059c58  mov     [rsp+48h+var_28], r9
0x180059c5d  mov     r9d, r8d
0x180059c60  mov     r8d, 1
0x180059c66  call    sub_18005835C
0x180059c6b  add     rsp, 48h
0x180059c6f  retn
```
