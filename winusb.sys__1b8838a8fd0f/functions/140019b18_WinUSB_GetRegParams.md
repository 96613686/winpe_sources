# WinUSB_GetRegParams

- ea: `0x140019b18`
- end: `0x14001a390`
- name: `WinUSB_GetRegParams`
- size: `2168`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140018010`

## callees

- `0x140001020`
- `0x1400011c8`
- `0x140010700`
- `0x140019b18`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140019c13`
- `ntoskrnl!RtlInitUnicodeString` at `0x140019cde`
- `ntoskrnl!RtlInitUnicodeString` at `0x140019d5f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140019dd5`
- `ntoskrnl!RtlInitUnicodeString` at `0x140019e48`
- `ntoskrnl!RtlInitUnicodeString` at `0x140019e9f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140019f1f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140019f9f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140019ff1`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001a043`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001a095`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001a0df`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001a134`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001a185`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001a205`
- `ntoskrnl!RtlInitUnicodeString` at `0x140019c13`
- `ntoskrnl!RtlInitUnicodeString` at `0x140019cde`
- `ntoskrnl!RtlInitUnicodeString` at `0x140019d5f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140019dd5`
- `ntoskrnl!RtlInitUnicodeString` at `0x140019e48`
- `ntoskrnl!RtlInitUnicodeString` at `0x140019e9f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140019f1f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140019f9f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140019ff1`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001a043`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001a095`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001a0df`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001a134`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001a185`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001a205`

## pseudocode

