# Wsp::Facade::FileServerFacade::CreateFileServer(WSP_SUBSYSTEM_TYPE,std::unique_ptr<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::default_delete<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const &,std::unique_ptr<std::vector<ushort,std::allocator<ushort>>,std::default_delete<std::vector<ushort,std::allocator<ushort>>>> const &,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const &)

- ea: `0x180053464`
- end: `0x180053753`
- name: `?CreateFileServer@FileServerFacade@Facade@Wsp@@SA?AV?$shared_ptr@VFileServerFacade@Facade@Wsp@@@std@@W4WSP_SUBSYSTEM_TYPE@@AEBV?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@5@AEBV?$unique_ptr@V?$vector@GV?$allocator@G@std@@@std@@U?$default_delete@V?$vector@GV?$allocator@G@std@@@std@@@2@@5@AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@5@@Z`
- size: `751`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18004e440`

## callees

- `0x180002a70`
- `0x1800034a4`
- `0x180005e68`
- `0x18000c168`
- `0x18000c284`
- `0x18000d920`
- `0x18000dc28`
- `0x18003aa54`
- `0x18003e574`
- `0x18004798c`
- `0x1800479d4`
- `0x1800532c8`
- `0x180053464`
- `0x1800a9010`

## string_xrefs

- `0x180053693`: `Unsupported protocol specified.`
- `0x180053713`: `Cluster FileServer Resource Type not installed.`
- `0x1800536d3`: `Invalid number of protocols ( only 1 supported ).`
- `0x180053613`: `CreateFileServer is does not support that storage subsystem / protocol combination.`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
_QWORD *__fastcall Wsp::Facade::FileServerFacade::CreateFileServer(
        _QWORD *a1,
        int a2,
        __int64 a3,
        _QWORD **a4,
        _QWORD *a5)
{
  _QWORD *v7; // rax
  _QWORD *Instance; // rax
  _QWORD *FileShareFactory; // rax
  char v10; // si
  _QWORD *v11; // rax
  _QWORD *v12; // rax
  __int64 v13; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  _QWORD *v25; // [rsp+30h] [rbp-D0h] BYREF
  int v26; // [rsp+38h] [rbp-C8h]
  __int64 v27; // [rsp+40h] [rbp-C0h] BYREF
  std::_Ref_count_base *v28; // [rsp+48h] [rbp-B8h]
  _BYTE v29[8]; // [rsp+50h] [rbp-B0h] BYREF
  std::_Ref_count_base *v30; // [rsp+58h] [rbp-A8h]
  _BYTE v31[8]; // [rsp+60h] [rbp-A0h] BYREF
  std::_Ref_count_base *v32; // [rsp+68h] [rbp-98h]
  _BYTE v33[8]; // [rsp+70h] [rbp-90h] BYREF
  std::_Ref_count_base *v34; // [rsp+78h] [rbp-88h]
  _BYTE pExceptionObject[112]; // [rsp+90h] [rbp-70h] BYREF

  v25 = a1;
  v26 = 1;
  if ( a5[1] - *a5 != 32 )
  {
    v17 = std::wstring::wstring(v33, L"Invalid number of host names ( only 1 supported ).");
    v18 = cxl::MIError(&v25, 4, v17);
    cxl::Error(pExceptionObject, v18);
    throw (cxl::Exception *)pExceptionObject;
  }
  v7 = *a4;
  if ( *a4 )
  {
    if ( v7[1] - *v7 != 2 )
    {
      v21 = std::wstring::wstring(v33, L"Invalid number of protocols ( only 1 supported ).");
      v22 = cxl::SMResult(&v25, 58014, v21);
      cxl::Error(pExceptionObject, v22);
      throw (cxl::Exception *)pExceptionObject;
    }
    if ( *(_WORD *)*v7 != 3 )
    {
      v19 = std::wstring::wstring(v33, L"Unsupported protocol specified.");
      v20 = cxl::SMResult(&v25, 58014, v19);
      cxl::Error(pExceptionObject, v20);
      throw (cxl::Exception *)pExceptionObject;
    }
  }
  if ( a2 != 1 )
  {
    v15 = std::wstring::wstring(
            v33,
            L"CreateFileServer is does not support that storage subsystem / protocol combination.");
    v16 = cxl::SMResult(&v25, 58010, v15);
    cxl::Error(pExceptionObject, v16);
    throw (cxl::Exception *)pExceptionObject;
  }
  Instance = (_QWORD *)Wsp::Singleton::GetInstance(v31);
  FileShareFactory = (_QWORD *)Wsp::Singleton::GetFileShareFactory(*Instance, v29);
  v10 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*FileShareFactory + 48LL))(*FileShareFactory);
  if ( v30 )
    std::_Ref_count_base::_Decref(v30);
  if ( v32 )
    std::_Ref_count_base::_Decref(v32);
  if ( !v10 )
  {
    v23 = std::wstring::wstring(v33, L"Cluster FileServer Resource Type not installed.");
    v24 = cxl::WinError(&v25, 5078, v23);
    cxl::Error(pExceptionObject, v24);
    throw (cxl::Exception *)pExceptionObject;
  }
  *a1 = 0;
  a1[1] = 0;
  v26 = 1;
  v11 = (_QWORD *)Wsp::Singleton::GetInstance(v29);
  v12 = (_QWORD *)Wsp::Singleton::GetFileShareFactory(*v11, v31);
  (*(void (__fastcall **)(_QWORD, __int64 *, _QWORD, __int64))(*(_QWORD *)*v12 + 56LL))(*v12, &v27, *a5, a3);
  if ( v32 )
    std::_Ref_count_base::_Decref(v32);
  if ( v30 )
    std::_Ref_count_base::_Decref(v30);
  if ( v27 )
  {
    v13 = std::make_shared<Wsp::Facade::FileServerFacade,std::shared_ptr<Wsp::Facade::IFileServer>>(v33, &v27);
    std::shared_ptr<ClusWmi::DataStore>::operator=(a1, v13);
    if ( v34 )
      std::_Ref_count_base::_Decref(v34);
  }
  if ( v28 )
    std::_Ref_count_base::_Decref(v28);
  return a1;
}

```

