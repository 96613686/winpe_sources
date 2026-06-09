# _SleepStudy::TryLoadSrumApi_::_2_::_lambda_1_::operator()

- ea: `0x18002e694`
- end: `0x18002e89a`
- name: `_SleepStudy::TryLoadSrumApi_::_2_::_lambda_1_::operator()`
- size: `518`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x1800b0760`

## callees

- `0x18002e694`
- `0x18002e8a0`
- `0x18002e94c`
- `0x1800612a8`
- `0x1800612c8`
- `0x1800b04d8`
- `0x1800f7010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002e6ba`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002e6ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002e6da`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002e74b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002e7bc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002e6da`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002e74b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002e7bc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002e883`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002e883`

## string_xrefs

- `0x18002e86a`: `onecoreuap\net\wcm\service\base\server\sleepstudy.cpp`
- `0x18002e6ad`: `srumapi.dll`
- `0x18002e6d0`: `SruUpdateStats`

## pseudocode

```c
void __fastcall SleepStudy::TryLoadSrumApi_::_2_::_lambda_1_::operator()(HMODULE a1)
{
  HMODULE Library; // rax
  const char *v2; // r9
  HMODULE v3; // rbx
  FARPROC ProcAddress; // rax
  _QWORD *v5; // rdx
  FARPROC v6; // rax
  _QWORD *v7; // rdx
  FARPROC v8; // rax
  _QWORD *v9; // rdx
  _QWORD v10[7]; // [rsp+20h] [rbp-69h] BYREF
  _QWORD *v11; // [rsp+58h] [rbp-31h]
  _QWORD v12[7]; // [rsp+60h] [rbp-29h] BYREF
  _QWORD *v13; // [rsp+98h] [rbp+Fh]
  _QWORD v14[7]; // [rsp+A0h] [rbp+17h] BYREF
  _QWORD *v15; // [rsp+D8h] [rbp+4Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]
  HMODULE v17; // [rsp+F0h] [rbp+67h] BYREF
  __int64 v18; // [rsp+F8h] [rbp+6Fh] BYREF

  v17 = a1;
  Library = LoadLibraryExW(L"srumapi.dll", 0, 0x800u);
  v17 = Library;
  v3 = Library;
  if ( !Library )
    goto LABEL_18;
  ProcAddress = GetProcAddress(Library, "SruUpdateStats");
  v11 = 0;
  if ( ProcAddress )
  {
    v10[1] = ProcAddress;
    v10[0] = &std::_Func_impl_no_alloc<unsigned long (*)(enum _SRU_PROVIDER_CLASS),unsigned long,enum _SRU_PROVIDER_CLASS>::`vftable';
    v11 = v10;
  }
  std::_Func_class<unsigned long,enum _SRU_PROVIDER_CLASS>::_Swap(v10, qword_18013F510);
  if ( v11 )
  {
    v5 = v10;
    LOBYTE(v5) = v11 != v10;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v11 + 32LL))(v11, v5);
  }
  if ( !qword_18013F548 )
    goto LABEL_18;
  v6 = GetProcAddress(v3, "SruQueryStats");
  v13 = 0;
  if ( v6 )
  {
    v12[1] = v6;
    v12[0] = &std::_Func_impl_no_alloc<unsigned long (*)(enum _SRU_PROVIDER_CLASS,_SYSTEMTIME *,_SYSTEMTIME *,unsigned long,_SRU_STATS_RECORD_SET * *),unsigned long,enum _SRU_PROVIDER_CLASS,_SYSTEMTIME *,_SYSTEMTIME *,unsigned long,_SRU_STATS_RECORD_SET * *>::`vftable';
    v13 = v12;
  }
  std::_Func_class<unsigned long,enum _SRU_PROVIDER_CLASS>::_Swap(v12, qword_18013F550);
  if ( v13 )
  {
    v7 = v12;
    LOBYTE(v7) = v13 != v12;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v13 + 32LL))(v13, v7);
  }
  if ( !qword_18013F588 )
    goto LABEL_18;
  v8 = GetProcAddress(v3, "SruFreeRecordSet");
  v15 = 0;
  if ( v8 )
  {
    v14[1] = v8;
    v14[0] = &std::_Func_impl_no_alloc<void (*)(_SRU_STATS_RECORD_SET *),void,_SRU_STATS_RECORD_SET *>::`vftable';
    v15 = v14;
  }
  std::_Func_class<void,_SRU_STATS_RECORD_SET *>::_Swap(v14, qword_18013F590);
  if ( v15 )
  {
    v9 = v14;
    LOBYTE(v9) = v15 != v14;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v15 + 32LL))(v15, v9);
  }
  if ( qword_18013F5C8 )
  {
    v18 = qword_18013F508;
    qword_18013F508 = 0;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::operator=(
      &qword_18013F508,
      &v17);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::operator=(
      &v17,
      &v18);
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v18);
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v17);
  }
  else
  {
LABEL_18:
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0x98,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\sleepstudy.cpp",
      v2);
    if ( v3 )
      FreeLibrary(v3);
  }
}

```

## disassembly

```asm
0x18002e694  mov     [rsp-8+arg_10], rbx
0x18002e699  mov     [rsp-8+arg_0], rcx
0x18002e69e  push    rbp
0x18002e69f  lea     rbp, [rsp-57h]
0x18002e6a4  sub     rsp, 0E0h
0x18002e6ab  xor     edx, edx; hFile
0x18002e6ad  lea     rcx, LibFileName; "srumapi.dll"
0x18002e6b4  mov     r8d, 800h; dwFlags
0x18002e6ba  call    cs:__imp_LoadLibraryExW
0x18002e6c0  mov     [rbp+57h+arg_0], rax
0x18002e6c4  mov     rbx, rax
0x18002e6c7  test    rax, rax
0x18002e6ca  jz      loc_18002E866
0x18002e6d0  lea     rdx, ProcName; "SruUpdateStats"
0x18002e6d7  mov     rcx, rax; hModule
0x18002e6da  call    cs:__imp_GetProcAddress
0x18002e6e0  mov     [rbp+57h+var_88], 0
0x18002e6e8  test    rax, rax
0x18002e6eb  jz      short loc_18002E704
0x18002e6ed  mov     [rbp+57h+var_B8], rax
0x18002e6f1  lea     rcx, ??_7?$_Func_impl_no_alloc@P6AKW4_SRU_PROVIDER_CLASS@@@ZKW41@@std@@6B@; const std::_Func_impl_no_alloc<ulong (*)(_SRU_PROVIDER_CLASS),ulong,_SRU_PROVIDER_CLASS>::`vftable'
0x18002e6f8  lea     rax, [rbp+57h+var_C0]
0x18002e6fc  mov     [rbp+57h+var_C0], rcx
0x18002e700  mov     [rbp+57h+var_88], rax
0x18002e704  lea     rdx, qword_18013F510
0x18002e70b  lea     rcx, [rbp+57h+var_C0]
0x18002e70f  call    ?_Swap@?$_Func_class@KW4_SRU_PROVIDER_CLASS@@@std@@IEAAXAEAV12@@Z; std::_Func_class<ulong,_SRU_PROVIDER_CLASS>::_Swap(std::_Func_class<ulong,_SRU_PROVIDER_CLASS> &)
0x18002e714  mov     rcx, [rbp+57h+var_88]
0x18002e718  test    rcx, rcx
0x18002e71b  jz      short loc_18002E733
0x18002e71d  mov     rax, [rcx]
0x18002e720  lea     rdx, [rbp+57h+var_C0]
0x18002e724  cmp     rcx, rdx
0x18002e727  setnz   dl
0x18002e72a  mov     rax, [rax+20h]
0x18002e72e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e733  cmp     cs:qword_18013F548, 0
0x18002e73b  jz      loc_18002E866
0x18002e741  lea     rdx, aSruquerystats; "SruQueryStats"
0x18002e748  mov     rcx, rbx; hModule
0x18002e74b  call    cs:__imp_GetProcAddress
0x18002e751  mov     [rbp+57h+var_48], 0
0x18002e759  test    rax, rax
0x18002e75c  jz      short loc_18002E775
0x18002e75e  mov     [rbp+57h+var_78], rax
0x18002e762  lea     rcx, ??_7?$_Func_impl_no_alloc@P6AKW4_SRU_PROVIDER_CLASS@@PEAU_SYSTEMTIME@@1KPEAPEAU_SRU_STATS_RECORD_SET@@@ZKW41@PEAU2@PEAU2@KPEAPEAU3@@std@@6B@; const std::_Func_impl_no_alloc<ulong (*)(_SRU_PROVIDER_CLASS,_SYSTEMTIME *,_SYSTEMTIME *,ulong,_SRU_STATS_RECORD_SET * *),ulong,_SRU_PROVIDER_CLASS,_SYSTEMTIME *,_SYSTEMTIME *,ulong,_SRU_STATS_RECORD_SET * *>::`vftable'
0x18002e769  lea     rax, [rbp+57h+var_80]
0x18002e76d  mov     [rbp+57h+var_80], rcx
0x18002e771  mov     [rbp+57h+var_48], rax
0x18002e775  lea     rdx, qword_18013F550
0x18002e77c  lea     rcx, [rbp+57h+var_80]
0x18002e780  call    ?_Swap@?$_Func_class@KW4_SRU_PROVIDER_CLASS@@@std@@IEAAXAEAV12@@Z; std::_Func_class<ulong,_SRU_PROVIDER_CLASS>::_Swap(std::_Func_class<ulong,_SRU_PROVIDER_CLASS> &)
0x18002e785  mov     rcx, [rbp+57h+var_48]
0x18002e789  test    rcx, rcx
0x18002e78c  jz      short loc_18002E7A4
0x18002e78e  mov     rax, [rcx]
0x18002e791  lea     rdx, [rbp+57h+var_80]
0x18002e795  cmp     rcx, rdx
0x18002e798  setnz   dl
0x18002e79b  mov     rax, [rax+20h]
0x18002e79f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e7a4  cmp     cs:qword_18013F588, 0
0x18002e7ac  jz      loc_18002E866
0x18002e7b2  lea     rdx, aSrufreerecords; "SruFreeRecordSet"
0x18002e7b9  mov     rcx, rbx; hModule
0x18002e7bc  call    cs:__imp_GetProcAddress
0x18002e7c2  mov     [rbp+57h+var_8], 0
0x18002e7ca  test    rax, rax
0x18002e7cd  jz      short loc_18002E7E6
0x18002e7cf  mov     [rbp+57h+var_38], rax
0x18002e7d3  lea     rcx, ??_7?$_Func_impl_no_alloc@P6AXPEAU_SRU_STATS_RECORD_SET@@@ZXPEAU1@@std@@6B@; const std::_Func_impl_no_alloc<void (*)(_SRU_STATS_RECORD_SET *),void,_SRU_STATS_RECORD_SET *>::`vftable'
0x18002e7da  lea     rax, [rbp+57h+var_40]
0x18002e7de  mov     [rbp+57h+var_40], rcx
0x18002e7e2  mov     [rbp+57h+var_8], rax
0x18002e7e6  lea     rdx, qword_18013F590
0x18002e7ed  lea     rcx, [rbp+57h+var_40]
0x18002e7f1  call    ?_Swap@?$_Func_class@XPEAU_SRU_STATS_RECORD_SET@@@std@@IEAAXAEAV12@@Z; std::_Func_class<void,_SRU_STATS_RECORD_SET *>::_Swap(std::_Func_class<void,_SRU_STATS_RECORD_SET *> &)
0x18002e7f6  mov     rcx, [rbp+57h+var_8]
0x18002e7fa  test    rcx, rcx
0x18002e7fd  jz      short loc_18002E815
0x18002e7ff  mov     rax, [rcx]
0x18002e802  lea     rdx, [rbp+57h+var_40]
0x18002e806  cmp     rcx, rdx
0x18002e809  setnz   dl
0x18002e80c  mov     rax, [rax+20h]
0x18002e810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e815  cmp     cs:qword_18013F5C8, 0
0x18002e81d  jz      short loc_18002E866
0x18002e81f  mov     rax, cs:qword_18013F508
0x18002e826  lea     rdx, [rbp+57h+arg_0]
0x18002e82a  lea     rcx, qword_18013F508
0x18002e831  mov     [rbp+57h+arg_8], rax
0x18002e835  mov     cs:qword_18013F508, 0
0x18002e840  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> &&)
0x18002e845  lea     rdx, [rbp+57h+arg_8]
0x18002e849  lea     rcx, [rbp+57h+arg_0]
0x18002e84d  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> &&)
0x18002e852  lea     rcx, [rbp+57h+arg_8]
0x18002e856  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18002e85b  lea     rcx, [rbp+57h+arg_0]
0x18002e85f  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18002e864  jmp     short loc_18002E889
0x18002e866  mov     rcx, [rbp+5Fh]; this
0x18002e86a  lea     r8, aOnecoreuapNetW_22; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x18002e871  mov     edx, 98h; void *
0x18002e876  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18002e87b  test    rbx, rbx
0x18002e87e  jz      short loc_18002E889
0x18002e880  mov     rcx, rbx; hLibModule
0x18002e883  call    cs:__imp_FreeLibrary
0x18002e889  mov     rbx, [rsp+0E0h+arg_10]
0x18002e891  add     rsp, 0E0h
0x18002e898  pop     rbp
0x18002e899  retn
```
