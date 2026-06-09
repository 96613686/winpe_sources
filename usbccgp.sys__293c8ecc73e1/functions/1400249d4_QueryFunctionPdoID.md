# QueryFunctionPdoID

- ea: `0x1400249d4`
- end: `0x1400253bc`
- name: `QueryFunctionPdoID`
- size: `2536`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140010650`

## callees

- `0x1400083c8`
- `0x14000a6cc`
- `0x14000b64c`
- `0x14000c158`
- `0x14000c768`
- `0x14000d364`
- `0x14000d9b4`
- `0x14000f558`
- `0x140010c08`
- `0x140011e14`
- `0x140011f4c`
- `0x140012174`
- `0x140012218`
- `0x140012348`
- `0x140013858`
- `0x140014e00`
- `0x1400238a4`
- `0x14002484c`
- `0x140024928`
- `0x1400249d4`
- `0x140025f38`
- `0x140029b50`
- `0x14002bc38`
- `0x14002d610`
- `0x14002e27c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140024f0e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024f2a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024f42`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024f71`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025108`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002512b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025387`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025399`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024f0e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024f2a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024f42`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024f71`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025108`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002512b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025387`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025399`
- `ntoskrnl!ExAllocatePool2` at `0x140024b5c`
- `ntoskrnl!ExAllocatePool2` at `0x140024e2c`
- `ntoskrnl!ExAllocatePool2` at `0x140024e88`
- `ntoskrnl!ExAllocatePool2` at `0x140024fbc`
- `ntoskrnl!ExAllocatePool2` at `0x1400251e0`
- `ntoskrnl!ExAllocatePool2` at `0x1400252ef`
- `ntoskrnl!ExAllocatePool2` at `0x140024b5c`
- `ntoskrnl!ExAllocatePool2` at `0x140024e2c`
- `ntoskrnl!ExAllocatePool2` at `0x140024e88`
- `ntoskrnl!ExAllocatePool2` at `0x140024fbc`
- `ntoskrnl!ExAllocatePool2` at `0x1400251e0`
- `ntoskrnl!ExAllocatePool2` at `0x1400252ef`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x140024c44`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x140024cf6`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x140024c44`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x140024cf6`

## string_xrefs

- `0x140024b28`: `custom & MSOS comaptibleID`
- `0x140024b19`: `custom compatibleID`
- `0x140024bae`: `custom compatibleID`
- `0x140024bb8`: `custom & MSOS compatibleID`

## pseudocode

