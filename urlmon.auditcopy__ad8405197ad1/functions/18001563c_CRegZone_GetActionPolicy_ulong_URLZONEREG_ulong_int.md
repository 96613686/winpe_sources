# CRegZone::GetActionPolicy(ulong,_URLZONEREG,ulong &,int)

- ea: `0x18001563c`
- end: `0x180015b4c`
- name: `?GetActionPolicy@CRegZone@@QEBAJKW4_URLZONEREG@@AEAKH@Z`
- size: `1296`
- prototype: `__int64 __fastcall(CRegZone *this, unsigned int, enum _URLZONEREG, unsigned int *, int)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800154f0`
- `0x180059eb0`

## callees

- `0x18001563c`
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

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001576c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015a05`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001576c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015a05`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800156ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800159b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800156ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800159b2`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180015869`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x1800158d5`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180015931`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180015a59`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180015869`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x1800158d5`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180015931`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180015a59`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegQueryUSValueW` at `0x18001598f`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegQueryUSValueW` at `0x180015ab1`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegQueryUSValueW` at `0x18001598f`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegQueryUSValueW` at `0x180015ab1`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x180015a29`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x180015a29`

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
  int i; // esi
  int v14; // r13d
  unsigned int v15; // ebx
  unsigned int v16; // ebx
  const WCHAR *v18; // rcx
  BOOL fIgnoreHKCU; // eax
  const WCHAR *v20; // rcx
  BOOL v21; // eax
  HUSKEY v22; // rcx
  __int64 v23; // rax
  HUSKEY phNewUSKey; // [rsp+40h] [rbp-51h] BYREF
  unsigned int v25; // [rsp+48h] [rbp-49h]
  LPCWSTR pwzPath; // [rsp+50h] [rbp-41h] BYREF
  const unsigned int *v27; // [rsp+58h] [rbp-39h] BYREF
  HUSKEY hUSKey; // [rsp+60h] [rbp-31h]
  BOOL v29; // [rsp+68h] [rbp-29h]
  __int64 v30; // [rsp+6Ch] [rbp-25h]
  LPCWSTR v31; // [rsp+78h] [rbp-19h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+80h] [rbp-11h]
  WCHAR pszValue[12]; // [rsp+88h] [rbp-9h] BYREF

  v5 = *(_DWORD *)this;
  v25 = v5;
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
  v31 = v11;
  lpCriticalSection = (LPCRITICAL_SECTION)(v9 + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 16));
  if ( !(unsigned int)CSharedMem::IsCounterEqual(v12, *(_DWORD *)(v9 + 56) != 0 ? 0xC : 0, *(_DWORD *)v9) )
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
    v14 = 1;
    if ( a4 )
      *a4 = *(_DWORD *)(v9 + 16LL * i + 76);
    goto LABEL_22;
  }
LABEL_29:
  v14 = 0;
  if ( (int)StringCchPrintfW(pszValue, 0xCu, L"%lX", v8) < 0 )
    goto LABEL_22;
  hUSKey = 0;
  phNewUSKey = 0;
  v27 = &CRegKey::`vftable';
  v29 = v10;
  v30 = 1;
  CRegKey::Close((CRegKey *)&v27);
  v18 = pwzPath;
  if ( !pwzPath )
    goto LABEL_39;
  if ( !(_DWORD)v30 )
    goto LABEL_32;
  fIgnoreHKCU = v29;
  if ( v29 )
  {
LABEL_33:
    if ( SHRegOpenUSKeyW(v18, 0x20019u, 0, &phNewUSKey, fIgnoreHKCU) )
      goto LABEL_39;
    goto LABEL_34;
  }
  if ( SHRegOpenUSKeyW(pwzPath, 0x20019u, 0, &phNewUSKey, 1) )
  {
    v18 = pwzPath;
LABEL_32:
    fIgnoreHKCU = v29;
    goto LABEL_33;
  }
LABEL_34:
  hUSKey = phNewUSKey;
  if ( !CRegKey::QueryValue((CRegKey *)&v27, a4, pszValue) )
  {
    v14 = 1;
    CRegZone::CRegZoneCache::Add((CRegZone::CRegZoneCache *)v9, v25, v8, v10, *a4, i);
    goto LABEL_49;
  }
