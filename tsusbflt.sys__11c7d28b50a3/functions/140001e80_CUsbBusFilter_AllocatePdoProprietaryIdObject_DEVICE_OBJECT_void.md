# CUsbBusFilter::AllocatePdoProprietaryIdObject(_DEVICE_OBJECT *,void * *)

- ea: `0x140001e80`
- end: `0x1400029dd`
- name: `?AllocatePdoProprietaryIdObject@CUsbBusFilter@@AEAAJPEAU_DEVICE_OBJECT@@PEAPEAX@Z`
- size: `2909`
- prototype: `__int64 __fastcall(CUsbBusFilter *__hidden this, struct _DEVICE_OBJECT *, void **)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140003258`

## callees

- `0x140001e80`
- `0x140003f90`
- `0x140004f18`
- `0x140004f48`
- `0x140004f8c`
- `0x140005000`
- `0x140009134`
- `0x1400092c8`
- `0x140009eb4`
- `0x14000a2e8`
- `0x14000a86c`
- `0x14000a90c`
- `0x14000a9f0`
- `0x14000aa30`
- `0x14000ab00`
- `0x14000b140`

## import_xrefs

- `ntoskrnl!ObQueryNameString` at `0x140001f6e`
- `ntoskrnl!ObQueryNameString` at `0x140001fcc`
- `ntoskrnl!ObQueryNameString` at `0x140001f6e`
- `ntoskrnl!ObQueryNameString` at `0x140001fcc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400023e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000257f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002598`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400025ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400025c8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400025de`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000262b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002645`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400023e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000257f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002598`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400025ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400025c8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400025de`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000262b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002645`
- `ntoskrnl!ExAllocatePool2` at `0x140001f9d`
- `ntoskrnl!ExAllocatePool2` at `0x14000254d`
- `ntoskrnl!ExAllocatePool2` at `0x140001f9d`
- `ntoskrnl!ExAllocatePool2` at `0x14000254d`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x14000283e`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x14000283e`

## pseudocode

```c
__int64 __fastcall CUsbBusFilter::AllocatePdoProprietaryIdObject(
        CUsbBusFilter *this,
        struct _DEVICE_OBJECT *a2,
        void **a3)
{
  wchar_t *v5; // rdi
  unsigned __int16 *v6; // r14
  void *v7; // rsi
  struct _USB_CONFIGURATION_DESCRIPTOR *v8; // r13
  NTSTATUS v9; // ebx
  struct _OBJECT_NAME_INFORMATION *Pool2; // rax
  int ID; // eax
  int v12; // r11d
  int v13; // eax
  int v14; // r9d
  size_t v15; // rdi
  int v16; // eax
  int v17; // r11d
  size_t v18; // r14
  int v19; // eax
  size_t v20; // rax
  STRSAFE_PCNZWCH v21; // rdx
  size_t v22; // rbx
  unsigned __int64 v23; // r13
  size_t v24; // r12
  unsigned __int16 *v25; // rsi
  unsigned __int16 *v26; // r15
  size_t v27; // rdi
  _WORD *v28; // rbx
  unsigned int v29; // eax
  unsigned __int16 *v30; // rdx
  size_t v31; // r8
  unsigned int v32; // ecx
  unsigned __int64 v33; // rdi
  size_t v34; // r15
  unsigned __int8 v35; // si
  struct _DEVICE_OBJECT *v36; // r12
  unsigned __int64 v37; // rax
  const void **v38; // rdx
  int v39; // ebx
  unsigned int *v40; // r9
  wchar_t *v41; // rdi
  __int64 v42; // r8
  int v43; // r9d
  int v44; // r9d
  CUsbBusFilter *v45; // rcx
  __int64 v46; // rax
  int v48; // edi
  int v49; // r9d
  int v50; // eax
  PDEVICE_OBJECT v51; // rcx
  __int64 v52; // rdx
  __int64 v53; // r9
  LONG v54; // ebx
  PUSB_INTERFACE_DESCRIPTOR v55; // rax
  __int128 v56; // xmm1
  const unsigned __int16 ***InterfaceClass; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 ***InterfaceClassa; // [rsp+20h] [rbp-E0h]
  unsigned __int64 InterfaceSubClass; // [rsp+28h] [rbp-D8h]
  unsigned __int64 InterfaceSubClassa; // [rsp+28h] [rbp-D8h]
  unsigned __int64 InterfaceSubClassb; // [rsp+28h] [rbp-D8h]
  unsigned __int64 InterfaceSubClassc; // [rsp+28h] [rbp-D8h]
  STRSAFE_PCNZWCH psz; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int8 v64; // [rsp+48h] [rbp-B8h]
  unsigned __int16 *v65; // [rsp+50h] [rbp-B0h] BYREF
  void *v66; // [rsp+60h] [rbp-A0h]
  ULONG ReturnLength; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v68; // [rsp+6Ch] [rbp-94h] BYREF
  size_t pcchLength; // [rsp+70h] [rbp-90h] BYREF
  size_t Size; // [rsp+78h] [rbp-88h] BYREF
  void *v71; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v72; // [rsp+88h] [rbp-78h] BYREF
  void *Src; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v74; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v75; // [rsp+A0h] [rbp-60h] BYREF
  STRSAFE_PCNZWCH v76; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 *v77; // [rsp+B0h] [rbp-50h] BYREF
  PVOID P; // [rsp+B8h] [rbp-48h] BYREF
  PVOID v79; // [rsp+C0h] [rbp-40h]
  PVOID v80; // [rsp+C8h] [rbp-38h]
  struct _IO_STACK_LOCATION v81; // [rsp+D0h] [rbp-30h] BYREF
  struct _DEVICE_OBJECT *v82; // [rsp+118h] [rbp+18h]
  void **v83; // [rsp+128h] [rbp+28h]
  _OWORD v84[2]; // [rsp+130h] [rbp+30h] BYREF
  __int128 v85; // [rsp+150h] [rbp+50h]
  __int64 *v86; // [rsp+160h] [rbp+60h]
  _QWORD v87[20]; // [rsp+170h] [rbp+70h] BYREF
  __int64 v88; // [rsp+210h] [rbp+110h] BYREF
  char v89; // [rsp+218h] [rbp+118h]
  __int128 v90; // [rsp+220h] [rbp+120h] BYREF
  __int16 v91; // [rsp+230h] [rbp+130h]
  _OWORD v92[4]; // [rsp+240h] [rbp+140h] BYREF

  v82 = a2;
  v83 = a3;
  memset(v92, 0, sizeof(v92));
  ReturnLength = 0;
  v72 = 0;
  v86 = 0;
  Size = 0;
  memset(v84, 0, sizeof(v84));
  v68 = 0;
  v75 = 0;
  v85 = 0;
  memset(v87, 0, 0x98u);
  v74 = 0;
  v91 = 0;
  v88 = 0;
  v89 = 0;
  psz = 0;
  v65 = 0;
  v90 = 0;
  v5 = 0;
  Src = 0;
  v6 = 0;
  v66 = 0;
  v7 = 0;
  v76 = 0;
  v71 = 0;
  v8 = 0;
  P = 0;
  v79 = 0;
  v77 = 0;
  if ( ObQueryNameString(a2, 0, 0, &ReturnLength) != -1073741820 )
  {
    v9 = -1073741811;
LABEL_60:
    if ( v71 )
    {
      ((void (__fastcall *)(struct _LIST_ENTRY *))WPP_MAIN_CB.Queue.ListEntry.Flink[104].Flink)(WPP_MAIN_CB.Queue.ListEntry.Blink);
      v71 = 0;
    }
    goto LABEL_62;
  }
  Pool2 = (struct _OBJECT_NAME_INFORMATION *)ExAllocatePool2(256, ReturnLength, 1179997012);
  v80 = Pool2;
  if ( !Pool2 )
  {
    v9 = -1073741801;
    goto LABEL_51;
  }
  v9 = ObQueryNameString(a2, Pool2, ReturnLength, &ReturnLength);
  if ( v9 >= 0 )
  {
    ID = PnpIrpQueryID(a2, BusQueryDeviceID, (unsigned __int16 **)&psz);
    v5 = (wchar_t *)psz;
    v9 = ID;
    if ( ID >= 0 )
    {
      pcchLength = 0;
      if ( !psz )
      {
        v9 = -1073741811;
        goto LABEL_50;
      }
      v9 = RtlStringLengthWorkerW(psz, 0x7FFFu, &pcchLength);
      if ( v9 < 0 )
        goto LABEL_50;
      v13 = PnpIrpQueryID(a2, (enum BUS_QUERY_ID_TYPE)(v12 + 1), &v65);
      v6 = v65;
      v9 = v13;
      if ( v13 < 0 )
        goto LABEL_50;
      v9 = ValidateMultiStrings(v65, 0xFFFFu, &v68, &v72, InterfaceClass);
      if ( v9 < 0 )
        goto LABEL_50;
      v9 = PnpIrpQueryID(a2, BusQueryCompatibleIDs, (unsigned __int16 **)&Src);
      if ( v9 < 0 )
        goto LABEL_50;
      v9 = ValidateMultiStrings((const unsigned __int16 *)Src, 0xFFFFu, &v75, &Size, InterfaceClassa);
      if ( v9 < 0 )
        goto LABEL_50;
      memset(&v81, 0, sizeof(v81));
      LODWORD(v92[0]) = 65600;
      *((_QWORD *)&v92[0] + 1) = -1;
      *(_WORD *)&v81.MajorFunction = 2331;
      v81.Parameters.WMI.ProviderId = (ULONG_PTR)v92;
      v9 = IopSynchronousCall(a2, &v81, 0, v14, 0, InterfaceSubClass, 0);
      if ( v9 < 0 )
        goto LABEL_50;
      v15 = 2 * pcchLength;
      if ( (BYTE4(v92[0]) & 0x40) != 0 )
      {
        v16 = PnpIrpQueryID(a2, BusQueryInstanceID, (unsigned __int16 **)&v76);
        v7 = (void *)v76;
        v9 = v16;
        if ( v16 >= 0 )
        {
          v66 = (void *)v76;
          pcchLength = 0;
          if ( v76 )
          {
            v9 = RtlStringLengthWorkerW(v76, 0x7FFFu, &pcchLength);
            if ( v9 >= 0 )
            {
              v18 = 2 * pcchLength;
LABEL_23:
              DWORD1(v84[1]) = v17;
              v74 = v72 - 2;
              Size -= 2LL;
              LODWORD(v84[0]) = 56;
              *((_QWORD *)&v84[1] + 1) = 0x100000001LL;
              v86 = off_14000F150;
              *(_QWORD *)&v85 = *(_QWORD *)this;
              v72 = v15 + v18 + v72 - 2 + Size + 4;
              *((_QWORD *)&v85 + 1) = ReturnLength + 104LL + v72;
              *(_OWORD *)((char *)v84 + 4) = 0;
              v9 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, _OWORD *, void **))WPP_MAIN_CB.Queue.ListEntry.Flink[103].Blink)(
                     WPP_MAIN_CB.Queue.ListEntry.Blink,
                     v84,
                     &v71);
              if ( v9 >= 0 )
              {
                v64 = 0;
                v20 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, void *, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[101].Flink)(
                        WPP_MAIN_CB.Queue.ListEntry.Blink,
                        v71,
                        off_14000F150);
                v21 = psz;
                pcchLength = v20;
                v22 = v20 + 104;
                *(_DWORD *)(v20 + 88) = 0;
                memmove((void *)(v20 + 104), v21, v15);
                v23 = v74;
                v24 = Size;
                v25 = v65;
                v26 = (unsigned __int16 *)Src;
                v27 = v15 >> 1;
                *(_WORD *)(v22 + 2 * v27) = 44;
                v28 = (_WORD *)(v22 + 2 * v27 + 2);
                v29 = 0;
                v68 = 0;
                do
                {
                  if ( v29 )
                  {
                    v30 = v26;
                    v31 = v24;
                  }
                  else
                  {
                    v30 = v25;
                    v31 = v23;
                  }
                  v32 = 0;
                  v33 = v31 >> 1;
                  if ( v31 >> 1 )
                  {
                    do
                    {
                      if ( !v30[v32] )
                        v30[v32] = 44;
                      ++v32;
                    }
                    while ( v32 < v33 );
                    v25 = v65;
                  }
                  memmove(v28, v30, v31);
                  v28 += v33;
                  v29 = v68 + 1;
                  v68 = v29;
                }
                while ( v29 < 2 );
                v34 = pcchLength;
                v35 = 0;
                v36 = v82;
                v8 = 0;
                if ( v18 )
                {
                  memmove(v28, v66, v18);
                  v28 += v18 >> 1;
                }
                v37 = v72;
                v38 = (const void **)v80;
                *v28 = 0;
                *(_QWORD *)(v34 + 96) = v37;
                memmove((void *)(v34 + v37 + 104), v38[1], *((unsigned __int16 *)v38 + 1));
                v39 = 0;
                while ( 1 )
                {
                  if ( (int)PnpIrpQueryID(v36, (enum BUS_QUERY_ID_TYPE)(2 - (v39 != 0)), (unsigned __int16 **)&P) >= 0 )
                  {
                    v41 = (wchar_t *)P;
                    if ( !v39 )
                      v64 = IsAnyStringInMultiSzOnStringTable(
                              (wchar_t *)P,
                              (const unsigned __int16 **const)&g_CompositeDeviceIdList,
                              1u,
                              v40);
                    v35 = IsAnyStringInMultiSzOnStringTable(
                            v41,
                            (const unsigned __int16 **const)&CUsbDeviceDisallowList::m_UsbDeviceDisallowList,
                            3u,
                            v40);
                    ExFreePoolWithTag(v41, 0);
                    P = 0;
                    if ( v35 )
                      break;
                  }
                  if ( (unsigned int)++v39 >= 2 )
                  {
                    LODWORD(v87[0]) = 721032;
                    HIDWORD(v87[4]) = 18;
                    v87[6] = 0;
                    v87[5] = &v90;
                    *(_DWORD *)((char *)&v87[16] + 2) = 256;
                    v87[7] = 0;
                    memset(&v81, 0, sizeof(v81));
                    v81.MajorFunction = 15;
                    v81.Parameters.WMI.ProviderId = (ULONG_PTR)v87;
                    v81.Parameters.Read.ByteOffset.LowPart = 2228227;
                    v9 = IopSynchronousCall(v36, &v81, 0, v43, 1, InterfaceSubClassa, &Size);
                    if ( v9 < 0 )
                    {
LABEL_47:
                      v7 = v66;
                      goto LABEL_48;
                    }
                    if ( v64 )
                    {
                      LODWORD(v87[0]) = 721032;
                      v88 = 0;
                      v89 = 0;
                      HIDWORD(v87[4]) = 9;
                      v87[6] = 0;
                      v87[5] = &v88;
                      *(_DWORD *)((char *)&v87[16] + 2) = 512;
                      v87[7] = 0;
                      memset(&v81, 0, sizeof(v81));
                      v81.MajorFunction = 15;
                      v81.Parameters.WMI.ProviderId = (ULONG_PTR)v87;
                      v81.Parameters.Read.ByteOffset.LowPart = 2228227;
                      v9 = IopSynchronousCall(v36, &v81, 0, v44, 1, InterfaceSubClassb, &Size);
                      if ( WORD1(v88) <= 9u )
                      {
                        if ( v9 < 0 )
                        {
                          v51 = WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                          {
                            goto LABEL_47;
                          }
                          v52 = 48;
                          v53 = (unsigned int)v9;
LABEL_75:
                          WPP_SF_d(v51->AttachedDevice, v52, WPP_b486fa217bde37cd2eb5d2f2271ffb01_Traceguids, v53);
                          goto LABEL_47;
                        }
                        v8 = (struct _USB_CONFIGURATION_DESCRIPTOR *)&v88;
                      }
                      else
                      {
                        v46 = ExAllocatePool2(64, WORD1(v88), 1179997012);
                        v8 = (struct _USB_CONFIGURATION_DESCRIPTOR *)v46;
                        if ( !v46 )
                        {
                          v9 = -1073741801;
                          goto LABEL_47;
                        }
                        v48 = WORD1(v88);
                        LODWORD(v87[0]) = 721032;
                        HIDWORD(v87[4]) = WORD1(v88);
                        v87[6] = 0;
                        v87[5] = v46;
                        *(_DWORD *)((char *)&v87[16] + 2) = 512;
                        v87[7] = 0;
                        memset(&v81, 0, sizeof(v81));
                        v81.MajorFunction = 15;
                        v81.Parameters.WMI.ProviderId = (ULONG_PTR)v87;
                        v81.Parameters.Read.ByteOffset.LowPart = 2228227;
                        v50 = IopSynchronousCall(v36, &v81, 0, v49, 1, InterfaceSubClassc, &Size);
                        v9 = v50;
                        if ( v50 < 0 )
                        {
                          v51 = WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                          {
                            goto LABEL_47;
                          }
                          v52 = 46;
                          v53 = (unsigned int)v50;
                          goto LABEL_75;
                        }
                        if ( v8->wTotalLength != v48 )
                        {
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                          {
                            WPP_SF_(
                              WPP_GLOBAL_Control->AttachedDevice,
                              47,
                              WPP_b486fa217bde37cd2eb5d2f2271ffb01_Traceguids);
                          }
                          v9 = -1073741823;
                          goto LABEL_47;
                        }
                      }
                      v54 = 0;
                      if ( v8->bNumInterfaces )
                      {
                        while ( !v35 )
                        {
                          v55 = USBD_ParseConfigurationDescriptorEx(v8, v8, v54, 0, -1, -1, -1);
                          if ( !v55 )
                          {
                            v45 = (CUsbBusFilter *)WPP_GLOBAL_Control;
                            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                            {
                              WPP_SF_(
                                WPP_GLOBAL_Control->AttachedDevice,
                                49,
                                WPP_b486fa217bde37cd2eb5d2f2271ffb01_Traceguids);
                            }
                            goto LABEL_99;
                          }
                          v45 = 0;
                          while ( (v55->bInterfaceProtocol
                                 | ((v55->bInterfaceSubClass | (v55->bInterfaceClass << 8)) << 8)) != *((_DWORD *)&CUsbDeviceClassDisallowList::m_UsbDeviceClassDisallowList + (_QWORD)v45) )
                          {
                            v45 = (CUsbBusFilter *)(unsigned int)((_DWORD)v45 + 1);
                            if ( (_DWORD)v45 )
                              goto LABEL_97;
                          }
                          v45 = (CUsbBusFilter *)WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                          {
                            WPP_SF_SD(
                              WPP_GLOBAL_Control->AttachedDevice,
                              50,
                              (unsigned int)WPP_b486fa217bde37cd2eb5d2f2271ffb01_Traceguids,
                              (_DWORD)psz,
                              v55->bInterfaceProtocol);
                          }
                          v35 = 1;
LABEL_97:
                          if ( ++v54 >= (unsigned int)v8->bNumInterfaces )
                          {
                            if ( v35 )
                              goto LABEL_100;
                            goto LABEL_99;
                          }
                        }
                      }
                      else
                      {
LABEL_99:
                        v35 = CUsbBusFilter::CheckForHIDKeyboardAndMouse(v45, v36);
                      }
                      goto LABEL_100;
                    }
                    LODWORD(v45) = 0;
                    while ( BYTE4(v90) != *((_DWORD *)&CUsbDeviceClassDisallowList::m_UsbDeviceClassDisallowList
                                          + (unsigned int)v45) )
                    {
                      v45 = (CUsbBusFilter *)(unsigned int)((_DWORD)v45 + 1);
                      if ( (_DWORD)v45 )
                        goto LABEL_99;
                    }
                    v35 = 1;
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                    {
                      v5 = (wchar_t *)psz;
                      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                        WPP_SF_SD(
                          WPP_GLOBAL_Control->AttachedDevice,
                          51,
                          (unsigned int)WPP_b486fa217bde37cd2eb5d2f2271ffb01_Traceguids,
                          (_DWORD)psz,
                          SBYTE4(v90));
                      goto LABEL_101;
                    }
LABEL_100:
                    v5 = (wchar_t *)psz;
                    goto LABEL_101;
                  }
                }
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  goto LABEL_100;
                v5 = (wchar_t *)psz;
                if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                  WPP_SF_S(WPP_GLOBAL_Control->AttachedDevice, 45, v42, psz);
LABEL_101:
                v6 = v65;
                *(_QWORD *)(v34 + 80) = v72;
                *(_QWORD *)(v34 + 8) = v36;
                v9 = 0;
                *(_OWORD *)(v34 + 16) = v92[0];
                *(_OWORD *)(v34 + 32) = v92[1];
                *(_OWORD *)(v34 + 48) = v92[2];
                v56 = v92[3];
                *(_BYTE *)(v34 + 2) = v35;
                v7 = v66;
                *(_OWORD *)(v34 + 64) = v56;
                *(_WORD *)v34 = 0;
                goto LABEL_50;
              }
LABEL_48:
              v6 = v65;
            }
          }
          else
          {
            v9 = -1073741811;
          }
        }
        v5 = (wchar_t *)psz;
        goto LABEL_50;
      }
      v19 = CUsbBusFilter::QueryChildDeviceText(
              this,
              a2,
              0,
              DeviceTextLocationInformation,
              0x409u,
              (const unsigned __int16 **)&v77,
              &v74);
      v17 = 0;
      if ( v19 < 0 )
      {
        v18 = 0;
        v79 = v77;
      }
      else
      {
        v7 = v77;
        v18 = v74;
        v66 = v77;
        v79 = 0;
      }
      goto LABEL_23;
    }
  }
