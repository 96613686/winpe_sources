# CRegZone::GetActionPolicy(ulong,_URLZONEREG,ulong &,int)

- ea: `0x18003589c`
- end: `0x180035d69`
- name: `?GetActionPolicy@CRegZone@@QEBAJKW4_URLZONEREG@@AEAKH@Z`
- size: `1229`
- prototype: `int(CRegZone *__hidden this, unsigned int, enum _URLZONEREG, unsigned int *, int)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180027dc0`
- `0x180035760`

## callees

- `0x18000eae0`
- `0x18001054c`
- `0x180013be0`
- `0x1800215c0`
- `0x1800342d0`
- `0x18003589c`
- `0x1800363e0`
- `0x180056d60`
- `0x18006b964`
- `0x18007ef30`
- `0x18011baa0`
- `0x18011c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800359c6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035c3a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800359c6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035c3a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003594c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035bed`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003594c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035bed`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180035abc`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180035b22`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180035b78`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180035c82`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180035abc`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180035b22`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180035b78`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180035c82`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegQueryUSValueW` at `0x180035bd0`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegQueryUSValueW` at `0x180035cd4`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegQueryUSValueW` at `0x180035bd0`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegQueryUSValueW` at `0x180035cd4`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x180035c58`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x180035c58`

## pseudocode

```c
__int64 __fastcall CRegZone::GetActionPolicy(
        CRegZone *this,
        unsigned int a2,
        enum _URLZONEREG a3,
        unsigned int *a4,
        int a5)
{
  unsigned int v5; // r13d
  unsigned int v8; // r12d
  __int64 v9; // rdi
  int v10; // r15d
  const WCHAR *v11; // rdx
  CSharedMem *v12; // rcx
  int v13; // r9d
  int i; // esi
  int v15; // r13d
  unsigned int v16; // ebx
  unsigned int v17; // ebx
  const WCHAR *v19; // rcx
  BOOL fIgnoreHKCU; // eax
  const WCHAR *v21; // rcx
  BOOL v22; // eax
  HUSKEY v23; // rcx
  __int64 v24; // rax
  HUSKEY phNewUSKey; // [rsp+40h] [rbp-51h] BYREF
  unsigned int v26; // [rsp+48h] [rbp-49h]
  LPCWSTR pwzPath; // [rsp+50h] [rbp-41h] BYREF
  const unsigned int *v28; // [rsp+58h] [rbp-39h] BYREF
  HUSKEY hUSKey; // [rsp+60h] [rbp-31h]
  BOOL v30; // [rsp+68h] [rbp-29h]
  __int64 v31; // [rsp+6Ch] [rbp-25h]
  LPCWSTR v32; // [rsp+78h] [rbp-19h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+80h] [rbp-11h]
  WCHAR pszValue[12]; // [rsp+88h] [rbp-9h] BYREF

  v5 = *(_DWORD *)this;
  v26 = v5;
  if ( v5 == -1 )
    return 2147500037LL;
  if ( a2 == 4610 || a2 == 4611 || a2 == 4612 || a2 == 5121 )
  {
    v8 = 4609;
  }
  else if ( a2 - 5634 < 2 )
  {
    v8 = 5633;
  }
  else
  {
    v8 = a2;
  }
  v9 = *((_QWORD *)this + 8);
  if ( a3 )
    v10 = a3 == URLZONEREG_HKLM;
  else
    v10 = *((_DWORD *)this + 10);
  v11 = (const WCHAR *)*((_QWORD *)this + 2);
  pwzPath = (LPCWSTR)*((_QWORD *)this + 3);
  v32 = v11;
  lpCriticalSection = (LPCRITICAL_SECTION)(v9 + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 16));
  if ( !(unsigned int)CSharedMem::IsCounterEqual(v12, *(_DWORD *)(v9 + 56) != 0 ? 0xC : 0, *(_DWORD *)v9, v13) )
    CRegZone::CRegZoneCache::Flush((CRegZone::CRegZoneCache *)v9);
  for ( i = 0; ; ++i )
  {
    if ( i >= 80 || *(_DWORD *)(v9 + 16 * (i + 4LL)) == -1 )
    {
      i = *(_DWORD *)(v9 + 1344);
      *(_DWORD *)(v9 + 1344) = (i + 1) % 80;
      goto LABEL_29;
    }
    if ( *(_DWORD *)(v9 + 16 * (i + 4LL)) == v5
      && *(_DWORD *)(v9 + 16LL * i + 68) == v8
      && *(_DWORD *)(v9 + 16LL * i + 72) == v10 )
    {
      break;
    }
  }
  if ( !a5 )
  {
    v15 = 1;
    if ( a4 )
      *a4 = *(_DWORD *)(v9 + 16LL * i + 76);
    goto LABEL_22;
  }
