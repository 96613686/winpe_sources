# ArchiveExtractWizard::ValidateDestinationPath(void)

- ea: `0x180031258`
- end: `0x1800317cf`
- name: `?ValidateDestinationPath@ArchiveExtractWizard@@AEAAJXZ`
- size: `1399`
- prototype: `__int64 __fastcall(ArchiveExtractWizard *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180028d64`

## callees

- `0x1800126a0`
- `0x1800208e0`
- `0x180020cbc`
- `0x1800210b0`
- `0x180021f0c`
- `0x180022a34`
- `0x180024a24`
- `0x18002abd0`
- `0x180030a3c`
- `0x180031258`
- `0x180031e94`
- `0x1800350cc`
- `0x180036f50`
- `0x180048d3c`
- `0x180052d94`
- `0x180071010`

## import_xrefs

- `SHELL32!SHCreateItemFromIDList` at `0x18003150b`
- `SHELL32!SHCreateItemFromIDList` at `0x18003150b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800315c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031723`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031764`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800315c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031723`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031764`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180031372`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180031372`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x1800312d4`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x1800312d4`

## pseudocode

```c
__int64 __fastcall ArchiveExtractWizard::ValidateDestinationPath(ArchiveExtractWizard *this)
{
  char *v2; // rsi
  const WCHAR *v4; // r15
  HRESULT v5; // eax
  unsigned int v6; // ebx
  unsigned __int64 v7; // r14
  int v8; // eax
  unsigned int v9; // ebx
  HRESULT v10; // eax
  unsigned int v11; // ebx
  int v12; // eax
  unsigned int v13; // ebx
  int v14; // eax
  int v15; // eax
  unsigned int v16; // ebx
  __int64 v17; // rax
  int v18; // eax
  unsigned int v19; // ebx
  HRESULT v20; // eax
  unsigned int v21; // ebx
  void *v22; // rdi
  __int64 (__fastcall *v23)(void *, __int64, LPVOID *); // rbx
  int v24; // eax
  unsigned int v25; // ebx
  unsigned __int16 *v26; // rax
  int v27; // r9d
  int v28; // ecx
  __int64 v29; // rax
  __int64 v30; // rdx
  __int64 v31; // rax
  __int64 v32; // rcx
  void *v33; // rdx
  __int64 v34; // rax
  __int64 v35; // r8
  int ppv; // [rsp+20h] [rbp-118h]
  int ppva; // [rsp+20h] [rbp-118h]
  PCWSTR ppszRootEnd; // [rsp+30h] [rbp-108h] BYREF
  LPVOID v39; // [rsp+38h] [rbp-100h] BYREF
  void *v40; // [rsp+40h] [rbp-F8h] BYREF
  LPCITEMIDLIST pidl; // [rsp+48h] [rbp-F0h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-E8h] BYREF
  _BYTE v43[16]; // [rsp+58h] [rbp-E0h] BYREF
  __int64 v44; // [rsp+68h] [rbp-D0h]
  unsigned __int16 v45[64]; // [rsp+80h] [rbp-B8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  v2 = (char *)this + 40;
  if ( *((_QWORD *)this + 7) )
  {
    v4 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 40);
    ppszRootEnd = 0;
    v5 = PathCchSkipRoot(v4, &ppszRootEnd);
    v6 = v5;
    if ( v5 >= 0 )
    {
      v7 = ppszRootEnd - v4;
      v8 = StringCchCopyNW(v45, 0x40u, v4, v7);
      v9 = v8;
      if ( v8 >= 0 )
      {
        v39 = 0;
        v10 = CoCreateInstance(&CLSID_ShellUrl, 0, 1u, &GUID_4f33718d_bae1_4f9b_96f2_d2a16e683346, &v39);
        v11 = v10;
        if ( v10 >= 0 )
        {
          v12 = SetDefaultShellPath(v39);
          v13 = v12;
          if ( v12 >= 0 )
          {
            v14 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v39 + 184LL))(v39, 0);
            v15 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *, _QWORD))(*(_QWORD *)v39 + 24LL))(
                    v39,
                    v45,
                    v14 | 0x85u);
            v16 = v15;
            if ( v15 >= 0 )
            {
              pidl = 0;
              v40 = 0;
              v17 = *(_QWORD *)v39;
              pidl = 0;
              v18 = (*(__int64 (__fastcall **)(LPVOID, LPCITEMIDLIST *))(v17 + 56))(v39, &pidl);
              v19 = v18;
              if ( v18 >= 0 )
              {
                if ( v40 )
                  winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v40);
                v20 = SHCreateItemFromIDList(pidl, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &v40);
                v21 = v20;
                if ( v20 >= 0 )
                {
                  pv = 0;
                  v22 = v40;
                  v23 = *(__int64 (__fastcall **)(void *, __int64, LPVOID *))(*(_QWORD *)v40 + 40LL);
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                    &pv,
                    0);
                  v24 = v23(v22, 2147844096LL, &pv);
                  v25 = v24;
                  if ( v24 >= 0 )
                  {
                    v26 = v45;
                    do
                    {
                      v27 = *(unsigned __int16 *)((char *)v26 + (_BYTE *)pv - (_BYTE *)v45);
                      v28 = *v26 - v27;
                      if ( v28 )
                        break;
                      ++v26;
                    }
                    while ( v27 );
                    if ( v28 )
                    {
                      std::wstring::wstring(v43, pv);
                      if ( v44 )
                      {
                        v29 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v43);
                        if ( *(_WORD *)(v29 + 2 * v30 - 2) != 92 )
                          std::wstring::push_back(v43);
                      }
                      v31 = std::_WChar_traits<unsigned short>::length(&v4[v7]);
                      std::wstring::_Append<unsigned short>(v43, v32, v31);
                      if ( v43 != v2 )
                        std::wstring::_Swap_data(v43, v2);
                      std::wstring::_Tidy_deallocate(v43);
                    }
                    if ( *(_WORD *)(std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v2)
                                  + 2LL * *((_QWORD *)v2 + 2)
                                  - 2) != 92 )
                    {
                      std::wstring::push_back(v2);
                      v33 = pv;
                    }
                    if ( *((_QWORD *)this + 7) > 1u
                      && (v34 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v2),
                          *(_WORD *)(v34 + 2 * v35 - 4) == 46) )
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x716,
                        (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
                        (const char *)0x80070057LL,
                        ppva);
                      if ( pv )
                        CoTaskMemFree(pv);
                      if ( v40 )
                        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v40);
                      wil::details::unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&void ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&void ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>(&pidl);
                      if ( v39 )
                        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v39);
                      return 2147942487LL;
                    }
                    else
                    {
                      if ( v33 )
                        CoTaskMemFree(v33);
                      if ( v40 )
                        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v40);
                      wil::details::unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&void ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&void ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>(&pidl);
                      if ( v39 )
                        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v39);
                      return 0;
                    }
                  }
                  else
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x6FF,
                      (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
                      (const char *)(unsigned int)v24,
                      ppva);
                    if ( pv )
                      CoTaskMemFree(pv);
                    if ( v40 )
                      winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v40);
                    wil::details::unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&void ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&void ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>(&pidl);
                    if ( v39 )
                      winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v39);
                    return v25;
                  }
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x6FB,
                    (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
                    (const char *)(unsigned int)v20,
                    ppva);
                  if ( v40 )
                    winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v40);
                  wil::details::unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&void ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&void ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>(&pidl);
                  if ( v39 )
                    winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v39);
                  return v21;
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x6FA,
                  (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
                  (const char *)(unsigned int)v18,
                  ppva);
                if ( v40 )
                  winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v40);
                wil::details::unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&void ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&void ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>(&pidl);
                if ( v39 )
                  winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v39);
                return v19;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x6F6,
                (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
                (const char *)(unsigned int)v15,
                ppva);
              if ( v39 )
                winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v39);
              return v16;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x6F3,
              (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
              (const char *)(unsigned int)v12,
              ppva);
            if ( v39 )
              winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v39);
            return v13;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x6F2,
            (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
            (const char *)(unsigned int)v10,
            ppva);
          if ( v39 )
            winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v39);
          return v11;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6EF,
          (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
          (const char *)(unsigned int)v8,
          ppv);
        return v9;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6EB,
        (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
        (const char *)(unsigned int)v5,
        ppv);
      return v6;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6E6,
      (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
      (const char *)0x80070057LL,
      ppv);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180031258  mov     [rsp+arg_8], rbx
