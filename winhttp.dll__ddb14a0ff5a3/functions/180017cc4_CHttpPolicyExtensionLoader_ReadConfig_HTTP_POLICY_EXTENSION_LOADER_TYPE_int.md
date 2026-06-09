# CHttpPolicyExtensionLoader::ReadConfig(_HTTP_POLICY_EXTENSION_LOADER_TYPE,int)

- ea: `0x180017cc4`
- end: `0x180017e3a`
- name: `?ReadConfig@CHttpPolicyExtensionLoader@@AEAAJW4_HTTP_POLICY_EXTENSION_LOADER_TYPE@@H@Z`
- size: `374`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006e610`

## callees

- `0x180017cc4`
- `0x18001944c`
- `0x1800a1d10`
- `0x1800a2660`
- `0x1800cf4c4`
- `0x1800db6b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017d40`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017d40`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017dca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017dca`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x180017d6d`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x180017d6d`

## string_xrefs

- `0x180017d32`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\PolicyExtensions`

## pseudocode

```c
__int64 __fastcall CHttpPolicyExtensionLoader::ReadConfig(unsigned __int16 *a1, __int64 a2, int a3)
{
  LSTATUS v5; // eax
  signed int v6; // ebx
  DWORD v7; // edi
  DWORD i; // edx
  LSTATUS v9; // eax
  __int64 v10; // rdx
  PHKEY phkResult; // [rsp+20h] [rbp-268h]
  HKEY hKey; // [rsp+38h] [rbp-250h] BYREF
  WCHAR Name; // [rsp+40h] [rbp-248h] BYREF
  _BYTE v15[526]; // [rsp+42h] [rbp-246h] BYREF

  hKey = 0;
  Name = 0;
  memset_0(v15, 0, 0x206u);
  if ( (BYTE1(xmmword_180107A60) & 0x40) != 0 )
    WPP_SF_Dd(1038, 31, WPP_70a6ea6fbc8b32957ec072c0c9e35dfc_Traceguids, 1);
  v5 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\PolicyExtensions",
         0,
         0x20019u,
         &hKey);
  v6 = v5;
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  if ( v6 >= 0 )
  {
    v7 = 0;
    for ( i = 0; ; i = v7 )
    {
      v9 = RegEnumKeyW(hKey, i, &Name, 0x104u);
      if ( v9 == 259 )
        break;
      v6 = v9 <= 0 ? v9 : (unsigned __int16)v9 | 0x80070000;
      if ( v6 < 0 )
        break;
      CHttpPolicyExtensionLoader::ReadExtensionConfig(a1, v10, a3, hKey, &Name);
      ++v7;
    }
  }
  if ( (BYTE1(xmmword_180107A60) & 0x40) != 0 )
    WPP_SF_d(1038, 32, WPP_70a6ea6fbc8b32957ec072c0c9e35dfc_Traceguids, (unsigned int)v6, phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180017cc4  push    rbx
0x180017cc6  push    rbp
0x180017cc7  push    rsi
0x180017cc8  push    rdi
0x180017cc9  sub     rsp, 268h
0x180017cd0  mov     rax, cs:__security_cookie
0x180017cd7  xor     rax, rsp
0x180017cda  mov     [rsp+288h+var_38], rax
0x180017ce2  mov     esi, r8d
0x180017ce5  mov     [rsp+288h+var_254], 0
0x180017ced  mov     rbp, rcx
0x180017cf0  mov     [rsp+288h+hKey], 0
0x180017cf9  xor     eax, eax
0x180017cfb  lea     rcx, [rsp+288h+var_246]; void *
0x180017d00  mov     r8d, 206h; Size
0x180017d06  mov     [rsp+288h+Name], ax
0x180017d0b  xor     edx, edx; Val
0x180017d0d  call    memset_0
0x180017d12  test    byte ptr cs:xmmword_180107A60+1, 40h
0x180017d19  jnz     loc_180017DF2
0x180017d1f  lea     rax, [rsp+288h+hKey]
0x180017d24  mov     r9d, 20019h; samDesired
0x180017d2a  xor     r8d, r8d; ulOptions
0x180017d2d  mov     [rsp+288h+phkResult], rax; phkResult
0x180017d32  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180017d39  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180017d40  call    cs:__imp_RegOpenKeyExW
0x180017d46  mov     ebx, eax
0x180017d48  test    eax, eax
0x180017d4a  jle     short loc_180017D55
0x180017d4c  movzx   ebx, ax
0x180017d4f  or      ebx, 80070000h
0x180017d55  test    ebx, ebx
0x180017d57  js      short loc_180017DAF
0x180017d59  xor     edi, edi
0x180017d5b  xor     edx, edx; dwIndex
0x180017d5d  mov     rcx, [rsp+288h+hKey]; hKey
0x180017d62  lea     r8, [rsp+288h+Name]; lpName
0x180017d67  mov     r9d, 104h; cchName
0x180017d6d  call    cs:__imp_RegEnumKeyW
0x180017d73  cmp     eax, 103h
0x180017d78  jz      short loc_180017DB7
0x180017d7a  test    eax, eax
0x180017d7c  jle     short loc_180017DEE
0x180017d7e  movzx   ebx, ax
0x180017d81  or      ebx, 80070000h
0x180017d87  test    ebx, ebx
0x180017d89  js      loc_180017E15
0x180017d8f  mov     r9, [rsp+288h+hKey]
0x180017d94  lea     rax, [rsp+288h+Name]
0x180017d99  mov     r8d, esi
0x180017d9c  mov     [rsp+288h+phkResult], rax
0x180017da1  mov     rcx, rbp
0x180017da4  call    ?ReadExtensionConfig@CHttpPolicyExtensionLoader@@AEAAJW4_HTTP_POLICY_EXTENSION_LOADER_TYPE@@HPEAUHKEY__@@PEBG@Z; CHttpPolicyExtensionLoader::ReadExtensionConfig(_HTTP_POLICY_EXTENSION_LOADER_TYPE,int,HKEY__ *,ushort const *)
0x180017da9  inc     edi
0x180017dab  mov     edx, edi
0x180017dad  jmp     short loc_180017D5D
0x180017daf  mov     [rsp+288h+var_254], 1CAh
0x180017db7  test    byte ptr cs:xmmword_180107A60+1, 40h
0x180017dbe  jnz     short loc_180017E1F
0x180017dc0  mov     rcx, [rsp+288h+hKey]; hKey
0x180017dc5  test    rcx, rcx
0x180017dc8  jz      short loc_180017DD0
0x180017dca  call    cs:__imp_RegCloseKey
0x180017dd0  mov     eax, ebx
0x180017dd2  mov     rcx, [rsp+288h+var_38]
0x180017dda  xor     rcx, rsp; StackCookie
0x180017ddd  call    __security_check_cookie
0x180017de2  add     rsp, 268h
0x180017de9  pop     rdi
0x180017dea  pop     rsi
0x180017deb  pop     rbp
0x180017dec  pop     rbx
0x180017ded  retn
0x180017dee  mov     ebx, eax
0x180017df0  jmp     short loc_180017D87
0x180017df2  mov     edx, 1Fh
0x180017df7  mov     dword ptr [rsp+288h+phkResult], esi
0x180017dfb  mov     ecx, 40Eh
0x180017e00  lea     r8, WPP_70a6ea6fbc8b32957ec072c0c9e35dfc_Traceguids
0x180017e07  lea     r9d, [rdx-1Eh]
0x180017e0b  call    WPP_SF_Dd
0x180017e10  jmp     loc_180017D1F
0x180017e15  mov     [rsp+288h+var_254], 1D6h
0x180017e1d  jmp     short loc_180017DB7
0x180017e1f  mov     edx, 20h ; ' '
0x180017e24  lea     r8, WPP_70a6ea6fbc8b32957ec072c0c9e35dfc_Traceguids
0x180017e2b  mov     ecx, 40Eh
0x180017e30  mov     r9d, ebx
0x180017e33  call    WPP_SF_d
0x180017e38  jmp     short loc_180017DC0
```
