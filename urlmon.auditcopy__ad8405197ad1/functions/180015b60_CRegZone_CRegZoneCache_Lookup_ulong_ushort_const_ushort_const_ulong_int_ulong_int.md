# CRegZone::CRegZoneCache::Lookup(ulong,ushort const *,ushort const *,ulong,int,ulong *,int)

- ea: `0x180015b60`
- end: `0x180015f7a`
- name: `?Lookup@CRegZoneCache@CRegZone@@QEAAHKPEBG0KHPEAKH@Z`
- size: `1050`
- prototype: `__int64 __fastcall(CRegZone::CRegZoneCache *this, unsigned int, const unsigned __int16 *, const unsigned __int16 *, unsigned int, int, unsigned int *pvData, int)`
- caller_count: `3`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x180059eb0`
- `0x18006db64`
- `0x180112cf8`

## callees

- `0x180015b60`
- `0x1800162d4`
- `0x18001721c`
- `0x18001c070`
- `0x18003bef0`
- `0x18005c800`
- `0x1800704b8`
- `0x180071894`
- `0x18008457c`
- `0x180128660`
- `0x180129010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015c28`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015e8e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015c28`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015e8e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015ba6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015e40`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015ba6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015e40`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180015cf8`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180015d65`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180015dc1`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180015ee2`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180015cf8`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180015d65`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180015dc1`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180015ee2`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegQueryUSValueW` at `0x180015e20`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegQueryUSValueW` at `0x180015f3c`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegQueryUSValueW` at `0x180015e20`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegQueryUSValueW` at `0x180015f3c`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x180015eb2`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x180015eb2`

## pseudocode

```c
__int64 __fastcall CRegZone::CRegZoneCache::Lookup(
        CRegZone::CRegZoneCache *this,
        int a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        int a6,
        unsigned int *pvData,
        int a8)
{
  CSharedMem *v10; // rcx
  int i; // ebx
  int v12; // eax
  _DWORD *v13; // rax
  unsigned int v14; // r14d
  const WCHAR *v16; // rcx
  BOOL fIgnoreHKCU; // eax
  const WCHAR *v18; // rcx
  BOOL v19; // eax
  HUSKEY v20; // rcx
  unsigned int v21; // r15d
  __int64 v22; // rax
  HUSKEY phNewUSKey; // [rsp+40h] [rbp-59h] BYREF
  LPCWSTR pwzPath; // [rsp+48h] [rbp-51h] BYREF
  const unsigned int *v25; // [rsp+50h] [rbp-49h] BYREF
  HUSKEY hUSKey; // [rsp+58h] [rbp-41h]
  BOOL v27; // [rsp+60h] [rbp-39h]
  __int64 v28; // [rsp+64h] [rbp-35h]
  LPCWSTR v29; // [rsp+70h] [rbp-29h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+78h] [rbp-21h]
  WCHAR pszValue[12]; // [rsp+80h] [rbp-19h] BYREF

  pwzPath = a4;
  v29 = a3;
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( !(unsigned int)CSharedMem::IsCounterEqual(v10, *((_DWORD *)this + 14) != 0 ? 0xC : 0, *(_DWORD *)this) )
    CRegZone::CRegZoneCache::Flush(this);
  for ( i = 0; ; ++i )
  {
    if ( i >= 80 || (v12 = *((_DWORD *)this + 4 * i + 16), v12 == -1) )
    {
      i = *((_DWORD *)this + 336);
      *((_DWORD *)this + 336) = (i + 1) % 80;
      goto LABEL_15;
    }
    if ( v12 == a2 )
    {
      v13 = (_DWORD *)((char *)this + 16 * i);
      if ( v13[17] == a5 && v13[18] == a6 )
        break;
    }
  }
  if ( !a8 )
  {
    v14 = 1;
    if ( pvData )
      *pvData = v13[19];
    goto LABEL_13;
  }
LABEL_15:
  v14 = 0;
  if ( (int)StringCchPrintfW(pszValue, 0xCu, L"%lX", a5) < 0 )
    goto LABEL_13;
  hUSKey = 0;
  v25 = &CRegKey::`vftable';
  v27 = a6;
  v28 = 1;
  phNewUSKey = 0;
  CRegKey::Close((CRegKey *)&v25);
  v16 = pwzPath;
  if ( !pwzPath )
    goto LABEL_25;
  if ( !(_DWORD)v28 )
    goto LABEL_18;
  fIgnoreHKCU = v27;
  if ( v27 )
  {
LABEL_19:
    if ( SHRegOpenUSKeyW(v16, 0x20019u, 0, &phNewUSKey, fIgnoreHKCU) )
      goto LABEL_25;
    goto LABEL_20;
  }
  if ( SHRegOpenUSKeyW(pwzPath, 0x20019u, 0, &phNewUSKey, 1) )
  {
    v16 = pwzPath;
LABEL_18:
    fIgnoreHKCU = v27;
    goto LABEL_19;
  }
