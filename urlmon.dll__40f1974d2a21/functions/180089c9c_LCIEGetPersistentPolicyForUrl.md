# LCIEGetPersistentPolicyForUrl

- ea: `0x180089c9c`
- end: `0x18008a2cd`
- name: `LCIEGetPersistentPolicyForUrl`
- size: `1585`
- prototype: `__int64 __usercall@<rax>(LPCWSTR pwzURI@<rcx>, __int64, BSTR bstrString)`
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18010f6d0`
- `0x18010fc7c`

## callees

- `0x180004e84`
- `0x18003b010`
- `0x180084d6c`
- `0x180089870`
- `0x180089c9c`
- `0x18008a2d4`
- `0x18008a310`
- `0x18009b8e4`
- `0x1800a8b10`
- `0x1800a9030`
- `0x1800a90b0`
- `0x1800f4498`
- `0x1800f4850`
- `0x1800f4ad0`
- `0x18010853c`
- `0x180110000`
- `0x18011c010`

## import_xrefs

- `iertutil!CreateUri` at `0x180089d3a`
- `iertutil!CreateUri` at `0x180089d3a`
- `iertutil!__imp_?IsProtectedModeEnabledForIE@@YAHXZ` at `0x180089efc`
- `iertutil!__imp_?IsProtectedModeEnabledForIE@@YAHXZ` at `0x180089efc`
- `iertutil!__imp_?IsBrowserProcess@@YAHXZ` at `0x180089ebf`
- `iertutil!__imp_?IsBrowserProcess@@YAHXZ` at `0x180089ebf`
- `iertutil!__imp_GetExtValue` at `0x180089e4a`
- `iertutil!__imp_GetExtValue` at `0x180089e4a`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternalEx` at `0x180089f77`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternalEx` at `0x180089f77`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180089cec`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180089d93`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180089da4`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180089db7`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180089dc6`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180089e59`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180089e80`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180089ed2`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180089ede`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180089f5e`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180089fde`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008a081`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008a090`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008a0a3`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008a0b2`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008a12c`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008a13b`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008a14a`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008a159`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008a17f`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008a195`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008a1a8`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008a1bb`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008a24c`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008a259`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180089cec`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180089d93`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180089da4`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180089db7`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180089dc6`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180089e59`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180089e80`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180089ed2`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180089ede`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180089f5e`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180089fde`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008a081`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008a090`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008a0a3`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008a0b2`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008a12c`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008a13b`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008a14a`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008a159`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008a17f`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008a195`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008a1a8`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008a1bb`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008a24c`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008a259`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18008a1f0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18008a1f0`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18008a21a`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18008a28c`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18008a21a`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18008a28c`
- `OLEAUT32!__imp_SysFreeString` at `0x180089eb9`
- `OLEAUT32!__imp_SysFreeString` at `0x180089eb9`

## pseudocode

