# LdapInitialDecodeMessage(ldap_connection *,ldapmsg *)

- ea: `0x180003840`
- end: `0x180004614`
- name: `?LdapInitialDecodeMessage@@YAKPEAUldap_connection@@PEAUldapmsg@@@Z`
- size: `3540`
- prototype: `unsigned int __fastcall(struct ldap_connection *, struct ldapmsg *)`
- caller_count: `5`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800018d0`
- `0x18000a358`
- `0x180045448`
- `0x180046038`
- `0x18004bd50`

## callees

- `0x1800014e0`
- `0x1800016b8`
- `0x180001790`
- `0x1800030f0`
- `0x180003570`
- `0x1800037a8`
- `0x180003840`
- `0x180006510`
- `0x18000da50`
- `0x18001ce90`
- `0x180027530`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000403d`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000403d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180003cfe`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180003cfe`

## string_xrefs

- `0x18000422d`: `ldapMsgFromBuff 1 connection 0x%x received protocol error 0x%x .\n`
- `0x180003cf2`: `ldapMsgFromBuff 2 connection 0x%x received protocol error 0x%x .\n`
- `0x180003ea7`: `ldapMsgFromBuff 11 connection 0x%x received protocol error 0x%x .\n`
- `0x1800042e9`: `ldapMsgFromBuff 3 connection 0x%x received protocol error 0x%x .\n`
- `0x1800043ed`: `ldapMsgFromBuff 5 connection 0x%x received protocol error 0x%x .\n`
- `0x180003db1`: `ldapMsgFromBuff 6 connection 0x%x received protocol error 0x%x .\n`
- `0x180003bd2`: `ldapMsgFromBuff 7 connection 0x%x received protocol error 0x%x .\n`
- `0x180004533`: `ldapMsgFromBuff 8 connection 0x%x received protocol error 0x%x .\n`
- `0x180004444`: `ldapMsgFromBuff 10 connection 0x%x received protocol error tag=0x%x .\n`
- `0x1800040e7`: `HrStartReadSequence ran out of data, length 0x%x, offset 0x%x.\n`
- `0x180004155`: `HrStartReadSequence ran out of data, length 0x%x, offset 0x%x.\n`
- `0x180004117`: `HrStartReadSequence expected tag of 0x%x, received 0x%x.\n`
- `0x180004189`: `HrStartReadSequence expected tag of 0x%x, received 0x%x.\n`
- `0x180004198`: `HrStartReadSequence 2 ran out of data, length 0x%x, offset 0x%x.\n`
- `0x18000433f`: `HrStartReadSequence 2 ran out of data, length 0x%x, offset 0x%x.\n`

## pseudocode

