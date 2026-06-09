# WpnSaveDeviceIdToRegistry(ushort const *)

- ea: `0x1800853b0`
- end: `0x180085484`
- name: `?WpnSaveDeviceIdToRegistry@@YAXPEBG@Z`
- size: `212`
- prototype: `void __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180074998`

## callees

- `0x18000fe0c`
- `0x180063934`
- `0x1800853b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800853f5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800853f5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18008544b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18008544b`

## string_xrefs

- `0x180085407`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`
- `0x18008545d`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall WpnSaveDeviceIdToRegistry(const BYTE *a1)
{
  LSTATUS v2; // eax
  __int64 v3; // rax
  LSTATUS v4; // eax
  int dwOptions; // [rsp+20h] [rbp-38h]
  int dwOptionsa; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  hKey = 0;
  v2 = RegCreateKeyExW(
         HKEY_CURRENT_USER,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\PushNotifications\\DeviceInfo",
         0,
         0,
         0,
         0xF003Fu,
         0,
         &hKey,
         0);
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7A3,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
      (const char *)(unsigned int)v2,
      dwOptions);
  v3 = -1;
  do
    ++v3;
  while ( *(_WORD *)&a1[2 * v3] );
  v4 = RegSetValueExW(hKey, L"DeviceVersionRepresentation", 0, 1u, a1, 2 * v3 + 2);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7AB,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
      (const char *)(unsigned int)v4,
      dwOptionsa);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x1800853b0  mov     r11, rsp
0x1800853b3  mov     [r11+8], rbx
0x1800853b7  push    rdi
0x1800853b8  sub     rsp, 50h
0x1800853bc  mov     rbx, rcx
0x1800853bf  xor     edi, edi
0x1800853c1  mov     [r11+10h], rdi
0x1800853c5  mov     [r11-18h], rdi
0x1800853c9  lea     rax, [r11+10h]
0x1800853cd  mov     [r11-20h], rax
0x1800853d1  mov     [r11-28h], rdi
0x1800853d5  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x1800853dd  mov     [rsp+58h+dwOptions], edi; int
0x1800853e1  xor     r9d, r9d; lpClass
0x1800853e4  xor     r8d, r8d; Reserved
0x1800853e7  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800853ee  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800853f5  call    cs:__imp_RegCreateKeyExW
0x1800853fb  mov     rcx, [rsp+58h]; this
0x180085400  test    eax, eax
0x180085402  jns     short loc_180085419
0x180085404  mov     r9d, eax; char *
0x180085407  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008540e  mov     edx, 7A3h; void *
0x180085413  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180085419  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008541d  inc     rax
0x180085420  cmp     [rbx+rax*2], di
0x180085424  jnz     short loc_18008541D
0x180085426  lea     eax, ds:2[rax*2]
0x18008542d  mov     [rsp+58h+samDesired], eax; cbData
0x180085431  mov     qword ptr [rsp+58h+dwOptions], rbx; int
0x180085436  mov     r9d, 1; dwType
0x18008543c  xor     r8d, r8d; Reserved
0x18008543f  lea     rdx, aDeviceversionr; "DeviceVersionRepresentation"
0x180085446  mov     rcx, [rsp+58h+hKey]; hKey
0x18008544b  call    cs:__imp_RegSetValueExW
0x180085451  mov     rcx, [rsp+58h]; this
0x180085456  test    eax, eax
0x180085458  jns     short loc_18008546F
0x18008545a  mov     r9d, eax; char *
0x18008545d  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180085464  mov     edx, 7ABh; void *
0x180085469  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008546f  lea     rcx, [rsp+58h+hKey]
0x180085474  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180085479  mov     rbx, [rsp+58h+arg_0]
0x18008547e  add     rsp, 50h
0x180085482  pop     rdi
0x180085483  retn
```