```c
__int64 __fastcall QueryFunctionPdoID(__int64 a1, IRP *a2)
{
  char *v2; // r12
  __int64 v3; // rsi
  _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  unsigned int Length; // edx
  unsigned int v8; // edx
  unsigned int v9; // edx
  unsigned int v10; // ebx
  wchar_t *v11; // rsi
  __int64 v12; // rbx
  int v13; // r8d
  int v14; // r9d
  void *v15; // rax
  PUSB_INTERFACE_DESCRIPTOR v16; // r13
  __int64 v17; // r8
  LONG v18; // eax
  PUSB_INTERFACE_DESCRIPTOR v19; // rax
  __int64 v20; // r8
  __int64 v21; // rax
  PUSB_INTERFACE_DESCRIPTOR MidiInterfaceDescriptor; // rax
  bool v23; // zf
  int v24; // r9d
  unsigned __int8 *p_bInterfaceClass; // rax
  int v26; // edx
  unsigned __int8 v27; // r10
  unsigned __int8 *v28; // r8
  unsigned __int8 bInterfaceSubClass; // al
  __int16 v30; // ax
  unsigned __int16 bInterfaceNumber; // r11
  PVOID v32; // r13
  __int64 v33; // rax
  void *v34; // rcx
  void *v35; // rax
  int v36; // edx
  unsigned __int64 v37; // rbx
  size_t v38; // rdx
  int v39; // r9d
  int v40; // r9d
  wchar_t *v41; // r12
  __int64 v42; // rax
  wchar_t *v43; // rbx
  _WORD *v44; // rdx
  unsigned __int64 v45; // rcx
  unsigned __int64 i; // r8
  unsigned __int64 v47; // r8
  __int64 v48; // r14
  wchar_t *v49; // rax
  wchar_t *v50; // rbx
  const wchar_t *Information; // rax
  wchar_t *Pool2; // rax
  wchar_t *v53; // rsi
  __int64 v54; // rcx
  __int64 appended; // rax
  size_t *InterfaceClass; // [rsp+20h] [rbp-59h]
  ULONG InterfaceSubClass; // [rsp+28h] [rbp-51h]
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-9h] BYREF
  PVOID v60[10]; // [rsp+80h] [rbp+7h] BYREF
  __int64 v61; // [rsp+E0h] [rbp+67h] BYREF
  __int64 v62; // [rsp+E8h] [rbp+6Fh] BYREF
  NTSTRSAFE_PCWSTR pszSrc; // [rsp+F0h] [rbp+77h]
  PVOID P; // [rsp+F8h] [rbp+7Fh] BYREF

  LODWORD(v2) = 0;
  v3 = *(_QWORD *)(a1 + 240);
  P = 0;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  Length = CurrentStackLocation->Parameters.Read.Length;
  if ( !Length )
  {
    a2->IoStatus.Information = 0;
    v44 = *(_WORD **)(v3 + 32);
    if ( !v44 || (*(_DWORD *)(v3 + 80) & 1) != 0 )
    {
      *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
      *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
      *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation->Parameters.SetQuota
                                                                                 + 6);
      CurrentStackLocation[-1].FileObject = CurrentStackLocation->FileObject;
      CurrentStackLocation[-1].Control = 0;
      v10 = CallDriverSync(*(PDEVICE_OBJECT *)(*(_QWORD *)(a1 + 232) + 32LL), a2);
      if ( (v10 & 0x80000000) == 0 )
      {
        Information = (const wchar_t *)a2->IoStatus.Information;
        pszSrc = Information;
        if ( Information )
        {
          LODWORD(v62) = WStrLen(Information);
          LODWORD(v61) = v62 + 2;
          *(_QWORD *)&DestinationString.Length = (unsigned int)(v62 + 2);
          v60[0] = (PVOID)(2LL * *(_QWORD *)&DestinationString.Length);
          Pool2 = (wchar_t *)ExAllocatePool2(256, 2LL * *(_QWORD *)&DestinationString.Length, 1130525525);
          v53 = Pool2;
          if ( Pool2 )
          {
            RtlStringCchCopyExW(
              Pool2,
              *(size_t *)&DestinationString.Length,
              pszSrc,
              (NTSTRSAFE_PWSTR *)&P,
              InterfaceClass,
              InterfaceSubClass);
            if ( (char *)P + 2 < (char *)v53 + (unsigned __int64)v60[0] )
            {
              *((_WORD *)P + 1) = 0;
            }
            else
            {
              v54 = (unsigned int)v62;
              v53[(unsigned int)(v61 - 1)] = 0;
              v53[v54] = 0;
            }
            appended = AppendInterfaceNumber(v53);
            if ( appended )
              a2->IoStatus.Information = appended;
            else
              v10 = -1073741668;
            ExFreePoolWithTag(v53, 0x43627355u);
          }
          else
          {
            v10 = -1073741670;
          }
          ExFreePoolWithTag((PVOID)pszSrc, 0);
        }
      }
      return v10;
    }
    v45 = (unsigned __int64)*(unsigned __int16 *)(v3 + 24) >> 1;
    for ( i = v45; v45; --v45 )
    {
      if ( !*v44 )
        break;
      ++v44;
    }
    v10 = v45 == 0 ? 0xC000000D : 0;
    if ( v45 )
      v47 = i - v45;
    else
      v47 = 0;
    v48 = (2 * v47) & -(__int64)(v45 != 0);
    if ( (v45 == 0 ? 0xC0000000 : 0) == 0xC0000000 || !v48 )
      return v10;
    v49 = (wchar_t *)ExAllocatePool2(256, v48 + 4, 1130525525);
    v50 = v49;
    if ( v49 )
    {
      v38 = (unsigned __int64)(v48 + 2) >> 1;
      if ( v38 )
      {
        if ( v38 <= 0x7FFFFFFF )
          RtlStringCopyWorkerW(v49, v38, 0, *(STRSAFE_PCNZWCH *)(v3 + 32), (size_t)InterfaceClass);
        else
          *v49 = 0;
      }
      a2->IoStatus.Information = (unsigned __int64)v50;
      v10 = 0;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return v10;
      v39 = 22;
LABEL_73:
      LOBYTE(v38) = 4;
      WPP_RECORDER_SF_q(
        *(_QWORD *)(a1 + 392),
        v38,
        2,
        v39,
        (__int64)WPP_5f3fca5046be3c4b9971a87d6c15ecbd_Traceguids,
        *(_QWORD *)(a1 + 224));
      return v10;
    }
    v10 = -1073741670;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v10;
    v40 = 23;
LABEL_76:
    LOBYTE(v36) = 2;
    WPP_RECORDER_SF_d(*(_QWORD *)(a1 + 392), v36, 8, v40, (__int64)WPP_5f3fca5046be3c4b9971a87d6c15ecbd_Traceguids, 154);
    return v10;
  }
  v8 = Length - 1;
  if ( !v8 )
  {
    if ( !*(_QWORD *)(v3 + 32) || (*(_DWORD *)(v3 + 80) & 1) != 0 )
    {
      *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
      *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
      *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation->Parameters.SetQuota
                                                                                 + 6);
      CurrentStackLocation[-1].FileObject = CurrentStackLocation->FileObject;
      CurrentStackLocation[-1].Control = 0;
      v10 = CallDriverSync(*(PDEVICE_OBJECT *)(*(_QWORD *)(a1 + 232) + 32LL), a2);
      if ( (v10 & 0x80000000) == 0 )
      {
        v41 = (wchar_t *)a2->IoStatus.Information;
        v42 = AppendInterfaceNumber(v41);
        v43 = (wchar_t *)v42;
        if ( *(_QWORD *)(v3 + 32) && v42 )
        {
          ExFreePoolWithTag(v41, 0);
          v41 = v43;
          v43 = (wchar_t *)AppendPdoIds(v43);
        }
        ExFreePoolWithTag(v41, 0);
        if ( v43 )
        {
          a2->IoStatus.Information = (unsigned __int64)v43;
          return 0;
        }
        else
        {
          a2->IoStatus.Information = 0;
          return (unsigned int)-1073741823;
        }
      }
      return v10;
    }
    v35 = (void *)ExAllocatePool2(256, *(unsigned __int16 *)(v3 + 24) + 2LL, 1130525525);
    v37 = (unsigned __int64)v35;
    if ( v35 )
    {
      memmove(v35, *(const void **)(v3 + 32), *(unsigned __int16 *)(v3 + 24));
      a2->IoStatus.Information = v37;
      v10 = 0;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return v10;
      v39 = 20;
      goto LABEL_73;
    }
    a2->IoStatus.Information = 0;
    v10 = -1073741670;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v10;
    v40 = 21;
    goto LABEL_76;
  }
  v9 = v8 - 1;
  if ( v9 )
  {
    if ( v9 == 1 )
    {
      v11 = (wchar_t *)MemDup(L"0000", 0xAu);
      if ( v11 )
      {
        RtlStringCchPrintfW(v11, 5u, L"%04x", *(_DWORD *)(a1 + 8) + (*(_BYTE *)(a1 + 303) != 0 ? 0xC000 : 0));
        v10 = 0;
      }
      else
      {
        v10 = -1073741670;
        v11 = 0;
      }
      a2->IoStatus.Information = (unsigned __int64)v11;
    }
    else
    {
      return (unsigned int)a2->IoStatus.Status;
    }
    return v10;
  }
  if ( !*(_QWORD *)(v3 + 48) || (*(_DWORD *)(v3 + 80) & 1) != 0 )
  {
    v16 = ***(PUSB_INTERFACE_DESCRIPTOR ***)(v3 + 8);
    if ( !v16 )
    {
      v10 = -1073741670;
      a2->IoStatus.Information = 0;
      return v10;
    }
    LODWORD(P) = 0;
    v61 = 0;
    v62 = 0;
    v10 = -1073741823;
    GetFunctionMSOSCompatibleIDs(a1, &v61, &v62);
    v18 = *(unsigned __int8 *)(a1 + 305);
    if ( (_BYTE)v18 )
    {
      v19 = USBD_ParseConfigurationDescriptorEx(
              *(PUSB_CONFIGURATION_DESCRIPTOR *)(*(_QWORD *)(a1 + 232) + 48LL),
              v16,
              v16->bInterfaceNumber,
              v18,
              -1,
              -1,
              -1);
      v16 = v19;
      if ( v19->bInterfaceClass == 7 && v19->bInterfaceSubClass == 1 && v19->bInterfaceProtocol == 4 )
      {
        if ( (unsigned int)Feature_WinUsb_Print__private_IsEnabledDeviceUsageNoInline() && *(_BYTE *)(a1 + 408) )
        {
          v2 = aWinusb;
          goto LABEL_33;
        }
        if ( (unsigned int)IsProtectedPrintEnabled() )
        {
          v21 = 0;
          *(_BYTE *)(a1 + 304) = 1;
          goto LABEL_42;
        }
        LOBYTE(v20) = v16->bInterfaceNumber;
        if ( (unsigned int)CheckIppUsbAltIndex(
                             *(unsigned __int16 *)(*(_QWORD *)(a1 + 232) + 104LL),
                             *(unsigned __int16 *)(*(_QWORD *)(a1 + 232) + 106LL),
                             v20) )
        {
          *(_BYTE *)(a1 + 304) = 1;
LABEL_33:
          v21 = 0;
          goto LABEL_42;
        }
        LODWORD(v2) = v61;
        if ( !v61 )
          goto LABEL_33;
        v16 = USBD_ParseConfigurationDescriptorEx(
                *(PUSB_CONFIGURATION_DESCRIPTOR *)(*(_QWORD *)(a1 + 232) + 48LL),
                ***(PVOID ***)(v3 + 8),
                v16->bInterfaceNumber,
                0,
                -1,
                -1,
                -1);
LABEL_41:
        v21 = v62;
LABEL_42:
        v61 = v21;
        v23 = (unsigned int)Feature_WinUsb_Print__private_IsEnabledDeviceUsageNoInline() == 0;
        p_bInterfaceClass = &v16->bInterfaceClass;
        if ( !v23 && *p_bInterfaceClass == 7 && *(_BYTE *)(a1 + 408) )
        {
          v2 = aWinusb;
          v26 = 0;
        }
        else
        {
          v26 = v61;
        }
        v27 = *p_bInterfaceClass;
        v28 = *(unsigned __int8 **)(v3 + 16);
        bInterfaceSubClass = v16->bInterfaceSubClass;
        LOBYTE(v24) = v16->bInterfaceProtocol;
        LOBYTE(v61) = bInterfaceSubClass;
        LOBYTE(v62) = v27;
        LOBYTE(pszSrc) = v24;
        if ( v28 )
        {
          if ( (_DWORD)P
            && (v30 = v28[2],
                bInterfaceNumber = v16->bInterfaceNumber,
                (unsigned __int8)bInterfaceNumber >= (unsigned __int8)v30)
            && bInterfaceNumber < (unsigned __int16)(v30 + v28[3]) )
          {
            bInterfaceSubClass = v61;
          }
          else
          {
            v27 = v28[4];
            bInterfaceSubClass = v28[5];
            LOBYTE(v24) = v28[6];
            LOBYTE(v62) = v27;
            LOBYTE(v61) = bInterfaceSubClass;
            LOBYTE(pszSrc) = v24;
          }
        }
        LOBYTE(InterfaceSubClass) = v24;
        LOBYTE(v24) = v27;
        LOBYTE(InterfaceClass) = bInterfaceSubClass;
        P = (PVOID)BuildCompatibleIDs(
                     (_DWORD)v2,
                     v26,
                     *(unsigned __int16 *)(*(_QWORD *)(a1 + 232) + 104LL),
                     v24,
                     (__int16)InterfaceClass,
                     InterfaceSubClass);
        v32 = P;
        v60[0] = (PVOID)0x100000;
        DestinationString = 0;
        v60[1] = (PVOID)ExAllocatePool2(256, 16, 1130525525);
        if ( v60[1] )
        {
          if ( (_BYTE)v62 == 1 && ((unsigned __int8)pszSrc & 0xDF) == 0 )
          {
            if ( (unsigned __int8)GetControllerSuffix(v60, a1) )
            {
              DestinationString.MaximumLength = 192;
              DestinationString.Buffer = (wchar_t *)ExAllocatePool2(256, 192, 1130525525);
              if ( v60[1] )
              {
                if ( RtlUnicodeStringPrintf(
                       &DestinationString,
                       L"USB\\Class_%02X&Subclass_%02X&Prot_%02X&%wZ%cUSB\\Class_%02X&Subclass_%02X&%wZ%cUSB\\Class_%02X&%wZ",
                       1) >= 0 )
                {
                  v32 = (PVOID)AppendPdoIdsReverse(v32);
                  ExFreePoolWithTag(P, 0x43627355u);
                }
              }
            }
          }
          if ( DestinationString.Buffer )
            ExFreePoolWithTag(DestinationString.Buffer, 0x43627355u);
          if ( v60[1] )
            ExFreePoolWithTag(v60[1], 0x43627355u);
          if ( *(_QWORD *)(v3 + 48) && v32 )
          {
            v33 = AppendPdoIds(v32);
            v34 = v32;
            v32 = (PVOID)v33;
            ExFreePoolWithTag(v34, 0x43627355u);
          }
          a2->IoStatus.Information = (unsigned __int64)v32;
          return v32 == 0 ? 0xC000009A : 0;
        }
        return v10;
      }
    }
    else if ( v16->bInterfaceClass == 1 )
    {
      MidiInterfaceDescriptor = FindMidiInterfaceDescriptor(
                                  *(struct _USB_CONFIGURATION_DESCRIPTOR **)(*(_QWORD *)(a1 + 232) + 48LL),
                                  ***(void ****)(v3 + 8),
                                  v17,
                                  *(_QWORD *)(a1 + 392));
      if ( MidiInterfaceDescriptor )
      {
        v16 = MidiInterfaceDescriptor;
        LODWORD(P) = 1;
      }
    }
    LODWORD(v2) = v61;
    goto LABEL_41;
  }
  if ( (unsigned __int8)IsMSOSCompatibleIDFlagSet(a1) )
  {
    v12 = PrependMSOSCompatibleIDs(a1);
  }
  else
  {
    v15 = (void *)ExAllocatePool2(256, *(unsigned __int16 *)(v3 + 40) + 2LL, 1130525525);
    v12 = (__int64)v15;
    if ( v15 )
    {
      memmove(v15, *(const void **)(v3 + 48), *(unsigned __int16 *)(v3 + 40));
LABEL_15:
      a2->IoStatus.Information = v12;
      v10 = 0;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_sq(*(_QWORD *)(a1 + 392), (unsigned int)"custom compatibleID", v13, v14);
      return v10;
    }
  }
  if ( v12 )
    goto LABEL_15;
  a2->IoStatus.Information = 0;
  v10 = -1073741670;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sd(*(_QWORD *)(a1 + 392), (unsigned int)"custom compatibleID", v13, v14);
  return v10;
}

```

