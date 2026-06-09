# DigestResponseBru

- ea: `0x18001d5e8`
- end: `0x18001e20f`
- name: `DigestResponseBru`
- size: `3111`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001c820`

## callees

- `0x1800061a0`
- `0x180006de0`
- `0x1800083a0`
- `0x180008498`
- `0x1800087f4`
- `0x180009770`
- `0x18000f3dc`
- `0x180011fec`
- `0x180012880`
- `0x180013304`
- `0x18001721c`
- `0x1800185b8`
- `0x18001bcec`
- `0x18001bf40`
- `0x18001d5e8`
- `0x180021f88`
- `0x1800221b8`
- `0x180022af8`
- `0x180022bb8`
- `0x180022eb0`
- `0x180022f38`
- `0x180022ffc`
- `0x18002357c`
- `0x180023b8c`
- `0x180038010`

## import_xrefs

- `ntdll!RtlCopySid` at `0x18001de39`
- `ntdll!RtlCopySid` at `0x18001de39`
- `ntdll!RtlLengthRequiredSid` at `0x18001de18`
- `ntdll!RtlLengthRequiredSid` at `0x18001de18`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001de0a`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001deaa`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001de0a`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001deaa`
- `ntdll!RtlSubAuthoritySid` at `0x18001debf`
- `ntdll!RtlSubAuthoritySid` at `0x18001debf`

## pseudocode

```c
__int64 __fastcall DigestResponseBru(unsigned __int16 a1, __int64 a2, _DWORD *a3, _QWORD *a4)
{
  _DWORD *v4; // r14
  _QWORD *v7; // r12
  void *v8; // r15
  int v9; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  int Passwd; // eax
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  PVOID *v16; // rcx
  int v17; // ebx
  int v18; // eax
  PVOID *v19; // rcx
  int v20; // eax
  int v21; // esi
  unsigned __int16 v22; // bx
  unsigned __int16 v23; // r14
  int v24; // eax
  PVOID *v25; // rcx
  int v26; // eax
  PSID v27; // r14
  ULONG v28; // r12d
  ULONG v29; // r13d
  ULONG v30; // r15d
  void *Memory; // rax
  void *v32; // r8
  void *v33; // r14
  PUCHAR v34; // rax
  __int64 v35; // rdx
  unsigned int v36; // r10d
  unsigned int v38; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v39; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v40; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v41[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v42; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD *v43; // [rsp+58h] [rbp-A8h]
  __int64 v44; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v45; // [rsp+68h] [rbp-98h]
  _BYTE v46[4]; // [rsp+70h] [rbp-90h] BYREF
  char v47; // [rsp+74h] [rbp-8Ch]
  int v48; // [rsp+78h] [rbp-88h]
  _BYTE v49[24]; // [rsp+248h] [rbp+148h] BYREF
  _BYTE v50[16]; // [rsp+260h] [rbp+160h] BYREF
  struct _UNICODE_STRING DomainName1; // [rsp+270h] [rbp+170h] BYREF
  _OWORD v52[27]; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v53[72]; // [rsp+430h] [rbp+330h] BYREF
  ULONG v54; // [rsp+478h] [rbp+378h]
  _BYTE v55[32]; // [rsp+480h] [rbp+380h] BYREF
  unsigned int v56; // [rsp+4A0h] [rbp+3A0h]
  int v57; // [rsp+4A4h] [rbp+3A4h]
  unsigned __int16 v58; // [rsp+4ACh] [rbp+3ACh]
  _WORD v59[49]; // [rsp+4AEh] [rbp+3AEh]
  unsigned __int16 v60; // [rsp+510h] [rbp+410h]
  _DWORD v61[6]; // [rsp+530h] [rbp+430h] BYREF
  __int128 v62; // [rsp+548h] [rbp+448h]

  v4 = a3;
  v43 = a3;
  v45 = a4;
  v7 = a4;
  memset_0(v46, 0, 0x410u);
  memset_0(v55, 0, 0xB0u);
  v41[0] = 0;
  v8 = 0;
  v44 = 0;
  v38 = 0;
  v40 = 0;
  v39 = 0;
  v42 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 244, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids);
  memset_0(v55, 0, 0xB0u);
  *v4 = 0;
  *v7 = 0;
  v9 = DigestInit(v46);
  if ( v9 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v11 = 245;
LABEL_8:
      WPP_SF_(v10[2], v11, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids);
      goto LABEL_92;
    }
    goto LABEL_92;
  }
  Passwd = BlobDecodeRequest(a1, a2, v46);
  v9 = Passwd;
  if ( Passwd < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_92;
    v14 = 246;
LABEL_13:
    v15 = (unsigned int)Passwd;
    goto LABEL_91;
  }
  if ( v48 != 3 )
  {
    v9 = -2146893046;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_92;
    v14 = 247;
    v15 = 2148074250LL;
    goto LABEL_91;
  }
  if ( DomainName1.Length && !(unsigned int)DigestCompareDomainNames(&DomainName1, &stru_180045A08) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 248, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids);
    Passwd = DigestForwardRequest((__int64)v46, &v39, &v38, v41);
    v9 = Passwd;
    if ( Passwd < 0 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_92;
      v14 = 249;
      goto LABEL_13;
    }
    v16 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_31;
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      250,
      &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids,
      (unsigned int)Passwd);
    goto LABEL_30;
  }
  Passwd = UserCredentialsExtract(v46, v55);
  v9 = Passwd;
  if ( Passwd < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_92;
    v14 = 251;
    goto LABEL_13;
  }
  v18 = DigestOpenSamUser(v46, &v42, v41, &v38);
  v9 = v18;
  if ( v18 < 0 )
  {
    v19 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_ZD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        252,
        (unsigned int)&WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids,
        (unsigned int)v49,
        v18);
      v19 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v9 != -1073741724 || (v47 & 1) == 0 )
    {
      if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 1) != 0 )
        WPP_SF_ZD(
          (unsigned int)v19[2],
          256,
          (unsigned int)&WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids,
          (unsigned int)v49,
          v9);
      goto LABEL_92;
    }
    if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 2) != 0 )
      WPP_SF_(v19[2], 253, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids);
    v20 = DigestForwardRequest((__int64)v46, &v39, &v38, v41);
    v9 = v20;
    if ( v20 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_ZD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          254,
          (unsigned int)&WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids,
          (unsigned int)v49,
          v20);
      goto LABEL_92;
    }
    v16 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_31;
    WPP_SF_ZD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      255,
      (unsigned int)&WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids,
      (unsigned int)v49,
      v20);
