# GetChannelDescForInterface

- ea: `0x1400131c0`
- end: `0x14001330b`
- name: `GetChannelDescForInterface`
- size: `331`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140013630`

## callees

- `0x1400088b4`
- `0x1400131c0`

## import_xrefs

- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x1400131f5`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x1400131f5`

## pseudocode

```c
PUSB_INTERFACE_DESCRIPTOR __fastcall GetChannelDescForInterface(__int64 a1)
{
  struct _USB_CONFIGURATION_DESCRIPTOR *v1; // rbx
  __int64 wTotalLength; // rsi
  PUSB_INTERFACE_DESCRIPTOR v4; // rdi
  PUSB_INTERFACE_DESCRIPTOR v5; // rdx
  unsigned __int8 *v6; // r8
  __int64 bLength; // rax
  struct _USB_INTERFACE_DESCRIPTOR *v8; // rcx
  unsigned __int8 *p_bLength; // rax
  unsigned __int8 *i; // rdx

  v1 = *(struct _USB_CONFIGURATION_DESCRIPTOR **)(a1 + 48);
  wTotalLength = v1->wTotalLength;
  v4 = 0;
  v5 = USBD_ParseConfigurationDescriptorEx(v1, v1, -1, 0, 13, -1, -1);
  if ( v5 )
  {
    v6 = &v1->bLength + wTotalLength;
    while ( v6 >= (unsigned __int8 *)v5
         && v6 - (unsigned __int8 *)v5 <= 0xFFFF
         && (unsigned __int64)(v6 - (unsigned __int8 *)v5) >= 2 )
    {
      bLength = v5->bLength;
      if ( v5->bDescriptorType == 34 )
      {
        v4 = v5;
        if ( (unsigned __int8)bLength < 7u )
          return 0;
        v8 = (PUSB_INTERFACE_DESCRIPTOR)((char *)v5 + bLength);
        p_bLength = &v1->bLength + wTotalLength;
        if ( v5 <= v8 )
          p_bLength = &v8->bLength;
        if ( p_bLength <= v6 )
          v6 = p_bLength;
        if ( (unsigned __int64)(v6 - (unsigned __int8 *)v5) < 7 )
          return 0;
        if ( (unsigned int)((_DWORD)v6 - (_DWORD)v5) > 7 )
        {
          for ( i = &v5->bInterfaceProtocol; v6 >= i && v6 - i <= 0xFFFF && v6 != i; i += 2 )
          {
            if ( i && *i == 1 )
              return v4;
            if ( i + 2 < i )
              break;
          }
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(i) = 2;
            WPP_RECORDER_SF_(
              *(_QWORD *)(a1 + 1368),
              (_DWORD)i,
              8,
              16,
              (__int64)WPP_e6d2562f3eed34437ee263ed282fdffa_Traceguids);
          }
          return 0;
        }
        return v4;
      }
      if ( !(_BYTE)bLength || (PUSB_INTERFACE_DESCRIPTOR)((char *)v5 + bLength) < v5 )
        return v4;
      v5 = (PUSB_INTERFACE_DESCRIPTOR)((char *)v5 + bLength);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1400131c0  push    rbx
0x1400131c2  push    rbp
0x1400131c3  push    rsi
0x1400131c4  push    rdi
0x1400131c5  sub     rsp, 48h
0x1400131c9  mov     rbx, [rcx+30h]
0x1400131cd  or      r8d, 0FFFFFFFFh; InterfaceNumber
0x1400131d1  mov     [rsp+68h+InterfaceProtocol], r8d; InterfaceProtocol
0x1400131d6  mov     rbp, rcx
0x1400131d9  mov     [rsp+68h+InterfaceSubClass], r8d; InterfaceSubClass
0x1400131de  xor     r9d, r9d; AlternateSetting
0x1400131e1  mov     rdx, rbx; StartPosition
0x1400131e4  mov     [rsp+68h+InterfaceClass], 0Dh; InterfaceClass
0x1400131ec  movzx   esi, word ptr [rbx+2]
0x1400131f0  mov     rcx, rbx; ConfigurationDescriptor
0x1400131f3  xor     edi, edi
0x1400131f5  call    cs:__imp_USBD_ParseConfigurationDescriptorEx
0x1400131fc  nop     dword ptr [rax+rax+00h]
0x140013201  mov     rdx, rax
0x140013204  test    rax, rax
0x140013207  jz      loc_1400132FA
0x14001320d  lea     r8, [rbx+rsi]
0x140013211  mov     r9d, 0FFFFh
0x140013217  cmp     r8, rdx
0x14001321a  jb      loc_1400132FA
0x140013220  mov     rax, r8
0x140013223  sub     rax, rdx
0x140013226  cmp     rax, r9
0x140013229  jg      loc_1400132FA
0x14001322f  cmp     rax, 2
0x140013233  jb      loc_1400132FA
0x140013239  cmp     byte ptr [rdx+1], 22h ; '"'
0x14001323d  movzx   eax, byte ptr [rdx]
0x140013240  jz      short loc_14001325C
0x140013242  test    al, al
0x140013244  jz      loc_1400132FA
0x14001324a  lea     rcx, [rdx+rax]
0x14001324e  cmp     rcx, rdx
0x140013251  jb      loc_1400132FA
0x140013257  mov     rdx, rcx
0x14001325a  jmp     short loc_140013217
0x14001325c  mov     rdi, rdx
0x14001325f  cmp     al, 7
0x140013261  jb      loc_140013307
0x140013267  lea     rcx, [rdx+rax]
0x14001326b  mov     rax, r8
0x14001326e  cmp     rdx, rcx
0x140013271  cmovbe  rax, rcx
0x140013275  cmp     rax, r8
0x140013278  cmovbe  r8, rax
0x14001327c  mov     rax, r8
0x14001327f  sub     rax, rdx
0x140013282  cmp     rax, 7
0x140013286  jb      short loc_140013307
0x140013288  mov     eax, r8d
0x14001328b  sub     eax, edx
0x14001328d  cmp     eax, 7
0x140013290  jbe     short loc_1400132FA
0x140013292  add     rdx, 7
0x140013296  cmp     r8, rdx
0x140013299  jb      short loc_1400132C4
0x14001329b  mov     rax, r8
0x14001329e  sub     rax, rdx
0x1400132a1  cmp     rax, r9
0x1400132a4  jg      short loc_1400132C4
0x1400132a6  cmp     rax, 1
0x1400132aa  jb      short loc_1400132C4
0x1400132ac  test    rdx, rdx
0x1400132af  jz      short loc_1400132B6
0x1400132b1  cmp     byte ptr [rdx], 1
0x1400132b4  jz      short loc_1400132FA
0x1400132b6  lea     rax, [rdx+2]
0x1400132ba  cmp     rax, rdx
0x1400132bd  jb      short loc_1400132C4
0x1400132bf  mov     rdx, rax
0x1400132c2  jmp     short loc_140013296
0x1400132c4  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400132cb  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400132d2  jz      short loc_1400132F8
0x1400132d4  mov     rcx, [rbp+558h]
0x1400132db  lea     rax, WPP_e6d2562f3eed34437ee263ed282fdffa_Traceguids
0x1400132e2  mov     r9d, 10h
0x1400132e8  mov     qword ptr [rsp+68h+InterfaceClass], rax
0x1400132ed  mov     dl, 2
0x1400132ef  lea     r8d, [r9-8]
0x1400132f3  call    WPP_RECORDER_SF_
0x1400132f8  xor     edi, edi
0x1400132fa  mov     rax, rdi
0x1400132fd  add     rsp, 48h
0x140013301  pop     rdi
0x140013302  pop     rsi
0x140013303  pop     rbp
0x140013304  pop     rbx
0x140013305  retn
0x140013307  xor     eax, eax
0x140013309  jmp     short loc_1400132FD
```
