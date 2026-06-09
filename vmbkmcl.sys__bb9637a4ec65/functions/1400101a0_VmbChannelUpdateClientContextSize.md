# VmbChannelUpdateClientContextSize

- ea: `0x1400101a0`
- end: `0x1400101af`
- name: `VmbChannelUpdateClientContextSize`
- size: `15`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x14001c34c`

## pseudocode

```c
__int64 __fastcall VmbChannelUpdateClientContextSize(__int64 *a1, int a2)
{
  return InChangeClientContextSize(a1, a2);
}

```

## disassembly

```asm
0x1400101a0  sub     rsp, 28h
0x1400101a4  call    InChangeClientContextSize
0x1400101a9  add     rsp, 28h
0x1400101ad  retn
```
