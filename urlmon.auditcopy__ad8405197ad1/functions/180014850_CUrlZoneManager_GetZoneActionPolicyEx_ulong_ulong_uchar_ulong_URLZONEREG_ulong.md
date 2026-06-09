# CUrlZoneManager::GetZoneActionPolicyEx(ulong,ulong,uchar *,ulong,_URLZONEREG,ulong)

- ea: `0x180014850`
- end: `0x180014f24`
- name: `?GetZoneActionPolicyEx@CUrlZoneManager@@UEAAJKKPEAEKW4_URLZONEREG@@K@Z`
- size: `1748`
- prototype: `__int64 __fastcall(CUrlZoneManager *this, unsigned int, unsigned int, unsigned __int8 *, unsigned int, enum _URLZONEREG, unsigned int)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180014850`
- `0x1800162d4`
- `0x18001721c`
- `0x18001c070`
- `0x180028510`
- `0x18003bef0`
- `0x18005c800`
- `0x1800704b8`
- `0x180071894`
- `0x18008457c`
- `0x180128660`
- `0x180129010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800148df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001498e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014abb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014b18`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014c6c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014ca0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800148df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001498e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014abb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014b18`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014c6c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014ca0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800148bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014a4a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014c1c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800148bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014a4a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014c1c`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180014b96`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180014d70`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180014dec`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180014e24`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180014b96`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180014d70`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180014dec`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180014e24`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegQueryUSValueW` at `0x180014bfc`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegQueryUSValueW` at `0x180014e7b`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegQueryUSValueW` at `0x180014bfc`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegQueryUSValueW` at `0x180014e7b`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x180014c90`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x180014c90`

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
  int v16; // esi
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
  if ( byte_18016B8D0 && (v14 = qword_18016B8C8) != 0 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_18016B8C8 + 8LL))(qword_18016B8C8);
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
0x180014850  mov     [rsp-8+arg_0], rbx
0x180014855  push    rbp
0x180014856  push    rsi
0x180014857  push    rdi
0x180014858  push    r12
0x18001485a  push    r13
0x18001485c  push    r14
0x18001485e  push    r15
0x180014860  lea     rbp, [rsp-0Fh]
0x180014865  sub     rsp, 0B0h
0x18001486c  mov     rax, cs:__security_cookie
0x180014873  xor     rax, rsp
0x180014876  mov     [rbp+3Fh+var_40], rax
0x18001487a  mov     r14d, [rbp+3Fh+arg_30]
0x18001487e  mov     r13, r9
0x180014881  mov     dword ptr [rbp+3Fh+phNewUSKey], r14d
0x180014885  mov     r15d, r8d
0x180014888  mov     [rbp+3Fh+pvData], r9
0x18001488c  mov     ebx, edx
0x18001488e  mov     [rbp+3Fh+var_60], r8d
0x180014892  test    r9, r9
0x180014895  jz      loc_18001493B
0x18001489b  mov     edi, [rbp+3Fh+arg_20]
0x18001489e  cmp     edi, 4
0x1800148a1  jb      loc_18001493B
0x1800148a7  test    r14d, 0FFFAFFFFh
0x1800148ae  jnz     loc_18001493B
0x1800148b4  lea     rcx, ?g_mxsPermanentISM@@3VCMutexSem@@A; lpCriticalSection
0x1800148bb  call    cs:__imp_EnterCriticalSection
0x1800148c2  nop     dword ptr [rax+rax+00h]
0x1800148c7  cmp     cs:byte_18016B8D0, 0
0x1800148ce  mov     r12d, [rbp+3Fh+arg_28]
0x1800148d2  jnz     loc_180014968
0x1800148d8  lea     rcx, ?g_mxsPermanentISM@@3VCMutexSem@@A; lpCriticalSection
0x1800148df  call    cs:__imp_LeaveCriticalSection
0x1800148e6  nop     dword ptr [rax+rax+00h]
0x1800148eb  bt      r14d, 10h
0x1800148f0  jb      loc_180014CDE
0x1800148f6  mov     r10, cs:?s_pRegZoneContainer@CUrlZoneManager@@1PEAVCRegZoneContainer@@EA; CRegZoneContainer * CUrlZoneManager::s_pRegZoneContainer
0x1800148fd  xor     r14d, r14d
0x180014900  mov     eax, r14d
0x180014903  mov     r11d, r14d
0x180014906  mov     r9d, [r10+18h]
0x18001490a  nop     word ptr [rax+rax+00h]
0x180014910  cmp     eax, r9d
0x180014913  jnb     short loc_180014932
0x180014915  mov     rcx, [r10+10h]
0x180014919  mov     edx, eax
0x18001491b  mov     r8, [rcx+rdx*8]
0x18001491f  test    r8, r8
0x180014922  jz      short loc_180014932
0x180014924  cmp     [r8], ebx
0x180014927  jz      short loc_18001492F
0x180014929  ja      short loc_180014932
0x18001492b  inc     eax
0x18001492d  jmp     short loc_180014910
0x18001492f  mov     r11, r8
0x180014932  test    r11, r11
0x180014935  jnz     loc_1800149E3
0x18001493b  mov     eax, 80070057h
0x180014940  mov     rcx, [rbp+3Fh+var_40]
0x180014944  xor     rcx, rsp; StackCookie
0x180014947  call    __security_check_cookie
0x18001494c  mov     rbx, [rsp+0E0h+arg_0]
0x180014954  add     rsp, 0B0h
0x18001495b  pop     r15
0x18001495d  pop     r14
0x18001495f  pop     r13
0x180014961  pop     r12
0x180014963  pop     rdi
0x180014964  pop     rsi
0x180014965  pop     rbp
0x180014966  retn
0x180014968  mov     rsi, cs:qword_18016B8C8
0x18001496f  test    rsi, rsi
0x180014972  jz      loc_1800148D8
0x180014978  mov     rax, [rsi]
0x18001497b  mov     rcx, rsi
0x18001497e  mov     rax, [rax+8]
0x180014982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014987  lea     rcx, ?g_mxsPermanentISM@@3VCMutexSem@@A; lpCriticalSection
0x18001498e  call    cs:__imp_LeaveCriticalSection
0x180014995  nop     dword ptr [rax+rax+00h]
0x18001499a  mov     rax, [rsi]
0x18001499d  mov     r9, r13
0x1800149a0  mov     dword ptr [rsp+0E0h+pvDefaultData], r14d
0x1800149a5  mov     r8d, r15d
0x1800149a8  mov     [rsp+0E0h+var_B8], r12d
0x1800149ad  mov     edx, ebx
0x1800149af  mov     rcx, rsi
0x1800149b2  mov     [rsp+0E0h+fIgnoreHKCU], edi
0x1800149b6  mov     rax, [rax+18h]
0x1800149ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149bf  mov     rdx, [rsi]
0x1800149c2  mov     edi, eax
0x1800149c4  mov     rcx, rsi
0x1800149c7  mov     rax, [rdx+10h]
0x1800149cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149d0  cmp     edi, 800C0011h
0x1800149d6  jz      loc_1800148EB
0x1800149dc  mov     eax, edi
0x1800149de  jmp     loc_180014940
0x1800149e3  mov     esi, [r11]
0x1800149e6  cmp     esi, 0FFFFFFFFh
0x1800149e9  jz      loc_180014B24
0x1800149ef  cmp     r15d, 1401h
0x1800149f6  ja      loc_180014B2E
0x1800149fc  jz      loc_180014E94
0x180014a02  mov     eax, r15d
0x180014a05  sub     eax, 1202h
0x180014a0a  jz      loc_180014E94
0x180014a10  sub     eax, 1
0x180014a13  jz      loc_180014E94
0x180014a19  cmp     eax, 1
0x180014a1c  jz      loc_180014E94
0x180014a22  mov     r13d, r15d
0x180014a25  mov     rdi, [r11+40h]
0x180014a29  test    r12d, r12d
0x180014a2c  jnz     loc_180014E9F
0x180014a32  mov     r15d, [r11+28h]
0x180014a36  mov     [rbp+3Fh+var_98], r15d
0x180014a3a  mov     rax, [r11+10h]
0x180014a3e  lea     rcx, [rdi+10h]; lpCriticalSection
0x180014a42  mov     r14, [r11+18h]
0x180014a46  mov     [rbp+3Fh+pwzPath], rax
0x180014a4a  call    cs:__imp_EnterCriticalSection
0x180014a51  nop     dword ptr [rax+rax+00h]
0x180014a56  mov     eax, [rdi+38h]
0x180014a59  mov     r8d, [rdi]; unsigned int
0x180014a5c  neg     eax
0x180014a5e  sbb     edx, edx
0x180014a60  and     edx, 0Ch; unsigned int
0x180014a63  call    ?IsCounterEqual@CSharedMem@@QEAAHKKH@Z; CSharedMem::IsCounterEqual(ulong,ulong,int)
0x180014a68  test    eax, eax
0x180014a6a  jz      loc_180014E3D
0x180014a70  xor     ebx, ebx
0x180014a72  cmp     ebx, 50h ; 'P'
0x180014a75  jge     short loc_180014ACC
0x180014a77  movsxd  rdx, ebx
0x180014a7a  lea     rax, [rdx+4]
0x180014a7e  add     rax, rax
0x180014a81  mov     ecx, [rdi+rax*8]
0x180014a84  cmp     ecx, 0FFFFFFFFh
0x180014a87  jz      short loc_180014ACC
0x180014a89  cmp     ecx, esi
0x180014a8b  jnz     short loc_180014A9B
0x180014a8d  add     rdx, rdx
0x180014a90  cmp     [rdi+rdx*8+44h], r13d
0x180014a95  lea     rax, [rdi+rdx*8]
0x180014a99  jz      short loc_180014A9F
0x180014a9b  inc     ebx
0x180014a9d  jmp     short loc_180014A72
0x180014a9f  cmp     [rax+48h], r15d
0x180014aa3  jnz     short loc_180014A9B
0x180014aa5  test    dword ptr [rbp+3Fh+phNewUSKey], 40000h
0x180014aac  jnz     short loc_180014AF4
0x180014aae  mov     eax, [rax+4Ch]
0x180014ab1  lea     rcx, [rdi+10h]; lpCriticalSection
0x180014ab5  mov     rbx, [rbp+3Fh+pvData]
0x180014ab9  mov     [rbx], eax
0x180014abb  call    cs:__imp_LeaveCriticalSection
0x180014ac2  nop     dword ptr [rax+rax+00h]
0x180014ac7  jmp     loc_180014CB5
0x180014acc  mov     ebx, [rdi+540h]
0x180014ad2  mov     eax, 66666667h
0x180014ad7  lea     ecx, [rbx+1]
0x180014ada  imul    ecx
0x180014adc  sar     edx, 5
0x180014adf  mov     eax, edx
0x180014ae1  shr     eax, 1Fh
0x180014ae4  add     edx, eax
0x180014ae6  lea     eax, [rdx+rdx*4]
0x180014ae9  shl     eax, 4
0x180014aec  sub     ecx, eax
0x180014aee  mov     [rdi+540h], ecx
0x180014af4  mov     r9d, r13d
0x180014af7  lea     r8, aLx; "%lX"
0x180014afe  mov     edx, 0Ch; unsigned __int64
0x180014b03  lea     rcx, [rbp+3Fh+pszValue]; unsigned __int16 *
0x180014b07  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180014b0c  test    eax, eax
0x180014b0e  jns     loc_180014D21
0x180014b14  lea     rcx, [rdi+10h]; lpCriticalSection
0x180014b18  call    cs:__imp_LeaveCriticalSection
0x180014b1f  nop     dword ptr [rax+rax+00h]
0x180014b24  mov     eax, 80004005h
0x180014b29  jmp     loc_180014940
0x180014b2e  mov     eax, r15d
0x180014b31  sub     eax, 1602h
0x180014b36  jz      short loc_180014B41
0x180014b38  cmp     eax, 1
0x180014b3b  jnz     loc_180014A22
0x180014b41  mov     r13d, 1601h
0x180014b47  jmp     loc_180014A25
0x180014b4c  xor     eax, eax
0x180014b4e  lea     rcx, [rbp+3Fh+var_88]
0x180014b52  mov     r14d, eax
0x180014b55  mov     dword ptr [rbp+3Fh+var_74], eax
0x180014b58  mov     [rbp+3Fh+phNewUSKey], rax
0x180014b5c  mov     rax, [rbp+3Fh+var_88]
0x180014b60  mov     rax, [rax+10h]
0x180014b64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b69  mov     r15, [rbp+3Fh+pwzPath]
0x180014b6d  test    r15, r15
0x180014b70  jz      loc_180014C78
0x180014b76  cmp     dword ptr [rbp+3Fh+var_74], r14d
0x180014b7a  jnz     loc_180014E02
0x180014b80  mov     eax, [rbp+3Fh+var_78]
0x180014b83  lea     r9, [rbp+3Fh+phNewUSKey]; phNewUSKey
0x180014b87  mov     [rsp+0E0h+fIgnoreHKCU], eax; fIgnoreHKCU
0x180014b8b  xor     r8d, r8d; hRelativeUSKey
0x180014b8e  mov     edx, 20019h; samDesired
0x180014b93  mov     rcx, r15; pwzPath
0x180014b96  call    cs:__imp_SHRegOpenUSKeyW
0x180014b9d  nop     dword ptr [rax+rax+00h]
0x180014ba2  test    eax, eax
0x180014ba4  jnz     loc_180014C78
0x180014baa  mov     rcx, [rbp+3Fh+phNewUSKey]; hUSKey
0x180014bae  xor     r15d, r15d
0x180014bb1  mov     [rbp+3Fh+hUSKey], rcx
0x180014bb5  mov     dword ptr [rbp+3Fh+phNewUSKey], r15d
0x180014bb9  mov     dword ptr [rbp+3Fh+pwzPath], 4
0x180014bc0  test    rcx, rcx
0x180014bc3  jz      loc_180014B14
0x180014bc9  cmp     dword ptr [rbp+3Fh+var_74], r14d
0x180014bcd  jnz     loc_180014E4A
0x180014bd3  mov     eax, [rbp+3Fh+var_78]
0x180014bd6  lea     r8, [rbp+3Fh+phNewUSKey]; pdwType
0x180014bda  mov     [rsp+0E0h+dwDefaultDataSize], r15d; dwDefaultDataSize
0x180014bdf  lea     rdx, [rbp+3Fh+pszValue]; pszValue
0x180014be3  mov     [rsp+0E0h+pvDefaultData], r15; pvDefaultData
0x180014be8  mov     r15, [rbp+3Fh+pvData]
0x180014bec  mov     [rsp+0E0h+var_B8], eax; fIgnoreHKCU
0x180014bf0  mov     r9, r15; pvData
0x180014bf3  lea     rax, [rbp+3Fh+pwzPath]
0x180014bf7  mov     qword ptr [rsp+0E0h+fIgnoreHKCU], rax; pcbData
0x180014bfc  call    cs:__imp_SHRegQueryUSValueW
0x180014c03  nop     dword ptr [rax+rax+00h]
0x180014c08  test    eax, eax
0x180014c0a  jnz     short loc_180014C78
0x180014c0c  mov     r15d, [r15]
0x180014c0f  lea     rcx, [rdi+10h]; lpCriticalSection
0x180014c13  mov     r14d, 1
0x180014c19  mov     dword ptr [rbp+3Fh+phNewUSKey], ebx
0x180014c1c  call    cs:__imp_EnterCriticalSection
0x180014c23  nop     dword ptr [rax+rax+00h]
0x180014c28  cmp     ebx, 0FFFFFFFFh
0x180014c2b  jz      loc_180014ED3
0x180014c31  mov     ecx, [rbp+3Fh+var_98]
0x180014c34  mov     r8, rdi; unsigned int *
0x180014c37  movsxd  rax, ebx
0x180014c3a  add     rax, 4
0x180014c3e  add     rax, rax
0x180014c41  mov     [rdi+rax*8+8], ecx
0x180014c45  lea     rcx, ?g_SharedMem@@3VCSharedMem@@A; this
0x180014c4c  mov     [rdi+rax*8], esi
0x180014c4f  mov     [rdi+rax*8+4], r13d
0x180014c54  mov     [rdi+rax*8+0Ch], r15d
0x180014c59  mov     eax, [rdi+38h]
0x180014c5c  neg     eax
0x180014c5e  sbb     edx, edx
0x180014c60  and     edx, 0Ch; unsigned int
0x180014c63  call    ?GetCounter@CSharedMem@@QEAAHKPEAK@Z; CSharedMem::GetCounter(ulong,ulong *)
0x180014c68  lea     rcx, [rdi+10h]; lpCriticalSection
0x180014c6c  call    cs:__imp_LeaveCriticalSection
0x180014c73  nop     dword ptr [rax+rax+00h]
0x180014c78  mov     rbx, [rbp+3Fh+pvData]
0x180014c7c  mov     rcx, [rbp+3Fh+hUSKey]; hUSKey
0x180014c80  lea     rax, ??_7CRegKey@@6B@; const CRegKey::`vftable'
0x180014c87  mov     [rbp+3Fh+var_88], rax
0x180014c8b  test    rcx, rcx
0x180014c8e  jz      short loc_180014C9C
0x180014c90  call    cs:__imp_SHRegCloseUSKey
0x180014c97  nop     dword ptr [rax+rax+00h]
0x180014c9c  lea     rcx, [rdi+10h]; lpCriticalSection
0x180014ca0  call    cs:__imp_LeaveCriticalSection
0x180014ca7  nop     dword ptr [rax+rax+00h]
0x180014cac  test    r14d, r14d
0x180014caf  jz      loc_180014B24
0x180014cb5  mov     eax, [rbp+3Fh+var_60]
0x180014cb8  sub     eax, 1202h
0x180014cbd  jz      loc_180014EF5
0x180014cc3  sub     eax, 1
0x180014cc6  jz      loc_180014EF5
0x180014ccc  cmp     eax, 1FEh
0x180014cd1  jz      loc_180014EF5
0x180014cd7  xor     eax, eax
0x180014cd9  jmp     loc_180014940
0x180014cde  mov     r9, cs:?s_pRegLockZoneContainer@CUrlZoneManager@@1PEAVCRegZoneContainer@@EA; CRegZoneContainer * CUrlZoneManager::s_pRegLockZoneContainer
0x180014ce5  xor     r14d, r14d
0x180014ce8  mov     edx, r14d
0x180014ceb  mov     r11d, r14d
0x180014cee  mov     r10d, [r9+18h]
0x180014cf2  cmp     edx, r10d
0x180014cf5  jnb     loc_180014932
0x180014cfb  mov     rax, [r9+10h]
0x180014cff  mov     ecx, edx
0x180014d01  mov     r8, [rax+rcx*8]
0x180014d05  test    r8, r8
0x180014d08  jz      loc_180014932
  ... truncated ...
```
