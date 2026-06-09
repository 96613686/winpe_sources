# HUBUCX_UCXIoctlComplete

- ea: `0x1400286e0`
- end: `0x140028fba`
- name: `HUBUCX_UCXIoctlComplete`
- size: `2266`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x140001f94`
- `0x1400025a4`
- `0x1400067ac`
- `0x14000a53c`
- `0x14000f304`
- `0x14001892c`
- `0x14001d788`
- `0x1400286e0`
- `0x140029714`
- `0x140033530`
- `0x140045570`
- `0x140045640`

## pseudocode

```c
void __fastcall HUBUCX_UCXIoctlComplete(__int64 a1, int a2, __int64 a3, __int64 a4)
{
  int v4; // esi
  int v6; // r15d
  _DWORD *v7; // rbx
  __int64 v8; // r14
  unsigned __int64 v9; // rax
  __int64 v10; // rcx
  int v11; // ecx
  __int64 v12; // rax
  __int64 v13; // r9
  __int64 v14; // rbx
  _QWORD *v15; // r9
  __int64 v16; // rdx
  unsigned int k; // ecx
  _QWORD *v18; // rax
  __int64 v19; // rax
  _QWORD *v20; // r9
  _QWORD *m; // rax
  unsigned int n; // edx
  _QWORD *v23; // rcx
  __int64 v24; // rdx
  unsigned int ii; // r8d
  __int64 v26; // rax
  unsigned int v27; // edx
  unsigned int v28; // eax
  unsigned int v29; // eax
  unsigned int v30; // ebx
  unsigned int v31; // r8d
  __int64 v32; // rdx
  __int64 v33; // rcx
  _QWORD *v34; // r9
  _QWORD *jj; // rax
  unsigned int kk; // edx
  _QWORD *v37; // rcx
  __int64 v38; // rdx
  __int64 v39; // rbp
  __int64 v40; // rbx
  __int64 v41; // rax
  char v42; // al
  int v43; // edx
  __int64 v44; // rax
  int v45; // edx
  int v46; // edx
  __int64 v47; // rcx
  __int64 v48; // rbx
  __int64 v49; // rax
  int v50; // edx
  unsigned __int8 v51; // cf
  __int64 v52; // rax
  _QWORD *v53; // r9
  _QWORD *i; // rax
  unsigned int j; // edx
  _QWORD *v56; // rcx
  __int64 v57; // rdx

  v4 = *(_DWORD *)(a3 + 8);
  v6 = 0;
  if ( v4 < 0 )
  {
    v7 = (_DWORD *)(a4 + 448);
    v8 = a4 + 8;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_Ld(
        *(_QWORD *)(*(_QWORD *)v8 + 1432LL),
        a2,
        5,
        11,
        (__int64)WPP_6f1e94dad5dd3d9188df346061fdcafd_Traceguids,
        *v7,
        v4);
    v9 = (unsigned int)(*v7 - 4788231);
    if ( (unsigned int)v9 > 0x38 || (v10 = 0x100000001000001LL, !_bittest64(&v10, v9)) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        WPP_RECORDER_SF_Ld(
          *(_QWORD *)(*(_QWORD *)v8 + 1432LL),
          *v7,
          5,
          12,
          (__int64)WPP_6f1e94dad5dd3d9188df346061fdcafd_Traceguids,
          *v7,
          v4);
        v7 = (_DWORD *)(a4 + 448);
      }
      v11 = *(_DWORD *)(**(_QWORD **)v8 + 2608LL);
      if ( (v11 & 0x80u) != 0 )
        HUBMISC_VerifierDbgBreak("HubHwVerifierControllerOperationFailure", *(_QWORD *)v8 + 272LL);
      if ( (byte_14006ED42 & 0x10) != 0 )
        McTemplateK0pqq_EtwWriteTransfer(
          v11,
          (unsigned int)USBHUB3_ETW_EVENT_UCX_IOCTL_FAILURE,
          a4 + 1524,
          *(_QWORD *)(a4 + 24),
          *v7,
          v4);
    }
  }
  switch ( *(_DWORD *)(a4 + 448) )
  {
    case 0x491017:
      if ( (*(_DWORD *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD))(WdfFunctions_01015 + 1552))(
                          WdfDriverGlobals,
                          *(_QWORD *)(a4 + 440),
                          0)
                      + 32)
          & 3) != 0 )
      {
        v57 = *(_QWORD *)(a4 + 2424);
        *(_DWORD *)(a4 + 1572) = -2147481856;
        v4 = -1073741823;
        (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01015 + 2552))(
          WdfDriverGlobals,
          v57,
          -10000000);
