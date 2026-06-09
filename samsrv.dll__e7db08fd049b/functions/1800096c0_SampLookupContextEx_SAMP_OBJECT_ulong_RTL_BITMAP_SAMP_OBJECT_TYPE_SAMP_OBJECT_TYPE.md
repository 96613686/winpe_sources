# SampLookupContextEx(_SAMP_OBJECT *,ulong,_RTL_BITMAP *,_SAMP_OBJECT_TYPE,_SAMP_OBJECT_TYPE *)

- ea: `0x1800096c0`
- end: `0x18000a561`
- name: `?SampLookupContextEx@@YAJPEAU_SAMP_OBJECT@@KPEAU_RTL_BITMAP@@W4_SAMP_OBJECT_TYPE@@PEAW43@@Z`
- size: `3745`
- prototype: `__int64 __fastcall(__int64, ACCESS_MASK, struct _RTL_BITMAP *, int, _DWORD *)`
- caller_count: `21`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180001760`
- `0x180002b40`
- `0x1800031c0`
- `0x180007bd0`
- `0x180009030`
- `0x18000a570`
- `0x18000b150`
- `0x180012160`
- `0x180013370`
- `0x180013710`
- `0x180013b90`
- `0x180014ea0`
- `0x180015430`
- `0x180015c50`
- `0x180015e90`
- `0x18001a0f0`
- `0x18001dc50`
- `0x180020f98`
- `0x180022b30`
- `0x180022db0`
- `0x1800291c0`

## callees

- `0x180002960`
- `0x1800096c0`
- `0x180017a60`
- `0x18001e1b0`
- `0x18001fd40`
- `0x180021400`
- `0x180027e24`
- `0x18002cd80`
- `0x180037284`
- `0x1800372ac`
- `0x180077044`
- `0x18008a550`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x180009740`
- `ntdll!RtlReleaseSRWLockShared` at `0x180009740`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000971e`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000971e`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180009730`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180009730`
- `ntdll!RtlAreAllAccessesGranted` at `0x180009b3d`
- `ntdll!RtlAreAllAccessesGranted` at `0x180009b3d`
- `ntdll!RtlInitializeBitMap` at `0x180009c2e`
- `ntdll!RtlInitializeBitMap` at `0x18000a323`
- `ntdll!RtlInitializeBitMap` at `0x180009c2e`
- `ntdll!RtlInitializeBitMap` at `0x18000a323`
- `ntdll!RtlClearAllBits` at `0x180009c39`
- `ntdll!RtlClearAllBits` at `0x18000a32e`
- `ntdll!RtlClearAllBits` at `0x180009c39`
- `ntdll!RtlClearAllBits` at `0x18000a32e`

## pseudocode

