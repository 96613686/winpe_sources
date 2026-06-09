# Wsp::Facade::FileShareFacade::ShouldDeleteDirectory(void)

- ea: `0x180052148`
- end: `0x18005252d`
- name: `?ShouldDeleteDirectory@FileShareFacade@Facade@Wsp@@AEAA_NXZ`
- size: `997`
- prototype: `char __fastcall(Wsp::Facade::FileShareFacade *this)`
- caller_count: `1`
- callee_count: `21`
- tags: ``

## callers

- `0x180051164`

## callees

- `0x180002a70`
- `0x180005e68`
- `0x18000a6dc`
- `0x18000c284`
- `0x18000dd74`
- `0x180010708`
- `0x180013e24`
- `0x180014630`
- `0x18001e964`
- `0x180025888`
- `0x180047e98`
- `0x1800508e8`
- `0x180050ce4`
- `0x1800513e4`
- `0x180051af0`
- `0x180052148`
- `0x180077acc`
- `0x180077cfc`
- `0x180077d90`
- `0x180078034`
- `0x1800a9010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1800522b1`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1800522b1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall Wsp::Facade::FileShareFacade::ShouldDeleteDirectory(Wsp::Facade::FileShareFacade *this)
{
  int v2; // edi
  __int64 v3; // rax
  char v4; // bl
  const WCHAR *v6; // rax
  __int64 v7; // rcx
  __int64 **v8; // rbx
  __int64 **v9; // r15
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 UniqueId; // rsi
  int v13; // edi
  __int64 v14; // rax
  __int64 v15; // rcx
  bool v16; // si
  __int64 v17; // [rsp+20h] [rbp-668h] BYREF
  __int64 v18; // [rsp+28h] [rbp-660h] BYREF
  int v19; // [rsp+30h] [rbp-658h]
  __int64 v20; // [rsp+38h] [rbp-650h] BYREF
  LPWSTR lpszVolumePathName[3]; // [rsp+40h] [rbp-648h] BYREF
  __int64 ***v22; // [rsp+58h] [rbp-630h] BYREF
  std::_Ref_count_base *v23; // [rsp+60h] [rbp-628h]
  _BYTE v24[32]; // [rsp+68h] [rbp-620h] BYREF
  _BYTE v25[40]; // [rsp+88h] [rbp-600h] BYREF
  _BYTE v26[80]; // [rsp+B0h] [rbp-5D8h] BYREF
  _BYTE v27[32]; // [rsp+100h] [rbp-588h] BYREF
  _BYTE v28[600]; // [rsp+120h] [rbp-568h] BYREF
  _BYTE v29[72]; // [rsp+378h] [rbp-310h] BYREF
  _BYTE v30[672]; // [rsp+3C0h] [rbp-2C8h] BYREF

  v2 = 0;
  v19 = 0;
  (*(void (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)this + 56LL))(*(_QWORD *)this, &v17);
  (*(void (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)this + 32LL))(*(_QWORD *)this, &v18);
  if ( v17 && v18 )
  {
    std::wstring::wstring(v25, L"*");
    cxl::Directory::Directory(v26, v17, v25);
    std::wstring::_Tidy_deallocate(v25);
    cxl::Directory::begin(v26, v28);
    v3 = cxl::Directory::end(v26, v30);
    v4 = std::operator!=<wchar_t>(v29, v3 + 600);
    cxl::DirectoryEntry::~DirectoryEntry((cxl::DirectoryEntry *)v30);
    cxl::DirectoryEntry::~DirectoryEntry((cxl::DirectoryEntry *)v28);
    if ( v4 )
    {
      cxl::Directory::~Directory((cxl::Directory *)v26);
      std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(&v18);
      std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(&v17);
      return 0;
    }
    else
    {
      std::vector<wchar_t>::vector<wchar_t>(lpszVolumePathName, *(_QWORD *)(v17 + 16));
      v6 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v17);
      GetVolumePathNameW(v6, lpszVolumePathName[0], lpszVolumePathName[1] - lpszVolumePathName[0]);
      std::wstring::wstring(v24, lpszVolumePathName[0]);
      std::wstring::append(v24, L"Shares\\");
      std::wstring::append(v24);
      if ( (unsigned __int8)cxl::CaseInsensitive_Equal::operator()(v7, v24, v17) )
      {
        Wsp::Facade::FileShareFacade::Enumerate(&v22, 2);
        if ( v22 )
        {
          v8 = *v22;
          v9 = v22[1];
          while ( v8 != v9 )
          {
            v10 = **v8;
            if ( v10 )
            {
              (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v10 + 56LL))(v10, &v20);
              v11 = v20;
            }
            else
            {
              v11 = 0;
              v20 = 0;
            }
            v2 |= 4u;
            if ( v11 )
            {
              v16 = 0;
              if ( (unsigned __int8)cxl::CaseInsensitive_Equal::operator()(v10, v17, v11) )
              {
                UniqueId = Wsp::Facade::FileShareFacade::GetUniqueId(*v8, v27);
                v13 = v2 | 1;
                v19 = v13;
                v14 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)this + 8LL))(*(_QWORD *)this, v25);
                v2 = v13 | 2;
                v19 = v2;
                if ( !(unsigned __int8)cxl::CaseInsensitive_Equal::operator()(v15, v14, UniqueId) )
                  v16 = 1;
              }
              if ( (v2 & 2) != 0 )
              {
                v2 &= ~2u;
                std::wstring::_Tidy_deallocate(v25);
              }
              if ( (v2 & 1) != 0 )
              {
                v2 &= ~1u;
                std::wstring::_Tidy_deallocate(v27);
              }
              if ( v16 )
              {
                std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(&v20);
                if ( v23 )
                  std::_Ref_count_base::_Decref(v23);
                goto LABEL_6;
              }
            }
            std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(&v20);
            v8 += 2;
          }
        }
        if ( v23 )
          std::_Ref_count_base::_Decref(v23);
        std::wstring::_Tidy_deallocate(v24);
        std::vector<unsigned short>::_Tidy(lpszVolumePathName);
        cxl::Directory::~Directory((cxl::Directory *)v26);
        std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(&v18);
        std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(&v17);
        return 1;
      }
      else
      {
LABEL_6:
        std::wstring::_Tidy_deallocate(v24);
        std::vector<unsigned short>::_Tidy(lpszVolumePathName);
        cxl::Directory::~Directory((cxl::Directory *)v26);
        std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(&v18);
        std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(&v17);
        return 0;
      }
    }
  }
  else
  {
    std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(&v18);
    std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(&v17);
    return 0;
  }
}

