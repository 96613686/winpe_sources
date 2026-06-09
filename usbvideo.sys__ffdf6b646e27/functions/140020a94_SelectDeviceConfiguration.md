# SelectDeviceConfiguration

- ea: `0x140020a94`
- end: `0x1400211a4`
- name: `SelectDeviceConfiguration`
- size: `1808`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x140015e60`

## callees

- `0x140009b9c`
- `0x14000cb20`
- `0x140019d34`
- `0x14001ab4c`
- `0x14001b15c`
- `0x14001d0cc`
- `0x140020a94`
- `0x140021924`
- `0x140021c54`
- `0x140040a70`
- `0x140040b40`
- `0x140040e40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140020b4e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400210bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400210d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021191`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020b4e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400210bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400210d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021191`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140020ae1`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140021024`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140020ae1`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140021024`
- `ks!KsAddItemToObjectBag` at `0x140020b32`
- `ks!KsAddItemToObjectBag` at `0x140021083`
- `ks!KsAddItemToObjectBag` at `0x140020b32`
- `ks!KsAddItemToObjectBag` at `0x140021083`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x140020b8e`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x140020bbb`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x140020d2f`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x140020db7`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x140020b8e`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x140020bbb`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x140020d2f`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x140020db7`
- `USBD!USBD_CreateConfigurationRequestEx` at `0x140020f0c`
- `USBD!USBD_CreateConfigurationRequestEx` at `0x140020f0c`

## pseudocode

