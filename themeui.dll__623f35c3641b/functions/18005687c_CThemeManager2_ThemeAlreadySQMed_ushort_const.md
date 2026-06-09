# CThemeManager2::_ThemeAlreadySQMed(ushort const *)

- ea: `0x18005687c`
- end: `0x1800569fe`
- name: `?_ThemeAlreadySQMed@CThemeManager2@@AEAA_NPEBG@Z`
- size: `386`
- prototype: `bool(CThemeManager2 *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001e5d0`

## callees

- `0x18001b26c`
- `0x1800358c0`
- `0x18005687c`
- `0x180060008`

## import_xrefs

- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x1800568d0`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x1800568d0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800568f0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180056917`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800569b8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800568f0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180056917`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800569b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800569ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800569ce`

## string_xrefs

- `0x180056942`: `Software\Microsoft\Windows\CurrentVersion\Themes\InstalledThemes\SQM`

## pseudocode

```c
char __fastcall CThemeManager2::_ThemeAlreadySQMed(const WCHAR *this, const unsigned __int16 *a2)
{
  unsigned int i; // ebx
  unsigned int v5; // r8d
  char v6; // bl
  int v7; // esi
  unsigned int v8; // edi
  unsigned int *bIgnoreCase; // [rsp+20h] [rbp-268h]
  unsigned int v11; // [rsp+40h] [rbp-248h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-240h] BYREF
  WCHAR String2[264]; // [rsp+50h] [rbp-238h] BYREF

  for ( i = 0; i < 0xA; ++i )
  {
    if ( (unsigned int)SHExpandEnvironmentStringsW((&off_18006FE40)[2 * (int)i], String2, 260)
      && CompareStringOrdinal(a2, -1, String2, -1, 1) == 2 )
    {
      return 1;
    }
  }
  if ( CompareStringOrdinal(a2, -1, this + 266, -1, 1) == 2 )
    return 1;
  hKey = 0;
  v6 = 0;
  if ( (int)HrRegOpenKeyEx(
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes\\InstalledThemes\\SQM",
              v5,
              0x20019u,
              &hKey) >= 0 )
  {
    v7 = 0;
    v8 = 0;
    while ( v7 >= 0 )
    {
      v11 = 260;
      v7 = HrRegEnumValue(hKey, v8, String2, &v11, bIgnoreCase, 0, 0, 0);
      if ( v7 >= 0 && CompareStringOrdinal(a2, -1, String2, -1, 1) == 2 )
      {
        v6 = 1;
        break;
      }
      ++v8;
    }
    RegCloseKey(hKey);
  }
  return v6;
}

```

## disassembly

