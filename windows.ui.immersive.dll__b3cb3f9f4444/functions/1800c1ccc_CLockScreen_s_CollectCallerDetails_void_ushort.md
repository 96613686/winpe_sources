# CLockScreen::_s_CollectCallerDetails(void *,ushort * *)

- ea: `0x1800c1ccc`
- end: `0x1800c1f5d`
- name: `?_s_CollectCallerDetails@CLockScreen@@KAJPEAXPEAPEAG@Z`
- size: `657`
- prototype: `__int64 __fastcall(void *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800bc090`
- `0x1800bc140`
- `0x1800c186c`

## callees

- `0x18000b5b8`
- `0x18000da00`
- `0x18003d244`
- `0x180054130`
- `0x1800c1ccc`
- `0x1800e03b4`
- `0x1800e043c`
- `0x1800e07ec`

## import_xrefs

- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800c1dc2`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800c1dc2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c1e46`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c1e46`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x1800c1e17`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x1800c1e17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1ef4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1ef4`

## string_xrefs

- `0x1800c1d21`: `%SystemRoot%\System32\SettingSyncHost.exe`
- `0x1800c1d5b`: `%SystemRoot%\System32\svchost.exe`
- `0x1800c1d50`: `%SystemRoot%\System32\dllhost.exe`
- `0x1800c1d45`: `%SystemRoot%\System32\taskhost.exe`
- `0x1800c1d39`: `%SystemRoot%\System32\rundll32.exe`

## pseudocode

```c
__int64 __fastcall CLockScreen::_s_CollectCallerDetails(void *a1, unsigned __int16 **a2, unsigned int *a3)
{
  unsigned __int16 **v5; // rdx
  int CallerProcessImageName; // ebx
  unsigned __int16 **v7; // r8
  unsigned int v8; // edi
  __int64 v9; // rcx
  int ProcessAppId; // eax
  void *v11; // rdi
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  DWORD dwSize; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 v19[4]; // [rsp+40h] [rbp-C0h] BYREF
  const WCHAR *v20; // [rsp+48h] [rbp-B8h]
  _BYTE v21[8]; // [rsp+50h] [rbp-B0h]
  const wchar_t *v22; // [rsp+58h] [rbp-A8h]
  const WCHAR *v23; // [rsp+60h] [rbp-A0h]
  char v24; // [rsp+68h] [rbp-98h]
  const wchar_t *v25; // [rsp+70h] [rbp-90h]
  __int64 v26; // [rsp+78h] [rbp-88h]
  char v27; // [rsp+80h] [rbp-80h]
  const wchar_t *v28; // [rsp+88h] [rbp-78h]
  __int64 v29; // [rsp+90h] [rbp-70h]
  char v30; // [rsp+98h] [rbp-68h]
  const wchar_t *v31; // [rsp+A0h] [rbp-60h]
  __int64 v32; // [rsp+A8h] [rbp-58h]
  char v33; // [rsp+B0h] [rbp-50h]
  const wchar_t *v34; // [rsp+B8h] [rbp-48h]
  __int64 v35; // [rsp+C0h] [rbp-40h]
  char v36; // [rsp+C8h] [rbp-38h]
  WCHAR ExeName[264]; // [rsp+250h] [rbp+150h] BYREF
  WCHAR String2[264]; // [rsp+460h] [rbp+360h] BYREF

  v21[0] = 1;
  *a2 = 0;
  *(_QWORD *)v19 = L"%SystemRoot%\\ImmersiveControlPanel\\SystemSettings.exe";
  v20 = L"IMMERSIVE_CPL";
  v22 = L"%SystemRoot%\\System32\\SettingSyncHost.exe";
  v23 = L"ROAMING";
  v25 = L"%SystemRoot%\\System32\\rundll32.exe";
  v28 = L"%SystemRoot%\\System32\\taskhost.exe";
  v31 = L"%SystemRoot%\\System32\\dllhost.exe";
  v34 = L"%SystemRoot%\\System32\\svchost.exe";
  v24 = 1;
  v26 = 0;
  v27 = 0;
  v29 = 0;
  v30 = 0;
  v32 = 0;
  v33 = 0;
  v35 = 0;
  v36 = 0;
  dwSize = 260;
  if ( !a1 )
  {
    CallerProcessImageName = CallerIdentity::GetCallerProcessImageName(ExeName, &dwSize, a3);
LABEL_6:
    v8 = 0;
    if ( CallerProcessImageName >= 0 )
      goto LABEL_7;
    return (unsigned int)CallerProcessImageName;
  }
  if ( !QueryFullProcessImageNameW(a1, 0, ExeName, &dwSize) )
  {
    CallerProcessImageName = ResultFromKnownLastError();
    if ( CallerProcessImageName < 0 )
      return (unsigned int)CallerProcessImageName;
    goto LABEL_6;
  }
  CallerProcessImageName = 0;
  v8 = 0;
  do
  {
LABEL_7:
    if ( *a2 || v8 >= 6 )
      break;
    CallerProcessImageName = SHExpandEnvironmentStringsW(*(_QWORD *)&v19[12 * v8], String2, 260);
    if ( CallerProcessImageName >= 0 && CompareStringOrdinal(ExeName, -1, String2, -1, 1) == 2 )
    {
      if ( !v21[24 * v8] )
        return (unsigned int)-2147024891;
      CallerProcessImageName = _AllocString<CTCoAllocPolicy>(v9, (__int64)v5, *(const WCHAR **)&v21[24 * v8 - 8], a2);
    }
    ++v8;
  }
  while ( CallerProcessImageName >= 0 );
  if ( CallerProcessImageName >= 0 && !*a2 )
  {
    pv = 0;
    if ( a1 )
      ProcessAppId = CallerIdentity::GetProcessAppId(a1, &pv, v7);
    else
      ProcessAppId = CallerIdentity::GetCallingProcessAppId((CallerIdentity *)&pv, v5);
    if ( ProcessAppId < 0 )
    {
      CallerProcessImageName = StringCchPrintfW(v19, 0x104u, L"%s%s", L"IMAGENAME:", ExeName);
      if ( CallerProcessImageName >= 0 )
        return (unsigned int)_AllocString<CTCoAllocPolicy>(v15, v14, v19, a2);
    }
    else
    {
      v11 = pv;
      CallerProcessImageName = StringCchPrintfW(v19, 0x104u, L"%s%s", L"APPID:", pv);
      if ( CallerProcessImageName >= 0 )
        CallerProcessImageName = _AllocString<CTCoAllocPolicy>(v13, v12, v19, a2);
      CoTaskMemFree(v11);
    }
  }
  return (unsigned int)CallerProcessImageName;
}

