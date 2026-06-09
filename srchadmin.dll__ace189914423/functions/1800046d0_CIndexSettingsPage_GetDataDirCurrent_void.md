# CIndexSettingsPage::_GetDataDirCurrent(void)

- ea: `0x1800046d0`
- end: `0x180004791`
- name: `?_GetDataDirCurrent@CIndexSettingsPage@@AEAAJXZ`
- size: `193`
- prototype: `__int64 __fastcall(CIndexSettingsPage *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019dcc`

## callees

- `0x1800046d0`

## import_xrefs

- `SHLWAPI!SHGetValueW` at `0x180004753`
- `SHLWAPI!SHGetValueW` at `0x180004753`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004708`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004708`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000477e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000477e`

## string_xrefs

- `0x180004735`: `DataDirectory`

## pseudocode

```c
__int64 __fastcall CIndexSettingsPage::_GetDataDirCurrent(CIndexSettingsPage *this)
{
  char *pvData; // rdi
  LSTATUS v2; // eax
  signed int v3; // ebx
  LSTATUS v4; // eax
  DWORD pdwType; // [rsp+40h] [rbp+8h] BYREF
  DWORD pcbData; // [rsp+48h] [rbp+10h] BYREF
  HKEY hkey; // [rsp+50h] [rbp+18h] BYREF

  pvData = (char *)this + 80;
  *((_WORD *)this + 40) = 0;
  hkey = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows Search", 0, 0x20019u, &hkey);
  v3 = v2;
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  if ( v3 >= 0 )
  {
    pdwType = 0;
    pcbData = 520;
    v4 = SHGetValueW(hkey, 0, L"DataDirectory", &pdwType, pvData, &pcbData);
    v3 = v4;
    if ( v4 > 0 )
      v3 = (unsigned __int16)v4 | 0x80070000;
    if ( v3 >= 0 && pdwType != 1 )
      v3 = -2147024883;
    RegCloseKey(hkey);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800046d0  mov     r11, rsp
0x1800046d3  mov     [r11+20h], rbx
0x1800046d7  push    rdi
0x1800046d8  sub     rsp, 30h
0x1800046dc  xor     eax, eax
0x1800046de  lea     rdi, [rcx+50h]
0x1800046e2  mov     [rdi], ax
0x1800046e5  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows Search"
0x1800046ec  mov     [r11+18h], rax
0x1800046f0  mov     r9d, 20019h; samDesired
0x1800046f6  lea     rax, [r11+18h]
0x1800046fa  xor     r8d, r8d; ulOptions
0x1800046fd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180004704  mov     [r11-18h], rax
0x180004708  call    cs:__imp_RegOpenKeyExW
0x18000470e  mov     ebx, eax
0x180004710  test    eax, eax
0x180004712  jle     short loc_18000471D
0x180004714  movzx   ebx, ax
0x180004717  or      ebx, 80070000h
0x18000471d  test    ebx, ebx
0x18000471f  js      short loc_180004784
0x180004721  mov     rcx, [rsp+38h+hkey]; hkey
0x180004726  lea     rax, [rsp+38h+arg_8]
0x18000472b  mov     [rsp+38h+pcbData], rax; pcbData
0x180004730  lea     r9, [rsp+38h+pdwType]; pdwType
0x180004735  lea     r8, aDatadirectory; "DataDirectory"
0x18000473c  mov     [rsp+38h+pvData], rdi; pvData
0x180004741  xor     edx, edx; pszSubKey
0x180004743  mov     [rsp+38h+pdwType], 0
0x18000474b  mov     [rsp+38h+arg_8], 208h
0x180004753  call    cs:__imp_SHGetValueW
0x180004759  mov     ebx, eax
0x18000475b  test    eax, eax
0x18000475d  jle     short loc_180004768
0x18000475f  movzx   ebx, ax
0x180004762  or      ebx, 80070000h
0x180004768  test    ebx, ebx
0x18000476a  js      short loc_180004779
0x18000476c  cmp     [rsp+38h+pdwType], 1
0x180004771  mov     eax, 8007000Dh
0x180004776  cmovnz  ebx, eax
0x180004779  mov     rcx, [rsp+38h+hkey]; hKey
0x18000477e  call    cs:__imp_RegCloseKey
0x180004784  mov     eax, ebx
0x180004786  mov     rbx, [rsp+38h+arg_18]
0x18000478b  add     rsp, 30h
0x18000478f  pop     rdi
0x180004790  retn
```
