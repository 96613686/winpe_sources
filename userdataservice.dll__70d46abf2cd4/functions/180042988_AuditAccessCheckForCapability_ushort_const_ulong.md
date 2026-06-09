# AuditAccessCheckForCapability(ushort const *,ulong)

- ea: `0x180042988`
- end: `0x180042c50`
- name: `?AuditAccessCheckForCapability@@YAJPEBGK@Z`
- size: `712`
- prototype: `__int64 __fastcall(PCWSTR sourceString, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18006ce60`

## callees

- `0x180004658`
- `0x180008f0c`
- `0x180042988`
- `0x180042c94`
- `0x180042d18`
- `0x180042d64`
- `0x18007339c`
- `0x18012c7b0`
- `0x18012e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180042a66`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180042bd8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180042a66`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180042bd8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800429d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800429d7`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180042a00`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180042a00`

## string_xrefs

- `0x180042a73`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x180042a8d`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x180042be5`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x180042c07`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x180042c20`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x1800429d0`: `Windows.Internal.CapabilityAccess.CapabilityAccess`

## pseudocode

```c
__int64 __fastcall AuditAccessCheckForCapability(PCWSTR sourceString, int a2)
{
  HRESULT v4; // eax
  HSTRING v5; // rbx
  int ActivationFactory; // eax
  unsigned int *v7; // rdx
  unsigned int v8; // ebx
  int CallingProcessId; // eax
  _QWORD *v10; // rdi
  __int64 v11; // r14
  unsigned __int64 v12; // rbx
  __int64 v13; // rcx
  _QWORD *v14; // rcx
  unsigned int v16; // eax
  int v17; // eax
  int v18; // eax
  __int64 v19; // rcx
  _QWORD *v20; // rcx
  __int64 v21; // r9
  __int64 v22; // [rsp+40h] [rbp-40h] BYREF
  _QWORD *v23; // [rsp+48h] [rbp-38h] BYREF
  unsigned int v24; // [rsp+50h] [rbp-30h] BYREF
  int v25; // [rsp+54h] [rbp-2Ch] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-28h] BYREF
  HSTRING string; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v23 = 0;
  string = 0;
  v4 = WindowsCreateStringReference(
         L"Windows.Internal.CapabilityAccess.CapabilityAccess",
         0x32u,
         &hstringHeader,
         &string);
  if ( v4 < 0 )
  {
    RaiseException(v4, 1u, 0, 0);
    __debugbreak();
  }
  v5 = string;
  Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v23);
  ActivationFactory = RoGetActivationFactory(v5, &GUID_518f3880_4e5c_4524_ab03_cd01336b2178, &v23);
  v8 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    Log_HREvent(
      (unsigned int)ActivationFactory,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      57);
LABEL_11:
    v14 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v14 + 16LL))(v14);
    }
    return v8;
  }
  v24 = 0;
  CallingProcessId = UserAwareCallerIdentity::GetCallingProcessId((UserAwareCallerIdentity *)&v24, v7);
  v8 = CallingProcessId;
  if ( CallingProcessId < 0 )
  {
    Log_HREvent(
      (unsigned int)CallingProcessId,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      60);
LABEL_30:
    Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v23);
    return v8;
  }
  v10 = v23;
  v22 = 0;
  v11 = *v23;
  Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v22);
  v12 = -1;
  string = 0;
  do
    ++v12;
  while ( sourceString[v12] );
  if ( v12 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v16 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v12);
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, sourceString, v16, v12);
  v17 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, HSTRING, _QWORD))(v11 + 56))(v10, 0, string, v24);
  v8 = v17;
  if ( v17 < 0 )
  {
    v21 = 68;
LABEL_27:
    Log_HREvent(
      (unsigned int)v17,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      v21);
LABEL_29:
    Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(&v22);
    goto LABEL_30;
  }
  v25 = 3;
  v17 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v22 + 144LL))(v22, 3);
  v8 = v17;
  if ( v17 < 0 )
  {
    v21 = 71;
    goto LABEL_27;
  }
  v18 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v22 + 152LL))(v22, &v25);
  v8 = v18;
  if ( v18 < 0 )
  {
    Log_HREvent(
      (unsigned int)v18,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      73);
    v13 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    goto LABEL_11;
  }
  if ( v25 != 3 )
  {
    v8 = -2147024891;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4B,
      (unsigned int)"onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      (const char *)0x80070005LL,
      a2);
    goto LABEL_29;
  }
  v19 = v22;
  if ( v22 )
  {
    v22 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  }
  v20 = v23;
  if ( v23 )
  {
    v23 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v20 + 16LL))(v20);
  }
  return 0;
}

