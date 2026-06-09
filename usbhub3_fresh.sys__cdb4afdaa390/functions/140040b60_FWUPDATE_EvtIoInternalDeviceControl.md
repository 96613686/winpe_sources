# FWUPDATE_EvtIoInternalDeviceControl

- ea: `0x140040b60`
- end: `0x14004131f`
- name: `FWUPDATE_EvtIoInternalDeviceControl`
- size: `1983`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1400024b8`
- `0x1400025a4`
- `0x1400067ac`
- `0x14001c674`
- `0x140040b60`
- `0x140045530`
- `0x140045570`
- `0x140045640`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140040eb9`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140040eb9`

## pseudocode

```c
__int64 __fastcall FWUPDATE_EvtIoInternalDeviceControl(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5)
{
  __int64 v7; // rbx
  __int64 v8; // rax
  int v9; // edx
  __int64 v10; // r14
  __int64 v11; // rsi
  unsigned int v12; // edi
  __int64 v13; // rax
  __int64 result; // rax
  int v15; // edx
  unsigned int v16; // eax
  int v17; // ecx
  int v18; // edx
  __int64 v19; // rcx
  PVOID v20; // r15
  int v21; // r9d
  int v22; // edx
  int v23; // r9d
  unsigned int v24; // r14d
  __int64 v25; // rax
  char v26; // al
  int v27; // edx
  __int64 v28; // r8
  __int64 v29; // rax
  __int64 Priority; // [rsp+28h] [rbp-58h]
  int Prioritya; // [rsp+28h] [rbp-58h]
  int Priorityb; // [rsp+28h] [rbp-58h]
  __int128 v33; // [rsp+40h] [rbp-40h] BYREF
  __int128 v34; // [rsp+50h] [rbp-30h]
  __int64 v35; // [rsp+60h] [rbp-20h]
  __int128 v36; // [rsp+68h] [rbp-18h] BYREF

  v35 = 0;
  v33 = 0;
  LOWORD(v33) = 40;
  v7 = 0;
  v36 = 0;
  v34 = 0;
  v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1256))(WdfDriverGlobals, a1);
  v10 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
          WdfDriverGlobals,
          v8,
          off_14006B248);
  v11 = *(_QWORD *)v10;
  if ( *(_BYTE *)(v10 + 24) == 1 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_(*(_QWORD *)(v11 + 2536), v9, 3, 23, (__int64)WPP_2fd11ae104fa34a9334eddada324a17a_Traceguids);
    }
    v12 = -1073741810;
    goto LABEL_80;
  }
  LOBYTE(v12) = 0;
  v36 = 0x800000010uLL;
  if ( a5 != 2228227 )
  {
    if ( a5 == 2228243 )
    {
      v13 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 336))(
              WdfDriverGlobals,
              *(_QWORD *)(v11 + 16));
      result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, __int128 *))(WdfFunctions_01015 + 2024))(
                 WdfDriverGlobals,
                 a2,
                 v13,
                 &v36);
      if ( (_BYTE)result )
        return result;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        Prioritya = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 2032))(
                      WdfDriverGlobals,
                      a2);
        LOBYTE(v15) = 2;
        WPP_RECORDER_SF_d(
          *(_QWORD *)(v11 + 2536),
          v15,
          3,
          33,
          (__int64)WPP_2fd11ae104fa34a9334eddada324a17a_Traceguids,
          Prioritya);
      }
      v16 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 2032))(WdfDriverGlobals, a2);
      result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01015 + 2104))(
                 WdfDriverGlobals,
                 a2,
                 v16);
      goto LABEL_13;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(v11 + 2536),
        v9,
        3,
        34,
        (__int64)WPP_2fd11ae104fa34a9334eddada324a17a_Traceguids,
        a5);
    }
    goto LABEL_79;
  }
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int128 *))(WdfFunctions_01015 + 2128))(
    WdfDriverGlobals,
    a2,
    &v33);
  v7 = *((_QWORD *)&v33 + 1);
  v18 = *(unsigned __int16 *)(*((_QWORD *)&v33 + 1) + 2LL);
  *(_DWORD *)(*((_QWORD *)&v33 + 1) + 4LL) = 0;
  switch ( v18 )
  {
    case 0:
      if ( *(_WORD *)v7 != 64 )
        goto LABEL_78;
      v29 = *(_QWORD *)(v7 + 24);
      if ( *(_BYTE *)(v29 + 4) != 1 || *(_BYTE *)(v29 + 5) != 1 )
        goto LABEL_78;
      if ( v29 )
      {
        if ( *(_BYTE *)(v7 + 42) || *(_BYTE *)(v7 + 43) || *(_DWORD *)(v7 + 56) )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v21 = 28;
            goto LABEL_77;
          }
          goto LABEL_78;
        }
        *(_QWORD *)(v7 + 48) = v10 + 16;
        *(_QWORD *)(v7 + 32) = v10 + 8;
      }
      else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v18) = 4;
        WPP_RECORDER_SF_(*(_QWORD *)(v11 + 2536), v18, 3, 27, (__int64)WPP_2fd11ae104fa34a9334eddada324a17a_Traceguids);
      }
      goto LABEL_62;
    case 1:
      if ( *(_WORD *)v7 != 56
        || *(_QWORD *)(v7 + 24) != (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1256))(
                                     WdfDriverGlobals,
                                     a1)
        || *(_BYTE *)(v7 + 34)
        || *(_BYTE *)(v7 + 35)
        || *(_DWORD *)(v7 + 48) )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v21 = 29;
          goto LABEL_77;
        }