```asm
0x18005687c  mov     [rsp+arg_10], rbx
0x180056881  mov     [rsp+arg_18], rbp
0x180056886  push    rsi
0x180056887  push    rdi
0x180056888  push    r12
0x18005688a  sub     rsp, 270h
0x180056891  mov     rax, cs:__security_cookie
0x180056898  xor     rax, rsp
0x18005689b  mov     [rsp+288h+var_28], rax
0x1800568a3  xor     ebx, ebx
0x1800568a5  mov     rbp, rdx
0x1800568a8  or      r12d, 0FFFFFFFFh
0x1800568ac  mov     rdi, rcx
0x1800568af  cmp     ebx, 0Ah
0x1800568b2  jnb     short loc_1800568FF
0x1800568b4  lea     rax, off_18006FE40; "%windir%\\Resources\\Themes\\aero.theme"
0x1800568bb  movsxd  rcx, ebx
0x1800568be  add     rcx, rcx
0x1800568c1  lea     rdx, [rsp+288h+String2]
0x1800568c6  mov     r8d, 104h
0x1800568cc  mov     rcx, [rax+rcx*8]
0x1800568d0  call    cs:__imp_SHExpandEnvironmentStringsW
0x1800568d6  test    eax, eax
0x1800568d8  jz      short loc_1800568FB
0x1800568da  mov     r9d, r12d; cchCount2
0x1800568dd  mov     [rsp+288h+bIgnoreCase], 1; bIgnoreCase
0x1800568e5  lea     r8, [rsp+288h+String2]; lpString2
0x1800568ea  mov     edx, r12d; cchCount1
0x1800568ed  mov     rcx, rbp; lpString1
0x1800568f0  call    cs:__imp_CompareStringOrdinal
0x1800568f6  cmp     eax, 2
0x1800568f9  jz      short loc_180056922
0x1800568fb  inc     ebx
0x1800568fd  jmp     short loc_1800568AF
0x1800568ff  lea     r8, [rdi+214h]; lpString2
0x180056906  mov     [rsp+288h+bIgnoreCase], 1; bIgnoreCase
0x18005690e  mov     r9d, r12d; cchCount2
0x180056911  mov     edx, r12d; cchCount1
0x180056914  mov     rcx, rbp; lpString1
0x180056917  call    cs:__imp_CompareStringOrdinal
0x18005691d  cmp     eax, 2
0x180056920  jnz     short loc_180056929
0x180056922  mov     bl, 1
0x180056924  jmp     loc_1800569D4
0x180056929  lea     rax, [rsp+288h+hKey]
0x18005692e  mov     [rsp+288h+hKey], 0
0x180056937  mov     r9d, 20019h; unsigned int
0x18005693d  mov     qword ptr [rsp+288h+bIgnoreCase], rax; unsigned int *
0x180056942  lea     rdx, aSoftwareMicros_16; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180056949  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x180056950  xor     bl, bl
0x180056952  call    ?HrRegOpenKeyEx@@YAJPEAUHKEY__@@PEBGKKPEAPEAU1@@Z; HrRegOpenKeyEx(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x180056957  test    eax, eax
0x180056959  js      short loc_1800569D4
0x18005695b  xor     esi, esi
0x18005695d  xor     edi, edi
0x18005695f  test    esi, esi
0x180056961  js      short loc_1800569C9
0x180056963  mov     rcx, [rsp+288h+hKey]; HKEY
0x180056968  lea     r9, [rsp+288h+var_248]; unsigned int *
0x18005696d  mov     [rsp+288h+var_250], 0; unsigned int *
0x180056976  lea     r8, [rsp+288h+String2]; unsigned __int16 *
0x18005697b  mov     [rsp+288h+var_258], 0; unsigned __int8 *
0x180056984  mov     edx, edi; unsigned int
0x180056986  mov     [rsp+288h+var_260], 0; unsigned int *
0x18005698f  mov     [rsp+288h+var_248], 104h
0x180056997  call    ?HrRegEnumValue@@YAJPEAUHKEY__@@KPEAGPEAK22PEAE2@Z; HrRegEnumValue(HKEY__ *,ulong,ushort *,ulong *,ulong *,ulong *,uchar *,ulong *)
0x18005699c  mov     esi, eax
0x18005699e  test    eax, eax
0x1800569a0  js      short loc_1800569C3
0x1800569a2  mov     r9d, r12d; cchCount2
0x1800569a5  mov     [rsp+288h+bIgnoreCase], 1; bIgnoreCase
0x1800569ad  lea     r8, [rsp+288h+String2]; lpString2
0x1800569b2  mov     edx, r12d; cchCount1
0x1800569b5  mov     rcx, rbp; lpString1
0x1800569b8  call    cs:__imp_CompareStringOrdinal
0x1800569be  cmp     eax, 2
0x1800569c1  jz      short loc_1800569C7
0x1800569c3  inc     edi
0x1800569c5  jmp     short loc_18005695F
0x1800569c7  mov     bl, 1
0x1800569c9  mov     rcx, [rsp+288h+hKey]; hKey
0x1800569ce  call    cs:__imp_RegCloseKey
0x1800569d4  mov     al, bl
0x1800569d6  mov     rcx, [rsp+288h+var_28]
0x1800569de  xor     rcx, rsp; StackCookie
0x1800569e1  call    __security_check_cookie
0x1800569e6  lea     r11, [rsp+288h+var_18]
0x1800569ee  mov     rbx, [r11+30h]
0x1800569f2  mov     rbp, [r11+38h]
0x1800569f6  mov     rsp, r11
0x1800569f9  pop     r12
0x1800569fb  pop     rdi
0x1800569fc  pop     rsi
0x1800569fd  retn
```
