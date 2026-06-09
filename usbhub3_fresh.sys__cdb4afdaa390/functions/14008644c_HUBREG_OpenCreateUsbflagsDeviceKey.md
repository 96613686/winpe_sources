# HUBREG_OpenCreateUsbflagsDeviceKey

- ea: `0x14008644c`
- end: `0x14008689f`
- name: `HUBREG_OpenCreateUsbflagsDeviceKey`
- size: `1107`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int, _QWORD *, _QWORD *, char, __int64)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1400853b0`
- `0x140087aa8`
- `0x140088744`

## callees

- `0x1400024b8`
- `0x14000f648`
- `0x140045530`
- `0x140045570`
- `0x14008644c`

## import_xrefs

- `ntoskrnl!RtlGetPersistedStateLocation` at `0x1400864f5`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x140086554`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x1400864f5`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x140086554`
- `ntoskrnl!ExFreePoolWithTag` at `0x140086807`
- `ntoskrnl!ExFreePoolWithTag` at `0x140086807`
- `ntoskrnl!ExAllocatePool2` at `0x14008651b`
- `ntoskrnl!ExAllocatePool2` at `0x14008651b`

## string_xrefs

- `0x1400864c0`: `\Registry\Machine\System\CurrentControlSet\Control\usbflags`

## pseudocode