LABEL_50:
  ExFreePoolWithTag(v80, 0);
LABEL_51:
  if ( v5 )
    ExFreePoolWithTag(v5, 0);
  if ( v6 )
    ExFreePoolWithTag(v6, 0);
  if ( Src )
    ExFreePoolWithTag(Src, 0);
  if ( v7 )
    ExFreePoolWithTag(v7, 0);
  if ( v9 < 0 )
    goto LABEL_60;
LABEL_62:
  if ( v8 && v8 != (struct _USB_CONFIGURATION_DESCRIPTOR *)&v88 )
    ExFreePoolWithTag(v8, 0);
  if ( v79 )
    ExFreePoolWithTag(v79, 0);
  *v83 = v71;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140001e80  mov     [rsp-8+arg_18], rbx
0x140001e85  push    rbp
0x140001e86  push    rsi
0x140001e87  push    rdi
0x140001e88  push    r12
0x140001e8a  push    r13
0x140001e8c  push    r14
0x140001e8e  push    r15
0x140001e90  lea     rbp, [rsp-190h]
0x140001e98  sub     rsp, 290h
0x140001e9f  mov     rax, cs:__security_cookie
0x140001ea6  xor     rax, rsp
0x140001ea9  mov     [rbp+1C0h+var_40], rax
0x140001eb0  mov     r12, rdx
0x140001eb3  mov     [rbp+1C0h+var_1A8], rdx
0x140001eb7  xor     edx, edx; Val
0x140001eb9  mov     [rbp+1C0h+var_198], r8
0x140001ebd  mov     r15, rcx
0x140001ec0  lea     rcx, [rbp+1C0h+var_80]; void *
0x140001ec7  lea     r8d, [rdx+40h]; Size
0x140001ecb  call    memset
0x140001ed0  xor     ebx, ebx
0x140001ed2  lea     rcx, [rbp+1C0h+var_150]; void *
0x140001ed6  xorps   xmm0, xmm0
0x140001ed9  mov     [rsp+2C0h+ReturnLength], ebx
0x140001edd  xor     eax, eax
0x140001edf  mov     [rbp+1C0h+var_238], rbx
0x140001ee3  xor     edx, edx; Val
0x140001ee5  mov     [rbp+1C0h+var_160], rax
0x140001ee9  mov     r8d, 98h; Size
0x140001eef  mov     [rsp+2C0h+Size], rbx
0x140001ef4  movups  [rbp+1C0h+var_190], xmm0
0x140001ef8  mov     [rsp+2C0h+var_254], ebx
0x140001efc  movups  [rbp+1C0h+var_180], xmm0
0x140001f00  mov     [rbp+1C0h+var_220], ebx
0x140001f03  movups  [rbp+1C0h+var_170], xmm0
0x140001f07  call    memset
0x140001f0c  xor     eax, eax
0x140001f0e  mov     [rbp+1C0h+var_228], rbx
0x140001f12  xorps   xmm0, xmm0
0x140001f15  mov     [rbp+1C0h+var_90], ax
0x140001f1c  lea     r9, [rsp+2C0h+ReturnLength]; ReturnLength
0x140001f21  mov     [rbp+1C0h+var_B0], rax
0x140001f28  xor     r8d, r8d; Length
0x140001f2b  mov     [rbp+1C0h+var_A8], al
0x140001f31  xor     edx, edx; ObjectNameInfo
0x140001f33  mov     [rsp+2C0h+psz], rbx
0x140001f38  mov     rcx, r12; Object
0x140001f3b  mov     [rsp+2C0h+var_270], rbx
0x140001f40  movups  [rbp+1C0h+var_A0], xmm0
0x140001f47  mov     edi, ebx
0x140001f49  mov     [rbp+1C0h+Src], rbx
0x140001f4d  mov     r14d, ebx
0x140001f50  mov     [rsp+2C0h+var_260], rbx
0x140001f55  mov     esi, ebx
0x140001f57  mov     [rbp+1C0h+var_218], rbx
0x140001f5b  mov     [rbp+1C0h+var_240], rbx
0x140001f5f  mov     r13d, ebx
0x140001f62  mov     [rbp+1C0h+P], rbx
0x140001f66  mov     [rbp+1C0h+var_200], rbx
0x140001f6a  mov     [rbp+1C0h+var_210], rbx
0x140001f6e  call    cs:__imp_ObQueryNameString
0x140001f75  nop     dword ptr [rax+rax+00h]
0x140001f7a  cmp     eax, 0C0000004h
0x140001f7f  jz      short loc_140001F8E
0x140001f81  mov     ebx, 0C000000Dh
0x140001f86  xor     r15d, r15d
0x140001f89  jmp     loc_1400025EE
0x140001f8e  mov     edx, [rsp+2C0h+ReturnLength]
0x140001f92  mov     ecx, 100h
0x140001f97  mov     r8d, 46555354h
0x140001f9d  call    cs:__imp_ExAllocatePool2
0x140001fa4  nop     dword ptr [rax+rax+00h]
0x140001fa9  mov     [rbp+1C0h+var_1F8], rax
0x140001fad  test    rax, rax
0x140001fb0  jnz     short loc_140001FBC
0x140001fb2  mov     ebx, 0C0000017h
0x140001fb7  jmp     loc_14000258B
0x140001fbc  mov     r8d, [rsp+2C0h+ReturnLength]; Length
0x140001fc1  lea     r9, [rsp+2C0h+ReturnLength]; ReturnLength
0x140001fc6  mov     rdx, rax; ObjectNameInfo
0x140001fc9  mov     rcx, r12; Object
0x140001fcc  call    cs:__imp_ObQueryNameString
0x140001fd3  nop     dword ptr [rax+rax+00h]
0x140001fd8  mov     ebx, eax
0x140001fda  test    eax, eax
0x140001fdc  js      loc_140002579
0x140001fe2  lea     r8, [rsp+2C0h+psz]; unsigned __int16 **
0x140001fe7  xor     edx, edx; enum BUS_QUERY_ID_TYPE
0x140001fe9  mov     rcx, r12; struct _DEVICE_OBJECT *
0x140001fec  call    ?PnpIrpQueryID@@YAJPEAU_DEVICE_OBJECT@@W4BUS_QUERY_ID_TYPE@@PEAPEAG@Z; PnpIrpQueryID(_DEVICE_OBJECT *,BUS_QUERY_ID_TYPE,ushort * *)
0x140001ff1  mov     rdi, [rsp+2C0h+psz]
0x140001ff6  xor     r11d, r11d
0x140001ff9  mov     ebx, eax
0x140001ffb  test    eax, eax
0x140001ffd  js      loc_140002579
0x140002003  mov     [rsp+2C0h+pcchLength], r11
0x140002008  test    rdi, rdi
0x14000200b  jz      loc_1400029D3
0x140002011  lea     r8, [rsp+2C0h+pcchLength]; pcchLength
0x140002016  mov     edx, 7FFFh; cchMax
0x14000201b  mov     rcx, rdi; psz
0x14000201e  call    RtlStringLengthWorkerW
0x140002023  mov     ebx, eax
0x140002025  test    eax, eax
0x140002027  js      loc_140002579
0x14000202d  lea     r8, [rsp+2C0h+var_270]; unsigned __int16 **
0x140002032  mov     rcx, r12; struct _DEVICE_OBJECT *
0x140002035  lea     edx, [r11+1]; enum BUS_QUERY_ID_TYPE
0x140002039  call    ?PnpIrpQueryID@@YAJPEAU_DEVICE_OBJECT@@W4BUS_QUERY_ID_TYPE@@PEAPEAG@Z; PnpIrpQueryID(_DEVICE_OBJECT *,BUS_QUERY_ID_TYPE,ushort * *)
0x14000203e  mov     r14, [rsp+2C0h+var_270]
0x140002043  mov     ebx, eax
0x140002045  test    eax, eax
0x140002047  js      loc_140002579
0x14000204d  lea     r9, [rbp+1C0h+var_238]; unsigned __int64 *
0x140002051  mov     edx, 0FFFFh; unsigned __int64
0x140002056  lea     r8, [rsp+2C0h+var_254]; unsigned int *
0x14000205b  mov     rcx, r14; unsigned __int16 *
0x14000205e  call    ?ValidateMultiStrings@@YAJPEBG_KPEAKPEA_KPEAPEAPEBG@Z; ValidateMultiStrings(ushort const *,unsigned __int64,ulong *,unsigned __int64 *,ushort const * * *)
0x140002063  mov     ebx, eax
0x140002065  test    eax, eax
0x140002067  js      loc_140002579
0x14000206d  lea     r8, [rbp+1C0h+Src]; unsigned __int16 **
0x140002071  mov     edx, 2; enum BUS_QUERY_ID_TYPE
0x140002076  mov     rcx, r12; struct _DEVICE_OBJECT *
0x140002079  call    ?PnpIrpQueryID@@YAJPEAU_DEVICE_OBJECT@@W4BUS_QUERY_ID_TYPE@@PEAPEAG@Z; PnpIrpQueryID(_DEVICE_OBJECT *,BUS_QUERY_ID_TYPE,ushort * *)
0x14000207e  mov     ebx, eax
0x140002080  test    eax, eax
0x140002082  js      loc_140002579
0x140002088  mov     rcx, [rbp+1C0h+Src]; unsigned __int16 *
0x14000208c  lea     r9, [rsp+2C0h+Size]; unsigned __int64 *
0x140002091  lea     r8, [rbp+1C0h+var_220]; unsigned int *
0x140002095  mov     edx, 0FFFFh; unsigned __int64
0x14000209a  call    ?ValidateMultiStrings@@YAJPEBG_KPEAKPEA_KPEAPEAPEBG@Z; ValidateMultiStrings(ushort const *,unsigned __int64,ulong *,unsigned __int64 *,ushort const * * *)
0x14000209f  mov     ebx, eax
0x1400020a1  test    eax, eax
0x1400020a3  js      loc_140002579
0x1400020a9  xor     edx, edx; Val
0x1400020ab  lea     rcx, [rbp+1C0h+var_1F0]; void *
0x1400020af  lea     r8d, [rdx+48h]; Size
0x1400020b3  call    memset
0x1400020b8  or      eax, 0FFFFFFFFh
0x1400020bb  mov     dword ptr [rbp+1C0h+var_80], 10040h
0x1400020c5  mov     dword ptr [rbp+1C0h+var_80+8], eax
0x1400020cb  lea     rdx, [rbp+1C0h+var_1F0]; struct _IO_STACK_LOCATION *
0x1400020cf  mov     dword ptr [rbp+1C0h+var_80+0Ch], eax
0x1400020d5  xor     r8d, r8d; void *
0x1400020d8  lea     rax, [rbp+1C0h+var_80]
0x1400020df  mov     word ptr [rbp+1C0h+var_1F0.MajorFunction], 91Bh
0x1400020e5  mov     qword ptr [rbp+1C0h+var_1F0.Parameters], rax
0x1400020e9  mov     rcx, r12; struct _DEVICE_OBJECT *
0x1400020ec  xor     eax, eax
0x1400020ee  mov     qword ptr [rsp+2C0h+InterfaceProtocol], rax; unsigned __int64 *
0x1400020f3  mov     byte ptr [rsp+2C0h+InterfaceClass], al; char
0x1400020f7  call    ?IopSynchronousCall@@YAJPEAU_DEVICE_OBJECT@@PEAU_IO_STACK_LOCATION@@PEAXJE_KPEA_K@Z; IopSynchronousCall(_DEVICE_OBJECT *,_IO_STACK_LOCATION *,void *,long,uchar,unsigned __int64,unsigned __int64 *)
0x1400020fc  mov     ebx, eax
0x1400020fe  test    eax, eax
0x140002100  js      loc_140002579
0x140002106  test    byte ptr [rbp+1C0h+var_80+4], 40h
0x14000210d  mov     rax, [rsp+2C0h+pcchLength]
0x140002112  lea     rdi, [rax+rax]
0x140002116  jz      short loc_14000217A
0x140002118  lea     r8, [rbp+1C0h+var_218]; unsigned __int16 **
0x14000211c  mov     edx, 3; enum BUS_QUERY_ID_TYPE
0x140002121  mov     rcx, r12; struct _DEVICE_OBJECT *
0x140002124  call    ?PnpIrpQueryID@@YAJPEAU_DEVICE_OBJECT@@W4BUS_QUERY_ID_TYPE@@PEAPEAG@Z; PnpIrpQueryID(_DEVICE_OBJECT *,BUS_QUERY_ID_TYPE,ushort * *)
0x140002129  mov     rsi, [rbp+1C0h+var_218]
0x14000212d  xor     r11d, r11d
0x140002130  mov     ebx, eax
0x140002132  test    eax, eax
0x140002134  js      loc_140002574
0x14000213a  mov     [rsp+2C0h+var_260], rsi
0x14000213f  mov     [rsp+2C0h+pcchLength], r11
0x140002144  test    rsi, rsi
0x140002147  jz      short loc_140002170
0x140002149  lea     r8, [rsp+2C0h+pcchLength]; pcchLength
0x14000214e  mov     edx, 7FFFh; cchMax
0x140002153  mov     rcx, rsi; psz
0x140002156  call    RtlStringLengthWorkerW
0x14000215b  mov     ebx, eax
0x14000215d  test    eax, eax
0x14000215f  js      loc_140002574
0x140002165  mov     rax, [rsp+2C0h+pcchLength]
0x14000216a  lea     r14, [rax+rax]
0x14000216e  jmp     short loc_1400021CD
0x140002170  mov     ebx, 0C000000Dh
0x140002175  jmp     loc_140002574
0x14000217a  lea     rax, [rbp+1C0h+var_228]
0x14000217e  mov     r9d, 1; enum DEVICE_TEXT_TYPE
0x140002184  mov     qword ptr [rsp+2C0h+InterfaceProtocol], rax; unsigned __int64 *
0x140002189  xor     r8d, r8d; unsigned __int16 *
0x14000218c  lea     rax, [rbp+1C0h+var_210]
0x140002190  mov     rdx, r12; struct _DEVICE_OBJECT *
0x140002193  mov     qword ptr [rsp+2C0h+InterfaceSubClass], rax; unsigned __int64
0x140002198  mov     rcx, r15; this
0x14000219b  mov     dword ptr [rsp+2C0h+InterfaceClass], 409h; unsigned int
0x1400021a3  call    ?QueryChildDeviceText@CUsbBusFilter@@AEAAJPEAU_DEVICE_OBJECT@@PEBGW4DEVICE_TEXT_TYPE@@KPEAPEBGPEA_K@Z; CUsbBusFilter::QueryChildDeviceText(_DEVICE_OBJECT *,ushort const *,DEVICE_TEXT_TYPE,ulong,ushort const * *,unsigned __int64 *)
0x1400021a8  xor     r11d, r11d
0x1400021ab  test    eax, eax
0x1400021ad  js      short loc_1400021C2
0x1400021af  mov     rsi, [rbp+1C0h+var_210]
0x1400021b3  mov     r14, [rbp+1C0h+var_228]
0x1400021b7  mov     [rsp+2C0h+var_260], rsi
0x1400021bc  mov     [rbp+1C0h+var_200], r11
0x1400021c0  jmp     short loc_1400021CD
0x1400021c2  mov     rax, [rbp+1C0h+var_210]
0x1400021c6  mov     r14, r11
0x1400021c9  mov     [rbp+1C0h+var_200], rax
0x1400021cd  mov     rcx, [rsp+2C0h+Size]
0x1400021d2  lea     r8, [rbp+1C0h+var_240]
0x1400021d6  mov     rax, [rbp+1C0h+var_238]
0x1400021da  lea     rdx, [rbp+1C0h+var_190]
0x1400021de  sub     rax, 2
0x1400021e2  mov     dword ptr [rbp+1C0h+var_180+4], r11d
0x1400021e6  sub     rcx, 2
0x1400021ea  mov     [rbp+1C0h+var_228], rax
0x1400021ee  mov     [rsp+2C0h+Size], rcx
0x1400021f3  xorps   xmm0, xmm0
0x1400021f6  add     rcx, 4
0x1400021fa  mov     dword ptr [rbp+1C0h+var_190], 38h ; '8'
0x140002201  add     rcx, rax
0x140002204  mov     eax, 1
0x140002209  mov     dword ptr [rbp+1C0h+var_180+8], eax
0x14000220c  add     rcx, r14
0x14000220f  mov     dword ptr [rbp+1C0h+var_180+0Ch], eax
0x140002212  add     rcx, rdi
0x140002215  mov     rax, cs:off_14000F150
0x14000221c  mov     [rbp+1C0h+var_160], rax
0x140002220  mov     rax, [r15]
0x140002223  mov     qword ptr [rbp+1C0h+var_170], rax
0x140002227  mov     eax, [rsp+2C0h+ReturnLength]
0x14000222b  add     rax, 68h ; 'h'
0x14000222f  mov     [rbp+1C0h+var_238], rcx
0x140002233  add     rcx, rax
0x140002236  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x14000223d  mov     qword ptr [rbp+1C0h+var_170+8], rcx
0x140002241  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140002248  movdqu  [rbp+1C0h+var_190+4], xmm0
0x14000224d  mov     rax, [rax+678h]
0x140002254  call    _guard_dispatch_icall
0x140002259  mov     ebx, eax
0x14000225b  xor     eax, eax
0x14000225d  test    ebx, ebx
0x14000225f  js      loc_14000256F
0x140002265  mov     r8, cs:off_14000F150
0x14000226c  mov     rdx, [rbp+1C0h+var_240]
0x140002270  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140002277  mov     [rsp+2C0h+var_278], al
0x14000227b  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140002282  mov     rax, [rax+650h]
0x140002289  call    _guard_dispatch_icall
0x14000228e  mov     rdx, [rsp+2C0h+psz]; Src
0x140002293  mov     r8, rdi; Size
0x140002296  mov     [rsp+2C0h+pcchLength], rax
0x14000229b  lea     rbx, [rax+68h]
0x14000229f  mov     [rax+58h], r13d
0x1400022a3  mov     rcx, rbx; void *
0x1400022a6  call    memmove
0x1400022ab  mov     r13, [rbp+1C0h+var_228]
0x1400022af  mov     r10d, 2Ch ; ','
0x1400022b5  mov     r12, [rsp+2C0h+Size]
0x1400022ba  mov     rsi, [rsp+2C0h+var_270]
0x1400022bf  mov     r15, [rbp+1C0h+Src]
0x1400022c3  shr     rdi, 1
0x1400022c6  mov     [rbx+rdi*2], r10w
0x1400022cb  lea     rbx, [rbx+rdi*2]
0x1400022cf  add     rbx, 2
0x1400022d3  xor     r9d, r9d
0x1400022d6  mov     eax, r9d
0x1400022d9  mov     [rsp+2C0h+var_254], eax
0x1400022dd  test    eax, eax
0x1400022df  jnz     short loc_1400022E9
0x1400022e1  mov     rdx, rsi
0x1400022e4  mov     r8, r13
0x1400022e7  jmp     short loc_1400022EF
0x1400022e9  mov     rdx, r15; Src
0x1400022ec  mov     r8, r12; Size
0x1400022ef  mov     rdi, r8
0x1400022f2  mov     ecx, r9d
0x1400022f5  shr     rdi, 1
0x1400022f8  jz      short loc_140002316
0x1400022fa  mov     eax, ecx
0x1400022fc  cmp     [rdx+rax*2], r9w
0x140002301  jnz     short loc_140002308
0x140002303  mov     [rdx+rax*2], r10w
0x140002308  inc     ecx
0x14000230a  mov     eax, ecx
0x14000230c  cmp     rax, rdi
0x14000230f  jb      short loc_1400022FA
0x140002311  mov     rsi, [rsp+2C0h+var_270]
0x140002316  mov     rcx, rbx; void *
0x140002319  call    memmove
0x14000231e  mov     eax, [rsp+2C0h+var_254]
0x140002322  lea     rbx, [rbx+rdi*2]
0x140002326  mov     edi, 1
0x14000232b  add     eax, edi
0x14000232d  mov     [rsp+2C0h+var_254], eax
0x140002331  lea     r9d, [rdi-1]
0x140002335  lea     r10d, [rdi+2Bh]
0x140002339  cmp     eax, 2
  ... truncated ...
```
