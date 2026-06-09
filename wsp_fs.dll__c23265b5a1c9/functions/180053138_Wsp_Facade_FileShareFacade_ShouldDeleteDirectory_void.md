# Wsp::Facade::FileShareFacade::ShouldDeleteDirectory(void)

- ea: `0x180053138`
- end: `0x180053523`
- name: `?ShouldDeleteDirectory@FileShareFacade@Facade@Wsp@@AEAA_NXZ`
- size: `1003`
- prototype: `bool __fastcall(Wsp::Facade::FileShareFacade *__hidden this)`
- caller_count: `1`
- callee_count: `21`
- tags: ``

## callers

- `0x180052138`

## callees

- `0x180002ad0`
- `0x180005fdc`
- `0x18000aa10`
- `0x18000c5c4`
- `0x18000e14c`
- `0x180010b6c`
- `0x1800143d8`
- `0x180014c94`
- `0x18001f588`
- `0x180026588`
- `0x18004905c`
- `0x1800518b8`
- `0x180051cb8`
- `0x1800523c0`
- `0x180052ad0`
- `0x180053138`
- `0x180079754`
- `0x180079984`
- `0x180079a1c`
- `0x180079cec`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1800532a1`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1800532a1`

## pseudocode

```c
// Hidden C++ exception states: #wind=12 #try_helpers=1
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
  char v29[72]; // [rsp+378h] [rbp-310h] BYREF
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
      std::wstring::append(v24, v18);
      if ( cxl::CaseInsensitive_Equal::operator()(v7, (__int64)v24, v17) )
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
              if ( cxl::CaseInsensitive_Equal::operator()(v10, v17, v11) )
              {
                UniqueId = Wsp::Facade::FileShareFacade::GetUniqueId(*v8, v27);
                v13 = v2 | 1;
                v19 = v13;
                v14 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)this + 8LL))(*(_QWORD *)this, v25);
                v2 = v13 | 2;
                v19 = v2;
                if ( !cxl::CaseInsensitive_Equal::operator()(v15, v14, UniqueId) )
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
0x180053138  mov     [rsp+arg_8], rbx
0x18005313d  mov     [rsp+arg_10], rsi
0x180053142  push    rdi
0x180053143  push    r14
0x180053145  push    r15
0x180053147  sub     rsp, 670h
0x18005314e  mov     rax, cs:__security_cookie
0x180053155  xor     rax, rsp
0x180053158  mov     [rsp+688h+var_28], rax
0x180053160  mov     r14, rcx
0x180053163  xor     edi, edi
0x180053165  mov     [rsp+688h+var_658], edi
0x180053169  mov     rcx, [rcx]
0x18005316c  mov     rax, [rcx]
0x18005316f  lea     rdx, [rsp+688h+var_668]
0x180053174  mov     rax, [rax+38h]
0x180053178  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005317d  nop
0x18005317e  mov     rcx, [r14]
0x180053181  mov     rax, [rcx]
0x180053184  lea     rdx, [rsp+688h+var_660]
0x180053189  mov     rax, [rax+20h]
0x18005318d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053192  nop
0x180053193  cmp     [rsp+688h+var_668], rdi
0x180053198  jz      loc_1800534DE
0x18005319e  cmp     [rsp+688h+var_660], rdi
0x1800531a3  jz      loc_1800534DE
0x1800531a9  lea     rdx, asc_18012F488; "*"
0x1800531b0  lea     rcx, [rsp+688h+var_600]
0x1800531b8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800531bd  nop
0x1800531be  lea     r8, [rsp+688h+var_600]
0x1800531c6  mov     rdx, [rsp+688h+var_668]
0x1800531cb  lea     rcx, [rsp+688h+var_5D8]
0x1800531d3  call    ??0Directory@cxl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z; cxl::Directory::Directory(std::wstring const &,std::wstring const &)
0x1800531d8  nop
0x1800531d9  lea     rcx, [rsp+688h+var_600]
0x1800531e1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800531e6  lea     rdx, [rsp+688h+var_568]
0x1800531ee  lea     rcx, [rsp+688h+var_5D8]
0x1800531f6  call    ?begin@Directory@cxl@@QEAA?AVDirectoryEntry@2@XZ; cxl::Directory::begin(void)
0x1800531fb  nop
0x1800531fc  lea     rdx, [rsp+688h+var_2C8]
0x180053204  lea     rcx, [rsp+688h+var_5D8]
0x18005320c  call    ?end@Directory@cxl@@QEAA?AVDirectoryEntry@2@XZ; cxl::Directory::end(void)
0x180053211  lea     rdx, [rax+258h]
0x180053218  lea     rcx, [rsp+688h+var_310]
0x180053220  call    ??$?9_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@0@Z; std::operator!=<wchar_t>(std::wstring const &,std::wstring const &)
0x180053225  mov     bl, al
0x180053227  lea     rcx, [rsp+688h+var_2C8]; this
0x18005322f  call    ??1DirectoryEntry@cxl@@QEAA@XZ; cxl::DirectoryEntry::~DirectoryEntry(void)
0x180053234  nop
0x180053235  lea     rcx, [rsp+688h+var_568]; this
0x18005323d  call    ??1DirectoryEntry@cxl@@QEAA@XZ; cxl::DirectoryEntry::~DirectoryEntry(void)
0x180053242  test    bl, bl
0x180053244  jz      short loc_180053270
0x180053246  lea     rcx, [rsp+688h+var_5D8]; this
0x18005324e  call    ??1Directory@cxl@@QEAA@XZ; cxl::Directory::~Directory(void)
0x180053253  nop
0x180053254  lea     rcx, [rsp+688h+var_660]
0x180053259  call    ??1?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(void)
0x18005325e  nop
0x18005325f  lea     rcx, [rsp+688h+var_668]
0x180053264  call    ??1?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(void)
0x180053269  xor     al, al
0x18005326b  jmp     loc_1800534F9
0x180053270  mov     rdx, [rsp+688h+var_668]
0x180053275  mov     rdx, [rdx+10h]
0x180053279  lea     rcx, [rsp+688h+lpszVolumePathName]
0x18005327e  call    ??0?$vector@_WV?$allocator@_W@std@@@std@@QEAA@_KAEBV?$allocator@_W@1@@Z; std::vector<wchar_t>::vector<wchar_t>(unsigned __int64,std::allocator<wchar_t> const &)
0x180053283  nop
0x180053284  mov     rcx, [rsp+688h+var_668]
0x180053289  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18005328e  mov     r8, [rsp+688h+var_640]
0x180053293  mov     rdx, [rsp+688h+lpszVolumePathName]; lpszVolumePathName
0x180053298  sub     r8, rdx
0x18005329b  sar     r8, 1; cchBufferLength
0x18005329e  mov     rcx, rax; lpszFileName
0x1800532a1  call    cs:__imp_GetVolumePathNameW
0x1800532a8  nop     dword ptr [rax+rax+00h]
0x1800532ad  mov     rdx, [rsp+688h+lpszVolumePathName]
0x1800532b2  lea     rcx, [rsp+688h+var_620]
0x1800532b7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800532bc  nop
0x1800532bd  lea     rdx, aShares; "Shares\\"
0x1800532c4  lea     rcx, [rsp+688h+var_620]
0x1800532c9  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x1800532ce  mov     rdx, [rsp+688h+var_660]
0x1800532d3  lea     rcx, [rsp+688h+var_620]
0x1800532d8  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x1800532dd  mov     r8, [rsp+688h+var_668]
0x1800532e2  lea     rdx, [rsp+688h+var_620]
0x1800532e7  call    ??RCaseInsensitive_Equal@cxl@@QEBA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z; cxl::CaseInsensitive_Equal::operator()(std::wstring const &,std::wstring const &)
0x1800532ec  test    al, al
0x1800532ee  jnz     short loc_180053330
0x1800532f0  lea     rcx, [rsp+688h+var_620]
0x1800532f5  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800532fa  nop
0x1800532fb  lea     rcx, [rsp+688h+lpszVolumePathName]
0x180053300  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180053305  nop
0x180053306  lea     rcx, [rsp+688h+var_5D8]; this
0x18005330e  call    ??1Directory@cxl@@QEAA@XZ; cxl::Directory::~Directory(void)
0x180053313  nop
0x180053314  lea     rcx, [rsp+688h+var_660]
0x180053319  call    ??1?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(void)
0x18005331e  nop
0x18005331f  lea     rcx, [rsp+688h+var_668]
0x180053324  call    ??1?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(void)
0x180053329  xor     al, al
0x18005332b  jmp     loc_1800534F9
0x180053330  mov     edx, 2
0x180053335  lea     rcx, [rsp+688h+var_630]
0x18005333a  call    ?Enumerate@FileShareFacade@Facade@Wsp@@SA?AV?$shared_ptr@V?$vector@V?$shared_ptr@VFileShareFacade@Facade@Wsp@@@std@@V?$allocator@V?$shared_ptr@VFileShareFacade@Facade@Wsp@@@std@@@2@@std@@@std@@W4WSP_SUBSYSTEM_FILTER@@@Z; Wsp::Facade::FileShareFacade::Enumerate(WSP_SUBSYSTEM_FILTER)
0x18005333f  nop
0x180053340  mov     rax, [rsp+688h+var_630]
0x180053345  test    rax, rax
0x180053348  jz      loc_180053491
0x18005334e  mov     rbx, [rax]
0x180053351  mov     r15, [rax+8]
0x180053355  cmp     rbx, r15
0x180053358  jz      loc_180053491
0x18005335e  mov     rax, [rbx]
0x180053361  mov     rcx, [rax]
0x180053364  test    rcx, rcx
0x180053367  jz      short loc_180053381
0x180053369  mov     rax, [rcx]
0x18005336c  lea     rdx, [rsp+688h+var_650]
0x180053371  mov     rax, [rax+38h]
0x180053375  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005337a  mov     r8, [rsp+688h+var_650]
0x18005337f  jmp     short loc_180053389
0x180053381  xor     r8d, r8d
0x180053384  mov     [rsp+688h+var_650], r8
0x180053389  or      edi, 4
0x18005338c  test    r8, r8
0x18005338f  jz      loc_18005347E
0x180053395  mov     rdx, [rsp+688h+var_668]
0x18005339a  call    ??RCaseInsensitive_Equal@cxl@@QEBA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z; cxl::CaseInsensitive_Equal::operator()(std::wstring const &,std::wstring const &)
0x18005339f  test    al, al
0x1800533a1  jz      short loc_1800533F0
0x1800533a3  lea     rdx, [rsp+688h+var_588]
0x1800533ab  mov     rcx, [rbx]
0x1800533ae  call    ?GetUniqueId@FileShareFacade@Facade@Wsp@@QEBA?BV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Wsp::Facade::FileShareFacade::GetUniqueId(void)
0x1800533b3  mov     rsi, rax
0x1800533b6  or      edi, 1
0x1800533b9  mov     [rsp+688h+var_658], edi
0x1800533bd  mov     rcx, [r14]
0x1800533c0  mov     rdx, [rcx]
0x1800533c3  mov     rax, [rdx+8]
0x1800533c7  lea     rdx, [rsp+688h+var_600]
0x1800533cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800533d4  nop
0x1800533d5  or      edi, 2
0x1800533d8  mov     [rsp+688h+var_658], edi
0x1800533dc  mov     r8, rsi
0x1800533df  mov     rdx, rax
0x1800533e2  call    ??RCaseInsensitive_Equal@cxl@@QEBA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z; cxl::CaseInsensitive_Equal::operator()(std::wstring const &,std::wstring const &)
0x1800533e7  test    al, al
0x1800533e9  jnz     short loc_1800533F0
0x1800533eb  mov     sil, 1
0x1800533ee  jmp     short loc_1800533F3
0x1800533f0  xor     sil, sil
0x1800533f3  test    dil, 2
0x1800533f7  jz      short loc_18005340A
0x1800533f9  and     edi, 0FFFFFFFDh
0x1800533fc  lea     rcx, [rsp+688h+var_600]
0x180053404  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180053409  nop
0x18005340a  test    dil, 1
0x18005340e  jz      short loc_180053421
0x180053410  and     edi, 0FFFFFFFEh
0x180053413  lea     rcx, [rsp+688h+var_588]
0x18005341b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180053420  nop
0x180053421  test    sil, sil
0x180053424  jz      short loc_18005347E
0x180053426  lea     rcx, [rsp+688h+var_650]
0x18005342b  call    ??1?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(void)
0x180053430  nop
0x180053431  mov     rcx, [rsp+688h+var_628]; this
0x180053436  test    rcx, rcx
0x180053439  jz      short loc_180053441
0x18005343b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180053440  nop
0x180053441  lea     rcx, [rsp+688h+var_620]
0x180053446  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005344b  nop
0x18005344c  lea     rcx, [rsp+688h+lpszVolumePathName]
0x180053451  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180053456  nop
0x180053457  lea     rcx, [rsp+688h+var_5D8]; this
0x18005345f  call    ??1Directory@cxl@@QEAA@XZ; cxl::Directory::~Directory(void)
0x180053464  nop
0x180053465  lea     rcx, [rsp+688h+var_660]
0x18005346a  call    ??1?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(void)
0x18005346f  nop
0x180053470  lea     rcx, [rsp+688h+var_668]
0x180053475  call    ??1?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(void)
0x18005347a  xor     al, al
0x18005347c  jmp     short loc_1800534F9
0x18005347e  lea     rcx, [rsp+688h+var_650]
0x180053483  call    ??1?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(void)
0x180053488  add     rbx, 10h
0x18005348c  jmp     loc_180053355
0x180053491  mov     rcx, [rsp+688h+var_628]; this
0x180053496  test    rcx, rcx
0x180053499  jz      short loc_1800534A1
0x18005349b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800534a0  nop
0x1800534a1  lea     rcx, [rsp+688h+var_620]
0x1800534a6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800534ab  nop
0x1800534ac  lea     rcx, [rsp+688h+lpszVolumePathName]
0x1800534b1  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800534b6  nop
0x1800534b7  lea     rcx, [rsp+688h+var_5D8]; this
0x1800534bf  call    ??1Directory@cxl@@QEAA@XZ; cxl::Directory::~Directory(void)
0x1800534c4  nop
0x1800534c5  lea     rcx, [rsp+688h+var_660]
0x1800534ca  call    ??1?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(void)
0x1800534cf  nop
0x1800534d0  lea     rcx, [rsp+688h+var_668]
0x1800534d5  call    ??1?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(void)
0x1800534da  mov     al, 1
0x1800534dc  jmp     short loc_1800534F9
0x1800534de  lea     rcx, [rsp+688h+var_660]
0x1800534e3  call    ??1?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(void)
0x1800534e8  nop
0x1800534e9  lea     rcx, [rsp+688h+var_668]
0x1800534ee  call    ??1?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(void)
0x1800534f3  xor     al, al
0x1800534f5  jmp     short loc_1800534F9
0x1800534f7  xor     al, al
0x1800534f9  mov     rcx, [rsp+688h+var_28]
0x180053501  xor     rcx, rsp; StackCookie
0x180053504  call    __security_check_cookie
0x180053509  lea     r11, [rsp+688h+var_18]
0x180053511  mov     rbx, [r11+28h]
0x180053515  mov     rsi, [r11+30h]
0x180053519  mov     rsp, r11
0x18005351c  pop     r15
0x18005351e  pop     r14
0x180053520  pop     rdi
0x180053521  retn
```
