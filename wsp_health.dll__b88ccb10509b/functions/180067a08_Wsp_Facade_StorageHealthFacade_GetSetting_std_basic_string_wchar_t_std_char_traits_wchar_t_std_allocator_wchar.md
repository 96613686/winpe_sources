# Wsp::Facade::StorageHealthFacade::GetSetting(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,mi::MiContext &)

- ea: `0x180067a08`
- end: `0x180067bc5`
- name: `?GetSetting@StorageHealthFacade@Facade@Wsp@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVMiContext@mi@@@Z`
- size: `445`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800526ac`

## callees

- `0x180002ae0`
- `0x180002f00`
- `0x180003520`
- `0x18000c9f0`
- `0x18000cad8`
- `0x18000d618`
- `0x180067a08`
- `0x180067ca8`
- `0x180077538`
- `0x180077d68`
- `0x18007825c`
- `0x180079368`

## string_xrefs

- `0x180067b2a`: `No connection to the Health Service.`
- `0x180067aee`: `The Health Service is not online.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall Wsp::Facade::StorageHealthFacade::GetSetting(__int64 a1, __int64 a2, void **a3)
{
  Wsp::Health::ResClient *v5; // rax
  Wsp::Health::ResClient *v6; // rax
  Wsp::Health::ResClient *v7; // rbx
  unsigned int v8; // edx
  const wchar_t *v9; // rax
  Wsp::Health::HealthConfiguration *v10; // rcx
  int result; // eax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  int v16; // [rsp+20h] [rbp-69h] BYREF
  int v17; // [rsp+24h] [rbp-65h]
  _BYTE v18[40]; // [rsp+28h] [rbp-61h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+50h] [rbp-39h] BYREF

  if ( !(unsigned int)Wsp::Facade::StorageHealthFacade::GetSubsystemType(a1) )
  {
    v15 = std::wstring::wstring(v18, L"non highlyavailable subsystems are not supported");
    v16 = 59001;
    v17 = 7;
    cxl::Exception::Exception(pExceptionObject, &v16, v15);
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
  v9 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a2);
  result = Wsp::Health::HealthConfiguration::GetSettings(
             v10,
             v9,
             (void (*)(const wchar_t *, const wchar_t *, void *))Wsp::Facade::_GetSettingCallback,
             *a3);
  if ( result < 0 )
  {
    if ( result != -2147024786 )
    {
      if ( result != -2147019892 )
      {
        v12 = std::wstring::wstring(v18, L"The operation failed");
        v16 = 4;
        v17 = 7;
        cxl::Exception::Exception(pExceptionObject, &v16, v12);
        throw (cxl::Exception *)pExceptionObject;
      }
      v13 = std::wstring::wstring(v18, L"The Health Service is not online.");
      v16 = 59006;
      v17 = 7;
      cxl::Exception::Exception(pExceptionObject, &v16, v13);
      throw (cxl::Exception *)pExceptionObject;
    }
    v14 = std::wstring::wstring(v18, L"No connection to the Health Service.");
    v16 = 59000;
    v17 = 7;
    cxl::Exception::Exception(pExceptionObject, &v16, v14);
    throw (cxl::Exception *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x180067a08  mov     [rsp-8+arg_18], rbx
0x180067a0d  push    rbp
0x180067a0e  push    rsi
0x180067a0f  push    rdi
0x180067a10  lea     rbp, [rsp-47h]
0x180067a15  sub     rsp, 0D0h
0x180067a1c  mov     rax, cs:__security_cookie
0x180067a23  xor     rax, rsp
0x180067a26  mov     [rbp+57h+var_20], rax
0x180067a2a  mov     rsi, r8
0x180067a2d  mov     rdi, rdx
0x180067a30  call    ?GetSubsystemType@StorageHealthFacade@Facade@Wsp@@QEBA?BW4WSP_SUBSYSTEM_TYPE@@XZ; Wsp::Facade::StorageHealthFacade::GetSubsystemType(void)
0x180067a35  test    eax, eax
0x180067a37  jz      loc_180067B66
0x180067a3d  cmp     cs:?g_ptrHealthClient@Health@Wsp@@3VGlobalResClientInst@12@A, 0; Wsp::Health::GlobalResClientInst Wsp::Health::g_ptrHealthClient
0x180067a45  jnz     short loc_180067A7E
0x180067a47  mov     ecx, 160h; Size
0x180067a4c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180067a51  mov     rcx, rax; this
0x180067a54  call    ??0ResClient@Health@Wsp@@QEAA@XZ; Wsp::Health::ResClient::ResClient(void)
0x180067a59  mov     rbx, rax
0x180067a5c  test    rax, rax
0x180067a5f  jz      short loc_180067A7E
0x180067a61  mov     rcx, rax; this
0x180067a64  call    ?Initialize@ResClient@Health@Wsp@@QEAAJXZ; Wsp::Health::ResClient::Initialize(void)
0x180067a69  test    eax, eax
0x180067a6b  jns     short loc_180067A77
0x180067a6d  mov     rcx, rbx; this
0x180067a70  call    ??_GResClient@Health@Wsp@@QEAAPEAXI@Z; Wsp::Health::ResClient::`scalar deleting destructor'(uint)
0x180067a75  jmp     short loc_180067A7E
0x180067a77  mov     cs:?g_ptrHealthClient@Health@Wsp@@3VGlobalResClientInst@12@A, rbx; Wsp::Health::GlobalResClientInst Wsp::Health::g_ptrHealthClient
0x180067a7e  mov     rcx, rdi
0x180067a81  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180067a86  mov     r9, [rsi]; void *
0x180067a89  lea     r8, ?_GetSettingCallback@Facade@Wsp@@YAXPEB_W0PEAX@Z; void (*)(const wchar_t *, const wchar_t *, void *)
0x180067a90  mov     rdx, rax; wchar_t *
0x180067a93  call    ?GetSettings@HealthConfiguration@Health@Wsp@@QEAAJPEB_WP6AX00PEAX@Z1@Z; Wsp::Health::HealthConfiguration::GetSettings(wchar_t const *,void (*)(wchar_t const *,wchar_t const *,void *),void *)
0x180067a98  test    eax, eax
0x180067a9a  jns     loc_180067BA6
0x180067aa0  lea     rcx, [rbp+57h+var_B8]
0x180067aa4  cmp     eax, 8007006Eh
0x180067aa9  jz      short loc_180067B2A
0x180067aab  cmp     eax, 8007138Ch
0x180067ab0  jz      short loc_180067AEE
0x180067ab2  lea     rdx, aTheOperationFa_0; "The operation failed"
0x180067ab9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180067abe  nop
0x180067abf  mov     [rbp+57h+var_C0], 4
0x180067ac6  mov     [rbp+57h+var_BC], 7
0x180067acd  mov     r8, rax
0x180067ad0  lea     rdx, [rbp+57h+var_C0]
0x180067ad4  lea     rcx, [rbp+57h+pExceptionObject]
0x180067ad8  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180067add  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180067ae4  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180067ae8  call    _CxxThrowException_0
0x180067aee  lea     rdx, aTheHealthServi; "The Health Service is not online."
0x180067af5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180067afa  nop
0x180067afb  mov     [rbp+57h+var_C0], 0E67Eh
0x180067b02  mov     [rbp+57h+var_BC], 7
0x180067b09  mov     r8, rax
0x180067b0c  lea     rdx, [rbp+57h+var_C0]
0x180067b10  lea     rcx, [rbp+57h+pExceptionObject]
0x180067b14  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180067b19  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180067b20  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180067b24  call    _CxxThrowException_0
0x180067b2a  lea     rdx, aNoConnectionTo; "No connection to the Health Service."
0x180067b31  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180067b36  nop
0x180067b37  mov     [rbp+57h+var_C0], 0E678h
0x180067b3e  mov     [rbp+57h+var_BC], 7
0x180067b45  mov     r8, rax
0x180067b48  lea     rdx, [rbp+57h+var_C0]
0x180067b4c  lea     rcx, [rbp+57h+pExceptionObject]
0x180067b50  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180067b55  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180067b5c  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180067b60  call    _CxxThrowException_0
0x180067b66  lea     rdx, aNonHighlyavail; "non highlyavailable subsystems are not "...
0x180067b6d  lea     rcx, [rbp+57h+var_B8]
0x180067b71  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180067b76  nop
0x180067b77  mov     [rbp+57h+var_C0], 0E679h
0x180067b7e  mov     [rbp+57h+var_BC], 7
0x180067b85  mov     r8, rax
0x180067b88  lea     rdx, [rbp+57h+var_C0]
0x180067b8c  lea     rcx, [rbp+57h+pExceptionObject]
0x180067b90  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180067b95  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180067b9c  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180067ba0  call    _CxxThrowException_0
0x180067ba6  mov     rcx, [rbp+57h+var_20]
0x180067baa  xor     rcx, rsp; StackCookie
0x180067bad  call    __security_check_cookie
0x180067bb2  mov     rbx, [rsp+0E0h+arg_18]
0x180067bba  add     rsp, 0D0h
0x180067bc1  pop     rdi
0x180067bc2  pop     rsi
0x180067bc3  pop     rbp
0x180067bc4  retn
```
