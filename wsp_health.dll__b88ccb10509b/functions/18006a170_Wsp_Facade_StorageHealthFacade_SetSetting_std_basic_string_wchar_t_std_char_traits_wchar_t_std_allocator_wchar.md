# Wsp::Facade::StorageHealthFacade::SetSetting(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x18006a170`
- end: `0x18006a32e`
- name: `?SetSetting@StorageHealthFacade@Facade@Wsp@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z`
- size: `446`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task`

## callers

- `0x180053198`

## callees

- `0x180002ae0`
- `0x180002f00`
- `0x180003520`
- `0x18000c9f0`
- `0x18000cad8`
- `0x18000d618`
- `0x180067ca8`
- `0x18006a170`
- `0x1800774b0`
- `0x180077d68`
- `0x18007825c`
- `0x180079368`

## string_xrefs

- `0x18006a293`: `No connection to the Health Service.`
- `0x18006a257`: `The Health Service is not online.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall Wsp::Facade::StorageHealthFacade::SetSetting(__int64 a1, __int64 a2, __int64 a3)
{
  Wsp::Health::ResClient *v5; // rax
  Wsp::Health::ResClient *v6; // rax
  Wsp::Health::ResClient *v7; // rbx
  unsigned int v8; // edx
  const wchar_t *v9; // rax
  Wsp::Health::HealthConfiguration *v10; // rcx
  const wchar_t *v11; // r8
  void *v12; // r9
  int result; // eax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  int v18; // [rsp+20h] [rbp-69h] BYREF
  int v19; // [rsp+24h] [rbp-65h]
  _BYTE v20[40]; // [rsp+28h] [rbp-61h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+50h] [rbp-39h] BYREF

  if ( !(unsigned int)Wsp::Facade::StorageHealthFacade::GetSubsystemType(a1) )
  {
    v17 = std::wstring::wstring(v20, L"non highlyavailable subsystems are not supported");
    v18 = 59001;
    v19 = 7;
    cxl::Exception::Exception(pExceptionObject, &v18, v17);
    throw (cxl::Exception *)pExceptionObject;
  }
  if ( !Wsp::Health::g_ptrHealthClient )
  {
    v5 = (Wsp::Health::ResClient *)operator new(0x160u);
    v6 = (Wsp::Health::ResClient *)Wsp::Health::ResClient::ResClient(v5);
    v7 = v6;
    if ( v6 )
    {
      if ( (int)Wsp::Health::ResClient::Initialize(v6) >= 0 )
        Wsp::Health::g_ptrHealthClient = v7;
      else
        Wsp::Health::ResClient::`scalar deleting destructor'(v7, v8);
    }
  }
  std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a3);
  v9 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a2);
  result = Wsp::Health::HealthConfiguration::AddSetting(v10, v9, v11, v12);
  if ( result < 0 )
  {
    if ( result != -2147024786 )
    {
      if ( result != -2147019892 )
      {
        v14 = std::wstring::wstring(v20, L"The operation failed");
        v18 = 4;
        v19 = 7;
        cxl::Exception::Exception(pExceptionObject, &v18, v14);
        throw (cxl::Exception *)pExceptionObject;
      }
      v15 = std::wstring::wstring(v20, L"The Health Service is not online.");
      v18 = 59006;
      v19 = 7;
      cxl::Exception::Exception(pExceptionObject, &v18, v15);
      throw (cxl::Exception *)pExceptionObject;
    }
    v16 = std::wstring::wstring(v20, L"No connection to the Health Service.");
    v18 = 59000;
    v19 = 7;
    cxl::Exception::Exception(pExceptionObject, &v18, v16);
    throw (cxl::Exception *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x18006a170  mov     [rsp-8+arg_18], rbx
0x18006a175  push    rbp
0x18006a176  push    rsi
0x18006a177  push    rdi
0x18006a178  lea     rbp, [rsp-47h]
0x18006a17d  sub     rsp, 0D0h
0x18006a184  mov     rax, cs:__security_cookie
0x18006a18b  xor     rax, rsp
0x18006a18e  mov     [rbp+57h+var_20], rax
0x18006a192  mov     rsi, r8
0x18006a195  mov     rdi, rdx
0x18006a198  call    ?GetSubsystemType@StorageHealthFacade@Facade@Wsp@@QEBA?BW4WSP_SUBSYSTEM_TYPE@@XZ; Wsp::Facade::StorageHealthFacade::GetSubsystemType(void)
0x18006a19d  test    eax, eax
0x18006a19f  jz      loc_18006A2CF
0x18006a1a5  cmp     cs:?g_ptrHealthClient@Health@Wsp@@3VGlobalResClientInst@12@A, 0; Wsp::Health::GlobalResClientInst Wsp::Health::g_ptrHealthClient
0x18006a1ad  jnz     short loc_18006A1E6
0x18006a1af  mov     ecx, 160h; Size
0x18006a1b4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006a1b9  mov     rcx, rax; this
0x18006a1bc  call    ??0ResClient@Health@Wsp@@QEAA@XZ; Wsp::Health::ResClient::ResClient(void)
0x18006a1c1  mov     rbx, rax
0x18006a1c4  test    rax, rax
0x18006a1c7  jz      short loc_18006A1E6
0x18006a1c9  mov     rcx, rax; this
0x18006a1cc  call    ?Initialize@ResClient@Health@Wsp@@QEAAJXZ; Wsp::Health::ResClient::Initialize(void)
0x18006a1d1  test    eax, eax
0x18006a1d3  jns     short loc_18006A1DF
0x18006a1d5  mov     rcx, rbx; this
0x18006a1d8  call    ??_GResClient@Health@Wsp@@QEAAPEAXI@Z; Wsp::Health::ResClient::`scalar deleting destructor'(uint)
0x18006a1dd  jmp     short loc_18006A1E6
0x18006a1df  mov     cs:?g_ptrHealthClient@Health@Wsp@@3VGlobalResClientInst@12@A, rbx; Wsp::Health::GlobalResClientInst Wsp::Health::g_ptrHealthClient
0x18006a1e6  mov     rcx, rsi
0x18006a1e9  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18006a1ee  mov     r8, rax
0x18006a1f1  mov     rcx, rdi
0x18006a1f4  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18006a1f9  mov     rdx, rax; wchar_t *
0x18006a1fc  call    ?AddSetting@HealthConfiguration@Health@Wsp@@QEAAJPEB_W0PEAX@Z; Wsp::Health::HealthConfiguration::AddSetting(wchar_t const *,wchar_t const *,void *)
0x18006a201  test    eax, eax
0x18006a203  jns     loc_18006A30F
0x18006a209  lea     rcx, [rbp+57h+var_B8]
0x18006a20d  cmp     eax, 8007006Eh
0x18006a212  jz      short loc_18006A293
0x18006a214  cmp     eax, 8007138Ch
0x18006a219  jz      short loc_18006A257
0x18006a21b  lea     rdx, aTheOperationFa_0; "The operation failed"
0x18006a222  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006a227  nop
0x18006a228  mov     [rbp+57h+var_C0], 4
0x18006a22f  mov     [rbp+57h+var_BC], 7
0x18006a236  mov     r8, rax
0x18006a239  lea     rdx, [rbp+57h+var_C0]
0x18006a23d  lea     rcx, [rbp+57h+pExceptionObject]
0x18006a241  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18006a246  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18006a24d  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18006a251  call    _CxxThrowException_0
0x18006a257  lea     rdx, aTheHealthServi; "The Health Service is not online."
0x18006a25e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006a263  nop
0x18006a264  mov     [rbp+57h+var_C0], 0E67Eh
0x18006a26b  mov     [rbp+57h+var_BC], 7
0x18006a272  mov     r8, rax
0x18006a275  lea     rdx, [rbp+57h+var_C0]
0x18006a279  lea     rcx, [rbp+57h+pExceptionObject]
0x18006a27d  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18006a282  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18006a289  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18006a28d  call    _CxxThrowException_0
0x18006a293  lea     rdx, aNoConnectionTo; "No connection to the Health Service."
0x18006a29a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006a29f  nop
0x18006a2a0  mov     [rbp+57h+var_C0], 0E678h
0x18006a2a7  mov     [rbp+57h+var_BC], 7
0x18006a2ae  mov     r8, rax
0x18006a2b1  lea     rdx, [rbp+57h+var_C0]
0x18006a2b5  lea     rcx, [rbp+57h+pExceptionObject]
0x18006a2b9  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18006a2be  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18006a2c5  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18006a2c9  call    _CxxThrowException_0
0x18006a2cf  lea     rdx, aNonHighlyavail; "non highlyavailable subsystems are not "...
0x18006a2d6  lea     rcx, [rbp+57h+var_B8]
0x18006a2da  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006a2df  nop
0x18006a2e0  mov     [rbp+57h+var_C0], 0E679h
0x18006a2e7  mov     [rbp+57h+var_BC], 7
0x18006a2ee  mov     r8, rax
0x18006a2f1  lea     rdx, [rbp+57h+var_C0]
0x18006a2f5  lea     rcx, [rbp+57h+pExceptionObject]
0x18006a2f9  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18006a2fe  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18006a305  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18006a309  call    _CxxThrowException_0
0x18006a30f  mov     rcx, [rbp+57h+var_20]
0x18006a313  xor     rcx, rsp; StackCookie
0x18006a316  call    __security_check_cookie
0x18006a31b  mov     rbx, [rsp+0E0h+arg_18]
0x18006a323  add     rsp, 0D0h
0x18006a32a  pop     rdi
0x18006a32b  pop     rsi
0x18006a32c  pop     rbp
0x18006a32d  retn
```
