# INI_STORE::CopyResource(IPubResource *,IPubResource *,IPubTransactionContext * *)

- ea: `0x180001c10`
- end: `0x180001c26`
- name: `?CopyResource@INI_STORE@@UEAAJPEAVIPubResource@@0PEAPEAVIPubTransactionContext@@@Z`
- size: `22`
- prototype: `__int64 __fastcall(INI_STORE *__hidden this, struct IPubResource *, struct IPubResource *, struct IPubTransactionContext **)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002080`

## pseudocode

```c
__int64 __fastcall INI_STORE::CopyResource(
        INI_STORE *this,
        struct IPubResource *a2,
        struct IPubResource *a3,
        struct IPubTransactionContext **a4)
{
  return INI_STORE::DoCopyOrMove(this, a2, a3, a4, 0);
}

```

## disassembly

```asm
0x180001c10  sub     rsp, 38h
0x180001c14  mov     [rsp+38h+var_18], 0; int
0x180001c1c  call    ?DoCopyOrMove@INI_STORE@@AEAAJPEAVIPubResource@@0PEAPEAVIPubTransactionContext@@H@Z; INI_STORE::DoCopyOrMove(IPubResource *,IPubResource *,IPubTransactionContext * *,int)
0x180001c21  add     rsp, 38h
0x180001c25  retn
```
