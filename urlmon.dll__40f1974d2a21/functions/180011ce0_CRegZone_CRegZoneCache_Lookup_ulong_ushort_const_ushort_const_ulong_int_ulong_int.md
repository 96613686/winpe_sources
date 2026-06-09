# CRegZone::CRegZoneCache::Lookup(ulong,ushort const *,ushort const *,ulong,int,ulong *,int)

- ea: `0x180011ce0`
- end: `0x1800120af`
- name: `?Lookup@CRegZoneCache@CRegZone@@QEAAHKPEBG0KHPEAKH@Z`
- size: `975`
- prototype: `__int64 __usercall@<rax>(CRegZone::CRegZoneCache *__hidden this@<rcx>, unsigned int@<edx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, unsigned int, int, unsigned int *, int)`
- caller_count: `3`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x180027dc0`
- `0x180068bd8`
- `0x180107768`

## callees

- `0x18000eae0`
- `0x18001054c`
- `0x180011ce0`
- `0x180013be0`
- `0x1800342d0`
- `0x1800363e0`
- `0x180056d60`
- `0x18006b964`
- `0x18007ef30`
- `0x18011baa0`
- `0x18011c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011d9e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011fdb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011d9e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011fdb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011d26`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011f93`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011d26`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011f93`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180011e63`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180011eca`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180011f20`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180012023`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180011e63`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180011eca`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180011f20`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180012023`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegQueryUSValueW` at `0x180011f79`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegQueryUSValueW` at `0x180012077`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegQueryUSValueW` at `0x180011f79`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegQueryUSValueW` at `0x180012077`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x180011ff9`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x180011ff9`

## pseudocode

