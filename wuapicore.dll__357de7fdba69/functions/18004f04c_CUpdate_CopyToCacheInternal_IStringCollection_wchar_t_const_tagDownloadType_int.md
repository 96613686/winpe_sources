# CUpdate::CopyToCacheInternal(IStringCollection *,wchar_t const *,tagDownloadType,int)

- ea: `0x18004f04c`
- end: `0x18004f465`
- name: `?CopyToCacheInternal@CUpdate@@AEAAJPEAUIStringCollection@@PEB_WW4tagDownloadType@@H@Z`
- size: `1049`
- prototype: `__int64 __fastcall(__int64, __int64, void *)`
- caller_count: `2`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18004ed60`
- `0x18005c750`

## callees

- `0x180005a00`
- `0x180006ac4`
- `0x18000ed54`
- `0x180045bb8`
- `0x180045e0c`
- `0x18004f04c`
- `0x18005d73c`
- `0x180081a38`
- `0x180082720`
- `0x18008d284`
- `0x18009b050`
- `0x1800a1960`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18004f179`
- `OLEAUT32!__imp_SysFreeString` at `0x18004f208`
- `OLEAUT32!__imp_SysFreeString` at `0x18004f36f`
- `OLEAUT32!__imp_SysFreeString` at `0x18004f179`
- `OLEAUT32!__imp_SysFreeString` at `0x18004f208`
- `OLEAUT32!__imp_SysFreeString` at `0x18004f36f`
- `OLEAUT32!__imp_SysStringLen` at `0x18004f1b0`
- `OLEAUT32!__imp_SysStringLen` at `0x18004f1b0`

## string_xrefs

- `0x18004f094`: `C:\__w\1\s\src\Client\comapi\Update.cpp`
- `0x18004f0c4`: `C:\__w\1\s\src\Client\comapi\Update.cpp`
- `0x18004f328`: `C:\__w\1\s\src\Client\comapi\Update.cpp`
- `0x18004f35e`: `C:\__w\1\s\src\Client\comapi\Update.cpp`
- `0x18004f420`: `C:\__w\1\s\src\Client\comapi\Update.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CUpdate::CopyToCacheInternal(__int64 a1, __int64 a2, void *a3)
{
  unsigned int v5; // r14d
  __int64 v6; // rdx
  int v7; // edi
  int v8; // ebx
  __int64 v9; // rdx
  int v11; // edi
  __int64 (__fastcall *v12)(__int64, _QWORD, BSTR *); // rbx
  void *v13; // rbx
  __int128 *v14; // rbx
  char IsEnabled; // al
  __int128 v16; // xmm1
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // rdx
  int v21; // [rsp+20h] [rbp-E0h]
  int v22; // [rsp+20h] [rbp-E0h]
  void *lpMem[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v24; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v25; // [rsp+70h] [rbp-90h]
  __int128 v26; // [rsp+80h] [rbp-80h]
  __int128 v27; // [rsp+90h] [rbp-70h]
  __int128 v28; // [rsp+A0h] [rbp-60h]
  __int128 v29; // [rsp+B0h] [rbp-50h]
  __int128 v30; // [rsp+C0h] [rbp-40h]
  __int128 v31; // [rsp+D0h] [rbp-30h]
  __int128 v32; // [rsp+E0h] [rbp-20h]
  __int128 v33; // [rsp+F0h] [rbp-10h]
  __int128 v34; // [rsp+100h] [rbp+0h]
  __int128 v35; // [rsp+110h] [rbp+10h]
  __int128 v36; // [rsp+120h] [rbp+20h]
  __int128 v37; // [rsp+130h] [rbp+30h]
  __int64 v38; // [rsp+140h] [rbp+40h]
  int v39; // [rsp+150h] [rbp+50h] BYREF
  BSTR pbstr; // [rsp+158h] [rbp+58h] BYREF
  void **v41; // [rsp+160h] [rbp+60h] BYREF
  __int64 v42; // [rsp+168h] [rbp+68h]
  __int64 v43; // [rsp+170h] [rbp+70h]
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  v5 = 0;
  if ( a2 )
  {
    v8 = SecurityCheck(1, a2, a3);
    if ( v8 < 0 )
    {
      v9 = 1325;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Update.cpp",
        (const char *)(unsigned int)v8,
        v21);
      return (unsigned int)v8;
    }
    if ( *(_DWORD *)(a1 + 320) == 1 )
    {
      v8 = -2145124298;
      v9 = 1328;
      goto LABEL_6;
    }
    if ( *(_WORD *)(a1 + 630) == 0xFFFF )
    {
      v8 = -2145124297;
      v9 = 1332;
      goto LABEL_6;
    }
    v39 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a2 + 80LL))(a2, &v39);
    if ( v8 < 0 )
    {
      v9 = 1335;
      goto LABEL_6;
    }
    if ( !v39 )
    {
      v6 = 1337;
      goto LABEL_3;
    }
    v41 = &CSusArrayList<wchar_t *,CSusArrayListItemOpSusFree<wchar_t *>>::`vftable';
    v11 = 0;
    v42 = 0;
    v43 = 0;
    if ( v39 > 0 )
    {
      while ( 1 )
      {
        pbstr = 0;
        v12 = *(__int64 (__fastcall **)(__int64, _QWORD, BSTR *))(*(_QWORD *)a2 + 56LL);
        SysFreeString(0);
        pbstr = 0;
        v7 = v12(a2, v5, &pbstr);
        if ( v7 < 0 )
        {
          v20 = 1343;
          goto LABEL_32;
        }
        if ( !pbstr || !SysStringLen(pbstr) )
        {
          v7 = -2147024809;
          v20 = 1344;
LABEL_32:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v20,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Update.cpp",
            (const char *)(unsigned int)v7,
            v21);
          goto LABEL_33;
        }
        lpMem[0] = 0;
        v7 = DuplicateString<wchar_t *,wchar_t *>(pbstr, lpMem);
        v13 = lpMem[0];
        if ( v7 < 0 )
          break;
        v7 = CSusArrayList<CSearchJob *,CSusArrayListItemOpInterfacePtr<CSearchJob *>>::Add(&v41, lpMem, 0);
        if ( v7 < 0 )
        {
          v19 = 1348;
          goto LABEL_28;
        }
        SysFreeString(pbstr);
        if ( (int)++v5 >= v39 )
        {
          v11 = v42;
          goto LABEL_23;
        }
      }
      v19 = 1347;
