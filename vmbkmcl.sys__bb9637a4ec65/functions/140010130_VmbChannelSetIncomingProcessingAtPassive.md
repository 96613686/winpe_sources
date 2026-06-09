# VmbChannelSetIncomingProcessingAtPassive

- ea: `0x140010130`
- end: `0x140010147`
- name: `VmbChannelSetIncomingProcessingAtPassive`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140010130`

## pseudocode

```c
bool __fastcall VmbChannelSetIncomingProcessingAtPassive(__int64 a1, char a2)
{
  bool result; // al

  result = a2 != 0;
  *(_BYTE *)(a1 + 1202) = a2 != 0;
  if ( a2 )
    *(_BYTE *)(a1 + 1201) = 1;
  return result;
}

```

## disassembly

```asm
0x140010130  test    dl, dl
0x140010132  setnz   al
0x140010135  mov     [rcx+4B2h], al
0x14001013b  test    dl, dl
0x14001013d  jz      short locret_140010146
0x14001013f  mov     byte ptr [rcx+4B1h], 1
0x140010146  retn
```