LABEL_20:
  hUSKey = phNewUSKey;
  if ( !CRegKey::QueryValue((CRegKey *)&v25, pvData, pszValue) )
  {
    v14 = 1;
    CRegZone::CRegZoneCache::Add(this, a2, a5, a6, *pvData, i);
    goto LABEL_35;
  }
LABEL_25:
  LODWORD(v28) = 0;
  phNewUSKey = 0;
  (*((void (__fastcall **)(const unsigned int **))v25 + 2))(&v25);
  v18 = v29;
  if ( !v29 )
    goto LABEL_35;
  if ( !(_DWORD)v28 )
    goto LABEL_27;
  v19 = v27;
  if ( v27 )
  {
LABEL_28:
    if ( SHRegOpenUSKeyW(v18, 0x20019u, 0, &phNewUSKey, v19) )
      goto LABEL_35;
    goto LABEL_29;
  }
  if ( SHRegOpenUSKeyW(v29, 0x20019u, 0, &phNewUSKey, 1) )
  {
    v18 = v29;
LABEL_27:
    v19 = v27;
    goto LABEL_28;
  }
LABEL_29:
  v20 = phNewUSKey;
  hUSKey = phNewUSKey;
  LODWORD(phNewUSKey) = 0;
  LODWORD(pwzPath) = 4;
  if ( !hUSKey )
    goto LABEL_13;
  if ( (_DWORD)v28 && !v27 )
  {
    if ( !SHRegQueryUSValueW(v20, pszValue, (DWORD *)&phNewUSKey, pvData, (DWORD *)&pwzPath, 1, 0, 0) )
      goto LABEL_32;
    v20 = hUSKey;
  }
  if ( !SHRegQueryUSValueW(v20, pszValue, (DWORD *)&phNewUSKey, pvData, (DWORD *)&pwzPath, v27, 0, 0) )
  {
LABEL_32:
    v21 = *pvData;
    v14 = 1;
    LODWORD(phNewUSKey) = i;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    if ( i == -1 )
    {
      CRegZone::CRegZoneCache::FindCacheEntry(this, a2, a5, a6, (int *)&phNewUSKey);
      i = (int)phNewUSKey;
    }
    v22 = 2 * (i + 4LL);
    *((_DWORD *)this + 2 * v22) = a2;
    *((_DWORD *)this + 2 * v22 + 1) = a5;
    *((_DWORD *)this + 2 * v22 + 2) = a6;
    *((_DWORD *)this + 2 * v22 + 3) = v21;
    CSharedMem::GetCounter((CSharedMem *)&g_SharedMem, *((_DWORD *)this + 14) != 0 ? 0xC : 0, (unsigned int *)this);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  }
LABEL_35:
  v25 = &CRegKey::`vftable';
  if ( hUSKey )
    SHRegCloseUSKey(hUSKey);
LABEL_13:
  LeaveCriticalSection(lpCriticalSection);
  return v14;
}

```

## disassembly

