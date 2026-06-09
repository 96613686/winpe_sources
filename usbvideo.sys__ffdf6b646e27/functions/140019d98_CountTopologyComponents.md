# CountTopologyComponents

- ea: `0x140019d98`
- end: `0x140019fc1`
- name: `CountTopologyComponents`
- size: `553`
- prototype: `__int64 __usercall@<rax>(PVOID DescriptorBuffer@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140021fb4`

## callees

- `0x140004bac`
- `0x14000d790`
- `0x140019d98`
- `0x14001b2f4`
- `0x140021bc8`

## import_xrefs

- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x140019df9`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x140019df9`

## pseudocode

```c
__int64 __fastcall CountTopologyComponents(
        struct _USB_CONFIGURATION_DESCRIPTOR *DescriptorBuffer,
        _DWORD *a2,
        _DWORD *a3,
        _DWORD *a4,
        _DWORD *a5)
{
  unsigned __int16 *p_bLength; // r14
  struct _USB_CONFIGURATION_DESCRIPTOR *i; // rdx
  __int64 result; // rax
  unsigned __int8 *v11; // r15
  PUSB_COMMON_DESCRIPTOR v12; // rax
  PUSB_COMMON_DESCRIPTOR v13; // rbp
  unsigned __int8 *j; // rbx
  int v15; // eax
  unsigned int PinNumberForStreamingTerminalUnit; // eax
  __int64 VideoStreamingInputHeader; // rax
  unsigned __int8 v18; // cl

  *a2 = 0;
  *a3 = 0;
  p_bLength = (unsigned __int16 *)&DescriptorBuffer->bLength;
  *a4 = 0;
  *a5 = 0;
  for ( i = DescriptorBuffer; ; i = (struct _USB_CONFIGURATION_DESCRIPTOR *)&v11[*v11] )
  {
    result = (__int64)USBD_ParseConfigurationDescriptorEx(DescriptorBuffer, i, -1, -1, 14, 1, -1);
    v11 = (unsigned __int8 *)result;
    if ( !result )
      break;
    v12 = USBParseDescriptorWrapper(p_bLength, p_bLength[1], (void *)result, 36, 0xCu);
    v13 = v12;
    if ( v12 )
    {
      for ( j = (unsigned __int8 *)USBParseDescriptorWrapper(
                                     v12,
                                     *(unsigned __int16 *)&v12[2].bDescriptorType,
                                     v12,
                                     36,
                                     4u);
            ;
            j = (unsigned __int8 *)((unsigned __int64)&j[*j]
                                  & -(__int64)(&j[*j] < &v13->bLength + *(unsigned __int16 *)&v13[2].bDescriptorType)) )
      {
        if ( !j )
          goto LABEL_25;
        if ( j[1] != 36 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_092df6b9c3fc3deff23d72b76b446421_Traceguids);
          return 3221225485LL;
        }
        if ( j[2] == 2 )
          goto LABEL_21;
        if ( j[2] == 3 )
          break;
        switch ( j[2] )
        {
          case 4u:
            v15 = j[4];
            break;
          case 5u:
            goto LABEL_13;
          case 6u:
            v15 = j[21];
            break;
          case 7u:
LABEL_13:
            ++*a3;
            ++*a4;
            continue;
          default:
            continue;
        }
        ++*a3;
        *a4 += v15;
LABEL_24:
        ;
      }
      ++*a4;
      if ( *((_WORD *)j + 2) == 257 )
      {
        PinNumberForStreamingTerminalUnit = GetPinNumberForStreamingTerminalUnit(p_bLength);
        VideoStreamingInputHeader = GetVideoStreamingInputHeader(PinNumberForStreamingTerminalUnit, p_bLength);
        if ( !VideoStreamingInputHeader )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_092df6b9c3fc3deff23d72b76b446421_Traceguids);
          return 3221225473LL;
        }
        if ( (unsigned __int8)(*(_BYTE *)(VideoStreamingInputHeader + 9) - 2) <= 1u )
          ++*a4;
      }
LABEL_21:
      ++*a3;
      ++*a4;
      if ( *((_WORD *)j + 2) == 257 )
      {
        v18 = j[2];
        if ( ((1 << v18) & *a5) == 0 )
        {
          *a5 |= 1 << v18;
          *a2 += (v18 == 2) + 1;
        }
      }
      goto LABEL_24;
    }
LABEL_25:
    DescriptorBuffer = (struct _USB_CONFIGURATION_DESCRIPTOR *)p_bLength;
  }
  return result;
}

```