```c
__int64 __fastcall SelectDeviceConfiguration(__int64 a1, struct _USB_CONFIGURATION_DESCRIPTOR *a2)
{
  __int64 v2; // rbx
  SIZE_T v5; // rsi
  PVOID PoolWithTag; // rax
  void *v7; // rdi
  NTSTATUS v8; // edi
  __int64 result; // rax
  int v10; // edi
  PUSB_INTERFACE_DESCRIPTOR v11; // rsi
  unsigned int v12; // r13d
  __int64 VideoSpecificDescriptor; // rax
  unsigned __int8 *v14; // rbp
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // r14
  PUSB_INTERFACE_DESCRIPTOR v18; // rax
  __int64 v19; // rdx
  PUSB_INTERFACE_DESCRIPTOR v20; // rax
  PURB ConfigurationRequest; // rax
  PURB v22; // rsi
  NTSTATUS v23; // ebp
  char v24; // al
  unsigned int i; // r12d
  __int64 v26; // rax
  int v27; // ecx
  unsigned __int16 *v28; // rdx
  PVOID v29; // rax
  PVOID v30; // rbp
  void *v31; // rdx
  void *v32; // rcx
  int StatusInterruptEndpointIndex; // eax
  unsigned __int16 *Src; // [rsp+40h] [rbp-48h]
  SIZE_T Size; // [rsp+A8h] [rbp+20h]

  v2 = *(_QWORD *)(a1 + 16);
  if ( !*(_QWORD *)(v2 + 664) )
  {
    v5 = 16 * (a2->bNumInterfaces + 1LL);
    PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1536, v5, 0x56425355u);
    v7 = PoolWithTag;
    if ( ExPoolZeroingNativelySupported || !PoolWithTag )
    {
      *(_QWORD *)(v2 + 664) = PoolWithTag;
      if ( !PoolWithTag )
        return 3221225626LL;
    }
    else
    {
      memset(PoolWithTag, 0, v5);
      *(_QWORD *)(v2 + 664) = v7;
    }
    v8 = KsAddItemToObjectBag(*(KSOBJECT_BAG *)(a1 + 8), v7, FreeMem);
    if ( v8 < 0 )
    {
      ExFreePoolWithTag(*(PVOID *)(v2 + 664), 0x56425355u);
      result = (unsigned int)v8;
      *(_QWORD *)(v2 + 664) = 0;
      return result;
    }
  }
  v10 = -1;
  if ( !USBD_ParseConfigurationDescriptorEx(a2, a2, -1, -1, 14, 1, -1) )
    return 3221225485LL;
  v11 = USBD_ParseConfigurationDescriptorEx(a2, a2, -1, -1, 14, -1, -1);
  if ( !v11 )
    return 3221225485LL;
  v12 = 0;
  while ( v11 )
  {
    if ( v12 >= a2->bNumInterfaces )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, v2);
      break;
    }
    if ( v11->bInterfaceSubClass == 1 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, v2, v11);
      *(_QWORD *)(*(_QWORD *)(v2 + 664) + 16LL * v12) = v11;
      VideoSpecificDescriptor = GetVideoSpecificDescriptor(a2);
      v14 = (unsigned __int8 *)VideoSpecificDescriptor;
      if ( !VideoSpecificDescriptor )
        return 3221225485LL;
      *(_DWORD *)(v2 + 720) = *(_DWORD *)(VideoSpecificDescriptor + 7);
      v15 = *(unsigned __int8 *)(VideoSpecificDescriptor + 11);
      v16 = *v14;
      if ( v16 != v15 + 12 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_qqddI(WPP_GLOBAL_Control->AttachedDevice, v16, v15 + 12, v2, v14, v16, v15, v15 + 12);
        return 3221225485LL;
      }
      ++v12;
      v17 = 0;
      while ( (unsigned int)v17 < v14[11] )
      {
        v18 = USBD_ParseConfigurationDescriptorEx(a2, a2, v14[v17 + 12], -1, 14, 2, -1);
        if ( !v18 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              WPP_SF_qD(
                WPP_GLOBAL_Control->AttachedDevice,
                29,
                WPP_b11e537a527d30190cd6733beb5dc248_Traceguids,
                v2,
                v17 + 1);
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, v2);
          }
          return 3221225485LL;
        }
        if ( v12 >= a2->bNumInterfaces )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, v2);
          break;
        }
        v19 = v12++;
        v17 = (unsigned int)(v17 + 1);
        *(_QWORD *)(*(_QWORD *)(v2 + 664) + 16 * v19) = v18;
      }
    }
    else if ( v11->bInterfaceSubClass == 2 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, v2, v11);
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        31,
        WPP_b11e537a527d30190cd6733beb5dc248_Traceguids,
        v2,
        v11->bInterfaceSubClass);
    }
    v20 = USBD_ParseConfigurationDescriptorEx(a2, &v11->bLength + v11->bLength, -1, -1, 14, -1, -1);
    v11 = v20;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, v2, v20);
  }
  *(_QWORD *)(*(_QWORD *)(v2 + 664) + 16LL * v12) = 0;
  ConfigurationRequest = USBD_CreateConfigurationRequestEx(a2, *(PUSBD_INTERFACE_LIST_ENTRY *)(v2 + 664));
  v22 = ConfigurationRequest;
  if ( !ConfigurationRequest )
    return 3221225626LL;
  v23 = SubmitUrbToUsbdSynch(a1, ConfigurationRequest);
  if ( v23 < 0 || v22->UrbHeader.Status < 0 )
  {
LABEL_69:
    ExFreePoolWithTag(v22, 0);
    return (unsigned int)v23;
  }
  else
  {
    *(_QWORD *)(v2 + 672) = v22->UrbSelectConfiguration.ConfigurationHandle;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_qDD(
        WPP_GLOBAL_Control->AttachedDevice,
        33,
        WPP_b11e537a527d30190cd6733beb5dc248_Traceguids,
        v2,
        a2->bNumInterfaces,
        v12);
    v24 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)(v2 + 680) + 64LL))(*(_QWORD *)(*(_QWORD *)(v2 + 680) + 8LL));
    *(_DWORD *)(v2 + 704) = v24 != 0 ? 128 : 32;
    *(_DWORD *)(v2 + 708) = v24 != 0 ? 16 : 2;
    for ( i = 0; i < v12; ++i )
    {
      v26 = *(_QWORD *)(v2 + 664);
      v27 = i;
      v28 = *(unsigned __int16 **)(v26 + 16LL * i + 8);
      Src = v28;
      if ( *(_BYTE *)(*(_QWORD *)(v26 + 16LL * i) + 6LL) != 1 )
        v27 = v10;
      Size = *v28;
      v10 = v27;
      v29 = ExAllocatePoolWithTag((POOL_TYPE)1536, Size, 0x56425355u);
      v30 = v29;
      if ( !ExPoolZeroingNativelySupported && v29 )
        memset(v29, 0, Size);
      *(_QWORD *)(*(_QWORD *)(v2 + 664) + 16LL * i + 8) = v30;
      v31 = *(void **)(*(_QWORD *)(v2 + 664) + 16LL * i + 8);
      if ( !v31 )
      {
        v23 = -1073741670;
        goto LABEL_69;
      }
      v23 = KsAddItemToObjectBag(*(KSOBJECT_BAG *)(a1 + 8), v31, FreeMem);
      v32 = *(void **)(*(_QWORD *)(v2 + 664) + 16LL * i + 8);
      if ( v23 < 0 )
      {
        ExFreePoolWithTag(v32, 0x56425355u);
        goto LABEL_69;
      }
      memmove(v32, Src, *Src);
    }
    *(_BYTE *)(v2 + 354) = 0;
    *(_BYTE *)(v2 + 355) = v10;
    StatusInterruptEndpointIndex = GetStatusInterruptEndpointIndex(a2);
    if ( StatusInterruptEndpointIndex < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        34,
        WPP_b11e537a527d30190cd6733beb5dc248_Traceguids,
        v2,
        StatusInterruptEndpointIndex);
    }
    ExFreePoolWithTag(v22, 0);
    return 0;
  }
}

```

