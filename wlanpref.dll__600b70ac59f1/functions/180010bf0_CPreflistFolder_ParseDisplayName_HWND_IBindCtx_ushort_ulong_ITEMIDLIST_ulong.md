# CPreflistFolder::ParseDisplayName(HWND__ *,IBindCtx *,ushort *,ulong *,_ITEMIDLIST * *,ulong *)

- ea: `0x180010bf0`
- end: `0x180010f01`
- name: `?ParseDisplayName@CPreflistFolder@@UEAAJPEAUHWND__@@PEAUIBindCtx@@PEAGPEAKPEAPEFAU_ITEMIDLIST@@3@Z`
- size: `785`
- prototype: `__int64 __fastcall(CPreflistFolder *this, HWND, struct IBindCtx *, unsigned __int16 *, unsigned int *, struct _ITEMIDLIST **, unsigned int *)`
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800036ac`
- `0x18000cf1c`
- `0x18000cfd4`
- `0x18000d264`
- `0x18000fc60`
- `0x1800103d4`
- `0x180010bf0`
- `0x18002749c`
- `0x180027594`
- `0x1800283a0`
- `0x18002d7f6`
- `0x18002d840`
- `0x180030010`

## import_xrefs

- `msvcrt!wcsstr` at `0x180010c61`
- `msvcrt!wcsstr` at `0x180010c61`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180010cc3`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180010cc3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010de7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010de7`

## pseudocode

```c
__int64 __fastcall CPreflistFolder::ParseDisplayName(
        CPreflistFolder *this,
        HWND a2,
        struct IBindCtx *a3,
        unsigned __int16 *a4,
        unsigned int *a5,
        struct _ITEMIDLIST **a6,
        unsigned int *a7)
{
  wchar_t *v8; // rbx
  wchar_t *v9; // rax
  __int64 v10; // rdi
  HRESULT v11; // ebx
  unsigned __int64 i; // rbx
  __int64 v13; // rdi
  int v14; // edi
  char *v15; // rax
  struct _ITEMIDLIST *v16; // rbx
  char v18[8]; // [rsp+30h] [rbp-B1h] BYREF
  LPCOLESTR lpsz; // [rsp+38h] [rbp-A9h] BYREF
  wchar_t *Str; // [rsp+40h] [rbp-A1h] BYREF
  __int64 v21; // [rsp+48h] [rbp-99h] BYREF
  unsigned __int64 v22; // [rsp+50h] [rbp-91h]
  __int64 v23; // [rsp+58h] [rbp-89h]
  int v24; // [rsp+60h] [rbp-81h]
  __int128 Buf2; // [rsp+68h] [rbp-79h] BYREF
  GUID iid; // [rsp+78h] [rbp-69h] BYREF
  _BYTE v27[96]; // [rsp+90h] [rbp-51h] BYREF

  if ( !a4 || !a6 )
    return 2147942487LL;
  *a6 = 0;
  WTL::CString::CString((WTL::CString *)&Str, a4);
  v8 = Str;
  if ( *((int *)Str - 2) < 0 || (v9 = wcsstr(Str, L"\\")) == 0 || (v10 = v9 - v8, (_DWORD)v10 == -1) )
  {
LABEL_20:
    v11 = -2147024809;
    goto LABEL_21;
  }
  WTL::CString::Mid(&Str, &lpsz, 0, (unsigned int)v10);
  WTL::CString::Mid(&Str, v18, (unsigned int)(v10 + 1), (unsigned int)(*((_DWORD *)v8 - 2) - (v10 + 1)));
  iid = 0;
  v11 = IIDFromString(lpsz, &iid);
  if ( v11 < 0 )
  {
    WTL::CString::~CString((WTL::CString *)v18);
    WTL::CString::~CString((WTL::CString *)&lpsz);
LABEL_21:
    WTL::CString::~CString((WTL::CString *)&Str);
    return (unsigned int)v11;
  }
  CPreflistFolder::InitializeDataSource((CPreflistFolder *)((char *)this - 8));
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)CSingletonPtr<CWlanProfileStore>::s_pInstance + 72LL))(
    CSingletonPtr<CWlanProfileStore>::s_pInstance,
    &v21);
  for ( i = 0; ; ++i )
  {
    if ( i >= v22 )
    {
      ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::~CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>(&v21);
      WTL::CString::~CString((WTL::CString *)v18);
      WTL::CString::~CString((WTL::CString *)&lpsz);
      goto LABEL_20;
    }
    v13 = ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::GetAt(&v21, i);
    Buf2 = *(_OWORD *)(v13 + 8);
    if ( !memcmp_0(&iid, &Buf2, 0x10u) )
      break;
  }
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)CSingletonPtr<CWlanProfileStore>::s_pInstance + 88LL))(
    CSingletonPtr<CWlanProfileStore>::s_pInstance,
    v13);
  CProfile::CProfile((CProfile *)v27);
  v14 = (*(__int64 (__fastcall **)(__int64, char *, _BYTE *))(*(_QWORD *)CSingletonPtr<CWlanProfileStore>::s_pInstance
                                                            + 56LL))(
          CSingletonPtr<CWlanProfileStore>::s_pInstance,
          v18,
          v27);
  if ( v14 < 0 )
  {
    CProfile::~CProfile((CProfile *)v27);
    ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::~CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>(&v21);
    WTL::CString::~CString((WTL::CString *)v18);
    WTL::CString::~CString((WTL::CString *)&lpsz);
    v11 = v14;
    goto LABEL_21;
  }
  v15 = (char *)CoTaskMemAlloc(0x838u);
  v16 = (struct _ITEMIDLIST *)v15;
  if ( !v15 )
  {
    CProfile::~CProfile((CProfile *)v27);
    ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::~CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>(&v21);
    WTL::CString::~CString((WTL::CString *)v18);
    WTL::CString::~CString((WTL::CString *)&lpsz);
    v11 = -2147024882;
    goto LABEL_21;
  }
  *(_WORD *)v15 = 2102;
  ProfileToStruct((const struct CProfile *)v27, (struct WPLDATA *)(v15 + 2));
  *(_WORD *)v16[700].mkid.abID = 0;
  *a6 = v16;
  if ( a7 )
  {
    *(_QWORD *)&Buf2 = v16;
    v14 = (*(__int64 (__fastcall **)(CPreflistFolder *, __int64, __int128 *, unsigned int *))(*(_QWORD *)this + 72LL))(
            this,
            1,
            &Buf2,
            a7);
  }
  CProfile::~CProfile((CProfile *)v27);
  ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::~CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>(&v21);
  WTL::CString::~CString((WTL::CString *)v18);
  WTL::CString::~CString((WTL::CString *)&lpsz);
  WTL::CString::~CString((WTL::CString *)&Str);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180010bf0  mov     [rsp-8+arg_8], rbx
