# WcGetUnionContext

- ea: `0x1400016f0`
- end: `0x140001702`
- name: `WcGetUnionContext`
- size: `18`
- prototype: `__int64 __fastcall(struct _FLT_CALLBACK_DATA *, struct _FLT_INSTANCE *, struct _FILE_OBJECT *)`
- caller_count: `15`
- callee_count: `1`
- tags: ``

## callers

- `0x1400184f0`
- `0x140018970`
- `0x140018e28`
- `0x14001bcec`
- `0x14001f1c8`
- `0x140023c90`
- `0x140026260`
- `0x140026cec`
- `0x140026e30`
- `0x1400278a4`
- `0x140027f74`
- `0x140030438`
- `0x140030ac0`
- `0x140031940`
- `0x140034410`

## callees

- `0x140001710`

## pseudocode

```c
__int64 __fastcall WcGetUnionContext(struct _FLT_CALLBACK_DATA *a1, struct _FLT_INSTANCE *a2, struct _FILE_OBJECT *a3)
{
  return WcpGetUnionContext(a1, a2, a3);
}

```

## disassembly

```asm
0x1400016f0  sub     rsp, 28h
0x1400016f4  xor     r9d, r9d
0x1400016f7  call    WcpGetUnionContext
0x1400016fc  add     rsp, 28h
0x140001700  retn
```
