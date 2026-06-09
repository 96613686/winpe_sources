# UtilGetFeatureConfigurations(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x180046e94`
- end: `0x1800470a5`
- name: `?UtilGetFeatureConfigurations@@YAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `529`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013838`

## callees

- `0x18000da00`
- `0x180020680`
- `0x18003de9c`
- `0x180045388`
- `0x180046e94`
- `0x18004caf0`
- `0x18004eee4`
- `0x180053300`
- `0x1800b2010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180046ec0`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180046ec0`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180047081`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180047081`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004701d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004701d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046f9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046ffe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047061`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046f9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180046ffe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047061`

## string_xrefs

- `0x180046f2f`: `Windows.Internal.Flighting.FeatureConfiguration.FeatureConfigurationsManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall UtilGetFeatureConfigurations(void *a1, __int64 a2, __int64 a3)
{
  int v4; // eax
  int v5; // ebx
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, HSTRING *); // rbx
  wchar_t *v8; // rax
  __int64 v9; // rdx
  WCHAR *StringRawBuffer; // rax
  __int64 v11; // rcx
  HSTRING string; // [rsp+20h] [rbp-48h] BYREF
  char v14; // [rsp+29h] [rbp-3Fh]
  __int64 v15; // [rsp+30h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-30h] BYREF
  __int64 v17; // [rsp+50h] [rbp-18h]

  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(0, a2, a3);
  v4 = RoInitialize(1);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v14 = 1;
    v15 = 0;
    v17 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.Flighting.FeatureConfiguration.FeatureConfigurationsManager",
      0x4Du,
      0x4Cu);
    v5 = Windows::Foundation::ActivateInstance<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsManager>(
           v17,
           &v15);
    if ( v5 < 0 )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          142,
          WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids,
          (unsigned int)v5);
      goto LABEL_23;
    }
    string = 0;
    v6 = v15;
    v7 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v15 + 64LL);
    WindowsDeleteString(0);
    string = 0;
    v5 = v7(v6, &string);
    if ( v5 >= 0 )
    {
      StringRawBuffer = (WCHAR *)WindowsGetStringRawBuffer(string, 0);
      if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                              a1,
                              StringRawBuffer) )
      {
        WindowsDeleteString(string);
        string = 0;
        v5 = 0;
        goto LABEL_23;
      }
      v5 = -2147024882;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      {
LABEL_17:
        WindowsDeleteString(string);
        string = 0;
LABEL_23:
        utl::unique_ptr<IXmlWriter,tlx::release_delete>::~unique_ptr<IXmlWriter,tlx::release_delete>(&v15);
        RoUninitialize(v11);
        return (unsigned int)v5;
      }
      v9 = 144;
    }
    else
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_17;
      v9 = 143;
    }
    WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids, (unsigned int)v5);
    goto LABEL_17;
  }
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      141,
      WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids,
      (unsigned int)v4);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180046e94  push    rbp