```asm
0x180015b60  mov     [rsp-8+arg_8], rbx
0x180015b65  push    rbp
0x180015b66  push    rsi
0x180015b67  push    rdi
0x180015b68  push    r12
0x180015b6a  push    r13
0x180015b6c  push    r14
0x180015b6e  push    r15
0x180015b70  lea     rbp, [rsp-7]
0x180015b75  sub     rsp, 0A0h
0x180015b7c  mov     rax, cs:__security_cookie
0x180015b83  xor     rax, rsp
0x180015b86  mov     [rbp+37h+var_38], rax
0x180015b8a  mov     r15, [rbp+37h+pvData]
0x180015b8e  lea     rax, [rcx+10h]
0x180015b92  mov     rdi, rcx
0x180015b95  mov     [rbp+37h+pwzPath], r9
0x180015b99  mov     rcx, rax; lpCriticalSection
0x180015b9c  mov     [rbp+37h+var_60], r8
0x180015ba0  mov     esi, edx
0x180015ba2  mov     [rbp+37h+lpCriticalSection], rax
0x180015ba6  call    cs:__imp_EnterCriticalSection
0x180015bad  nop     dword ptr [rax+rax+00h]
0x180015bb2  mov     eax, [rdi+38h]
0x180015bb5  mov     r8d, [rdi]; unsigned int
0x180015bb8  neg     eax
0x180015bba  sbb     edx, edx
0x180015bbc  and     edx, 0Ch; unsigned int
0x180015bbf  call    ?IsCounterEqual@CSharedMem@@QEAAHKKH@Z; CSharedMem::IsCounterEqual(ulong,ulong,int)
0x180015bc4  test    eax, eax
0x180015bc6  jz      loc_180015EFF
0x180015bcc  mov     r13d, [rbp+37h+arg_28]
0x180015bd0  xor     ebx, ebx
0x180015bd2  mov     r12d, [rbp+37h+arg_20]
0x180015bd6  cmp     ebx, 50h ; 'P'
0x180015bd9  jge     loc_180015C5F
0x180015bdf  movsxd  rcx, ebx
0x180015be2  lea     rax, [rcx+4]
0x180015be6  add     rax, rax
0x180015be9  mov     eax, [rdi+rax*8]
0x180015bec  cmp     eax, 0FFFFFFFFh
0x180015bef  jz      short loc_180015C5F
0x180015bf1  cmp     eax, esi
0x180015bf3  jnz     short loc_180015C03
0x180015bf5  add     rcx, rcx
0x180015bf8  cmp     [rdi+rcx*8+44h], r12d
0x180015bfd  lea     rax, [rdi+rcx*8]
0x180015c01  jz      short loc_180015C07
0x180015c03  inc     ebx
0x180015c05  jmp     short loc_180015BD6
0x180015c07  cmp     [rax+48h], r13d
0x180015c0b  jnz     short loc_180015C03
0x180015c0d  cmp     [rbp+37h+arg_38], 0
0x180015c11  jnz     short loc_180015C87
0x180015c13  mov     r14d, 1
0x180015c19  test    r15, r15
0x180015c1c  jz      short loc_180015C24
0x180015c1e  mov     eax, [rax+4Ch]
0x180015c21  mov     [r15], eax
0x180015c24  mov     rcx, [rbp+37h+lpCriticalSection]; lpCriticalSection
0x180015c28  call    cs:__imp_LeaveCriticalSection
0x180015c2f  nop     dword ptr [rax+rax+00h]
0x180015c34  mov     eax, r14d
0x180015c37  mov     rcx, [rbp+37h+var_38]
0x180015c3b  xor     rcx, rsp; StackCookie
0x180015c3e  call    __security_check_cookie
0x180015c43  mov     rbx, [rsp+0D0h+arg_8]
0x180015c4b  add     rsp, 0A0h
0x180015c52  pop     r15
0x180015c54  pop     r14
0x180015c56  pop     r13
0x180015c58  pop     r12
0x180015c5a  pop     rdi
0x180015c5b  pop     rsi
0x180015c5c  pop     rbp
0x180015c5d  retn
0x180015c5f  mov     ebx, [rdi+540h]
0x180015c65  mov     eax, 66666667h
0x180015c6a  lea     ecx, [rbx+1]
0x180015c6d  imul    ecx
0x180015c6f  sar     edx, 5
0x180015c72  mov     eax, edx
0x180015c74  shr     eax, 1Fh
0x180015c77  add     edx, eax
0x180015c79  lea     eax, [rdx+rdx*4]
0x180015c7c  shl     eax, 4
0x180015c7f  sub     ecx, eax
0x180015c81  mov     [rdi+540h], ecx
0x180015c87  mov     r9d, r12d
0x180015c8a  lea     r8, aLx; "%lX"
0x180015c91  mov     edx, 0Ch; unsigned __int64
0x180015c96  lea     rcx, [rbp+37h+pszValue]; unsigned __int16 *
0x180015c9a  xor     r14d, r14d
0x180015c9d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180015ca2  test    eax, eax
0x180015ca4  js      loc_180015C24
0x180015caa  lea     rax, ??_7CRegKey@@6B@; const CRegKey::`vftable'
0x180015cb1  mov     [rbp+37h+hUSKey], r14
0x180015cb5  lea     rcx, [rbp+37h+var_80]; this
0x180015cb9  mov     [rbp+37h+var_80], rax
0x180015cbd  mov     [rbp+37h+var_70], r13d
0x180015cc1  mov     [rbp+37h+var_6C], 1
0x180015cc9  mov     [rbp+37h+phNewUSKey], r14
0x180015ccd  call    ?Close@CRegKey@@UEAAJXZ; CRegKey::Close(void)
0x180015cd2  mov     rcx, [rbp+37h+pwzPath]; pwzPath
0x180015cd6  test    rcx, rcx
0x180015cd9  jz      loc_180015D7E
0x180015cdf  cmp     dword ptr [rbp+37h+var_6C], r14d
0x180015ce3  jnz     short loc_180015D4A
0x180015ce5  mov     eax, [rbp+37h+var_70]
0x180015ce8  lea     r9, [rbp+37h+phNewUSKey]; phNewUSKey
0x180015cec  mov     [rsp+0D0h+fIgnoreHKCU], eax; fIgnoreHKCU
0x180015cf0  xor     r8d, r8d; hRelativeUSKey
0x180015cf3  mov     edx, 20019h; samDesired
0x180015cf8  call    cs:__imp_SHRegOpenUSKeyW
0x180015cff  nop     dword ptr [rax+rax+00h]
0x180015d04  test    eax, eax
0x180015d06  jnz     short loc_180015D7E
0x180015d08  mov     rax, [rbp+37h+phNewUSKey]
0x180015d0c  lea     r8, [rbp+37h+pszValue]; unsigned __int16 *
0x180015d10  mov     rdx, r15; unsigned int *
0x180015d13  mov     [rbp+37h+hUSKey], rax
0x180015d17  lea     rcx, [rbp+37h+var_80]; this
0x180015d1b  call    ?QueryValue@CRegKey@@QEAAJPEAKPEBG@Z; CRegKey::QueryValue(ulong *,ushort const *)
0x180015d20  test    eax, eax
0x180015d22  jnz     short loc_180015D7E
0x180015d24  mov     eax, [r15]
0x180015d27  mov     r9d, r13d; int
0x180015d2a  mov     [rsp+0D0h+var_A8], ebx; int
0x180015d2e  mov     r8d, r12d; unsigned int
0x180015d31  mov     edx, esi; unsigned int
0x180015d33  mov     [rsp+0D0h+fIgnoreHKCU], eax; unsigned int
0x180015d37  mov     rcx, rdi; this
0x180015d3a  mov     r14d, 1
0x180015d40  call    ?Add@CRegZoneCache@CRegZone@@QEAAXKKHKH@Z; CRegZone::CRegZoneCache::Add(ulong,ulong,int,ulong,int)
0x180015d45  jmp     loc_180015E9A
0x180015d4a  mov     eax, [rbp+37h+var_70]
0x180015d4d  test    eax, eax
0x180015d4f  jnz     short loc_180015CE8
0x180015d51  lea     r9, [rbp+37h+phNewUSKey]; phNewUSKey
0x180015d55  mov     [rsp+0D0h+fIgnoreHKCU], 1; fIgnoreHKCU
0x180015d5d  xor     r8d, r8d; hRelativeUSKey
0x180015d60  mov     edx, 20019h; samDesired
0x180015d65  call    cs:__imp_SHRegOpenUSKeyW
0x180015d6c  nop     dword ptr [rax+rax+00h]
0x180015d71  test    eax, eax
0x180015d73  jz      short loc_180015D08
0x180015d75  mov     rcx, [rbp+37h+pwzPath]
0x180015d79  jmp     loc_180015CE5
0x180015d7e  mov     rax, [rbp+37h+var_80]
0x180015d82  lea     rcx, [rbp+37h+var_80]
0x180015d86  mov     dword ptr [rbp+37h+var_6C], r14d
0x180015d8a  mov     [rbp+37h+phNewUSKey], r14
0x180015d8e  mov     rax, [rax+10h]
0x180015d92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d97  mov     rcx, [rbp+37h+var_60]; pwzPath
0x180015d9b  test    rcx, rcx
0x180015d9e  jz      loc_180015E9A
0x180015da4  cmp     dword ptr [rbp+37h+var_6C], r14d
0x180015da8  jnz     loc_180015EC3
0x180015dae  mov     eax, [rbp+37h+var_70]
0x180015db1  lea     r9, [rbp+37h+phNewUSKey]; phNewUSKey
0x180015db5  mov     [rsp+0D0h+fIgnoreHKCU], eax; fIgnoreHKCU
0x180015db9  xor     r8d, r8d; hRelativeUSKey
0x180015dbc  mov     edx, 20019h; samDesired
0x180015dc1  call    cs:__imp_SHRegOpenUSKeyW
0x180015dc8  nop     dword ptr [rax+rax+00h]
0x180015dcd  test    eax, eax
0x180015dcf  jnz     loc_180015E9A
0x180015dd5  mov     rcx, [rbp+37h+phNewUSKey]; hUSKey
0x180015dd9  mov     [rbp+37h+hUSKey], rcx
0x180015ddd  mov     dword ptr [rbp+37h+phNewUSKey], r14d
0x180015de1  mov     dword ptr [rbp+37h+pwzPath], 4
0x180015de8  test    rcx, rcx
0x180015deb  jz      loc_180015C24
0x180015df1  cmp     dword ptr [rbp+37h+var_6C], r14d
0x180015df5  jnz     loc_180015F0C
0x180015dfb  mov     eax, [rbp+37h+var_70]
0x180015dfe  lea     r8, [rbp+37h+phNewUSKey]; pdwType
0x180015e02  mov     [rsp+0D0h+dwDefaultDataSize], r14d; dwDefaultDataSize
0x180015e07  lea     rdx, [rbp+37h+pszValue]; pszValue
0x180015e0b  mov     [rsp+0D0h+pvDefaultData], r14; pvDefaultData
0x180015e10  mov     r9, r15; pvData
0x180015e13  mov     [rsp+0D0h+var_A8], eax; fIgnoreHKCU
0x180015e17  lea     rax, [rbp+37h+pwzPath]
0x180015e1b  mov     qword ptr [rsp+0D0h+fIgnoreHKCU], rax; pcbData
0x180015e20  call    cs:__imp_SHRegQueryUSValueW
0x180015e27  nop     dword ptr [rax+rax+00h]
0x180015e2c  test    eax, eax
0x180015e2e  jnz     short loc_180015E9A
0x180015e30  mov     r15d, [r15]
0x180015e33  lea     rcx, [rdi+10h]; lpCriticalSection
0x180015e37  mov     r14d, 1
0x180015e3d  mov     dword ptr [rbp+37h+phNewUSKey], ebx
0x180015e40  call    cs:__imp_EnterCriticalSection
0x180015e47  nop     dword ptr [rax+rax+00h]
0x180015e4c  cmp     ebx, 0FFFFFFFFh
0x180015e4f  jz      loc_180015F59
0x180015e55  movsxd  rax, ebx
0x180015e58  lea     rcx, ?g_SharedMem@@3VCSharedMem@@A; this
0x180015e5f  add     rax, 4
0x180015e63  mov     r8, rdi; unsigned int *
0x180015e66  add     rax, rax
0x180015e69  mov     [rdi+rax*8], esi
0x180015e6c  mov     [rdi+rax*8+4], r12d
0x180015e71  mov     [rdi+rax*8+8], r13d
0x180015e76  mov     [rdi+rax*8+0Ch], r15d
0x180015e7b  mov     eax, [rdi+38h]
0x180015e7e  neg     eax
0x180015e80  sbb     edx, edx
0x180015e82  and     edx, 0Ch; unsigned int
0x180015e85  call    ?GetCounter@CSharedMem@@QEAAHKPEAK@Z; CSharedMem::GetCounter(ulong,ulong *)
0x180015e8a  lea     rcx, [rdi+10h]; lpCriticalSection
0x180015e8e  call    cs:__imp_LeaveCriticalSection
0x180015e95  nop     dword ptr [rax+rax+00h]
0x180015e9a  mov     rcx, [rbp+37h+hUSKey]; hUSKey
0x180015e9e  lea     rax, ??_7CRegKey@@6B@; const CRegKey::`vftable'
0x180015ea5  mov     [rbp+37h+var_80], rax
0x180015ea9  test    rcx, rcx
0x180015eac  jz      loc_180015C24
0x180015eb2  call    cs:__imp_SHRegCloseUSKey
0x180015eb9  nop     dword ptr [rax+rax+00h]
0x180015ebe  jmp     loc_180015C24
0x180015ec3  mov     eax, [rbp+37h+var_70]
0x180015ec6  test    eax, eax
0x180015ec8  jnz     loc_180015DB1
0x180015ece  lea     r9, [rbp+37h+phNewUSKey]; phNewUSKey
0x180015ed2  mov     [rsp+0D0h+fIgnoreHKCU], 1; fIgnoreHKCU
0x180015eda  xor     r8d, r8d; hRelativeUSKey
0x180015edd  mov     edx, 20019h; samDesired
0x180015ee2  call    cs:__imp_SHRegOpenUSKeyW
0x180015ee9  nop     dword ptr [rax+rax+00h]
0x180015eee  test    eax, eax
0x180015ef0  jz      loc_180015DD5
0x180015ef6  mov     rcx, [rbp+37h+var_60]
0x180015efa  jmp     loc_180015DAE
0x180015eff  mov     rcx, rdi; this
0x180015f02  call    ?Flush@CRegZoneCache@CRegZone@@QEAAXXZ; CRegZone::CRegZoneCache::Flush(void)
0x180015f07  jmp     loc_180015BCC
0x180015f0c  cmp     [rbp+37h+var_70], r14d
0x180015f10  jnz     loc_180015DFB
0x180015f16  mov     [rsp+0D0h+dwDefaultDataSize], r14d; dwDefaultDataSize
0x180015f1b  lea     rax, [rbp+37h+pwzPath]
0x180015f1f  mov     [rsp+0D0h+pvDefaultData], r14; pvDefaultData
0x180015f24  lea     r8, [rbp+37h+phNewUSKey]; pdwType
0x180015f28  mov     [rsp+0D0h+var_A8], 1; fIgnoreHKCU
0x180015f30  lea     rdx, [rbp+37h+pszValue]; pszValue
0x180015f34  mov     r9, r15; pvData
0x180015f37  mov     qword ptr [rsp+0D0h+fIgnoreHKCU], rax; pcbData
0x180015f3c  call    cs:__imp_SHRegQueryUSValueW
0x180015f43  nop     dword ptr [rax+rax+00h]
0x180015f48  test    eax, eax
0x180015f4a  jz      loc_180015E30
0x180015f50  mov     rcx, [rbp+37h+hUSKey]
0x180015f54  jmp     loc_180015DFB
0x180015f59  lea     rax, [rbp+37h+phNewUSKey]
0x180015f5d  mov     r9d, r13d; int
0x180015f60  mov     r8d, r12d; unsigned int
0x180015f63  mov     qword ptr [rsp+0D0h+fIgnoreHKCU], rax; int *
0x180015f68  mov     edx, esi; unsigned int
0x180015f6a  mov     rcx, rdi; this
0x180015f6d  call    ?FindCacheEntry@CRegZoneCache@CRegZone@@IEAAHKKHAEAH@Z; CRegZone::CRegZoneCache::FindCacheEntry(ulong,ulong,int,int &)
0x180015f72  mov     ebx, dword ptr [rbp+37h+phNewUSKey]
0x180015f75  jmp     loc_180015E55
```
