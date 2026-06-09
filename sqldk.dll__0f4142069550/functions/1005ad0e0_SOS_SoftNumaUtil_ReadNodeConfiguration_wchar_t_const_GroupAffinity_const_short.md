# SOS_SoftNumaUtil::ReadNodeConfiguration(wchar_t const *,GroupAffinity * const,short *)

- ea: `0x1005ad0e0`
- end: `0x1005ad777`
- name: `?ReadNodeConfiguration@SOS_SoftNumaUtil@@SAXPEB_WQEAVGroupAffinity@@PEAF@Z`
- size: `1687`
- prototype: `void __fastcall(const wchar_t *, struct GroupAffinity *const, __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x100403070`
- `0x100404bf2`
- `0x100458050`
- `0x1004b3270`
- `0x1005ad0e0`
- `0x1005b1fc0`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x1005ad48a`
- `ADVAPI32!RegQueryValueExW` at `0x1005ad61d`
- `ADVAPI32!RegQueryValueExW` at `0x1005ad48a`
- `ADVAPI32!RegQueryValueExW` at `0x1005ad61d`
- `ADVAPI32!RegOpenKeyExW` at `0x1005ad34c`
- `ADVAPI32!RegOpenKeyExW` at `0x1005ad435`
- `ADVAPI32!RegOpenKeyExW` at `0x1005ad34c`
- `ADVAPI32!RegOpenKeyExW` at `0x1005ad435`
- `ADVAPI32!RegCloseKey` at `0x1005ad37f`
- `ADVAPI32!RegCloseKey` at `0x1005ad4ce`
- `ADVAPI32!RegCloseKey` at `0x1005ad699`
- `ADVAPI32!RegCloseKey` at `0x1005ad37f`
- `ADVAPI32!RegCloseKey` at `0x1005ad4ce`
- `ADVAPI32!RegCloseKey` at `0x1005ad699`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1005ad6c8`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1005ad6c8`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1005ad6d4`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1005ad6d4`

## string_xrefs

- `0x1005ad2e4`: `%ls\NodeConfiguration`
- `0x1005ad4b4`: `Detected error in soft-NUMA configuration at Node%u.\n`
- `0x1005ad3c7`: `%ls\NodeConfiguration\Node%d`
- `0x1005ad5d0`: `Detected error in soft-NUMA configuration. System: %u CPUs, configuration: %u CPUs.\n`

## pseudocode

```c
void __fastcall SOS_SoftNumaUtil::ReadNodeConfiguration(const wchar_t *a1, struct GroupAffinity *const a2, __int16 *a3)
{
  const wchar_t *v3; // rbx
  unsigned int v4; // esi
  __int16 v5; // r14
  __int64 v6; // r15
  HKEY v7; // rbx
  unsigned int v8; // eax
  unsigned int v9; // r12d
  LSTATUS v10; // eax
  unsigned __int16 v11; // bx
  __int64 v12; // r9
  unsigned __int64 *v13; // r8
  __int64 v14; // r11
  int v15; // r10d
  unsigned __int64 v16; // rdx
  struct GroupAffinity *v17; // rdi
  unsigned __int64 *v18; // r8
  unsigned __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rax
  __int128 *v23; // rax
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  __int128 v28; // xmm0
  __int128 v29; // xmm1
  __int128 v30; // xmm0
  __int128 v31; // xmm1
  LPDWORD lpcbData; // [rsp+28h] [rbp-D8h]
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cbData; // [rsp+3Ch] [rbp-C4h] BYREF
  DWORD Type; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v37; // [rsp+44h] [rbp-BCh] BYREF
  DWORD v38; // [rsp+48h] [rbp-B8h] BYREF
  BYTE v39[8]; // [rsp+50h] [rbp-B0h] BYREF
  const wchar_t *v40; // [rsp+58h] [rbp-A8h]
  struct GroupAffinity *v41; // [rsp+60h] [rbp-A0h]
  __int16 *v42; // [rsp+68h] [rbp-98h]
  _OWORD v43[8]; // [rsp+70h] [rbp-90h] BYREF
  _OWORD v44[64]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR SubKey[264]; // [rsp+4F0h] [rbp+3F0h] BYREF

  v42 = a3;
  v3 = a1;
  v41 = a2;
  v4 = 0;
  *a3 = 0;
  v40 = a1;
  memset(v44, 0, sizeof(v44));
  memset_0(SubKey, 0, 0x208u);
  if ( (int)StringCchPrintf_lW(SubKey, 0x104u, L"%ls\\NodeConfiguration", g_crtLocale, v3) < 0 )
    utassert_fail(1u, "SUCCEEDED(hr)", "sosnumap_ext.cpp", 340, 0);
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey) )
  {
    RegCloseKey(hKey);
    hKey = 0;
    memset(v43, 0, sizeof(v43));
    v5 = 0;
    v6 = 8;
    while ( 1 )
    {
      LODWORD(lpcbData) = v5;
      if ( (int)StringCchPrintf_lW(SubKey, 0x104u, L"%ls\\NodeConfiguration\\Node%d", g_crtLocale, v3, lpcbData) < 0 )
        utassert_fail(1u, "SUCCEEDED(hr)", "sosnumap_ext.cpp", 362, 0);
      if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey) )
        break;
      v7 = hKey;
      v8 = (*(__int64 (__fastcall **)(struct OsNumaConfig *))(*(_QWORD *)OsNumaConfig::sm_instance + 72LL))(OsNumaConfig::sm_instance);
      *(_DWORD *)Data = 0;
      v9 = v8;
      cbData = 4;
      v10 = RegQueryValueExW(v7, L"Group", 0, &Type, Data, &cbData);
      if ( v10 == 2 )
      {
        v11 = 0;
        *(_DWORD *)Data = 0;
      }
      else if ( v10 || Type != 4 || (v11 = *(_WORD *)Data, *(_DWORD *)Data >= v9) )
      {
LABEL_12:
        SOS_OS_LogUnlocalizedRoutine(L"Detected error in soft-NUMA configuration at Node%u.\n", (unsigned int)v5);
        v5 = 0;
        break;
      }
      *(_QWORD *)v39 = 0;
      v37 = 8;
      if ( RegQueryValueExW(hKey, L"CPUMask", 0, &v38, v39, &v37) )
        goto LABEL_12;
      v20 = *(_QWORD *)v39;
      if ( !*(_QWORD *)v39
        || (*(_QWORD *)v39 & *((_QWORD *)v43 + v11)) != 0
        || (*(_QWORD *)v39 & *((_QWORD *)&SOS_PublicGlobals::sm_osSystemAffinity + v11)) != *(_QWORD *)v39
        || ((v38 - 3) & 0xFFFFFFF6) != 0
        || v38 == 12 )
      {
        goto LABEL_12;
      }
      v21 = v5;
      *(_QWORD *)&v44[v21] = *(_QWORD *)v39;
      WORD4(v44[v21]) = v11;
      v22 = WORD4(v44[v5]);
      *((_QWORD *)v43 + v22) |= v20;
      RegCloseKey(hKey);
      v3 = v40;
      ++v5;
      hKey = 0;
      if ( v5 >= 64 )
        goto LABEL_15;
    }
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
LABEL_15:
    v12 = 16;
    v13 = (unsigned __int64 *)v43;
    v14 = 16;
    v15 = 0;
    do
    {
      v16 = *v13++;
      v15 += (unsigned int)((0x101010101010101LL
                           * ((((v16 - ((v16 >> 1) & 0x5555555555555555LL)) & 0x3333333333333333LL)
                             + (((v16 - ((v16 >> 1) & 0x5555555555555555LL)) >> 2) & 0x3333333333333333LL)
                             + ((((v16 - ((v16 >> 1) & 0x5555555555555555LL)) & 0x3333333333333333LL)
                               + (((v16 - ((v16 >> 1) & 0x5555555555555555LL)) >> 2) & 0x3333333333333333LL)) >> 4))
                            & 0xF0F0F0F0F0F0F0FLL)) >> 32) >> 24;
      --v14;
    }
    while ( v14 );
    v17 = v41;
    if ( v15 == (_DWORD)SOS_PublicGlobals::sm_cpuCount )
    {
      if ( v5 )
      {
        if ( v41 )
        {
          v23 = v44;
          do
          {
            v17 = (struct GroupAffinity *)((char *)v17 + 128);
            v24 = *v23;
            v25 = v23[1];
            v23 += 8;
            *((_OWORD *)v17 - 8) = v24;
            v26 = *(v23 - 6);
            *((_OWORD *)v17 - 7) = v25;
            v27 = *(v23 - 5);
            *((_OWORD *)v17 - 6) = v26;
            v28 = *(v23 - 4);
            *((_OWORD *)v17 - 5) = v27;
            v29 = *(v23 - 3);
            *((_OWORD *)v17 - 4) = v28;
            v30 = *(v23 - 2);
            *((_OWORD *)v17 - 3) = v29;
            v31 = *(v23 - 1);
            *((_OWORD *)v17 - 2) = v30;
            *((_OWORD *)v17 - 1) = v31;
            --v6;
          }
          while ( v6 );
        }
        else
        {
          *_errno() = 22;
          _invalid_parameter_noinfo();
        }
        *v42 = v5;
      }
    }
    else
    {
      v18 = (unsigned __int64 *)v43;
      do
      {
        v19 = *v18++;
        v4 += (unsigned int)((0x101010101010101LL
                            * ((((v19 - ((v19 >> 1) & 0x5555555555555555LL)) & 0x3333333333333333LL)
                              + (((v19 - ((v19 >> 1) & 0x5555555555555555LL)) >> 2) & 0x3333333333333333LL)
                              + ((((v19 - ((v19 >> 1) & 0x5555555555555555LL)) & 0x3333333333333333LL)
                                + (((v19 - ((v19 >> 1) & 0x5555555555555555LL)) >> 2) & 0x3333333333333333LL)) >> 4))
                             & 0xF0F0F0F0F0F0F0FLL)) >> 32) >> 24;
        --v12;
      }
      while ( v12 );
      SOS_OS_LogUnlocalizedRoutine(
        L"Detected error in soft-NUMA configuration. System: %u CPUs, configuration: %u CPUs.\n",
        (unsigned int)SOS_PublicGlobals::sm_cpuCount,
        v4);
    }
  }
}