```

## disassembly

```asm
0x180042988  mov     [rsp-28h+arg_10], rbx
0x18004298d  mov     [rsp-28h+arg_18], rsi
0x180042992  push    rbp
0x180042993  push    rdi
0x180042994  push    r12
0x180042996  push    r14
0x180042998  push    r15
0x18004299a  mov     rbp, rsp
0x18004299d  sub     rsp, 80h
0x1800429a4  mov     rax, cs:__security_cookie
0x1800429ab  xor     rax, rsp
0x1800429ae  mov     [rbp+var_8], rax
0x1800429b2  xor     r12d, r12d
0x1800429b5  lea     r9, [rbp+string]; string
0x1800429b9  mov     r15d, edx
0x1800429bc  mov     [rbp+var_38], r12
0x1800429c0  mov     rsi, rcx
0x1800429c3  mov     [rbp+string], r12
0x1800429c7  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800429cb  lea     edx, [r12+32h]; length
0x1800429d0  lea     rcx, ?RuntimeClass_Windows_Internal_CapabilityAccess_CapabilityAccess@@3QBGB; "Windows.Internal.CapabilityAccess.Capab"...
0x1800429d7  call    cs:__imp_WindowsCreateStringReference
0x1800429dd  test    eax, eax
0x1800429df  js      loc_180042BCC
0x1800429e5  mov     rbx, [rbp+string]
0x1800429e9  lea     rcx, [rbp+var_38]
0x1800429ed  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x1800429f2  lea     r8, [rbp+var_38]
0x1800429f6  mov     rcx, rbx
0x1800429f9  lea     rdx, _GUID_518f3880_4e5c_4524_ab03_cd01336b2178
0x180042a00  call    cs:__imp_RoGetActivationFactory
0x180042a06  mov     ebx, eax
0x180042a08  test    eax, eax
0x180042a0a  js      short loc_180042A6D
0x180042a0c  lea     rcx, [rbp+var_30]; this
0x180042a10  mov     [rbp+var_30], r12d
0x180042a14  call    ?GetCallingProcessId@UserAwareCallerIdentity@@YAJPEAK@Z; UserAwareCallerIdentity::GetCallingProcessId(ulong *)
0x180042a19  mov     ebx, eax
0x180042a1b  test    eax, eax
0x180042a1d  js      loc_180042BDF
0x180042a23  mov     rdi, [rbp+var_38]
0x180042a27  lea     rcx, [rbp+var_40]
0x180042a2b  mov     [rbp+var_40], r12
0x180042a2f  mov     r14, [rdi]
0x180042a32  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x180042a37  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180042a3b  mov     [rbp+string], r12
0x180042a3f  inc     rbx
0x180042a42  cmp     [rsi+rbx*2], r12w
0x180042a47  jnz     short loc_180042A3F
0x180042a49  mov     eax, 0FFFFFFFFh
0x180042a4e  cmp     rbx, rax
0x180042a51  jbe     loc_180042AD8
0x180042a57  xor     r9d, r9d; lpArguments
0x180042a5a  xor     r8d, r8d; nNumberOfArguments
0x180042a5d  mov     ecx, 80070216h; dwExceptionCode
0x180042a62  lea     edx, [r9+1]; dwExceptionFlags
0x180042a66  call    cs:__imp_RaiseException
0x180042a6c  int     3; Trap to Debugger
0x180042a6d  mov     r9d, 39h ; '9'
0x180042a73  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180042a7a  mov     ecx, ebx
0x180042a7c  lea     edx, [r9-38h]
0x180042a80  call    Log_HREvent
0x180042a85  jmp     short loc_180042AB8
0x180042a87  mov     r9d, 49h ; 'I'
0x180042a8d  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180042a94  mov     ecx, ebx
0x180042a96  lea     edx, [r9-48h]
0x180042a9a  call    Log_HREvent
0x180042a9f  mov     rcx, [rbp+var_40]
0x180042aa3  test    rcx, rcx
0x180042aa6  jz      short loc_180042AB8
0x180042aa8  mov     [rbp+var_40], r12
0x180042aac  mov     rax, [rcx]
0x180042aaf  mov     rax, [rax+10h]
0x180042ab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042ab8  mov     rcx, [rbp+var_38]
0x180042abc  test    rcx, rcx
0x180042abf  jz      short loc_180042AD1
0x180042ac1  mov     [rbp+var_38], r12
0x180042ac5  mov     rax, [rcx]
0x180042ac8  mov     rax, [rax+10h]
0x180042acc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042ad1  mov     eax, ebx
0x180042ad3  jmp     loc_180042BA4
0x180042ad8  mov     ecx, ebx; unsigned int
0x180042ada  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180042adf  mov     r9d, ebx; unsigned int
0x180042ae2  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180042ae6  mov     r8d, eax; unsigned int
0x180042ae9  mov     rdx, rsi; sourceString
0x180042aec  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180042af1  mov     r9d, [rbp+var_30]
0x180042af5  lea     rax, [rbp+var_40]
0x180042af9  mov     r8, [rbp+string]
0x180042afd  xor     edx, edx
0x180042aff  mov     [rsp+80h+var_58], rax
0x180042b04  mov     rcx, rdi
0x180042b07  mov     rax, [r14+38h]
0x180042b0b  mov     [rsp+80h+var_60], r15d; int
0x180042b10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042b15  mov     ebx, eax
0x180042b17  test    eax, eax
0x180042b19  js      loc_180042BF9
0x180042b1f  mov     rcx, [rbp+var_40]
0x180042b23  mov     edi, 3
0x180042b28  mov     [rbp+var_2C], edi
0x180042b2b  mov     edx, edi
0x180042b2d  mov     rax, [rcx]
0x180042b30  mov     rax, [rax+90h]
0x180042b37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042b3c  mov     ebx, eax
0x180042b3e  test    eax, eax
0x180042b40  js      loc_180042C01
0x180042b46  mov     rcx, [rbp+var_40]
0x180042b4a  lea     rdx, [rbp+var_2C]
0x180042b4e  mov     rax, [rcx]
0x180042b51  mov     rax, [rax+98h]
0x180042b58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042b5d  mov     ebx, eax
0x180042b5f  test    eax, eax
0x180042b61  js      loc_180042A87
0x180042b67  cmp     [rbp+var_2C], edi
0x180042b6a  jnz     loc_180042C1C
0x180042b70  mov     rcx, [rbp+var_40]
0x180042b74  test    rcx, rcx
0x180042b77  jz      short loc_180042B89
0x180042b79  mov     [rbp+var_40], r12
0x180042b7d  mov     rax, [rcx]
0x180042b80  mov     rax, [rax+10h]
0x180042b84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042b89  mov     rcx, [rbp+var_38]
0x180042b8d  test    rcx, rcx
0x180042b90  jz      short loc_180042BA2
0x180042b92  mov     [rbp+var_38], r12
0x180042b96  mov     rax, [rcx]
0x180042b99  mov     rax, [rax+10h]
0x180042b9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042ba2  xor     eax, eax
0x180042ba4  mov     rcx, [rbp+var_8]
0x180042ba8  xor     rcx, rsp; StackCookie
0x180042bab  call    __security_check_cookie
0x180042bb0  lea     r11, [rsp+80h+var_s0]
0x180042bb8  mov     rbx, [r11+40h]
0x180042bbc  mov     rsi, [r11+48h]
0x180042bc0  mov     rsp, r11
0x180042bc3  pop     r15
0x180042bc5  pop     r14
0x180042bc7  pop     r12
0x180042bc9  pop     rdi
0x180042bca  pop     rbp
0x180042bcb  retn
0x180042bcc  xor     r9d, r9d; lpArguments
0x180042bcf  xor     r8d, r8d; nNumberOfArguments
0x180042bd2  mov     ecx, eax; dwExceptionCode
0x180042bd4  lea     edx, [r9+1]; dwExceptionFlags
0x180042bd8  call    cs:__imp_RaiseException
0x180042bde  int     3; Trap to Debugger
0x180042bdf  mov     r9d, 3Ch ; '<'
0x180042be5  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180042bec  mov     ecx, eax
0x180042bee  lea     edx, [r9-3Bh]
0x180042bf2  call    Log_HREvent
0x180042bf7  jmp     short loc_180042C42
0x180042bf9  mov     r9d, 44h ; 'D'
0x180042bff  jmp     short loc_180042C07
0x180042c01  mov     r9d, 47h ; 'G'
0x180042c07  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180042c0e  mov     edx, 1
0x180042c13  mov     ecx, eax
0x180042c15  call    Log_HREvent
0x180042c1a  jmp     short loc_180042C39
0x180042c1c  mov     rcx, [rbp+28h]; this
0x180042c20  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180042c27  mov     ebx, 80070005h
0x180042c2c  mov     edx, 4Bh ; 'K'; void *
0x180042c31  mov     r9d, ebx; char *
0x180042c34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042c39  lea     rcx, [rbp+var_40]
0x180042c3d  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x180042c42  lea     rcx, [rbp+var_38]
0x180042c46  call    ?InternalRelease@?$ComPtr@U?$OperationCallback@PEAVAccount@Sync@Experiences@PhoneInternal@@@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OperationCallback<PhoneInternal::Experiences::Sync::Account *>>::InternalRelease(void)
0x180042c4b  jmp     loc_180042AD1
```
