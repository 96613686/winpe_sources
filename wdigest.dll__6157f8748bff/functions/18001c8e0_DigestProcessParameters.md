# DigestProcessParameters

- ea: `0x18001c8e0`
- end: `0x18001d5e0`
- name: `DigestProcessParameters`
- size: `3328`
- prototype: ``
- caller_count: `1`
- callee_count: `28`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001e4b0`

## callees

- `0x1800061a0`
- `0x180006de0`
- `0x1800083a0`
- `0x180009770`
- `0x18000cb00`
- `0x180011fec`
- `0x180012880`
- `0x1800179f4`
- `0x180017ee0`
- `0x180017efc`
- `0x1800185b8`
- `0x18001874c`
- `0x1800187bc`
- `0x180018988`
- `0x180018b18`
- `0x18001b4b0`
- `0x18001baac`
- `0x18001c8e0`
- `0x18001e218`
- `0x180022444`
- `0x1800224a4`
- `0x180022bb8`
- `0x180024c58`
- `0x180028ff0`
- `0x18002a3ac`
- `0x18002a668`
- `0x1800377bc`
- `0x180038010`

## import_xrefs

- `ntdll!RtlCharToInteger` at `0x18001ca98`
- `ntdll!RtlCharToInteger` at `0x18001ca98`
- `ntdll!RtlCompareString` at `0x18001ca1f`
- `ntdll!RtlCompareString` at `0x18001ca1f`
- `ntdll!NtClose` at `0x18001d522`
- `ntdll!NtClose` at `0x18001d522`
- `LSASRV!LsaIModifyPerformanceCounter` at `0x18001d2fc`
- `LSASRV!LsaIModifyPerformanceCounter` at `0x18001d2fc`

## pseudocode

```c
__int64 __fastcall DigestProcessParameters(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int *a4,
        int *a5,
        _DWORD *a6,
        _DWORD *a7)
{
  int v10; // ebx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  size_t v13; // r8
  const void *v14; // rdx
  int v15; // eax
  PVOID *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r9
  __int64 v19; // rcx
  _QWORD *v20; // r12
  int v21; // r12d
  int v22; // r13d
  _DWORD *Memory; // rax
  _DWORD *v24; // rbx
  _WORD *v25; // rcx
  char *v26; // rbx
  size_t v27; // r8
  char *v28; // rcx
  _DWORD *v29; // rbx
  void *v30; // rdx
  __int64 v31; // r8
  PVOID *v32; // rcx
  int v33; // eax
  __int64 v34; // rcx
  __int64 v35; // r9
  _QWORD *v36; // r13
  PVOID *v37; // rcx
  int *v38; // rax
  void *v39; // rcx
  unsigned __int16 v41[2]; // [rsp+60h] [rbp-A0h] BYREF
  NTSTATUS v42; // [rsp+64h] [rbp-9Ch] BYREF
  ULONG Value; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v44; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int v45; // [rsp+70h] [rbp-90h] BYREF
  int v46; // [rsp+74h] [rbp-8Ch] BYREF
  int v47; // [rsp+78h] [rbp-88h]
  int *v48; // [rsp+80h] [rbp-80h]
  HLOCAL hMem; // [rsp+88h] [rbp-78h]
  __int64 v50; // [rsp+90h] [rbp-70h] BYREF
  HLOCAL v51; // [rsp+98h] [rbp-68h] BYREF
  void *Src; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v53; // [rsp+A8h] [rbp-58h] BYREF
  _DWORD *v54; // [rsp+B8h] [rbp-48h]
  _DWORD *v55; // [rsp+C0h] [rbp-40h]
  __int64 v56; // [rsp+C8h] [rbp-38h]
  _QWORD v57[2]; // [rsp+D0h] [rbp-30h] BYREF
  char String[8]; // [rsp+E0h] [rbp-20h] BYREF
  char v59; // [rsp+E8h] [rbp-18h]

  v48 = a5;
  v54 = a6;
  v55 = a7;
  v42 = 0;
  Value = 0;
  v47 = 0;
  Src = 0;
  v57[1] = L"MICROSOFT_AUTHENTICATION_PACKAGE_V1_0";
  hMem = 0;
  v50 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v53 = 0;
  v51 = 0;
  v56 = a3;
  v57[0] = 4980810;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 196, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids);
  *a6 = 0;
  *a4 = -1073741715;
  *a5 = -1073741715;
  *a7 = 0;
  *(_DWORD *)(a2 + 8) = *(_DWORD *)(a1 + 52);
  *(_DWORD *)a2 = *(_DWORD *)(a1 + 44);
  *(_DWORD *)(a2 + 12) = *(_DWORD *)(a1 + 48);
  *(_DWORD *)(a2 + 20) = *(_DWORD *)(a1 + 60);
  if ( (int)NonceIsValid(a2 + 56) < 0 )
  {
    v10 = -1073741811;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v12 = 197;
LABEL_152:
      WPP_SF_(v11[2], v12, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids);
      goto LABEL_153;
    }
    goto LABEL_153;
  }
  if ( !RtlCompareString((const STRING *)(a1 + 64), (const STRING *)(a2 + 56), 0) )
  {
    if ( (unsigned __int16)(*(_WORD *)(a2 + 88) - 1) > 7u )
    {
      v10 = -1073741811;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v12 = 200;
        goto LABEL_152;
      }
      goto LABEL_153;
    }
    v13 = *(unsigned __int16 *)(a2 + 88);
    v14 = *(const void **)(a2 + 96);
    *(_QWORD *)String = 0;
    v59 = 0;
    memcpy_0(String, v14, v13);
    if ( RtlCharToInteger(String, 0x10u, &Value) < 0 )
    {
      v10 = -1073741811;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v12 = 199;
        goto LABEL_152;
      }
      goto LABEL_153;
    }
    if ( Value != 1 )
    {
      v10 = -2146893040;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v12 = 201;
        goto LABEL_152;
      }
      goto LABEL_153;
    }
    if ( *(_DWORD *)(a1 + 96) && *(_WORD *)(a1 + 128) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 202, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids);
      StringFree(a2 + 960);
      v10 = StringDuplicate(a2 + 960, a1 + 128);
      if ( v10 < 0 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v12 = 203;
          goto LABEL_152;
        }
        goto LABEL_153;
      }
      v10 = DigestCalculation(a2, 0);
      if ( v10 < 0 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v12 = 204;
          goto LABEL_152;
        }
        goto LABEL_153;
      }
      *(_DWORD *)(a1 + 96) = Value;
