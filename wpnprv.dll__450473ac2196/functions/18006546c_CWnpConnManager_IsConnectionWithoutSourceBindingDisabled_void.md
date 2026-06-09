# CWnpConnManager::IsConnectionWithoutSourceBindingDisabled(void)

- ea: `0x18006546c`
- end: `0x180065585`
- name: `?IsConnectionWithoutSourceBindingDisabled@CWnpConnManager@@AEAA_NXZ`
- size: `281`
- prototype: `bool __fastcall(CWnpConnManager *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800665f4`

## callees

- `0x18000fe2c`
- `0x18002f808`
- `0x180063934`
- `0x18006546c`
- `0x180066964`
- `0x1800852d4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800654df`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800654df`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall CWnpConnManager::IsConnectionWithoutSourceBindingDisabled(CWnpConnManager *this)
{
  bool v1; // bl
  unsigned int v2; // eax
  const char *v3; // r9
  unsigned int phkResult; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  bool v7; // [rsp+40h] [rbp+8h]
  unsigned int v9; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 133, &WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids);
  }
  v1 = 0;
  v7 = 0;
  hKey = 0;
  v2 = RegOpenKeyExA(
         HKEY_LOCAL_MACHINE,
         "Software\\Microsoft\\Windows\\CurrentVersion\\PushNotifications",
         0,
         1u,
         &hKey);
  try
  {
    if ( v2 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x449,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpconnmanager.cpp",
        (const char *)v2,
        phkResult);
    v9 = 1;
    if ( (int)WpnRegLoadDWord(hKey, L"ConnectionWithoutSourceBindingDisabled", &v9) >= 0 )
    {
      v1 = v9 != 0;
      v7 = v9 != 0;
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x452,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpconnmanager.cpp",
      v3);
    v1 = v7;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    LOBYTE(v3) = v1;
    WPP_SF_c(*((_QWORD *)WPP_GLOBAL_Control + 2), 134, &WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids, v3);
  }
  return v1;
}

```

## disassembly

```asm
0x18006546c  mov     [rsp+arg_18], rbx
0x180065471  mov     [rsp+arg_0], rcx
0x180065476  push    rdi
0x180065477  sub     rsp, 30h
0x18006547b  lea     rdi, WPP_GLOBAL_Control
0x180065482  mov     rcx, cs:WPP_GLOBAL_Control
0x180065489  cmp     rcx, rdi
0x18006548c  jz      short loc_1800654AF
0x18006548e  test    byte ptr [rcx+1Ch], 4
0x180065492  jz      short loc_1800654AF
0x180065494  cmp     byte ptr [rcx+19h], 6
0x180065498  jb      short loc_1800654AF
0x18006549a  mov     edx, 85h
0x18006549f  lea     r8, WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids
0x1800654a6  mov     rcx, [rcx+10h]
0x1800654aa  call    WPP_SF_
0x1800654af  xor     bl, bl
0x1800654b1  mov     byte ptr [rsp+38h+arg_0], bl
0x1800654b5  mov     [rsp+38h+hKey], 0
0x1800654be  lea     rax, [rsp+38h+hKey]
0x1800654c3  mov     qword ptr [rsp+38h+phkResult], rax; unsigned int
0x1800654c8  mov     r9d, 1; samDesired
0x1800654ce  xor     r8d, r8d; ulOptions
0x1800654d1  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800654d8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800654df  call    cs:__imp_RegOpenKeyExA
0x1800654e5  mov     rcx, [rsp+38h]; this
0x1800654ea  test    eax, eax
0x1800654ec  jz      short loc_180065502
0x1800654ee  mov     r9d, eax; char *
0x1800654f1  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800654f8  mov     edx, 449h; void *
0x1800654fd  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180065502  mov     [rsp+38h+arg_8], 1
0x18006550a  lea     r8, [rsp+38h+arg_8]; unsigned int *
0x18006550f  lea     rdx, aConnectionwith; "ConnectionWithoutSourceBindingDisabled"
0x180065516  mov     rcx, [rsp+38h+hKey]; hKey
0x18006551b  call    ?WpnRegLoadDWord@@YAJPEAUHKEY__@@PEBGPEAK@Z; WpnRegLoadDWord(HKEY__ *,ushort const *,ulong *)
0x180065520  test    eax, eax
0x180065522  js      short loc_180065530
0x180065524  cmp     [rsp+38h+arg_8], 0
0x180065529  setnz   bl
0x18006552c  mov     byte ptr [rsp+38h+arg_0], bl
0x180065530  lea     rcx, [rsp+38h+hKey]
0x180065535  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18006553a  nop
0x18006553b  jmp     short loc_180065548
0x18006553d  lea     rdi, WPP_GLOBAL_Control
0x180065544  mov     bl, byte ptr [rsp+38h+arg_0]
0x180065548  mov     rcx, cs:WPP_GLOBAL_Control
0x18006554f  cmp     rcx, rdi
0x180065552  jz      short loc_180065578
0x180065554  test    byte ptr [rcx+1Ch], 4
0x180065558  jz      short loc_180065578
0x18006555a  cmp     byte ptr [rcx+19h], 6
0x18006555e  jb      short loc_180065578
0x180065560  mov     edx, 86h
0x180065565  mov     r9b, bl
0x180065568  lea     r8, WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids
0x18006556f  mov     rcx, [rcx+10h]
0x180065573  call    WPP_SF_c
0x180065578  mov     al, bl
0x18006557a  mov     rbx, [rsp+38h+arg_18]
0x18006557f  add     rsp, 30h
0x180065583  pop     rdi
0x180065584  retn
```
