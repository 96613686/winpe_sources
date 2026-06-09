# Wsp::Facade::StorageHealthFacade::RemoveSetting(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180069034`
- end: `0x1800691e9`
- name: `?RemoveSetting@StorageHealthFacade@Facade@Wsp@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `437`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task`

## callers

- `0x180052fc8`

## callees

- `0x180002ae0`
- `0x180002f00`
- `0x180003520`
- `0x18000c9f0`
- `0x18000cad8`
- `0x18000d618`
- `0x180067ca8`
- `0x180069034`
- `0x1800775e4`
- `0x180077d68`
- `0x18007825c`
- `0x180079368`

## string_xrefs

- `0x18006914c`: `No connection to the Health Service.`
- `0x180069110`: `The Health Service is not online.`

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
0x180069034  mov     [rsp-8+arg_10], rbx
0x180069039  mov     [rsp-8+arg_18], rdi
0x18006903e  push    rbp
0x18006903f  lea     rbp, [rsp-57h]
0x180069044  sub     rsp, 0D0h
0x18006904b  mov     rax, cs:__security_cookie
0x180069052  xor     rax, rsp
0x180069055  mov     [rbp+57h+var_10], rax
0x180069059  mov     rdi, rdx
0x18006905c  call    ?GetSubsystemType@StorageHealthFacade@Facade@Wsp@@QEBA?BW4WSP_SUBSYSTEM_TYPE@@XZ; Wsp::Facade::StorageHealthFacade::GetSubsystemType(void)
0x180069061  test    eax, eax
0x180069063  jz      loc_180069188
0x180069069  cmp     cs:?g_ptrHealthClient@Health@Wsp@@3VGlobalResClientInst@12@A, 0; Wsp::Health::GlobalResClientInst Wsp::Health::g_ptrHealthClient
0x180069071  jnz     short loc_1800690AA
0x180069073  mov     ecx, 160h; Size
0x180069078  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006907d  mov     rcx, rax; this
0x180069080  call    ??0ResClient@Health@Wsp@@QEAA@XZ; Wsp::Health::ResClient::ResClient(void)
0x180069085  mov     rbx, rax
0x180069088  test    rax, rax
0x18006908b  jz      short loc_1800690AA
0x18006908d  mov     rcx, rax; this
0x180069090  call    ?Initialize@ResClient@Health@Wsp@@QEAAJXZ; Wsp::Health::ResClient::Initialize(void)
0x180069095  test    eax, eax
0x180069097  jns     short loc_1800690A3
0x180069099  mov     rcx, rbx; this
0x18006909c  call    ??_GResClient@Health@Wsp@@QEAAPEAXI@Z; Wsp::Health::ResClient::`scalar deleting destructor'(uint)
0x1800690a1  jmp     short loc_1800690AA
0x1800690a3  mov     cs:?g_ptrHealthClient@Health@Wsp@@3VGlobalResClientInst@12@A, rbx; Wsp::Health::GlobalResClientInst Wsp::Health::g_ptrHealthClient
0x1800690aa  mov     rcx, rdi
0x1800690ad  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800690b2  mov     rdx, rax; wchar_t *
0x1800690b5  call    ?RemoveSetting@HealthConfiguration@Health@Wsp@@QEAAJPEB_WPEAX@Z; Wsp::Health::HealthConfiguration::RemoveSetting(wchar_t const *,void *)
0x1800690ba  test    eax, eax
0x1800690bc  jns     loc_1800691C8
0x1800690c2  lea     rcx, [rbp+57h+var_A8]
0x1800690c6  cmp     eax, 8007006Eh
0x1800690cb  jz      short loc_18006914C
0x1800690cd  cmp     eax, 8007138Ch
0x1800690d2  jz      short loc_180069110
0x1800690d4  lea     rdx, aTheOperationFa_0; "The operation failed"
0x1800690db  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800690e0  nop
0x1800690e1  mov     [rbp+57h+var_B0], 4
0x1800690e8  mov     [rbp+57h+var_AC], 7
0x1800690ef  mov     r8, rax
0x1800690f2  lea     rdx, [rbp+57h+var_B0]
0x1800690f6  lea     rcx, [rbp+57h+pExceptionObject]
0x1800690fa  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x1800690ff  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180069106  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18006910a  call    _CxxThrowException_0
0x180069110  lea     rdx, aTheHealthServi; "The Health Service is not online."
0x180069117  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18006911c  nop
0x18006911d  mov     [rbp+57h+var_B0], 0E67Eh
0x180069124  mov     [rbp+57h+var_AC], 7
0x18006912b  mov     r8, rax
0x18006912e  lea     rdx, [rbp+57h+var_B0]
0x180069132  lea     rcx, [rbp+57h+pExceptionObject]
0x180069136  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18006913b  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180069142  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180069146  call    _CxxThrowException_0
0x18006914c  lea     rdx, aNoConnectionTo; "No connection to the Health Service."
0x180069153  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180069158  nop
0x180069159  mov     [rbp+57h+var_B0], 0E678h
0x180069160  mov     [rbp+57h+var_AC], 7
0x180069167  mov     r8, rax
0x18006916a  lea     rdx, [rbp+57h+var_B0]
0x18006916e  lea     rcx, [rbp+57h+pExceptionObject]
0x180069172  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180069177  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18006917e  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180069182  call    _CxxThrowException_0
0x180069188  lea     rdx, aNonHighlyavail; "non highlyavailable subsystems are not "...
0x18006918f  lea     rcx, [rbp+57h+var_A8]
0x180069193  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180069198  nop
0x180069199  mov     [rbp+57h+var_B0], 0E679h
0x1800691a0  mov     [rbp+57h+var_AC], 7
0x1800691a7  mov     r8, rax
0x1800691aa  lea     rdx, [rbp+57h+var_B0]
0x1800691ae  lea     rcx, [rbp+57h+pExceptionObject]
0x1800691b2  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x1800691b7  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x1800691be  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800691c2  call    _CxxThrowException_0
0x1800691c8  mov     rcx, [rbp+57h+var_10]
0x1800691cc  xor     rcx, rsp; StackCookie
0x1800691cf  call    __security_check_cookie
0x1800691d4  lea     r11, [rsp+0D0h+var_s0]
0x1800691dc  mov     rbx, [r11+20h]
0x1800691e0  mov     rdi, [r11+28h]
0x1800691e4  mov     rsp, r11
0x1800691e7  pop     rbp
0x1800691e8  retn
```