LABEL_39:
  LODWORD(v30) = 0;
  phNewUSKey = 0;
  (*((void (__fastcall **)(const unsigned int **))v27 + 2))(&v27);
  v20 = v31;
  if ( !v31 )
    goto LABEL_49;
  if ( !(_DWORD)v30 )
    goto LABEL_41;
  v21 = v29;
  if ( v29 )
  {
LABEL_42:
    if ( SHRegOpenUSKeyW(v20, 0x20019u, 0, &phNewUSKey, v21) )
      goto LABEL_49;
    goto LABEL_43;
  }
  if ( SHRegOpenUSKeyW(v31, 0x20019u, 0, &phNewUSKey, 1) )
  {
    v20 = v31;
LABEL_41:
    v21 = v29;
    goto LABEL_42;
  }
LABEL_43:
  v22 = phNewUSKey;
  hUSKey = phNewUSKey;
  LODWORD(phNewUSKey) = 0;
  LODWORD(pwzPath) = 4;
  if ( !hUSKey )
    goto LABEL_22;
  if ( (_DWORD)v30 && !v29 )
  {
    if ( !SHRegQueryUSValueW(v22, pszValue, (DWORD *)&phNewUSKey, a4, (DWORD *)&pwzPath, 1, 0, 0) )
      goto LABEL_46;
    v22 = hUSKey;
  }
  if ( !SHRegQueryUSValueW(v22, pszValue, (DWORD *)&phNewUSKey, a4, (DWORD *)&pwzPath, v29, 0, 0) )
  {
LABEL_46:
    LODWORD(pwzPath) = *a4;
    v14 = 1;
    LODWORD(phNewUSKey) = i;
    EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 16));
    if ( i == -1 )
    {
      CRegZone::CRegZoneCache::FindCacheEntry((CRegZone::CRegZoneCache *)v9, v25, v8, v10, (int *)&phNewUSKey);
      i = (int)phNewUSKey;
    }
    v23 = 2 * (i + 4LL);
    *(_DWORD *)(v9 + 8 * v23) = v25;
    *(_DWORD *)(v9 + 8 * v23 + 12) = (_DWORD)pwzPath;
    *(_DWORD *)(v9 + 8 * v23 + 4) = v8;
    *(_DWORD *)(v9 + 8 * v23 + 8) = v10;
    CSharedMem::GetCounter((CSharedMem *)&g_SharedMem, *(_DWORD *)(v9 + 56) != 0 ? 0xC : 0, (unsigned int *)v9);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 16));
  }
