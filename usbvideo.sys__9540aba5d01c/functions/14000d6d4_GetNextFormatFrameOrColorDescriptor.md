# GetNextFormatFrameOrColorDescriptor

- ea: `0x14000d6d4`
- end: `0x14000d78a`
- name: `GetNextFormatFrameOrColorDescriptor`
- size: `182`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000cbf0`
- `0x14001a938`

## callees

- `0x140004bac`
- `0x14000d6d4`
- `0x14000d790`

## pseudocode

```c
PUSB_COMMON_DESCRIPTOR __fastcall GetNextFormatFrameOrColorDescriptor(
        unsigned __int16 *a1,
        unsigned __int8 *a2,
        unsigned __int8 *a3)
{
  PUSB_COMMON_DESCRIPTOR v4; // rax
  PDEVICE_OBJECT v5; // rcx
  __int64 v6; // rdx

  v4 = USBParseDescriptorWrapper(a1, a1[1], &a2[*a2], 36, 3u);
  if ( !v4 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      return 0;
    v6 = 27;
    goto LABEL_11;
  }
  if ( v4[1].bLength == 1 || v4[1].bLength == 2 )
    return USBParseDescriptorWrapper(v4, *(_WORD *)&v4[2], &a3[*a3], 36, 3u);
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v6 = 26;
LABEL_11:
    WPP_SF_(v5->AttachedDevice, v6, WPP_092df6b9c3fc3deff23d72b76b446421_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x14000d6d4  push    rbx
0x14000d6d6  sub     rsp, 30h
0x14000d6da  mov     rbx, r8
0x14000d6dd  mov     [rsp+38h+var_18], 3
0x14000d6e6  movzx   r8d, byte ptr [rdx]
0x14000d6ea  mov     r9d, 24h ; '$'
0x14000d6f0  add     r8, rdx
0x14000d6f3  movzx   edx, word ptr [rcx+2]
0x14000d6f7  call    USBParseDescriptorWrapper
0x14000d6fc  test    rax, rax
0x14000d6ff  jz      short loc_14000D753
0x14000d701  movzx   edx, byte ptr [rax+2]
0x14000d705  sub     edx, 1
0x14000d708  jz      short loc_14000D72F
0x14000d70a  cmp     edx, 1
0x14000d70d  jz      short loc_14000D72F
0x14000d70f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d716  lea     rax, WPP_GLOBAL_Control
0x14000d71d  cmp     rcx, rax
0x14000d720  jz      short loc_14000D781
0x14000d722  cmp     byte ptr [rcx+29h], 2
0x14000d726  jb      short loc_14000D781
0x14000d728  mov     edx, 1Ah
0x14000d72d  jmp     short loc_14000D771
0x14000d72f  movzx   r8d, byte ptr [rbx]
0x14000d733  mov     r9d, 24h ; '$'
0x14000d739  movzx   edx, word ptr [rax+4]
0x14000d73d  add     r8, rbx
0x14000d740  mov     rcx, rax
0x14000d743  mov     [rsp+38h+var_18], 3
0x14000d74c  call    USBParseDescriptorWrapper
0x14000d751  jmp     short loc_14000D783
0x14000d753  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d75a  lea     rax, WPP_GLOBAL_Control
0x14000d761  cmp     rcx, rax
0x14000d764  jz      short loc_14000D781
0x14000d766  cmp     byte ptr [rcx+29h], 2
0x14000d76a  jb      short loc_14000D781
0x14000d76c  mov     edx, 1Bh
0x14000d771  mov     rcx, [rcx+18h]
0x14000d775  lea     r8, WPP_092df6b9c3fc3deff23d72b76b446421_Traceguids
0x14000d77c  call    WPP_SF_
0x14000d781  xor     eax, eax
0x14000d783  add     rsp, 30h
0x14000d787  pop     rbx
0x14000d788  retn
```
