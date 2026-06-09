# DataStoreReader::LoadMostRecentResultsGetStateGetDoc(WinSATData &,__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 &,IXMLDOMDocument2 * *)

- ea: `0x180004e00`
- end: `0x18000535d`
- name: `?LoadMostRecentResultsGetStateGetDoc@DataStoreReader@@KAJAEAUWinSATData@@AEAW4__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002@@PEAPEAUIXMLDOMDocument2@@@Z`
- size: `1373`
- prototype: `__int64 __fastcall(struct WinSATData *, enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 *, struct IXMLDOMDocument2 **)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180004114`

## callees

- `0x180001a34`
- `0x180004a48`
- `0x180004b10`
- `0x180004e00`
- `0x180005370`
- `0x180005394`
- `0x180005570`
- `0x180006148`
- `0x180006580`
- `0x1800071d0`
- `0x18000a3cc`
- `0x18000c5e4`
- `0x180013220`
- `0x180013290`
- `0x180013370`
- `0x180013fa3`
- `0x1800151bb`
- `0x18001ee18`
- `0x18002aa74`
- `0x18002dec0`
- `0x180031010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180004fa7`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000503d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000505d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180004fa7`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000503d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000505d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005095`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000509e`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800050c1`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000516e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005218`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005273`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000529c`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800052a5`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800052e0`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005309`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005312`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005095`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000509e`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800050c1`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000516e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005218`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005273`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000529c`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800052a5`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800052e0`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005309`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005312`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004f9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000506b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004f9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000506b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004f7e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004fb0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004f7e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004fb0`
- `KERNEL32!GetCurrentDirectoryW` at `0x180004f91`
- `KERNEL32!GetCurrentDirectoryW` at `0x180004f91`

## string_xrefs

