# InstanceCreatePdo

- ea: `0x14002846c`
- end: `0x1400293d9`
- name: `InstanceCreatePdo`
- size: `3949`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x14002b2b0`

## callees

- `0x14000389c`
- `0x1400038cc`
- `0x140003dd0`
- `0x1400052fc`
- `0x1400054fc`
- `0x140005564`
- `0x140017000`
- `0x140017190`
- `0x140017540`
- `0x140027f88`
- `0x140028034`
- `0x14002846c`
- `0x14002f340`

## pseudocode

```c
__int64 __fastcall InstanceCreatePdo(__int64 a1, __int64 a2, unsigned int *a3)
{
  __int64 v4; // rbx
  int v5; // r8d
  __int16 v6; // r12
  int v7; // eax
  NTSTATUS v8; // ebx
  PDEVICE_OBJECT v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  __int64 v12; // r8
  NTSTATUS v13; // eax
  __int64 v14; // r9
  unsigned int *v15; // r13
  NTSTATUS v16; // eax
  __int64 v17; // r9
  __int64 v18; // r9
  int v19; // edx
  int v20; // r8d
  __int64 v21; // rax
  __int64 v22; // r9
  __int64 v23; // r9
  __int64 v24; // r9
  __int64 v25; // r9
  __int64 v26; // rsi
  int v27; // eax
  __int64 v29; // [rsp+20h] [rbp-E0h]
  __int64 v30; // [rsp+28h] [rbp-D8h]
  __int64 v31; // [rsp+30h] [rbp-D0h]
  __int64 v32; // [rsp+38h] [rbp-C8h]
  __int64 v33; // [rsp+40h] [rbp-C0h]
  __int64 v34; // [rsp+48h] [rbp-B8h]
  __int64 v35; // [rsp+50h] [rbp-B0h]
  __int64 v36; // [rsp+58h] [rbp-A8h]
  __int64 v37; // [rsp+60h] [rbp-A0h]
  __int64 v38; // [rsp+70h] [rbp-90h] BYREF
  char v39[8]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v40; // [rsp+80h] [rbp-80h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-78h] BYREF
  __int128 v42; // [rsp+98h] [rbp-68h] BYREF
  _OWORD v43[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v44; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v45; // [rsp+D8h] [rbp-28h]
  __int128 v46; // [rsp+E8h] [rbp-18h]
  __int64 *v47; // [rsp+F8h] [rbp-8h]
  __int64 v48; // [rsp+100h] [rbp+0h]
  __int128 v49; // [rsp+108h] [rbp+8h] BYREF
  __int128 v50; // [rsp+118h] [rbp+18h]
  __int64 (__fastcall *v51)(); // [rsp+128h] [rbp+28h]
  _OWORD v52[4]; // [rsp+130h] [rbp+30h] BYREF
  _QWORD v53[8]; // [rsp+170h] [rbp+70h] BYREF
  _QWORD v54[18]; // [rsp+1B0h] [rbp+B0h] BYREF
  _OWORD v55[3]; // [rsp+240h] [rbp+140h] BYREF
  char v56; // [rsp+270h] [rbp+170h] BYREF

  v48 = a2;
  v4 = a1;
  v38 = a1;
  memset(v54, 0, 0x8Cu);
  memset(v43, 0, 28);
  LODWORD(v47) = 0;
  v40 = 0;
  memset(v55, 0, sizeof(v55));
  v42 = 0;
  memset(v52, 0, 60);
  v44 = 0;
  v45 = 0;
  v46 = 0;
  memset(v53, 0, sizeof(v53));
  *(_QWORD *)&DestinationString.Length = 5898240;
  v51 = 0;
  v39[0] = 8;
  DestinationString.Buffer = (wchar_t *)&v56;
  v49 = 0;
  v50 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF__guid__guid_D(WPP_GLOBAL_Control->AttachedDevice, (_DWORD)a3 + 16, v5, (_DWORD)a3, (__int64)(a3 + 4));
    v4 = v38;
  }
  v6 = *((_WORD *)a3 + 23);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01033 + 528))(WdfDriverGlobals, v4, 42);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01033 + 488))(WdfDriverGlobals, v38, 3);
  if ( (a3[10] & 1) == 0 && !v6 )
  {
LABEL_20:
    memset(v52, 0, sizeof(v52));
    if ( WdfClientVersionHigherThanFramework )
    {
      if ( (unsigned int)WdfStructureCount <= 0x28 )
        LODWORD(v52[0]) = -1;
      else
        LODWORD(v52[0]) = *(_DWORD *)(WdfStructures + 320);
    }
    else
    {
      LODWORD(v52[0]) = 64;
    }
    *(_QWORD *)&v52[1] = InstanceDeviceResourceRequirementsQuery;
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _OWORD *))(WdfFunctions_01033 + 1688))(
      WdfDriverGlobals,
      v38,
      v52);
    if ( v6 )
    {
      v13 = RtlUnicodeStringPrintf(&DestinationString, L"VMBUS\\SUBCHANNEL");
    }
    else
    {
      LODWORD(v29) = *((unsigned __int16 *)a3 + 3);
      v13 = RtlUnicodeStringPrintf(
              &DestinationString,
              L"VMBUS\\{%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}",
              *a3,
              *((unsigned __int16 *)a3 + 2),
              v29,
              *((unsigned __int8 *)a3 + 8),
              *((unsigned __int8 *)a3 + 9),
              *((unsigned __int8 *)a3 + 10),
              *((unsigned __int8 *)a3 + 11),
              *((unsigned __int8 *)a3 + 12),
              *((unsigned __int8 *)a3 + 13),
              *((unsigned __int8 *)a3 + 14),
              *((unsigned __int8 *)a3 + 15));
    }
    v8 = v13;
    if ( v13 < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        return (unsigned int)v8;
      }
      v10 = 23;
      goto LABEL_18;
    }
    v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *))(WdfFunctions_01033 + 1696))(
           WdfDriverGlobals,
           v38,
           &DestinationString);
    if ( v8 < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        return (unsigned int)v8;
      }
      v10 = 24;
      goto LABEL_18;
    }
    v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *))(WdfFunctions_01033 + 1712))(
           WdfDriverGlobals,
           v38,
           &DestinationString);
    if ( v8 < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        return (unsigned int)v8;
      }
      v10 = 25;
      goto LABEL_18;
    }
    v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *))(WdfFunctions_01033 + 1720))(
           WdfDriverGlobals,
           v38,
           &DestinationString);
    if ( v8 < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        return (unsigned int)v8;
      }
      v10 = 26;
      goto LABEL_18;
    }
    if ( v6 )
      goto LABEL_59;
    LODWORD(v37) = *((unsigned __int8 *)a3 + 31);
    LODWORD(v36) = *((unsigned __int8 *)a3 + 30);
    LODWORD(v35) = *((unsigned __int8 *)a3 + 29);
    LODWORD(v34) = *((unsigned __int8 *)a3 + 28);
    LODWORD(v33) = *((unsigned __int8 *)a3 + 27);
    LODWORD(v32) = *((unsigned __int8 *)a3 + 26);
    LODWORD(v31) = *((unsigned __int8 *)a3 + 25);
    LODWORD(v30) = *((unsigned __int8 *)a3 + 24);
    LODWORD(v29) = *((unsigned __int16 *)a3 + 11);
    v8 = RtlUnicodeStringPrintf(
           &DestinationString,
           L"VMBUS\\{%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}",
           a3[4],
           *((unsigned __int16 *)a3 + 10),
           v29,
           v30,
           v31,
           v32,
           v33,
           v34,
           v35,
           v36,
           v37);
    if ( v8 < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        return (unsigned int)v8;
      }
      v10 = 27;
      goto LABEL_18;
    }
    v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *))(WdfFunctions_01033 + 1712))(
           WdfDriverGlobals,
           v38,
           &DestinationString);
    if ( v8 >= 0 )
    {
LABEL_59:
      v14 = *((unsigned __int16 *)a3 + 10);
      v15 = a3 + 4;
      LODWORD(v37) = *((unsigned __int8 *)a3 + 31);
      LODWORD(v36) = *((unsigned __int8 *)a3 + 30);
      LODWORD(v35) = *((unsigned __int8 *)a3 + 29);
      LODWORD(v34) = *((unsigned __int8 *)a3 + 28);
      LODWORD(v33) = *((unsigned __int8 *)a3 + 27);
      LODWORD(v32) = *((unsigned __int8 *)a3 + 26);
      LODWORD(v31) = *((unsigned __int8 *)a3 + 25);
      LODWORD(v30) = *((unsigned __int8 *)a3 + 24);
      LODWORD(v29) = *((unsigned __int16 *)a3 + 11);
      if ( v6 )
        v16 = RtlUnicodeStringPrintf(
                &DestinationString,
                L"{%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}-%04x",
                *v15,
                v14,
                v29,
                v30,
                v31,
                v32,
                v33,
                v34,
                v35,
                v36,
                v37,
                *((unsigned __int16 *)a3 + 23));
      else
        v16 = RtlUnicodeStringPrintf(
                &DestinationString,
                L"{%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}",
                *v15,
                v14,
                v29,
                v30,
                v31,
                v32,
                v33,
                v34,
                v35,
                v36,
                v37);
      v8 = v16;
      if ( v16 >= 0 )
      {
        v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *))(WdfFunctions_01033
                                                                                               + 1704))(
               WdfDriverGlobals,
               v38,
               &DestinationString);
        if ( v8 >= 0 )
        {
          v8 = InstanceFileInit(v38);
          if ( v8 >= 0 )
          {
            memset(v54, 0, sizeof(v54));
            if ( WdfClientVersionHigherThanFramework )
            {
              if ( (unsigned int)WdfStructureCount <= 0x29 )
                LODWORD(v54[0]) = -1;
              else
                LODWORD(v54[0]) = *(_DWORD *)(WdfStructures + 328);
            }
            else
            {
              LODWORD(v54[0]) = 144;
            }
            v54[5] = InstancePdoPrepareHardware;
            v54[6] = InstancePdoReleaseHardware;
            v54[10] = InstancePdoSelfManagedIOSuspend;
            v54[11] = InstancePdoSelfManagedIORestart;
            v54[7] = InstancePdoSelfManagedIoCleanup;
            (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD *))(WdfFunctions_01033 + 440))(
              WdfDriverGlobals,
              v38,
              v54);
            if ( (a3[10] & 0x11) == 0x11 )
              (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01033 + 512))(WdfDriverGlobals, v38);
            else
              (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01033 + 504))(WdfDriverGlobals, v38);
            if ( (a3[10] & 0x10) != 0 )
            {
              LOBYTE(v17) = 4;
              v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 (__fastcall *)(__int64, __int64), __int64, _QWORD, _DWORD))(WdfFunctions_01033 + 584))(
                     WdfDriverGlobals,
                     v38,
                     InstancePdoReadWritePreprocess,
                     v17,
                     0,
                     0);
              if ( v8 < 0 )
                return (unsigned int)v8;
              LOBYTE(v18) = 3;
              v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 (__fastcall *)(__int64, __int64), __int64, _QWORD, _DWORD))(WdfFunctions_01033 + 584))(
                     WdfDriverGlobals,
                     v38,
                     InstancePdoReadWritePreprocess,
                     v18,
                     0,
                     0);
              if ( v8 < 0 )
                return (unsigned int)v8;
            }
            v44 = 0;
            v47 = 0;
            v45 = 0;
            v46 = 0;
            if ( WdfClientVersionHigherThanFramework )
            {
              if ( (unsigned int)WdfStructureCount <= 0x26 )
                LODWORD(v44) = -1;
              else
                LODWORD(v44) = *(_DWORD *)(WdfStructures + 304);
            }
            else
            {
              LODWORD(v44) = 56;
            }
            v47 = off_14001C160;
            *((_QWORD *)&v45 + 1) = 0x100000001LL;
            *((_QWORD *)&v44 + 1) = InstancePdoCleanup;
            LOBYTE(v17) = 27;
            v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 (__fastcall *)(__int64, IRP *), __int64, char *, int))(WdfFunctions_01033 + 584))(
                   WdfDriverGlobals,
                   v38,
                   VmBusQueryInterfaceIrpPreprocess,
                   v17,
                   v39,
                   1);
            if ( v8 >= 0 )
            {
              v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64 *, __int128 *, __int64 *))(WdfFunctions_01033 + 600))(
                     WdfDriverGlobals,
                     &v38,
                     &v44,
                     &v40);
              if ( v8 >= 0 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                {
                  WPP_SF__guid__guid_q(WPP_GLOBAL_Control->AttachedDevice, v19, v20, (_DWORD)a3, (__int64)(a3 + 4));
                }
                v21 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01033 + 248))(
                        WdfDriverGlobals,
                        v40);
                LOBYTE(v22) = 1;
                *(_DWORD *)(v21 + 48) &= ~0x2000u;
                (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, __int64))(WdfFunctions_01033 + 392))(
                  WdfDriverGlobals,
                  v40,
                  1,
                  v22);
                LOBYTE(v23) = 1;
                (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, __int64))(WdfFunctions_01033 + 392))(
                  WdfDriverGlobals,
                  v40,
                  2,
                  v23);
                LOBYTE(v24) = 1;
                (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, __int64))(WdfFunctions_01033 + 392))(
                  WdfDriverGlobals,
                  v40,
                  3,
                  v24);
                LOBYTE(v25) = 1;
                (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, __int64))(WdfFunctions_01033 + 392))(
                  WdfDriverGlobals,
                  v40,
                  6,
                  v25);
                v26 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
                        WdfDriverGlobals,
                        v40,
                        off_14001C160);
                v8 = InstanceContextInit(v26, (_DWORD)a3, v48, v40, v40);
                if ( v8 < 0 )
                  return (unsigned int)v8;
                if ( (a3[10] & 1) == 0 && !v6 )
                  goto LABEL_119;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                {
                  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_2ff8b0bb8e893dc1ecd1a3d57a9e5fd9_Traceguids);
                }
                v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, unsigned int *, _QWORD))(WdfFunctions_01033 + 616))(
                       WdfDriverGlobals,
                       v40,
                       a3,
                       0);
                if ( v8 < 0 )
                {
                  v9 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                    || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                  {
                    return (unsigned int)v8;
                  }
                  v10 = 36;
                }
                else
                {
LABEL_119:
                  memset(v55, 0, sizeof(v55));
                  if ( WdfClientVersionHigherThanFramework )
                  {
                    if ( (unsigned int)WdfStructureCount <= 0xC )
                      LODWORD(v55[0]) = -1;
                    else
                      LODWORD(v55[0]) = *(_DWORD *)(WdfStructures + 96);
                  }
                  else
                  {
                    LODWORD(v55[0]) = 48;
                  }
                  *(__m128i *)((char *)v55 + 4) = _mm_load_si128((const __m128i *)&_xmm);
                  HIDWORD(v55[2]) = -1;
                  *(_OWORD *)((char *)&v55[1] + 8) = *(_OWORD *)((char *)v55 + 4);
                  DWORD1(v55[1]) = 1;
                  if ( (a3[10] & 1) != 0 || v6 )
                  {
                    v27 = DWORD1(v55[2]);
                    HIDWORD(v55[1]) = 1;
                    if ( v6 )
                      v27 = 1;
                    DWORD1(v55[2]) = v27;
                  }
                  DWORD2(v55[2]) = *v15;
                  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _OWORD *))(WdfFunctions_01033 + 664))(
                    WdfDriverGlobals,
                    v40,
                    v55);
                  v8 = InstanceIoctlInit(v40);
                  if ( v8 < 0 )
                    return (unsigned int)v8;
                  v53[3] = BusPdoDereferenceInterface;
                  LODWORD(v53[0]) = 65600;
                  v53[1] = v26 + 288;
                  v53[4] = BusPdoTranslateBusAddress;
                  v53[2] = BusPdoReferenceInterface;
                  v53[5] = &BusPdoGetDmaAdapter;
                  v53[6] = BusPdoSetBusData;
                  v53[7] = BusPdoSetBusData;
                  v42 = 0;
                  memset(v43, 0, sizeof(v43));
                  if ( WdfClientVersionHigherThanFramework )
                  {
                    if ( (unsigned int)WdfStructureCount <= 0x2D )
                      LODWORD(v42) = -1;
                    else
                      LODWORD(v42) = *(_DWORD *)(WdfStructures + 360);
                  }
                  else
                  {
                    LODWORD(v42) = 48;
                  }
                  *((_QWORD *)&v42 + 1) = v53;
                  *(_QWORD *)&v43[0] = &GUID_BUS_INTERFACE_STANDARD;
                  *(_QWORD *)&v43[1] = 0;
                  v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int128 *))(WdfFunctions_01033 + 1824))(
                         WdfDriverGlobals,
                         v40,
                         &v42);
                  if ( v8 >= 0 )
                  {
                    if ( v6 )
                      goto LABEL_157;
                    *((_QWORD *)&v50 + 1) = BusPdoDereferenceInterface;
                    LODWORD(v49) = 65576;
                    v51 = InstancePdoGetLocationStrings;
                    *((_QWORD *)&v49 + 1) = v26 + 288;
                    *(_QWORD *)&v50 = BusPdoReferenceInterface;
                    v42 = 0;
                    memset(v43, 0, sizeof(v43));
                    if ( WdfClientVersionHigherThanFramework )
                      LODWORD(v42) = (unsigned int)WdfStructureCount <= 0x2D ? -1 : *(_DWORD *)(WdfStructures + 360);
                    else
                      LODWORD(v42) = 48;
                    *((_QWORD *)&v42 + 1) = &v49;
                    *(_QWORD *)&v43[0] = &GUID_PNP_LOCATION_INTERFACE;
                    *(_QWORD *)&v43[1] = 0;
                    v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int128 *))(WdfFunctions_01033 + 1824))(
                           WdfDriverGlobals,
                           v40,
                           &v42);
                    if ( v8 >= 0 )
                    {
LABEL_157:
                      if ( (a3[10] & 0x10) == 0 )
                        return 0;
                      v8 = PipeCreate(0, v26 + 296);
                      if ( v8 >= 0 )
                        return 0;
                      return (unsigned int)v8;
                    }
                    v9 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                    {
                      return (unsigned int)v8;
                    }
                    v10 = 38;
                  }
                  else
                  {
                    v9 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                    {
                      return (unsigned int)v8;
                    }
                    v10 = 37;
                  }
                }
              }
              else
              {
                v9 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                  || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                {
                  return (unsigned int)v8;
                }
                v10 = 33;
              }
            }
            else
            {
              v9 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
              {
                return (unsigned int)v8;
              }
              v10 = 32;
            }
          }
          else
          {
            v9 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
            {
              return (unsigned int)v8;
            }
            v10 = 31;
          }
        }
        else
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            return (unsigned int)v8;
          }
          v10 = 30;
        }
      }
      else
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          return (unsigned int)v8;
        }
        v10 = 29;
      }
    }
    else
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        return (unsigned int)v8;
      }
      v10 = 28;
    }
