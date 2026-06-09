# GetTerminalUnitForInterface

- ea: `0x14000d0f4`
- end: `0x14000d18b`
- name: `GetTerminalUnitForInterface`
- size: `151`
- prototype: `__int64 __fastcall(PUSB_CONFIGURATION_DESCRIPTOR ConfigurationDescriptor)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000cbf0`

## callees

- `0x140004bac`
- `0x14000d0f4`
- `0x14000d194`

## import_xrefs

- `USBD!USBD_ParseDescriptors` at `0x14000d115`
- `USBD!USBD_ParseDescriptors` at `0x14000d115`

## pseudocode

```c
unsigned __int8 *__fastcall GetTerminalUnitForInterface(
        PUSB_CONFIGURATION_DESCRIPTOR ConfigurationDescriptor,
        unsigned __int8 *a2)
{
  int bLength; // ebx
  PUSB_COMMON_DESCRIPTOR v4; // rax

  bLength = -1;
  v4 = USBD_ParseDescriptors(ConfigurationDescriptor, ConfigurationDescriptor->wTotalLength, &a2[*a2], 36);
  if ( !v4 || v4->bLength < 3u )
    return GetUnit(ConfigurationDescriptor, bLength);
  if ( v4[1].bLength == 1 )
  {
    bLength = v4[4].bLength;
    return GetUnit(ConfigurationDescriptor, bLength);
  }
  if ( v4[1].bLength == 2 )
  {
    bLength = v4[3].bDescriptorType;
    return GetUnit(ConfigurationDescriptor, bLength);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_092df6b9c3fc3deff23d72b76b446421_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x14000d0f4  mov     [rsp+arg_0], rbx
0x14000d0f9  push    rdi
0x14000d0fa  sub     rsp, 20h
0x14000d0fe  movzx   r8d, byte ptr [rdx]
0x14000d102  mov     r9d, 24h ; '$'; DescriptorType
0x14000d108  add     r8, rdx; StartPosition
0x14000d10b  mov     rdi, rcx
0x14000d10e  movzx   edx, word ptr [rcx+2]; TotalLength
0x14000d112  or      ebx, 0FFFFFFFFh
0x14000d115  call    cs:__imp_USBD_ParseDescriptors
0x14000d11c  nop     dword ptr [rax+rax+00h]
0x14000d121  test    rax, rax
0x14000d124  jz      short loc_14000D175
0x14000d126  cmp     byte ptr [rax], 3
0x14000d129  jb      short loc_14000D175
0x14000d12b  movzx   edx, byte ptr [rax+2]
0x14000d12f  sub     edx, 1
0x14000d132  jz      short loc_14000D171
0x14000d134  cmp     edx, 1
0x14000d137  jz      short loc_14000D16B
0x14000d139  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d140  lea     rax, WPP_GLOBAL_Control
0x14000d147  cmp     rcx, rax
0x14000d14a  jz      short loc_14000D167
0x14000d14c  cmp     byte ptr [rcx+29h], 2
0x14000d150  jb      short loc_14000D167
0x14000d152  mov     rcx, [rcx+18h]
0x14000d156  lea     r8, WPP_092df6b9c3fc3deff23d72b76b446421_Traceguids
0x14000d15d  mov     edx, 27h ; '''
0x14000d162  call    WPP_SF_
0x14000d167  xor     eax, eax
0x14000d169  jmp     short loc_14000D17F
0x14000d16b  movzx   ebx, byte ptr [rax+7]
0x14000d16f  jmp     short loc_14000D175
0x14000d171  movzx   ebx, byte ptr [rax+8]
0x14000d175  mov     edx, ebx
0x14000d177  mov     rcx, rdi; ConfigurationDescriptor
0x14000d17a  call    GetUnit
0x14000d17f  mov     rbx, [rsp+28h+arg_0]
0x14000d184  add     rsp, 20h
0x14000d188  pop     rdi
0x14000d189  retn
```