LABEL_78:
        *(_DWORD *)(v7 + 4) = -2147482880;
LABEL_79:
        v12 = -1073741811;
        goto LABEL_80;
      }
      *(_QWORD *)(v7 + 40) = v10 + 16;
LABEL_62:
      result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01015 + 2104))(
                 WdfDriverGlobals,
                 a2,
                 0);
      goto LABEL_81;
    case 8:
LABEL_49:
      if ( (*(_BYTE *)(v7 + 128) & 0x60) != 0x40 )
      {
        v12 = -1073741811;
        *(_DWORD *)(v7 + 4) = -2147482880;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v18) = 2;
          WPP_RECORDER_SF_(
            *(_QWORD *)(v11 + 2536),
            v18,
            3,
            30,
            (__int64)WPP_2fd11ae104fa34a9334eddada324a17a_Traceguids);
        }
LABEL_80:
        result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01015 + 2104))(
                   WdfDriverGlobals,
                   a2,
                   v12);
        if ( a5 != 2228227 )
          goto LABEL_13;
        goto LABEL_81;
      }
      goto LABEL_52;
    case 11:
      v19 = *(_QWORD *)(v7 + 48);
      if ( v19 )
      {
        if ( (*(_BYTE *)(v19 + 10) & 5) != 0 )
          v20 = *(PVOID *)(v19 + 24);
        else
          v20 = MmMapLockedPagesSpecifyCache((PMDL)v19, 0, MmCached, 0, 0, 0x40000010u);
      }
      else
      {
        v20 = *(PVOID *)(v7 + 40);
      }
      if ( !v20 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v21 = 24;
LABEL_77:
          LOBYTE(v18) = 2;
          WPP_RECORDER_SF_(
            *(_QWORD *)(v11 + 2536),
            v18,
            3,
            v21,
            (__int64)WPP_2fd11ae104fa34a9334eddada324a17a_Traceguids);
          goto LABEL_78;
        }
        goto LABEL_78;
      }
      v22 = *(unsigned __int8 *)(v7 + 131);
      if ( v22 == 1 )
      {
        v24 = *(_DWORD *)(v7 + 36);
        if ( v24 > 0x12 )
          v24 = 18;
        memmove(v20, FwUpdateDeviceDescriptor, v24);
        *((_WORD *)v20 + 4) = *(_WORD *)(v11 + 2480);
        *((_WORD *)v20 + 5) = *(_WORD *)(v11 + 2482);
        *((_WORD *)v20 + 6) = *(_WORD *)(v11 + 2484);
        *((_WORD *)v20 + 1) = *(_WORD *)(v11 + 2474);
        *((_BYTE *)v20 + 7) = *(_BYTE *)(v11 + 2479);
      }
      else
      {
        if ( *(_BYTE *)(v7 + 131) != 2 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_78;
          v23 = 26;
          LODWORD(Priority) = *(unsigned __int8 *)(v7 + 131);
LABEL_36:
          LOBYTE(v22) = 2;
          WPP_RECORDER_SF_d(
            *(_QWORD *)(v11 + 2536),
            v22,
            3,
            v23,
            (__int64)WPP_2fd11ae104fa34a9334eddada324a17a_Traceguids,
            Priority);
          goto LABEL_78;
        }
        if ( *(_BYTE *)(v7 + 130) )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_78;
          v23 = 25;
          LODWORD(Priority) = *(unsigned __int8 *)(v7 + 130);
          goto LABEL_36;
        }
        v24 = *(_DWORD *)(v7 + 36);
        if ( v24 > 0x12 )
          v24 = 18;
        memmove(v20, FwUpdateConfigurationDescriptor, v24);
      }
      *(_DWORD *)(v7 + 32) |= 1u;
      if ( (*(_DWORD *)(v7 + 32) & 8) != 0 )
        *(_WORD *)(v7 + 2) = 8;
      *(_DWORD *)(v7 + 36) = v24;
      result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, _QWORD))(WdfFunctions_01015 + 2120))(
                 WdfDriverGlobals,
                 a2,
                 0,
                 v24);
      goto LABEL_81;
  }
  if ( v18 != 19 )
  {
    if ( v18 != 50 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        Priorityb = v18;
        LOBYTE(v18) = 2;
        WPP_RECORDER_SF_d(
          *(_QWORD *)(v11 + 2536),
          v18,
          3,
          32,
          (__int64)WPP_2fd11ae104fa34a9334eddada324a17a_Traceguids,
          Priorityb);
      }
      goto LABEL_78;
    }
    goto LABEL_49;
  }
