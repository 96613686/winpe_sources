# FindMidiInterfaceDescriptor

- ea: `0x140029828`
- end: `0x140029989`
- name: `FindMidiInterfaceDescriptor`
- size: `353`
- prototype: `__int64 __fastcall(PVOID DescriptorBuffer)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14002c2dc`

## callees

- `0x1400072b0`
- `0x14001d788`
- `0x140029828`

## import_xrefs

- `USBD!USBD_ParseDescriptors` at `0x1400298c7`
- `USBD!USBD_ParseDescriptors` at `0x1400298c7`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x14002985e`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x1400298a7`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x14002985e`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x1400298a7`

## pseudocode

```c
PUSB_INTERFACE_DESCRIPTOR __fastcall FindMidiInterfaceDescriptor(
        struct _USB_CONFIGURATION_DESCRIPTOR *DescriptorBuffer,
        void *a2,
        __int64 a3,
        int a4)
{
  __int64 v6; // rsi
  int v7; // edx
  PUSB_INTERFACE_DESCRIPTOR v8; // rbx
  __int64 bLength; // rcx
  unsigned __int8 *v10; // rbp
  PUSB_INTERFACE_DESCRIPTOR v11; // rdi
  PUSB_COMMON_DESCRIPTOR v12; // rax

  v6 = 0;
  v8 = USBD_ParseConfigurationDescriptorEx(DescriptorBuffer, a2, -1, -1, 1, 3, -1);
  if ( v8 )
  {
    while ( 1 )
    {
      bLength = v8->bLength;
      v10 = &v8->bLength + bLength;
      if ( (PUSB_INTERFACE_DESCRIPTOR)((char *)v8 + bLength) < v8 )
        break;
      v11 = USBD_ParseConfigurationDescriptorEx(DescriptorBuffer, &v8->bLength + bLength, -1, -1, 1, 3, -1);
      v12 = USBD_ParseDescriptors(DescriptorBuffer, DescriptorBuffer->wTotalLength, v10, 36);
      if ( !v12 || v11 && v12 > (PUSB_COMMON_DESCRIPTOR)v11 || v12->bLength < 7u || v12[1].bLength != 1 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v7) = 2;
          WPP_RECORDER_SF_q(a4, v7, 5, 71, (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids, (char)v8);
        }
        return (PUSB_INTERFACE_DESCRIPTOR)v6;
      }
      if ( v12[2].bLength == 2 )
        return v8;
      v8 = v11;
      if ( !v11 )
        return (PUSB_INTERFACE_DESCRIPTOR)v6;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = 2;
      WPP_RECORDER_SF_qd(a4, v7, 5, 70, (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids, (char)v8, bLength);
    }
  }
  return (PUSB_INTERFACE_DESCRIPTOR)v6;
}

```

## disassembly

