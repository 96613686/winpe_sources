# CFirewallManager::CheckAllowedInterfaces(ushort,ushort,ulong,AllowedInterface *)

- ea: `0x1800121b0`
- end: `0x18001319e`
- name: `?CheckAllowedInterfaces@CFirewallManager@@AEAAKGGKPEAUAllowedInterface@@@Z`
- size: `4078`
- prototype: `unsigned int(CFirewallManager *__hidden this, unsigned __int16, unsigned __int16, unsigned int, struct AllowedInterface *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x180011f30`

## callees

- `0x1800121b0`
- `0x1800131a4`
- `0x18001c594`
- `0x1800271fc`
- `0x1800287d0`
- `0x18002911c`
- `0x180029a48`
- `0x180029df0`
- `0x180031018`
- `0x180035260`
- `0x1800352b8`
- `0x1800353e8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180012423`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180012423`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x180012323`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x180012323`
- `NSI!NsiGetParameter` at `0x18001236c`
- `NSI!NsiGetParameter` at `0x180012d60`
- `NSI!NsiGetParameter` at `0x18001236c`
- `NSI!NsiGetParameter` at `0x180012d60`
- `ext-ms-win-firewallapi-webproxy-l1-1-0!FWGetConfig` at `0x1800125ec`
- `ext-ms-win-firewallapi-webproxy-l1-1-0!FWGetConfig` at `0x180012842`
- `ext-ms-win-firewallapi-webproxy-l1-1-0!FWGetConfig` at `0x1800128cb`
- `ext-ms-win-firewallapi-webproxy-l1-1-0!FWGetConfig` at `0x1800125ec`
- `ext-ms-win-firewallapi-webproxy-l1-1-0!FWGetConfig` at `0x180012842`
- `ext-ms-win-firewallapi-webproxy-l1-1-0!FWGetConfig` at `0x1800128cb`
- `ext-ms-win-firewallapi-webproxy-l1-1-0!IsFirewallInCoExistanceMode` at `0x180012278`
- `ext-ms-win-firewallapi-webproxy-l1-1-0!IsFirewallInCoExistanceMode` at `0x180012278`
- `ext-ms-win-firewallapi-webproxy-l1-1-0!FWGetGlobalConfig` at `0x1800122c0`
- `ext-ms-win-firewallapi-webproxy-l1-1-0!FWGetGlobalConfig` at `0x1800122c0`
- `ext-ms-win-firewallapi-webproxy-l1-1-0!FWOpenPolicyStore` at `0x18001256d`
- `ext-ms-win-firewallapi-webproxy-l1-1-0!FWOpenPolicyStore` at `0x18001256d`
- `ext-ms-win-firewallapi-webproxy-l1-1-0!FWQueryFirewallRules` at `0x180012757`
- `ext-ms-win-firewallapi-webproxy-l1-1-0!FWQueryFirewallRules` at `0x180012757`
- `ext-ms-win-firewallapi-webproxy-l1-1-0!FWFreeFirewallRules` at `0x1800124ac`
- `ext-ms-win-firewallapi-webproxy-l1-1-0!FWFreeFirewallRules` at `0x1800124ac`
- `ext-ms-win-firewallapi-webproxy-l1-1-0!FWClosePolicyStore` at `0x180012408`
- `ext-ms-win-firewallapi-webproxy-l1-1-0!FWClosePolicyStore` at `0x180012408`

## pseudocode

```c
__int64 __fastcall CFirewallManager::CheckAllowedInterfaces(
        CFirewallManager *this,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        struct AllowedInterface *a5)
{
  struct AllowedInterface *v5; // rsi
  unsigned int v6; // r14d
  unsigned __int16 *v7; // r15
  __int64 n; // rdx
  __int64 m; // r8
  unsigned int v10; // eax
  unsigned int Parameter; // ebx
  unsigned int v12; // edi
  const GUID *v13; // rsi
  unsigned int v14; // eax
  LPCSTR v15; // rcx
  unsigned int ii; // edx
  __int64 v18; // rax
  int v19; // r15d
  __int64 *v20; // rdi
  CFirewallManager *v21; // rcx
  unsigned int i; // edi
  unsigned int j; // edi
  unsigned int k; // ebx
  unsigned int v25; // eax
  unsigned int SvchostPath; // eax
  unsigned int v27; // eax
  __int16 v28; // ax
  __int64 v29; // r9
  int v30; // r9d
  __int64 v31; // rdx
  __int64 v32; // r9
  int v33; // r11d
  CFirewallManager *v34; // rcx
  __int64 v35; // r9
  __int64 v36; // rax
  char *v37; // rcx
  __int64 v38; // rax
  __int64 v39; // r9
  __int64 v40; // rax
  char *v41; // rcx
  __int64 v42; // rax
  __int64 v43; // rdx
  CFirewallManager *v44; // rcx
  CFirewallManager *v45; // rcx
  __int64 v46; // rcx
  LPCSTR v47; // r10
  __int64 v48; // rbx
  __int64 v49; // rdx
  __int64 v50; // rbx
  struct AllowedInterface *v51; // [rsp+28h] [rbp-100h]
  int v52; // [rsp+A8h] [rbp-80h] BYREF
  unsigned int v53; // [rsp+ACh] [rbp-7Ch] BYREF
  NET_LUID InterfaceLuid; // [rsp+B0h] [rbp-78h] BYREF
  int v55; // [rsp+B8h] [rbp-70h] BYREF
  struct AllowedInterface *v56; // [rsp+C0h] [rbp-68h]
  unsigned __int16 *v57; // [rsp+C8h] [rbp-60h] BYREF
  __int64 v58; // [rsp+D0h] [rbp-58h] BYREF
  unsigned int v59; // [rsp+D8h] [rbp-50h]
  __int64 v60; // [rsp+E0h] [rbp-48h]
  __int64 *v61; // [rsp+E8h] [rbp-40h] BYREF
  int v62; // [rsp+F0h] [rbp-38h] BYREF
  int v63; // [rsp+F4h] [rbp-34h] BYREF
  __int64 *v64; // [rsp+F8h] [rbp-30h]
  char *v65; // [rsp+100h] [rbp-28h]
  char *v66; // [rsp+108h] [rbp-20h]
  _DWORD v67[2]; // [rsp+110h] [rbp-18h] BYREF
  _QWORD *v68; // [rsp+118h] [rbp-10h]
  __int64 v69; // [rsp+120h] [rbp-8h]
  unsigned __int16 *v70; // [rsp+128h] [rbp+0h]
  _QWORD v71[3]; // [rsp+130h] [rbp+8h] BYREF
  _BYTE v72[16]; // [rsp+148h] [rbp+20h] BYREF
  int v73; // [rsp+158h] [rbp+30h]
  __int64 v74; // [rsp+238h] [rbp+110h] BYREF
  int v75; // [rsp+240h] [rbp+118h]
  unsigned int v76; // [rsp+248h] [rbp+120h]
  __int64 v77; // [rsp+250h] [rbp+128h]
  int v78; // [rsp+258h] [rbp+130h]
  int v79; // [rsp+260h] [rbp+138h]
  __int64 v80; // [rsp+268h] [rbp+140h]
  int v81; // [rsp+270h] [rbp+148h]
  __int16 v82; // [rsp+278h] [rbp+150h]
  __int64 v83; // [rsp+280h] [rbp+158h]
  int v84; // [rsp+288h] [rbp+160h]
  __int16 v85; // [rsp+290h] [rbp+168h]
  __int64 v86; // [rsp+298h] [rbp+170h]
  int v87; // [rsp+2A0h] [rbp+178h]
  int v88; // [rsp+2A8h] [rbp+180h]
  __int64 v89; // [rsp+2B0h] [rbp+188h]
  int v90; // [rsp+2B8h] [rbp+190h]
  const wchar_t *v91; // [rsp+2C0h] [rbp+198h]
  __int64 v92; // [rsp+2C8h] [rbp+1A0h]
  int v93; // [rsp+2D0h] [rbp+1A8h]
  unsigned __int16 *v94; // [rsp+2D8h] [rbp+1B0h]
  __int64 v95; // [rsp+2E0h] [rbp+1B8h]
  int v96; // [rsp+2E8h] [rbp+1C0h]
  const wchar_t *v97; // [rsp+2F0h] [rbp+1C8h]

  v5 = a5;
  v71[1] = &v74;
  v59 = a4;
  v68 = v71;
  v56 = a5;
  v6 = a4;
  v58 = 0;
  v7 = 0;
  v63 = 0;
  v61 = 0;
  v57 = 0;
  v53 = 0;
  v62 = 4;
  v55 = 0;
  v71[0] = 8;
  v67[0] = 522;
  v67[1] = 1;
  v69 = 0x10000;
  if ( !a5 )
    return 87;
  if ( !(unsigned __int8)IsFWIndicatePortInUsePresent(this)
    || (unsigned int)IsFirewallInCoExistanceMode(&v55, 2)
    || v55 == 1 )
  {
    Parameter = 0;
    v55 = 1;
    goto LABEL_22;
  }
  v10 = FWGetGlobalConfig(545, 0, 5, 2, 0, &v53, &v62);
  Parameter = v10;
  if ( v10 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      goto LABEL_23;
    v31 = 23;
    v32 = v10;
    goto LABEL_136;
  }
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_db283a32a0f73fa63383008e81c323d4_Traceguids, v53);
  Parameter = 0;
  v12 = 0;
  while ( v12 < v6 )
  {
    memset_0(v72, 0, 0xF0u);
    InterfaceLuid.Value = 0;
    v13 = (const GUID *)((char *)v5 + 28 * v12);
    v14 = ConvertInterfaceGuidToLuid(v13, &InterfaceLuid);
    Parameter = v14;
    if ( v14 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
      {
        v43 = 10;
LABEL_146:
        WPP_SF_d(*((_QWORD *)v15 + 2), v43, WPP_db283a32a0f73fa63383008e81c323d4_Traceguids, v14);
        v15 = WPP_GLOBAL_Control;
      }
LABEL_20:
      v5 = v56;
LABEL_89:
      if ( v15 == (LPCSTR)&WPP_GLOBAL_Control || (*((_DWORD *)v15 + 7) & 0x200) == 0 )
        goto LABEL_23;
      v31 = 25;
      v32 = Parameter;
      goto LABEL_136;
    }
    Parameter = NsiGetParameter(1, &NPI_MS_IPV4_MODULEID, 7, &InterfaceLuid, 8, 0, v72, 240, 0);
    if ( Parameter )
    {
      if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_db283a32a0f73fa63383008e81c323d4_Traceguids, Parameter);
      v14 = NsiGetParameter(1, &NPI_MS_IPV6_MODULEID, 7, &InterfaceLuid, 8, 0, v72, 240, 0);
      Parameter = v14;
      if ( v14 )
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
        {
          v43 = 12;
          goto LABEL_146;
        }
        goto LABEL_20;
      }
    }
    if ( v73 == 2 )
    {
      v13[1].Data1 = 1;
      ++v12;
      v5 = v56;
    }
    else
    {
      if ( v73 == 1 )
        v13[1].Data1 = 2;
      else
        v13[1].Data1 = 4;
      v5 = v56;
      ++v12;
    }
  }
  if ( Parameter )
  {
    v15 = WPP_GLOBAL_Control;
    goto LABEL_89;
  }
  Parameter = FWOpenPolicyStore(545, 0, 5, 1, 0, &v58);
  if ( Parameter )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      goto LABEL_23;
    v31 = 26;
    v32 = Parameter;
