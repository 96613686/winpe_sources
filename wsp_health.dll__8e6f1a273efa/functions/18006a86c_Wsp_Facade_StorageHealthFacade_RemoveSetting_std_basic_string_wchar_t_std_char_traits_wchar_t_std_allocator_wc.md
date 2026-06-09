# Wsp::Facade::StorageHealthFacade::RemoveSetting(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x18006a86c`
- end: `0x18006aa22`
- name: `?RemoveSetting@StorageHealthFacade@Facade@Wsp@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `438`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task`

## callers

- `0x1800549c4`

## callees

- `0x180002b50`
- `0x180002f70`
- `0x1800035c0`
- `0x18000cd9c`
- `0x18000ce84`
- `0x18000da34`
- `0x1800694d4`
- `0x18006a86c`
- `0x180079494`
- `0x180079c48`
- `0x18007a1a0`
- `0x18007b370`

## string_xrefs

- `0x18006a984`: `No connection to the Health Service.`
- `0x18006a948`: `The Health Service is not online.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall Wsp::Facade::StorageHealthFacade::RemoveSetting(__int64 a1, __int64 a2)
{
  Wsp::Health::ResClient *v3; // rax
  Wsp::Health::ResClient *v4; // rax
  Wsp::Health::ResClient *v5; // rbx
  unsigned int v6; // edx
  const wchar_t *v7; // rax
  Wsp::Health::HealthConfiguration *v8; // rcx
  void *v9; // r8
  int result; // eax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  int v15; // [rsp+20h] [rbp-59h] BYREF
  int v16; // [rsp+24h] [rbp-55h]
  _BYTE v17[40]; // [rsp+28h] [rbp-51h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+50h] [rbp-29h] BYREF

  if ( !(unsigned int)Wsp::Facade::StorageHealthFacade::GetSubsystemType(a1) )
  {
    v14 = std::wstring::wstring(v17, L"non highlyavailable subsystems are not supported");
    v15 = 59001;
    v16 = 7;
    cxl::Exception::Exception(pExceptionObject, &v15, v14);
    throw (cxl::Exception *)pExceptionObject;
  }
  if ( !Wsp::Health::g_ptrHealthClient )
  {
    v3 = (Wsp::Health::ResClient *)operator new(0x160u);
    v4 = (Wsp::Health::ResClient *)Wsp::Health::ResClient::ResClient(v3);
    v5 = v4;
    if ( v4 )
    {
      if ( (int)Wsp::Health::ResClient::Initialize(v4) >= 0 )
        Wsp::Health::g_ptrHealthClient = v5;
      else
        Wsp::Health::ResClient::`scalar deleting destructor'(v5, v6);
    }
  }
  v7 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a2);
  result = Wsp::Health::HealthConfiguration::RemoveSetting(v8, v7, v9);
  if ( result < 0 )
  {
    if ( result != -2147024786 )
    {
      if ( result != -2147019892 )
      {
        v11 = std::wstring::wstring(v17, L"The operation failed");
        v15 = 4;
        v16 = 7;
        cxl::Exception::Exception(pExceptionObject, &v15, v11);
        throw (cxl::Exception *)pExceptionObject;
      }
      v12 = std::wstring::wstring(v17, L"The Health Service is not online.");
      v15 = 59006;
      v16 = 7;
      cxl::Exception::Exception(pExceptionObject, &v15, v12);
      throw (cxl::Exception *)pExceptionObject;
    }
    v13 = std::wstring::wstring(v17, L"No connection to the Health Service.");
    v15 = 59000;
    v16 = 7;
    cxl::Exception::Exception(pExceptionObject, &v15, v13);
    throw (cxl::Exception *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x18006a86c  mov     [rsp-8+arg_10], rbx
0x18006a871  mov     [rsp-8+arg_18], rdi
0x18006a876  push    rbp
0x18006a877  lea     rbp, [rsp-57h]
0x18006a87c  sub     rsp, 0D0h
0x18006a883  mov     rax, cs:__security_cookie
0x18006a88a  xor     rax, rsp
0x18006a88d  mov     [rbp+57h+var_10], rax
0x18006a891  mov     rdi, rdx
0x18006a894  call    ?GetSubsystemType@StorageHealthFacade@Facade@Wsp@@QEBA?BW4WSP_SUBSYSTEM_TYPE@@XZ; Wsp::Facade::StorageHealthFacade::GetSubsystemType(void)
0x18006a899  test    eax, eax
0x18006a89b  jz      loc_18006A9C0
0x18006a8a1  cmp     cs:?g_ptrHealthClient@Health@Wsp@@3VGlobalResClientInst@12@A, 0; Wsp::Health::GlobalResClientInst Wsp::Health::g_ptrHealthClient
0x18006a8a9  jnz     short loc_18006A8E2
0x18006a8ab  mov     ecx, 160h; Size
0x18006a8b0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006a8b5  mov     rcx, rax; this
0x18006a8b8  call    ??0ResClient@Health@Wsp@@QEAA@XZ; Wsp::Health::ResClient::ResClient(void)
0x18006a8bd  mov     rbx, rax
0x18006a8c0  test    rax, rax
0x18006a8c3  jz      short loc_18006A8E2
0x18006a8c5  mov     rcx, rax; this
0x18006a8c8  call    ?Initialize@ResClient@Health@Wsp@@QEAAJXZ; Wsp::Health::ResClient::Initialize(void)
0x18006a8cd  test    eax, eax
0x18006a8cf  jns     short loc_18006A8DB
0x18006a8d1  mov     rcx, rbx; this
0x18006a8d4  call    ??_GResClient@Health@Wsp@@QEAAPEAXI@Z; Wsp::Health::ResClient::`scalar deleting destructor'(uint)
0x18006a8d9  jmp     short loc_18006A8E2
0x18006a8db  mov     cs:?g_ptrHealthClient@Health@Wsp@@3VGlobalResClientInst@12@A, rbx; Wsp::Health::GlobalResClientInst Wsp::Health::g_ptrHealthClient
0x18006a8e2  mov     rcx, rdi
0x18006a8e5  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18006a8ea  mov     rdx, rax; wchar_t *
0x18006a8ed  call    ?RemoveSetting@HealthConfiguration@Health@Wsp@@QEAAJPEB_WPEAX@Z; Wsp::Health::HealthConfiguration::RemoveSetting(wchar_t const *,void *)
0x18006a8f2  test    eax, eax
0x18006a8f4  jns     loc_18006AA00
0x18006a8fa  lea     rcx, [rbp+57h+var_A8]
0x18006a8fe  cmp     eax, 8007006Eh
0x18006a903  jz      short loc_18006A984
0x18006a905  cmp     eax, 8007138Ch
0x18006a90a  jz      short loc_18006A948
0x18006a90c  lea     rdx, aTheOperationFa_0; "The operation failed"
0x18006a913  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006a918  nop
0x18006a919  mov     [rbp+57h+var_B0], 4
0x18006a920  mov     [rbp+57h+var_AC], 7
0x18006a927  mov     r8, rax
0x18006a92a  lea     rdx, [rbp+57h+var_B0]
0x18006a92e  lea     rcx, [rbp+57h+pExceptionObject]
0x18006a932  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18006a937  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18006a93e  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18006a942  call    _CxxThrowException_0
0x18006a948  lea     rdx, aTheHealthServi; "The Health Service is not online."
0x18006a94f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006a954  nop
0x18006a955  mov     [rbp+57h+var_B0], 0E67Eh
0x18006a95c  mov     [rbp+57h+var_AC], 7
0x18006a963  mov     r8, rax
0x18006a966  lea     rdx, [rbp+57h+var_B0]
0x18006a96a  lea     rcx, [rbp+57h+pExceptionObject]
0x18006a96e  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18006a973  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18006a97a  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18006a97e  call    _CxxThrowException_0
0x18006a984  lea     rdx, aNoConnectionTo; "No connection to the Health Service."
0x18006a98b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006a990  nop
0x18006a991  mov     [rbp+57h+var_B0], 0E678h
0x18006a998  mov     [rbp+57h+var_AC], 7
0x18006a99f  mov     r8, rax
0x18006a9a2  lea     rdx, [rbp+57h+var_B0]
0x18006a9a6  lea     rcx, [rbp+57h+pExceptionObject]
0x18006a9aa  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18006a9af  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18006a9b6  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18006a9ba  call    _CxxThrowException_0
0x18006a9c0  lea     rdx, aNonHighlyavail; "non highlyavailable subsystems are not "...
0x18006a9c7  lea     rcx, [rbp+57h+var_A8]
0x18006a9cb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006a9d0  nop
0x18006a9d1  mov     [rbp+57h+var_B0], 0E679h
0x18006a9d8  mov     [rbp+57h+var_AC], 7
0x18006a9df  mov     r8, rax
0x18006a9e2  lea     rdx, [rbp+57h+var_B0]
0x18006a9e6  lea     rcx, [rbp+57h+pExceptionObject]
0x18006a9ea  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18006a9ef  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18006a9f6  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18006a9fa  call    _CxxThrowException_0
0x18006aa00  mov     rcx, [rbp+57h+var_10]
0x18006aa04  xor     rcx, rsp; StackCookie
0x18006aa07  call    __security_check_cookie
0x18006aa0c  lea     r11, [rsp+0D0h+var_s0]
0x18006aa14  mov     rbx, [r11+20h]
0x18006aa18  mov     rdi, [r11+28h]
0x18006aa1c  mov     rsp, r11
0x18006aa1f  pop     rbp
0x18006aa20  retn
```