0x180046e96  push    rbx
0x180046e97  push    rsi
0x180046e98  push    rdi
0x180046e99  mov     rbp, rsp
0x180046e9c  sub     rsp, 68h
0x180046ea0  mov     rax, cs:__security_cookie
0x180046ea7  xor     rax, rsp
0x180046eaa  mov     [rbp+var_10], rax
0x180046eae  mov     rsi, rcx
0x180046eb1  test    rcx, rcx
0x180046eb4  jnz     short loc_180046EBB
0x180046eb6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180046ebb  mov     ecx, 1
0x180046ec0  call    cs:__imp_RoInitialize
0x180046ec7  nop     dword ptr [rax+rax+00h]
0x180046ecc  mov     ebx, eax
0x180046ece  test    eax, eax
0x180046ed0  jns     short loc_180046F11
0x180046ed2  lea     rcx, WPP_GLOBAL_Control
0x180046ed9  mov     r10, cs:WPP_GLOBAL_Control
0x180046ee0  cmp     r10, rcx
0x180046ee3  jz      loc_18004708D
0x180046ee9  test    byte ptr [r10+1Ch], 1
0x180046eee  jz      loc_18004708D
0x180046ef4  mov     edx, 8Dh
0x180046ef9  mov     r9d, eax
0x180046efc  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x180046f03  mov     rcx, [r10+10h]
0x180046f07  call    WPP_SF_d
0x180046f0c  jmp     loc_18004708D
0x180046f11  mov     [rbp+var_3F], 1
0x180046f15  mov     [rbp+var_38], 0
0x180046f1d  mov     [rbp+var_18], 0
0x180046f25  mov     r9d, 4Ch ; 'L'; unsigned int
0x180046f2b  lea     r8d, [r9+1]; unsigned int
0x180046f2f  lea     rdx, ?RuntimeClass_Windows_Internal_Flighting_FeatureConfiguration_FeatureConfigurationsManager@@3QB_WB; "Windows.Internal.Flighting.FeatureConfi"...
0x180046f36  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180046f3a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEB_WII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(wchar_t const *,uint,uint)
0x180046f3f  nop
0x180046f40  lea     rdx, [rbp+var_38]
0x180046f44  mov     rcx, [rbp+var_18]
0x180046f48  call    ??$ActivateInstance@UIFeatureConfigurationsManager@FeatureConfiguration@Flighting@Internal@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIFeatureConfigurationsManager@FeatureConfiguration@Flighting@Internal@1@@Z; Windows::Foundation::ActivateInstance<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsManager>(HSTRING__ *,Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsManager * *)
0x180046f4d  mov     ebx, eax
0x180046f4f  test    eax, eax
0x180046f51  jns     short loc_180046F8A
0x180046f53  lea     rcx, WPP_GLOBAL_Control
0x180046f5a  mov     rax, cs:WPP_GLOBAL_Control
0x180046f61  cmp     rax, rcx
0x180046f64  jz      short loc_180046F85
0x180046f66  test    byte ptr [rax+1Ch], 1
0x180046f6a  jz      short loc_180046F85
0x180046f6c  mov     edx, 8Eh
0x180046f71  mov     r9d, ebx
0x180046f74  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x180046f7b  mov     rcx, [rax+10h]
0x180046f7f  call    WPP_SF_d
0x180046f84  nop
0x180046f85  jmp     loc_180047077
0x180046f8a  mov     [rbp+string], 0
0x180046f92  mov     rdi, [rbp+var_38]
0x180046f96  mov     rax, [rdi]
0x180046f99  mov     rbx, [rax+40h]
0x180046f9d  xor     ecx, ecx; string
0x180046f9f  call    cs:__imp_WindowsDeleteString
0x180046fa6  nop     dword ptr [rax+rax+00h]
0x180046fab  mov     [rbp+string], 0
0x180046fb3  lea     rdx, [rbp+string]
0x180046fb7  mov     rcx, rdi
0x180046fba  mov     rax, rbx
0x180046fbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046fc2  mov     ebx, eax
0x180046fc4  test    eax, eax
0x180046fc6  jns     short loc_180047017
0x180046fc8  lea     rcx, WPP_GLOBAL_Control
0x180046fcf  mov     rax, cs:WPP_GLOBAL_Control
0x180046fd6  cmp     rax, rcx
0x180046fd9  jz      short loc_180046FFA
0x180046fdb  test    byte ptr [rax+1Ch], 1
0x180046fdf  jz      short loc_180046FFA
0x180046fe1  mov     edx, 8Fh
0x180046fe6  mov     r9d, ebx
0x180046fe9  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x180046ff0  mov     rcx, [rax+10h]
0x180046ff4  call    WPP_SF_d
0x180046ff9  nop
0x180046ffa  mov     rcx, [rbp+string]; string
0x180046ffe  call    cs:__imp_WindowsDeleteString
0x180047005  nop     dword ptr [rax+rax+00h]
0x18004700a  mov     [rbp+string], 0
0x180047012  jmp     loc_180046F85
0x180047017  xor     edx, edx; length
0x180047019  mov     rcx, [rbp+string]; string
0x18004701d  call    cs:__imp_WindowsGetStringRawBuffer
0x180047024  nop     dword ptr [rax+rax+00h]
0x180047029  mov     rdx, rax
0x18004702c  mov     rcx, rsi
0x18004702f  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x180047034  test    al, al
0x180047036  jnz     short loc_18004705D
0x180047038  mov     ebx, 8007000Eh
0x18004703d  lea     rcx, WPP_GLOBAL_Control
0x180047044  mov     rax, cs:WPP_GLOBAL_Control
0x18004704b  cmp     rax, rcx
0x18004704e  jz      short loc_180046FFA
0x180047050  test    byte ptr [rax+1Ch], 1
0x180047054  jz      short loc_180046FFA
0x180047056  mov     edx, 90h
0x18004705b  jmp     short loc_180046FE6
0x18004705d  mov     rcx, [rbp+string]; string
0x180047061  call    cs:__imp_WindowsDeleteString
0x180047068  nop     dword ptr [rax+rax+00h]
0x18004706d  mov     [rbp+string], 0
0x180047075  xor     ebx, ebx
0x180047077  lea     rcx, [rbp+var_38]
0x18004707b  call    ??1?$unique_ptr@UIXmlWriter@@Urelease_delete@tlx@@@utl@@QEAA@XZ; utl::unique_ptr<IXmlWriter,tlx::release_delete>::~unique_ptr<IXmlWriter,tlx::release_delete>(void)
0x180047080  nop
0x180047081  call    cs:__imp_RoUninitialize
0x180047088  nop     dword ptr [rax+rax+00h]
0x18004708d  mov     eax, ebx
0x18004708f  mov     rcx, [rbp+var_10]
0x180047093  xor     rcx, rsp; StackCookie
0x180047096  call    __security_check_cookie
0x18004709b  add     rsp, 68h
0x18004709f  pop     rdi
0x1800470a0  pop     rsi
0x1800470a1  pop     rbx
0x1800470a2  pop     rbp
0x1800470a3  retn
```
