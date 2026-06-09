# GetUnitControlInterface

- ea: `0x140018a70`
- end: `0x140018b10`
- name: `GetUnitControlInterface`
- size: `160`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400125c0`
- `0x1400228a0`
- `0x1400229b0`
- `0x140022ac0`
- `0x140022cd0`
- `0x140022e40`

## callees

- `0x14000cb20`
- `0x140018a70`

## import_xrefs

- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x140018aed`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x140018aed`

## pseudocode

```c
char __fastcall GetUnitControlInterface(__int64 a1, char a2)
{
  struct _USB_CONFIGURATION_DESCRIPTOR *v2; // rbp
  struct _USB_CONFIGURATION_DESCRIPTOR *v4; // rdx
  char bLength; // di
  PUSB_COMMON_DESCRIPTOR VideoSpecificDescriptor; // rax
  UCHAR *i; // rcx
  struct _USB_COMMON_DESCRIPTOR *v8; // rax
  struct _USB_COMMON_DESCRIPTOR *v9; // rbx

  v2 = *(struct _USB_CONFIGURATION_DESCRIPTOR **)(a1 + 32);
  v4 = v2;
  bLength = -1;
  while ( 1 )
  {
    v8 = (struct _USB_COMMON_DESCRIPTOR *)USBD_ParseConfigurationDescriptorEx(v2, v4, -1, -1, 14, 1, -1);
    v9 = v8;
    if ( !v8 )
      break;
    bLength = v8[1].bLength;
    VideoSpecificDescriptor = GetVideoSpecificDescriptor(v2, v8, 1);
    for ( i = &VideoSpecificDescriptor->bLength + VideoSpecificDescriptor->bLength;
          i < &VideoSpecificDescriptor->bLength + *(unsigned __int16 *)&VideoSpecificDescriptor[2].bDescriptorType;
          i += *i )
    {
      if ( i[3] == a2 )
        return bLength;
    }
    if ( i[3] == a2 )
      break;
    v4 = (struct _USB_CONFIGURATION_DESCRIPTOR *)(&v9->bLength + v9->bLength);
  }
  return bLength;
}

```

## disassembly

```asm
0x140018a70  push    rbx
0x140018a72  push    rbp
0x140018a73  push    rsi
0x140018a74  push    rdi
0x140018a75  push    r14
0x140018a77  sub     rsp, 40h
0x140018a7b  mov     rbp, [rcx+20h]
0x140018a7f  mov     sil, dl
0x140018a82  mov     rdx, rbp
0x140018a85  mov     dil, 0FFh
0x140018a88  or      r14d, 0FFFFFFFFh
0x140018a8c  jmp     short loc_140018ACF
0x140018a8e  mov     dil, [rbx+2]
0x140018a92  mov     r8d, 1
0x140018a98  mov     rdx, rbx
0x140018a9b  mov     rcx, rbp; DescriptorBuffer
0x140018a9e  call    GetVideoSpecificDescriptor
0x140018aa3  movzx   ecx, byte ptr [rax]
0x140018aa6  movzx   edx, word ptr [rax+5]
0x140018aaa  add     rcx, rax
0x140018aad  add     rdx, rax
0x140018ab0  jmp     short loc_140018ABE
0x140018ab2  cmp     [rcx+3], sil
0x140018ab6  jz      short loc_140018B01
0x140018ab8  movzx   eax, byte ptr [rcx]
0x140018abb  add     rcx, rax
0x140018abe  cmp     rcx, rdx
0x140018ac1  jb      short loc_140018AB2
0x140018ac3  cmp     [rcx+3], sil
0x140018ac7  jz      short loc_140018B01
0x140018ac9  movzx   edx, byte ptr [rbx]
0x140018acc  add     rdx, rbx; StartPosition
0x140018acf  mov     [rsp+68h+InterfaceProtocol], r14d; InterfaceProtocol
0x140018ad4  mov     r9d, r14d; AlternateSetting
0x140018ad7  mov     [rsp+68h+InterfaceSubClass], 1; InterfaceSubClass
0x140018adf  mov     r8d, r14d; InterfaceNumber
0x140018ae2  mov     rcx, rbp; ConfigurationDescriptor
0x140018ae5  mov     [rsp+68h+InterfaceClass], 0Eh; InterfaceClass
0x140018aed  call    cs:__imp_USBD_ParseConfigurationDescriptorEx
0x140018af4  nop     dword ptr [rax+rax+00h]
0x140018af9  mov     rbx, rax
0x140018afc  test    rax, rax
0x140018aff  jnz     short loc_140018A8E
0x140018b01  mov     al, dil
0x140018b04  add     rsp, 40h
0x140018b08  pop     r14
0x140018b0a  pop     rdi
0x140018b0b  pop     rsi
0x140018b0c  pop     rbp
0x140018b0d  pop     rbx
0x140018b0e  retn
```
