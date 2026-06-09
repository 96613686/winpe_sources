# udk::npu_detection::_anonymous_namespace_::IsHybridComputeFrameworkPresent

- ea: `0x18002b3cc`
- end: `0x18002b467`
- name: `udk::npu_detection::_anonymous_namespace_::IsHybridComputeFrameworkPresent`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002b470`

## callees

- `0x180005418`
- `0x1800057a0`
- `0x18002b3cc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b3fc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b3fc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool udk::npu_detection::_anonymous_namespace_::IsHybridComputeFrameworkPresent()
{
  LSTATUS v0; // eax
  int v1; // r8d
  int v2; // r9d
  bool v3; // sf
  signed int v4; // eax
  bool result; // al
  bool v6; // bl
  const char *v7; // r9
  wil::reg::reg_view_details *phkResult; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v10; // [rsp+40h] [rbp+8h] BYREF
  char v11; // [rsp+44h] [rbp+Ch]
  HKEY v12; // [rsp+48h] [rbp+10h] BYREF
  HKEY v13; // [rsp+50h] [rbp+18h] BYREF

  v12 = 0;
  v0 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkloadManager\\HCF\\Status",
         0,
         0x20019u,
         &v12);
  v3 = v0 < 0;
  if ( v0 > 0 )
  {
    v4 = (unsigned __int16)v0 | 0x80070000;
    v3 = v4 < 0;
  }
  if ( v3 )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v12);
    return 0;
  }
  else
  {
    v13 = v12;
    LODWORD(phkResult) = 16;
    try
    {
      wil::reg::reg_view_details::reg_view_t<wil::err_exception_policy>::try_get_value<unsigned int>(
        (int)&v13,
        (int)&v10,
        v1,
        v2,
        phkResult);
      v6 = (v11 != 0 ? v10 : 0) != 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v12);
      result = v6;
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x1F7,
        (unsigned int)"OneCore\\Internal\\Shell\\inc\\npu_detection.h",
        v7);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002b3cc  push    rbx
0x18002b3ce  sub     rsp, 30h
0x18002b3d2  mov     [rsp+38h+arg_8], 0
0x18002b3db  lea     rax, [rsp+38h+arg_8]
0x18002b3e0  mov     [rsp+38h+phkResult], rax; phkResult
0x18002b3e5  mov     r9d, 20019h; samDesired
0x18002b3eb  xor     r8d, r8d; ulOptions
0x18002b3ee  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18002b3f5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002b3fc  call    cs:__imp_RegOpenKeyExW
0x18002b402  test    eax, eax
0x18002b404  jle     short loc_18002B410
0x18002b406  movzx   eax, ax
0x18002b409  or      eax, 80070000h
0x18002b40e  test    eax, eax
0x18002b410  jns     short loc_18002B420
0x18002b412  lea     rcx, [rsp+38h+arg_8]
0x18002b417  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002b41c  xor     al, al
0x18002b41e  jmp     short loc_18002B460
0x18002b420  mov     rax, [rsp+38h+arg_8]
0x18002b425  mov     [rsp+38h+arg_10], rax
0x18002b42a  mov     dword ptr [rsp+38h+phkResult], 10h; wil::reg::reg_view_details *
0x18002b432  lea     rdx, [rsp+38h+arg_0]; int
0x18002b437  lea     rcx, [rsp+38h+arg_10]; int
0x18002b43c  call    ??$try_get_value@I@?$reg_view_t@Uerr_exception_policy@wil@@@reg_view_details@reg@wil@@QEBA?AV?$optional@I@std@@PEBG0K@Z; wil::reg::reg_view_details::reg_view_t<wil::err_exception_policy>::try_get_value<uint>(ushort const *,ushort const *,ulong)
0x18002b441  mov     al, [rsp+38h+arg_4]
0x18002b445  neg     al
0x18002b447  sbb     ecx, ecx
0x18002b449  and     ecx, [rsp+38h+arg_0]
0x18002b44d  setnz   bl
0x18002b450  lea     rcx, [rsp+38h+arg_8]
0x18002b455  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002b45a  mov     al, bl
0x18002b45c  jmp     short loc_18002B460
0x18002b45e  xor     al, al
0x18002b460  add     rsp, 30h
0x18002b464  pop     rbx
0x18002b465  retn
```
