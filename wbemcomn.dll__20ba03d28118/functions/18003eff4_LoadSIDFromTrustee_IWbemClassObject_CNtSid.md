# LoadSIDFromTrustee(IWbemClassObject *,CNtSid * *)

- ea: `0x18003eff4`
- end: `0x18003f65d`
- name: `?LoadSIDFromTrustee@@YAJPEAUIWbemClassObject@@PEAPEAVCNtSid@@@Z`
- size: `1641`
- prototype: `int(struct IWbemClassObject *, struct CNtSid **)`
- caller_count: `3`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18003cb18`
- `0x18003d310`
- `0x18003e7c4`

## callees

- `0x18000a290`
- `0x180013564`
- `0x180014120`
- `0x18001c340`
- `0x18001c4d0`
- `0x18001c56c`
- `0x1800269d4`
- `0x180028484`
- `0x18002ee96`
- `0x180039f70`
- `0x18003a678`
- `0x18003c6f8`
- `0x18003dfa8`
- `0x18003eff4`
- `0x180044168`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f3ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f3ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f3a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f3a6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f443`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003f419`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003f419`
- `OLEAUT32!__imp_VariantInit` at `0x18003f018`
- `OLEAUT32!__imp_VariantInit` at `0x18003f54e`
- `OLEAUT32!__imp_VariantInit` at `0x18003f018`
- `OLEAUT32!__imp_VariantInit` at `0x18003f54e`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18003f06a`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18003f06a`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18003f0ef`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18003f0ef`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18003f08b`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18003f08b`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18003f149`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18003f149`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18003f233`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18003f233`

## string_xrefs

