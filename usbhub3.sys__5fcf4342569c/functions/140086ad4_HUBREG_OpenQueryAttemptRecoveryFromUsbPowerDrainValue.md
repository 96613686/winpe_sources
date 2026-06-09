# HUBREG_OpenQueryAttemptRecoveryFromUsbPowerDrainValue

- ea: `0x140086ad4`
- end: `0x140086fac`
- name: `HUBREG_OpenQueryAttemptRecoveryFromUsbPowerDrainValue`
- size: `1240`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14000e6d0`
- `0x140081c50`

## callees

- `0x1400024b8`
- `0x140045570`
- `0x140086ad4`

## import_xrefs

- `ntoskrnl!RtlGetPersistedStateLocation` at `0x140086c85`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x140086d26`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x140086c85`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x140086d26`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x140086c4a`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x140086c4a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140086f19`
- `ntoskrnl!ExFreePoolWithTag` at `0x140086f19`
- `ntoskrnl!ExAllocatePool2` at `0x140086cc7`
- `ntoskrnl!ExAllocatePool2` at `0x140086cc7`

## string_xrefs

- `0x140086c6a`: `\Registry\Machine\System\CurrentControlSet\Control\usb`
- `0x140086d05`: `\Registry\Machine\System\CurrentControlSet\Control\usb`

## pseudocode