LABEL_144:
      v38 = v48;
      *a4 = 0;
      *v38 = 0;
      goto LABEL_153;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 205, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids);
    v15 = DigestDecodeDirectiveStrings(a2);
    v10 = v15;
    if ( v15 < 0 )
    {
      v16 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_153;
      v17 = 206;
LABEL_42:
      v18 = (unsigned int)v15;
      goto LABEL_43;
    }
    v19 = *(_QWORD *)(a1 + 624);
    if ( v19 )
    {
      v20 = (_QWORD *)(a1 + 632);
      if ( (int)SsiIIsAccountInRealm(v19, a2 + 472, a2 + 456, a1 + 632) >= 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_ZZ(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            207,
            &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids,
            a2 + 472,
            a2 + 456);
        v10 = DigestSsiProcessParameters(a1, a2, v56, (_DWORD)a4, (__int64)v48, (__int64)v54, (__int64)v55);
        if ( v10 >= 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 209, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids);
          *(_DWORD *)(a1 + 96) = Value;
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            208,
            &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids,
            (unsigned int)v10);
        }
        SsiIReleasePrincipal(*(_QWORD *)(a1 + 624), *v20);
        *v20 = 0;
        goto LABEL_153;
      }
    }
    v15 = DigestDecodeUserAccount(a2);
    v10 = v15;
    if ( v15 < 0 )
    {
      v16 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_153;
      v17 = 210;
      goto LABEL_42;
    }
    *(_WORD *)(a2 + 4) |= 4u;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_Z(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        211,
        &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids,
        &word_1800459F8);
    v41[0] = 0;
    v15 = BlobEncodeRequest(a2, &Src, v41);
    v10 = v15;
    if ( v15 < 0 )
    {
      v16 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_153;
      v17 = 212;
      goto LABEL_42;
    }
    v21 = v41[0];
    v22 = v41[0] + g_ustrNtDigestPackageName.Length + (unsigned __int16)word_1800459F8;
    Memory = (_DWORD *)DigestAllocateMemory((unsigned int)(v22 + 64));
    hMem = Memory;
    if ( !Memory )
    {
      v10 = -1073741670;
      goto LABEL_153;
    }
    v24 = Memory + 16;
    *Memory = 7;
    *((_WORD *)Memory + 4) = word_1800459F8;
    *((_WORD *)Memory + 5) = word_1800459F8;
    *((_QWORD *)Memory + 2) = Memory + 16;
    memcpy_0(Memory + 16, ::Src, (unsigned __int16)word_1800459F8);
    v25 = hMem;
    v26 = (char *)v24 + (unsigned __int16)word_1800459F8;
    *((_WORD *)hMem + 12) = g_ustrNtDigestPackageName.Length;
    v25[13] = g_ustrNtDigestPackageName.Length;
    *((_QWORD *)v25 + 4) = v26;
    memcpy_0(v26, g_ustrNtDigestPackageName.Buffer, g_ustrNtDigestPackageName.Length);
    v27 = v41[0];
    v28 = &v26[g_ustrNtDigestPackageName.Length];
    v29 = hMem;
    v30 = Src;
    *((_QWORD *)hMem + 6) = v28;
    v29[10] = v21;
    memcpy_0(v28, v30, v27);
    v10 = (*(__int64 (__fastcall **)(_QWORD *, _DWORD *, _QWORD, __int64 *, unsigned int *, NTSTATUS *))(*(_QWORD *)&g_LsaFunctions + 176LL))(
            v57,
            v29,
            (unsigned int)(v22 + 64),
            &v50,
            &v44,
            &v42);
    v32 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_lDD(*((_QWORD *)WPP_GLOBAL_Control + 2), 213, v31, v44, v10, v42);
      v32 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v10 < 0 )
    {
      if ( v32 != &WPP_GLOBAL_Control && (*((_BYTE *)v32 + 28) & 1) != 0 )
        WPP_SF_d(v32[2], 214, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids, (unsigned int)v10);
      if ( v10 == -1073741821 )
        v10 = -1073741715;
      goto LABEL_153;
    }
    v10 = v42;
    *v54 = 1;
    if ( v10 >= 0 )
    {
      v34 = v50;
      if ( !v50 || !v44 || (v35 = *(unsigned int *)(v50 + 8), !(_DWORD)v35) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 216, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids);
        v10 = -1073741595;
        goto LABEL_153;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 217, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids, v35);
        v34 = v50;
      }
      v15 = DigestDecodeResponse(
              *(unsigned int *)(v34 + 8),
              (void *)(v34 + 24),
              &v46,
              &v45,
              &v51,
              a1 + 128,
              a1 + 600,
              a1 + 568);
      v10 = v15;
      if ( v15 < 0 )
      {
        v16 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_153;
        v17 = 218;
        goto LABEL_42;
      }
      v16 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 219, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids);
        v16 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v46 )
      {
        v10 = DigestCheckPacForSidFiltering((struct _DIGEST_PARAMETER *)a2);
        if ( v10 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              221,
              &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids,
              (unsigned int)v10);
          StringFree(a1 + 128);
          goto LABEL_153;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 222, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids);
        v36 = (_QWORD *)(a1 + 544);
        v10 = (*(__int64 (__fastcall **)(HLOCAL, _QWORD, __int64, struct _TOKEN_SOURCE *, int, __int64, __int64, __int64, __int128 *, NTSTATUS *))(*(_QWORD *)&g_LsaFunctions + 272LL))(
                v51,
                v45,
                2,
                &g_DigestSource,
                3,
                (a1 + 568) & -(__int64)(*(_WORD *)(a1 + 568) != 0),
                a1 + 544,
                a1 + 552,
                &v53,
                &v42);
        if ( v10 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              223,
              &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids,
              (unsigned int)v10,
              v42);
          *v36 = 0;
          StringFree(a1 + 128);
          goto LABEL_153;
        }
        *v55 = 2;
        LsaIModifyPerformanceCounter(10, 0, 0);
        v47 = 1;
        v37 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            WPP_SF_qDL(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              224,
              &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids,
              *v36,
              *(_DWORD *)(a1 + 556),
              *(_DWORD *)(a1 + 552));
            v37 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v37 != &WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)v37 + 28) & 4) != 0 )
            {
              WPP_SF_Z(v37[2], 225, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids, &v53);
              v37 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v37 != &WPP_GLOBAL_Control && (*((_BYTE *)v37 + 28) & 4) != 0 )
              WPP_SF_aZ(v37[2], 226, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids, a1 + 128);
          }
        }
        *(_DWORD *)(a1 + 96) = Value;
        if ( *(_DWORD *)(a1 + 44) == 4 )
        {
          StringFree(a2 + 960);
          v10 = StringDuplicate(a2 + 960, a1 + 128);
          if ( v10 < 0 )
          {
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v12 = 227;
              goto LABEL_152;
            }
            goto LABEL_153;
          }
          v10 = DigestSASLResponseAuth(a2, v56);
          if ( v10 < 0 )
          {
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v12 = 228;
              goto LABEL_152;
            }
            goto LABEL_153;
          }
        }
        goto LABEL_144;
      }
      v10 = -1073741595;
      if ( v16 == &WPP_GLOBAL_Control || (*((_BYTE *)v16 + 28) & 1) == 0 )
        goto LABEL_153;
      v17 = 220;
      v18 = 3221225701LL;