0x180010bf5  push    rbp
0x180010bf6  push    rsi
0x180010bf7  push    rdi
0x180010bf8  push    r14
0x180010bfa  push    r15
0x180010bfc  lea     rbp, [rsp-1Fh]
0x180010c01  sub     rsp, 100h
0x180010c08  mov     rax, cs:__security_cookie
0x180010c0f  xor     rax, rsp
0x180010c12  mov     [rbp+3Fh+var_30], rax
0x180010c16  mov     r14, rcx
0x180010c19  mov     rsi, [rbp+3Fh+arg_28]
0x180010c1d  mov     r15, [rbp+3Fh+arg_30]
0x180010c21  test    r9, r9
0x180010c24  jz      loc_180010ED9
0x180010c2a  test    rsi, rsi
0x180010c2d  jz      loc_180010ED9
0x180010c33  mov     qword ptr [rsi], 0
0x180010c3a  mov     rdx, r9; Source
0x180010c3d  lea     rcx, [rsp+120h+Str]; this
0x180010c42  call    ??0CString@WTL@@QEAA@PEBG@Z; WTL::CString::CString(ushort const *)
0x180010c47  nop
0x180010c48  mov     rbx, [rsp+120h+Str]
0x180010c4d  cmp     dword ptr [rbx-8], 0
0x180010c51  jl      loc_180010EC6
0x180010c57  lea     rdx, SubStr; "\\"
0x180010c5e  mov     rcx, rbx; Str
0x180010c61  call    cs:__imp_wcsstr
0x180010c67  mov     rdi, rax
0x180010c6a  test    rax, rax
0x180010c6d  jz      loc_180010EC6
0x180010c73  sub     rdi, rbx
0x180010c76  sar     rdi, 1
0x180010c79  cmp     edi, 0FFFFFFFFh
0x180010c7c  jz      loc_180010EC6
0x180010c82  mov     r9d, edi
0x180010c85  xor     r8d, r8d
0x180010c88  lea     rdx, [rsp+120h+lpsz]
0x180010c8d  lea     rcx, [rsp+120h+Str]
0x180010c92  call    ?Mid@CString@WTL@@QEBA?AV12@HH@Z; WTL::CString::Mid(int,int)
0x180010c97  nop
0x180010c98  lea     r8d, [rdi+1]
0x180010c9c  mov     r9d, [rbx-8]
0x180010ca0  sub     r9d, r8d
0x180010ca3  lea     rdx, [rsp+120h+var_F0]
0x180010ca8  lea     rcx, [rsp+120h+Str]
0x180010cad  call    ?Mid@CString@WTL@@QEBA?AV12@HH@Z; WTL::CString::Mid(int,int)
0x180010cb2  nop
0x180010cb3  xorps   xmm0, xmm0
0x180010cb6  movups  xmmword ptr [rbp+3Fh+iid.Data1], xmm0
0x180010cba  lea     rdx, [rbp+3Fh+iid]; lpiid
0x180010cbe  mov     rcx, [rsp+120h+lpsz]; lpsz
0x180010cc3  call    cs:__imp_IIDFromString
0x180010cc9  mov     ebx, eax
0x180010ccb  test    eax, eax
0x180010ccd  jns     short loc_180010CE9
0x180010ccf  lea     rcx, [rsp+120h+var_F0]; this
0x180010cd4  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x180010cd9  nop
0x180010cda  lea     rcx, [rsp+120h+lpsz]; this
0x180010cdf  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x180010ce4  jmp     loc_180010ECB
0x180010ce9  lea     rcx, [r14-8]; this
0x180010ced  call    ?InitializeDataSource@CPreflistFolder@@IEAAXXZ; CPreflistFolder::InitializeDataSource(void)
0x180010cf2  mov     [rsp+120h+var_D8], 0
0x180010cfb  mov     [rsp+120h+var_D0], 0
0x180010d04  mov     [rsp+120h+var_C8], 0
0x180010d0d  mov     [rsp+120h+var_C0], 0
0x180010d15  mov     rcx, cs:?s_pInstance@?$CSingletonPtr@VCWlanProfileStore@@@@0PEAVCWlanProfileStore@@EA; CWlanProfileStore * CSingletonPtr<CWlanProfileStore>::s_pInstance
0x180010d1c  mov     rax, [rcx]
0x180010d1f  lea     rdx, [rsp+120h+var_D8]
0x180010d24  mov     rax, [rax+48h]
0x180010d28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d2d  xor     ebx, ebx
0x180010d2f  cmp     rbx, [rsp+120h+var_D0]
0x180010d34  jnb     loc_180010EA6
0x180010d3a  mov     rdx, rbx
0x180010d3d  lea     rcx, [rsp+120h+var_D8]
0x180010d42  call    ?GetAt@?$CAtlArray@VCAdapter@@V?$CElementTraits@VCAdapter@@@ATL@@@ATL@@QEBAAEBVCAdapter@@_K@Z; ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::GetAt(unsigned __int64)
0x180010d47  mov     rdi, rax
0x180010d4a  movups  xmm0, xmmword ptr [rax+8]
0x180010d4e  movdqu  [rbp+3Fh+Buf2], xmm0
0x180010d53  mov     r8d, 10h; Size
0x180010d59  lea     rdx, [rbp+3Fh+Buf2]; Buf2
0x180010d5d  lea     rcx, [rbp+3Fh+iid]; Buf1
0x180010d61  call    memcmp_0
0x180010d66  test    eax, eax
0x180010d68  jz      short loc_180010D6F
0x180010d6a  inc     rbx
0x180010d6d  jmp     short loc_180010D2F
0x180010d6f  mov     rcx, cs:?s_pInstance@?$CSingletonPtr@VCWlanProfileStore@@@@0PEAVCWlanProfileStore@@EA; CWlanProfileStore * CSingletonPtr<CWlanProfileStore>::s_pInstance
0x180010d76  mov     rax, [rcx]
0x180010d79  mov     rdx, rdi
0x180010d7c  mov     rax, [rax+58h]
0x180010d80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d85  lea     rcx, [rbp+3Fh+var_90]; this
0x180010d89  call    ??0CProfile@@QEAA@XZ; CProfile::CProfile(void)
0x180010d8e  nop
0x180010d8f  mov     rcx, cs:?s_pInstance@?$CSingletonPtr@VCWlanProfileStore@@@@0PEAVCWlanProfileStore@@EA; CWlanProfileStore * CSingletonPtr<CWlanProfileStore>::s_pInstance
0x180010d96  mov     rax, [rcx]
0x180010d99  lea     r8, [rbp+3Fh+var_90]
0x180010d9d  lea     rdx, [rsp+120h+var_F0]
0x180010da2  mov     rax, [rax+38h]
0x180010da6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010dab  mov     edi, eax
0x180010dad  test    eax, eax
0x180010daf  jns     short loc_180010DE2
0x180010db1  lea     rcx, [rbp+3Fh+var_90]; this
0x180010db5  call    ??1CProfile@@UEAA@XZ; CProfile::~CProfile(void)
0x180010dba  nop
0x180010dbb  lea     rcx, [rsp+120h+var_D8]
0x180010dc0  call    ??1?$CAtlArray@VCAdapter@@V?$CElementTraits@VCAdapter@@@ATL@@@ATL@@QEAA@XZ; ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::~CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>(void)
0x180010dc5  nop
0x180010dc6  lea     rcx, [rsp+120h+var_F0]; this
0x180010dcb  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x180010dd0  nop
0x180010dd1  lea     rcx, [rsp+120h+lpsz]; this
0x180010dd6  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x180010ddb  mov     ebx, edi
0x180010ddd  jmp     loc_180010ECB
0x180010de2  mov     ecx, 838h; cb
0x180010de7  call    cs:__imp_CoTaskMemAlloc
0x180010ded  mov     rbx, rax
0x180010df0  test    rax, rax
0x180010df3  jnz     short loc_180010E29
0x180010df5  lea     rcx, [rbp+3Fh+var_90]; this
0x180010df9  call    ??1CProfile@@UEAA@XZ; CProfile::~CProfile(void)
0x180010dfe  nop
0x180010dff  lea     rcx, [rsp+120h+var_D8]
0x180010e04  call    ??1?$CAtlArray@VCAdapter@@V?$CElementTraits@VCAdapter@@@ATL@@@ATL@@QEAA@XZ; ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::~CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>(void)
0x180010e09  nop
0x180010e0a  lea     rcx, [rsp+120h+var_F0]; this
0x180010e0f  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x180010e14  nop
0x180010e15  lea     rcx, [rsp+120h+lpsz]; this
0x180010e1a  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x180010e1f  mov     ebx, 8007000Eh
0x180010e24  jmp     loc_180010ECB
0x180010e29  mov     word ptr [rax], 836h
0x180010e2e  lea     rdx, [rax+2]; struct WPLDATA *
0x180010e32  lea     rcx, [rbp+3Fh+var_90]; struct CProfile *
0x180010e36  call    ?ProfileToStruct@@YAXAEBVCProfile@@AEAUWPLDATA@@@Z; ProfileToStruct(CProfile const &,WPLDATA &)
0x180010e3b  xor     eax, eax
0x180010e3d  mov     [rbx+836h], ax
0x180010e44  mov     [rsi], rbx
0x180010e47  test    r15, r15
0x180010e4a  jz      short loc_180010E6D
0x180010e4c  mov     qword ptr [rbp+3Fh+Buf2], rbx
0x180010e50  mov     rax, [r14]
0x180010e53  mov     r9, r15
0x180010e56  lea     r8, [rbp+3Fh+Buf2]
0x180010e5a  mov     edx, 1
0x180010e5f  mov     rcx, r14
0x180010e62  mov     rax, [rax+48h]
0x180010e66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e6b  mov     edi, eax
0x180010e6d  lea     rcx, [rbp+3Fh+var_90]; this
0x180010e71  call    ??1CProfile@@UEAA@XZ; CProfile::~CProfile(void)
0x180010e76  nop
0x180010e77  lea     rcx, [rsp+120h+var_D8]
0x180010e7c  call    ??1?$CAtlArray@VCAdapter@@V?$CElementTraits@VCAdapter@@@ATL@@@ATL@@QEAA@XZ; ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::~CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>(void)
0x180010e81  nop
0x180010e82  lea     rcx, [rsp+120h+var_F0]; this
0x180010e87  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x180010e8c  nop
0x180010e8d  lea     rcx, [rsp+120h+lpsz]; this
0x180010e92  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x180010e97  nop
0x180010e98  lea     rcx, [rsp+120h+Str]; this
0x180010e9d  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x180010ea2  mov     eax, edi
0x180010ea4  jmp     short loc_180010EDE
0x180010ea6  lea     rcx, [rsp+120h+var_D8]
0x180010eab  call    ??1?$CAtlArray@VCAdapter@@V?$CElementTraits@VCAdapter@@@ATL@@@ATL@@QEAA@XZ; ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::~CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>(void)
0x180010eb0  nop
0x180010eb1  lea     rcx, [rsp+120h+var_F0]; this
0x180010eb6  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x180010ebb  nop
0x180010ebc  lea     rcx, [rsp+120h+lpsz]; this
0x180010ec1  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x180010ec6  mov     ebx, 80070057h
0x180010ecb  lea     rcx, [rsp+120h+Str]; this
0x180010ed0  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x180010ed5  mov     eax, ebx
0x180010ed7  jmp     short loc_180010EDE
0x180010ed9  mov     eax, 80070057h
0x180010ede  mov     rcx, [rbp+3Fh+var_30]
0x180010ee2  xor     rcx, rsp; StackCookie
0x180010ee5  call    __security_check_cookie
0x180010eea  mov     rbx, [rsp+120h+arg_8]
0x180010ef2  add     rsp, 100h
0x180010ef9  pop     r15
0x180010efb  pop     r14
0x180010efd  pop     rdi
0x180010efe  pop     rsi
0x180010eff  pop     rbp
0x180010f00  retn
```
