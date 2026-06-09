# RegistryDeleteValue(HKEY__ *,ushort const *,ushort const *)

- ea: `0x180089ec8`
- end: `0x180089f91`
- name: `?RegistryDeleteValue@@YAJPEAUHKEY__@@PEBG1@Z`
- size: `201`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800e6e5c`

## callees

- `0x180008f0c`
- `0x180068404`
- `0x180089ec8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180089f58`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180089f6c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180089f80`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180089f58`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180089f6c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180089f80`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180089f01`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180089f01`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180089f19`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180089f19`

## string_xrefs

- `0x180089f3e`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\RegistryUtil.h`

## pseudocode

```c
__int64 __fastcall RegistryDeleteValue(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  HKEY *phkResult; // rax
  int v4; // ebx
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  hKey = 0;
  phkResult = tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>(&hKey);
  v4 = RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\UserData\\ChatRT", 0, 2u, phkResult);
  if ( !v4 )
    v4 = RegDeleteValueW(hKey, L"defaultMessagingAppInstanceId");
  if ( (unsigned int)(v4 - 2) <= 1 )
  {
    if ( hKey )
      RegCloseKey(hKey);
    return 1;
  }
  else if ( v4 )
  {
    if ( v4 > 0 )
      v4 = (unsigned __int16)v4 | 0x80070000;
    Log_HREvent(
      (unsigned int)v4,
      0,
      "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\RegistryUtil.h",
      360);
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)v4;
  }
  else
  {
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
}

```

## disassembly

```asm
0x180089ec8  mov     [rsp+hKey], r8
0x180089ecd  push    rbx
0x180089ece  sub     rsp, 30h
0x180089ed2  lea     rcx, [rsp+38h+hKey]
0x180089ed7  mov     [rsp+38h+hKey], 0
0x180089ee0  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x180089ee5  mov     r9d, 2; samDesired
0x180089eeb  mov     [rsp+38h+phkResult], rax; phkResult
0x180089ef0  xor     r8d, r8d; ulOptions
0x180089ef3  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\UserData\\ChatRT"
0x180089efa  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180089f01  call    cs:__imp_RegOpenKeyExW
0x180089f07  mov     ebx, eax
0x180089f09  test    eax, eax
0x180089f0b  jnz     short loc_180089F21
0x180089f0d  mov     rcx, [rsp+38h+hKey]; hKey
0x180089f12  lea     rdx, aDefaultmessagi; "defaultMessagingAppInstanceId"
0x180089f19  call    cs:__imp_RegDeleteValueW
0x180089f1f  mov     ebx, eax
0x180089f21  lea     eax, [rbx-2]
0x180089f24  cmp     eax, 1
0x180089f27  jbe     short loc_180089F76
0x180089f29  test    ebx, ebx
0x180089f2b  jz      short loc_180089F62
0x180089f2d  jle     short loc_180089F38
0x180089f2f  movzx   ebx, bx
0x180089f32  or      ebx, 80070000h
0x180089f38  mov     r9d, 168h
0x180089f3e  lea     r8, aOnecoreuapBase_48; "onecoreuap\\base\\AppModel\\UserDataAcc"...
0x180089f45  xor     edx, edx
0x180089f47  mov     ecx, ebx
0x180089f49  call    Log_HREvent
0x180089f4e  mov     rcx, [rsp+38h+hKey]; hKey
0x180089f53  test    rcx, rcx
0x180089f56  jz      short loc_180089F5E
0x180089f58  call    cs:__imp_RegCloseKey
0x180089f5e  mov     eax, ebx
0x180089f60  jmp     short loc_180089F8B
0x180089f62  mov     rcx, [rsp+38h+hKey]; hKey
0x180089f67  test    rcx, rcx
0x180089f6a  jz      short loc_180089F72
0x180089f6c  call    cs:__imp_RegCloseKey
0x180089f72  xor     eax, eax
0x180089f74  jmp     short loc_180089F8B
0x180089f76  mov     rcx, [rsp+38h+hKey]; hKey
0x180089f7b  test    rcx, rcx
0x180089f7e  jz      short loc_180089F86
0x180089f80  call    cs:__imp_RegCloseKey
0x180089f86  mov     eax, 1
0x180089f8b  add     rsp, 30h
0x180089f8f  pop     rbx
0x180089f90  retn
```
