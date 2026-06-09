# CUrlZoneManager::GetZoneActionPolicyEx(ulong,ulong,uchar *,ulong,_URLZONEREG,ulong)

- ea: `0x180035d70`
- end: `0x1800363da`
- name: `?GetZoneActionPolicyEx@CUrlZoneManager@@UEAAJKKPEAEKW4_URLZONEREG@@K@Z`
- size: `1642`
- prototype: `int(CUrlZoneManager *__hidden this, unsigned int, unsigned int, unsigned __int8 *, unsigned int, enum _URLZONEREG, unsigned int)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000eae0`
- `0x18001054c`
- `0x180013be0`
- `0x1800215c0`
- `0x1800342d0`
- `0x180035d70`
- `0x1800363e0`
- `0x180056d60`
- `0x18006b964`
- `0x18007ef30`
- `0x18011baa0`
- `0x18011c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035df1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035e93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035fb9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036010`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003614c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036174`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035df1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035e93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035fb9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036010`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003614c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036174`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035dd3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035f49`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036102`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035dd3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035f49`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036102`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180036088`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x18003623e`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x1800362b4`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x1800362e6`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180036088`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x18003623e`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x1800362b4`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x1800362e6`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegQueryUSValueW` at `0x1800360e8`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegQueryUSValueW` at `0x180036337`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegQueryUSValueW` at `0x1800360e8`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegQueryUSValueW` at `0x180036337`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x18003616a`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x18003616a`

## pseudocode

```c
__int64 __fastcall CUrlZoneManager::GetZoneActionPolicyEx(
        CUrlZoneManager *this,
        unsigned int a2,
        unsigned int a3,
        unsigned __int8 *a4,
        unsigned int a5,
        enum _URLZONEREG a6,
        unsigned int a7)
{
  unsigned int v10; // eax
  unsigned int *v11; // r11
  unsigned int *v12; // r8
  __int64 v14; // rsi
  unsigned int v15; // edi
  unsigned int v16; // esi
  unsigned int v17; // r13d
  __int64 v18; // rdi
  int v19; // r15d
  const WCHAR *v20; // r14
  CSharedMem *v21; // rcx
  int i; // ebx
  int v23; // ecx
  _DWORD *v24; // rax
  _DWORD *v25; // rbx
  int v26; // r14d
  const WCHAR *v27; // r15
  BOOL fIgnoreHKCU; // eax
  HUSKEY v29; // rcx
  int *v30; // r15
  LSTATUS USValueW; // eax
  int v32; // r15d
  __int64 v33; // rax
  unsigned int v34; // edx
  BOOL v35; // eax
  BOOL v36; // [rsp+28h] [rbp-79h]
  HUSKEY phNewUSKey; // [rsp+40h] [rbp-61h] BYREF
  int v38; // [rsp+48h] [rbp-59h]
  void *pvData; // [rsp+50h] [rbp-51h]
  const unsigned int *v40; // [rsp+58h] [rbp-49h] BYREF
  HUSKEY hUSKey; // [rsp+60h] [rbp-41h]
  BOOL v42; // [rsp+68h] [rbp-39h]
  __int64 v43; // [rsp+6Ch] [rbp-35h]
  LPCWSTR pwzPath; // [rsp+78h] [rbp-29h] BYREF
  unsigned int v45; // [rsp+80h] [rbp-21h]
  WCHAR pszValue[12]; // [rsp+88h] [rbp-19h] BYREF

  LODWORD(phNewUSKey) = a7;
  pvData = a4;
  v45 = a3;
  if ( !a4 || a5 < 4 || (a7 & 0xFFFAFFFF) != 0 )
    return 2147942487LL;
  EnterCriticalSection(&g_mxsPermanentISM);
  if ( byte_18015E7D8 && (v14 = qword_18015E7D0) != 0 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_18015E7D0 + 8LL))(qword_18015E7D0);
    LeaveCriticalSection(&g_mxsPermanentISM);
    v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, unsigned __int8 *, unsigned int, enum _URLZONEREG, unsigned int))(*(_QWORD *)v14 + 24LL))(
            v14,
            a2,
            a3,
            a4,
            a5,
            a6,
            a7);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    if ( v15 != -2146697199 )
      return v15;
  }
  else
  {
    LeaveCriticalSection(&g_mxsPermanentISM);
  }
  if ( (a7 & 0x10000) != 0 )
  {
    v34 = 0;
    v11 = 0;
    while ( v34 < *((_DWORD *)CUrlZoneManager::s_pRegLockZoneContainer + 6) )
    {
      v12 = *(unsigned int **)(*((_QWORD *)CUrlZoneManager::s_pRegLockZoneContainer + 2) + 8LL * v34);
      if ( !v12 )
        break;
      if ( *v12 == a2 )
      {
LABEL_13:
        v11 = v12;
        break;
      }
      if ( *v12 > a2 )
        break;
      ++v34;
    }
  }
  else
  {
    v10 = 0;
    v11 = 0;
    while ( v10 < *((_DWORD *)CUrlZoneManager::s_pRegZoneContainer + 6) )
    {
      v12 = *(unsigned int **)(*((_QWORD *)CUrlZoneManager::s_pRegZoneContainer + 2) + 8LL * v10);
      if ( !v12 )
        break;
      if ( *v12 == a2 )
        goto LABEL_13;
      if ( *v12 > a2 )
        break;
      ++v10;
    }
  }
  if ( !v11 )
    return 2147942487LL;
  v16 = *v11;
  if ( *v11 == -1 )
    return 2147500037LL;
  if ( a3 > 0x1401 )
  {
    if ( a3 != 5634 && a3 != 5635 )
      goto LABEL_24;
    v17 = 5633;
  }
  else
  {
    if ( a3 != 5121 && a3 != 4610 && a3 - 4611 >= 2 )
    {
LABEL_24:
      v17 = a3;
      goto LABEL_25;
    }
    v17 = 4609;
  }
