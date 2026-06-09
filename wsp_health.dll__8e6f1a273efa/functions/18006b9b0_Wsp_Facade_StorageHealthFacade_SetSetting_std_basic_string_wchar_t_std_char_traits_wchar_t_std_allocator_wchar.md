# Wsp::Facade::StorageHealthFacade::SetSetting(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x18006b9b0`
- end: `0x18006bb6f`
- name: `?SetSetting@StorageHealthFacade@Facade@Wsp@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z`
- size: `447`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task`

## callers

- `0x180054b94`

## callees

- `0x180002b50`
- `0x180002f70`
- `0x1800035c0`
- `0x18000cd9c`
- `0x18000ce84`
- `0x18000da34`
- `0x1800694d4`
- `0x18006b9b0`
- `0x18007935c`
- `0x180079c48`
- `0x18007a1a0`
- `0x18007b370`

## string_xrefs

- `0x18006bad3`: `No connection to the Health Service.`
- `0x18006ba97`: `The Health Service is not online.`

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
0x18006b9b0  mov     [rsp-8+arg_18], rbx
0x18006b9b5  push    rbp
0x18006b9b6  push    rsi
0x18006b9b7  push    rdi
0x18006b9b8  lea     rbp, [rsp-47h]
0x18006b9bd  sub     rsp, 0D0h
0x18006b9c4  mov     rax, cs:__security_cookie
0x18006b9cb  xor     rax, rsp
0x18006b9ce  mov     [rbp+57h+var_20], rax
0x18006b9d2  mov     rsi, r8
0x18006b9d5  mov     rdi, rdx
0x18006b9d8  call    ?GetSubsystemType@StorageHealthFacade@Facade@Wsp@@QEBA?BW4WSP_SUBSYSTEM_TYPE@@XZ; Wsp::Facade::StorageHealthFacade::GetSubsystemType(void)
0x18006b9dd  test    eax, eax
0x18006b9df  jz      loc_18006BB0F
0x18006b9e5  cmp     cs:?g_ptrHealthClient@Health@Wsp@@3VGlobalResClientInst@12@A, 0; Wsp::Health::GlobalResClientInst Wsp::Health::g_ptrHealthClient
0x18006b9ed  jnz     short loc_18006BA26
0x18006b9ef  mov     ecx, 160h; Size
0x18006b9f4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006b9f9  mov     rcx, rax; this
0x18006b9fc  call    ??0ResClient@Health@Wsp@@QEAA@XZ; Wsp::Health::ResClient::ResClient(void)
0x18006ba01  mov     rbx, rax
0x18006ba04  test    rax, rax
0x18006ba07  jz      short loc_18006BA26
0x18006ba09  mov     rcx, rax; this
0x18006ba0c  call    ?Initialize@ResClient@Health@Wsp@@QEAAJXZ; Wsp::Health::ResClient::Initialize(void)
0x18006ba11  test    eax, eax
0x18006ba13  jns     short loc_18006BA1F
0x18006ba15  mov     rcx, rbx; this
0x18006ba18  call    ??_GResClient@Health@Wsp@@QEAAPEAXI@Z; Wsp::Health::ResClient::`scalar deleting destructor'(uint)
0x18006ba1d  jmp     short loc_18006BA26
0x18006ba1f  mov     cs:?g_ptrHealthClient@Health@Wsp@@3VGlobalResClientInst@12@A, rbx; Wsp::Health::GlobalResClientInst Wsp::Health::g_ptrHealthClient
0x18006ba26  mov     rcx, rsi
0x18006ba29  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18006ba2e  mov     r8, rax
0x18006ba31  mov     rcx, rdi
0x18006ba34  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18006ba39  mov     rdx, rax; wchar_t *
0x18006ba3c  call    ?AddSetting@HealthConfiguration@Health@Wsp@@QEAAJPEB_W0PEAX@Z; Wsp::Health::HealthConfiguration::AddSetting(wchar_t const *,wchar_t const *,void *)
0x18006ba41  test    eax, eax
0x18006ba43  jns     loc_18006BB4F
0x18006ba49  lea     rcx, [rbp+57h+var_B8]
0x18006ba4d  cmp     eax, 8007006Eh
0x18006ba52  jz      short loc_18006BAD3
0x18006ba54  cmp     eax, 8007138Ch
0x18006ba59  jz      short loc_18006BA97
0x18006ba5b  lea     rdx, aTheOperationFa_0; "The operation failed"
0x18006ba62  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006ba67  nop
0x18006ba68  mov     [rbp+57h+var_C0], 4
0x18006ba6f  mov     [rbp+57h+var_BC], 7
0x18006ba76  mov     r8, rax
0x18006ba79  lea     rdx, [rbp+57h+var_C0]
0x18006ba7d  lea     rcx, [rbp+57h+pExceptionObject]
0x18006ba81  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18006ba86  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18006ba8d  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18006ba91  call    _CxxThrowException_0
0x18006ba97  lea     rdx, aTheHealthServi; "The Health Service is not online."
0x18006ba9e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006baa3  nop
0x18006baa4  mov     [rbp+57h+var_C0], 0E67Eh
0x18006baab  mov     [rbp+57h+var_BC], 7
0x18006bab2  mov     r8, rax
0x18006bab5  lea     rdx, [rbp+57h+var_C0]
0x18006bab9  lea     rcx, [rbp+57h+pExceptionObject]
0x18006babd  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18006bac2  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18006bac9  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18006bacd  call    _CxxThrowException_0
0x18006bad3  lea     rdx, aNoConnectionTo; "No connection to the Health Service."
0x18006bada  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006badf  nop
0x18006bae0  mov     [rbp+57h+var_C0], 0E678h
0x18006bae7  mov     [rbp+57h+var_BC], 7
0x18006baee  mov     r8, rax
0x18006baf1  lea     rdx, [rbp+57h+var_C0]
0x18006baf5  lea     rcx, [rbp+57h+pExceptionObject]
0x18006baf9  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18006bafe  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18006bb05  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18006bb09  call    _CxxThrowException_0
0x18006bb0f  lea     rdx, aNonHighlyavail; "non highlyavailable subsystems are not "...
0x18006bb16  lea     rcx, [rbp+57h+var_B8]
0x18006bb1a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006bb1f  nop
0x18006bb20  mov     [rbp+57h+var_C0], 0E679h
0x18006bb27  mov     [rbp+57h+var_BC], 7
0x18006bb2e  mov     r8, rax
0x18006bb31  lea     rdx, [rbp+57h+var_C0]
0x18006bb35  lea     rcx, [rbp+57h+pExceptionObject]
0x18006bb39  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18006bb3e  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18006bb45  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18006bb49  call    _CxxThrowException_0
0x18006bb4f  mov     rcx, [rbp+57h+var_20]
0x18006bb53  xor     rcx, rsp; StackCookie
0x18006bb56  call    __security_check_cookie
0x18006bb5b  mov     rbx, [rsp+0E0h+arg_18]
0x18006bb63  add     rsp, 0D0h
0x18006bb6a  pop     rdi
0x18006bb6b  pop     rsi
0x18006bb6c  pop     rbp
0x18006bb6d  retn
```