```c
__int64 __fastcall HUBREG_OpenCreateUsbflagsDeviceKey(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        _QWORD *a5,
        _QWORD *a6,
        char a7,
        __int64 a8)
{
  _QWORD *v8; // rsi
  NTSTATUS PersistedStateLocation; // ebx
  __int64 Pool2; // rax
  _WORD *v11; // rsi
  __int64 v12; // rcx
  _WORD *v13; // rax
  const wchar_t *v14; // rax
  __int16 v15; // cx
  unsigned int v16; // r14d
  int v17; // edx
  int v18; // r9d
  __int64 v20; // [rsp+28h] [rbp-C1h]
  __int64 v21; // [rsp+28h] [rbp-C1h]
  __int64 v22; // [rsp+28h] [rbp-C1h]
  unsigned int v23; // [rsp+50h] [rbp-99h] BYREF
  __int64 v24; // [rsp+58h] [rbp-91h] BYREF
  __int128 v25; // [rsp+60h] [rbp-89h] BYREF
  unsigned int v26; // [rsp+70h] [rbp-79h]
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-71h] BYREF
  _QWORD *v28; // [rsp+88h] [rbp-61h]
  __int64 v29; // [rsp+90h] [rbp-59h]
  __int64 v30; // [rsp+98h] [rbp-51h]
  __int64 v31; // [rsp+A0h] [rbp-49h]
  char v32; // [rsp+A8h] [rbp-41h] BYREF

  v8 = a5;
  v30 = a2;
  v26 = a4;
  v29 = a3;
  v31 = a1;
  v28 = a5;
  *(_QWORD *)&DestinationString.Length = 3407872;
  DestinationString.Buffer = (wchar_t *)&v32;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  if ( a5 )
    *a5 = 0;
  *a6 = 0;
  if ( a7 != 1 )
  {
    v11 = 0;
    v12 = 0x7FFF;
    v14 = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\usbflags";
    while ( *v14 )
    {
      ++v14;
      if ( !--v12 )
        goto LABEL_22;
    }
    *((_QWORD *)&v25 + 1) = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\usbflags";
    goto LABEL_21;
  }
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"UsbFlags",
                             0,
                             L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\usbflags",
                             0,
                             0,
                             0,
                             &v23);
  if ( PersistedStateLocation == -2147483643 )
  {
    Pool2 = ExAllocatePool2(64, v23, 1681082453);
    v11 = (_WORD *)Pool2;
    if ( !Pool2 )
      goto LABEL_22;
    PersistedStateLocation = RtlGetPersistedStateLocation(
                               L"UsbFlags",
                               0,
                               L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\usbflags",
                               0,
                               Pool2,
                               v23,
                               0);
    if ( PersistedStateLocation < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v21) = PersistedStateLocation;
        WPP_RECORDER_SF_d(a8, 2, 5, 10, (__int64)WPP_fe827790944537bbfef1c01f2ab82bc9_Traceguids, v21);
      }
      goto LABEL_39;
    }
    v12 = 0x7FFF;
    v25 = 0;
    v13 = v11;
    while ( *v13 )
    {
      ++v13;
      if ( !--v12 )
        goto LABEL_22;
    }
    *((_QWORD *)&v25 + 1) = v11;
LABEL_21:
    v15 = 2 * v12;
    LOWORD(v25) = -2 - v15;
    WORD1(v25) = -v15;
LABEL_22:
    v16 = v26;
    PersistedStateLocation = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int128 *, _QWORD, _QWORD, __int64 *))(WdfFunctions_01015 + 1832))(
                               WdfDriverGlobals,
                               0,
                               &v25,
                               v26,
                               0,
                               &v24);
    if ( PersistedStateLocation == -1073741772 )
    {
      if ( a7 != 1 )
      {
LABEL_26:
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_38;
        v18 = 12;
        goto LABEL_37;
      }
      PersistedStateLocation = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int128 *, _QWORD, _DWORD, _QWORD, _QWORD, __int64 *))(WdfFunctions_01015 + 1840))(
                                 WdfDriverGlobals,
                                 0,
                                 &v25,
                                 v16,
                                 0,
                                 0,
                                 0,
                                 &v24);
    }
    if ( PersistedStateLocation < 0 )
      goto LABEL_26;
    PersistedStateLocation = RtlUnicodeStringPrintf(&DestinationString, L"%S%S%S", v31, v30, v29);
    if ( PersistedStateLocation < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_38;
      v18 = 13;
      goto LABEL_37;
    }
    PersistedStateLocation = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *, __int64, _QWORD, _QWORD *))(WdfFunctions_01015 + 1832))(
                               WdfDriverGlobals,
                               v24,
                               &DestinationString,
                               131097,
                               0,
                               a6);
    if ( PersistedStateLocation == -1073741772 )
    {
      if ( a7 != 1 )
      {
LABEL_35:
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_38;
        v18 = 14;
LABEL_37:
        LODWORD(v22) = PersistedStateLocation;
        LOBYTE(v17) = 2;
        WPP_RECORDER_SF_d(a8, v17, 5, v18, (__int64)WPP_fe827790944537bbfef1c01f2ab82bc9_Traceguids, v22);
LABEL_38:
        if ( !v11 )
        {
LABEL_40:
          v8 = v28;
          goto LABEL_41;
        }
LABEL_39:
        ExFreePoolWithTag(v11, 0x64334855u);
        goto LABEL_40;
      }
      PersistedStateLocation = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *, __int64, _DWORD, _QWORD, _QWORD, _QWORD *))(WdfFunctions_01015 + 1840))(
                                 WdfDriverGlobals,
                                 v24,
                                 &DestinationString,
                                 983103,
                                 0,
                                 0,
                                 0,
                                 a6);
    }
    if ( PersistedStateLocation >= 0 )
      goto LABEL_38;
    goto LABEL_35;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LODWORD(v20) = PersistedStateLocation;
    WPP_RECORDER_SF_d(a8, 2, 5, 11, (__int64)WPP_fe827790944537bbfef1c01f2ab82bc9_Traceguids, v20);
  }
LABEL_41:
  if ( PersistedStateLocation >= 0 )
  {
    if ( !v8 )
    {
LABEL_48:
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 1848))(WdfDriverGlobals);
      return (unsigned int)PersistedStateLocation;
    }
    *v8 = v24;
  }
  else
  {
    if ( *a6 )
    {
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 1848))(WdfDriverGlobals);
      *a6 = 0;
    }
    if ( v24 )
      goto LABEL_48;
  }
  return (unsigned int)PersistedStateLocation;
}

```

## disassembly

