# SetEndpointChangedStatusInRegistry(bool)

- ea: `0x1800848e4`
- end: `0x1800849b3`
- name: `?SetEndpointChangedStatusInRegistry@@YAX_N@Z`
- size: `207`
- prototype: `void __fastcall(bool)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180039834`
- `0x180071e6c`

## callees

- `0x180063934`
- `0x180066964`
- `0x1800848e4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180084936`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180084936`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18008497d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18008497d`

## string_xrefs

- `0x180084948`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`
- `0x18008498f`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SetEndpointChangedStatusInRegistry(unsigned __int8 a1)
{
  unsigned int v1; // eax
  unsigned int v2; // eax
  const char *v3; // r9
  unsigned int dwOptions; // [rsp+20h] [rbp-38h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  int Data; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  Data = a1;
  hKey = 0;
  v1 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\PushNotifications\\DeviceInfo",
         0,
         0,
         0,
         0xF003Fu,
         0,
         &hKey,
         0);
  try
  {
    if ( v1 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x826,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
        (const char *)v1,
        dwOptions);
    v2 = RegSetValueExW(hKey, L"DeviceEndpointChanged", 0, 4u, (const BYTE *)&Data, 4u);
    if ( v2 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x82E,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
        (const char *)v2,
        dwOptionsa);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x830,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
      v3);
  }
}

```

## disassembly

```asm
0x1800848e4  mov     r11, rsp
0x1800848e7  sub     rsp, 58h
0x1800848eb  movzx   eax, cl
0x1800848ee  mov     [rsp+58h+Data], eax
0x1800848f2  mov     qword ptr [r11+10h], 0
0x1800848fa  mov     qword ptr [r11-18h], 0
0x180084902  lea     rax, [r11+10h]
0x180084906  mov     [r11-20h], rax
0x18008490a  mov     qword ptr [r11-28h], 0
0x180084912  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x18008491a  mov     [rsp+58h+dwOptions], 0; unsigned int
0x180084922  xor     r9d, r9d; lpClass
0x180084925  xor     r8d, r8d; Reserved
0x180084928  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18008492f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180084936  call    cs:__imp_RegCreateKeyExW
0x18008493c  mov     rcx, [rsp+58h]; this
0x180084941  test    eax, eax
0x180084943  jz      short loc_180084959
0x180084945  mov     r9d, eax; char *
0x180084948  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008494f  mov     edx, 826h; void *
0x180084954  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180084959  mov     r9d, 4; dwType
0x18008495f  mov     [rsp+58h+samDesired], r9d; cbData
0x180084964  lea     rax, [rsp+58h+Data]
0x180084969  mov     qword ptr [rsp+58h+dwOptions], rax; unsigned int
0x18008496e  xor     r8d, r8d; Reserved
0x180084971  lea     rdx, aDeviceendpoint; "DeviceEndpointChanged"
0x180084978  mov     rcx, [rsp+58h+hKey]; hKey
0x18008497d  call    cs:__imp_RegSetValueExW
0x180084983  mov     rcx, [rsp+58h]; this
0x180084988  test    eax, eax
0x18008498a  jz      short loc_1800849A1
0x18008498c  mov     r9d, eax; char *
0x18008498f  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180084996  mov     edx, 82Eh; void *
0x18008499b  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800849a1  lea     rcx, [rsp+58h+hKey]
0x1800849a6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800849ab  nop
0x1800849ac  jmp     short $+2
0x1800849ae  add     rsp, 58h
0x1800849b2  retn
```
