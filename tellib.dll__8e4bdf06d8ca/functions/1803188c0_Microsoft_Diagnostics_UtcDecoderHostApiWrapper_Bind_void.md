# Microsoft::Diagnostics::UtcDecoderHostApiWrapper::Bind(void)

- ea: `0x1803188c0`
- end: `0x180318b23`
- name: `?Bind@UtcDecoderHostApiWrapper@Diagnostics@Microsoft@@AEAAJXZ`
- size: `611`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE *Binding)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18009be24`

## callees

- `0x180026ecc`
- `0x18005af1c`
- `0x18006dd98`
- `0x18006f66c`
- `0x18007fae8`
- `0x1800b83bc`
- `0x18012de40`
- `0x1802ce9d8`
- `0x1803188c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180318b15`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180318b15`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18031893f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18031893f`
- `RPCRT4!RpcBindingBind` at `0x180318a93`
- `RPCRT4!RpcBindingBind` at `0x180318a93`
- `RPCRT4!RpcBindingCreateW` at `0x180318a3e`
- `RPCRT4!RpcBindingCreateW` at `0x180318a3e`

## string_xrefs

- `0x18031895d`: `onecore\base\telemetry\utc\service\utcdecoderhost\api\client\utcdecoderhostapiwrapper.cpp`
- `0x180318a68`: `onecore\base\telemetry\utc\service\utcdecoderhost\api\client\utcdecoderhostapiwrapper.cpp`
- `0x180318abd`: `onecore\base\telemetry\utc\service\utcdecoderhost\api\client\utcdecoderhostapiwrapper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Diagnostics::UtcDecoderHostApiWrapper::Bind(RPC_BINDING_HANDLE *Binding)
{
  unsigned int v2; // ebx
  const char *v3; // r9
  __int64 result; // rax
  wilp *v5; // rbx
  void *v6; // rdx
  RPC_STATUS v7; // eax
  unsigned int v8; // ebx
  RPC_STATUS v9; // eax
  unsigned int v10; // ebx
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+20h] [rbp-C8h] BYREF
  int v12; // [rsp+28h] [rbp-C0h] BYREF
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+30h] [rbp-B8h] BYREF
  __int64 v14; // [rsp+58h] [rbp-90h] BYREF
  int v15; // [rsp+60h] [rbp-88h]
  __int64 v16; // [rsp+64h] [rbp-84h]
  int v17; // [rsp+6Ch] [rbp-7Ch]
  __int128 v18; // [rsp+70h] [rbp-78h]
  __int64 v19; // [rsp+80h] [rbp-68h]
  PSECURITY_DESCRIPTOR v20; // [rsp+88h] [rbp-60h]
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+90h] [rbp-58h] BYREF
  RPC_BINDING_HANDLE_OPTIONS_V1 Options; // [rsp+C8h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  if ( *Binding )
  {
    _o_terminate();
    __debugbreak();
    __debugbreak();
    JUMPOUT(0x180318B23LL);
  }
  *(_QWORD *)&Template.Version = 1;
  *(_QWORD *)&Template.ProtocolSequence = 3;
  memset(&Template.NetworkAddress, 0, 40);
  SecurityDescriptor = 0;
  wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(
    &SecurityDescriptor,
    0);
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"D:(A;;GA;;;S-1-5-80-2620808479-2171380039-3191355562-2070425692-3097948119)(A;;GA;;;S-1-15-2-3403125134-4244430"
          "74-1489734032-3328068408-1744204695-205958814-4102323917)",
         1u,
         &SecurityDescriptor,
         0) )
  {
    v14 = 5;
    v15 = 0;
    v16 = 3;
    v17 = 0;
    v18 = 0;
    v19 = 0;
    v20 = SecurityDescriptor;
    *(_QWORD *)&Security.Version = 1;
    Security.ServerPrincName = 0;
    Security.AuthnLevel = 6;
    Security.AuthnSvc = 10;
    Security.AuthIdentity = 0;
    Security.SecurityQos = (RPC_SECURITY_QOS *)&v14;
    Options.Version = 1;
    Options.Flags = 1;
    *(_QWORD *)&Options.ComTimeout = 5;
    v5 = (wilp *)*Binding;
    if ( *Binding )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v12);
      wilp::CloseRpcBindingHandle(v5, v6);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v12);
    }
    *Binding = 0;
    v7 = RpcBindingCreateW(&Template, &Security, &Options, Binding);
    v8 = v7;
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80010000;
    if ( (v8 & 0x80000000) == 0 )
    {
      v9 = RpcBindingBind(0, *Binding, &unk_1803693B0);
      v10 = v9;
      if ( v9 > 0 )
        v10 = (unsigned __int16)v9 | 0x80010000;
      if ( (v10 & 0x80000000) == 0 )
      {
        wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&SecurityDescriptor);
        result = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x148,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\utcdecoderhost\\api\\client\\utcdecoderhostapiwrapper.cpp",
          (const char *)v10,
          (int)SecurityDescriptor);
        wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&SecurityDescriptor);
        result = v10;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x143,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\utcdecoderhost\\api\\client\\utcdecoderhostapiwrapper.cpp",
        (const char *)v8,
        (int)SecurityDescriptor);
      wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&SecurityDescriptor);
      result = v8;
    }
  }
  else
  {
    v2 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x11D,
           (unsigned int)"onecore\\base\\telemetry\\utc\\service\\utcdecoderhost\\api\\client\\utcdecoderhostapiwrapper.cpp",
           (const char *)0x53A,
           (unsigned int)SecurityDescriptor);
    wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&SecurityDescriptor);
    result = v2;
  }
  while ( 2 )
  {
    try
    {
    }
    catch ( ... )
    {
      LODWORD(SecurityDescriptor) = wil::details::in1diag3::Return_CaughtException(
                                      retaddr,
                                      (void *)0x14A,
                                      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\utcdecoderhost\\api\\client\\"
                                                    "utcdecoderhostapiwrapper.cpp",
                                      v3);
      result = (unsigned int)SecurityDescriptor;
      continue;
    }
    break;
  }
  return result;
}

