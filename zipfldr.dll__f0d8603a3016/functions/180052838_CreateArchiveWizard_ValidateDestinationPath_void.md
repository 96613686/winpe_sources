# CreateArchiveWizard::ValidateDestinationPath(void)

- ea: `0x180052838`
- end: `0x180052d8b`
- name: `?ValidateDestinationPath@CreateArchiveWizard@@AEAAJXZ`
- size: `1363`
- prototype: `__int64 __fastcall(CreateArchiveWizard *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180051400`

## callees

- `0x1800126a0`
- `0x180020cbc`
- `0x1800210b0`
- `0x180021f0c`
- `0x180022a34`
- `0x180024a24`
- `0x18002abd0`
- `0x180030a3c`
- `0x180031e94`
- `0x1800350cc`
- `0x180036f50`
- `0x180048d3c`
- `0x180052838`
- `0x180071010`

## import_xrefs

- `SHELL32!SHCreateItemFromIDList` at `0x180052b61`
- `SHELL32!SHCreateItemFromIDList` at `0x180052b61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052c1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052d20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052c1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052d20`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800529c8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800529c8`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x18005292a`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x18005292a`

## string_xrefs

- `0x180052884`: `shell\ext\zip\archive\createarchivewizard.cpp`
- `0x1800528c2`: `shell\ext\zip\archive\createarchivewizard.cpp`
- `0x1800528fa`: `shell\ext\zip\archive\createarchivewizard.cpp`
- `0x180052941`: `shell\ext\zip\archive\createarchivewizard.cpp`
- `0x18005298d`: `shell\ext\zip\archive\createarchivewizard.cpp`
- `0x1800529df`: `shell\ext\zip\archive\createarchivewizard.cpp`
- `0x180052a24`: `shell\ext\zip\archive\createarchivewizard.cpp`
- `0x180052a98`: `shell\ext\zip\archive\createarchivewizard.cpp`
- `0x180052af8`: `shell\ext\zip\archive\createarchivewizard.cpp`
- `0x180052b78`: `shell\ext\zip\archive\createarchivewizard.cpp`
- `0x180052c02`: `shell\ext\zip\archive\createarchivewizard.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall CreateArchiveWizard::ValidateDestinationPath(CreateArchiveWizard *this)
{
  __int128 *v1; // rsi
  __int64 v3; // rax
  __int64 v4; // rdx
  __int64 v5; // rax
  __int64 v6; // rdx
  const WCHAR *v7; // r15
  HRESULT v8; // eax
  unsigned int v9; // ebx
  unsigned __int64 v10; // r14
  int v11; // eax
  unsigned int v12; // ebx
  HRESULT v13; // eax
  unsigned int v14; // ebx
  int v15; // eax
  unsigned int v16; // ebx
  int v17; // eax
  int v18; // eax
  unsigned int v19; // ebx
  __int64 v20; // rax
  int v21; // eax
  unsigned int v22; // ebx
  HRESULT v23; // eax
  unsigned int v24; // ebx
  void *v25; // rdi
  __int64 (__fastcall *v26)(void *, __int64, LPVOID *); // rbx
  int v27; // eax
  unsigned int v28; // ebx
  unsigned __int16 *v29; // rax
  void *v30; // rcx
  int v31; // r9d
  int v32; // r8d
  __int64 v33; // rax
  __int64 v34; // r8
  const WCHAR *v35; // rdx
  __int64 v36; // r8
  __int128 v37; // xmm2
  __int128 v38; // xmm3
  int ppv; // [rsp+20h] [rbp-D8h]
  int ppva; // [rsp+20h] [rbp-D8h]
  PCWSTR ppszRootEnd; // [rsp+30h] [rbp-C8h] BYREF
  LPVOID v42; // [rsp+38h] [rbp-C0h] BYREF
  void *v43; // [rsp+40h] [rbp-B8h] BYREF
  LPCITEMIDLIST pidl; // [rsp+48h] [rbp-B0h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-A8h] BYREF
  __int128 v46; // [rsp+58h] [rbp-A0h] BYREF
  __int128 v47; // [rsp+68h] [rbp-90h]
  unsigned __int16 v48[32]; // [rsp+80h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v1 = (__int128 *)((char *)this + 40);
  if ( *((_QWORD *)this + 7) )
  {
    v3 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 40);
    if ( *(_WORD *)(v3 + 2 * v4 - 2) == 92 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2DA,
        (unsigned int)"shell\\ext\\zip\\archive\\createarchivewizard.cpp",
        (const char *)0x80070057LL,
        ppv);
      return 2147942487LL;
    }
    else
    {
      v5 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v1);
      if ( *(_WORD *)(v5 + 2 * v6 - 2) == 46 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2DB,
          (unsigned int)"shell\\ext\\zip\\archive\\createarchivewizard.cpp",
          (const char *)0x80070057LL,
          ppv);
        return 2147942487LL;
      }
      else
      {
        v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v1);
        ppszRootEnd = 0;
        v8 = PathCchSkipRoot(v7, &ppszRootEnd);
        v9 = v8;
        if ( v8 >= 0 )
        {
          v10 = ppszRootEnd - v7;
          v11 = StringCchCopyNW(v48, 0x20u, v7, v10);
          v12 = v11;
          if ( v11 >= 0 )
          {
            v42 = 0;
            v13 = CoCreateInstance(&CLSID_ShellUrl, 0, 1u, &GUID_4f33718d_bae1_4f9b_96f2_d2a16e683346, &v42);
            v14 = v13;
            if ( v13 >= 0 )
            {
              v15 = SetDefaultShellPath(v42);
              v16 = v15;
              if ( v15 >= 0 )
              {
                v17 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v42 + 184LL))(v42, 0);
                v18 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *, _QWORD))(*(_QWORD *)v42 + 24LL))(
                        v42,
                        v48,
                        v17 | 0x85u);
                v19 = v18;
                if ( v18 >= 0 )
                {
                  pidl = 0;
                  v43 = 0;
                  v20 = *(_QWORD *)v42;
                  pidl = 0;
                  v21 = (*(__int64 (__fastcall **)(LPVOID, LPCITEMIDLIST *))(v20 + 56))(v42, &pidl);
                  v22 = v21;
                  if ( v21 >= 0 )
                  {
                    if ( v43 )
                      winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v43);
                    v23 = SHCreateItemFromIDList(pidl, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &v43);
                    v24 = v23;
                    if ( v23 >= 0 )
                    {
                      pv = 0;
                      v25 = v43;
                      v26 = *(__int64 (__fastcall **)(void *, __int64, LPVOID *))(*(_QWORD *)v43 + 40LL);
                      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                        &pv,
                        0);
                      v27 = v26(v25, 2147844096LL, &pv);
                      v28 = v27;
                      if ( v27 >= 0 )
                      {
                        v29 = v48;
                        v30 = pv;
                        do
                        {
                          v31 = *(unsigned __int16 *)((char *)v29 + (_BYTE *)pv - (_BYTE *)v48);
                          v32 = *v29 - v31;
                          if ( v32 )
                            break;
                          ++v29;
                        }
                        while ( v31 );
                        if ( v32 )
                        {
                          std::wstring::wstring(&v46, pv);
                          if ( (_QWORD)v47 )
                          {
                            v33 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v46);
                            if ( *(_WORD *)(v33 + 2 * v34 - 2) != 92 )
                              std::wstring::push_back(&v46);
                          }
                          v35 = &v7[v10];
                          v36 = -1;
                          do
                            ++v36;
                          while ( v35[v36] );
                          std::wstring::_Append<unsigned short>(&v46, v35, v36);
                          if ( &v46 != v1 )
                          {
                            v37 = v46;
                            v38 = v47;
                            v46 = *v1;
                            v47 = v1[1];
                            *v1 = v37;
                            v1[1] = v38;
                          }
                          std::wstring::_Tidy_deallocate(&v46);
                          v30 = pv;
                        }
                        if ( v30 )
                          CoTaskMemFree(v30);
                        if ( v43 )
                          winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v43);
                        wil::details::unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&void ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&void ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>(&pidl);
                        if ( v42 )
                          winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v42);
                        return 0;
                      }
                      else
                      {
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)0x2F4,
                          (unsigned int)"shell\\ext\\zip\\archive\\createarchivewizard.cpp",
                          (const char *)(unsigned int)v27,
                          ppva);
                        if ( pv )
                          CoTaskMemFree(pv);
                        if ( v43 )
                          winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v43);
                        wil::details::unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&void ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&void ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>(&pidl);
                        if ( v42 )
                          winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v42);
                        return v28;
                      }
                    }
                    else
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x2F0,
                        (unsigned int)"shell\\ext\\zip\\archive\\createarchivewizard.cpp",
                        (const char *)(unsigned int)v23,
                        ppva);
                      if ( v43 )
                        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v43);
                      wil::details::unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&void ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&void ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>(&pidl);
                      if ( v42 )
                        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v42);
                      return v24;
                    }
                  }
                  else
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x2EF,
                      (unsigned int)"shell\\ext\\zip\\archive\\createarchivewizard.cpp",
                      (const char *)(unsigned int)v21,
                      ppva);
                    if ( v43 )
                      winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v43);
                    wil::details::unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&void ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&void ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>(&pidl);
                    if ( v42 )
                      winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v42);
                    return v22;
                  }
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x2EB,
                    (unsigned int)"shell\\ext\\zip\\archive\\createarchivewizard.cpp",
                    (const char *)(unsigned int)v18,
                    ppva);
                  if ( v42 )
                    winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v42);
                  return v19;
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x2E8,
                  (unsigned int)"shell\\ext\\zip\\archive\\createarchivewizard.cpp",
                  (const char *)(unsigned int)v15,
                  ppva);
                if ( v42 )
                  winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v42);
                return v16;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x2E7,
                (unsigned int)"shell\\ext\\zip\\archive\\createarchivewizard.cpp",
                (const char *)(unsigned int)v13,
                ppva);
              if ( v42 )
                winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v42);
              return v14;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2E4,
              (unsigned int)"shell\\ext\\zip\\archive\\createarchivewizard.cpp",
              (const char *)(unsigned int)v11,
              ppv);
            return v12;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2E0,
            (unsigned int)"shell\\ext\\zip\\archive\\createarchivewizard.cpp",
            (const char *)(unsigned int)v8,
            ppv);
          return v9;
        }
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D9,
      (unsigned int)"shell\\ext\\zip\\archive\\createarchivewizard.cpp",
      (const char *)0x80070057LL,
      ppv);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180052838  mov     [rsp+arg_8], rbx
