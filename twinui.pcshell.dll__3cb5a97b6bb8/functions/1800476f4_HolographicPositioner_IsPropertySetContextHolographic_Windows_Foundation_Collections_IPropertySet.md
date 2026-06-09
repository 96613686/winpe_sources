# HolographicPositioner::_IsPropertySetContextHolographic(Windows::Foundation::Collections::IPropertySet *)

- ea: `0x1800476f4`
- end: `0x1800479b4`
- name: `?_IsPropertySetContextHolographic@HolographicPositioner@@AEAA?AW4HolographicDetermination@@PEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `704`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800da8ac`

## callees

- `0x1800134f8`
- `0x18001f6e0`
- `0x180031c70`
- `0x180045dfc`
- `0x1800475dc`
- `0x1800476f4`
- `0x18005d940`
- `0x18007b3e0`
- `0x1800d9db4`
- `0x1801407b0`
- `0x180356360`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800478a8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180047930`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180047943`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180047956`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004797a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800478a8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180047930`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180047943`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180047956`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004797a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180047747`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180047782`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800477c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004783b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180047747`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180047782`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800477c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004783b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall HolographicPositioner::_IsPropertySetContextHolographic(__int64 a1, __int64 a2)
{
  HRESULT v3; // eax
  HRESULT v4; // eax
  HRESULT v5; // eax
  __int64 v6; // r8
  char v7; // al
  unsigned __int64 v8; // rdi
  unsigned int v9; // eax
  UINT32 v10; // edx
  HRESULT v11; // eax
  __int64 v12; // r8
  unsigned int v13; // eax
  __int64 v15; // rsi
  unsigned int v16; // edi
  __int64 v17; // rcx
  int v18; // eax
  int v19; // eax
  __int64 v20; // r8
  int v21; // [rsp+20h] [rbp-50h] BYREF
  int v22; // [rsp+24h] [rbp-4Ch] BYREF
  __int64 v23; // [rsp+28h] [rbp-48h] BYREF
  unsigned int v24; // [rsp+30h] [rbp-40h] BYREF
  int v25; // [rsp+34h] [rbp-3Ch] BYREF
  HWND v26; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  HSTRING string; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  v22 = 0;
  v23 = a2;
  Microsoft::WRL::ComPtr<IWindowingEnvironmentConfig>::InternalAddRef(&v23);
  string = 0;
  v3 = WindowsCreateStringReference(L"AppInstanceId", 0xDu, &hstringHeader, &string);
  if ( v3 < 0 )
  {
    RaiseException(v3, 1u, 0, 0);
    __debugbreak();
  }
  if ( Windows::Internal::ShellHelpers::PropertySetHelper::HasKey(
         (Windows::Internal::ShellHelpers::PropertySetHelper *)&v23,
         string) )
  {
    goto LABEL_37;
  }
  string = 0;
  v4 = WindowsCreateStringReference(L"DesignatedHolographicLaunch", 0x1Bu, &hstringHeader, &string);
  if ( v4 < 0 )
  {
    RaiseException(v4, 1u, 0, 0);
    __debugbreak();
  }
  if ( Windows::Internal::ShellHelpers::PropertySetHelper::HasKey(
         (Windows::Internal::ShellHelpers::PropertySetHelper *)&v23,
         string) )
  {
    goto LABEL_37;
  }
  v25 = 0;
  string = 0;
  v5 = WindowsCreateStringReference(L"ClientRequestedNavigationType", 0x1Du, &hstringHeader, &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
  }
  else
  {
    v22 = 1;
    if ( (int)Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<unsigned int>(&v23, string, v6, &v25) < 0 )
    {
LABEL_7:
      v7 = 0;
      goto LABEL_8;
    }
  }
  v7 = 1;
  if ( v25 != 1 )
    goto LABEL_7;
LABEL_8:
  if ( v7 )
  {
    LODWORD(v26) = 0;
    string = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"SwitchAsync_IdTo", 0x11u, 0x10u);
    if ( (int)Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<unsigned int>(&v23, string, v20, &v26) >= 0 )
    {
      v21 = 0;
      if ( (int)HolographicPositioner::IsWindowManaged(
                  (HolographicPositioner *)(a1 + 136),
                  (HWND)(unsigned int)v26,
                  &v21) >= 0 )
      {
        v16 = (v21 != 0) + 1;
        goto LABEL_27;
      }
    }
  }
  v24 = 0;
  string = 0;
  v8 = -1;
  do
    ++v8;
  while ( aViewsizeprefer_1[v8] );
  if ( v8 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v8);
  v10 = v9 - 1;
  if ( (unsigned int)v8 < v9 )
    v10 = v8;
  v11 = WindowsCreateStringReference(L"ViewSizePreferences.SourceWindow", v10, &hstringHeader, &string);
  if ( v11 < 0 )
  {
    RaiseException(v11, 1u, 0, 0);
    __debugbreak();
  }
  if ( (int)Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<unsigned int>(&v23, string, v12, &v24) >= 0 )
  {
    v13 = v24;
  }
  else
  {
    v13 = 0;
    v24 = 0;
  }
  if ( !v13 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
    return 0;
  }
  v15 = v13;
  v16 = 0;
  v21 = 0;
  if ( (int)Windows::Internal::Shell::Holographic::GetWindowDisplayContext(v13, 1, &v21) < 0 )
  {
LABEL_22:
    v17 = *(_QWORD *)(a1 + 256);
    if ( v17 )
    {
      v22 = 0;
      v18 = (*(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v17 + 40LL))(v17, v15, &v22);
      if ( v18 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x586,
          (unsigned int)"pcshell\\twinui\\holographicpositioner\\lib\\holographicpositioner.cpp",
          (const char *)(unsigned int)v18,
          v21);
      }
      else
      {
        v19 = v16;
        if ( v22 )
          v19 = 2;
        v16 = v19;
      }
    }
    goto LABEL_27;
  }
  if ( v21 != 1 )
  {
    v16 = 1;
    goto LABEL_22;
  }