```

## disassembly

```asm
0x180052148  mov     [rsp+arg_8], rbx
0x18005214d  mov     [rsp+arg_10], rsi
0x180052152  push    rdi
0x180052153  push    r14
0x180052155  push    r15
0x180052157  sub     rsp, 670h
0x18005215e  mov     rax, cs:__security_cookie
0x180052165  xor     rax, rsp
0x180052168  mov     [rsp+688h+var_28], rax
0x180052170  mov     r14, rcx
0x180052173  xor     edi, edi
0x180052175  mov     [rsp+688h+var_658], edi
0x180052179  mov     rcx, [rcx]
0x18005217c  mov     rax, [rcx]
0x18005217f  lea     rdx, [rsp+688h+var_668]
0x180052184  mov     rax, [rax+38h]
0x180052188  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005218d  nop
0x18005218e  mov     rcx, [r14]
0x180052191  mov     rax, [rcx]
0x180052194  lea     rdx, [rsp+688h+var_660]
0x180052199  mov     rax, [rax+20h]
0x18005219d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800521a2  nop
0x1800521a3  cmp     [rsp+688h+var_668], rdi
0x1800521a8  jz      loc_1800524E8
0x1800521ae  cmp     [rsp+688h+var_660], rdi
0x1800521b3  jz      loc_1800524E8
0x1800521b9  lea     rdx, asc_18012D478; "*"
0x1800521c0  lea     rcx, [rsp+688h+var_600]
0x1800521c8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800521cd  nop
0x1800521ce  lea     r8, [rsp+688h+var_600]
0x1800521d6  mov     rdx, [rsp+688h+var_668]
0x1800521db  lea     rcx, [rsp+688h+var_5D8]
0x1800521e3  call    ??0Directory@cxl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z; cxl::Directory::Directory(std::wstring const &,std::wstring const &)
0x1800521e8  nop
0x1800521e9  lea     rcx, [rsp+688h+var_600]
0x1800521f1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800521f6  lea     rdx, [rsp+688h+var_568]
0x1800521fe  lea     rcx, [rsp+688h+var_5D8]
0x180052206  call    ?begin@Directory@cxl@@QEAA?AVDirectoryEntry@2@XZ; cxl::Directory::begin(void)
0x18005220b  nop
0x18005220c  lea     rdx, [rsp+688h+var_2C8]
0x180052214  lea     rcx, [rsp+688h+var_5D8]
0x18005221c  call    ?end@Directory@cxl@@QEAA?AVDirectoryEntry@2@XZ; cxl::Directory::end(void)
0x180052221  lea     rdx, [rax+258h]
0x180052228  lea     rcx, [rsp+688h+var_310]
0x180052230  call    ??$?9_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@0@Z; std::operator!=<wchar_t>(std::wstring const &,std::wstring const &)
0x180052235  mov     bl, al
0x180052237  lea     rcx, [rsp+688h+var_2C8]; this
0x18005223f  call    ??1DirectoryEntry@cxl@@QEAA@XZ; cxl::DirectoryEntry::~DirectoryEntry(void)
0x180052244  nop
0x180052245  lea     rcx, [rsp+688h+var_568]; this
0x18005224d  call    ??1DirectoryEntry@cxl@@QEAA@XZ; cxl::DirectoryEntry::~DirectoryEntry(void)
0x180052252  test    bl, bl
0x180052254  jz      short loc_180052280
0x180052256  lea     rcx, [rsp+688h+var_5D8]; this
0x18005225e  call    ??1Directory@cxl@@QEAA@XZ; cxl::Directory::~Directory(void)
0x180052263  nop
0x180052264  lea     rcx, [rsp+688h+var_660]
0x180052269  call    ??1?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(void)
0x18005226e  nop
0x18005226f  lea     rcx, [rsp+688h+var_668]
0x180052274  call    ??1?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(void)
0x180052279  xor     al, al
0x18005227b  jmp     loc_180052503
0x180052280  mov     rdx, [rsp+688h+var_668]
0x180052285  mov     rdx, [rdx+10h]
0x180052289  lea     rcx, [rsp+688h+lpszVolumePathName]
0x18005228e  call    ??0?$vector@_WV?$allocator@_W@std@@@std@@QEAA@_KAEBV?$allocator@_W@1@@Z; std::vector<wchar_t>::vector<wchar_t>(unsigned __int64,std::allocator<wchar_t> const &)
0x180052293  nop
0x180052294  mov     rcx, [rsp+688h+var_668]
0x180052299  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18005229e  mov     r8, [rsp+688h+var_640]
0x1800522a3  mov     rdx, [rsp+688h+lpszVolumePathName]; lpszVolumePathName
0x1800522a8  sub     r8, rdx
0x1800522ab  sar     r8, 1; cchBufferLength
0x1800522ae  mov     rcx, rax; lpszFileName
0x1800522b1  call    cs:__imp_GetVolumePathNameW
0x1800522b7  mov     rdx, [rsp+688h+lpszVolumePathName]
0x1800522bc  lea     rcx, [rsp+688h+var_620]
0x1800522c1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800522c6  nop
0x1800522c7  lea     rdx, aShares; "Shares\\"
0x1800522ce  lea     rcx, [rsp+688h+var_620]
0x1800522d3  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x1800522d8  mov     rdx, [rsp+688h+var_660]
0x1800522dd  lea     rcx, [rsp+688h+var_620]
0x1800522e2  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x1800522e7  mov     r8, [rsp+688h+var_668]
0x1800522ec  lea     rdx, [rsp+688h+var_620]
0x1800522f1  call    ??RCaseInsensitive_Equal@cxl@@QEBA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z; cxl::CaseInsensitive_Equal::operator()(std::wstring const &,std::wstring const &)
0x1800522f6  test    al, al
0x1800522f8  jnz     short loc_18005233A
0x1800522fa  lea     rcx, [rsp+688h+var_620]
0x1800522ff  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180052304  nop
0x180052305  lea     rcx, [rsp+688h+lpszVolumePathName]
0x18005230a  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18005230f  nop
0x180052310  lea     rcx, [rsp+688h+var_5D8]; this
0x180052318  call    ??1Directory@cxl@@QEAA@XZ; cxl::Directory::~Directory(void)
0x18005231d  nop
0x18005231e  lea     rcx, [rsp+688h+var_660]
0x180052323  call    ??1?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(void)
0x180052328  nop
0x180052329  lea     rcx, [rsp+688h+var_668]
0x18005232e  call    ??1?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(void)
0x180052333  xor     al, al
0x180052335  jmp     loc_180052503
0x18005233a  mov     edx, 2
0x18005233f  lea     rcx, [rsp+688h+var_630]
0x180052344  call    ?Enumerate@FileShareFacade@Facade@Wsp@@SA?AV?$shared_ptr@V?$vector@V?$shared_ptr@VFileShareFacade@Facade@Wsp@@@std@@V?$allocator@V?$shared_ptr@VFileShareFacade@Facade@Wsp@@@std@@@2@@std@@@std@@W4WSP_SUBSYSTEM_FILTER@@@Z; Wsp::Facade::FileShareFacade::Enumerate(WSP_SUBSYSTEM_FILTER)
0x180052349  nop
0x18005234a  mov     rax, [rsp+688h+var_630]
0x18005234f  test    rax, rax
0x180052352  jz      loc_18005249B
0x180052358  mov     rbx, [rax]
0x18005235b  mov     r15, [rax+8]
0x18005235f  cmp     rbx, r15
0x180052362  jz      loc_18005249B
0x180052368  mov     rax, [rbx]
0x18005236b  mov     rcx, [rax]
0x18005236e  test    rcx, rcx
0x180052371  jz      short loc_18005238B
0x180052373  mov     rax, [rcx]
0x180052376  lea     rdx, [rsp+688h+var_650]
0x18005237b  mov     rax, [rax+38h]
0x18005237f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052384  mov     r8, [rsp+688h+var_650]
0x180052389  jmp     short loc_180052393
0x18005238b  xor     r8d, r8d
0x18005238e  mov     [rsp+688h+var_650], r8
0x180052393  or      edi, 4
0x180052396  test    r8, r8
0x180052399  jz      loc_180052488
0x18005239f  mov     rdx, [rsp+688h+var_668]
0x1800523a4  call    ??RCaseInsensitive_Equal@cxl@@QEBA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z; cxl::CaseInsensitive_Equal::operator()(std::wstring const &,std::wstring const &)
0x1800523a9  test    al, al
0x1800523ab  jz      short loc_1800523FA
0x1800523ad  lea     rdx, [rsp+688h+var_588]
0x1800523b5  mov     rcx, [rbx]
0x1800523b8  call    ?GetUniqueId@FileShareFacade@Facade@Wsp@@QEBA?BV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Wsp::Facade::FileShareFacade::GetUniqueId(void)
0x1800523bd  mov     rsi, rax
0x1800523c0  or      edi, 1
0x1800523c3  mov     [rsp+688h+var_658], edi
0x1800523c7  mov     rcx, [r14]
0x1800523ca  mov     rdx, [rcx]
0x1800523cd  mov     rax, [rdx+8]
0x1800523d1  lea     rdx, [rsp+688h+var_600]
0x1800523d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800523de  nop
0x1800523df  or      edi, 2
0x1800523e2  mov     [rsp+688h+var_658], edi
0x1800523e6  mov     r8, rsi
0x1800523e9  mov     rdx, rax
0x1800523ec  call    ??RCaseInsensitive_Equal@cxl@@QEBA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z; cxl::CaseInsensitive_Equal::operator()(std::wstring const &,std::wstring const &)
0x1800523f1  test    al, al
0x1800523f3  jnz     short loc_1800523FA
0x1800523f5  mov     sil, 1
0x1800523f8  jmp     short loc_1800523FD
0x1800523fa  xor     sil, sil
0x1800523fd  test    dil, 2
0x180052401  jz      short loc_180052414
0x180052403  and     edi, 0FFFFFFFDh
0x180052406  lea     rcx, [rsp+688h+var_600]
0x18005240e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180052413  nop
0x180052414  test    dil, 1
0x180052418  jz      short loc_18005242B
0x18005241a  and     edi, 0FFFFFFFEh
0x18005241d  lea     rcx, [rsp+688h+var_588]
0x180052425  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005242a  nop
0x18005242b  test    sil, sil
0x18005242e  jz      short loc_180052488
0x180052430  lea     rcx, [rsp+688h+var_650]
0x180052435  call    ??1?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(void)
0x18005243a  nop
0x18005243b  mov     rcx, [rsp+688h+var_628]; this
0x180052440  test    rcx, rcx
0x180052443  jz      short loc_18005244B
0x180052445  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005244a  nop
0x18005244b  lea     rcx, [rsp+688h+var_620]
0x180052450  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180052455  nop
0x180052456  lea     rcx, [rsp+688h+lpszVolumePathName]
0x18005245b  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180052460  nop
0x180052461  lea     rcx, [rsp+688h+var_5D8]; this
0x180052469  call    ??1Directory@cxl@@QEAA@XZ; cxl::Directory::~Directory(void)
0x18005246e  nop
0x18005246f  lea     rcx, [rsp+688h+var_660]
0x180052474  call    ??1?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(void)
0x180052479  nop
0x18005247a  lea     rcx, [rsp+688h+var_668]
0x18005247f  call    ??1?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(void)
0x180052484  xor     al, al
0x180052486  jmp     short loc_180052503
0x180052488  lea     rcx, [rsp+688h+var_650]
0x18005248d  call    ??1?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(void)
0x180052492  add     rbx, 10h
0x180052496  jmp     loc_18005235F
0x18005249b  mov     rcx, [rsp+688h+var_628]; this
0x1800524a0  test    rcx, rcx
0x1800524a3  jz      short loc_1800524AB
0x1800524a5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800524aa  nop
0x1800524ab  lea     rcx, [rsp+688h+var_620]
0x1800524b0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800524b5  nop
0x1800524b6  lea     rcx, [rsp+688h+lpszVolumePathName]
0x1800524bb  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800524c0  nop
0x1800524c1  lea     rcx, [rsp+688h+var_5D8]; this
0x1800524c9  call    ??1Directory@cxl@@QEAA@XZ; cxl::Directory::~Directory(void)
0x1800524ce  nop
0x1800524cf  lea     rcx, [rsp+688h+var_660]
0x1800524d4  call    ??1?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(void)
0x1800524d9  nop
0x1800524da  lea     rcx, [rsp+688h+var_668]
0x1800524df  call    ??1?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(void)
0x1800524e4  mov     al, 1
0x1800524e6  jmp     short loc_180052503
0x1800524e8  lea     rcx, [rsp+688h+var_660]
0x1800524ed  call    ??1?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(void)
0x1800524f2  nop
0x1800524f3  lea     rcx, [rsp+688h+var_668]
0x1800524f8  call    ??1?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(void)
0x1800524fd  xor     al, al
0x1800524ff  jmp     short loc_180052503
0x180052501  xor     al, al
0x180052503  mov     rcx, [rsp+688h+var_28]
0x18005250b  xor     rcx, rsp; StackCookie
0x18005250e  call    __security_check_cookie
0x180052513  lea     r11, [rsp+688h+var_18]
0x18005251b  mov     rbx, [r11+28h]
0x18005251f  mov     rsi, [r11+30h]
0x180052523  mov     rsp, r11
0x180052526  pop     r15
0x180052528  pop     r14
0x18005252a  pop     rdi
0x18005252b  retn
```