```c
__int64 __fastcall HUBREG_OpenQueryAttemptRecoveryFromUsbPowerDrainValue(_DWORD *a1)
{
  __int64 v2; // rsi
  _WORD *Pool2; // r14
  char v4; // r13
  char v5; // r12
  int v6; // edx
  signed int v7; // ebx
  __int64 *v8; // rcx
  int v9; // edx
  int v10; // edx
  int PersistedStateLocation; // eax
  int v12; // r9d
  __int64 v13; // rcx
  _WORD *v14; // rax
  char v16; // [rsp+28h] [rbp-28h]
  __int128 v17; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v18; // [rsp+98h] [rbp+48h] BYREF
  __int64 v19; // [rsp+A0h] [rbp+50h] BYREF
  __int64 v20; // [rsp+A8h] [rbp+58h] BYREF

  v17 = 0;
  v18 = 0;
  v20 = 0;
  v19 = 0;
  v2 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         WdfDriverGlobals->Driver,
         off_14006B2C0);
  v19 = 0;
  v20 = 0;
  Pool2 = 0;
  v4 = 0;
  v5 = 0;
  v7 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64 *, __int64, _QWORD, __int64 *))(WdfFunctions_01015 + 1832))(
         WdfDriverGlobals,
         0,
         &g_UsbAutomaticSurpriseRemovalKeyName,
         131097,
         0,
         &v19);
  v8 = WPP_fe827790944537bbfef1c01f2ab82bc9_Traceguids;
  if ( v7 >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, const wchar_t *, _DWORD *))(WdfFunctions_01015 + 1920))(
           WdfDriverGlobals,
           v19,
           L"@B",
           a1);
    if ( v7 >= 0 )
    {
      v4 = 1;
    }
    else
    {
      *a1 = 0;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v9) = 2;
        WPP_RECORDER_SF_d(
          *(_QWORD *)(v2 + 64),
          v9,
          2,
          138,
          (__int64)WPP_fe827790944537bbfef1c01f2ab82bc9_Traceguids,
          v7);
      }
    }
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1848))(WdfDriverGlobals, v19);
    v19 = 0;
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v6) = 2;
    WPP_RECORDER_SF_d(*(_QWORD *)(v2 + 64), v6, 2, 137, (__int64)WPP_fe827790944537bbfef1c01f2ab82bc9_Traceguids, v7);
  }
  if ( (unsigned __int8)RtlIsStateSeparationEnabled(v8) == 1 )
  {
    PersistedStateLocation = RtlGetPersistedStateLocation(
                               L"USB",
                               0,
                               L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\usb",
                               0,
                               0,
                               0,
                               &v18);
    v7 = PersistedStateLocation;
    if ( PersistedStateLocation == -2147483643 )
    {
      Pool2 = (_WORD *)ExAllocatePool2(64, v18, 1681082453);
      if ( Pool2 )
      {
        PersistedStateLocation = RtlGetPersistedStateLocation(
                                   L"USB",
                                   0,
                                   L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\usb",
                                   0,
                                   Pool2,
                                   v18,
                                   0);
        v7 = PersistedStateLocation;
        if ( PersistedStateLocation >= 0 )
        {
          v17 = 0;
          v13 = 0x7FFF;
          v14 = Pool2;
          v10 = 2;
          do
          {
            if ( !*v14 )
              break;
            ++v14;
            --v13;
          }
          while ( v13 );
          v7 = v13 == 0 ? 0xC000000D : 0;
          if ( v13 )
          {
            *((_QWORD *)&v17 + 1) = Pool2;
            LOWORD(v17) = -2 - 2 * v13;
            WORD1(v17) = -2 * v13;
            PersistedStateLocation = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int128 *, __int64, _QWORD, __int64 *))(WdfFunctions_01015 + 1832))(
                                       WdfDriverGlobals,
                                       0,
                                       &v17,
                                       131097,
                                       0,
                                       &v20);
            v7 = PersistedStateLocation;
            if ( PersistedStateLocation < 0 )
            {
              if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                goto LABEL_35;
              v12 = 143;
              goto LABEL_19;
            }
            PersistedStateLocation = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, const wchar_t *, __int64, _QWORD, __int64 *))(WdfFunctions_01015 + 1832))(
                                       WdfDriverGlobals,
                                       v20,
                                       L"02",
                                       131097,
                                       0,
                                       &v19);
            v7 = PersistedStateLocation;
            if ( PersistedStateLocation < 0 )
            {
              if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                goto LABEL_35;
              v12 = 144;
              goto LABEL_19;
            }
            PersistedStateLocation = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, const wchar_t *, _DWORD *))(WdfFunctions_01015 + 1920))(
                                       WdfDriverGlobals,
                                       v19,
                                       L"@B",
                                       a1);
            v7 = PersistedStateLocation;
            if ( PersistedStateLocation >= 0 )
            {
              v5 = 1;
              goto LABEL_35;
            }
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              v12 = 145;
              goto LABEL_19;
            }
          }
          else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            WPP_RECORDER_SF_d(
              *(_QWORD *)(v2 + 64),
              2,
              2,
              142,
              (__int64)WPP_fe827790944537bbfef1c01f2ab82bc9_Traceguids,
              v7);
          }
        }
        else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v12 = 141;
          goto LABEL_19;
        }
      }
      else
      {
        v7 = -1073741670;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v12 = 140;
          v16 = -102;
LABEL_20:
          LOBYTE(v10) = 2;
          WPP_RECORDER_SF_d(
            *(_QWORD *)(v2 + 64),
            v10,
            2,
            v12,
            (__int64)WPP_fe827790944537bbfef1c01f2ab82bc9_Traceguids,
            v16);
        }
      }
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v12 = 139;
LABEL_19:
      v16 = PersistedStateLocation;
      goto LABEL_20;
    }
  }
LABEL_35:
  if ( v4 && !v5 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = 3;
      WPP_RECORDER_SF_d(*(_QWORD *)(v2 + 64), v10, 2, 146, (__int64)WPP_fe827790944537bbfef1c01f2ab82bc9_Traceguids, v7);
    }
    v7 = 0;
  }
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x64334855u);
  if ( v20 )
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 1848))(WdfDriverGlobals);
  if ( v19 )
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 1848))(WdfDriverGlobals);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140086ad4  mov     [rsp-38h+arg_0], rbx
0x140086ad9  push    rbp
0x140086ada  push    rsi
0x140086adb  push    rdi
0x140086adc  push    r12
0x140086ade  push    r13
0x140086ae0  push    r14
0x140086ae2  push    r15
0x140086ae4  mov     rbp, rsp
0x140086ae7  sub     rsp, 50h
0x140086aeb  mov     rax, cs:WdfFunctions_01015
0x140086af2  xor     edi, edi
0x140086af4  mov     r8, cs:off_14006B2C0
0x140086afb  mov     r15, rcx
0x140086afe  mov     rcx, cs:WdfDriverGlobals
0x140086b05  xorps   xmm0, xmm0
0x140086b08  movups  [rbp+var_10], xmm0
0x140086b0c  mov     [rbp+arg_8], edi
0x140086b0f  mov     [rbp+arg_18], rdi
0x140086b13  mov     [rbp+arg_10], rdi
0x140086b17  mov     rdx, [rcx]
0x140086b1a  mov     rax, [rax+650h]
0x140086b21  call    _guard_dispatch_icall
0x140086b26  mov     rcx, cs:WdfFunctions_01015
0x140086b2d  lea     r8, g_UsbAutomaticSurpriseRemovalKeyName
0x140086b34  mov     rsi, rax
0x140086b37  mov     [rbp+arg_10], rdi
0x140086b3b  mov     [rbp+arg_18], rdi
0x140086b3f  mov     r9d, 20019h
0x140086b45  xor     edx, edx
0x140086b47  mov     r14d, edi
0x140086b4a  mov     rax, [rcx+728h]
0x140086b51  mov     r13b, dil
0x140086b54  lea     rcx, [rbp+arg_10]
0x140086b58  mov     r12b, dil
0x140086b5b  mov     [rsp+50h+var_28], rcx
0x140086b60  mov     rcx, cs:WdfDriverGlobals
0x140086b67  mov     [rsp+50h+var_30], rdi
0x140086b6c  call    _guard_dispatch_icall
0x140086b71  mov     ebx, eax
0x140086b73  lea     rcx, WPP_fe827790944537bbfef1c01f2ab82bc9_Traceguids
0x140086b7a  lea     eax, [rdi+2]
0x140086b7d  test    ebx, ebx
0x140086b7f  jns     short loc_140086BB7
0x140086b81  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140086b88  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140086b8f  jz      loc_140086C4A
0x140086b95  mov     dword ptr [rsp+50h+var_28], ebx
0x140086b99  mov     r9d, 89h
0x140086b9f  mov     [rsp+50h+var_30], rcx
0x140086ba4  mov     r8d, eax
0x140086ba7  mov     rcx, [rsi+40h]
0x140086bab  mov     dl, al
0x140086bad  call    WPP_RECORDER_SF_d
0x140086bb2  jmp     loc_140086C4A
0x140086bb7  mov     rax, cs:WdfFunctions_01015
0x140086bbe  lea     r8, g_UsbAutomaticSurpriseRemovalAttemptRecoveryFromUsbPowerDrainName; "@B"
0x140086bc5  mov     rdx, [rbp+arg_10]
0x140086bc9  mov     r9, r15
0x140086bcc  mov     rcx, cs:WdfDriverGlobals
0x140086bd3  mov     rax, [rax+780h]
0x140086bda  call    _guard_dispatch_icall
0x140086bdf  mov     ebx, eax
0x140086be1  lea     rdi, WPP_RECORDER_INITIALIZED
0x140086be8  xor     eax, eax
0x140086bea  test    ebx, ebx
0x140086bec  jns     short loc_140086C25
0x140086bee  mov     [r15], eax
0x140086bf1  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x140086bf8  jz      short loc_140086C28
0x140086bfa  mov     rcx, [rsi+40h]
0x140086bfe  lea     rax, WPP_fe827790944537bbfef1c01f2ab82bc9_Traceguids
0x140086c05  mov     dword ptr [rsp+50h+var_28], ebx
0x140086c09  mov     r9d, 8Ah
0x140086c0f  mov     [rsp+50h+var_30], rax
0x140086c14  mov     eax, 2
0x140086c19  mov     r8d, eax
0x140086c1c  mov     dl, al
0x140086c1e  call    WPP_RECORDER_SF_d
0x140086c23  jmp     short loc_140086C28
0x140086c25  mov     r13b, 1
0x140086c28  mov     rax, cs:WdfFunctions_01015
0x140086c2f  mov     rdx, [rbp+arg_10]
0x140086c33  mov     rcx, cs:WdfDriverGlobals
0x140086c3a  mov     rax, [rax+738h]
0x140086c41  call    _guard_dispatch_icall
0x140086c46  mov     [rbp+arg_10], r14
0x140086c4a  call    cs:__imp_RtlIsStateSeparationEnabled
0x140086c51  nop     dword ptr [rax+rax+00h]
0x140086c56  cmp     al, 1
0x140086c58  jnz     loc_140086ECE
0x140086c5e  lea     rax, [rbp+arg_8]
0x140086c62  xor     r9d, r9d
0x140086c65  mov     [rsp+50h+var_20], rax
0x140086c6a  lea     r8, aRegistryMachin_13; "\\Registry\\Machine\\System\\CurrentCon"...
0x140086c71  xor     eax, eax
0x140086c73  lea     rcx, aUsb; "USB"
0x140086c7a  mov     dword ptr [rsp+50h+var_28], eax
0x140086c7e  xor     edx, edx
0x140086c80  mov     [rsp+50h+var_30], rax
0x140086c85  call    cs:__imp_RtlGetPersistedStateLocation
0x140086c8c  nop     dword ptr [rax+rax+00h]
0x140086c91  mov     ebx, eax
0x140086c93  cmp     eax, 80000005h
0x140086c98  jz      short loc_140086CB9
0x140086c9a  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x140086ca1  lea     r15, WPP_fe827790944537bbfef1c01f2ab82bc9_Traceguids
0x140086ca8  jz      loc_140086ED5
0x140086cae  mov     r9d, 8Bh
0x140086cb4  jmp     loc_140086D52
0x140086cb9  mov     edx, [rbp+arg_8]
0x140086cbc  mov     ecx, 40h ; '@'
0x140086cc1  mov     r8d, 64334855h
0x140086cc7  call    cs:__imp_ExAllocatePool2
0x140086cce  nop     dword ptr [rax+rax+00h]
0x140086cd3  xor     ebx, ebx
0x140086cd5  mov     r14, rax
0x140086cd8  test    rax, rax
0x140086cdb  jnz     short loc_140086D02
0x140086cdd  mov     ebx, 0C000009Ah
0x140086ce2  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x140086ce9  lea     r15, WPP_fe827790944537bbfef1c01f2ab82bc9_Traceguids
0x140086cf0  jz      loc_140086ED5
0x140086cf6  mov     r9d, 8Ch
0x140086cfc  mov     dword ptr [rsp+50h+var_28], ebx
0x140086d00  jmp     short loc_140086D56
0x140086d02  mov     eax, [rbp+arg_8]
0x140086d05  lea     r8, aRegistryMachin_13; "\\Registry\\Machine\\System\\CurrentCon"...
0x140086d0c  mov     [rsp+50h+var_20], rbx
0x140086d11  lea     rcx, aUsb; "USB"
0x140086d18  mov     dword ptr [rsp+50h+var_28], eax
0x140086d1c  xor     r9d, r9d
0x140086d1f  xor     edx, edx
0x140086d21  mov     [rsp+50h+var_30], r14
0x140086d26  call    cs:__imp_RtlGetPersistedStateLocation
0x140086d2d  nop     dword ptr [rax+rax+00h]
0x140086d32  mov     ebx, eax
0x140086d34  test    eax, eax
0x140086d36  jns     short loc_140086D72
0x140086d38  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x140086d3f  lea     r15, WPP_fe827790944537bbfef1c01f2ab82bc9_Traceguids
0x140086d46  jz      loc_140086ED5
0x140086d4c  mov     r9d, 8Dh
0x140086d52  mov     dword ptr [rsp+50h+var_28], eax
0x140086d56  mov     r8d, 2
0x140086d5c  mov     dl, r8b
0x140086d5f  mov     rcx, [rsi+40h]
0x140086d63  mov     [rsp+50h+var_30], r15
0x140086d68  call    WPP_RECORDER_SF_d
0x140086d6d  jmp     loc_140086ED5
0x140086d72  xor     ebx, ebx
0x140086d74  xorps   xmm0, xmm0
0x140086d77  movups  [rbp+var_10], xmm0
0x140086d7b  mov     ecx, 7FFFh
0x140086d80  mov     rax, r14
0x140086d83  lea     edx, [rbx+2]
0x140086d86  cmp     [rax], bx
0x140086d89  jz      short loc_140086D94
0x140086d8b  add     rax, rdx
0x140086d8e  sub     rcx, 1
0x140086d92  jnz     short loc_140086D86
0x140086d94  mov     rax, rcx
0x140086d97  neg     rax
0x140086d9a  sbb     ebx, ebx
0x140086d9c  not     ebx
0x140086d9e  and     ebx, 0C000000Dh
0x140086da4  test    rcx, rcx
0x140086da7  jz      loc_140086F86
0x140086dad  add     cx, cx
0x140086db0  mov     qword ptr [rbp+var_10+8], r14
0x140086db4  mov     eax, 0FFFEh
0x140086db9  lea     r8, [rbp+var_10]
0x140086dbd  sub     ax, cx
0x140086dc0  mov     r9d, 20019h
0x140086dc6  mov     word ptr [rbp+var_10], ax
0x140086dca  lea     rcx, [rbp+arg_18]
0x140086dce  add     ax, dx
0x140086dd1  mov     [rsp+50h+var_28], rcx
0x140086dd6  mov     rcx, cs:WdfDriverGlobals
0x140086ddd  xor     edx, edx
0x140086ddf  mov     word ptr [rbp+var_10+2], ax
0x140086de3  mov     rax, cs:WdfFunctions_01015
0x140086dea  mov     [rsp+50h+var_30], 0
0x140086df3  mov     rax, [rax+728h]
0x140086dfa  call    _guard_dispatch_icall
0x140086dff  mov     ebx, eax
0x140086e01  test    eax, eax
0x140086e03  jns     short loc_140086E24
0x140086e05  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x140086e0c  lea     r15, WPP_fe827790944537bbfef1c01f2ab82bc9_Traceguids
0x140086e13  jz      loc_140086ED5
0x140086e19  mov     r9d, 8Fh
0x140086e1f  jmp     loc_140086D52
0x140086e24  mov     rax, cs:WdfFunctions_01015
0x140086e2b  lea     rcx, [rbp+arg_10]
0x140086e2f  mov     rdx, [rbp+arg_18]
0x140086e33  lea     r8, g_UsbAutomaticSurpriseRemovalSubkeyName; "02"
0x140086e3a  mov     [rsp+50h+var_28], rcx
0x140086e3f  mov     r9d, 20019h
0x140086e45  mov     rcx, cs:WdfDriverGlobals
0x140086e4c  mov     rax, [rax+728h]
0x140086e53  mov     [rsp+50h+var_30], 0
0x140086e5c  call    _guard_dispatch_icall
0x140086e61  mov     ebx, eax
0x140086e63  test    eax, eax
0x140086e65  jns     short loc_140086E82
0x140086e67  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x140086e6e  lea     r15, WPP_fe827790944537bbfef1c01f2ab82bc9_Traceguids
0x140086e75  jz      short loc_140086ED5
0x140086e77  mov     r9d, 90h
0x140086e7d  jmp     loc_140086D52
0x140086e82  mov     rax, cs:WdfFunctions_01015
0x140086e89  lea     r8, g_UsbAutomaticSurpriseRemovalAttemptRecoveryFromUsbPowerDrainName; "@B"
0x140086e90  mov     rdx, [rbp+arg_10]
0x140086e94  mov     r9, r15
0x140086e97  mov     rcx, cs:WdfDriverGlobals
0x140086e9e  mov     rax, [rax+780h]
0x140086ea5  call    _guard_dispatch_icall
0x140086eaa  mov     ebx, eax
0x140086eac  test    eax, eax
0x140086eae  jns     short loc_140086ECB
0x140086eb0  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x140086eb7  lea     r15, WPP_fe827790944537bbfef1c01f2ab82bc9_Traceguids
0x140086ebe  jz      short loc_140086ED5
0x140086ec0  mov     r9d, 91h
0x140086ec6  jmp     loc_140086D52
0x140086ecb  mov     r12b, 1
0x140086ece  lea     r15, WPP_fe827790944537bbfef1c01f2ab82bc9_Traceguids
0x140086ed5  test    r13b, r13b
0x140086ed8  jz      short loc_140086F0C
0x140086eda  xor     r13d, r13d
0x140086edd  test    r12b, r12b
0x140086ee0  jnz     short loc_140086F0C
0x140086ee2  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x140086ee9  jz      short loc_140086F09
0x140086eeb  mov     rcx, [rsi+40h]
0x140086eef  lea     r8d, [r13+2]
0x140086ef3  mov     r9d, 92h
0x140086ef9  mov     dword ptr [rsp+50h+var_28], ebx
0x140086efd  mov     dl, 3
0x140086eff  mov     [rsp+50h+var_30], r15
0x140086f04  call    WPP_RECORDER_SF_d
0x140086f09  mov     ebx, r13d
0x140086f0c  test    r14, r14
0x140086f0f  jz      short loc_140086F25
0x140086f11  mov     edx, 64334855h; Tag
0x140086f16  mov     rcx, r14; P
0x140086f19  call    cs:__imp_ExFreePoolWithTag
0x140086f20  nop     dword ptr [rax+rax+00h]
0x140086f25  mov     rdx, [rbp+arg_18]
0x140086f29  test    rdx, rdx
0x140086f2c  jz      short loc_140086F48
0x140086f2e  mov     rax, cs:WdfFunctions_01015
0x140086f35  mov     rcx, cs:WdfDriverGlobals
0x140086f3c  mov     rax, [rax+738h]
0x140086f43  call    _guard_dispatch_icall
0x140086f48  mov     rdx, [rbp+arg_10]
0x140086f4c  test    rdx, rdx
0x140086f4f  jz      short loc_140086F6B
0x140086f51  mov     rax, cs:WdfFunctions_01015
0x140086f58  mov     rcx, cs:WdfDriverGlobals
0x140086f5f  mov     rax, [rax+738h]
0x140086f66  call    _guard_dispatch_icall
0x140086f6b  mov     eax, ebx
0x140086f6d  mov     rbx, [rsp+50h+arg_0]
0x140086f75  add     rsp, 50h
0x140086f79  pop     r15
0x140086f7b  pop     r14
0x140086f7d  pop     r13
0x140086f7f  pop     r12
0x140086f81  pop     rdi
0x140086f82  pop     rsi
0x140086f83  pop     rbp
0x140086f84  retn
0x140086f86  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x140086f8d  lea     r15, WPP_fe827790944537bbfef1c01f2ab82bc9_Traceguids
0x140086f94  jz      loc_140086ED5
0x140086f9a  mov     r9d, 8Eh
0x140086fa0  mov     dword ptr [rsp+50h+var_28], ebx
0x140086fa4  mov     r8d, edx
0x140086fa7  jmp     loc_140086D5F
```