LABEL_114:
        *(_DWORD *)(a4 + 1568) = v4;
        if ( !*(_DWORD *)(a4 + 1572) )
          *(_DWORD *)(a4 + 1572) = HUBPDO_GetUSBDErrorFromNTStatus((unsigned int)v4);
        v30 = 4020;
LABEL_117:
        if ( v6 )
          return;
        goto LABEL_118;
      }
      if ( v4 < 0 )
      {
        if ( v4 == -1073741823 )
          v4 = -1073741670;
        goto LABEL_114;
      }
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD))(WdfFunctions_01015 + 2560))(
        WdfDriverGlobals,
        *(_QWORD *)(a4 + 2424),
        0);
LABEL_110:
      v30 = 4028;
      goto LABEL_117;
    case 0x49101B:
      v52 = *(_QWORD *)(a4 + 48);
      if ( v52 )
      {
        v53 = (_QWORD *)(v52 + 16);
        for ( i = *(_QWORD **)(v52 + 16); ; i = (_QWORD *)*i )
        {
          v56 = i - 1;
          if ( v53 == i )
            break;
          for ( j = 0; j < *((_DWORD *)v56 + 6); ++j )
          {
            if ( LODWORD(v56[10 * j + 6]) == 5 )
              LODWORD(v56[10 * j + 6]) = 6;
          }
        }
      }
