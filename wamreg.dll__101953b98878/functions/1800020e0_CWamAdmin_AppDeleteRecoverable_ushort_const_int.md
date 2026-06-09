# CWamAdmin::AppDeleteRecoverable(ushort const *,int)

- ea: `0x1800020e0`
- end: `0x1800020fc`
- name: `?AppDeleteRecoverable@CWamAdmin@@UEAAJPEBGH@Z`
- size: `28`
- prototype: `__int64 __fastcall(CWamAdmin *__hidden this, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003720`

## pseudocode

```c
__int64 __fastcall CWamAdmin::AppDeleteRecoverable(CWamAdmin *this, WamRegGlobal *a2, int a3)
{
  return CWamAdmin::PrivateDeleteApplication(this, a2, a3, 1u, 0);
}

```

## disassembly

```asm
0x1800020e0  sub     rsp, 38h
0x1800020e4  mov     r9d, 1; int
0x1800020ea  mov     [rsp+38h+var_18], 0; int
0x1800020f2  call    ?PrivateDeleteApplication@CWamAdmin@@AEAAJPEBGHHH@Z; CWamAdmin::PrivateDeleteApplication(ushort const *,int,int,int)
0x1800020f7  add     rsp, 38h
0x1800020fb  retn
```
