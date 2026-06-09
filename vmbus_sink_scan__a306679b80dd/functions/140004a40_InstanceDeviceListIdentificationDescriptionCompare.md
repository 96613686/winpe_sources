# InstanceDeviceListIdentificationDescriptionCompare

- ea: `0x140004a40`
- end: `0x140004a69`
- name: `InstanceDeviceListIdentificationDescriptionCompare`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140004a40`

## pseudocode

```c
bool __fastcall InstanceDeviceListIdentificationDescriptionCompare(__int64 a1, __int64 a2, __int64 a3)
{
  return *(_BYTE *)(a2 + 192) && *(_BYTE *)(a3 + 192) || *(_QWORD *)(a2 + 184) == *(_QWORD *)(a3 + 184);
}

```

## disassembly

```asm
0x140004a40  cmp     byte ptr [rdx+0C0h], 0
0x140004a47  jz      short loc_140004A57
0x140004a49  cmp     byte ptr [r8+0C0h], 0
0x140004a51  jz      short loc_140004A57
0x140004a53  mov     al, 1
0x140004a55  retn
0x140004a57  mov     rax, [r8+0B8h]
0x140004a5e  cmp     [rdx+0B8h], rax
0x140004a65  setz    al
0x140004a68  retn
```
