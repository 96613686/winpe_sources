# TryGetConfigDescriptor

- ea: `0x14002ca84`
- end: `0x14002ceca`
- name: `TryGetConfigDescriptor`
- size: `1094`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x14002c8e4`

## callees

- `0x14000a6cc`
- `0x14000b0ec`
- `0x14000b1f0`
- `0x14000b40c`
- `0x14000bb28`
- `0x14000d240`
- `0x1400103a4`
- `0x14002ca84`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002cac7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002cea3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002cac7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002cea3`
- `ntoskrnl!ExAllocatePool2` at `0x14002cb33`
- `ntoskrnl!ExAllocatePool2` at `0x14002cc29`
- `ntoskrnl!ExAllocatePool2` at `0x14002cb33`
- `ntoskrnl!ExAllocatePool2` at `0x14002cc29`

## pseudocode

```c
__int64 __fastcall TryGetConfigDescriptor(__int64 a1, unsigned __int8 a2, _BYTE *a3, int *a4, unsigned int *a5)
{
  void *v6; // rcx
  unsigned int *v10; // rax
  USBD_HANDLE v11; // rcx
  NTSTATUS v12; // eax
  unsigned int v13; // edi
  unsigned __int16 *v14; // r14
  int v15; // r9d
  int v16; // edx
  unsigned __int16 *Pool2; // rax
  int v18; // r8d
  int v19; // r9d
  unsigned __int16 v20; // si
  int v21; // eax
  unsigned int v22; // r15d
  __int64 v23; // rax
  int v24; // r8d
  int v25; // r9d
  unsigned __int8 v26; // cl
  int v27; // eax
  int v28; // eax
  int v29; // eax
  int v30; // edx
  int v31; // r8d
  unsigned __int64 v32; // rax
  char v34; // [rsp+28h] [rbp-28h]
  __int128 v35; // [rsp+40h] [rbp-10h] BYREF
  PURB Urb; // [rsp+90h] [rbp+40h] BYREF
  unsigned __int8 v37; // [rsp+98h] [rbp+48h]
  __int64 v38; // [rsp+A0h] [rbp+50h] BYREF

  v37 = a2;
  v6 = *(void **)(a1 + 48);
  Urb = 0;
  v38 = 0;
  if ( v6 )
  {
    ExFreePoolWithTag(v6, 0x43627355u);
    *(_QWORD *)(a1 + 48) = 0;
  }
  v10 = a5;
  v11 = *(USBD_HANDLE *)(a1 + 1344);
  *a3 = 0;
  *a4 = 0;
  *v10 = 0;
  v12 = USBD_UrbAllocate(v11, &Urb);
  v13 = v12;
  if ( v12 < 0 )
  {
    v14 = 0;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_41;
    v15 = 19;
    v34 = v12;
LABEL_6:
    v16 = 2;
LABEL_40:
    WPP_RECORDER_SF_d(
      *(_QWORD *)(a1 + 1368),
      v16,
      8,
      v15,
      (__int64)WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids,
      v34);
    goto LABEL_41;
  }
  Pool2 = (unsigned __int16 *)ExAllocatePool2(64, 9, 1130525525);
  v14 = Pool2;
  if ( !Pool2 )
  {
    v13 = -1073741670;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_41;
    v15 = 20;
    v34 = -102;
    goto LABEL_6;
  }
  Urb->UrbHeader.Function = 11;
  Urb->UrbHeader.Length = 136;
  Urb->UrbControlTransfer.TransferBufferLength = 9;
  Urb->UrbSelectInterface.Interface.InterfaceHandle = Pool2;
  Urb->UrbSelectConfiguration.Interface.InterfaceHandle = 0;
  v20 = 2;
  Urb->UrbControlTransfer.SetupPacket[3] = 2;
  Urb->UrbControlTransfer.SetupPacket[2] = a2;
  Urb->UrbControlDescriptorRequest.LanguageId = 0;
  Urb->UrbControlTransfer.UrbLink = 0;
  v21 = SubmitUrb(a1, (_DWORD)Urb, v18, v19);
  v13 = v21;
  if ( v21 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_41;
    v15 = 21;
    v34 = v21;
    goto LABEL_39;
  }
  v22 = v14[1];
  if ( v22 < 9 || Urb->UrbControlTransfer.TransferBufferLength < 9 )
  {
    v13 = -1073741668;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_41;
    v15 = 22;
    goto LABEL_38;
  }
  v23 = ExAllocatePool2(64, v14[1], 1130525525);
  *(_QWORD *)(a1 + 48) = v23;
  if ( !v23 )
  {
    v16 = -1073741670;
    v13 = -1073741670;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_41;
    v15 = 23;
    v34 = -102;
    goto LABEL_39;
  }
  *a5 = v22;
  Urb->UrbHeader.Function = 11;
  Urb->UrbHeader.Length = 136;
  Urb->UrbControlTransfer.TransferBufferLength = v22;
  Urb->UrbSelectInterface.Interface.InterfaceHandle = *(void **)(a1 + 48);
  v26 = v37;
  Urb->UrbSelectConfiguration.Interface.InterfaceHandle = 0;
  Urb->UrbControlTransfer.SetupPacket[3] = 2;
  Urb->UrbControlTransfer.SetupPacket[2] = v26;
  Urb->UrbControlDescriptorRequest.LanguageId = 0;
  Urb->UrbControlTransfer.UrbLink = 0;
  v27 = SubmitUrb(a1, (_DWORD)Urb, v24, v25);
  v13 = v27;
  if ( v27 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v16) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(a1 + 1368),
        v16,
        8,
        24,
        (__int64)WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids,
        v27);
    }
    *a4 = Urb->UrbHeader.Status;
    goto LABEL_41;
  }
  if ( Urb->UrbControlTransfer.TransferBufferLength < v22 )
  {
    v13 = -1073741668;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_41;
    v15 = 25;
LABEL_38:
    v34 = -100;
LABEL_39:
    LOBYTE(v16) = 2;
    goto LABEL_40;
  }
  v28 = *(_DWORD *)(a1 + 1224);
  if ( (v28 & 4) != 0 )
  {
    v20 = 3;
  }
  else if ( (v28 & 8) != 0 )
  {
    v20 = 1;
  }
  v29 = USBD_ValidateConfigurationDescriptorInternal(*(_QWORD *)(a1 + 48), v22, v20, (unsigned int)&v38);
  *a4 = v29;
  if ( v29 >= 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v32 = *(_QWORD *)(a1 + 48);
      v35 = v32;
      WORD4(v35) = *(_WORD *)(v32 + 2);
      WPP_RECORDER_SF__HEX_(
        *(_QWORD *)(a1 + 1368),
        v30,
        v31,
        27,
        (__int64)WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids,
        (__int64)&v35);
    }
    *(_QWORD *)(a1 + 56) = *(_QWORD *)(a1 + 48);
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_Dd(
        *(_QWORD *)(a1 + 1368),
        v30,
        8,
        26,
        (__int64)WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids,
        v29,
        v38 - *(_BYTE *)(a1 + 48));
    v13 = -1073741668;
    *a3 = 1;
  }
LABEL_41:
  if ( Urb )
    USBD_UrbFree(*(USBD_HANDLE *)(a1 + 1344), Urb);
  if ( v14 )
    ExFreePoolWithTag(v14, 0x43627355u);
  return v13;
}

```