LABEL_30:
    v16 = (PVOID *)WPP_GLOBAL_Control;
LABEL_31:
    v17 = 1;
LABEL_137:
    if ( v39 == 1 && (v47 & 4) != 0 )
    {
      v36 = v38;
      if ( v38 && v41[0] )
      {
        if ( v17 == 1 )
        {
          if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 4) != 0 )
            WPP_SF_(v16[2], 271, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids);
          Passwd = DigestCheckPacForSidFiltering((struct _DIGEST_PARAMETER *)v46);
          v9 = Passwd;
          if ( Passwd < 0 )
          {
            v13 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_92;
            v14 = 272;
            goto LABEL_13;
          }
          v36 = v38;
          v16 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 4) != 0 )
        {
          WPP_SF_d(v16[2], 273, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids, v36);
          v36 = v38;
        }
        Passwd = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64 *, unsigned int *))(*(_QWORD *)&g_LsaFunctions
                                                                                              + 376LL))(
                   v41[0],
                   v36,
                   0,
                   &v44,
                   &v40);
        v9 = Passwd;
        if ( Passwd < 0 )
        {
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_92;
          v14 = 274;
          goto LABEL_13;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 275, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids, v40);
        if ( v41[0] )
          (*(void (**)(void))(*(_QWORD *)&g_LsaFunctions + 48LL))();
        v36 = v40;
        v41[0] = v44;
        v38 = v40;
        v40 = 0;
        v44 = 0;
      }
    }
    else
    {
      v36 = v38;
    }
    Passwd = DigestEncodeResponse(v39, v46, v36, v41[0], v4, v7);
    v9 = Passwd;
    if ( Passwd >= 0 )
      goto LABEL_92;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_92;
    v14 = 276;
    goto LABEL_13;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 257, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids, v38);
  Passwd = DigestGetPasswd(v42, v46, v55);
  v9 = Passwd;
  if ( Passwd < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_92;
    v14 = 258;
    goto LABEL_13;
  }
  v16 = (PVOID *)WPP_GLOBAL_Control;
  v21 = -1073741715;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 259, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids, v56);
      v16 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 4) != 0 )
    {
      WPP_SF_d(v16[2], 260, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids, v59[41]);
      v16 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  v22 = 1;
  v39 = 0;
  if ( v57 == 1 )
  {
    v23 = 29;
    if ( v60 <= 0x1Du )
      v23 = v60;
    while ( 1 )
    {
      while ( 1 )
      {
        if ( v39 )
          goto LABEL_114;
        if ( v22 > v23 )
        {
          v57 = 0;
          goto LABEL_104;
        }
        if ( v59[v22] )
          break;
LABEL_87:
        ++v22;
      }
      if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 4) != 0 )
        WPP_SF_d(v16[2], 261, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids, v22);
      v58 = v22;
      StringFree(v53);
      v21 = DigestCalculation(v46, v55);
      if ( v21 < 0 )
      {
        if ( v21 != -1073741718 && v21 != -2146893042 )
        {
          v9 = v21;
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v14 = 264;
            v15 = (unsigned int)v21;
            goto LABEL_91;
          }
          goto LABEL_92;
        }
        v16 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 263, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids, v22);
          v16 = (PVOID *)WPP_GLOBAL_Control;
        }
        goto LABEL_87;
      }
      v16 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 262, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids, v22);
        v16 = (PVOID *)WPP_GLOBAL_Control;
      }
      v39 = 1;
    }
  }
