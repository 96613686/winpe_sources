# USBParseDescriptorWrapper

- ea: `0x14000d790`
- end: `0x14000d7b9`
- name: `USBParseDescriptorWrapper`
- size: `41`
- prototype: ``
- caller_count: `13`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000ca50`
- `0x14000d2d0`
- `0x14000d6d4`
- `0x1400151a0`
- `0x14001916c`
- `0x140019d98`
- `0x14001b2f4`
- `0x14001b468`
- `0x14001b4b8`
- `0x140021aa4`
- `0x140021c54`
- `0x140021dd8`
- `0x140021fb4`

## callees

- `0x14000d790`

## import_xrefs

- `USBD!USBD_ParseDescriptors` at `0x14000d794`
- `USBD!USBD_ParseDescriptors` at `0x14000d794`

## pseudocode

```c
PUSB_COMMON_DESCRIPTOR __fastcall USBParseDescriptorWrapper(void *a1, ULONG a2, void *a3, LONG a4, unsigned __int64 a5)
{
  PUSB_COMMON_DESCRIPTOR result; // rax

  result = USBD_ParseDescriptors(a1, a2, a3, a4);
  if ( result )
  {
    if ( result->bLength < a5 )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000d790  sub     rsp, 28h
0x14000d794  call    cs:__imp_USBD_ParseDescriptors
0x14000d79b  nop     dword ptr [rax+rax+00h]
0x14000d7a0  test    rax, rax
0x14000d7a3  jz      short loc_14000D7B3
0x14000d7a5  movzx   edx, byte ptr [rax]
0x14000d7a8  xor     ecx, ecx
0x14000d7aa  cmp     rdx, [rsp+28h+arg_20]
0x14000d7af  cmovb   rax, rcx
0x14000d7b3  add     rsp, 28h
0x14000d7b7  retn
```