```

## disassembly

```asm
0x1803188c0  mov     r11, rsp
0x1803188c3  mov     [r11+10h], rbx
0x1803188c7  mov     [r11+18h], rsi
0x1803188cb  push    rdi
0x1803188cc  sub     rsp, 0E0h
0x1803188d3  mov     rax, cs:__security_cookie
0x1803188da  xor     rax, rsp
0x1803188dd  mov     [rsp+0E8h+var_10], rax
0x1803188e5  mov     rdi, rcx
0x1803188e8  xor     esi, esi
0x1803188ea  cmp     [rcx], rsi
0x1803188ed  jnz     loc_180318B15
0x1803188f3  lea     ebx, [rsi+1]
0x1803188f6  mov     [r11-58h], rbx
0x1803188fa  mov     qword ptr [r11-50h], 3
0x180318902  xorps   xmm0, xmm0
0x180318905  movdqu  xmmword ptr [r11-48h], xmm0
0x18031890b  mov     [r11-38h], rsi
0x18031890f  mov     [r11-30h], esi
0x180318913  xor     eax, eax
0x180318915  mov     [r11-2Ch], rax
0x180318919  mov     [r11-24h], eax
0x18031891d  mov     [rsp+0E8h+SecurityDescriptor], rsi; int
0x180318922  xor     edx, edx
0x180318924  lea     rcx, [rsp+0E8h+SecurityDescriptor]
0x180318929  call    ?reset@?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAAXPEA_W@Z; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(wchar_t *)
0x18031892e  xor     r9d, r9d; SecurityDescriptorSize
0x180318931  lea     r8, [rsp+0E8h+SecurityDescriptor]; SecurityDescriptor
0x180318936  mov     edx, ebx; StringSDRevision
0x180318938  mov     rcx, cs:off_1803692A0; StringSecurityDescriptor
0x18031893f  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180318946  nop     dword ptr [rax+rax+00h]
0x18031894b  test    eax, eax
0x18031894d  jnz     short loc_180318981
0x18031894f  mov     rcx, [rsp+0E8h]; this
0x180318957  mov     r9d, 53Ah; char *
0x18031895d  lea     r8, aOnecoreBaseTel_220; "onecore\\base\\telemetry\\utc\\service"...
0x180318964  mov     edx, 11Dh; void *
0x180318969  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18031896e  mov     ebx, eax
0x180318970  lea     rcx, [rsp+0E8h+SecurityDescriptor]
0x180318975  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x18031897a  mov     eax, ebx
0x18031897c  jmp     loc_180318AE9
0x180318981  mov     [rsp+0E8h+var_90], 5
0x18031898a  mov     [rsp+0E8h+var_88], esi
0x18031898e  mov     [rsp+0E8h+var_84], 3
0x180318997  xor     eax, eax
0x180318999  mov     [rsp+0E8h+var_7C], eax
0x18031899d  xorps   xmm0, xmm0
0x1803189a0  movdqu  [rsp+0E8h+var_78], xmm0
0x1803189a6  mov     [rsp+0E8h+var_68], rsi
0x1803189ae  mov     rax, [rsp+0E8h+SecurityDescriptor]
0x1803189b3  mov     [rsp+0E8h+var_60], rax
0x1803189bb  mov     qword ptr [rsp+0E8h+Security.Version], rbx
0x1803189c0  mov     [rsp+0E8h+Security.ServerPrincName], rsi
0x1803189c5  mov     [rsp+0E8h+Security.AuthnLevel], 6
0x1803189cd  mov     [rsp+0E8h+Security.AuthnSvc], 0Ah
0x1803189d5  mov     [rsp+0E8h+Security.AuthIdentity], rsi
0x1803189da  lea     rax, [rsp+0E8h+var_90]
0x1803189df  mov     [rsp+0E8h+Security.SecurityQos], rax
0x1803189e4  mov     [rsp+0E8h+Options.Version], ebx
0x1803189eb  mov     [rsp+0E8h+Options.Flags], ebx
0x1803189f2  mov     qword ptr [rsp+0E8h+Options.ComTimeout], 5
0x1803189fe  mov     rbx, [rdi]
0x180318a01  test    rbx, rbx
0x180318a04  jz      short loc_180318A23
0x180318a06  lea     rcx, [rsp+0E8h+var_C0]; this
0x180318a0b  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180318a10  mov     rcx, rbx; this
0x180318a13  call    ?CloseRpcBindingHandle@wilp@@YAXPEAX@Z; wilp::CloseRpcBindingHandle(void *)
0x180318a18  lea     rcx, [rsp+0E8h+var_C0]; this
0x180318a1d  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180318a22  nop
0x180318a23  mov     [rdi], rsi
0x180318a26  mov     r9, rdi; Binding
0x180318a29  lea     r8, [rsp+0E8h+Options]; Options
0x180318a31  lea     rdx, [rsp+0E8h+Security]; Security
0x180318a36  lea     rcx, [rsp+0E8h+Template]; Template
0x180318a3e  call    cs:__imp_RpcBindingCreateW
0x180318a45  nop     dword ptr [rax+rax+00h]
0x180318a4a  mov     ebx, eax
0x180318a4c  test    eax, eax
0x180318a4e  jle     short loc_180318A59
0x180318a50  movzx   ebx, ax
0x180318a53  or      ebx, 80010000h
0x180318a59  test    ebx, ebx
0x180318a5b  jns     short loc_180318A87
0x180318a5d  mov     rcx, [rsp+0E8h]; this
0x180318a65  mov     r9d, ebx; char *
0x180318a68  lea     r8, aOnecoreBaseTel_220; "onecore\\base\\telemetry\\utc\\service"...
0x180318a6f  mov     edx, 143h; void *
0x180318a74  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180318a79  lea     rcx, [rsp+0E8h+SecurityDescriptor]
0x180318a7e  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x180318a83  mov     eax, ebx
0x180318a85  jmp     short loc_180318AE9
0x180318a87  lea     r8, unk_1803693B0; IfSpec
0x180318a8e  mov     rdx, [rdi]; Binding
0x180318a91  xor     ecx, ecx; pAsync
0x180318a93  call    cs:__imp_RpcBindingBind
0x180318a9a  nop     dword ptr [rax+rax+00h]
0x180318a9f  mov     ebx, eax
0x180318aa1  test    eax, eax
0x180318aa3  jle     short loc_180318AAE
0x180318aa5  movzx   ebx, ax
0x180318aa8  or      ebx, 80010000h
0x180318aae  test    ebx, ebx
0x180318ab0  jns     short loc_180318ADC
0x180318ab2  mov     rcx, [rsp+0E8h]; this
0x180318aba  mov     r9d, ebx; char *
0x180318abd  lea     r8, aOnecoreBaseTel_220; "onecore\\base\\telemetry\\utc\\service"...
0x180318ac4  mov     edx, 148h; void *
0x180318ac9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180318ace  lea     rcx, [rsp+0E8h+SecurityDescriptor]
0x180318ad3  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x180318ad8  mov     eax, ebx
0x180318ada  jmp     short loc_180318AE9
0x180318adc  lea     rcx, [rsp+0E8h+SecurityDescriptor]
0x180318ae1  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x180318ae6  nop
0x180318ae7  xor     eax, eax
0x180318ae9  mov     rcx, [rsp+0E8h+var_10]
0x180318af1  xor     rcx, rsp; StackCookie
0x180318af4  call    __security_check_cookie
0x180318af9  lea     r11, [rsp+0E8h+var_8]
0x180318b01  mov     rbx, [r11+18h]
0x180318b05  mov     rsi, [r11+20h]
0x180318b09  mov     rsp, r11
0x180318b0c  pop     rdi
0x180318b0d  retn
0x180318b0f  mov     eax, dword ptr [rsp+0E8h+SecurityDescriptor]
0x180318b13  jmp     short loc_180318AE9
0x180318b15  call    cs:__imp__o_terminate
0x180318b1c  nop     dword ptr [rax+rax+00h]
0x180318b21  int     3; Trap to Debugger
0x180318b22  int     3; Trap to Debugger
```