LABEL_28:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Update.cpp",
        (const char *)(unsigned int)v7,
        v21);
      if ( v13 )
        SusFree(v13);
LABEL_33:
      SysFreeString(pbstr);
      goto LABEL_38;
    }
LABEL_23:
    v14 = (__int128 *)(a1 + 688);
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_WUSAMultiMSURebase>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WUSAMultiMSURebase>::GetImpl'::`2'::impl);
    v16 = *(_OWORD *)(a1 + 704);
    if ( IsEnabled )
    {
      v24 = *v14;
      v25 = v16;
      v26 = *(_OWORD *)(a1 + 720);
      v27 = *(_OWORD *)(a1 + 736);
      v28 = *(_OWORD *)(a1 + 752);
      v29 = *(_OWORD *)(a1 + 768);
      v30 = *(_OWORD *)(a1 + 784);
      v31 = *(_OWORD *)(a1 + 800);
      v32 = *(_OWORD *)(a1 + 816);
      v33 = *(_OWORD *)(a1 + 832);
      v34 = *(_OWORD *)(a1 + 848);
      v35 = *(_OWORD *)(a1 + 864);
      v36 = *(_OWORD *)(a1 + 880);
      v37 = *(_OWORD *)(a1 + 896);
      v38 = *(_QWORD *)(a1 + 912);
      v22 = v11;
      v17 = CSusInternalWrapper::CopyUpdateToCache3(a1 + 72, a1 + 936, &v24, (unsigned int)v39);
      v7 = v17;
      if ( v17 < 0 )
      {
        v18 = 1366;
LABEL_36:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v18,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Update.cpp",
          (const char *)(unsigned int)v17,
          v22);
LABEL_38:
        CSusArrayList<wchar_t *,CSusArrayListItemOpSusFree<wchar_t *>>::~CSusArrayList<wchar_t *,CSusArrayListItemOpSusFree<wchar_t *>>(&v41);
        return (unsigned int)v7;
      }
    }
    else
    {
      v24 = *v14;
      v25 = v16;
      v26 = *(_OWORD *)(a1 + 720);
      v27 = *(_OWORD *)(a1 + 736);
      v28 = *(_OWORD *)(a1 + 752);
      v29 = *(_OWORD *)(a1 + 768);
      v30 = *(_OWORD *)(a1 + 784);
      v31 = *(_OWORD *)(a1 + 800);
      v32 = *(_OWORD *)(a1 + 816);
      v33 = *(_OWORD *)(a1 + 832);
      v34 = *(_OWORD *)(a1 + 848);
      v35 = *(_OWORD *)(a1 + 864);
      v36 = *(_OWORD *)(a1 + 880);
      v37 = *(_OWORD *)(a1 + 896);
      v38 = *(_QWORD *)(a1 + 912);
      v22 = v11;
      v17 = CSusInternalWrapper::CopyUpdateToCache2(a1 + 72, a1 + 936, &v24, (unsigned int)v39);
      v7 = v17;
      if ( v17 < 0 )
      {
        v18 = 1375;
        goto LABEL_36;
      }
    }
    v7 = 0;
    goto LABEL_38;
  }
  v6 = 1322;