LABEL_136:
    WPP_SF_d(*((_QWORD *)v15 + 2), v31, WPP_db283a32a0f73fa63383008e81c323d4_Traceguids, v32);
    goto LABEL_22;
  }
  for ( i = 1; i < 5; i *= 2 )
  {
    v52 = 0;
    LODWORD(InterfaceLuid.Value) = 4;
    if ( (i & v53) != 0 )
    {
      Parameter = FWGetConfig(v58, 1, i, 0, &v52, &InterfaceLuid);
      if ( Parameter )
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
          goto LABEL_23;
        v31 = 27;
        v32 = Parameter;
        goto LABEL_136;
      }
      if ( !v52 )
      {
        v34 = (CFirewallManager *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_db283a32a0f73fa63383008e81c323d4_Traceguids);
        CFirewallManager::SetAllowedInterfacesByProfile(v34, 1, i, v6, v5);
        v53 &= ~i;
      }
    }
  }
  if ( !v53 )
  {
LABEL_22:
    v15 = WPP_GLOBAL_Control;
    goto LABEL_23;
  }
  for ( j = 1; ; j *= 2 )
  {
    if ( j >= 5 )
    {
      if ( !v53 )
        goto LABEL_22;
      for ( k = 1; k < 5; k *= 2 )
      {
        v52 = 0;
        LODWORD(InterfaceLuid.Value) = 4;
        if ( (k & v53) != 0 )
        {
          v25 = FWGetConfig(v58, 17, k, 0, &v52, &InterfaceLuid);
          if ( v25 )
          {
            v21 = (CFirewallManager *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_db283a32a0f73fa63383008e81c323d4_Traceguids, v25);
          }
          else if ( !v52 )
          {
            v45 = (CFirewallManager *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_db283a32a0f73fa63383008e81c323d4_Traceguids);
            CFirewallManager::SetAllowedInterfacesByProfile(v45, 1, k, v6, v5);
          }
        }
      }
      SvchostPath = CFirewallManager::GetSvchostPath(v21, &v57);
      Parameter = SvchostPath;
      if ( SvchostPath )
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
        {
          v7 = v57;
        }
        else
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            33,
            WPP_db283a32a0f73fa63383008e81c323d4_Traceguids,
            SvchostPath);
          v15 = WPP_GLOBAL_Control;
          v7 = v57;
        }
        goto LABEL_23;
      }
      v7 = v57;
      v76 = v53;
      v85 = 1900;
      v91 = L"SSDPSRV";
      v97 = L"S-1-0-0";
      v74 = 0;
      v75 = 3;
      v77 = 1;
      v78 = 3;
      v79 = 196608;
      v80 = 5;
      v81 = 2;
      v82 = 17;
      v83 = 6;
      v84 = 2;
      v86 = 10;
      v87 = 3;
      v88 = 1;
      v89 = 9;
      v90 = 5;
      v92 = 4;
      v93 = 5;
      v70 = v57;
      v94 = v57;
      v95 = 12;
      v96 = 5;
      if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_db283a32a0f73fa63383008e81c323d4_Traceguids);
      v27 = FWQueryFirewallRules(v58, v67, 103, &v63, &v61);
      LODWORD(v57) = v27;
      Parameter = v27;
      if ( v27 )
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_db283a32a0f73fa63383008e81c323d4_Traceguids, v27);
          v15 = WPP_GLOBAL_Control;
        }
        goto LABEL_23;
      }
      if ( !v61 )
      {
        v47 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 2) == 0 )
        {
LABEL_72:
          v20 = v61;
          v64 = v61;
          if ( v61 )
          {
            do
            {
              v28 = *((_WORD *)v20 + 146);
              if ( (v28 & 1) != 0 )
              {
                if ( v47 != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)v47 + 7) & 0x200) != 0 )
                {
                  WPP_SF_SSDdd(
                    *((_QWORD *)v47 + 2),
                    n,
                    m,
                    v20[3],
                    v20[4],
                    v28,
                    *((_DWORD *)v20 + 72),
                    *((_DWORD *)v20 + 10));
                  v47 = WPP_GLOBAL_Control;
                }
                v29 = *((unsigned int *)v20 + 72);
                if ( (_DWORD)v29 == 3 )
                {
                  n = v20[45];
                  if ( n )
                  {
                    v30 = 0;
                    for ( m = 0; (unsigned int)m < *(_DWORD *)(n + 8); m = (unsigned int)(m + 1) )
                    {
                      v46 = (unsigned int)m;
                      v33 = *(_DWORD *)(*(_QWORD *)(n + 16) + 4LL * (unsigned int)m);
                      if ( v33 == 7 )
                        goto LABEL_179;
                      if ( v33 == 1 )
                        v30 = 1;
                    }
                    if ( v30 )
                    {
                      if ( v47 != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)v47 + 7) & 0x200) != 0 )
                      {
                        WPP_SF_(*((_QWORD *)v47 + 2), 20, WPP_db283a32a0f73fa63383008e81c323d4_Traceguids);
                        v47 = WPP_GLOBAL_Control;
                      }
                      if ( *((_DWORD *)v20 + 62) )
                      {
                        LODWORD(v46) = 0;
                        LODWORD(InterfaceLuid.Value) = 0;
                        do
                        {
                          n = 0;
                          v52 = 0;
                          if ( v6 )
                          {
                            m = 0;
                            v48 = 16LL * (unsigned int)v46;
                            v60 = 0;
                            do
                            {
                              v35 = v48 + v20[32];
                              v36 = *(_QWORD *)v35;
                              v37 = (char *)v5 + 28 * m;
                              v65 = (char *)v35;
                              v66 = v37;
                              v38 = v36 - *(_QWORD *)v37;
                              if ( !v38 )
                                v38 = *(_QWORD *)(v35 + 8) - *((_QWORD *)v37 + 1);
                              if ( !v38 && (*((_DWORD *)v37 + 4) & (_DWORD)v20[5]) != 0 )
                              {
                                if ( v47 != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)v47 + 7) & 0x200) != 0 )
                                {
                                  WPP_SF_DDDDDDDDDDDDDDDD(
                                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                                    39,
                                    *(unsigned __int8 *)(v35 + 13),
                                    *(unsigned __int8 *)(v35 + 3),
                                    v65[2],
                                    v65[1],
                                    *v65,
                                    v65[5],
                                    *(_BYTE *)(v35 + 4),
                                    *(_BYTE *)(v35 + 7),
                                    *(_BYTE *)(v35 + 6),
                                    *(_BYTE *)(v35 + 8),
                                    *(_BYTE *)(v35 + 9),
                                    *(_BYTE *)(v35 + 10),
                                    *(_BYTE *)(v35 + 11),
                                    *(_BYTE *)(v35 + 12),
                                    *(_BYTE *)(v35 + 13),
                                    *(_BYTE *)(v35 + 14),
                                    *(_BYTE *)(v35 + 15));
                                  v37 = v66;
                                  LODWORD(n) = v52;
                                  m = v60;
                                  v5 = v56;
                                  v6 = v59;
                                  v20 = v64;
                                }
                                *((_DWORD *)v37 + 5) = 1;
                                v47 = WPP_GLOBAL_Control;
                              }
                              n = (unsigned int)(n + 1);
                              ++m;
                              v52 = n;
                              v60 = m;
                            }
                            while ( (unsigned int)n < v6 );
                            LODWORD(v46) = InterfaceLuid.Value;
                          }
                          v46 = (unsigned int)(v46 + 1);
                          LODWORD(InterfaceLuid.Value) = v46;
                        }
                        while ( (unsigned int)v46 < *((_DWORD *)v20 + 62) );
                      }
                      else
                      {
                        if ( v47 != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)v47 + 7) & 0x200) != 0 )
                        {
                          WPP_SF_(*((_QWORD *)v47 + 2), 38, WPP_db283a32a0f73fa63383008e81c323d4_Traceguids);
                          v47 = WPP_GLOBAL_Control;
                        }
                        v19 = *((_DWORD *)v20 + 10);
                        if ( v47 != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)v47 + 7) & 0x200) != 0 )
                          WPP_SF_Dd(
                            *((_QWORD *)v47 + 2),
                            13,
                            WPP_db283a32a0f73fa63383008e81c323d4_Traceguids,
                            1,
                            *((_DWORD *)v20 + 10));
                        for ( n = 0; (unsigned int)n < v6; n = (unsigned int)(n + 1) )
                        {
                          v46 = 28LL * (unsigned int)n;
                          if ( (v19 & *(_DWORD *)((_BYTE *)v5 + v46 + 16)) != 0 )
                            *(_DWORD *)((char *)v5 + v46 + 20) = 1;
                        }
                      }
                      goto LABEL_49;
                    }
