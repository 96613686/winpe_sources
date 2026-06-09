# _anonymous_namespace_::GetDynamicScrollbarsRegistryValue

- ea: `0x180031060`
- end: `0x180031189`
- name: `_anonymous_namespace_::GetDynamicScrollbarsRegistryValue`
- size: `297`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180030f30`

## callees

- `0x180031060`
- `0x180031410`
- `0x180033610`
- `0x180033634`
- `0x180084ef0`
- `0x1800a6604`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800310ae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800310ae`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180031101`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180031101`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031150`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031167`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031150`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031167`

## string_xrefs

- `0x1800310a0`: `Control Panel\Accessibility`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall anonymous_namespace_::GetDynamicScrollbarsRegistryValue(bool *a1)
{
  unsigned int v2; // eax
  void *v3; // rdx
  unsigned int v4; // r8d
  unsigned int ValueW; // eax
  unsigned int v6; // ebx
  unsigned int phkResult; // [rsp+20h] [rbp-20h]
  unsigned int phkResulta; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  int pvData; // [rsp+60h] [rbp+20h] BYREF
  DWORD pcbData; // [rsp+68h] [rbp+28h] BYREF
  HKEY hkey; // [rsp+70h] [rbp+30h] BYREF

  *a1 = 1;
  hkey = 0;
  v2 = RegOpenKeyExW(HKEY_CURRENT_USER, L"Control Panel\\Accessibility", 0, 0x20019u, &hkey);
  if ( v2 )
    wil::details::in1diag3::_Log_Win32(retaddr, v3, v4, (const char *)v2, phkResult);
  if ( hkey )
  {
    pvData = 0;
    pcbData = 4;
    ValueW = RegGetValueW(hkey, 0, L"DynamicScrollbars", 0x10u, 0, &pvData, &pcbData);
    if ( ValueW )
    {
      if ( ValueW != 2 )
      {
        v6 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x27C,
               (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\uisettings\\uisettings.cpp",
               (const char *)ValueW,
               phkResulta);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
        return v6;
      }
    }
    else
    {
      *a1 = pvData != 0;
    }
  }
  if ( hkey )
    RegCloseKey(hkey);
  return 0;
}

```

## disassembly

```asm
0x180031060  push    rbp
0x180031062  push    rbx
0x180031063  push    rdi
0x180031064  mov     rbp, rsp
0x180031067  sub     rsp, 40h
0x18003106b  mov     rdi, rcx
0x18003106e  mov     byte ptr [rcx], 1
0x180031071  mov     [rbp+hkey], 0
0x180031079  mov     rbx, [rbp+hkey]
0x18003107d  test    rbx, rbx
0x180031080  jnz     loc_18003115B
0x180031086  mov     [rbp+hkey], 0
0x18003108e  lea     rax, [rbp+hkey]
0x180031092  mov     [rsp+40h+phkResult], rax; unsigned int
0x180031097  mov     r9d, 20019h; samDesired
0x18003109d  xor     r8d, r8d; ulOptions
0x1800310a0  lea     rdx, aControlPanelAc; "Control Panel\\Accessibility"
0x1800310a7  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800310ae  call    cs:__imp_RegOpenKeyExW
0x1800310b4  mov     rcx, [rbp+18h]; this
0x1800310b8  test    eax, eax
0x1800310ba  jnz     loc_18003117C
0x1800310c0  mov     rcx, [rbp+hkey]; hkey
0x1800310c4  test    rcx, rcx
0x1800310c7  jz      short loc_180031147
0x1800310c9  mov     [rbp+arg_0], 0
0x1800310d0  mov     [rbp+arg_8], 4
0x1800310d7  lea     rax, [rbp+arg_8]
0x1800310db  mov     [rsp+40h+pcbData], rax; pcbData
0x1800310e0  lea     rax, [rbp+arg_0]
0x1800310e4  mov     [rsp+40h+pvData], rax; pvData
0x1800310e9  mov     [rsp+40h+phkResult], 0; unsigned int
0x1800310f2  mov     r9d, 10h; dwFlags
0x1800310f8  lea     r8, aDynamicscrollb; "DynamicScrollbars"
0x1800310ff  xor     edx, edx; lpSubKey
0x180031101  call    cs:__imp_RegGetValueW
0x180031107  test    eax, eax
0x180031109  jz      short loc_18003113E
0x18003110b  cmp     eax, 2
0x18003110e  jz      short loc_180031147
0x180031110  mov     rcx, [rbp+18h]; this
0x180031114  mov     r9d, eax; char *
0x180031117  lea     r8, aOnecoreuapWind_21; "onecoreuap\\windows\\advcore\\winrt\\ui"...
0x18003111e  mov     edx, 27Ch; void *
0x180031123  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180031128  mov     ebx, eax
0x18003112a  lea     rcx, [rbp+hkey]
0x18003112e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180031133  nop
0x180031134  mov     eax, ebx
0x180031136  add     rsp, 40h
0x18003113a  pop     rdi
0x18003113b  pop     rbx
0x18003113c  pop     rbp
0x18003113d  retn
0x18003113e  cmp     [rbp+arg_0], 0
0x180031142  setnz   al
0x180031145  mov     [rdi], al
0x180031147  mov     rcx, [rbp+hkey]; hKey
0x18003114b  test    rcx, rcx
0x18003114e  jz      short loc_180031157
0x180031150  call    cs:__imp_RegCloseKey
0x180031156  nop
0x180031157  xor     eax, eax
0x180031159  jmp     short loc_180031136
0x18003115b  lea     rcx, [rbp+arg_0]; this
0x18003115f  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180031164  mov     rcx, rbx; hKey
0x180031167  call    cs:__imp_RegCloseKey
0x18003116d  lea     rcx, [rbp+arg_0]; this
0x180031171  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180031176  nop
0x180031177  jmp     loc_180031086
0x18003117c  mov     r9d, eax; char *
0x18003117f  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180031184  jmp     loc_1800310C0
```