```c
__int64 __fastcall WinUSB_GetRegParams(__int64 a1, int *a2)
{
  __int64 v4; // rax
  int v5; // eax
  unsigned int v6; // edi
  unsigned __int16 v7; // r9
  unsigned __int64 v8; // rax
  char v9; // al
  char v10; // al
  char v11; // al
  int v12; // eax
  __int64 v14; // [rsp+28h] [rbp-51h]
  __int64 v15; // [rsp+40h] [rbp-39h] BYREF
  __int64 v16; // [rsp+48h] [rbp-31h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-29h] BYREF
  __int128 v18; // [rsp+60h] [rbp-19h] BYREF
  __int64 v19; // [rsp+70h] [rbp-9h]
  __int64 v20; // [rsp+78h] [rbp-1h]
  __int128 v21; // [rsp+80h] [rbp+7h]
  __int64 v22; // [rsp+90h] [rbp+17h]
  unsigned int v23; // [rsp+F0h] [rbp+77h] BYREF
  __int64 v24; // [rsp+F8h] [rbp+7Fh] BYREF

  DestinationString = 0;
  v23 = 0;
  v24 = 0;
  v16 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      5u,
      1u,
      0x43u,
      (__int64)WPP_26f1e60b7ed939401ac6450f7fef2921_Traceguids);
  v4 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1632))(WdfDriverGlobals, a1);
  v5 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, __int64, _QWORD, __int64 *))(WdfFunctions_01015 + 384))(
         WdfDriverGlobals,
         v4,
         1,
         2031616,
         0,
         &v24);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_69;
    v7 = 68;
    goto LABEL_68;
  }
  RtlInitUnicodeString(&DestinationString, L"DeviceInterfaceGUIDs");
  if ( (*(int (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *, _QWORD, _QWORD))(WdfFunctions_01015 + 1896))(
         WdfDriverGlobals,
         v24,
         &DestinationString,
         0,
         *(_QWORD *)(a1 + 152)) < 0 )
  {
    v15 = 0;
    v22 = 0;
    v8 = *(_QWORD *)(a1 + 152);
    v19 = 0;
    v20 = 0x100000001LL;
    v21 = v8;
    v18 = 0;
    LODWORD(v18) = 56;
    v5 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int128 *, __int64 *))(WdfFunctions_01015 + 2464))(
           WdfDriverGlobals,
           0,
           &v18,
           &v15);
    v6 = v5;
    if ( v5 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_69;
      v7 = 69;
      goto LABEL_68;
    }
    RtlInitUnicodeString(&DestinationString, L"DeviceInterfaceGUID");
    if ( (*(int (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *, __int64))(WdfFunctions_01015
                                                                                                + 1912))(
           WdfDriverGlobals,
           v24,
           &DestinationString,
           v15) >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64))(WdfFunctions_01015 + 120))(
             WdfDriverGlobals,
             *(_QWORD *)(a1 + 152),
             v15);
      v6 = v5;
      if ( v5 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_69;
        v7 = 70;
        goto LABEL_68;
      }
    }
  }
  RtlInitUnicodeString(&DestinationString, L"ResetPortEnabled");
  if ( (*(int (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *, __int64))(WdfFunctions_01015 + 1920))(
         WdfDriverGlobals,
         v24,
         &DestinationString,
         a1 + 304) < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        (__int64)WPP_GLOBAL_Control->DeviceExtension,
        4u,
        0xBu,
        0x47u,
        (__int64)WPP_26f1e60b7ed939401ac6450f7fef2921_Traceguids);
    *(_DWORD *)(a1 + 304) = 0;
  }
  RtlInitUnicodeString(&DestinationString, L"CyclePortEnabled");
  if ( (*(int (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *, __int64))(WdfFunctions_01015 + 1920))(
         WdfDriverGlobals,
         v24,
         &DestinationString,
         a1 + 308) < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        (__int64)WPP_GLOBAL_Control->DeviceExtension,
        4u,
        0xBu,
        0x48u,
        (__int64)WPP_26f1e60b7ed939401ac6450f7fef2921_Traceguids);
    *(_DWORD *)(a1 + 308) = 0;
  }
  RtlInitUnicodeString(&DestinationString, L"WinusbIsochUsed");
  if ( (*(int (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *, __int64))(WdfFunctions_01015 + 1920))(
         WdfDriverGlobals,
         v24,
         &DestinationString,
         a1 + 404) < 0 )
    *(_DWORD *)(a1 + 404) = 0;
  if ( *(_BYTE *)(a1 + 160) )
  {
    RtlInitUnicodeString(&DestinationString, L"SystemWakeEnabled");
    if ( (*(int (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *, unsigned int *))(WdfFunctions_01015 + 1920))(
           WdfDriverGlobals,
           v24,
           &DestinationString,
           &v23) >= 0 )
    {
      *(_BYTE *)(a1 + 236) = v23 != 0;
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          (__int64)WPP_GLOBAL_Control->DeviceExtension,
          4u,
          0xBu,
          0x49u,
          (__int64)WPP_26f1e60b7ed939401ac6450f7fef2921_Traceguids);
      *(_BYTE *)(a1 + 236) = 0;
    }
    RtlInitUnicodeString(&DestinationString, L"DeviceIdleEnabled");
    if ( (*(int (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *, unsigned int *))(WdfFunctions_01015 + 1920))(
           WdfDriverGlobals,
           v24,
           &DestinationString,
           &v23) >= 0 )
    {
      *(_BYTE *)(a1 + 232) = v23 != 0;
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          (__int64)WPP_GLOBAL_Control->DeviceExtension,
          4u,
          0xBu,
          0x4Au,
          (__int64)WPP_26f1e60b7ed939401ac6450f7fef2921_Traceguids);
      *(_BYTE *)(a1 + 232) = 0;
    }
    RtlInitUnicodeString(&DestinationString, L"DeviceIdleIgnoreWakeEnable");
    if ( (*(int (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *, unsigned int *))(WdfFunctions_01015 + 1920))(
           WdfDriverGlobals,
           v24,
           &DestinationString,
           &v23) < 0
      || (v9 = 1, !v23) )
    {
      v9 = 0;
    }
    *(_BYTE *)(a1 + 234) = v9;
    RtlInitUnicodeString(&DestinationString, L"UserSetDeviceIdleEnabled");
    if ( (*(int (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *, unsigned int *))(WdfFunctions_01015 + 1920))(
           WdfDriverGlobals,
           v24,
           &DestinationString,
           &v23) < 0
      || (v10 = 1, !v23) )
    {
      v10 = 0;
    }
    *(_BYTE *)(a1 + 233) = v10;
    RtlInitUnicodeString(&DestinationString, L"DefaultIdleState");
    if ( (*(int (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *, unsigned int *))(WdfFunctions_01015 + 1920))(
           WdfDriverGlobals,
           v24,
           &DestinationString,
           &v23) < 0
      || (v11 = 1, !v23) )
    {
      v11 = 0;
    }
    *(_BYTE *)(a1 + 235) = v11;
    RtlInitUnicodeString(&DestinationString, L"DefaultIdleTimeout");
    if ( (*(int (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *, __int64))(WdfFunctions_01015
                                                                                                + 1920))(
           WdfDriverGlobals,
           v24,
           &DestinationString,
           a1 + 228) < 0 )
      *(_DWORD *)(a1 + 228) = 0;
    RtlInitUnicodeString(&DestinationString, L"DevicePowerUpOnS0Entry");
    if ( (*(int (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *, unsigned int *))(WdfFunctions_01015 + 1920))(
           WdfDriverGlobals,
           v24,
           &DestinationString,
           &v23) >= 0 )
      v12 = v23 != 0;
    else
      v12 = 2;
    *a2 = v12;
    RtlInitUnicodeString(&DestinationString, L"e5b3b5ac-9725-4f78-963f-03dfb1d828c7");
    if ( (*(int (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *, __int64, _QWORD, __int64 *))(WdfFunctions_01015 + 1832))(
           WdfDriverGlobals,
           v24,
           &DestinationString,
           131097,
           0,
           &v16) < 0
      || (RtlInitUnicodeString(&DestinationString, L"D3ColdSupported"),
          (*(int (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *, unsigned int *))(WdfFunctions_01015 + 1920))(
            WdfDriverGlobals,
            v16,
            &DestinationString,
            &v23) < 0) )
    {
      *(_BYTE *)(a1 + 276) = 0;
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          (__int64)WPP_GLOBAL_Control->DeviceExtension,
          4u,
          0xBu,
          0x4Bu,
          (__int64)WPP_26f1e60b7ed939401ac6450f7fef2921_Traceguids);
      *(_BYTE *)(a1 + 276) = v23 != 0;
    }
  }
  RtlInitUnicodeString(&DestinationString, L"WinRtInterfaceRestrictionLevel");
  v5 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *, unsigned int *))(WdfFunctions_01015 + 1920))(
         WdfDriverGlobals,
         v24,
         &DestinationString,
         &v23);
  v6 = v5;
  if ( v5 < 0 )
  {
    *(_DWORD *)(a1 + 440) = 255;
    if ( v5 == -1073741772 )
    {
      v6 = 0;
      goto LABEL_69;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v7 = 78;
LABEL_68:
      LODWORD(v14) = v5;
      WPP_RECORDER_SF_d(
        (__int64)WPP_GLOBAL_Control->DeviceExtension,
        2u,
        0xBu,
        v7,
        (__int64)WPP_26f1e60b7ed939401ac6450f7fef2921_Traceguids,
        v14);
    }
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v14) = v23;
      WPP_RECORDER_SF_d(
        (__int64)WPP_GLOBAL_Control->DeviceExtension,
        4u,
        0xBu,
        0x4Cu,
        (__int64)WPP_26f1e60b7ed939401ac6450f7fef2921_Traceguids,
        v14);
    }
    if ( v23 <= 1 )
    {
      *(_DWORD *)(a1 + 440) = v23;
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v14) = 0;
        WPP_RECORDER_SF_d(
          (__int64)WPP_GLOBAL_Control->DeviceExtension,
          4u,
          0xBu,
          0x4Du,
          (__int64)WPP_26f1e60b7ed939401ac6450f7fef2921_Traceguids,
          v14);
      }
      *(_DWORD *)(a1 + 440) = 0;
    }
  }
LABEL_69:
  if ( v24 )
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 1848))(WdfDriverGlobals);
  if ( v16 )
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 1848))(WdfDriverGlobals);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LODWORD(v14) = v6;
    WPP_RECORDER_SF_d(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      5u,
      1u,
      0x4Fu,
      (__int64)WPP_26f1e60b7ed939401ac6450f7fef2921_Traceguids,
      v14);
  }
  return v6;
}

```

