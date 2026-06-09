# FWUPDATE_CreateFirmwareUpdateDevice

- ea: `0x14008f0a4`
- end: `0x14008f8a2`
- name: `FWUPDATE_CreateFirmwareUpdateDevice`
- size: `2046`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140079940`
- `0x14008f8b0`

## callees

- `0x140001f04`
- `0x1400024b8`
- `0x1400067ac`
- `0x14000f648`
- `0x140045530`
- `0x140045570`
- `0x140045940`
- `0x14008ece0`
- `0x14008f0a4`

## pseudocode

```c
__int64 __fastcall FWUPDATE_CreateFirmwareUpdateDevice(__int64 a1)
{
  int v2; // edx
  int v3; // ecx
  char v4; // si
  char v5; // r15
  int updated; // ebx
  __int64 v7; // rax
  __int64 v8; // r9
  int v9; // edx
  int v10; // edx
  int v11; // r9d
  int v12; // r8d
  unsigned int v13; // r14d
  __int64 v14; // r12
  int v15; // eax
  __int64 v16; // rax
  int v17; // edx
  __m128i si128; // xmm0
  int v19; // r8d
  int v20; // edx
  __int64 v21; // rcx
  BOOL v22; // eax
  __int64 v23; // rdx
  int v24; // edx
  __int64 v26; // [rsp+28h] [rbp-D8h]
  char v27[8]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v28; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v29; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v30; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v32; // [rsp+78h] [rbp-88h] BYREF
  __int128 v33; // [rsp+80h] [rbp-80h] BYREF
  __int128 v34; // [rsp+90h] [rbp-70h]
  __int128 v35; // [rsp+A0h] [rbp-60h]
  __int64 *v36; // [rsp+B0h] [rbp-50h]
  _OWORD v37[4]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v38[12]; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v39[18]; // [rsp+160h] [rbp+60h] BYREF
  __int128 v40; // [rsp+1F0h] [rbp+F0h] BYREF
  __int128 v41; // [rsp+200h] [rbp+100h]
  __int128 v42; // [rsp+210h] [rbp+110h]
  _QWORD v43[10]; // [rsp+220h] [rbp+120h] BYREF
  char v44; // [rsp+270h] [rbp+170h] BYREF

  LODWORD(v36) = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  memset(v38, 0, sizeof(v38));
  v32 = 0;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  memset(v43, 0, sizeof(v43));
  v30 = 0;
  v27[0] = 0;
  memset(v37, 0, 60);
  memset(v39, 0, 0x8Cu);
  v3 = *(_DWORD *)(a1 + 160);
  v29 = 0;
  v4 = 0;
  v28 = 0;
  v5 = 0;
  if ( v3 == 1 )
  {
    v7 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1632))(WdfDriverGlobals, a1);
    v28 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1680))(WdfDriverGlobals, v7);
    v9 = v28;
    if ( v28 )
    {
      v27[0] = 8;
      LOBYTE(v8) = 27;
      v5 = 1;
      updated = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, NTSTATUS (__fastcall *)(__int64, IRP *), __int64, char *, int))(WdfFunctions_01015 + 584))(
                  WdfDriverGlobals,
                  v28,
                  FWUPDATE_EvtDeviceWdmIrpQueryInterfacePreprocess,
                  v8,
                  v27,
                  1);
      if ( updated >= 0 )
      {
        memset(v39, 0, sizeof(v39));
        v39[1] = FWUPDATE_EvtDeviceD0Entry;
        v39[3] = FWUPDATE_EvtDeviceD0Exit;
        LODWORD(v39[0]) = 144;
        (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD *))(WdfFunctions_01015 + 440))(
          WdfDriverGlobals,
          v28,
          v39);
        memset(v37, 0, sizeof(v37));
        *((_QWORD *)&v37[3] + 1) = FWUPDATE_EvtDeviceReportedMissing;
        *(_QWORD *)&v37[1] = FWUPDATE_EvtDeviceResourceRequirementsQuery;
        LODWORD(v37[0]) = 64;
        (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _OWORD *))(WdfFunctions_01015 + 1688))(
          WdfDriverGlobals,
          v28,
          v37);
        (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01015 + 528))(
          WdfDriverGlobals,
          v28,
          34);
        (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01015 + 496))(
          WdfDriverGlobals,
          v28,
          0);
        (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 3136))(WdfDriverGlobals, v28);
        v30 = 0x100000008LL;
        (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 3224))(
          WdfDriverGlobals,
          v28,
          &v30);
        updated = FWUPDATE_AddIdsForFirmwareUpdateDevice(a1, v28);
        if ( updated < 0 )
          goto LABEL_42;
        v36 = off_14006B248;
        v13 = 0;
        *(_QWORD *)&v33 = 56;
        *((_QWORD *)&v33 + 1) = FWUPDATE_EvtDeviceCleanup;
        *(_QWORD *)&v34 = 0;
        v35 = 0;
        *((_QWORD *)&v34 + 1) = 0x100000001LL;
        while ( 1 )
        {
          v14 = v28;
          DestinationString.Buffer = (wchar_t *)&v44;
          *(_QWORD *)&DestinationString.Length = 12582912;
          updated = RtlUnicodeStringPrintf(&DestinationString, L"\\Device\\USBFWU-%d", v13);
          if ( updated >= 0 )
            updated = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *))(WdfFunctions_01015 + 536))(
                        WdfDriverGlobals,
                        v14,
                        &DestinationString);
          if ( updated < 0 )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_42;
            v11 = 38;
            goto LABEL_40;
          }
          updated = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, const UNICODE_STRING *))(WdfFunctions_01015 + 544))(
                      WdfDriverGlobals,
                      v28,
                      &SDDL_DEVOBJ_SYS_ALL_ADM_RWX_WORLD_RW_RES_R);
          if ( updated < 0 )
            break;
          v15 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64 *, __int128 *, __int64 *))(WdfFunctions_01015
                                                                                                 + 600))(
                  WdfDriverGlobals,
                  &v28,
                  &v33,
                  &v29);
          updated = v15;
          if ( v15 >= 0 )
          {
            v16 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
                    WdfDriverGlobals,
                    v29,
                    off_14006B248);
            v5 = 0;
            *(_QWORD *)v16 = a1;
            *(_DWORD *)(v16 + 28) = 5;
            memset(v38, 0, sizeof(v38));
            v38[6] = FWUPDATE_EvtIoInternalDeviceControl;
            LODWORD(v38[0]) = 96;
            v38[5] = FWUPDATE_EvtIoDeviceControl;
            BYTE5(v38[1]) = 1;
            *(_QWORD *)((char *)v38 + 4) = 1;
            updated = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD *, _QWORD, __int64 *))(WdfFunctions_01015 + 1216))(
                        WdfDriverGlobals,
                        v29,
                        v38,
                        0,
                        &v32);
            if ( updated >= 0 )
            {
              *(_QWORD *)&v40 = 0x200000030LL;
              *((_QWORD *)&v40 + 1) = 2;
              *(_QWORD *)&v41 = 2;
              *((_QWORD *)&v41 + 1) = 2;
              LODWORD(v42) = 2;
              *(_QWORD *)((char *)&v42 + 4) = 2;
              HIDWORD(v42) = -1;
              (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int128 *))(WdfFunctions_01015 + 664))(
                WdfDriverGlobals,
                v29,
                &v40);
              si128 = _mm_load_si128((const __m128i *)&_xmm);
              v4 = 1;
              v19 = *(_DWORD *)(a1 + 756);
              v20 = 2;
              *(__m128i *)((char *)&v43[3] + 4) = si128;
              LODWORD(v43[4]) = 1;
              *(__m128i *)&v43[5] = si128;
              v43[0] = 80;
              HIDWORD(v43[7]) = v19;
              LODWORD(v43[7]) = 1;
              *(_QWORD *)((char *)&v43[1] + 4) = 1;
              *(_QWORD *)((char *)&v43[2] + 4) = 0;
              v43[8] = 0;
              v43[9] = 0x500000000LL;
              LODWORD(v43[1]) = 0;
              while ( 1 )
              {
                v21 = (unsigned int)v20;
                v22 = v20++ > v19;
                *((_DWORD *)&v43[3] + v21 + 1) = v22 + 3;
                if ( v20 > 6 )
                  break;
                v19 = HIDWORD(v43[7]);
              }
              (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD *))(WdfFunctions_01015 + 672))(
                WdfDriverGlobals,
                v29,
                v43);
              v23 = *(_QWORD *)(a1 + 16);
              *(_QWORD *)(a1 + 2672) = v29;
              updated = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1064))(
                          WdfDriverGlobals,
                          v23);
              if ( updated >= 0 )
              {
                v4 = 0;
              }
              else
              {
                if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                {
                  LODWORD(v26) = updated;
                  LOBYTE(v24) = 2;
                  WPP_RECORDER_SF_d(
                    *(_QWORD *)(a1 + 2536),
                    v24,
                    3,
                    42,
                    (__int64)WPP_2fd11ae104fa34a9334eddada324a17a_Traceguids,
                    v26);
                }
                *(_QWORD *)(a1 + 2672) = 0;
              }
            }
            else
            {
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                LODWORD(v26) = updated;
                LOBYTE(v17) = 2;
                WPP_RECORDER_SF_d(
                  *(_QWORD *)(a1 + 2536),
                  v17,
                  3,
                  41,
                  (__int64)WPP_2fd11ae104fa34a9334eddada324a17a_Traceguids,
                  v26);
              }
              v4 = 1;
            }
            goto LABEL_42;
          }
          if ( v15 != -1073741771 )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_42;
            v11 = 40;
