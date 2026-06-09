# SampInitializeWellKnownSids(void)

- ea: `0x18007b910`
- end: `0x18007bd38`
- name: `?SampInitializeWellKnownSids@@YAJXZ`
- size: `1064`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800799a8`

## callees

- `0x180022530`
- `0x180027e24`
- `0x18002cd80`
- `0x18007b910`
- `0x1800af7a0`

## import_xrefs

- `ntdll!RtlAllocateAndInitializeSid` at `0x18007bc04`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18007bc4e`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18007bc04`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18007bc4e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007bcc5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007bcc5`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18007bcdd`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18007bcdd`

## pseudocode

```c
__int64 SampInitializeWellKnownSids(void)
{
  signed int AccountDomainInfo; // ebx
  unsigned int v1; // edi
  NTSTATUS v2; // eax
  PSID *v3; // rdi
  HLOCAL hMem[2]; // [rsp+60h] [rbp-A0h] BYREF
  UCHAR SubAuthorityCount[4]; // [rsp+70h] [rbp-90h]
  ULONG SubAuthority0[2]; // [rsp+74h] [rbp-8Ch]
  ULONG v8[2]; // [rsp+7Ch] [rbp-84h]
  ULONG v9; // [rsp+84h] [rbp-7Ch]
  PSID *v10; // [rsp+88h] [rbp-78h]
  char v11; // [rsp+90h] [rbp-70h]
  __int64 v12; // [rsp+94h] [rbp-6Ch]
  __int64 v13; // [rsp+9Ch] [rbp-64h]
  int v14; // [rsp+A4h] [rbp-5Ch]
  PSID *v15; // [rsp+A8h] [rbp-58h]
  char v16; // [rsp+B0h] [rbp-50h]
  __int64 v17; // [rsp+B4h] [rbp-4Ch]
  __int64 v18; // [rsp+BCh] [rbp-44h]
  int v19; // [rsp+C4h] [rbp-3Ch]
  PSID *v20; // [rsp+C8h] [rbp-38h]
  char v21; // [rsp+D0h] [rbp-30h]
  __int64 v22; // [rsp+D4h] [rbp-2Ch]
  __int64 v23; // [rsp+DCh] [rbp-24h]
  int v24; // [rsp+E4h] [rbp-1Ch]
  PSID *v25; // [rsp+E8h] [rbp-18h]
  char v26; // [rsp+F0h] [rbp-10h]
  __int64 v27; // [rsp+F4h] [rbp-Ch]
  __int64 v28; // [rsp+FCh] [rbp-4h]
  int v29; // [rsp+104h] [rbp+4h]
  __int64 *v30; // [rsp+108h] [rbp+8h]
  char v31; // [rsp+110h] [rbp+10h]
  __int64 v32; // [rsp+114h] [rbp+14h]
  __int64 v33; // [rsp+11Ch] [rbp+1Ch]
  int v34; // [rsp+124h] [rbp+24h]
  __int64 *v35; // [rsp+128h] [rbp+28h]
  char v36; // [rsp+130h] [rbp+30h]
  __int64 v37; // [rsp+134h] [rbp+34h]
  __int64 v38; // [rsp+13Ch] [rbp+3Ch]
  int v39; // [rsp+144h] [rbp+44h]
  __int64 *v40; // [rsp+148h] [rbp+48h]
  char v41; // [rsp+150h] [rbp+50h]
  __int64 v42; // [rsp+154h] [rbp+54h]
  __int64 v43; // [rsp+15Ch] [rbp+5Ch]
  int v44; // [rsp+164h] [rbp+64h]
  __int64 *v45; // [rsp+168h] [rbp+68h]
  char v46; // [rsp+170h] [rbp+70h]
  __int64 v47; // [rsp+174h] [rbp+74h]
  __int64 v48; // [rsp+17Ch] [rbp+7Ch]
  int v49; // [rsp+184h] [rbp+84h]
  __int64 *v50; // [rsp+188h] [rbp+88h]
  char v51; // [rsp+190h] [rbp+90h]
  __int64 v52; // [rsp+194h] [rbp+94h]
  __int64 v53; // [rsp+19Ch] [rbp+9Ch]
  int v54; // [rsp+1A4h] [rbp+A4h]
  __int64 *v55; // [rsp+1A8h] [rbp+A8h]
  char v56; // [rsp+1B0h] [rbp+B0h]
  __int64 v57; // [rsp+1B4h] [rbp+B4h]
  __int64 v58; // [rsp+1BCh] [rbp+BCh]
  int v59; // [rsp+1C4h] [rbp+C4h]
  __int64 *v60; // [rsp+1C8h] [rbp+C8h]
  char v61; // [rsp+1D0h] [rbp+D0h]
  __int64 v62; // [rsp+1D4h] [rbp+D4h]
  __int64 v63; // [rsp+1DCh] [rbp+DCh]
  int v64; // [rsp+1E4h] [rbp+E4h]
  __int64 *v65; // [rsp+1E8h] [rbp+E8h]
  char v66; // [rsp+1F0h] [rbp+F0h]
  __int64 v67; // [rsp+1F4h] [rbp+F4h]
  __int64 v68; // [rsp+1FCh] [rbp+FCh]
  int v69; // [rsp+204h] [rbp+104h]
  __int64 *v70; // [rsp+208h] [rbp+108h]
  char v71; // [rsp+210h] [rbp+110h]
  int v72; // [rsp+214h] [rbp+114h]
  __int64 v73; // [rsp+218h] [rbp+118h]
  __int64 v74; // [rsp+220h] [rbp+120h]
  PSID *v75; // [rsp+228h] [rbp+128h]
  char v76; // [rsp+230h] [rbp+130h]
  int v77; // [rsp+234h] [rbp+134h]
  __int64 v78; // [rsp+238h] [rbp+138h]
  __int64 v79; // [rsp+240h] [rbp+140h]
  __int64 *v80; // [rsp+248h] [rbp+148h]
  char v81; // [rsp+250h] [rbp+150h]
  __int64 v82; // [rsp+254h] [rbp+154h]
  __int64 v83; // [rsp+25Ch] [rbp+15Ch]
  int v84; // [rsp+264h] [rbp+164h]
  void **v85; // [rsp+268h] [rbp+168h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+270h] [rbp+170h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v87; // [rsp+278h] [rbp+178h] BYREF

  *(_WORD *)&v87.Value[4] = 256;
  hMem[0] = 0;
  v10 = &SampAnonymousSid;
  AccountDomainInfo = 0;
  *(_DWORD *)v87.Value = 0;
  v15 = &SampAuthenticatedUsersSid;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  v20 = &SampBuiltinDomainSid;
  v25 = &SampLocalSystemSid;
  v30 = &SampNetworkSid;
  v35 = &SampEnterpriseDomainControllersSid;
  v40 = &SampNetworkServiceSid;
  v45 = &SampPrincipalSelfSid;
  v50 = &SampIUserSid;
  v55 = &SampInteractiveSid;
  v60 = &SampLocalLogonSid;
  v65 = &SampRemoteInteractiveSid;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  SubAuthorityCount[0] = 1;
  *(_QWORD *)SubAuthority0 = 7;
  *(_QWORD *)v8 = 0;
  v9 = 0;
  v11 = 1;
  v12 = 11;
  v13 = 0;
  v14 = 0;
  v16 = 1;
  v17 = 32;
  v18 = 0;
  v19 = 0;
  v21 = 1;
  v22 = 18;
  v23 = 0;
  v24 = 0;
  v26 = 1;
  v27 = 2;
  v28 = 0;
  v29 = 0;
  v31 = 1;
  v32 = 9;
  v33 = 0;
  v34 = 0;
  v36 = 1;
  v37 = 20;
  v38 = 0;
  v39 = 0;
  v41 = 1;
  v42 = 10;
  v43 = 0;
  v44 = 0;
  v46 = 1;
  v47 = 17;
  v48 = 0;
  v49 = 0;
  v51 = 1;
  v52 = 4;
  v53 = 0;
  v54 = 0;
  v56 = 1;
  v57 = 1;
  v58 = 0;
  v59 = 0;
  v61 = 1;
  v62 = 14;
  v63 = 0;
  v64 = 0;
  v66 = 1;
  v67 = 13;
  v70 = &SampTerminalServerSid;
  v1 = 0;
  v68 = 0;
  v75 = &SampAdministratorsAliasSid;
  v80 = &SampAccountOperatorsAliasSid;
  v85 = &SampClaimsSentinelSid;
  v69 = 0;
  v71 = 2;
  v72 = 32;
  v73 = 544;
  v74 = 0;
  v76 = 2;
  v77 = 32;
  v78 = 548;
  v79 = 0;
  v81 = 5;
  v82 = 21;
  v83 = 0;
  v84 = 497;
  while ( AccountDomainInfo >= 0 )
  {
    v2 = RtlAllocateAndInitializeSid(
           &IdentifierAuthority,
           SubAuthorityCount[32 * v1],
           SubAuthority0[8 * v1],
           SubAuthority0[8 * v1 + 1],
           v8[8 * v1],
           v8[8 * v1 + 1],
           *(&v9 + 8 * v1),
           0,
           0,
           0,
           (&v10)[4 * v1]);
    ++v1;
    AccountDomainInfo = v2;
    if ( v1 >= 0x10 )
    {
      if ( v2 >= 0 )
      {
        AccountDomainInfo = RtlAllocateAndInitializeSid(&v87, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &SampWorldSid);
        if ( AccountDomainInfo >= 0 )
        {
          AccountDomainInfo = SampGetAccountDomainInfo(0, hMem);
          if ( AccountDomainInfo >= 0 )
          {
            v3 = (PSID *)hMem[0];
            AccountDomainInfo = SampCreateFullSid(*((PSID *)hMem[0] + 2), 0x1F4u, &SampAdministratorUserSid);
            if ( AccountDomainInfo >= 0 )
            {
              AccountDomainInfo = SampCreateFullSid(v3[2], 0x200u, (PSID *)&SampDomainAdminsGroupSid);
              if ( AccountDomainInfo >= 0 )
                AccountDomainInfo = SampCreateFullSid(v3[2], 0x23Cu, (PSID *)&SampNonCachablePrincipalsSid);
            }
            LocalFree(v3);
            if ( AccountDomainInfo >= 0 )
              AccountDomainInfo = !ConvertStringSidToSidW(
                                     L"S-1-15-3-1024-1730716382-2949791265-2036182297-688374192-553408039-4133924312-4201181712-267922143",
                                     &SampUserSigninSupportCapabilitySid)
                                ? 0xC0000017
                                : 0;
          }
        }
      }
      break;
    }
  }
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control[3].Buffer,
      189,
      WPP_6405431812663459a7a3c2922bf567cd_Traceguids,
      (unsigned int)AccountDomainInfo,
      AccountDomainInfo);
  return (unsigned int)AccountDomainInfo;
}

```