LABEL_179:
                    if ( v47 != (LPCSTR)&WPP_GLOBAL_Control && (v47[28] & 2) != 0 )
                    {
                      v49 = 21;
                      goto LABEL_182;
                    }
                  }
                  else if ( v47 != (LPCSTR)&WPP_GLOBAL_Control && (v47[28] & 1) != 0 )
                  {
                    v49 = 22;
LABEL_182:
                    WPP_SF_(*((_QWORD *)v47 + 2), v49, WPP_db283a32a0f73fa63383008e81c323d4_Traceguids);
                  }
                }
                else if ( (_DWORD)v29 == 2 )
                {
                  if ( *((_DWORD *)v20 + 62) )
                  {
                    LODWORD(v46) = 0;
                    v52 = 0;
                    do
                    {
                      n = 0;
                      LODWORD(InterfaceLuid.Value) = 0;
                      if ( v6 )
                      {
                        m = 0;
                        v50 = 16LL * (unsigned int)v46;
                        v60 = 0;
                        do
                        {
                          v39 = v50 + v20[32];
                          v40 = *(_QWORD *)v39;
                          v41 = (char *)v5 + 28 * m;
                          v66 = (char *)v39;
                          v65 = v41;
                          v42 = v40 - *(_QWORD *)v41;
                          if ( !v42 )
                            v42 = *(_QWORD *)(v39 + 8) - *((_QWORD *)v41 + 1);
                          if ( !v42 && (*((_DWORD *)v41 + 4) & (_DWORD)v20[5]) != 0 )
                          {
                            if ( v47 != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)v47 + 7) & 0x200) != 0 )
                            {
                              WPP_SF_DDDDDDDDDDDDDDDD(
                                *((_QWORD *)WPP_GLOBAL_Control + 2),
                                41,
                                *(unsigned __int8 *)(v39 + 13),
                                *(unsigned __int8 *)(v39 + 3),
                                v66[2],
                                v66[1],
                                *v66,
                                v66[5],
                                *(_BYTE *)(v39 + 4),
                                *(_BYTE *)(v39 + 7),
                                *(_BYTE *)(v39 + 6),
                                *(_BYTE *)(v39 + 8),
                                *(_BYTE *)(v39 + 9),
                                *(_BYTE *)(v39 + 10),
                                *(_BYTE *)(v39 + 11),
                                *(_BYTE *)(v39 + 12),
                                *(_BYTE *)(v39 + 13),
                                *(_BYTE *)(v39 + 14),
                                *(_BYTE *)(v39 + 15));
                              v41 = v65;
                              LODWORD(n) = InterfaceLuid.Value;
                              m = v60;
                              v5 = v56;
                              v6 = v59;
                              v20 = v64;
                            }
                            *((_DWORD *)v41 + 6) = 1;
                            v47 = WPP_GLOBAL_Control;
                          }
                          n = (unsigned int)(n + 1);
                          ++m;
                          LODWORD(InterfaceLuid.Value) = n;
                          v60 = m;
                        }
                        while ( (unsigned int)n < v6 );
                        LODWORD(v46) = v52;
                      }
                      v46 = (unsigned int)(v46 + 1);
                      v52 = v46;
                    }
                    while ( (unsigned int)v46 < *((_DWORD *)v20 + 62) );
                  }
                  else
                  {
                    if ( v47 != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)v47 + 7) & 0x200) != 0 )
                      WPP_SF_(*((_QWORD *)v47 + 2), 40, WPP_db283a32a0f73fa63383008e81c323d4_Traceguids);
                    CFirewallManager::SetAllowedInterfacesByProfile(
                      (CFirewallManager *)v46,
                      0,
                      *((_DWORD *)v20 + 10),
                      v6,
                      v5);
                  }
                }
                else if ( v47 != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)v47 + 7) & 0x200) != 0 )
                {
                  WPP_SF_d(*((_QWORD *)v47 + 2), 42, WPP_db283a32a0f73fa63383008e81c323d4_Traceguids, v29);
                }
              }