```

## disassembly

```asm
0x1800c1ccc  mov     [rsp-8+arg_10], rbx
0x1800c1cd1  mov     [rsp-8+arg_18], rsi
0x1800c1cd6  push    rbp
0x1800c1cd7  push    rdi
0x1800c1cd8  push    r12
0x1800c1cda  push    r14
0x1800c1cdc  push    r15
0x1800c1cde  lea     rbp, [rsp-580h]
0x1800c1ce6  sub     rsp, 680h
0x1800c1ced  mov     rax, cs:__security_cookie
0x1800c1cf4  xor     rax, rsp
0x1800c1cf7  mov     [rbp+5A0h+var_30], rax
0x1800c1cfe  xor     r12d, r12d
0x1800c1d01  mov     [rsp+6A0h+var_650], 1
0x1800c1d06  mov     [rdx], r12
0x1800c1d09  lea     rax, aSystemrootImme; "%SystemRoot%\\ImmersiveControlPanel\\Sy"...
0x1800c1d10  mov     qword ptr [rsp+6A0h+var_660], rax
0x1800c1d15  lea     rax, aImmersiveCpl; "IMMERSIVE_CPL"
0x1800c1d1c  mov     [rsp+6A0h+var_658], rax
0x1800c1d21  lea     rax, aSystemrootSyst_0; "%SystemRoot%\\System32\\SettingSyncHost"...
0x1800c1d28  mov     [rsp+6A0h+var_648], rax
0x1800c1d2d  lea     rax, aRoaming; "ROAMING"
0x1800c1d34  mov     [rsp+6A0h+var_640], rax
0x1800c1d39  lea     rax, aSystemrootSyst_4; "%SystemRoot%\\System32\\rundll32.exe"
0x1800c1d40  mov     [rsp+6A0h+var_630], rax
0x1800c1d45  lea     rax, aSystemrootSyst_3; "%SystemRoot%\\System32\\taskhost.exe"
0x1800c1d4c  mov     [rbp+5A0h+var_618], rax
0x1800c1d50  lea     rax, aSystemrootSyst_5; "%SystemRoot%\\System32\\dllhost.exe"
0x1800c1d57  mov     [rbp+5A0h+var_600], rax
0x1800c1d5b  lea     rax, aSystemrootSyst; "%SystemRoot%\\System32\\svchost.exe"
0x1800c1d62  mov     [rbp+5A0h+var_5E8], rax
0x1800c1d66  mov     rsi, rdx
0x1800c1d69  mov     [rsp+6A0h+var_638], 1
0x1800c1d6e  mov     r15, rcx
0x1800c1d71  mov     [rsp+6A0h+var_628], r12
0x1800c1d76  mov     [rbp+5A0h+var_620], r12b
0x1800c1d7a  mov     [rbp+5A0h+var_610], r12
0x1800c1d7e  mov     [rbp+5A0h+var_608], r12b
0x1800c1d82  mov     [rbp+5A0h+var_5F8], r12
0x1800c1d86  mov     [rbp+5A0h+var_5F0], r12b
0x1800c1d8a  mov     [rbp+5A0h+var_5E0], r12
0x1800c1d8e  mov     [rbp+5A0h+var_5D8], r12b
0x1800c1d92  mov     [rsp+6A0h+dwSize], 104h
0x1800c1d9a  test    rcx, rcx
0x1800c1d9d  jnz     short loc_1800C1DB4
0x1800c1d9f  lea     rdx, [rsp+6A0h+dwSize]; lpdwSize
0x1800c1da4  lea     rcx, [rbp+5A0h+ExeName]; lpExeName
0x1800c1dab  call    ?GetCallerProcessImageName@CallerIdentity@@YAJPEAGPEAK@Z; CallerIdentity::GetCallerProcessImageName(ushort *,ulong *)
0x1800c1db0  mov     ebx, eax
0x1800c1db2  jmp     short loc_1800C1DE9
0x1800c1db4  lea     r9, [rsp+6A0h+dwSize]; lpdwSize
0x1800c1db9  xor     edx, edx; dwFlags
0x1800c1dbb  lea     r8, [rbp+5A0h+ExeName]; lpExeName
0x1800c1dc2  call    cs:__imp_QueryFullProcessImageNameW
0x1800c1dc9  nop     dword ptr [rax+rax+00h]
0x1800c1dce  test    eax, eax
0x1800c1dd0  jz      short loc_1800C1DDA
0x1800c1dd2  mov     ebx, r12d
0x1800c1dd5  mov     edi, r12d
0x1800c1dd8  jmp     short loc_1800C1DF4
0x1800c1dda  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800c1ddf  mov     ebx, eax
0x1800c1de1  test    eax, eax
0x1800c1de3  js      loc_1800C1F2F
0x1800c1de9  mov     edi, r12d
0x1800c1dec  test    ebx, ebx
0x1800c1dee  js      loc_1800C1F2F
0x1800c1df4  cmp     [rsi], r12
0x1800c1df7  jnz     short loc_1800C1E73
0x1800c1df9  cmp     edi, 6
0x1800c1dfc  jnb     short loc_1800C1E73
0x1800c1dfe  movsxd  rax, edi
0x1800c1e01  lea     rdx, [rbp+5A0h+String2]
0x1800c1e08  mov     r8d, 104h
0x1800c1e0e  lea     r14, [rax+rax*2]
0x1800c1e12  mov     rcx, qword ptr [rsp+r14*8+6A0h+var_660]
0x1800c1e17  call    cs:__imp_SHExpandEnvironmentStringsW
0x1800c1e1e  nop     dword ptr [rax+rax+00h]
0x1800c1e23  mov     ebx, eax
0x1800c1e25  test    eax, eax
0x1800c1e27  js      short loc_1800C1E6D
0x1800c1e29  or      r9d, 0FFFFFFFFh; cchCount2
0x1800c1e2d  mov     [rsp+6A0h+bIgnoreCase], 1; bIgnoreCase
0x1800c1e35  or      edx, r9d; cchCount1
0x1800c1e38  lea     r8, [rbp+5A0h+String2]; lpString2
0x1800c1e3f  lea     rcx, [rbp+5A0h+ExeName]; lpString1
0x1800c1e46  call    cs:__imp_CompareStringOrdinal
0x1800c1e4d  nop     dword ptr [rax+rax+00h]
0x1800c1e52  cmp     eax, 2
0x1800c1e55  jnz     short loc_1800C1E6D
0x1800c1e57  cmp     [rsp+r14*8+6A0h+var_650], r12b
0x1800c1e5c  jz      short loc_1800C1E9A
0x1800c1e5e  mov     r8, [rsp+r14*8+6A0h+var_658]
0x1800c1e63  mov     r9, rsi
0x1800c1e66  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1800c1e6b  mov     ebx, eax
0x1800c1e6d  inc     edi
0x1800c1e6f  test    ebx, ebx
0x1800c1e71  jns     short loc_1800C1DF4
0x1800c1e73  test    ebx, ebx
0x1800c1e75  js      loc_1800C1F2F
0x1800c1e7b  cmp     [rsi], r12
0x1800c1e7e  jnz     loc_1800C1F2F
0x1800c1e84  mov     [rsp+6A0h+pv], r12
0x1800c1e89  test    r15, r15
0x1800c1e8c  jnz     short loc_1800C1EA4
0x1800c1e8e  lea     rcx, [rsp+6A0h+pv]; this
0x1800c1e93  call    ?GetCallingProcessAppId@CallerIdentity@@YAJPEAPEAG@Z; CallerIdentity::GetCallingProcessAppId(ushort * *)
0x1800c1e98  jmp     short loc_1800C1EB1
0x1800c1e9a  mov     ebx, 80070005h
0x1800c1e9f  jmp     loc_1800C1F2F
0x1800c1ea4  lea     rdx, [rsp+6A0h+pv]; void *
0x1800c1ea9  mov     rcx, r15; ProcessHandle
0x1800c1eac  call    ?GetProcessAppId@CallerIdentity@@YAJPEAXPEAPEAG@Z; CallerIdentity::GetProcessAppId(void *,ushort * *)
0x1800c1eb1  lea     r8, aSS_2; "%s%s"
0x1800c1eb8  mov     edx, 104h; unsigned __int64
0x1800c1ebd  lea     rcx, [rsp+6A0h+var_660]; unsigned __int16 *
0x1800c1ec2  test    eax, eax
0x1800c1ec4  js      short loc_1800C1F02
0x1800c1ec6  mov     rdi, [rsp+6A0h+pv]
0x1800c1ecb  lea     r9, aAppid; "APPID:"
0x1800c1ed2  mov     qword ptr [rsp+6A0h+bIgnoreCase], rdi
0x1800c1ed7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800c1edc  mov     ebx, eax
0x1800c1ede  test    eax, eax
0x1800c1ee0  js      short loc_1800C1EF1
0x1800c1ee2  mov     r9, rsi
0x1800c1ee5  lea     r8, [rsp+6A0h+var_660]
0x1800c1eea  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1800c1eef  mov     ebx, eax
0x1800c1ef1  mov     rcx, rdi; pv
0x1800c1ef4  call    cs:__imp_CoTaskMemFree
0x1800c1efb  nop     dword ptr [rax+rax+00h]
0x1800c1f00  jmp     short loc_1800C1F2F
0x1800c1f02  lea     rax, [rbp+5A0h+ExeName]
0x1800c1f09  lea     r9, aImagename; "IMAGENAME:"
0x1800c1f10  mov     qword ptr [rsp+6A0h+bIgnoreCase], rax
0x1800c1f15  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800c1f1a  mov     ebx, eax
0x1800c1f1c  test    eax, eax
0x1800c1f1e  js      short loc_1800C1F2F
0x1800c1f20  mov     r9, rsi
0x1800c1f23  lea     r8, [rsp+6A0h+var_660]
0x1800c1f28  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1800c1f2d  mov     ebx, eax
0x1800c1f2f  mov     eax, ebx
0x1800c1f31  mov     rcx, [rbp+5A0h+var_30]
0x1800c1f38  xor     rcx, rsp; StackCookie
0x1800c1f3b  call    __security_check_cookie
0x1800c1f40  lea     r11, [rsp+6A0h+var_20]
0x1800c1f48  mov     rbx, [r11+40h]
0x1800c1f4c  mov     rsi, [r11+48h]
0x1800c1f50  mov     rsp, r11
0x1800c1f53  pop     r15
0x1800c1f55  pop     r14
0x1800c1f57  pop     r12
0x1800c1f59  pop     rdi
0x1800c1f5a  pop     rbp
0x1800c1f5b  retn
```
