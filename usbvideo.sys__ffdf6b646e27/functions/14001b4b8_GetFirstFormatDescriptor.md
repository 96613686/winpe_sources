# GetFirstFormatDescriptor

- ea: `0x14001b4b8`
- end: `0x14001b54f`
- name: `GetFirstFormatDescriptor`
- size: `151`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000cbf0`
- `0x14001a938`

## callees

- `0x140004bac`
- `0x14000d790`
- `0x14001b4b8`

## pseudocode

```c
PUSB_COMMON_DESCRIPTOR __fastcall GetFirstFormatDescriptor(unsigned __int16 *a1, unsigned __int8 *a2)
{
  __int64 v2; // rbx
  PUSB_COMMON_DESCRIPTOR v3; // rax

  v2 = 0;
  v3 = USBParseDescriptorWrapper(a1, a1[1], &a2[*a2], 36, 3u);
  if ( !v3 )
    return (PUSB_COMMON_DESCRIPTOR)v2;
  if ( v3[1].bLength == 1 || v3[1].bLength == 2 )
    return USBParseDescriptorWrapper(v3, *(_WORD *)&v3[2], &v3->bLength + v3->bLength, 36, 3u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_092df6b9c3fc3deff23d72b76b446421_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x14001b4b8  push    rbx
0x14001b4ba  sub     rsp, 30h
0x14001b4be  movzx   r8d, byte ptr [rdx]
0x14001b4c2  xor     ebx, ebx
0x14001b4c4  add     r8, rdx
0x14001b4c7  mov     [rsp+38h+var_18], 3
0x14001b4d0  movzx   edx, word ptr [rcx+2]
0x14001b4d4  lea     r9d, [rbx+24h]
0x14001b4d8  call    USBParseDescriptorWrapper
0x14001b4dd  test    rax, rax
0x14001b4e0  jz      short loc_14001B545
0x14001b4e2  movzx   ecx, byte ptr [rax+2]
0x14001b4e6  sub     ecx, 1
0x14001b4e9  jz      short loc_14001B520
0x14001b4eb  cmp     ecx, 1
0x14001b4ee  jz      short loc_14001B520
0x14001b4f0  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b4f7  lea     rax, WPP_GLOBAL_Control
0x14001b4fe  cmp     rcx, rax
0x14001b501  jz      short loc_14001B51C
0x14001b503  cmp     byte ptr [rcx+29h], 2
0x14001b507  jb      short loc_14001B51C
0x14001b509  mov     rcx, [rcx+18h]
0x14001b50d  lea     edx, [rbx+19h]
0x14001b510  lea     r8, WPP_092df6b9c3fc3deff23d72b76b446421_Traceguids
0x14001b517  call    WPP_SF_
0x14001b51c  xor     eax, eax
0x14001b51e  jmp     short loc_14001B548
0x14001b520  movzx   r8d, byte ptr [rax]
0x14001b524  mov     r9d, 24h ; '$'
0x14001b52a  movzx   edx, word ptr [rax+4]
0x14001b52e  add     r8, rax
0x14001b531  mov     rcx, rax
0x14001b534  mov     [rsp+38h+var_18], 3
0x14001b53d  call    USBParseDescriptorWrapper
0x14001b542  mov     rbx, rax
0x14001b545  mov     rax, rbx
0x14001b548  add     rsp, 30h
0x14001b54c  pop     rbx
0x14001b54d  retn
```