LABEL_37:
  v16 = 2;
LABEL_27:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
  return v16;
}

```

## disassembly

```asm
0x1800476f4  mov     [rsp-18h+arg_8], rsi
0x1800476f9  mov     [rsp-18h+arg_10], rdi
0x1800476fe  push    rbp
0x1800476ff  push    r14
0x180047701  push    r15
0x180047703  mov     rbp, rsp
0x180047706  sub     rsp, 70h
0x18004770a  mov     rax, cs:__security_cookie
0x180047711  xor     rax, rsp
0x180047714  mov     [rbp+var_10], rax
0x180047718  mov     r14, rcx
0x18004771b  xor     r15d, r15d
0x18004771e  mov     [rbp+var_4C], r15d
0x180047722  mov     [rbp+var_48], rdx
0x180047726  lea     rcx, [rbp+var_48]
0x18004772a  call    ?InternalAddRef@?$ComPtr@UIWindowingEnvironmentConfig@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IWindowingEnvironmentConfig>::InternalAddRef(void)
0x18004772f  nop
0x180047730  mov     [rbp+string], r15
0x180047734  lea     r9, [rbp+string]; string
0x180047738  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18004773c  lea     edx, [r15+0Dh]; length
0x180047740  lea     rcx, aAppinstanceid; "AppInstanceId"
0x180047747  call    cs:__imp_WindowsCreateStringReference
0x18004774d  test    eax, eax
0x18004774f  js      loc_180047924
0x180047755  mov     rdx, [rbp+string]; HSTRING
0x180047759  lea     rcx, [rbp+var_48]; this
0x18004775d  call    ?HasKey@PropertySetHelper@ShellHelpers@Internal@Windows@@QEAA_NPEAUHSTRING__@@@Z; Windows::Internal::ShellHelpers::PropertySetHelper::HasKey(HSTRING__ *)
0x180047762  nop
0x180047763  test    al, al
0x180047765  jnz     loc_1800479AA
0x18004776b  mov     [rbp+string], r15
0x18004776f  lea     r9, [rbp+string]; string
0x180047773  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180047777  lea     edx, [r15+1Bh]; length
0x18004777b  lea     rcx, aDesignatedholo; "DesignatedHolographicLaunch"
0x180047782  call    cs:__imp_WindowsCreateStringReference
0x180047788  test    eax, eax
0x18004778a  js      loc_180047937
0x180047790  mov     rdx, [rbp+string]; HSTRING
0x180047794  lea     rcx, [rbp+var_48]; this
0x180047798  call    ?HasKey@PropertySetHelper@ShellHelpers@Internal@Windows@@QEAA_NPEAUHSTRING__@@@Z; Windows::Internal::ShellHelpers::PropertySetHelper::HasKey(HSTRING__ *)
0x18004779d  nop
0x18004779e  test    al, al
0x1800477a0  jnz     loc_1800479AA
0x1800477a6  mov     [rbp+var_3C], r15d
0x1800477aa  mov     [rbp+string], r15
0x1800477ae  lea     r9, [rbp+string]; string
0x1800477b2  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800477b6  lea     edx, [r15+1Dh]; length
0x1800477ba  lea     rcx, aClientrequeste; "ClientRequestedNavigationType"
0x1800477c1  call    cs:__imp_WindowsCreateStringReference
0x1800477c7  test    eax, eax
0x1800477c9  js      loc_18004794A
0x1800477cf  mov     [rbp+var_4C], 1
0x1800477d6  lea     r9, [rbp+var_3C]
0x1800477da  mov     rdx, [rbp+string]
0x1800477de  lea     rcx, [rbp+var_48]
0x1800477e2  call    ??$GetValue@I@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValue@Foundation@3@EAAJPEAI@Z1@Z; Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<uint>(HSTRING__ *,long (Windows::Foundation::IPropertyValue::*)(uint *),uint *)
0x1800477e7  test    eax, eax
0x1800477e9  jns     loc_18004795D
0x1800477ef  mov     al, r15b
0x1800477f2  test    al, al
0x1800477f4  jnz     loc_1806EDABA
0x1800477fa  mov     [rbp+var_40], r15d
0x1800477fe  mov     [rbp+string], r15
0x180047802  mov     rsi, cs:off_1806FE780; "ViewSizePreferences.SourceWindow"
0x180047809  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004780d  inc     rdi
0x180047810  cmp     [rsi+rdi*2], r15w
0x180047815  jnz     short loc_18004780D
0x180047817  mov     eax, 0FFFFFFFFh
0x18004781c  cmp     rdi, rax
0x18004781f  ja      short loc_180047899
0x180047821  mov     ecx, edi; unsigned int
0x180047823  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180047828  lea     edx, [rax-1]
0x18004782b  cmp     edi, eax
0x18004782d  cmovb   edx, edi; length
0x180047830  lea     r9, [rbp+string]; string
0x180047834  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180047838  mov     rcx, rsi; sourceString
0x18004783b  call    cs:__imp_WindowsCreateStringReference
0x180047841  test    eax, eax
0x180047843  js      loc_18004796E
0x180047849  lea     r9, [rbp+var_40]
0x18004784d  mov     rdx, [rbp+string]
0x180047851  lea     rcx, [rbp+var_48]
0x180047855  call    ??$GetValue@I@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValue@Foundation@3@EAAJPEAI@Z1@Z; Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<uint>(HSTRING__ *,long (Windows::Foundation::IPropertyValue::*)(uint *),uint *)
0x18004785a  nop
0x18004785b  shr     eax, 1Fh
0x18004785e  test    al, al
0x180047860  jz      short loc_1800478AF
0x180047862  mov     eax, r15d
0x180047865  mov     [rbp+var_40], eax
0x180047868  test    eax, eax
0x18004786a  jnz     short loc_1800478B4
0x18004786c  lea     rcx, [rbp+var_48]
0x180047870  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180047875  xor     eax, eax
0x180047877  mov     rcx, [rbp+var_10]
0x18004787b  xor     rcx, rsp; StackCookie
0x18004787e  call    __security_check_cookie
0x180047883  lea     r11, [rsp+70h+var_s0]
0x180047888  mov     rsi, [r11+28h]
0x18004788c  mov     rdi, [r11+30h]
0x180047890  mov     rsp, r11
0x180047893  pop     r15
0x180047895  pop     r14
0x180047897  pop     rbp
0x180047898  retn
0x180047899  xor     r9d, r9d; lpArguments
0x18004789c  xor     r8d, r8d; nNumberOfArguments
0x18004789f  lea     edx, [r9+1]; dwExceptionFlags
0x1800478a3  mov     ecx, 80070216h; dwExceptionCode
0x1800478a8  call    cs:__imp_RaiseException
0x1800478ae  int     3; Trap to Debugger
0x1800478af  mov     eax, [rbp+var_40]
0x1800478b2  jmp     short loc_180047868
0x1800478b4  mov     esi, eax
0x1800478b6  mov     edi, r15d
0x1800478b9  mov     [rbp+var_50], r15d
0x1800478bd  lea     r8, [rbp+var_50]
0x1800478c1  mov     edx, 1
0x1800478c6  mov     ecx, eax
0x1800478c8  call    ?GetWindowDisplayContext@Holographic@Shell@Internal@Windows@@YAJPEAUHWND__@@W4ContextInspectionOptions@1234@PEAW4UserDisplayContext@1234@@Z; Windows::Internal::Shell::Holographic::GetWindowDisplayContext(HWND__ *,Windows::Internal::Shell::Holographic::ContextInspectionOptions,Windows::Internal::Shell::Holographic::UserDisplayContext *)
0x1800478cd  test    eax, eax
0x1800478cf  jns     loc_180047981
0x1800478d5  mov     rcx, [r14+100h]
0x1800478dc  test    rcx, rcx
0x1800478df  jz      short loc_180047914
0x1800478e1  mov     [rbp+var_4C], r15d
0x1800478e5  mov     rax, [rcx]
0x1800478e8  lea     r8, [rbp+var_4C]
0x1800478ec  mov     rdx, rsi
0x1800478ef  mov     rax, [rax+28h]
0x1800478f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800478f8  mov     rcx, [rbp+18h]; this
0x1800478fc  test    eax, eax
0x1800478fe  js      loc_180047991
0x180047904  mov     eax, edi
0x180047906  mov     edi, 2
0x18004790b  cmp     [rbp+var_4C], r15d
0x18004790f  cmovnz  eax, edi
0x180047912  mov     edi, eax
0x180047914  lea     rcx, [rbp+var_48]
0x180047918  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004791d  mov     eax, edi
0x18004791f  jmp     loc_180047877
0x180047924  xor     r9d, r9d; lpArguments
0x180047927  xor     r8d, r8d; nNumberOfArguments
0x18004792a  lea     edx, [r9+1]; dwExceptionFlags
0x18004792e  mov     ecx, eax; dwExceptionCode
0x180047930  call    cs:__imp_RaiseException
0x180047936  int     3; Trap to Debugger
0x180047937  xor     r9d, r9d; lpArguments
0x18004793a  xor     r8d, r8d; nNumberOfArguments
0x18004793d  lea     edx, [r9+1]; dwExceptionFlags
0x180047941  mov     ecx, eax; dwExceptionCode
0x180047943  call    cs:__imp_RaiseException
0x180047949  int     3; Trap to Debugger
0x18004794a  xor     r9d, r9d; lpArguments
0x18004794d  xor     r8d, r8d; nNumberOfArguments
0x180047950  lea     edx, [r9+1]; dwExceptionFlags
0x180047954  mov     ecx, eax; dwExceptionCode
0x180047956  call    cs:__imp_RaiseException
0x18004795c  nop
0x18004795d  cmp     [rbp+var_3C], 1
0x180047961  mov     al, 1
0x180047963  jz      loc_1800477F2
0x180047969  jmp     loc_1800477EF
0x18004796e  xor     r9d, r9d; lpArguments
0x180047971  xor     r8d, r8d; nNumberOfArguments
0x180047974  lea     edx, [r9+1]; dwExceptionFlags
0x180047978  mov     ecx, eax; dwExceptionCode
0x18004797a  call    cs:__imp_RaiseException
0x180047980  int     3; Trap to Debugger
0x180047981  cmp     [rbp+var_50], 1
0x180047985  jz      short loc_1800479AA
0x180047987  mov     edi, 1
0x18004798c  jmp     loc_1800478D5
0x180047991  mov     r9d, eax; char *
0x180047994  lea     r8, aPcshellTwinuiH_3; "pcshell\\twinui\\holographicpositioner"...
0x18004799b  mov     edx, 586h; void *
0x1800479a0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800479a5  jmp     loc_180047914
0x1800479aa  mov     edi, 2
0x1800479af  jmp     loc_180047914
0x1806edaba  mov     dword ptr [rbp+var_38], r15d
0x1806edabe  mov     [rbp+string], r15
0x1806edac2  mov     r9d, 10h; unsigned int
0x1806edac8  lea     r8d, [r9+1]; unsigned int
0x1806edacc  lea     rdx, aSwitchasyncIdt; "SwitchAsync_IdTo"
0x1806edad3  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1806edad7  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1806edadc  nop
0x1806edadd  lea     r9, [rbp+var_38]
0x1806edae1  mov     rdx, [rbp+string]
0x1806edae5  lea     rcx, [rbp+var_48]
0x1806edae9  call    ??$GetValue@I@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValue@Foundation@3@EAAJPEAI@Z1@Z; Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<uint>(HSTRING__ *,long (Windows::Foundation::IPropertyValue::*)(uint *),uint *)
0x1806edaee  nop
0x1806edaef  shr     eax, 1Fh
0x1806edaf2  xor     al, 1
0x1806edaf4  jz      loc_1800477FA
0x1806edafa  mov     [rbp+var_50], r15d
0x1806edafe  mov     edx, dword ptr [rbp+var_38]; HWND
0x1806edb01  lea     rcx, [r14+88h]; this
0x1806edb08  lea     r8, [rbp+var_50]; int *
0x1806edb0c  call    ?IsWindowManaged@HolographicPositioner@@UEAAJPEAUHWND__@@PEAH@Z; HolographicPositioner::IsWindowManaged(HWND__ *,int *)
0x1806edb11  test    eax, eax
0x1806edb13  js      loc_1800477FA
0x1806edb19  mov     eax, [rbp+var_50]
0x1806edb1c  neg     eax
0x1806edb1e  sbb     edi, edi
0x1806edb20  neg     edi
0x1806edb22  inc     edi
0x1806edb24  jmp     loc_180047914
```