0x18005283d  mov     [rsp+arg_10], rsi
0x180052842  push    rdi
0x180052843  push    r12
0x180052845  push    r13
0x180052847  push    r14
0x180052849  push    r15
0x18005284b  sub     rsp, 0D0h
0x180052852  mov     rax, cs:__security_cookie
0x180052859  xor     rax, rsp
0x18005285c  mov     [rsp+0F8h+var_38], rax
0x180052864  lea     rsi, [rcx+28h]
0x180052868  mov     rdx, [rsi+10h]
0x18005286c  xor     r12d, r12d
0x18005286f  test    rdx, rdx
0x180052872  jnz     short loc_18005289C
0x180052874  mov     rcx, [rsp+0F8h]; this
0x18005287c  mov     ebx, 80070057h
0x180052881  mov     r9d, ebx; char *
0x180052884  lea     r8, aShellExtZipArc_1; "shell\\ext\\zip\\archive\\createarchive"...
0x18005288b  mov     edx, 2D9h; void *
0x180052890  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052895  mov     eax, ebx
0x180052897  jmp     loc_180052D5D
0x18005289c  mov     rcx, rsi
0x18005289f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800528a4  mov     r13d, 5Ch ; '\'
0x1800528aa  cmp     [rax+rdx*2-2], r13w
0x1800528b0  jnz     short loc_1800528DA
0x1800528b2  mov     rcx, [rsp+0F8h]; this
0x1800528ba  mov     ebx, 80070057h
0x1800528bf  mov     r9d, ebx; char *
0x1800528c2  lea     r8, aShellExtZipArc_1; "shell\\ext\\zip\\archive\\createarchive"...
0x1800528c9  mov     edx, 2DAh; void *
0x1800528ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800528d3  mov     eax, ebx
0x1800528d5  jmp     loc_180052D5D
0x1800528da  mov     rcx, rsi
0x1800528dd  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800528e2  cmp     word ptr [rax+rdx*2-2], 2Eh ; '.'
0x1800528e8  jnz     short loc_180052912
0x1800528ea  mov     rcx, [rsp+0F8h]; this
0x1800528f2  mov     ebx, 80070057h
0x1800528f7  mov     r9d, ebx; char *
0x1800528fa  lea     r8, aShellExtZipArc_1; "shell\\ext\\zip\\archive\\createarchive"...
0x180052901  mov     edx, 2DBh; void *
0x180052906  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005290b  mov     eax, ebx
0x18005290d  jmp     loc_180052D5D
0x180052912  mov     rcx, rsi
0x180052915  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005291a  mov     r15, rax
0x18005291d  mov     [rsp+0F8h+ppszRootEnd], r12
0x180052922  lea     rdx, [rsp+0F8h+ppszRootEnd]; ppszRootEnd
0x180052927  mov     rcx, rax; pszPath
0x18005292a  call    cs:__imp_PathCchSkipRoot
0x180052930  mov     ebx, eax
0x180052932  test    eax, eax
0x180052934  jns     short loc_180052959
0x180052936  mov     rcx, [rsp+0F8h]; this
0x18005293e  mov     r9d, eax; char *
0x180052941  lea     r8, aShellExtZipArc_1; "shell\\ext\\zip\\archive\\createarchive"...
0x180052948  mov     edx, 2E0h; void *
0x18005294d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052952  mov     eax, ebx
0x180052954  jmp     loc_180052D5D
0x180052959  mov     r14, [rsp+0F8h+ppszRootEnd]
0x18005295e  sub     r14, r15
0x180052961  sar     r14, 1
0x180052964  mov     r9, r14; unsigned __int64
0x180052967  mov     r8, r15; unsigned __int16 *
0x18005296a  mov     edx, 20h ; ' '; unsigned __int64
0x18005296f  lea     rcx, [rsp+0F8h+var_78]; unsigned __int16 *
0x180052977  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18005297c  mov     ebx, eax
0x18005297e  test    eax, eax
0x180052980  jns     short loc_1800529A5
0x180052982  mov     rcx, [rsp+0F8h]; this
0x18005298a  mov     r9d, eax; char *
0x18005298d  lea     r8, aShellExtZipArc_1; "shell\\ext\\zip\\archive\\createarchive"...
0x180052994  mov     edx, 2E4h; void *
0x180052999  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005299e  mov     eax, ebx
0x1800529a0  jmp     loc_180052D5D
0x1800529a5  mov     [rsp+0F8h+var_C0], r12
0x1800529aa  lea     rax, [rsp+0F8h+var_C0]
0x1800529af  mov     qword ptr [rsp+0F8h+ppv], rax; int
0x1800529b4  lea     r9, _GUID_4f33718d_bae1_4f9b_96f2_d2a16e683346; riid
0x1800529bb  xor     edx, edx; pUnkOuter
0x1800529bd  lea     r8d, [rdx+1]; dwClsContext
0x1800529c1  lea     rcx, CLSID_ShellUrl; rclsid
0x1800529c8  call    cs:__imp_CoCreateInstance
0x1800529ce  mov     ebx, eax
0x1800529d0  test    eax, eax
0x1800529d2  jns     short loc_180052A09
0x1800529d4  mov     rcx, [rsp+0F8h]; this
0x1800529dc  mov     r9d, eax; char *
0x1800529df  lea     r8, aShellExtZipArc_1; "shell\\ext\\zip\\archive\\createarchive"...
0x1800529e6  mov     edx, 2E7h; void *
0x1800529eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800529f0  nop
0x1800529f1  cmp     [rsp+0F8h+var_C0], r12
0x1800529f6  jz      short loc_180052A02
0x1800529f8  lea     rcx, [rsp+0F8h+var_C0]
0x1800529fd  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x180052a02  mov     eax, ebx
0x180052a04  jmp     loc_180052D5D
0x180052a09  mov     rcx, [rsp+0F8h+var_C0]
0x180052a0e  call    SetDefaultShellPath
0x180052a13  mov     ebx, eax
0x180052a15  test    eax, eax
0x180052a17  jns     short loc_180052A4E
0x180052a19  mov     rcx, [rsp+0F8h]; this
0x180052a21  mov     r9d, eax; char *
0x180052a24  lea     r8, aShellExtZipArc_1; "shell\\ext\\zip\\archive\\createarchive"...
0x180052a2b  mov     edx, 2E8h; void *
0x180052a30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052a35  nop
0x180052a36  cmp     [rsp+0F8h+var_C0], r12
0x180052a3b  jz      short loc_180052A47
0x180052a3d  lea     rcx, [rsp+0F8h+var_C0]
0x180052a42  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x180052a47  mov     eax, ebx
0x180052a49  jmp     loc_180052D5D
0x180052a4e  mov     rcx, [rsp+0F8h+var_C0]
0x180052a53  mov     rax, [rcx]
0x180052a56  xor     edx, edx
0x180052a58  mov     rax, [rax+0B8h]
0x180052a5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052a64  mov     r8d, eax
0x180052a67  mov     rcx, [rsp+0F8h+var_C0]
0x180052a6c  mov     rax, [rcx]
0x180052a6f  or      r8d, 85h
0x180052a76  lea     rdx, [rsp+0F8h+var_78]
0x180052a7e  mov     rax, [rax+18h]
0x180052a82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052a87  mov     ebx, eax
0x180052a89  test    eax, eax
0x180052a8b  jns     short loc_180052AC2
0x180052a8d  mov     rcx, [rsp+0F8h]; this
0x180052a95  mov     r9d, eax; char *
0x180052a98  lea     r8, aShellExtZipArc_1; "shell\\ext\\zip\\archive\\createarchive"...
0x180052a9f  mov     edx, 2EBh; void *
0x180052aa4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052aa9  nop
0x180052aaa  cmp     [rsp+0F8h+var_C0], r12
0x180052aaf  jz      short loc_180052ABB
0x180052ab1  lea     rcx, [rsp+0F8h+var_C0]
0x180052ab6  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x180052abb  mov     eax, ebx
0x180052abd  jmp     loc_180052D5D
0x180052ac2  mov     [rsp+0F8h+pidl], r12
0x180052ac7  mov     [rsp+0F8h+var_B8], r12
0x180052acc  mov     rcx, [rsp+0F8h+var_C0]
0x180052ad1  mov     rax, [rcx]
0x180052ad4  mov     [rsp+0F8h+pidl], r12
0x180052ad9  lea     rdx, [rsp+0F8h+pidl]
0x180052ade  mov     rax, [rax+38h]
0x180052ae2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052ae7  mov     ebx, eax
0x180052ae9  test    eax, eax
0x180052aeb  jns     short loc_180052B3F
0x180052aed  mov     rcx, [rsp+0F8h]; this
0x180052af5  mov     r9d, eax; char *
0x180052af8  lea     r8, aShellExtZipArc_1; "shell\\ext\\zip\\archive\\createarchive"...
0x180052aff  mov     edx, 2EFh; void *
0x180052b04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052b09  nop
0x180052b0a  cmp     [rsp+0F8h+var_B8], r12
0x180052b0f  jz      short loc_180052B1C
0x180052b11  lea     rcx, [rsp+0F8h+var_B8]
0x180052b16  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x180052b1b  nop
0x180052b1c  lea     rcx, [rsp+0F8h+pidl]
0x180052b21  call    ??1?$unique_storage@U?$resource_policy@PEAU_ITEMIDLIST_RELATIVE@@P6AXPEAU1@@Z$1?ILFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>(void)
0x180052b26  nop
0x180052b27  cmp     [rsp+0F8h+var_C0], r12
0x180052b2c  jz      short loc_180052B38
0x180052b2e  lea     rcx, [rsp+0F8h+var_C0]
0x180052b33  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x180052b38  mov     eax, ebx
0x180052b3a  jmp     loc_180052D5D
0x180052b3f  cmp     [rsp+0F8h+var_B8], r12
0x180052b44  jz      short loc_180052B50
0x180052b46  lea     rcx, [rsp+0F8h+var_B8]
0x180052b4b  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x180052b50  lea     r8, [rsp+0F8h+var_B8]; ppv
0x180052b55  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180052b5c  mov     rcx, [rsp+0F8h+pidl]; pidl
0x180052b61  call    cs:__imp_SHCreateItemFromIDList
0x180052b67  mov     ebx, eax
0x180052b69  test    eax, eax
0x180052b6b  jns     short loc_180052BBF
0x180052b6d  mov     rcx, [rsp+0F8h]; this
0x180052b75  mov     r9d, eax; char *
0x180052b78  lea     r8, aShellExtZipArc_1; "shell\\ext\\zip\\archive\\createarchive"...
0x180052b7f  mov     edx, 2F0h; void *
0x180052b84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052b89  nop
0x180052b8a  cmp     [rsp+0F8h+var_B8], r12
0x180052b8f  jz      short loc_180052B9C
0x180052b91  lea     rcx, [rsp+0F8h+var_B8]
0x180052b96  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x180052b9b  nop
0x180052b9c  lea     rcx, [rsp+0F8h+pidl]
0x180052ba1  call    ??1?$unique_storage@U?$resource_policy@PEAU_ITEMIDLIST_RELATIVE@@P6AXPEAU1@@Z$1?ILFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>(void)
0x180052ba6  nop
0x180052ba7  cmp     [rsp+0F8h+var_C0], r12
0x180052bac  jz      short loc_180052BB8
0x180052bae  lea     rcx, [rsp+0F8h+var_C0]
0x180052bb3  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x180052bb8  mov     eax, ebx
0x180052bba  jmp     loc_180052D5D
0x180052bbf  mov     [rsp+0F8h+pv], r12
0x180052bc4  mov     rdi, [rsp+0F8h+var_B8]
0x180052bc9  mov     rax, [rdi]
0x180052bcc  mov     rbx, [rax+28h]
0x180052bd0  xor     edx, edx
0x180052bd2  lea     rcx, [rsp+0F8h+pv]
0x180052bd7  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180052bdc  lea     r8, [rsp+0F8h+pv]
0x180052be1  mov     edx, 80058000h
0x180052be6  mov     rcx, rdi
0x180052be9  mov     rax, rbx
0x180052bec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052bf1  mov     ebx, eax
0x180052bf3  test    eax, eax
0x180052bf5  jns     short loc_180052C5A
0x180052bf7  mov     rcx, [rsp+0F8h]; this
0x180052bff  mov     r9d, eax; char *
0x180052c02  lea     r8, aShellExtZipArc_1; "shell\\ext\\zip\\archive\\createarchive"...
0x180052c09  mov     edx, 2F4h; void *
0x180052c0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052c13  nop
0x180052c14  mov     rcx, [rsp+0F8h+pv]; pv
0x180052c19  test    rcx, rcx
0x180052c1c  jz      short loc_180052C25
0x180052c1e  call    cs:__imp_CoTaskMemFree
0x180052c24  nop
0x180052c25  cmp     [rsp+0F8h+var_B8], r12
0x180052c2a  jz      short loc_180052C37
0x180052c2c  lea     rcx, [rsp+0F8h+var_B8]
0x180052c31  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x180052c36  nop
0x180052c37  lea     rcx, [rsp+0F8h+pidl]
0x180052c3c  call    ??1?$unique_storage@U?$resource_policy@PEAU_ITEMIDLIST_RELATIVE@@P6AXPEAU1@@Z$1?ILFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_ITEMIDLIST_RELATIVE *,void (*)(_ITEMIDLIST_RELATIVE *),&ILFree(_ITEMIDLIST_RELATIVE *),wistd::integral_constant<unsigned __int64,0>,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,0,std::nullptr_t>>(void)
0x180052c41  nop
0x180052c42  cmp     [rsp+0F8h+var_C0], r12
0x180052c47  jz      short loc_180052C53
0x180052c49  lea     rcx, [rsp+0F8h+var_C0]
0x180052c4e  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x180052c53  mov     eax, ebx
0x180052c55  jmp     loc_180052D5D
0x180052c5a  lea     rax, [rsp+0F8h+var_78]
0x180052c62  mov     rcx, [rsp+0F8h+pv]
0x180052c67  mov     rdx, rcx
0x180052c6a  sub     rdx, rax
0x180052c6d  movzx   r8d, word ptr [rax]
0x180052c71  movzx   r9d, word ptr [rax+rdx]
0x180052c76  sub     r8d, r9d
0x180052c79  jnz     short loc_180052C84
0x180052c7b  add     rax, 2
0x180052c7f  test    r9d, r9d
0x180052c82  jnz     short loc_180052C6D
0x180052c84  test    r8d, r8d
0x180052c87  jz      loc_180052D1B
0x180052c8d  mov     rdx, rcx
0x180052c90  lea     rcx, [rsp+0F8h+var_A0]
0x180052c95  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180052c9a  nop
0x180052c9b  mov     r8, qword ptr [rsp+0F8h+var_90]
0x180052ca0  test    r8, r8
0x180052ca3  jz      short loc_180052CC4
0x180052ca5  lea     rcx, [rsp+0F8h+var_A0]
0x180052caa  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180052caf  cmp     [rax+r8*2-2], r13w
0x180052cb5  jz      short loc_180052CC4
0x180052cb7  mov     edx, r13d
0x180052cba  lea     rcx, [rsp+0F8h+var_A0]
0x180052cbf  call    ?push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z; std::wstring::push_back(ushort)
0x180052cc4  lea     rdx, [r15+r14*2]
0x180052cc8  or      r8, 0FFFFFFFFFFFFFFFFh
0x180052ccc  inc     r8
0x180052ccf  cmp     [rdx+r8*2], r12w
0x180052cd4  jnz     short loc_180052CCC
0x180052cd6  lea     rcx, [rsp+0F8h+var_A0]
0x180052cdb  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180052ce0  lea     rax, [rsp+0F8h+var_A0]
0x180052ce5  cmp     rax, rsi
0x180052ce8  jz      short loc_180052D0C
0x180052cea  movups  xmm2, [rsp+0F8h+var_A0]
0x180052cef  movups  xmm3, [rsp+0F8h+var_90]
0x180052cf4  movups  xmm0, xmmword ptr [rsi]
0x180052cf7  movups  [rsp+0F8h+var_A0], xmm0
0x180052cfc  movups  xmm1, xmmword ptr [rsi+10h]
0x180052d00  movups  [rsp+0F8h+var_90], xmm1
0x180052d05  movups  xmmword ptr [rsi], xmm2
0x180052d08  movups  xmmword ptr [rsi+10h], xmm3
0x180052d0c  lea     rcx, [rsp+0F8h+var_A0]
0x180052d11  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
  ... truncated ...
```