```c
unsigned int __fastcall LdapInitialDecodeMessage(struct ldap_connection *a1, struct ldapmsg *a2)
{
  unsigned int *lm_ber; // rbx
  unsigned int v3; // edi
  __int64 v6; // r8
  unsigned int v7; // edx
  __int64 v8; // rcx
  __int64 v9; // r9
  __int64 v10; // r8
  char v11; // cl
  ULONG v12; // r15d
  int v13; // r9d
  __int64 v14; // rax
  unsigned int v15; // edx
  unsigned int v16; // ecx
  unsigned int Length; // r14d
  __int64 v18; // rbp
  unsigned int v19; // r8d
  int v20; // r9d
  unsigned int v21; // ecx
  unsigned int v22; // r14d
  unsigned int v23; // eax
  __int64 v24; // r8
  unsigned int v25; // ecx
  __int64 v26; // r9
  __int64 v27; // r8
  char v28; // r9
  int v29; // r9d
  __int64 v30; // rax
  unsigned int v31; // ecx
  unsigned int v32; // edx
  unsigned int v33; // edx
  __int64 v34; // rcx
  unsigned int v35; // r8d
  __int64 lm_msgtype; // r9
  __int64 v37; // rdx
  unsigned int v38; // r8d
  int v39; // r9d
  int v40; // r9d
  unsigned int v41; // ecx
  unsigned int v42; // r8d
  unsigned int v43; // r10d
  int v44; // edx
  char *v45; // rcx
  BOOL v46; // r11d
  int v47; // eax
  unsigned int result; // eax
  DWORD v49; // ecx
  ULONG v50; // ecx
  PCHAR v51; // rax
  _DWORD *Value; // rbx
  unsigned int Sequence; // eax
  const char *v54; // rdx
  unsigned int v55; // r10d
  unsigned int v56; // ecx
  int v57; // edx
  char *v58; // r8
  BOOL v59; // r9d
  int v60; // eax
  unsigned int v61; // r12d
  _DWORD *v62; // rax
  unsigned int v63; // r14d
  unsigned int v64; // [rsp+78h] [rbp+10h] BYREF
  unsigned int v65; // [rsp+80h] [rbp+18h] BYREF
  unsigned int v66; // [rsp+88h] [rbp+20h] BYREF

  lm_ber = (unsigned int *)a2->lm_ber;
  v3 = 0;
  v64 = 0;
  if ( !lm_ber )
    return 82;
  v6 = lm_ber[1];
  v7 = *lm_ber;
  if ( *lm_ber <= (unsigned int)v6 )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000) != 0 )
      LDAPClientPrint(0x2000, "HrStartReadSequence ran out of data, length 0x%x, offset 0x%x.\n", v7, v6);
    Length = 16;
    goto LABEL_120;
  }
  v8 = *((_QWORD *)lm_ber + 2);
  v9 = *(unsigned __int8 *)(v6 + v8);
  if ( (_BYTE)v9 != 48 )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000) != 0 )
      LDAPClientPrint(0x2000, "HrStartReadSequence expected tag of 0x%x, received 0x%x.\n", 48, v9);
    goto LABEL_57;
  }
  v10 = (unsigned int)(v6 + 1);
  lm_ber[1] = v10;
  if ( v7 <= (unsigned int)v10 )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000) != 0 )
      LDAPClientPrint(
        0x2000,
        "HrStartReadSequence 2 ran out of data, length 0x%x, offset 0x%x.\n",
        v7,
        (unsigned int)v10);
    goto LABEL_57;
  }
  v11 = *(_BYTE *)(v10 + v8);
  v12 = 1;
  v13 = 1;
  if ( v11 < 0 )
    v13 = (v11 & 0x7F) + 1;
  v14 = lm_ber[8];
  if ( (unsigned int)v14 >= 0x32 )
  {
    Length = -2147024882;
  }
  else
  {
    v15 = lm_ber[209];
    v16 = lm_ber[210];
    lm_ber[4 * v14 + 9] = v10;
    lm_ber[4 * lm_ber[8] + 10] = v13;
    lm_ber[4 * lm_ber[8] + 11] = v16;
    lm_ber[4 * lm_ber[8]++ + 12] = v15;
    Length = CLdapBer::HrGetLength((CLdapBer *)lm_ber, lm_ber + 209);
    if ( Length )
      CLdapBer::HrPopSeqStack((CLdapBer *)lm_ber, &v66, &v65, lm_ber + 210, lm_ber + 209);
    else
      lm_ber[210] = lm_ber[1];
  }
  v18 = lm_ber[1];
  v19 = *lm_ber;
  if ( (unsigned int)v18 > *lm_ber )
  {
LABEL_57:
    Length = -2147024809;
    goto LABEL_120;
  }
  if ( Length )
  {
LABEL_120:
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
      LDAPClientPrint(0x400000, "ldapMsgFromBuff 1 connection 0x%x received protocol error 0x%x .\n", a1, Length);
    goto LABEL_121;
  }
  v65 = 0;
  if ( v19 <= (unsigned int)v18 )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000) != 0 )
      LDAPClientPrint(0x2000, "HrGetValue ran out of data, length 0x%x, offset 0x%x.\n", v19, v18);
    v63 = 16;
    goto LABEL_75;
  }
  v20 = *(unsigned __int8 *)(v18 + *((_QWORD *)lm_ber + 2));
  if ( v20 != 2 )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000) != 0 )
      LDAPClientPrint(0x2000, "HrGetValue expected tag of 0x%x, received 0x%x.\n", 2, v20);
    v63 = -2147024809;
    goto LABEL_75;
  }
  lm_ber[1] = v18 + 1;
  if ( v19 <= (int)v18 + 1 )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000) != 0 )
      LDAPClientPrint(0x2000, "HrGetValue ran out of data, length 0x%x, offset 0x%x.\n", v19, v18 + 1);
    lm_ber[1] = v18;
    v63 = 16;
    goto LABEL_75;
  }
  v21 = CLdapBer::HrGetLength((CLdapBer *)lm_ber, &v65);
  v22 = 16;
  if ( v21 )
  {
LABEL_16:
    lm_ber[1] = v18;
    v63 = v21;
LABEL_75:
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
      LDAPClientPrint(0x400000, "ldapMsgFromBuff 2 connection 0x%x received protocol error 0x%x .\n", a1, v63);
    goto LABEL_121;
  }
  v55 = lm_ber[1];
  if ( v55 >= *lm_ber )
  {
    v21 = 16;
    goto LABEL_16;
  }
  v56 = v65;
  if ( v65 > 4 )
  {
    v21 = 84;
    v61 = 0x7FFFFFFF;
  }
  else
  {
    v57 = 0;
    v58 = (char *)(*((_QWORD *)lm_ber + 2) + v55);
    v59 = 0;
    if ( v65 != 4 )
      v59 = *v58 < 0;
    if ( v65 )
    {
      do
      {
        v60 = (unsigned __int8)*v58++;
        v57 = v60 | (v57 << 8);
        --v56;
      }
      while ( v56 );
    }
    if ( v59 )
      v61 = v57 | ((int)0x80000000 >> (8 * (4 - v65)));
    else
      v61 = v57;
    v21 = 0;
  }
  lm_ber[1] = v55 + v65;
  if ( v21 )
    goto LABEL_16;
  a2->lm_referral = v61 >> 25;
  a2->lm_msgid = v61 & 0x1FFFFFF;
  v23 = lm_ber[1];
  if ( *lm_ber <= v23 )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000) != 0 )
      LDAPClientPrint(0x2000, "HrPeekTag ran out of data, length 0x%x, offset 0x%x.\n", *lm_ber, v23);
  }
  else
  {
    v3 = *(unsigned __int8 *)(v23 + *((_QWORD *)lm_ber + 2));
    v64 = v3;
  }
  if ( *((_QWORD *)a1 + 120) != -1 && *((_DWORD *)a1 + 250) == 2 && v3 == 4 )
  {
    Sequence = CLdapBer::HrSkipElement((CLdapBer *)lm_ber);
    if ( Sequence )
    {
      if ( !g_fTracingOn || !g_fProviderEnabled || (g_ulTraceFlags & 0x400000) == 0 )
        goto LABEL_121;
      v54 = "ldapMsgFromBuff 11 connection 0x%x received protocol error 0x%x .\n";
LABEL_219:
      LDAPClientPrint(0x400000, v54, a1, Sequence);
      goto LABEL_121;
    }
    CLdapBer::HrPeekTag((CLdapBer *)lm_ber, &v64);
    v3 = v64;
  }
  if ( v3 == 48 )
  {
    Sequence = CLdapBer::HrStartReadSequence((CLdapBer *)lm_ber, 0x30u, 0);
    if ( Sequence )
    {
      if ( !g_fTracingOn || !g_fProviderEnabled || (g_ulTraceFlags & 0x400000) == 0 )
        goto LABEL_121;
      v54 = "ldapMsgFromBuff 3 connection 0x%x received protocol error 0x%x .\n";
      goto LABEL_219;
    }
    CLdapBer::HrPeekTag((CLdapBer *)lm_ber, &v64);
    v3 = v64;
  }
  a2->lm_msgtype = v3;
  v24 = lm_ber[1];
  v25 = *lm_ber;
  if ( *lm_ber <= (unsigned int)v24 )
  {
    if ( !g_fTracingOn )
      goto LABEL_121;
    if ( g_fProviderEnabled && (g_ulTraceFlags & 0x2000) != 0 )
      LDAPClientPrint(0x2000, "HrStartReadSequence ran out of data, length 0x%x, offset 0x%x.\n", v25, v24);
LABEL_192:
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
      LDAPClientPrint(0x400000, "ldapMsgFromBuff 5 connection 0x%x received protocol error 0x%x .\n", a1, v22);
    goto LABEL_121;
  }
  v26 = *((_QWORD *)lm_ber + 2);
  if ( *(unsigned __int8 *)(v24 + v26) != v3 )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000) != 0 )
      LDAPClientPrint(
        0x2000,
        "HrStartReadSequence expected tag of 0x%x, received 0x%x.\n",
        v3,
        *(unsigned __int8 *)(v24 + v26));
    goto LABEL_71;
  }
  v27 = (unsigned int)(v24 + 1);
  lm_ber[1] = v27;
  if ( v25 <= (unsigned int)v27 )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000) != 0 )
      LDAPClientPrint(
        0x2000,
        "HrStartReadSequence 2 ran out of data, length 0x%x, offset 0x%x.\n",
        v25,
        (unsigned int)v27);
    goto LABEL_71;
  }
  v28 = *(_BYTE *)(v27 + v26);
  if ( v28 >= 0 )
    v29 = 1;
  else
    v29 = (v28 & 0x7F) + 1;
  v30 = lm_ber[8];
  if ( (unsigned int)v30 >= 0x32 )
  {
    v33 = -2147024882;
  }
  else
  {
    v31 = lm_ber[210];
    v32 = lm_ber[209];
    lm_ber[4 * v30 + 9] = v27;
    lm_ber[4 * lm_ber[8] + 10] = v29;
    lm_ber[4 * lm_ber[8] + 11] = v31;
    lm_ber[4 * lm_ber[8]++ + 12] = v32;
    v64 = CLdapBer::HrGetLength((CLdapBer *)lm_ber, lm_ber + 209);
    v33 = v64;
    if ( v64 )
    {
      CLdapBer::HrPopSeqStack((CLdapBer *)lm_ber, &v66, &v65, lm_ber + 210, lm_ber + 209);
      v33 = v64;
    }
    else
    {
      lm_ber[210] = lm_ber[1];
    }
  }
  v34 = lm_ber[1];
  v35 = *lm_ber;
  if ( (unsigned int)v34 > *lm_ber )
  {
LABEL_71:
    v22 = -2147024809;
    goto LABEL_192;
  }
  if ( v33 )
  {
    v22 = v33;
    goto LABEL_192;
  }
  lm_msgtype = a2->lm_msgtype;
  if ( (_DWORD)lm_msgtype != 100 )
  {
    if ( (_DWORD)lm_msgtype == 120 )
    {
LABEL_33:
      if ( v35 <= (unsigned int)v34 )
      {
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000) != 0 )
          LDAPClientPrint(0x2000, "HrPeekTag ran out of data, length 0x%x, offset 0x%x.\n", v35, v34);
      }
      else
      {
        v3 = *(unsigned __int8 *)(v34 + *((_QWORD *)lm_ber + 2));
      }
      if ( v3 == 48 )
      {
        Sequence = CLdapBer::HrStartReadSequence((CLdapBer *)lm_ber, 0x30u, 0);
        if ( Sequence )
        {
LABEL_91:
          if ( !g_fTracingOn || !g_fProviderEnabled || (g_ulTraceFlags & 0x400000) == 0 )
            goto LABEL_121;
          v54 = "ldapMsgFromBuff 6 connection 0x%x received protocol error 0x%x .\n";
          goto LABEL_219;
        }
      }
      v37 = lm_ber[1];
      v38 = *lm_ber;
      v64 = 0;
      if ( v38 <= (unsigned int)v37 )
      {
        if ( g_fTracingOn )
        {
          if ( g_fProviderEnabled && (g_ulTraceFlags & 0x2000) != 0 )
          {
            v40 = v37;
LABEL_149:
            LDAPClientPrint(0x2000, "HrGetEnumValue ran out of data, length 0x%x, offset 0x%x.\n", v38, v40);
          }
LABEL_52:
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
            LDAPClientPrint(0x400000, "ldapMsgFromBuff 7 connection 0x%x received protocol error 0x%x .\n", a1, v22);
        }
      }
      else
      {
        v39 = *(unsigned __int8 *)(v37 + *((_QWORD *)lm_ber + 2));
        if ( v39 != 10 )
        {
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000) != 0 )
            LDAPClientPrint(0x2000, "HrGetEnumValue expected tag of 0x%x, received 0x%x.\n", 10, v39);
          v22 = -2147024809;
          goto LABEL_52;
        }
        v40 = v37 + 1;
        lm_ber[1] = v37 + 1;
        if ( v38 > (int)v37 + 1 )
        {
          v41 = CLdapBer::HrGetLength((CLdapBer *)lm_ber, &v64);
          if ( !v41 )
          {
            v42 = lm_ber[1];
            if ( v42 < *lm_ber )
            {
              v43 = v64;
              if ( v64 > 4 )
              {
                v41 = 84;
                v12 = 0x7FFFFFFF;
              }
              else
              {
                v44 = 0;
                v45 = (char *)(*((_QWORD *)lm_ber + 2) + v42);
                v46 = 0;
                if ( v64 != 4 )
                  v46 = *v45 < 0;
                if ( v64 )
                {
                  do
                  {
                    v47 = (unsigned __int8)*v45++;
                    v44 = v47 | (v44 << 8);
                    --v43;
                  }
                  while ( v43 );
                }
                if ( v46 )
                  v12 = v44 | ((int)0x80000000 >> (8 * (4 - v64)));
                else
                  v12 = v44;
                v41 = 0;
              }
              lm_ber[1] = v42 + v64;
            }
          }
          if ( v41 )
          {
            v22 = v41;
            goto LABEL_52;
          }
LABEL_63:
          v49 = GlobalTlsLastErrorIndex;
          a2->lm_returncode = v12;
          if ( v49 != -1 )
          {
            Value = TlsGetValue(v49);
            if ( !Value )
            {
              v62 = (_DWORD *)ldapMalloc(16, 1817471076);
              Value = v62;
              if ( !v62 )
                goto LABEL_64;
              TlsSetValue(GlobalTlsLastErrorIndex, v62);
            }
            *Value = v12;
          }
LABEL_64:
          if ( a1 )
          {
            *((_DWORD *)a1 + 255) = v12;
            if ( v12 > 0x61 )
            {
              if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x8000000) != 0 )
                LDAPClientPrint(0x8000000, "ldap SetConnectionError does not have text for message 0x%x.\n", v12);
              v50 = 80;
            }
            else
            {
              v50 = v12;
            }
            v51 = ldap_err2string(v50);
            *((_QWORD *)a1 + 129) = v51;
            *((_QWORD *)a1 + 128) = 0;
            if ( !*v51 )
            {
              if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x8000000) != 0 )
                LDAPClientPrint(0x8000000, "ldap SetConnectionError does not have text for message 0x%x.\n", v12);
              *((_QWORD *)a1 + 129) = ldap_err2string(0x50u);
            }
          }
          return 0;
        }
        if ( g_fTracingOn )
        {
          if ( g_fProviderEnabled && (g_ulTraceFlags & 0x2000) != 0 )
            goto LABEL_149;
          goto LABEL_52;
        }
      }
LABEL_121:
      SetConnectionError(a1, 2);
      return 2;
    }
    if ( (_DWORD)lm_msgtype != 115 )
    {
      switch ( (int)lm_msgtype )
      {
        case 'a':
        case 'e':
        case 'g':
        case 'i':
        case 'k':
        case 'm':
        case 'o':
          goto LABEL_33;
        default:
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x100000) != 0 )
            LDAPClientPrint(
              0x400000,
              "ldapMsgFromBuff 10 connection 0x%x received protocol error tag=0x%x .\n",
              a1,
              lm_msgtype);
          goto LABEL_121;
      }
    }
    if ( v35 <= (unsigned int)v34 )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000) != 0 )
        LDAPClientPrint(0x2000, "HrPeekTag ran out of data, length 0x%x, offset 0x%x.\n", v35, v34);
    }
    else
    {
      v3 = *(unsigned __int8 *)(v34 + *((_QWORD *)lm_ber + 2));
    }
    if ( v3 == 48 )
    {
      Sequence = CLdapBer::HrStartReadSequence((CLdapBer *)lm_ber, 0x30u, 0);
      if ( Sequence )
        goto LABEL_91;
    }
LABEL_62:
    v12 = 0;
    goto LABEL_63;
  }
  if ( v35 <= (unsigned int)v34 )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000) != 0 )
      LDAPClientPrint(0x2000, "HrPeekTag ran out of data, length 0x%x, offset 0x%x.\n", v35, v34);
  }
  else
  {
    v3 = *(unsigned __int8 *)(v34 + *((_QWORD *)lm_ber + 2));
  }
  if ( v3 == 48 )
  {
    Sequence = CLdapBer::HrStartReadSequence((CLdapBer *)lm_ber, 0x30u, 0);
    if ( Sequence )
    {
      if ( !g_fTracingOn || !g_fProviderEnabled || (g_ulTraceFlags & 0x400000) == 0 )
        goto LABEL_121;
      v54 = "ldapMsgFromBuff 8 connection 0x%x received protocol error 0x%x .\n";
      goto LABEL_219;
    }
  }
  result = CLdapBer::HrSetDNLocation((CLdapBer *)lm_ber);
  if ( !result )
    goto LABEL_62;
  return result;
}

```