## disassembly

```asm
0x18007b910  push    rbp
0x18007b912  push    rbx
0x18007b913  push    rsi
0x18007b914  push    rdi
0x18007b915  lea     rbp, [rsp-198h]
0x18007b91d  sub     rsp, 298h
0x18007b924  mov     rax, cs:__security_cookie
0x18007b92b  xor     rax, rsp
0x18007b92e  mov     [rbp+1B0h+var_30], rax
0x18007b935  xor     esi, esi
0x18007b937  mov     word ptr [rbp+1B0h+var_38.Value+4], 100h
0x18007b940  lea     rax, SampAnonymousSid
0x18007b947  mov     [rsp+2B0h+hMem], rsi
0x18007b94c  mov     [rbp+1B0h+var_228], rax
0x18007b950  mov     ebx, esi
0x18007b952  lea     rax, SampAuthenticatedUsersSid
0x18007b959  mov     dword ptr [rbp+1B0h+var_38.Value], esi
0x18007b95f  mov     [rbp+1B0h+var_208], rax
0x18007b963  lea     ecx, [rsi+20h]
0x18007b966  lea     rax, SampBuiltinDomainSid
0x18007b96d  mov     dword ptr [rbp+1B0h+IdentifierAuthority.Value], esi
0x18007b973  mov     [rbp+1B0h+var_1E8], rax
0x18007b977  lea     rax, SampLocalSystemSid
0x18007b97e  mov     [rbp+1B0h+var_1C8], rax
0x18007b982  lea     rax, SampNetworkSid
0x18007b989  mov     [rbp+1B0h+var_1A8], rax
0x18007b98d  lea     rax, SampEnterpriseDomainControllersSid
0x18007b994  mov     [rbp+1B0h+var_188], rax
0x18007b998  lea     rax, SampNetworkServiceSid
0x18007b99f  mov     [rbp+1B0h+var_168], rax
0x18007b9a3  lea     rax, SampPrincipalSelfSid
0x18007b9aa  mov     [rbp+1B0h+var_148], rax
0x18007b9ae  lea     rax, SampIUserSid
0x18007b9b5  mov     [rbp+1B0h+var_128], rax
0x18007b9bc  lea     rax, SampInteractiveSid
0x18007b9c3  mov     [rbp+1B0h+var_108], rax
0x18007b9ca  lea     rax, SampLocalLogonSid
0x18007b9d1  mov     [rbp+1B0h+var_E8], rax
0x18007b9d8  lea     rax, SampRemoteInteractiveSid
0x18007b9df  mov     [rbp+1B0h+var_C8], rax
0x18007b9e6  mov     word ptr [rbp+1B0h+IdentifierAuthority.Value+4], 500h
0x18007b9ef  mov     [rsp+2B0h+SubAuthorityCount], 1
0x18007b9f4  mov     qword ptr [rsp+2B0h+SubAuthority0], 7
0x18007b9fd  mov     qword ptr [rsp+2B0h+var_234], rsi
0x18007ba02  mov     [rbp+1B0h+var_22C], esi
0x18007ba05  mov     [rbp+1B0h+var_220], 1
0x18007ba09  mov     [rbp+1B0h+var_21C], 0Bh
0x18007ba11  mov     [rbp+1B0h+var_214], rsi
0x18007ba15  mov     [rbp+1B0h+var_20C], esi
0x18007ba18  mov     [rbp+1B0h+var_200], 1
0x18007ba1c  mov     [rbp+1B0h+var_1FC], rcx
0x18007ba20  mov     [rbp+1B0h+var_1F4], rsi
0x18007ba24  mov     [rbp+1B0h+var_1EC], esi
0x18007ba27  mov     [rbp+1B0h+var_1E0], 1
0x18007ba2b  mov     [rbp+1B0h+var_1DC], 12h
0x18007ba33  mov     [rbp+1B0h+var_1D4], rsi
0x18007ba37  mov     [rbp+1B0h+var_1CC], esi
0x18007ba3a  mov     [rbp+1B0h+var_1C0], 1
0x18007ba3e  mov     [rbp+1B0h+var_1BC], 2
0x18007ba46  mov     [rbp+1B0h+var_1B4], rsi
0x18007ba4a  mov     [rbp+1B0h+var_1AC], esi
0x18007ba4d  mov     [rbp+1B0h+var_1A0], 1
0x18007ba51  mov     [rbp+1B0h+var_19C], 9
0x18007ba59  mov     [rbp+1B0h+var_194], rsi
0x18007ba5d  mov     [rbp+1B0h+var_18C], esi
0x18007ba60  mov     [rbp+1B0h+var_180], 1
0x18007ba64  mov     [rbp+1B0h+var_17C], 14h
0x18007ba6c  mov     [rbp+1B0h+var_174], rsi
0x18007ba70  mov     [rbp+1B0h+var_16C], esi
0x18007ba73  mov     [rbp+1B0h+var_160], 1
0x18007ba77  mov     [rbp+1B0h+var_15C], 0Ah
0x18007ba7f  mov     [rbp+1B0h+var_154], rsi
0x18007ba83  mov     [rbp+1B0h+var_14C], esi
0x18007ba86  mov     [rbp+1B0h+var_140], 1
0x18007ba8a  mov     [rbp+1B0h+var_13C], 11h
0x18007ba92  mov     [rbp+1B0h+var_134], rsi
0x18007ba96  mov     [rbp+1B0h+var_12C], esi
0x18007ba9c  mov     [rbp+1B0h+var_120], 1
0x18007baa3  mov     [rbp+1B0h+var_11C], 4
0x18007baae  mov     [rbp+1B0h+var_114], rsi
0x18007bab5  mov     [rbp+1B0h+var_10C], esi
0x18007babb  mov     [rbp+1B0h+var_100], 1
0x18007bac2  mov     [rbp+1B0h+var_FC], 1
0x18007bacd  mov     [rbp+1B0h+var_F4], rsi
0x18007bad4  mov     [rbp+1B0h+var_EC], esi
0x18007bada  mov     [rbp+1B0h+var_E0], 1
0x18007bae1  mov     [rbp+1B0h+var_DC], 0Eh
0x18007baec  mov     [rbp+1B0h+var_D4], rsi
0x18007baf3  mov     [rbp+1B0h+var_CC], esi
0x18007baf9  mov     [rbp+1B0h+var_C0], 1
0x18007bb00  lea     rax, SampTerminalServerSid
0x18007bb07  mov     [rbp+1B0h+var_BC], 0Dh
0x18007bb12  mov     [rbp+1B0h+var_A8], rax
0x18007bb19  mov     edi, esi
0x18007bb1b  lea     rax, SampAdministratorsAliasSid
0x18007bb22  mov     [rbp+1B0h+var_B4], rsi
0x18007bb29  mov     [rbp+1B0h+var_88], rax
0x18007bb30  lea     rax, SampAccountOperatorsAliasSid
0x18007bb37  mov     [rbp+1B0h+var_68], rax
0x18007bb3e  lea     rax, SampClaimsSentinelSid
0x18007bb45  mov     [rbp+1B0h+var_48], rax
0x18007bb4c  mov     [rbp+1B0h+var_AC], esi
0x18007bb52  mov     [rbp+1B0h+var_A0], 2
0x18007bb59  mov     [rbp+1B0h+var_9C], ecx
0x18007bb5f  mov     [rbp+1B0h+var_98], 220h
0x18007bb6a  mov     [rbp+1B0h+var_90], rsi
0x18007bb71  mov     [rbp+1B0h+var_80], 2
0x18007bb78  mov     [rbp+1B0h+var_7C], ecx
0x18007bb7e  mov     [rbp+1B0h+var_78], 224h
0x18007bb89  mov     [rbp+1B0h+var_70], rsi
0x18007bb90  mov     [rbp+1B0h+var_60], 5
0x18007bb97  mov     [rbp+1B0h+var_5C], 15h
0x18007bba2  mov     [rbp+1B0h+var_54], rsi
0x18007bba9  mov     [rbp+1B0h+var_4C], 1F1h
0x18007bbb3  test    ebx, ebx
0x18007bbb5  js      loc_18007BCEF
0x18007bbbb  mov     edx, edi
0x18007bbbd  lea     rcx, [rbp+1B0h+IdentifierAuthority]; IdentifierAuthority
0x18007bbc4  shl     rdx, 5
0x18007bbc8  mov     rax, [rbp+rdx+1B0h+var_228]
0x18007bbcd  mov     r9d, [rsp+rdx+2B0h+SubAuthority0+4]; SubAuthority1
0x18007bbd2  mov     r8d, [rsp+rdx+2B0h+SubAuthority0]; SubAuthority0
0x18007bbd7  mov     [rsp+2B0h+Sid], rax; Sid
0x18007bbdc  mov     eax, [rbp+rdx+1B0h+var_22C]
0x18007bbe0  mov     [rsp+2B0h+SubAuthority7], esi; SubAuthority7
0x18007bbe4  mov     [rsp+2B0h+SubAuthority6], esi; SubAuthority6
0x18007bbe8  mov     [rsp+2B0h+SubAuthority5], esi; SubAuthority5
0x18007bbec  mov     [rsp+2B0h+SubAuthority4], eax; SubAuthority4
0x18007bbf0  mov     eax, [rbp+rdx+1B0h+var_234+4]
0x18007bbf4  mov     [rsp+2B0h+SubAuthority3], eax; SubAuthority3
0x18007bbf8  mov     eax, [rsp+rdx+2B0h+var_234]
0x18007bbfc  mov     dl, [rsp+rdx+2B0h+SubAuthorityCount]; SubAuthorityCount
0x18007bc00  mov     [rsp+2B0h+SubAuthority2], eax; SubAuthority2
0x18007bc04  call    cs:__imp_RtlAllocateAndInitializeSid
0x18007bc0a  inc     edi
0x18007bc0c  mov     ebx, eax
0x18007bc0e  cmp     edi, 10h
0x18007bc11  jb      short loc_18007BBB3
0x18007bc13  test    eax, eax
0x18007bc15  js      loc_18007BCEF
0x18007bc1b  lea     rax, SampWorldSid
0x18007bc22  xor     r9d, r9d; SubAuthority1
0x18007bc25  mov     [rsp+2B0h+Sid], rax; Sid
0x18007bc2a  lea     rcx, [rbp+1B0h+var_38]; IdentifierAuthority
0x18007bc31  mov     [rsp+2B0h+SubAuthority7], esi; SubAuthority7
0x18007bc35  xor     r8d, r8d; SubAuthority0
0x18007bc38  mov     [rsp+2B0h+SubAuthority6], esi; SubAuthority6
0x18007bc3c  mov     dl, 1; SubAuthorityCount
0x18007bc3e  mov     [rsp+2B0h+SubAuthority5], esi; SubAuthority5
0x18007bc42  mov     [rsp+2B0h+SubAuthority4], esi; SubAuthority4
0x18007bc46  mov     [rsp+2B0h+SubAuthority3], esi; SubAuthority3
0x18007bc4a  mov     [rsp+2B0h+SubAuthority2], esi; SubAuthority2
0x18007bc4e  call    cs:__imp_RtlAllocateAndInitializeSid
0x18007bc54  mov     ebx, eax
0x18007bc56  test    eax, eax
0x18007bc58  js      loc_18007BCEF
0x18007bc5e  lea     rdx, [rsp+2B0h+hMem]
0x18007bc63  xor     ecx, ecx
0x18007bc65  call    SampGetAccountDomainInfo
0x18007bc6a  mov     ebx, eax
0x18007bc6c  test    eax, eax
0x18007bc6e  js      short loc_18007BCEF
0x18007bc70  mov     rdi, [rsp+2B0h+hMem]
0x18007bc75  lea     r8, SampAdministratorUserSid
0x18007bc7c  mov     edx, 1F4h
0x18007bc81  mov     rcx, [rdi+10h]; SourceSid
0x18007bc85  call    SampCreateFullSid
0x18007bc8a  mov     ebx, eax
0x18007bc8c  test    eax, eax
0x18007bc8e  js      short loc_18007BCC2
0x18007bc90  mov     rcx, [rdi+10h]; SourceSid
0x18007bc94  lea     r8, SampDomainAdminsGroupSid
0x18007bc9b  mov     edx, 200h
0x18007bca0  call    SampCreateFullSid
0x18007bca5  mov     ebx, eax
0x18007bca7  test    eax, eax
0x18007bca9  js      short loc_18007BCC2
0x18007bcab  mov     rcx, [rdi+10h]; SourceSid
0x18007bcaf  lea     r8, SampNonCachablePrincipalsSid
0x18007bcb6  mov     edx, 23Ch
0x18007bcbb  call    SampCreateFullSid
0x18007bcc0  mov     ebx, eax
0x18007bcc2  mov     rcx, rdi; hMem
0x18007bcc5  call    cs:__imp_LocalFree
0x18007bccb  test    ebx, ebx
0x18007bccd  js      short loc_18007BCEF
0x18007bccf  lea     rdx, SampUserSigninSupportCapabilitySid; Sid
0x18007bcd6  lea     rcx, StringSid; "S-1-15-3-1024-1730716382-2949791265-203"...
0x18007bcdd  call    cs:__imp_ConvertStringSidToSidW
0x18007bce3  neg     eax
0x18007bce5  sbb     ebx, ebx
0x18007bce7  not     ebx
0x18007bce9  and     ebx, 0C0000017h
0x18007bcef  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bcf6  test    dword ptr [rcx+44h], 20000h
0x18007bcfd  jz      short loc_18007BD1B
0x18007bcff  mov     rcx, [rcx+38h]
0x18007bd03  lea     r8, WPP_6405431812663459a7a3c2922bf567cd_Traceguids
0x18007bd0a  mov     edx, 0BDh
0x18007bd0f  mov     [rsp+2B0h+SubAuthority2], ebx
0x18007bd13  mov     r9d, ebx
0x18007bd16  call    WPP_SF_Dd
0x18007bd1b  mov     eax, ebx
0x18007bd1d  mov     rcx, [rbp+1B0h+var_30]
0x18007bd24  xor     rcx, rsp; StackCookie
0x18007bd27  call    __security_check_cookie
0x18007bd2c  add     rsp, 298h
0x18007bd33  pop     rdi
0x18007bd34  pop     rsi
0x18007bd35  pop     rbx
0x18007bd36  pop     rbp
0x18007bd37  retn
```
