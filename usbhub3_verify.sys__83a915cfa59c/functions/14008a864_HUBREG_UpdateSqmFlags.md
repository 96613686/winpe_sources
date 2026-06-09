# HUBREG_UpdateSqmFlags

- ea: `0x14008a864`
- end: `0x14008add9`
- name: `HUBREG_UpdateSqmFlags`
- size: `1397`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140015eb0`
- `0x140080590`

## callees

- `0x1400024b8`
- `0x140045570`
- `0x14008a864`

## import_xrefs

- `ntoskrnl!RtlNumberOfSetBits` at `0x14008aacc`
- `ntoskrnl!RtlNumberOfSetBits` at `0x14008aacc`

## pseudocode

```c
signed int __fastcall HUBREG_UpdateSqmFlags(__int64 a1)
{
  __int64 v2; // rdx
  __int64 v3; // rax
  signed int result; // eax
  int v5; // r9d
  signed int v6; // edi
  __int64 v7; // rax
  __int64 *v8; // rdx
  int v9; // r9d
  __int64 *v10; // rdx
  __int64 v11; // [rsp+28h] [rbp-28h]
  int v12; // [rsp+70h] [rbp+20h] BYREF
  __int64 v13; // [rsp+78h] [rbp+28h] BYREF
  __int64 v14; // [rsp+80h] [rbp+30h] BYREF

  v2 = *(_QWORD *)(a1 + 16);
  v12 = 0;
  v14 = 0;
  v13 = 0;
  v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1632))(WdfDriverGlobals, v2);
  result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, __int64, _QWORD, __int64 *))(WdfFunctions_01015 + 384))(
             WdfDriverGlobals,
             v3,
             1,
             131103,
             0,
             &v14);
  if ( result < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_42;
    v5 = 119;
    goto LABEL_41;
  }
  result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, const wchar_t *, __int64, _DWORD, _QWORD, _QWORD, __int64 *))(WdfFunctions_01015 + 1840))(
             WdfDriverGlobals,
             v14,
             L"\b\n",
             131103,
             0,
             0,
             0,
             &v13);
  if ( result < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_42;
    v5 = 120;
    goto LABEL_41;
  }
  result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, const wchar_t *, int *))(WdfFunctions_01015 + 1920))(
             WdfDriverGlobals,
             v13,
             L"\"$",
             &v12);
  v6 = result;
  if ( result >= 0 )
  {
    v9 = v12;
  }
  else
  {
    if ( result != -1073741772 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v7 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
               WdfDriverGlobals,
               WdfDriverGlobals->Driver,
               off_14006B2C0);
        v8 = WPP_fe827790944537bbfef1c01f2ab82bc9_Traceguids;
        LODWORD(v11) = v6;
        LOBYTE(v8) = 2;
        result = WPP_RECORDER_SF_d(
                   *(_QWORD *)(v7 + 64),
                   (_DWORD)v8,
                   2,
                   121,
                   (__int64)WPP_fe827790944537bbfef1c01f2ab82bc9_Traceguids,
                   v11);
      }
      goto LABEL_42;
    }
    v9 = 0;
  }
  v12 = *(_DWORD *)(a1 + 1648) | 8 | v9;
  result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, const wchar_t *))(WdfFunctions_01015 + 1968))(
             WdfDriverGlobals,
             v13,
             L"\"$");
  if ( result < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_42;
    v5 = 122;
    goto LABEL_41;
  }
  result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, const wchar_t *, _QWORD))(WdfFunctions_01015 + 1968))(
             WdfDriverGlobals,
             v13,
             L"(*",
             *(unsigned int *)(*(_QWORD *)(a1 + 8) + 216LL));
  if ( result < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_42;
    v5 = 123;
    goto LABEL_41;
  }
  result = RtlNumberOfSetBits((PRTL_BITMAP)(a1 + 2600));
  if ( !result )
    goto LABEL_42;
  result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, const wchar_t *, __int64, int, __int64))(WdfFunctions_01015 + 1928))(
             WdfDriverGlobals,
             v13,
             L"24",
             4,
             4,
             a1 + 2616);
  if ( result < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_42;
    v5 = 124;
    goto LABEL_41;
  }
  result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, const wchar_t *, __int64, int, __int64))(WdfFunctions_01015 + 1928))(
             WdfDriverGlobals,
             v13,
             L"24",
             4,
             4,
             a1 + 2620);
  if ( result < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_42;
    v5 = 125;
    goto LABEL_41;
  }
  result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, const wchar_t *, __int64, int, __int64))(WdfFunctions_01015 + 1928))(
             WdfDriverGlobals,
             v13,
             L"24",
             4,
             4,
             a1 + 2624);
  if ( result < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_42;
    v5 = 126;
    goto LABEL_41;
  }
  result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, const wchar_t *, __int64, int, __int64))(WdfFunctions_01015 + 1928))(
             WdfDriverGlobals,
             v13,
             L"24",
             4,
             4,
             a1 + 2628);
  if ( result < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_42;
    v5 = 127;
    goto LABEL_41;
  }
  result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, const wchar_t *, __int64, int, __int64))(WdfFunctions_01015 + 1928))(
             WdfDriverGlobals,
             v13,
             L"24",
             4,
             4,
             a1 + 2632);
  if ( result < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_42;
    v5 = 128;
    goto LABEL_41;
  }
  result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, const wchar_t *, __int64, int, __int64))(WdfFunctions_01015 + 1928))(
             WdfDriverGlobals,
             v13,
             L"24",
             4,
             4,
             a1 + 2636);
  if ( result < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_42;
    v5 = 129;
    goto LABEL_41;
  }
  result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, const wchar_t *, __int64, int, __int64))(WdfFunctions_01015 + 1928))(
             WdfDriverGlobals,
             v13,
             L"24",
             4,
             4,
             a1 + 2640);
  if ( result < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v5 = 130;
LABEL_41:
    v10 = WPP_fe827790944537bbfef1c01f2ab82bc9_Traceguids;
    LODWORD(v11) = result;
    LOBYTE(v10) = 2;
    result = WPP_RECORDER_SF_d(
               *(_QWORD *)(*(_QWORD *)(a1 + 8) + 1432LL),
               (_DWORD)v10,
               5,
               v5,
               (__int64)WPP_fe827790944537bbfef1c01f2ab82bc9_Traceguids,
               v11);
  }