LABEL_52:
  *(_QWORD *)(v7 + 8) = *(_QWORD *)(v11 + 248);
  v25 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 336))(
          WdfDriverGlobals,
          *(_QWORD *)(v11 + 16));
  result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, __int128 *))(WdfFunctions_01015 + 2024))(
             WdfDriverGlobals,
             a2,
             v25,
             &v36);
  if ( (_BYTE)result )
    return result;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v26 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 2032))(WdfDriverGlobals, a2);
    LOBYTE(v27) = 2;
    WPP_RECORDER_SF_dD(
      *(_QWORD *)(v11 + 2536),
      v27,
      3,
      31,
      (__int64)WPP_2fd11ae104fa34a9334eddada324a17a_Traceguids,
      *(_WORD *)(v7 + 2),
      v26);
  }
  v28 = (*(unsigned int (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 2032))(WdfDriverGlobals, a2);
  result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01015 + 2104))(
             WdfDriverGlobals,
             a2,
             v28);
LABEL_81:
  if ( v7 )
  {
    if ( (byte_14006ED41 & 4) != 0 )
      return McTemplateK0ppqq_EtwWriteTransfer(
               *(unsigned __int16 *)(v7 + 2),
               (unsigned int)USBHUB3_ETW_EVENT_FIRMWARE_UPDATE_URB_COMPLETE,
               (int)v11 + 2292,
               *(_QWORD *)(v11 + 248),
               *(_QWORD *)(v11 + 2672),
               *(_WORD *)(v7 + 2),
               *(_DWORD *)(v7 + 4));
    return result;
  }
LABEL_13:
  if ( (byte_14006ED41 & 4) != 0 )
    return McTemplateK0ppqq_EtwWriteTransfer(
             v17,
             (unsigned int)USBHUB3_ETW_EVENT_FIRMWARE_UPDATE_INTERNAL_IOCTL_COMPLETE,
             (int)v11 + 2292,
             *(_QWORD *)(v11 + 248),
             *(_QWORD *)(v11 + 2672),
             SBYTE8(v34),
             v12);
  return result;
}

