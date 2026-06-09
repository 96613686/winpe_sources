# FirewallManagementRules::ConvertAppPackageFamilyNameToPackageSid

- ea: `0x18006cb0c`
- end: `0x18006cbd8`
- name: `FirewallManagementRules::ConvertAppPackageFamilyNameToPackageSid`
- size: `204`
- prototype: `__int64 __fastcall(LPWSTR *StringSid)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180073070`

## callees

- `0x18001c11c`
- `0x18006cb0c`
- `0x18006cbe0`
- `0x18007b57c`
- `0x180084f50`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18006cbbb`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18006cbbb`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18006cb97`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18006cb97`
- `USERENV!DeriveAppContainerSidFromAppContainerName` at `0x18006cb45`
- `USERENV!DeriveAppContainerSidFromAppContainerName` at `0x18006cb45`

## string_xrefs

- `0x18006cb57`: `onecoreuap\net\wcm\service\base\firewallmanager\firewallmanagementrules.cpp`
- `0x18006cba6`: `onecoreuap\net\wcm\service\base\firewallmanager\firewallmanagementrules.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPWSTR *__fastcall FirewallManagementRules::ConvertAppPackageFamilyNameToPackageSid(LPWSTR *StringSid, __int64 a2)
{
  int v3; // eax
  const char *v4; // r9
  PSID Sid; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  Sid = 0;
  v3 = DeriveAppContainerSidFromAppContainerName(a2, &Sid);
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x2C,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\firewallmanager\\firewallmanagementrules.cpp",
      (const char *)(unsigned int)v3,
      0);
  *StringSid = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    StringSid,
    0);
  if ( !ConvertSidToStringSidW(Sid, StringSid) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x32,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\firewallmanager\\firewallmanagementrules.cpp",
      v4);
  FreeSid(Sid);
  return StringSid;
}

```

## disassembly

```asm
0x18006cb0c  push    rbx
0x18006cb0e  sub     rsp, 50h
0x18006cb12  mov     rax, cs:__security_cookie
0x18006cb19  xor     rax, rsp
0x18006cb1c  mov     [rsp+58h+var_10], rax
0x18006cb21  mov     rax, rdx
0x18006cb24  mov     rbx, rcx
0x18006cb27  mov     [rsp+58h+var_30], rcx
0x18006cb2c  mov     [rsp+58h+var_38], 0; int
0x18006cb34  mov     [rsp+58h+Sid], 0
0x18006cb3d  lea     rdx, [rsp+58h+Sid]
0x18006cb42  mov     rcx, rax
0x18006cb45  call    cs:__imp_DeriveAppContainerSidFromAppContainerName
0x18006cb4b  mov     rcx, [rsp+58h]; this
0x18006cb50  test    eax, eax
0x18006cb52  jns     short loc_18006CB69
0x18006cb54  mov     r9d, eax; char *
0x18006cb57  lea     r8, aOnecoreuapNetW_34; "onecoreuap\\net\\wcm\\service\\base\\fi"...
0x18006cb5e  mov     edx, 2Ch ; ','; void *
0x18006cb63  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18006cb69  lea     rax, [rsp+58h+Sid]
0x18006cb6e  mov     [rsp+58h+var_28], rax
0x18006cb73  mov     [rsp+58h+var_20], 1
0x18006cb78  xor     eax, eax
0x18006cb7a  mov     [rbx], rax
0x18006cb7d  mov     [rsp+58h+var_38], 1
0x18006cb85  xor     edx, edx
0x18006cb87  mov     rcx, rbx
0x18006cb8a  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18006cb8f  mov     rdx, rbx; StringSid
0x18006cb92  mov     rcx, [rsp+58h+Sid]; Sid
0x18006cb97  call    cs:__imp_ConvertSidToStringSidW
0x18006cb9d  mov     rcx, [rsp+58h]; this
0x18006cba2  test    eax, eax
0x18006cba4  jnz     short loc_18006CBB6
0x18006cba6  lea     r8, aOnecoreuapNetW_34; "onecoreuap\\net\\wcm\\service\\base\\fi"...
0x18006cbad  lea     edx, [rax+32h]; void *
0x18006cbb0  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18006cbb6  mov     rcx, [rsp+58h+Sid]; pSid
0x18006cbbb  call    cs:__imp_FreeSid
0x18006cbc1  mov     rax, rbx
0x18006cbc4  mov     rcx, [rsp+58h+var_10]
0x18006cbc9  xor     rcx, rsp; StackCookie
0x18006cbcc  call    __security_check_cookie
0x18006cbd1  add     rsp, 50h
0x18006cbd5  pop     rbx
0x18006cbd6  retn
```