LABEL_29:
  v15 = 0;
  if ( (int)StringCchPrintfW(pszValue, 0xCu, L"%lX", v8) < 0 )
    goto LABEL_22;
  hUSKey = 0;
  phNewUSKey = 0;
  v28 = &CRegKey::`vftable';
  v30 = v10;
  v31 = 1;
  CRegKey::Close((CRegKey *)&v28);
  v19 = pwzPath;
  if ( !pwzPath )
    goto LABEL_39;
  if ( !(_DWORD)v31 )
    goto LABEL_32;
  fIgnoreHKCU = v30;
  if ( v30 )
  {
LABEL_33:
    if ( SHRegOpenUSKeyW(v19, 0x20019u, 0, &phNewUSKey, fIgnoreHKCU) )
      goto LABEL_39;
    goto LABEL_34;
  }
  if ( SHRegOpenUSKeyW(pwzPath, 0x20019u, 0, &phNewUSKey, 1) )
  {
    v19 = pwzPath;
LABEL_32:
    fIgnoreHKCU = v30;
    goto LABEL_33;
  }
LABEL_34:
  hUSKey = phNewUSKey;
  if ( !CRegKey::QueryValue((CRegKey *)&v28, a4, pszValue) )
  {
    v15 = 1;
    CRegZone::CRegZoneCache::Add((CRegZone::CRegZoneCache *)v9, v26, v8, v10, *a4, i);
    goto LABEL_49;
  }
LABEL_39:
  LODWORD(v31) = 0;
  phNewUSKey = 0;
  (*((void (__fastcall **)(const unsigned int **))v28 + 2))(&v28);
  v21 = v32;
  if ( !v32 )
    goto LABEL_49;
  if ( !(_DWORD)v31 )
    goto LABEL_41;
  v22 = v30;
  if ( v30 )
  {
LABEL_42:
    if ( SHRegOpenUSKeyW(v21, 0x20019u, 0, &phNewUSKey, v22) )
      goto LABEL_49;
    goto LABEL_43;
  }
  if ( SHRegOpenUSKeyW(v32, 0x20019u, 0, &phNewUSKey, 1) )
  {
    v21 = v32;
LABEL_41:
    v22 = v30;
    goto LABEL_42;
  }
LABEL_43:
  v23 = phNewUSKey;
  hUSKey = phNewUSKey;
  LODWORD(phNewUSKey) = 0;
  LODWORD(pwzPath) = 4;
  if ( !hUSKey )
    goto LABEL_22;
  if ( (_DWORD)v31 && !v30 )
  {
    if ( !SHRegQueryUSValueW(v23, pszValue, (DWORD *)&phNewUSKey, a4, (DWORD *)&pwzPath, 1, 0, 0) )
      goto LABEL_46;
    v23 = hUSKey;
  }
  if ( !SHRegQueryUSValueW(v23, pszValue, (DWORD *)&phNewUSKey, a4, (DWORD *)&pwzPath, v30, 0, 0) )
  {
LABEL_46:
    LODWORD(pwzPath) = *a4;
    v15 = 1;
    LODWORD(phNewUSKey) = i;
    EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 16));
    if ( i == -1 )
    {
      CRegZone::CRegZoneCache::FindCacheEntry((CRegZone::CRegZoneCache *)v9, v26, v8, v10, (int *)&phNewUSKey);
      i = (int)phNewUSKey;
    }
    v24 = 2 * (i + 4LL);
    *(_DWORD *)(v9 + 8 * v24) = v26;
    *(_DWORD *)(v9 + 8 * v24 + 12) = (_DWORD)pwzPath;
    *(_DWORD *)(v9 + 8 * v24 + 4) = v8;
    *(_DWORD *)(v9 + 8 * v24 + 8) = v10;
    CSharedMem::GetCounter((CSharedMem *)&g_SharedMem, *(_DWORD *)(v9 + 56) != 0 ? 0xC : 0, (unsigned int *)v9);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 16));
  }
LABEL_49:
  v28 = &CRegKey::`vftable';
  if ( hUSKey )
    SHRegCloseUSKey(hUSKey);