```

## disassembly

```asm
0x140040b60  mov     [rsp-38h+arg_10], rbx
0x140040b65  push    rbp
0x140040b66  push    rsi
0x140040b67  push    rdi
0x140040b68  push    r12
0x140040b6a  push    r13
0x140040b6c  push    r14
0x140040b6e  push    r15
0x140040b70  mov     rbp, rsp
0x140040b73  sub     rsp, 80h
0x140040b7a  mov     rax, cs:__security_cookie
0x140040b81  xor     rax, rsp
0x140040b84  mov     [rbp+var_8], rax
0x140040b88  xor     eax, eax
0x140040b8a  xorps   xmm1, xmm1
0x140040b8d  mov     [rbp+var_20], rax
0x140040b91  xorps   xmm0, xmm0
0x140040b94  movups  [rbp+var_40], xmm1
0x140040b98  mov     eax, 28h ; '('
0x140040b9d  mov     r12, rdx
0x140040ba0  mov     word ptr [rbp+var_40], ax
0x140040ba4  mov     r15, rcx
0x140040ba7  mov     rax, cs:WdfFunctions_01015
0x140040bae  mov     rdx, rcx
0x140040bb1  mov     rcx, cs:WdfDriverGlobals
0x140040bb8  xor     ebx, ebx
0x140040bba  movups  [rbp+var_18], xmm0
0x140040bbe  movups  [rbp+var_30], xmm1
0x140040bc2  mov     rax, [rax+4E8h]
0x140040bc9  call    _guard_dispatch_icall
0x140040bce  mov     rcx, cs:WdfFunctions_01015
0x140040bd5  mov     rdx, rax
0x140040bd8  mov     r8, cs:off_14006B248
0x140040bdf  mov     r9, [rcx+650h]
0x140040be6  mov     rcx, cs:WdfDriverGlobals
0x140040bed  mov     rax, r9
0x140040bf0  call    _guard_dispatch_icall
0x140040bf5  mov     r13d, [rbp+arg_20]
0x140040bf9  mov     r14, rax
0x140040bfc  cmp     byte ptr [rax+18h], 1
0x140040c00  mov     rsi, [rax]
0x140040c03  jnz     short loc_140040C41
0x140040c05  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140040c0c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140040c13  jz      short loc_140040C37
0x140040c15  mov     rcx, [rsi+9E8h]
0x140040c1c  lea     rax, WPP_2fd11ae104fa34a9334eddada324a17a_Traceguids
0x140040c23  lea     r9d, [rbx+17h]
0x140040c27  mov     qword ptr [rsp+80h+BugCheckOnFailure], rax
0x140040c2c  lea     r8d, [rbx+3]
0x140040c30  mov     dl, 2
0x140040c32  call    WPP_RECORDER_SF_
0x140040c37  mov     edi, 0C000000Eh
0x140040c3c  jmp     loc_1400412C1
0x140040c41  xor     edi, edi
0x140040c43  mov     qword ptr [rbp+var_18+8], rbx
0x140040c47  mov     eax, r13d
0x140040c4a  mov     dword ptr [rbp+var_18], 10h
0x140040c51  mov     dword ptr [rbp+var_18+4], 8
0x140040c58  sub     eax, 220003h
0x140040c5d  jz      loc_140040DEC
0x140040c63  cmp     eax, 10h
0x140040c66  jz      short loc_140040CA8
0x140040c68  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140040c6f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140040c76  jz      loc_1400412BC
0x140040c7c  mov     rcx, [rsi+9E8h]
0x140040c83  lea     rax, WPP_2fd11ae104fa34a9334eddada324a17a_Traceguids
0x140040c8a  lea     r9d, [rdi+22h]
0x140040c8e  mov     dword ptr [rsp+80h+Priority], r13d
0x140040c93  lea     r8d, [rdi+3]
0x140040c97  mov     qword ptr [rsp+80h+BugCheckOnFailure], rax
0x140040c9c  mov     dl, 2
0x140040c9e  call    WPP_RECORDER_SF_d
0x140040ca3  jmp     loc_1400412BC
0x140040ca8  mov     rax, cs:WdfFunctions_01015
0x140040caf  mov     rdx, [rsi+10h]
0x140040cb3  mov     rcx, cs:WdfDriverGlobals
0x140040cba  mov     rax, [rax+150h]
0x140040cc1  call    _guard_dispatch_icall
0x140040cc6  mov     rcx, cs:WdfFunctions_01015
0x140040ccd  lea     r9, [rbp+var_18]
0x140040cd1  mov     r8, rax
0x140040cd4  mov     rdx, r12
0x140040cd7  mov     r10, [rcx+7E8h]
0x140040cde  mov     rcx, cs:WdfDriverGlobals
0x140040ce5  mov     rax, r10
0x140040ce8  call    _guard_dispatch_icall
0x140040ced  test    al, al
0x140040cef  jnz     loc_140040DC4
0x140040cf5  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140040cfc  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140040d03  jz      short loc_140040D4A
0x140040d05  mov     rax, cs:WdfFunctions_01015
0x140040d0c  mov     rdx, r12
0x140040d0f  mov     rcx, cs:WdfDriverGlobals
0x140040d16  mov     rax, [rax+7F0h]
0x140040d1d  call    _guard_dispatch_icall
0x140040d22  mov     rcx, [rsi+9E8h]
0x140040d29  mov     r9d, 21h ; '!'
0x140040d2f  mov     dword ptr [rsp+80h+Priority], eax
0x140040d33  mov     dl, 2
0x140040d35  lea     rax, WPP_2fd11ae104fa34a9334eddada324a17a_Traceguids
0x140040d3c  mov     qword ptr [rsp+80h+BugCheckOnFailure], rax
0x140040d41  lea     r8d, [r9-1Eh]
0x140040d45  call    WPP_RECORDER_SF_d
0x140040d4a  mov     rax, cs:WdfFunctions_01015
0x140040d51  mov     rdx, r12
0x140040d54  mov     rcx, cs:WdfDriverGlobals
0x140040d5b  mov     rax, [rax+7F0h]
0x140040d62  call    _guard_dispatch_icall
0x140040d67  mov     rcx, cs:WdfFunctions_01015
0x140040d6e  mov     r8d, eax
0x140040d71  mov     rdx, r12
0x140040d74  mov     r9, [rcx+838h]
0x140040d7b  mov     rcx, cs:WdfDriverGlobals
0x140040d82  mov     rax, r9
0x140040d85  call    _guard_dispatch_icall
0x140040d8a  test    cs:byte_14006ED41, 4
0x140040d91  jz      short loc_140040DC4
0x140040d93  mov     eax, dword ptr [rbp+var_30+8]
0x140040d96  lea     rdx, USBHUB3_ETW_EVENT_FIRMWARE_UPDATE_INTERNAL_IOCTL_COMPLETE
0x140040d9d  mov     [rsp+80h+var_50], edi
0x140040da1  mov     dword ptr [rsp+80h+Priority], eax
0x140040da5  mov     rax, [rsi+0A70h]
0x140040dac  lea     r8, [rsi+8F4h]
0x140040db3  mov     r9, [rsi+0F8h]
0x140040dba  mov     qword ptr [rsp+80h+BugCheckOnFailure], rax
0x140040dbf  call    McTemplateK0ppqq_EtwWriteTransfer
0x140040dc4  mov     rcx, [rbp+var_8]
0x140040dc8  xor     rcx, rsp; StackCookie
0x140040dcb  call    __security_check_cookie
0x140040dd0  mov     rbx, [rsp+80h+arg_10]
0x140040dd8  add     rsp, 80h
0x140040ddf  pop     r15
0x140040de1  pop     r14
0x140040de3  pop     r13
0x140040de5  pop     r12
0x140040de7  pop     rdi
0x140040de8  pop     rsi
0x140040de9  pop     rbp
0x140040dea  retn
0x140040dec  mov     rax, cs:WdfFunctions_01015
0x140040df3  lea     r8, [rbp+var_40]
0x140040df7  mov     rcx, cs:WdfDriverGlobals
0x140040dfe  mov     rdx, r12
0x140040e01  mov     rax, [rax+850h]
0x140040e08  call    _guard_dispatch_icall
0x140040e0d  mov     rbx, qword ptr [rbp+var_40+8]
0x140040e11  movzx   edx, word ptr [rbx+2]
0x140040e15  mov     [rbx+4], edi
0x140040e18  mov     ecx, edx
0x140040e1a  test    edx, edx
0x140040e1c  jz      loc_1400411F9
0x140040e22  sub     ecx, 1
0x140040e25  jz      loc_140041185
0x140040e2b  mov     r14d, 3
0x140040e31  sub     ecx, 7
0x140040e34  jz      loc_140041038
0x140040e3a  sub     ecx, r14d
0x140040e3d  jz      short loc_140040E8F
0x140040e3f  sub     ecx, 8
0x140040e42  jz      loc_14004108C
0x140040e48  cmp     ecx, 1Fh
0x140040e4b  jz      loc_140041038
0x140040e51  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140040e58  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140040e5f  jz      loc_1400412B5
0x140040e65  mov     rcx, [rsi+9E8h]
0x140040e6c  lea     rax, WPP_2fd11ae104fa34a9334eddada324a17a_Traceguids
0x140040e73  mov     dword ptr [rsp+80h+Priority], edx
0x140040e77  lea     r9d, [r14+1Dh]
0x140040e7b  mov     dl, 2
0x140040e7d  mov     qword ptr [rsp+80h+BugCheckOnFailure], rax
0x140040e82  mov     r8d, r14d
0x140040e85  call    WPP_RECORDER_SF_d
0x140040e8a  jmp     loc_1400412B5
0x140040e8f  mov     rcx, [rbx+30h]; MemoryDescriptorList
0x140040e93  test    rcx, rcx
0x140040e96  jz      short loc_140040ECA
0x140040e98  test    byte ptr [rcx+0Ah], 5
0x140040e9c  jz      short loc_140040EA4
0x140040e9e  mov     r15, [rcx+18h]
0x140040ea2  jmp     short loc_140040ECE
0x140040ea4  xor     r9d, r9d; RequestedAddress
0x140040ea7  mov     dword ptr [rsp+80h+Priority], 40000010h; Priority
0x140040eaf  xor     edx, edx; AccessMode
0x140040eb1  mov     [rsp+80h+BugCheckOnFailure], edi; BugCheckOnFailure
0x140040eb5  lea     r8d, [r9+1]; CacheType
0x140040eb9  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140040ec0  nop     dword ptr [rax+rax+00h]
0x140040ec5  mov     r15, rax
0x140040ec8  jmp     short loc_140040ECE
0x140040eca  mov     r15, [rbx+28h]
0x140040ece  test    r15, r15
0x140040ed1  jnz     short loc_140040EF3
0x140040ed3  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140040eda  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140040ee1  jz      loc_1400412B5
0x140040ee7  lea     r9d, [r15+18h]
0x140040eeb  mov     r8d, r14d
0x140040eee  jmp     loc_14004129B
0x140040ef3  movzx   edx, byte ptr [rbx+83h]
0x140040efa  mov     ecx, edx
0x140040efc  sub     ecx, 1
0x140040eff  jz      loc_140040F99
0x140040f05  cmp     ecx, 1
0x140040f08  jz      short loc_140040F4A
0x140040f0a  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140040f11  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140040f18  jz      loc_1400412B5
0x140040f1e  mov     r9d, 1Ah
0x140040f24  mov     dword ptr [rsp+80h+Priority], edx
0x140040f28  mov     rcx, [rsi+9E8h]
0x140040f2f  lea     rax, WPP_2fd11ae104fa34a9334eddada324a17a_Traceguids
0x140040f36  mov     r8d, r14d
0x140040f39  mov     qword ptr [rsp+80h+BugCheckOnFailure], rax
0x140040f3e  mov     dl, 2
0x140040f40  call    WPP_RECORDER_SF_d
0x140040f45  jmp     loc_1400412B5
0x140040f4a  movzx   ecx, byte ptr [rbx+82h]
0x140040f51  test    cl, cl
0x140040f53  jz      short loc_140040F75
0x140040f55  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140040f5c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140040f63  jz      loc_1400412B5
0x140040f69  mov     r9d, 19h
0x140040f6f  mov     dword ptr [rsp+80h+Priority], ecx
0x140040f73  jmp     short loc_140040F28
0x140040f75  mov     r14d, [rbx+24h]
0x140040f79  lea     rdx, FwUpdateConfigurationDescriptor; Src
0x140040f80  mov     eax, 12h
0x140040f85  mov     rcx, r15; void *
0x140040f88  cmp     r14d, eax
0x140040f8b  cmova   r14d, eax
0x140040f8f  mov     r8d, r14d; Size
0x140040f92  call    memmove
0x140040f97  jmp     short loc_140040FF5
0x140040f99  mov     r14d, [rbx+24h]
0x140040f9d  lea     rdx, FwUpdateDeviceDescriptor; Src
0x140040fa4  mov     eax, 12h
0x140040fa9  mov     rcx, r15; void *
0x140040fac  cmp     r14d, eax
0x140040faf  cmova   r14d, eax
0x140040fb3  mov     r8d, r14d; Size
0x140040fb6  call    memmove
0x140040fbb  movzx   eax, word ptr [rsi+9B0h]
0x140040fc2  mov     [r15+8], ax
0x140040fc7  movzx   eax, word ptr [rsi+9B2h]
0x140040fce  mov     [r15+0Ah], ax
0x140040fd3  movzx   eax, word ptr [rsi+9B4h]
0x140040fda  mov     [r15+0Ch], ax
0x140040fdf  movzx   eax, word ptr [rsi+9AAh]
0x140040fe6  mov     [r15+2], ax
0x140040feb  mov     al, [rsi+9AFh]
0x140040ff1  mov     [r15+7], al
0x140040ff5  or      dword ptr [rbx+20h], 1
0x140040ff9  mov     r8d, 8
0x140040fff  mov     eax, [rbx+20h]
0x140041002  test    r8b, al
0x140041005  jz      short loc_14004100C
0x140041007  mov     [rbx+2], r8w
0x14004100c  mov     [rbx+24h], r14d
0x140041010  xor     r8d, r8d
0x140041013  mov     rax, cs:WdfFunctions_01015
0x14004101a  mov     rdx, r12
0x14004101d  mov     rcx, cs:WdfDriverGlobals
0x140041024  mov     r9d, r14d
0x140041027  mov     rax, [rax+848h]
0x14004102e  call    _guard_dispatch_icall
0x140041033  jmp     loc_1400412EE
0x140041038  mov     al, [rbx+80h]
0x14004103e  and     al, 60h
0x140041040  cmp     al, 40h ; '@'
0x140041042  jz      short loc_14004108C
0x140041044  mov     edi, 0C000000Dh
0x140041049  mov     dword ptr [rbx+4], 80000300h
0x140041050  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140041057  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004105e  jz      loc_1400412C1
0x140041064  mov     rcx, [rsi+9E8h]
0x14004106b  lea     rax, WPP_2fd11ae104fa34a9334eddada324a17a_Traceguids
0x140041072  mov     r9d, 1Eh
0x140041078  mov     qword ptr [rsp+80h+BugCheckOnFailure], rax
0x14004107d  mov     r8d, r14d
0x140041080  mov     dl, 2
0x140041082  call    WPP_RECORDER_SF_
0x140041087  jmp     loc_1400412C1
0x14004108c  mov     rax, [rsi+0F8h]
0x140041093  mov     [rbx+8], rax
0x140041097  mov     rax, cs:WdfFunctions_01015
0x14004109e  mov     rdx, [rsi+10h]
0x1400410a2  mov     rcx, cs:WdfDriverGlobals
0x1400410a9  mov     rax, [rax+150h]
0x1400410b0  call    _guard_dispatch_icall
0x1400410b5  mov     rcx, cs:WdfFunctions_01015
0x1400410bc  lea     r9, [rbp+var_18]
0x1400410c0  mov     r8, rax
0x1400410c3  mov     rdx, r12
0x1400410c6  mov     r10, [rcx+7E8h]
  ... truncated ...
```