LABEL_105:
      if ( v4 < 0 )
        goto LABEL_114;
      goto LABEL_110;
    case 0x49101F:
      v48 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
              WdfDriverGlobals,
              WdfDriverGlobals->Driver,
              off_14006B2C0);
      if ( v4 < 0 )
      {
        *(_DWORD *)(a4 + 2440) = 1073807361;
        if ( Microsoft_Windows_USB_USBHUB3EnableBits < 0 )
          McTemplateK0pq_EtwWriteTransfer(
            v47,
            USBHUB3_ETW_EVENT_SET_ADDRESS_FAILURE,
            a4 + 1524,
            *(_QWORD *)(a4 + 24),
            v4);
        if ( (*(_DWORD *)(a4 + 1464) & 0x20000) != 0 && (*(_DWORD *)(a4 + 1644) & 0x10000) == 0 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v46) = 2;
            WPP_RECORDER_SF_(
              *(_QWORD *)(*(_QWORD *)(a4 + 8) + 1432LL),
              v46,
              5,
              19,
              (__int64)WPP_6f1e94dad5dd3d9188df346061fdcafd_Traceguids);
          }
          _InterlockedOr((volatile signed __int32 *)(a4 + 1644), 0x10000u);
          _InterlockedIncrement((volatile signed __int32 *)(v48 + 88));
        }
        goto LABEL_114;
      }
      v49 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD))(WdfFunctions_01015 + 1552))(
              WdfDriverGlobals,
              *(_QWORD *)(a4 + 440),
              0);
      v51 = _bittest((const signed __int32 *)(a4 + 1644), 0x10u);
      *(_DWORD *)(a4 + 1656) = *(_DWORD *)(v49 + 28);
      if ( v51 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v50) = 2;
          WPP_RECORDER_SF_(
            *(_QWORD *)(*(_QWORD *)(a4 + 8) + 1432LL),
            v50,
            5,
            18,
            (__int64)WPP_6f1e94dad5dd3d9188df346061fdcafd_Traceguids);
        }
        _InterlockedAnd((volatile signed __int32 *)(a4 + 1644), 0xFFFEFFFF);
        _InterlockedDecrement((volatile signed __int32 *)(v48 + 88));
      }
      goto LABEL_110;
    case 0x491023:
      v44 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD))(WdfFunctions_01015 + 1552))(
              WdfDriverGlobals,
              *(_QWORD *)(a4 + 440),
              0);
      if ( v4 < 0 )
      {
        if ( (*(_DWORD *)(v44 + 56) & 1) != 0 )
        {
          v30 = 4024;
          goto LABEL_118;
        }
        goto LABEL_114;
      }
      *(_WORD *)(a4 + 2216) = *(_WORD *)(a4 + 2218);
      if ( (*(_DWORD *)(v44 + 24) & 0x80u) != 0 )
      {
        if ( *(_BYTE *)(v44 + 67) )
        {
          *(_DWORD *)(a4 + 2732) = *(unsigned __int8 *)(v44 + 67);
        }
        else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v45) = 2;
          WPP_RECORDER_SF_(
            *(_QWORD *)(*(_QWORD *)(a4 + 8) + 1432LL),
            v45,
            5,
            20,
            (__int64)WPP_6f1e94dad5dd3d9188df346061fdcafd_Traceguids);
        }
      }
      goto LABEL_110;
    case 0x49102B:
      if ( (*(_DWORD *)(a4 + 1652) & 0x4000000) != 0 )
      {
        v38 = *(_QWORD *)(a4 + 16);
        if ( v38 )
        {
          if ( *(_DWORD *)(v38 + 4) == 1 )
          {
            v39 = v38 + 456;
            if ( *(_QWORD *)(v38 + 488) && (*(_DWORD *)(v38 + 496) & 2) != 0 )
            {
              *(_BYTE *)(v38 + 536) = 1;
              v40 = *(_QWORD *)(v38 + 544);
              v41 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
                      WdfDriverGlobals,
                      v40,
                      off_14006B1F8);
              *(_QWORD *)v41 = v39;
              *(_QWORD *)(v41 + 16) = a4;
              *(_DWORD *)(v41 + 8) = 1;
              (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 3040))(WdfDriverGlobals, v40);
              v6 = 1;
            }
            else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              v42 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 1632))(WdfDriverGlobals);
              LOBYTE(v43) = 4;
              WPP_RECORDER_SF_q(
                *(_QWORD *)(*(_QWORD *)(a4 + 8) + 1432LL),
                v43,
                2,
                13,
                (__int64)WPP_6f1e94dad5dd3d9188df346061fdcafd_Traceguids,
                v42);
            }
          }
        }
      }
      goto LABEL_105;
  }
  if ( *(_DWORD *)(a4 + 448) != 4788279 )
    goto LABEL_105;
  v12 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD))(WdfFunctions_01015 + 1552))(
          WdfDriverGlobals,
          *(_QWORD *)(a4 + 440),
          0);
  v13 = *(_QWORD *)(a4 + 48);
  v14 = v12;
  if ( v13 )
  {
    v15 = (_QWORD *)(v13 + 16);
    v16 = *v15 - 8LL;
    if ( v15 != (_QWORD *)*v15 )
    {
      do
      {
        for ( k = 0; k < *(_DWORD *)(v16 + 24); ++k )
        {
          if ( *(_DWORD *)(v16 + 80LL * k + 48) == 5 )
            *(_DWORD *)(v16 + 80LL * k + 48) = 6;
        }
        v18 = *(_QWORD **)(v16 + 8);
        v16 = (__int64)(v18 - 1);
      }
      while ( v15 != v18 );
    }
  }
  v19 = *(_QWORD *)(a4 + 56);
  if ( v19 )
  {
    v20 = (_QWORD *)(v19 + 16);
    for ( m = *(_QWORD **)(v19 + 16); ; m = (_QWORD *)*m )
    {
      v23 = m - 1;
      if ( v20 == m )
        break;
      for ( n = 0; n < *((_DWORD *)v23 + 6); ++n )
      {
        if ( LODWORD(v23[10 * n + 6]) == 5 )
          LODWORD(v23[10 * n + 6]) = 6;
      }
    }
  }
  v24 = *(_QWORD *)(a4 + 72);
  if ( v24 )
  {
    for ( ii = 0; ii < *(_DWORD *)(v24 + 24); *(_DWORD *)(v24 + 80 * v26 + 48) = 6 )
      v26 = ii++;
  }
  v27 = *(_DWORD *)(v14 + 76);
  if ( v27 )
  {
    if ( (*(_DWORD *)(v14 + 72) & 4) != 0 )
    {
      v28 = *(unsigned __int16 *)(a4 + 2216);
      if ( v28 <= v27 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v27) = 2;
          WPP_RECORDER_SF_dD(
            *(_QWORD *)(*(_QWORD *)(a4 + 8) + 1432LL),
            v27,
            5,
            15,
            (__int64)WPP_6f1e94dad5dd3d9188df346061fdcafd_Traceguids,
            *(_DWORD *)(v14 + 76),
            v28);
        }
      }
      else
      {
        v29 = v28 - v27;
        *(_DWORD *)(a4 + 2592) = v29;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v27) = 4;
          WPP_RECORDER_SF_dD(
            *(_QWORD *)(*(_QWORD *)(a4 + 8) + 1432LL),
            v27,
            5,
            14,
            (__int64)WPP_6f1e94dad5dd3d9188df346061fdcafd_Traceguids,
            *(_DWORD *)(v14 + 76),
            v29);
        }
      }
      goto LABEL_43;
    }
    if ( v4 < 0 )
    {
LABEL_43:
      *(_DWORD *)(a4 + 2592) = 0;
      goto LABEL_44;
    }
    v31 = v27 + *(unsigned __int16 *)(a4 + 2216);
    *(_DWORD *)(a4 + 2592) = v31;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v27) = 4;
      WPP_RECORDER_SF_dD(
        *(_QWORD *)(*(_QWORD *)(a4 + 8) + 1432LL),
        v27,
        5,
        16,
        (__int64)WPP_6f1e94dad5dd3d9188df346061fdcafd_Traceguids,
        *(_DWORD *)(v14 + 76),
        v31);
    }
  }
