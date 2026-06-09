# Windows::Internal::Notifications::CAppInfoProvider_UWP::FindAppInfo(HSTRING__ *,Windows::ApplicationModel::IAppInfo * *)

- ea: `0x180006d30`
- end: `0x1800070e0`
- name: `?FindAppInfo@CAppInfoProvider_UWP@Notifications@Internal@Windows@@UEAAJPEAUHSTRING__@@PEAPEAUIAppInfo@ApplicationModel@4@@Z`
- size: `944`
- prototype: `__int64 __fastcall(Windows::Internal::Notifications::CAppInfoProvider_UWP *__hidden this, HSTRING, struct Windows::ApplicationModel::IAppInfo **)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180005670`
- `0x180006d30`
- `0x1800070e8`
- `0x18001ff00`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180007080`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000709b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180007080`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000709b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180006d83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180006ea0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180006d83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180006ea0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180006dbd`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180006ec9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180006dbd`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180006ec9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::Notifications::CAppInfoProvider_UWP::FindAppInfo(
        Windows::Internal::Notifications::CAppInfoProvider_UWP *this,
        HSTRING a2,
        struct Windows::ApplicationModel::IAppInfo **a3)
{
  int ActivationFactory; // eax
  unsigned int v6; // ebx
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rcx
  __int64 v10; // rcx
  int v12; // eax
  unsigned int v13; // ebx
  HSTRING v14; // rbx
  int v15; // eax
  unsigned int v16; // ebx
  int v17; // eax
  unsigned int v18; // ebx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  int v28; // [rsp+20h] [rbp-60h]
  __int64 v29; // [rsp+30h] [rbp-50h] BYREF
  __int64 v30; // [rsp+38h] [rbp-48h] BYREF
  __int64 v31; // [rsp+40h] [rbp-40h] BYREF
  __int64 v32; // [rsp+48h] [rbp-38h] BYREF
  HSTRING string; // [rsp+50h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  if ( a3 )
  {
    *a3 = 0;
    v29 = 0;
    if ( WindowsCreateStringReference(L"Windows.Internal.StateRepository.Application", 0x2Cu, &hstringHeader, &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    ActivationFactory = RoGetActivationFactory(string, &GUID_07adcc9a_e505_48c2_b471_45af8561f6af, &v29);
    v6 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\cappinfoprovider_uwp.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v28);
      v22 = v29;
      if ( v29 )
      {
        v29 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      }
      return v6;
    }
    else
    {
      v30 = 0;
      v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, HSTRING, __int64 *))(*(_QWORD *)v29 + 240LL))(v29, 0, a2, &v30);
      v8 = v7;
      if ( v7 >= 0 )
      {
        v32 = 0;
        v12 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v30 + 48LL))(v30, &v32);
        v13 = v12;
        if ( v12 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x30,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\cappinfoprovider_uwp.cpp",
            (const char *)(unsigned int)v12,
            v28);
          v26 = v30;
          if ( v30 )
          {
            v30 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
          }
          v27 = v29;
          if ( v29 )
          {
            v29 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
          }
          return v13;
        }
        else
        {
          v31 = 0;
          if ( WindowsCreateStringReference(L"Windows.ApplicationModel.AppInfo", 0x20u, &hstringHeader, &string) < 0 )
            RaiseException(0xC000000D, 1u, 0, 0);
          v14 = string;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
          v15 = RoGetActivationFactory(v14, &GUID_32cb3d52_6a9e_45b6_8d83_95b6458efcc0, &v31);
          v16 = v15;
          if ( v15 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x35,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\cappinfoprovider_uwp.cpp",
              (const char *)(unsigned int)v15,
              v28);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
            return v16;
          }
          else
          {
            v17 = (*(__int64 (__fastcall **)(__int64, __int64, struct Windows::ApplicationModel::IAppInfo **))(*(_QWORD *)v31 + 48LL))(
                    v31,
                    v32,
                    a3);
            v18 = v17;
            if ( v17 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x37,
                (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\cappinfoprovider_uwp.cpp",
                (const char *)(unsigned int)v17,
                v28);
              v23 = v31;
              if ( v31 )
              {
                v31 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
              }
              v24 = v30;
              if ( v30 )
              {
                v30 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
              }
              v25 = v29;
              if ( v29 )
              {
                v29 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
              }
              return v18;
            }
            else
            {
              v19 = v31;
              if ( v31 )
              {
                v31 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
              }
              v20 = v30;
              if ( v30 )
              {
                v30 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
              }
              v21 = v29;
              if ( v29 )
              {
                v29 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
              }
              return 0;
            }
          }
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2D,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\cappinfoprovider_uwp.cpp",
          (const char *)(unsigned int)v7,
          v28);
        v9 = v30;
        if ( v30 )
        {
          v30 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
        }
        v10 = v29;
        if ( v29 )
        {
          v29 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
        }
        return v8;
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\cappinfoprovider_uwp.cpp",
      (const char *)0x80004003LL,
      v28);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x180006d30  mov     [rsp-18h+arg_0], rbx
