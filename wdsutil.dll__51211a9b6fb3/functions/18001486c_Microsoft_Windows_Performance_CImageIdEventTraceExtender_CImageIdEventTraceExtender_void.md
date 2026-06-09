# Microsoft::Windows::Performance::CImageIdEventTraceExtender::CImageIdEventTraceExtender(void)

- ea: `0x18001486c`
- end: `0x180014f86`
- name: `??0CImageIdEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ`
- size: `1818`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CImageIdEventTraceExtender *__hidden this)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180018c2c`

## callees

- `0x1800085b8`
- `0x18000a89c`
- `0x18000aadc`
- `0x18000b87c`
- `0x18000b92c`
- `0x18000dd14`
- `0x18000e390`
- `0x1800147d4`
- `0x18001486c`
- `0x1800158c4`
- `0x1800182e4`
- `0x1800185b0`
- `0x180018660`
- `0x180019098`
- `0x1800196b8`
- `0x18001a228`
- `0x18001b0c0`
- `0x18001ca30`
- `0x18001cbd0`
- `0x18001cc1c`
- `0x18001cc68`
- `0x18001ccb4`
- `0x1800319f0`
- `0x180034010`

## import_xrefs

- `msvcrt!free` at `0x180014c6c`
- `msvcrt!free` at `0x180014cad`
- `msvcrt!free` at `0x180014c6c`
- `msvcrt!free` at `0x180014cad`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180014c7d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180014c93`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180014c7d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180014c93`
- `KERNEL32!GetLastError` at `0x180014f45`
- `KERNEL32!GetLastError` at `0x180014f45`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x180014ccb`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x180014ccb`
- `KERNEL32!GetFullPathNameW` at `0x180014d55`
- `KERNEL32!GetFullPathNameW` at `0x180014dd1`
- `KERNEL32!GetFullPathNameW` at `0x180014d55`
- `KERNEL32!GetFullPathNameW` at `0x180014dd1`

## string_xrefs

- `0x180014aaa`: `XPERF_EmbeddedPdbPath`
- `0x180014aee`: `_NT_SYMBOL_PATH`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
Microsoft::Windows::Performance::CImageIdEventTraceExtender *__fastcall Microsoft::Windows::Performance::CImageIdEventTraceExtender::CImageIdEventTraceExtender(
        Microsoft::Windows::Performance::CImageIdEventTraceExtender *this)
{
  __int64 v2; // rcx
  LPCWSTR *v3; // rdi
  unsigned int v4; // edx
  __int64 v5; // r8
  __int64 v6; // rax
  int v7; // ebx
  char *v8; // rdx
  _QWORD *v9; // rdx
  unsigned __int64 v10; // rax
  _QWORD *v11; // rdx
  DWORD FullPathNameW; // eax
  DWORD v13; // esi
  __int64 v14; // rax
  WCHAR *v15; // rbx
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rcx
  _QWORD *v20; // rdx
  signed int LastError; // eax
  __int64 v22; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR *v23; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v24; // [rsp+40h] [rbp-C0h] BYREF
  volatile signed __int32 *v25; // [rsp+48h] [rbp-B8h] BYREF
  int v26; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v27; // [rsp+58h] [rbp-A8h]
  __int64 v28; // [rsp+60h] [rbp-A0h]
  void *v29; // [rsp+68h] [rbp-98h]
  _QWORD *v30; // [rsp+70h] [rbp-90h]
  void *Block; // [rsp+78h] [rbp-88h] BYREF
  __int128 v32; // [rsp+80h] [rbp-80h]
  int v33; // [rsp+90h] [rbp-70h]
  __int64 v34; // [rsp+98h] [rbp-68h]
  int v35; // [rsp+A0h] [rbp-60h] BYREF
  void *v36[2]; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B8h] [rbp-48h]
  int v38; // [rsp+C0h] [rbp-40h]
  __int64 v39; // [rsp+C8h] [rbp-38h]
  int v40; // [rsp+D0h] [rbp-30h]
  __int64 v41; // [rsp+D8h] [rbp-28h]
  Microsoft::Windows::Performance::CImageIdEventTraceExtender *v42; // [rsp+E0h] [rbp-20h]
  WCHAR Buffer[264]; // [rsp+F0h] [rbp-10h] BYREF

  v41 = -2;
  v42 = this;
  *((_DWORD *)this + 6) = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *(_QWORD *)this = &Microsoft::Windows::Performance::CImageIdEventTraceExtender::`vftable';
  *((_DWORD *)this + 8) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_DWORD *)this + 12) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 17) = 7;
  *((_QWORD *)this + 16) = 0;
  *((_WORD *)this + 56) = 0;
  *((_QWORD *)this + 21) = 7;
  *((_QWORD *)this + 20) = 0;
  *((_WORD *)this + 72) = 0;
  *((_BYTE *)this + 176) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 24) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_WORD *)this + 100) = 0;
  *((_BYTE *)this + 202) = 0;
  v25 = (volatile signed __int32 *)((char *)this + 208);
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_QWORD *)this + 26) = std::_List_alloc<0,std::_List_base_types<Microsoft::Windows::Performance::CCvDDCache::CCvDD>>::_Buynode0(
                             v2,
                             0,
                             0);
  *((_QWORD *)this + 28) = 0;
  *((_QWORD *)this + 29) = 0;
  *((_QWORD *)this + 28) = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<unsigned long const,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>>::_Buyheadnode();
  *((_QWORD *)this + 30) = 0;
  *((_QWORD *)this + 31) = 0;
  *((_QWORD *)this + 30) = std::_Tree_alloc<0,std::_Tree_base_types<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>>>::_Buyheadnode();
  *((_QWORD *)this + 32) = 0;
  *((_QWORD *)this + 33) = 0;
  *((_QWORD *)this + 32) = std::_Tree_alloc<0,std::_Tree_base_types<unsigned __int64>>::_Buyheadnode();
  *((_QWORD *)this + 34) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 35) = 0;
  *((_DWORD *)this + 72) = 0;
  *((_BYTE *)this + 296) = 0;
  *((_QWORD *)this + 38) = 0;
  *((_QWORD *)this + 39) = 0;
  *((_QWORD *)this + 40) = 0;
  v3 = (LPCWSTR *)((char *)this + 328);
  *((_QWORD *)this + 41) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 42) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 43) = 0;
  *((_QWORD *)this + 44) = 0;
  *((_QWORD *)this + 45) = 0;
  *((_QWORD *)this + 46) = 0;
  Microsoft::Windows::Performance::CErrorEvent::CErrorEvent(
    (Microsoft::Windows::Performance::CImageIdEventTraceExtender *)((char *)this + 376),
    v4);
  if ( !(unsigned __int8)ATL::CAutoVectorPtr<_CVDD>::Allocate((char *)this + 344, 2)
    || !(unsigned __int8)ATL::CAutoVectorPtr<unsigned long>::Allocate((char *)this + 352, 2)
    || !(unsigned __int8)ATL::CAutoVectorPtr<unsigned __int64>::Allocate((char *)this + 360, 2) )
  {
    ATL::AtlThrowImpl(-2147024882);
  }
  *((_DWORD *)this + 92) = 2;
  if ( !(unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::GetEnvironmentVariableW(
                        (char *)this + 328,
                        L"XPERF_EmbeddedPdbPath")
    || !*((_DWORD *)*v3 - 4) )
  {
    v22 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
    if ( (unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::GetEnvironmentVariableW(
                         &v22,
                         L"_NT_SYMBOL_PATH") )
    {
      *(_OWORD *)v36 = 0;
      v37 = 0;
      v38 = 0;
      v39 = 0;
      v40 = 1;
      v35 = 0;
      if ( (unsigned int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Parse(&v35) )
        ATL::AtlThrowImpl(-2147024882);
      v29 = 0;
      v30 = 0;
      Block = 0;
      v32 = 0;
      v33 = 0;
      v26 = 0;
      v34 = 0;
      if ( (unsigned __int8)ATL::CAtlArray<void *,ATL::CElementTraits<void *>>::GrowBuffer(&Block, 256) )
      {
        ATL::CAtlArray<void *,ATL::CElementTraits<void *>>::CallConstructors();
        *(_QWORD *)&v32 = 256;
      }
      v27 = 0;
      v28 = 0;
      LODWORD(v23) = 0;
      v24 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
      while ( 1 )
      {
        v6 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
               &v22,
               &v25,
               v5,
               &v23);
        v7 = *(_DWORD *)(*(_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
                                      &v24,
                                      v6)
                       - 16LL);
        v8 = (char *)(v25 - 6);
        if ( _InterlockedDecrement(v25 - 2) <= 0 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v8 + 8LL))(*(_QWORD *)v8);
        if ( !v7 )
          break;
        if ( (unsigned int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Match(&v35, v24, &v26, 0) )
        {
          if ( !v26 )
            ATL::AtlThrowImpl(-2147467259);
          ATL::CSimpleStringT<unsigned short,0>::SetString((char *)this + 328, *v30, (__int64)(v30[1] - *v30) >> 1);
          break;
        }
      }
      v9 = (_QWORD *)(v24 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v24 - 24 + 16)) <= 0 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v9 + 8LL))(*v9);
      if ( Block )
        free(Block);
      operator delete[](v30);
      v30 = 0;
      operator delete[](v29);
      v29 = 0;
      if ( v36[0] )
        free(v36[0]);
    }
    if ( !*((_DWORD *)*v3 - 4) )
    {
      if ( !GetSystemWindowsDirectoryW(Buffer, 0x105u) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        ATL::AtlThrowImpl(LastError);
      }
      v10 = -1;
      do
        ++v10;
      while ( Buffer[v10] );
      if ( v10 < 2 || Buffer[1] != 58 )
        ATL::AtlThrowImpl(-2147418113);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        (char *)this + 328,
        L"%wc:\\Symbols",
        Buffer[0]);
    }
    v11 = (_QWORD *)(v22 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v22 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 8LL))(*v11);
  }
  if ( *((_DWORD *)*v3 - 4) )
  {
    FullPathNameW = GetFullPathNameW(*v3, 0, 0, 0);
    if ( FullPathNameW )
    {
      v13 = FullPathNameW + 1;
      v14 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
      v15 = (WCHAR *)(v14 + 24);
      v23 = (WCHAR *)(v14 + 24);
      if ( (((*(_DWORD *)(v14 + 12) - v13) | (1 - *(_DWORD *)(v14 + 16))) & 0x80000000) != 0 )
      {
        ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&v23, v13);
        v15 = v23;
      }
      if ( *((int *)v15 - 2) > 1 )
      {
        ATL::CSimpleStringT<unsigned short,0>::Fork(&v23, *((unsigned int *)v15 - 4));
        v15 = v23;
      }
      if ( !GetFullPathNameW(*v3, v13, v15, 0) )
        goto LABEL_39;
      if ( v15 )
      {
        v17 = -1;
        do
          ++v17;
        while ( v15[v17] );
        if ( (int)v17 < 0 )
          goto LABEL_55;
      }
      else
      {
        LODWORD(v17) = 0;
      }
      if ( (int)v17 <= *((_DWORD *)v15 - 3) )
      {
        *((_DWORD *)v15 - 4) = v17;
        v15[(unsigned int)v17] = 0;
        if ( *((int *)v15 - 4) >= 0 )
        {
          if ( *v15 != 92 )
          {
            v18 = *((_QWORD *)v15 - 3);
            if ( !v18 || (v19 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 32LL))(v18)) == 0 )
            {
              v19 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[4])(&ATL::g_strmgr);
              if ( !v19 )
                ATL::AtlThrowImpl(-2147467259);
            }
            v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 24LL))(v19) + 24;
            ATL::CSimpleStringT<unsigned short,0>::Concatenate(&v22, L"\\\\?\\", 4, v15, *((_DWORD *)v15 - 4));
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
              (char *)this + 328,
              &v22);
            v20 = (_QWORD *)(v22 - 24);
            if ( _InterlockedDecrement((volatile signed __int32 *)(v22 - 24 + 16)) <= 0 )
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v20 + 8LL))(*v20);
          }