```

## disassembly

```asm
0x1005ad0e0  push    rbp
0x1005ad0e2  push    rbx
0x1005ad0e3  push    rsi
0x1005ad0e4  push    rdi
0x1005ad0e5  lea     rbp, [rsp-628h]
0x1005ad0ed  sub     rsp, 728h
0x1005ad0f4  mov     rax, cs:__security_cookie
0x1005ad0fb  xor     rax, rsp
0x1005ad0fe  mov     [rbp+640h+var_40], rax
0x1005ad105  movups  xmm0, xmmword ptr cs:?sm_val@?$Zero@ULocaleEntry@?$XE_StaticPackage@$00@@@@2ULocaleEntry@?$XE_StaticPackage@$00@@B.Data1; XE_StaticPackage<1>::LocaleEntry const Zero<XE_StaticPackage<1>::LocaleEntry>::sm_val ...
0x1005ad10c  mov     [rsp+740h+var_6D8], r8
0x1005ad111  mov     rbx, rcx
0x1005ad114  mov     [rsp+740h+var_6E0], rdx
0x1005ad119  xor     esi, esi
0x1005ad11b  mov     [r8], si
0x1005ad11f  xor     edx, edx; Val
0x1005ad121  mov     [rsp+740h+var_6E8], rcx
0x1005ad126  mov     r8d, 208h; Size
0x1005ad12c  lea     rcx, [rbp+640h+SubKey]; void *
0x1005ad133  movaps  [rbp+640h+var_650], xmm0
0x1005ad137  movaps  [rbp+640h+var_640], xmm0
0x1005ad13b  movaps  [rbp+640h+var_630], xmm0
0x1005ad13f  movaps  [rbp+640h+var_620], xmm0
0x1005ad143  movaps  [rbp+640h+var_610], xmm0
0x1005ad147  movaps  [rbp+640h+var_600], xmm0
0x1005ad14b  movaps  [rbp+640h+var_5F0], xmm0
0x1005ad14f  movaps  [rbp+640h+var_5E0], xmm0
0x1005ad153  movaps  [rbp+640h+var_5D0], xmm0
0x1005ad157  movaps  [rbp+640h+var_5C0], xmm0
0x1005ad15e  movaps  [rbp+640h+var_5B0], xmm0
0x1005ad165  movaps  [rbp+640h+var_5A0], xmm0
0x1005ad16c  movaps  [rbp+640h+var_590], xmm0
0x1005ad173  movaps  [rbp+640h+var_580], xmm0
0x1005ad17a  movaps  [rbp+640h+var_570], xmm0
0x1005ad181  movaps  [rbp+640h+var_560], xmm0
0x1005ad188  movaps  [rbp+640h+var_550], xmm0
0x1005ad18f  movaps  [rbp+640h+var_540], xmm0
0x1005ad196  movaps  [rbp+640h+var_530], xmm0
0x1005ad19d  movaps  [rbp+640h+var_520], xmm0
0x1005ad1a4  movaps  [rbp+640h+var_510], xmm0
0x1005ad1ab  movaps  [rbp+640h+var_500], xmm0
0x1005ad1b2  movaps  [rbp+640h+var_4F0], xmm0
0x1005ad1b9  movaps  [rbp+640h+var_4E0], xmm0
0x1005ad1c0  movaps  [rbp+640h+var_4D0], xmm0
0x1005ad1c7  movaps  [rbp+640h+var_4C0], xmm0
0x1005ad1ce  movaps  [rbp+640h+var_4B0], xmm0
0x1005ad1d5  movaps  [rbp+640h+var_4A0], xmm0
0x1005ad1dc  movaps  [rbp+640h+var_490], xmm0
0x1005ad1e3  movaps  [rbp+640h+var_480], xmm0
0x1005ad1ea  movaps  [rbp+640h+var_470], xmm0
0x1005ad1f1  movaps  [rbp+640h+var_460], xmm0
0x1005ad1f8  movaps  [rbp+640h+var_450], xmm0
0x1005ad1ff  movaps  [rbp+640h+var_440], xmm0
0x1005ad206  movaps  [rbp+640h+var_430], xmm0
0x1005ad20d  movaps  [rbp+640h+var_420], xmm0
0x1005ad214  movaps  [rbp+640h+var_410], xmm0
0x1005ad21b  movaps  [rbp+640h+var_400], xmm0
0x1005ad222  movaps  [rbp+640h+var_3F0], xmm0
0x1005ad229  movaps  [rbp+640h+var_3E0], xmm0
0x1005ad230  movaps  [rbp+640h+var_3D0], xmm0
0x1005ad237  movaps  [rbp+640h+var_3C0], xmm0
0x1005ad23e  movaps  [rbp+640h+var_3B0], xmm0
0x1005ad245  movaps  [rbp+640h+var_3A0], xmm0
0x1005ad24c  movaps  [rbp+640h+var_390], xmm0
0x1005ad253  movaps  [rbp+640h+var_380], xmm0
0x1005ad25a  movaps  [rbp+640h+var_370], xmm0
0x1005ad261  movaps  [rbp+640h+var_360], xmm0
0x1005ad268  movaps  [rbp+640h+var_350], xmm0
0x1005ad26f  movaps  [rbp+640h+var_340], xmm0
0x1005ad276  movaps  [rbp+640h+var_330], xmm0
0x1005ad27d  movaps  [rbp+640h+var_320], xmm0
0x1005ad284  movaps  [rbp+640h+var_310], xmm0
0x1005ad28b  movaps  [rbp+640h+var_300], xmm0
0x1005ad292  movaps  [rbp+640h+var_2F0], xmm0
0x1005ad299  movaps  [rbp+640h+var_2E0], xmm0
0x1005ad2a0  movaps  [rbp+640h+var_2D0], xmm0
0x1005ad2a7  movaps  [rbp+640h+var_2C0], xmm0
0x1005ad2ae  movaps  [rbp+640h+var_2B0], xmm0
0x1005ad2b5  movaps  [rbp+640h+var_2A0], xmm0
0x1005ad2bc  movaps  [rbp+640h+var_290], xmm0
0x1005ad2c3  movaps  [rbp+640h+var_280], xmm0
0x1005ad2ca  movaps  [rbp+640h+var_270], xmm0
0x1005ad2d1  movaps  [rbp+640h+var_260], xmm0
0x1005ad2d8  call    memset_0
0x1005ad2dd  mov     r9, cs:?g_crtLocale@@3PEAU__crt_locale_pointers@@EA; struct __crt_locale_pointers *
0x1005ad2e4  lea     r8, aLsNodeconfigur_0; "%ls\\NodeConfiguration"
0x1005ad2eb  mov     edx, 104h; unsigned __int64
0x1005ad2f0  mov     [rsp+740h+phkResult], rbx
0x1005ad2f5  lea     rcx, [rbp+640h+SubKey]; Buffer
0x1005ad2fc  call    ?StringCchPrintf_lW@@YAJPEA_W_KPEB_WPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lW(wchar_t *,unsigned __int64,wchar_t const *,__crt_locale_pointers *,...)
0x1005ad301  test    eax, eax
0x1005ad303  jns     short loc_1005AD326
0x1005ad305  mov     r9d, 154h; int
0x1005ad30b  mov     [rsp+740h+phkResult], rsi; Format
0x1005ad310  lea     r8, aSosnumapExtCpp; "sosnumap_ext.cpp"
0x1005ad317  lea     rdx, aSucceededHr; "SUCCEEDED(hr)"
0x1005ad31e  lea     ecx, [rsi+1]; unsigned int
0x1005ad321  call    ?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x1005ad326  lea     rax, [rsp+740h+hKey]
0x1005ad32b  mov     [rsp+740h+hKey], rsi
0x1005ad330  mov     r9d, 20019h; samDesired
0x1005ad336  mov     [rsp+740h+phkResult], rax; phkResult
0x1005ad33b  xor     r8d, r8d; ulOptions
0x1005ad33e  lea     rdx, [rbp+640h+SubKey]; lpSubKey
0x1005ad345  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1005ad34c  call    cs:__imp_RegOpenKeyExW
0x1005ad352  test    eax, eax
0x1005ad354  jnz     loc_1005AD75C
0x1005ad35a  mov     rcx, [rsp+740h+hKey]; hKey
0x1005ad35f  mov     [rsp+740h+arg_18], r12
0x1005ad367  mov     [rsp+740h+var_20], r13
0x1005ad36f  mov     [rsp+740h+var_28], r14
0x1005ad377  mov     [rsp+740h+var_30], r15
0x1005ad37f  call    cs:__imp_RegCloseKey
0x1005ad385  xorps   xmm0, xmm0
0x1005ad388  mov     [rsp+740h+hKey], rsi
0x1005ad38d  movups  [rsp+740h+var_6D0], xmm0
0x1005ad392  movzx   r14d, si
0x1005ad396  mov     r15d, 8
0x1005ad39c  movups  [rbp+640h+var_6C0], xmm0
0x1005ad3a0  movups  [rbp+640h+var_6B0], xmm0
0x1005ad3a4  movups  [rbp+640h+var_6A0], xmm0
0x1005ad3a8  movups  [rbp+640h+var_690], xmm0
0x1005ad3ac  movups  [rbp+640h+var_680], xmm0
0x1005ad3b0  movups  [rbp+640h+var_670], xmm0
0x1005ad3b4  movups  [rbp+640h+var_660], xmm0
0x1005ad3b8  nop     dword ptr [rax+rax+00000000h]
0x1005ad3c0  mov     r9, cs:?g_crtLocale@@3PEAU__crt_locale_pointers@@EA; struct __crt_locale_pointers *
0x1005ad3c7  lea     r8, aLsNodeconfigur; "%ls\\NodeConfiguration\\Node%d"
0x1005ad3ce  movsx   r13d, r14w
0x1005ad3d2  lea     rcx, [rbp+640h+SubKey]; Buffer
0x1005ad3d9  mov     dword ptr [rsp+740h+lpcbData], r13d
0x1005ad3de  mov     edx, 104h; unsigned __int64
0x1005ad3e3  mov     [rsp+740h+phkResult], rbx
0x1005ad3e8  call    ?StringCchPrintf_lW@@YAJPEA_W_KPEB_WPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lW(wchar_t *,unsigned __int64,wchar_t const *,__crt_locale_pointers *,...)
0x1005ad3ed  test    eax, eax
0x1005ad3ef  jns     short loc_1005AD414
0x1005ad3f1  mov     r9d, 16Ah; int
0x1005ad3f7  mov     [rsp+740h+phkResult], rsi; Format
0x1005ad3fc  lea     r8, aSosnumapExtCpp; "sosnumap_ext.cpp"
0x1005ad403  mov     ecx, 1; unsigned int
0x1005ad408  lea     rdx, aSucceededHr; "SUCCEEDED(hr)"
0x1005ad40f  call    ?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x1005ad414  lea     rax, [rsp+740h+hKey]
0x1005ad419  mov     r9d, 20019h; samDesired
0x1005ad41f  xor     r8d, r8d; ulOptions
0x1005ad422  mov     [rsp+740h+phkResult], rax; phkResult
0x1005ad427  lea     rdx, [rbp+640h+SubKey]; lpSubKey
0x1005ad42e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1005ad435  call    cs:__imp_RegOpenKeyExW
0x1005ad43b  test    eax, eax
0x1005ad43d  jnz     loc_1005AD4C4
0x1005ad443  mov     rcx, cs:?sm_instance@OsNumaConfig@@0PEAV1@EA; OsNumaConfig * OsNumaConfig::sm_instance
0x1005ad44a  mov     rbx, [rsp+740h+hKey]
0x1005ad44f  mov     rax, [rcx]
0x1005ad452  call    qword ptr [rax+48h]
0x1005ad455  lea     r9, [rsp+740h+Type]; lpType
0x1005ad45a  mov     dword ptr [rsp+740h+Data], esi
0x1005ad45e  mov     r12d, eax
0x1005ad461  mov     [rsp+740h+cbData], 4
0x1005ad469  lea     rax, [rsp+740h+cbData]
0x1005ad46e  xor     r8d, r8d; lpReserved
0x1005ad471  mov     [rsp+740h+lpcbData], rax; lpcbData
0x1005ad476  lea     rdx, aGroup; "Group"
0x1005ad47d  lea     rax, [rsp+740h+Data]
0x1005ad482  mov     rcx, rbx; hKey
0x1005ad485  mov     [rsp+740h+phkResult], rax; lpData
0x1005ad48a  call    cs:__imp_RegQueryValueExW
0x1005ad490  cmp     eax, 2
0x1005ad493  jz      loc_1005AD5E5
0x1005ad499  test    eax, eax
0x1005ad49b  jnz     short loc_1005AD4B1
0x1005ad49d  cmp     [rsp+740h+Type], 4
0x1005ad4a2  jnz     short loc_1005AD4B1
0x1005ad4a4  mov     ebx, dword ptr [rsp+740h+Data]
0x1005ad4a8  cmp     ebx, r12d
0x1005ad4ab  jb      loc_1005AD5EB
0x1005ad4b1  mov     edx, r13d
0x1005ad4b4  lea     rcx, aDetectedErrorI; "Detected error in soft-NUMA configurati"...
0x1005ad4bb  call    cs:?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA; SOS_OS::LogUnlocalizedRoutine(wchar_t const *,...)
0x1005ad4c1  mov     r14d, esi
0x1005ad4c4  mov     rcx, [rsp+740h+hKey]; hKey
0x1005ad4c9  test    rcx, rcx
0x1005ad4cc  jz      short loc_1005AD4D9
0x1005ad4ce  call    cs:__imp_RegCloseKey
0x1005ad4d4  mov     [rsp+740h+hKey], rsi
0x1005ad4d9  mov     r9d, 10h
0x1005ad4df  lea     r8, [rsp+740h+var_6D0]
0x1005ad4e4  mov     r11d, r9d
0x1005ad4e7  mov     r10d, esi
0x1005ad4ea  mov     rbx, 3333333333333333h
0x1005ad4f4  mov     rdi, 101010101010101h
0x1005ad4fe  mov     r12, 5555555555555555h
0x1005ad508  mov     r13, 0F0F0F0F0F0F0F0Fh
0x1005ad512  nop     dword ptr [rax+00h]
0x1005ad516  nop     word ptr [rax+rax+00000000h]
0x1005ad520  mov     rdx, [r8]
0x1005ad523  lea     r8, [r8+8]
0x1005ad527  mov     rax, rdx
0x1005ad52a  shr     rax, 1
0x1005ad52d  and     rax, r12
0x1005ad530  sub     rdx, rax
0x1005ad533  mov     rcx, rdx
0x1005ad536  and     rdx, rbx
0x1005ad539  shr     rcx, 2
0x1005ad53d  and     rcx, rbx
0x1005ad540  add     rcx, rdx
0x1005ad543  mov     rax, rcx
0x1005ad546  shr     rax, 4
0x1005ad54a  add     rax, rcx
0x1005ad54d  and     rax, r13
0x1005ad550  imul    rax, rdi
0x1005ad554  shr     rax, 38h
0x1005ad558  add     r10d, eax
0x1005ad55b  sub     r11, 1
0x1005ad55f  jnz     short loc_1005AD520
0x1005ad561  mov     eax, cs:?sm_cpuCount@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_cpuCount
0x1005ad567  mov     rdi, [rsp+740h+var_6E0]
0x1005ad56c  cmp     r10d, eax
0x1005ad56f  jz      loc_1005AD6BD
0x1005ad575  lea     r8, [rsp+740h+var_6D0]
0x1005ad57a  nop     word ptr [rax+rax+00h]
0x1005ad580  mov     rdx, [r8]
0x1005ad583  lea     r8, [r8+8]
0x1005ad587  mov     rax, rdx
0x1005ad58a  shr     rax, 1
0x1005ad58d  and     rax, r12
0x1005ad590  sub     rdx, rax
0x1005ad593  mov     rcx, rdx
0x1005ad596  and     rdx, rbx
0x1005ad599  shr     rcx, 2
0x1005ad59d  and     rcx, rbx
0x1005ad5a0  add     rcx, rdx
0x1005ad5a3  mov     rax, rcx
0x1005ad5a6  shr     rax, 4
0x1005ad5aa  add     rax, rcx
0x1005ad5ad  mov     rcx, 101010101010101h
0x1005ad5b7  and     rax, r13
0x1005ad5ba  imul    rax, rcx
0x1005ad5be  shr     rax, 38h
0x1005ad5c2  add     esi, eax
0x1005ad5c4  sub     r9, 1
0x1005ad5c8  jnz     short loc_1005AD580
0x1005ad5ca  mov     edx, cs:?sm_cpuCount@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_cpuCount
0x1005ad5d0  lea     rcx, aDetectedErrorI_0; "Detected error in soft-NUMA configurati"...
0x1005ad5d7  mov     r8d, esi
0x1005ad5da  call    cs:?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA; SOS_OS::LogUnlocalizedRoutine(wchar_t const *,...)
0x1005ad5e0  jmp     loc_1005AD73C
0x1005ad5e5  mov     ebx, esi
0x1005ad5e7  mov     dword ptr [rsp+740h+Data], ebx
0x1005ad5eb  mov     rcx, [rsp+740h+hKey]; hKey
0x1005ad5f0  lea     rax, [rsp+740h+var_6FC]
0x1005ad5f5  mov     [rsp+740h+lpcbData], rax; lpcbData
0x1005ad5fa  lea     r9, [rsp+740h+var_6F8]; lpType
0x1005ad5ff  lea     rax, [rsp+740h+var_6F0]
0x1005ad604  mov     qword ptr [rsp+740h+var_6F0], rsi
0x1005ad609  xor     r8d, r8d; lpReserved
0x1005ad60c  mov     [rsp+740h+phkResult], rax; lpData
0x1005ad611  lea     rdx, aCpumask; "CPUMask"
0x1005ad618  mov     [rsp+740h+var_6FC], r15d
0x1005ad61d  call    cs:__imp_RegQueryValueExW
0x1005ad623  test    eax, eax
0x1005ad625  jnz     loc_1005AD4B1
0x1005ad62b  mov     rcx, qword ptr [rsp+740h+var_6F0]
0x1005ad630  test    rcx, rcx
0x1005ad633  jz      loc_1005AD4B1
0x1005ad639  movzx   eax, bx
0x1005ad63c  test    qword ptr [rsp+rax*8+740h+var_6D0], rcx
0x1005ad641  jnz     loc_1005AD4B1
0x1005ad647  lea     rdx, ?sm_osSystemAffinity@SOS_PublicGlobals@@2VSystemAffinity@@A; SystemAffinity SOS_PublicGlobals::sm_osSystemAffinity
0x1005ad64e  mov     rax, [rdx+rax*8]
0x1005ad652  and     rax, rcx
0x1005ad655  cmp     rax, rcx
0x1005ad658  jnz     loc_1005AD4B1
0x1005ad65e  mov     edx, [rsp+740h+var_6F8]
0x1005ad662  lea     eax, [rdx-3]
0x1005ad665  test    eax, 0FFFFFFF6h
0x1005ad66a  jnz     loc_1005AD4B1
0x1005ad670  cmp     edx, 0Ch
0x1005ad673  jz      loc_1005AD4B1
0x1005ad679  movsx   rax, r14w
0x1005ad67d  add     rax, rax
0x1005ad680  mov     qword ptr [rbp+rax*8+640h+var_650], rcx
0x1005ad685  mov     word ptr [rbp+rax*8+640h+var_650+8], bx
0x1005ad68a  movzx   eax, word ptr [rbp+rax*8+640h+var_650+8]
0x1005ad68f  or      qword ptr [rsp+rax*8+740h+var_6D0], rcx
0x1005ad694  mov     rcx, [rsp+740h+hKey]; hKey
0x1005ad699  call    cs:__imp_RegCloseKey
0x1005ad69f  mov     rbx, [rsp+740h+var_6E8]
0x1005ad6a4  inc     r14w
0x1005ad6a8  mov     [rsp+740h+hKey], rsi
0x1005ad6ad  cmp     r14w, 40h ; '@'
0x1005ad6b2  jl      loc_1005AD3C0
0x1005ad6b8  jmp     loc_1005AD4D9
0x1005ad6bd  test    r14w, r14w
0x1005ad6c1  jz      short loc_1005AD73C
0x1005ad6c3  test    rdi, rdi
0x1005ad6c6  jnz     short loc_1005AD6DC
0x1005ad6c8  call    cs:__imp__errno
0x1005ad6ce  mov     dword ptr [rax], 16h
  ... truncated ...
```