LABEL_49:
  v27 = &CRegKey::`vftable';
  if ( hUSKey )
    SHRegCloseUSKey(hUSKey);
LABEL_22:
  LeaveCriticalSection(lpCriticalSection);
  if ( !v14 )
    return 2147500037LL;
  v15 = a2 - 4610;
  if ( !v15 || (v16 = v15 - 1) == 0 || v16 == 510 )
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
0x18001563c  mov     [rsp-8+arg_10], rbx
0x180015641  push    rbp
0x180015642  push    rsi
0x180015643  push    rdi
0x180015644  push    r12
0x180015646  push    r13
0x180015648  push    r14
0x18001564a  push    r15
0x18001564c  lea     rbp, [rsp-1Fh]
0x180015651  sub     rsp, 0B0h
0x180015658  mov     rax, cs:__security_cookie
0x18001565f  xor     rax, rsp
0x180015662  mov     [rbp+4Fh+var_40], rax
0x180015666  mov     r13d, [rcx]
0x180015669  mov     r14, r9
0x18001566c  mov     [rbp+4Fh+var_98], r13d
0x180015670  mov     ebx, edx
0x180015672  cmp     r13d, 0FFFFFFFFh
0x180015676  jz      loc_1800157C8
0x18001567c  mov     eax, edx
0x18001567e  sub     eax, 1202h
0x180015683  jz      loc_180015ADB
0x180015689  sub     eax, 1
0x18001568c  jz      loc_180015ADB
0x180015692  sub     eax, 1
0x180015695  jz      loc_180015ADB
0x18001569b  sub     eax, 1FDh
0x1800156a0  jz      loc_180015ADB
0x1800156a6  sub     eax, 201h
0x1800156ab  jz      loc_180015AD0
0x1800156b1  cmp     eax, 1
0x1800156b4  jz      loc_180015AD0
0x1800156ba  mov     r12d, edx
0x1800156bd  mov     rdi, [rcx+40h]
0x1800156c1  xor     r15d, r15d
0x1800156c4  test    r8d, r8d
0x1800156c7  jnz     loc_180015AE6
0x1800156cd  mov     r15d, [rcx+28h]
0x1800156d1  mov     rax, [rcx+18h]
0x1800156d5  mov     rdx, [rcx+10h]
0x1800156d9  mov     [rbp+4Fh+pwzPath], rax
0x1800156dd  lea     rax, [rdi+10h]
0x1800156e1  mov     rcx, rax; lpCriticalSection
0x1800156e4  mov     [rbp+4Fh+var_68], rdx
0x1800156e8  mov     [rbp+4Fh+lpCriticalSection], rax
0x1800156ec  call    cs:__imp_EnterCriticalSection
0x1800156f3  nop     dword ptr [rax+rax+00h]
0x1800156f8  mov     eax, [rdi+38h]
0x1800156fb  mov     r8d, [rdi]; unsigned int
0x1800156fe  neg     eax
0x180015700  sbb     edx, edx
0x180015702  and     edx, 0Ch; unsigned int
0x180015705  call    ?IsCounterEqual@CSharedMem@@QEAAHKKH@Z; CSharedMem::IsCounterEqual(ulong,ulong,int)
0x18001570a  test    eax, eax
0x18001570c  jz      loc_180015A76
0x180015712  xor     esi, esi
0x180015714  cmp     esi, 50h ; 'P'
0x180015717  jge     loc_1800157CF
0x18001571d  movsxd  rcx, esi
0x180015720  lea     rax, [rcx+4]
0x180015724  add     rax, rax
0x180015727  cmp     dword ptr [rdi+rax*8], 0FFFFFFFFh
0x18001572b  jz      loc_1800157CF
0x180015731  cmp     [rdi+rax*8], r13d
0x180015735  jnz     short loc_180015741
0x180015737  add     rcx, rcx
0x18001573a  cmp     [rdi+rcx*8+44h], r12d
0x18001573f  jz      short loc_180015745
0x180015741  inc     esi
0x180015743  jmp     short loc_180015714
0x180015745  cmp     [rdi+rcx*8+48h], r15d
0x18001574a  jnz     short loc_180015741
0x18001574c  cmp     [rbp+4Fh+arg_20], 0
0x180015750  jnz     loc_1800157F7
0x180015756  mov     r13d, 1
0x18001575c  test    r14, r14
0x18001575f  jz      short loc_180015768
0x180015761  mov     eax, [rdi+rcx*8+4Ch]
0x180015765  mov     [r14], eax
0x180015768  mov     rcx, [rbp+4Fh+lpCriticalSection]; lpCriticalSection
0x18001576c  call    cs:__imp_LeaveCriticalSection
0x180015773  nop     dword ptr [rax+rax+00h]
0x180015778  test    r13d, r13d
0x18001577b  jz      short loc_1800157C8
0x18001577d  sub     ebx, 1202h
0x180015783  jz      loc_180015B1B
0x180015789  sub     ebx, 1
0x18001578c  jz      loc_180015B1B
0x180015792  cmp     ebx, 1FEh
0x180015798  jz      loc_180015B1B
0x18001579e  xor     eax, eax
0x1800157a0  mov     rcx, [rbp+4Fh+var_40]
0x1800157a4  xor     rcx, rsp; StackCookie
0x1800157a7  call    __security_check_cookie
0x1800157ac  mov     rbx, [rsp+0E0h+arg_10]
0x1800157b4  add     rsp, 0B0h
0x1800157bb  pop     r15
0x1800157bd  pop     r14
0x1800157bf  pop     r13
0x1800157c1  pop     r12
0x1800157c3  pop     rdi
0x1800157c4  pop     rsi
0x1800157c5  pop     rbp
0x1800157c6  retn
0x1800157c8  mov     eax, 80004005h
0x1800157cd  jmp     short loc_1800157A0
0x1800157cf  mov     esi, [rdi+540h]
0x1800157d5  mov     eax, 66666667h
0x1800157da  lea     ecx, [rsi+1]
0x1800157dd  imul    ecx
0x1800157df  sar     edx, 5
0x1800157e2  mov     eax, edx
0x1800157e4  shr     eax, 1Fh
0x1800157e7  add     edx, eax
0x1800157e9  lea     eax, [rdx+rdx*4]
0x1800157ec  shl     eax, 4
0x1800157ef  sub     ecx, eax
0x1800157f1  mov     [rdi+540h], ecx
0x1800157f7  xor     r13d, r13d
0x1800157fa  lea     r8, aLx; "%lX"
0x180015801  mov     r9d, r12d
0x180015804  lea     rcx, [rbp+4Fh+pszValue]; unsigned __int16 *
0x180015808  lea     edx, [r13+0Ch]; unsigned __int64
0x18001580c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180015811  xor     ecx, ecx
0x180015813  test    eax, eax
0x180015815  js      loc_180015768
0x18001581b  lea     rax, ??_7CRegKey@@6B@; const CRegKey::`vftable'
0x180015822  mov     [rbp+4Fh+hUSKey], rcx
0x180015826  mov     [rbp+4Fh+phNewUSKey], rcx
0x18001582a  lea     rcx, [rbp+4Fh+var_88]; this
0x18001582e  mov     [rbp+4Fh+var_88], rax
0x180015832  mov     [rbp+4Fh+var_78], r15d
0x180015836  mov     [rbp+4Fh+var_74], 1
0x18001583e  call    ?Close@CRegKey@@UEAAJXZ; CRegKey::Close(void)
0x180015843  mov     rcx, [rbp+4Fh+pwzPath]; pwzPath
0x180015847  test    rcx, rcx
0x18001584a  jz      loc_1800158EE
0x180015850  cmp     dword ptr [rbp+4Fh+var_74], r13d
0x180015854  jnz     short loc_1800158BA
0x180015856  mov     eax, [rbp+4Fh+var_78]
0x180015859  lea     r9, [rbp+4Fh+phNewUSKey]; phNewUSKey
0x18001585d  mov     [rsp+0E0h+fIgnoreHKCU], eax; fIgnoreHKCU
0x180015861  xor     r8d, r8d; hRelativeUSKey
0x180015864  mov     edx, 20019h; samDesired
0x180015869  call    cs:__imp_SHRegOpenUSKeyW
0x180015870  nop     dword ptr [rax+rax+00h]
0x180015875  test    eax, eax
0x180015877  jnz     short loc_1800158EE
0x180015879  mov     rax, [rbp+4Fh+phNewUSKey]
0x18001587d  lea     r8, [rbp+4Fh+pszValue]; unsigned __int16 *
0x180015881  mov     rdx, r14; unsigned int *
0x180015884  mov     [rbp+4Fh+hUSKey], rax
0x180015888  lea     rcx, [rbp+4Fh+var_88]; this
0x18001588c  call    ?QueryValue@CRegKey@@QEAAJPEAKPEBG@Z; CRegKey::QueryValue(ulong *,ushort const *)
0x180015891  test    eax, eax
0x180015893  jnz     short loc_1800158EE
0x180015895  mov     edx, [rbp+4Fh+var_98]; unsigned int
0x180015898  lea     r13d, [rax+1]
0x18001589c  mov     eax, [r14]
0x18001589f  mov     r9d, r15d; int
0x1800158a2  mov     [rsp+0E0h+var_B8], esi; int
0x1800158a6  mov     r8d, r12d; unsigned int
0x1800158a9  mov     rcx, rdi; this
0x1800158ac  mov     [rsp+0E0h+fIgnoreHKCU], eax; unsigned int
0x1800158b0  call    ?Add@CRegZoneCache@CRegZone@@QEAAXKKHKH@Z; CRegZone::CRegZoneCache::Add(ulong,ulong,int,ulong,int)
0x1800158b5  jmp     loc_180015A11
0x1800158ba  mov     eax, [rbp+4Fh+var_78]
0x1800158bd  test    eax, eax
0x1800158bf  jnz     short loc_180015859
0x1800158c1  lea     r9, [rbp+4Fh+phNewUSKey]; phNewUSKey
0x1800158c5  mov     [rsp+0E0h+fIgnoreHKCU], 1; fIgnoreHKCU
0x1800158cd  xor     r8d, r8d; hRelativeUSKey
0x1800158d0  mov     edx, 20019h; samDesired
0x1800158d5  call    cs:__imp_SHRegOpenUSKeyW
0x1800158dc  nop     dword ptr [rax+rax+00h]
0x1800158e1  test    eax, eax
0x1800158e3  jz      short loc_180015879
0x1800158e5  mov     rcx, [rbp+4Fh+pwzPath]
0x1800158e9  jmp     loc_180015856
0x1800158ee  mov     rax, [rbp+4Fh+var_88]
0x1800158f2  lea     rcx, [rbp+4Fh+var_88]
0x1800158f6  mov     dword ptr [rbp+4Fh+var_74], r13d
0x1800158fa  mov     [rbp+4Fh+phNewUSKey], r13
0x1800158fe  mov     rax, [rax+10h]
0x180015902  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015907  mov     rcx, [rbp+4Fh+var_68]; pwzPath
0x18001590b  test    rcx, rcx
0x18001590e  jz      loc_180015A11
0x180015914  cmp     dword ptr [rbp+4Fh+var_74], r13d
0x180015918  jnz     loc_180015A3A
0x18001591e  mov     eax, [rbp+4Fh+var_78]
0x180015921  lea     r9, [rbp+4Fh+phNewUSKey]; phNewUSKey
0x180015925  mov     [rsp+0E0h+fIgnoreHKCU], eax; fIgnoreHKCU
0x180015929  xor     r8d, r8d; hRelativeUSKey
0x18001592c  mov     edx, 20019h; samDesired
0x180015931  call    cs:__imp_SHRegOpenUSKeyW
0x180015938  nop     dword ptr [rax+rax+00h]
0x18001593d  test    eax, eax
0x18001593f  jnz     loc_180015A11
0x180015945  mov     rcx, [rbp+4Fh+phNewUSKey]; hUSKey
0x180015949  xor     eax, eax
0x18001594b  mov     [rbp+4Fh+hUSKey], rcx
0x18001594f  mov     dword ptr [rbp+4Fh+phNewUSKey], eax
0x180015952  mov     dword ptr [rbp+4Fh+pwzPath], 4
0x180015959  test    rcx, rcx
0x18001595c  jz      loc_180015768
0x180015962  cmp     dword ptr [rbp+4Fh+var_74], eax
0x180015965  jnz     loc_180015A83
0x18001596b  mov     [rsp+0E0h+dwDefaultDataSize], eax; dwDefaultDataSize
0x18001596f  lea     r8, [rbp+4Fh+phNewUSKey]; pdwType
0x180015973  mov     [rsp+0E0h+pvDefaultData], rax; pvDefaultData
0x180015978  lea     rdx, [rbp+4Fh+pszValue]; pszValue
0x18001597c  mov     eax, [rbp+4Fh+var_78]
0x18001597f  mov     r9, r14; pvData
0x180015982  mov     [rsp+0E0h+var_B8], eax; fIgnoreHKCU
0x180015986  lea     rax, [rbp+4Fh+pwzPath]
0x18001598a  mov     qword ptr [rsp+0E0h+fIgnoreHKCU], rax; pcbData
0x18001598f  call    cs:__imp_SHRegQueryUSValueW
0x180015996  nop     dword ptr [rax+rax+00h]
0x18001599b  test    eax, eax
0x18001599d  jnz     short loc_180015A11
0x18001599f  mov     eax, [r14]
0x1800159a2  lea     rcx, [rdi+10h]; lpCriticalSection
0x1800159a6  mov     dword ptr [rbp+4Fh+pwzPath], eax
0x1800159a9  mov     r13d, 1
0x1800159af  mov     dword ptr [rbp+4Fh+phNewUSKey], esi
0x1800159b2  call    cs:__imp_EnterCriticalSection
0x1800159b9  nop     dword ptr [rax+rax+00h]
0x1800159be  cmp     esi, 0FFFFFFFFh
0x1800159c1  jz      loc_180015AF9
0x1800159c7  mov     ecx, [rbp+4Fh+var_98]
0x1800159ca  mov     r8, rdi; unsigned int *
0x1800159cd  movsxd  rax, esi
0x1800159d0  add     rax, 4
0x1800159d4  add     rax, rax
0x1800159d7  mov     [rdi+rax*8], ecx
0x1800159da  mov     ecx, dword ptr [rbp+4Fh+pwzPath]
0x1800159dd  mov     [rdi+rax*8+0Ch], ecx
0x1800159e1  lea     rcx, ?g_SharedMem@@3VCSharedMem@@A; this
0x1800159e8  mov     [rdi+rax*8+4], r12d
0x1800159ed  mov     [rdi+rax*8+8], r15d
0x1800159f2  mov     eax, [rdi+38h]
0x1800159f5  neg     eax
0x1800159f7  sbb     edx, edx
0x1800159f9  and     edx, 0Ch; unsigned int
0x1800159fc  call    ?GetCounter@CSharedMem@@QEAAHKPEAK@Z; CSharedMem::GetCounter(ulong,ulong *)
0x180015a01  lea     rcx, [rdi+10h]; lpCriticalSection
0x180015a05  call    cs:__imp_LeaveCriticalSection
0x180015a0c  nop     dword ptr [rax+rax+00h]
0x180015a11  mov     rcx, [rbp+4Fh+hUSKey]; hUSKey
0x180015a15  lea     rax, ??_7CRegKey@@6B@; const CRegKey::`vftable'
0x180015a1c  mov     [rbp+4Fh+var_88], rax
0x180015a20  test    rcx, rcx
0x180015a23  jz      loc_180015768
0x180015a29  call    cs:__imp_SHRegCloseUSKey
0x180015a30  nop     dword ptr [rax+rax+00h]
0x180015a35  jmp     loc_180015768
0x180015a3a  mov     eax, [rbp+4Fh+var_78]
0x180015a3d  test    eax, eax
0x180015a3f  jnz     loc_180015921
0x180015a45  lea     r9, [rbp+4Fh+phNewUSKey]; phNewUSKey
0x180015a49  mov     [rsp+0E0h+fIgnoreHKCU], 1; fIgnoreHKCU
0x180015a51  xor     r8d, r8d; hRelativeUSKey
0x180015a54  mov     edx, 20019h; samDesired
0x180015a59  call    cs:__imp_SHRegOpenUSKeyW
0x180015a60  nop     dword ptr [rax+rax+00h]
0x180015a65  test    eax, eax
0x180015a67  jz      loc_180015945
0x180015a6d  mov     rcx, [rbp+4Fh+var_68]
0x180015a71  jmp     loc_18001591E
0x180015a76  mov     rcx, rdi; this
0x180015a79  call    ?Flush@CRegZoneCache@CRegZone@@QEAAXXZ; CRegZone::CRegZoneCache::Flush(void)
0x180015a7e  jmp     loc_180015712
0x180015a83  cmp     [rbp+4Fh+var_78], eax
0x180015a86  jnz     loc_18001596B
0x180015a8c  mov     [rsp+0E0h+dwDefaultDataSize], eax; dwDefaultDataSize
0x180015a90  lea     r8, [rbp+4Fh+phNewUSKey]; pdwType
0x180015a94  mov     [rsp+0E0h+pvDefaultData], rax; pvDefaultData
0x180015a99  lea     rdx, [rbp+4Fh+pszValue]; pszValue
0x180015a9d  lea     rax, [rbp+4Fh+pwzPath]
0x180015aa1  mov     [rsp+0E0h+var_B8], 1; fIgnoreHKCU
0x180015aa9  mov     r9, r14; pvData
0x180015aac  mov     qword ptr [rsp+0E0h+fIgnoreHKCU], rax; pcbData
0x180015ab1  call    cs:__imp_SHRegQueryUSValueW
0x180015ab8  nop     dword ptr [rax+rax+00h]
0x180015abd  test    eax, eax
0x180015abf  jz      loc_18001599F
0x180015ac5  mov     rcx, [rbp+4Fh+hUSKey]
0x180015ac9  xor     eax, eax
0x180015acb  jmp     loc_18001596B
0x180015ad0  mov     r12d, 1601h
0x180015ad6  jmp     loc_1800156BD
0x180015adb  mov     r12d, 1201h
0x180015ae1  jmp     loc_1800156BD
0x180015ae6  sub     r8d, 1
0x180015aea  jnz     loc_1800156D1
0x180015af0  lea     r15d, [r8+1]
0x180015af4  jmp     loc_1800156D1
0x180015af9  mov     edx, [rbp+4Fh+var_98]; unsigned int
  ... truncated ...
```