## disassembly

```asm
0x1400249d4  push    rbp
0x1400249d6  push    rbx
0x1400249d7  push    rsi
0x1400249d8  push    rdi
0x1400249d9  push    r12
0x1400249db  push    r13
0x1400249dd  push    r14
0x1400249df  push    r15
0x1400249e1  lea     rbp, [rsp-1Fh]
0x1400249e6  sub     rsp, 98h
0x1400249ed  mov     rax, [rcx+0E8h]
0x1400249f4  xor     r12d, r12d
0x1400249f7  mov     rsi, [rcx+0F0h]
0x1400249fe  mov     r15, rdx
0x140024a01  mov     rdi, rcx
0x140024a04  mov     [rbp+57h+P], r12
0x140024a08  movzx   r13d, r12b
0x140024a0c  lea     r14d, [r12+1]
0x140024a11  cmp     [rax+554h], r12b
0x140024a18  jz      short loc_140024A37
0x140024a1a  mov     rax, [rsi+10h]
0x140024a1e  test    rax, rax
0x140024a21  jz      short loc_140024A37
0x140024a23  cmp     [rax+4], r14b
0x140024a27  jnz     short loc_140024A37
0x140024a29  cmp     [rax+5], r12b
0x140024a2d  jnz     short loc_140024A37
0x140024a2f  cmp     byte ptr [rax+6], 20h ; ' '
0x140024a33  cmovz   r13d, r14d
0x140024a37  mov     rcx, [rdx+0B8h]
0x140024a3e  mov     edx, [rcx+8]
0x140024a41  test    edx, edx
0x140024a43  jz      loc_140025155
0x140024a49  sub     edx, r14d
0x140024a4c  jz      loc_140024F93
0x140024a52  sub     edx, r14d
0x140024a55  jz      short loc_140024ABE
0x140024a57  cmp     edx, r14d
0x140024a5a  jz      short loc_140024A65
0x140024a5c  mov     ebx, [r15+30h]
0x140024a60  jmp     loc_1400253A5
0x140024a65  mov     edx, 0Ah; Size
0x140024a6a  lea     rcx, a0000; "0000"
0x140024a71  call    MemDup
0x140024a76  mov     rsi, rax
0x140024a79  test    rax, rax
0x140024a7c  jz      short loc_140024AAD
0x140024a7e  mov     al, [rdi+12Fh]
0x140024a84  lea     r8, a04x; "%04x"
0x140024a8b  neg     al
0x140024a8d  mov     edx, 5; cchDest
0x140024a92  mov     rcx, rsi; pszDest
0x140024a95  sbb     r9d, r9d
0x140024a98  and     r9d, 0C000h
0x140024a9f  add     r9d, [rdi+8]
0x140024aa3  call    RtlStringCchPrintfW
0x140024aa8  mov     ebx, r12d
0x140024aab  jmp     short loc_140024AB5
0x140024aad  mov     ebx, 0C000009Ah
0x140024ab2  mov     rsi, r12
0x140024ab5  mov     [r15+38h], rsi
0x140024ab9  jmp     loc_1400253A5
0x140024abe  cmp     [rsi+30h], r12
0x140024ac2  jz      loc_140024BD2
0x140024ac8  mov     eax, [rsi+50h]
0x140024acb  test    r14b, al
0x140024ace  jnz     loc_140024BD2
0x140024ad4  mov     rcx, rdi
0x140024ad7  call    IsMSOSCompatibleIDFlagSet
0x140024adc  mov     r14b, al
0x140024adf  test    al, al
0x140024ae1  jz      short loc_140024B49
0x140024ae3  mov     rcx, rdi
0x140024ae6  call    PrependMSOSCompatibleIDs
0x140024aeb  mov     rbx, rax
0x140024aee  test    rbx, rbx
0x140024af1  jz      loc_140024B8A
0x140024af7  mov     [r15+38h], rbx
0x140024afb  mov     ebx, r12d
0x140024afe  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140024b05  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140024b0c  jz      loc_1400253A5
0x140024b12  mov     rax, [rdi+0E0h]
0x140024b19  lea     rdx, aCustomCompatib; "custom compatibleID"
0x140024b20  test    r14b, r14b
0x140024b23  mov     qword ptr [rsp+0D0h+InterfaceProtocol], rax
0x140024b28  lea     rcx, aCustomMsosComa; "custom & MSOS comaptibleID"
0x140024b2f  cmovz   rcx, rdx
0x140024b33  mov     qword ptr [rsp+0D0h+InterfaceSubClass], rcx
0x140024b38  mov     rcx, [rdi+188h]
0x140024b3f  call    WPP_RECORDER_SF_sq
0x140024b44  jmp     loc_1400253A5
0x140024b49  movzx   edx, word ptr [rsi+28h]
0x140024b4d  mov     ecx, 100h
0x140024b52  add     rdx, 2
0x140024b56  mov     r8d, 43627355h
0x140024b5c  call    cs:__imp_ExAllocatePool2
0x140024b63  nop     dword ptr [rax+rax+00h]
0x140024b68  mov     rbx, rax
0x140024b6b  test    rax, rax
0x140024b6e  jz      loc_140024AEE
0x140024b74  movzx   r8d, word ptr [rsi+28h]; Size
0x140024b79  mov     rcx, rax; void *
0x140024b7c  mov     rdx, [rsi+30h]; Src
0x140024b80  call    memmove
0x140024b85  jmp     loc_140024AF7
0x140024b8a  mov     [r15+38h], r12
0x140024b8e  mov     ebx, 0C000009Ah
0x140024b93  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140024b9a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140024ba1  jz      loc_1400253A5
0x140024ba7  mov     rcx, [rdi+188h]
0x140024bae  lea     rdx, aCustomCompatib; "custom compatibleID"
0x140024bb5  test    r14b, r14b
0x140024bb8  lea     rax, aCustomMsosComp; "custom & MSOS compatibleID"
0x140024bbf  cmovz   rax, rdx
0x140024bc3  mov     qword ptr [rsp+0D0h+InterfaceSubClass], rax
0x140024bc8  call    WPP_RECORDER_SF_sd
0x140024bcd  jmp     loc_1400253A5
0x140024bd2  mov     rax, [rsi+8]
0x140024bd6  mov     rcx, [rax]
0x140024bd9  mov     r13, [rcx]
0x140024bdc  test    r13, r13
0x140024bdf  jnz     short loc_140024BEF
0x140024be1  mov     ebx, 0C000009Ah
0x140024be6  mov     [r15+38h], r12
0x140024bea  jmp     loc_1400253A5
0x140024bef  lea     r8, [rbp+57h+arg_8]
0x140024bf3  mov     dword ptr [rbp+57h+P], r12d
0x140024bf7  lea     rdx, [rbp+57h+arg_0]
0x140024bfb  mov     [rbp+57h+arg_0], r12
0x140024bff  mov     rcx, rdi
0x140024c02  mov     [rbp+57h+arg_8], r12
0x140024c06  mov     ebx, 0C0000001h
0x140024c0b  call    GetFunctionMSOSCompatibleIDs
0x140024c10  movzx   eax, byte ptr [rdi+131h]
0x140024c17  test    al, al
0x140024c19  jz      loc_140024D1D
0x140024c1f  mov     rcx, [rdi+0E8h]
0x140024c26  mov     r9d, eax; AlternateSetting
0x140024c29  movzx   r8d, byte ptr [r13+2]; InterfaceNumber
0x140024c2e  or      eax, 0FFFFFFFFh
0x140024c31  mov     [rsp+0D0h+InterfaceProtocol], eax; InterfaceProtocol
0x140024c35  mov     rdx, r13; StartPosition
0x140024c38  mov     [rsp+0D0h+InterfaceSubClass], eax; InterfaceSubClass
0x140024c3c  mov     rcx, [rcx+30h]; ConfigurationDescriptor
0x140024c40  mov     [rsp+0D0h+InterfaceClass], eax; InterfaceClass
0x140024c44  call    cs:__imp_USBD_ParseConfigurationDescriptorEx
0x140024c4b  nop     dword ptr [rax+rax+00h]
0x140024c50  mov     r13, rax
0x140024c53  cmp     byte ptr [rax+5], 7
0x140024c57  jnz     loc_140024D50
0x140024c5d  cmp     [rax+6], r14b
0x140024c61  jnz     loc_140024D50
0x140024c67  cmp     byte ptr [rax+7], 4
0x140024c6b  jnz     loc_140024D50
0x140024c71  call    Feature_WinUsb_Print__private_IsEnabledDeviceUsageNoInline
0x140024c76  test    eax, eax
0x140024c78  jnz     loc_140024D07
0x140024c7e  call    IsProtectedPrintEnabled
0x140024c83  test    eax, eax
0x140024c85  jz      short loc_140024C95
0x140024c87  xor     eax, eax
0x140024c89  mov     [rdi+130h], r14b
0x140024c90  jmp     loc_140024D58
0x140024c95  mov     rcx, [rdi+0E8h]
0x140024c9c  mov     r8b, [r13+2]
0x140024ca0  movzx   edx, word ptr [rcx+6Ah]
0x140024ca4  movzx   ecx, word ptr [rcx+68h]
0x140024ca8  call    CheckIppUsbAltIndex
0x140024cad  test    eax, eax
0x140024caf  jz      short loc_140024CBA
0x140024cb1  mov     [rdi+130h], r14b
0x140024cb8  jmp     short loc_140024CC3
0x140024cba  mov     r12, [rbp+57h+arg_0]
0x140024cbe  test    r12, r12
0x140024cc1  jnz     short loc_140024CCA
0x140024cc3  xor     eax, eax
0x140024cc5  jmp     loc_140024D58
0x140024cca  mov     rax, [rsi+8]
0x140024cce  xor     r9d, r9d; AlternateSetting
0x140024cd1  mov     rcx, [rdi+0E8h]
0x140024cd8  movzx   r8d, byte ptr [r13+2]; InterfaceNumber
0x140024cdd  mov     rdx, [rax]
0x140024ce0  or      eax, 0FFFFFFFFh
0x140024ce3  mov     rcx, [rcx+30h]; ConfigurationDescriptor
0x140024ce7  mov     [rsp+0D0h+InterfaceProtocol], eax; InterfaceProtocol
0x140024ceb  mov     [rsp+0D0h+InterfaceSubClass], eax; InterfaceSubClass
0x140024cef  mov     rdx, [rdx]; StartPosition
0x140024cf2  mov     [rsp+0D0h+InterfaceClass], eax; InterfaceClass
0x140024cf6  call    cs:__imp_USBD_ParseConfigurationDescriptorEx
0x140024cfd  nop     dword ptr [rax+rax+00h]
0x140024d02  mov     r13, rax
0x140024d05  jmp     short loc_140024D54
0x140024d07  cmp     [rdi+198h], r12b
0x140024d0e  jz      loc_140024C7E
0x140024d14  lea     r12, aWinusb; "WINUSB"
0x140024d1b  jmp     short loc_140024CC3
0x140024d1d  cmp     [r13+5], r14b
0x140024d21  jnz     short loc_140024D50
0x140024d23  mov     rax, [rsi+8]
0x140024d27  mov     rcx, [rdi+0E8h]
0x140024d2e  mov     r9, [rdi+188h]
0x140024d35  mov     rdx, [rax]
0x140024d38  mov     rcx, [rcx+30h]; DescriptorBuffer
0x140024d3c  mov     rdx, [rdx]
0x140024d3f  call    FindMidiInterfaceDescriptor
0x140024d44  test    rax, rax
0x140024d47  jz      short loc_140024D50
0x140024d49  mov     r13, rax
0x140024d4c  mov     dword ptr [rbp+57h+P], r14d
0x140024d50  mov     r12, [rbp+57h+arg_0]
0x140024d54  mov     rax, [rbp+57h+arg_8]
0x140024d58  mov     [rbp+57h+arg_0], rax
0x140024d5c  call    Feature_WinUsb_Print__private_IsEnabledDeviceUsageNoInline
0x140024d61  xor     ecx, ecx
0x140024d63  test    eax, eax
0x140024d65  lea     rax, [r13+5]
0x140024d69  jz      short loc_140024D83
0x140024d6b  cmp     byte ptr [rax], 7
0x140024d6e  jnz     short loc_140024D83
0x140024d70  cmp     [rdi+198h], cl
0x140024d76  jz      short loc_140024D83
0x140024d78  lea     r12, aWinusb; "WINUSB"
0x140024d7f  mov     edx, ecx
0x140024d81  jmp     short loc_140024D87
0x140024d83  mov     rdx, [rbp+57h+arg_0]
0x140024d87  mov     r10b, [rax]
0x140024d8a  mov     r8, [rsi+10h]
0x140024d8e  mov     al, [r13+6]
0x140024d92  mov     r9b, [r13+7]
0x140024d96  mov     byte ptr [rbp+57h+arg_0], al
0x140024d99  mov     byte ptr [rbp+57h+arg_8], r10b
0x140024d9d  mov     byte ptr [rbp+57h+pszSrc], r9b
0x140024da1  test    r8, r8
0x140024da4  jz      short loc_140024DE4
0x140024da6  cmp     dword ptr [rbp+57h+P], ecx
0x140024da9  jz      short loc_140024DC8
0x140024dab  movzx   eax, byte ptr [r8+2]
0x140024db0  movzx   r11d, byte ptr [r13+2]
0x140024db5  cmp     r11b, al
0x140024db8  jb      short loc_140024DC8
0x140024dba  movzx   ecx, byte ptr [r8+3]
0x140024dbf  add     cx, ax
0x140024dc2  cmp     r11w, cx
0x140024dc6  jb      short loc_140024DE1
0x140024dc8  mov     r10b, [r8+4]
0x140024dcc  mov     al, [r8+5]
0x140024dd0  mov     r9b, [r8+6]
0x140024dd4  mov     byte ptr [rbp+57h+arg_8], r10b
0x140024dd8  mov     byte ptr [rbp+57h+arg_0], al
0x140024ddb  mov     byte ptr [rbp+57h+pszSrc], r9b
0x140024ddf  jmp     short loc_140024DE4
0x140024de1  mov     al, byte ptr [rbp+57h+arg_0]
0x140024de4  mov     r8, [rdi+0E8h]
0x140024deb  mov     rcx, r12
0x140024dee  mov     byte ptr [rsp+0D0h+InterfaceSubClass], r9b
0x140024df3  mov     r9b, r10b
0x140024df6  mov     byte ptr [rsp+0D0h+InterfaceClass], al
0x140024dfa  movzx   r8d, word ptr [r8+68h]
0x140024dff  call    BuildCompatibleIDs
0x140024e04  xorps   xmm0, xmm0
0x140024e07  mov     [rbp+57h+P], rax
0x140024e0b  xorps   xmm1, xmm1
0x140024e0e  mov     r12d, 43627355h
0x140024e14  mov     r8d, r12d
0x140024e17  mov     edx, 10h
0x140024e1c  mov     ecx, 100h
0x140024e21  mov     r13, rax
0x140024e24  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x140024e28  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x140024e2c  call    cs:__imp_ExAllocatePool2
0x140024e33  nop     dword ptr [rax+rax+00h]
0x140024e38  mov     [rbp+57h+var_50+8], rax
0x140024e3c  mov     ecx, 10h
0x140024e41  mov     word ptr [rbp+57h+var_50+2], cx
0x140024e45  test    rax, rax
0x140024e48  jz      loc_1400253A5
0x140024e4e  cmp     byte ptr [rbp+57h+arg_8], r14b
0x140024e52  jnz     loc_140024F1C
0x140024e58  movzx   ebx, byte ptr [rbp+57h+pszSrc]
0x140024e5c  test    bl, 0DFh
0x140024e5f  jnz     loc_140024F1C
0x140024e65  mov     rdx, rdi
0x140024e68  lea     rcx, [rbp+57h+var_50]
0x140024e6c  call    GetControllerSuffix
0x140024e71  xor     edi, edi
0x140024e73  test    al, al
0x140024e75  jz      loc_140024F1E
0x140024e7b  mov     edi, 0C0h
0x140024e80  mov     r8d, r12d
0x140024e83  mov     edx, edi
0x140024e85  lea     ecx, [rdi+40h]
0x140024e88  call    cs:__imp_ExAllocatePool2
0x140024e8f  nop     dword ptr [rax+rax+00h]
0x140024e94  mov     [rbp+57h+DestinationString.MaximumLength], di
0x140024e98  xor     edi, edi
0x140024e9a  mov     [rbp+57h+DestinationString.Buffer], rax
0x140024e9e  cmp     [rbp+57h+var_50+8], rdi
0x140024ea2  jz      short loc_140024F1E
  ... truncated ...
```
