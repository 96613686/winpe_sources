# CWamAdmin::AppDelete(ushort const *,int)

- ea: `0x1800020c0`
- end: `0x1800020d9`
- name: `?AppDelete@CWamAdmin@@UEAAJPEBGH@Z`
- size: `25`
- prototype: `int __fastcall(CWamAdmin *this, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003720`

## pseudocode

```c
int __fastcall CWamAdmin::AppDelete(CWamAdmin *this, const unsigned __int16 *a2, int a3)
{
  return CWamAdmin::PrivateDeleteApplication(this, a2, a3, 0, 1);
}

```

## disassembly

```asm
0x1800020c0  sub     rsp, 38h
0x1800020c4  xor     r9d, r9d; int
0x1800020c7  mov     [rsp+38h+var_18], 1; int
0x1800020cf  call    ?PrivateDeleteApplication@CWamAdmin@@AEAAJPEBGHHH@Z; CWamAdmin::PrivateDeleteApplication(ushort const *,int,int,int)
0x1800020d4  add     rsp, 38h
0x1800020d8  retn
```