LABEL_49:
              v20 = (__int64 *)*v20;
              v47 = WPP_GLOBAL_Control;
              v64 = v20;
            }
            while ( v20 );
            Parameter = (unsigned int)v57;
            v7 = v70;
          }
          goto LABEL_22;
        }
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_db283a32a0f73fa63383008e81c323d4_Traceguids);
      }
      v47 = WPP_GLOBAL_Control;
      goto LABEL_72;
    }
    v52 = 0;
    LODWORD(InterfaceLuid.Value) = 4;
    if ( (j & v53) != 0 )
      break;
LABEL_95:
    ;
  }
  Parameter = FWGetConfig(v58, 3, j, 0, &v52, &InterfaceLuid);
  if ( !Parameter )
  {
    if ( v52 == 1 )
    {
      v44 = (CFirewallManager *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_db283a32a0f73fa63383008e81c323d4_Traceguids);
      CFirewallManager::SetAllowedInterfacesByProfile(v44, 0, j, v6, v5);
      v53 &= ~j;
    }
    goto LABEL_95;
  }
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
  {
    v31 = 29;
    v32 = Parameter;
    goto LABEL_136;
  }
LABEL_23:
  if ( v61 )
  {
    FWFreeFirewallRules(v61);
    v15 = WPP_GLOBAL_Control;
  }
  if ( v58 )
  {
    FWClosePolicyStore(v58);
    v15 = WPP_GLOBAL_Control;
  }
  if ( v7 )
  {
    free(v7);
    v15 = WPP_GLOBAL_Control;
  }
  if ( Parameter || v55 == 1 )
  {
    if ( v15 != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)v15 + 7) & 0x200) != 0 )
    {
      LODWORD(v51) = v55;
      WPP_SF_DD(*((_QWORD *)v15 + 2), n, m, Parameter, v51);
    }
    for ( ii = 0; ii < v6; *((_DWORD *)v5 + 7 * v18 + 5) = 1 )
      v18 = ii++;
  }
  return Parameter;
}

