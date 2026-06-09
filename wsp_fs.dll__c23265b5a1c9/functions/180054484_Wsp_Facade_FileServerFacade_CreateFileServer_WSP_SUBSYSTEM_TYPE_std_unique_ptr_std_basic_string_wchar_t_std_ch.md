# Wsp::Facade::FileServerFacade::CreateFileServer(WSP_SUBSYSTEM_TYPE,std::unique_ptr<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::default_delete<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const &,std::unique_ptr<std::vector<ushort,std::allocator<ushort>>,std::default_delete<std::vector<ushort,std::allocator<ushort>>>> const &,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const &)

- ea: `0x180054484`
- end: `0x180054774`
- name: `?CreateFileServer@FileServerFacade@Facade@Wsp@@SA?AV?$shared_ptr@VFileServerFacade@Facade@Wsp@@@std@@W4WSP_SUBSYSTEM_TYPE@@AEBV?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@5@AEBV?$unique_ptr@V?$vector@GV?$allocator@G@std@@@std@@U?$default_delete@V?$vector@GV?$allocator@G@std@@@std@@@2@@5@AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@5@@Z`
- size: `752`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18004f480`

## callees

- `0x180002ad0`
- `0x180003534`
- `0x180005fdc`
- `0x18000c4ac`
- `0x18000c5c4`
- `0x18000dcc4`
- `0x18000dffc`
- `0x18003bdc0`
- `0x18003f8b4`
- `0x180048b4c`
- `0x180048b94`
- `0x1800542ec`
- `0x180054484`
- `0x1800ab010`

## string_xrefs

- `0x1800546f4`: `Invalid number of protocols ( only 1 supported ).`
- `0x180054634`: `CreateFileServer is does not support that storage subsystem / protocol combination.`
- `0x1800546b4`: `Unsupported protocol specified.`
- `0x180054734`: `Cluster FileServer Resource Type not installed.`

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
0x180054484  mov     [rsp-8+arg_8], rbx
0x180054489  mov     [rsp-8+arg_18], rsi
0x18005448e  push    rbp
0x18005448f  push    rdi
0x180054490  push    r14
0x180054492  lea     rbp, [rsp-10h]
0x180054497  sub     rsp, 110h
0x18005449e  mov     rax, cs:__security_cookie
0x1800544a5  xor     rax, rsp
0x1800544a8  mov     [rbp+20h+var_20], rax
0x1800544ac  mov     r14, r8
0x1800544af  mov     rbx, rcx
0x1800544b2  mov     rdi, [rbp+20h+arg_20]
0x1800544b6  mov     [rsp+120h+var_F0], rcx
0x1800544bb  mov     [rsp+120h+var_E8], 1
0x1800544c3  mov     rax, [rdi+8]
0x1800544c7  sub     rax, [rdi]
0x1800544ca  cmp     rax, 20h ; ' '
0x1800544ce  jnz     loc_180054674
0x1800544d4  mov     rax, [r9]
0x1800544d7  test    rax, rax
0x1800544da  jz      short loc_180054504
0x1800544dc  mov     rcx, [rax]
0x1800544df  mov     rax, [rax+8]
0x1800544e3  sub     rax, rcx
0x1800544e6  cmp     rax, 2
0x1800544ea  jnz     loc_1800546F4
0x1800544f0  movzx   ecx, word ptr [rcx]
0x1800544f3  sub     ecx, eax
0x1800544f5  jz      loc_1800546B4
0x1800544fb  cmp     ecx, 1
0x1800544fe  jnz     loc_1800546B4
0x180054504  cmp     edx, 1
0x180054507  jnz     loc_180054634
0x18005450d  lea     rcx, [rsp+120h+var_C0]
0x180054512  call    ?GetInstance@Singleton@Wsp@@SA?AV?$shared_ptr@VSingleton@Wsp@@@std@@XZ; Wsp::Singleton::GetInstance(void)
0x180054517  nop
0x180054518  lea     rdx, [rsp+120h+var_D0]
0x18005451d  mov     rcx, [rax]
0x180054520  call    ?GetFileShareFactory@Singleton@Wsp@@QEBA?AV?$shared_ptr@VIFileShareFactory@Facade@Wsp@@@std@@XZ; Wsp::Singleton::GetFileShareFactory(void)
0x180054525  nop
0x180054526  mov     rcx, [rax]
0x180054529  mov     rax, [rcx]
0x18005452c  mov     rax, [rax+30h]
0x180054530  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054535  mov     sil, al
0x180054538  mov     rcx, [rsp+120h+var_C8]; this
0x18005453d  test    rcx, rcx
0x180054540  jz      short loc_180054548
0x180054542  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180054547  nop
0x180054548  mov     rcx, [rsp+120h+var_B8]; this
0x18005454d  test    rcx, rcx
0x180054550  jz      short loc_180054557
0x180054552  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180054557  test    sil, sil
0x18005455a  jz      loc_180054734
0x180054560  mov     qword ptr [rbx], 0
0x180054567  mov     qword ptr [rbx+8], 0
0x18005456f  mov     [rsp+120h+var_E8], 1
0x180054577  lea     rcx, [rsp+120h+var_D0]
0x18005457c  call    ?GetInstance@Singleton@Wsp@@SA?AV?$shared_ptr@VSingleton@Wsp@@@std@@XZ; Wsp::Singleton::GetInstance(void)
0x180054581  nop
0x180054582  lea     rdx, [rsp+120h+var_C0]
0x180054587  mov     rcx, [rax]
0x18005458a  call    ?GetFileShareFactory@Singleton@Wsp@@QEBA?AV?$shared_ptr@VIFileShareFactory@Facade@Wsp@@@std@@XZ; Wsp::Singleton::GetFileShareFactory(void)
0x18005458f  nop
0x180054590  mov     rcx, [rax]
0x180054593  mov     rax, [rcx]
0x180054596  mov     r9, r14
0x180054599  mov     r8, [rdi]
0x18005459c  lea     rdx, [rsp+120h+var_E0]
0x1800545a1  mov     rax, [rax+38h]
0x1800545a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800545aa  nop
0x1800545ab  mov     rcx, [rsp+120h+var_B8]; this
0x1800545b0  test    rcx, rcx
0x1800545b3  jz      short loc_1800545BB
0x1800545b5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800545ba  nop
0x1800545bb  mov     rcx, [rsp+120h+var_C8]; this
0x1800545c0  test    rcx, rcx
0x1800545c3  jz      short loc_1800545CA
0x1800545c5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800545ca  cmp     [rsp+120h+var_E0], 0
0x1800545d0  jz      short loc_1800545FC
0x1800545d2  lea     rdx, [rsp+120h+var_E0]
0x1800545d7  lea     rcx, [rsp+120h+var_B0]
0x1800545dc  call    ??$make_shared@VFileServerFacade@Facade@Wsp@@V?$shared_ptr@UIFileServer@Facade@Wsp@@@std@@@std@@YA?AV?$shared_ptr@VFileServerFacade@Facade@Wsp@@@0@$$QEAV?$shared_ptr@UIFileServer@Facade@Wsp@@@0@@Z; std::make_shared<Wsp::Facade::FileServerFacade,std::shared_ptr<Wsp::Facade::IFileServer>>(std::shared_ptr<Wsp::Facade::IFileServer> &&)
0x1800545e1  mov     rdx, rax
0x1800545e4  mov     rcx, rbx
0x1800545e7  call    ??4?$shared_ptr@VDataStore@ClusWmi@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<ClusWmi::DataStore>::operator=(std::shared_ptr<ClusWmi::DataStore> &&)
0x1800545ec  mov     rcx, [rsp+120h+var_A8]; this
0x1800545f1  test    rcx, rcx
0x1800545f4  jz      short loc_1800545FC
0x1800545f6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800545fb  nop
0x1800545fc  mov     rcx, [rsp+120h+var_D8]; this
0x180054601  test    rcx, rcx
0x180054604  jz      short loc_18005460C
0x180054606  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005460b  nop
0x18005460c  mov     rax, rbx
0x18005460f  mov     rcx, [rbp+20h+var_20]
0x180054613  xor     rcx, rsp; StackCookie
0x180054616  call    __security_check_cookie
0x18005461b  lea     r11, [rsp+120h+var_10]
0x180054623  mov     rbx, [r11+28h]
0x180054627  mov     rsi, [r11+38h]
0x18005462b  mov     rsp, r11
0x18005462e  pop     r14
0x180054630  pop     rdi
0x180054631  pop     rbp
0x180054632  retn
0x180054634  lea     rdx, aCreatefileserv_0; "CreateFileServer is does not support th"...
0x18005463b  lea     rcx, [rsp+120h+var_B0]
0x180054640  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180054645  mov     r8, rax
0x180054648  mov     edx, 0E29Ah
0x18005464d  lea     rcx, [rsp+120h+var_F0]
0x180054652  call    ?SMResult@cxl@@YA?AVErrorCode@1@H@Z; cxl::SMResult(int)
0x180054657  mov     rdx, rax
0x18005465a  lea     rcx, [rbp+20h+pExceptionObject]
0x18005465e  call    ?Error@cxl@@YA?AVException@1@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Error(cxl::ErrorCode const &,std::wstring const &)
0x180054663  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18005466a  lea     rcx, [rbp+20h+pExceptionObject]; pExceptionObject
0x18005466e  call    _CxxThrowException_0
0x180054674  lea     rdx, aInvalidNumberO; "Invalid number of host names ( only 1 s"...
0x18005467b  lea     rcx, [rsp+120h+var_B0]
0x180054680  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180054685  mov     r8, rax
0x180054688  mov     edx, 4
0x18005468d  lea     rcx, [rsp+120h+var_F0]
0x180054692  call    ?MIError@cxl@@YA?AVErrorCode@1@H@Z; cxl::MIError(int)
0x180054697  mov     rdx, rax
0x18005469a  lea     rcx, [rbp+20h+pExceptionObject]
0x18005469e  call    ?Error@cxl@@YA?AVException@1@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Error(cxl::ErrorCode const &,std::wstring const &)
0x1800546a3  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x1800546aa  lea     rcx, [rbp+20h+pExceptionObject]; pExceptionObject
0x1800546ae  call    _CxxThrowException_0
0x1800546b4  lea     rdx, aUnsupportedPro; "Unsupported protocol specified."
0x1800546bb  lea     rcx, [rsp+120h+var_B0]
0x1800546c0  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800546c5  mov     r8, rax
0x1800546c8  mov     edx, 0E29Eh
0x1800546cd  lea     rcx, [rsp+120h+var_F0]
0x1800546d2  call    ?SMResult@cxl@@YA?AVErrorCode@1@H@Z; cxl::SMResult(int)
0x1800546d7  mov     rdx, rax
0x1800546da  lea     rcx, [rbp+20h+pExceptionObject]
0x1800546de  call    ?Error@cxl@@YA?AVException@1@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Error(cxl::ErrorCode const &,std::wstring const &)
0x1800546e3  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x1800546ea  lea     rcx, [rbp+20h+pExceptionObject]; pExceptionObject
0x1800546ee  call    _CxxThrowException_0
0x1800546f4  lea     rdx, aInvalidNumberO_0; "Invalid number of protocols ( only 1 su"...
0x1800546fb  lea     rcx, [rsp+120h+var_B0]
0x180054700  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180054705  mov     r8, rax
0x180054708  mov     edx, 0E29Eh
0x18005470d  lea     rcx, [rsp+120h+var_F0]
0x180054712  call    ?SMResult@cxl@@YA?AVErrorCode@1@H@Z; cxl::SMResult(int)
0x180054717  mov     rdx, rax
0x18005471a  lea     rcx, [rbp+20h+pExceptionObject]
0x18005471e  call    ?Error@cxl@@YA?AVException@1@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Error(cxl::ErrorCode const &,std::wstring const &)
0x180054723  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18005472a  lea     rcx, [rbp+20h+pExceptionObject]; pExceptionObject
0x18005472e  call    _CxxThrowException_0
0x180054734  lea     rdx, aClusterFileser; "Cluster FileServer Resource Type not in"...
0x18005473b  lea     rcx, [rsp+120h+var_B0]
0x180054740  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180054745  mov     r8, rax
0x180054748  mov     edx, 13D6h
0x18005474d  lea     rcx, [rsp+120h+var_F0]
0x180054752  call    ?WinError@cxl@@YA?AVErrorCode@1@H@Z; cxl::WinError(int)
0x180054757  mov     rdx, rax
0x18005475a  lea     rcx, [rbp+20h+pExceptionObject]
0x18005475e  call    ?Error@cxl@@YA?AVException@1@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Error(cxl::ErrorCode const &,std::wstring const &)
0x180054763  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18005476a  lea     rcx, [rbp+20h+pExceptionObject]; pExceptionObject
0x18005476e  call    _CxxThrowException_0
```