LABEL_40:
            v12 = 2;
            LOBYTE(v10) = 2;
            goto LABEL_41;
          }
          ++v13;
        }
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_42;
        v11 = 39;
      }
      else
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_42;
        v11 = 37;
      }
      v12 = 3;
      LOBYTE(v10) = 2;
LABEL_41:
      LODWORD(v26) = updated;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(a1 + 2536),
        v10,
        v12,
        v11,
        (__int64)WPP_2fd11ae104fa34a9334eddada324a17a_Traceguids,
        v26);
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v9) = 2;
        WPP_RECORDER_SF_(*(_QWORD *)(a1 + 2536), v9, 3, 36, (__int64)WPP_2fd11ae104fa34a9334eddada324a17a_Traceguids);
      }
      updated = -1073741670;
    }
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v2) = 2;
      WPP_RECORDER_SF_d(*(_QWORD *)(a1 + 2536), v2, 3, 35, (__int64)WPP_2fd11ae104fa34a9334eddada324a17a_Traceguids, v3);
    }
    updated = -1073741823;
  }
LABEL_42:
  if ( (Microsoft_Windows_USB_USBHUB3EnableBits & 0x40) != 0 )
    McTemplateK0ppuq_EtwWriteTransfer(
      v3,
      (unsigned int)USBHUB3_ETW_EVENT_FIRMWARE_UPDATE_ENUMERATION_COMPLETE,
      a1 + 2292,
      *(_QWORD *)(a1 + 248),
      *(_QWORD *)(a1 + 2672),
      *(_BYTE *)(a1 + 160),
      updated);
  if ( v5 )
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 432))(WdfDriverGlobals, v28);
  if ( v4 )
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1664))(WdfDriverGlobals, v29);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x14008f0a4  push    rbp
0x14008f0a6  push    rbx
0x14008f0a7  push    rsi
0x14008f0a8  push    rdi
0x14008f0a9  push    r12
0x14008f0ab  push    r13
0x14008f0ad  push    r14
0x14008f0af  push    r15
0x14008f0b1  lea     rbp, [rsp-248h]
0x14008f0b9  sub     rsp, 348h
0x14008f0c0  mov     rax, cs:__security_cookie
0x14008f0c7  xor     rax, rsp
0x14008f0ca  mov     [rbp+280h+var_50], rax
0x14008f0d1  xorps   xmm0, xmm0
0x14008f0d4  xor     eax, eax
0x14008f0d6  mov     rdi, rcx
0x14008f0d9  mov     dword ptr [rbp+280h+var_2D0], eax
0x14008f0dc  xor     edx, edx; Val
0x14008f0de  lea     rcx, [rbp+280h+var_280]; void *
0x14008f0e2  movups  [rbp+280h+var_300], xmm0
0x14008f0e6  lea     r8d, [rax+60h]; Size
0x14008f0ea  movups  [rbp+280h+var_2F0], xmm0
0x14008f0ee  movups  [rbp+280h+var_2E0], xmm0
0x14008f0f2  call    memset
0x14008f0f7  xorps   xmm0, xmm0
0x14008f0fa  lea     rcx, [rbp+280h+var_160]; void *
0x14008f101  xor     r13d, r13d
0x14008f104  xor     edx, edx; Val
0x14008f106  mov     [rsp+380h+var_308], r13
0x14008f10b  movups  [rbp+280h+var_190], xmm0
0x14008f112  lea     r8d, [r13+50h]; Size
0x14008f116  movups  [rbp+280h+var_180], xmm0
0x14008f11d  movups  [rbp+280h+var_170], xmm0
0x14008f124  call    memset
0x14008f129  xorps   xmm0, xmm0
0x14008f12c  mov     [rsp+380h+var_328], r13
0x14008f131  xor     eax, eax
0x14008f133  mov     [rsp+380h+var_340], r13b
0x14008f138  movups  [rbp+280h+var_2A0], xmm0
0x14008f13c  xor     edx, edx; Val
0x14008f13e  mov     [rbp+280h+var_21C], eax
0x14008f141  mov     r8d, 8Ch; Size
0x14008f147  lea     rcx, [rbp+280h+var_220]; void *
0x14008f14b  movups  [rbp+280h+var_2A0+0Ch], xmm0
0x14008f14f  movups  [rbp+280h+var_2C0], xmm0
0x14008f153  movups  [rbp+280h+var_2B0], xmm0
0x14008f157  call    memset
0x14008f15c  mov     ecx, [rdi+0A0h]
0x14008f162  lea     r12d, [r13+1]
0x14008f166  mov     [rsp+380h+var_330], r13
0x14008f16b  mov     sil, r13b
0x14008f16e  mov     [rsp+380h+var_338], r13
0x14008f173  mov     r15b, r13b
0x14008f176  cmp     ecx, r12d
0x14008f179  jz      short loc_14008F1BB
0x14008f17b  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008f182  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14008f189  jz      short loc_14008F1B1
0x14008f18b  mov     dword ptr [rsp+380h+var_358], ecx
0x14008f18f  lea     rax, WPP_2fd11ae104fa34a9334eddada324a17a_Traceguids
0x14008f196  mov     rcx, [rdi+9E8h]
0x14008f19d  lea     r9d, [r13+23h]
0x14008f1a1  lea     r8d, [r13+3]
0x14008f1a5  mov     [rsp+380h+var_360], rax
0x14008f1aa  mov     dl, 2
0x14008f1ac  call    WPP_RECORDER_SF_d
0x14008f1b1  mov     ebx, 0C0000001h
0x14008f1b6  jmp     loc_14008F7F7
0x14008f1bb  mov     rax, cs:WdfFunctions_01015
0x14008f1c2  mov     rdx, rdi
0x14008f1c5  mov     rcx, cs:WdfDriverGlobals
0x14008f1cc  mov     rax, [rax+660h]
0x14008f1d3  call    _guard_dispatch_icall
0x14008f1d8  mov     rcx, cs:WdfDriverGlobals
0x14008f1df  mov     rdx, rax
0x14008f1e2  mov     rax, cs:WdfFunctions_01015
0x14008f1e9  mov     rax, [rax+690h]
0x14008f1f0  call    _guard_dispatch_icall
0x14008f1f5  mov     [rsp+380h+var_338], rax
0x14008f1fa  mov     rdx, rax
0x14008f1fd  test    rax, rax
0x14008f200  jnz     short loc_14008F23E
0x14008f202  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008f209  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14008f210  jz      short loc_14008F234
0x14008f212  mov     rcx, [rdi+9E8h]
0x14008f219  lea     r9d, [rdx+24h]
0x14008f21d  lea     rax, WPP_2fd11ae104fa34a9334eddada324a17a_Traceguids
0x14008f224  lea     r8d, [rdx+3]
0x14008f228  mov     [rsp+380h+var_360], rax
0x14008f22d  mov     dl, 2
0x14008f22f  call    WPP_RECORDER_SF_
0x14008f234  mov     ebx, 0C000009Ah
0x14008f239  jmp     loc_14008F7F7
0x14008f23e  mov     rax, cs:WdfFunctions_01015
0x14008f245  lea     rcx, [rsp+380h+var_340]
0x14008f24a  mov     [rsp+380h+var_340], 8
0x14008f24f  lea     r8, FWUPDATE_EvtDeviceWdmIrpQueryInterfacePreprocess
0x14008f256  mov     dword ptr [rsp+380h+var_358], r12d
0x14008f25b  mov     r9b, 1Bh
0x14008f25e  mov     [rsp+380h+var_360], rcx
0x14008f263  mov     r15b, r12b
0x14008f266  mov     rax, [rax+248h]
0x14008f26d  mov     rcx, cs:WdfDriverGlobals
0x14008f274  call    _guard_dispatch_icall
0x14008f279  mov     ebx, eax
0x14008f27b  test    eax, eax
0x14008f27d  jns     short loc_14008F2A6
0x14008f27f  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008f286  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14008f28d  jz      loc_14008F7F7
0x14008f293  mov     r9d, 25h ; '%'
0x14008f299  mov     r8d, 3
0x14008f29f  mov     dl, 2
0x14008f2a1  jmp     loc_14008F7DB
0x14008f2a6  mov     ebx, 90h
0x14008f2ab  lea     rcx, [rbp+280h+var_220]; void *
0x14008f2af  mov     r8d, ebx; Size
0x14008f2b2  xor     edx, edx; Val
0x14008f2b4  call    memset
0x14008f2b9  mov     rdx, [rsp+380h+var_338]
0x14008f2be  lea     rax, FWUPDATE_EvtDeviceD0Entry
0x14008f2c5  mov     rcx, cs:WdfDriverGlobals
0x14008f2cc  lea     r8, [rbp+280h+var_220]
0x14008f2d0  mov     [rbp+280h+var_218], rax
0x14008f2d4  lea     rax, FWUPDATE_EvtDeviceD0Exit
0x14008f2db  mov     [rbp+280h+var_208], rax
0x14008f2df  mov     rax, cs:WdfFunctions_01015
0x14008f2e6  mov     [rbp+280h+var_220], ebx
0x14008f2e9  mov     rax, [rax+1B8h]
0x14008f2f0  call    _guard_dispatch_icall
0x14008f2f5  mov     ebx, 40h ; '@'
0x14008f2fa  lea     rcx, [rbp+280h+var_2C0]; void *
0x14008f2fe  mov     r8d, ebx; Size
0x14008f301  xor     edx, edx; Val
0x14008f303  call    memset
0x14008f308  mov     rdx, [rsp+380h+var_338]
0x14008f30d  lea     rax, FWUPDATE_EvtDeviceReportedMissing
0x14008f314  mov     rcx, cs:WdfDriverGlobals
0x14008f31b  lea     r8, [rbp+280h+var_2C0]
0x14008f31f  mov     [rbp+280h+var_288], rax
0x14008f323  lea     rax, FWUPDATE_EvtDeviceResourceRequirementsQuery
0x14008f32a  mov     qword ptr [rbp+280h+var_2B0], rax
0x14008f32e  mov     rax, cs:WdfFunctions_01015
0x14008f335  mov     dword ptr [rbp+280h+var_2C0], ebx
0x14008f338  mov     rax, [rax+698h]
0x14008f33f  call    _guard_dispatch_icall
0x14008f344  mov     rax, cs:WdfFunctions_01015
0x14008f34b  lea     r8d, [rbx-1Eh]
0x14008f34f  mov     rdx, [rsp+380h+var_338]
0x14008f354  mov     rcx, cs:WdfDriverGlobals
0x14008f35b  mov     rax, [rax+210h]
0x14008f362  call    _guard_dispatch_icall
0x14008f367  mov     rax, cs:WdfFunctions_01015
0x14008f36e  xor     r8d, r8d
0x14008f371  mov     rdx, [rsp+380h+var_338]
0x14008f376  mov     rcx, cs:WdfDriverGlobals
0x14008f37d  mov     rax, [rax+1F0h]
0x14008f384  call    _guard_dispatch_icall
0x14008f389  mov     rax, cs:WdfFunctions_01015
0x14008f390  mov     rdx, [rsp+380h+var_338]
0x14008f395  mov     rcx, cs:WdfDriverGlobals
0x14008f39c  mov     rax, [rax+0C40h]
0x14008f3a3  call    _guard_dispatch_icall
0x14008f3a8  mov     rax, cs:WdfFunctions_01015
0x14008f3af  lea     r8, [rsp+380h+var_328]
0x14008f3b4  mov     rdx, [rsp+380h+var_338]
0x14008f3b9  mov     rcx, cs:WdfDriverGlobals
0x14008f3c0  mov     dword ptr [rsp+380h+var_328], 8
0x14008f3c8  mov     dword ptr [rsp+380h+var_328+4], r12d
0x14008f3cd  mov     rax, [rax+0C98h]
0x14008f3d4  call    _guard_dispatch_icall
0x14008f3d9  mov     rdx, [rsp+380h+var_338]
0x14008f3de  mov     rcx, rdi
0x14008f3e1  call    FWUPDATE_AddIdsForFirmwareUpdateDevice
0x14008f3e6  mov     ebx, eax
0x14008f3e8  test    eax, eax
0x14008f3ea  js      loc_14008F7F7
0x14008f3f0  mov     rax, cs:off_14006B248
0x14008f3f7  xorps   xmm0, xmm0
0x14008f3fa  mov     [rbp+280h+var_2D0], rax
0x14008f3fe  mov     r14d, r13d
0x14008f401  lea     rax, FWUPDATE_EvtDeviceCleanup
0x14008f408  mov     qword ptr [rbp+280h+var_300], 38h ; '8'
0x14008f410  mov     qword ptr [rbp+280h+var_300+8], rax
0x14008f414  mov     qword ptr [rbp+280h+var_2F0], r13
0x14008f418  movdqu  [rbp+280h+var_2E0], xmm0
0x14008f41d  mov     dword ptr [rbp+280h+var_2F0+8], r12d
0x14008f421  mov     dword ptr [rbp+280h+var_2F0+0Ch], r12d
0x14008f425  mov     r12, [rsp+380h+var_338]
0x14008f42a  lea     rax, [rbp+280h+var_110]
0x14008f431  mov     r8d, r14d
0x14008f434  mov     [rsp+380h+DestinationString.Buffer], rax
0x14008f439  lea     rdx, aDeviceUsbfwuD; "\\Device\\USBFWU-%d"
0x14008f440  mov     qword ptr [rsp+380h+DestinationString.Length], 0C00000h
0x14008f449  lea     rcx, [rsp+380h+DestinationString]; DestinationString
0x14008f44e  call    RtlUnicodeStringPrintf
0x14008f453  mov     ebx, eax
0x14008f455  test    eax, eax
0x14008f457  js      short loc_14008F47D
0x14008f459  mov     rax, cs:WdfFunctions_01015
0x14008f460  lea     r8, [rsp+380h+DestinationString]
0x14008f465  mov     rcx, cs:WdfDriverGlobals
0x14008f46c  mov     rdx, r12
0x14008f46f  mov     rax, [rax+218h]
0x14008f476  call    _guard_dispatch_icall
0x14008f47b  mov     ebx, eax
0x14008f47d  test    ebx, ebx
0x14008f47f  js      loc_14008F7BC
0x14008f485  mov     rax, cs:WdfFunctions_01015
0x14008f48c  lea     r8, SDDL_DEVOBJ_SYS_ALL_ADM_RWX_WORLD_RW_RES_R
0x14008f493  mov     rdx, [rsp+380h+var_338]
0x14008f498  mov     rcx, cs:WdfDriverGlobals
0x14008f49f  mov     rax, [rax+220h]
0x14008f4a6  call    _guard_dispatch_icall
0x14008f4ab  mov     ebx, eax
0x14008f4ad  test    eax, eax
0x14008f4af  js      loc_14008F7A1
0x14008f4b5  mov     rax, cs:WdfFunctions_01015
0x14008f4bc  lea     r9, [rsp+380h+var_330]
0x14008f4c1  mov     rcx, cs:WdfDriverGlobals
0x14008f4c8  lea     r8, [rbp+280h+var_300]
0x14008f4cc  lea     rdx, [rsp+380h+var_338]
0x14008f4d1  mov     rax, [rax+258h]
0x14008f4d8  call    _guard_dispatch_icall
0x14008f4dd  mov     ebx, eax
0x14008f4df  test    eax, eax
0x14008f4e1  jns     short loc_14008F511
0x14008f4e3  cmp     eax, 0C0000035h
0x14008f4e8  jnz     short loc_14008F4F2
0x14008f4ea  inc     r14d
0x14008f4ed  jmp     loc_14008F425
0x14008f4f2  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008f4f9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14008f500  jz      loc_14008F7F7
0x14008f506  mov     r9d, 28h ; '('
0x14008f50c  jmp     loc_14008F7D2
0x14008f511  mov     rax, cs:WdfFunctions_01015
0x14008f518  mov     r8, cs:off_14006B248
0x14008f51f  mov     rdx, [rsp+380h+var_330]
0x14008f524  mov     rcx, cs:WdfDriverGlobals
0x14008f52b  mov     rax, [rax+650h]
0x14008f532  call    _guard_dispatch_icall
0x14008f537  mov     r12d, 5
0x14008f53d  lea     rcx, [rbp+280h+var_280]; void *
0x14008f541  xor     edx, edx; Val
0x14008f543  mov     r15b, r13b
0x14008f546  mov     [rax], rdi
0x14008f549  lea     ebx, [r12+5Bh]
0x14008f54e  mov     [rax+1Ch], r12d
0x14008f552  mov     r8d, ebx; Size
0x14008f555  call    memset
0x14008f55a  mov     rdx, [rsp+380h+var_330]
0x14008f55f  lea     rax, FWUPDATE_EvtIoInternalDeviceControl
0x14008f566  mov     [rbp+280h+var_250], rax
0x14008f56a  lea     r14d, [r12-4]
0x14008f56f  lea     rax, FWUPDATE_EvtIoDeviceControl
0x14008f576  mov     [rbp+280h+var_280], ebx
0x14008f579  mov     [rbp+280h+var_258], rax
0x14008f57d  lea     rcx, [rsp+380h+var_308]
0x14008f582  mov     rax, cs:WdfFunctions_01015
0x14008f589  lea     r8, [rbp+280h+var_280]
0x14008f58d  mov     [rbp+280h+var_273], r14b
0x14008f591  xor     r9d, r9d
0x14008f594  mov     [rbp+280h+var_27C], r14
0x14008f598  mov     [rsp+380h+var_360], rcx
0x14008f59d  mov     rax, [rax+4C0h]
0x14008f5a4  mov     rcx, cs:WdfDriverGlobals
0x14008f5ab  call    _guard_dispatch_icall
0x14008f5b0  mov     ebx, eax
0x14008f5b2  test    eax, eax
0x14008f5b4  jns     short loc_14008F5F6
0x14008f5b6  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008f5bd  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14008f5c4  jz      short loc_14008F5EE
0x14008f5c6  mov     rcx, [rdi+9E8h]
0x14008f5cd  lea     rax, WPP_2fd11ae104fa34a9334eddada324a17a_Traceguids
0x14008f5d4  lea     r9d, [r12+24h]
0x14008f5d9  mov     dword ptr [rsp+380h+var_358], ebx
0x14008f5dd  lea     r8d, [r12-2]
0x14008f5e2  mov     [rsp+380h+var_360], rax
0x14008f5e7  mov     dl, 2
0x14008f5e9  call    WPP_RECORDER_SF_d
0x14008f5ee  mov     sil, r14b
0x14008f5f1  jmp     loc_14008F7F7
0x14008f5f6  mov     rax, cs:WdfFunctions_01015
0x14008f5fd  lea     r8, [rbp+280h+var_190]
0x14008f604  mov     rdx, [rsp+380h+var_330]
0x14008f609  mov     rcx, cs:WdfDriverGlobals
0x14008f610  mov     dword ptr [rbp+280h+var_190], 30h ; '0'
0x14008f61a  mov     dword ptr [rbp+280h+var_190+4], 2
0x14008f624  mov     qword ptr [rbp+280h+var_190+8], 2
0x14008f62f  mov     qword ptr [rbp+280h+var_180], 2
0x14008f63a  mov     qword ptr [rbp+280h+var_180+8], 2
0x14008f645  mov     dword ptr [rbp+280h+var_170], 2
0x14008f64f  mov     qword ptr [rbp+280h+var_170+4], 2
0x14008f65a  mov     dword ptr [rbp+280h+var_170+0Ch], 0FFFFFFFFh
0x14008f664  mov     rax, [rax+298h]
0x14008f66b  call    _guard_dispatch_icall
0x14008f670  movdqa  xmm0, cs:__xmm@00000005000000050000000500000005
  ... truncated ...
```