LABEL_25:
  v18 = *((_QWORD *)v11 + 8);
  if ( a6 )
  {
    v38 = 0;
    v19 = 0;
    if ( a6 != URLZONEREG_HKLM )
    {
      if ( a6 == URLZONEREG_HKCU )
        v38 = 0;
      goto LABEL_28;
    }
    v19 = 1;
  }
  else
  {
    v19 = v11[10];
  }
  v38 = v19;
LABEL_28:
  v20 = (const WCHAR *)*((_QWORD *)v11 + 3);
  pwzPath = (LPCWSTR)*((_QWORD *)v11 + 2);
  EnterCriticalSection((LPCRITICAL_SECTION)(v18 + 16));
  if ( !(unsigned int)CSharedMem::IsCounterEqual(v21, *(_DWORD *)(v18 + 56) != 0 ? 0xC : 0, *(_DWORD *)v18) )
    CRegZone::CRegZoneCache::Flush((CRegZone::CRegZoneCache *)v18);
  for ( i = 0; ; ++i )
  {
    if ( i >= 80 || (v23 = *(_DWORD *)(v18 + 16 * (i + 4LL)), v23 == -1) )
    {
      i = *(_DWORD *)(v18 + 1344);
      *(_DWORD *)(v18 + 1344) = (i + 1) % 80;
      goto LABEL_40;
    }
    if ( v23 == v16 )
    {
      v24 = (_DWORD *)(v18 + 16LL * i);
      if ( v24[17] == v17 && v24[18] == v19 )
        break;
    }
  }
  if ( ((unsigned int)phNewUSKey & 0x40000) == 0 )
  {
    v25 = pvData;
    *(_DWORD *)pvData = v24[19];
    LeaveCriticalSection((LPCRITICAL_SECTION)(v18 + 16));
    goto LABEL_61;
  }