LABEL_42:
  if ( v13 )
    result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 1848))(WdfDriverGlobals);
  if ( v14 )
    return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 1848))(WdfDriverGlobals);
  return result;
}

```

## disassembly

```asm
0x14008a864  mov     [rsp-18h+arg_18], rbx
0x14008a869  push    rbp
0x14008a86a  push    rdi
0x14008a86b  push    r14
0x14008a86d  mov     rbp, rsp
0x14008a870  sub     rsp, 50h
0x14008a874  mov     rax, cs:WdfFunctions_01015
0x14008a87b  mov     rbx, rcx
0x14008a87e  mov     rdx, [rcx+10h]
0x14008a882  mov     rcx, cs:WdfDriverGlobals
0x14008a889  mov     [rbp+arg_0], 0
0x14008a890  mov     [rbp+arg_10], 0
0x14008a898  mov     [rbp+arg_8], 0
0x14008a8a0  mov     rax, [rax+660h]
0x14008a8a7  call    _guard_dispatch_icall
0x14008a8ac  mov     rcx, cs:WdfFunctions_01015
0x14008a8b3  mov     rdx, rax
0x14008a8b6  mov     edi, 2001Fh
0x14008a8bb  mov     r8d, 1
0x14008a8c1  mov     r9d, edi
0x14008a8c4  mov     r10, [rcx+180h]
0x14008a8cb  lea     rcx, [rbp+arg_10]
0x14008a8cf  mov     [rsp+50h+var_28], rcx
0x14008a8d4  mov     rax, r10
0x14008a8d7  mov     rcx, cs:WdfDriverGlobals
0x14008a8de  mov     [rsp+50h+var_30], 0
0x14008a8e7  call    _guard_dispatch_icall
0x14008a8ec  test    eax, eax
0x14008a8ee  jns     short loc_14008A90F
0x14008a8f0  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008a8f7  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14008a8fe  jz      loc_14008AD81
0x14008a904  mov     r9d, 77h ; 'w'
0x14008a90a  jmp     loc_14008AD59
0x14008a90f  mov     rax, cs:WdfFunctions_01015
0x14008a916  lea     rcx, [rbp+arg_8]
0x14008a91a  mov     rdx, [rbp+arg_10]
0x14008a91e  lea     r8, g_DeviceCeipKey; "\b\n"
0x14008a925  mov     [rsp+50h+var_18], rcx
0x14008a92a  mov     r9d, edi
0x14008a92d  mov     rcx, cs:WdfDriverGlobals
0x14008a934  mov     rax, [rax+730h]
0x14008a93b  mov     [rsp+50h+var_20], 0
0x14008a944  mov     [rsp+50h+var_28], 0
0x14008a94d  mov     dword ptr [rsp+50h+var_30], 0
0x14008a955  call    _guard_dispatch_icall
0x14008a95a  test    eax, eax
0x14008a95c  jns     short loc_14008A97D
0x14008a95e  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008a965  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14008a96c  jz      loc_14008AD81
0x14008a972  mov     r9d, 78h ; 'x'
0x14008a978  jmp     loc_14008AD59
0x14008a97d  mov     rax, cs:WdfFunctions_01015
0x14008a984  lea     r9, [rbp+arg_0]
0x14008a988  mov     rdx, [rbp+arg_8]
0x14008a98c  lea     r8, g_DeviceInformation; "\"$"
0x14008a993  mov     rcx, cs:WdfDriverGlobals
0x14008a99a  mov     rax, [rax+780h]
0x14008a9a1  call    _guard_dispatch_icall
0x14008a9a6  mov     edi, eax
0x14008a9a8  test    eax, eax
0x14008a9aa  jns     short loc_14008AA16
0x14008a9ac  cmp     eax, 0C0000034h
0x14008a9b1  jz      short loc_14008AA11
0x14008a9b3  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008a9ba  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14008a9c1  jz      loc_14008AD81
0x14008a9c7  mov     rcx, cs:WdfFunctions_01015
0x14008a9ce  mov     r8, cs:off_14006B2C0
0x14008a9d5  mov     rax, [rcx+650h]
0x14008a9dc  mov     rcx, cs:WdfDriverGlobals
0x14008a9e3  mov     rdx, [rcx]
0x14008a9e6  call    _guard_dispatch_icall
0x14008a9eb  lea     rdx, WPP_fe827790944537bbfef1c01f2ab82bc9_Traceguids
0x14008a9f2  mov     dword ptr [rsp+50h+var_28], edi
0x14008a9f6  mov     r9d, 79h ; 'y'
0x14008a9fc  mov     [rsp+50h+var_30], rdx
0x14008aa01  mov     rcx, [rax+40h]
0x14008aa05  lea     r8d, [r9-77h]
0x14008aa09  mov     dl, r8b
0x14008aa0c  jmp     loc_14008AD7C
0x14008aa11  xor     r9d, r9d
0x14008aa14  jmp     short loc_14008AA1A
0x14008aa16  mov     r9d, [rbp+arg_0]
0x14008aa1a  mov     eax, [rbx+670h]
0x14008aa20  lea     r8, g_DeviceInformation; "\"$"
0x14008aa27  mov     rdx, [rbp+arg_8]
0x14008aa2b  or      eax, 8
0x14008aa2e  mov     rcx, cs:WdfDriverGlobals
0x14008aa35  or      r9d, eax
0x14008aa38  mov     rax, cs:WdfFunctions_01015
0x14008aa3f  mov     [rbp+arg_0], r9d
0x14008aa43  mov     rax, [rax+7B0h]
0x14008aa4a  call    _guard_dispatch_icall
0x14008aa4f  test    eax, eax
0x14008aa51  jns     short loc_14008AA72
0x14008aa53  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008aa5a  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14008aa61  jz      loc_14008AD81
0x14008aa67  mov     r9d, 7Ah ; 'z'
0x14008aa6d  jmp     loc_14008AD59
0x14008aa72  mov     r9, [rbx+8]
0x14008aa76  lea     r8, g_PortInterconnectType; "(*"
0x14008aa7d  mov     rax, cs:WdfFunctions_01015
0x14008aa84  mov     rdx, [rbp+arg_8]
0x14008aa88  mov     rcx, cs:WdfDriverGlobals
0x14008aa8f  mov     r9d, [r9+0D8h]
0x14008aa96  mov     rax, [rax+7B0h]
0x14008aa9d  call    _guard_dispatch_icall
0x14008aaa2  test    eax, eax
0x14008aaa4  jns     short loc_14008AAC5
0x14008aaa6  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008aaad  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14008aab4  jz      loc_14008AD81
0x14008aaba  mov     r9d, 7Bh ; '{'
0x14008aac0  jmp     loc_14008AD59
0x14008aac5  lea     rcx, [rbx+0A28h]; BitMapHeader
0x14008aacc  call    cs:__imp_RtlNumberOfSetBits
0x14008aad3  nop     dword ptr [rax+rax+00h]
0x14008aad8  test    eax, eax
0x14008aada  jz      loc_14008AD81
0x14008aae0  mov     rax, cs:WdfFunctions_01015
0x14008aae7  lea     rdi, [rbx+0A38h]
0x14008aaee  mov     rdx, [rbp+arg_8]
0x14008aaf2  lea     r8, g_DescriptorValidationInfo0; "24"
0x14008aaf9  mov     rcx, cs:WdfDriverGlobals
0x14008ab00  mov     r14d, 4
0x14008ab06  mov     [rsp+50h+var_28], rdi
0x14008ab0b  mov     r9d, r14d
0x14008ab0e  mov     rax, [rax+788h]
0x14008ab15  mov     dword ptr [rsp+50h+var_30], r14d
0x14008ab1a  call    _guard_dispatch_icall
0x14008ab1f  test    eax, eax
0x14008ab21  jns     short loc_14008AB40
0x14008ab23  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008ab2a  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14008ab31  jz      loc_14008AD81
0x14008ab37  lea     r9d, [r14+78h]
0x14008ab3b  jmp     loc_14008AD59
0x14008ab40  mov     rax, cs:WdfFunctions_01015
0x14008ab47  lea     rcx, [rdi+4]
0x14008ab4b  mov     rdx, [rbp+arg_8]
0x14008ab4f  lea     r8, g_DescriptorValidationInfo1; "24"
0x14008ab56  mov     [rsp+50h+var_28], rcx
0x14008ab5b  mov     r9d, r14d
0x14008ab5e  mov     rcx, cs:WdfDriverGlobals
0x14008ab65  mov     rax, [rax+788h]
0x14008ab6c  mov     dword ptr [rsp+50h+var_30], r14d
0x14008ab71  call    _guard_dispatch_icall
0x14008ab76  test    eax, eax
0x14008ab78  jns     short loc_14008AB99
0x14008ab7a  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008ab81  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14008ab88  jz      loc_14008AD81
0x14008ab8e  mov     r9d, 7Dh ; '}'
0x14008ab94  jmp     loc_14008AD59
0x14008ab99  mov     rax, cs:WdfFunctions_01015
0x14008aba0  lea     rcx, [rbx+0A40h]
0x14008aba7  mov     rdx, [rbp+arg_8]
0x14008abab  lea     r8, g_DescriptorValidationInfo2; "24"
0x14008abb2  mov     [rsp+50h+var_28], rcx
0x14008abb7  mov     r9d, r14d
0x14008abba  mov     rcx, cs:WdfDriverGlobals
0x14008abc1  mov     rax, [rax+788h]
0x14008abc8  mov     dword ptr [rsp+50h+var_30], r14d
0x14008abcd  call    _guard_dispatch_icall
0x14008abd2  test    eax, eax
0x14008abd4  jns     short loc_14008ABF5
0x14008abd6  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008abdd  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14008abe4  jz      loc_14008AD81
0x14008abea  mov     r9d, 7Eh ; '~'
0x14008abf0  jmp     loc_14008AD59
0x14008abf5  mov     rax, cs:WdfFunctions_01015
0x14008abfc  lea     rcx, [rbx+0A44h]
0x14008ac03  mov     rdx, [rbp+arg_8]
0x14008ac07  lea     r8, g_DescriptorValidationInfo3; "24"
0x14008ac0e  mov     [rsp+50h+var_28], rcx
0x14008ac13  mov     r9d, r14d
0x14008ac16  mov     rcx, cs:WdfDriverGlobals
0x14008ac1d  mov     rax, [rax+788h]
0x14008ac24  mov     dword ptr [rsp+50h+var_30], r14d
0x14008ac29  call    _guard_dispatch_icall
0x14008ac2e  test    eax, eax
0x14008ac30  jns     short loc_14008AC51
0x14008ac32  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008ac39  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14008ac40  jz      loc_14008AD81
0x14008ac46  mov     r9d, 7Fh
0x14008ac4c  jmp     loc_14008AD59
0x14008ac51  mov     rax, cs:WdfFunctions_01015
0x14008ac58  lea     rcx, [rbx+0A48h]
0x14008ac5f  mov     rdx, [rbp+arg_8]
0x14008ac63  lea     r8, g_DescriptorValidationInfo4; "24"
0x14008ac6a  mov     [rsp+50h+var_28], rcx
0x14008ac6f  mov     r9d, r14d
0x14008ac72  mov     rcx, cs:WdfDriverGlobals
0x14008ac79  mov     rax, [rax+788h]
0x14008ac80  mov     dword ptr [rsp+50h+var_30], r14d
0x14008ac85  call    _guard_dispatch_icall
0x14008ac8a  test    eax, eax
0x14008ac8c  jns     short loc_14008ACAD
0x14008ac8e  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008ac95  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14008ac9c  jz      loc_14008AD81
0x14008aca2  mov     r9d, 80h
0x14008aca8  jmp     loc_14008AD59
0x14008acad  mov     rax, cs:WdfFunctions_01015
0x14008acb4  lea     rcx, [rbx+0A4Ch]
0x14008acbb  mov     rdx, [rbp+arg_8]
0x14008acbf  lea     r8, g_DescriptorValidationInfo5; "24"
0x14008acc6  mov     [rsp+50h+var_28], rcx
0x14008accb  mov     r9d, r14d
0x14008acce  mov     rcx, cs:WdfDriverGlobals
0x14008acd5  mov     rax, [rax+788h]
0x14008acdc  mov     dword ptr [rsp+50h+var_30], r14d
0x14008ace1  call    _guard_dispatch_icall
0x14008ace6  test    eax, eax
0x14008ace8  jns     short loc_14008AD06
0x14008acea  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008acf1  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14008acf8  jz      loc_14008AD81
0x14008acfe  mov     r9d, 81h
0x14008ad04  jmp     short loc_14008AD59
0x14008ad06  mov     rax, cs:WdfFunctions_01015
0x14008ad0d  lea     rcx, [rbx+0A50h]
0x14008ad14  mov     rdx, [rbp+arg_8]
0x14008ad18  lea     r8, g_DescriptorValidationInfo6; "24"
0x14008ad1f  mov     [rsp+50h+var_28], rcx
0x14008ad24  mov     r9d, r14d
0x14008ad27  mov     rcx, cs:WdfDriverGlobals
0x14008ad2e  mov     rax, [rax+788h]
0x14008ad35  mov     dword ptr [rsp+50h+var_30], r14d
0x14008ad3a  call    _guard_dispatch_icall
0x14008ad3f  test    eax, eax
0x14008ad41  jns     short loc_14008AD81
0x14008ad43  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008ad4a  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14008ad51  jz      short loc_14008AD81
0x14008ad53  mov     r9d, 82h
0x14008ad59  mov     rcx, [rbx+8]
0x14008ad5d  lea     rdx, WPP_fe827790944537bbfef1c01f2ab82bc9_Traceguids
0x14008ad64  mov     dword ptr [rsp+50h+var_28], eax
0x14008ad68  mov     r8d, 5
0x14008ad6e  mov     [rsp+50h+var_30], rdx
0x14008ad73  mov     dl, 2
0x14008ad75  mov     rcx, [rcx+598h]
0x14008ad7c  call    WPP_RECORDER_SF_d
0x14008ad81  mov     rdx, [rbp+arg_8]
0x14008ad85  test    rdx, rdx
0x14008ad88  jz      short loc_14008ADA4
0x14008ad8a  mov     rax, cs:WdfFunctions_01015
0x14008ad91  mov     rcx, cs:WdfDriverGlobals
0x14008ad98  mov     rax, [rax+738h]
0x14008ad9f  call    _guard_dispatch_icall
0x14008ada4  mov     rdx, [rbp+arg_10]
0x14008ada8  test    rdx, rdx
0x14008adab  jz      short loc_14008ADC7
0x14008adad  mov     rax, cs:WdfFunctions_01015
0x14008adb4  mov     rcx, cs:WdfDriverGlobals
0x14008adbb  mov     rax, [rax+738h]
0x14008adc2  call    _guard_dispatch_icall
0x14008adc7  mov     rbx, [rsp+50h+arg_18]
0x14008adcf  add     rsp, 50h
0x14008add3  pop     r14
0x14008add5  pop     rdi
0x14008add6  pop     rbp
0x14008add7  retn
```
