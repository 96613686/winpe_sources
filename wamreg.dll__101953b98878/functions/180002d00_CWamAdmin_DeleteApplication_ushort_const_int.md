# CWamAdmin::DeleteApplication(ushort const *,int)

- ea: `0x180002d00`
- end: `0x180002d1d`
- name: `?DeleteApplication@CWamAdmin@@UEAAJPEBGH@Z`
- size: `29`
- prototype: `__int64 __fastcall(CWamAdmin *__hidden this, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003720`

## pseudocode

```c
__int64 __fastcall CWamAdmin::DeleteApplication(CWamAdmin *this, WamRegGlobal *a2, int a3)
{
  return CWamAdmin::PrivateDeleteApplication((CWamAdmin *)((char *)this - 16), a2, a3, 0, 1);
}

```

## disassembly

```asm
0x180002d00  sub     rsp, 38h
0x180002d04  add     rcx, 0FFFFFFFFFFFFFFF0h; this
0x180002d08  mov     [rsp+38h+var_18], 1; int
0x180002d10  xor     r9d, r9d; int
0x180002d13  call    ?PrivateDeleteApplication@CWamAdmin@@AEAAJPEBGHHH@Z; CWamAdmin::PrivateDeleteApplication(ushort const *,int,int,int)
0x180002d18  add     rsp, 38h
0x180002d1c  retn
```