LABEL_104:
  if ( v56 == 1 )
  {
    StringFree(v53);
    v26 = DigestCalculation(v46, v55);
    v21 = v26;
    if ( v26 >= 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 265, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids);
      v39 = 1;
      v17 = 0;
      goto LABEL_116;
    }
    if ( v26 != -1073741718 )
    {
      v9 = v26;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_92;
      v14 = 267;
      v15 = (unsigned int)v26;
LABEL_91:
      WPP_SF_d(v13[2], v14, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids, v15);
      goto LABEL_92;
    }
    v16 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 266, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids);
      v16 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
LABEL_114:
  v17 = 0;
  if ( v39 != 1 && v21 != -1073741718 )
    goto LABEL_136;
LABEL_116:
  memset_0(v61, 0, 0xC0u);
  v27 = hMem;
  v28 = v54;
  v29 = *RtlSubAuthorityCountSid(hMem);
  v30 = RtlLengthRequiredSid(v29 + 1);
  Memory = (void *)DigestAllocateMemory(v30);
  if ( Memory )
  {
    v32 = v27;
    v33 = Memory;
    if ( RtlCopySid(v30, Memory, v32) < 0 )
    {
      DigestFreeMemory(v33);
      goto LABEL_119;
    }
    v34 = RtlSubAuthorityCountSid(v33);
    ++*v34;
    *RtlSubAuthoritySid(v33, v29) = v28;
    if ( v39 == 1 )
    {
      v61[0] = 0x40000000;
      DigestUpdateLogonStatistics(v42, v61);
      DigestAuditAccountLogon(0, v50, v52, v33);
      v16 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_130;
      v35 = 269;
    }
    else
    {
      if ( v21 != -1073741718 )
      {
        v16 = (PVOID *)WPP_GLOBAL_Control;
        v8 = v33;
        v7 = v45;
        goto LABEL_136;
      }
      v62 = v52[0];
      v61[0] = 402653184;
      DigestUpdateLogonStatistics(v42, v61);
      DigestAuditAccountLogon(3221225578LL, v50, v52, v33);
      v16 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
LABEL_130:
        v7 = v45;
        v8 = v33;
LABEL_136:
        v4 = v43;
        goto LABEL_137;
      }
      v35 = 270;
    }
    WPP_SF_(v16[2], v35, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids);
    v16 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_130;
  }
LABEL_119:
  v9 = -1073741801;
  v8 = 0;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v11 = 268;
    goto LABEL_8;
  }
