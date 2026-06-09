# VmbChannelSetIncomingPollOnCompletion

- ea: `0x140010110`
- end: `0x14001011c`
- name: `VmbChannelSetIncomingPollOnCompletion`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
bool __fastcall VmbChannelSetIncomingPollOnCompletion(__int64 a1, char a2)
{
  bool result; // al

  result = a2 != 0;
  *(_BYTE *)(a1 + 1200) = a2 != 0;
  return result;
}

```

## disassembly

```asm
0x140010110  test    dl, dl
0x140010112  setnz   al
0x140010115  mov     [rcx+4B0h], al
0x14001011b  retn
```