```c
__int64 __fastcall SampLookupContextEx(__int64 a1, ACCESS_MASK a2, struct _RTL_BITMAP *a3, int a4, _DWORD *a5)
{
  PVOID v8; // rdi
  _BOOL8 v9; // rdx
  PUNICODE_STRING v10; // rcx
  int FixedAttributes; // r14d
  ACCESS_MASK v12; // r15d
  int v13; // eax
  char v14; // r12
  __int64 v15; // rsi
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v19; // rcx
  __int64 v20; // rdi
  __int128 *v21; // rcx
  char *v22; // r8
  __int64 v23; // rdx
  __int128 *v24; // rax
  __int128 v25; // xmm0
  __int128 v26; // xmm1
  __int128 v27; // xmm0
  __int128 v28; // xmm1
  __int128 v29; // xmm0
  __int128 v30; // xmm1
  __int128 v31; // xmm0
  __int128 v32; // xmm1
  __int128 v33; // xmm1
  __int128 v34; // xmm0
  __int128 v35; // xmm1
  __int128 v36; // xmm0
  __int128 v37; // xmm1
  __int128 v38; // xmm0
  _OWORD *v39; // rax
  __int128 v40; // xmm0
  __int128 v41; // xmm1
  __int128 v42; // xmm0
  __int128 v43; // xmm1
  __int128 v44; // xmm0
  __int128 v45; // xmm1
  __int128 v46; // xmm0
  __int128 v47; // xmm1
  __int128 v48; // xmm1
  __int128 v49; // xmm0
  __int128 v50; // xmm1
  __int128 v51; // xmm0
  __int128 v52; // xmm1
  __int128 v53; // xmm0
  PUNICODE_STRING v54; // rcx
  __int64 v55; // r12
  __int128 *v56; // r13
  unsigned __int8 v57; // r9
  __int128 *v58; // rax
  __int128 *v59; // rcx
  __int64 v60; // rdx
  __int128 v61; // xmm0
  __int128 v62; // xmm1
  __int128 v63; // xmm0
  __int128 v64; // xmm1
  __int128 v65; // xmm0
  __int128 v66; // xmm1
  __int128 v67; // xmm0
  __int128 v68; // xmm1
  int v69; // edi
  __int128 v70; // xmm1
  char v71; // si
  __int128 v72; // xmm0
  __int128 v73; // xmm1
  __int64 v74; // rax
  PULONG v75; // rcx
  int v76; // eax
  __int64 v77; // rcx
  PULONG v78; // rax
  __int128 *v79; // rax
  __int128 v80; // xmm0
  __int128 v81; // xmm1
  __int128 v82; // xmm0
  __int128 v83; // xmm1
  __int128 v84; // xmm0
  __int128 v85; // xmm1
  __int128 v86; // xmm0
  __int128 v87; // xmm1
  __int128 v88; // xmm1
  __int128 v89; // xmm0
  __int128 v90; // xmm1
  __int64 v91; // rdx
  PUNICODE_STRING v92; // rcx
  __int64 v93; // rdx
  int DomainSettingsDs; // eax
  __int64 v95; // r9
  char *v96; // r8
  __int128 *v97; // rax
  __int128 *v98; // rdx
  __int128 *v99; // rcx
  __int128 v100; // xmm0
  __int128 v101; // xmm0
  __int64 v102; // rdx
  __int128 *v103; // rcx
  __int128 v104; // xmm0
  __int128 v105; // xmm0
  int v106; // eax
  PUNICODE_STRING v107; // rcx
  unsigned __int8 v108; // r9
  PULONG v109; // rcx
  __int64 v110; // rdx
  int v111; // esi
  __int64 v112; // rax
  __int128 *v113; // rax
  __int128 *v114; // rcx
  __int128 v115; // xmm0
  __int128 v116; // xmm1
  __int128 v117; // xmm0
  __int128 v118; // xmm1
  __int128 v119; // xmm0
  __int128 v120; // xmm1
  __int128 v121; // xmm0
  __int128 v122; // xmm1
  __int128 v123; // xmm1
  __int128 v124; // xmm0
  __int128 v125; // xmm1
  int v126; // eax
  __int64 v127; // rcx
  __int64 v128; // rdx
  PULONG v129; // rax
  __int128 *v130; // rax
  __int128 *v131; // rcx
  __int128 v132; // xmm0
  __int128 v133; // xmm1
  __int128 v134; // xmm0
  __int128 v135; // xmm1
  __int128 v136; // xmm0
  __int128 v137; // xmm1
  __int128 v138; // xmm0
  __int128 v139; // xmm1
  __int128 v140; // xmm1
  __int128 v141; // xmm0
  __int128 v142; // xmm1
  __int64 v143; // rdx
  bool v144; // [rsp+30h] [rbp-D0h]
  unsigned __int8 v145[7]; // [rsp+31h] [rbp-CFh] BYREF
  struct _RTL_BITMAP Buffer; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v147; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v148; // [rsp+4Ch] [rbp-B4h] BYREF
  __int64 v149; // [rsp+50h] [rbp-B0h]
  __int128 *v150; // [rsp+58h] [rbp-A8h] BYREF
  struct _RTL_BITMAP *v151; // [rsp+60h] [rbp-A0h]
  _BYTE v152[576]; // [rsp+70h] [rbp-90h] BYREF
  ULONG BitMapBuffer[6]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v151 = a3;
  if ( SampServiceState == 6 )
  {
    v92 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    {
      v93 = 17;
LABEL_116:
      WPP_SF_Dd(v92[3].Buffer, v93, WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids, 3221225692LL, -1073741604);
    }
    return 3221225692LL;
  }
  *(_QWORD *)&Buffer.SizeOfBitMap = a1;
  RtlAcquireSRWLockShared(&SampClientContextLock);
  v8 = RtlLookupElementGenericTableAvl(&SampClientContextTableAVL, &Buffer);
  RtlReleaseSRWLockShared(&SampClientContextLock);
  v10 = WPP_GLOBAL_Control;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 51, WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids, v8 != 0);
    v10 = WPP_GLOBAL_Control;
  }
  if ( v8 )
  {
    LODWORD(v8) = 0;
    FixedAttributes = 0;
    if ( *(_DWORD *)(a1 + 24) != -294125688 )
      FixedAttributes = -1073741816;
  }
  else
  {
    FixedAttributes = -1073545211;
  }
  if ( (*(_DWORD *)(&v10[4].MaximumLength + 1) & 0x20000) != 0 )
  {
    WPP_SF_Dd(
      v10[3].Buffer,
      15,
      WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids,
      (unsigned int)FixedAttributes,
      FixedAttributes);
    v10 = WPP_GLOBAL_Control;
  }
  if ( FixedAttributes < 0 )
  {
    if ( (*(_DWORD *)(&v10[4].MaximumLength + 1) & 0x20000) != 0 )
    {
      v91 = 18;
      goto LABEL_140;
    }
    return (unsigned int)FixedAttributes;
  }
  v12 = 0;
  LOBYTE(v9) = a2 == -1879048193;
  if ( a2 != -1879048193 )
    v12 = a2;
  v144 = a2 == -1879048193;
  if ( v12 == -1 )
  {
    LOBYTE(v9) = 1;
    v12 = 0;
    v144 = 1;
  }
  else if ( (*(_BYTE *)(a1 + 21) & 1) == 0 )
  {
    if ( (*(_DWORD *)(&v10[4].MaximumLength + 1) & 0x20000) == 0 )
      return 3221225480LL;
    v17 = 19;
LABEL_124:
    WPP_SF_Dd(v10[3].Buffer, v17, WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids, 3221225480LL, -1073741816);
    return 3221225480LL;
  }
  v13 = *(_DWORD *)(a1 + 16);
  *a5 = v13;
  if ( a4 != 5 && a4 != v13 )
  {
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      WPP_SF_Dd(
        WPP_GLOBAL_Control[3].Buffer,
        20,
        WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids,
        3221225508LL,
        -1073741788);
    return 3221225508LL;
  }
  if ( SampLock.OwningThread == NtCurrentTeb()->ClientId.UniqueThread )
  {
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 209, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, 1);
    FixedAttributes = 0;
    v150 = 0;
    v145[0] = 1;
    v14 = 0;
    v147 = 0;
    v15 = 2;
    v148 = 0;
    while ( (unsigned int)v8 < SampDefinedDomainsCount )
    {
      v16 = 1360LL * (unsigned int)v8;
      v149 = v16;
      if ( (*(_BYTE *)(*(_QWORD *)((char *)SampDefinedDomains + v16) + 192LL) & 2) != 0
        && !*((_BYTE *)SampDefinedDomains + v16 + 864) )
      {
        if ( !v14 )
        {
          DomainSettingsDs = SampExtGetDomainSettingsDs(v145, &v147, &v148);
          FixedAttributes = DomainSettingsDs;
          if ( DomainSettingsDs < 0 )
          {
            if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
              WPP_SF_Dd(
                WPP_GLOBAL_Control[3].Buffer,
                28,
                WPP_48bf36016493398285a8dbc678e80a21_Traceguids,
                (unsigned int)DomainSettingsDs,
                DomainSettingsDs);
            goto LABEL_103;
          }
          v14 = 1;
        }
        FixedAttributes = SampGetFixedAttributes(*(_QWORD *)((char *)SampDefinedDomains + v149), 0, &v150);
        if ( FixedAttributes < 0 )
          break;
        v95 = 2;
        v96 = (char *)SampDefinedDomains + v149;
        v97 = v150;
        v98 = v150;
        v99 = (__int128 *)((char *)SampDefinedDomains + v149 + 128);
        do
        {
          v99 += 8;
          v100 = *v98;
          v98 += 8;
          *(v99 - 8) = v100;
          *(v99 - 7) = *(v98 - 7);
          *(v99 - 6) = *(v98 - 6);
          *(v99 - 5) = *(v98 - 5);
          *(v99 - 4) = *(v98 - 4);
          *(v99 - 3) = *(v98 - 3);
          *(v99 - 2) = *(v98 - 2);
          *(v99 - 1) = *(v98 - 1);
          --v95;
        }
        while ( v95 );
        *v99 = *v98;
        v99[1] = v98[1];
        v99[2] = v98[2];
        v99[3] = v98[3];
        v99[4] = v98[4];
        v99[5] = v98[5];
        v101 = v98[6];
        v102 = 2;
        v99[6] = v101;
        v103 = (__int128 *)(v96 + 496);
        do
        {
          v103 += 8;
          v104 = *v97;
          v97 += 8;
          *(v103 - 8) = v104;
          *(v103 - 7) = *(v97 - 7);
          *(v103 - 6) = *(v97 - 6);
          *(v103 - 5) = *(v97 - 5);
          *(v103 - 4) = *(v97 - 4);
          *(v103 - 3) = *(v97 - 3);
          *(v103 - 2) = *(v97 - 2);
          *(v103 - 1) = *(v97 - 1);
          --v102;
        }
        while ( v102 );
        *v103 = *v97;
        v103[1] = v97[1];
        v103[2] = v97[2];
        v103[3] = v97[3];
        v103[4] = v97[4];
        v103[5] = v97[5];
        v105 = v97[6];
        v106 = *((_DWORD *)v96 + 327);
        *((_DWORD *)v96 + 55) = v106;
        v103[6] = v105;
        *((_DWORD *)v96 + 147) = v106;
        v96[864] = 1;
        v96[1297] = v145[0];
        *((_DWORD *)v96 + 325) = v147;
        *((_DWORD *)v96 + 326) = v148;
      }
      LODWORD(v8) = (_DWORD)v8 + 1;
    }
    v19 = (__int64)WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      WPP_SF_Dd(
        WPP_GLOBAL_Control[3].Buffer,
        29,
        WPP_48bf36016493398285a8dbc678e80a21_Traceguids,
        (unsigned int)FixedAttributes,
        FixedAttributes);
    if ( FixedAttributes >= 0 )
    {
      if ( (unsigned int)(*(_DWORD *)(a1 + 16) - 1) <= 3 )
      {
        if ( SampLock.OwningThread == NtCurrentTeb()->ClientId.UniqueThread )
        {
          if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
            WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 209, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, 1);
          SampTransactionWithinDomainGlobal = 0;
        }
        else
        {
          v107 = WPP_GLOBAL_Control;
          if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 210, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, 0);
            v107 = WPP_GLOBAL_Control;
          }
          if ( (*(_BYTE *)(&v107[4].MaximumLength + 1) & 4) != 0 && HIBYTE(v107[4].Length) >= 2u )
            WPP_SF_(v107[3].Buffer, 10, WPP_48bf36016493398285a8dbc678e80a21_Traceguids);
        }
        v20 = *(unsigned int *)(a1 + 200);
        if ( SampLock.OwningThread == NtCurrentTeb()->ClientId.UniqueThread )
        {
          if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
            WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 209, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, 1);
          SampTransactionWithinDomainGlobal = 1;
        }
        else if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 210, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, 0);
        }
        SampTransactionDomainIndexGlobal = v20;
        v21 = (__int128 *)v152;
        v22 = (char *)SampDefinedDomains + 1360 * v20;
        v23 = 2;
        v24 = (__int128 *)(v22 + 496);
        do
        {
          v21 += 8;
          v25 = *v24;
          v26 = v24[1];
          v24 += 8;
          *(v21 - 8) = v25;
          v27 = *(v24 - 6);
          *(v21 - 7) = v26;
          v28 = *(v24 - 5);
          *(v21 - 6) = v27;
          v29 = *(v24 - 4);
          *(v21 - 5) = v28;
          v30 = *(v24 - 3);
          *(v21 - 4) = v29;
          v31 = *(v24 - 2);
          *(v21 - 3) = v30;
          v32 = *(v24 - 1);
          *(v21 - 2) = v31;
          *(v21 - 1) = v32;
          --v23;
        }
        while ( v23 );
        v33 = v24[1];
        *v21 = *v24;
        v34 = v24[2];
        v21[1] = v33;
        v35 = v24[3];
        v21[2] = v34;
        v36 = v24[4];
        v21[3] = v35;
        v37 = v24[5];
        v21[4] = v36;
        v38 = v24[6];
        v39 = v22 + 128;
        v21[5] = v37;
        v21[6] = v38;
        v19 = (__int64)v152;
        do
        {
          v39 += 8;
          v40 = *(_OWORD *)v19;
          v41 = *(_OWORD *)(v19 + 16);
          v19 += 128;
          *(v39 - 8) = v40;
          v42 = *(_OWORD *)(v19 - 96);
          *(v39 - 7) = v41;
          v43 = *(_OWORD *)(v19 - 80);
          *(v39 - 6) = v42;
          v44 = *(_OWORD *)(v19 - 64);
          *(v39 - 5) = v43;
          v45 = *(_OWORD *)(v19 - 48);
          *(v39 - 4) = v44;
          v46 = *(_OWORD *)(v19 - 32);
          *(v39 - 3) = v45;
          v47 = *(_OWORD *)(v19 - 16);
          *(v39 - 2) = v46;
          *(v39 - 1) = v47;
          --v15;
        }
        while ( v15 );
        v48 = *(_OWORD *)(v19 + 16);
        *v39 = *(_OWORD *)v19;
        v49 = *(_OWORD *)(v19 + 32);
        v39[1] = v48;
        v50 = *(_OWORD *)(v19 + 48);
        v39[2] = v49;
        v51 = *(_OWORD *)(v19 + 64);
        v39[3] = v50;
        v52 = *(_OWORD *)(v19 + 80);
        v39[4] = v51;
        v53 = *(_OWORD *)(v19 + 96);
        v39[5] = v52;
        v39[6] = v53;
      }
      goto LABEL_46;
    }
LABEL_103:
    v10 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) == 0 )
      return (unsigned int)FixedAttributes;
    v91 = 21;
    goto LABEL_140;
  }
  v19 = (__int64)WPP_GLOBAL_Control;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 210, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, 0);
LABEL_46:
    v9 = v144;
  }
  if ( (*(_BYTE *)(a1 + 20) & 0x20) != 0 )
  {
LABEL_48:
    if ( (*(_BYTE *)(a1 + 192) & 2) != 0 )
      goto LABEL_143;
    if ( !v9 )
    {
      FixedAttributes = SampCheckIfObjectExists((struct _SAMP_OBJECT *)a1);
      if ( FixedAttributes < 0 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
        {
          v91 = 24;
          goto LABEL_140;
        }
        return (unsigned int)FixedAttributes;
      }
    }
    if ( (*(_BYTE *)(a1 + 192) & 2) != 0 )
    {
LABEL_143:
      if ( !v144 && !(unsigned __int8)SampDsIsRunning(v19, v9) )
      {
        if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
          WPP_SF_Dd(
            WPP_GLOBAL_Control[3].Buffer,
            25,
            WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids,
            3221226150LL,
            -1073741146);
        return 3221226150LL;
      }
    }
    if ( (*(_BYTE *)(a1 + 20) & 0x20) == 0 )
    {
      if ( *(_BYTE *)(a1 + 856) && a2 != -1879048193 && !SampContextOwnerIsCurrentCaller((struct _SAMP_OBJECT *)a1) )
      {
        v10 = WPP_GLOBAL_Control;
        if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) == 0 )
          return 3221225480LL;
        v17 = 26;
        goto LABEL_124;
      }
      if ( *(_DWORD *)(a1 + 16) == 4 )
      {
        v55 = 4;
        if ( (v12 & 0x40) != 0 )
        {
          Buffer = 0;
          RtlInitializeBitMap(&Buffer, BitMapBuffer, 0x8Cu);
          RtlClearAllBits(&Buffer);
          v56 = (__int128 *)(a1 + 864);
          v109 = Buffer.Buffer;
          v110 = 4;
          v111 = *(_DWORD *)(a1 + 148);
          v145[0] = *(_BYTE *)(a1 + 208);
          Buffer.SizeOfBitMap = *(_DWORD *)(a1 + 232);
          v112 = *(_QWORD *)(a1 + 240);
          *(_OWORD *)Buffer.Buffer = *(_OWORD *)v112;
          v109[4] = *(_DWORD *)(v112 + 16);
          v113 = (__int128 *)(a1 + 864);
          v114 = (__int128 *)v152;
          do
          {
            v114 += 8;
            v115 = *v113;
            v116 = v113[1];
            v113 += 8;
            *(v114 - 8) = v115;
            v117 = *(v113 - 6);
            *(v114 - 7) = v116;
            v118 = *(v113 - 5);
            *(v114 - 6) = v117;
            v119 = *(v113 - 4);
            *(v114 - 5) = v118;
            v120 = *(v113 - 3);
            *(v114 - 4) = v119;
            v121 = *(v113 - 2);
            *(v114 - 3) = v120;
            v122 = *(v113 - 1);
            *(v114 - 2) = v121;
            *(v114 - 1) = v122;
            --v110;
          }
          while ( v110 );
          v123 = v113[1];
          *v114 = *v113;
          v124 = v113[2];
          v114[1] = v123;
          v125 = v113[3];
          v114[2] = v124;
          v114[3] = v125;
          v126 = SampValidateObjectAccess2((struct _SAMP_OBJECT *)a1, 0x40u, 0, v108, 1u, 0);
          v127 = *(_QWORD *)(a1 + 240);
          FixedAttributes = v126;
          v128 = 4;
          *(_BYTE *)(a1 + 208) = v145[0];
          *(_DWORD *)(a1 + 232) = Buffer.SizeOfBitMap;
          v129 = Buffer.Buffer;
          *(_DWORD *)(a1 + 148) = v111;
          *(_OWORD *)v127 = *(_OWORD *)v129;
          *(_DWORD *)(v127 + 16) = v129[4];
          v130 = (__int128 *)(a1 + 864);
          v131 = (__int128 *)v152;
          do
          {
            v130 += 8;
            v132 = *v131;
            v133 = v131[1];
            v131 += 8;
            *(v130 - 8) = v132;
            v134 = *(v131 - 6);
            *(v130 - 7) = v133;
            v135 = *(v131 - 5);
            *(v130 - 6) = v134;
            v136 = *(v131 - 4);
            *(v130 - 5) = v135;
            v137 = *(v131 - 3);
            *(v130 - 4) = v136;
            v138 = *(v131 - 2);
            *(v130 - 3) = v137;
            v139 = *(v131 - 1);
            *(v130 - 2) = v138;
            *(v130 - 1) = v139;
            --v128;
          }
          while ( v128 );
          v140 = v131[1];
          *v130 = *v131;
          v141 = v131[2];
          v130[1] = v140;
          v142 = v131[3];
          v130[2] = v141;
          v130[3] = v142;
          if ( FixedAttributes < 0 )
          {
            v10 = WPP_GLOBAL_Control;
            if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
            {
              v91 = 27;
              goto LABEL_140;
            }
            return (unsigned int)FixedAttributes;
          }
          v12 &= ~0x40u;
        }
        else
        {
          v56 = (__int128 *)(a1 + 864);
        }
        if ( *(char *)(a1 + 20) < 0 && (v12 & 0x80u) != 0 && !*(_BYTE *)(a1 + 326) )
        {
          Buffer = 0;
          RtlInitializeBitMap(&Buffer, BitMapBuffer, 0x8Cu);
          RtlClearAllBits(&Buffer);
          v58 = v56;
          v59 = (__int128 *)v152;
          v60 = 4;
          do
          {
            v59 += 8;
            v61 = *v58;
            v62 = v58[1];
            v58 += 8;
            *(v59 - 8) = v61;
            v63 = *(v58 - 6);
            *(v59 - 7) = v62;
            v64 = *(v58 - 5);
            *(v59 - 6) = v63;
            v65 = *(v58 - 4);
            *(v59 - 5) = v64;
            v66 = *(v58 - 3);
            *(v59 - 4) = v65;
            v67 = *(v58 - 2);
            *(v59 - 3) = v66;
            v68 = *(v58 - 1);
            *(v59 - 2) = v67;
            *(v59 - 1) = v68;
            --v60;
          }
          while ( v60 );
          v69 = *(_DWORD *)(a1 + 148);
          v70 = v58[1];
          v71 = *(_BYTE *)(a1 + 208);
          *v59 = *v58;
          v72 = v58[2];
          v59[1] = v70;
          v73 = v58[3];
          Buffer.SizeOfBitMap = *(_DWORD *)(a1 + 232);
          v74 = *(_QWORD *)(a1 + 240);
          v59[2] = v72;
          v59[3] = v73;
          v75 = Buffer.Buffer;
          *(_OWORD *)Buffer.Buffer = *(_OWORD *)v74;
          v75[4] = *(_DWORD *)(v74 + 16);
          v76 = SampValidateObjectAccess2((struct _SAMP_OBJECT *)a1, 0x80u, 0, v57, 0, 1u);
          v77 = *(_QWORD *)(a1 + 240);
          FixedAttributes = v76;
          *(_DWORD *)(a1 + 232) = Buffer.SizeOfBitMap;
          v78 = Buffer.Buffer;
          *(_DWORD *)(a1 + 148) = v69;
          *(_BYTE *)(a1 + 208) = v71;
          *(_OWORD *)v77 = *(_OWORD *)v78;
          *(_DWORD *)(v77 + 16) = v78[4];
          v79 = (__int128 *)v152;
          do
          {
            v56 += 8;
            v80 = *v79;
            v81 = v79[1];
            v79 += 8;
            *(v56 - 8) = v80;
            v82 = *(v79 - 6);
            *(v56 - 7) = v81;
            v83 = *(v79 - 5);
            *(v56 - 6) = v82;
            v84 = *(v79 - 4);
            *(v56 - 5) = v83;
            v85 = *(v79 - 3);
            *(v56 - 4) = v84;
            v86 = *(v79 - 2);
            *(v56 - 3) = v85;
            v87 = *(v79 - 1);
            *(v56 - 2) = v86;
            *(v56 - 1) = v87;
            --v55;
          }
          while ( v55 );
          v88 = v79[1];
          *v56 = *v79;
          v89 = v79[2];
          v56[1] = v88;
          v90 = v79[3];
          v56[2] = v89;
          v56[3] = v90;
          if ( FixedAttributes < 0 )
          {
            v10 = WPP_GLOBAL_Control;
            if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
            {
              v91 = 28;
LABEL_140:
              WPP_SF_Dd(
                v10[3].Buffer,
                v91,
                WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids,
                (unsigned int)FixedAttributes,
                FixedAttributes);
            }
            return (unsigned int)FixedAttributes;
          }
          v12 &= ~0x80u;
        }
      }
      if ( v12 && !RtlAreAllAccessesGranted(*(_DWORD *)(a1 + 148), v12) )
      {
        v54 = WPP_GLOBAL_Control;
        if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) == 0 )
          return 3221225506LL;
        v143 = 29;
LABEL_138:
        WPP_SF_Dd(v54[3].Buffer, v143, WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids, 3221225506LL, -1073741790);
        return 3221225506LL;
      }
      if ( v151 && !SampIsAttributeAccessGranted((struct _RTL_BITMAP *)(a1 + 232), v151) )
      {
        v54 = WPP_GLOBAL_Control;
        if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) == 0 )
          return 3221225506LL;
        v143 = 30;
        goto LABEL_138;
      }
    }
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 144));
    v10 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    {
      v91 = 31;
      goto LABEL_140;
    }
    return (unsigned int)FixedAttributes;
  }
  if ( SampServiceState != 2 )
  {
    v92 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    {
      v93 = 22;
      goto LABEL_116;
    }
    return 3221225692LL;
  }
  if ( (unsigned int)(*(_DWORD *)(a1 + 16) - 2) > 2 )
    goto LABEL_48;
  v19 = 1360LL * *(unsigned int *)(a1 + 200);
  if ( *(_DWORD *)((char *)SampDefinedDomains + v19 + 216) == 1 )
    goto LABEL_48;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control[3].Buffer,
      23,
      WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids,
      3221225693LL,
      -1073741603);
  return 3221225693LL;
}

```

