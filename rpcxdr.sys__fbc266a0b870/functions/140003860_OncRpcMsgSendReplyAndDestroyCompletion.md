# OncRpcMsgSendReplyAndDestroyCompletion

- ea: `0x140003860`
- end: `0x140003872`
- name: `OncRpcMsgSendReplyAndDestroyCompletion`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140002b00`

## pseudocode

```c
__int64 __fastcall OncRpcMsgSendReplyAndDestroyCompletion(__int64 a1, __int64 a2, __int64 a3)
{
  return OncRpcMsgDestroy(a3);
}

```

## disassembly

```asm
0x140003860  sub     rsp, 28h
0x140003864  mov     rcx, r8
0x140003867  call    OncRpcMsgDestroy
0x14000386c  add     rsp, 28h
0x140003870  retn
```
