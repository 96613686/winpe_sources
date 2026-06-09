# GetPhoneLineName(_GUID,ushort * *)

- ea: `0x1800d93b8`
- end: `0x1800d95fc`
- name: `?GetPhoneLineName@@YAJU_GUID@@PEAPEAG@Z`
- size: `580`
- prototype: `__int64 __fastcall(struct _GUID *__struct_ptr, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800d8c34`

## callees

- `0x180004658`
- `0x180008f0c`
- `0x180042d18`
- `0x1800d84a0`
- `0x1800d93b8`
- `0x18012c7b0`
- `0x18012e010`

## import_xrefs

- `PhoneUtil!IsCellularVoiceCapableDevice` at `0x1800d93e4`
- `PhoneUtil!IsCellularVoiceCapableDevice` at `0x1800d93e4`
- `UserDataTypeHelperUtil!DupString` at `0x1800d95a8`
- `UserDataTypeHelperUtil!DupString` at `0x1800d95a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d9543`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d9583`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d95c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d9543`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d9583`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d95c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d959c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d959c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800d9453`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800d9453`

## string_xrefs

- `0x1800d93f3`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistoryprop.cpp`
- `0x1800d9465`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistoryprop.cpp`
- `0x1800d94d4`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistoryprop.cpp`
- `0x1800d956c`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistoryprop.cpp`

## pseudocode

```c
__int64 __fastcall GetPhoneLineName(struct _GUID *a1, unsigned __int16 **a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rbx
  int ActivationFactory; // eax
  int v7; // eax
  __int64 v8; // r9
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, HSTRING *); // rbx
  int v13; // eax
  __int64 v14; // r9
  PCWSTR StringRawBuffer; // rax
  HSTRING string; // [rsp+30h] [rbp-29h] BYREF
  __int64 v18; // [rsp+38h] [rbp-21h] BYREF
  int v19; // [rsp+40h] [rbp-19h] BYREF
  __int64 v20; // [rsp+48h] [rbp-11h] BYREF
  __int64 v21; // [rsp+50h] [rbp-9h] BYREF
  __int64 (__fastcall *v22)(); // [rsp+58h] [rbp-1h] BYREF
  __int64 *v23; // [rsp+60h] [rbp+7h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp+Fh] BYREF
  __int64 v25; // [rsp+80h] [rbp+27h]

  *a2 = 0;
  if ( (unsigned __int8)IsCellularVoiceCapableDevice() )
  {
    v20 = 0;
    v25 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.ApplicationModel.Calls.PhoneLine",
      0x29u,
      0x28u);
    v5 = v25;
    Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v20);
    ActivationFactory = RoGetActivationFactory(v5, &GUID_f38b5f23_ceb0_404f_bcf2_ba9f697d8adf, &v20);
    v4 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      Log_HREvent(
        (unsigned int)ActivationFactory,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistoryprop.cpp",
        162);
LABEL_20:
      Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v20);
      return v4;
    }
    v18 = 0;
    v23 = &v18;
    v21 = v20;
    v22 =  Windows::Storage::IStorageFileStatics::`vcall'{48,{flat}};
    hstringHeader.Reserved.Reserved1 = &v21;
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = &v22;
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = a1;
    v7 = AwaitResultHelper<Windows::ApplicationModel::Calls::PhoneLine *,_lambda_e62fddd3b23788c835871310dcdf9b7e_,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Calls::IPhoneLine>> &>(
           (__int64 **)&hstringHeader,
           &v23);
    v4 = v7;
    if ( v7 >= 0 )
    {
      v19 = 0;
      v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v18 + 120LL))(v18, &v19);
      v4 = v7;
      if ( v7 >= 0 )
      {
        if ( !v19 )
        {
          v11 = v18;
          string = 0;
          v12 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v18 + 88LL);
          WindowsDeleteString(0);
          string = 0;
          v13 = v12(v11, &string);
          v4 = v13;
          if ( v13 >= 0 )
          {
            StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
            v13 = DupString(a2, StringRawBuffer);
            v4 = v13;
            if ( v13 >= 0 )
            {
              WindowsDeleteString(string);
              string = 0;
              Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v18);
              v4 = 0;
              goto LABEL_20;
            }
            v14 = 177;
          }
          else
          {
            v14 = 176;
          }
          Log_HREvent(
            (unsigned int)v13,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistoryprop.cpp",
            v14);
          WindowsDeleteString(string);
          string = 0;
          goto LABEL_9;
        }
        v4 = -2147024809;
        v8 = 173;
        v10 = 2147942487LL;
        v9 = 0;
LABEL_8:
        Log_HREvent(
          v10,
          v9,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistoryprop.cpp",
          v8);
LABEL_9:
        Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v18);
        goto LABEL_20;
      }
      v8 = 172;
    }
    else
    {
      v8 = 169;
    }
    v9 = 1;
    v10 = (unsigned int)v7;
    goto LABEL_8;
  }
  v4 = -2147024809;
  Log_HREvent(
    2147942487LL,
    0,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistoryprop.cpp",
    156);
  return v4;
}

```

