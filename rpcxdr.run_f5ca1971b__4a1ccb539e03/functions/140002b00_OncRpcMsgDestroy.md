# OncRpcMsgDestroy

- ea: `0x140002b00`
- end: `0x140002b29`
- name: `OncRpcMsgDestroy`
- size: `41`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140002288`
- `0x140002f50`
- `0x140003860`
- `0x140006c30`

## callees

- `0x140002b00`
- `0x140002f20`
- `0x140004600`

## pseudocode

```c
void __fastcall OncRpcMsgDestroy(__int64 a1)
{
  if ( *(_DWORD *)(a1 + 268) || *(_QWORD *)(a1 + 248) )
    OncRpcMsgpDestroy((_QWORD *)a1);
  else
    OncRpcMsgOutgoingCallDereference((PVOID)a1);
}

```

## disassembly

```asm
0x140002b00  sub     rsp, 28h
0x140002b04  cmp     dword ptr [rcx+10Ch], 0
0x140002b0b  jnz     short loc_140002B1E
0x140002b0d  cmp     qword ptr [rcx+0F8h], 0
0x140002b15  jnz     short loc_140002B1E
0x140002b17  call    OncRpcMsgOutgoingCallDereference
0x140002b1c  jmp     short loc_140002B23
0x140002b1e  call    OncRpcMsgpDestroy
0x140002b23  add     rsp, 28h
0x140002b27  retn
```
