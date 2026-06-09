# UpdateTimeZoneCache(ushort const *)

- ea: `0x180016d18`
- end: `0x180016de0`
- name: `?UpdateTimeZoneCache@@YAJPEBG@Z`
- size: `200`
- prototype: `__int64 __fastcall(const BYTE *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x18000bc30`
- `0x1800169f8`

## callees

- `0x18000e47c`
- `0x180015bac`
- `0x180016d18`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180016d5d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180016d5d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180016da0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180016da0`

## string_xrefs

- `0x180016db4`: `onecore\base\win32\winnls\tzautoupdate\timezonetoastnotification.cpp`

## pseudocode

```c
__int64 __fastcall UpdateTimeZoneCache(const BYTE *a1)
{
  unsigned int v2; // eax
  __int64 v3; // rdx
  __int64 v4; // rax
  unsigned int v5; // ebx
  unsigned int dwOptions; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  hKey = 0;
  v2 = RegCreateKeyExW(
         HKEY_USERS,
         L"S-1-5-19\\Control Panel\\International\\TzNotification",
         0,
         0,
         0,
         0x20006u,
         0,
         &hKey,
         0);
  if ( v2 )
  {
    v3 = 260;
  }
  else
  {
    v4 = -1;
    do
      ++v4;
    while ( *(_WORD *)&a1[2 * v4] );
    v2 = RegSetValueExW(hKey, L"PreviousTzChange", 0, 1u, a1, 2 * v4 + 2);
    if ( !v2 )
    {
      v5 = 0;
      goto LABEL_9;
    }
    v3 = 268;
  }
  v5 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)v3,
         (unsigned int)"onecore\\base\\win32\\winnls\\tzautoupdate\\timezonetoastnotification.cpp",
         (const char *)v2,
         dwOptions);
LABEL_9:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v5;
}

```

## disassembly

```asm
0x180016d18  mov     r11, rsp
0x180016d1b  mov     [r11+8], rbx
0x180016d1f  push    rdi
0x180016d20  sub     rsp, 50h
0x180016d24  xor     edi, edi
0x180016d26  lea     rax, [r11+10h]
0x180016d2a  mov     [r11-18h], rdi
0x180016d2e  lea     rdx, aS1519ControlPa; "S-1-5-19\\Control Panel\\International"...
0x180016d35  mov     [r11-20h], rax
0x180016d39  mov     rbx, rcx
0x180016d3c  mov     [r11-28h], rdi
0x180016d40  xor     r9d, r9d; lpClass
0x180016d43  mov     [rsp+58h+samDesired], 20006h; samDesired
0x180016d4b  xor     r8d, r8d; Reserved
0x180016d4e  mov     rcx, 0FFFFFFFF80000003h; hKey
0x180016d55  mov     [rsp+58h+dwOptions], edi; dwOptions
0x180016d59  mov     [r11+10h], rdi
0x180016d5d  call    cs:__imp_RegCreateKeyExW
0x180016d63  test    eax, eax
0x180016d65  jz      short loc_180016D6E
0x180016d67  mov     edx, 104h
0x180016d6c  jmp     short loc_180016DAF
0x180016d6e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180016d72  inc     rax
0x180016d75  cmp     [rbx+rax*2], di
0x180016d79  jnz     short loc_180016D72
0x180016d7b  mov     rcx, [rsp+58h+hKey]; hKey
0x180016d80  lea     eax, ds:2[rax*2]
0x180016d87  mov     [rsp+58h+samDesired], eax; cbData
0x180016d8b  lea     rdx, ValueName; "PreviousTzChange"
0x180016d92  mov     r9d, 1; dwType
0x180016d98  mov     qword ptr [rsp+58h+dwOptions], rbx; unsigned int
0x180016d9d  xor     r8d, r8d; Reserved
0x180016da0  call    cs:__imp_RegSetValueExW
0x180016da6  test    eax, eax
0x180016da8  jz      short loc_180016DC7
0x180016daa  mov     edx, 10Ch; void *
0x180016daf  mov     rcx, [rsp+58h]; this
0x180016db4  lea     r8, aOnecoreBaseWin_2; "onecore\\base\\win32\\winnls\\tzautoupd"...
0x180016dbb  mov     r9d, eax; char *
0x180016dbe  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180016dc3  mov     ebx, eax
0x180016dc5  jmp     short loc_180016DC9
0x180016dc7  mov     ebx, edi
0x180016dc9  lea     rcx, [rsp+58h+hKey]
0x180016dce  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180016dd3  mov     eax, ebx
0x180016dd5  mov     rbx, [rsp+58h+arg_0]
0x180016dda  add     rsp, 50h
0x180016dde  pop     rdi
0x180016ddf  retn
```
