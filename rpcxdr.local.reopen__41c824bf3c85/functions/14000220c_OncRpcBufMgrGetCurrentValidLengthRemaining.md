# OncRpcBufMgrGetCurrentValidLengthRemaining

- ea: `0x14000220c`
- end: `0x140002228`
- name: `OncRpcBufMgrGetCurrentValidLengthRemaining`
- size: `28`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x140002b30`
- `0x140003dbc`
- `0x140005a34`
- `0x140005ae8`
- `0x14000d104`
- `0x14000d154`
- `0x14001530c`
- `0x140015408`

## callees

- `0x14000220c`
- `0x14000225c`

## pseudocode

```c
__int64 __fastcall OncRpcBufMgrGetCurrentValidLengthRemaining(__int64 a1)
{
  __int64 v1; // rcx

  v1 = *(_QWORD *)(a1 + 40);
  if ( v1 )
    return OncRpcBufMgrGetDescriptorValidLengthRemaining(v1);
  else
    return 0;
}

```

## disassembly

```asm
0x14000220c  sub     rsp, 28h
0x140002210  mov     rcx, [rcx+28h]
0x140002214  test    rcx, rcx
0x140002217  jnz     short loc_14000221D
0x140002219  xor     eax, eax
0x14000221b  jmp     short loc_140002222
0x14000221d  call    OncRpcBufMgrGetDescriptorValidLengthRemaining
0x140002222  add     rsp, 28h
0x140002226  retn
```
