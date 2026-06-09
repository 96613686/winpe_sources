# INI_STORE::MoveResource(IPubResource *,IPubResource *,IPubTransactionContext * *)

- ea: `0x1800024c0`
- end: `0x1800024d6`
- name: `?MoveResource@INI_STORE@@UEAAJPEAVIPubResource@@0PEAPEAVIPubTransactionContext@@@Z`
- size: `22`
- prototype: `__int64 __fastcall(INI_STORE *__hidden this, struct IPubResource *, struct IPubResource *, struct IPubTransactionContext **)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002080`

## pseudocode

```c
__int64 __fastcall INI_STORE::MoveResource(
        INI_STORE *this,
        struct IPubResource *a2,
        struct IPubResource *a3,
        struct IPubTransactionContext **a4)
{
  return INI_STORE::DoCopyOrMove(this, a2, a3, a4, 1);
}

```

## disassembly

```asm
0x1800024c0  sub     rsp, 38h
0x1800024c4  mov     [rsp+38h+var_18], 1; int
0x1800024cc  call    ?DoCopyOrMove@INI_STORE@@AEAAJPEAVIPubResource@@0PEAPEAVIPubTransactionContext@@H@Z; INI_STORE::DoCopyOrMove(IPubResource *,IPubResource *,IPubTransactionContext * *,int)
0x1800024d1  add     rsp, 38h
0x1800024d5  retn
```