0x18003125d  mov     [rsp+arg_10], rsi
0x180031262  push    rdi
0x180031263  push    r12
0x180031265  push    r13
0x180031267  push    r14
0x180031269  push    r15
0x18003126b  sub     rsp, 110h
0x180031272  mov     rax, cs:__security_cookie
0x180031279  xor     rax, rsp
0x18003127c  mov     [rsp+138h+var_38], rax
0x180031284  mov     r13, rcx
0x180031287  lea     rsi, [rcx+28h]
0x18003128b  xor     r12d, r12d
0x18003128e  cmp     [rsi+10h], r12
0x180031292  jnz     short loc_1800312BC
0x180031294  mov     rcx, [rsp+138h]; this
0x18003129c  mov     ebx, 80070057h
0x1800312a1  mov     r9d, ebx; char *
0x1800312a4  lea     r8, aShellExtZipArc_8; "shell\\ext\\zip\\archive\\archiveextrac"...
0x1800312ab  mov     edx, 6E6h; void *
0x1800312b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800312b5  mov     eax, ebx
0x1800312b7  jmp     loc_1800317A1
0x1800312bc  mov     rcx, rsi
0x1800312bf  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800312c4  mov     r15, rax
0x1800312c7  mov     [rsp+138h+ppszRootEnd], r12
0x1800312cc  lea     rdx, [rsp+138h+ppszRootEnd]; ppszRootEnd
0x1800312d1  mov     rcx, rax; pszPath
0x1800312d4  call    cs:__imp_PathCchSkipRoot
0x1800312da  mov     ebx, eax
0x1800312dc  test    eax, eax
0x1800312de  jns     short loc_180031303
0x1800312e0  mov     rcx, [rsp+138h]; this
0x1800312e8  mov     r9d, eax; char *
0x1800312eb  lea     r8, aShellExtZipArc_8; "shell\\ext\\zip\\archive\\archiveextrac"...
0x1800312f2  mov     edx, 6EBh; void *
0x1800312f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800312fc  mov     eax, ebx
0x1800312fe  jmp     loc_1800317A1
0x180031303  mov     r14, [rsp+138h+ppszRootEnd]
0x180031308  sub     r14, r15
0x18003130b  sar     r14, 1
0x18003130e  mov     r9, r14; unsigned __int64
0x180031311  mov     r8, r15; unsigned __int16 *
0x180031314  mov     edx, 40h ; '@'; unsigned __int64
0x180031319  lea     rcx, [rsp+138h+var_B8]; unsigned __int16 *
0x180031321  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180031326  mov     ebx, eax
0x180031328  test    eax, eax
0x18003132a  jns     short loc_18003134F
0x18003132c  mov     rcx, [rsp+138h]; this
0x180031334  mov     r9d, eax; char *
0x180031337  lea     r8, aShellExtZipArc_8; "shell\\ext\\zip\\archive\\archiveextrac"...
0x18003133e  mov     edx, 6EFh; void *
0x180031343  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031348  mov     eax, ebx
0x18003134a  jmp     loc_1800317A1
0x18003134f  mov     [rsp+138h+var_100], r12
0x180031354  lea     rax, [rsp+138h+var_100]
0x180031359  mov     qword ptr [rsp+138h+ppv], rax; int
0x18003135e  lea     r9, _GUID_4f33718d_bae1_4f9b_96f2_d2a16e683346; riid
0x180031365  xor     edx, edx; pUnkOuter
0x180031367  lea     r8d, [rdx+1]; dwClsContext
0x18003136b  lea     rcx, CLSID_ShellUrl; rclsid
0x180031372  call    cs:__imp_CoCreateInstance
0x180031378  mov     ebx, eax
0x18003137a  test    eax, eax
0x18003137c  jns     short loc_1800313B3
0x18003137e  mov     rcx, [rsp+138h]; this
0x180031386  mov     r9d, eax; char *
0x180031389  lea     r8, aShellExtZipArc_8; "shell\\ext\\zip\\archive\\archiveextrac"...
0x180031390  mov     edx, 6F2h; void *
0x180031395  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003139a  nop
0x18003139b  cmp     [rsp+138h+var_100], r12
0x1800313a0  jz      short loc_1800313AC
0x1800313a2  lea     rcx, [rsp+138h+var_100]
0x1800313a7  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x1800313ac  mov     eax, ebx
0x1800313ae  jmp     loc_1800317A1
0x1800313b3  mov     rcx, [rsp+138h+var_100]
0x1800313b8  call    SetDefaultShellPath
0x1800313bd  mov     ebx, eax
0x1800313bf  test    eax, eax
0x1800313c1  jns     short loc_1800313F8
0x1800313c3  mov     rcx, [rsp+138h]; this
0x1800313cb  mov     r9d, eax; char *
0x1800313ce  lea     r8, aShellExtZipArc_8; "shell\\ext\\zip\\archive\\archiveextrac"...
0x1800313d5  mov     edx, 6F3h; void *
0x1800313da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800313df  nop
0x1800313e0  cmp     [rsp+138h+var_100], r12
0x1800313e5  jz      short loc_1800313F1
0x1800313e7  lea     rcx, [rsp+138h+var_100]
0x1800313ec  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x1800313f1  mov     eax, ebx
0x1800313f3  jmp     loc_1800317A1
0x1800313f8  mov     rcx, [rsp+138h+var_100]
0x1800313fd  mov     rax, [rcx]
0x180031400  xor     edx, edx
0x180031402  mov     rax, [rax+0B8h]
0x180031409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003140e  mov     r8d, eax
0x180031411  mov     rcx, [rsp+138h+var_100]
0x180031416  mov     rax, [rcx]
0x180031419  or      r8d, 85h
0x180031420  lea     rdx, [rsp+138h+var_B8]
0x180031428  mov     rax, [rax+18h]
0x18003142c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031431  mov     ebx, eax
0x180031433  test    eax, eax
0x180031435  jns     short loc_18003146C
0x180031437  mov     rcx, [rsp+138h]; this
0x18003143f  mov     r9d, eax; char *
0x180031442  lea     r8, aShellExtZipArc_8; "shell\\ext\\zip\\archive\\archiveextrac"...
0x180031449  mov     edx, 6F6h; void *
0x18003144e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031453  nop
0x180031454  cmp     [rsp+138h+var_100], r12
0x180031459  jz      short loc_180031465
0x18003145b  lea     rcx, [rsp+138h+var_100]
0x180031460  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x180031465  mov     eax, ebx
0x180031467  jmp     loc_1800317A1
0x18003146c  mov     [rsp+138h+pidl], r12
0x180031471  mov     [rsp+138h+var_F8], r12
0x180031476  mov     rcx, [rsp+138h+var_100]
0x18003147b  mov     rax, [rcx]
0x18003147e  mov     [rsp+138h+pidl], r12
0x180031483  lea     rdx, [rsp+138h+pidl]
0x180031488  mov     rax, [rax+38h]
0x18003148c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031491  mov     ebx, eax
0x180031493  test    eax, eax
0x180031495  jns     short loc_1800314E9
0x180031497  mov     rcx, [rsp+138h]; this
0x18003149f  mov     r9d, eax; char *
0x1800314a2  lea     r8, aShellExtZipArc_8; "shell\\ext\\zip\\archive\\archiveextrac"...
0x1800314a9  mov     edx, 6FAh; void *
0x1800314ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800314b3  nop
0x1800314b4  cmp     [rsp+138h+var_F8], r12
0x1800314b9  jz      short loc_1800314C6
0x1800314bb  lea     rcx, [rsp+138h+var_F8]
0x1800314c0  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x1800314c5  nop
0x1800314c6  lea     rcx, [rsp+138h+pidl]
0x1800314cb  call    ??1?$unique_storage@U?$resource_policy@PEAU_ITEMIDLIST_RELATIVE@@P6AXPEAU1@@Z$1?ILFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>(void)
0x1800314d0  nop
0x1800314d1  cmp     [rsp+138h+var_100], r12
0x1800314d6  jz      short loc_1800314E2
0x1800314d8  lea     rcx, [rsp+138h+var_100]
0x1800314dd  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x1800314e2  mov     eax, ebx
0x1800314e4  jmp     loc_1800317A1
0x1800314e9  cmp     [rsp+138h+var_F8], r12
0x1800314ee  jz      short loc_1800314FA
0x1800314f0  lea     rcx, [rsp+138h+var_F8]
0x1800314f5  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x1800314fa  lea     r8, [rsp+138h+var_F8]; ppv
0x1800314ff  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180031506  mov     rcx, [rsp+138h+pidl]; pidl
0x18003150b  call    cs:__imp_SHCreateItemFromIDList
0x180031511  mov     ebx, eax
0x180031513  test    eax, eax
0x180031515  jns     short loc_180031569
0x180031517  mov     rcx, [rsp+138h]; this
0x18003151f  mov     r9d, eax; char *
0x180031522  lea     r8, aShellExtZipArc_8; "shell\\ext\\zip\\archive\\archiveextrac"...
0x180031529  mov     edx, 6FBh; void *
0x18003152e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031533  nop
0x180031534  cmp     [rsp+138h+var_F8], r12
0x180031539  jz      short loc_180031546
0x18003153b  lea     rcx, [rsp+138h+var_F8]
0x180031540  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x180031545  nop
0x180031546  lea     rcx, [rsp+138h+pidl]
0x18003154b  call    ??1?$unique_storage@U?$resource_policy@PEAU_ITEMIDLIST_RELATIVE@@P6AXPEAU1@@Z$1?ILFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>(void)
0x180031550  nop
0x180031551  cmp     [rsp+138h+var_100], r12
0x180031556  jz      short loc_180031562
0x180031558  lea     rcx, [rsp+138h+var_100]
0x18003155d  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x180031562  mov     eax, ebx
0x180031564  jmp     loc_1800317A1
0x180031569  mov     [rsp+138h+pv], r12
0x18003156e  mov     rdi, [rsp+138h+var_F8]
0x180031573  mov     rax, [rdi]
0x180031576  mov     rbx, [rax+28h]
0x18003157a  xor     edx, edx
0x18003157c  lea     rcx, [rsp+138h+pv]
0x180031581  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180031586  lea     r8, [rsp+138h+pv]
0x18003158b  mov     edx, 80058000h
0x180031590  mov     rcx, rdi
0x180031593  mov     rax, rbx
0x180031596  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003159b  mov     ebx, eax
0x18003159d  test    eax, eax
0x18003159f  jns     short loc_180031604
0x1800315a1  mov     rcx, [rsp+138h]; this
0x1800315a9  mov     r9d, eax; char *
0x1800315ac  lea     r8, aShellExtZipArc_8; "shell\\ext\\zip\\archive\\archiveextrac"...
0x1800315b3  mov     edx, 6FFh; void *
0x1800315b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800315bd  nop
0x1800315be  mov     rcx, [rsp+138h+pv]; pv
0x1800315c3  test    rcx, rcx
0x1800315c6  jz      short loc_1800315CF
0x1800315c8  call    cs:__imp_CoTaskMemFree
0x1800315ce  nop
0x1800315cf  cmp     [rsp+138h+var_F8], r12
0x1800315d4  jz      short loc_1800315E1
0x1800315d6  lea     rcx, [rsp+138h+var_F8]
0x1800315db  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x1800315e0  nop
0x1800315e1  lea     rcx, [rsp+138h+pidl]
0x1800315e6  call    ??1?$unique_storage@U?$resource_policy@PEAU_ITEMIDLIST_RELATIVE@@P6AXPEAU1@@Z$1?ILFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>(void)
0x1800315eb  nop
0x1800315ec  cmp     [rsp+138h+var_100], r12
0x1800315f1  jz      short loc_1800315FD
0x1800315f3  lea     rcx, [rsp+138h+var_100]
0x1800315f8  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x1800315fd  mov     eax, ebx
0x1800315ff  jmp     loc_1800317A1
0x180031604  lea     rax, [rsp+138h+var_B8]
0x18003160c  mov     rdx, [rsp+138h+pv]
0x180031611  mov     r8, rdx
0x180031614  sub     r8, rax
0x180031617  movzx   ecx, word ptr [rax]
0x18003161a  movzx   r9d, word ptr [rax+r8]
0x18003161f  sub     ecx, r9d
0x180031622  jnz     short loc_18003162D
0x180031624  add     rax, 2
0x180031628  test    r9d, r9d
0x18003162b  jnz     short loc_180031617
0x18003162d  test    ecx, ecx
0x18003162f  jz      loc_1800316B5
0x180031635  lea     rcx, [rsp+138h+var_E0]
0x18003163a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003163f  nop
0x180031640  mov     rdx, [rsp+138h+var_D0]
0x180031645  test    rdx, rdx
0x180031648  jz      short loc_18003166E
0x18003164a  lea     rcx, [rsp+138h+var_E0]
0x18003164f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180031654  mov     ebx, 5Ch ; '\'
0x180031659  cmp     [rax+rdx*2-2], bx
0x18003165e  jz      short loc_180031673
0x180031660  mov     edx, ebx
0x180031662  lea     rcx, [rsp+138h+var_E0]
0x180031667  call    ?push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z; std::wstring::push_back(ushort)
0x18003166c  jmp     short loc_180031673
0x18003166e  mov     ebx, 5Ch ; '\'
0x180031673  lea     rcx, [r15+r14*2]
0x180031677  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18003167c  mov     r8, rax
0x18003167f  mov     rdx, rcx
0x180031682  lea     rcx, [rsp+138h+var_E0]
0x180031687  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18003168c  lea     rax, [rsp+138h+var_E0]
0x180031691  cmp     rax, rsi
0x180031694  jz      short loc_1800316A4
0x180031696  mov     rdx, rsi
0x180031699  lea     rcx, [rsp+138h+var_E0]
0x18003169e  call    ?_Swap_data@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXAEAV12@@Z; std::wstring::_Swap_data(std::wstring &)
0x1800316a3  nop
0x1800316a4  lea     rcx, [rsp+138h+var_E0]
0x1800316a9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800316ae  mov     rdx, [rsp+138h+pv]
0x1800316b3  jmp     short loc_1800316BA
0x1800316b5  mov     ebx, 5Ch ; '\'
0x1800316ba  mov     rcx, rsi
0x1800316bd  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800316c2  mov     rcx, [rsi+10h]
0x1800316c6  cmp     [rax+rcx*2-2], bx
0x1800316cb  jz      short loc_1800316DC
0x1800316cd  mov     edx, ebx
0x1800316cf  mov     rcx, rsi
0x1800316d2  call    ?push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z; std::wstring::push_back(ushort)
0x1800316d7  mov     rdx, [rsp+138h+pv]
0x1800316dc  mov     r8, [r13+38h]
0x1800316e0  cmp     r8, 1
0x1800316e4  jbe     short loc_18003175C
0x1800316e6  mov     rcx, rsi
0x1800316e9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800316ee  cmp     word ptr [rax+r8*2-4], 2Eh ; '.'
0x1800316f5  jnz     short loc_18003175C
0x1800316f7  mov     rcx, [rsp+138h]; this
0x1800316ff  mov     ebx, 80070057h
0x180031704  mov     r9d, ebx; char *
0x180031707  lea     r8, aShellExtZipArc_8; "shell\\ext\\zip\\archive\\archiveextrac"...
0x18003170e  mov     edx, 716h; void *
0x180031713  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031718  nop
0x180031719  mov     rcx, [rsp+138h+pv]; pv
0x18003171e  test    rcx, rcx
  ... truncated ...
```
