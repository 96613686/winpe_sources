# LCIEGetPersistentPolicyForUrl

- ea: `0x18008f954`
- end: `0x18009001c`
- name: `LCIEGetPersistentPolicyForUrl`
- size: `1736`
- prototype: `__int64 __fastcall(LPCWSTR pwzURI, unsigned int, unsigned int, char, _DWORD *, BSTR bstrString)`
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18011b51c`
- `0x18011bb30`

## callees

- `0x1800052d8`
- `0x18003e100`
- `0x18008aa60`
- `0x18008efc4`
- `0x18008f954`
- `0x180090024`
- `0x180090068`
- `0x1800a24d4`
- `0x1800afb80`
- `0x1800b00f0`
- `0x1800b0170`
- `0x1800fe9d0`
- `0x1800fedb0`
- `0x1800ff040`
- `0x180113b3c`
- `0x18011bee0`
- `0x18011bf3c`
- `0x180129010`

## import_xrefs

- `iertutil!CreateUri` at `0x18008f9f8`
- `iertutil!CreateUri` at `0x18008f9f8`
- `iertutil!__imp_?IsProtectedModeEnabledForIE@@YAHXZ` at `0x18008fc02`
- `iertutil!__imp_?IsProtectedModeEnabledForIE@@YAHXZ` at `0x18008fc02`
- `iertutil!__imp_?IsBrowserProcess@@YAHXZ` at `0x18008fbb3`
- `iertutil!__imp_?IsBrowserProcess@@YAHXZ` at `0x18008fbb3`
- `iertutil!__imp_GetExtValue` at `0x18008fb26`
- `iertutil!__imp_GetExtValue` at `0x18008fb26`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008f9a4`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008fa57`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008fa6e`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008fa87`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008fa9c`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008fb3b`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008fb68`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008fbcc`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008fbde`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008fc61`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008fcba`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008fd65`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008fd7a`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008fd93`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008fda8`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008fe28`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008fe3d`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008fe52`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008fe67`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008fe93`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008feaf`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008fec8`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008fee1`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008ff88`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008ff9b`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008f9a4`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008fa57`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008fa6e`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008fa87`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008fa9c`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008fb3b`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008fb68`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008fbcc`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008fbde`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008fc61`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008fcba`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008fd65`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008fd7a`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008fd93`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008fda8`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008fe28`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008fe3d`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008fe52`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008fe67`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008fe93`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008feaf`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008fec8`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008fee1`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008ff88`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18008ff9b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18008ff20`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18008ff20`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18008ff50`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18008ffd4`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18008ff50`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18008ffd4`
- `OLEAUT32!__imp_SysFreeString` at `0x18008fba7`
- `OLEAUT32!__imp_SysFreeString` at `0x18008fba7`

## pseudocode