LABEL_44:
  if ( (*(_DWORD *)(v14 + 72) & 7) == 0 )
  {
LABEL_51:
    if ( (*(_DWORD *)(a4 + 1644) & 0x8000) != 0 )
    {
      _InterlockedAnd((volatile signed __int32 *)(a4 + 1644), 0xFFFF7FFF);
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v27) = 4;
        WPP_RECORDER_SF_(
          *(_QWORD *)(*(_QWORD *)(a4 + 8) + 1432LL),
          v27,
          5,
          17,
          (__int64)WPP_6f1e94dad5dd3d9188df346061fdcafd_Traceguids);
      }
      v32 = *(_QWORD *)(a4 + 2424);
      *(_DWORD *)(a4 + 1572) = -2147481856;
      v4 = -1073741823;
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01015 + 2552))(
        WdfDriverGlobals,
        v32,
        -10000000);
    }
    else if ( *(_DWORD *)(a4 + 112) && v4 >= 0 )
    {
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD))(WdfFunctions_01015 + 2560))(
        WdfDriverGlobals,
        *(_QWORD *)(a4 + 2424),
        0);
    }
    else if ( v4 == -1073741823 )
    {
      v4 = -1073741670;
    }
    v33 = *(_QWORD *)(a4 + 48);
    if ( v33 )
    {
      v34 = (_QWORD *)(v33 + 16);
      for ( jj = *(_QWORD **)(v33 + 16); ; jj = (_QWORD *)*jj )
      {
        v37 = jj - 1;
        if ( v34 == jj )
          break;
        for ( kk = 0; kk < *((_DWORD *)v37 + 6); ++kk )
        {
          if ( LODWORD(v37[10 * kk + 6]) == 3 )
            LODWORD(v37[10 * kk + 6]) = ((v4 >> 31) & 2) + 4;
        }
      }
    }
    *(_DWORD *)(a4 + 128) = 0;
    *(_DWORD *)(a4 + 112) = 0;
    *(_DWORD *)(a4 + 144) = 0;
    goto LABEL_105;
  }
  *(_DWORD *)(a4 + 1572) = -2147481856;
  if ( !*(_WORD *)(a4 + 2216) )
  {
    v4 = -1073741823;
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64))(WdfFunctions_01015 + 2552))(
      WdfDriverGlobals,
      *(_QWORD *)(a4 + 2424),
      -10000000);
    goto LABEL_51;
  }
  memmove(
    (void *)(*(_QWORD *)(a4 + 136) + 8LL * *(unsigned int *)(a4 + 144)),
    *(const void **)(a4 + 120),
    8LL * *(unsigned int *)(a4 + 128));
  *(_DWORD *)(a4 + 144) += *(_DWORD *)(a4 + 128);
  v30 = 4024;
  *(_DWORD *)(a4 + 128) = 0;
  *(_DWORD *)(a4 + 1568) = HUBPDO_GetUSBDErrorFromNTStatus(3221225473LL);