LABEL_40:
  if ( (int)StringCchPrintfW(pszValue, 0xCu, L"%lX", v17) < 0 )
  {
LABEL_41:
    LeaveCriticalSection((LPCRITICAL_SECTION)(v18 + 16));
    return 2147500037LL;
  }
  v42 = v19;
  v40 = &CRegKey::`vftable';
  v43 = 1;
  hUSKey = 0;
  phNewUSKey = 0;
  CRegKey::Close((CRegKey *)&v40);
  if ( !v20 )
  {
LABEL_46:
    v26 = 0;
    LODWORD(v43) = 0;
    phNewUSKey = 0;
    (*((void (__fastcall **)(const unsigned int **))v40 + 2))(&v40);
    v27 = pwzPath;
    if ( !pwzPath )
      goto LABEL_57;
    if ( (_DWORD)v43 )
    {
      fIgnoreHKCU = v42;
      if ( v42 )
      {
LABEL_49:
        if ( !SHRegOpenUSKeyW(v27, 0x20019u, 0, &phNewUSKey, fIgnoreHKCU) )
          goto LABEL_50;
LABEL_57:
        v25 = pvData;
        goto LABEL_58;
      }
      if ( !SHRegOpenUSKeyW(pwzPath, 0x20019u, 0, &phNewUSKey, 1) )
      {
LABEL_50:
        v29 = phNewUSKey;
        hUSKey = phNewUSKey;
        LODWORD(phNewUSKey) = 0;
        LODWORD(pwzPath) = 4;
        if ( !hUSKey )
          goto LABEL_41;
        if ( (_DWORD)v43 && !v42 )
        {
          USValueW = SHRegQueryUSValueW(v29, pszValue, (DWORD *)&phNewUSKey, pvData, (DWORD *)&pwzPath, 1, 0, 0);
          if ( !USValueW )
          {
            v30 = (int *)pvData;
LABEL_53:
            if ( !USValueW )
            {
              v32 = *v30;
              v26 = 1;
              LODWORD(phNewUSKey) = i;
              EnterCriticalSection((LPCRITICAL_SECTION)(v18 + 16));
              if ( i == -1 )
              {
                CRegZone::CRegZoneCache::FindCacheEntry(
                  (CRegZone::CRegZoneCache *)v18,
                  v16,
                  v17,
                  v38,
                  (int *)&phNewUSKey);
                i = (int)phNewUSKey;
              }
              v33 = 2 * (i + 4LL);
              *(_DWORD *)(v18 + 8 * v33 + 8) = v38;
              *(_DWORD *)(v18 + 8 * v33) = v16;
              *(_DWORD *)(v18 + 8 * v33 + 4) = v17;
              *(_DWORD *)(v18 + 8 * v33 + 12) = v32;
              CSharedMem::GetCounter(
                (CSharedMem *)&g_SharedMem,
                *(_DWORD *)(v18 + 56) != 0 ? 0xC : 0,
                (unsigned int *)v18);
              LeaveCriticalSection((LPCRITICAL_SECTION)(v18 + 16));
            }
            goto LABEL_57;
          }
          v29 = hUSKey;
        }
        v30 = (int *)pvData;
        USValueW = SHRegQueryUSValueW(v29, pszValue, (DWORD *)&phNewUSKey, pvData, (DWORD *)&pwzPath, v42, 0, 0);
        goto LABEL_53;
      }
    }
    fIgnoreHKCU = v42;
    goto LABEL_49;
  }
  if ( !(_DWORD)v43 )
  {
LABEL_73:
    v35 = v42;
    goto LABEL_74;
  }
  v35 = v42;
  if ( !v42 )
  {
    if ( !SHRegOpenUSKeyW(v20, 0x20019u, 0, &phNewUSKey, 1) )
      goto LABEL_75;
    goto LABEL_73;
  }
LABEL_74:
  if ( SHRegOpenUSKeyW(v20, 0x20019u, 0, &phNewUSKey, v35) )
    goto LABEL_46;
LABEL_75:
  hUSKey = phNewUSKey;
  if ( CRegKey::QueryValue((CRegKey *)&v40, (unsigned int *)pvData, pszValue) )
    goto LABEL_46;
  v36 = i;
  v25 = pvData;
  v26 = 1;
  CRegZone::CRegZoneCache::Add((CRegZone::CRegZoneCache *)v18, v16, v17, v19, *(_DWORD *)pvData, v36);
LABEL_58:
  v40 = &CRegKey::`vftable';
  if ( hUSKey )
    SHRegCloseUSKey(hUSKey);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v18 + 16));
  if ( !v26 )
    return 2147500037LL;