LABEL_3:
  v7 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Update.cpp",
    (const char *)0x80070057LL,
    v21);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18004f04c  push    rbp
0x18004f04e  push    rbx
0x18004f04f  push    rsi
0x18004f050  push    rdi
0x18004f051  push    r12
0x18004f053  push    r13
0x18004f055  push    r14
0x18004f057  push    r15
0x18004f059  lea     rbp, [rsp-88h]
0x18004f061  sub     rsp, 188h
0x18004f068  mov     rax, cs:__security_cookie
0x18004f06f  xor     rax, rsp
0x18004f072  mov     [rbp+0C0h+var_48], rax
0x18004f076  mov     r13d, r9d
0x18004f079  mov     r12, r8
0x18004f07c  mov     r15, rdx
0x18004f07f  mov     rsi, rcx
0x18004f082  xor     r14d, r14d
0x18004f085  test    rdx, rdx
0x18004f088  jnz     short loc_18004F0AF
0x18004f08a  mov     edx, 52Ah; void *
0x18004f08f  mov     edi, 80070057h
0x18004f094  lea     r8, aCW1SSrcClientC_32; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x18004f09b  mov     r9d, edi; char *
0x18004f09e  mov     rcx, [rbp+0C8h]; this
0x18004f0a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f0aa  jmp     loc_18004F443
0x18004f0af  mov     ecx, 1; unsigned int
0x18004f0b4  call    ?SecurityCheck@@YAJK@Z; SecurityCheck(ulong)
0x18004f0b9  mov     ebx, eax
0x18004f0bb  test    eax, eax
0x18004f0bd  jns     short loc_18004F0E1
0x18004f0bf  mov     edx, 52Dh; void *
0x18004f0c4  lea     r8, aCW1SSrcClientC_32; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x18004f0cb  mov     r9d, ebx; char *
0x18004f0ce  mov     rcx, [rbp+0C8h]; this
0x18004f0d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f0da  mov     eax, ebx
0x18004f0dc  jmp     loc_18004F445
0x18004f0e1  cmp     dword ptr [rsi+140h], 1
0x18004f0e8  jnz     short loc_18004F0F6
0x18004f0ea  mov     ebx, 80240036h
0x18004f0ef  mov     edx, 530h
0x18004f0f4  jmp     short loc_18004F0C4
0x18004f0f6  or      eax, 0FFFFFFFFh
0x18004f0f9  cmp     ax, [rsi+276h]
0x18004f100  jnz     short loc_18004F10E
0x18004f102  mov     ebx, 80240037h
0x18004f107  mov     edx, 534h
0x18004f10c  jmp     short loc_18004F0C4
0x18004f10e  mov     [rbp+0C0h+var_70], r14d
0x18004f112  mov     rax, [r15]
0x18004f115  lea     rdx, [rbp+0C0h+var_70]
0x18004f119  mov     rcx, r15
0x18004f11c  mov     rax, [rax+50h]
0x18004f120  call    _guard_dispatch_icall
0x18004f125  mov     ebx, eax
0x18004f127  test    eax, eax
0x18004f129  jns     short loc_18004F132
0x18004f12b  mov     edx, 537h
0x18004f130  jmp     short loc_18004F0C4
0x18004f132  mov     eax, [rbp+0C0h+var_70]
0x18004f135  test    eax, eax
0x18004f137  jnz     short loc_18004F143
0x18004f139  mov     edx, 539h
0x18004f13e  jmp     loc_18004F08F
0x18004f143  xorps   xmm0, xmm0
0x18004f146  movups  [rbp+0C0h+var_60], xmm0
0x18004f14a  lea     rcx, ??_7?$CSusArrayList@PEA_WV?$CSusArrayListItemOpSusFree@PEA_W@@@@6B@; const CSusArrayList<wchar_t *,CSusArrayListItemOpSusFree<wchar_t *>>::`vftable'
0x18004f151  mov     qword ptr [rbp+0C0h+var_60], rcx
0x18004f155  mov     rdi, r14
0x18004f158  mov     qword ptr [rbp+0C0h+var_60+8], r14
0x18004f15c  mov     [rbp+0C0h+var_50], r14
0x18004f160  test    eax, eax
0x18004f162  jle     loc_18004F21F
0x18004f168  mov     [rbp+0C0h+pbstr], 0
0x18004f170  mov     rax, [r15]
0x18004f173  mov     rbx, [rax+38h]
0x18004f177  xor     ecx, ecx; bstrString
0x18004f179  call    cs:__imp_SysFreeString
0x18004f17f  mov     [rbp+0C0h+pbstr], 0
0x18004f187  lea     r8, [rbp+0C0h+pbstr]
0x18004f18b  mov     edx, r14d
0x18004f18e  mov     rcx, r15
0x18004f191  mov     rax, rbx
0x18004f194  call    _guard_dispatch_icall
0x18004f199  mov     edi, eax
0x18004f19b  test    eax, eax
0x18004f19d  js      loc_18004F34F
0x18004f1a3  mov     rcx, [rbp+0C0h+pbstr]; pbstr
0x18004f1a7  test    rcx, rcx
0x18004f1aa  jz      loc_18004F343
0x18004f1b0  call    cs:__imp_SysStringLen
0x18004f1b6  test    eax, eax
0x18004f1b8  jz      loc_18004F343
0x18004f1be  mov     [rsp+1C0h+lpMem], 0
0x18004f1c7  lea     rdx, [rsp+1C0h+lpMem]
0x18004f1cc  mov     rcx, [rbp+0C0h+pbstr]
0x18004f1d0  call    ??$DuplicateString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x18004f1d5  mov     edi, eax
0x18004f1d7  mov     rbx, [rsp+1C0h+lpMem]
0x18004f1dc  test    eax, eax
0x18004f1de  js      loc_18004F319
0x18004f1e4  mov     [rsp+1C0h+lpMem], rbx
0x18004f1e9  xor     r8d, r8d
0x18004f1ec  lea     rdx, [rsp+1C0h+lpMem]
0x18004f1f1  lea     rcx, [rbp+0C0h+var_60]
0x18004f1f5  call    ?Add@?$CSusArrayList@PEAVCSearchJob@@V?$CSusArrayListItemOpInterfacePtr@PEAVCSearchJob@@@@@@UEAAJAEBQEAVCSearchJob@@PEAK@Z; CSusArrayList<CSearchJob *,CSusArrayListItemOpInterfacePtr<CSearchJob *>>::Add(CSearchJob * const &,ulong *)
0x18004f1fa  mov     edi, eax
0x18004f1fc  test    eax, eax
0x18004f1fe  js      loc_18004F312
0x18004f204  mov     rcx, [rbp+0C0h+pbstr]; bstrString
0x18004f208  call    cs:__imp_SysFreeString
0x18004f20e  inc     r14d
0x18004f211  cmp     r14d, [rbp+0C0h+var_70]
0x18004f215  jl      loc_18004F168
0x18004f21b  mov     rdi, qword ptr [rbp+0C0h+var_60+8]
0x18004f21f  lea     rbx, [rsi+2B0h]
0x18004f226  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WUSAMultiMSURebase@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WUSAMultiMSURebase@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WUSAMultiMSURebase> `wil::Feature<__WilFeatureTraits_Feature_WUSAMultiMSURebase>::GetImpl(void)'::`2'::impl
0x18004f22d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WUSAMultiMSURebase@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WUSAMultiMSURebase>::__private_IsEnabled(void)
0x18004f232  movups  xmm0, xmmword ptr [rbx]
0x18004f235  movups  xmm1, xmmword ptr [rbx+10h]
0x18004f239  test    al, al
0x18004f23b  mov     eax, 80h
0x18004f240  jz      loc_18004F37A
0x18004f246  lea     r8, [rsp+1C0h+var_160]
0x18004f24b  movups  xmmword ptr [r8], xmm0
0x18004f24f  movups  xmmword ptr [r8+10h], xmm1
0x18004f254  movups  xmm0, xmmword ptr [rbx+20h]
0x18004f258  movups  xmmword ptr [r8+20h], xmm0
0x18004f25d  movups  xmm1, xmmword ptr [rbx+30h]
0x18004f261  movups  xmmword ptr [r8+30h], xmm1
0x18004f266  movups  xmm0, xmmword ptr [rbx+40h]
0x18004f26a  movups  xmmword ptr [r8+40h], xmm0
0x18004f26f  movups  xmm1, xmmword ptr [rbx+50h]
0x18004f273  movups  xmmword ptr [r8+50h], xmm1
0x18004f278  movups  xmm0, xmmword ptr [rbx+60h]
0x18004f27c  movups  xmmword ptr [r8+60h], xmm0
0x18004f281  add     r8, rax
0x18004f284  movups  xmm0, xmmword ptr [rbx+70h]
0x18004f288  movups  xmmword ptr [r8-10h], xmm0
0x18004f28d  add     rbx, rax
0x18004f290  movups  xmm1, xmmword ptr [rbx]
0x18004f293  movups  xmmword ptr [r8], xmm1
0x18004f297  movups  xmm0, xmmword ptr [rbx+10h]
0x18004f29b  movups  xmmword ptr [r8+10h], xmm0
0x18004f2a0  movups  xmm1, xmmword ptr [rbx+20h]
0x18004f2a4  movups  xmmword ptr [r8+20h], xmm1
0x18004f2a9  movups  xmm0, xmmword ptr [rbx+30h]
0x18004f2ad  movups  xmmword ptr [r8+30h], xmm0
0x18004f2b2  movups  xmm1, xmmword ptr [rbx+40h]
0x18004f2b6  movups  xmmword ptr [r8+40h], xmm1
0x18004f2bb  movups  xmm0, xmmword ptr [rbx+50h]
0x18004f2bf  movups  xmmword ptr [r8+50h], xmm0
0x18004f2c4  mov     rax, [rbx+60h]
0x18004f2c8  mov     [r8+60h], rax
0x18004f2cc  mov     eax, [rbp+0C0h+arg_20]
0x18004f2d2  mov     [rsp+1C0h+var_180], eax
0x18004f2d6  mov     [rsp+1C0h+var_188], r13d
0x18004f2db  mov     [rsp+1C0h+var_190], r12
0x18004f2e0  mov     qword ptr [rsp+1C0h+var_1A0], rdi
0x18004f2e5  mov     r9d, [rbp+0C0h+var_70]
0x18004f2e9  lea     r8, [rsp+1C0h+var_160]
0x18004f2ee  lea     rdx, [rsi+3A8h]
0x18004f2f5  lea     rcx, [rsi+48h]
0x18004f2f9  call    ?CopyUpdateToCache3@CSusInternalWrapper@@QEAAJAEBU_GUID@@UtagMatchingUpdate@@KQEAPEB_WKPEB_WW4tagDownloadType@@H@Z; CSusInternalWrapper::CopyUpdateToCache3(_GUID const &,tagMatchingUpdate,ulong,wchar_t const * * const,ulong,wchar_t const *,tagDownloadType,int)
0x18004f2fe  mov     edi, eax
0x18004f300  test    eax, eax
0x18004f302  jns     loc_18004F438
0x18004f308  mov     edx, 556h
0x18004f30d  jmp     loc_18004F420
0x18004f312  mov     edx, 544h
0x18004f317  jmp     short loc_18004F31E
0x18004f319  mov     edx, 543h; void *
0x18004f31e  mov     rcx, [rbp+0C8h]; this
0x18004f325  mov     r9d, edi; char *
0x18004f328  lea     r8, aCW1SSrcClientC_32; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x18004f32f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f334  test    rbx, rbx
0x18004f337  jz      short loc_18004F36B
0x18004f339  mov     rcx, rbx; lpMem
0x18004f33c  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18004f341  jmp     short loc_18004F36B
0x18004f343  mov     edi, 80070057h
0x18004f348  mov     edx, 540h
0x18004f34d  jmp     short loc_18004F354
0x18004f34f  mov     edx, 53Fh; void *
0x18004f354  mov     rcx, [rbp+0C8h]; this
0x18004f35b  mov     r9d, edi; char *
0x18004f35e  lea     r8, aCW1SSrcClientC_32; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x18004f365  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f36a  nop
0x18004f36b  mov     rcx, [rbp+0C0h+pbstr]; bstrString
0x18004f36f  call    cs:__imp_SysFreeString
0x18004f375  jmp     loc_18004F43A
0x18004f37a  lea     rcx, [rsp+1C0h+var_160]
0x18004f37f  movups  xmmword ptr [rcx], xmm0
0x18004f382  movups  xmmword ptr [rcx+10h], xmm1
0x18004f386  movups  xmm0, xmmword ptr [rbx+20h]
0x18004f38a  movups  xmmword ptr [rcx+20h], xmm0
0x18004f38e  movups  xmm1, xmmword ptr [rbx+30h]
0x18004f392  movups  xmmword ptr [rcx+30h], xmm1
0x18004f396  movups  xmm0, xmmword ptr [rbx+40h]
0x18004f39a  movups  xmmword ptr [rcx+40h], xmm0
0x18004f39e  movups  xmm1, xmmword ptr [rbx+50h]
0x18004f3a2  movups  xmmword ptr [rcx+50h], xmm1
0x18004f3a6  movups  xmm0, xmmword ptr [rbx+60h]
0x18004f3aa  movups  xmmword ptr [rcx+60h], xmm0
0x18004f3ae  add     rcx, rax
0x18004f3b1  movups  xmm0, xmmword ptr [rbx+70h]
0x18004f3b5  movups  xmmword ptr [rcx-10h], xmm0
0x18004f3b9  add     rbx, rax
0x18004f3bc  movups  xmm1, xmmword ptr [rbx]
0x18004f3bf  movups  xmmword ptr [rcx], xmm1
0x18004f3c2  movups  xmm0, xmmword ptr [rbx+10h]
0x18004f3c6  movups  xmmword ptr [rcx+10h], xmm0
0x18004f3ca  movups  xmm1, xmmword ptr [rbx+20h]
0x18004f3ce  movups  xmmword ptr [rcx+20h], xmm1
0x18004f3d2  movups  xmm0, xmmword ptr [rbx+30h]
0x18004f3d6  movups  xmmword ptr [rcx+30h], xmm0
0x18004f3da  movups  xmm1, xmmword ptr [rbx+40h]
0x18004f3de  movups  xmmword ptr [rcx+40h], xmm1
0x18004f3e2  movups  xmm0, xmmword ptr [rbx+50h]
0x18004f3e6  movups  xmmword ptr [rcx+50h], xmm0
0x18004f3ea  mov     rax, [rbx+60h]
0x18004f3ee  mov     [rcx+60h], rax
0x18004f3f2  mov     [rsp+1C0h+var_190], r12
0x18004f3f7  mov     qword ptr [rsp+1C0h+var_1A0], rdi; int
0x18004f3fc  mov     r9d, [rbp+0C0h+var_70]
0x18004f400  lea     r8, [rsp+1C0h+var_160]
0x18004f405  lea     rdx, [rsi+3A8h]
0x18004f40c  lea     rcx, [rsi+48h]
0x18004f410  call    ?CopyUpdateToCache2@CSusInternalWrapper@@QEAAJAEBU_GUID@@UtagMatchingUpdate@@KQEAPEB_WKPEB_W@Z; CSusInternalWrapper::CopyUpdateToCache2(_GUID const &,tagMatchingUpdate,ulong,wchar_t const * * const,ulong,wchar_t const *)
0x18004f415  mov     edi, eax
0x18004f417  test    eax, eax
0x18004f419  jns     short loc_18004F438
0x18004f41b  mov     edx, 55Fh; void *
0x18004f420  lea     r8, aCW1SSrcClientC_32; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x18004f427  mov     r9d, eax; char *
0x18004f42a  mov     rcx, [rbp+0C8h]; this
0x18004f431  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f436  jmp     short loc_18004F43A
0x18004f438  xor     edi, edi
0x18004f43a  lea     rcx, [rbp+0C0h+var_60]
0x18004f43e  call    ??1?$CSusArrayList@PEA_WV?$CSusArrayListItemOpSusFree@PEA_W@@@@UEAA@XZ; CSusArrayList<wchar_t *,CSusArrayListItemOpSusFree<wchar_t *>>::~CSusArrayList<wchar_t *,CSusArrayListItemOpSusFree<wchar_t *>>(void)
0x18004f443  mov     eax, edi
0x18004f445  mov     rcx, [rbp+0C0h+var_48]
0x18004f449  xor     rcx, rsp; StackCookie
0x18004f44c  call    __security_check_cookie
0x18004f451  add     rsp, 188h
0x18004f458  pop     r15
0x18004f45a  pop     r14
0x18004f45c  pop     r13
0x18004f45e  pop     r12
0x18004f460  pop     rdi
0x18004f461  pop     rsi
0x18004f462  pop     rbx
0x18004f463  pop     rbp
0x18004f464  retn
```