## disassembly

```asm
0x180053464  mov     [rsp-8+arg_8], rbx
0x180053469  mov     [rsp-8+arg_18], rsi
0x18005346e  push    rbp
0x18005346f  push    rdi
0x180053470  push    r14
0x180053472  lea     rbp, [rsp-10h]
0x180053477  sub     rsp, 110h
0x18005347e  mov     rax, cs:__security_cookie
0x180053485  xor     rax, rsp
0x180053488  mov     [rbp+20h+var_20], rax
0x18005348c  mov     r14, r8
0x18005348f  mov     rbx, rcx
0x180053492  mov     rdi, [rbp+20h+arg_20]
0x180053496  mov     [rsp+120h+var_F0], rcx
0x18005349b  mov     [rsp+120h+var_E8], 1
0x1800534a3  mov     rax, [rdi+8]
0x1800534a7  sub     rax, [rdi]
0x1800534aa  cmp     rax, 20h ; ' '
0x1800534ae  jnz     loc_180053653
0x1800534b4  mov     rax, [r9]
0x1800534b7  test    rax, rax
0x1800534ba  jz      short loc_1800534E4
0x1800534bc  mov     rcx, [rax]
0x1800534bf  mov     rax, [rax+8]
0x1800534c3  sub     rax, rcx
0x1800534c6  cmp     rax, 2
0x1800534ca  jnz     loc_1800536D3
0x1800534d0  movzx   ecx, word ptr [rcx]
0x1800534d3  sub     ecx, eax
0x1800534d5  jz      loc_180053693
0x1800534db  cmp     ecx, 1
0x1800534de  jnz     loc_180053693
0x1800534e4  cmp     edx, 1
0x1800534e7  jnz     loc_180053613
0x1800534ed  lea     rcx, [rsp+120h+var_C0]
0x1800534f2  call    ?GetInstance@Singleton@Wsp@@SA?AV?$shared_ptr@VSingleton@Wsp@@@std@@XZ; Wsp::Singleton::GetInstance(void)
0x1800534f7  nop
0x1800534f8  lea     rdx, [rsp+120h+var_D0]
0x1800534fd  mov     rcx, [rax]
0x180053500  call    ?GetFileShareFactory@Singleton@Wsp@@QEBA?AV?$shared_ptr@VIFileShareFactory@Facade@Wsp@@@std@@XZ; Wsp::Singleton::GetFileShareFactory(void)
0x180053505  nop
0x180053506  mov     rcx, [rax]
0x180053509  mov     rax, [rcx]
0x18005350c  mov     rax, [rax+30h]
0x180053510  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053515  mov     sil, al
0x180053518  mov     rcx, [rsp+120h+var_C8]; this
0x18005351d  test    rcx, rcx
0x180053520  jz      short loc_180053528
0x180053522  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180053527  nop
0x180053528  mov     rcx, [rsp+120h+var_B8]; this
0x18005352d  test    rcx, rcx
0x180053530  jz      short loc_180053537
0x180053532  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180053537  test    sil, sil
0x18005353a  jz      loc_180053713
0x180053540  mov     qword ptr [rbx], 0
0x180053547  mov     qword ptr [rbx+8], 0
0x18005354f  mov     [rsp+120h+var_E8], 1
0x180053557  lea     rcx, [rsp+120h+var_D0]
0x18005355c  call    ?GetInstance@Singleton@Wsp@@SA?AV?$shared_ptr@VSingleton@Wsp@@@std@@XZ; Wsp::Singleton::GetInstance(void)
0x180053561  nop
0x180053562  lea     rdx, [rsp+120h+var_C0]
0x180053567  mov     rcx, [rax]
0x18005356a  call    ?GetFileShareFactory@Singleton@Wsp@@QEBA?AV?$shared_ptr@VIFileShareFactory@Facade@Wsp@@@std@@XZ; Wsp::Singleton::GetFileShareFactory(void)
0x18005356f  nop
0x180053570  mov     rcx, [rax]
0x180053573  mov     rax, [rcx]
0x180053576  mov     r9, r14
0x180053579  mov     r8, [rdi]
0x18005357c  lea     rdx, [rsp+120h+var_E0]
0x180053581  mov     rax, [rax+38h]
0x180053585  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005358a  nop
0x18005358b  mov     rcx, [rsp+120h+var_B8]; this
0x180053590  test    rcx, rcx
0x180053593  jz      short loc_18005359B
0x180053595  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005359a  nop
0x18005359b  mov     rcx, [rsp+120h+var_C8]; this
0x1800535a0  test    rcx, rcx
0x1800535a3  jz      short loc_1800535AA
0x1800535a5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800535aa  cmp     [rsp+120h+var_E0], 0
0x1800535b0  jz      short loc_1800535DC
0x1800535b2  lea     rdx, [rsp+120h+var_E0]
0x1800535b7  lea     rcx, [rsp+120h+var_B0]
0x1800535bc  call    ??$make_shared@VFileServerFacade@Facade@Wsp@@V?$shared_ptr@UIFileServer@Facade@Wsp@@@std@@@std@@YA?AV?$shared_ptr@VFileServerFacade@Facade@Wsp@@@0@$$QEAV?$shared_ptr@UIFileServer@Facade@Wsp@@@0@@Z; std::make_shared<Wsp::Facade::FileServerFacade,std::shared_ptr<Wsp::Facade::IFileServer>>(std::shared_ptr<Wsp::Facade::IFileServer> &&)
0x1800535c1  mov     rdx, rax
0x1800535c4  mov     rcx, rbx
0x1800535c7  call    ??4?$shared_ptr@VDataStore@ClusWmi@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<ClusWmi::DataStore>::operator=(std::shared_ptr<ClusWmi::DataStore> &&)
0x1800535cc  mov     rcx, [rsp+120h+var_A8]; this
0x1800535d1  test    rcx, rcx
0x1800535d4  jz      short loc_1800535DC
0x1800535d6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800535db  nop
0x1800535dc  mov     rcx, [rsp+120h+var_D8]; this
0x1800535e1  test    rcx, rcx
0x1800535e4  jz      short loc_1800535EC
0x1800535e6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800535eb  nop
0x1800535ec  mov     rax, rbx
0x1800535ef  mov     rcx, [rbp+20h+var_20]
0x1800535f3  xor     rcx, rsp; StackCookie
0x1800535f6  call    __security_check_cookie
0x1800535fb  lea     r11, [rsp+120h+var_10]
0x180053603  mov     rbx, [r11+28h]
0x180053607  mov     rsi, [r11+38h]
0x18005360b  mov     rsp, r11
0x18005360e  pop     r14
0x180053610  pop     rdi
0x180053611  pop     rbp
0x180053612  retn
0x180053613  lea     rdx, aCreatefileserv_0; "CreateFileServer is does not support th"...
0x18005361a  lea     rcx, [rsp+120h+var_B0]
0x18005361f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180053624  mov     r8, rax
0x180053627  mov     edx, 0E29Ah
0x18005362c  lea     rcx, [rsp+120h+var_F0]
0x180053631  call    ?SMResult@cxl@@YA?AVErrorCode@1@H@Z; cxl::SMResult(int)
0x180053636  mov     rdx, rax
0x180053639  lea     rcx, [rbp+20h+pExceptionObject]
0x18005363d  call    ?Error@cxl@@YA?AVException@1@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Error(cxl::ErrorCode const &,std::wstring const &)
0x180053642  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180053649  lea     rcx, [rbp+20h+pExceptionObject]; pExceptionObject
0x18005364d  call    _CxxThrowException_0
0x180053653  lea     rdx, aInvalidNumberO; "Invalid number of host names ( only 1 s"...
0x18005365a  lea     rcx, [rsp+120h+var_B0]
0x18005365f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180053664  mov     r8, rax
0x180053667  mov     edx, 4
0x18005366c  lea     rcx, [rsp+120h+var_F0]
0x180053671  call    ?MIError@cxl@@YA?AVErrorCode@1@H@Z; cxl::MIError(int)
0x180053676  mov     rdx, rax
0x180053679  lea     rcx, [rbp+20h+pExceptionObject]
0x18005367d  call    ?Error@cxl@@YA?AVException@1@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Error(cxl::ErrorCode const &,std::wstring const &)
0x180053682  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180053689  lea     rcx, [rbp+20h+pExceptionObject]; pExceptionObject
0x18005368d  call    _CxxThrowException_0
0x180053693  lea     rdx, aUnsupportedPro; "Unsupported protocol specified."
0x18005369a  lea     rcx, [rsp+120h+var_B0]
0x18005369f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800536a4  mov     r8, rax
0x1800536a7  mov     edx, 0E29Eh
0x1800536ac  lea     rcx, [rsp+120h+var_F0]
0x1800536b1  call    ?SMResult@cxl@@YA?AVErrorCode@1@H@Z; cxl::SMResult(int)
0x1800536b6  mov     rdx, rax
0x1800536b9  lea     rcx, [rbp+20h+pExceptionObject]
0x1800536bd  call    ?Error@cxl@@YA?AVException@1@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Error(cxl::ErrorCode const &,std::wstring const &)
0x1800536c2  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x1800536c9  lea     rcx, [rbp+20h+pExceptionObject]; pExceptionObject
0x1800536cd  call    _CxxThrowException_0
0x1800536d3  lea     rdx, aInvalidNumberO_0; "Invalid number of protocols ( only 1 su"...
0x1800536da  lea     rcx, [rsp+120h+var_B0]
0x1800536df  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800536e4  mov     r8, rax
0x1800536e7  mov     edx, 0E29Eh
0x1800536ec  lea     rcx, [rsp+120h+var_F0]
0x1800536f1  call    ?SMResult@cxl@@YA?AVErrorCode@1@H@Z; cxl::SMResult(int)
0x1800536f6  mov     rdx, rax
0x1800536f9  lea     rcx, [rbp+20h+pExceptionObject]
0x1800536fd  call    ?Error@cxl@@YA?AVException@1@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Error(cxl::ErrorCode const &,std::wstring const &)
0x180053702  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180053709  lea     rcx, [rbp+20h+pExceptionObject]; pExceptionObject
0x18005370d  call    _CxxThrowException_0
0x180053713  lea     rdx, aClusterFileser; "Cluster FileServer Resource Type not in"...
0x18005371a  lea     rcx, [rsp+120h+var_B0]
0x18005371f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180053724  mov     r8, rax
0x180053727  mov     edx, 13D6h
0x18005372c  lea     rcx, [rsp+120h+var_F0]
0x180053731  call    ?WinError@cxl@@YA?AVErrorCode@1@H@Z; cxl::WinError(int)
0x180053736  mov     rdx, rax
0x180053739  lea     rcx, [rbp+20h+pExceptionObject]
0x18005373d  call    ?Error@cxl@@YA?AVException@1@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Error(cxl::ErrorCode const &,std::wstring const &)
0x180053742  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180053749  lea     rcx, [rbp+20h+pExceptionObject]; pExceptionObject
0x18005374d  call    _CxxThrowException_0
```
