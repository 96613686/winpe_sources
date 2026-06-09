# GetTerminalUnitForBridgePin

- ea: `0x140021dd8`
- end: `0x140021f22`
- name: `GetTerminalUnitForBridgePin`
- size: `330`
- prototype: `__int64 __fastcall(PUSB_CONFIGURATION_DESCRIPTOR ConfigurationDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140023dfc`

## callees

- `0x14000d790`
- `0x140021dd8`

## import_xrefs

- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x140021e14`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x140021ef7`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x140021e14`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x140021ef7`

## pseudocode

```c
unsigned __int8 *__fastcall GetTerminalUnitForBridgePin(PUSB_CONFIGURATION_DESCRIPTOR ConfigurationDescriptor, int a2)
{
  unsigned __int8 *v4; // rbx
  char v5; // si
  int v6; // edi
  PUSB_INTERFACE_DESCRIPTOR v7; // r14
  __int64 v8; // rax
  __int64 v9; // rbp
  int v10; // eax

  v4 = 0;
  v5 = 0;
  v6 = 0;
  v7 = USBD_ParseConfigurationDescriptorEx(ConfigurationDescriptor, ConfigurationDescriptor, -1, -1, 14, 1, -1);
  while ( v7 )
  {
    if ( v5 )
      break;
    v8 = USBParseDescriptorWrapper(
           (_DWORD)ConfigurationDescriptor,
           ConfigurationDescriptor->wTotalLength,
           (_DWORD)v7,
           36,
           12);
    v9 = v8;
    if ( v8 && (v4 = (unsigned __int8 *)USBParseDescriptorWrapper(v8, *(unsigned __int16 *)(v8 + 5), v8, 36, 4)) != 0 )
    {
      while ( !v5 )
      {
        if ( (v4[2] == 2 || v4[2] == 3) && *((_WORD *)v4 + 2) != 257 && (v10 = v6, ++v6, v10 == a2) )
        {
          v5 = 1;
        }
        else
        {
          v4 += *v4;
          if ( (unsigned __int64)v4 >= v9 + (unsigned __int64)*(unsigned __int16 *)(v9 + 5) )
          {
            v4 = 0;
            goto LABEL_16;
          }
        }
        if ( !v4 )
        {
          if ( v5 )
            break;
          goto LABEL_16;
        }
      }
    }
    else
    {
LABEL_16:
      v7 = USBD_ParseConfigurationDescriptorEx(ConfigurationDescriptor, &v7->bLength + v7->bLength, -1, -1, 14, 1, -1);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x140021dd8  push    rbx
0x140021dda  push    rbp
0x140021ddb  push    rsi
0x140021ddc  push    rdi
0x140021ddd  push    r12
0x140021ddf  push    r14
0x140021de1  push    r15
0x140021de3  sub     rsp, 40h
0x140021de7  or      ebp, 0FFFFFFFFh
0x140021dea  mov     r12d, edx
0x140021ded  mov     [rsp+78h+InterfaceProtocol], ebp; InterfaceProtocol
0x140021df1  mov     r9d, ebp; AlternateSetting
0x140021df4  mov     [rsp+78h+InterfaceSubClass], 1; InterfaceSubClass
0x140021dfc  mov     r8d, ebp; InterfaceNumber
0x140021dff  mov     rdx, rcx; StartPosition
0x140021e02  mov     [rsp+78h+InterfaceClass], 0Eh; InterfaceClass
0x140021e0a  mov     r15, rcx
0x140021e0d  xor     ebx, ebx
0x140021e0f  xor     sil, sil
0x140021e12  xor     edi, edi
0x140021e14  call    cs:__imp_USBD_ParseConfigurationDescriptorEx
0x140021e1b  nop     dword ptr [rax+rax+00h]
0x140021e20  mov     r14, rax
0x140021e23  test    rax, rax
0x140021e26  jz      loc_140021F0F
0x140021e2c  test    sil, sil
0x140021e2f  jnz     loc_140021F0F
0x140021e35  movzx   edx, word ptr [r15+2]
0x140021e3a  mov     r9d, 24h ; '$'
0x140021e40  mov     r8, r14
0x140021e43  mov     qword ptr [rsp+78h+InterfaceClass], 0Ch
0x140021e4c  mov     rcx, r15
0x140021e4f  call    USBParseDescriptorWrapper
0x140021e54  mov     rbp, rax
0x140021e57  test    rax, rax
0x140021e5a  jz      short loc_140021ED0
0x140021e5c  movzx   edx, word ptr [rax+5]
0x140021e60  mov     r9d, 24h ; '$'
0x140021e66  mov     r8, rax
0x140021e69  mov     qword ptr [rsp+78h+InterfaceClass], 4
0x140021e72  mov     rcx, rax
0x140021e75  call    USBParseDescriptorWrapper
0x140021e7a  mov     rbx, rax
0x140021e7d  test    rax, rax
0x140021e80  jz      short loc_140021ED0
0x140021e82  test    sil, sil
0x140021e85  jnz     short loc_140021F06
0x140021e87  movzx   edx, byte ptr [rbx+2]
0x140021e8b  sub     edx, 2
0x140021e8e  jz      short loc_140021E95
0x140021e90  cmp     edx, 1
0x140021e93  jnz     short loc_140021EAE
0x140021e95  mov     eax, 101h
0x140021e9a  cmp     [rbx+4], ax
0x140021e9e  jz      short loc_140021EAE
0x140021ea0  mov     eax, edi
0x140021ea2  inc     edi
0x140021ea4  cmp     eax, r12d
0x140021ea7  jnz     short loc_140021EAE
0x140021ea9  mov     sil, 1
0x140021eac  jmp     short loc_140021EC0
0x140021eae  movzx   eax, byte ptr [rbx]
0x140021eb1  add     rbx, rax
0x140021eb4  movzx   eax, word ptr [rbp+5]
0x140021eb8  add     rax, rbp
0x140021ebb  cmp     rbx, rax
0x140021ebe  jnb     short loc_140021ECE
0x140021ec0  mov     al, sil
0x140021ec3  test    rbx, rbx
0x140021ec6  jnz     short loc_140021E82
0x140021ec8  test    al, al
0x140021eca  jnz     short loc_140021F06
0x140021ecc  jmp     short loc_140021ED0
0x140021ece  xor     ebx, ebx
0x140021ed0  movzx   edx, byte ptr [r14]
0x140021ed4  or      eax, 0FFFFFFFFh
0x140021ed7  mov     [rsp+78h+InterfaceProtocol], eax; InterfaceProtocol
0x140021edb  add     rdx, r14; StartPosition
0x140021ede  mov     [rsp+78h+InterfaceSubClass], 1; InterfaceSubClass
0x140021ee6  mov     r9d, eax; AlternateSetting
0x140021ee9  mov     r8d, eax; InterfaceNumber
0x140021eec  mov     [rsp+78h+InterfaceClass], 0Eh; InterfaceClass
0x140021ef4  mov     rcx, r15; ConfigurationDescriptor
0x140021ef7  call    cs:__imp_USBD_ParseConfigurationDescriptorEx
0x140021efe  nop     dword ptr [rax+rax+00h]
0x140021f03  mov     r14, rax
0x140021f06  test    r14, r14
0x140021f09  jnz     loc_140021E2C
0x140021f0f  mov     rax, rbx
0x140021f12  add     rsp, 40h
0x140021f16  pop     r15
0x140021f18  pop     r14
0x140021f1a  pop     r12
0x140021f1c  pop     rdi
0x140021f1d  pop     rsi
0x140021f1e  pop     rbp
0x140021f1f  pop     rbx
0x140021f20  retn
```
