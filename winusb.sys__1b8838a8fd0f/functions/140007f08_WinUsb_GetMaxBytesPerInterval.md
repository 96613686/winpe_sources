# WinUsb_GetMaxBytesPerInterval

- ea: `0x140007f08`
- end: `0x140007fd5`
- name: `WinUsb_GetMaxBytesPerInterval`
- size: `205`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140006dec`

## callees

- `0x140007f08`

## import_xrefs

- `USBD!USBD_ParseDescriptors` at `0x140007f76`
- `USBD!USBD_ParseDescriptors` at `0x140007f76`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x140007f3d`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x140007f3d`

## pseudocode

```c
__int64 __fastcall WinUsb_GetMaxBytesPerInterval(__int64 a1, unsigned __int8 *a2, __int64 a3)
{
  struct _USB_CONFIGURATION_DESCRIPTOR *v3; // rdi
  unsigned int v6; // ebx
  PUSB_INTERFACE_DESCRIPTOR v7; // rax
  __int64 wTotalLength; // rbp
  PUSB_INTERFACE_DESCRIPTOR v9; // r8
  ULONG i; // edx
  __int64 bLength; // rcx
  PUSB_COMMON_DESCRIPTOR v12; // rdx
  char *v13; // rcx

  v3 = *(struct _USB_CONFIGURATION_DESCRIPTOR **)(a1 + 56);
  v6 = 0;
  v7 = USBD_ParseConfigurationDescriptorEx(v3, v3, *a2, a2[1], -1, -1, -1);
  if ( v7 )
  {
    wTotalLength = v3->wTotalLength;
    v9 = v7;
    for ( i = v3->wTotalLength; ; i = v3->wTotalLength )
    {
      v12 = USBD_ParseDescriptors(v3, i, v9, 5);
      if ( !v12 )
        break;
      bLength = v12->bLength;
      if ( v12[1].bLength == *(_BYTE *)(a3 + 8) )
      {
        v13 = (char *)(&v12->bLength + bLength);
        if ( v13 < (char *)&v3->bLength + wTotalLength && v13[1] == 48 && v13 )
        {
          return *((unsigned __int16 *)v13 + 2);
        }
        else
        {
          v6 = (unsigned __int16)v12[2];
          if ( (*(_DWORD *)(a1 + 32) & 4) != 0 )
            return (*(_WORD *)&v12[2] & 0x7FF) * (((v6 >> 11) & 3) + 1);
        }
        return v6;
      }
      v9 = (PUSB_INTERFACE_DESCRIPTOR)(&v12->bLength + bLength);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x140007f08  push    rbx
0x140007f0a  push    rbp
0x140007f0b  push    rsi
0x140007f0c  push    rdi
0x140007f0d  push    r14
0x140007f0f  sub     rsp, 40h
0x140007f13  mov     rdi, [rcx+38h]
0x140007f17  or      eax, 0FFFFFFFFh
0x140007f1a  movzx   r9d, byte ptr [rdx+1]; AlternateSetting
0x140007f1f  mov     r14, r8
0x140007f22  movzx   r8d, byte ptr [rdx]; InterfaceNumber
0x140007f26  mov     rsi, rcx
0x140007f29  mov     [rsp+68h+InterfaceProtocol], eax; InterfaceProtocol
0x140007f2d  mov     rdx, rdi; StartPosition
0x140007f30  mov     [rsp+68h+InterfaceSubClass], eax; InterfaceSubClass
0x140007f34  mov     rcx, rdi; ConfigurationDescriptor
0x140007f37  mov     [rsp+68h+InterfaceClass], eax; InterfaceClass
0x140007f3b  xor     ebx, ebx
0x140007f3d  call    cs:__imp_USBD_ParseConfigurationDescriptorEx
0x140007f44  nop     dword ptr [rax+rax+00h]
0x140007f49  test    rax, rax
0x140007f4c  jz      short loc_140007FC7
0x140007f4e  movzx   ebp, word ptr [rdi+2]
0x140007f52  mov     r8, rax
0x140007f55  mov     edx, ebp
0x140007f57  jmp     short loc_140007F6D
0x140007f59  mov     al, [r14+8]
0x140007f5d  movzx   ecx, byte ptr [rdx]
0x140007f60  cmp     [rdx+2], al
0x140007f63  jz      short loc_140007F8C
0x140007f65  lea     r8, [rdx+rcx]; StartPosition
0x140007f69  movzx   edx, word ptr [rdi+2]; TotalLength
0x140007f6d  mov     r9d, 5; DescriptorType
0x140007f73  mov     rcx, rdi; DescriptorBuffer
0x140007f76  call    cs:__imp_USBD_ParseDescriptors
0x140007f7d  nop     dword ptr [rax+rax+00h]
0x140007f82  mov     rdx, rax
0x140007f85  test    rax, rax
0x140007f88  jnz     short loc_140007F59
0x140007f8a  jmp     short loc_140007FC7
0x140007f8c  add     rcx, rdx
0x140007f8f  lea     rax, [rdi+rbp]
0x140007f93  cmp     rcx, rax
0x140007f96  jnb     short loc_140007FA9
0x140007f98  cmp     byte ptr [rcx+1], 30h ; '0'
0x140007f9c  jnz     short loc_140007FA9
0x140007f9e  test    rcx, rcx
0x140007fa1  jz      short loc_140007FA9
0x140007fa3  movzx   ebx, word ptr [rcx+4]
0x140007fa7  jmp     short loc_140007FC7
0x140007fa9  movzx   ecx, word ptr [rdx+4]
0x140007fad  mov     eax, [rsi+20h]
0x140007fb0  mov     ebx, ecx
0x140007fb2  test    al, 4
0x140007fb4  jz      short loc_140007FC7
0x140007fb6  shr     ebx, 0Bh
0x140007fb9  and     ecx, 7FFh
0x140007fbf  and     ebx, 3
0x140007fc2  inc     ebx
0x140007fc4  imul    ebx, ecx
0x140007fc7  mov     eax, ebx
0x140007fc9  add     rsp, 40h
0x140007fcd  pop     r14
0x140007fcf  pop     rdi
0x140007fd0  pop     rsi
0x140007fd1  pop     rbp
0x140007fd2  pop     rbx
0x140007fd3  retn
```