```asm
0x14008644c  push    rbp
0x14008644e  push    rbx
0x14008644f  push    rsi
0x140086450  push    rdi
0x140086451  push    r13
0x140086453  push    r14
0x140086455  push    r15
0x140086457  lea     rbp, [rsp-7]
0x14008645c  sub     rsp, 0F0h
0x140086463  mov     rax, cs:__security_cookie
0x14008646a  xor     rax, rsp
0x14008646d  mov     [rbp+37h+var_40], rax
0x140086471  mov     rsi, [rbp+37h+arg_20]
0x140086475  lea     rax, [rbp+37h+var_78]
0x140086479  mov     r15, [rbp+37h+arg_28]
0x14008647d  xorps   xmm0, xmm0
0x140086480  mov     r13, [rbp+37h+arg_38]
0x140086484  mov     [rbp+37h+var_88], rdx
0x140086488  xor     edx, edx
0x14008648a  mov     [rbp+37h+var_B0], r9d
0x14008648e  mov     [rbp+37h+var_90], r8
0x140086492  mov     [rbp+37h+var_80], rcx
0x140086496  mov     [rbp+37h+var_98], rsi
0x14008649a  mov     qword ptr [rbp+37h+DestinationString.Length], 340000h
0x1400864a2  mov     [rbp+37h+DestinationString.Buffer], rax
0x1400864a6  mov     [rsp+120h+var_D0], edx
0x1400864aa  mov     [rsp+120h+var_C8], rdx
0x1400864af  movups  [rsp+120h+var_C0], xmm0
0x1400864b4  test    rsi, rsi
0x1400864b7  jz      short loc_1400864BC
0x1400864b9  mov     [rsi], rdx
0x1400864bc  cmp     [rbp+37h+arg_30], 1
0x1400864c0  lea     r14, aRegistryMachin_9; "\\Registry\\Machine\\System\\CurrentCon"...
0x1400864c7  mov     [r15], rdx
0x1400864ca  mov     edi, 2
0x1400864cf  jnz     loc_140086608
0x1400864d5  lea     rax, [rsp+120h+var_D0]
0x1400864da  xor     r9d, r9d
0x1400864dd  mov     [rsp+120h+var_F0], rax
0x1400864e2  lea     rcx, aUsbflags; "UsbFlags"
0x1400864e9  mov     dword ptr [rsp+120h+var_F8], edx
0x1400864ed  mov     r8, r14
0x1400864f0  mov     [rsp+120h+var_100], rdx
0x1400864f5  call    cs:__imp_RtlGetPersistedStateLocation
0x1400864fc  nop     dword ptr [rax+rax+00h]
0x140086501  mov     ebx, eax
0x140086503  cmp     eax, 80000005h
0x140086508  jnz     loc_1400865CA
0x14008650e  mov     edx, [rsp+120h+var_D0]
0x140086512  lea     ecx, [rdi+3Eh]
0x140086515  mov     r8d, 64334855h
0x14008651b  call    cs:__imp_ExAllocatePool2
0x140086522  nop     dword ptr [rax+rax+00h]
0x140086527  xor     edx, edx
0x140086529  mov     rsi, rax
0x14008652c  test    rax, rax
0x14008652f  jz      loc_140086640
0x140086535  mov     eax, [rsp+120h+var_D0]
0x140086539  lea     rcx, aUsbflags; "UsbFlags"
0x140086540  mov     [rsp+120h+var_F0], rdx
0x140086545  xor     r9d, r9d
0x140086548  mov     dword ptr [rsp+120h+var_F8], eax
0x14008654c  mov     r8, r14
0x14008654f  mov     [rsp+120h+var_100], rsi
0x140086554  call    cs:__imp_RtlGetPersistedStateLocation
0x14008655b  nop     dword ptr [rax+rax+00h]
0x140086560  xor     edx, edx
0x140086562  mov     ebx, eax
0x140086564  test    eax, eax
0x140086566  jns     short loc_1400865A3
0x140086568  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008656f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140086576  jz      loc_1400867FF
0x14008657c  lea     rax, WPP_fe827790944537bbfef1c01f2ab82bc9_Traceguids
0x140086583  mov     dword ptr [rsp+120h+var_F8], ebx
0x140086587  lea     r9d, [rdi+8]
0x14008658b  mov     [rsp+120h+var_100], rax
0x140086590  mov     edx, edi
0x140086592  lea     r8d, [rdi+3]
0x140086596  mov     rcx, r13
0x140086599  call    WPP_RECORDER_SF_d
0x14008659e  jmp     loc_1400867FF
0x1400865a3  xorps   xmm0, xmm0
0x1400865a6  mov     ecx, 7FFFh
0x1400865ab  movups  [rsp+120h+var_C0], xmm0
0x1400865b0  mov     rax, rsi
0x1400865b3  cmp     [rax], dx
0x1400865b6  jz      short loc_1400865C3
0x1400865b8  add     rax, rdi
0x1400865bb  sub     rcx, 1
0x1400865bf  jnz     short loc_1400865B3
0x1400865c1  jmp     short loc_140086640
0x1400865c3  mov     qword ptr [rsp+120h+var_C0+8], rsi
0x1400865c8  jmp     short loc_140086628
0x1400865ca  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400865d1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400865d8  jz      loc_140086817
0x1400865de  mov     r9d, 0Bh
0x1400865e4  mov     dword ptr [rsp+120h+var_F8], ebx
0x1400865e8  lea     rax, WPP_fe827790944537bbfef1c01f2ab82bc9_Traceguids
0x1400865ef  mov     rdx, rdi
0x1400865f2  mov     rcx, r13
0x1400865f5  mov     [rsp+120h+var_100], rax
0x1400865fa  lea     r8d, [r9-6]
0x1400865fe  call    WPP_RECORDER_SF_d
0x140086603  jmp     loc_140086817
0x140086608  mov     rsi, rdx
0x14008660b  mov     ecx, 7FFFh
0x140086610  mov     rax, r14
0x140086613  cmp     [rax], dx
0x140086616  jz      short loc_140086623
0x140086618  add     rax, rdi
0x14008661b  sub     rcx, 1
0x14008661f  jnz     short loc_140086613
0x140086621  jmp     short loc_140086640
0x140086623  mov     qword ptr [rsp+120h+var_C0+8], r14
0x140086628  add     cx, cx
0x14008662b  mov     eax, 0FFFEh
0x140086630  sub     ax, cx
0x140086633  mov     word ptr [rsp+120h+var_C0], ax
0x140086638  add     ax, di
0x14008663b  mov     word ptr [rsp+120h+var_C0+2], ax
0x140086640  mov     rax, cs:WdfFunctions_01015
0x140086647  lea     rcx, [rsp+120h+var_C8]
0x14008664c  mov     r14d, [rbp+37h+var_B0]
0x140086650  lea     r8, [rsp+120h+var_C0]
0x140086655  mov     [rsp+120h+var_F8], rcx
0x14008665a  mov     r9d, r14d
0x14008665d  mov     rcx, cs:WdfDriverGlobals
0x140086664  mov     rax, [rax+728h]
0x14008666b  mov     [rsp+120h+var_100], rdx
0x140086670  xor     edx, edx
0x140086672  call    _guard_dispatch_icall
0x140086677  mov     ebx, eax
0x140086679  cmp     eax, 0C0000034h
0x14008667e  jnz     short loc_1400866C6
0x140086680  cmp     [rbp+37h+arg_30], 1
0x140086684  jnz     short loc_1400866CA
0x140086686  mov     rax, cs:WdfFunctions_01015
0x14008668d  lea     rcx, [rsp+120h+var_C8]
0x140086692  mov     [rsp+120h+var_E8], rcx
0x140086697  lea     r8, [rsp+120h+var_C0]
0x14008669c  xor     ecx, ecx
0x14008669e  mov     r9d, r14d
0x1400866a1  mov     [rsp+120h+var_F0], rcx
0x1400866a6  xor     edx, edx
0x1400866a8  mov     rax, [rax+730h]
0x1400866af  mov     [rsp+120h+var_F8], rcx
0x1400866b4  mov     dword ptr [rsp+120h+var_100], ecx
0x1400866b8  mov     rcx, cs:WdfDriverGlobals
0x1400866bf  call    _guard_dispatch_icall
0x1400866c4  mov     ebx, eax
0x1400866c6  test    ebx, ebx
0x1400866c8  jns     short loc_1400866E9
0x1400866ca  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400866d1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400866d8  jz      loc_1400867FA
0x1400866de  mov     r9d, 0Ch
0x1400866e4  jmp     loc_1400867D9
0x1400866e9  mov     rax, [rbp+37h+var_90]
0x1400866ed  lea     rdx, aSSS; "%S%S%S"
0x1400866f4  mov     r9, [rbp+37h+var_88]
0x1400866f8  lea     rcx, [rbp+37h+DestinationString]; DestinationString
0x1400866fc  mov     r8, [rbp+37h+var_80]
0x140086700  mov     [rsp+120h+var_100], rax
0x140086705  call    RtlUnicodeStringPrintf
0x14008670a  mov     ebx, eax
0x14008670c  test    eax, eax
0x14008670e  jns     short loc_14008672F
0x140086710  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140086717  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14008671e  jz      loc_1400867FA
0x140086724  mov     r9d, 0Dh
0x14008672a  jmp     loc_1400867D9
0x14008672f  mov     rax, cs:WdfFunctions_01015
0x140086736  lea     r8, [rbp+37h+DestinationString]
0x14008673a  mov     rdx, [rsp+120h+var_C8]
0x14008673f  mov     r9d, 20019h
0x140086745  mov     rcx, cs:WdfDriverGlobals
0x14008674c  mov     [rsp+120h+var_F8], r15
0x140086751  mov     rax, [rax+728h]
0x140086758  mov     [rsp+120h+var_100], 0
0x140086761  call    _guard_dispatch_icall
0x140086766  mov     ebx, eax
0x140086768  cmp     eax, 0C0000034h
0x14008676d  jnz     short loc_1400867BF
0x14008676f  cmp     [rbp+37h+arg_30], 1
0x140086773  jnz     short loc_1400867C3
0x140086775  mov     rax, cs:WdfFunctions_01015
0x14008677c  lea     r8, [rbp+37h+DestinationString]
0x140086780  mov     rdx, [rsp+120h+var_C8]
0x140086785  mov     r9d, 0F003Fh
0x14008678b  mov     rcx, cs:WdfDriverGlobals
0x140086792  mov     [rsp+120h+var_E8], r15
0x140086797  mov     rax, [rax+730h]
0x14008679e  mov     [rsp+120h+var_F0], 0
0x1400867a7  mov     [rsp+120h+var_F8], 0
0x1400867b0  mov     dword ptr [rsp+120h+var_100], 0
0x1400867b8  call    _guard_dispatch_icall
0x1400867bd  mov     ebx, eax
0x1400867bf  test    ebx, ebx
0x1400867c1  jns     short loc_1400867FA
0x1400867c3  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400867ca  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400867d1  jz      short loc_1400867FA
0x1400867d3  mov     r9d, 0Eh
0x1400867d9  lea     rax, WPP_fe827790944537bbfef1c01f2ab82bc9_Traceguids
0x1400867e0  mov     dword ptr [rsp+120h+var_F8], ebx
0x1400867e4  mov     r8d, 5
0x1400867ea  mov     [rsp+120h+var_100], rax
0x1400867ef  mov     dl, dil
0x1400867f2  mov     rcx, r13
0x1400867f5  call    WPP_RECORDER_SF_d
0x1400867fa  test    rsi, rsi
0x1400867fd  jz      short loc_140086813
0x1400867ff  mov     edx, 64334855h; Tag
0x140086804  mov     rcx, rsi; P
0x140086807  call    cs:__imp_ExFreePoolWithTag
0x14008680e  nop     dword ptr [rax+rax+00h]
0x140086813  mov     rsi, [rbp+37h+var_98]
0x140086817  test    ebx, ebx
0x140086819  jns     short loc_140086850
0x14008681b  mov     rdx, [r15]
0x14008681e  test    rdx, rdx
0x140086821  jz      short loc_140086844
0x140086823  mov     rax, cs:WdfFunctions_01015
0x14008682a  mov     rcx, cs:WdfDriverGlobals
0x140086831  mov     rax, [rax+738h]
0x140086838  call    _guard_dispatch_icall
0x14008683d  mov     qword ptr [r15], 0
0x140086844  mov     rdx, [rsp+120h+var_C8]
0x140086849  test    rdx, rdx
0x14008684c  jz      short loc_14008687E
0x14008684e  jmp     short loc_140086864
0x140086850  test    rsi, rsi
0x140086853  jz      short loc_14008685F
0x140086855  mov     rax, [rsp+120h+var_C8]
0x14008685a  mov     [rsi], rax
0x14008685d  jmp     short loc_14008687E
0x14008685f  mov     rdx, [rsp+120h+var_C8]
0x140086864  mov     rax, cs:WdfFunctions_01015
0x14008686b  mov     rcx, cs:WdfDriverGlobals
0x140086872  mov     rax, [rax+738h]
0x140086879  call    _guard_dispatch_icall
0x14008687e  mov     eax, ebx
0x140086880  mov     rcx, [rbp+37h+var_40]
0x140086884  xor     rcx, rsp; StackCookie
0x140086887  call    __security_check_cookie
0x14008688c  add     rsp, 0F0h
0x140086893  pop     r15
0x140086895  pop     r14
0x140086897  pop     r13
0x140086899  pop     rdi
0x14008689a  pop     rsi
0x14008689b  pop     rbx
0x14008689c  pop     rbp
0x14008689d  retn
```