LABEL_22:
  LeaveCriticalSection(lpCriticalSection);
  if ( !v15 )
    return 2147500037LL;
  v16 = a2 - 4610;
  if ( !v16 || (v17 = v16 - 1) == 0 || v17 == 510 )
  {
    if ( (unsigned int)CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::FEATURE_RESPECT_OBJECTSAFETY_POLICY_KB905547) )
    {
      if ( (*a4 & 0xF) == 1 )
        *a4 = *a4 & 0xFFFFFFF0 | 3;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18003589c  mov     [rsp-8+arg_10], rbx
0x1800358a1  push    rbp
0x1800358a2  push    rsi
0x1800358a3  push    rdi
0x1800358a4  push    r12
0x1800358a6  push    r13
0x1800358a8  push    r14
0x1800358aa  push    r15
0x1800358ac  lea     rbp, [rsp-1Fh]
0x1800358b1  sub     rsp, 0B0h
0x1800358b8  mov     rax, cs:__security_cookie
0x1800358bf  xor     rax, rsp
0x1800358c2  mov     [rbp+4Fh+var_40], rax
0x1800358c6  mov     r13d, [rcx]
0x1800358c9  mov     r14, r9
0x1800358cc  mov     [rbp+4Fh+var_98], r13d
0x1800358d0  mov     ebx, edx
0x1800358d2  cmp     r13d, 0FFFFFFFFh
0x1800358d6  jz      loc_180035A1B
0x1800358dc  mov     eax, edx
0x1800358de  sub     eax, 1202h
0x1800358e3  jz      loc_180035CF8
0x1800358e9  sub     eax, 1
0x1800358ec  jz      loc_180035CF8
0x1800358f2  sub     eax, 1
0x1800358f5  jz      loc_180035CF8
0x1800358fb  sub     eax, 1FDh
0x180035900  jz      loc_180035CF8
0x180035906  sub     eax, 201h
0x18003590b  jz      loc_180035CED
0x180035911  cmp     eax, 1
0x180035914  jz      loc_180035CED
0x18003591a  mov     r12d, edx
0x18003591d  mov     rdi, [rcx+40h]
0x180035921  xor     r15d, r15d
0x180035924  test    r8d, r8d
0x180035927  jnz     loc_180035D03
0x18003592d  mov     r15d, [rcx+28h]
0x180035931  mov     rax, [rcx+18h]
0x180035935  mov     rdx, [rcx+10h]
0x180035939  mov     [rbp+4Fh+pwzPath], rax
0x18003593d  lea     rax, [rdi+10h]
0x180035941  mov     rcx, rax; lpCriticalSection
0x180035944  mov     [rbp+4Fh+var_68], rdx
0x180035948  mov     [rbp+4Fh+lpCriticalSection], rax
0x18003594c  call    cs:__imp_EnterCriticalSection
0x180035952  mov     eax, [rdi+38h]
0x180035955  mov     r8d, [rdi]; unsigned int
0x180035958  neg     eax
0x18003595a  sbb     edx, edx
0x18003595c  and     edx, 0Ch; unsigned int
0x18003595f  call    ?IsCounterEqual@CSharedMem@@QEAAHKKH@Z; CSharedMem::IsCounterEqual(ulong,ulong,int)
0x180035964  test    eax, eax
0x180035966  jz      loc_180035C99
0x18003596c  xor     esi, esi
0x18003596e  cmp     esi, 50h ; 'P'
0x180035971  jge     loc_180035A22
0x180035977  movsxd  rcx, esi
0x18003597a  lea     rax, [rcx+4]
0x18003597e  add     rax, rax
0x180035981  cmp     dword ptr [rdi+rax*8], 0FFFFFFFFh
0x180035985  jz      loc_180035A22
0x18003598b  cmp     [rdi+rax*8], r13d
0x18003598f  jnz     short loc_18003599B
0x180035991  add     rcx, rcx
0x180035994  cmp     [rdi+rcx*8+44h], r12d
0x180035999  jz      short loc_18003599F
0x18003599b  inc     esi
0x18003599d  jmp     short loc_18003596E
0x18003599f  cmp     [rdi+rcx*8+48h], r15d
0x1800359a4  jnz     short loc_18003599B
0x1800359a6  cmp     [rbp+4Fh+arg_20], 0
0x1800359aa  jnz     loc_180035A4A
0x1800359b0  mov     r13d, 1
0x1800359b6  test    r14, r14
0x1800359b9  jz      short loc_1800359C2
0x1800359bb  mov     eax, [rdi+rcx*8+4Ch]
0x1800359bf  mov     [r14], eax
0x1800359c2  mov     rcx, [rbp+4Fh+lpCriticalSection]; lpCriticalSection
0x1800359c6  call    cs:__imp_LeaveCriticalSection
0x1800359cc  test    r13d, r13d
0x1800359cf  jz      short loc_180035A1B
0x1800359d1  sub     ebx, 1202h
0x1800359d7  jz      loc_180035D38
0x1800359dd  sub     ebx, 1
0x1800359e0  jz      loc_180035D38
0x1800359e6  cmp     ebx, 1FEh
0x1800359ec  jz      loc_180035D38
0x1800359f2  xor     eax, eax
0x1800359f4  mov     rcx, [rbp+4Fh+var_40]
0x1800359f8  xor     rcx, rsp; StackCookie
0x1800359fb  call    __security_check_cookie
0x180035a00  mov     rbx, [rsp+0E0h+arg_10]
0x180035a08  add     rsp, 0B0h
0x180035a0f  pop     r15
0x180035a11  pop     r14
0x180035a13  pop     r13
0x180035a15  pop     r12
0x180035a17  pop     rdi
0x180035a18  pop     rsi
0x180035a19  pop     rbp
0x180035a1a  retn
0x180035a1b  mov     eax, 80004005h
0x180035a20  jmp     short loc_1800359F4
0x180035a22  mov     esi, [rdi+540h]
0x180035a28  mov     eax, 66666667h
0x180035a2d  lea     ecx, [rsi+1]
0x180035a30  imul    ecx
0x180035a32  sar     edx, 5
0x180035a35  mov     eax, edx
0x180035a37  shr     eax, 1Fh
0x180035a3a  add     edx, eax
0x180035a3c  lea     eax, [rdx+rdx*4]
0x180035a3f  shl     eax, 4
0x180035a42  sub     ecx, eax
0x180035a44  mov     [rdi+540h], ecx
0x180035a4a  xor     r13d, r13d
0x180035a4d  lea     r8, aLx; "%lX"
0x180035a54  mov     r9d, r12d
0x180035a57  lea     rcx, [rbp+4Fh+pszValue]; unsigned __int16 *
0x180035a5b  lea     edx, [r13+0Ch]; unsigned __int64
0x180035a5f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180035a64  xor     ecx, ecx
0x180035a66  test    eax, eax
0x180035a68  js      loc_1800359C2
0x180035a6e  lea     rax, ??_7CRegKey@@6B@; const CRegKey::`vftable'
0x180035a75  mov     [rbp+4Fh+hUSKey], rcx
0x180035a79  mov     [rbp+4Fh+phNewUSKey], rcx
0x180035a7d  lea     rcx, [rbp+4Fh+var_88]; this
0x180035a81  mov     [rbp+4Fh+var_88], rax
0x180035a85  mov     [rbp+4Fh+var_78], r15d
0x180035a89  mov     [rbp+4Fh+var_74], 1
0x180035a91  call    ?Close@CRegKey@@UEAAJXZ; CRegKey::Close(void)
0x180035a96  mov     rcx, [rbp+4Fh+pwzPath]; pwzPath
0x180035a9a  test    rcx, rcx
0x180035a9d  jz      loc_180035B35
0x180035aa3  cmp     dword ptr [rbp+4Fh+var_74], r13d
0x180035aa7  jnz     short loc_180035B07
0x180035aa9  mov     eax, [rbp+4Fh+var_78]
0x180035aac  lea     r9, [rbp+4Fh+phNewUSKey]; phNewUSKey
0x180035ab0  mov     [rsp+0E0h+fIgnoreHKCU], eax; fIgnoreHKCU
0x180035ab4  xor     r8d, r8d; hRelativeUSKey
0x180035ab7  mov     edx, 20019h; samDesired
0x180035abc  call    cs:__imp_SHRegOpenUSKeyW
0x180035ac2  test    eax, eax
0x180035ac4  jnz     short loc_180035B35
0x180035ac6  mov     rax, [rbp+4Fh+phNewUSKey]
0x180035aca  lea     r8, [rbp+4Fh+pszValue]; unsigned __int16 *
0x180035ace  mov     rdx, r14; unsigned int *
0x180035ad1  mov     [rbp+4Fh+hUSKey], rax
0x180035ad5  lea     rcx, [rbp+4Fh+var_88]; this
0x180035ad9  call    ?QueryValue@CRegKey@@QEAAJPEAKPEBG@Z; CRegKey::QueryValue(ulong *,ushort const *)
0x180035ade  test    eax, eax
0x180035ae0  jnz     short loc_180035B35
0x180035ae2  mov     edx, [rbp+4Fh+var_98]; unsigned int
0x180035ae5  lea     r13d, [rax+1]
0x180035ae9  mov     eax, [r14]
0x180035aec  mov     r9d, r15d; int
0x180035aef  mov     [rsp+0E0h+var_B8], esi; int
0x180035af3  mov     r8d, r12d; unsigned int
0x180035af6  mov     rcx, rdi; this
0x180035af9  mov     [rsp+0E0h+fIgnoreHKCU], eax; unsigned int
0x180035afd  call    ?Add@CRegZoneCache@CRegZone@@QEAAXKKHKH@Z; CRegZone::CRegZoneCache::Add(ulong,ulong,int,ulong,int)
0x180035b02  jmp     loc_180035C40
0x180035b07  mov     eax, [rbp+4Fh+var_78]
0x180035b0a  test    eax, eax
0x180035b0c  jnz     short loc_180035AAC
0x180035b0e  lea     r9, [rbp+4Fh+phNewUSKey]; phNewUSKey
0x180035b12  mov     [rsp+0E0h+fIgnoreHKCU], 1; fIgnoreHKCU
0x180035b1a  xor     r8d, r8d; hRelativeUSKey
0x180035b1d  mov     edx, 20019h; samDesired
0x180035b22  call    cs:__imp_SHRegOpenUSKeyW
0x180035b28  test    eax, eax
0x180035b2a  jz      short loc_180035AC6
0x180035b2c  mov     rcx, [rbp+4Fh+pwzPath]
0x180035b30  jmp     loc_180035AA9
0x180035b35  mov     rax, [rbp+4Fh+var_88]
0x180035b39  lea     rcx, [rbp+4Fh+var_88]
0x180035b3d  mov     dword ptr [rbp+4Fh+var_74], r13d
0x180035b41  mov     [rbp+4Fh+phNewUSKey], r13
0x180035b45  mov     rax, [rax+10h]
0x180035b49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035b4e  mov     rcx, [rbp+4Fh+var_68]; pwzPath
0x180035b52  test    rcx, rcx
0x180035b55  jz      loc_180035C40
0x180035b5b  cmp     dword ptr [rbp+4Fh+var_74], r13d
0x180035b5f  jnz     loc_180035C63
0x180035b65  mov     eax, [rbp+4Fh+var_78]
0x180035b68  lea     r9, [rbp+4Fh+phNewUSKey]; phNewUSKey
0x180035b6c  mov     [rsp+0E0h+fIgnoreHKCU], eax; fIgnoreHKCU
0x180035b70  xor     r8d, r8d; hRelativeUSKey
0x180035b73  mov     edx, 20019h; samDesired
0x180035b78  call    cs:__imp_SHRegOpenUSKeyW
0x180035b7e  test    eax, eax
0x180035b80  jnz     loc_180035C40
0x180035b86  mov     rcx, [rbp+4Fh+phNewUSKey]; hUSKey
0x180035b8a  xor     eax, eax
0x180035b8c  mov     [rbp+4Fh+hUSKey], rcx
0x180035b90  mov     dword ptr [rbp+4Fh+phNewUSKey], eax
0x180035b93  mov     dword ptr [rbp+4Fh+pwzPath], 4
0x180035b9a  test    rcx, rcx
0x180035b9d  jz      loc_1800359C2
0x180035ba3  cmp     dword ptr [rbp+4Fh+var_74], eax
0x180035ba6  jnz     loc_180035CA6
0x180035bac  mov     [rsp+0E0h+dwDefaultDataSize], eax; dwDefaultDataSize
0x180035bb0  lea     r8, [rbp+4Fh+phNewUSKey]; pdwType
0x180035bb4  mov     [rsp+0E0h+pvDefaultData], rax; pvDefaultData
0x180035bb9  lea     rdx, [rbp+4Fh+pszValue]; pszValue
0x180035bbd  mov     eax, [rbp+4Fh+var_78]
0x180035bc0  mov     r9, r14; pvData
0x180035bc3  mov     [rsp+0E0h+var_B8], eax; fIgnoreHKCU
0x180035bc7  lea     rax, [rbp+4Fh+pwzPath]
0x180035bcb  mov     qword ptr [rsp+0E0h+fIgnoreHKCU], rax; pcbData
0x180035bd0  call    cs:__imp_SHRegQueryUSValueW
0x180035bd6  test    eax, eax
0x180035bd8  jnz     short loc_180035C40
0x180035bda  mov     eax, [r14]
0x180035bdd  lea     rcx, [rdi+10h]; lpCriticalSection
0x180035be1  mov     dword ptr [rbp+4Fh+pwzPath], eax
0x180035be4  mov     r13d, 1
0x180035bea  mov     dword ptr [rbp+4Fh+phNewUSKey], esi
0x180035bed  call    cs:__imp_EnterCriticalSection
0x180035bf3  cmp     esi, 0FFFFFFFFh
0x180035bf6  jz      loc_180035D16
0x180035bfc  mov     ecx, [rbp+4Fh+var_98]
0x180035bff  mov     r8, rdi; unsigned int *
0x180035c02  movsxd  rax, esi
0x180035c05  add     rax, 4
0x180035c09  add     rax, rax
0x180035c0c  mov     [rdi+rax*8], ecx
0x180035c0f  mov     ecx, dword ptr [rbp+4Fh+pwzPath]
0x180035c12  mov     [rdi+rax*8+0Ch], ecx
0x180035c16  lea     rcx, ?g_SharedMem@@3VCSharedMem@@A; this
0x180035c1d  mov     [rdi+rax*8+4], r12d
0x180035c22  mov     [rdi+rax*8+8], r15d
0x180035c27  mov     eax, [rdi+38h]
0x180035c2a  neg     eax
0x180035c2c  sbb     edx, edx
0x180035c2e  and     edx, 0Ch; unsigned int
0x180035c31  call    ?GetCounter@CSharedMem@@QEAAHKPEAK@Z; CSharedMem::GetCounter(ulong,ulong *)
0x180035c36  lea     rcx, [rdi+10h]; lpCriticalSection
0x180035c3a  call    cs:__imp_LeaveCriticalSection
0x180035c40  mov     rcx, [rbp+4Fh+hUSKey]; hUSKey
0x180035c44  lea     rax, ??_7CRegKey@@6B@; const CRegKey::`vftable'
0x180035c4b  mov     [rbp+4Fh+var_88], rax
0x180035c4f  test    rcx, rcx
0x180035c52  jz      loc_1800359C2
0x180035c58  call    cs:__imp_SHRegCloseUSKey
0x180035c5e  jmp     loc_1800359C2
0x180035c63  mov     eax, [rbp+4Fh+var_78]
0x180035c66  test    eax, eax
0x180035c68  jnz     loc_180035B68
0x180035c6e  lea     r9, [rbp+4Fh+phNewUSKey]; phNewUSKey
0x180035c72  mov     [rsp+0E0h+fIgnoreHKCU], 1; fIgnoreHKCU
0x180035c7a  xor     r8d, r8d; hRelativeUSKey
0x180035c7d  mov     edx, 20019h; samDesired
0x180035c82  call    cs:__imp_SHRegOpenUSKeyW
0x180035c88  test    eax, eax
0x180035c8a  jz      loc_180035B86
0x180035c90  mov     rcx, [rbp+4Fh+var_68]
0x180035c94  jmp     loc_180035B65
0x180035c99  mov     rcx, rdi; this
0x180035c9c  call    ?Flush@CRegZoneCache@CRegZone@@QEAAXXZ; CRegZone::CRegZoneCache::Flush(void)
0x180035ca1  jmp     loc_18003596C
0x180035ca6  cmp     [rbp+4Fh+var_78], eax
0x180035ca9  jnz     loc_180035BAC
0x180035caf  mov     [rsp+0E0h+dwDefaultDataSize], eax; dwDefaultDataSize
0x180035cb3  lea     r8, [rbp+4Fh+phNewUSKey]; pdwType
0x180035cb7  mov     [rsp+0E0h+pvDefaultData], rax; pvDefaultData
0x180035cbc  lea     rdx, [rbp+4Fh+pszValue]; pszValue
0x180035cc0  lea     rax, [rbp+4Fh+pwzPath]
0x180035cc4  mov     [rsp+0E0h+var_B8], 1; fIgnoreHKCU
0x180035ccc  mov     r9, r14; pvData
0x180035ccf  mov     qword ptr [rsp+0E0h+fIgnoreHKCU], rax; pcbData
0x180035cd4  call    cs:__imp_SHRegQueryUSValueW
0x180035cda  test    eax, eax
0x180035cdc  jz      loc_180035BDA
0x180035ce2  mov     rcx, [rbp+4Fh+hUSKey]
0x180035ce6  xor     eax, eax
0x180035ce8  jmp     loc_180035BAC
0x180035ced  mov     r12d, 1601h
0x180035cf3  jmp     loc_18003591D
0x180035cf8  mov     r12d, 1201h
0x180035cfe  jmp     loc_18003591D
0x180035d03  sub     r8d, 1
0x180035d07  jnz     loc_180035931
0x180035d0d  lea     r15d, [r8+1]
0x180035d11  jmp     loc_180035931
0x180035d16  mov     edx, [rbp+4Fh+var_98]; unsigned int
0x180035d19  lea     rax, [rbp+4Fh+phNewUSKey]
0x180035d1d  mov     r9d, r15d; int
0x180035d20  mov     qword ptr [rsp+0E0h+fIgnoreHKCU], rax; int *
0x180035d25  mov     r8d, r12d; unsigned int
0x180035d28  mov     rcx, rdi; this
0x180035d2b  call    ?FindCacheEntry@CRegZoneCache@CRegZone@@IEAAHKKHAEAH@Z; CRegZone::CRegZoneCache::FindCacheEntry(ulong,ulong,int,int &)
0x180035d30  mov     esi, dword ptr [rbp+4Fh+phNewUSKey]
0x180035d33  jmp     loc_180035BFC
0x180035d38  lea     rcx, ?FEATURE_RESPECT_OBJECTSAFETY_POLICY_KB905547@FCK@@3VCFeatureControlKey@@A; this
0x180035d3f  call    ?_CoInternetIsFeatureEnabledInternal@CFeatureControlKey@@QEAAJXZ; CFeatureControlKey::_CoInternetIsFeatureEnabledInternal(void)
0x180035d44  test    eax, eax
  ... truncated ...
```
