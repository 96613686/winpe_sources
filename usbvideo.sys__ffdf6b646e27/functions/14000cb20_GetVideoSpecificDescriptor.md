# GetVideoSpecificDescriptor

- ea: `0x14000cb20`
- end: `0x14000cbe9`
- name: `GetVideoSpecificDescriptor`
- size: `201`
- prototype: `__int64 __fastcall(PVOID DescriptorBuffer)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000c80c`
- `0x140018a70`
- `0x140020a94`
- `0x140021bc8`
- `0x140021fb4`

## callees

- `0x14000cb20`
- `0x14000d3e8`

## import_xrefs

- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x14000cb5d`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x14000cb5d`
- `USBD!USBD_ParseDescriptors` at `0x14000cb9b`
- `USBD!USBD_ParseDescriptors` at `0x14000cb9b`

## pseudocode

```c
PUSB_COMMON_DESCRIPTOR __fastcall GetVideoSpecificDescriptor(
        struct _USB_CONFIGURATION_DESCRIPTOR *DescriptorBuffer,
        struct _USB_COMMON_DESCRIPTOR *a2,
        int a3)
{
  PUSB_COMMON_DESCRIPTOR v4; // rbx
  struct _USB_COMMON_DESCRIPTOR *v6; // rdi
  PUSB_INTERFACE_DESCRIPTOR v7; // rax
  unsigned __int64 NextVideoAltSetting; // rsi
  PUSB_COMMON_DESCRIPTOR result; // rax

  v4 = a2;
  v6 = a2;
  do
  {
    v7 = USBD_ParseConfigurationDescriptorEx(DescriptorBuffer, &v6->bLength + v6->bLength, -1, -1, 14, 2, -1);
    v6 = (struct _USB_COMMON_DESCRIPTOR *)v7;
  }
  while ( v7 && v7->bInterfaceNumber == v4[1].bLength );
  NextVideoAltSetting = GetNextVideoAltSetting(DescriptorBuffer, v4);
  while ( 1 )
  {
    result = USBD_ParseDescriptors(DescriptorBuffer, DescriptorBuffer->wTotalLength, &v4->bLength + v4->bLength, 36);
    v4 = result;
    if ( result )
    {
      if ( result->bLength < 3u )
        break;
    }
    if ( !result || NextVideoAltSetting && (unsigned __int64)result > NextVideoAltSetting || v6 && result > v6 )
      break;
    if ( result[1].bLength == a3 )
      return result;
  }
  return 0;
}

```

## disassembly

```asm
0x14000cb20  push    rbx
0x14000cb22  push    rbp
0x14000cb23  push    rsi
0x14000cb24  push    rdi
0x14000cb25  push    r14
0x14000cb27  sub     rsp, 40h
0x14000cb2b  mov     r14d, r8d
0x14000cb2e  mov     rbx, rdx
0x14000cb31  mov     rbp, rcx
0x14000cb34  mov     rdi, rdx
0x14000cb37  or      esi, 0FFFFFFFFh
0x14000cb3a  movzx   edx, byte ptr [rdi]
0x14000cb3d  mov     r9d, esi; AlternateSetting
0x14000cb40  mov     [rsp+68h+InterfaceProtocol], esi; InterfaceProtocol
0x14000cb44  add     rdx, rdi; StartPosition
0x14000cb47  mov     [rsp+68h+InterfaceSubClass], 2; InterfaceSubClass
0x14000cb4f  mov     r8d, esi; InterfaceNumber
0x14000cb52  mov     rcx, rbp; ConfigurationDescriptor
0x14000cb55  mov     [rsp+68h+InterfaceClass], 0Eh; InterfaceClass
0x14000cb5d  call    cs:__imp_USBD_ParseConfigurationDescriptorEx
0x14000cb64  nop     dword ptr [rax+rax+00h]
0x14000cb69  mov     rdi, rax
0x14000cb6c  test    rax, rax
0x14000cb6f  jz      short loc_14000CB79
0x14000cb71  mov     cl, [rbx+2]
0x14000cb74  cmp     [rax+2], cl
0x14000cb77  jz      short loc_14000CB3A
0x14000cb79  mov     rdx, rbx
0x14000cb7c  mov     rcx, rbp
0x14000cb7f  call    GetNextVideoAltSetting
0x14000cb84  mov     rsi, rax
0x14000cb87  movzx   r8d, byte ptr [rbx]
0x14000cb8b  mov     r9d, 24h ; '$'; DescriptorType
0x14000cb91  movzx   edx, word ptr [rbp+2]; TotalLength
0x14000cb95  add     r8, rbx; StartPosition
0x14000cb98  mov     rcx, rbp; DescriptorBuffer
0x14000cb9b  call    cs:__imp_USBD_ParseDescriptors
0x14000cba2  nop     dword ptr [rax+rax+00h]
0x14000cba7  mov     rbx, rax
0x14000cbaa  test    rax, rax
0x14000cbad  jz      short loc_14000CBB4
0x14000cbaf  cmp     byte ptr [rax], 3
0x14000cbb2  jb      short loc_14000CBDB
0x14000cbb4  test    rbx, rbx
0x14000cbb7  jz      short loc_14000CBDB
0x14000cbb9  test    rsi, rsi
0x14000cbbc  jz      short loc_14000CBC3
0x14000cbbe  cmp     rbx, rsi
0x14000cbc1  ja      short loc_14000CBDB
0x14000cbc3  test    rdi, rdi
0x14000cbc6  jz      short loc_14000CBCD
0x14000cbc8  cmp     rbx, rdi
0x14000cbcb  ja      short loc_14000CBDB
0x14000cbcd  movzx   eax, byte ptr [rax+2]
0x14000cbd1  cmp     eax, r14d
0x14000cbd4  jnz     short loc_14000CB87
0x14000cbd6  mov     rax, rbx
0x14000cbd9  jmp     short loc_14000CBDD
0x14000cbdb  xor     eax, eax
0x14000cbdd  add     rsp, 40h
0x14000cbe1  pop     r14
0x14000cbe3  pop     rdi
0x14000cbe4  pop     rsi
0x14000cbe5  pop     rbp
0x14000cbe6  pop     rbx
0x14000cbe7  retn
```