LABEL_92:
  DigestFree(v46);
  UserCredentialsFree(v55);
  if ( v41[0] )
  {
    (*(void (**)(void))(*(_QWORD *)&g_LsaFunctions + 48LL))();
    v41[0] = 0;
    v38 = 0;
  }
  if ( v44 )
  {
    (*(void (**)(void))(*(_QWORD *)&g_LsaFunctions + 48LL))();
    v44 = 0;
    v40 = 0;
  }
  if ( v42 )
  {
    v24 = DigestCloseSamUser();
    if ( v24 < 0 )
    {
      v25 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_102;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        277,
        &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids,
        (unsigned int)v24);
    }
    v25 = (PVOID *)WPP_GLOBAL_Control;
LABEL_102:
    v42 = 0;
    goto LABEL_169;
  }
  v25 = (PVOID *)WPP_GLOBAL_Control;
LABEL_169:
  if ( v8 )
  {
    DigestFreeMemory(v8);
    v25 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v25 != &WPP_GLOBAL_Control && *((char *)v25 + 28) < 0 )
    WPP_SF_d(v25[2], 278, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids, (unsigned int)v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001d5e8  push    rbp
0x18001d5ea  push    rbx
0x18001d5eb  push    rsi
0x18001d5ec  push    rdi
0x18001d5ed  push    r12
0x18001d5ef  push    r13
0x18001d5f1  push    r14
0x18001d5f3  push    r15
0x18001d5f5  lea     rbp, [rsp-508h]
0x18001d5fd  sub     rsp, 608h
0x18001d604  mov     rax, cs:__security_cookie
0x18001d60b  xor     rax, rsp
0x18001d60e  mov     [rbp+540h+var_50], rax
0x18001d615  mov     r14, r8
0x18001d618  mov     [rsp+640h+var_5E8], r8
0x18001d61d  mov     rsi, rdx
0x18001d620  mov     [rsp+640h+var_5D8], r9
0x18001d625  movzx   edi, cx
0x18001d628  xor     edx, edx; Val
0x18001d62a  mov     r8d, 410h; Size
0x18001d630  lea     rcx, [rsp+640h+var_5D0]; void *
0x18001d635  mov     r12, r9
0x18001d638  call    memset_0
0x18001d63d  mov     ebx, 0B0h
0x18001d642  lea     rcx, [rbp+540h+var_1C0]; void *
0x18001d649  mov     r8d, ebx; Size
0x18001d64c  xor     edx, edx; Val
0x18001d64e  call    memset_0
0x18001d653  xor     r13d, r13d
0x18001d656  mov     [rsp+640h+var_600], r13
0x18001d65b  mov     r15d, r13d
0x18001d65e  mov     [rsp+640h+var_5E0], r13
0x18001d663  mov     [rsp+640h+var_610], r13d
0x18001d668  mov     [rsp+640h+var_608], r13d
0x18001d66d  mov     [rsp+640h+var_60C], r13d
0x18001d672  mov     [rsp+640h+var_5F0], r13
0x18001d677  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d67e  lea     rax, WPP_GLOBAL_Control
0x18001d685  cmp     rcx, rax
0x18001d688  jz      short loc_18001D6A3
0x18001d68a  test    byte ptr [rcx+1Ch], 80h
0x18001d68e  jz      short loc_18001D6A3
0x18001d690  mov     rcx, [rcx+10h]
0x18001d694  lea     edx, [rbx+44h]
0x18001d697  lea     r8, WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids
0x18001d69e  call    WPP_SF_
0x18001d6a3  mov     r8, rbx; Size
0x18001d6a6  lea     rcx, [rbp+540h+var_1C0]; void *
0x18001d6ad  xor     edx, edx; Val
0x18001d6af  call    memset_0
0x18001d6b4  mov     [r14], r13d
0x18001d6b7  lea     rcx, [rsp+640h+var_5D0]
0x18001d6bc  mov     [r12], r13
0x18001d6c0  call    DigestInit
0x18001d6c5  mov     ebx, eax
0x18001d6c7  test    eax, eax
0x18001d6c9  jns     short loc_18001D706
0x18001d6cb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d6d2  lea     rsi, WPP_GLOBAL_Control
0x18001d6d9  cmp     rcx, rsi
0x18001d6dc  jz      loc_18001DC74
0x18001d6e2  test    byte ptr [rcx+1Ch], 1
0x18001d6e6  jz      loc_18001DC74
0x18001d6ec  mov     edx, 0F5h
0x18001d6f1  mov     rcx, [rcx+10h]
0x18001d6f5  lea     r8, WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids
0x18001d6fc  call    WPP_SF_
0x18001d701  jmp     loc_18001DC74
0x18001d706  lea     r8, [rsp+640h+var_5D0]
0x18001d70b  mov     rdx, rsi
0x18001d70e  movzx   ecx, di
0x18001d711  call    BlobDecodeRequest
0x18001d716  mov     ebx, eax
0x18001d718  test    eax, eax
0x18001d71a  jns     short loc_18001D75A
0x18001d71c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d723  lea     rsi, WPP_GLOBAL_Control
0x18001d72a  cmp     rcx, rsi
0x18001d72d  jz      loc_18001DC74
0x18001d733  test    byte ptr [rcx+1Ch], 1
0x18001d737  jz      loc_18001DC74
0x18001d73d  mov     edx, 0F6h
0x18001d742  mov     r9d, eax
0x18001d745  mov     rcx, [rcx+10h]
0x18001d749  lea     r8, WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids
0x18001d750  call    WPP_SF_d
0x18001d755  jmp     loc_18001DC74
0x18001d75a  cmp     [rsp+640h+var_5C8], 3
0x18001d75f  jz      short loc_18001D794
0x18001d761  mov     ebx, 8009030Ah
0x18001d766  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d76d  lea     rsi, WPP_GLOBAL_Control
0x18001d774  cmp     rcx, rsi
0x18001d777  jz      loc_18001DC74
0x18001d77d  test    byte ptr [rcx+1Ch], 1
0x18001d781  jz      loc_18001DC74
0x18001d787  mov     edx, 0F7h
0x18001d78c  mov     r9d, 8009030Ah
0x18001d792  jmp     short loc_18001D745
0x18001d794  cmp     [rbp+540h+DomainName1.Length], r13w
0x18001d79c  jz      loc_18001D873
0x18001d7a2  lea     r8, word_1800459F8
0x18001d7a9  lea     rdx, stru_180045A08; struct _UNICODE_STRING *
0x18001d7b0  lea     rcx, [rbp+540h+DomainName1]; DomainName1
0x18001d7b7  call    DigestCompareDomainNames
0x18001d7bc  test    eax, eax
0x18001d7be  jnz     loc_18001D873
0x18001d7c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d7cb  lea     rsi, WPP_GLOBAL_Control
0x18001d7d2  cmp     rcx, rsi
0x18001d7d5  jz      short loc_18001D7F2
0x18001d7d7  test    byte ptr [rcx+1Ch], 2
0x18001d7db  jz      short loc_18001D7F2
0x18001d7dd  mov     rcx, [rcx+10h]
0x18001d7e1  lea     r8, WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids
0x18001d7e8  mov     edx, 0F8h
0x18001d7ed  call    WPP_SF_
0x18001d7f2  lea     r9, [rsp+640h+var_600]
0x18001d7f7  lea     r8, [rsp+640h+var_610]
0x18001d7fc  lea     rdx, [rsp+640h+var_60C]
0x18001d801  lea     rcx, [rsp+640h+var_5D0]
0x18001d806  call    DigestForwardRequest
0x18001d80b  mov     ebx, eax
0x18001d80d  test    eax, eax
0x18001d80f  jns     short loc_18001D835
0x18001d811  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d818  cmp     rcx, rsi
0x18001d81b  jz      loc_18001DC74
0x18001d821  test    byte ptr [rcx+1Ch], 1
0x18001d825  jz      loc_18001DC74
0x18001d82b  mov     edx, 0F9h
0x18001d830  jmp     loc_18001D742
0x18001d835  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d83c  mov     dil, 4
0x18001d83f  cmp     rcx, rsi
0x18001d842  jz      short loc_18001D869
0x18001d844  test    [rcx+1Ch], dil
0x18001d848  jz      short loc_18001D869
0x18001d84a  mov     rcx, [rcx+10h]
0x18001d84e  lea     r8, WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids
0x18001d855  mov     edx, 0FAh
0x18001d85a  mov     r9d, eax
0x18001d85d  call    WPP_SF_d
0x18001d862  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d869  mov     ebx, 1
0x18001d86e  jmp     loc_18001DFD6
0x18001d873  lea     rdx, [rbp+540h+var_1C0]
0x18001d87a  lea     rcx, [rsp+640h+var_5D0]
0x18001d87f  call    UserCredentialsExtract
0x18001d884  mov     ebx, eax
0x18001d886  test    eax, eax
0x18001d888  jns     short loc_18001D8B5
0x18001d88a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d891  lea     rsi, WPP_GLOBAL_Control
0x18001d898  cmp     rcx, rsi
0x18001d89b  jz      loc_18001DC74
0x18001d8a1  test    byte ptr [rcx+1Ch], 1
0x18001d8a5  jz      loc_18001DC74
0x18001d8ab  mov     edx, 0FBh
0x18001d8b0  jmp     loc_18001D742
0x18001d8b5  lea     r9, [rsp+640h+var_610]
0x18001d8ba  lea     r8, [rsp+640h+var_600]
0x18001d8bf  lea     rdx, [rsp+640h+var_5F0]
0x18001d8c4  lea     rcx, [rsp+640h+var_5D0]
0x18001d8c9  call    DigestOpenSamUser
0x18001d8ce  mov     ebx, eax
0x18001d8d0  test    eax, eax
0x18001d8d2  jns     loc_18001DA0D
0x18001d8d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d8df  lea     rsi, WPP_GLOBAL_Control
0x18001d8e6  cmp     rcx, rsi
0x18001d8e9  jz      short loc_18001D918
0x18001d8eb  test    byte ptr [rcx+1Ch], 2
0x18001d8ef  jz      short loc_18001D918
0x18001d8f1  mov     rcx, [rcx+10h]
0x18001d8f5  lea     r9, [rbp+540h+var_3F8]
0x18001d8fc  mov     edx, 0FCh
0x18001d901  mov     dword ptr [rsp+640h+var_620], eax
0x18001d905  lea     r8, WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids
0x18001d90c  call    WPP_SF_ZD
0x18001d911  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d918  cmp     ebx, 0C0000064h
0x18001d91e  jnz     loc_18001D9EF
0x18001d924  test    [rsp+640h+var_5CC], 1
0x18001d929  jz      loc_18001D9EF
0x18001d92f  cmp     rcx, rsi
0x18001d932  jz      short loc_18001D94F
0x18001d934  test    byte ptr [rcx+1Ch], 2
0x18001d938  jz      short loc_18001D94F
0x18001d93a  mov     rcx, [rcx+10h]
0x18001d93e  lea     r8, WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids
0x18001d945  mov     edx, 0FDh
0x18001d94a  call    WPP_SF_
0x18001d94f  lea     r9, [rsp+640h+var_600]
0x18001d954  lea     r8, [rsp+640h+var_610]
0x18001d959  lea     rdx, [rsp+640h+var_60C]
0x18001d95e  lea     rcx, [rsp+640h+var_5D0]
0x18001d963  call    DigestForwardRequest
0x18001d968  mov     ebx, eax
0x18001d96a  test    eax, eax
0x18001d96c  jns     short loc_18001D9AD
0x18001d96e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d975  cmp     rcx, rsi
0x18001d978  jz      loc_18001DC74
0x18001d97e  test    byte ptr [rcx+1Ch], 1
0x18001d982  jz      loc_18001DC74
0x18001d988  mov     edx, 0FEh
0x18001d98d  mov     dword ptr [rsp+640h+var_620], eax
0x18001d991  mov     rcx, [rcx+10h]
0x18001d995  lea     r9, [rbp+540h+var_3F8]
0x18001d99c  lea     r8, WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids
0x18001d9a3  call    WPP_SF_ZD
0x18001d9a8  jmp     loc_18001DC74
0x18001d9ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d9b4  mov     dil, 4
0x18001d9b7  cmp     rcx, rsi
0x18001d9ba  jz      loc_18001D869
0x18001d9c0  test    [rcx+1Ch], dil
0x18001d9c4  jz      loc_18001D869
0x18001d9ca  mov     rcx, [rcx+10h]
0x18001d9ce  lea     r9, [rbp+540h+var_3F8]
0x18001d9d5  mov     edx, 0FFh
0x18001d9da  mov     dword ptr [rsp+640h+var_620], eax
0x18001d9de  lea     r8, WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids
0x18001d9e5  call    WPP_SF_ZD
0x18001d9ea  jmp     loc_18001D862
0x18001d9ef  cmp     rcx, rsi
0x18001d9f2  jz      loc_18001DC74
0x18001d9f8  test    byte ptr [rcx+1Ch], 1
0x18001d9fc  jz      loc_18001DC74
0x18001da02  mov     edx, 100h
0x18001da07  mov     dword ptr [rsp+640h+var_620], ebx
0x18001da0b  jmp     short loc_18001D991
0x18001da0d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001da14  lea     rsi, WPP_GLOBAL_Control
0x18001da1b  mov     dil, 4
0x18001da1e  cmp     rcx, rsi
0x18001da21  jz      short loc_18001DA43
0x18001da23  test    [rcx+1Ch], dil
0x18001da27  jz      short loc_18001DA43
0x18001da29  mov     r9d, [rsp+640h+var_610]
0x18001da2e  lea     r8, WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids
0x18001da35  mov     rcx, [rcx+10h]
0x18001da39  mov     edx, 101h
0x18001da3e  call    WPP_SF_d
0x18001da43  mov     rcx, [rsp+640h+var_5F0]
0x18001da48  lea     r8, [rbp+540h+var_1C0]
0x18001da4f  lea     rdx, [rsp+640h+var_5D0]
0x18001da54  call    DigestGetPasswd
0x18001da59  mov     ebx, eax
0x18001da5b  test    eax, eax
0x18001da5d  jns     short loc_18001DA83
0x18001da5f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001da66  cmp     rcx, rsi
0x18001da69  jz      loc_18001DC74
0x18001da6f  test    byte ptr [rcx+1Ch], 1
0x18001da73  jz      loc_18001DC74
0x18001da79  mov     edx, 102h
0x18001da7e  jmp     loc_18001D742
0x18001da83  mov     rcx, cs:WPP_GLOBAL_Control
0x18001da8a  lea     r14, WPP_GLOBAL_Control
0x18001da91  mov     esi, 0C000006Dh
0x18001da96  cmp     rcx, r14
0x18001da99  jz      short loc_18001DAF3
0x18001da9b  test    [rcx+1Ch], dil
0x18001da9f  jz      short loc_18001DAC4
0x18001daa1  mov     r9d, [rbp+540h+var_1A0]
0x18001daa8  lea     r8, WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids
0x18001daaf  mov     rcx, [rcx+10h]
0x18001dab3  mov     edx, 103h
0x18001dab8  call    WPP_SF_d
0x18001dabd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dac4  cmp     rcx, r14
0x18001dac7  jz      short loc_18001DAF3
0x18001dac9  test    [rcx+1Ch], dil
0x18001dacd  jz      short loc_18001DAF3
0x18001dacf  movzx   r9d, [rbp+540h+var_140]
0x18001dad7  lea     r8, WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids
0x18001dade  mov     rcx, [rcx+10h]
0x18001dae2  mov     edx, 104h
0x18001dae7  call    WPP_SF_d
0x18001daec  mov     rcx, cs:WPP_GLOBAL_Control
0x18001daf3  mov     ebx, 1
0x18001daf8  mov     [rsp+640h+var_60C], r13d
0x18001dafd  cmp     [rbp+540h+var_19C], ebx
0x18001db03  jnz     loc_18001DD37
0x18001db09  lea     r14d, [rbx+1Ch]
0x18001db0d  cmp     r14w, [rbp+540h+var_130]
0x18001db15  jb      short loc_18001DB1F
0x18001db17  movzx   r14d, [rbp+540h+var_130]
0x18001db1f  mov     edx, ebx
0x18001db21  cmp     [rsp+640h+var_60C], r13d
0x18001db26  jnz     loc_18001DDCF
0x18001db2c  cmp     bx, r14w
0x18001db30  ja      loc_18001DD24
0x18001db36  movzx   eax, bx
0x18001db39  cmp     [rbp+rax*2+540h+var_192], r13w
0x18001db42  jz      loc_18001DC32
0x18001db48  lea     rax, WPP_GLOBAL_Control
0x18001db4f  cmp     rcx, rax
  ... truncated ...
```