0x180006d35  mov     [rsp-18h+arg_18], rsi
0x180006d3a  push    rbp
0x180006d3b  push    rdi
0x180006d3c  push    r14
0x180006d3e  mov     rbp, rsp
0x180006d41  sub     rsp, 80h
0x180006d48  mov     rax, cs:__security_cookie
0x180006d4f  xor     rax, rsp
0x180006d52  mov     [rbp+var_10], rax
0x180006d56  mov     rdi, r8
0x180006d59  mov     rsi, rdx
0x180006d5c  test    r8, r8
0x180006d5f  jz      loc_180006F89
0x180006d65  xor     r14d, r14d
0x180006d68  mov     [r8], r14
0x180006d6b  mov     [rbp+var_50], r14
0x180006d6f  lea     r9, [rbp+string]; string
0x180006d73  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180006d77  mov     edx, 2Ch ; ','; length
0x180006d7c  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_Application@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x180006d83  call    cs:__imp_WindowsCreateStringReference
0x180006d89  test    eax, eax
0x180006d8b  js      loc_180007070
0x180006d91  mov     rbx, [rbp+string]
0x180006d95  mov     rcx, [rbp+var_50]
0x180006d99  test    rcx, rcx
0x180006d9c  jz      short loc_180006DAF
0x180006d9e  mov     [rbp+var_50], r14
0x180006da2  mov     rax, [rcx]
0x180006da5  mov     rax, [rax+10h]
0x180006da9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006dae  nop
0x180006daf  lea     r8, [rbp+var_50]
0x180006db3  lea     rdx, _GUID_07adcc9a_e505_48c2_b471_45af8561f6af
0x180006dba  mov     rcx, rbx
0x180006dbd  call    cs:__imp_RoGetActivationFactory
0x180006dc3  mov     ebx, eax
0x180006dc5  test    eax, eax
0x180006dc7  js      loc_180006F4F
0x180006dcd  mov     [rbp+var_48], r14
0x180006dd1  mov     rcx, [rbp+var_50]
0x180006dd5  mov     rax, [rcx]
0x180006dd8  lea     r9, [rbp+var_48]
0x180006ddc  mov     r8, rsi
0x180006ddf  xor     edx, edx
0x180006de1  mov     rax, [rax+0F0h]
0x180006de8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ded  mov     ebx, eax
0x180006def  test    eax, eax
0x180006df1  jns     short loc_180006E66
0x180006df3  mov     rcx, [rbp+18h]; this
0x180006df7  mov     r9d, eax; char *
0x180006dfa  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180006e01  mov     edx, 2Dh ; '-'; void *
0x180006e06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006e0b  nop
0x180006e0c  mov     rcx, [rbp+var_48]
0x180006e10  test    rcx, rcx
0x180006e13  jz      short loc_180006E26
0x180006e15  mov     [rbp+var_48], r14
0x180006e19  mov     rax, [rcx]
0x180006e1c  mov     rax, [rax+10h]
0x180006e20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e25  nop
0x180006e26  mov     rcx, [rbp+var_50]
0x180006e2a  test    rcx, rcx
0x180006e2d  jz      short loc_180006E40
0x180006e2f  mov     [rbp+var_50], r14
0x180006e33  mov     rax, [rcx]
0x180006e36  mov     rax, [rax+10h]
0x180006e3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e3f  nop
0x180006e40  mov     eax, ebx
0x180006e42  mov     rcx, [rbp+var_10]
0x180006e46  xor     rcx, rsp; StackCookie
0x180006e49  call    __security_check_cookie
0x180006e4e  lea     r11, [rsp+80h+var_s0]
0x180006e56  mov     rbx, [r11+20h]
0x180006e5a  mov     rsi, [r11+38h]
0x180006e5e  mov     rsp, r11
0x180006e61  pop     r14
0x180006e63  pop     rdi
0x180006e64  pop     rbp
0x180006e65  retn
0x180006e66  mov     [rbp+var_38], r14
0x180006e6a  mov     rcx, [rbp+var_48]
0x180006e6e  mov     rax, [rcx]
0x180006e71  lea     rdx, [rbp+var_38]
0x180006e75  mov     rax, [rax+30h]
0x180006e79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e7e  mov     ebx, eax
0x180006e80  test    eax, eax
0x180006e82  js      loc_18000701C
0x180006e88  mov     [rbp+var_40], r14
0x180006e8c  lea     r9, [rbp+string]; string
0x180006e90  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180006e94  mov     edx, 20h ; ' '; length
0x180006e99  lea     rcx, ?RuntimeClass_Windows_ApplicationModel_AppInfo@@3QBGB; "Windows.ApplicationModel.AppInfo"
0x180006ea0  call    cs:__imp_WindowsCreateStringReference
0x180006ea6  test    eax, eax
0x180006ea8  js      loc_18000708B
0x180006eae  mov     rbx, [rbp+string]
0x180006eb2  lea     rcx, [rbp+var_40]
0x180006eb6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180006ebb  lea     r8, [rbp+var_40]
0x180006ebf  lea     rdx, _GUID_32cb3d52_6a9e_45b6_8d83_95b6458efcc0
0x180006ec6  mov     rcx, rbx
0x180006ec9  call    cs:__imp_RoGetActivationFactory
0x180006ecf  mov     ebx, eax
0x180006ed1  test    eax, eax
0x180006ed3  js      loc_1800070A6
0x180006ed9  mov     rcx, [rbp+var_40]
0x180006edd  mov     rax, [rcx]
0x180006ee0  mov     r8, rdi
0x180006ee3  mov     rdx, [rbp+var_38]
0x180006ee7  mov     rax, [rax+30h]
0x180006eeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ef0  mov     ebx, eax
0x180006ef2  test    eax, eax
0x180006ef4  js      loc_180006FAE
0x180006efa  mov     rcx, [rbp+var_40]
0x180006efe  test    rcx, rcx
0x180006f01  jz      short loc_180006F14
0x180006f03  mov     [rbp+var_40], r14
0x180006f07  mov     rax, [rcx]
0x180006f0a  mov     rax, [rax+10h]
0x180006f0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f13  nop
0x180006f14  mov     rcx, [rbp+var_48]
0x180006f18  test    rcx, rcx
0x180006f1b  jz      short loc_180006F2E
0x180006f1d  mov     [rbp+var_48], r14
0x180006f21  mov     rax, [rcx]
0x180006f24  mov     rax, [rax+10h]
0x180006f28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f2d  nop
0x180006f2e  mov     rcx, [rbp+var_50]
0x180006f32  test    rcx, rcx
0x180006f35  jz      short loc_180006F48
0x180006f37  mov     [rbp+var_50], r14
0x180006f3b  mov     rax, [rcx]
0x180006f3e  mov     rax, [rax+10h]
0x180006f42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f47  nop
0x180006f48  xor     eax, eax
0x180006f4a  jmp     loc_180006E42
0x180006f4f  mov     rcx, [rbp+18h]; this
0x180006f53  mov     r9d, ebx; char *
0x180006f56  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180006f5d  mov     edx, 2Ah ; '*'; void *
0x180006f62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006f67  nop
0x180006f68  mov     rcx, [rbp+var_50]
0x180006f6c  test    rcx, rcx
0x180006f6f  jz      short loc_180006F82
0x180006f71  mov     [rbp+var_50], r14
0x180006f75  mov     rax, [rcx]
0x180006f78  mov     rax, [rax+10h]
0x180006f7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f81  nop
0x180006f82  mov     eax, ebx
0x180006f84  jmp     loc_180006E42
0x180006f89  mov     rcx, [rbp+18h]; this
0x180006f8d  mov     r9d, 80004003h; char *
0x180006f93  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180006f9a  mov     edx, 24h ; '$'; void *
0x180006f9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006fa4  mov     eax, 80004003h
0x180006fa9  jmp     loc_180006E42
0x180006fae  mov     rcx, [rbp+18h]; this
0x180006fb2  mov     r9d, ebx; char *
0x180006fb5  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180006fbc  mov     edx, 37h ; '7'; void *
0x180006fc1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006fc6  nop
0x180006fc7  mov     rcx, [rbp+var_40]
0x180006fcb  test    rcx, rcx
0x180006fce  jz      short loc_180006FE1
0x180006fd0  mov     [rbp+var_40], r14
0x180006fd4  mov     rax, [rcx]
0x180006fd7  mov     rax, [rax+10h]
0x180006fdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fe0  nop
0x180006fe1  mov     rcx, [rbp+var_48]
0x180006fe5  test    rcx, rcx
0x180006fe8  jz      short loc_180006FFB
0x180006fea  mov     [rbp+var_48], r14
0x180006fee  mov     rax, [rcx]
0x180006ff1  mov     rax, [rax+10h]
0x180006ff5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ffa  nop
0x180006ffb  mov     rcx, [rbp+var_50]
0x180006fff  test    rcx, rcx
0x180007002  jz      short loc_180007015
0x180007004  mov     [rbp+var_50], r14
0x180007008  mov     rax, [rcx]
0x18000700b  mov     rax, [rax+10h]
0x18000700f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007014  nop
0x180007015  mov     eax, ebx
0x180007017  jmp     loc_180006E42
0x18000701c  mov     rcx, [rbp+18h]; this
0x180007020  mov     r9d, ebx; char *
0x180007023  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000702a  mov     edx, 30h ; '0'; void *
0x18000702f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007034  nop
0x180007035  mov     rcx, [rbp+var_48]
0x180007039  test    rcx, rcx
0x18000703c  jz      short loc_18000704F
0x18000703e  mov     [rbp+var_48], r14
0x180007042  mov     rax, [rcx]
0x180007045  mov     rax, [rax+10h]
0x180007049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000704e  nop
0x18000704f  mov     rcx, [rbp+var_50]
0x180007053  test    rcx, rcx
0x180007056  jz      short loc_180007069
0x180007058  mov     [rbp+var_50], r14
0x18000705c  mov     rax, [rcx]
0x18000705f  mov     rax, [rax+10h]
0x180007063  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007068  nop
0x180007069  mov     eax, ebx
0x18000706b  jmp     loc_180006E42
0x180007070  xor     r9d, r9d; lpArguments
0x180007073  xor     r8d, r8d; nNumberOfArguments
0x180007076  mov     edx, 1; dwExceptionFlags
0x18000707b  mov     ecx, 0C000000Dh; dwExceptionCode
0x180007080  call    cs:__imp_RaiseException
0x180007086  jmp     loc_180006D91
0x18000708b  xor     r9d, r9d; lpArguments
0x18000708e  xor     r8d, r8d; nNumberOfArguments
0x180007091  mov     edx, 1; dwExceptionFlags
0x180007096  mov     ecx, 0C000000Dh; dwExceptionCode
0x18000709b  call    cs:__imp_RaiseException
0x1800070a1  jmp     loc_180006EAE
0x1800070a6  mov     rcx, [rbp+18h]; this
0x1800070aa  mov     r9d, ebx; char *
0x1800070ad  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800070b4  mov     edx, 35h ; '5'; void *
0x1800070b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800070be  lea     rcx, [rbp+var_40]
0x1800070c2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800070c7  lea     rcx, [rbp+var_48]
0x1800070cb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800070d0  lea     rcx, [rbp+var_50]
0x1800070d4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800070d9  mov     eax, ebx
0x1800070db  jmp     loc_180006E42
```