## disassembly

```asm
0x180003840  push    rbx
0x180003842  push    rsi
0x180003843  push    rdi
0x180003844  push    r13
0x180003846  sub     rsp, 48h
0x18000384a  mov     rbx, [rdx+8]
0x18000384e  xor     edi, edi
0x180003850  mov     [rsp+68h+arg_8], edi
0x180003854  mov     rsi, rdx
0x180003857  mov     r13, rcx
0x18000385a  test    rbx, rbx
0x18000385d  jz      loc_180004123
0x180003863  mov     r8d, [rbx+4]
0x180003867  mov     edx, [rbx]
0x180003869  mov     [rsp+68h+arg_0], rbp
0x18000386e  mov     [rsp+68h+var_28], r12
0x180003873  mov     [rsp+68h+var_30], r14
0x180003878  mov     [rsp+68h+var_38], r15
0x18000387d  cmp     edx, r8d
0x180003880  jbe     loc_180003EB3
0x180003886  mov     rcx, [rbx+10h]
0x18000388a  movzx   r9d, byte ptr [r8+rcx]
0x18000388f  cmp     r9b, 30h ; '0'
0x180003893  jnz     loc_180003BDE
0x180003899  inc     r8d
0x18000389c  mov     [rbx+4], r8d
0x1800038a0  cmp     edx, r8d
0x1800038a3  jbe     loc_1800041AE
0x1800038a9  movzx   ecx, byte ptr [r8+rcx]
0x1800038ae  lea     r12, [rbx+344h]
0x1800038b5  mov     eax, ecx
0x1800038b7  mov     r15d, 1
0x1800038bd  and     eax, 7Fh
0x1800038c0  mov     r9d, r15d
0x1800038c3  inc     eax
0x1800038c5  test    cl, cl
0x1800038c7  cmovs   r9d, eax
0x1800038cb  mov     eax, [rbx+20h]
0x1800038ce  cmp     eax, 32h ; '2'
0x1800038d1  jnb     loc_180004202
0x1800038d7  mov     edx, [r12]
0x1800038db  add     rax, rax
0x1800038de  mov     ecx, [rbx+348h]
0x1800038e4  mov     [rbx+rax*8+24h], r8d
0x1800038e9  mov     eax, [rbx+20h]
0x1800038ec  add     rax, rax
0x1800038ef  mov     [rbx+rax*8+28h], r9d
0x1800038f4  mov     eax, [rbx+20h]
0x1800038f7  add     rax, rax
0x1800038fa  mov     [rbx+rax*8+2Ch], ecx
0x1800038fe  mov     rcx, rbx; this
0x180003901  mov     eax, [rbx+20h]
0x180003904  add     rax, 3
0x180003908  add     rax, rax
0x18000390b  mov     [rbx+rax*8], edx
0x18000390e  mov     rdx, r12; unsigned int *
0x180003911  inc     dword ptr [rbx+20h]
0x180003914  call    ?HrGetLength@CLdapBer@@QEAAKPEAK@Z; CLdapBer::HrGetLength(ulong *)
0x180003919  mov     r14d, eax
0x18000391c  test    eax, eax
0x18000391e  jnz     loc_1800041D9
0x180003924  mov     eax, [rbx+4]
0x180003927  mov     [rbx+348h], eax
0x18000392d  mov     ebp, [rbx+4]
0x180003930  mov     r8d, [rbx]
0x180003933  cmp     ebp, r8d
0x180003936  ja      loc_180003BEA
0x18000393c  test    r14d, r14d
0x18000393f  jnz     loc_180003EC5
0x180003945  mov     [rsp+68h+arg_10], edi
0x18000394c  cmp     r8d, ebp
0x18000394f  jbe     loc_180003CB4
0x180003955  mov     rax, [rbx+10h]
0x180003959  movzx   r9d, byte ptr [rbp+rax+0]
0x18000395f  cmp     r9d, 2
0x180003963  jnz     loc_180003E35
0x180003969  lea     r9d, [rbp+1]
0x18000396d  mov     [rbx+4], r9d
0x180003971  cmp     r8d, r9d
0x180003974  jbe     loc_180003D1E
0x18000397a  lea     rdx, [rsp+68h+arg_10]; unsigned int *
0x180003982  mov     rcx, rbx; this
0x180003985  xor     r12d, r12d
0x180003988  call    ?HrGetLength@CLdapBer@@QEAAKPEAK@Z; CLdapBer::HrGetLength(ulong *)
0x18000398d  mov     ecx, eax
0x18000398f  mov     r14d, 10h
0x180003995  test    eax, eax
0x180003997  jz      loc_180003DBD
0x18000399d  mov     [rbx+4], ebp
0x1800039a0  test    ecx, ecx
0x1800039a2  jnz     loc_18000428C
0x1800039a8  mov     eax, r12d
0x1800039ab  shr     r12d, 19h
0x1800039af  and     eax, 1FFFFFFh
0x1800039b4  mov     [rsi+3Ch], r12w
0x1800039b9  mov     [rsi], eax
0x1800039bb  mov     eax, [rbx+4]
0x1800039be  mov     r8d, [rbx]
0x1800039c1  cmp     r8d, eax
0x1800039c4  jbe     loc_180003EE8
0x1800039ca  mov     ecx, eax
0x1800039cc  mov     rax, [rbx+10h]
0x1800039d0  movzx   edi, byte ptr [rcx+rax]
0x1800039d4  mov     [rsp+68h+arg_8], edi
0x1800039d8  cmp     qword ptr [r13+3C0h], 0FFFFFFFFFFFFFFFFh
0x1800039e0  jnz     loc_180003E61
0x1800039e6  cmp     edi, 30h ; '0'
0x1800039e9  jz      loc_1800042AA
0x1800039ef  mov     [rsi+4], edi
0x1800039f2  mov     r8d, [rbx+4]
0x1800039f6  mov     ecx, [rbx]
0x1800039f8  cmp     ecx, r8d
0x1800039fb  jbe     loc_18000430B
0x180003a01  mov     r9, [rbx+10h]
0x180003a05  movzx   edx, byte ptr [r8+r9]
0x180003a0a  cmp     edx, edi
0x180003a0c  jnz     loc_180003C94
0x180003a12  inc     r8d
0x180003a15  mov     [rbx+4], r8d
0x180003a19  cmp     ecx, r8d
0x180003a1c  jbe     loc_180004358
0x180003a22  movzx   r9d, byte ptr [r8+r9]
0x180003a27  test    r9b, r9b
0x180003a2a  jns     loc_180003CAC
0x180003a30  and     r9d, 7Fh
0x180003a34  inc     r9d
0x180003a37  mov     eax, [rbx+20h]
0x180003a3a  cmp     eax, 32h ; '2'
0x180003a3d  jnb     loc_1800043B2
0x180003a43  mov     ecx, [rbx+348h]
0x180003a49  lea     r12, [rbx+344h]
0x180003a50  mov     edx, [r12]
0x180003a54  add     rax, rax
0x180003a57  mov     [rbx+rax*8+24h], r8d
0x180003a5c  mov     eax, [rbx+20h]
0x180003a5f  add     rax, rax
0x180003a62  mov     [rbx+rax*8+28h], r9d
0x180003a67  mov     eax, [rbx+20h]
0x180003a6a  add     rax, rax
0x180003a6d  mov     [rbx+rax*8+2Ch], ecx
0x180003a71  mov     rcx, rbx; this
0x180003a74  mov     eax, [rbx+20h]
0x180003a77  add     rax, 3
0x180003a7b  add     rax, rax
0x180003a7e  mov     [rbx+rax*8], edx
0x180003a81  mov     rdx, r12; unsigned int *
0x180003a84  inc     dword ptr [rbx+20h]
0x180003a87  call    ?HrGetLength@CLdapBer@@QEAAKPEAK@Z; CLdapBer::HrGetLength(ulong *)
0x180003a8c  mov     [rsp+68h+arg_8], eax
0x180003a90  mov     edx, eax
0x180003a92  test    eax, eax
0x180003a94  jnz     loc_180004385
0x180003a9a  mov     eax, [rbx+4]
0x180003a9d  mov     [rbx+348h], eax
0x180003aa3  mov     ecx, [rbx+4]
0x180003aa6  mov     r8d, [rbx]
0x180003aa9  cmp     ecx, r8d
0x180003aac  ja      loc_180003CA1
0x180003ab2  test    edx, edx
0x180003ab4  jnz     loc_1800043BC
0x180003aba  mov     r9d, [rsi+4]
0x180003abe  cmp     r9d, 64h ; 'd'
0x180003ac2  jz      loc_180003BF5
0x180003ac8  cmp     r9d, 78h ; 'x'
0x180003acc  jnz     loc_180003D4D
0x180003ad2  cmp     r8d, ecx; jumptable 0000000180004413 cases 97,101,103,105,107,109,111
0x180003ad5  jbe     loc_180003F6E
0x180003adb  mov     rax, [rbx+10h]
0x180003adf  movzx   edi, byte ptr [rcx+rax]
0x180003ae3  cmp     edi, 30h ; '0'
0x180003ae6  jz      loc_180003FB2
0x180003aec  mov     edx, [rbx+4]
0x180003aef  mov     r8d, [rbx]
0x180003af2  mov     [rsp+68h+arg_8], 0
0x180003afa  cmp     r8d, edx
0x180003afd  jbe     loc_180004450
0x180003b03  mov     rax, [rbx+10h]
0x180003b07  movzx   r9d, byte ptr [rdx+rax]
0x180003b0c  cmp     r9d, 0Ah
0x180003b10  jnz     loc_18000446F
0x180003b16  lea     r9d, [rdx+1]
0x180003b1a  mov     [rbx+4], r9d
0x180003b1e  cmp     r8d, r9d
0x180003b21  jbe     loc_1800044B0
0x180003b27  lea     rdx, [rsp+68h+arg_8]; unsigned int *
0x180003b2c  mov     rcx, rbx; this
0x180003b2f  call    ?HrGetLength@CLdapBer@@QEAAKPEAK@Z; CLdapBer::HrGetLength(ulong *)
0x180003b34  mov     ecx, eax
0x180003b36  test    eax, eax
0x180003b38  jnz     short loc_180003B9D
0x180003b3a  mov     r8d, [rbx+4]
0x180003b3e  cmp     r8d, [rbx]
0x180003b41  jnb     short loc_180003B9D
0x180003b43  mov     r9d, [rsp+68h+arg_8]
0x180003b48  mov     r10d, r9d
0x180003b4b  cmp     r9d, 4
0x180003b4f  ja      loc_1800044E0
0x180003b55  mov     ecx, r8d
0x180003b58  xor     edx, edx
0x180003b5a  add     rcx, [rbx+10h]
0x180003b5e  xor     r11d, r11d
0x180003b61  mov     edi, 4
0x180003b66  sub     edi, r9d
0x180003b69  jz      short loc_180003B71
0x180003b6b  cmp     [rcx], dl
0x180003b6d  cmovl   r11d, r15d
0x180003b71  test    r9d, r9d
0x180003b74  jz      short loc_180003B88
0x180003b76  movzx   eax, byte ptr [rcx]
0x180003b79  lea     rcx, [rcx+1]
0x180003b7d  shl     edx, 8
0x180003b80  or      edx, eax
0x180003b82  add     r10d, 0FFFFFFFFh
0x180003b86  jnz     short loc_180003B76
0x180003b88  test    r11d, r11d
0x180003b8b  jnz     loc_180004067
0x180003b91  mov     r15d, edx
0x180003b94  xor     ecx, ecx
0x180003b96  lea     eax, [r8+r9]
0x180003b9a  mov     [rbx+4], eax
0x180003b9d  test    ecx, ecx
0x180003b9f  jz      short loc_180003C1E
0x180003ba1  mov     r14d, ecx
0x180003ba4  cmp     cs:g_fTracingOn, 0
0x180003bab  jz      loc_180003ED1
0x180003bb1  cmp     cs:g_fProviderEnabled, 0
0x180003bb8  jz      loc_180003ED1
0x180003bbe  test    cs:g_ulTraceFlags, 400000h
0x180003bc9  jz      loc_180003ED1
0x180003bcf  mov     r9d, r14d
0x180003bd2  lea     rdx, aLdapmsgfrombuf_6; "ldapMsgFromBuff 7 connection 0x%x recei"...
0x180003bd9  jmp     loc_18000453D
0x180003bde  cmp     cs:g_fTracingOn, edi
0x180003be4  jnz     loc_180004166
0x180003bea  mov     r14d, 80070057h
0x180003bf0  jmp     loc_180003EC5
0x180003bf5  cmp     r8d, ecx
0x180003bf8  jbe     loc_180003F2A
0x180003bfe  mov     rax, [rbx+10h]
0x180003c02  movzx   edi, byte ptr [rcx+rax]
0x180003c06  cmp     edi, 30h ; '0'
0x180003c09  jz      loc_1800044F0
0x180003c0f  mov     rcx, rbx; this
0x180003c12  call    ?HrSetDNLocation@CLdapBer@@QEAAKXZ; CLdapBer::HrSetDNLocation(void)
0x180003c17  test    eax, eax
0x180003c19  jnz     short loc_180003C75
0x180003c1b  xor     r15d, r15d
0x180003c1e  mov     ecx, cs:GlobalTlsLastErrorIndex; dwTlsIndex
0x180003c24  mov     [rsi+38h], r15d
0x180003c28  cmp     ecx, 0FFFFFFFFh
0x180003c2b  jnz     loc_180003CFE
0x180003c31  test    r13, r13
0x180003c34  jz      short loc_180003C73
0x180003c36  mov     [r13+3FCh], r15d
0x180003c3d  test    r15d, r15d
0x180003c40  js      loc_18000454F
0x180003c46  cmp     r15d, 62h ; 'b'
0x180003c4a  jnb     loc_18000454F
0x180003c50  mov     ecx, r15d; err
0x180003c53  call    ldap_err2string
0x180003c58  mov     [r13+408h], rax
0x180003c5f  mov     qword ptr [r13+400h], 0
0x180003c6a  cmp     byte ptr [rax], 0
0x180003c6d  jz      loc_18000458C
0x180003c73  xor     eax, eax
0x180003c75  mov     r14, [rsp+68h+var_30]
0x180003c7a  mov     r12, [rsp+68h+var_28]
0x180003c7f  mov     rbp, [rsp+68h+arg_0]
0x180003c84  mov     r15, [rsp+68h+var_38]
0x180003c89  add     rsp, 48h
0x180003c8d  pop     r13
0x180003c8f  pop     rdi
0x180003c90  pop     rsi
0x180003c91  pop     rbx
0x180003c92  retn
0x180003c94  cmp     cs:g_fTracingOn, 0
0x180003c9b  jnz     loc_18000432A
0x180003ca1  mov     r14d, 80070057h
0x180003ca7  jmp     loc_1800043BF
0x180003cac  mov     r9d, r15d
0x180003caf  jmp     loc_180003A37
0x180003cb4  cmp     cs:g_fTracingOn, edi
0x180003cba  jnz     loc_180004239
0x180003cc0  mov     r14d, 10h
0x180003cc6  cmp     cs:g_fTracingOn, edi
0x180003ccc  jz      loc_180003ED1
0x180003cd2  cmp     cs:g_fProviderEnabled, edi
0x180003cd8  jz      loc_180003ED1
0x180003cde  test    cs:g_ulTraceFlags, 400000h
0x180003ce9  jz      loc_180003ED1
0x180003cef  mov     r9d, r14d
0x180003cf2  lea     rdx, aLdapmsgfrombuf_0; "ldapMsgFromBuff 2 connection 0x%x recei"...
0x180003cf9  jmp     loc_18000453D
0x180003cfe  call    cs:__imp_TlsGetValue
0x180003d05  nop     dword ptr [rax+rax+00h]
0x180003d0a  mov     rbx, rax
0x180003d0d  test    rax, rax
0x180003d10  jz      loc_18000401B
0x180003d16  mov     [rbx], r15d
0x180003d19  jmp     loc_180003C31
  ... truncated ...
```