- `0x18003f354`: `SIDString`
- `0x18003f40b`: `ConvertStringSidToSidW`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall LoadSIDFromTrustee(struct IWbemClassObject *a1, struct CNtSid **a2)
{
  HRESULT LBound; // eax
  unsigned int v5; // ebx
  _QWORD *v6; // r10
  __int64 v7; // rdx
  __int64 v8; // r9
  __int64 v9; // rcx
  HRESULT UBound; // eax
  HRESULT v11; // eax
  _QWORD *v12; // rax
  void *v13; // rax
  CNtSid *v14; // rax
  struct CNtSid *v15; // rbx
  LONGLONG llVal; // rbx
  FARPROC ProcAddress; // rax
  DWORD SddlDll; // eax
  signed int LastError; // eax
  CNtSid *v20; // rax
  struct CNtSid *v21; // rbx
  const unsigned __int16 *bstrVal; // rbx
  int SidFromDomainAndUser; // eax
  __int64 v24; // rdx
  __int64 v25; // r9
  __int64 v26; // rcx
  VARIANTARG pvarg; // [rsp+40h] [rbp-29h] BYREF
  void *ppvData; // [rsp+58h] [rbp-11h] BYREF
  void *v30[3]; // [rsp+60h] [rbp-9h] BYREF
  VARIANTARG v31; // [rsp+78h] [rbp+Fh] BYREF
  CNtSid *v32; // [rsp+98h] [rbp+2Fh]
  CNtSid *plUbound; // [rsp+D0h] [rbp+67h] BYREF
  LONG plLbound; // [rsp+E0h] [rbp+77h] BYREF
  void *v35; // [rsp+E8h] [rbp+7Fh] BYREF

  v35 = 0;
  VariantInit(&pvarg);
  if ( ((int (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))a1->lpVtbl->Get)(
         a1,
         L"SID",
         0,
         &pvarg,
         0,
         0) < 0
    || pvarg.vt != 8209
    || !pvarg.llVal )
  {
    _variant_t::Clear((_variant_t *)&pvarg);
    if ( ((int (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))a1->lpVtbl->Get)(
           a1,
           L"SIDString",
           0,
           &pvarg,
           0,
           0) >= 0
      && pvarg.vt == 8 )
    {
      llVal = pvarg.llVal;
      if ( pvarg.llVal )
      {
        v35 = 0;
        ProcAddress = (FARPROC)qword_180070408;
        if ( !qword_180070408 )
        {
          SddlDll = DLpLoadSddlDll();
          if ( SddlDll )
          {
            SetLastError(SddlDll);
            goto LABEL_51;
          }
          ProcAddress = GetProcAddress(g_hInstSddlDLL, "ConvertStringSidToSidW");
          qword_180070408 = (__int64)ProcAddress;
          if ( !ProcAddress )
            goto LABEL_51;
        }
        if ( ((unsigned int (__fastcall *)(LONGLONG, void **))ProcAddress)(llVal, &v35) )
        {
          MakeGuard<void * (*)(void *),unsigned short *>(v30, LocalFree, v35);
          v20 = (CNtSid *)CWin32DefaultArena::WbemMemAlloc(0x10u);
          plUbound = v20;
          if ( v20 )
            v21 = CNtSid::CNtSid(v20, v35);
          else
            v21 = 0;
          if ( v21 )
          {
            if ( (unsigned int)CNtSid::IsValid(v21) )
            {
              *a2 = v21;
              ScopeGuardImpl1<void (*)(tagVARIANT const *),tagVARIANT *>::~ScopeGuardImpl1<void (*)(tagVARIANT const *),tagVARIANT *>((__int64)v30);
              goto LABEL_34;
            }
            CNtSid::`scalar deleting destructor'((void **)v21);
          }
          v5 = -2147217402;
          CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, -2147217402);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              78,
              WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids,
              2147749894LL);
          }
          ScopeGuardImpl1<void (*)(tagVARIANT const *),tagVARIANT *>::~ScopeGuardImpl1<void (*)(tagVARIANT const *),tagVARIANT *>((__int64)v30);
          goto LABEL_93;
        }
LABEL_51:
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
        if ( (v5 & 0x80000000) != 0 )
          CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v5);
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_93;
        }
        v7 = 79;
        goto LABEL_59;
      }
    }
    bstrVal = 0;
    _variant_t::Clear((_variant_t *)&pvarg);
    if ( ((int (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))a1->lpVtbl->Get)(
           a1,
           L"Domain",
           0,
           &pvarg,
           0,
           0) >= 0
      && pvarg.vt == 8
      && pvarg.llVal )
    {
      bstrVal = pvarg.bstrVal;
    }
    VariantInit(&v31);
    if ( ((int (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))a1->lpVtbl->Get)(
           a1,
           L"Name",
           0,
           &v31,
           0,
           0) >= 0
      && v31.vt == 8
      && v31.llVal )
    {
      SidFromDomainAndUser = GetSidFromDomainAndUser(bstrVal, v31.bstrVal, a2);
      v5 = SidFromDomainAndUser;
      if ( SidFromDomainAndUser >= 0 )
      {
        _variant_t::~_variant_t(&v31);
        goto LABEL_34;
      }
      CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, SidFromDomainAndUser);
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_92:
        _variant_t::~_variant_t(&v31);
        goto LABEL_93;
      }
      v24 = 80;
      v25 = v5;
      v26 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    }
    else
    {
      v5 = -2147217400;
      CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, -2147217400);
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_92;
      }
      v24 = 81;
      v25 = 2147749896LL;
      v26 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    }
    WPP_SF_D(v26, v24, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, v25);
    goto LABEL_92;
  }
  if ( SafeArrayGetDim(pvarg.parray) != 1 )
  {
    v5 = -2147217400;
    CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, -2147217400);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_93;
    }
    v7 = 77;
    v8 = 2147749896LL;
LABEL_26:
    v9 = v12[2];
    goto LABEL_27;
  }
  plLbound = 0;
  LODWORD(plUbound) = 0;
  LBound = SafeArrayGetLBound(pvarg.parray, 1u, &plLbound);
  v5 = LBound;
  if ( LBound < 0 )
  {
    CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, LBound);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = 72;
LABEL_10:
      v8 = v5;
      v9 = v6[2];
LABEL_27:
      WPP_SF_D(v9, v7, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, v8);
      goto LABEL_93;
    }
    goto LABEL_93;
  }
  UBound = SafeArrayGetUBound(pvarg.parray, 1u, (LONG *)&plUbound);
  v5 = UBound;
  if ( UBound >= 0 )
  {
    ppvData = 0;
    v11 = SafeArrayAccessData(pvarg.parray, &ppvData);
    v5 = v11;
    if ( v11 < 0 )
    {
      CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v11);
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_93;
      }
      v7 = 74;
LABEL_59:
      v8 = v5;
      goto LABEL_26;
    }
    v13 = CWin32DefaultArena::WbemMemAlloc((int)plUbound - plLbound + 1);
    v35 = v13;
    if ( !v13 )
    {
      v5 = -2147217402;
      CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, -2147217402);
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_93;
      }
      v7 = 75;
      v8 = 2147749894LL;
      goto LABEL_26;
    }
    v30[0] = v13;
    v30[1] = 0;
    memcpy_0(v35, ppvData, (int)plUbound - plLbound + 1);
    SafeArrayUnaccessData(pvarg.parray);
    v14 = (CNtSid *)CWin32DefaultArena::WbemMemAlloc(0x10u);
    v32 = v14;
    if ( v14 )
      v15 = CNtSid::CNtSid(v14, v35);
    else
      v15 = 0;
    if ( v15 )
    {
      if ( (unsigned int)CNtSid::IsValid(v15) )
      {
        *a2 = v15;
        CVectorDeleteMe<char>::~CVectorDeleteMe<char>(v30);
LABEL_34:
        v5 = 0;
        goto LABEL_93;
      }
      CNtSid::`scalar deleting destructor'((void **)v15);
    }
    v5 = -2147217402;
    CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, -2147217402);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, 2147749894LL);
    }
    CVectorDeleteMe<char>::~CVectorDeleteMe<char>(v30);
    goto LABEL_93;
  }
  CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, UBound);
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v7 = 73;
    goto LABEL_10;
  }
