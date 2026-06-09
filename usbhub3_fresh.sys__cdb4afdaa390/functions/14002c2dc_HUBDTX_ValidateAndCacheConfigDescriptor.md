# HUBDTX_ValidateAndCacheConfigDescriptor

- ea: `0x14002c2dc`
- end: `0x14002c903`
- name: `HUBDTX_ValidateAndCacheConfigDescriptor`
- size: `1575`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x140024930`

## callees

- `0x1400025a4`
- `0x1400067ac`
- `0x1400083b4`
- `0x140029828`
- `0x14002c2dc`
- `0x14003bd60`
- `0x14003cce8`
- `0x140045570`
- `0x140045640`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14002c649`
- `ntoskrnl!ExAllocatePool2` at `0x14002c649`

## pseudocode

```c
__int64 __fastcall HUBDTX_ValidateAndCacheConfigDescriptor(__int64 a1)
{
  struct _USB_CONFIGURATION_DESCRIPTOR *v1; // rsi
  __int64 v3; // rax
  __int64 v4; // r9
  int v5; // ecx
  bool v6; // zf
  unsigned int v7; // edx
  __int64 v8; // r9
  unsigned __int8 *v9; // rdx
  __int64 v10; // rcx
  int v11; // r9d
  __int16 v12; // ax
  int wTotalLength; // edx
  char v14; // al
  struct _USB_CONFIGURATION_DESCRIPTOR *v15; // rcx
  struct _USB_CONFIGURATION_DESCRIPTOR *v16; // rdx
  __int64 bLength; // r9
  unsigned __int64 v18; // rax
  unsigned __int8 bDescriptorType; // r8
  int v20; // r9d
  char v21; // al
  void *Pool2; // rax
  unsigned __int8 *v23; // rax
  __int64 v24; // r8
  PUSB_INTERFACE_DESCRIPTOR MidiInterfaceDescriptor; // rax
  int v26; // eax
  unsigned __int8 *v27; // rax
  __int64 v28; // rax
  unsigned int v29; // edi
  _WORD v31[2]; // [rsp+50h] [rbp-19h] BYREF
  int v32; // [rsp+54h] [rbp-15h]
  __int64 v33; // [rsp+58h] [rbp-11h]
  int v34; // [rsp+60h] [rbp-9h]
  int v35; // [rsp+64h] [rbp-5h]
  void (__fastcall *v36)(__int64, ULONG, __int64, __int64); // [rsp+68h] [rbp-1h]
  void (__fastcall *v37)(__int64, ULONG, __int64, __int64); // [rsp+70h] [rbp+7h]
  __int64 v38; // [rsp+78h] [rbp+Fh]
  _BOOL8 v39; // [rsp+80h] [rbp+17h]
  char v40; // [rsp+D0h] [rbp+67h] BYREF

  v1 = *(struct _USB_CONFIGURATION_DESCRIPTOR **)(a1 + 2024);
  v40 = 0;
  if ( !v1 )
    v1 = (struct _USB_CONFIGURATION_DESCRIPTOR *)(a1 + 1740);
  v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         WdfDriverGlobals->Driver,
         off_14006B2C0);
  v4 = *(_QWORD *)(a1 + 8);
  v38 = a1;
  v33 = 0;
  v31[1] = 0;
  v35 = 0;
  v31[0] = *(_WORD *)(a1 + 1998);
  v32 = *(_DWORD *)(a1 + 172);
  v5 = *(_DWORD *)(v3 + 4);
  v39 = 0;
  *(_WORD *)((char *)&v33 + 5) = (v5 & 0x20) != 0;
  HIBYTE(v33) = (v5 & 0x2000) != 0;
  v6 = (*(_DWORD *)(a1 + 1652) & 0x200000) == 0;
  v7 = *(_DWORD *)(a1 + 264);
  BYTE4(v33) = (v5 & 0x4000) != 0;
  LODWORD(v3) = *(_DWORD *)(v4 + 220);
  v8 = *(_QWORD *)(v4 + 1432);
  v34 = v3;
  v36 = HUBMISC_LogDescriptorValidationErrorForDevice;
  v37 = HUBMISC_LogDescriptorValidationWarningForDevice;
  v39 = !v6;
  if ( !HUBDESC_ValidateConfigurationDescriptorSet((__int64)v1, v7, (__int64)v31, v8, &v40) )
  {
    *(_DWORD *)(a1 + 2440) = 1073807364;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_88;
    v11 = 72;
    goto LABEL_87;
  }
  v12 = *(_WORD *)(a1 + 1742);
  if ( v1->wTotalLength != v12 )
  {
    *(_DWORD *)(a1 + 2440) = 1073807364;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      wTotalLength = v1->wTotalLength;
      LOBYTE(wTotalLength) = 2;
      WPP_RECORDER_SF_dD(
        *(_QWORD *)(*(_QWORD *)(a1 + 8) + 1432LL),
        wTotalLength,
        5,
        73,
        (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids,
        v1->wTotalLength,
        v12);
    }
    ((void (__fastcall *)(__int64, __int64))v36)(v38, 61);
    goto LABEL_88;
  }
  _InterlockedOr((volatile signed __int32 *)(a1 + 1644), 0x2000u);
  if ( v40 )
    _InterlockedOr((volatile signed __int32 *)(a1 + 1648), 0x40u);
  if ( *(_BYTE *)(a1 + 2013) > 1u )
    _InterlockedOr((volatile signed __int32 *)(a1 + 1648), 0x80u);
  if ( *(_BYTE *)(a1 + 2013) > 1u && v1->bNumInterfaces > 1u )
  {
    v14 = *(_BYTE *)(a1 + 2000);
    if ( !v14 || v14 == -17 && *(_BYTE *)(a1 + 2001) == 2 && *(_BYTE *)(a1 + 2002) == 1 )
    {
      v15 = v1 + 1;
      v16 = (struct _USB_CONFIGURATION_DESCRIPTOR *)((char *)v1 + v1->wTotalLength);
      while ( v15 < v16 )
      {
        bLength = v15->bLength;
        if ( !(_BYTE)bLength )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            break;
          v20 = 74;
          goto LABEL_43;
        }
        v18 = (char *)v16 - (char *)v15;
        if ( (unsigned __int64)((char *)v16 - (char *)v15) < 2 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            break;
          v20 = 75;
          goto LABEL_43;
        }
        bDescriptorType = v15->bDescriptorType;
        if ( bDescriptorType == 11 )
        {
          if ( v18 < 5 )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              break;
            v20 = 76;
LABEL_43:
            LOBYTE(v16) = 2;
            WPP_RECORDER_SF_(
              *(_QWORD *)(*(_QWORD *)(a1 + 8) + 1432LL),
              (_DWORD)v16,
              5,
              v20,
              (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids);
            break;
          }
          if ( v15->bNumInterfaces == 1 )
            goto LABEL_26;
        }
        else
        {
          if ( bDescriptorType != 4 )
            goto LABEL_32;
          if ( v18 < 6 )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              break;
            v20 = 77;
            goto LABEL_43;
          }
        }
        if ( bDescriptorType == 4 && v15->bConfigurationValue == 1 )
        {
LABEL_26:
          _InterlockedOr((volatile signed __int32 *)(a1 + 1640), 4u);
          if ( *(_BYTE *)(*(_QWORD *)a1 + 201LL) )
            _InterlockedOr((volatile signed __int32 *)(a1 + 1652), 0x2000000u);
          break;
        }
LABEL_32:
        v15 = (struct _USB_CONFIGURATION_DESCRIPTOR *)((char *)v15 + bLength);
      }
    }
  }
  if ( (*(_DWORD *)(a1 + 1640) & 4) == 0 && *(_BYTE *)(a1 + 2013) == 1 && v1->bNumInterfaces > 1u )
  {
    v21 = *(_BYTE *)(a1 + 2000);
    if ( !v21 || v21 == -17 && *(_BYTE *)(a1 + 2001) == 2 && *(_BYTE *)(a1 + 2002) == 1 )
      _InterlockedOr((volatile signed __int32 *)(a1 + 1640), 4u);
  }
  if ( !*(_QWORD *)(a1 + 2024) )
  {
    Pool2 = (void *)ExAllocatePool2(64, v1->wTotalLength, 1681082453);
    *(_QWORD *)(a1 + 2024) = Pool2;
    if ( !Pool2 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_88;
      v11 = 78;
      goto LABEL_87;
    }
    memmove(Pool2, v1, v1->wTotalLength);
    v1 = *(struct _USB_CONFIGURATION_DESCRIPTOR **)(a1 + 2024);
  }
  v23 = HUBDESC_ParseConfigurationDescriptor(
          (__int64)v1,
          &v1->bLength,
          -1,
          -1,
          -1,
          -1,
          -1,
          0,
          *(_QWORD *)(*(_QWORD *)(a1 + 8) + 1432LL));
  *(_QWORD *)(a1 + 2016) = v23;
  v9 = v23;
  if ( v23 )
  {
    LOBYTE(v10) = v23[5];
    if ( (_BYTE)v10 == 9 )
    {
      _InterlockedOr((volatile signed __int32 *)(a1 + 1640), 2u);
      _InterlockedOr((volatile signed __int32 *)(a1 + 1644), 0x800u);
    }
    else if ( (*(_DWORD *)(a1 + 1640) & 4) == 0 )
    {
      if ( (_BYTE)v10 == 1 )
      {
        MidiInterfaceDescriptor = FindMidiInterfaceDescriptor(v1, v23, v24, *(_QWORD *)(*(_QWORD *)(a1 + 8) + 1432LL));
        if ( MidiInterfaceDescriptor )
          *(_QWORD *)(a1 + 2016) = MidiInterfaceDescriptor;
      }
      else if ( *(_WORD *)(a1 + 1998) > 0x200u && (*(_DWORD *)(a1 + 1652) & 0x800) == 0 )
      {
        v26 = *(_DWORD *)(a1 + 172);
        if ( v26 == 3 )
        {
          v10 = *(unsigned int *)(*(_QWORD *)a1 + 776LL);
          if ( (v10 & 1) == 0 )
            goto LABEL_72;
        }
        else if ( v26 != 2 )
        {
          goto LABEL_72;
        }
        v27 = HUBDESC_ParseConfigurationDescriptor(
                (__int64)v1,
                v9,
                v9[2],
                -1,
                8,
                6,
                98,
                0,
                *(_QWORD *)(*(_QWORD *)(a1 + 8) + 1432LL));
        if ( v27 )
        {
          _InterlockedOr((volatile signed __int32 *)(a1 + 1644), 0x800u);
          *(_QWORD *)(a1 + 2016) = v27;
        }
      }
    }
LABEL_72:
    if ( *(_BYTE *)(*(_QWORD *)a1 + 201LL) )
    {
      if ( (*(_DWORD *)(a1 + 1640) & 4) == 0 )
      {
        v28 = *(_QWORD *)(a1 + 2016);
        if ( *(_BYTE *)(v28 + 5) == 1 && !*(_BYTE *)(v28 + 7) )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v9) = 2;
            WPP_RECORDER_SF_(
              *(_QWORD *)(*(_QWORD *)(a1 + 8) + 1432LL),
              (_DWORD)v9,
              5,
              79,
              (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids);
          }
          *(_QWORD *)(a1 + 2016) = 0;
          *(_DWORD *)(a1 + 2440) = 1073807393;
          goto LABEL_88;
        }
      }
    }
  }
  v29 = 4077;
  if ( (*(_BYTE *)(a1 + 1640) & 6) == 6 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v9) = 2;
    WPP_RECORDER_SF_(
      *(_QWORD *)(*(_QWORD *)(a1 + 8) + 1432LL),
      (_DWORD)v9,
      5,
      80,
      (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids);
  }
  if ( (v1->bmAttributes & 0x20) != 0 )
    _InterlockedOr((volatile signed __int32 *)(a1 + 1640), 0x100u);
  if ( (*(_DWORD *)(a1 + 1652) & 0x100000) != 0 )
  {
    *(_DWORD *)(a1 + 2440) = 1073807387;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_88;
    v11 = 81;
LABEL_87:
    LOBYTE(v9) = 2;
    WPP_RECORDER_SF_(
      *(_QWORD *)(*(_QWORD *)(a1 + 8) + 1432LL),
      (_DWORD)v9,
      5,
      v11,
      (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids);
LABEL_88:
    v29 = 4065;
    if ( (byte_14006ED41 & 1) != 0 )
      McTemplateK0p_EtwWriteTransfer(
        v10,
        (const EVENT_DESCRIPTOR *)USBHUB3_ETW_EVENT_INVALID_CONFIGURATION_DESCRIPTOR,
        (const GUID *)(a1 + 1524),
        *(_QWORD *)(a1 + 24));
  }
  return v29;
}

```