LABEL_61:
  if ( v45 == 4610 || v45 == 4611 || v45 == 5121 )
  {
    if ( (unsigned int)CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::FEATURE_RESPECT_OBJECTSAFETY_POLICY_KB905547) )
    {
      if ( (*v25 & 0xF) == 1 )
        *v25 = *v25 & 0xFFFFFFF0 | 3;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180035d70  mov     [rsp-8+arg_0], rbx
0x180035d75  push    rbp
0x180035d76  push    rsi
0x180035d77  push    rdi
0x180035d78  push    r12
0x180035d7a  push    r13
0x180035d7c  push    r14
0x180035d7e  push    r15
0x180035d80  lea     rbp, [rsp-0Fh]
0x180035d85  sub     rsp, 0B0h
0x180035d8c  mov     rax, cs:__security_cookie
0x180035d93  xor     rax, rsp
0x180035d96  mov     [rbp+3Fh+var_40], rax
0x180035d9a  mov     r14d, [rbp+3Fh+arg_30]
0x180035d9e  mov     r13, r9
0x180035da1  mov     dword ptr [rbp+3Fh+phNewUSKey], r14d
0x180035da5  mov     r15d, r8d
0x180035da8  mov     [rbp+3Fh+pvData], r9
0x180035dac  mov     ebx, edx
0x180035dae  mov     [rbp+3Fh+var_60], r8d
0x180035db2  test    r9, r9
0x180035db5  jz      loc_180035E41
0x180035dbb  mov     edi, [rbp+3Fh+arg_20]
0x180035dbe  cmp     edi, 4
0x180035dc1  jb      short loc_180035E41
0x180035dc3  test    r14d, 0FFFAFFFFh
0x180035dca  jnz     short loc_180035E41
0x180035dcc  lea     rcx, ?g_mxsPermanentISM@@3VCMutexSem@@A; lpCriticalSection
0x180035dd3  call    cs:__imp_EnterCriticalSection
0x180035dd9  cmp     cs:byte_18015E7D8, 0
0x180035de0  mov     r12d, [rbp+3Fh+arg_28]
0x180035de4  jnz     loc_180035E6D
0x180035dea  lea     rcx, ?g_mxsPermanentISM@@3VCMutexSem@@A; lpCriticalSection
0x180035df1  call    cs:__imp_LeaveCriticalSection
0x180035df7  bt      r14d, 10h
0x180035dfc  jb      loc_1800361AC
0x180035e02  mov     r10, cs:?s_pRegZoneContainer@CUrlZoneManager@@1PEAVCRegZoneContainer@@EA; CRegZoneContainer * CUrlZoneManager::s_pRegZoneContainer
0x180035e09  xor     r14d, r14d
0x180035e0c  mov     eax, r14d
0x180035e0f  mov     r11d, r14d
0x180035e12  mov     r9d, [r10+18h]
0x180035e16  cmp     eax, r9d
0x180035e19  jnb     short loc_180035E38
0x180035e1b  mov     rcx, [r10+10h]
0x180035e1f  mov     edx, eax
0x180035e21  mov     r8, [rcx+rdx*8]
0x180035e25  test    r8, r8
0x180035e28  jz      short loc_180035E38
0x180035e2a  cmp     [r8], ebx
0x180035e2d  jz      short loc_180035E35
0x180035e2f  ja      short loc_180035E38
0x180035e31  inc     eax
0x180035e33  jmp     short loc_180035E16
0x180035e35  mov     r11, r8
0x180035e38  test    r11, r11
0x180035e3b  jnz     loc_180035EE2
0x180035e41  mov     eax, 80070057h
0x180035e46  mov     rcx, [rbp+3Fh+var_40]
0x180035e4a  xor     rcx, rsp; StackCookie
0x180035e4d  call    __security_check_cookie
0x180035e52  mov     rbx, [rsp+0E0h+arg_0]
0x180035e5a  add     rsp, 0B0h
0x180035e61  pop     r15
0x180035e63  pop     r14
0x180035e65  pop     r13
0x180035e67  pop     r12
0x180035e69  pop     rdi
0x180035e6a  pop     rsi
0x180035e6b  pop     rbp
0x180035e6c  retn
0x180035e6d  mov     rsi, cs:qword_18015E7D0
0x180035e74  test    rsi, rsi
0x180035e77  jz      loc_180035DEA
0x180035e7d  mov     rax, [rsi]
0x180035e80  mov     rcx, rsi
0x180035e83  mov     rax, [rax+8]
0x180035e87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035e8c  lea     rcx, ?g_mxsPermanentISM@@3VCMutexSem@@A; lpCriticalSection
0x180035e93  call    cs:__imp_LeaveCriticalSection
0x180035e99  mov     rax, [rsi]
0x180035e9c  mov     r9, r13
0x180035e9f  mov     dword ptr [rsp+0E0h+pvDefaultData], r14d
0x180035ea4  mov     r8d, r15d
0x180035ea7  mov     [rsp+0E0h+var_B8], r12d
0x180035eac  mov     edx, ebx
0x180035eae  mov     rcx, rsi
0x180035eb1  mov     [rsp+0E0h+fIgnoreHKCU], edi
0x180035eb5  mov     rax, [rax+18h]
0x180035eb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035ebe  mov     rdx, [rsi]
0x180035ec1  mov     edi, eax
0x180035ec3  mov     rcx, rsi
0x180035ec6  mov     rax, [rdx+10h]
0x180035eca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035ecf  cmp     edi, 800C0011h
0x180035ed5  jz      loc_180035DF7
0x180035edb  mov     eax, edi
0x180035edd  jmp     loc_180035E46
0x180035ee2  mov     esi, [r11]
0x180035ee5  cmp     esi, 0FFFFFFFFh
0x180035ee8  jz      loc_180036016
0x180035eee  cmp     r15d, 1401h
0x180035ef5  ja      loc_180036020
0x180035efb  jz      loc_18003634A
0x180035f01  mov     eax, r15d
0x180035f04  sub     eax, 1202h
0x180035f09  jz      loc_18003634A
0x180035f0f  sub     eax, 1
0x180035f12  jz      loc_18003634A
0x180035f18  cmp     eax, 1
0x180035f1b  jz      loc_18003634A
0x180035f21  mov     r13d, r15d
0x180035f24  mov     rdi, [r11+40h]
0x180035f28  test    r12d, r12d
0x180035f2b  jnz     loc_180036355
0x180035f31  mov     r15d, [r11+28h]
0x180035f35  mov     [rbp+3Fh+var_98], r15d
0x180035f39  mov     rax, [r11+10h]
0x180035f3d  lea     rcx, [rdi+10h]; lpCriticalSection
0x180035f41  mov     r14, [r11+18h]
0x180035f45  mov     [rbp+3Fh+pwzPath], rax
0x180035f49  call    cs:__imp_EnterCriticalSection
0x180035f4f  mov     eax, [rdi+38h]
0x180035f52  mov     r8d, [rdi]; unsigned int
0x180035f55  neg     eax
0x180035f57  sbb     edx, edx
0x180035f59  and     edx, 0Ch; unsigned int
0x180035f5c  call    ?IsCounterEqual@CSharedMem@@QEAAHKKH@Z; CSharedMem::IsCounterEqual(ulong,ulong,int)
0x180035f61  test    eax, eax
0x180035f63  jz      loc_1800362F9
0x180035f69  xor     ebx, ebx
0x180035f6b  nop     dword ptr [rax+rax+00h]
0x180035f70  cmp     ebx, 50h ; 'P'
0x180035f73  jge     short loc_180035FC4
0x180035f75  movsxd  rdx, ebx
0x180035f78  lea     rax, [rdx+4]
0x180035f7c  add     rax, rax
0x180035f7f  mov     ecx, [rdi+rax*8]
0x180035f82  cmp     ecx, 0FFFFFFFFh
0x180035f85  jz      short loc_180035FC4
0x180035f87  cmp     ecx, esi
0x180035f89  jnz     short loc_180035F99
0x180035f8b  add     rdx, rdx
0x180035f8e  cmp     [rdi+rdx*8+44h], r13d
0x180035f93  lea     rax, [rdi+rdx*8]
0x180035f97  jz      short loc_180035F9D
0x180035f99  inc     ebx
0x180035f9b  jmp     short loc_180035F70
0x180035f9d  cmp     [rax+48h], r15d
0x180035fa1  jnz     short loc_180035F99
0x180035fa3  test    dword ptr [rbp+3Fh+phNewUSKey], 40000h
0x180035faa  jnz     short loc_180035FEC
0x180035fac  mov     eax, [rax+4Ch]
0x180035faf  lea     rcx, [rdi+10h]; lpCriticalSection
0x180035fb3  mov     rbx, [rbp+3Fh+pvData]
0x180035fb7  mov     [rbx], eax
0x180035fb9  call    cs:__imp_LeaveCriticalSection
0x180035fbf  jmp     loc_180036183
0x180035fc4  mov     ebx, [rdi+540h]
0x180035fca  mov     eax, 66666667h
0x180035fcf  lea     ecx, [rbx+1]
0x180035fd2  imul    ecx
0x180035fd4  sar     edx, 5
0x180035fd7  mov     eax, edx
0x180035fd9  shr     eax, 1Fh
0x180035fdc  add     edx, eax
0x180035fde  lea     eax, [rdx+rdx*4]
0x180035fe1  shl     eax, 4
0x180035fe4  sub     ecx, eax
0x180035fe6  mov     [rdi+540h], ecx
0x180035fec  mov     r9d, r13d
0x180035fef  lea     r8, aLx; "%lX"
0x180035ff6  mov     edx, 0Ch; unsigned __int64
0x180035ffb  lea     rcx, [rbp+3Fh+pszValue]; unsigned __int16 *
0x180035fff  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180036004  test    eax, eax
0x180036006  jns     loc_1800361EF
0x18003600c  lea     rcx, [rdi+10h]; lpCriticalSection
0x180036010  call    cs:__imp_LeaveCriticalSection
0x180036016  mov     eax, 80004005h
0x18003601b  jmp     loc_180035E46
0x180036020  mov     eax, r15d
0x180036023  sub     eax, 1602h
0x180036028  jz      short loc_180036033
0x18003602a  cmp     eax, 1
0x18003602d  jnz     loc_180035F21
0x180036033  mov     r13d, 1601h
0x180036039  jmp     loc_180035F24
0x18003603e  xor     eax, eax
0x180036040  lea     rcx, [rbp+3Fh+var_88]
0x180036044  mov     r14d, eax
0x180036047  mov     dword ptr [rbp+3Fh+var_74], eax
0x18003604a  mov     [rbp+3Fh+phNewUSKey], rax
0x18003604e  mov     rax, [rbp+3Fh+var_88]
0x180036052  mov     rax, [rax+10h]
0x180036056  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003605b  mov     r15, [rbp+3Fh+pwzPath]
0x18003605f  test    r15, r15
0x180036062  jz      loc_180036152
0x180036068  cmp     dword ptr [rbp+3Fh+var_74], r14d
0x18003606c  jnz     loc_1800362C4
0x180036072  mov     eax, [rbp+3Fh+var_78]
0x180036075  lea     r9, [rbp+3Fh+phNewUSKey]; phNewUSKey
0x180036079  mov     [rsp+0E0h+fIgnoreHKCU], eax; fIgnoreHKCU
0x18003607d  xor     r8d, r8d; hRelativeUSKey
0x180036080  mov     edx, 20019h; samDesired
0x180036085  mov     rcx, r15; pwzPath
0x180036088  call    cs:__imp_SHRegOpenUSKeyW
0x18003608e  test    eax, eax
0x180036090  jnz     loc_180036152
0x180036096  mov     rcx, [rbp+3Fh+phNewUSKey]; hUSKey
0x18003609a  xor     r15d, r15d
0x18003609d  mov     [rbp+3Fh+hUSKey], rcx
0x1800360a1  mov     dword ptr [rbp+3Fh+phNewUSKey], r15d
0x1800360a5  mov     dword ptr [rbp+3Fh+pwzPath], 4
0x1800360ac  test    rcx, rcx
0x1800360af  jz      loc_18003600C
0x1800360b5  cmp     dword ptr [rbp+3Fh+var_74], r14d
0x1800360b9  jnz     loc_180036306
0x1800360bf  mov     eax, [rbp+3Fh+var_78]
0x1800360c2  lea     r8, [rbp+3Fh+phNewUSKey]; pdwType
0x1800360c6  mov     [rsp+0E0h+dwDefaultDataSize], r15d; dwDefaultDataSize
0x1800360cb  lea     rdx, [rbp+3Fh+pszValue]; pszValue
0x1800360cf  mov     [rsp+0E0h+pvDefaultData], r15; pvDefaultData
0x1800360d4  mov     r15, [rbp+3Fh+pvData]
0x1800360d8  mov     [rsp+0E0h+var_B8], eax; fIgnoreHKCU
0x1800360dc  mov     r9, r15; pvData
0x1800360df  lea     rax, [rbp+3Fh+pwzPath]
0x1800360e3  mov     qword ptr [rsp+0E0h+fIgnoreHKCU], rax; pcbData
0x1800360e8  call    cs:__imp_SHRegQueryUSValueW
0x1800360ee  test    eax, eax
0x1800360f0  jnz     short loc_180036152
0x1800360f2  mov     r15d, [r15]
0x1800360f5  lea     rcx, [rdi+10h]; lpCriticalSection
0x1800360f9  mov     r14d, 1
0x1800360ff  mov     dword ptr [rbp+3Fh+phNewUSKey], ebx
0x180036102  call    cs:__imp_EnterCriticalSection
0x180036108  cmp     ebx, 0FFFFFFFFh
0x18003610b  jz      loc_180036389
0x180036111  mov     ecx, [rbp+3Fh+var_98]
0x180036114  mov     r8, rdi; unsigned int *
0x180036117  movsxd  rax, ebx
0x18003611a  add     rax, 4
0x18003611e  add     rax, rax
0x180036121  mov     [rdi+rax*8+8], ecx
0x180036125  lea     rcx, ?g_SharedMem@@3VCSharedMem@@A; this
0x18003612c  mov     [rdi+rax*8], esi
0x18003612f  mov     [rdi+rax*8+4], r13d
0x180036134  mov     [rdi+rax*8+0Ch], r15d
0x180036139  mov     eax, [rdi+38h]
0x18003613c  neg     eax
0x18003613e  sbb     edx, edx
0x180036140  and     edx, 0Ch; unsigned int
0x180036143  call    ?GetCounter@CSharedMem@@QEAAHKPEAK@Z; CSharedMem::GetCounter(ulong,ulong *)
0x180036148  lea     rcx, [rdi+10h]; lpCriticalSection
0x18003614c  call    cs:__imp_LeaveCriticalSection
0x180036152  mov     rbx, [rbp+3Fh+pvData]
0x180036156  mov     rcx, [rbp+3Fh+hUSKey]; hUSKey
0x18003615a  lea     rax, ??_7CRegKey@@6B@; const CRegKey::`vftable'
0x180036161  mov     [rbp+3Fh+var_88], rax
0x180036165  test    rcx, rcx
0x180036168  jz      short loc_180036170
0x18003616a  call    cs:__imp_SHRegCloseUSKey
0x180036170  lea     rcx, [rdi+10h]; lpCriticalSection
0x180036174  call    cs:__imp_LeaveCriticalSection
0x18003617a  test    r14d, r14d
0x18003617d  jz      loc_180036016
0x180036183  mov     eax, [rbp+3Fh+var_60]
0x180036186  sub     eax, 1202h
0x18003618b  jz      loc_1800363AB
0x180036191  sub     eax, 1
0x180036194  jz      loc_1800363AB
0x18003619a  cmp     eax, 1FEh
0x18003619f  jz      loc_1800363AB
0x1800361a5  xor     eax, eax
0x1800361a7  jmp     loc_180035E46
0x1800361ac  mov     r9, cs:?s_pRegLockZoneContainer@CUrlZoneManager@@1PEAVCRegZoneContainer@@EA; CRegZoneContainer * CUrlZoneManager::s_pRegLockZoneContainer
0x1800361b3  xor     r14d, r14d
0x1800361b6  mov     edx, r14d
0x1800361b9  mov     r11d, r14d
0x1800361bc  mov     r10d, [r9+18h]
0x1800361c0  cmp     edx, r10d
0x1800361c3  jnb     loc_180035E38
0x1800361c9  mov     rax, [r9+10h]
0x1800361cd  mov     ecx, edx
0x1800361cf  mov     r8, [rax+rcx*8]
0x1800361d3  test    r8, r8
0x1800361d6  jz      loc_180035E38
0x1800361dc  cmp     [r8], ebx
0x1800361df  jz      loc_180035E35
0x1800361e5  ja      loc_180035E38
0x1800361eb  inc     edx
0x1800361ed  jmp     short loc_1800361C0
0x1800361ef  lea     rax, ??_7CRegKey@@6B@; const CRegKey::`vftable'
0x1800361f6  mov     [rbp+3Fh+var_78], r15d
0x1800361fa  mov     [rbp+3Fh+var_88], rax
0x1800361fe  lea     rcx, [rbp+3Fh+var_88]; this
0x180036202  xor     eax, eax
0x180036204  mov     [rbp+3Fh+var_74], 1
0x18003620c  mov     [rbp+3Fh+hUSKey], rax
  ... truncated ...
```