## disassembly

```asm
0x140020a94  mov     [rsp+arg_8], rbx
0x140020a99  mov     [rsp+arg_0], rcx
0x140020a9e  push    rbp
0x140020a9f  push    rsi
0x140020aa0  push    rdi
0x140020aa1  push    r12
0x140020aa3  push    r13
0x140020aa5  push    r14
0x140020aa7  push    r15
0x140020aa9  sub     rsp, 50h
0x140020aad  mov     rbx, [rcx+10h]
0x140020ab1  mov     r15, rdx
0x140020ab4  mov     rbp, rcx
0x140020ab7  mov     r14d, 56425355h
0x140020abd  cmp     qword ptr [rbx+298h], 0
0x140020ac5  jnz     loc_140020B6C
0x140020acb  movzx   esi, byte ptr [rdx+4]
0x140020acf  mov     r8d, r14d; Tag
0x140020ad2  inc     rsi
0x140020ad5  mov     ecx, 600h; PoolType
0x140020ada  shl     rsi, 4
0x140020ade  mov     rdx, rsi; NumberOfBytes
0x140020ae1  call    cs:__imp_ExAllocatePoolWithTag
0x140020ae8  nop     dword ptr [rax+rax+00h]
0x140020aed  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140020af4  mov     rdi, rax
0x140020af7  jnz     short loc_140020B14
0x140020af9  test    rax, rax
0x140020afc  jz      short loc_140020B14
0x140020afe  mov     r8, rsi; Size
0x140020b01  xor     edx, edx; Val
0x140020b03  mov     rcx, rax; void *
0x140020b06  call    memset
0x140020b0b  mov     [rbx+298h], rdi
0x140020b12  jmp     short loc_140020B24
0x140020b14  mov     [rbx+298h], rdi
0x140020b1b  test    rdi, rdi
0x140020b1e  jz      loc_140020F20
0x140020b24  mov     rcx, [rbp+8]; ObjectBag
0x140020b28  lea     r8, FreeMem; Free
0x140020b2f  mov     rdx, rdi; Item
0x140020b32  call    cs:__imp_KsAddItemToObjectBag
0x140020b39  nop     dword ptr [rax+rax+00h]
0x140020b3e  mov     edi, eax
0x140020b40  test    eax, eax
0x140020b42  jns     short loc_140020B6C
0x140020b44  mov     rcx, [rbx+298h]; P
0x140020b4b  mov     edx, r14d; Tag
0x140020b4e  call    cs:__imp_ExFreePoolWithTag
0x140020b55  nop     dword ptr [rax+rax+00h]
0x140020b5a  mov     eax, edi
0x140020b5c  mov     qword ptr [rbx+298h], 0
0x140020b67  jmp     loc_140020E71
0x140020b6c  or      edi, 0FFFFFFFFh
0x140020b6f  mov     rdx, r15; StartPosition
0x140020b72  mov     [rsp+88h+InterfaceProtocol], edi; InterfaceProtocol
0x140020b76  mov     r9d, edi; AlternateSetting
0x140020b79  mov     [rsp+88h+InterfaceSubClass], 1; InterfaceSubClass
0x140020b81  mov     r8d, edi; InterfaceNumber
0x140020b84  mov     rcx, r15; ConfigurationDescriptor
0x140020b87  lea     esi, [rdi+0Fh]
0x140020b8a  mov     [rsp+88h+InterfaceClass], esi; InterfaceClass
0x140020b8e  call    cs:__imp_USBD_ParseConfigurationDescriptorEx
0x140020b95  nop     dword ptr [rax+rax+00h]
0x140020b9a  test    rax, rax
0x140020b9d  jz      loc_140020E6C
0x140020ba3  mov     [rsp+88h+InterfaceProtocol], edi; InterfaceProtocol
0x140020ba7  mov     r9d, edi; AlternateSetting
0x140020baa  mov     [rsp+88h+InterfaceSubClass], edi; InterfaceSubClass
0x140020bae  mov     r8d, edi; InterfaceNumber
0x140020bb1  mov     rdx, r15; StartPosition
0x140020bb4  mov     [rsp+88h+InterfaceClass], esi; InterfaceClass
0x140020bb8  mov     rcx, r15; ConfigurationDescriptor
0x140020bbb  call    cs:__imp_USBD_ParseConfigurationDescriptorEx
0x140020bc2  nop     dword ptr [rax+rax+00h]
0x140020bc7  mov     rsi, rax
0x140020bca  test    rax, rax
0x140020bcd  jz      loc_140020E6C
0x140020bd3  xor     r13d, r13d
0x140020bd6  lea     rdx, WPP_GLOBAL_Control
0x140020bdd  test    rsi, rsi
0x140020be0  jz      loc_140020EED
0x140020be6  movzx   eax, byte ptr [r15+4]
0x140020beb  cmp     r13d, eax
0x140020bee  jnb     loc_140020EC3
0x140020bf4  movzx   r8d, byte ptr [rsi+6]
0x140020bf9  mov     ecx, r8d
0x140020bfc  sub     ecx, 1
0x140020bff  jz      short loc_140020C7E
0x140020c01  cmp     ecx, 1
0x140020c04  jz      short loc_140020C42
0x140020c06  mov     rcx, cs:WPP_GLOBAL_Control
0x140020c0d  cmp     rcx, rdx
0x140020c10  jz      loc_140020D98
0x140020c16  cmp     byte ptr [rcx+29h], 5
0x140020c1a  jb      loc_140020D98
0x140020c20  mov     rcx, [rcx+18h]
0x140020c24  mov     edx, 1Fh
0x140020c29  mov     [rsp+88h+InterfaceClass], r8d
0x140020c2e  mov     r9, rbx
0x140020c31  lea     r8, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids
0x140020c38  call    WPP_SF_qD
0x140020c3d  jmp     loc_140020D98
0x140020c42  mov     rcx, cs:WPP_GLOBAL_Control
0x140020c49  cmp     rcx, rdx
0x140020c4c  jz      loc_140020D98
0x140020c52  cmp     byte ptr [rcx+29h], 5
0x140020c56  jb      loc_140020D98
0x140020c5c  mov     rcx, [rcx+18h]
0x140020c60  lea     r8, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids
0x140020c67  mov     edx, 19h
0x140020c6c  mov     qword ptr [rsp+88h+InterfaceClass], rsi
0x140020c71  mov     r9, rbx
0x140020c74  call    WPP_SF_qq
0x140020c79  jmp     loc_140020D98
0x140020c7e  mov     rcx, cs:WPP_GLOBAL_Control
0x140020c85  cmp     rcx, rdx
0x140020c88  jz      short loc_140020CAD
0x140020c8a  cmp     byte ptr [rcx+29h], 5
0x140020c8e  jb      short loc_140020CAD
0x140020c90  mov     rcx, [rcx+18h]
0x140020c94  lea     r8, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids
0x140020c9b  mov     edx, 1Ah
0x140020ca0  mov     qword ptr [rsp+88h+InterfaceClass], rsi
0x140020ca5  mov     r9, rbx
0x140020ca8  call    WPP_SF_qq
0x140020cad  mov     rax, [rbx+298h]
0x140020cb4  mov     r8d, 1
0x140020cba  mov     ecx, r13d
0x140020cbd  mov     rdx, rsi
0x140020cc0  add     rcx, rcx
0x140020cc3  mov     [rax+rcx*8], rsi
0x140020cc7  mov     rcx, r15; DescriptorBuffer
0x140020cca  call    GetVideoSpecificDescriptor
0x140020ccf  mov     rbp, rax
0x140020cd2  test    rax, rax
0x140020cd5  jz      loc_140020E6C
0x140020cdb  mov     ecx, [rax+7]
0x140020cde  mov     [rbx+2D0h], ecx
0x140020ce4  movzx   eax, byte ptr [rax+0Bh]
0x140020ce8  movzx   edx, byte ptr [rbp+0]
0x140020cec  lea     r8, [rax+0Ch]
0x140020cf0  cmp     rdx, r8
0x140020cf3  jnz     loc_140020E8A
0x140020cf9  inc     r13d
0x140020cfc  xor     r14d, r14d
0x140020cff  movzx   eax, byte ptr [rbp+0Bh]
0x140020d03  cmp     r14d, eax
0x140020d06  jnb     loc_140020D98
0x140020d0c  movzx   r8d, byte ptr [r14+rbp+0Ch]; InterfaceNumber
0x140020d12  mov     r9d, edi; AlternateSetting
0x140020d15  mov     [rsp+88h+InterfaceProtocol], edi; InterfaceProtocol
0x140020d19  mov     rdx, r15; StartPosition
0x140020d1c  mov     [rsp+88h+InterfaceSubClass], 2; InterfaceSubClass
0x140020d24  mov     rcx, r15; ConfigurationDescriptor
0x140020d27  mov     [rsp+88h+InterfaceClass], 0Eh; InterfaceClass
0x140020d2f  call    cs:__imp_USBD_ParseConfigurationDescriptorEx
0x140020d36  nop     dword ptr [rax+rax+00h]
0x140020d3b  test    rax, rax
0x140020d3e  jz      loc_140020E09
0x140020d44  movzx   ecx, byte ptr [r15+4]
0x140020d49  cmp     r13d, ecx
0x140020d4c  jnb     short loc_140020D67
0x140020d4e  mov     rcx, [rbx+298h]
0x140020d55  mov     edx, r13d
0x140020d58  inc     r13d
0x140020d5b  add     rdx, rdx
0x140020d5e  inc     r14d
0x140020d61  mov     [rcx+rdx*8], rax
0x140020d65  jmp     short loc_140020CFF
0x140020d67  mov     rcx, cs:WPP_GLOBAL_Control
0x140020d6e  lea     r9, WPP_GLOBAL_Control
0x140020d75  cmp     rcx, r9
0x140020d78  jz      short loc_140020D98
0x140020d7a  cmp     byte ptr [rcx+29h], 3
0x140020d7e  jb      short loc_140020D98
0x140020d80  mov     rcx, [rcx+18h]
0x140020d84  lea     r8, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids
0x140020d8b  mov     edx, 1Ch
0x140020d90  mov     r9, rbx
0x140020d93  call    WPP_SF_q
0x140020d98  movzx   edx, byte ptr [rsi]
0x140020d9b  mov     r9d, edi; AlternateSetting
0x140020d9e  mov     [rsp+88h+InterfaceProtocol], edi; InterfaceProtocol
0x140020da2  add     rdx, rsi; StartPosition
0x140020da5  mov     [rsp+88h+InterfaceSubClass], edi; InterfaceSubClass
0x140020da9  mov     r8d, edi; InterfaceNumber
0x140020dac  mov     rcx, r15; ConfigurationDescriptor
0x140020daf  mov     [rsp+88h+InterfaceClass], 0Eh; InterfaceClass
0x140020db7  call    cs:__imp_USBD_ParseConfigurationDescriptorEx
0x140020dbe  nop     dword ptr [rax+rax+00h]
0x140020dc3  mov     rsi, rax
0x140020dc6  mov     rcx, cs:WPP_GLOBAL_Control
0x140020dcd  lea     rdx, WPP_GLOBAL_Control
0x140020dd4  cmp     rcx, rdx
0x140020dd7  jz      loc_140020BDD
0x140020ddd  cmp     byte ptr [rcx+29h], 5
0x140020de1  jb      loc_140020BDD
0x140020de7  mov     rcx, [rcx+18h]
0x140020deb  lea     r8, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids
0x140020df2  mov     edx, 20h ; ' '
0x140020df7  mov     qword ptr [rsp+88h+InterfaceClass], rax
0x140020dfc  mov     r9, rbx
0x140020dff  call    WPP_SF_qq
0x140020e04  jmp     loc_140020BD6
0x140020e09  mov     rcx, cs:WPP_GLOBAL_Control
0x140020e10  lea     rdi, WPP_GLOBAL_Control
0x140020e17  cmp     rcx, rdi
0x140020e1a  jz      short loc_140020E6C
0x140020e1c  cmp     byte ptr [rcx+29h], 2
0x140020e20  jb      short loc_140020E42
0x140020e22  mov     rcx, [rcx+18h]
0x140020e26  lea     eax, [r14+1]
0x140020e2a  mov     edx, 1Dh
0x140020e2f  mov     [rsp+88h+InterfaceClass], eax
0x140020e33  mov     r9, rbx
0x140020e36  lea     r8, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids
0x140020e3d  call    WPP_SF_qD
0x140020e42  mov     rcx, cs:WPP_GLOBAL_Control
0x140020e49  cmp     rcx, rdi
0x140020e4c  jz      short loc_140020E6C
0x140020e4e  cmp     byte ptr [rcx+29h], 2
0x140020e52  jb      short loc_140020E6C
0x140020e54  mov     rcx, [rcx+18h]
0x140020e58  lea     r8, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids
0x140020e5f  mov     edx, 1Eh
0x140020e64  mov     r9, rbx
0x140020e67  call    WPP_SF_q
0x140020e6c  mov     eax, 0C000000Dh
0x140020e71  mov     rbx, [rsp+88h+arg_8]
0x140020e79  add     rsp, 50h
0x140020e7d  pop     r15
0x140020e7f  pop     r14
0x140020e81  pop     r13
0x140020e83  pop     r12
0x140020e85  pop     rdi
0x140020e86  pop     rsi
0x140020e87  pop     rbp
0x140020e88  retn
0x140020e8a  mov     rcx, cs:WPP_GLOBAL_Control
0x140020e91  lea     r9, WPP_GLOBAL_Control
0x140020e98  cmp     rcx, r9
0x140020e9b  jz      short loc_140020E6C
0x140020e9d  cmp     byte ptr [rcx+29h], 2
0x140020ea1  jb      short loc_140020E6C
0x140020ea3  mov     rcx, [rcx+18h]
0x140020ea7  mov     r9, rbx
0x140020eaa  mov     [rsp+88h+var_50], r8
0x140020eaf  mov     [rsp+88h+InterfaceProtocol], eax
0x140020eb3  mov     [rsp+88h+InterfaceSubClass], edx
0x140020eb7  mov     qword ptr [rsp+88h+InterfaceClass], rbp
0x140020ebc  call    WPP_SF_qqddI
0x140020ec1  jmp     short loc_140020E6C
0x140020ec3  mov     rcx, cs:WPP_GLOBAL_Control
0x140020eca  cmp     rcx, rdx
0x140020ecd  jz      short loc_140020EED
0x140020ecf  cmp     byte ptr [rcx+29h], 3
0x140020ed3  jb      short loc_140020EED
0x140020ed5  mov     rcx, [rcx+18h]
0x140020ed9  lea     r8, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids
0x140020ee0  mov     edx, 18h
0x140020ee5  mov     r9, rbx
0x140020ee8  call    WPP_SF_q
0x140020eed  mov     rax, [rbx+298h]
0x140020ef4  mov     ecx, r13d
0x140020ef7  add     rcx, rcx
0x140020efa  mov     qword ptr [rax+rcx*8], 0
0x140020f02  mov     rcx, r15; ConfigurationDescriptor
0x140020f05  mov     rdx, [rbx+298h]; InterfaceList
0x140020f0c  call    cs:__imp_USBD_CreateConfigurationRequestEx
0x140020f13  nop     dword ptr [rax+rax+00h]
0x140020f18  mov     rsi, rax
0x140020f1b  test    rax, rax
0x140020f1e  jnz     short loc_140020F2A
0x140020f20  mov     eax, 0C000009Ah
0x140020f25  jmp     loc_140020E71
0x140020f2a  mov     rcx, [rsp+88h+arg_0]
0x140020f32  mov     rdx, rsi
0x140020f35  call    SubmitUrbToUsbdSynch
0x140020f3a  mov     ebp, eax
0x140020f3c  test    eax, eax
0x140020f3e  js      loc_1400210CF
0x140020f44  cmp     dword ptr [rsi+4], 0
0x140020f48  jl      loc_1400210CF
0x140020f4e  mov     rax, [rsi+20h]
0x140020f52  mov     [rbx+2A0h], rax
0x140020f59  mov     rcx, cs:WPP_GLOBAL_Control
0x140020f60  lea     rbp, WPP_GLOBAL_Control
0x140020f67  cmp     rcx, rbp
0x140020f6a  jz      short loc_140020F98
0x140020f6c  cmp     byte ptr [rcx+29h], 5
0x140020f70  jb      short loc_140020F98
0x140020f72  movzx   eax, byte ptr [r15+4]
0x140020f77  lea     r8, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids
0x140020f7e  mov     rcx, [rcx+18h]
0x140020f82  mov     edx, 21h ; '!'
0x140020f87  mov     [rsp+88h+InterfaceSubClass], r13d
0x140020f8c  mov     r9, rbx
0x140020f8f  mov     [rsp+88h+InterfaceClass], eax
0x140020f93  call    WPP_SF_qDD
  ... truncated ...
```