```c
__int64 __fastcall LCIEGetPersistentPolicyForUrl(
        LPCWSTR pwzURI,
        int a2,
        unsigned int a3,
        char a4,
        _DWORD *a5,
        BSTR bstrString)
{
  BSTR v10; // rsi
  int v11; // edi
  DWORD v12; // eax
  int DomainWithHostFallbackFromUri; // eax
  char Bool; // al
  int v15; // ecx
  char v16; // al
  int v17; // eax
  int LRACPIC; // eax
  CFeatureControlKey *v19; // rcx
  char v20; // al
  unsigned int v21; // eax
  unsigned int v22; // r14d
  unsigned __int8 v23; // dl
  char v24; // si
  bool v25; // r14
  struct IsoScope *DefaultScope; // rax
  DWORD v27; // eax
  _WORD *Value; // rax
  int v30; // [rsp+50h] [rbp-28h] BYREF
  int v31; // [rsp+54h] [rbp-24h] BYREF
  int v32; // [rsp+58h] [rbp-20h] BYREF
  int v33; // [rsp+5Ch] [rbp-1Ch] BYREF
  int v34; // [rsp+60h] [rbp-18h] BYREF
  int v35; // [rsp+64h] [rbp-14h] BYREF
  IUri *ppURI; // [rsp+68h] [rbp-10h] BYREF

  v30 = 0;
  if ( !dword_18016BC1C )
    dword_18016BC1C = IsoGetIntegrity(1u);
  v10 = bstrString;
  if ( bstrString )
    *(_DWORD *)bstrString = 0;
  if ( (unsigned __int8)IEConfiguration_GetBool(268435526) )
  {
    v11 = 0;
    *a5 = IsoGetIntegrity(0) & 0x47F;
    return (unsigned int)v11;
  }
  v32 = 0;
  v31 = -1;
  ppURI = 0;
  v12 = HelperAddUriDefaultFlags(50342784, 4u);
  v11 = CreateUri(pwzURI, v12, 0, &ppURI);
  if ( v11 >= 0 )
  {
    v11 = ((__int64 (__fastcall *)(IUri *, int *))ppURI->lpVtbl->GetScheme)(ppURI, &v31);
    if ( v11 >= 0 )
    {
      v11 = ((__int64 (__fastcall *)(IUri *, __int64, int *))ppURI->lpVtbl->HasProperty)(ppURI, 6, &v32);
      if ( v11 >= 0 )
      {
        if ( ((unsigned __int8)IEConfiguration_GetBool(268435482) || (unsigned __int8)IEConfiguration_GetBool(268435481))
          && ((unsigned __int8)IEConfiguration_GetBool(268435529) || (unsigned __int8)IEConfiguration_GetBool(268435479)) )
        {
          bstrString = 0;
          if ( v31 != 9 || v32 )
            DomainWithHostFallbackFromUri = GetDomainWithHostFallbackFromUri(ppURI, &bstrString, 0, 0);
          else
            DomainWithHostFallbackFromUri = ((__int64 (__fastcall *)(IUri *, BSTR *))ppURI->lpVtbl->GetAbsoluteUri)(
                                              ppURI,
                                              &bstrString);
          if ( !DomainWithHostFallbackFromUri
            && (int)GetExtValue((__int64 *)SettingStore::IEVALUE_LCIE_TabProcConfig_Value[0], 8, 1, &v30) >= 0 )
          {
            Bool = IEConfiguration_GetBool(268435477);
            v15 = v30;
            if ( Bool && (v30 & 0x400) != 0 )
            {
              v30 &= 0xFFFFF980;
              if ( (v15 & 0x100) != 0 )
              {
                v16 = IEConfiguration_GetBool(268435519);
                v15 = IsoGetLRACPIC(v16) | v30;
                v30 = v15;
              }
              else
              {
                v15 = 1;
                v30 = 1;
              }
            }
            if ( (v15 & 0xFFFFE080) != 0 || (v15 & 0x7Fu) - 1 > 0x7B )
              v30 = 0;
          }
          SysFreeString(bstrString);
        }
        if ( IsBrowserProcess()
          && ((unsigned __int8)IEConfiguration_GetBool(268435482) || (unsigned __int8)IEConfiguration_GetBool(268435481)) )
        {
          v17 = IsProtectedModeIUri(ppURI, a2, a3, v10);
        }
        else
        {
          if ( !IsProtectedModeEnabledForIE() )
            goto LABEL_52;
          v17 = IsProtectedModeIUriInternal(ppURI, a2, a3, v10);
        }
        v11 = v17;
        if ( v17 != 1 )
        {
          if ( v17 )
          {
            if ( v17 >= 0 )
              v11 = -2147467259;
          }
          else
          {
            if ( (unsigned int)dword_18016BC1C < 0x7C && (unsigned int)IsProtectedModeNeutralIUri(ppURI) )
            {
              LRACPIC = dword_18016BC1C & 0x7F;
            }
            else if ( !(unsigned __int8)IEConfiguration_GetBool(268435530)
                   && ((unsigned int)CFeatureControlKey::_CoInternetIsFeatureEnabledInternalEx(v19)
                    || (unsigned int)IsUriFileInSpecialFolder(ppURI)) )
            {
              LODWORD(bstrString) = 0;
              v11 = IEGetZoneIUri((__int64)ppURI, a3, (__int64)&bstrString, (int *)v10);
              if ( v11 < 0 || (unsigned int)((_DWORD)bstrString - 1) > 1 )
              {
                LRACPIC = 1;
              }
              else
              {
                v20 = IEConfiguration_GetBool(268435519);
                LRACPIC = IsoGetLRACPIC(v20);
              }
            }
            else
            {
              LRACPIC = 123;
            }
            *a5 = LRACPIC;
          }
LABEL_56:
          if ( v30 )
          {
            v23 = *(_BYTE *)a5 & 0x7F;
            if ( (unsigned __int8)(v30 & 0x7F) <= v23 )
              *a5 |= v30 & ~(v23 < 0x7Bu ? 127 : 383);
            else
              *a5 = v30;
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
            v33 = 0;
            v35 = 0;
            if ( ((unsigned int)ShouldRestrictEPMForDomain((__int64)ppURI, &bstrString) || !(_DWORD)bstrString)
              && ((unsigned int)ShouldUriBeInEMIE((__int64)ppURI, &v33, &v35) || !v33) )
            {
              if ( !(unsigned int)ShouldRestrictEPMNotificationsForDomain((__int64)ppURI, &bstrString)
                && (_DWORD)bstrString )
              {
                *a5 |= 0x200u;
              }
            }
            else
            {
              *a5 &= 0xFFFFFEFB;
              *a5 |= 0x47Bu;
            }
          }
          v34 = 0;
          if ( ((unsigned __int8)IEConfiguration_GetBool(268435482)
             || (unsigned __int8)IEConfiguration_GetBool(268435481))
            && (unsigned __int8)IEConfiguration_GetBool(268435529)
            && !(unsigned __int8)IEConfiguration_GetBool(268435477) )
          {
            IsDomainSandboxNeutral((__int64)ppURI, &v34);
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
                        InitOnceExecuteOnce(&g_InitOnce, (PINIT_ONCE_FN)LoadIsoDll, 0, 0);
                        v24 = 1;
                        v25 = (unsigned int)((__int64 (__fastcall *)(__int64))qword_1801810D0)(256) == 0;
                      }
                    }
                  }
                }
              }
            }
          }
          if ( v34 )
          {
            *a5 |= 0x2000u;
            if ( !v25
              && !(unsigned __int8)IEConfiguration_GetBool(536870913)
              && (unsigned __int8)IEConfiguration_GetBool(536870914) )
            {
              *a5 &= 0xFFFFFB80;
              *a5 |= dword_18016BC1C;
            }
          }
          else if ( v24 )
          {
            InitOnceExecuteOnce(&g_InitOnce, (PINIT_ONCE_FN)LoadIsoDll, 0, 0);
            ((void (__fastcall *)(_QWORD, __int64))qword_1801810C8)(0, 8);
          }
          goto LABEL_96;
        }
LABEL_52:
        v11 = 0;
        v21 = IsoGetIntegrity(0) & 0x47F;
        *a5 = v21;
        v22 = a4 & 0x7F;
        if ( v22 && v22 < v21 && (unsigned int)IsProtectedModeNeutralIUri(ppURI) )
          *a5 = v22;
        goto LABEL_56;
      }
    }
  }
LABEL_96:
  if ( ppURI )
    ((void (__fastcall *)(IUri *))ppURI->lpVtbl->Release)(ppURI);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18008f954  push    rbp
0x18008f956  push    rbx
0x18008f957  push    rsi
0x18008f958  push    rdi
0x18008f959  push    r12
0x18008f95b  push    r13
0x18008f95d  push    r14
0x18008f95f  push    r15
0x18008f961  mov     rbp, rsp
0x18008f964  sub     rsp, 78h
0x18008f968  xor     r13d, r13d
0x18008f96b  mov     r14d, r9d
0x18008f96e  cmp     cs:dword_18016BC1C, r13d
0x18008f975  mov     r12d, r8d
0x18008f978  mov     r15d, edx
0x18008f97b  mov     [rbp+var_28], r13d
0x18008f97f  mov     rbx, rcx
0x18008f982  jnz     short loc_18008F993
0x18008f984  lea     ecx, [r13+1]
0x18008f988  call    ?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z; IsoGetIntegrity(ulong)
0x18008f98d  mov     cs:dword_18016BC1C, eax
0x18008f993  mov     rsi, [rbp+bstrString]
0x18008f997  test    rsi, rsi
0x18008f99a  jz      short loc_18008F99F
0x18008f99c  mov     [rsi], r13d
0x18008f99f  mov     ecx, 10000046h
0x18008f9a4  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18008f9ab  nop     dword ptr [rax+rax+00h]
0x18008f9b0  test    al, al
0x18008f9b2  jz      short loc_18008F9CE
0x18008f9b4  xor     ecx, ecx
0x18008f9b6  mov     edi, r13d
0x18008f9b9  call    ?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z; IsoGetIntegrity(ulong)
0x18008f9be  mov     rcx, [rbp+arg_20]
0x18008f9c2  and     eax, 47Fh
0x18008f9c7  mov     [rcx], eax
0x18008f9c9  jmp     loc_180090008
0x18008f9ce  mov     edx, 4; unsigned int
0x18008f9d3  mov     [rbp+var_20], r13d
0x18008f9d7  mov     ecx, 3002B80h; unsigned int
0x18008f9dc  mov     [rbp+var_24], 0FFFFFFFFh
0x18008f9e3  mov     [rbp+ppURI], r13
0x18008f9e7  call    ?HelperAddUriDefaultFlags@@YAKKK@Z; HelperAddUriDefaultFlags(ulong,ulong)
0x18008f9ec  mov     edx, eax; dwFlags
0x18008f9ee  lea     r9, [rbp+ppURI]; ppURI
0x18008f9f2  mov     rcx, rbx; pwzURI
0x18008f9f5  xor     r8d, r8d; dwReserved
0x18008f9f8  call    cs:__imp_CreateUri
0x18008f9ff  nop     dword ptr [rax+rax+00h]
0x18008fa04  mov     edi, eax
0x18008fa06  test    eax, eax
0x18008fa08  js      loc_18008FFF3
0x18008fa0e  mov     rcx, [rbp+ppURI]
0x18008fa12  lea     rdx, [rbp+var_24]
0x18008fa16  mov     rax, [rcx]
0x18008fa19  mov     rax, [rax+0C0h]
0x18008fa20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fa25  mov     edi, eax
0x18008fa27  test    eax, eax
0x18008fa29  js      loc_18008FFF3
0x18008fa2f  mov     rcx, [rbp+ppURI]
0x18008fa33  lea     r8, [rbp+var_20]
0x18008fa37  mov     edx, 6
0x18008fa3c  mov     rax, [rcx]
0x18008fa3f  mov     rax, [rax+30h]
0x18008fa43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fa48  mov     edi, eax
0x18008fa4a  test    eax, eax
0x18008fa4c  js      loc_18008FFF3
0x18008fa52  mov     ecx, 1000001Ah
0x18008fa57  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18008fa5e  nop     dword ptr [rax+rax+00h]
0x18008fa63  mov     edi, 10000019h
0x18008fa68  test    al, al
0x18008fa6a  jnz     short loc_18008FA82
0x18008fa6c  mov     ecx, edi
0x18008fa6e  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18008fa75  nop     dword ptr [rax+rax+00h]
0x18008fa7a  test    al, al
0x18008fa7c  jz      loc_18008FBB3
0x18008fa82  mov     ecx, 10000049h
0x18008fa87  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18008fa8e  nop     dword ptr [rax+rax+00h]
0x18008fa93  test    al, al
0x18008fa95  jnz     short loc_18008FAB0
0x18008fa97  mov     ecx, 10000017h
0x18008fa9c  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18008faa3  nop     dword ptr [rax+rax+00h]
0x18008faa8  test    al, al
0x18008faaa  jz      loc_18008FBB3
0x18008fab0  cmp     [rbp+var_24], 9
0x18008fab4  mov     [rbp+bstrString], r13
0x18008fab8  jnz     short loc_18008FAD6
0x18008faba  cmp     [rbp+var_20], r13d
0x18008fabe  jnz     short loc_18008FAD6
0x18008fac0  mov     rcx, [rbp+ppURI]
0x18008fac4  lea     rdx, [rbp+bstrString]
0x18008fac8  mov     rax, [rcx]
0x18008facb  mov     rax, [rax+38h]
0x18008facf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fad4  jmp     short loc_18008FAE9
0x18008fad6  mov     rcx, [rbp+ppURI]; struct IUri *
0x18008fada  lea     rdx, [rbp+bstrString]; unsigned __int16 **
0x18008fade  xor     r9d, r9d; int *
0x18008fae1  xor     r8d, r8d; unsigned int
0x18008fae4  call    ?GetDomainWithHostFallbackFromUri@@YAJPEAUIUri@@PEAPEAGKPEAH@Z; GetDomainWithHostFallbackFromUri(IUri *,ushort * *,ulong,int *)
0x18008fae9  test    eax, eax
0x18008faeb  jnz     loc_18008FBA3
0x18008faf1  mov     rax, [rbp+bstrString]
0x18008faf5  lea     r9, [rbp+var_28]
0x18008faf9  mov     rcx, cs:?IEVALUE_LCIE_TabProcConfig_Value@SettingStore@@3U?$EXTVALUE1ID@K@1@B; SettingStore::EXTVALUE1ID<ulong> const SettingStore::IEVALUE_LCIE_TabProcConfig_Value
0x18008fb00  mov     ebx, 1
0x18008fb05  mov     [rsp+78h+var_38], rax
0x18008fb0a  mov     r8d, ebx
0x18008fb0d  mov     [rsp+78h+var_40], ebx
0x18008fb11  mov     [rsp+78h+var_48], r13
0x18008fb16  mov     [rsp+78h+var_50], r13
0x18008fb1b  lea     edx, [rbx+7]
0x18008fb1e  mov     [rsp+78h+var_58], 4
0x18008fb26  call    cs:__imp_GetExtValue
0x18008fb2d  nop     dword ptr [rax+rax+00h]
0x18008fb32  test    eax, eax
0x18008fb34  js      short loc_18008FBA3
0x18008fb36  mov     ecx, 10000015h
0x18008fb3b  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18008fb42  nop     dword ptr [rax+rax+00h]
0x18008fb47  mov     ecx, [rbp+var_28]
0x18008fb4a  test    al, al
0x18008fb4c  jz      short loc_18008FB8A
0x18008fb4e  bt      ecx, 0Ah
0x18008fb52  jnb     short loc_18008FB8A
0x18008fb54  and     ecx, 0FFFFF980h
0x18008fb5a  mov     [rbp+var_28], ecx
0x18008fb5d  bt      ecx, 8
0x18008fb61  jnb     short loc_18008FB85
0x18008fb63  mov     ecx, 1000003Fh
0x18008fb68  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18008fb6f  nop     dword ptr [rax+rax+00h]
0x18008fb74  mov     cl, al; bool
0x18008fb76  call    ?IsoGetLRACPIC@@YAK_N@Z; IsoGetLRACPIC(bool)
0x18008fb7b  mov     ecx, [rbp+var_28]
0x18008fb7e  or      ecx, eax
0x18008fb80  mov     [rbp+var_28], ecx
0x18008fb83  jmp     short loc_18008FB8A
0x18008fb85  mov     ecx, ebx
0x18008fb87  mov     [rbp+var_28], ebx
0x18008fb8a  test    ecx, 0FFFFE080h
0x18008fb90  jnz     short loc_18008FB9F
0x18008fb92  movzx   eax, cl
0x18008fb95  and     eax, 7Fh
0x18008fb98  sub     eax, ebx
0x18008fb9a  cmp     eax, 7Bh ; '{'
0x18008fb9d  jbe     short loc_18008FBA3
0x18008fb9f  mov     [rbp+var_28], r13d
0x18008fba3  mov     rcx, [rbp+bstrString]; bstrString
0x18008fba7  call    cs:__imp_SysFreeString
0x18008fbae  nop     dword ptr [rax+rax+00h]
0x18008fbb3  call    cs:__imp_?IsBrowserProcess@@YAHXZ; IsBrowserProcess(void)
0x18008fbba  nop     dword ptr [rax+rax+00h]
0x18008fbbf  mov     rbx, [rbp+arg_20]
0x18008fbc3  test    eax, eax
0x18008fbc5  jz      short loc_18008FC02
0x18008fbc7  mov     ecx, 1000001Ah
0x18008fbcc  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18008fbd3  nop     dword ptr [rax+rax+00h]
0x18008fbd8  test    al, al
0x18008fbda  jnz     short loc_18008FBEE
0x18008fbdc  mov     ecx, edi
0x18008fbde  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18008fbe5  nop     dword ptr [rax+rax+00h]
0x18008fbea  test    al, al
0x18008fbec  jz      short loc_18008FC02
0x18008fbee  mov     rcx, [rbp+ppURI]
0x18008fbf2  mov     r9, rsi
0x18008fbf5  mov     r8d, r12d
0x18008fbf8  mov     edx, r15d
0x18008fbfb  call    IsProtectedModeIUri
0x18008fc00  jmp     short loc_18008FC28
0x18008fc02  call    cs:__imp_?IsProtectedModeEnabledForIE@@YAHXZ; IsProtectedModeEnabledForIE(void)
0x18008fc09  nop     dword ptr [rax+rax+00h]
0x18008fc0e  test    eax, eax
0x18008fc10  jz      loc_18008FCE4
0x18008fc16  mov     rcx, [rbp+ppURI]
0x18008fc1a  mov     r9, rsi
0x18008fc1d  mov     r8d, r12d
0x18008fc20  mov     edx, r15d
0x18008fc23  call    IsProtectedModeIUriInternal
0x18008fc28  mov     edi, eax
0x18008fc2a  cmp     eax, 1
0x18008fc2d  jz      loc_18008FCE4
0x18008fc33  test    eax, eax
0x18008fc35  jnz     loc_18008FCD8
0x18008fc3b  cmp     cs:dword_18016BC1C, 7Ch ; '|'
0x18008fc42  jnb     short loc_18008FC5C
0x18008fc44  mov     rcx, [rbp+ppURI]; struct IUri *
0x18008fc48  call    ?IsProtectedModeNeutralIUri@@YAHPEAUIUri@@@Z; IsProtectedModeNeutralIUri(IUri *)
0x18008fc4d  test    eax, eax
0x18008fc4f  jz      short loc_18008FC5C
0x18008fc51  mov     al, byte ptr cs:dword_18016BC1C
0x18008fc57  and     eax, 7Fh
0x18008fc5a  jmp     short loc_18008FCD4
0x18008fc5c  mov     ecx, 1000004Ah
0x18008fc61  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18008fc68  nop     dword ptr [rax+rax+00h]
0x18008fc6d  test    al, al
0x18008fc6f  jnz     short loc_18008FC87
0x18008fc71  call    ?_CoInternetIsFeatureEnabledInternalEx@CFeatureControlKey@@QEAAJH@Z; CFeatureControlKey::_CoInternetIsFeatureEnabledInternalEx(int)
0x18008fc76  test    eax, eax
0x18008fc78  jnz     short loc_18008FC8E
0x18008fc7a  mov     rcx, [rbp+ppURI]; struct IUri *
0x18008fc7e  call    _IsUriFileInSpecialFolder
0x18008fc83  test    eax, eax
0x18008fc85  jnz     short loc_18008FC8E
0x18008fc87  mov     eax, 7Bh ; '{'
0x18008fc8c  jmp     short loc_18008FCD4
0x18008fc8e  mov     rcx, [rbp+ppURI]
0x18008fc92  lea     r8, [rbp+bstrString]
0x18008fc96  mov     r9, rsi
0x18008fc99  mov     dword ptr [rbp+bstrString], r13d
0x18008fc9d  mov     edx, r12d
0x18008fca0  call    IEGetZoneIUri
0x18008fca5  mov     edi, eax
0x18008fca7  test    eax, eax
0x18008fca9  js      short loc_18008FCCF
0x18008fcab  mov     eax, dword ptr [rbp+bstrString]
0x18008fcae  dec     eax
0x18008fcb0  cmp     eax, 1
0x18008fcb3  ja      short loc_18008FCCF
0x18008fcb5  mov     ecx, 1000003Fh
0x18008fcba  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18008fcc1  nop     dword ptr [rax+rax+00h]
0x18008fcc6  mov     cl, al; bool
0x18008fcc8  call    ?IsoGetLRACPIC@@YAK_N@Z; IsoGetLRACPIC(bool)
0x18008fccd  jmp     short loc_18008FCD4
0x18008fccf  mov     eax, 1
0x18008fcd4  mov     [rbx], eax
0x18008fcd6  jmp     short loc_18008FD10
0x18008fcd8  test    edi, edi
0x18008fcda  mov     eax, 80004005h
0x18008fcdf  cmovns  edi, eax
0x18008fce2  jmp     short loc_18008FD10
0x18008fce4  xor     ecx, ecx
0x18008fce6  mov     edi, r13d
0x18008fce9  call    ?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z; IsoGetIntegrity(ulong)
0x18008fcee  and     eax, 47Fh
0x18008fcf3  mov     [rbx], eax
0x18008fcf5  and     r14d, 7Fh
0x18008fcf9  jbe     short loc_18008FD10
0x18008fcfb  cmp     r14d, eax
0x18008fcfe  jnb     short loc_18008FD10
0x18008fd00  mov     rcx, [rbp+ppURI]; struct IUri *
0x18008fd04  call    ?IsProtectedModeNeutralIUri@@YAHPEAUIUri@@@Z; IsProtectedModeNeutralIUri(IUri *)
0x18008fd09  test    eax, eax
0x18008fd0b  jz      short loc_18008FD10
0x18008fd0d  mov     [rbx], r14d
0x18008fd10  mov     ecx, [rbp+var_28]
0x18008fd13  test    ecx, ecx
0x18008fd15  jz      short loc_18008FD3D
0x18008fd17  mov     dl, [rbx]
0x18008fd19  mov     al, cl
0x18008fd1b  and     dl, 7Fh
0x18008fd1e  and     al, 7Fh
0x18008fd20  cmp     al, dl
0x18008fd22  jbe     short loc_18008FD28
0x18008fd24  mov     [rbx], ecx
0x18008fd26  jmp     short loc_18008FD3D
0x18008fd28  cmp     dl, 7Bh ; '{'
0x18008fd2b  sbb     eax, eax
0x18008fd2d  and     eax, 0FFFFFF00h
0x18008fd32  add     eax, 17Fh
0x18008fd37  not     eax
0x18008fd39  and     eax, ecx
0x18008fd3b  or      [rbx], eax
0x18008fd3d  call    ?IsOs_Win8OrGreater@@YA_NXZ; IsOs_Win8OrGreater(void)
0x18008fd42  test    al, al
0x18008fd44  jnz     short loc_18008FD54
0x18008fd46  mov     al, [rbx]
0x18008fd48  and     al, 7Fh
0x18008fd4a  cmp     al, 7Bh ; '{'
0x18008fd4c  jnb     short loc_18008FD54
0x18008fd4e  mov     dword ptr [rbx], 7Bh ; '{'
0x18008fd54  mov     al, [rbx]
0x18008fd56  and     al, 7Fh
0x18008fd58  cmp     al, 7Bh ; '{'
0x18008fd5a  jnb     loc_18008FE1F
0x18008fd60  mov     ecx, 1000001Ah
0x18008fd65  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18008fd6c  nop     dword ptr [rax+rax+00h]
0x18008fd71  test    al, al
0x18008fd73  jnz     short loc_18008FD8E
0x18008fd75  mov     ecx, 10000019h
0x18008fd7a  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18008fd81  nop     dword ptr [rax+rax+00h]
0x18008fd86  test    al, al
0x18008fd88  jz      loc_18008FE1F
0x18008fd8e  mov     ecx, 10000049h
0x18008fd93  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18008fd9a  nop     dword ptr [rax+rax+00h]
0x18008fd9f  test    al, al
0x18008fda1  jz      short loc_18008FE1F
  ... truncated ...
```