```c
__int64 __fastcall LCIEGetPersistentPolicyForUrl(
        LPCWSTR pwzURI,
        unsigned int a2,
        unsigned int a3,
        char a4,
        _DWORD *a5,
        BSTR bstrString)
{
  BSTR v10; // rsi
  HRESULT v11; // edi
  DWORD v12; // eax
  int DomainWithHostFallbackFromUri; // eax
  char Bool; // al
  unsigned int v15; // ecx
  char v16; // al
  int v17; // eax
  int LRACPIC; // eax
  int IsFeatureEnabledInternal; // eax
  char v20; // al
  unsigned int v21; // eax
  unsigned int v22; // r14d
  unsigned __int8 v23; // dl
  char v24; // si
  bool v25; // r14
  struct IsoScope *DefaultScope; // rax
  DWORD v27; // eax
  _WORD *Value; // rax
  int v30; // [rsp+20h] [rbp-58h]
  __int64 v31; // [rsp+28h] [rbp-50h]
  __int64 v32; // [rsp+30h] [rbp-48h]
  int v33; // [rsp+38h] [rbp-40h]
  BSTR v34; // [rsp+40h] [rbp-38h]
  int v35; // [rsp+50h] [rbp-28h] BYREF
  int v36; // [rsp+54h] [rbp-24h] BYREF
  int v37; // [rsp+58h] [rbp-20h] BYREF
  int v38; // [rsp+5Ch] [rbp-1Ch] BYREF
  int v39; // [rsp+60h] [rbp-18h] BYREF
  int v40; // [rsp+64h] [rbp-14h] BYREF
  IUri *ppURI; // [rsp+68h] [rbp-10h] BYREF

  v35 = 0;
  if ( !dword_18015EB64 )
    dword_18015EB64 = IsoGetIntegrity(1);
  v10 = bstrString;
  if ( bstrString )
    *(_DWORD *)bstrString = 0;
  if ( (unsigned __int8)IEConfiguration_GetBool(268435526) )
  {
    v11 = 0;
    *a5 = IsoGetIntegrity(0) & 0x47F;
    return (unsigned int)v11;
  }
  v37 = 0;
  v36 = -1;
  ppURI = 0;
  v12 = HelperAddUriDefaultFlags(0x3002B80u, 4u);
  v11 = CreateUri(pwzURI, v12, 0, &ppURI);
  if ( v11 >= 0 )
  {
    v11 = ((__int64 (__fastcall *)(IUri *, int *))ppURI->lpVtbl->GetScheme)(ppURI, &v36);
    if ( v11 >= 0 )
    {
      v11 = ((__int64 (__fastcall *)(IUri *, __int64, int *))ppURI->lpVtbl->HasProperty)(ppURI, 6, &v37);
      if ( v11 >= 0 )
      {
        if ( ((unsigned __int8)IEConfiguration_GetBool(268435482) || (unsigned __int8)IEConfiguration_GetBool(268435481))
          && ((unsigned __int8)IEConfiguration_GetBool(268435529) || (unsigned __int8)IEConfiguration_GetBool(268435479)) )
        {
          bstrString = 0;
          if ( v36 != 9 || v37 )
            DomainWithHostFallbackFromUri = GetDomainWithHostFallbackFromUri(ppURI, &bstrString, 0, 0);
          else
            DomainWithHostFallbackFromUri = ((__int64 (__fastcall *)(IUri *, BSTR *))ppURI->lpVtbl->GetAbsoluteUri)(
                                              ppURI,
                                              &bstrString);
          if ( !DomainWithHostFallbackFromUri )
          {
            v34 = bstrString;
            v33 = 1;
            v32 = 0;
            v31 = 0;
            v30 = 4;
            if ( (int)GetExtValue((__int64 *)SettingStore::IEVALUE_LCIE_TabProcConfig_Value[0], 8, 1, &v35) >= 0 )
            {
              Bool = IEConfiguration_GetBool(268435477);
              v15 = v35;
              if ( Bool && (v35 & 0x400) != 0 )
              {
                v35 &= 0xFFFFF980;
                if ( (v15 & 0x100) != 0 )
                {
                  v16 = IEConfiguration_GetBool(268435519);
                  v15 = IsoGetLRACPIC(v16) | v35;
                  v35 = v15;
                }
                else
                {
                  v15 = 1;
                  v35 = 1;
                }
              }
              if ( (v15 & 0xFFFFE080) != 0 || (v15 & 0x7F) - 1 > 0x7B )
                v35 = 0;
            }
          }
          SysFreeString(bstrString);
        }
        if ( IsBrowserProcess()
          && ((unsigned __int8)IEConfiguration_GetBool(268435482) || (unsigned __int8)IEConfiguration_GetBool(268435481)) )
        {
          v17 = IsProtectedModeIUri(ppURI, a2, a3, v10, v30, v31, v32, v33, v34);
        }
        else
        {
          if ( !IsProtectedModeEnabledForIE() )
            goto LABEL_55;
          v17 = IsProtectedModeIUriInternal(ppURI, a2, a3, v10);
        }
        v11 = v17;
        if ( v17 != 1 )
        {
          if ( v17 )
          {
            if ( v17 >= 0 )
              v11 = -2147467259;
            goto LABEL_59;
          }
          if ( (unsigned int)dword_18015EB64 < 0x7C && (unsigned int)IsProtectedModeNeutralIUri(ppURI) )
          {
            LRACPIC = dword_18015EB64 & 0x7F;
LABEL_51:
            *a5 = LRACPIC;
LABEL_59:
            if ( v35 )
            {
              v23 = *(_BYTE *)a5 & 0x7F;
              if ( (unsigned __int8)(v35 & 0x7F) <= v23 )
                *a5 |= v35 & ~(v23 < 0x7Bu ? 127 : 383);
              else
                *a5 = v35;
            }
            if ( !IsOs_Win8OrGreater() && (*(_BYTE *)a5 & 0x7Fu) < 0x7B )
              *a5 = 123;
            if ( (*(_BYTE *)a5 & 0x7Fu) < 0x7B
              && ((unsigned __int8)IEConfiguration_GetBool(268435482)
               || (unsigned __int8)IEConfiguration_GetBool(268435481))
              && (unsigned __int8)IEConfiguration_GetBool(268435529)
              && !(unsigned __int8)IEConfiguration_GetBool(268435477) )
            {
              LODWORD(bstrString) = 0;
              v38 = 0;
              v40 = 0;
              if ( ((unsigned int)ShouldRestrictEPMForDomain(ppURI, &bstrString) || !(_DWORD)bstrString)
                && ((unsigned int)ShouldUriBeInEMIE(ppURI, &v38, &v40) || !v38) )
              {
                if ( !(unsigned int)ShouldRestrictEPMNotificationsForDomain(ppURI, &bstrString) && (_DWORD)bstrString )
                  *a5 |= 0x200u;
              }
              else
              {
                *a5 &= 0xFFFFFEFB;
                *a5 |= 0x47Bu;
              }
            }
            v39 = 0;
            if ( ((unsigned __int8)IEConfiguration_GetBool(268435482)
               || (unsigned __int8)IEConfiguration_GetBool(268435481))
              && (unsigned __int8)IEConfiguration_GetBool(268435529)
              && !(unsigned __int8)IEConfiguration_GetBool(268435477) )
            {
              IsDomainSandboxNeutral(ppURI, &v39);
            }
            v24 = 0;
            v25 = 0;
            if ( !(unsigned __int8)IEConfiguration_GetBool(536870913) )
            {
              if ( (unsigned __int8)IEConfiguration_GetBool(536870914) )
              {
                if ( (unsigned __int8)IEConfiguration_GetBool(268435529) )
                {
                  if ( !(unsigned __int8)IEConfiguration_GetBool(268435477) )
                  {
                    if ( IsoGetDefaultScope() )
                    {
                      DefaultScope = IsoGetDefaultScope();
                      v27 = (*(__int64 (__fastcall **)(struct IsoScope *, __int64))(*(_QWORD *)DefaultScope + 680LL))(
                              DefaultScope,
                              1);
                      Value = TlsGetValue(v27);
                      if ( Value )
                      {
                        if ( Value[1] == 515 )
                        {
                          InitOnceExecuteOnce(&g_InitOnce, LoadIsoDll, 0, 0);
                          v24 = 1;
                          v25 = (unsigned int)((__int64 (__fastcall *)(__int64))qword_1801740D0)(256) == 0;
                        }
                      }
                    }
                  }
                }
              }
            }
            if ( v39 )
            {
              *a5 |= 0x2000u;
              if ( !v25
                && !(unsigned __int8)IEConfiguration_GetBool(536870913)
                && (unsigned __int8)IEConfiguration_GetBool(536870914) )
              {
                *a5 &= 0xFFFFFB80;
                *a5 |= dword_18015EB64;
              }
            }
            else if ( v24 )
            {
              InitOnceExecuteOnce(&g_InitOnce, LoadIsoDll, 0, 0);
              ((void (__fastcall *)(_QWORD, __int64))qword_1801740C8)(0, 8);
            }
            goto LABEL_99;
          }
          if ( (unsigned __int8)IEConfiguration_GetBool(268435530) )
          {
LABEL_46:
            LRACPIC = 123;
            goto LABEL_51;
          }
          if ( FCK::FEATURE_EPM_SPECIAL_FOLDER_LOWIL )
          {
            IsFeatureEnabledInternal = CoInternetIsFeatureEnabledInternalEx(FCK::FEATURE_EPM_SPECIAL_FOLDER_LOWIL, 1);
            if ( IsFeatureEnabledInternal < 0 )
              goto LABEL_47;
            dword_180159CE8 = IsFeatureEnabledInternal == 0;
            FCK::FEATURE_EPM_SPECIAL_FOLDER_LOWIL = 0;
          }
          if ( dword_180159CE8 && !(unsigned int)IsUriFileInSpecialFolder(ppURI) )
            goto LABEL_46;
LABEL_47:
          LODWORD(bstrString) = 0;
          v11 = IEGetZoneIUri(ppURI, a3, &bstrString, v10);
          if ( v11 < 0 || (unsigned int)((_DWORD)bstrString - 1) > 1 )
          {
            LRACPIC = 1;
          }
          else
          {
            v20 = IEConfiguration_GetBool(268435519);
            LRACPIC = IsoGetLRACPIC(v20);
          }
          goto LABEL_51;
        }
LABEL_55:
        v11 = 0;
        v21 = IsoGetIntegrity(0) & 0x47F;
        *a5 = v21;
        v22 = a4 & 0x7F;
        if ( v22 && v22 < v21 && (unsigned int)IsProtectedModeNeutralIUri(ppURI) )
          *a5 = v22;
        goto LABEL_59;
      }
    }
  }
LABEL_99:
  if ( ppURI )
    ((void (__fastcall *)(IUri *))ppURI->lpVtbl->Release)(ppURI);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180089c9c  push    rbp
0x180089c9e  push    rbx
0x180089c9f  push    rsi
0x180089ca0  push    rdi
0x180089ca1  push    r12
0x180089ca3  push    r13
0x180089ca5  push    r14
0x180089ca7  push    r15
0x180089ca9  mov     rbp, rsp
0x180089cac  sub     rsp, 78h
0x180089cb0  xor     r13d, r13d
0x180089cb3  mov     r14d, r9d
0x180089cb6  cmp     cs:dword_18015EB64, r13d
0x180089cbd  mov     r12d, r8d
0x180089cc0  mov     r15d, edx
0x180089cc3  mov     [rbp+var_28], r13d
0x180089cc7  mov     rbx, rcx
0x180089cca  jnz     short loc_180089CDB
0x180089ccc  lea     ecx, [r13+1]
0x180089cd0  call    ?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z; IsoGetIntegrity(ulong)
0x180089cd5  mov     cs:dword_18015EB64, eax
0x180089cdb  mov     rsi, [rbp+bstrString]
0x180089cdf  test    rsi, rsi
0x180089ce2  jz      short loc_180089CE7
0x180089ce4  mov     [rsi], r13d
0x180089ce7  mov     ecx, 10000046h
0x180089cec  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180089cf2  test    al, al
0x180089cf4  jz      short loc_180089D10
0x180089cf6  xor     ecx, ecx
0x180089cf8  mov     edi, r13d
0x180089cfb  call    ?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z; IsoGetIntegrity(ulong)
0x180089d00  mov     rcx, [rbp+arg_20]
0x180089d04  and     eax, 47Fh
0x180089d09  mov     [rcx], eax
0x180089d0b  jmp     loc_18008A2BA
0x180089d10  mov     edx, 4; unsigned int
0x180089d15  mov     [rbp+var_20], r13d
0x180089d19  mov     ecx, 3002B80h; unsigned int
0x180089d1e  mov     [rbp+var_24], 0FFFFFFFFh
0x180089d25  mov     [rbp+ppURI], r13
0x180089d29  call    ?HelperAddUriDefaultFlags@@YAKKK@Z; HelperAddUriDefaultFlags(ulong,ulong)
0x180089d2e  mov     edx, eax; dwFlags
0x180089d30  lea     r9, [rbp+ppURI]; ppURI
0x180089d34  mov     rcx, rbx; pwzURI
0x180089d37  xor     r8d, r8d; dwReserved
0x180089d3a  call    cs:__imp_CreateUri
0x180089d40  mov     edi, eax
0x180089d42  test    eax, eax
0x180089d44  js      loc_18008A2A5
0x180089d4a  mov     rcx, [rbp+ppURI]
0x180089d4e  lea     rdx, [rbp+var_24]
0x180089d52  mov     rax, [rcx]
0x180089d55  mov     rax, [rax+0C0h]
0x180089d5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089d61  mov     edi, eax
0x180089d63  test    eax, eax
0x180089d65  js      loc_18008A2A5
0x180089d6b  mov     rcx, [rbp+ppURI]
0x180089d6f  lea     r8, [rbp+var_20]
0x180089d73  mov     edx, 6
0x180089d78  mov     rax, [rcx]
0x180089d7b  mov     rax, [rax+30h]
0x180089d7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089d84  mov     edi, eax
0x180089d86  test    eax, eax
0x180089d88  js      loc_18008A2A5
0x180089d8e  mov     ecx, 1000001Ah
0x180089d93  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180089d99  mov     edi, 10000019h
0x180089d9e  test    al, al
0x180089da0  jnz     short loc_180089DB2
0x180089da2  mov     ecx, edi
0x180089da4  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180089daa  test    al, al
0x180089dac  jz      loc_180089EBF
0x180089db2  mov     ecx, 10000049h
0x180089db7  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180089dbd  test    al, al
0x180089dbf  jnz     short loc_180089DD4
0x180089dc1  mov     ecx, 10000017h
0x180089dc6  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180089dcc  test    al, al
0x180089dce  jz      loc_180089EBF
0x180089dd4  cmp     [rbp+var_24], 9
0x180089dd8  mov     [rbp+bstrString], r13
0x180089ddc  jnz     short loc_180089DFA
0x180089dde  cmp     [rbp+var_20], r13d
0x180089de2  jnz     short loc_180089DFA
0x180089de4  mov     rcx, [rbp+ppURI]
0x180089de8  lea     rdx, [rbp+bstrString]
0x180089dec  mov     rax, [rcx]
0x180089def  mov     rax, [rax+38h]
0x180089df3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089df8  jmp     short loc_180089E0D
0x180089dfa  mov     rcx, [rbp+ppURI]; struct IUri *
0x180089dfe  lea     rdx, [rbp+bstrString]; unsigned __int16 **
0x180089e02  xor     r9d, r9d; int *
0x180089e05  xor     r8d, r8d; unsigned int
0x180089e08  call    ?GetDomainWithHostFallbackFromUri@@YAJPEAUIUri@@PEAPEAGKPEAH@Z; GetDomainWithHostFallbackFromUri(IUri *,ushort * *,ulong,int *)
0x180089e0d  test    eax, eax
0x180089e0f  jnz     loc_180089EB5
0x180089e15  mov     rax, [rbp+bstrString]
0x180089e19  lea     r9, [rbp+var_28]
0x180089e1d  mov     rcx, cs:?IEVALUE_LCIE_TabProcConfig_Value@SettingStore@@3U?$EXTVALUE1ID@K@1@B; SettingStore::EXTVALUE1ID<ulong> const SettingStore::IEVALUE_LCIE_TabProcConfig_Value
0x180089e24  mov     ebx, 1
0x180089e29  mov     [rsp+78h+var_38], rax
0x180089e2e  mov     r8d, ebx
0x180089e31  mov     [rsp+78h+var_40], ebx
0x180089e35  mov     [rsp+78h+var_48], r13
0x180089e3a  mov     [rsp+78h+var_50], r13
0x180089e3f  lea     edx, [rbx+7]
0x180089e42  mov     [rsp+78h+var_58], 4
0x180089e4a  call    cs:__imp_GetExtValue
0x180089e50  test    eax, eax
0x180089e52  js      short loc_180089EB5
0x180089e54  mov     ecx, 10000015h
0x180089e59  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180089e5f  mov     ecx, [rbp+var_28]
0x180089e62  test    al, al
0x180089e64  jz      short loc_180089E9C
0x180089e66  bt      ecx, 0Ah
0x180089e6a  jnb     short loc_180089E9C
0x180089e6c  and     ecx, 0FFFFF980h
0x180089e72  mov     [rbp+var_28], ecx
0x180089e75  bt      ecx, 8
0x180089e79  jnb     short loc_180089E97
0x180089e7b  mov     ecx, 1000003Fh
0x180089e80  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180089e86  mov     cl, al; bool
0x180089e88  call    ?IsoGetLRACPIC@@YAK_N@Z; IsoGetLRACPIC(bool)
0x180089e8d  mov     ecx, [rbp+var_28]
0x180089e90  or      ecx, eax
0x180089e92  mov     [rbp+var_28], ecx
0x180089e95  jmp     short loc_180089E9C
0x180089e97  mov     ecx, ebx
0x180089e99  mov     [rbp+var_28], ebx
0x180089e9c  test    ecx, 0FFFFE080h
0x180089ea2  jnz     short loc_180089EB1
0x180089ea4  movzx   eax, cl
0x180089ea7  and     eax, 7Fh
0x180089eaa  sub     eax, ebx
0x180089eac  cmp     eax, 7Bh ; '{'
0x180089eaf  jbe     short loc_180089EB5
0x180089eb1  mov     [rbp+var_28], r13d
0x180089eb5  mov     rcx, [rbp+bstrString]; bstrString
0x180089eb9  call    cs:__imp_SysFreeString
0x180089ebf  call    cs:__imp_?IsBrowserProcess@@YAHXZ; IsBrowserProcess(void)
0x180089ec5  mov     rbx, [rbp+arg_20]
0x180089ec9  test    eax, eax
0x180089ecb  jz      short loc_180089EFC
0x180089ecd  mov     ecx, 1000001Ah
0x180089ed2  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180089ed8  test    al, al
0x180089eda  jnz     short loc_180089EE8
0x180089edc  mov     ecx, edi
0x180089ede  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180089ee4  test    al, al
0x180089ee6  jz      short loc_180089EFC
0x180089ee8  mov     rcx, [rbp+ppURI]
0x180089eec  mov     r9, rsi
0x180089eef  mov     r8d, r12d
0x180089ef2  mov     edx, r15d
0x180089ef5  call    IsProtectedModeIUri
0x180089efa  jmp     short loc_180089F1C
0x180089efc  call    cs:__imp_?IsProtectedModeEnabledForIE@@YAHXZ; IsProtectedModeEnabledForIE(void)
0x180089f02  test    eax, eax
0x180089f04  jz      loc_18008A000
0x180089f0a  mov     rcx, [rbp+ppURI]
0x180089f0e  mov     r9, rsi
0x180089f11  mov     r8d, r12d
0x180089f14  mov     edx, r15d
0x180089f17  call    IsProtectedModeIUriInternal
0x180089f1c  mov     r15d, 1
0x180089f22  mov     edi, eax
0x180089f24  cmp     eax, r15d
0x180089f27  jz      loc_18008A000
0x180089f2d  test    eax, eax
0x180089f2f  jnz     loc_180089FF4
0x180089f35  cmp     cs:dword_18015EB64, 7Ch ; '|'
0x180089f3c  jnb     short loc_180089F59
0x180089f3e  mov     rcx, [rbp+ppURI]; struct IUri *
0x180089f42  call    ?IsProtectedModeNeutralIUri@@YAHPEAUIUri@@@Z; IsProtectedModeNeutralIUri(IUri *)
0x180089f47  test    eax, eax
0x180089f49  jz      short loc_180089F59
0x180089f4b  mov     al, byte ptr cs:dword_18015EB64
0x180089f51  and     eax, 7Fh
0x180089f54  jmp     loc_180089FF0
0x180089f59  mov     ecx, 1000004Ah
0x180089f5e  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180089f64  test    al, al
0x180089f66  jnz     short loc_180089FAB
0x180089f68  mov     rcx, cs:?FEATURE_EPM_SPECIAL_FOLDER_LOWIL@FCK@@3VCFeatureControlKey@@A; CFeatureControlKey FCK::FEATURE_EPM_SPECIAL_FOLDER_LOWIL
0x180089f6f  test    rcx, rcx
0x180089f72  jz      short loc_180089F94
0x180089f74  mov     edx, r15d
0x180089f77  call    cs:__imp_CoInternetIsFeatureEnabledInternalEx
0x180089f7d  test    eax, eax
0x180089f7f  js      short loc_180089FB2
0x180089f81  mov     ecx, r13d
0x180089f84  setz    cl
0x180089f87  mov     cs:dword_180159CE8, ecx
0x180089f8d  mov     cs:?FEATURE_EPM_SPECIAL_FOLDER_LOWIL@FCK@@3VCFeatureControlKey@@A, r13; CFeatureControlKey FCK::FEATURE_EPM_SPECIAL_FOLDER_LOWIL
0x180089f94  mov     eax, cs:dword_180159CE8
0x180089f9a  test    eax, eax
0x180089f9c  jz      short loc_180089FB2
0x180089f9e  mov     rcx, [rbp+ppURI]; struct IUri *
0x180089fa2  call    _IsUriFileInSpecialFolder
0x180089fa7  test    eax, eax
0x180089fa9  jnz     short loc_180089FB2
0x180089fab  mov     eax, 7Bh ; '{'
0x180089fb0  jmp     short loc_180089FF0
0x180089fb2  mov     rcx, [rbp+ppURI]
0x180089fb6  lea     r8, [rbp+bstrString]
0x180089fba  mov     r9, rsi
0x180089fbd  mov     dword ptr [rbp+bstrString], r13d
0x180089fc1  mov     edx, r12d
0x180089fc4  call    IEGetZoneIUri
0x180089fc9  mov     edi, eax
0x180089fcb  test    eax, eax
0x180089fcd  js      short loc_180089FED
0x180089fcf  mov     eax, dword ptr [rbp+bstrString]
0x180089fd2  dec     eax
0x180089fd4  cmp     eax, r15d
0x180089fd7  ja      short loc_180089FED
0x180089fd9  mov     ecx, 1000003Fh
0x180089fde  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180089fe4  mov     cl, al; bool
0x180089fe6  call    ?IsoGetLRACPIC@@YAK_N@Z; IsoGetLRACPIC(bool)
0x180089feb  jmp     short loc_180089FF0
0x180089fed  mov     eax, r15d
0x180089ff0  mov     [rbx], eax
0x180089ff2  jmp     short loc_18008A02C
0x180089ff4  test    edi, edi
0x180089ff6  mov     eax, 80004005h
0x180089ffb  cmovns  edi, eax
0x180089ffe  jmp     short loc_18008A02C
0x18008a000  xor     ecx, ecx
0x18008a002  mov     edi, r13d
0x18008a005  call    ?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z; IsoGetIntegrity(ulong)
0x18008a00a  and     eax, 47Fh
0x18008a00f  mov     [rbx], eax
0x18008a011  and     r14d, 7Fh
0x18008a015  jbe     short loc_18008A02C
0x18008a017  cmp     r14d, eax
0x18008a01a  jnb     short loc_18008A02C
0x18008a01c  mov     rcx, [rbp+ppURI]; struct IUri *
0x18008a020  call    ?IsProtectedModeNeutralIUri@@YAHPEAUIUri@@@Z; IsProtectedModeNeutralIUri(IUri *)
0x18008a025  test    eax, eax
0x18008a027  jz      short loc_18008A02C
0x18008a029  mov     [rbx], r14d
0x18008a02c  mov     ecx, [rbp+var_28]
0x18008a02f  test    ecx, ecx
0x18008a031  jz      short loc_18008A059
0x18008a033  mov     dl, [rbx]
0x18008a035  mov     al, cl
0x18008a037  and     dl, 7Fh
0x18008a03a  and     al, 7Fh
0x18008a03c  cmp     al, dl
0x18008a03e  jbe     short loc_18008A044
0x18008a040  mov     [rbx], ecx
0x18008a042  jmp     short loc_18008A059
0x18008a044  cmp     dl, 7Bh ; '{'
0x18008a047  sbb     eax, eax
0x18008a049  and     eax, 0FFFFFF00h
0x18008a04e  add     eax, 17Fh
0x18008a053  not     eax
0x18008a055  and     eax, ecx
0x18008a057  or      [rbx], eax
0x18008a059  call    ?IsOs_Win8OrGreater@@YA_NXZ; IsOs_Win8OrGreater(void)
0x18008a05e  test    al, al
0x18008a060  jnz     short loc_18008A070
0x18008a062  mov     al, [rbx]
0x18008a064  and     al, 7Fh
0x18008a066  cmp     al, 7Bh ; '{'
0x18008a068  jnb     short loc_18008A070
0x18008a06a  mov     dword ptr [rbx], 7Bh ; '{'
0x18008a070  mov     al, [rbx]
0x18008a072  and     al, 7Fh
0x18008a074  cmp     al, 7Bh ; '{'
0x18008a076  jnb     loc_18008A123
0x18008a07c  mov     ecx, 1000001Ah
0x18008a081  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18008a087  test    al, al
0x18008a089  jnz     short loc_18008A09E
0x18008a08b  mov     ecx, 10000019h
0x18008a090  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18008a096  test    al, al
0x18008a098  jz      loc_18008A123
0x18008a09e  mov     ecx, 10000049h
0x18008a0a3  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18008a0a9  test    al, al
0x18008a0ab  jz      short loc_18008A123
0x18008a0ad  mov     ecx, 10000015h
0x18008a0b2  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18008a0b8  test    al, al
0x18008a0ba  jnz     short loc_18008A123
0x18008a0bc  mov     rcx, [rbp+ppURI]
0x18008a0c0  lea     rdx, [rbp+bstrString]
0x18008a0c4  mov     dword ptr [rbp+bstrString], r13d
  ... truncated ...
```