LABEL_118:
  HUBSM_AddEvent(a4 + 512, v30);
}

```

## disassembly

```asm
0x1400286e0  push    rbx
0x1400286e2  push    rbp
0x1400286e3  push    rsi
0x1400286e4  push    rdi
0x1400286e5  push    r12
0x1400286e7  push    r13
0x1400286e9  push    r14
0x1400286eb  push    r15
0x1400286ed  sub     rsp, 48h
0x1400286f1  mov     esi, [r8+8]
0x1400286f5  lea     r13, WPP_RECORDER_INITIALIZED
0x1400286fc  xor     r12d, r12d
0x1400286ff  lea     r14, WPP_6f1e94dad5dd3d9188df346061fdcafd_Traceguids
0x140028706  mov     rdi, r9
0x140028709  mov     r15d, r12d
0x14002870c  lea     ebp, [r12+5]
0x140028711  test    esi, esi
0x140028713  jns     loc_14002880B
0x140028719  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140028720  lea     rbx, [r9+1C0h]
0x140028727  lea     r14, [r9+8]
0x14002872b  jz      short loc_14002875A
0x14002872d  mov     eax, [rbx]
0x14002872f  lea     r9d, [r12+0Bh]
0x140028734  mov     rcx, [r14]
0x140028737  mov     r8d, ebp
0x14002873a  mov     [rsp+88h+var_58], esi
0x14002873e  mov     dword ptr [rsp+88h+var_60], eax
0x140028742  lea     rax, WPP_6f1e94dad5dd3d9188df346061fdcafd_Traceguids
0x140028749  mov     [rsp+88h+var_68], rax
0x14002874e  mov     rcx, [rcx+598h]
0x140028755  call    WPP_RECORDER_SF_Ld
0x14002875a  mov     edx, [rbx]
0x14002875c  lea     eax, [rdx-491007h]
0x140028762  cmp     eax, 38h ; '8'
0x140028765  ja      short loc_14002877B
0x140028767  mov     rcx, 100000001000001h
0x140028771  bt      rcx, rax
0x140028775  jb      loc_140028804
0x14002877b  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140028782  jz      short loc_1400287B7
0x140028784  mov     rcx, [r14]
0x140028787  lea     rax, WPP_6f1e94dad5dd3d9188df346061fdcafd_Traceguids
0x14002878e  mov     [rsp+88h+var_58], esi
0x140028792  mov     r9d, 0Ch
0x140028798  mov     dword ptr [rsp+88h+var_60], edx
0x14002879c  mov     r8d, ebp
0x14002879f  mov     [rsp+88h+var_68], rax
0x1400287a4  mov     rcx, [rcx+598h]
0x1400287ab  call    WPP_RECORDER_SF_Ld
0x1400287b0  lea     rbx, [rdi+1C0h]
0x1400287b7  mov     rdx, [r14]
0x1400287ba  mov     rax, [rdx]
0x1400287bd  mov     ecx, [rax+0A30h]
0x1400287c3  test    cl, cl
0x1400287c5  jns     short loc_1400287DA
0x1400287c7  add     rdx, 110h
0x1400287ce  lea     rcx, aHubhwverifierc_0; "HubHwVerifierControllerOperationFailure"
0x1400287d5  call    HUBMISC_VerifierDbgBreak
0x1400287da  test    cs:byte_14006ED42, 10h
0x1400287e1  jz      short loc_140028804
0x1400287e3  mov     eax, [rbx]
0x1400287e5  lea     r8, [rdi+5F4h]
0x1400287ec  mov     r9, [rdi+18h]
0x1400287f0  lea     rdx, USBHUB3_ETW_EVENT_UCX_IOCTL_FAILURE
0x1400287f7  mov     dword ptr [rsp+88h+var_60], esi
0x1400287fb  mov     dword ptr [rsp+88h+var_68], eax
0x1400287ff  call    McTemplateK0pqq_EtwWriteTransfer
0x140028804  lea     r14, WPP_6f1e94dad5dd3d9188df346061fdcafd_Traceguids
0x14002880b  mov     ecx, [rdi+1C0h]
0x140028811  sub     ecx, 491017h
0x140028817  jz      loc_140028ED3
0x14002881d  sub     ecx, 4
0x140028820  jz      loc_140028E82
0x140028826  sub     ecx, 4
0x140028829  jz      loc_140028D56
0x14002882f  sub     ecx, 4
0x140028832  jz      loc_140028CBB
0x140028838  sub     ecx, 8
0x14002883b  jz      loc_140028BC6
0x140028841  cmp     ecx, 0Ch
0x140028844  jnz     loc_140028ECA
0x14002884a  mov     rax, cs:WdfFunctions_01015
0x140028851  xor     r8d, r8d
0x140028854  mov     rdx, [rdi+1B8h]
0x14002885b  mov     rcx, cs:WdfDriverGlobals
0x140028862  mov     rax, [rax+610h]
0x140028869  call    _guard_dispatch_icall
0x14002886e  mov     r9, [rdi+30h]
0x140028872  mov     rbx, rax
0x140028875  mov     r10d, 6
0x14002887b  test    r9, r9
0x14002887e  jz      short loc_1400288C2
0x140028880  add     r9, 10h
0x140028884  mov     rcx, [r9]
0x140028887  lea     rdx, [rcx-8]
0x14002888b  cmp     r9, rcx
0x14002888e  jz      short loc_1400288C2
0x140028890  mov     ecx, r12d
0x140028893  cmp     [rdx+18h], r12d
0x140028897  jbe     short loc_1400288B5
0x140028899  mov     eax, ecx
0x14002889b  lea     r8, [rax+rax*4]
0x14002889f  add     r8, r8
0x1400288a2  cmp     [rdx+r8*8+30h], ebp
0x1400288a7  jnz     short loc_1400288AE
0x1400288a9  mov     [rdx+r8*8+30h], r10d
0x1400288ae  inc     ecx
0x1400288b0  cmp     ecx, [rdx+18h]
0x1400288b3  jb      short loc_140028899
0x1400288b5  mov     rax, [rdx+8]
0x1400288b9  lea     rdx, [rax-8]
0x1400288bd  cmp     r9, rax
0x1400288c0  jnz     short loc_140028890
0x1400288c2  mov     rax, [rdi+38h]
0x1400288c6  test    rax, rax
0x1400288c9  jz      short loc_140028906
0x1400288cb  lea     r9, [rax+10h]
0x1400288cf  mov     rax, [r9]
0x1400288d2  jmp     short loc_1400288FD
0x1400288d4  mov     edx, r12d
0x1400288d7  cmp     [rcx+18h], r12d
0x1400288db  jbe     short loc_1400288F9
0x1400288dd  mov     eax, edx
0x1400288df  lea     r8, [rax+rax*4]
0x1400288e3  add     r8, r8
0x1400288e6  cmp     [rcx+r8*8+30h], ebp
0x1400288eb  jnz     short loc_1400288F2
0x1400288ed  mov     [rcx+r8*8+30h], r10d
0x1400288f2  inc     edx
0x1400288f4  cmp     edx, [rcx+18h]
0x1400288f7  jb      short loc_1400288DD
0x1400288f9  mov     rax, [rcx+8]
0x1400288fd  lea     rcx, [rax-8]
0x140028901  cmp     r9, rax
0x140028904  jnz     short loc_1400288D4
0x140028906  mov     rdx, [rdi+48h]
0x14002890a  test    rdx, rdx
0x14002890d  jz      short loc_140028930
0x14002890f  mov     r8d, r12d
0x140028912  cmp     [rdx+18h], r12d
0x140028916  jbe     short loc_140028930
0x140028918  mov     eax, r8d
0x14002891b  inc     r8d
0x14002891e  lea     rcx, [rax+rax*4]
0x140028922  add     rcx, rcx
0x140028925  mov     [rdx+rcx*8+30h], r10d
0x14002892a  cmp     r8d, [rdx+18h]
0x14002892e  jb      short loc_140028918
0x140028930  mov     edx, [rbx+4Ch]
0x140028933  test    edx, edx
0x140028935  jz      short loc_1400289AB
0x140028937  mov     eax, [rbx+48h]
0x14002893a  test    al, 4
0x14002893c  jz      loc_140028A27
0x140028942  movzx   eax, word ptr [rdi+8A8h]
0x140028949  cmp     eax, edx
0x14002894b  jbe     short loc_140028973
0x14002894d  sub     eax, edx
0x14002894f  mov     [rdi+0A20h], eax
0x140028955  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14002895c  jz      short loc_1400289A4
0x14002895e  mov     [rsp+88h+var_58], eax
0x140028962  mov     r9d, 0Eh
0x140028968  mov     eax, [rbx+4Ch]
0x14002896b  mov     dl, 4
0x14002896d  mov     dword ptr [rsp+88h+var_60], eax
0x140028971  jmp     short loc_14002898C
0x140028973  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14002897a  jz      short loc_1400289A4
0x14002897c  mov     [rsp+88h+var_58], eax
0x140028980  mov     r9d, 0Fh
0x140028986  mov     dword ptr [rsp+88h+var_60], edx
0x14002898a  mov     dl, 2
0x14002898c  mov     rcx, [rdi+8]
0x140028990  mov     r8d, ebp
0x140028993  mov     [rsp+88h+var_68], r14
0x140028998  mov     rcx, [rcx+598h]
0x14002899f  call    WPP_RECORDER_SF_dD
0x1400289a4  mov     [rdi+0A20h], r12d
0x1400289ab  mov     eax, [rbx+48h]
0x1400289ae  mov     rbx, 0FFFFFFFFFF676980h
0x1400289b5  test    al, 7
0x1400289b7  jz      loc_140028AA8
0x1400289bd  mov     dword ptr [rdi+624h], 80000700h
0x1400289c7  cmp     [rdi+8A8h], r12w
0x1400289cf  jbe     loc_140028A7F
0x1400289d5  mov     ecx, [rdi+90h]
0x1400289db  mov     rax, [rdi+88h]
0x1400289e2  mov     r8d, [rdi+80h]
0x1400289e9  mov     rdx, [rdi+78h]; Src
0x1400289ed  shl     r8, 3; Size
0x1400289f1  lea     rcx, [rax+rcx*8]; void *
0x1400289f5  call    memmove
0x1400289fa  mov     eax, [rdi+80h]
0x140028a00  mov     ecx, 0C0000001h
0x140028a05  add     [rdi+90h], eax
0x140028a0b  mov     ebx, 0FB8h
0x140028a10  mov     [rdi+80h], r12d
0x140028a17  call    HUBPDO_GetUSBDErrorFromNTStatus
0x140028a1c  mov     [rdi+620h], eax
0x140028a22  jmp     loc_140028F9A
0x140028a27  test    esi, esi
0x140028a29  js      loc_1400289A4
0x140028a2f  movzx   r8d, word ptr [rdi+8A8h]
0x140028a37  add     r8d, edx
0x140028a3a  mov     [rdi+0A20h], r8d
0x140028a41  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140028a48  jz      loc_1400289AB
0x140028a4e  mov     rcx, [rdi+8]
0x140028a52  mov     r9d, 10h
0x140028a58  mov     eax, [rbx+4Ch]
0x140028a5b  mov     dl, 4
0x140028a5d  mov     [rsp+88h+var_58], r8d
0x140028a62  mov     r8d, ebp
0x140028a65  mov     dword ptr [rsp+88h+var_60], eax
0x140028a69  mov     rcx, [rcx+598h]
0x140028a70  mov     [rsp+88h+var_68], r14
0x140028a75  call    WPP_RECORDER_SF_dD
0x140028a7a  jmp     loc_1400289AB
0x140028a7f  mov     rax, cs:WdfFunctions_01015
0x140028a86  mov     r8, rbx
0x140028a89  mov     rdx, [rdi+978h]
0x140028a90  mov     esi, 0C0000001h
0x140028a95  mov     rcx, cs:WdfDriverGlobals
0x140028a9c  mov     rax, [rax+9F8h]
0x140028aa3  call    _guard_dispatch_icall
0x140028aa8  test    dword ptr [rdi+66Ch], 8000h
0x140028ab2  jz      short loc_140028B1D
0x140028ab4  lock and dword ptr [rdi+66Ch], 0FFFF7FFFh
0x140028abf  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140028ac6  jz      short loc_140028AE8
0x140028ac8  mov     rcx, [rdi+8]
0x140028acc  mov     r9d, 11h
0x140028ad2  mov     r8d, ebp
0x140028ad5  mov     [rsp+88h+var_68], r14
0x140028ada  mov     dl, 4
0x140028adc  mov     rcx, [rcx+598h]
0x140028ae3  call    WPP_RECORDER_SF_
0x140028ae8  mov     rdx, [rdi+978h]
0x140028aef  mov     r8, rbx
0x140028af2  mov     dword ptr [rdi+624h], 80000700h
0x140028afc  mov     esi, 0C0000001h
0x140028b01  mov     rax, cs:WdfFunctions_01015
0x140028b08  mov     rcx, cs:WdfDriverGlobals
0x140028b0f  mov     rax, [rax+9F8h]
0x140028b16  call    _guard_dispatch_icall
0x140028b1b  jmp     short loc_140028B5B
0x140028b1d  cmp     [rdi+70h], r12d
0x140028b21  jz      short loc_140028B4D
0x140028b23  test    esi, esi
0x140028b25  js      short loc_140028B4D
0x140028b27  mov     rax, cs:WdfFunctions_01015
0x140028b2e  xor     r8d, r8d
0x140028b31  mov     rdx, [rdi+978h]
0x140028b38  mov     rcx, cs:WdfDriverGlobals
0x140028b3f  mov     rax, [rax+0A00h]
0x140028b46  call    _guard_dispatch_icall
0x140028b4b  jmp     short loc_140028B5B
0x140028b4d  cmp     esi, 0C0000001h
0x140028b53  mov     eax, 0C000009Ah
0x140028b58  cmovz   esi, eax
0x140028b5b  mov     rcx, [rdi+30h]
0x140028b5f  test    rcx, rcx
0x140028b62  jz      short loc_140028BAF
0x140028b64  mov     r10d, esi
0x140028b67  lea     r9, [rcx+10h]
0x140028b6b  mov     rax, [r9]
0x140028b6e  sar     r10d, 1Fh
0x140028b72  and     r10d, 2
0x140028b76  add     r10d, 4
0x140028b7a  jmp     short loc_140028BA6
0x140028b7c  mov     edx, r12d
0x140028b7f  cmp     [rcx+18h], r12d
0x140028b83  jbe     short loc_140028BA2
0x140028b85  mov     eax, edx
0x140028b87  lea     r8, [rax+rax*4]
0x140028b8b  add     r8, r8
0x140028b8e  cmp     dword ptr [rcx+r8*8+30h], 3
0x140028b94  jnz     short loc_140028B9B
0x140028b96  mov     [rcx+r8*8+30h], r10d
0x140028b9b  inc     edx
0x140028b9d  cmp     edx, [rcx+18h]
0x140028ba0  jb      short loc_140028B85
0x140028ba2  mov     rax, [rcx+8]
0x140028ba6  lea     rcx, [rax-8]
0x140028baa  cmp     r9, rax
0x140028bad  jnz     short loc_140028B7C
0x140028baf  mov     [rdi+80h], r12d
0x140028bb6  mov     [rdi+70h], r12d
0x140028bba  mov     [rdi+90h], r12d
0x140028bc1  jmp     loc_140028ECA
0x140028bc6  test    dword ptr [rdi+674h], 4000000h
0x140028bd0  jz      loc_140028ECA
0x140028bd6  mov     rdx, [rdi+10h]
0x140028bda  test    rdx, rdx
0x140028bdd  jz      loc_140028ECA
0x140028be3  cmp     dword ptr [rdx+4], 1
0x140028be7  jnz     loc_140028ECA
0x140028bed  lea     rbp, [rdx+1C8h]
  ... truncated ...
```
