# OncRpcTimerCreate

- ea: `0x140007060`
- end: `0x14000706f`
- name: `OncRpcTimerCreate`
- size: `15`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400102b4`

## pseudocode

```c
__int64 __fastcall OncRpcTimerCreate(__int64 a1, __int64 a2, _QWORD *a3)
{
  return OncRpcWiMgrTimerCreate(a1, a2, a3);
}

```

## disassembly

```asm
0x140007060  sub     rsp, 28h
0x140007064  call    OncRpcWiMgrTimerCreate
0x140007069  add     rsp, 28h
0x14000706d  retn
```