```asm
0x140029828  push    rbx
0x14002982a  push    rbp
0x14002982b  push    rsi
0x14002982c  push    rdi
0x14002982d  push    r12
0x14002982f  push    r14
0x140029831  push    r15
0x140029833  sub     rsp, 40h
0x140029837  or      r12d, 0FFFFFFFFh
0x14002983b  mov     r14, r9
0x14002983e  mov     [rsp+78h+InterfaceProtocol], r12d; InterfaceProtocol
0x140029843  mov     r9d, r12d; AlternateSetting
0x140029846  mov     [rsp+78h+InterfaceSubClass], 3; InterfaceSubClass
0x14002984e  mov     r8d, r12d; InterfaceNumber
0x140029851  mov     [rsp+78h+InterfaceClass], 1; InterfaceClass
0x140029859  mov     r15, rcx
0x14002985c  xor     esi, esi
0x14002985e  call    cs:__imp_USBD_ParseConfigurationDescriptorEx
0x140029865  nop     dword ptr [rax+rax+00h]
0x14002986a  mov     rbx, rax
0x14002986d  test    rax, rax
0x140029870  jz      loc_140029976
0x140029876  movzx   ecx, byte ptr [rbx]
0x140029879  lea     rbp, [rcx+rbx]
0x14002987d  cmp     rbp, rbx
0x140029880  jb      loc_14002993D
0x140029886  mov     [rsp+78h+InterfaceProtocol], r12d; InterfaceProtocol
0x14002988b  mov     r9d, r12d; AlternateSetting
0x14002988e  mov     [rsp+78h+InterfaceSubClass], 3; InterfaceSubClass
0x140029896  mov     r8d, r12d; InterfaceNumber
0x140029899  mov     rdx, rbp; StartPosition
0x14002989c  mov     [rsp+78h+InterfaceClass], 1; InterfaceClass
0x1400298a4  mov     rcx, r15; ConfigurationDescriptor
0x1400298a7  call    cs:__imp_USBD_ParseConfigurationDescriptorEx
0x1400298ae  nop     dword ptr [rax+rax+00h]
0x1400298b3  movzx   edx, word ptr [r15+2]; TotalLength
0x1400298b8  mov     r9d, 24h ; '$'; DescriptorType
0x1400298be  mov     r8, rbp; StartPosition
0x1400298c1  mov     rcx, r15; DescriptorBuffer
0x1400298c4  mov     rdi, rax
0x1400298c7  call    cs:__imp_USBD_ParseDescriptors
0x1400298ce  nop     dword ptr [rax+rax+00h]
0x1400298d3  test    rax, rax
0x1400298d6  jz      short loc_140029906
0x1400298d8  test    rdi, rdi
0x1400298db  jz      short loc_1400298E2
0x1400298dd  cmp     rax, rdi
0x1400298e0  ja      short loc_140029906
0x1400298e2  cmp     byte ptr [rax], 7
0x1400298e5  jb      short loc_140029906
0x1400298e7  cmp     byte ptr [rax+2], 1
0x1400298eb  jnz     short loc_140029906
0x1400298ed  cmp     byte ptr [rax+4], 2
0x1400298f1  jz      short loc_140029901
0x1400298f3  mov     rbx, rdi
0x1400298f6  test    rdi, rdi
0x1400298f9  jnz     loc_140029876
0x1400298ff  jmp     short loc_140029976
0x140029901  mov     rsi, rbx
0x140029904  jmp     short loc_140029976
0x140029906  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002990d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140029914  jz      short loc_140029976
0x140029916  mov     r9d, 47h ; 'G'
0x14002991c  mov     qword ptr [rsp+78h+InterfaceSubClass], rbx
0x140029921  lea     rax, WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids
0x140029928  mov     dl, 2
0x14002992a  mov     rcx, r14
0x14002992d  mov     qword ptr [rsp+78h+InterfaceClass], rax
0x140029932  lea     r8d, [r9-42h]
0x140029936  call    WPP_RECORDER_SF_q
0x14002993b  jmp     short loc_140029976
0x14002993d  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140029944  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002994b  jz      short loc_140029976
0x14002994d  mov     [rsp+78h+InterfaceProtocol], ecx
0x140029951  lea     rax, WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids
0x140029958  mov     r9d, 46h ; 'F'
0x14002995e  mov     qword ptr [rsp+78h+InterfaceSubClass], rbx
0x140029963  mov     dl, 2
0x140029965  mov     qword ptr [rsp+78h+InterfaceClass], rax
0x14002996a  mov     rcx, r14
0x14002996d  lea     r8d, [r9-41h]
0x140029971  call    WPP_RECORDER_SF_qd
0x140029976  mov     rax, rsi
0x140029979  add     rsp, 40h
0x14002997d  pop     r15
0x14002997f  pop     r14
0x140029981  pop     r12
0x140029983  pop     rdi
0x140029984  pop     rsi
0x140029985  pop     rbp
0x140029986  pop     rbx
0x140029987  retn
```