LABEL_43:
      WPP_SF_d(v16[2], v17, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids, v18);
      goto LABEL_153;
    }
    if ( v10 == -1073741713 || v10 == -1073741712 || v10 == -1073741711 || v10 == -1073741710 )
    {
      *a4 = -1073741714;
    }
    else
    {
      v33 = -1073741477;
      if ( v10 == -1073741477
        || (v33 = -1073741421, v10 == -1073741421)
        || (v33 = -1073741276, v10 == -1073741276)
        || (v33 = -1073741260, v10 == -1073741260) )
      {
        *a4 = v33;
        goto LABEL_93;
      }
      *a4 = -1073741715;
    }
    *v48 = v10;
LABEL_93:
    v16 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_153;
    v17 = 215;
    v18 = (unsigned int)v10;
    goto LABEL_43;
  }
  v10 = -1073741811;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v12 = 198;
    goto LABEL_152;
  }
LABEL_153:
  BlobFreeRequest(Src);
  if ( v10 < 0 )
  {
    if ( v47 == 1 )
    {
      v42 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)&g_LsaFunctions + 8LL))(a1 + 552);
      if ( v42 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 229, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids);
    }
    v39 = *(void **)(a1 + 544);
    if ( v39 )
    {
      v42 = NtClose(v39);
      *(_QWORD *)(a1 + 544) = 0;
    }
  }
  if ( hMem )
    DigestFreeMemory(hMem);
  if ( v50 )
    (*(void (**)(void))(*(_QWORD *)&g_LsaFunctions + 184LL))();
  if ( *((_QWORD *)&v53 + 1) )
  {
    (*(void (**)(void))(*(_QWORD *)&g_LsaFunctions + 48LL))();
    *((_QWORD *)&v53 + 1) = 0;
    LODWORD(v53) = 0;
  }
  DigestFreeMemory(v51);
  DigestFreeMemory(0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      230,
      &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids,
      (unsigned int)v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001c8e0  push    rbp
0x18001c8e2  push    rbx
0x18001c8e3  push    rsi
0x18001c8e4  push    rdi
0x18001c8e5  push    r12
0x18001c8e7  push    r13
0x18001c8e9  push    r14
0x18001c8eb  push    r15
0x18001c8ed  lea     rbp, [rsp-8]
0x18001c8f2  sub     rsp, 108h
0x18001c8f9  mov     rax, cs:__security_cookie
0x18001c900  xor     rax, rsp
0x18001c903  mov     [rbp+40h+var_50], rax
0x18001c907  mov     r14, [rbp+40h+arg_20]
0x18001c90b  lea     rax, aMicrosoftAuthe; "MICROSOFT_AUTHENTICATION_PACKAGE_V1_0"
0x18001c912  mov     rbx, [rbp+40h+arg_28]
0x18001c916  xor     r13d, r13d
0x18001c919  mov     r12, [rbp+40h+arg_30]
0x18001c920  xorps   xmm0, xmm0
0x18001c923  mov     [rbp+40h+var_C0], r14
0x18001c927  mov     r15, r9
0x18001c92a  mov     [rbp+40h+var_88], rbx
0x18001c92e  mov     rsi, rdx
0x18001c931  mov     [rbp+40h+var_80], r12
0x18001c935  mov     rdi, rcx
0x18001c938  mov     [rsp+140h+var_DC], r13d
0x18001c93d  mov     [rsp+140h+Value], r13d
0x18001c942  mov     [rsp+140h+var_C8], r13d
0x18001c947  mov     [rbp+40h+Src], r13
0x18001c94b  mov     [rbp+40h+var_68], rax
0x18001c94f  mov     [rbp+40h+hMem], r13
0x18001c953  mov     [rbp+40h+var_B0], r13
0x18001c957  mov     [rsp+140h+var_D4], r13d
0x18001c95c  mov     [rsp+140h+var_D0], r13d
0x18001c961  mov     [rsp+140h+var_CC], r13d
0x18001c966  movups  [rbp+40h+var_98], xmm0
0x18001c96a  mov     [rbp+40h+var_A8], r13
0x18001c96e  mov     [rbp+40h+var_78], r8
0x18001c972  mov     [rbp+40h+var_70], 4C004Ah
0x18001c97a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c981  lea     rax, WPP_GLOBAL_Control
0x18001c988  cmp     rcx, rax
0x18001c98b  jz      short loc_18001C9A8
0x18001c98d  test    byte ptr [rcx+1Ch], 80h
0x18001c991  jz      short loc_18001C9A8
0x18001c993  mov     rcx, [rcx+10h]
0x18001c997  lea     r8, WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids
0x18001c99e  mov     edx, 0C4h
0x18001c9a3  call    WPP_SF_
0x18001c9a8  mov     [rbx], r13d
0x18001c9ab  lea     rcx, [rsi+38h]
0x18001c9af  mov     eax, 0C000006Dh
0x18001c9b4  mov     [r15], eax
0x18001c9b7  mov     [r14], eax
0x18001c9ba  mov     [r12], r13d
0x18001c9be  mov     eax, [rdi+34h]
0x18001c9c1  mov     [rsi+8], eax
0x18001c9c4  mov     eax, [rdi+2Ch]
0x18001c9c7  mov     [rsi], eax
0x18001c9c9  mov     eax, [rdi+30h]
0x18001c9cc  mov     [rsi+0Ch], eax
0x18001c9cf  mov     eax, [rdi+3Ch]
0x18001c9d2  mov     [rsi+14h], eax
0x18001c9d5  call    NonceIsValid
0x18001c9da  mov     r14d, 1
0x18001c9e0  test    eax, eax
0x18001c9e2  jns     short loc_18001CA14
0x18001c9e4  mov     ebx, 0C000000Dh
0x18001c9e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c9f0  lea     r12, WPP_GLOBAL_Control
0x18001c9f7  cmp     rcx, r12
0x18001c9fa  jz      loc_18001D4BC
0x18001ca00  test    [rcx+1Ch], r14b
0x18001ca04  jz      loc_18001D4BC
0x18001ca0a  mov     edx, 0C5h
0x18001ca0f  jmp     loc_18001D4AC
0x18001ca14  lea     rcx, [rdi+40h]; String1
0x18001ca18  xor     r8d, r8d; CaseInSensitive
0x18001ca1b  lea     rdx, [rsi+38h]; String2
0x18001ca1f  call    cs:__imp_RtlCompareString
0x18001ca25  test    eax, eax
0x18001ca27  jz      short loc_18001CA59
0x18001ca29  mov     ebx, 0C000000Dh
0x18001ca2e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ca35  lea     r12, WPP_GLOBAL_Control
0x18001ca3c  cmp     rcx, r12
0x18001ca3f  jz      loc_18001D4BC
0x18001ca45  test    [rcx+1Ch], r14b
0x18001ca49  jz      loc_18001D4BC
0x18001ca4f  mov     edx, 0C6h
0x18001ca54  jmp     loc_18001D4AC
0x18001ca59  movzx   eax, word ptr [rsi+58h]
0x18001ca5d  mov     ecx, 7
0x18001ca62  sub     ax, r14w
0x18001ca66  cmp     ax, cx
0x18001ca69  ja      loc_18001D489
0x18001ca6f  movzx   r8d, word ptr [rsi+58h]; Size
0x18001ca74  lea     rcx, [rbp+40h+String]; void *
0x18001ca78  mov     rdx, [rsi+60h]; Src
0x18001ca7c  xor     eax, eax
0x18001ca7e  mov     qword ptr [rbp+40h+String], rax
0x18001ca82  mov     [rbp+40h+var_58], al
0x18001ca85  call    memcpy_0
0x18001ca8a  lea     r8, [rsp+140h+Value]; Value
0x18001ca8f  mov     edx, 10h; Base
0x18001ca94  lea     rcx, [rbp+40h+String]; String
0x18001ca98  call    cs:__imp_RtlCharToInteger
0x18001ca9e  test    eax, eax
0x18001caa0  jns     short loc_18001CAD2
0x18001caa2  mov     ebx, 0C000000Dh
0x18001caa7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001caae  lea     r12, WPP_GLOBAL_Control
0x18001cab5  cmp     rcx, r12
0x18001cab8  jz      loc_18001D4BC
0x18001cabe  test    [rcx+1Ch], r14b
0x18001cac2  jz      loc_18001D4BC
0x18001cac8  mov     edx, 0C7h
0x18001cacd  jmp     loc_18001D4AC
0x18001cad2  cmp     [rsp+140h+Value], r14d
0x18001cad7  jz      short loc_18001CB09
0x18001cad9  mov     ebx, 80090310h
0x18001cade  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cae5  lea     r12, WPP_GLOBAL_Control
0x18001caec  cmp     rcx, r12
0x18001caef  jz      loc_18001D4BC
0x18001caf5  test    [rcx+1Ch], r14b
0x18001caf9  jz      loc_18001D4BC
0x18001caff  mov     edx, 0C9h
0x18001cb04  jmp     loc_18001D4AC
0x18001cb09  cmp     [rdi+60h], r13d
0x18001cb0d  jz      loc_18001CBF1
0x18001cb13  lea     r12, [rdi+80h]
0x18001cb1a  cmp     [r12], r13w
0x18001cb1f  jz      loc_18001CBF1
0x18001cb25  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cb2c  lea     rax, WPP_GLOBAL_Control
0x18001cb33  cmp     rcx, rax
0x18001cb36  jz      short loc_18001CB5F
0x18001cb38  mov     r14d, 4
0x18001cb3e  test    [rcx+1Ch], r14b
0x18001cb42  jz      short loc_18001CB59
0x18001cb44  mov     rcx, [rcx+10h]
0x18001cb48  lea     r8, WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids
0x18001cb4f  mov     edx, 0CAh
0x18001cb54  call    WPP_SF_
0x18001cb59  mov     r14d, 1
0x18001cb5f  lea     rbx, [rsi+3C0h]
0x18001cb66  mov     rcx, rbx
0x18001cb69  call    StringFree
0x18001cb6e  mov     rdx, r12
0x18001cb71  mov     rcx, rbx
0x18001cb74  call    StringDuplicate
0x18001cb79  mov     ebx, eax
0x18001cb7b  test    eax, eax
0x18001cb7d  jns     short loc_18001CBAA
0x18001cb7f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cb86  lea     r12, WPP_GLOBAL_Control
0x18001cb8d  cmp     rcx, r12
0x18001cb90  jz      loc_18001D4BC
0x18001cb96  test    [rcx+1Ch], r14b
0x18001cb9a  jz      loc_18001D4BC
0x18001cba0  mov     edx, 0CBh
0x18001cba5  jmp     loc_18001D4AC
0x18001cbaa  xor     edx, edx
0x18001cbac  mov     rcx, rsi
0x18001cbaf  call    DigestCalculation
0x18001cbb4  mov     ebx, eax
0x18001cbb6  test    eax, eax
0x18001cbb8  jns     short loc_18001CBE5
0x18001cbba  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cbc1  lea     r12, WPP_GLOBAL_Control
0x18001cbc8  cmp     rcx, r12
0x18001cbcb  jz      loc_18001D4BC
0x18001cbd1  test    [rcx+1Ch], r14b
0x18001cbd5  jz      loc_18001D4BC
0x18001cbdb  mov     edx, 0CCh
0x18001cbe0  jmp     loc_18001D4AC
0x18001cbe5  mov     eax, [rsp+140h+Value]
0x18001cbe9  mov     [rdi+60h], eax
0x18001cbec  jmp     loc_18001D448
0x18001cbf1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cbf8  lea     r12, WPP_GLOBAL_Control
0x18001cbff  mov     r14d, 4
0x18001cc05  cmp     rcx, r12
0x18001cc08  jz      short loc_18001CC25
0x18001cc0a  test    [rcx+1Ch], r14b
0x18001cc0e  jz      short loc_18001CC25
0x18001cc10  mov     rcx, [rcx+10h]
0x18001cc14  lea     r8, WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids
0x18001cc1b  mov     edx, 0CDh
0x18001cc20  call    WPP_SF_
0x18001cc25  mov     rcx, rsi
0x18001cc28  call    DigestDecodeDirectiveStrings
0x18001cc2d  mov     ebx, eax
0x18001cc2f  test    eax, eax
0x18001cc31  jns     short loc_18001CC6A
0x18001cc33  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cc3a  cmp     rcx, r12
0x18001cc3d  jz      loc_18001D4BC
0x18001cc43  test    byte ptr [rcx+1Ch], 1
0x18001cc47  jz      loc_18001D4BC
0x18001cc4d  mov     edx, 0CEh
0x18001cc52  mov     r9d, eax
0x18001cc55  mov     rcx, [rcx+10h]
0x18001cc59  lea     r8, WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids
0x18001cc60  call    WPP_SF_d
0x18001cc65  jmp     loc_18001D4BC
0x18001cc6a  mov     rcx, [rdi+270h]
0x18001cc71  test    rcx, rcx
0x18001cc74  jz      loc_18001CD9C
0x18001cc7a  lea     rbx, [rsi+1C8h]
0x18001cc81  lea     r13, [rsi+1D8h]
0x18001cc88  mov     r8, rbx
0x18001cc8b  lea     r12, [rdi+278h]
0x18001cc92  mov     rdx, r13
0x18001cc95  mov     r9, r12
0x18001cc98  call    SsiIIsAccountInRealm
0x18001cc9d  test    eax, eax
0x18001cc9f  js      loc_18001CD92
0x18001cca5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ccac  lea     rax, WPP_GLOBAL_Control
0x18001ccb3  cmp     rcx, rax
0x18001ccb6  jz      short loc_18001CCDB
0x18001ccb8  test    [rcx+1Ch], r14b
0x18001ccbc  jz      short loc_18001CCDB
0x18001ccbe  mov     rcx, [rcx+10h]
0x18001ccc2  lea     r8, WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids
0x18001ccc9  mov     edx, 0CFh
0x18001ccce  mov     [rsp+140h+var_120], rbx
0x18001ccd3  mov     r9, r13
0x18001ccd6  call    WPP_SF_ZZ
0x18001ccdb  mov     rax, [rbp+40h+var_80]
0x18001ccdf  mov     r9, r15
0x18001cce2  mov     r8, [rbp+40h+var_78]
0x18001cce6  mov     rdx, rsi
0x18001cce9  mov     [rsp+140h+var_110], rax
0x18001ccee  mov     rcx, rdi
0x18001ccf1  mov     rax, [rbp+40h+var_88]
0x18001ccf5  mov     [rsp+140h+var_118], rax
0x18001ccfa  mov     rax, [rbp+40h+var_C0]
0x18001ccfe  mov     [rsp+140h+var_120], rax
0x18001cd03  call    DigestSsiProcessParameters
0x18001cd08  xor     r13d, r13d
0x18001cd0b  mov     ebx, eax
0x18001cd0d  test    eax, eax
0x18001cd0f  jns     short loc_18001CD44
0x18001cd11  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cd18  lea     rax, WPP_GLOBAL_Control
0x18001cd1f  cmp     rcx, rax
0x18001cd22  jz      short loc_18001CD79
0x18001cd24  test    byte ptr [rcx+1Ch], 1
0x18001cd28  jz      short loc_18001CD79
0x18001cd2a  mov     rcx, [rcx+10h]
0x18001cd2e  lea     r8, WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids
0x18001cd35  mov     edx, 0D0h
0x18001cd3a  mov     r9d, ebx
0x18001cd3d  call    WPP_SF_d
0x18001cd42  jmp     short loc_18001CD79
0x18001cd44  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cd4b  lea     rax, WPP_GLOBAL_Control
0x18001cd52  cmp     rcx, rax
0x18001cd55  jz      short loc_18001CD72
0x18001cd57  test    [rcx+1Ch], r14b
0x18001cd5b  jz      short loc_18001CD72
0x18001cd5d  mov     rcx, [rcx+10h]
0x18001cd61  lea     r8, WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids
0x18001cd68  mov     edx, 0D1h
0x18001cd6d  call    WPP_SF_
0x18001cd72  mov     eax, [rsp+140h+Value]
0x18001cd76  mov     [rdi+60h], eax
0x18001cd79  mov     rdx, [r12]
0x18001cd7d  mov     rcx, [rdi+270h]
0x18001cd84  call    SsiIReleasePrincipal
0x18001cd89  mov     [r12], r13
0x18001cd8d  jmp     loc_18001D452
0x18001cd92  xor     r13d, r13d
0x18001cd95  lea     r12, WPP_GLOBAL_Control
0x18001cd9c  mov     rcx, rsi
0x18001cd9f  call    DigestDecodeUserAccount
0x18001cda4  mov     ebx, eax
0x18001cda6  test    eax, eax
0x18001cda8  jns     short loc_18001CDCE
0x18001cdaa  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cdb1  cmp     rcx, r12
0x18001cdb4  jz      loc_18001D4BC
0x18001cdba  test    byte ptr [rcx+1Ch], 1
0x18001cdbe  jz      loc_18001D4BC
0x18001cdc4  mov     edx, 0D2h
0x18001cdc9  jmp     loc_18001CC52
0x18001cdce  or      [rsi+4], r14w
0x18001cdd3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cdda  cmp     rcx, r12
0x18001cddd  jz      short loc_18001CE01
0x18001cddf  test    [rcx+1Ch], r14b
0x18001cde3  jz      short loc_18001CE01
0x18001cde5  mov     rcx, [rcx+10h]
0x18001cde9  lea     r9, word_1800459F8
0x18001cdf0  mov     edx, 0D3h
0x18001cdf5  lea     r8, WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids
0x18001cdfc  call    WPP_SF_Z
  ... truncated ...
```