## disassembly

```asm
0x1800096c0  mov     [rsp-8+arg_18], rbx
0x1800096c5  push    rbp
0x1800096c6  push    rsi
0x1800096c7  push    rdi
0x1800096c8  push    r12
0x1800096ca  push    r13
0x1800096cc  push    r14
0x1800096ce  push    r15
0x1800096d0  lea     rbp, [rsp-1D0h]
0x1800096d8  sub     rsp, 2D0h
0x1800096df  mov     rax, cs:__security_cookie
0x1800096e6  xor     rax, rsp
0x1800096e9  mov     [rbp+200h+var_38], rax
0x1800096f0  cmp     cs:?SampServiceState@@3W4_SAMP_SERVICE_STATE@@A, 6; _SAMP_SERVICE_STATE SampServiceState
0x1800096f7  mov     esi, r9d
0x1800096fa  mov     r12, [rbp+200h+arg_20]
0x180009701  mov     r13d, edx
0x180009704  mov     [rsp+300h+var_2A0], r8
0x180009709  mov     rbx, rcx
0x18000970c  jz      loc_180009E74
0x180009712  mov     qword ptr [rsp+300h+Buffer], rcx
0x180009717  lea     rcx, ?SampClientContextLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK SampClientContextLock
0x18000971e  call    cs:__imp_RtlAcquireSRWLockShared
0x180009724  lea     rdx, [rsp+300h+Buffer]; Buffer
0x180009729  lea     rcx, ?SampClientContextTableAVL@@3U_RTL_AVL_TABLE@@A; Table
0x180009730  call    cs:__imp_RtlLookupElementGenericTableAvl
0x180009736  lea     rcx, ?SampClientContextLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK SampClientContextLock
0x18000973d  mov     rdi, rax
0x180009740  call    cs:__imp_RtlReleaseSRWLockShared
0x180009746  mov     rcx, cs:WPP_GLOBAL_Control
0x18000974d  test    dword ptr [rcx+44h], 20000h
0x180009754  jnz     loc_180009E92
0x18000975a  test    rdi, rdi
0x18000975d  jz      loc_180009EBD
0x180009763  xor     edi, edi
0x180009765  cmp     dword ptr [rbx+18h], 0EE77FF88h
0x18000976c  mov     r14d, edi
0x18000976f  jnz     loc_180009EC8
0x180009775  test    dword ptr [rcx+44h], 20000h
0x18000977c  jnz     loc_180009E4B
0x180009782  test    r14d, r14d
0x180009785  js      loc_180009ED3
0x18000978b  cmp     r13d, 8FFFFFFFh
0x180009792  mov     r15d, edi
0x180009795  setz    dl
0x180009798  cmovnz  r15d, r13d
0x18000979c  mov     [rsp+300h+var_2D0], dl
0x1800097a0  cmp     r15d, 0FFFFFFFFh
0x1800097a4  jnz     loc_180009844
0x1800097aa  mov     dl, 1
0x1800097ac  mov     r15d, edi
0x1800097af  mov     [rsp+300h+var_2D0], dl
0x1800097b3  mov     eax, [rbx+10h]
0x1800097b6  mov     [r12], eax
0x1800097ba  cmp     esi, 5
0x1800097bd  jnz     loc_180009865
0x1800097c3  mov     rax, gs:30h
0x1800097cc  mov     rax, [rax+48h]
0x1800097d0  cmp     cs:?SampLock@@3U_RTL_CRITICAL_SECTION@@A.OwningThread, rax; _RTL_CRITICAL_SECTION SampLock ...
0x1800097d7  jnz     loc_18000A21E
0x1800097dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800097e4  test    dword ptr [rcx+44h], 20000h
0x1800097eb  jnz     loc_180009EEA
0x1800097f1  mov     r14d, edi
0x1800097f4  mov     [rsp+300h+var_2A8], rdi
0x1800097f9  mov     [rsp+300h+var_2CF], 1
0x1800097fe  xor     r12b, r12b
0x180009801  mov     [rsp+300h+var_2B8], edi
0x180009805  mov     esi, 2
0x18000980a  mov     [rsp+300h+var_2B4], edi
0x18000980e  cmp     edi, cs:?SampDefinedDomainsCount@@3KA; ulong SampDefinedDomainsCount
0x180009814  jnb     loc_1800098AA
0x18000981a  mov     rdx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x180009821  mov     eax, edi
0x180009823  imul    rcx, rax, 550h
0x18000982a  mov     [rsp+300h+var_2B0], rcx
0x18000982f  mov     rax, [rdx+rcx]
0x180009833  test    [rax+0C0h], sil
0x18000983a  jnz     loc_180009F0A
0x180009840  inc     edi
0x180009842  jmp     short loc_18000980E
0x180009844  test    byte ptr [rbx+15h], 1
0x180009848  jnz     loc_1800097B3
0x18000984e  test    dword ptr [rcx+44h], 20000h
0x180009855  jz      loc_180009E41
0x18000985b  mov     edx, 13h
0x180009860  jmp     loc_18000A2E6
0x180009865  cmp     esi, eax
0x180009867  jz      loc_1800097C3
0x18000986d  mov     rcx, cs:WPP_GLOBAL_Control
0x180009874  test    dword ptr [rcx+44h], 20000h
0x18000987b  jz      short loc_1800098A0
0x18000987d  mov     rcx, [rcx+38h]
0x180009881  lea     r8, WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids
0x180009888  mov     edx, 14h
0x18000988d  mov     dword ptr [rsp+300h+var_2E0], 0C0000024h
0x180009895  mov     r9d, 0C0000024h
0x18000989b  call    WPP_SF_Dd
0x1800098a0  mov     eax, 0C0000024h
0x1800098a5  jmp     loc_180009B0A
0x1800098aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800098b1  test    dword ptr [rcx+44h], 20000h
0x1800098b8  jnz     loc_18000A12E
0x1800098be  test    r14d, r14d
0x1800098c1  js      loc_18000A110
0x1800098c7  mov     eax, [rbx+10h]
0x1800098ca  dec     eax
0x1800098cc  cmp     eax, 3
0x1800098cf  ja      loc_180009A86
0x1800098d5  mov     rax, gs:30h
0x1800098de  mov     rax, [rax+48h]
0x1800098e2  cmp     cs:?SampLock@@3U_RTL_CRITICAL_SECTION@@A.OwningThread, rax; _RTL_CRITICAL_SECTION SampLock ...
0x1800098e9  jnz     loc_18000A170
0x1800098ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800098f6  test    dword ptr [rcx+44h], 20000h
0x1800098fd  jnz     loc_18000A150
0x180009903  mov     cs:?SampTransactionWithinDomainGlobal@@3EA, 0; uchar SampTransactionWithinDomainGlobal
0x18000990a  mov     rax, gs:30h
0x180009913  mov     edi, [rbx+0C8h]
0x180009919  mov     rcx, [rax+48h]
0x18000991d  cmp     cs:?SampLock@@3U_RTL_CRITICAL_SECTION@@A.OwningThread, rcx; _RTL_CRITICAL_SECTION SampLock ...
0x180009924  jnz     loc_18000A1ED
0x18000992a  mov     rcx, cs:WPP_GLOBAL_Control
0x180009931  test    dword ptr [rcx+44h], 20000h
0x180009938  jnz     loc_18000A1CD
0x18000993e  mov     cs:?SampTransactionWithinDomainGlobal@@3EA, 1; uchar SampTransactionWithinDomainGlobal
0x180009945  imul    r8, rdi, 550h
0x18000994c  mov     cs:?SampTransactionDomainIndexGlobal@@3KA, edi; ulong SampTransactionDomainIndexGlobal
0x180009952  lea     rcx, [rsp+300h+var_290]
0x180009957  add     r8, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x18000995e  mov     rdx, rsi
0x180009961  lea     rax, [r8+1F0h]
0x180009968  lea     rcx, [rcx+80h]
0x18000996f  movups  xmm0, xmmword ptr [rax]
0x180009972  movups  xmm1, xmmword ptr [rax+10h]
0x180009976  lea     rax, [rax+80h]
0x18000997d  movups  xmmword ptr [rcx-80h], xmm0
0x180009981  movups  xmm0, xmmword ptr [rax-60h]
0x180009985  movups  xmmword ptr [rcx-70h], xmm1
0x180009989  movups  xmm1, xmmword ptr [rax-50h]
0x18000998d  movups  xmmword ptr [rcx-60h], xmm0
0x180009991  movups  xmm0, xmmword ptr [rax-40h]
0x180009995  movups  xmmword ptr [rcx-50h], xmm1
0x180009999  movups  xmm1, xmmword ptr [rax-30h]
0x18000999d  movups  xmmword ptr [rcx-40h], xmm0
0x1800099a1  movups  xmm0, xmmword ptr [rax-20h]
0x1800099a5  movups  xmmword ptr [rcx-30h], xmm1
0x1800099a9  movups  xmm1, xmmword ptr [rax-10h]
0x1800099ad  movups  xmmword ptr [rcx-20h], xmm0
0x1800099b1  movups  xmmword ptr [rcx-10h], xmm1
0x1800099b5  sub     rdx, 1
0x1800099b9  jnz     short loc_180009968
0x1800099bb  movups  xmm0, xmmword ptr [rax]
0x1800099be  movups  xmm1, xmmword ptr [rax+10h]
0x1800099c2  movups  xmmword ptr [rcx], xmm0
0x1800099c5  movups  xmm0, xmmword ptr [rax+20h]
0x1800099c9  movups  xmmword ptr [rcx+10h], xmm1
0x1800099cd  movups  xmm1, xmmword ptr [rax+30h]
0x1800099d1  movups  xmmword ptr [rcx+20h], xmm0
0x1800099d5  movups  xmm0, xmmword ptr [rax+40h]
0x1800099d9  movups  xmmword ptr [rcx+30h], xmm1
0x1800099dd  movups  xmm1, xmmword ptr [rax+50h]
0x1800099e1  movups  xmmword ptr [rcx+40h], xmm0
0x1800099e5  movups  xmm0, xmmword ptr [rax+60h]
0x1800099e9  lea     rax, [r8+80h]
0x1800099f0  movups  xmmword ptr [rcx+50h], xmm1
0x1800099f4  movups  xmmword ptr [rcx+60h], xmm0
0x1800099f8  lea     rcx, [rsp+300h+var_290]
0x1800099fd  lea     rax, [rax+80h]
0x180009a04  movups  xmm0, xmmword ptr [rcx]
0x180009a07  movups  xmm1, xmmword ptr [rcx+10h]
0x180009a0b  lea     rcx, [rcx+80h]
0x180009a12  movups  xmmword ptr [rax-80h], xmm0
0x180009a16  movups  xmm0, xmmword ptr [rcx-60h]
0x180009a1a  movups  xmmword ptr [rax-70h], xmm1
0x180009a1e  movups  xmm1, xmmword ptr [rcx-50h]
0x180009a22  movups  xmmword ptr [rax-60h], xmm0
0x180009a26  movups  xmm0, xmmword ptr [rcx-40h]
0x180009a2a  movups  xmmword ptr [rax-50h], xmm1
0x180009a2e  movups  xmm1, xmmword ptr [rcx-30h]
0x180009a32  movups  xmmword ptr [rax-40h], xmm0
0x180009a36  movups  xmm0, xmmword ptr [rcx-20h]
0x180009a3a  movups  xmmword ptr [rax-30h], xmm1
0x180009a3e  movups  xmm1, xmmword ptr [rcx-10h]
0x180009a42  movups  xmmword ptr [rax-20h], xmm0
0x180009a46  movups  xmmword ptr [rax-10h], xmm1
0x180009a4a  sub     rsi, 1
0x180009a4e  jnz     short loc_1800099FD
0x180009a50  movups  xmm0, xmmword ptr [rcx]
0x180009a53  movups  xmm1, xmmword ptr [rcx+10h]
0x180009a57  movups  xmmword ptr [rax], xmm0
0x180009a5a  movups  xmm0, xmmword ptr [rcx+20h]
0x180009a5e  movups  xmmword ptr [rax+10h], xmm1
0x180009a62  movups  xmm1, xmmword ptr [rcx+30h]
0x180009a66  movups  xmmword ptr [rax+20h], xmm0
0x180009a6a  movups  xmm0, xmmword ptr [rcx+40h]
0x180009a6e  movups  xmmword ptr [rax+30h], xmm1
0x180009a72  movups  xmm1, xmmword ptr [rcx+50h]
0x180009a76  movups  xmmword ptr [rax+40h], xmm0
0x180009a7a  movups  xmm0, xmmword ptr [rcx+60h]
0x180009a7e  movups  xmmword ptr [rax+50h], xmm1
0x180009a82  movups  xmmword ptr [rax+60h], xmm0
0x180009a86  movzx   edx, [rsp+300h+var_2D0]
0x180009a8b  test    byte ptr [rbx+14h], 20h
0x180009a8f  jz      loc_180009B62
0x180009a95  test    byte ptr [rbx+0C0h], 2
0x180009a9c  jnz     loc_18000A28C
0x180009aa2  test    dl, dl
0x180009aa4  jz      loc_180009DDF
0x180009aaa  test    byte ptr [rbx+0C0h], 2
0x180009ab1  jnz     loc_18000A28C
0x180009ab7  test    byte ptr [rbx+14h], 20h
0x180009abb  jnz     short loc_180009AE7
0x180009abd  cmp     byte ptr [rbx+358h], 0
0x180009ac4  jnz     loc_180009E10
0x180009aca  cmp     dword ptr [rbx+10h], 4
0x180009ace  jz      loc_180009BDD
0x180009ad4  test    r15d, r15d
0x180009ad7  jnz     short loc_180009B34
0x180009ad9  mov     rdx, [rsp+300h+var_2A0]; struct _RTL_BITMAP *
0x180009ade  test    rdx, rdx
0x180009ae1  jnz     loc_18000A4EF
0x180009ae7  test    r14d, r14d
0x180009aea  js      short loc_180009AF3
0x180009aec  lock inc dword ptr [rbx+90h]
0x180009af3  mov     rcx, cs:WPP_GLOBAL_Control
0x180009afa  test    dword ptr [rcx+44h], 20000h
0x180009b01  jnz     loc_18000A53F
0x180009b07  mov     eax, r14d
0x180009b0a  mov     rcx, [rbp+200h+var_38]
0x180009b11  xor     rcx, rsp; StackCookie
0x180009b14  call    __security_check_cookie
0x180009b19  mov     rbx, [rsp+300h+arg_18]
0x180009b21  add     rsp, 2D0h
0x180009b28  pop     r15
0x180009b2a  pop     r14
0x180009b2c  pop     r13
0x180009b2e  pop     r12
0x180009b30  pop     rdi
0x180009b31  pop     rsi
0x180009b32  pop     rbp
0x180009b33  retn
0x180009b34  mov     ecx, [rbx+94h]; GrantedAccess
0x180009b3a  mov     edx, r15d; DesiredAccess
0x180009b3d  call    cs:__imp_RtlAreAllAccessesGranted
0x180009b43  test    al, al
0x180009b45  jnz     short loc_180009AD9
0x180009b47  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b4e  test    dword ptr [rcx+44h], 20000h
0x180009b55  jnz     loc_18000A4E8
0x180009b5b  mov     eax, 0C0000022h
0x180009b60  jmp     short loc_180009B0A
0x180009b62  cmp     cs:?SampServiceState@@3W4_SAMP_SERVICE_STATE@@A, 2; _SAMP_SERVICE_STATE SampServiceState
0x180009b69  jnz     loc_18000A24F
0x180009b6f  mov     eax, [rbx+10h]
0x180009b72  sub     eax, 2
0x180009b75  cmp     eax, 2
0x180009b78  ja      loc_180009A95
0x180009b7e  mov     eax, [rbx+0C8h]
0x180009b84  imul    rcx, rax, 550h
0x180009b8b  mov     rax, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x180009b92  cmp     dword ptr [rcx+rax+0D8h], 1
0x180009b9a  jz      loc_180009A95
0x180009ba0  mov     rcx, cs:WPP_GLOBAL_Control
0x180009ba7  test    dword ptr [rcx+44h], 20000h
0x180009bae  jz      short loc_180009BD3
0x180009bb0  mov     rcx, [rcx+38h]
0x180009bb4  lea     r8, WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids
0x180009bbb  mov     edx, 17h
0x180009bc0  mov     dword ptr [rsp+300h+var_2E0], 0C00000DDh
0x180009bc8  mov     r9d, 0C00000DDh
0x180009bce  call    WPP_SF_Dd
0x180009bd3  mov     eax, 0C00000DDh
0x180009bd8  jmp     loc_180009B0A
0x180009bdd  mov     r12d, 4
0x180009be3  test    r15b, 40h
0x180009be7  jnz     loc_18000A309
0x180009bed  lea     r13, [rbx+360h]
0x180009bf4  cmp     byte ptr [rbx+14h], 0
0x180009bf8  jge     loc_180009AD4
0x180009bfe  test    r15b, r15b
0x180009c01  jns     loc_180009AD4
0x180009c07  cmp     byte ptr [rbx+146h], 0
0x180009c0e  jnz     loc_180009AD4
0x180009c14  xorps   xmm0, xmm0
0x180009c17  lea     rdx, [rbp+200h+BitMapBuffer]; BitMapBuffer
0x180009c1e  mov     r8d, 8Ch; SizeOfBitMap
0x180009c24  lea     rcx, [rsp+300h+Buffer]; BitMapHeader
0x180009c29  movups  [rsp+300h+Buffer], xmm0
0x180009c2e  call    cs:__imp_RtlInitializeBitMap
0x180009c34  lea     rcx, [rsp+300h+Buffer]; BitMapHeader
0x180009c39  call    cs:__imp_RtlClearAllBits
0x180009c3f  mov     rax, r13
0x180009c42  lea     rcx, [rsp+300h+var_290]
0x180009c47  mov     rdx, r12
0x180009c4a  lea     rcx, [rcx+80h]
0x180009c51  movups  xmm0, xmmword ptr [rax]
0x180009c54  movups  xmm1, xmmword ptr [rax+10h]
0x180009c58  lea     rax, [rax+80h]
0x180009c5f  movups  xmmword ptr [rcx-80h], xmm0
  ... truncated ...
```
