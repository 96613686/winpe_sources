# Wsp::Facade::StorageHealthFacade::GetSetting(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,mi::MiContext &)

- ea: `0x180069234`
- end: `0x1800693f2`
- name: `?GetSetting@StorageHealthFacade@Facade@Wsp@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVMiContext@mi@@@Z`
- size: `446`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800540a8`

## callees

- `0x180002b50`
- `0x180002f70`
- `0x1800035c0`
- `0x18000cd9c`
- `0x18000ce84`
- `0x18000da34`
- `0x180069234`
- `0x1800694d4`
- `0x1800793e8`
- `0x180079c48`
- `0x18007a1a0`
- `0x18007b370`

## string_xrefs

- `0x180069356`: `No connection to the Health Service.`
- `0x18006931a`: `The Health Service is not online.`

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
0x180069234  mov     [rsp-8+arg_18], rbx
0x180069239  push    rbp
0x18006923a  push    rsi
0x18006923b  push    rdi
0x18006923c  lea     rbp, [rsp-47h]
0x180069241  sub     rsp, 0D0h
0x180069248  mov     rax, cs:__security_cookie
0x18006924f  xor     rax, rsp
0x180069252  mov     [rbp+57h+var_20], rax
0x180069256  mov     rsi, r8
0x180069259  mov     rdi, rdx
0x18006925c  call    ?GetSubsystemType@StorageHealthFacade@Facade@Wsp@@QEBA?BW4WSP_SUBSYSTEM_TYPE@@XZ; Wsp::Facade::StorageHealthFacade::GetSubsystemType(void)
0x180069261  test    eax, eax
0x180069263  jz      loc_180069392
0x180069269  cmp     cs:?g_ptrHealthClient@Health@Wsp@@3VGlobalResClientInst@12@A, 0; Wsp::Health::GlobalResClientInst Wsp::Health::g_ptrHealthClient
0x180069271  jnz     short loc_1800692AA
0x180069273  mov     ecx, 160h; Size
0x180069278  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006927d  mov     rcx, rax; this
0x180069280  call    ??0ResClient@Health@Wsp@@QEAA@XZ; Wsp::Health::ResClient::ResClient(void)
0x180069285  mov     rbx, rax
0x180069288  test    rax, rax
0x18006928b  jz      short loc_1800692AA
0x18006928d  mov     rcx, rax; this
0x180069290  call    ?Initialize@ResClient@Health@Wsp@@QEAAJXZ; Wsp::Health::ResClient::Initialize(void)
0x180069295  test    eax, eax
0x180069297  jns     short loc_1800692A3
0x180069299  mov     rcx, rbx; this
0x18006929c  call    ??_GResClient@Health@Wsp@@QEAAPEAXI@Z; Wsp::Health::ResClient::`scalar deleting destructor'(uint)
0x1800692a1  jmp     short loc_1800692AA
0x1800692a3  mov     cs:?g_ptrHealthClient@Health@Wsp@@3VGlobalResClientInst@12@A, rbx; Wsp::Health::GlobalResClientInst Wsp::Health::g_ptrHealthClient
0x1800692aa  mov     rcx, rdi
0x1800692ad  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800692b2  mov     r9, [rsi]; void *
0x1800692b5  lea     r8, ?_GetSettingCallback@Facade@Wsp@@YAXPEB_W0PEAX@Z; void (*)(const wchar_t *, const wchar_t *, void *)
0x1800692bc  mov     rdx, rax; wchar_t *
0x1800692bf  call    ?GetSettings@HealthConfiguration@Health@Wsp@@QEAAJPEB_WP6AX00PEAX@Z1@Z; Wsp::Health::HealthConfiguration::GetSettings(wchar_t const *,void (*)(wchar_t const *,wchar_t const *,void *),void *)
0x1800692c4  test    eax, eax
0x1800692c6  jns     loc_1800693D2
0x1800692cc  lea     rcx, [rbp+57h+var_B8]
0x1800692d0  cmp     eax, 8007006Eh
0x1800692d5  jz      short loc_180069356
0x1800692d7  cmp     eax, 8007138Ch
0x1800692dc  jz      short loc_18006931A
0x1800692de  lea     rdx, aTheOperationFa_0; "The operation failed"
0x1800692e5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800692ea  nop
0x1800692eb  mov     [rbp+57h+var_C0], 4
0x1800692f2  mov     [rbp+57h+var_BC], 7
0x1800692f9  mov     r8, rax
0x1800692fc  lea     rdx, [rbp+57h+var_C0]
0x180069300  lea     rcx, [rbp+57h+pExceptionObject]
0x180069304  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180069309  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180069310  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180069314  call    _CxxThrowException_0
0x18006931a  lea     rdx, aTheHealthServi; "The Health Service is not online."
0x180069321  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180069326  nop
0x180069327  mov     [rbp+57h+var_C0], 0E67Eh
0x18006932e  mov     [rbp+57h+var_BC], 7
0x180069335  mov     r8, rax
0x180069338  lea     rdx, [rbp+57h+var_C0]
0x18006933c  lea     rcx, [rbp+57h+pExceptionObject]
0x180069340  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180069345  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18006934c  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180069350  call    _CxxThrowException_0
0x180069356  lea     rdx, aNoConnectionTo; "No connection to the Health Service."
0x18006935d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180069362  nop
0x180069363  mov     [rbp+57h+var_C0], 0E678h
0x18006936a  mov     [rbp+57h+var_BC], 7
0x180069371  mov     r8, rax
0x180069374  lea     rdx, [rbp+57h+var_C0]
0x180069378  lea     rcx, [rbp+57h+pExceptionObject]
0x18006937c  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180069381  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180069388  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18006938c  call    _CxxThrowException_0
0x180069392  lea     rdx, aNonHighlyavail; "non highlyavailable subsystems are not "...
0x180069399  lea     rcx, [rbp+57h+var_B8]
0x18006939d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800693a2  nop
0x1800693a3  mov     [rbp+57h+var_C0], 0E679h
0x1800693aa  mov     [rbp+57h+var_BC], 7
0x1800693b1  mov     r8, rax
0x1800693b4  lea     rdx, [rbp+57h+var_C0]
0x1800693b8  lea     rcx, [rbp+57h+pExceptionObject]
0x1800693bc  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x1800693c1  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x1800693c8  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800693cc  call    _CxxThrowException_0
0x1800693d2  mov     rcx, [rbp+57h+var_20]
0x1800693d6  xor     rcx, rsp; StackCookie
0x1800693d9  call    __security_check_cookie
0x1800693de  mov     rbx, [rsp+0E0h+arg_18]
0x1800693e6  add     rsp, 0D0h
0x1800693ed  pop     rdi
0x1800693ee  pop     rsi
0x1800693ef  pop     rbp
0x1800693f0  retn
```