```c
__int64 __fastcall CRegZone::CRegZoneCache::Lookup(
        CRegZone::CRegZoneCache *this,
        unsigned int a2,
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
0x180011ce0  mov     [rsp-8+arg_8], rbx
0x180011ce5  push    rbp
0x180011ce6  push    rsi
0x180011ce7  push    rdi
0x180011ce8  push    r12
0x180011cea  push    r13
0x180011cec  push    r14
0x180011cee  push    r15
0x180011cf0  lea     rbp, [rsp-7]
0x180011cf5  sub     rsp, 0A0h
0x180011cfc  mov     rax, cs:__security_cookie
0x180011d03  xor     rax, rsp
0x180011d06  mov     [rbp+37h+var_38], rax
0x180011d0a  mov     r15, [rbp+37h+pvData]
0x180011d0e  lea     rax, [rcx+10h]
0x180011d12  mov     rdi, rcx
0x180011d15  mov     [rbp+37h+pwzPath], r9
0x180011d19  mov     rcx, rax; lpCriticalSection
0x180011d1c  mov     [rbp+37h+var_60], r8
0x180011d20  mov     esi, edx
0x180011d22  mov     [rbp+37h+lpCriticalSection], rax
0x180011d26  call    cs:__imp_EnterCriticalSection
0x180011d2c  mov     eax, [rdi+38h]
0x180011d2f  mov     r8d, [rdi]; unsigned int
0x180011d32  neg     eax
0x180011d34  sbb     edx, edx
0x180011d36  and     edx, 0Ch; unsigned int
0x180011d39  call    ?IsCounterEqual@CSharedMem@@QEAAHKKH@Z; CSharedMem::IsCounterEqual(ulong,ulong,int)
0x180011d3e  test    eax, eax
0x180011d40  jz      loc_18001203A
0x180011d46  mov     r13d, [rbp+37h+arg_28]
0x180011d4a  xor     ebx, ebx
0x180011d4c  mov     r12d, [rbp+37h+arg_20]
0x180011d50  cmp     ebx, 50h ; 'P'
0x180011d53  jge     short loc_180011DCE
0x180011d55  movsxd  rcx, ebx
0x180011d58  lea     rax, [rcx+4]
0x180011d5c  add     rax, rax
0x180011d5f  mov     eax, [rdi+rax*8]
0x180011d62  cmp     eax, 0FFFFFFFFh
0x180011d65  jz      short loc_180011DCE
0x180011d67  cmp     eax, esi
0x180011d69  jnz     short loc_180011D79
0x180011d6b  add     rcx, rcx
0x180011d6e  cmp     [rdi+rcx*8+44h], r12d
0x180011d73  lea     rax, [rdi+rcx*8]
0x180011d77  jz      short loc_180011D7D
0x180011d79  inc     ebx
0x180011d7b  jmp     short loc_180011D50
0x180011d7d  cmp     [rax+48h], r13d
0x180011d81  jnz     short loc_180011D79
0x180011d83  cmp     [rbp+37h+arg_38], 0
0x180011d87  jnz     short loc_180011DF6
0x180011d89  mov     r14d, 1
0x180011d8f  test    r15, r15
0x180011d92  jz      short loc_180011D9A
0x180011d94  mov     eax, [rax+4Ch]
0x180011d97  mov     [r15], eax
0x180011d9a  mov     rcx, [rbp+37h+lpCriticalSection]; lpCriticalSection
0x180011d9e  call    cs:__imp_LeaveCriticalSection
0x180011da4  mov     eax, r14d
0x180011da7  mov     rcx, [rbp+37h+var_38]
0x180011dab  xor     rcx, rsp; StackCookie
0x180011dae  call    __security_check_cookie
0x180011db3  mov     rbx, [rsp+0D0h+arg_8]
0x180011dbb  add     rsp, 0A0h
0x180011dc2  pop     r15
0x180011dc4  pop     r14
0x180011dc6  pop     r13
0x180011dc8  pop     r12
0x180011dca  pop     rdi
0x180011dcb  pop     rsi
0x180011dcc  pop     rbp
0x180011dcd  retn
0x180011dce  mov     ebx, [rdi+540h]
0x180011dd4  mov     eax, 66666667h
0x180011dd9  lea     ecx, [rbx+1]
0x180011ddc  imul    ecx
0x180011dde  sar     edx, 5
0x180011de1  mov     eax, edx
0x180011de3  shr     eax, 1Fh
0x180011de6  add     edx, eax
0x180011de8  lea     eax, [rdx+rdx*4]
0x180011deb  shl     eax, 4
0x180011dee  sub     ecx, eax
0x180011df0  mov     [rdi+540h], ecx
0x180011df6  mov     r9d, r12d
0x180011df9  lea     r8, aLx; "%lX"
0x180011e00  mov     edx, 0Ch; unsigned __int64
0x180011e05  lea     rcx, [rbp+37h+pszValue]; unsigned __int16 *
0x180011e09  xor     r14d, r14d
0x180011e0c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180011e11  test    eax, eax
0x180011e13  js      short loc_180011D9A
0x180011e15  lea     rax, ??_7CRegKey@@6B@; const CRegKey::`vftable'
0x180011e1c  mov     [rbp+37h+hUSKey], r14
0x180011e20  lea     rcx, [rbp+37h+var_80]; this
0x180011e24  mov     [rbp+37h+var_80], rax
0x180011e28  mov     [rbp+37h+var_70], r13d
0x180011e2c  mov     [rbp+37h+var_6C], 1
0x180011e34  mov     [rbp+37h+phNewUSKey], r14
0x180011e38  call    ?Close@CRegKey@@UEAAJXZ; CRegKey::Close(void)
0x180011e3d  mov     rcx, [rbp+37h+pwzPath]; pwzPath
0x180011e41  test    rcx, rcx
0x180011e44  jz      loc_180011EDD
0x180011e4a  cmp     dword ptr [rbp+37h+var_6C], r14d
0x180011e4e  jnz     short loc_180011EAF
0x180011e50  mov     eax, [rbp+37h+var_70]
0x180011e53  lea     r9, [rbp+37h+phNewUSKey]; phNewUSKey
0x180011e57  mov     [rsp+0D0h+fIgnoreHKCU], eax; fIgnoreHKCU
0x180011e5b  xor     r8d, r8d; hRelativeUSKey
0x180011e5e  mov     edx, 20019h; samDesired
0x180011e63  call    cs:__imp_SHRegOpenUSKeyW
0x180011e69  test    eax, eax
0x180011e6b  jnz     short loc_180011EDD
0x180011e6d  mov     rax, [rbp+37h+phNewUSKey]
0x180011e71  lea     r8, [rbp+37h+pszValue]; unsigned __int16 *
0x180011e75  mov     rdx, r15; unsigned int *
0x180011e78  mov     [rbp+37h+hUSKey], rax
0x180011e7c  lea     rcx, [rbp+37h+var_80]; this
0x180011e80  call    ?QueryValue@CRegKey@@QEAAJPEAKPEBG@Z; CRegKey::QueryValue(ulong *,ushort const *)
0x180011e85  test    eax, eax
0x180011e87  jnz     short loc_180011EDD
0x180011e89  mov     eax, [r15]
0x180011e8c  mov     r9d, r13d; int
0x180011e8f  mov     [rsp+0D0h+var_A8], ebx; int
0x180011e93  mov     r8d, r12d; unsigned int
0x180011e96  mov     edx, esi; unsigned int
0x180011e98  mov     [rsp+0D0h+fIgnoreHKCU], eax; unsigned int
0x180011e9c  mov     rcx, rdi; this
0x180011e9f  mov     r14d, 1
0x180011ea5  call    ?Add@CRegZoneCache@CRegZone@@QEAAXKKHKH@Z; CRegZone::CRegZoneCache::Add(ulong,ulong,int,ulong,int)
0x180011eaa  jmp     loc_180011FE1
0x180011eaf  mov     eax, [rbp+37h+var_70]
0x180011eb2  test    eax, eax
0x180011eb4  jnz     short loc_180011E53
0x180011eb6  lea     r9, [rbp+37h+phNewUSKey]; phNewUSKey
0x180011eba  mov     [rsp+0D0h+fIgnoreHKCU], 1; fIgnoreHKCU
0x180011ec2  xor     r8d, r8d; hRelativeUSKey
0x180011ec5  mov     edx, 20019h; samDesired
0x180011eca  call    cs:__imp_SHRegOpenUSKeyW
0x180011ed0  test    eax, eax
0x180011ed2  jz      short loc_180011E6D
0x180011ed4  mov     rcx, [rbp+37h+pwzPath]
0x180011ed8  jmp     loc_180011E50
0x180011edd  mov     rax, [rbp+37h+var_80]
0x180011ee1  lea     rcx, [rbp+37h+var_80]
0x180011ee5  mov     dword ptr [rbp+37h+var_6C], r14d
0x180011ee9  mov     [rbp+37h+phNewUSKey], r14
0x180011eed  mov     rax, [rax+10h]
0x180011ef1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ef6  mov     rcx, [rbp+37h+var_60]; pwzPath
0x180011efa  test    rcx, rcx
0x180011efd  jz      loc_180011FE1
0x180011f03  cmp     dword ptr [rbp+37h+var_6C], r14d
0x180011f07  jnz     loc_180012004
0x180011f0d  mov     eax, [rbp+37h+var_70]
0x180011f10  lea     r9, [rbp+37h+phNewUSKey]; phNewUSKey
0x180011f14  mov     [rsp+0D0h+fIgnoreHKCU], eax; fIgnoreHKCU
0x180011f18  xor     r8d, r8d; hRelativeUSKey
0x180011f1b  mov     edx, 20019h; samDesired
0x180011f20  call    cs:__imp_SHRegOpenUSKeyW
0x180011f26  test    eax, eax
0x180011f28  jnz     loc_180011FE1
0x180011f2e  mov     rcx, [rbp+37h+phNewUSKey]; hUSKey
0x180011f32  mov     [rbp+37h+hUSKey], rcx
0x180011f36  mov     dword ptr [rbp+37h+phNewUSKey], r14d
0x180011f3a  mov     dword ptr [rbp+37h+pwzPath], 4
0x180011f41  test    rcx, rcx
0x180011f44  jz      loc_180011D9A
0x180011f4a  cmp     dword ptr [rbp+37h+var_6C], r14d
0x180011f4e  jnz     loc_180012047
0x180011f54  mov     eax, [rbp+37h+var_70]
0x180011f57  lea     r8, [rbp+37h+phNewUSKey]; pdwType
0x180011f5b  mov     [rsp+0D0h+dwDefaultDataSize], r14d; dwDefaultDataSize
0x180011f60  lea     rdx, [rbp+37h+pszValue]; pszValue
0x180011f64  mov     [rsp+0D0h+pvDefaultData], r14; pvDefaultData
0x180011f69  mov     r9, r15; pvData
0x180011f6c  mov     [rsp+0D0h+var_A8], eax; fIgnoreHKCU
0x180011f70  lea     rax, [rbp+37h+pwzPath]
0x180011f74  mov     qword ptr [rsp+0D0h+fIgnoreHKCU], rax; pcbData
0x180011f79  call    cs:__imp_SHRegQueryUSValueW
0x180011f7f  test    eax, eax
0x180011f81  jnz     short loc_180011FE1
0x180011f83  mov     r15d, [r15]
0x180011f86  lea     rcx, [rdi+10h]; lpCriticalSection
0x180011f8a  mov     r14d, 1
0x180011f90  mov     dword ptr [rbp+37h+phNewUSKey], ebx
0x180011f93  call    cs:__imp_EnterCriticalSection
0x180011f99  cmp     ebx, 0FFFFFFFFh
0x180011f9c  jz      loc_18001208E
0x180011fa2  movsxd  rax, ebx
0x180011fa5  lea     rcx, ?g_SharedMem@@3VCSharedMem@@A; this
0x180011fac  add     rax, 4
0x180011fb0  mov     r8, rdi; unsigned int *
0x180011fb3  add     rax, rax
0x180011fb6  mov     [rdi+rax*8], esi
0x180011fb9  mov     [rdi+rax*8+4], r12d
0x180011fbe  mov     [rdi+rax*8+8], r13d
0x180011fc3  mov     [rdi+rax*8+0Ch], r15d
0x180011fc8  mov     eax, [rdi+38h]
0x180011fcb  neg     eax
0x180011fcd  sbb     edx, edx
0x180011fcf  and     edx, 0Ch; unsigned int
0x180011fd2  call    ?GetCounter@CSharedMem@@QEAAHKPEAK@Z; CSharedMem::GetCounter(ulong,ulong *)
0x180011fd7  lea     rcx, [rdi+10h]; lpCriticalSection
0x180011fdb  call    cs:__imp_LeaveCriticalSection
0x180011fe1  mov     rcx, [rbp+37h+hUSKey]; hUSKey
0x180011fe5  lea     rax, ??_7CRegKey@@6B@; const CRegKey::`vftable'
0x180011fec  mov     [rbp+37h+var_80], rax
0x180011ff0  test    rcx, rcx
0x180011ff3  jz      loc_180011D9A
0x180011ff9  call    cs:__imp_SHRegCloseUSKey
0x180011fff  jmp     loc_180011D9A
0x180012004  mov     eax, [rbp+37h+var_70]
0x180012007  test    eax, eax
0x180012009  jnz     loc_180011F10
0x18001200f  lea     r9, [rbp+37h+phNewUSKey]; phNewUSKey
0x180012013  mov     [rsp+0D0h+fIgnoreHKCU], 1; fIgnoreHKCU
0x18001201b  xor     r8d, r8d; hRelativeUSKey
0x18001201e  mov     edx, 20019h; samDesired
0x180012023  call    cs:__imp_SHRegOpenUSKeyW
0x180012029  test    eax, eax
0x18001202b  jz      loc_180011F2E
0x180012031  mov     rcx, [rbp+37h+var_60]
0x180012035  jmp     loc_180011F0D
0x18001203a  mov     rcx, rdi; this
0x18001203d  call    ?Flush@CRegZoneCache@CRegZone@@QEAAXXZ; CRegZone::CRegZoneCache::Flush(void)
0x180012042  jmp     loc_180011D46
0x180012047  cmp     [rbp+37h+var_70], r14d
0x18001204b  jnz     loc_180011F54
0x180012051  mov     [rsp+0D0h+dwDefaultDataSize], r14d; dwDefaultDataSize
0x180012056  lea     rax, [rbp+37h+pwzPath]
0x18001205a  mov     [rsp+0D0h+pvDefaultData], r14; pvDefaultData
0x18001205f  lea     r8, [rbp+37h+phNewUSKey]; pdwType
0x180012063  mov     [rsp+0D0h+var_A8], 1; fIgnoreHKCU
0x18001206b  lea     rdx, [rbp+37h+pszValue]; pszValue
0x18001206f  mov     r9, r15; pvData
0x180012072  mov     qword ptr [rsp+0D0h+fIgnoreHKCU], rax; pcbData
0x180012077  call    cs:__imp_SHRegQueryUSValueW
0x18001207d  test    eax, eax
0x18001207f  jz      loc_180011F83
0x180012085  mov     rcx, [rbp+37h+hUSKey]
0x180012089  jmp     loc_180011F54
0x18001208e  lea     rax, [rbp+37h+phNewUSKey]
0x180012092  mov     r9d, r13d; int
0x180012095  mov     r8d, r12d; unsigned int
0x180012098  mov     qword ptr [rsp+0D0h+fIgnoreHKCU], rax; int *
0x18001209d  mov     edx, esi; unsigned int
0x18001209f  mov     rcx, rdi; this
0x1800120a2  call    ?FindCacheEntry@CRegZoneCache@CRegZone@@IEAAHKKHAEAH@Z; CRegZone::CRegZoneCache::FindCacheEntry(ulong,ulong,int,int &)
0x1800120a7  mov     ebx, dword ptr [rbp+37h+phNewUSKey]
0x1800120aa  jmp     loc_180011FA2
```
