# DllUnregisterServer

- ea: `0x1800025b0`
- end: `0x180002637`
- name: `DllUnregisterServer`
- size: `135`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800025b0`
- `0x180003938`

## import_xrefs

- `ADVAPI32!RegDeleteTreeW` at `0x180002610`
- `ADVAPI32!RegDeleteTreeW` at `0x180002610`

## string_xrefs

- `0x1800025bb`: `CLSID\{606B3777-3051-401F-974A-E66ACA82A3A3}`
- `0x1800025d0`: `Software\Microsoft\Windows\CurrentVersion\Explorer\VolumeCaches\Update Cleanup`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  HRESULT v0; // ebx
  unsigned __int64 v1; // rdi
  const WCHAR *v2; // rsi
  HKEY v3; // rbp
  LSTATUS v4; // eax
  HKEY hKey; // [rsp+20h] [rbp-48h]
  LPCWSTR lpSubKey[8]; // [rsp+28h] [rbp-40h]

  hKey = HKEY_CLASSES_ROOT;
  lpSubKey[0] = L"CLSID\\{606B3777-3051-401F-974A-E66ACA82A3A3}";
  v0 = 0;
  lpSubKey[1] = (LPCWSTR)-2147483646LL;
  lpSubKey[2] = L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\VolumeCaches\\Update Cleanup";
  v1 = 0;
  do
  {
    if ( v1 >= 2 )
      break;
    v2 = lpSubKey[2 * v1];
    v3 = (HKEY)lpSubKey[2 * v1 - 1];
    if ( (unsigned int)RegExists(v3, v2) )
    {
      v4 = RegDeleteTreeW(v3, v2);
      v0 = v4;
      if ( v4 > 0 )
        v0 = (unsigned __int16)v4 | 0x80070000;
    }
    ++v1;
  }
  while ( v0 >= 0 );
  return v0;
}

```

## disassembly

```asm
0x1800025b0  mov     r11, rsp
0x1800025b3  push    rbx
0x1800025b4  push    rbp
0x1800025b5  push    rsi
0x1800025b6  push    rdi
0x1800025b7  sub     rsp, 48h
0x1800025bb  lea     rax, aClsid606b37773_0; "CLSID\\{606B3777-3051-401F-974A-E66ACA8"...
0x1800025c2  mov     qword ptr [r11-48h], 0FFFFFFFF80000000h
0x1800025ca  mov     [r11-40h], rax
0x1800025ce  xor     ebx, ebx
0x1800025d0  lea     rax, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800025d7  mov     qword ptr [r11-38h], 0FFFFFFFF80000002h
0x1800025df  mov     [r11-30h], rax
0x1800025e3  xor     edi, edi
0x1800025e5  cmp     rdi, 2
0x1800025e9  jnb     short loc_18000262C
0x1800025eb  mov     rax, rdi
0x1800025ee  add     rax, rax
0x1800025f1  mov     rsi, [rsp+rax*8+68h+lpSubKey]
0x1800025f6  mov     rbp, [rsp+rax*8+68h+hKey]
0x1800025fb  mov     rdx, rsi
0x1800025fe  mov     rcx, rbp
0x180002601  call    RegExists
0x180002606  test    eax, eax
0x180002608  jz      short loc_180002625
0x18000260a  mov     rdx, rsi; lpSubKey
0x18000260d  mov     rcx, rbp; hKey
0x180002610  call    cs:__imp_RegDeleteTreeW
0x180002616  mov     ebx, eax
0x180002618  test    eax, eax
0x18000261a  jle     short loc_180002625
0x18000261c  movzx   ebx, ax
0x18000261f  or      ebx, 80070000h
0x180002625  inc     rdi
0x180002628  test    ebx, ebx
0x18000262a  jns     short loc_1800025E5
0x18000262c  mov     eax, ebx
0x18000262e  add     rsp, 48h
0x180002632  pop     rdi
0x180002633  pop     rsi
0x180002634  pop     rbp
0x180002635  pop     rbx
0x180002636  retn
```