- `0x180004f02`: `.WinSAT.xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall DataStoreReader::LoadMostRecentResultsGetStateGetDoc(
        struct WinSATData *a1,
        enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 *a2,
        struct IXMLDOMDocument2 **a3)
{
  struct IXMLDOMDocument2 *v5; // rax
  int WinSATDataStoreDir; // ebx
  struct IXMLDOMDocument2 *v7; // rax
  _QWORD *v8; // rax
  __int64 v9; // rcx
  const wchar_t *i; // rax
  _QWORD *v11; // rbx
  __int64 v12; // r14
  _QWORD *v13; // rdi
  WCHAR *v14; // rdx
  WCHAR *v15; // rsi
  WCHAR *v16; // rax
  DWORD LastError; // r14d
  signed int v18; // eax
  __int64 v19; // rcx
  signed int v20; // esi
  bool v21; // zf
  void *v22; // rcx
  __int64 v24; // r8
  __int64 v25; // rcx
  __int64 v26; // rdx
  const unsigned __int16 *v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  int HistoryVersion; // esi
  struct IXMLDOMDocument2 *v31; // rbx
  void *v32; // rcx
  void *v33; // rcx
  __int128 v34; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v35; // [rsp+40h] [rbp-C0h]
  struct IXMLDOMDocument2 *v36; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v37[2]; // [rsp+50h] [rbp-B0h] BYREF
  char pExceptionObject; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD *v39; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v40; // [rsp+68h] [rbp-98h] BYREF
  __int64 v41; // [rsp+70h] [rbp-90h]
  void **v42; // [rsp+80h] [rbp-80h] BYREF
  __int16 v43; // [rsp+88h] [rbp-78h]
  __int64 v44; // [rsp+290h] [rbp+190h]
  __int64 v45; // [rsp+298h] [rbp+198h]
  __int64 v46; // [rsp+2A0h] [rbp+1A0h]
  __int64 v47; // [rsp+2A8h] [rbp+1A8h]
  __int64 v48; // [rsp+2B0h] [rbp+1B0h]
  void **v49; // [rsp+2B8h] [rbp+1B8h]
  __int128 v50; // [rsp+2C0h] [rbp+1C0h]
  __int128 v51; // [rsp+2D0h] [rbp+1D0h]
  __int128 *v52; // [rsp+2E0h] [rbp+1E0h]

  v41 = -2;
  if ( !a1 || !a2 )
    return 2147942487LL;
  memset_0(a1, 0, 0x1A0u);
  *a2 = WINSAT_ASSESSMENT_STATE_MIN;
  v5 = (struct IXMLDOMDocument2 *)operator new(0x28u);
  if ( !v5 )
    std::_Xbad_alloc();
  v36 = v5;
  v39 = mlib::mstring_buf<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::mstring_buf<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
          v5,
          260);
  WinSATDataStoreDir = DataStoreReader::GetWinSATDataStoreDir(&v39);
  if ( WinSATDataStoreDir < 0 )
  {
LABEL_42:
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v39);
    return (unsigned int)WinSATDataStoreDir;
  }
  v34 = 0;
  v35 = 0;
  v7 = (struct IXMLDOMDocument2 *)mlib::mstring_buf<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::operator new();
  v36 = v7;
  if ( v7 )
    v8 = mlib::mstring_buf<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::mstring_buf<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
           v7,
           260);
  else
    v8 = 0;
  *(_QWORD *)v37 = v8;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
    v37,
    L"*%s.Assessment (%s)",
    L"Formal",
    L"*");
  v9 = 0x10000;
  for ( i = L".WinSAT.xml"; ; ++i )
  {
    if ( !v9 )
      throw (mlib::CStringTooBig *)&pExceptionObject;
    if ( !*i )
      break;
    --v9;
  }
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::munge(
    v37,
    0,
    **(_QWORD **)v37);
  v11 = *(_QWORD **)v37;
  v12 = *(_QWORD *)(*(_QWORD *)v37 + 24LL);
  v13 = v39;
  v14 = (WCHAR *)v39[3];
  if ( !v14 || (v15 = 0, !*v14) )
  {
    v16 = (WCHAR *)operator new[](0x208u);
    v15 = v16;
    if ( !v16 )
    {
      SetLastError(8u);
      goto LABEL_24;
    }
    if ( !GetCurrentDirectoryW(0x104u, v16) )
    {
      LastError = GetLastError();
      operator delete[](v15);
      SetLastError(LastError);
      goto LABEL_23;
    }
    v14 = v15;
  }
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v47 = -1;
  v48 = 0;
  v49 = &mlib::FSpecList<unsigned short>::`vftable';
  v50 = 0;
  v51 = 0;
  v43 = 0;
  v42 = &mlib::FileFinder<unsigned short>::`vftable';
  v52 = &v34;
  LastError = mlib::TraverseDirT<unsigned short>::traverse_dir(&v42, v14, v12);
  if ( v15 )
    operator delete[](v15);
  v42 = &mlib::TraverseDirT<unsigned short>::`vftable';
  v49 = &mlib::FSpecList<unsigned short>::`vftable';
  operator delete[](*((void **)&v51 + 1));
LABEL_23:
  if ( !LastError )
  {
    std::_Sort<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>> *,__int64,bool (*)(mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>> const &,mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>> const &)>(
      v34,
      *((_QWORD *)&v34 + 1),
      (__int64)(*((_QWORD *)&v34 + 1) - v34) >> 3);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)v37);
    goto LABEL_36;
  }
LABEL_24:
  v18 = GetLastError();
  v20 = v18;
  if ( v18 > 0 )
    v20 = (unsigned __int16)v18 | 0x80070000;
  v21 = v11[2]-- == 1;
  if ( v21 && v11 )
  {
    v22 = (void *)v11[3];
    if ( v22 )
      operator delete(v22);
    operator delete(v11);
  }
  if ( v20 < 0 )
  {
    if ( (_QWORD)v34 )
    {
      std::vector<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>::_Destroy(
        v19,
        v34,
        *((_QWORD *)&v34 + 1));
      operator delete((void *)v34);
      v34 = 0;
      v35 = 0;
    }
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v39);
    return (unsigned int)v20;
  }
LABEL_36:
  v24 = *((_QWORD *)&v34 + 1);
  v25 = v34;
  if ( *((_QWORD *)&v34 + 1) == (_QWORD)v34 )
  {
    *a2 = WINSAT_ASSESSMENT_STATE_NOT_AVAILABLE;
    if ( v25 )
    {
      v26 = v25;
LABEL_48:
      std::vector<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>::_Destroy(
        v25,
        v26,
        v24);
      operator delete((void *)v34);
      v35 = 0;
      v34 = 0;
      goto LABEL_49;
    }
    goto LABEL_49;
  }
  v36 = 0;
  WinSATDataStoreDir = DataStoreReader::LoadRecentResultsFromFile(v34, a1, &v36);
  if ( WinSATDataStoreDir < 0 )
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v36);
    if ( (_QWORD)v34 )
    {
      std::vector<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>::_Destroy(
        v28,
        v34,
        *((_QWORD *)&v34 + 1));
      operator delete((void *)v34);
      v34 = 0;
      v35 = 0;
    }
    goto LABEL_42;
  }
  v37[0] = 0;
  v40 = 0;
  HistoryVersion = DataStoreReader::GetHistoryVersion(v27, v37);
  v31 = v36;
  if ( HistoryVersion < 0
    || (HistoryVersion = DataStoreReader::GetHistoryValueFromDocument(v36, &v40), HistoryVersion < 0) )
  {
    if ( v31 )
      ((void (__fastcall *)(struct IXMLDOMDocument2 *))v31->lpVtbl->Release)(v31);
    if ( (_QWORD)v34 )
    {
      std::vector<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>::_Destroy(
        v29,
        v34,
        *((_QWORD *)&v34 + 1));
      operator delete((void *)v34);
      v34 = 0;
      v35 = 0;
    }
    v21 = v13[2]-- == 1;
    if ( v21 && v13 )
    {
      v33 = (void *)v13[3];
      if ( v33 )
        operator delete(v33);
      operator delete(v13);
    }
    return (unsigned int)HistoryVersion;
  }
  else
  {
    if ( v37[0] != v40 )
    {
      memset_0(a1, 0, 0x1A0u);
      *a2 = WINSAT_ASSESSMENT_STATE_NOT_AVAILABLE;
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v36);
      v26 = v34;
      if ( (_QWORD)v34 )
      {
        v24 = *((_QWORD *)&v34 + 1);
        goto LABEL_48;
      }
LABEL_49:
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf((__int64)&v39);
      return 0;
    }
    *a2 = WINSAT_ASSESSMENT_STATE_VALID;
    if ( v31 )
      ((void (__fastcall *)(struct IXMLDOMDocument2 *))v31->lpVtbl->Release)(v31);
    if ( (_QWORD)v34 )
    {
      std::vector<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>::_Destroy(
        v29,
        v34,
        *((_QWORD *)&v34 + 1));
      operator delete((void *)v34);
      v34 = 0;
      v35 = 0;
    }
    v21 = v13[2]-- == 1;
    if ( v21 && v13 )
    {
      v32 = (void *)v13[3];
      if ( v32 )
        operator delete(v32);
      operator delete(v13);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x180004e00  push    rbp
0x180004e02  push    rsi
0x180004e03  push    rdi
0x180004e04  push    r12
0x180004e06  push    r13
0x180004e08  push    r14
0x180004e0a  push    r15
0x180004e0c  lea     rbp, [rsp-200h]
0x180004e14  sub     rsp, 300h
0x180004e1b  mov     [rsp+330h+var_2C0], 0FFFFFFFFFFFFFFFEh
0x180004e24  mov     [rsp+330h+arg_10], rbx
0x180004e2c  mov     rax, cs:__security_cookie
0x180004e33  xor     rax, rsp
0x180004e36  mov     [rbp+230h+var_40], rax
0x180004e3d  mov     r12, rdx
0x180004e40  mov     r15, rcx
0x180004e43  test    rcx, rcx
0x180004e46  jz      loc_18000532E
0x180004e4c  test    rdx, rdx
0x180004e4f  jz      loc_18000532E
0x180004e55  xor     edx, edx; Val
0x180004e57  mov     r8d, 1A0h; Size
0x180004e5d  call    memset_0
0x180004e62  xor     r13d, r13d
0x180004e65  mov     [r12], r13d
0x180004e69  mov     ecx, 28h ; '('; Size
0x180004e6e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004e73  test    rax, rax
0x180004e76  jnz     short loc_180004E7E
0x180004e78  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180004e7e  mov     [rsp+330h+var_2E8], rax
0x180004e83  mov     edx, 104h
0x180004e88  mov     rcx, rax
0x180004e8b  call    ??0?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@AEAA@_KAEBV?$allocator@G@std@@@Z; mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64,std::allocator<ushort> const &)
0x180004e90  nop
0x180004e91  mov     [rsp+330h+var_2D0], rax
0x180004e96  lea     rcx, [rsp+330h+var_2D0]
0x180004e9b  call    ?GetWinSATDataStoreDir@DataStoreReader@@SAJAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@Z; DataStoreReader::GetWinSATDataStoreDir(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)
0x180004ea0  mov     ebx, eax
0x180004ea2  test    eax, eax
0x180004ea4  js      loc_180005182
0x180004eaa  xorps   xmm0, xmm0
0x180004ead  movdqu  [rsp+330h+var_300], xmm0
0x180004eb3  mov     [rsp+330h+var_2F0], r13
0x180004eb8  call    ??2?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@CAPEAX_K@Z; mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::operator new(unsigned __int64)
0x180004ebd  mov     [rsp+330h+var_2E8], rax
0x180004ec2  test    rax, rax
0x180004ec5  jz      short loc_180004ED6
0x180004ec7  mov     edx, 104h
0x180004ecc  mov     rcx, rax
0x180004ecf  call    ??0?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@AEAA@_KAEBV?$allocator@G@std@@@Z; mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64,std::allocator<ushort> const &)
0x180004ed4  jmp     short loc_180004ED9
0x180004ed6  mov     rax, r13
0x180004ed9  mov     qword ptr [rsp+330h+var_2E0], rax
0x180004ede  lea     r9, asc_180035914; "*"
0x180004ee5  lea     r8, aFormal; "Formal"
0x180004eec  lea     rdx, aSAssessmentS; "*%s.Assessment (%s)"
0x180004ef3  lea     rcx, [rsp+330h+var_2E0]
0x180004ef8  call    ?spf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXPEBGZZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::spf(ushort const *,...)
0x180004efd  mov     ecx, 10000h
0x180004f02  lea     r9, aWinsatXml; ".WinSAT.xml"
0x180004f09  mov     rax, r9
0x180004f0c  nop     dword ptr [rax+00h]
0x180004f10  test    rcx, rcx
0x180004f13  jz      loc_18000531C
0x180004f19  cmp     word ptr [rax], 0
0x180004f1d  jz      short loc_180004F28
0x180004f1f  add     rax, 2
0x180004f23  dec     rcx
0x180004f26  jmp     short loc_180004F10
0x180004f28  sub     rax, r9
0x180004f2b  sar     rax, 1
0x180004f2e  mov     [rsp+330h+var_310], rax
0x180004f33  mov     r8, qword ptr [rsp+330h+var_2E0]
0x180004f38  mov     r8, [r8]
0x180004f3b  xor     edx, edx
0x180004f3d  lea     rcx, [rsp+330h+var_2E0]
0x180004f42  call    ?munge@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAX_K0PEBG0@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::munge(unsigned __int64,unsigned __int64,ushort const *,unsigned __int64)
0x180004f47  mov     rbx, qword ptr [rsp+330h+var_2E0]
0x180004f4c  mov     r14, [rbx+18h]
0x180004f50  mov     rdi, [rsp+330h+var_2D0]
0x180004f55  mov     rdx, [rdi+18h]
0x180004f59  test    rdx, rdx
0x180004f5c  jz      short loc_180004F67
0x180004f5e  mov     rsi, r13
0x180004f61  cmp     [rdx], r13w
0x180004f65  jnz     short loc_180004FBE
0x180004f67  mov     ecx, 208h; unsigned __int64
0x180004f6c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180004f71  mov     rsi, rax
0x180004f74  test    rax, rax
0x180004f77  jnz     short loc_180004F89
0x180004f79  mov     ecx, 8; dwErrCode
0x180004f7e  call    cs:__imp_SetLastError
0x180004f84  jmp     loc_18000506B
0x180004f89  mov     rdx, rsi; lpBuffer
0x180004f8c  mov     ecx, 104h; nBufferLength
0x180004f91  call    cs:__imp_GetCurrentDirectoryW
0x180004f97  test    eax, eax
0x180004f99  jnz     short loc_180004FBB
0x180004f9b  call    cs:__imp_GetLastError
0x180004fa1  mov     r14d, eax
0x180004fa4  mov     rcx, rsi
0x180004fa7  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180004fad  mov     ecx, r14d; dwErrCode
0x180004fb0  call    cs:__imp_SetLastError
0x180004fb6  jmp     loc_180005066
0x180004fbb  mov     rdx, rsi
0x180004fbe  mov     [rbp+230h+var_A0], r13
0x180004fc5  mov     [rbp+230h+var_98], r13
0x180004fcc  mov     [rbp+230h+var_90], r13
0x180004fd3  mov     [rbp+230h+var_88], 0FFFFFFFFFFFFFFFFh
0x180004fde  mov     [rbp+230h+var_80], r13
0x180004fe5  lea     r13, ??_7?$FSpecList@G@mlib@@6B@; const mlib::FSpecList<ushort>::`vftable'
0x180004fec  mov     [rbp+230h+var_78], r13
0x180004ff3  xorps   xmm0, xmm0
0x180004ff6  movdqa  [rbp+230h+var_70], xmm0
0x180004ffe  xorps   xmm1, xmm1
0x180005001  movdqa  [rbp+230h+var_60], xmm1
0x180005009  xor     eax, eax
0x18000500b  mov     [rbp+230h+var_2A8], ax
0x18000500f  lea     rax, ??_7?$FileFinder@G@mlib@@6B@; const mlib::FileFinder<ushort>::`vftable'
0x180005016  mov     [rbp+230h+var_2B0], rax
0x18000501a  lea     rax, [rsp+330h+var_300]
0x18000501f  mov     [rbp+230h+var_50], rax
0x180005026  mov     r8, r14
0x180005029  lea     rcx, [rbp+230h+var_2B0]
0x18000502d  call    ?traverse_dir@?$TraverseDirT@G@mlib@@QEAAKPEBG0_K_N@Z; mlib::TraverseDirT<ushort>::traverse_dir(ushort const *,ushort const *,unsigned __int64,bool)
0x180005032  mov     r14d, eax
0x180005035  test    rsi, rsi
0x180005038  jz      short loc_180005044
0x18000503a  mov     rcx, rsi
0x18000503d  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180005043  nop
0x180005044  lea     rax, ??_7?$TraverseDirT@G@mlib@@6B@; const mlib::TraverseDirT<ushort>::`vftable'
0x18000504b  mov     [rbp+230h+var_2B0], rax
0x18000504f  mov     [rbp+230h+var_78], r13
0x180005056  mov     rcx, qword ptr [rbp+230h+var_60+8]
0x18000505d  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180005063  xor     r13d, r13d
0x180005066  test    r14d, r14d
0x180005069  jz      short loc_1800050E6
0x18000506b  call    cs:__imp_GetLastError
0x180005071  mov     esi, eax
0x180005073  test    eax, eax
0x180005075  jle     short loc_180005080
0x180005077  movzx   esi, ax
0x18000507a  or      esi, 80070000h
0x180005080  sub     qword ptr [rbx+10h], 1
0x180005085  jnz     short loc_1800050A4
0x180005087  test    rbx, rbx
0x18000508a  jz      short loc_1800050A4
0x18000508c  mov     rcx, [rbx+18h]
0x180005090  test    rcx, rcx
0x180005093  jz      short loc_18000509B
0x180005095  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000509b  mov     rcx, rbx
0x18000509e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800050a4  test    esi, esi
0x1800050a6  jns     short loc_18000510A
0x1800050a8  mov     rdx, qword ptr [rsp+330h+var_300]
0x1800050ad  test    rdx, rdx
0x1800050b0  jz      short loc_1800050D5
0x1800050b2  mov     r8, qword ptr [rsp+330h+var_300+8]
0x1800050b7  call    ?_Destroy@?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@IEAAXPEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0@Z; std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>>::_Destroy(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x1800050bc  mov     rcx, qword ptr [rsp+330h+var_300]
0x1800050c1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800050c7  xorps   xmm0, xmm0
0x1800050ca  movdqu  [rsp+330h+var_300], xmm0
0x1800050d0  mov     [rsp+330h+var_2F0], r13
0x1800050d5  lea     rcx, [rsp+330h+var_2D0]
0x1800050da  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x1800050df  mov     eax, esi
0x1800050e1  jmp     loc_180005333
0x1800050e6  mov     rdx, qword ptr [rsp+330h+var_300+8]
0x1800050eb  mov     rcx, qword ptr [rsp+330h+var_300]
0x1800050f0  mov     r8, rdx
0x1800050f3  sub     r8, rcx
0x1800050f6  sar     r8, 3
0x1800050fa  call    ??$_Sort@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@_JP6A_NAEBV12@0@Z@std@@YAXPEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0_JP6A_NAEBV12@2@Z@Z; std::_Sort<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,__int64,bool (*)(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)>(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,__int64,bool (*)(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &))
0x1800050ff  nop
0x180005100  lea     rcx, [rsp+330h+var_2E0]
0x180005105  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18000510a  mov     r8, qword ptr [rsp+330h+var_300+8]
0x18000510f  mov     rcx, qword ptr [rsp+330h+var_300]
0x180005114  cmp     r8, rcx
0x180005117  jnz     short loc_180005132
0x180005119  mov     dword ptr [r12], 3
0x180005121  test    rcx, rcx
0x180005124  jz      loc_18000522C
0x18000512a  mov     rdx, rcx
0x18000512d  jmp     loc_18000520E
0x180005132  mov     [rsp+330h+var_2E8], r13
0x180005137  lea     r8, [rsp+330h+var_2E8]
0x18000513c  mov     rdx, r15
0x18000513f  call    ?LoadRecentResultsFromFile@DataStoreReader@@KAJAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@AEAUWinSATData@@PEAPEAUIXMLDOMDocument2@@@Z; DataStoreReader::LoadRecentResultsFromFile(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &,WinSATData &,IXMLDOMDocument2 * *)
0x180005144  mov     ebx, eax
0x180005146  test    eax, eax
0x180005148  jns     short loc_180005193
0x18000514a  lea     rcx, [rsp+330h+var_2E8]
0x18000514f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180005154  nop
0x180005155  mov     rdx, qword ptr [rsp+330h+var_300]
0x18000515a  test    rdx, rdx
0x18000515d  jz      short loc_180005182
0x18000515f  mov     r8, qword ptr [rsp+330h+var_300+8]
0x180005164  call    ?_Destroy@?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@IEAAXPEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0@Z; std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>>::_Destroy(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x180005169  mov     rcx, qword ptr [rsp+330h+var_300]
0x18000516e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005174  xorps   xmm0, xmm0
0x180005177  movdqu  [rsp+330h+var_300], xmm0
0x18000517d  mov     [rsp+330h+var_2F0], r13
0x180005182  lea     rcx, [rsp+330h+var_2D0]
0x180005187  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18000518c  mov     eax, ebx
0x18000518e  jmp     loc_180005333
0x180005193  mov     [rsp+330h+var_2E0], r13d
0x180005198  mov     [rsp+330h+var_2C8], r13d
0x18000519d  lea     rdx, [rsp+330h+var_2E0]; unsigned int *
0x1800051a2  call    ?GetHistoryVersion@DataStoreReader@@CAJPEBGAEAK@Z; DataStoreReader::GetHistoryVersion(ushort const *,ulong &)
0x1800051a7  mov     esi, eax
0x1800051a9  mov     rbx, [rsp+330h+var_2E8]
0x1800051ae  test    eax, eax
0x1800051b0  js      loc_1800052B2
0x1800051b6  lea     rdx, [rsp+330h+var_2C8]; unsigned int *
0x1800051bb  mov     rcx, rbx; struct IXMLDOMDocument2 *
0x1800051be  call    ?GetHistoryValueFromDocument@DataStoreReader@@KAJPEAUIXMLDOMDocument2@@AEAK@Z; DataStoreReader::GetHistoryValueFromDocument(IXMLDOMDocument2 *,ulong &)
0x1800051c3  mov     esi, eax
0x1800051c5  test    eax, eax
0x1800051c7  js      loc_1800052B2
0x1800051cd  mov     eax, [rsp+330h+var_2C8]
0x1800051d1  cmp     [rsp+330h+var_2E0], eax
0x1800051d5  setz    al
0x1800051d8  test    al, al
0x1800051da  jnz     short loc_18000523D
0x1800051dc  xor     edx, edx; Val
0x1800051de  mov     r8d, 1A0h; Size
0x1800051e4  mov     rcx, r15; void *
0x1800051e7  call    memset_0
0x1800051ec  mov     dword ptr [r12], 3
0x1800051f4  lea     rcx, [rsp+330h+var_2E8]
0x1800051f9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800051fe  nop
0x1800051ff  mov     rdx, qword ptr [rsp+330h+var_300]
0x180005204  test    rdx, rdx
0x180005207  jz      short loc_18000522C
0x180005209  mov     r8, qword ptr [rsp+330h+var_300+8]
0x18000520e  call    ?_Destroy@?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@IEAAXPEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0@Z; std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>>::_Destroy(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x180005213  mov     rcx, qword ptr [rsp+330h+var_300]
0x180005218  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000521e  xorps   xmm0, xmm0
0x180005221  mov     [rsp+330h+var_2F0], r13
0x180005226  movdqu  [rsp+330h+var_300], xmm0
0x18000522c  lea     rcx, [rsp+330h+var_2D0]
0x180005231  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180005236  xor     eax, eax
0x180005238  jmp     loc_180005333
0x18000523d  mov     dword ptr [r12], 1
0x180005245  test    rbx, rbx
0x180005248  jz      short loc_18000525A
0x18000524a  mov     rax, [rbx]
0x18000524d  mov     rcx, rbx
0x180005250  mov     rax, [rax+10h]
0x180005254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005259  nop
0x18000525a  mov     rdx, qword ptr [rsp+330h+var_300]
0x18000525f  test    rdx, rdx
0x180005262  jz      short loc_180005287
0x180005264  mov     r8, qword ptr [rsp+330h+var_300+8]
0x180005269  call    ?_Destroy@?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@IEAAXPEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0@Z; std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>>::_Destroy(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x18000526e  mov     rcx, qword ptr [rsp+330h+var_300]
0x180005273  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005279  xorps   xmm0, xmm0
0x18000527c  movdqu  [rsp+330h+var_300], xmm0
0x180005282  mov     [rsp+330h+var_2F0], r13
0x180005287  sub     qword ptr [rdi+10h], 1
0x18000528c  jnz     short loc_1800052AB
0x18000528e  test    rdi, rdi
0x180005291  jz      short loc_1800052AB
0x180005293  mov     rcx, [rdi+18h]
0x180005297  test    rcx, rcx
0x18000529a  jz      short loc_1800052A2
0x18000529c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800052a2  mov     rcx, rdi
0x1800052a5  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800052ab  xor     eax, eax
0x1800052ad  jmp     loc_180005333
0x1800052b2  test    rbx, rbx
0x1800052b5  jz      short loc_1800052C7
0x1800052b7  mov     rax, [rbx]
0x1800052ba  mov     rcx, rbx
0x1800052bd  mov     rax, [rax+10h]
0x1800052c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052c6  nop
0x1800052c7  mov     rdx, qword ptr [rsp+330h+var_300]
0x1800052cc  test    rdx, rdx
0x1800052cf  jz      short loc_1800052F4
0x1800052d1  mov     r8, qword ptr [rsp+330h+var_300+8]
0x1800052d6  call    ?_Destroy@?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@IEAAXPEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0@Z; std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>>::_Destroy(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x1800052db  mov     rcx, qword ptr [rsp+330h+var_300]
  ... truncated ...
```