LABEL_39:
          if ( _InterlockedDecrement((volatile signed __int32 *)v15 - 2) <= 0 )
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v15 - 3) + 8LL))(*((_QWORD *)v15 - 3));
          return this;
        }
      }
LABEL_55:
      ATL::AtlThrowImpl(-2147024809);
    }
  }
  return this;
}

```

## disassembly

```asm
0x18001486c  push    rbp
0x18001486e  push    rbx
0x18001486f  push    rsi
0x180014870  push    rdi
0x180014871  push    r12
0x180014873  push    r13
0x180014875  push    r14
0x180014877  push    r15
0x180014879  lea     rbp, [rsp-218h]
0x180014881  sub     rsp, 318h
0x180014888  mov     [rbp+250h+var_278], 0FFFFFFFFFFFFFFFEh
0x180014890  mov     rax, cs:__security_cookie
0x180014897  xor     rax, rsp
0x18001489a  mov     [rbp+250h+var_50], rax
0x1800148a1  mov     r14, rcx
0x1800148a4  mov     [rbp+250h+var_270], rcx
0x1800148a8  xor     r12d, r12d
0x1800148ab  mov     [rcx+18h], r12d
0x1800148af  mov     [rcx+8], r12
0x1800148b3  mov     [rcx+10h], r12
0x1800148b7  lea     rax, ??_7CImageIdEventTraceExtender@Performance@Windows@Microsoft@@6B@; const Microsoft::Windows::Performance::CImageIdEventTraceExtender::`vftable'
0x1800148be  mov     [rcx], rax
0x1800148c1  mov     [rcx+20h], r12d
0x1800148c5  mov     [rcx+28h], r12
0x1800148c9  mov     [rcx+30h], r12d
0x1800148cd  mov     [rcx+38h], r12
0x1800148d1  mov     [rcx+40h], r12
0x1800148d5  mov     [rcx+48h], r12
0x1800148d9  mov     [rcx+50h], r12
0x1800148dd  mov     [rcx+58h], r12
0x1800148e1  mov     [rcx+60h], r12
0x1800148e5  mov     [rcx+68h], r12
0x1800148e9  lea     ecx, [r12+7]
0x1800148ee  mov     [r14+88h], rcx
0x1800148f5  mov     [r14+80h], r12
0x1800148fc  mov     [r14+70h], r12w
0x180014901  mov     [r14+0A8h], rcx
0x180014908  mov     [r14+0A0h], r12
0x18001490f  mov     [r14+90h], r12w
0x180014917  mov     [r14+0B0h], r12b
0x18001491e  mov     [r14+0B8h], r12
0x180014925  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001492c  lea     rsi, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180014933  mov     rcx, rsi
0x180014936  mov     rax, [rax+18h]
0x18001493a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001493f  add     rax, 18h
0x180014943  mov     [r14+0C0h], rax
0x18001494a  mov     [r14+0C8h], r12w
0x180014952  mov     [r14+0CAh], r12b
0x180014959  lea     rdi, [r14+0D0h]
0x180014960  mov     [rsp+350h+var_308], rdi
0x180014965  mov     [rdi], r12
0x180014968  mov     [rdi+8], r12
0x18001496c  xor     r8d, r8d
0x18001496f  xor     edx, edx
0x180014971  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@V?$allocator@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAPEAU?$_List_node@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<Microsoft::Windows::Performance::CCvDDCache::CCvDD>>::_Buynode0(std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *> *,std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *> *)
0x180014976  mov     [rdi], rax
0x180014979  mov     [rdi+10h], r12
0x18001497d  mov     [rdi+18h], r12
0x180014981  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>>::_Buyheadnode(void)
0x180014986  mov     [rdi+10h], rax
0x18001498a  mov     [rdi+20h], r12
0x18001498e  mov     [rdi+28h], r12
0x180014992  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@V?$allocator@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>>>::_Buyheadnode(void)
0x180014997  mov     [rdi+20h], rax
0x18001499b  mov     [rdi+30h], r12
0x18001499f  mov     [rdi+38h], r12
0x1800149a3  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@_KV?$allocator@_K@std@@@std@@@std@@QEAAPEAU?$_Tree_node@_KPEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<unsigned __int64>>::_Buyheadnode(void)
0x1800149a8  mov     [rdi+30h], rax
0x1800149ac  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800149b3  mov     rcx, rsi
0x1800149b6  mov     rax, [rax+18h]
0x1800149ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149bf  add     rax, 18h
0x1800149c3  mov     [r14+110h], rax
0x1800149ca  mov     [r14+118h], r12
0x1800149d1  mov     [r14+120h], r12d
0x1800149d8  mov     [r14+128h], r12b
0x1800149df  mov     [r14+130h], r12
0x1800149e6  mov     [r14+138h], r12
0x1800149ed  mov     [r14+140h], r12
0x1800149f4  lea     rdi, [r14+148h]
0x1800149fb  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180014a02  mov     rcx, rsi
0x180014a05  mov     rax, [rax+18h]
0x180014a09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a0e  add     rax, 18h
0x180014a12  mov     [rdi], rax
0x180014a15  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180014a1c  mov     rcx, rsi
0x180014a1f  mov     rax, [rax+18h]
0x180014a23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a28  add     rax, 18h
0x180014a2c  mov     [r14+150h], rax
0x180014a33  lea     rbx, [r14+158h]
0x180014a3a  mov     [rbx], r12
0x180014a3d  lea     rsi, [r14+160h]
0x180014a44  mov     [rsi], r12
0x180014a47  lea     r15, [r14+168h]
0x180014a4e  mov     [r15], r12
0x180014a51  mov     [r14+170h], r12
0x180014a58  lea     rcx, [r14+178h]; this
0x180014a5f  call    ??0CErrorEvent@Performance@Windows@Microsoft@@QEAA@K@Z; Microsoft::Windows::Performance::CErrorEvent::CErrorEvent(ulong)
0x180014a64  nop
0x180014a65  lea     r13d, [r12+2]
0x180014a6a  mov     edx, r13d
0x180014a6d  mov     rcx, rbx
0x180014a70  call    ?Allocate@?$CAutoVectorPtr@T_CVDD@@@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<_CVDD>::Allocate(unsigned __int64)
0x180014a75  test    al, al
0x180014a77  jz      loc_180014F2F
0x180014a7d  mov     edx, r13d
0x180014a80  mov     rcx, rsi
0x180014a83  call    ?Allocate@?$CAutoVectorPtr@K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<ulong>::Allocate(unsigned __int64)
0x180014a88  test    al, al
0x180014a8a  jz      loc_180014F2F
0x180014a90  mov     edx, r13d
0x180014a93  mov     rcx, r15
0x180014a96  call    ?Allocate@?$CAutoVectorPtr@_K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<unsigned __int64>::Allocate(unsigned __int64)
0x180014a9b  test    al, al
0x180014a9d  jz      loc_180014F2F
0x180014aa3  mov     [r14+170h], r13d
0x180014aaa  lea     rdx, aXperfEmbeddedp; "XPERF_EmbeddedPdbPath"
0x180014ab1  mov     rcx, rdi
0x180014ab4  call    ?GetEnvironmentVariableW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::GetEnvironmentVariableW(ushort const *)
0x180014ab9  or      r15, 0FFFFFFFFFFFFFFFFh
0x180014abd  test    eax, eax
0x180014abf  jz      short loc_180014ACE
0x180014ac1  mov     rax, [rdi]
0x180014ac4  cmp     [rax-10h], r12d
0x180014ac8  jnz     loc_180014D40
0x180014ace  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180014ad5  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180014adc  mov     rax, [rax+18h]
0x180014ae0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ae5  add     rax, 18h
0x180014ae9  mov     [rsp+350h+var_320], rax
0x180014aee  lea     rdx, aNtSymbolPath; "_NT_SYMBOL_PATH"
0x180014af5  lea     rcx, [rsp+350h+var_320]
0x180014afa  call    ?GetEnvironmentVariableW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::GetEnvironmentVariableW(ushort const *)
0x180014aff  test    eax, eax
0x180014b01  jz      loc_180014CB9
0x180014b07  xorps   xmm0, xmm0
0x180014b0a  movdqu  xmmword ptr [rbp+250h+var_2A8], xmm0
0x180014b0f  mov     [rbp+250h+var_298], r12
0x180014b13  mov     [rbp+250h+var_290], r12d
0x180014b17  mov     [rbp+250h+var_288], r12
0x180014b1b  mov     [rbp+250h+var_280], 1
0x180014b22  mov     [rbp+250h+var_2B0], r12d
0x180014b26  lea     rcx, [rbp+250h+var_2B0]
0x180014b2a  call    ?Parse@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@QEAA?AW4REParseError@2@PEBGH@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Parse(ushort const *,int)
0x180014b2f  test    eax, eax
0x180014b31  jnz     loc_180014F3A
0x180014b37  mov     [rsp+350h+var_2E8], r12
0x180014b3c  mov     [rsp+350h+var_2E0], r12
0x180014b41  mov     [rsp+350h+Block], r12
0x180014b46  xorps   xmm0, xmm0
0x180014b49  movdqa  [rbp+250h+var_2D0], xmm0
0x180014b4e  mov     [rbp+250h+var_2C0], r12d
0x180014b52  mov     [rsp+350h+var_300], r12d
0x180014b57  mov     [rbp+250h+var_2B8], r12
0x180014b5b  mov     ebx, 100h
0x180014b60  mov     edx, ebx
0x180014b62  lea     rcx, [rsp+350h+Block]
0x180014b67  call    ?GrowBuffer@?$CAtlArray@PEAXV?$CElementTraits@PEAX@ATL@@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<void *,ATL::CElementTraits<void *>>::GrowBuffer(unsigned __int64)
0x180014b6c  test    al, al
0x180014b6e  jz      short loc_180014B79
0x180014b70  call    ?CallConstructors@?$CAtlArray@PEAXV?$CElementTraits@PEAX@ATL@@@ATL@@CAXPEAPEAX_K@Z; ATL::CAtlArray<void *,ATL::CElementTraits<void *>>::CallConstructors(void * *,unsigned __int64)
0x180014b75  mov     qword ptr [rbp+250h+var_2D0], rbx
0x180014b79  mov     [rsp+350h+var_2F8], r12
0x180014b7e  mov     [rsp+350h+var_2F0], r12
0x180014b83  mov     dword ptr [rsp+350h+var_318], r12d
0x180014b88  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180014b8f  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180014b96  mov     rax, [rax+18h]
0x180014b9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b9f  add     rax, 18h
0x180014ba3  mov     [rsp+350h+var_310], rax
0x180014ba8  lea     r9, [rsp+350h+var_318]
0x180014bad  lea     rdx, [rsp+350h+var_308]
0x180014bb2  lea     rcx, [rsp+350h+var_320]
0x180014bb7  call    ?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Tokenize(ushort const *,int &)
0x180014bbc  mov     rdx, rax
0x180014bbf  lea     rcx, [rsp+350h+var_310]
0x180014bc4  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180014bc9  mov     rcx, [rax]
0x180014bcc  mov     ebx, [rcx-10h]
0x180014bcf  mov     rdx, [rsp+350h+var_308]
0x180014bd4  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180014bd8  mov     eax, r15d
0x180014bdb  lock xadd [rdx+10h], eax
0x180014be0  add     eax, r15d
0x180014be3  test    eax, eax
0x180014be5  jg      short loc_180014BF6
0x180014be7  mov     rcx, [rdx]
0x180014bea  mov     rax, [rcx]
0x180014bed  mov     rax, [rax+8]
0x180014bf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014bf6  test    ebx, ebx
0x180014bf8  jz      short loc_180014C3A
0x180014bfa  xor     r9d, r9d
0x180014bfd  lea     r8, [rsp+350h+var_300]
0x180014c02  mov     rdx, [rsp+350h+var_310]
0x180014c07  lea     rcx, [rbp+250h+var_2B0]
0x180014c0b  call    ?Match@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@QEAAHPEBGPEAV?$CAtlREMatchContext@VCAtlRECharTraitsW@ATL@@@2@PEAPEBG@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Match(ushort const *,ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW> *,ushort const * *)
0x180014c10  test    eax, eax
0x180014c12  jz      short loc_180014BA8
0x180014c14  cmp     [rsp+350h+var_300], r12d
0x180014c19  jbe     loc_180014F65
0x180014c1f  mov     rax, [rsp+350h+var_2E0]
0x180014c24  mov     r8, [rax+8]
0x180014c28  sub     r8, [rax]
0x180014c2b  sar     r8, 1
0x180014c2e  mov     rdx, [rax]
0x180014c31  mov     rcx, rdi
0x180014c34  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180014c39  nop
0x180014c3a  mov     rdx, [rsp+350h+var_310]
0x180014c3f  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180014c43  mov     eax, r15d
0x180014c46  lock xadd [rdx+10h], eax
0x180014c4b  add     eax, r15d
0x180014c4e  test    eax, eax
0x180014c50  jg      short loc_180014C62
0x180014c52  mov     rcx, [rdx]
0x180014c55  mov     rax, [rcx]
0x180014c58  mov     rax, [rax+8]
0x180014c5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c61  nop
0x180014c62  mov     rcx, [rsp+350h+Block]; Block
0x180014c67  test    rcx, rcx
0x180014c6a  jz      short loc_180014C78
0x180014c6c  call    cs:__imp_free
0x180014c73  nop     dword ptr [rax+rax+00h]
0x180014c78  mov     rcx, [rsp+350h+var_2E0]
0x180014c7d  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180014c84  nop     dword ptr [rax+rax+00h]
0x180014c89  mov     [rsp+350h+var_2E0], r12
0x180014c8e  mov     rcx, [rsp+350h+var_2E8]
0x180014c93  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180014c9a  nop     dword ptr [rax+rax+00h]
0x180014c9f  mov     [rsp+350h+var_2E8], r12
0x180014ca4  mov     rcx, [rbp+250h+var_2A8]; Block
0x180014ca8  test    rcx, rcx
0x180014cab  jz      short loc_180014CB9
0x180014cad  call    cs:__imp_free
0x180014cb4  nop     dword ptr [rax+rax+00h]
0x180014cb9  mov     rax, [rdi]
0x180014cbc  cmp     [rax-10h], r12d
0x180014cc0  jnz     short loc_180014D19
0x180014cc2  mov     edx, 105h; uSize
0x180014cc7  lea     rcx, [rbp+250h+Buffer]; lpBuffer
0x180014ccb  call    cs:__imp_GetSystemWindowsDirectoryW
0x180014cd2  nop     dword ptr [rax+rax+00h]
0x180014cd7  test    eax, eax
0x180014cd9  jz      loc_180014F45
0x180014cdf  lea     rcx, [rbp+250h+Buffer]
0x180014ce3  mov     rax, r15
0x180014ce6  inc     rax
0x180014ce9  cmp     [rcx+rax*2], r12w
0x180014cee  jnz     short loc_180014CE6
0x180014cf0  cmp     rax, r13
0x180014cf3  jb      loc_180014F70
0x180014cf9  cmp     [rbp+250h+var_25E], 3Ah ; ':'
0x180014cfe  jnz     loc_180014F70
0x180014d04  movzx   r8d, [rbp+250h+Buffer]
0x180014d09  lea     rdx, aWcSymbols; "%wc:\\Symbols"
0x180014d10  mov     rcx, rdi
0x180014d13  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180014d18  nop
0x180014d19  mov     rdx, [rsp+350h+var_320]
0x180014d1e  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180014d22  mov     eax, r15d
0x180014d25  lock xadd [rdx+10h], eax
0x180014d2a  add     eax, r15d
0x180014d2d  test    eax, eax
0x180014d2f  jg      short loc_180014D40
0x180014d31  mov     rcx, [rdx]
0x180014d34  mov     rax, [rcx]
0x180014d37  mov     rax, [rax+8]
0x180014d3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d40  mov     rcx, [rdi]; lpFileName
0x180014d43  cmp     [rcx-10h], r12d
0x180014d47  jz      loc_180014E04
0x180014d4d  xor     r9d, r9d; lpFilePart
0x180014d50  xor     r8d, r8d; lpBuffer
0x180014d53  xor     edx, edx; nBufferLength
0x180014d55  call    cs:__imp_GetFullPathNameW
0x180014d5c  nop     dword ptr [rax+rax+00h]
0x180014d61  test    eax, eax
0x180014d63  jz      loc_180014E04
0x180014d69  lea     esi, [rax+1]
0x180014d6c  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180014d73  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180014d7a  mov     rax, [rax+18h]
0x180014d7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d83  lea     rbx, [rax+18h]
0x180014d87  mov     [rsp+350h+var_318], rbx
0x180014d8c  mov     ecx, 1
0x180014d91  sub     ecx, [rbx-8]
  ... truncated ...
```
