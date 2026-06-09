# InstanceCreatePdo

- ea: `0x14002841c`
- end: `0x140029389`
- name: `InstanceCreatePdo`
- size: `3949`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x14002b260`

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
- `0x140027f38`
- `0x140027fe4`
- `0x14002841c`
- `0x14002f2f0`

## pseudocode

```c
__int64 __fastcall InstanceCreatePdo(__int64 a1, __int64 a2, unsigned int *a3)
{
  __int64 v4; // rbx
  int v5; // r8d
  __int16 v6; // r12
  int v7; // eax
  int v8; // ebx
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
  __int64 (__fastcall *v51)(__int64, wchar_t **); // [rsp+128h] [rbp+28h]
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
                  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_9bc149055a283eb2988b2e39efb7d62e_Traceguids);
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
                      v8 = PipeCreate(0, (KSPIN_LOCK **)(v26 + 296));
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
    WPP_SF_d(v9->AttachedDevice, v10, WPP_9bc149055a283eb2988b2e39efb7d62e_Traceguids, v11);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14002841c  mov     [rsp-8+arg_18], rbx
0x140028421  push    rbp
0x140028422  push    rsi
0x140028423  push    rdi
0x140028424  push    r12
0x140028426  push    r13
0x140028428  push    r14
0x14002842a  push    r15
0x14002842c  lea     rbp, [rsp-1E0h]
0x140028434  sub     rsp, 2E0h
0x14002843b  mov     rax, cs:__security_cookie
0x140028442  xor     rax, rsp
0x140028445  mov     [rbp+210h+var_40], rax
0x14002844c  mov     r15, r8
0x14002844f  mov     [rbp+210h+var_210], rdx
0x140028453  mov     rbx, rcx
0x140028456  mov     [rsp+310h+var_2A0], rcx
0x14002845b  xor     eax, eax
0x14002845d  lea     rcx, [rbp+210h+var_160]; void *
0x140028464  xor     edx, edx; Val
0x140028466  mov     [rbp+210h+var_15C], eax
0x14002846c  mov     r8d, 8Ch; Size
0x140028472  call    memset
0x140028477  xorps   xmm0, xmm0
0x14002847a  lea     rcx, [rbp+210h+var_1A0]; void *
0x14002847e  xor     eax, eax
0x140028480  xor     r14d, r14d
0x140028483  movups  [rbp+210h+var_268], xmm0
0x140028487  xor     edx, edx; Val
0x140028489  mov     dword ptr [rbp+210h+var_218], eax
0x14002848c  movups  [rbp+210h+var_1C0], xmm0
0x140028490  lea     esi, [rax+40h]
0x140028493  mov     [rbp+210h+var_290], r14
0x140028497  mov     r8d, esi; Size
0x14002849a  movups  [rbp+210h+var_D0], xmm0
0x1400284a1  movups  [rbp+210h+var_C0], xmm0
0x1400284a8  movups  [rbp+210h+var_B0], xmm0
0x1400284af  movups  [rbp+210h+var_278], xmm0
0x1400284b3  movups  [rbp+210h+var_268+0Ch], xmm0
0x1400284b7  movups  [rbp+210h+var_1E0], xmm0
0x1400284bb  movups  [rbp+210h+var_1D0], xmm0
0x1400284bf  movups  [rbp+210h+var_1C0+0Ch], xmm0
0x1400284c3  movups  [rbp+210h+var_248], xmm0
0x1400284c7  movups  [rbp+210h+var_238], xmm0
0x1400284cb  movups  [rbp+210h+var_228], xmm0
0x1400284cf  call    memset
0x1400284d4  xor     eax, eax
0x1400284d6  mov     qword ptr [rbp+210h+DestinationString.Length], 5A0000h
0x1400284de  xorps   xmm0, xmm0
0x1400284e1  mov     [rbp+210h+var_1E8], rax
0x1400284e5  lea     rax, [rbp+210h+var_A0]
0x1400284ec  mov     [rsp+310h+var_298], 8
0x1400284f1  mov     [rbp+210h+DestinationString.Buffer], rax
0x1400284f5  movups  [rbp+210h+var_208], xmm0
0x1400284f9  movups  [rbp+210h+var_1F8], xmm0
0x1400284fd  mov     rcx, cs:WPP_GLOBAL_Control
0x140028504  lea     rdi, WPP_GLOBAL_Control
0x14002850b  lea     r13d, [r14+1]
0x14002850f  cmp     rcx, rdi
0x140028512  jz      short loc_140028545
0x140028514  mov     eax, [rcx+2Ch]
0x140028517  test    r13b, al
0x14002851a  jz      short loc_140028545
0x14002851c  cmp     byte ptr [rcx+29h], 5
0x140028520  jb      short loc_140028545
0x140028522  movzx   eax, word ptr [r15+28h]
0x140028527  lea     rdx, [r15+10h]
0x14002852b  mov     rcx, [rcx+18h]
0x14002852f  mov     r9, r15
0x140028532  mov     dword ptr [rsp+310h+var_2E8], eax
0x140028536  mov     [rsp+310h+var_2F0], rdx
0x14002853b  call    WPP_SF__guid__guid_D
0x140028540  mov     rbx, [rsp+310h+var_2A0]
0x140028545  mov     rax, cs:WdfFunctions_01033
0x14002854c  mov     r8d, 2Ah ; '*'
0x140028552  mov     rcx, cs:WdfDriverGlobals
0x140028559  mov     rdx, rbx
0x14002855c  movzx   r12d, word ptr [r15+2Eh]
0x140028561  mov     rax, [rax+210h]
0x140028568  call    _guard_dispatch_icall
0x14002856d  mov     rax, cs:WdfFunctions_01033
0x140028574  mov     r8d, 3
0x14002857a  mov     rdx, [rsp+310h+var_2A0]
0x14002857f  mov     rcx, cs:WdfDriverGlobals
0x140028586  mov     rax, [rax+1E8h]
0x14002858d  call    _guard_dispatch_icall
0x140028592  test    [r15+28h], r13b
0x140028596  jnz     short loc_1400285A2
0x140028598  test    r12w, r12w
0x14002859c  jz      loc_14002868F
0x1400285a2  mov     rax, cs:WdfFunctions_01033
0x1400285a9  lea     r8, SDDL_DEVOBJ_SYS_ALL_ADM_ALL
0x1400285b0  mov     rdx, [rsp+310h+var_2A0]
0x1400285b5  mov     rcx, cs:WdfDriverGlobals
0x1400285bc  mov     rax, [rax+220h]
0x1400285c3  call    _guard_dispatch_icall
0x1400285c8  mov     ebx, eax
0x1400285ca  test    eax, eax
0x1400285cc  jns     short loc_140028611
0x1400285ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1400285d5  cmp     rcx, rdi
0x1400285d8  jz      loc_14002935C
0x1400285de  mov     edx, [rcx+2Ch]
0x1400285e1  test    r13b, dl
0x1400285e4  jz      loc_14002935C
0x1400285ea  cmp     byte ptr [rcx+29h], 2
0x1400285ee  jb      loc_14002935C
0x1400285f4  mov     edx, 15h
0x1400285f9  mov     r9d, eax
0x1400285fc  mov     rcx, [rcx+18h]
0x140028600  lea     r8, WPP_9bc149055a283eb2988b2e39efb7d62e_Traceguids
0x140028607  call    WPP_SF_d
0x14002860c  jmp     loc_14002935C
0x140028611  mov     rax, cs:WdfFunctions_01033
0x140028618  lea     r8, GUID_BUS_VMBUS
0x14002861f  mov     rdx, [rsp+310h+var_2A0]
0x140028624  mov     rcx, cs:WdfDriverGlobals
0x14002862b  mov     rax, [rax+6D0h]
0x140028632  call    _guard_dispatch_icall
0x140028637  mov     ebx, eax
0x140028639  test    eax, eax
0x14002863b  jns     short loc_14002866D
0x14002863d  mov     rcx, cs:WPP_GLOBAL_Control
0x140028644  cmp     rcx, rdi
0x140028647  jz      loc_14002935C
0x14002864d  mov     eax, [rcx+2Ch]
0x140028650  test    r13b, al
0x140028653  jz      loc_14002935C
0x140028659  cmp     byte ptr [rcx+29h], 2
0x14002865d  jb      loc_14002935C
0x140028663  mov     edx, 16h
0x140028668  mov     r9d, ebx
0x14002866b  jmp     short loc_1400285FC
0x14002866d  mov     rax, cs:WdfFunctions_01033
0x140028674  mov     r8b, r13b
0x140028677  mov     rdx, [rsp+310h+var_2A0]
0x14002867c  mov     rcx, cs:WdfDriverGlobals
0x140028683  mov     rax, [rax+1F0h]
0x14002868a  call    _guard_dispatch_icall
0x14002868f  mov     r8, rsi; Size
0x140028692  lea     rcx, [rbp+210h+var_1E0]; void *
0x140028696  xor     edx, edx; Val
0x140028698  call    memset
0x14002869d  cmp     cs:WdfClientVersionHigherThanFramework, r14b
0x1400286a4  jz      short loc_1400286CA
0x1400286a6  cmp     cs:WdfStructureCount, 28h ; '('
0x1400286ad  jbe     short loc_1400286C1
0x1400286af  mov     rax, cs:WdfStructures
0x1400286b6  mov     ecx, [rax+140h]
0x1400286bc  mov     dword ptr [rbp+210h+var_1E0], ecx
0x1400286bf  jmp     short loc_1400286CD
0x1400286c1  mov     dword ptr [rbp+210h+var_1E0], 0FFFFFFFFh
0x1400286c8  jmp     short loc_1400286CD
0x1400286ca  mov     dword ptr [rbp+210h+var_1E0], esi
0x1400286cd  mov     rdx, [rsp+310h+var_2A0]
0x1400286d2  lea     rax, InstanceDeviceResourceRequirementsQuery
0x1400286d9  mov     rcx, cs:WdfDriverGlobals
0x1400286e0  lea     r8, [rbp+210h+var_1E0]
0x1400286e4  mov     qword ptr [rbp+210h+var_1D0], rax
0x1400286e8  mov     rax, cs:WdfFunctions_01033
0x1400286ef  mov     rax, [rax+698h]
0x1400286f6  call    _guard_dispatch_icall
0x1400286fb  test    r12w, r12w
0x1400286ff  jz      short loc_140028713
0x140028701  lea     rdx, aVmbusSubchanne; "VMBUS\\SUBCHANNEL"
0x140028708  lea     rcx, [rbp+210h+DestinationString]; DestinationString
0x14002870c  call    RtlUnicodeStringPrintf
0x140028711  jmp     short loc_140028786
0x140028713  movzx   ecx, byte ptr [r15+0Eh]
0x140028718  movzx   edx, byte ptr [r15+0Dh]
0x14002871d  movzx   r8d, byte ptr [r15+0Ch]
0x140028722  movzx   eax, byte ptr [r15+0Fh]
0x140028727  movzx   r10d, byte ptr [r15+0Bh]
0x14002872c  movzx   r11d, byte ptr [r15+0Ah]
0x140028731  movzx   ebx, byte ptr [r15+9]
0x140028736  movzx   edi, byte ptr [r15+8]
0x14002873b  movzx   esi, word ptr [r15+6]
0x140028740  movzx   r9d, word ptr [r15+4]
0x140028745  mov     dword ptr [rsp+310h+var_2B0], eax
0x140028749  mov     dword ptr [rsp+310h+var_2B8], ecx
0x14002874d  lea     rcx, [rbp+210h+DestinationString]; DestinationString
0x140028751  mov     dword ptr [rsp+310h+var_2C0], edx
0x140028755  lea     rdx, aVmbus08lx04x04; "VMBUS\\{%08lx-%04x-%04x-%02x%02x-%02x%0"...
0x14002875c  mov     dword ptr [rsp+310h+var_2C8], r8d
0x140028761  mov     r8d, [r15]
0x140028764  mov     dword ptr [rsp+310h+var_2D0], r10d
0x140028769  mov     dword ptr [rsp+310h+var_2D8], r11d
0x14002876e  mov     dword ptr [rsp+310h+var_2E0], ebx
0x140028772  mov     dword ptr [rsp+310h+var_2E8], edi
0x140028776  mov     dword ptr [rsp+310h+var_2F0], esi
0x14002877a  call    RtlUnicodeStringPrintf
0x14002877f  lea     rdi, WPP_GLOBAL_Control
0x140028786  mov     ebx, eax
0x140028788  test    eax, eax
0x14002878a  jns     short loc_1400287BC
0x14002878c  mov     rcx, cs:WPP_GLOBAL_Control
0x140028793  cmp     rcx, rdi
0x140028796  jz      loc_14002935C
0x14002879c  mov     eax, [rcx+2Ch]
0x14002879f  test    r13b, al
0x1400287a2  jz      loc_14002935C
0x1400287a8  cmp     byte ptr [rcx+29h], 2
0x1400287ac  jb      loc_14002935C
0x1400287b2  mov     edx, 17h
0x1400287b7  jmp     loc_140028668
0x1400287bc  mov     rax, cs:WdfFunctions_01033
0x1400287c3  lea     r8, [rbp+210h+DestinationString]
0x1400287c7  mov     rdx, [rsp+310h+var_2A0]
0x1400287cc  mov     rcx, cs:WdfDriverGlobals
0x1400287d3  mov     rax, [rax+6A0h]
0x1400287da  call    _guard_dispatch_icall
0x1400287df  mov     ebx, eax
0x1400287e1  test    eax, eax
0x1400287e3  jns     short loc_140028815
0x1400287e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400287ec  cmp     rcx, rdi
0x1400287ef  jz      loc_14002935C
0x1400287f5  mov     eax, [rcx+2Ch]
0x1400287f8  test    r13b, al
0x1400287fb  jz      loc_14002935C
0x140028801  cmp     byte ptr [rcx+29h], 2
0x140028805  jb      loc_14002935C
0x14002880b  mov     edx, 18h
0x140028810  jmp     loc_140028668
0x140028815  mov     rax, cs:WdfFunctions_01033
0x14002881c  lea     r8, [rbp+210h+DestinationString]
0x140028820  mov     rdx, [rsp+310h+var_2A0]
0x140028825  mov     rcx, cs:WdfDriverGlobals
0x14002882c  mov     rax, [rax+6B0h]
0x140028833  call    _guard_dispatch_icall
0x140028838  mov     ebx, eax
0x14002883a  test    eax, eax
0x14002883c  jns     short loc_14002886E
0x14002883e  mov     rcx, cs:WPP_GLOBAL_Control
0x140028845  cmp     rcx, rdi
0x140028848  jz      loc_14002935C
0x14002884e  mov     eax, [rcx+2Ch]
0x140028851  test    r13b, al
0x140028854  jz      loc_14002935C
0x14002885a  cmp     byte ptr [rcx+29h], 2
0x14002885e  jb      loc_14002935C
0x140028864  mov     edx, 19h
0x140028869  jmp     loc_140028668
0x14002886e  mov     rax, cs:WdfFunctions_01033
0x140028875  lea     r8, [rbp+210h+DestinationString]
0x140028879  mov     rdx, [rsp+310h+var_2A0]
0x14002887e  mov     rcx, cs:WdfDriverGlobals
0x140028885  mov     rax, [rax+6B8h]
0x14002888c  call    _guard_dispatch_icall
0x140028891  mov     ebx, eax
0x140028893  test    eax, eax
0x140028895  jns     short loc_1400288C7
0x140028897  mov     rcx, cs:WPP_GLOBAL_Control
0x14002889e  cmp     rcx, rdi
0x1400288a1  jz      loc_14002935C
0x1400288a7  mov     eax, [rcx+2Ch]
0x1400288aa  test    r13b, al
0x1400288ad  jz      loc_14002935C
0x1400288b3  cmp     byte ptr [rcx+29h], 2
0x1400288b7  jb      loc_14002935C
0x1400288bd  mov     edx, 1Ah
0x1400288c2  jmp     loc_140028668
0x1400288c7  test    r12w, r12w
0x1400288cb  jnz     loc_1400289DE
0x1400288d1  movzx   ecx, byte ptr [r15+1Eh]
0x1400288d6  lea     rdx, aVmbus08lx04x04; "VMBUS\\{%08lx-%04x-%04x-%02x%02x-%02x%0"...
0x1400288dd  movzx   r8d, byte ptr [r15+1Dh]
0x1400288e2  movzx   eax, byte ptr [r15+1Fh]
0x1400288e7  movzx   r10d, byte ptr [r15+1Ch]
0x1400288ec  movzx   r11d, byte ptr [r15+1Bh]
0x1400288f1  movzx   ebx, byte ptr [r15+1Ah]
0x1400288f6  movzx   edi, byte ptr [r15+19h]
0x1400288fb  movzx   esi, byte ptr [r15+18h]
0x140028900  movzx   r14d, word ptr [r15+16h]
0x140028905  movzx   r9d, word ptr [r15+14h]
0x14002890a  mov     dword ptr [rsp+310h+var_2B0], eax
0x14002890e  mov     dword ptr [rsp+310h+var_2B8], ecx
0x140028912  lea     rcx, [rbp+210h+DestinationString]; DestinationString
0x140028916  mov     dword ptr [rsp+310h+var_2C0], r8d
0x14002891b  mov     r8d, [r15+10h]
0x14002891f  mov     dword ptr [rsp+310h+var_2C8], r10d
0x140028924  mov     dword ptr [rsp+310h+var_2D0], r11d
0x140028929  mov     dword ptr [rsp+310h+var_2D8], ebx
0x14002892d  mov     dword ptr [rsp+310h+var_2E0], edi
0x140028931  mov     dword ptr [rsp+310h+var_2E8], esi
0x140028935  mov     dword ptr [rsp+310h+var_2F0], r14d
0x14002893a  call    RtlUnicodeStringPrintf
0x14002893f  xor     r14d, r14d
0x140028942  mov     ebx, eax
0x140028944  test    eax, eax
0x140028946  jns     short loc_14002897E
0x140028948  mov     rcx, cs:WPP_GLOBAL_Control
0x14002894f  lea     rax, WPP_GLOBAL_Control
0x140028956  cmp     rcx, rax
0x140028959  jz      loc_14002935C
0x14002895f  mov     eax, [rcx+2Ch]
0x140028962  test    r13b, al
0x140028965  jz      loc_14002935C
0x14002896b  cmp     byte ptr [rcx+29h], 2
0x14002896f  jb      loc_14002935C
  ... truncated ...
```