LABEL_18:
    v11 = (unsigned int)v8;
    goto LABEL_12;
  }
  v7 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, const UNICODE_STRING *))(WdfFunctions_01033 + 544))(
         WdfDriverGlobals,
         v38,
         &SDDL_DEVOBJ_SYS_ALL_ADM_ALL);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, GUID *))(WdfFunctions_01033 + 1744))(
           WdfDriverGlobals,
           v38,
           &GUID_BUS_VMBUS);
    if ( v8 < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        return (unsigned int)v8;
      }
      v10 = 22;
      goto LABEL_18;
    }
    LOBYTE(v12) = 1;
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01033 + 496))(
      WdfDriverGlobals,
      v38,
      v12);
    goto LABEL_20;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v10 = 21;
    v11 = (unsigned int)v7;
LABEL_12:
    WPP_SF_d(v9->AttachedDevice, v10, WPP_2ff8b0bb8e893dc1ecd1a3d57a9e5fd9_Traceguids, v11);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14002846c  mov     [rsp-8+arg_18], rbx
0x140028471  push    rbp
0x140028472  push    rsi
0x140028473  push    rdi
0x140028474  push    r12
0x140028476  push    r13
0x140028478  push    r14
0x14002847a  push    r15
0x14002847c  lea     rbp, [rsp-1E0h]
0x140028484  sub     rsp, 2E0h
0x14002848b  mov     rax, cs:__security_cookie
0x140028492  xor     rax, rsp
0x140028495  mov     [rbp+210h+var_40], rax
0x14002849c  mov     r15, r8
0x14002849f  mov     [rbp+210h+var_210], rdx
0x1400284a3  mov     rbx, rcx
0x1400284a6  mov     [rsp+310h+var_2A0], rcx
0x1400284ab  xor     eax, eax
0x1400284ad  lea     rcx, [rbp+210h+var_160]; void *
0x1400284b4  xor     edx, edx; Val
0x1400284b6  mov     [rbp+210h+var_15C], eax
0x1400284bc  mov     r8d, 8Ch; Size
0x1400284c2  call    memset
0x1400284c7  xorps   xmm0, xmm0
0x1400284ca  lea     rcx, [rbp+210h+var_1A0]; void *
0x1400284ce  xor     eax, eax
0x1400284d0  xor     r14d, r14d
0x1400284d3  movups  [rbp+210h+var_268], xmm0
0x1400284d7  xor     edx, edx; Val
0x1400284d9  mov     dword ptr [rbp+210h+var_218], eax
0x1400284dc  movups  [rbp+210h+var_1C0], xmm0
0x1400284e0  lea     esi, [rax+40h]
0x1400284e3  mov     [rbp+210h+var_290], r14
0x1400284e7  mov     r8d, esi; Size
0x1400284ea  movups  [rbp+210h+var_D0], xmm0
0x1400284f1  movups  [rbp+210h+var_C0], xmm0
0x1400284f8  movups  [rbp+210h+var_B0], xmm0
0x1400284ff  movups  [rbp+210h+var_278], xmm0
0x140028503  movups  [rbp+210h+var_268+0Ch], xmm0
0x140028507  movups  [rbp+210h+var_1E0], xmm0
0x14002850b  movups  [rbp+210h+var_1D0], xmm0
0x14002850f  movups  [rbp+210h+var_1C0+0Ch], xmm0
0x140028513  movups  [rbp+210h+var_248], xmm0
0x140028517  movups  [rbp+210h+var_238], xmm0
0x14002851b  movups  [rbp+210h+var_228], xmm0
0x14002851f  call    memset
0x140028524  xor     eax, eax
0x140028526  mov     qword ptr [rbp+210h+DestinationString.Length], 5A0000h
0x14002852e  xorps   xmm0, xmm0
0x140028531  mov     [rbp+210h+var_1E8], rax
0x140028535  lea     rax, [rbp+210h+var_A0]
0x14002853c  mov     [rsp+310h+var_298], 8
0x140028541  mov     [rbp+210h+DestinationString.Buffer], rax
0x140028545  movups  [rbp+210h+var_208], xmm0
0x140028549  movups  [rbp+210h+var_1F8], xmm0
0x14002854d  mov     rcx, cs:WPP_GLOBAL_Control
0x140028554  lea     rdi, WPP_GLOBAL_Control
0x14002855b  lea     r13d, [r14+1]
0x14002855f  cmp     rcx, rdi
0x140028562  jz      short loc_140028595
0x140028564  mov     eax, [rcx+2Ch]
0x140028567  test    r13b, al
0x14002856a  jz      short loc_140028595
0x14002856c  cmp     byte ptr [rcx+29h], 5
0x140028570  jb      short loc_140028595
0x140028572  movzx   eax, word ptr [r15+28h]
0x140028577  lea     rdx, [r15+10h]
0x14002857b  mov     rcx, [rcx+18h]
0x14002857f  mov     r9, r15
0x140028582  mov     dword ptr [rsp+310h+var_2E8], eax
0x140028586  mov     [rsp+310h+var_2F0], rdx
0x14002858b  call    WPP_SF__guid__guid_D
0x140028590  mov     rbx, [rsp+310h+var_2A0]
0x140028595  mov     rax, cs:WdfFunctions_01033
0x14002859c  mov     r8d, 2Ah ; '*'
0x1400285a2  mov     rcx, cs:WdfDriverGlobals
0x1400285a9  mov     rdx, rbx
0x1400285ac  movzx   r12d, word ptr [r15+2Eh]
0x1400285b1  mov     rax, [rax+210h]
0x1400285b8  call    _guard_dispatch_icall
0x1400285bd  mov     rax, cs:WdfFunctions_01033
0x1400285c4  mov     r8d, 3
0x1400285ca  mov     rdx, [rsp+310h+var_2A0]
0x1400285cf  mov     rcx, cs:WdfDriverGlobals
0x1400285d6  mov     rax, [rax+1E8h]
0x1400285dd  call    _guard_dispatch_icall
0x1400285e2  test    [r15+28h], r13b
0x1400285e6  jnz     short loc_1400285F2
0x1400285e8  test    r12w, r12w
0x1400285ec  jz      loc_1400286DF
0x1400285f2  mov     rax, cs:WdfFunctions_01033
0x1400285f9  lea     r8, SDDL_DEVOBJ_SYS_ALL_ADM_ALL
0x140028600  mov     rdx, [rsp+310h+var_2A0]
0x140028605  mov     rcx, cs:WdfDriverGlobals
0x14002860c  mov     rax, [rax+220h]
0x140028613  call    _guard_dispatch_icall
0x140028618  mov     ebx, eax
0x14002861a  test    eax, eax
0x14002861c  jns     short loc_140028661
0x14002861e  mov     rcx, cs:WPP_GLOBAL_Control
0x140028625  cmp     rcx, rdi
0x140028628  jz      loc_1400293AC
0x14002862e  mov     edx, [rcx+2Ch]
0x140028631  test    r13b, dl
0x140028634  jz      loc_1400293AC
0x14002863a  cmp     byte ptr [rcx+29h], 2
0x14002863e  jb      loc_1400293AC
0x140028644  mov     edx, 15h
0x140028649  mov     r9d, eax
0x14002864c  mov     rcx, [rcx+18h]
0x140028650  lea     r8, WPP_2ff8b0bb8e893dc1ecd1a3d57a9e5fd9_Traceguids
0x140028657  call    WPP_SF_d
0x14002865c  jmp     loc_1400293AC
0x140028661  mov     rax, cs:WdfFunctions_01033
0x140028668  lea     r8, GUID_BUS_VMBUS
0x14002866f  mov     rdx, [rsp+310h+var_2A0]
0x140028674  mov     rcx, cs:WdfDriverGlobals
0x14002867b  mov     rax, [rax+6D0h]
0x140028682  call    _guard_dispatch_icall
0x140028687  mov     ebx, eax
0x140028689  test    eax, eax
0x14002868b  jns     short loc_1400286BD
0x14002868d  mov     rcx, cs:WPP_GLOBAL_Control
0x140028694  cmp     rcx, rdi
0x140028697  jz      loc_1400293AC
0x14002869d  mov     eax, [rcx+2Ch]
0x1400286a0  test    r13b, al
0x1400286a3  jz      loc_1400293AC
0x1400286a9  cmp     byte ptr [rcx+29h], 2
0x1400286ad  jb      loc_1400293AC
0x1400286b3  mov     edx, 16h
0x1400286b8  mov     r9d, ebx
0x1400286bb  jmp     short loc_14002864C
0x1400286bd  mov     rax, cs:WdfFunctions_01033
0x1400286c4  mov     r8b, r13b
0x1400286c7  mov     rdx, [rsp+310h+var_2A0]
0x1400286cc  mov     rcx, cs:WdfDriverGlobals
0x1400286d3  mov     rax, [rax+1F0h]
0x1400286da  call    _guard_dispatch_icall
0x1400286df  mov     r8, rsi; Size
0x1400286e2  lea     rcx, [rbp+210h+var_1E0]; void *
0x1400286e6  xor     edx, edx; Val
0x1400286e8  call    memset
0x1400286ed  cmp     cs:WdfClientVersionHigherThanFramework, r14b
0x1400286f4  jz      short loc_14002871A
0x1400286f6  cmp     cs:WdfStructureCount, 28h ; '('
0x1400286fd  jbe     short loc_140028711
0x1400286ff  mov     rax, cs:WdfStructures
0x140028706  mov     ecx, [rax+140h]
0x14002870c  mov     dword ptr [rbp+210h+var_1E0], ecx
0x14002870f  jmp     short loc_14002871D
0x140028711  mov     dword ptr [rbp+210h+var_1E0], 0FFFFFFFFh
0x140028718  jmp     short loc_14002871D
0x14002871a  mov     dword ptr [rbp+210h+var_1E0], esi
0x14002871d  mov     rdx, [rsp+310h+var_2A0]
0x140028722  lea     rax, InstanceDeviceResourceRequirementsQuery
0x140028729  mov     rcx, cs:WdfDriverGlobals
0x140028730  lea     r8, [rbp+210h+var_1E0]
0x140028734  mov     qword ptr [rbp+210h+var_1D0], rax
0x140028738  mov     rax, cs:WdfFunctions_01033
0x14002873f  mov     rax, [rax+698h]
0x140028746  call    _guard_dispatch_icall
0x14002874b  test    r12w, r12w
0x14002874f  jz      short loc_140028763
0x140028751  lea     rdx, aVmbusSubchanne; "VMBUS\\SUBCHANNEL"
0x140028758  lea     rcx, [rbp+210h+DestinationString]; DestinationString
0x14002875c  call    RtlUnicodeStringPrintf
0x140028761  jmp     short loc_1400287D6
0x140028763  movzx   ecx, byte ptr [r15+0Eh]
0x140028768  movzx   edx, byte ptr [r15+0Dh]
0x14002876d  movzx   r8d, byte ptr [r15+0Ch]
0x140028772  movzx   eax, byte ptr [r15+0Fh]
0x140028777  movzx   r10d, byte ptr [r15+0Bh]
0x14002877c  movzx   r11d, byte ptr [r15+0Ah]
0x140028781  movzx   ebx, byte ptr [r15+9]
0x140028786  movzx   edi, byte ptr [r15+8]
0x14002878b  movzx   esi, word ptr [r15+6]
0x140028790  movzx   r9d, word ptr [r15+4]
0x140028795  mov     dword ptr [rsp+310h+var_2B0], eax
0x140028799  mov     dword ptr [rsp+310h+var_2B8], ecx
0x14002879d  lea     rcx, [rbp+210h+DestinationString]; DestinationString
0x1400287a1  mov     dword ptr [rsp+310h+var_2C0], edx
0x1400287a5  lea     rdx, aVmbus08lx04x04; "VMBUS\\{%08lx-%04x-%04x-%02x%02x-%02x%0"...
0x1400287ac  mov     dword ptr [rsp+310h+var_2C8], r8d
0x1400287b1  mov     r8d, [r15]
0x1400287b4  mov     dword ptr [rsp+310h+var_2D0], r10d
0x1400287b9  mov     dword ptr [rsp+310h+var_2D8], r11d
0x1400287be  mov     dword ptr [rsp+310h+var_2E0], ebx
0x1400287c2  mov     dword ptr [rsp+310h+var_2E8], edi
0x1400287c6  mov     dword ptr [rsp+310h+var_2F0], esi
0x1400287ca  call    RtlUnicodeStringPrintf
0x1400287cf  lea     rdi, WPP_GLOBAL_Control
0x1400287d6  mov     ebx, eax
0x1400287d8  test    eax, eax
0x1400287da  jns     short loc_14002880C
0x1400287dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400287e3  cmp     rcx, rdi
0x1400287e6  jz      loc_1400293AC
0x1400287ec  mov     eax, [rcx+2Ch]
0x1400287ef  test    r13b, al
0x1400287f2  jz      loc_1400293AC
0x1400287f8  cmp     byte ptr [rcx+29h], 2
0x1400287fc  jb      loc_1400293AC
0x140028802  mov     edx, 17h
0x140028807  jmp     loc_1400286B8
0x14002880c  mov     rax, cs:WdfFunctions_01033
0x140028813  lea     r8, [rbp+210h+DestinationString]
0x140028817  mov     rdx, [rsp+310h+var_2A0]
0x14002881c  mov     rcx, cs:WdfDriverGlobals
0x140028823  mov     rax, [rax+6A0h]
0x14002882a  call    _guard_dispatch_icall
0x14002882f  mov     ebx, eax
0x140028831  test    eax, eax
0x140028833  jns     short loc_140028865
0x140028835  mov     rcx, cs:WPP_GLOBAL_Control
0x14002883c  cmp     rcx, rdi
0x14002883f  jz      loc_1400293AC
0x140028845  mov     eax, [rcx+2Ch]
0x140028848  test    r13b, al
0x14002884b  jz      loc_1400293AC
0x140028851  cmp     byte ptr [rcx+29h], 2
0x140028855  jb      loc_1400293AC
0x14002885b  mov     edx, 18h
0x140028860  jmp     loc_1400286B8
0x140028865  mov     rax, cs:WdfFunctions_01033
0x14002886c  lea     r8, [rbp+210h+DestinationString]
0x140028870  mov     rdx, [rsp+310h+var_2A0]
0x140028875  mov     rcx, cs:WdfDriverGlobals
0x14002887c  mov     rax, [rax+6B0h]
0x140028883  call    _guard_dispatch_icall
0x140028888  mov     ebx, eax
0x14002888a  test    eax, eax
0x14002888c  jns     short loc_1400288BE
0x14002888e  mov     rcx, cs:WPP_GLOBAL_Control
0x140028895  cmp     rcx, rdi
0x140028898  jz      loc_1400293AC
0x14002889e  mov     eax, [rcx+2Ch]
0x1400288a1  test    r13b, al
0x1400288a4  jz      loc_1400293AC
0x1400288aa  cmp     byte ptr [rcx+29h], 2
0x1400288ae  jb      loc_1400293AC
0x1400288b4  mov     edx, 19h
0x1400288b9  jmp     loc_1400286B8
0x1400288be  mov     rax, cs:WdfFunctions_01033
0x1400288c5  lea     r8, [rbp+210h+DestinationString]
0x1400288c9  mov     rdx, [rsp+310h+var_2A0]
0x1400288ce  mov     rcx, cs:WdfDriverGlobals
0x1400288d5  mov     rax, [rax+6B8h]
0x1400288dc  call    _guard_dispatch_icall
0x1400288e1  mov     ebx, eax
0x1400288e3  test    eax, eax
0x1400288e5  jns     short loc_140028917
0x1400288e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400288ee  cmp     rcx, rdi
0x1400288f1  jz      loc_1400293AC
0x1400288f7  mov     eax, [rcx+2Ch]
0x1400288fa  test    r13b, al
0x1400288fd  jz      loc_1400293AC
0x140028903  cmp     byte ptr [rcx+29h], 2
0x140028907  jb      loc_1400293AC
0x14002890d  mov     edx, 1Ah
0x140028912  jmp     loc_1400286B8
0x140028917  test    r12w, r12w
0x14002891b  jnz     loc_140028A2E
0x140028921  movzx   ecx, byte ptr [r15+1Eh]
0x140028926  lea     rdx, aVmbus08lx04x04; "VMBUS\\{%08lx-%04x-%04x-%02x%02x-%02x%0"...
0x14002892d  movzx   r8d, byte ptr [r15+1Dh]
0x140028932  movzx   eax, byte ptr [r15+1Fh]
0x140028937  movzx   r10d, byte ptr [r15+1Ch]
0x14002893c  movzx   r11d, byte ptr [r15+1Bh]
0x140028941  movzx   ebx, byte ptr [r15+1Ah]
0x140028946  movzx   edi, byte ptr [r15+19h]
0x14002894b  movzx   esi, byte ptr [r15+18h]
0x140028950  movzx   r14d, word ptr [r15+16h]
0x140028955  movzx   r9d, word ptr [r15+14h]
0x14002895a  mov     dword ptr [rsp+310h+var_2B0], eax
0x14002895e  mov     dword ptr [rsp+310h+var_2B8], ecx
0x140028962  lea     rcx, [rbp+210h+DestinationString]; DestinationString
0x140028966  mov     dword ptr [rsp+310h+var_2C0], r8d
0x14002896b  mov     r8d, [r15+10h]
0x14002896f  mov     dword ptr [rsp+310h+var_2C8], r10d
0x140028974  mov     dword ptr [rsp+310h+var_2D0], r11d
0x140028979  mov     dword ptr [rsp+310h+var_2D8], ebx
0x14002897d  mov     dword ptr [rsp+310h+var_2E0], edi
0x140028981  mov     dword ptr [rsp+310h+var_2E8], esi
0x140028985  mov     dword ptr [rsp+310h+var_2F0], r14d
0x14002898a  call    RtlUnicodeStringPrintf
0x14002898f  xor     r14d, r14d
0x140028992  mov     ebx, eax
0x140028994  test    eax, eax
0x140028996  jns     short loc_1400289CE
0x140028998  mov     rcx, cs:WPP_GLOBAL_Control
0x14002899f  lea     rax, WPP_GLOBAL_Control
0x1400289a6  cmp     rcx, rax
0x1400289a9  jz      loc_1400293AC
0x1400289af  mov     eax, [rcx+2Ch]
0x1400289b2  test    r13b, al
0x1400289b5  jz      loc_1400293AC
0x1400289bb  cmp     byte ptr [rcx+29h], 2
0x1400289bf  jb      loc_1400293AC
  ... truncated ...
```
