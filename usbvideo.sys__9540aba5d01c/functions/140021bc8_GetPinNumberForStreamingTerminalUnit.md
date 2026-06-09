# GetPinNumberForStreamingTerminalUnit

- ea: `0x140021bc8`
- end: `0x140021c4d`
- name: `GetPinNumberForStreamingTerminalUnit`
- size: `133`
- prototype: `__int64 __fastcall(PVOID DescriptorBuffer)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400125c0`
- `0x140019d98`
- `0x140022ac0`

## callees

- `0x14000c80c`
- `0x14000cb20`
- `0x14000d3e8`
- `0x140021bc8`

## pseudocode

```c
__int64 __fastcall GetPinNumberForStreamingTerminalUnit(
        struct _USB_CONFIGURATION_DESCRIPTOR *DescriptorBuffer,
        unsigned __int8 a2)
{
  unsigned int v2; // edi
  unsigned int v4; // edx
  struct _USB_CONFIGURATION_DESCRIPTOR *v5; // rsi
  struct _USB_COMMON_DESCRIPTOR *FirstVideoStreamingAltSetting; // rbx
  PUSB_COMMON_DESCRIPTOR VideoSpecificDescriptor; // rax
  bool v8; // zf
  PUSB_COMMON_DESCRIPTOR v9; // rax

  v2 = 0;
  v4 = 0;
  v5 = DescriptorBuffer;
LABEL_2:
  FirstVideoStreamingAltSetting = (struct _USB_COMMON_DESCRIPTOR *)GetFirstVideoStreamingAltSetting(
                                                                     DescriptorBuffer,
                                                                     v4);
  while ( FirstVideoStreamingAltSetting )
  {
    VideoSpecificDescriptor = GetVideoSpecificDescriptor(v5, FirstVideoStreamingAltSetting, 1);
    if ( VideoSpecificDescriptor )
    {
      v8 = VideoSpecificDescriptor[4].bLength == a2;
    }
    else
    {
      v9 = GetVideoSpecificDescriptor(v5, FirstVideoStreamingAltSetting, 2);
      if ( !v9 )
        goto LABEL_9;
      v8 = v9[3].bDescriptorType == a2;
    }
    if ( v8 )
      return v2;
LABEL_9:
    FirstVideoStreamingAltSetting = (struct _USB_COMMON_DESCRIPTOR *)GetNextVideoAltSetting(
                                                                       v5,
                                                                       &FirstVideoStreamingAltSetting->bLength);
    if ( !FirstVideoStreamingAltSetting )
    {
      ++v2;
      DescriptorBuffer = v5;
      v4 = v2;
      goto LABEL_2;
    }
  }
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x140021bc8  push    rbx
0x140021bca  push    rbp
0x140021bcb  push    rsi
0x140021bcc  push    rdi
0x140021bcd  sub     rsp, 28h
0x140021bd1  xor     edi, edi
0x140021bd3  mov     bpl, dl
0x140021bd6  xor     edx, edx
0x140021bd8  mov     rsi, rcx
0x140021bdb  call    GetFirstVideoStreamingAltSetting
0x140021be0  mov     rbx, rax
0x140021be3  test    rbx, rbx
0x140021be6  jz      short loc_140021C40
0x140021be8  mov     r8d, 1
0x140021bee  mov     rdx, rbx
0x140021bf1  mov     rcx, rsi; DescriptorBuffer
0x140021bf4  call    GetVideoSpecificDescriptor
0x140021bf9  test    rax, rax
0x140021bfc  jz      short loc_140021C04
0x140021bfe  cmp     [rax+8], bpl
0x140021c02  jmp     short loc_140021C1E
0x140021c04  mov     r8d, 2
0x140021c0a  mov     rdx, rbx
0x140021c0d  mov     rcx, rsi; DescriptorBuffer
0x140021c10  call    GetVideoSpecificDescriptor
0x140021c15  test    rax, rax
0x140021c18  jz      short loc_140021C20
0x140021c1a  cmp     [rax+7], bpl
0x140021c1e  jz      short loc_140021C3C
0x140021c20  mov     rdx, rbx
0x140021c23  mov     rcx, rsi
0x140021c26  call    GetNextVideoAltSetting
0x140021c2b  mov     rbx, rax
0x140021c2e  test    rax, rax
0x140021c31  jnz     short loc_140021BE3
0x140021c33  inc     edi
0x140021c35  mov     rcx, rsi
0x140021c38  mov     edx, edi
0x140021c3a  jmp     short loc_140021BDB
0x140021c3c  mov     eax, edi
0x140021c3e  jmp     short loc_140021C43
0x140021c40  or      eax, 0FFFFFFFFh
0x140021c43  add     rsp, 28h
0x140021c47  pop     rdi
0x140021c48  pop     rsi
0x140021c49  pop     rbp
0x140021c4a  pop     rbx
0x140021c4b  retn
```