## disassembly

```asm
0x14002ca84  mov     [rsp-38h+arg_18], rbx
0x14002ca89  mov     [rsp-38h+arg_8], dl
0x14002ca8d  push    rbp
0x14002ca8e  push    rsi
0x14002ca8f  push    rdi
0x14002ca90  push    r12
0x14002ca92  push    r13
0x14002ca94  push    r14
0x14002ca96  push    r15
0x14002ca98  mov     rbp, rsp
0x14002ca9b  sub     rsp, 50h
0x14002ca9f  xor     esi, esi
0x14002caa1  mov     rbx, rcx
0x14002caa4  mov     rcx, [rcx+30h]; P
0x14002caa8  mov     r12, r9
0x14002caab  mov     [rbp+Urb], rsi
0x14002caaf  mov     r13, r8
0x14002cab2  mov     [rbp+arg_10], rsi
0x14002cab6  mov     r15b, dl
0x14002cab9  mov     r14d, 43627355h
0x14002cabf  test    rcx, rcx
0x14002cac2  jz      short loc_14002CAD7
0x14002cac4  mov     edx, r14d; Tag
0x14002cac7  call    cs:__imp_ExFreePoolWithTag
0x14002cace  nop     dword ptr [rax+rax+00h]
0x14002cad3  mov     [rbx+30h], rsi
0x14002cad7  mov     rax, [rbp+arg_20]
0x14002cadb  lea     rdx, [rbp+Urb]; Urb
0x14002cadf  mov     rcx, [rbx+540h]; USBDHandle
0x14002cae6  mov     [r13+0], sil
0x14002caea  mov     [r12], esi
0x14002caee  mov     [rax], esi
0x14002caf0  call    USBD_UrbAllocate
0x14002caf5  mov     edi, eax
0x14002caf7  test    eax, eax
0x14002caf9  jns     short loc_14002CB26
0x14002cafb  mov     r14, rsi
0x14002cafe  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002cb05  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002cb0c  jz      loc_14002CE81
0x14002cb12  mov     r9d, 13h
0x14002cb18  mov     dword ptr [rsp+50h+var_28], eax
0x14002cb1c  mov     edx, 2
0x14002cb21  jmp     loc_14002CE63
0x14002cb26  mov     edi, 9
0x14002cb2b  mov     r8d, r14d
0x14002cb2e  mov     edx, edi
0x14002cb30  lea     ecx, [rdi+37h]
0x14002cb33  call    cs:__imp_ExAllocatePool2
0x14002cb3a  nop     dword ptr [rax+rax+00h]
0x14002cb3f  mov     r14, rax
0x14002cb42  test    rax, rax
0x14002cb45  jnz     short loc_14002CB6C
0x14002cb47  mov     edx, 0C000009Ah
0x14002cb4c  mov     edi, edx
0x14002cb4e  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002cb55  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002cb5c  jz      loc_14002CE81
0x14002cb62  lea     r9d, [rax+14h]
0x14002cb66  mov     dword ptr [rsp+50h+var_28], edx
0x14002cb6a  jmp     short loc_14002CB1C
0x14002cb6c  mov     rax, [rbp+Urb]
0x14002cb70  xor     ecx, ecx
0x14002cb72  mov     byte ptr [rsp+50h+var_28], 1
0x14002cb77  mov     word ptr [rax+2], 0Bh
0x14002cb7d  mov     rax, [rbp+Urb]
0x14002cb81  mov     word ptr [rax], 88h
0x14002cb86  mov     rax, [rbp+Urb]
0x14002cb8a  mov     [rax+24h], edi
0x14002cb8d  mov     rax, [rbp+Urb]
0x14002cb91  mov     [rax+28h], r14
0x14002cb95  mov     rax, [rbp+Urb]
0x14002cb99  mov     [rax+30h], rsi
0x14002cb9d  mov     esi, 2
0x14002cba2  mov     rax, [rbp+Urb]
0x14002cba6  mov     [rax+83h], sil
0x14002cbad  mov     rax, [rbp+Urb]
0x14002cbb1  mov     [rax+82h], r15b
0x14002cbb8  mov     rax, [rbp+Urb]
0x14002cbbc  mov     [rax+84h], cx
0x14002cbc3  mov     rax, [rbp+Urb]
0x14002cbc7  mov     [rax+38h], rcx
0x14002cbcb  mov     rcx, rbx
0x14002cbce  mov     rdx, [rbp+Urb]
0x14002cbd2  call    SubmitUrb
0x14002cbd7  mov     edi, eax
0x14002cbd9  test    eax, eax
0x14002cbdb  jns     short loc_14002CBFE
0x14002cbdd  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002cbe4  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002cbeb  jz      loc_14002CE81
0x14002cbf1  lea     r9d, [rsi+13h]
0x14002cbf5  mov     dword ptr [rsp+50h+var_28], eax
0x14002cbf9  jmp     loc_14002CE60
0x14002cbfe  movzx   r15d, word ptr [r14+2]
0x14002cc03  cmp     r15d, 9
0x14002cc07  jb      loc_14002CE41
0x14002cc0d  mov     rax, [rbp+Urb]
0x14002cc11  cmp     dword ptr [rax+24h], 9
0x14002cc15  jb      loc_14002CE41
0x14002cc1b  mov     edx, r15d
0x14002cc1e  mov     ecx, 40h ; '@'
0x14002cc23  mov     r8d, 43627355h
0x14002cc29  call    cs:__imp_ExAllocatePool2
0x14002cc30  nop     dword ptr [rax+rax+00h]
0x14002cc35  mov     [rbx+30h], rax
0x14002cc39  test    rax, rax
0x14002cc3c  jnz     short loc_14002CC66
0x14002cc3e  mov     edx, 0C000009Ah
0x14002cc43  mov     edi, edx
0x14002cc45  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002cc4c  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002cc53  jz      loc_14002CE81
0x14002cc59  lea     r9d, [rax+17h]
0x14002cc5d  mov     dword ptr [rsp+50h+var_28], edx
0x14002cc61  jmp     loc_14002CE60
0x14002cc66  mov     rax, [rbp+arg_20]
0x14002cc6a  mov     byte ptr [rsp+50h+var_28], 1
0x14002cc6f  mov     [rax], r15d
0x14002cc72  mov     rax, [rbp+Urb]
0x14002cc76  mov     word ptr [rax+2], 0Bh
0x14002cc7c  mov     rax, [rbp+Urb]
0x14002cc80  mov     word ptr [rax], 88h
0x14002cc85  mov     rax, [rbp+Urb]
0x14002cc89  mov     [rax+24h], r15d
0x14002cc8d  mov     rcx, [rbx+30h]
0x14002cc91  mov     rax, [rbp+Urb]
0x14002cc95  mov     [rax+28h], rcx
0x14002cc99  mov     rax, [rbp+Urb]
0x14002cc9d  mov     cl, [rbp+arg_8]
0x14002cca0  mov     qword ptr [rax+30h], 0
0x14002cca8  mov     rax, [rbp+Urb]
0x14002ccac  mov     [rax+83h], sil
0x14002ccb3  mov     rax, [rbp+Urb]
0x14002ccb7  mov     [rax+82h], cl
0x14002ccbd  xor     ecx, ecx
0x14002ccbf  mov     rax, [rbp+Urb]
0x14002ccc3  mov     [rax+84h], cx
0x14002ccca  mov     rax, [rbp+Urb]
0x14002ccce  mov     [rax+38h], rcx
0x14002ccd2  mov     rcx, rbx
0x14002ccd5  mov     rdx, [rbp+Urb]
0x14002ccd9  call    SubmitUrb
0x14002ccde  mov     edi, eax
0x14002cce0  test    eax, eax
0x14002cce2  jns     short loc_14002CD2D
0x14002cce4  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002cceb  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002ccf2  jz      short loc_14002CD1D
0x14002ccf4  mov     r9d, 18h
0x14002ccfa  mov     dword ptr [rsp+50h+var_28], eax
0x14002ccfe  lea     rcx, WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids
0x14002cd05  mov     dl, sil
0x14002cd08  mov     [rsp+50h+var_30], rcx
0x14002cd0d  mov     rcx, [rbx+558h]
0x14002cd14  lea     r8d, [r9-10h]
0x14002cd18  call    WPP_RECORDER_SF_d
0x14002cd1d  mov     rax, [rbp+Urb]
0x14002cd21  mov     ecx, [rax+4]
0x14002cd24  mov     [r12], ecx
0x14002cd28  jmp     loc_14002CE81
0x14002cd2d  mov     rax, [rbp+Urb]
0x14002cd31  cmp     [rax+24h], r15d
0x14002cd35  jnb     short loc_14002CD5B
0x14002cd37  mov     edi, 0C000009Ch
0x14002cd3c  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002cd43  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002cd4a  jz      loc_14002CE81
0x14002cd50  mov     r9d, 19h
0x14002cd56  jmp     loc_14002CE5C
0x14002cd5b  mov     eax, [rbx+4C8h]
0x14002cd61  test    al, 4
0x14002cd63  jz      short loc_14002CD6C
0x14002cd65  mov     esi, 3
0x14002cd6a  jmp     short loc_14002CD75
0x14002cd6c  test    al, 8
0x14002cd6e  jz      short loc_14002CD75
0x14002cd70  mov     esi, 1
0x14002cd75  mov     rcx, [rbx+30h]
0x14002cd79  lea     r9, [rbp+arg_10]
0x14002cd7d  movzx   r8d, si
0x14002cd81  mov     edx, r15d
0x14002cd84  call    USBD_ValidateConfigurationDescriptorInternal
0x14002cd89  mov     [r12], eax
0x14002cd8d  test    eax, eax
0x14002cd8f  jns     short loc_14002CDE0
0x14002cd91  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002cd98  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002cd9f  jz      short loc_14002CDD1
0x14002cda1  mov     ecx, dword ptr [rbp+arg_10]
0x14002cda4  mov     r9d, 1Ah
0x14002cdaa  sub     ecx, [rbx+30h]
0x14002cdad  mov     [rsp+50h+var_20], ecx
0x14002cdb1  lea     rcx, WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids
0x14002cdb8  mov     dword ptr [rsp+50h+var_28], eax
0x14002cdbc  mov     [rsp+50h+var_30], rcx
0x14002cdc1  lea     r8d, [r9-12h]
0x14002cdc5  mov     rcx, [rbx+558h]
0x14002cdcc  call    WPP_RECORDER_SF_Dd
0x14002cdd1  mov     edi, 0C000009Ch
0x14002cdd6  mov     byte ptr [r13+0], 1
0x14002cddb  jmp     loc_14002CE81
0x14002cde0  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002cde7  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002cdee  jz      short loc_14002CE37
0x14002cdf0  mov     rax, [rbx+30h]
0x14002cdf4  lea     rcx, WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids
0x14002cdfb  xorps   xmm0, xmm0
0x14002cdfe  mov     r9d, 1Bh
0x14002ce04  movups  [rbp+var_10], xmm0
0x14002ce08  mov     qword ptr [rbp+var_10], rax
0x14002ce0c  movzx   eax, word ptr [rax+2]
0x14002ce10  mov     word ptr [rbp+var_10+8], ax
0x14002ce14  lea     rax, [rbp+var_10]
0x14002ce18  movaps  xmm0, [rbp+var_10]
0x14002ce1c  mov     [rsp+50h+var_28], rax
0x14002ce21  mov     [rsp+50h+var_30], rcx
0x14002ce26  mov     rcx, [rbx+558h]
0x14002ce2d  movdqa  [rbp+var_10], xmm0
0x14002ce32  call    WPP_RECORDER_SF__HEX_
0x14002ce37  mov     rax, [rbx+30h]
0x14002ce3b  mov     [rbx+38h], rax
0x14002ce3f  jmp     short loc_14002CE81
0x14002ce41  mov     edi, 0C000009Ch
0x14002ce46  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002ce4d  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002ce54  jz      short loc_14002CE81
0x14002ce56  mov     r9d, 16h
0x14002ce5c  mov     dword ptr [rsp+50h+var_28], edi
0x14002ce60  mov     dl, sil
0x14002ce63  lea     rcx, WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids
0x14002ce6a  mov     r8d, 8
0x14002ce70  mov     [rsp+50h+var_30], rcx
0x14002ce75  mov     rcx, [rbx+558h]
0x14002ce7c  call    WPP_RECORDER_SF_d
0x14002ce81  mov     rdx, [rbp+Urb]; Urb
0x14002ce85  test    rdx, rdx
0x14002ce88  jz      short loc_14002CE96
0x14002ce8a  mov     rcx, [rbx+540h]; USBDHandle
0x14002ce91  call    USBD_UrbFree
0x14002ce96  test    r14, r14
0x14002ce99  jz      short loc_14002CEAF
0x14002ce9b  mov     edx, 43627355h; Tag
0x14002cea0  mov     rcx, r14; P
0x14002cea3  call    cs:__imp_ExFreePoolWithTag
0x14002ceaa  nop     dword ptr [rax+rax+00h]
0x14002ceaf  mov     rbx, [rsp+50h+arg_18]
0x14002ceb7  mov     eax, edi
0x14002ceb9  add     rsp, 50h
0x14002cebd  pop     r15
0x14002cebf  pop     r14
0x14002cec1  pop     r13
0x14002cec3  pop     r12
0x14002cec5  pop     rdi
0x14002cec6  pop     rsi
0x14002cec7  pop     rbp
0x14002cec8  retn
```