LABEL_93:
  _variant_t::~_variant_t(&pvarg);
  return v5;
}

```

## disassembly

```asm
0x18003eff4  push    rbp
0x18003eff6  push    rbx
0x18003eff7  push    rsi
0x18003eff8  push    rdi
0x18003eff9  push    r14
0x18003effb  lea     rbp, [rsp-37h]
0x18003f000  sub     rsp, 0A0h
0x18003f007  mov     rsi, rdx
0x18003f00a  mov     rdi, rcx
0x18003f00d  xor     r14d, r14d
0x18003f010  mov     [rbp+57h+arg_18], r14
0x18003f014  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18003f018  call    cs:__imp_VariantInit
0x18003f01e  nop
0x18003f01f  mov     rax, [rdi]
0x18003f022  mov     [rsp+0C0h+var_98], r14
0x18003f027  mov     [rsp+0C0h+var_A0], r14
0x18003f02c  lea     r9, [rbp+57h+pvarg]
0x18003f030  xor     r8d, r8d
0x18003f033  lea     rdx, aSid; "SID"
0x18003f03a  mov     rcx, rdi
0x18003f03d  mov     rax, [rax+20h]
0x18003f041  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f046  test    eax, eax
0x18003f048  js      loc_18003F337
0x18003f04e  mov     eax, 2011h
0x18003f053  cmp     word ptr [rbp+57h+pvarg], ax
0x18003f057  jnz     loc_18003F337
0x18003f05d  mov     rcx, qword ptr [rbp+57h+pvarg+8]; psa
0x18003f061  test    rcx, rcx
0x18003f064  jz      loc_18003F337
0x18003f06a  call    cs:__imp_SafeArrayGetDim
0x18003f070  cmp     eax, 1
0x18003f073  jnz     loc_18003F2E9
0x18003f079  mov     [rbp+57h+plLbound], r14d
0x18003f07d  mov     dword ptr [rbp+57h+plUbound], r14d
0x18003f081  lea     r8, [rbp+57h+plLbound]; plLbound
0x18003f085  mov     edx, eax; nDim
0x18003f087  mov     rcx, qword ptr [rbp+57h+pvarg+8]; psa
0x18003f08b  call    cs:__imp_SafeArrayGetLBound
0x18003f091  mov     ebx, eax
0x18003f093  test    eax, eax
0x18003f095  jns     short loc_18003F0E2
0x18003f097  mov     edx, eax; int
0x18003f099  lea     rcx, qword_18006A9C0; this
0x18003f0a0  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003f0a5  lea     rcx, WPP_GLOBAL_Control
0x18003f0ac  mov     r10, cs:WPP_GLOBAL_Control
0x18003f0b3  cmp     r10, rcx
0x18003f0b6  jz      loc_18003F644
0x18003f0bc  test    byte ptr [r10+1Ch], 1
0x18003f0c1  jz      loc_18003F644
0x18003f0c7  cmp     byte ptr [r10+19h], 2
0x18003f0cc  jb      loc_18003F644
0x18003f0d2  lea     edx, [r14+48h]
0x18003f0d6  mov     r9d, ebx
0x18003f0d9  mov     rcx, [r10+10h]
0x18003f0dd  jmp     loc_18003F1FE
0x18003f0e2  lea     r8, [rbp+57h+plUbound]; plUbound
0x18003f0e6  mov     edx, 1; nDim
0x18003f0eb  mov     rcx, qword ptr [rbp+57h+pvarg+8]; psa
0x18003f0ef  call    cs:__imp_SafeArrayGetUBound
0x18003f0f5  mov     ebx, eax
0x18003f0f7  test    eax, eax
0x18003f0f9  jns     short loc_18003F13D
0x18003f0fb  mov     edx, eax; int
0x18003f0fd  lea     rcx, qword_18006A9C0; this
0x18003f104  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003f109  lea     rcx, WPP_GLOBAL_Control
0x18003f110  mov     r10, cs:WPP_GLOBAL_Control
0x18003f117  cmp     r10, rcx
0x18003f11a  jz      loc_18003F644
0x18003f120  test    byte ptr [r10+1Ch], 1
0x18003f125  jz      loc_18003F644
0x18003f12b  cmp     byte ptr [r10+19h], 2
0x18003f130  jb      loc_18003F644
0x18003f136  mov     edx, 49h ; 'I'
0x18003f13b  jmp     short loc_18003F0D6
0x18003f13d  mov     [rbp+57h+ppvData], r14
0x18003f141  lea     rdx, [rbp+57h+ppvData]; ppvData
0x18003f145  mov     rcx, qword ptr [rbp+57h+pvarg+8]; psa
0x18003f149  call    cs:__imp_SafeArrayAccessData
0x18003f14f  mov     ebx, eax
0x18003f151  test    eax, eax
0x18003f153  jns     short loc_18003F198
0x18003f155  mov     edx, eax; int
0x18003f157  lea     rcx, qword_18006A9C0; this
0x18003f15e  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003f163  lea     rcx, WPP_GLOBAL_Control
0x18003f16a  mov     rax, cs:WPP_GLOBAL_Control
0x18003f171  cmp     rax, rcx
0x18003f174  jz      loc_18003F644
0x18003f17a  test    byte ptr [rax+1Ch], 1
0x18003f17e  jz      loc_18003F644
0x18003f184  cmp     byte ptr [rax+19h], 2
0x18003f188  jb      loc_18003F644
0x18003f18e  mov     edx, 4Ah ; 'J'
0x18003f193  jmp     loc_18003F403
0x18003f198  mov     eax, dword ptr [rbp+57h+plUbound]
0x18003f19b  sub     eax, [rbp+57h+plLbound]
0x18003f19e  inc     eax
0x18003f1a0  movsxd  rcx, eax; unsigned __int64
0x18003f1a3  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18003f1a8  mov     [rbp+57h+arg_18], rax
0x18003f1ac  test    rax, rax
0x18003f1af  jnz     short loc_18003F20F
0x18003f1b1  mov     ebx, 80041006h
0x18003f1b6  mov     edx, ebx; int
0x18003f1b8  lea     rcx, qword_18006A9C0; this
0x18003f1bf  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003f1c4  lea     rcx, WPP_GLOBAL_Control
0x18003f1cb  mov     rax, cs:WPP_GLOBAL_Control
0x18003f1d2  cmp     rax, rcx
0x18003f1d5  jz      loc_18003F644
0x18003f1db  test    byte ptr [rax+1Ch], 1
0x18003f1df  jz      loc_18003F644
0x18003f1e5  cmp     byte ptr [rax+19h], 2
0x18003f1e9  jb      loc_18003F644
0x18003f1ef  mov     edx, 4Bh ; 'K'
0x18003f1f4  mov     r9d, 80041006h
0x18003f1fa  mov     rcx, [rax+10h]
0x18003f1fe  lea     r8, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids
0x18003f205  call    WPP_SF_D
0x18003f20a  jmp     loc_18003F644
0x18003f20f  mov     [rbp+57h+var_60], rax
0x18003f213  mov     [rbp+57h+var_58], r14
0x18003f217  mov     eax, dword ptr [rbp+57h+plUbound]
0x18003f21a  sub     eax, [rbp+57h+plLbound]
0x18003f21d  inc     eax
0x18003f21f  movsxd  r8, eax; Size
0x18003f222  mov     rdx, [rbp+57h+ppvData]; Src
0x18003f226  mov     rcx, [rbp+57h+arg_18]; void *
0x18003f22a  call    memcpy_0
0x18003f22f  mov     rcx, qword ptr [rbp+57h+pvarg+8]; psa
0x18003f233  call    cs:__imp_SafeArrayUnaccessData
0x18003f239  mov     ecx, 10h; unsigned __int64
0x18003f23e  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18003f243  mov     [rbp+57h+var_28], rax
0x18003f247  test    rax, rax
0x18003f24a  jz      short loc_18003F25D
0x18003f24c  mov     rdx, [rbp+57h+arg_18]; void *
0x18003f250  mov     rcx, rax; this
0x18003f253  call    ??0CNtSid@@QEAA@PEAX@Z; CNtSid::CNtSid(void *)
0x18003f258  mov     rbx, rax
0x18003f25b  jmp     short loc_18003F260
0x18003f25d  mov     rbx, r14
0x18003f260  test    rbx, rbx
0x18003f263  jz      short loc_18003F28D
0x18003f265  mov     rcx, rbx; this
0x18003f268  call    ?IsValid@CNtSid@@QEAAHXZ; CNtSid::IsValid(void)
0x18003f26d  test    eax, eax
0x18003f26f  jz      short loc_18003F285
0x18003f271  mov     [rsi], rbx
0x18003f274  lea     rcx, [rbp+57h+var_60]
0x18003f278  call    ??1?$CVectorDeleteMe@D@@QEAA@XZ; CVectorDeleteMe<char>::~CVectorDeleteMe<char>(void)
0x18003f27d  mov     ebx, r14d
0x18003f280  jmp     loc_18003F644
0x18003f285  mov     rcx, rbx; this
0x18003f288  call    ??_GCNtSid@@QEAAPEAXI@Z; CNtSid::`scalar deleting destructor'(uint)
0x18003f28d  mov     ebx, 80041006h
0x18003f292  mov     edx, ebx; int
0x18003f294  lea     rcx, qword_18006A9C0; this
0x18003f29b  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003f2a0  lea     rcx, WPP_GLOBAL_Control
0x18003f2a7  mov     rax, cs:WPP_GLOBAL_Control
0x18003f2ae  cmp     rax, rcx
0x18003f2b1  jz      short loc_18003F2DB
0x18003f2b3  test    byte ptr [rax+1Ch], 1
0x18003f2b7  jz      short loc_18003F2DB
0x18003f2b9  cmp     byte ptr [rax+19h], 2
0x18003f2bd  jb      short loc_18003F2DB
0x18003f2bf  mov     edx, 4Ch ; 'L'
0x18003f2c4  mov     r9d, 80041006h
0x18003f2ca  lea     r8, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids
0x18003f2d1  mov     rcx, [rax+10h]
0x18003f2d5  call    WPP_SF_D
0x18003f2da  nop
0x18003f2db  lea     rcx, [rbp+57h+var_60]
0x18003f2df  call    ??1?$CVectorDeleteMe@D@@QEAA@XZ; CVectorDeleteMe<char>::~CVectorDeleteMe<char>(void)
0x18003f2e4  jmp     loc_18003F644
0x18003f2e9  mov     ebx, 80041008h
0x18003f2ee  mov     edx, ebx; int
0x18003f2f0  lea     rcx, qword_18006A9C0; this
0x18003f2f7  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003f2fc  lea     rcx, WPP_GLOBAL_Control
0x18003f303  mov     rax, cs:WPP_GLOBAL_Control
0x18003f30a  cmp     rax, rcx
0x18003f30d  jz      loc_18003F644
0x18003f313  test    byte ptr [rax+1Ch], 1
0x18003f317  jz      loc_18003F644
0x18003f31d  cmp     byte ptr [rax+19h], 2
0x18003f321  jb      loc_18003F644
0x18003f327  mov     edx, 4Dh ; 'M'
0x18003f32c  mov     r9d, 80041008h
0x18003f332  jmp     loc_18003F1FA
0x18003f337  lea     rcx, [rbp+57h+pvarg]; this
0x18003f33b  call    ?Clear@_variant_t@@QEAAXXZ; _variant_t::Clear(void)
0x18003f340  mov     rax, [rdi]
0x18003f343  mov     [rsp+0C0h+var_98], r14
0x18003f348  mov     [rsp+0C0h+var_A0], r14
0x18003f34d  lea     r9, [rbp+57h+pvarg]
0x18003f351  xor     r8d, r8d
0x18003f354  lea     rdx, aSidstring; "SIDString"
0x18003f35b  mov     rcx, rdi
0x18003f35e  mov     rax, [rax+20h]
0x18003f362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f367  test    eax, eax
0x18003f369  js      loc_18003F501
0x18003f36f  cmp     word ptr [rbp+57h+pvarg], 8
0x18003f374  jnz     loc_18003F501
0x18003f37a  mov     rbx, qword ptr [rbp+57h+pvarg+8]
0x18003f37e  test    rbx, rbx
0x18003f381  jz      loc_18003F501
0x18003f387  mov     [rbp+57h+arg_18], r14
0x18003f38b  mov     rax, cs:qword_180070408
0x18003f392  test    rax, rax
0x18003f395  jnz     loc_18003F42B
0x18003f39b  call    ?DLpLoadSddlDll@@YAKXZ; DLpLoadSddlDll(void)
0x18003f3a0  test    eax, eax
0x18003f3a2  jz      short loc_18003F40B
0x18003f3a4  mov     ecx, eax; dwErrCode
0x18003f3a6  call    cs:__imp_SetLastError
0x18003f3ac  call    cs:__imp_GetLastError
0x18003f3b2  mov     ebx, eax
0x18003f3b4  test    eax, eax
0x18003f3b6  jle     short loc_18003F3C1
0x18003f3b8  movzx   ebx, ax
0x18003f3bb  or      ebx, 80070000h
0x18003f3c1  test    ebx, ebx
0x18003f3c3  jns     short loc_18003F3D3
0x18003f3c5  mov     edx, ebx; int
0x18003f3c7  lea     rcx, qword_18006A9C0; this
0x18003f3ce  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003f3d3  lea     rcx, WPP_GLOBAL_Control
0x18003f3da  mov     rax, cs:WPP_GLOBAL_Control
0x18003f3e1  cmp     rax, rcx
0x18003f3e4  jz      loc_18003F644
0x18003f3ea  test    byte ptr [rax+1Ch], 1
0x18003f3ee  jz      loc_18003F644
0x18003f3f4  cmp     byte ptr [rax+19h], 2
0x18003f3f8  jb      loc_18003F644
0x18003f3fe  mov     edx, 4Fh ; 'O'
0x18003f403  mov     r9d, ebx
0x18003f406  jmp     loc_18003F1FA
0x18003f40b  lea     rdx, aConvertstrings; "ConvertStringSidToSidW"
0x18003f412  mov     rcx, cs:?g_hInstSddlDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18003f419  call    cs:__imp_GetProcAddress
0x18003f41f  mov     cs:qword_180070408, rax
0x18003f426  test    rax, rax
0x18003f429  jz      short loc_18003F3AC
0x18003f42b  lea     rdx, [rbp+57h+arg_18]
0x18003f42f  mov     rcx, rbx
0x18003f432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f437  test    eax, eax
0x18003f439  jz      loc_18003F3AC
0x18003f43f  mov     r8, [rbp+57h+arg_18]
0x18003f443  mov     rdx, cs:__imp_LocalFree
0x18003f44a  lea     rcx, [rbp+57h+var_60]
0x18003f44e  call    ??$MakeGuard@P6APEAXPEAX@ZPEAG@@YA?AV?$ScopeGuardImpl1@P6APEAXPEAX@ZPEAG@@P6APEAXPEAX@ZPEAG@Z; MakeGuard<void * (*)(void *),ushort *>(void * (*)(void *),ushort *)
0x18003f453  nop
0x18003f454  mov     ecx, 10h; unsigned __int64
0x18003f459  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18003f45e  mov     [rbp+57h+plUbound], rax
0x18003f462  test    rax, rax
0x18003f465  jz      short loc_18003F478
0x18003f467  mov     rdx, [rbp+57h+arg_18]; void *
0x18003f46b  mov     rcx, rax; this
0x18003f46e  call    ??0CNtSid@@QEAA@PEAX@Z; CNtSid::CNtSid(void *)
0x18003f473  mov     rbx, rax
0x18003f476  jmp     short loc_18003F47B
0x18003f478  mov     rbx, r14
0x18003f47b  test    rbx, rbx
0x18003f47e  jz      short loc_18003F4A5
0x18003f480  mov     rcx, rbx; this
0x18003f483  call    ?IsValid@CNtSid@@QEAAHXZ; CNtSid::IsValid(void)
0x18003f488  test    eax, eax
0x18003f48a  jz      short loc_18003F49D
0x18003f48c  mov     [rsi], rbx
0x18003f48f  lea     rcx, [rbp+57h+var_60]
0x18003f493  call    ??1?$ScopeGuardImpl1@P6AXPEBUtagVARIANT@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<void (*)(tagVARIANT const *),tagVARIANT *>::~ScopeGuardImpl1<void (*)(tagVARIANT const *),tagVARIANT *>(void)
0x18003f498  jmp     loc_18003F27D
0x18003f49d  mov     rcx, rbx; this
0x18003f4a0  call    ??_GCNtSid@@QEAAPEAXI@Z; CNtSid::`scalar deleting destructor'(uint)
0x18003f4a5  mov     ebx, 80041006h
0x18003f4aa  mov     edx, ebx; int
0x18003f4ac  lea     rcx, qword_18006A9C0; this
0x18003f4b3  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003f4b8  lea     rcx, WPP_GLOBAL_Control
0x18003f4bf  mov     rax, cs:WPP_GLOBAL_Control
0x18003f4c6  cmp     rax, rcx
0x18003f4c9  jz      short loc_18003F4F3
0x18003f4cb  test    byte ptr [rax+1Ch], 1
0x18003f4cf  jz      short loc_18003F4F3
0x18003f4d1  cmp     byte ptr [rax+19h], 2
0x18003f4d5  jb      short loc_18003F4F3
0x18003f4d7  mov     edx, 4Eh ; 'N'
0x18003f4dc  mov     r9d, 80041006h
0x18003f4e2  lea     r8, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids
0x18003f4e9  mov     rcx, [rax+10h]
0x18003f4ed  call    WPP_SF_D
  ... truncated ...
```
