# wil::reg::create_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)

- ea: `0x180035dd0`
- end: `0x180035e43`
- name: `?create_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z`
- size: `115`
- prototype: `LSTATUS __fastcall(__int64, __int64, __int64, DWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180035444`

## callees

- `0x180027b94`
- `0x180035dd0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180035e2c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180035e2c`

## string_xrefs

- `0x180035df3`: `SOFTWARE\Microsoft\Security Center\NCP`

## pseudocode

```c
LSTATUS __fastcall wil::reg::create_unique_key_nothrow(__int64 a1, __int64 a2, __int64 a3, DWORD a4)
{
  HKEY *phkResult; // rax
  LSTATUS result; // eax
  DWORD dwDisposition; // [rsp+78h] [rbp+20h] BYREF

  dwDisposition = a4;
  phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(a3);
  dwDisposition = 0;
  *phkResult = 0;
  result = RegCreateKeyExW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Security Center\\NCP",
             0,
             0,
             0,
             0xF003Fu,
             0,
             phkResult,
             &dwDisposition);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180035dd0  mov     [rsp+dwDisposition], r9d
0x180035dd5  sub     rsp, 58h
0x180035dd9  mov     rcx, r8
0x180035ddc  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180035de1  lea     rcx, [rsp+58h+dwDisposition]
0x180035de6  mov     [rsp+58h+dwDisposition], 0
0x180035dee  mov     [rsp+58h+lpdwDisposition], rcx; lpdwDisposition
0x180035df3  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Security Center\\N"...
0x180035dfa  mov     [rsp+58h+phkResult], rax; phkResult
0x180035dff  xor     r9d, r9d; lpClass
0x180035e02  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180035e0b  xor     r8d, r8d; Reserved
0x180035e0e  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x180035e16  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180035e1d  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180035e25  mov     qword ptr [rax], 0
0x180035e2c  call    cs:__imp_RegCreateKeyExW
0x180035e32  test    eax, eax
0x180035e34  jle     short loc_180035E3E
0x180035e36  movzx   eax, ax
0x180035e39  or      eax, 80070000h
0x180035e3e  add     rsp, 58h
0x180035e42  retn
```