## disassembly

```asm
0x14002c2dc  push    rbp
0x14002c2de  push    rbx
0x14002c2df  push    rsi
0x14002c2e0  push    rdi
0x14002c2e1  push    r12
0x14002c2e3  push    r14
0x14002c2e5  lea     rbp, [rsp-2Fh]
0x14002c2ea  sub     rsp, 98h
0x14002c2f1  mov     rsi, [rcx+7E8h]
0x14002c2f8  mov     rbx, rcx
0x14002c2fb  mov     [rbp+57h+arg_0], 0
0x14002c2ff  test    rsi, rsi
0x14002c302  jnz     short loc_14002C30B
0x14002c304  lea     rsi, [rcx+6CCh]
0x14002c30b  mov     rax, cs:WdfFunctions_01015
0x14002c312  mov     rcx, cs:WdfDriverGlobals
0x14002c319  mov     r8, cs:off_14006B2C0
0x14002c320  mov     rax, [rax+650h]
0x14002c327  mov     rdx, [rcx]
0x14002c32a  call    _guard_dispatch_icall
0x14002c32f  mov     r9, [rbx+8]
0x14002c333  lea     r8, [rbp+57h+var_70]
0x14002c337  xor     ecx, ecx
0x14002c339  mov     [rbp+57h+var_48], rbx
0x14002c33d  mov     [rbp+57h+var_68], rcx
0x14002c341  xor     edx, edx
0x14002c343  mov     [rbp+57h+var_6E], cx
0x14002c347  mov     r14d, 2000h
0x14002c34d  mov     [rbp+57h+var_5C], ecx
0x14002c350  movzx   ecx, word ptr [rbx+7CEh]
0x14002c357  mov     [rbp+57h+var_70], cx
0x14002c35b  lea     edi, [rdx+1]
0x14002c35e  mov     ecx, [rbx+0ACh]
0x14002c364  mov     [rbp+57h+var_6C], ecx
0x14002c367  mov     ecx, [rax+4]
0x14002c36a  test    cl, 20h
0x14002c36d  movzx   eax, byte ptr [rbp+57h+var_68+5]
0x14002c371  cmovnz  eax, edi
0x14002c374  mov     [rbp+57h+var_40], rdx
0x14002c378  mov     byte ptr [rbp+57h+var_68+5], al
0x14002c37b  test    r14d, ecx
0x14002c37e  movzx   eax, byte ptr [rbp+57h+var_68+7]
0x14002c382  cmovnz  eax, edi
0x14002c385  bt      ecx, 0Eh
0x14002c389  mov     byte ptr [rbp+57h+var_68+7], al
0x14002c38c  movzx   eax, byte ptr [rbp+57h+var_68+4]
0x14002c390  cmovb   eax, edi
0x14002c393  movzx   ecx, dl
0x14002c396  test    dword ptr [rbx+674h], 200000h
0x14002c3a0  mov     edx, [rbx+108h]
0x14002c3a6  mov     byte ptr [rbp+57h+var_68+4], al
0x14002c3a9  cmovnz  ecx, edi
0x14002c3ac  mov     eax, [r9+0DCh]
0x14002c3b3  mov     r9, [r9+598h]
0x14002c3ba  mov     [rbp+57h+var_60], eax
0x14002c3bd  lea     rax, HUBMISC_LogDescriptorValidationErrorForDevice
0x14002c3c4  mov     [rbp+57h+var_58], rax
0x14002c3c8  lea     rax, HUBMISC_LogDescriptorValidationWarningForDevice
0x14002c3cf  mov     [rbp+57h+var_50], rax
0x14002c3d3  lea     rax, [rbp+57h+arg_0]
0x14002c3d7  mov     byte ptr [rbp+57h+var_40], cl
0x14002c3da  mov     rcx, rsi
0x14002c3dd  mov     [rsp+0C0h+var_A0], rax
0x14002c3e2  call    HUBDESC_ValidateConfigurationDescriptorSet
0x14002c3e7  test    al, al
0x14002c3e9  jnz     short loc_14002C419
0x14002c3eb  mov     dword ptr [rbx+988h], 40010004h
0x14002c3f5  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002c3fc  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14002c403  jz      loc_14002C8CB
0x14002c409  lea     r9d, [rdi+47h]
0x14002c40d  lea     r12, WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids
0x14002c414  jmp     loc_14002C8AE
0x14002c419  movzx   eax, word ptr [rbx+6CEh]
0x14002c420  cmp     [rsi+2], ax
0x14002c424  jz      short loc_14002C48B
0x14002c426  mov     dword ptr [rbx+988h], 40010004h
0x14002c430  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002c437  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14002c43e  jz      short loc_14002C474
0x14002c440  movzx   edx, word ptr [rsi+2]
0x14002c444  lea     r12, WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids
0x14002c44b  mov     rcx, [rbx+8]
0x14002c44f  mov     r9d, 49h ; 'I'
0x14002c455  mov     [rsp+0C0h+var_90], eax
0x14002c459  mov     [rsp+0C0h+var_98], edx
0x14002c45d  mov     dl, 2
0x14002c45f  mov     [rsp+0C0h+var_A0], r12
0x14002c464  mov     rcx, [rcx+598h]
0x14002c46b  lea     r8d, [r9-44h]
0x14002c46f  call    WPP_RECORDER_SF_dD
0x14002c474  mov     rcx, [rbp+57h+var_48]
0x14002c478  mov     edx, 3Dh ; '='
0x14002c47d  mov     rax, [rbp+57h+var_58]
0x14002c481  call    _guard_dispatch_icall
0x14002c486  jmp     loc_14002C8CB
0x14002c48b  lock or [rbx+66Ch], r14d
0x14002c493  cmp     [rbp+57h+arg_0], 0
0x14002c497  jz      short loc_14002C4A1
0x14002c499  lock or dword ptr [rbx+670h], 40h
0x14002c4a1  cmp     [rbx+7DDh], dil
0x14002c4a8  jbe     short loc_14002C4B5
0x14002c4aa  lock or dword ptr [rbx+670h], 80h
0x14002c4b5  lea     r14, WPP_RECORDER_INITIALIZED
0x14002c4bc  lea     r12, WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids
0x14002c4c3  cmp     [rbx+7DDh], dil
0x14002c4ca  jbe     loc_14002C5EF
0x14002c4d0  cmp     [rsi+4], dil
0x14002c4d4  jbe     loc_14002C5EF
0x14002c4da  mov     al, [rbx+7D0h]
0x14002c4e0  test    al, al
0x14002c4e2  jz      short loc_14002C506
0x14002c4e4  cmp     al, 0EFh
0x14002c4e6  jnz     loc_14002C5EF
0x14002c4ec  cmp     byte ptr [rbx+7D1h], 2
0x14002c4f3  jnz     loc_14002C5EF
0x14002c4f9  cmp     [rbx+7D2h], dil
0x14002c500  jnz     loc_14002C5EF
0x14002c506  movzx   edx, word ptr [rsi+2]
0x14002c50a  lea     rcx, [rsi+9]
0x14002c50e  add     rdx, rsi
0x14002c511  jmp     short loc_14002C589
0x14002c513  movzx   r9d, byte ptr [rcx]
0x14002c517  test    r9b, r9b
0x14002c51a  jz      loc_14002C5C3
0x14002c520  mov     rax, rdx
0x14002c523  sub     rax, rcx
0x14002c526  cmp     rax, 2
0x14002c52a  jb      loc_14002C5B2
0x14002c530  mov     r8b, [rcx+1]
0x14002c534  cmp     r8b, 0Bh
0x14002c538  jnz     short loc_14002C56E
0x14002c53a  cmp     rax, 5
0x14002c53e  jb      short loc_14002C590
0x14002c540  cmp     [rcx+4], dil
0x14002c544  jnz     short loc_14002C57A
0x14002c546  lock or dword ptr [rbx+668h], 4
0x14002c54e  mov     rax, [rbx]
0x14002c551  cmp     byte ptr [rax+0C9h], 0
0x14002c558  jz      loc_14002C5EF
0x14002c55e  lock or dword ptr [rbx+674h], 2000000h
0x14002c569  jmp     loc_14002C5EF
0x14002c56e  cmp     r8b, 4
0x14002c572  jnz     short loc_14002C586
0x14002c574  cmp     rax, 6
0x14002c578  jb      short loc_14002C5A1
0x14002c57a  cmp     r8b, 4
0x14002c57e  jnz     short loc_14002C586
0x14002c580  cmp     [rcx+5], dil
0x14002c584  jz      short loc_14002C546
0x14002c586  add     rcx, r9
0x14002c589  cmp     rcx, rdx
0x14002c58c  jb      short loc_14002C513
0x14002c58e  jmp     short loc_14002C5EF
0x14002c590  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14002c597  jz      short loc_14002C5EF
0x14002c599  mov     r9d, 4Ch ; 'L'
0x14002c59f  jmp     short loc_14002C5D2
0x14002c5a1  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14002c5a8  jz      short loc_14002C5EF
0x14002c5aa  mov     r9d, 4Dh ; 'M'
0x14002c5b0  jmp     short loc_14002C5D2
0x14002c5b2  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14002c5b9  jz      short loc_14002C5EF
0x14002c5bb  mov     r9d, 4Bh ; 'K'
0x14002c5c1  jmp     short loc_14002C5D2
0x14002c5c3  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14002c5ca  jz      short loc_14002C5EF
0x14002c5cc  mov     r9d, 4Ah ; 'J'
0x14002c5d2  mov     rcx, [rbx+8]
0x14002c5d6  mov     r8d, 5
0x14002c5dc  mov     dl, 2
0x14002c5de  mov     [rsp+0C0h+var_A0], r12
0x14002c5e3  mov     rcx, [rcx+598h]
0x14002c5ea  call    WPP_RECORDER_SF_
0x14002c5ef  mov     eax, [rbx+668h]
0x14002c5f5  test    al, 4
0x14002c5f7  jnz     short loc_14002C630
0x14002c5f9  cmp     [rbx+7DDh], dil
0x14002c600  jnz     short loc_14002C630
0x14002c602  cmp     [rsi+4], dil
0x14002c606  jbe     short loc_14002C630
0x14002c608  mov     al, [rbx+7D0h]
0x14002c60e  test    al, al
0x14002c610  jz      short loc_14002C628
0x14002c612  cmp     al, 0EFh
0x14002c614  jnz     short loc_14002C630
0x14002c616  cmp     byte ptr [rbx+7D1h], 2
0x14002c61d  jnz     short loc_14002C630
0x14002c61f  cmp     [rbx+7D2h], dil
0x14002c626  jnz     short loc_14002C630
0x14002c628  lock or dword ptr [rbx+668h], 4
0x14002c630  cmp     qword ptr [rbx+7E8h], 0
0x14002c638  jnz     short loc_14002C68E
0x14002c63a  movzx   edx, word ptr [rsi+2]
0x14002c63e  mov     ecx, 40h ; '@'
0x14002c643  mov     r8d, 64334855h
0x14002c649  call    cs:__imp_ExAllocatePool2
0x14002c650  nop     dword ptr [rax+rax+00h]
0x14002c655  mov     [rbx+7E8h], rax
0x14002c65c  test    rax, rax
0x14002c65f  jnz     short loc_14002C677
0x14002c661  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14002c668  jz      loc_14002C8CB
0x14002c66e  lea     r9d, [rax+4Eh]
0x14002c672  jmp     loc_14002C8AE
0x14002c677  movzx   r8d, word ptr [rsi+2]; Size
0x14002c67c  mov     rdx, rsi; Src
0x14002c67f  mov     rcx, rax; void *
0x14002c682  call    memmove
0x14002c687  mov     rsi, [rbx+7E8h]
0x14002c68e  mov     rax, [rbx+8]
0x14002c692  mov     rdx, rsi
0x14002c695  mov     rcx, [rax+598h]
0x14002c69c  or      eax, 0FFFFFFFFh
0x14002c69f  mov     [rsp+0C0h+var_80], rcx
0x14002c6a4  mov     r9d, eax
0x14002c6a7  mov     [rsp+0C0h+var_88], 0
0x14002c6b0  mov     r8d, eax
0x14002c6b3  mov     [rsp+0C0h+var_90], eax
0x14002c6b7  mov     rcx, rsi
0x14002c6ba  mov     [rsp+0C0h+var_98], eax
0x14002c6be  mov     dword ptr [rsp+0C0h+var_A0], eax
0x14002c6c2  call    HUBDESC_ParseConfigurationDescriptor
0x14002c6c7  mov     [rbx+7E0h], rax
0x14002c6ce  mov     rdx, rax
0x14002c6d1  test    rax, rax
0x14002c6d4  jz      loc_14002C83C
0x14002c6da  mov     cl, [rax+5]
0x14002c6dd  cmp     cl, 9
0x14002c6e0  jnz     short loc_14002C6FB
0x14002c6e2  lock or dword ptr [rbx+668h], 2
0x14002c6ea  mov     edi, 800h
0x14002c6ef  lock or [rbx+66Ch], edi
0x14002c6f6  jmp     loc_14002C7CA
0x14002c6fb  mov     eax, [rbx+668h]
0x14002c701  test    al, 4
0x14002c703  jnz     loc_14002C7CF
0x14002c709  cmp     cl, dil
0x14002c70c  jnz     short loc_14002C736
0x14002c70e  mov     r9, [rbx+8]
0x14002c712  mov     rcx, rsi; DescriptorBuffer
0x14002c715  mov     r9, [r9+598h]
0x14002c71c  call    FindMidiInterfaceDescriptor
0x14002c721  test    rax, rax
0x14002c724  jz      loc_14002C7CF
0x14002c72a  mov     [rbx+7E0h], rax
0x14002c731  jmp     loc_14002C7CF
0x14002c736  mov     eax, 200h
0x14002c73b  cmp     [rbx+7CEh], ax
0x14002c742  jbe     loc_14002C7CF
0x14002c748  mov     edi, 800h
0x14002c74d  test    [rbx+674h], edi
0x14002c753  jnz     short loc_14002C7CA
0x14002c755  mov     eax, [rbx+0ACh]
0x14002c75b  cmp     eax, 3
0x14002c75e  jnz     short loc_14002C770
0x14002c760  mov     rax, [rbx]
0x14002c763  mov     ecx, [rax+308h]
0x14002c769  test    cl, 1
0x14002c76c  jnz     short loc_14002C775
0x14002c76e  jmp     short loc_14002C7CA
0x14002c770  cmp     eax, 2
0x14002c773  jnz     short loc_14002C7CA
0x14002c775  mov     rax, [rbx+8]
0x14002c779  or      r9d, 0FFFFFFFFh
0x14002c77d  movzx   r8d, byte ptr [rdx+2]
0x14002c782  mov     rcx, rsi
0x14002c785  mov     rax, [rax+598h]
0x14002c78c  mov     [rsp+0C0h+var_80], rax
0x14002c791  mov     [rsp+0C0h+var_88], 0
0x14002c79a  mov     [rsp+0C0h+var_90], 62h ; 'b'
0x14002c7a2  mov     [rsp+0C0h+var_98], 6
0x14002c7aa  mov     dword ptr [rsp+0C0h+var_A0], 8
0x14002c7b2  call    HUBDESC_ParseConfigurationDescriptor
0x14002c7b7  test    rax, rax
0x14002c7ba  jz      short loc_14002C7CA
0x14002c7bc  lock or [rbx+66Ch], edi
0x14002c7c3  mov     [rbx+7E0h], rax
0x14002c7ca  mov     edi, 1
0x14002c7cf  mov     rax, [rbx]
0x14002c7d2  cmp     byte ptr [rax+0C9h], 0
0x14002c7d9  jz      short loc_14002C83C
0x14002c7db  mov     eax, [rbx+668h]
0x14002c7e1  test    al, 4
0x14002c7e3  jnz     short loc_14002C83C
0x14002c7e5  mov     rax, [rbx+7E0h]
0x14002c7ec  cmp     [rax+5], dil
0x14002c7f0  jnz     short loc_14002C83C
0x14002c7f2  cmp     byte ptr [rax+7], 0
0x14002c7f6  jnz     short loc_14002C83C
0x14002c7f8  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14002c7ff  jz      short loc_14002C822
0x14002c801  mov     rcx, [rbx+8]
0x14002c805  mov     r9d, 4Fh ; 'O'
0x14002c80b  mov     dl, 2
0x14002c80d  mov     [rsp+0C0h+var_A0], r12
0x14002c812  mov     rcx, [rcx+598h]
0x14002c819  lea     r8d, [r9-4Ah]
0x14002c81d  call    WPP_RECORDER_SF_
  ... truncated ...
```