```

## disassembly

```asm
0x1800121b0  mov     r11, rsp
0x1800121b3  mov     [r11+18h], rsi
0x1800121b7  push    rbp
0x1800121b8  push    r12
0x1800121ba  push    r13
0x1800121bc  push    r14
0x1800121be  push    r15
0x1800121c0  lea     rbp, [r11-208h]
0x1800121c7  sub     rsp, 300h
0x1800121ce  mov     rax, cs:__security_cookie
0x1800121d5  xor     rax, rsp
0x1800121d8  mov     [rbp+200h+var_30], rax
0x1800121df  mov     rsi, [rbp+200h+arg_20]
0x1800121e6  lea     rax, [rbp+200h+var_F0]
0x1800121ed  xor     r12d, r12d
0x1800121f0  mov     [rbp+200h+var_1F0], rax
0x1800121f4  mov     [rbp+200h+var_250], r9d
0x1800121f8  lea     rax, [rbp+200h+var_1F8]
0x1800121fc  mov     [rbp+200h+var_210], rax
0x180012200  mov     r13d, 1
0x180012206  mov     [rbp+200h+var_268], rsi
0x18001220a  mov     r14d, r9d
0x18001220d  mov     [rbp+200h+var_258], r12
0x180012211  mov     r15d, r12d
0x180012214  mov     [rbp+200h+var_234], r12d
0x180012218  mov     [rbp+200h+var_240], r12
0x18001221c  mov     [rbp+200h+var_260], r12
0x180012220  mov     [rbp+200h+var_27C], r12d
0x180012224  mov     [rbp+200h+var_238], 4
0x18001222b  mov     [rbp+200h+var_270], r12d
0x18001222f  mov     [rbp+200h+var_1F8], 8
0x180012237  mov     [rbp+200h+var_218], 20Ah
0x18001223e  mov     [rbp+200h+var_214], r13d
0x180012242  mov     [rbp+200h+var_208], 10000h
0x18001224a  test    rsi, rsi
0x18001224d  jz      loc_180012C89
0x180012253  mov     [r11+8], rbx
0x180012257  mov     [r11+10h], rdi
0x18001225b  call    IsFWIndicatePortInUsePresent
0x180012260  lea     rdi, WPP_GLOBAL_Control
0x180012267  test    al, al
0x180012269  jz      loc_1800123DA
0x18001226f  mov     edx, 2
0x180012274  lea     rcx, [rbp+200h+var_270]
0x180012278  call    cs:__imp_IsFirewallInCoExistanceMode
0x18001227f  nop     dword ptr [rax+rax+00h]
0x180012284  test    eax, eax
0x180012286  jnz     loc_1800123DA
0x18001228c  cmp     [rbp+200h+var_270], r13d
0x180012290  jz      loc_1800123DA
0x180012296  lea     rax, [rbp+200h+var_238]
0x18001229a  mov     ecx, 221h
0x18001229f  mov     qword ptr [rsp+320h+var_2F0], rax
0x1800122a4  xor     edx, edx
0x1800122a6  lea     rax, [rbp+200h+var_27C]
0x1800122aa  mov     r9d, 2
0x1800122b0  mov     [rsp+320h+var_2F8], rax
0x1800122b5  mov     r8d, 5
0x1800122bb  mov     dword ptr [rsp+320h+var_300], r12d
0x1800122c0  call    cs:__imp_FWGetGlobalConfig
0x1800122c7  nop     dword ptr [rax+rax+00h]
0x1800122cc  mov     ebx, eax
0x1800122ce  test    eax, eax
0x1800122d0  jnz     loc_180012C93
0x1800122d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800122dd  cmp     rcx, rdi
0x1800122e0  jz      short loc_1800122EF
0x1800122e2  test    dword ptr [rcx+1Ch], 200h
0x1800122e9  jnz     loc_180012CD7
0x1800122ef  mov     ebx, r12d
0x1800122f2  mov     edi, r12d
0x1800122f5  cmp     edi, r14d
0x1800122f8  jnb     loc_180012547
0x1800122fe  xor     edx, edx; Val
0x180012300  lea     rcx, [rbp+200h+var_1E0]; void *
0x180012304  mov     r8d, 0F0h; Size
0x18001230a  call    memset_0
0x18001230f  mov     eax, edi
0x180012311  lea     rdx, [rbp+200h+InterfaceLuid]; InterfaceLuid
0x180012315  imul    rcx, rax, 1Ch
0x180012319  mov     qword ptr [rbp+200h+InterfaceLuid], r12
0x18001231d  add     rsi, rcx
0x180012320  mov     rcx, rsi; InterfaceGuid
0x180012323  call    cs:__imp_ConvertInterfaceGuidToLuid
0x18001232a  nop     dword ptr [rax+rax+00h]
0x18001232f  mov     ebx, eax
0x180012331  test    eax, eax
0x180012333  jnz     short loc_1800123B4
0x180012335  mov     [rsp+320h+var_2E0], r12d
0x18001233a  lea     rax, [rbp+200h+var_1E0]
0x18001233e  mov     [rsp+320h+var_2E8], 0F0h
0x180012346  lea     r9, [rbp+200h+InterfaceLuid]
0x18001234a  mov     qword ptr [rsp+320h+var_2F0], rax
0x18001234f  lea     rdx, NPI_MS_IPV4_MODULEID
0x180012356  mov     dword ptr [rsp+320h+var_2F8], r12d
0x18001235b  mov     r8d, 7
0x180012361  mov     ecx, r13d
0x180012364  mov     dword ptr [rsp+320h+var_300], 8
0x18001236c  call    cs:__imp_NsiGetParameter
0x180012373  nop     dword ptr [rax+rax+00h]
0x180012378  mov     ebx, eax
0x18001237a  test    eax, eax
0x18001237c  jnz     loc_180012CF5
0x180012382  mov     eax, [rbp+200h+var_1D0]
0x180012385  cmp     eax, 2
0x180012388  jz      short loc_1800123A5
0x18001238a  cmp     eax, r13d
0x18001238d  jnz     loc_180012D9E
0x180012393  mov     dword ptr [rsi+10h], 2
0x18001239a  mov     rsi, [rbp+200h+var_268]
0x18001239e  inc     edi
0x1800123a0  jmp     loc_1800122F5
0x1800123a5  mov     [rsi+10h], r13d
0x1800123a9  inc     edi
0x1800123ab  mov     rsi, [rbp+200h+var_268]
0x1800123af  jmp     loc_1800122F5
0x1800123b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800123bb  lea     rdi, WPP_GLOBAL_Control
0x1800123c2  cmp     rcx, rdi
0x1800123c5  jz      short loc_1800123D1
0x1800123c7  test    [rcx+1Ch], r13b
0x1800123cb  jnz     loc_180012DAA
0x1800123d1  mov     rsi, [rbp+200h+var_268]
0x1800123d5  jmp     loc_180012877
0x1800123da  mov     ebx, r12d
0x1800123dd  mov     [rbp+200h+var_270], r13d
0x1800123e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800123e8  lea     rdi, WPP_GLOBAL_Control
0x1800123ef  mov     rax, [rbp+200h+var_240]
0x1800123f3  test    rax, rax
0x1800123f6  jnz     loc_1800124A9
0x1800123fc  mov     rax, [rbp+200h+var_258]
0x180012400  test    rax, rax
0x180012403  jz      short loc_18001241B
0x180012405  mov     rcx, rax
0x180012408  call    cs:__imp_FWClosePolicyStore
0x18001240f  nop     dword ptr [rax+rax+00h]
0x180012414  mov     rcx, cs:WPP_GLOBAL_Control
0x18001241b  test    r15, r15
0x18001241e  jz      short loc_180012436
0x180012420  mov     rcx, r15; Block
0x180012423  call    cs:__imp_free
0x18001242a  nop     dword ptr [rax+rax+00h]
0x18001242f  mov     rcx, cs:WPP_GLOBAL_Control
0x180012436  test    ebx, ebx
0x180012438  jnz     short loc_18001247B
0x18001243a  cmp     [rbp+200h+var_270], 1
0x18001243e  jz      short loc_18001247B
0x180012440  mov     rdi, [rsp+320h+arg_8]
0x180012448  mov     eax, ebx
0x18001244a  mov     rbx, [rsp+320h+arg_0]
0x180012452  mov     rcx, [rbp+200h+var_30]
0x180012459  xor     rcx, rsp; StackCookie
0x18001245c  call    __security_check_cookie
0x180012461  mov     rsi, [rsp+320h+arg_10]
0x180012469  add     rsp, 300h
0x180012470  pop     r15
0x180012472  pop     r14
0x180012474  pop     r13
0x180012476  pop     r12
0x180012478  pop     rbp
0x180012479  retn
0x18001247b  cmp     rcx, rdi
0x18001247e  jz      short loc_18001248D
0x180012480  test    dword ptr [rcx+1Ch], 200h
0x180012487  jnz     loc_180013186
0x18001248d  mov     edx, r12d
0x180012490  test    r14d, r14d
0x180012493  jz      short loc_180012440
0x180012495  mov     eax, edx
0x180012497  inc     edx
0x180012499  imul    rcx, rax, 1Ch
0x18001249d  mov     [rcx+rsi+14h], r13d
0x1800124a2  cmp     edx, r14d
0x1800124a5  jb      short loc_180012495
0x1800124a7  jmp     short loc_180012440
0x1800124a9  mov     rcx, rax
0x1800124ac  call    cs:__imp_FWFreeFirewallRules
0x1800124b3  nop     dword ptr [rax+rax+00h]
0x1800124b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800124bf  jmp     loc_1800123FC
0x1800124c4  test    dword ptr [r10+1Ch], 200h
0x1800124cc  jnz     loc_180012FE9
0x1800124d2  mov     eax, [rdi+0F8h]
0x1800124d8  test    eax, eax
0x1800124da  jnz     loc_180013069
0x1800124e0  cmp     r10, rbx
0x1800124e3  jnz     loc_18001300A
0x1800124e9  mov     r15d, [rdi+28h]
0x1800124ed  cmp     r10, rbx
0x1800124f0  jnz     loc_180013039
0x1800124f6  mov     edx, r12d
0x1800124f9  test    r14d, r14d
0x1800124fc  jz      short loc_180012524
0x1800124fe  xchg    ax, ax
0x180012500  mov     eax, edx
0x180012502  imul    rcx, rax, 1Ch
0x180012506  test    [rcx+rsi+10h], r15d
0x18001250b  jz      short loc_180012512
0x18001250d  mov     [rcx+rsi+14h], r13d
0x180012512  inc     edx
0x180012514  cmp     edx, r14d
0x180012517  jb      short loc_180012500
0x180012519  jmp     short loc_180012524
0x18001251b  cmp     r10, rbx
0x18001251e  jnz     loc_1800130CD
0x180012524  mov     rdi, [rdi]
0x180012527  mov     r10, cs:WPP_GLOBAL_Control
0x18001252e  mov     [rbp+200h+var_230], rdi
0x180012532  test    rdi, rdi
0x180012535  jnz     loc_1800127A2
0x18001253b  mov     ebx, dword ptr [rbp+200h+var_260]
0x18001253e  mov     r15, [rbp+200h+var_200]
0x180012542  jmp     loc_1800123E1
0x180012547  test    ebx, ebx
0x180012549  jnz     loc_180012869
0x18001254f  lea     rax, [rbp+200h+var_258]
0x180012553  mov     ecx, 221h
0x180012558  mov     [rsp+320h+var_2F8], rax
0x18001255d  mov     r9d, r13d
0x180012560  xor     edx, edx
0x180012562  mov     dword ptr [rsp+320h+var_300], r12d
0x180012567  mov     r8d, 5
0x18001256d  call    cs:__imp_FWOpenPolicyStore
0x180012574  nop     dword ptr [rax+rax+00h]
0x180012579  mov     ebx, eax
0x18001257b  test    eax, eax
0x18001257d  jnz     loc_180012958
0x180012583  mov     edi, r13d
0x180012586  cmp     edi, 5
0x180012589  jb      loc_180012813
0x18001258f  cmp     [rbp+200h+var_27C], r12d
0x180012593  jz      loc_1800123E1
0x180012599  mov     edi, r13d
0x18001259c  cmp     edi, 5
0x18001259f  jb      loc_18001289A
0x1800125a5  cmp     [rbp+200h+var_27C], r12d
0x1800125a9  jz      loc_1800123E1
0x1800125af  mov     ebx, r13d
0x1800125b2  lea     r15, WPP_GLOBAL_Control
0x1800125b9  mov     edi, 11h
0x1800125be  mov     [rbp+200h+var_280], r12d
0x1800125c2  mov     dword ptr [rbp+200h+InterfaceLuid], 4
0x1800125c9  test    [rbp+200h+var_27C], ebx
0x1800125cc  jz      short loc_18001260A
0x1800125ce  mov     rcx, [rbp+200h+var_258]
0x1800125d2  lea     rax, [rbp+200h+InterfaceLuid]
0x1800125d6  mov     [rsp+320h+var_2F8], rax
0x1800125db  xor     r9d, r9d
0x1800125de  lea     rax, [rbp+200h+var_280]
0x1800125e2  mov     r8d, ebx
0x1800125e5  mov     edx, edi
0x1800125e7  mov     [rsp+320h+var_300], rax
0x1800125ec  call    cs:__imp_FWGetConfig
0x1800125f3  nop     dword ptr [rax+rax+00h]
0x1800125f8  test    eax, eax
0x1800125fa  jnz     loc_180012E9E
0x180012600  cmp     [rbp+200h+var_280], r12d
0x180012604  jz      loc_180012ED8
0x18001260a  add     ebx, ebx
0x18001260c  cmp     ebx, 5
0x18001260f  jb      short loc_1800125BE
0x180012611  lea     rdx, [rbp+200h+var_260]; unsigned __int16 **
0x180012615  call    ?GetSvchostPath@CFirewallManager@@AEAAKPEAPEAG@Z; CFirewallManager::GetSvchostPath(ushort * *)
0x18001261a  mov     ebx, eax
0x18001261c  test    eax, eax
0x18001261e  jnz     loc_180012F28
0x180012624  mov     eax, [rbp+200h+var_27C]
0x180012627  mov     r15, [rbp+200h+var_260]
0x18001262b  mov     [rbp+200h+var_E0], eax
0x180012631  mov     eax, 76Ch
0x180012636  mov     [rbp+200h+var_98], ax
0x18001263d  lea     rax, aSsdpsrv_0; "SSDPSRV"
0x180012644  mov     [rbp+200h+var_68], rax
0x18001264b  lea     rax, aS100; "S-1-0-0"
0x180012652  mov     [rbp+200h+var_38], rax
0x180012659  mov     [rbp+200h+var_F0], r12
0x180012660  mov     [rbp+200h+var_E8], 3
0x18001266a  mov     [rbp+200h+var_D8], r13
0x180012671  mov     [rbp+200h+var_D0], 3
0x18001267b  mov     [rbp+200h+var_C8], 30000h
0x180012685  mov     [rbp+200h+var_C0], 5
0x180012690  mov     [rbp+200h+var_B8], 2
0x18001269a  mov     [rbp+200h+var_B0], di
0x1800126a1  mov     [rbp+200h+var_A8], 6
0x1800126ac  mov     [rbp+200h+var_A0], 2
0x1800126b6  mov     [rbp+200h+var_90], 0Ah
0x1800126c1  mov     [rbp+200h+var_88], 3
0x1800126cb  mov     [rbp+200h+var_80], r13d
0x1800126d2  mov     [rbp+200h+var_78], 9
0x1800126dd  mov     [rbp+200h+var_70], 5
0x1800126e7  mov     [rbp+200h+var_60], 4
0x1800126f2  mov     [rbp+200h+var_58], 5
0x1800126fc  mov     [rbp+200h+var_200], r15
0x180012700  mov     [rbp+200h+var_50], r15
0x180012707  mov     [rbp+200h+var_48], 0Ch
0x180012712  mov     [rbp+200h+var_40], 5
0x18001271c  mov     rcx, cs:WPP_GLOBAL_Control
0x180012723  lea     rdi, WPP_GLOBAL_Control
0x18001272a  cmp     rcx, rdi
  ... truncated ...
```