## disassembly

```asm
0x140019b18  mov     [rsp-8+arg_0], rbx
0x140019b1d  push    rbp
0x140019b1e  push    rsi
0x140019b1f  push    rdi
0x140019b20  push    r12
0x140019b22  push    r13
0x140019b24  push    r14
0x140019b26  push    r15
0x140019b28  lea     rbp, [rsp-27h]
0x140019b2d  sub     rsp, 0A0h
0x140019b34  xor     r15d, r15d
0x140019b37  xorps   xmm0, xmm0
0x140019b3a  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140019b3e  mov     [rbp+57h+arg_10], r15d
0x140019b42  mov     r14, rdx
0x140019b45  mov     [rbp+57h+arg_18], r15
0x140019b49  mov     rbx, rcx
0x140019b4c  mov     [rbp+57h+var_88], r15
0x140019b50  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140019b57  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140019b5e  lea     r13, WPP_26f1e60b7ed939401ac6450f7fef2921_Traceguids
0x140019b65  jz      short loc_140019B8D
0x140019b67  mov     rcx, cs:WPP_GLOBAL_Control
0x140019b6e  cmp     [rcx+48h], r15w
0x140019b73  jz      short loc_140019B8D
0x140019b75  mov     rcx, [rcx+40h]
0x140019b79  lea     r9d, [r15+43h]
0x140019b7d  lea     r8d, [r15+1]
0x140019b81  mov     [rsp+0D0h+var_B0], r13
0x140019b86  mov     dl, 5
0x140019b88  call    WPP_RECORDER_SF_
0x140019b8d  mov     rax, cs:WdfFunctions_01015
0x140019b94  mov     rdx, rbx
0x140019b97  mov     rcx, cs:WdfDriverGlobals
0x140019b9e  mov     rax, [rax+660h]
0x140019ba5  call    _guard_dispatch_icall
0x140019baa  mov     rcx, cs:WdfFunctions_01015
0x140019bb1  mov     rdx, rax
0x140019bb4  mov     r9d, 1F0000h
0x140019bba  mov     r8d, 1
0x140019bc0  mov     r10, [rcx+180h]
0x140019bc7  lea     rcx, [rbp+57h+arg_18]
0x140019bcb  mov     [rsp+0D0h+var_A8], rcx
0x140019bd0  mov     rax, r10
0x140019bd3  mov     rcx, cs:WdfDriverGlobals
0x140019bda  mov     [rsp+0D0h+var_B0], r15
0x140019bdf  call    _guard_dispatch_icall
0x140019be4  mov     edi, eax
0x140019be6  test    eax, eax
0x140019be8  jns     short loc_140019C08
0x140019bea  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140019bf1  jz      loc_14001A2F7
0x140019bf7  mov     r9d, 44h ; 'D'
0x140019bfd  mov     r8d, 0Bh
0x140019c03  jmp     loc_14001A2DC
0x140019c08  lea     rdx, aDeviceinterfac; "DeviceInterfaceGUIDs"
0x140019c0f  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140019c13  call    cs:__imp_RtlInitUnicodeString
0x140019c1a  nop     dword ptr [rax+rax+00h]
0x140019c1f  mov     rcx, [rbx+98h]
0x140019c26  lea     r8, [rbp+57h+DestinationString]
0x140019c2a  mov     rax, cs:WdfFunctions_01015
0x140019c31  xor     r9d, r9d
0x140019c34  mov     rdx, [rbp+57h+arg_18]
0x140019c38  mov     [rsp+0D0h+var_B0], rcx
0x140019c3d  mov     rcx, cs:WdfDriverGlobals
0x140019c44  mov     rax, [rax+768h]
0x140019c4b  call    _guard_dispatch_icall
0x140019c50  test    eax, eax
0x140019c52  jns     loc_140019D54
0x140019c58  mov     rcx, cs:WdfDriverGlobals
0x140019c5f  lea     r9, [rbp+57h+var_90]
0x140019c63  xor     eax, eax
0x140019c65  mov     [rbp+57h+var_90], r15
0x140019c69  mov     [rbp+57h+var_40], rax
0x140019c6d  lea     r8, [rbp+57h+var_70]
0x140019c71  mov     rax, [rbx+98h]
0x140019c78  xorps   xmm0, xmm0
0x140019c7b  movups  [rbp+57h+var_60], xmm0
0x140019c7f  mov     dword ptr [rbp+57h+var_60+8], 1
0x140019c86  xor     edx, edx
0x140019c88  movups  [rbp+57h+var_50], xmm0
0x140019c8c  mov     qword ptr [rbp+57h+var_50], rax
0x140019c90  mov     rax, cs:WdfFunctions_01015
0x140019c97  movups  [rbp+57h+var_70], xmm0
0x140019c9b  mov     dword ptr [rbp+57h+var_70], 38h ; '8'
0x140019ca2  mov     dword ptr [rbp+57h+var_60+0Ch], 1
0x140019ca9  mov     rax, [rax+9A0h]
0x140019cb0  call    _guard_dispatch_icall
0x140019cb5  mov     edi, eax
0x140019cb7  test    eax, eax
0x140019cb9  jns     short loc_140019CD3
0x140019cbb  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140019cc2  jz      loc_14001A2F7
0x140019cc8  mov     r9d, 45h ; 'E'
0x140019cce  jmp     loc_140019BFD
0x140019cd3  lea     rdx, aDeviceinterfac_0; "DeviceInterfaceGUID"
0x140019cda  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140019cde  call    cs:__imp_RtlInitUnicodeString
0x140019ce5  nop     dword ptr [rax+rax+00h]
0x140019cea  mov     rax, cs:WdfFunctions_01015
0x140019cf1  lea     r8, [rbp+57h+DestinationString]
0x140019cf5  mov     r9, [rbp+57h+var_90]
0x140019cf9  mov     rdx, [rbp+57h+arg_18]
0x140019cfd  mov     rcx, cs:WdfDriverGlobals
0x140019d04  mov     rax, [rax+778h]
0x140019d0b  call    _guard_dispatch_icall
0x140019d10  test    eax, eax
0x140019d12  js      short loc_140019D54
0x140019d14  mov     rax, cs:WdfFunctions_01015
0x140019d1b  mov     r8, [rbp+57h+var_90]
0x140019d1f  mov     rdx, [rbx+98h]
0x140019d26  mov     rcx, cs:WdfDriverGlobals
0x140019d2d  mov     rax, [rax+78h]
0x140019d31  call    _guard_dispatch_icall
0x140019d36  mov     edi, eax
0x140019d38  test    eax, eax
0x140019d3a  jns     short loc_140019D54
0x140019d3c  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140019d43  jz      loc_14001A2F7
0x140019d49  mov     r9d, 46h ; 'F'
0x140019d4f  jmp     loc_140019BFD
0x140019d54  lea     rdx, aResetportenabl; "ResetPortEnabled"
0x140019d5b  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140019d5f  call    cs:__imp_RtlInitUnicodeString
0x140019d66  nop     dword ptr [rax+rax+00h]
0x140019d6b  mov     rax, cs:WdfFunctions_01015
0x140019d72  lea     rdi, [rbx+130h]
0x140019d79  mov     rdx, [rbp+57h+arg_18]
0x140019d7d  lea     r8, [rbp+57h+DestinationString]
0x140019d81  mov     rcx, cs:WdfDriverGlobals
0x140019d88  mov     r9, rdi
0x140019d8b  mov     rax, [rax+780h]
0x140019d92  call    _guard_dispatch_icall
0x140019d97  mov     esi, 0Bh
0x140019d9c  test    eax, eax
0x140019d9e  jns     short loc_140019DCA
0x140019da0  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140019da7  jz      short loc_140019DC7
0x140019da9  mov     rcx, cs:WPP_GLOBAL_Control
0x140019db0  lea     r9d, [rsi+3Ch]
0x140019db4  mov     r8d, esi
0x140019db7  mov     [rsp+0D0h+var_B0], r13
0x140019dbc  mov     dl, 4
0x140019dbe  mov     rcx, [rcx+40h]
0x140019dc2  call    WPP_RECORDER_SF_
0x140019dc7  mov     [rdi], r15d
0x140019dca  lea     rdx, aCycleportenabl; "CyclePortEnabled"
0x140019dd1  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140019dd5  call    cs:__imp_RtlInitUnicodeString
0x140019ddc  nop     dword ptr [rax+rax+00h]
0x140019de1  mov     rax, cs:WdfFunctions_01015
0x140019de8  lea     rdi, [rbx+134h]
0x140019def  mov     rdx, [rbp+57h+arg_18]
0x140019df3  lea     r8, [rbp+57h+DestinationString]
0x140019df7  mov     rcx, cs:WdfDriverGlobals
0x140019dfe  mov     r9, rdi
0x140019e01  mov     rax, [rax+780h]
0x140019e08  call    _guard_dispatch_icall
0x140019e0d  test    eax, eax
0x140019e0f  jns     short loc_140019E3D
0x140019e11  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140019e18  jz      short loc_140019E3A
0x140019e1a  mov     rcx, cs:WPP_GLOBAL_Control
0x140019e21  mov     r9d, 48h ; 'H'
0x140019e27  mov     r8d, esi
0x140019e2a  mov     [rsp+0D0h+var_B0], r13
0x140019e2f  mov     dl, 4
0x140019e31  mov     rcx, [rcx+40h]
0x140019e35  call    WPP_RECORDER_SF_
0x140019e3a  mov     [rdi], r15d
0x140019e3d  lea     rdx, aWinusbisochuse; "WinusbIsochUsed"
0x140019e44  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140019e48  call    cs:__imp_RtlInitUnicodeString
0x140019e4f  nop     dword ptr [rax+rax+00h]
0x140019e54  mov     rax, cs:WdfFunctions_01015
0x140019e5b  lea     rdi, [rbx+194h]
0x140019e62  mov     rdx, [rbp+57h+arg_18]
0x140019e66  lea     r8, [rbp+57h+DestinationString]
0x140019e6a  mov     rcx, cs:WdfDriverGlobals
0x140019e71  mov     r9, rdi
0x140019e74  mov     rax, [rax+780h]
0x140019e7b  call    _guard_dispatch_icall
0x140019e80  test    eax, eax
0x140019e82  jns     short loc_140019E87
0x140019e84  mov     [rdi], r15d
0x140019e87  cmp     [rbx+0A0h], r15b
0x140019e8e  jz      loc_14001A1FA
0x140019e94  lea     rdx, aSystemwakeenab; "SystemWakeEnabled"
0x140019e9b  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140019e9f  call    cs:__imp_RtlInitUnicodeString
0x140019ea6  nop     dword ptr [rax+rax+00h]
0x140019eab  mov     rax, cs:WdfFunctions_01015
0x140019eb2  lea     r9, [rbp+57h+arg_10]
0x140019eb6  mov     rdx, [rbp+57h+arg_18]
0x140019eba  lea     r8, [rbp+57h+DestinationString]
0x140019ebe  mov     rcx, cs:WdfDriverGlobals
0x140019ec5  mov     rax, [rax+780h]
0x140019ecc  call    _guard_dispatch_icall
0x140019ed1  test    eax, eax
0x140019ed3  jns     short loc_140019F07
0x140019ed5  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140019edc  jz      short loc_140019EFE
0x140019ede  mov     rcx, cs:WPP_GLOBAL_Control
0x140019ee5  mov     r9d, 49h ; 'I'
0x140019eeb  mov     r8d, esi
0x140019eee  mov     [rsp+0D0h+var_B0], r13
0x140019ef3  mov     dl, 4
0x140019ef5  mov     rcx, [rcx+40h]
0x140019ef9  call    WPP_RECORDER_SF_
0x140019efe  mov     [rbx+0ECh], r15b
0x140019f05  jmp     short loc_140019F14
0x140019f07  cmp     [rbp+57h+arg_10], r15d
0x140019f0b  setnz   al
0x140019f0e  mov     [rbx+0ECh], al
0x140019f14  lea     rdx, aDeviceidleenab; "DeviceIdleEnabled"
0x140019f1b  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140019f1f  call    cs:__imp_RtlInitUnicodeString
0x140019f26  nop     dword ptr [rax+rax+00h]
0x140019f2b  mov     rax, cs:WdfFunctions_01015
0x140019f32  lea     r9, [rbp+57h+arg_10]
0x140019f36  mov     rdx, [rbp+57h+arg_18]
0x140019f3a  lea     r8, [rbp+57h+DestinationString]
0x140019f3e  mov     rcx, cs:WdfDriverGlobals
0x140019f45  mov     rax, [rax+780h]
0x140019f4c  call    _guard_dispatch_icall
0x140019f51  test    eax, eax
0x140019f53  jns     short loc_140019F87
0x140019f55  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140019f5c  jz      short loc_140019F7E
0x140019f5e  mov     rcx, cs:WPP_GLOBAL_Control
0x140019f65  mov     r9d, 4Ah ; 'J'
0x140019f6b  mov     r8d, esi
0x140019f6e  mov     [rsp+0D0h+var_B0], r13
0x140019f73  mov     dl, 4
0x140019f75  mov     rcx, [rcx+40h]
0x140019f79  call    WPP_RECORDER_SF_
0x140019f7e  mov     [rbx+0E8h], r15b
0x140019f85  jmp     short loc_140019F94
0x140019f87  cmp     [rbp+57h+arg_10], r15d
0x140019f8b  setnz   al
0x140019f8e  mov     [rbx+0E8h], al
0x140019f94  lea     rdx, aDeviceidleigno; "DeviceIdleIgnoreWakeEnable"
0x140019f9b  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140019f9f  call    cs:__imp_RtlInitUnicodeString
0x140019fa6  nop     dword ptr [rax+rax+00h]
0x140019fab  mov     rax, cs:WdfFunctions_01015
0x140019fb2  lea     r9, [rbp+57h+arg_10]
0x140019fb6  mov     rdx, [rbp+57h+arg_18]
0x140019fba  lea     r8, [rbp+57h+DestinationString]
0x140019fbe  mov     rcx, cs:WdfDriverGlobals
0x140019fc5  mov     rax, [rax+780h]
0x140019fcc  call    _guard_dispatch_icall
0x140019fd1  test    eax, eax
0x140019fd3  js      short loc_140019FDD
0x140019fd5  mov     al, 1
0x140019fd7  cmp     [rbp+57h+arg_10], r15d
0x140019fdb  jnz     short loc_140019FE0
0x140019fdd  mov     al, r15b
0x140019fe0  lea     rdx, aUsersetdevicei; "UserSetDeviceIdleEnabled"
0x140019fe7  mov     [rbx+0EAh], al
0x140019fed  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140019ff1  call    cs:__imp_RtlInitUnicodeString
0x140019ff8  nop     dword ptr [rax+rax+00h]
0x140019ffd  mov     rax, cs:WdfFunctions_01015
0x14001a004  lea     r9, [rbp+57h+arg_10]
0x14001a008  mov     rdx, [rbp+57h+arg_18]
0x14001a00c  lea     r8, [rbp+57h+DestinationString]
0x14001a010  mov     rcx, cs:WdfDriverGlobals
0x14001a017  mov     rax, [rax+780h]
0x14001a01e  call    _guard_dispatch_icall
0x14001a023  test    eax, eax
0x14001a025  js      short loc_14001A02F
0x14001a027  mov     al, 1
0x14001a029  cmp     [rbp+57h+arg_10], r15d
0x14001a02d  jnz     short loc_14001A032
0x14001a02f  mov     al, r15b
0x14001a032  lea     rdx, aDefaultidlesta; "DefaultIdleState"
0x14001a039  mov     [rbx+0E9h], al
0x14001a03f  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14001a043  call    cs:__imp_RtlInitUnicodeString
0x14001a04a  nop     dword ptr [rax+rax+00h]
0x14001a04f  mov     rax, cs:WdfFunctions_01015
0x14001a056  lea     r9, [rbp+57h+arg_10]
0x14001a05a  mov     rdx, [rbp+57h+arg_18]
0x14001a05e  lea     r8, [rbp+57h+DestinationString]
0x14001a062  mov     rcx, cs:WdfDriverGlobals
0x14001a069  mov     rax, [rax+780h]
0x14001a070  call    _guard_dispatch_icall
0x14001a075  test    eax, eax
0x14001a077  js      short loc_14001A081
0x14001a079  mov     al, 1
0x14001a07b  cmp     [rbp+57h+arg_10], r15d
0x14001a07f  jnz     short loc_14001A084
0x14001a081  mov     al, r15b
0x14001a084  lea     rdx, aDefaultidletim; "DefaultIdleTimeout"
0x14001a08b  mov     [rbx+0EBh], al
0x14001a091  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14001a095  call    cs:__imp_RtlInitUnicodeString
0x14001a09c  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