## disassembly

```asm
0x1800d93b8  push    rbp
0x1800d93ba  push    rbx
0x1800d93bb  push    rsi
0x1800d93bc  push    rdi
0x1800d93bd  lea     rbp, [rsp-3Fh]
0x1800d93c2  sub     rsp, 98h
0x1800d93c9  mov     rax, cs:__security_cookie
0x1800d93d0  xor     rax, rsp
0x1800d93d3  mov     [rbp+57h+var_28], rax
0x1800d93d7  mov     rsi, rdx
0x1800d93da  mov     qword ptr [rdx], 0
0x1800d93e1  mov     rdi, rcx
0x1800d93e4  call    cs:__imp_IsCellularVoiceCapableDevice
0x1800d93ea  test    al, al
0x1800d93ec  jnz     short loc_1800D940E
0x1800d93ee  mov     ebx, 80070057h
0x1800d93f3  lea     r8, aOnecoreuapBase_79; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800d93fa  mov     ecx, ebx
0x1800d93fc  mov     r9d, 9Ch
0x1800d9402  xor     edx, edx
0x1800d9404  call    Log_HREvent
0x1800d9409  jmp     loc_1800D95E2
0x1800d940e  mov     r9d, 28h ; '('; unsigned int
0x1800d9414  mov     [rbp+57h+var_68], 0
0x1800d941c  lea     rdx, ?RuntimeClass_Windows_ApplicationModel_Calls_PhoneLine@@3QBGB; "Windows.ApplicationModel.Calls.PhoneLin"...
0x1800d9423  mov     [rbp+57h+var_30], 0
0x1800d942b  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800d942f  lea     r8d, [r9+1]; unsigned int
0x1800d9433  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800d9438  mov     rbx, [rbp+57h+var_30]
0x1800d943c  lea     rcx, [rbp+57h+var_68]
0x1800d9440  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x1800d9445  lea     r8, [rbp+57h+var_68]
0x1800d9449  mov     rcx, rbx
0x1800d944c  lea     rdx, _GUID_f38b5f23_ceb0_404f_bcf2_ba9f697d8adf
0x1800d9453  call    cs:__imp_RoGetActivationFactory
0x1800d9459  mov     ebx, eax
0x1800d945b  test    eax, eax
0x1800d945d  jns     short loc_1800D947D
0x1800d945f  mov     r9d, 0A2h
0x1800d9465  lea     r8, aOnecoreuapBase_79; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800d946c  mov     edx, 1
0x1800d9471  mov     ecx, eax
0x1800d9473  call    Log_HREvent
0x1800d9478  jmp     loc_1800D95D9
0x1800d947d  lea     rax, [rbp+57h+var_78]
0x1800d9481  mov     [rbp+57h+var_78], 0
0x1800d9489  mov     [rbp+57h+var_50], rax
0x1800d948d  lea     rdx, [rbp+57h+var_50]
0x1800d9491  mov     rax, [rbp+57h+var_68]
0x1800d9495  lea     rcx, [rbp+57h+hstringHeader]
0x1800d9499  mov     [rbp+57h+var_60], rax
0x1800d949d  lea     rax, ??_9IStorageFileStatics@Storage@Windows@@$BDA@AA; [thunk]: Windows::Storage::IStorageFileStatics::`vcall'{48,{flat}}
0x1800d94a4  mov     [rbp+57h+var_58], rax
0x1800d94a8  lea     rax, [rbp+57h+var_60]
0x1800d94ac  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x1800d94b0  lea     rax, [rbp+57h+var_58]
0x1800d94b4  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], rax
0x1800d94b8  mov     qword ptr [rbp+57h+hstringHeader.Reserved+10h], rdi
0x1800d94bc  call    ??$AwaitResultHelper@PEAVPhoneLine@Calls@ApplicationModel@Windows@@V_lambda_e62fddd3b23788c835871310dcdf9b7e_@@AEAV?$ComPtrRef@V?$ComPtr@UIPhoneLine@Calls@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@@YAJAEBV_lambda_e62fddd3b23788c835871310dcdf9b7e_@@AEAV?$ComPtrRef@V?$ComPtr@UIPhoneLine@Calls@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; AwaitResultHelper<Windows::ApplicationModel::Calls::PhoneLine *,_lambda_e62fddd3b23788c835871310dcdf9b7e_,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Calls::IPhoneLine>> &>(_lambda_e62fddd3b23788c835871310dcdf9b7e_ const &,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Calls::IPhoneLine>> &)
0x1800d94c1  mov     ebx, eax
0x1800d94c3  test    eax, eax
0x1800d94c5  jns     short loc_1800D94EE
0x1800d94c7  mov     r9d, 0A9h
0x1800d94cd  mov     edx, 1
0x1800d94d2  mov     ecx, eax
0x1800d94d4  lea     r8, aOnecoreuapBase_79; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800d94db  call    Log_HREvent
0x1800d94e0  lea     rcx, [rbp+57h+var_78]
0x1800d94e4  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x1800d94e9  jmp     loc_1800D95D9
0x1800d94ee  mov     rcx, [rbp+57h+var_78]
0x1800d94f2  lea     rdx, [rbp+57h+var_70]
0x1800d94f6  mov     [rbp+57h+var_70], 0
0x1800d94fd  mov     rax, [rcx]
0x1800d9500  mov     rax, [rax+78h]
0x1800d9504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9509  mov     ebx, eax
0x1800d950b  test    eax, eax
0x1800d950d  jns     short loc_1800D9517
0x1800d950f  mov     r9d, 0ACh
0x1800d9515  jmp     short loc_1800D94CD
0x1800d9517  cmp     [rbp+57h+var_70], 0
0x1800d951b  jz      short loc_1800D952E
0x1800d951d  mov     ebx, 80070057h
0x1800d9522  mov     r9d, 0ADh
0x1800d9528  mov     ecx, ebx
0x1800d952a  xor     edx, edx
0x1800d952c  jmp     short loc_1800D94D4
0x1800d952e  mov     rdi, [rbp+57h+var_78]
0x1800d9532  xor     ecx, ecx; string
0x1800d9534  mov     [rbp+57h+string], 0
0x1800d953c  mov     rax, [rdi]
0x1800d953f  mov     rbx, [rax+58h]
0x1800d9543  call    cs:__imp_WindowsDeleteString
0x1800d9549  lea     rdx, [rbp+57h+string]
0x1800d954d  mov     [rbp+57h+string], 0
0x1800d9555  mov     rcx, rdi
0x1800d9558  mov     rax, rbx
0x1800d955b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9560  mov     ebx, eax
0x1800d9562  test    eax, eax
0x1800d9564  jns     short loc_1800D9596
0x1800d9566  mov     r9d, 0B0h
0x1800d956c  lea     r8, aOnecoreuapBase_79; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800d9573  mov     edx, 1
0x1800d9578  mov     ecx, eax
0x1800d957a  call    Log_HREvent
0x1800d957f  mov     rcx, [rbp+57h+string]; string
0x1800d9583  call    cs:__imp_WindowsDeleteString
0x1800d9589  mov     [rbp+57h+string], 0
0x1800d9591  jmp     loc_1800D94E0
0x1800d9596  mov     rcx, [rbp+57h+string]; string
0x1800d959a  xor     edx, edx; length
0x1800d959c  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d95a2  mov     rdx, rax
0x1800d95a5  mov     rcx, rsi
0x1800d95a8  call    cs:__imp_DupString
0x1800d95ae  mov     ebx, eax
0x1800d95b0  test    eax, eax
0x1800d95b2  jns     short loc_1800D95BC
0x1800d95b4  mov     r9d, 0B1h
0x1800d95ba  jmp     short loc_1800D956C
0x1800d95bc  mov     rcx, [rbp+57h+string]; string
0x1800d95c0  call    cs:__imp_WindowsDeleteString
0x1800d95c6  lea     rcx, [rbp+57h+var_78]
0x1800d95ca  mov     [rbp+57h+string], 0
0x1800d95d2  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x1800d95d7  xor     ebx, ebx
0x1800d95d9  lea     rcx, [rbp+57h+var_68]
0x1800d95dd  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x1800d95e2  mov     eax, ebx
0x1800d95e4  mov     rcx, [rbp+57h+var_28]
0x1800d95e8  xor     rcx, rsp; StackCookie
0x1800d95eb  call    __security_check_cookie
0x1800d95f0  add     rsp, 98h
0x1800d95f7  pop     rdi
0x1800d95f8  pop     rsi
0x1800d95f9  pop     rbx
0x1800d95fa  pop     rbp
0x1800d95fb  retn
```