## disassembly

```asm
0x140019d98  push    rbx
0x140019d9a  push    rbp
0x140019d9b  push    rsi
0x140019d9c  push    rdi
0x140019d9d  push    r12
0x140019d9f  push    r13
0x140019da1  push    r14
0x140019da3  push    r15
0x140019da5  sub     rsp, 48h
0x140019da9  mov     r12, [rsp+88h+arg_20]
0x140019db1  mov     r13, rdx
0x140019db4  mov     dword ptr [rdx], 0
0x140019dba  mov     rdi, r9
0x140019dbd  mov     rsi, r8
0x140019dc0  mov     dword ptr [r8], 0
0x140019dc7  mov     r14, rcx
0x140019dca  mov     dword ptr [r9], 0
0x140019dd1  mov     dword ptr [r12], 0
0x140019dd9  or      ebx, 0FFFFFFFFh
0x140019ddc  mov     rdx, rcx; StartPosition
0x140019ddf  mov     [rsp+88h+InterfaceProtocol], ebx; InterfaceProtocol
0x140019de3  mov     r9d, ebx; AlternateSetting
0x140019de6  mov     [rsp+88h+InterfaceSubClass], 1; InterfaceSubClass
0x140019dee  mov     r8d, ebx; InterfaceNumber
0x140019df1  mov     [rsp+88h+InterfaceClass], 0Eh; InterfaceClass
0x140019df9  call    cs:__imp_USBD_ParseConfigurationDescriptorEx
0x140019e00  nop     dword ptr [rax+rax+00h]
0x140019e05  mov     r15, rax
0x140019e08  test    rax, rax
0x140019e0b  jz      loc_140019FAF
0x140019e11  movzx   edx, word ptr [r14+2]
0x140019e16  mov     r9d, 24h ; '$'
0x140019e1c  mov     r8, rax
0x140019e1f  mov     qword ptr [rsp+88h+InterfaceClass], 0Ch
0x140019e28  mov     rcx, r14
0x140019e2b  call    USBParseDescriptorWrapper
0x140019e30  mov     rbp, rax
0x140019e33  test    rax, rax
0x140019e36  jz      loc_140019F38
0x140019e3c  movzx   edx, word ptr [rax+5]
0x140019e40  mov     r9d, 24h ; '$'
0x140019e46  mov     r8, rax
0x140019e49  mov     qword ptr [rsp+88h+InterfaceClass], 4
0x140019e52  mov     rcx, rax
0x140019e55  call    USBParseDescriptorWrapper
0x140019e5a  mov     rbx, rax
0x140019e5d  test    rbx, rbx
0x140019e60  jz      loc_140019F35
0x140019e66  cmp     byte ptr [rbx+1], 24h ; '$'
0x140019e6a  jnz     loc_140019F7C
0x140019e70  movzx   ecx, byte ptr [rbx+2]
0x140019e74  sub     ecx, 2
0x140019e77  jz      short loc_140019EE5
0x140019e79  sub     ecx, 1
0x140019e7c  jz      short loc_140019EAC
0x140019e7e  sub     ecx, 1
0x140019e81  jz      short loc_140019EA2
0x140019e83  sub     ecx, 1
0x140019e86  jz      short loc_140019E96
0x140019e88  sub     ecx, 1
0x140019e8b  jz      short loc_140019E9C
0x140019e8d  cmp     ecx, 1
0x140019e90  jnz     loc_140019F1A
0x140019e96  inc     dword ptr [rsi]
0x140019e98  inc     dword ptr [rdi]
0x140019e9a  jmp     short loc_140019F1A
0x140019e9c  movzx   eax, byte ptr [rbx+15h]
0x140019ea0  jmp     short loc_140019EA6
0x140019ea2  movzx   eax, byte ptr [rbx+4]
0x140019ea6  inc     dword ptr [rsi]
0x140019ea8  add     [rdi], eax
0x140019eaa  jmp     short loc_140019F1A
0x140019eac  inc     dword ptr [rdi]
0x140019eae  mov     eax, 101h
0x140019eb3  cmp     [rbx+4], ax
0x140019eb7  jnz     short loc_140019EEA
0x140019eb9  mov     dl, [rbx+3]
0x140019ebc  mov     rcx, r14; DescriptorBuffer
0x140019ebf  call    GetPinNumberForStreamingTerminalUnit
0x140019ec4  mov     rdx, r14
0x140019ec7  mov     ecx, eax
0x140019ec9  call    GetVideoStreamingInputHeader
0x140019ece  test    rax, rax
0x140019ed1  jz      short loc_140019F47
0x140019ed3  mov     al, [rax+9]
0x140019ed6  sub     al, 2
0x140019ed8  cmp     al, 1
0x140019eda  mov     eax, 101h
0x140019edf  ja      short loc_140019EEA
0x140019ee1  inc     dword ptr [rdi]
0x140019ee3  jmp     short loc_140019EEA
0x140019ee5  mov     eax, 101h
0x140019eea  inc     dword ptr [rsi]
0x140019eec  inc     dword ptr [rdi]
0x140019eee  cmp     [rbx+4], ax
0x140019ef2  jnz     short loc_140019F1A
0x140019ef4  mov     cl, [rbx+2]
0x140019ef7  mov     eax, 1
0x140019efc  mov     edx, [r12]
0x140019f00  shl     eax, cl
0x140019f02  test    edx, eax
0x140019f04  jnz     short loc_140019F1A
0x140019f06  or      eax, edx
0x140019f08  mov     [r12], eax
0x140019f0c  xor     eax, eax
0x140019f0e  cmp     cl, 2
0x140019f11  setz    al
0x140019f14  inc     eax
0x140019f16  add     [r13+0], eax
0x140019f1a  movzx   ecx, byte ptr [rbx]
0x140019f1d  movzx   eax, word ptr [rbp+5]
0x140019f21  add     rcx, rbx
0x140019f24  add     rax, rbp
0x140019f27  cmp     rcx, rax
0x140019f2a  sbb     rbx, rbx
0x140019f2d  and     rbx, rcx
0x140019f30  jmp     loc_140019E5D
0x140019f35  or      ebx, 0FFFFFFFFh
0x140019f38  movzx   edx, byte ptr [r15]
0x140019f3c  mov     rcx, r14
0x140019f3f  add     rdx, r15
0x140019f42  jmp     loc_140019DDF
0x140019f47  mov     rcx, cs:WPP_GLOBAL_Control
0x140019f4e  lea     rax, WPP_GLOBAL_Control
0x140019f55  cmp     rcx, rax
0x140019f58  jz      short loc_140019F75
0x140019f5a  cmp     byte ptr [rcx+29h], 5
0x140019f5e  jb      short loc_140019F75
0x140019f60  mov     rcx, [rcx+18h]
0x140019f64  lea     r8, WPP_092df6b9c3fc3deff23d72b76b446421_Traceguids
0x140019f6b  mov     edx, 25h ; '%'
0x140019f70  call    WPP_SF_
0x140019f75  mov     eax, 0C0000001h
0x140019f7a  jmp     short loc_140019FAF
0x140019f7c  mov     rcx, cs:WPP_GLOBAL_Control
0x140019f83  lea     rax, WPP_GLOBAL_Control
0x140019f8a  cmp     rcx, rax
0x140019f8d  jz      short loc_140019FAA
0x140019f8f  cmp     byte ptr [rcx+29h], 2
0x140019f93  jb      short loc_140019FAA
0x140019f95  mov     rcx, [rcx+18h]
0x140019f99  lea     r8, WPP_092df6b9c3fc3deff23d72b76b446421_Traceguids
0x140019fa0  mov     edx, 24h ; '$'
0x140019fa5  call    WPP_SF_
0x140019faa  mov     eax, 0C000000Dh
0x140019faf  add     rsp, 48h
0x140019fb3  pop     r15
0x140019fb5  pop     r14
0x140019fb7  pop     r13
0x140019fb9  pop     r12
0x140019fbb  pop     rdi
0x140019fbc  pop     rsi
0x140019fbd  pop     rbp
0x140019fbe  pop     rbx
0x140019fbf  retn
```
