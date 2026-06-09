# PolicyHelpers::ReadSkuUpdateManagementGroupHelper(tagUpdateManagementGroup &)

- ea: `0x18001f000`
- end: `0x18001f094`
- name: `?ReadSkuUpdateManagementGroupHelper@PolicyHelpers@@SAJAEAW4tagUpdateManagementGroup@@@Z`
- size: `148`
- prototype: `__int64 __fastcall(DWORD *pdwValue)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000cf60`
- `0x18001efb4`

## callees

- `0x18001f000`
- `0x18002d730`
- `0x18002d85c`
- `0x18002ffd0`

## import_xrefs

- `api-ms-win-core-apiquery-l2-1-0!IsApiSetImplemented` at `0x18001f030`
- `api-ms-win-core-apiquery-l2-1-0!IsApiSetImplemented` at `0x18001f030`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18001f048`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18001f048`
- `SLC!SLGetWindowsInformationDWORD` at `0x18001f071`
- `SLC!SLGetWindowsInformationDWORD` at `0x18001f071`

## string_xrefs

- `0x18001f029`: `ext-ms-win-security-slc-l1-1-0`
- `0x18001f06a`: `UpdatePolicy-UpdateManagementGroup`

## pseudocode

```c
HRESULT __fastcall PolicyHelpers::ReadSkuUpdateManagementGroupHelper(wchar_t *pdwValue)
{
  WUSystemInterfaceHelper *v2; // rcx
  unsigned int *v3; // r8
  HRESULT result; // eax
  int v5; // [rsp+20h] [rbp-18h] BYREF

  if ( (int)WUSystemInterfaceHelper::IsCapabilitySupported((WUSystemInterfaceHelper *)6) >= 0 )
    return WUSystemInterfaceHelper::SLGetWindowsInformationDWORD(v2, pdwValue, v3);
  if ( IsApiSetImplemented("ext-ms-win-security-slc-l1-1-0") )
    return SLGetWindowsInformationDWORD(L"UpdatePolicy-UpdateManagementGroup", (DWORD *)pdwValue);
  v5 = 0;
  RtlGetDeviceFamilyInfoEnum(0, &v5, 0);
  result = 0;
  if ( v5 == 10 )
    *(_DWORD *)pdwValue = 2;
  else
    *(_DWORD *)pdwValue = 0;
  return result;
}

```

## disassembly

```asm
0x18001f000  push    rbx
0x18001f002  sub     rsp, 30h
0x18001f006  mov     rax, cs:__security_cookie
0x18001f00d  xor     rax, rsp
0x18001f010  mov     [rsp+38h+var_10], rax
0x18001f015  mov     rbx, rcx
0x18001f018  mov     ecx, 6; this
0x18001f01d  call    ?IsCapabilitySupported@WUSystemInterfaceHelper@@YAJK@Z; WUSystemInterfaceHelper::IsCapabilitySupported(ulong)
0x18001f022  shr     eax, 1Fh
0x18001f025  test    al, al
0x18001f027  jz      short loc_18001F079
0x18001f029  lea     rcx, Contract; "ext-ms-win-security-slc-l1-1-0"
0x18001f030  call    cs:__imp_IsApiSetImplemented
0x18001f036  test    eax, eax
0x18001f038  jnz     short loc_18001F067
0x18001f03a  xor     r8d, r8d
0x18001f03d  mov     [rsp+38h+var_18], eax
0x18001f041  lea     rdx, [rsp+38h+var_18]
0x18001f046  xor     ecx, ecx
0x18001f048  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18001f04e  xor     eax, eax
0x18001f050  cmp     [rsp+38h+var_18], 0Ah
0x18001f055  jnz     short loc_18001F05F
0x18001f057  mov     dword ptr [rbx], 2
0x18001f05d  jmp     short loc_18001F081
0x18001f05f  mov     dword ptr [rbx], 0
0x18001f065  jmp     short loc_18001F081
0x18001f067  mov     rdx, rbx; pdwValue
0x18001f06a  lea     rcx, pwszValueName; "UpdatePolicy-UpdateManagementGroup"
0x18001f071  call    cs:__imp_SLGetWindowsInformationDWORD
0x18001f077  jmp     short loc_18001F081
0x18001f079  mov     rdx, rbx; wchar_t *
0x18001f07c  call    ?SLGetWindowsInformationDWORD@WUSystemInterfaceHelper@@YAJPEB_WPEAK@Z; WUSystemInterfaceHelper::SLGetWindowsInformationDWORD(wchar_t const *,ulong *)
0x18001f081  mov     rcx, [rsp+38h+var_10]
0x18001f086  xor     rcx, rsp; StackCookie
0x18001f089  call    __security_check_cookie
0x18001f08e  add     rsp, 30h
0x18001f092  pop     rbx
0x18001f093  retn
```
