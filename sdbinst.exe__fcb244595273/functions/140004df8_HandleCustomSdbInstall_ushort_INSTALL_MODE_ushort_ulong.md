# HandleCustomSdbInstall(ushort *,_INSTALL_MODE,ushort *,ulong)

- ea: `0x140004df8`
- end: `0x14000549c`
- name: `?HandleCustomSdbInstall@@YAHPEAGW4_INSTALL_MODE@@0K@Z`
- size: `1700`
- prototype: `__int64 __fastcall(const WCHAR *, unsigned int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140008500`

## callees

- `0x140001e68`
- `0x140002206`
- `0x1400045e0`
- `0x140004694`
- `0x1400046f4`
- `0x140004df8`
- `0x140005988`
- `0x140006238`
- `0x140006480`
- `0x140007024`
- `0x1400075a8`
- `0x14000792c`
- `0x140012ca8`
- `0x140013898`
- `0x140014380`
- `0x14001443c`
- `0x140014574`
- `0x140016198`
- `0x140017ef8`
- `0x140018514`
- `0x14002e3e2`
- `0x14002e420`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x140005089`
- `ADVAPI32!RegCreateKeyExW` at `0x1400050f9`
- `ADVAPI32!RegCreateKeyExW` at `0x140005089`
- `ADVAPI32!RegCreateKeyExW` at `0x1400050f9`
- `ADVAPI32!RegCloseKey` at `0x140004f53`
- `ADVAPI32!RegCloseKey` at `0x1400050bd`
- `ADVAPI32!RegCloseKey` at `0x140005111`
- `ADVAPI32!RegCloseKey` at `0x140004f53`
- `ADVAPI32!RegCloseKey` at `0x1400050bd`
- `ADVAPI32!RegCloseKey` at `0x140005111`
- `KERNEL32!SetFileAttributesW` at `0x1400053bf`
- `KERNEL32!SetFileAttributesW` at `0x140005471`
- `KERNEL32!SetFileAttributesW` at `0x1400053bf`
- `KERNEL32!SetFileAttributesW` at `0x140005471`
- `KERNEL32!DeleteFileW` at `0x1400053db`
- `KERNEL32!DeleteFileW` at `0x14000547a`
- `KERNEL32!DeleteFileW` at `0x1400053db`
- `KERNEL32!DeleteFileW` at `0x14000547a`
- `KERNEL32!CopyFileW` at `0x1400053a0`
- `KERNEL32!CopyFileW` at `0x1400053a0`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140004e5e`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140004e5e`
- `msvcrt!wcsrchr` at `0x140004ea4`
- `msvcrt!wcsrchr` at `0x140004f2c`
- `msvcrt!wcsrchr` at `0x140004ea4`
- `msvcrt!wcsrchr` at `0x140004f2c`
- `ntdll!RtlFreeUnicodeString` at `0x140005041`
- `ntdll!RtlFreeUnicodeString` at `0x140005041`
- `ntdll!RtlStringFromGUID` at `0x140004fd9`
- `ntdll!RtlStringFromGUID` at `0x140004fd9`

## string_xrefs

- `0x1400050d2`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Custom`
- `0x140005103`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Custom`
- `0x140005061`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`
- `0x1400050a2`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`

## pseudocode

```c
__int64 __fastcall HandleCustomSdbInstall(const WCHAR *a1, unsigned int a2, unsigned __int16 *a3)
{
  unsigned __int64 v6; // rbx
  wchar_t *v7; // rax
  _WORD *v8; // rax
  __int64 v9; // r12
  _WORD *v10; // r8
  __int64 v11; // rcx
  __int64 v12; // rdx
  _WORD *v13; // rcx
  wchar_t *v14; // rax
  unsigned int v15; // esi
  struct _DB *v17; // r14
  __int64 Length; // rdi
  __int64 v19; // rdx
  __int64 v20; // rcx
  unsigned __int64 v21; // rdi
  __int64 v22; // rdx
  LSTATUS v23; // eax
  const WCHAR *v24; // rdx
  __int64 v25; // rax
  unsigned int v26; // r9d
  unsigned __int16 *v27; // rcx
  __int64 v28; // rdx
  unsigned __int16 *v29; // rax
  unsigned __int16 *v30; // rcx
  unsigned int NextTag; // eax
  unsigned int v32; // r12d
  unsigned int v33; // eax
  const WCHAR *StringTagPtr; // rax
  unsigned int v35; // edi
  unsigned int v36; // eax
  unsigned int v37; // r12d
  unsigned int v38; // eax
  const WCHAR *v39; // rax
  unsigned int v40; // edi
  unsigned int FirstTag; // [rsp+50h] [rbp-B0h]
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  struct _FILETIME v43; // [rsp+60h] [rbp-A0h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+68h] [rbp-98h] BYREF
  _UNICODE_STRING GuidString; // [rsp+70h] [rbp-90h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+80h] [rbp-80h]
  GUID v47; // [rsp+90h] [rbp-70h] BYREF
  GUID Guid; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v49[256]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v50[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  _BYTE v51[528]; // [rsp+4C0h] [rbp+3C0h] BYREF

  lpExistingFileName = a1;
  hKey = 0;
  SystemTimeAsFileTime = 0;
  v43 = 0;
  Guid = 0;
  GuidString = 0;
  if ( a2 )
  {
    v6 = (unsigned __int64)v43;
  }
  else
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v6 = (unsigned __int64)SystemTimeAsFileTime;
    v43 = SystemTimeAsFileTime;
  }
  if ( !a1 || !a3 )
    goto LABEL_22;
  memset_0(v49, 0, sizeof(v49));
  v7 = wcsrchr(a1, 0x5Cu);
  if ( !v7 )
    goto LABEL_21;
  v8 = v7 + 1;
  if ( !v8 )
    goto LABEL_21;
  v9 = 2147483646;
  v10 = v51;
  v11 = 2147483646;
  v12 = 260;
  do
  {
    if ( !v11 )
      break;
    if ( !*v8 )
      break;
    *v10++ = *v8++;
    --v11;
    --v12;
  }
  while ( v12 );
  v13 = v10 - 1;
  if ( v12 )
    v13 = v10;
  *v13 = 0;
  if ( !v12 )
    goto LABEL_22;
  if ( !a2 )
  {
    if ( !(unsigned int)GetInstallPathForSdb(a1, a3, (unsigned int)v10) )
      goto LABEL_22;
    goto LABEL_27;
  }
  if ( a2 == 2 )
  {
    v14 = wcsrchr(a3, 0x5Cu);
    if ( v14 && v14 != (wchar_t *)-2LL )
      goto LABEL_27;
LABEL_21:
    PrintMessage(0x3E9u);
    goto LABEL_22;
  }
  if ( (int)StringCchCopyW(a3, 0x104u, a1) < 0 )
    goto LABEL_22;
LABEL_27:
  v17 = 0;
  if ( !(unsigned int)GetGuid(a1, &Guid) )
  {
LABEL_56:
    v15 = 0;
    if ( !a2 )
      goto LABEL_102;
    if ( v17 )
    {
      SdbCloseDatabase(v17);
      v17 = 0;
    }
LABEL_101:
    SetFileAttributesW(a3, 0x80u);
    DeleteFileW(a3);
LABEL_102:
    if ( !v17 )
      goto LABEL_23;
    goto LABEL_103;
  }
  v47 = Guid;
  if ( (unsigned int)SdbIsStandardDatabase(&v47) )
  {
    PrintMessage(0x3EDu);
    goto LABEL_56;
  }
  if ( RtlStringFromGUID(&Guid, &GuidString) < 0 )
  {
    PrintMessage(0x407u);
    goto LABEL_56;
  }
  if ( (GuidString.Length & 0xFFFEu) > 0x206 )
  {
    PrintMessage(0x409u);
    goto LABEL_56;
  }
  Length = GuidString.Length;
  memcpy_0(v50, GuidString.Buffer, GuidString.Length);
  v21 = Length & 0xFFFFFFFFFFFFFFFEuLL;
  if ( v21 >= 0x208 )
    _report_rangecheckfailure(v20, v19);
  *(unsigned __int16 *)((char *)v50 + v21) = 0;
  RtlFreeUnicodeString(&GuidString);
  if ( !a2 )
  {
    v23 = RegCreateKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags",
            0,
            0,
            0,
            0x101u,
            0,
            &hKey,
            0);
    if ( v23 )
    {
      if ( v23 == 5 )
      {
        PrintMessage(0x3F0u);
        goto LABEL_22;
      }
      v24 = L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags";
LABEL_40:
      PrintMessage(0x3F1u, v24);
      goto LABEL_22;
    }
    RegCloseKey(hKey);
    hKey = 0;
    if ( RegCreateKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\Custom",
           0,
           0,
           0,
           0x101u,
           0,
           &hKey,
           0) )
    {
      v24 = L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\Custom";
      goto LABEL_40;
    }
    RegCloseKey(hKey);
    hKey = 0;
  }
  v25 = SdbOpenDatabaseEx(a1, v22, 0);
  v17 = (struct _DB *)v25;
  if ( !v25 )
  {
    PrintMessage(0x3EAu, a1);
    goto LABEL_56;
  }
  FirstTag = SdbFindFirstTag(v25, 0, 28673);
  if ( !FirstTag )
  {
    PrintMessage(0x3EBu, a1);
    goto LABEL_56;
  }
  if ( !GetInternalNameFromPdb(a1, v17, v49, v26) )
  {
    v27 = (unsigned __int16 *)v51;
    v28 = 256;
    v29 = v49;
    do
    {
      if ( !v9 )
        break;
      if ( !*v27 )
        break;
      *v29++ = *v27++;
      --v9;
      --v28;
    }
    while ( v28 );
    v30 = v29 - 1;
    if ( v28 )
      v30 = v29;
    *v30 = 0;
    if ( !v28 )
      goto LABEL_56;
  }
  v15 = 1;
  NextTag = SdbFindFirstTag(v17, FirstTag, 28679);
  v32 = NextTag;
  do
  {
    if ( !NextTag )
      break;
    v33 = SdbFindFirstTag(v17, v32, 24577);
    if ( v33 )
    {
      StringTagPtr = (const WCHAR *)SdbGetStringTagPtr(v17, v33);
      if ( StringTagPtr )
      {
        if ( a2 )
        {
          if ( !(unsigned int)UninstallSdbEntry(StringTagPtr, v50, 0) )
            goto LABEL_103;
        }
        else if ( !(unsigned int)InstallSdbEntry(StringTagPtr, v50, v6, 0) )
        {
LABEL_68:
          v15 = 0;
          goto LABEL_102;
        }
      }
      else
      {
        v15 = 0;
        if ( a2 - 1 > 1 )
        {
LABEL_65:
          PrintMessage(0x3F3u);
          goto LABEL_103;
        }
      }
    }
    else
    {
      v15 = 0;
      if ( a2 - 1 > 1 )
      {
LABEL_62:
        PrintMessage(0x3F2u);
        goto LABEL_103;
      }
    }
    v35 = v32;
    NextTag = SdbFindNextTag(v17, FirstTag, v32);
    v32 = NextTag;
  }
  while ( NextTag != v35 );
  v36 = SdbFindFirstTag(v17, FirstTag, 28683);
  v37 = v36;
  do
  {
    if ( !v36 )
      break;
    v38 = SdbFindFirstTag(v17, v37, 24577);
    if ( v38 )
    {
      v39 = (const WCHAR *)SdbGetStringTagPtr(v17, v38);
      if ( v39 )
      {
        if ( a2 )
        {
          if ( !(unsigned int)UninstallSdbEntry(v39, v50, 1) )
            goto LABEL_103;
        }
        else if ( !(unsigned int)InstallSdbEntry(v39, v50, v6, 1) )
        {
          goto LABEL_68;
        }
      }
      else
      {
        v15 = 0;
        if ( a2 - 1 > 1 )
          goto LABEL_65;
      }
    }
    else
    {
      v15 = 0;
      if ( a2 - 1 > 1 )
        goto LABEL_62;
    }
    v40 = v37;
    v36 = SdbFindNextTag(v17, FirstTag, v37);
    v37 = v36;
  }
  while ( v36 != v40 );
  if ( (unsigned int)ProcessMSIPackages(v17, FirstTag, v50, v6, a2) )
  {
    SdbCloseDatabase(v17);
    if ( a2 )
    {
      if ( !SetFileAttributesW(a3, 0x80u) )
      {
        PrintMessage(0x41Bu, a3);
        v15 = 0;
      }
      if ( !DeleteFileW(a3) )
      {
        PrintMessage(0x3FAu, a3);
        v15 = 0;
      }
    }
    else if ( !CopyFileW(lpExistingFileName, a3, 1) )
    {
      PrintMessage(0x3F9u, a3);
      goto LABEL_22;
    }
    UninstallationString(a2, a3, v50, v49);
    if ( a2 )
    {
      v17 = 0;
      if ( !(unsigned int)SdbUnregisterDatabase(&Guid) )
        PrintMessage(0x40Bu, v49);
      PrintMessage(0x3FCu, v49);
      goto LABEL_101;
    }
    if ( (unsigned int)SdbRegisterDatabaseEx(a3) )
    {
      PrintMessage(0x3FBu, v49);
      goto LABEL_23;
    }
    PrintMessage(0x40Au, v49);
LABEL_22:
    v15 = 0;
    goto LABEL_23;
  }
  v15 = 0;
LABEL_103:
  SdbCloseDatabase(v17);
LABEL_23:
  if ( hKey )
    RegCloseKey(hKey);
  return v15;
}

```

## disassembly

```asm
0x140004df8  mov     [rsp-8+arg_8], rbx
0x140004dfd  push    rbp
0x140004dfe  push    rsi
0x140004dff  push    rdi
0x140004e00  push    r12
0x140004e02  push    r13
0x140004e04  push    r14
0x140004e06  push    r15
0x140004e08  lea     rbp, [rsp-5E0h]
0x140004e10  sub     rsp, 6E0h
0x140004e17  mov     rax, cs:__security_cookie
0x140004e1e  xor     rax, rsp
0x140004e21  mov     [rbp+610h+var_40], rax
0x140004e28  xor     edi, edi
0x140004e2a  mov     [rbp+610h+lpExistingFileName], rcx
0x140004e2e  mov     [rsp+710h+hKey], rdi
0x140004e33  xorps   xmm0, xmm0
0x140004e36  mov     qword ptr [rsp+710h+SystemTimeAsFileTime.dwLowDateTime], rdi
0x140004e3b  xorps   xmm1, xmm1
0x140004e3e  mov     [rsp+710h+var_6B0], rdi
0x140004e43  mov     r15, r8
0x140004e46  mov     r13d, edx
0x140004e49  mov     rsi, rcx
0x140004e4c  movups  xmmword ptr [rbp+610h+Guid.Data1], xmm0
0x140004e50  movups  xmmword ptr [rsp+710h+GuidString.Length], xmm1
0x140004e55  test    edx, edx
0x140004e57  jnz     short loc_140004E70
0x140004e59  lea     rcx, [rsp+710h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140004e5e  call    cs:__imp_GetSystemTimeAsFileTime
0x140004e64  mov     rbx, qword ptr [rsp+710h+SystemTimeAsFileTime.dwLowDateTime]
0x140004e69  mov     [rsp+710h+var_6B0], rbx
0x140004e6e  jmp     short loc_140004E75
0x140004e70  mov     rbx, [rsp+710h+var_6B0]
0x140004e75  test    rsi, rsi
0x140004e78  jz      loc_140004F47
0x140004e7e  test    r15, r15
0x140004e81  jz      loc_140004F47
0x140004e87  xor     edx, edx; Val
0x140004e89  lea     rcx, [rbp+610h+var_660]; void *
0x140004e8d  mov     r8d, 200h; Size
0x140004e93  call    memset_0
0x140004e98  mov     r14d, 5Ch ; '\'
0x140004e9e  mov     rcx, rsi; Str
0x140004ea1  mov     edx, r14d; Ch
0x140004ea4  call    cs:__imp_wcsrchr
0x140004eaa  test    rax, rax
0x140004ead  jz      loc_140004F3D
0x140004eb3  add     rax, 2
0x140004eb7  jz      loc_140004F3D
0x140004ebd  mov     r12d, 7FFFFFFEh
0x140004ec3  lea     r8, [rbp+610h+var_250]
0x140004eca  mov     r10d, 104h
0x140004ed0  mov     ecx, r12d
0x140004ed3  mov     edx, r10d
0x140004ed6  test    rcx, rcx
0x140004ed9  jz      short loc_140004EFA
0x140004edb  movzx   r9d, word ptr [rax]
0x140004edf  test    r9w, r9w
0x140004ee3  jz      short loc_140004EFA
0x140004ee5  mov     [r8], r9w
0x140004ee9  add     rax, 2
0x140004eed  add     r8, 2; unsigned int
0x140004ef1  dec     rcx
0x140004ef4  sub     rdx, 1
0x140004ef8  jnz     short loc_140004ED6
0x140004efa  test    rdx, rdx
0x140004efd  lea     rcx, [r8-2]
0x140004f01  cmovnz  rcx, r8
0x140004f05  mov     [rcx], di
0x140004f08  jz      short loc_140004F47
0x140004f0a  test    r13d, r13d
0x140004f0d  jnz     short loc_140004F20
0x140004f0f  mov     rdx, r15; unsigned __int16 *
0x140004f12  mov     rcx, rsi; unsigned __int16 *
0x140004f15  call    ?GetInstallPathForSdb@@YAHPEBGPEAGK@Z; GetInstallPathForSdb(ushort const *,ushort *,ulong)
0x140004f1a  test    eax, eax
0x140004f1c  jnz     short loc_140004F94
0x140004f1e  jmp     short loc_140004F47
0x140004f20  mov     rcx, r15; unsigned __int16 *
0x140004f23  cmp     r13d, 2
0x140004f27  jnz     short loc_140004F85
0x140004f29  mov     edx, r14d; Ch
0x140004f2c  call    cs:__imp_wcsrchr
0x140004f32  test    rax, rax
0x140004f35  jz      short loc_140004F3D
0x140004f37  add     rax, 2
0x140004f3b  jnz     short loc_140004F94
0x140004f3d  mov     ecx, 3E9h; unsigned int
0x140004f42  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140004f47  mov     esi, edi
0x140004f49  mov     rcx, [rsp+710h+hKey]; hKey
0x140004f4e  test    rcx, rcx
0x140004f51  jz      short loc_140004F59
0x140004f53  call    cs:__imp_RegCloseKey
0x140004f59  mov     eax, esi
0x140004f5b  mov     rcx, [rbp+610h+var_40]
0x140004f62  xor     rcx, rsp; StackCookie
0x140004f65  call    __security_check_cookie
0x140004f6a  mov     rbx, [rsp+710h+arg_8]
0x140004f72  add     rsp, 6E0h
0x140004f79  pop     r15
0x140004f7b  pop     r14
0x140004f7d  pop     r13
0x140004f7f  pop     r12
0x140004f81  pop     rdi
0x140004f82  pop     rsi
0x140004f83  pop     rbp
0x140004f84  retn
0x140004f85  mov     r8, rsi; unsigned __int16 *
0x140004f88  mov     rdx, r10; unsigned __int64
0x140004f8b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140004f90  test    eax, eax
0x140004f92  js      short loc_140004F47
0x140004f94  lea     rdx, [rbp+610h+Guid]; struct _GUID *
0x140004f98  mov     rcx, rsi; unsigned __int16 *
0x140004f9b  mov     r14, rdi
0x140004f9e  call    ?GetGuid@@YAHPEBGPEAU_GUID@@@Z; GetGuid(ushort const *,_GUID *)
0x140004fa3  test    eax, eax
0x140004fa5  jz      loc_1400051B4
0x140004fab  movaps  xmm0, xmmword ptr [rbp+610h+Guid.Data1]
0x140004faf  lea     rcx, [rbp+610h+var_680]
0x140004fb3  movdqa  [rbp+610h+var_680], xmm0
0x140004fb8  call    SdbIsStandardDatabase
0x140004fbd  test    eax, eax
0x140004fbf  jz      short loc_140004FD0
0x140004fc1  mov     ecx, 3EDh; unsigned int
0x140004fc6  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140004fcb  jmp     loc_1400051B4
0x140004fd0  lea     rdx, [rsp+710h+GuidString]; GuidString
0x140004fd5  lea     rcx, [rbp+610h+Guid]; Guid
0x140004fd9  call    cs:__imp_RtlStringFromGUID
0x140004fdf  test    eax, eax
0x140004fe1  jns     short loc_140004FEA
0x140004fe3  mov     ecx, 407h
0x140004fe8  jmp     short loc_140004FC6
0x140004fea  movzx   eax, [rsp+710h+GuidString.Length]
0x140004fef  mov     ecx, 0FFFEh
0x140004ff4  and     ax, cx
0x140004ff7  mov     ecx, 206h
0x140004ffc  cmp     ax, cx
0x140004fff  jbe     short loc_140005008
0x140005001  mov     ecx, 409h
0x140005006  jmp     short loc_140004FC6
0x140005008  movzx   edi, [rsp+710h+GuidString.Length]
0x14000500d  lea     rcx, [rbp+610h+var_460]; void *
0x140005014  mov     rdx, [rsp+710h+GuidString.Buffer]; Src
0x140005019  mov     r8d, edi; Size
0x14000501c  call    memcpy_0
0x140005021  and     rdi, 0FFFFFFFFFFFFFFFEh
0x140005025  cmp     rdi, 208h
0x14000502c  jnb     loc_140005496
0x140005032  xor     eax, eax
0x140005034  lea     rcx, [rsp+710h+GuidString]; UnicodeString
0x140005039  mov     [rbp+rdi+610h+var_460], ax
0x140005041  call    cs:__imp_RtlFreeUnicodeString
0x140005047  xor     edi, edi
0x140005049  test    r13d, r13d
0x14000504c  jnz     loc_14000511C
0x140005052  mov     [rsp+710h+lpdwDisposition], rdi; lpdwDisposition
0x140005057  lea     rax, [rsp+710h+hKey]
0x14000505c  mov     [rsp+710h+phkResult], rax; phkResult
0x140005061  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows NT\\Curren"...
0x140005068  mov     [rsp+710h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x14000506d  mov     r14d, 101h
0x140005073  mov     [rsp+710h+samDesired], r14d; samDesired
0x140005078  xor     r9d, r9d; lpClass
0x14000507b  xor     r8d, r8d; Reserved
0x14000507e  mov     [rsp+710h+dwOptions], edi; dwOptions
0x140005082  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140005089  call    cs:__imp_RegCreateKeyExW
0x14000508f  test    eax, eax
0x140005091  jz      short loc_1400050B8
0x140005093  cmp     eax, 5
0x140005096  jnz     short loc_1400050A2
0x140005098  mov     ecx, 3F0h
0x14000509d  jmp     loc_140004F42
0x1400050a2  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows NT\\Curren"...
0x1400050a9  mov     ecx, 3F1h; unsigned int
0x1400050ae  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x1400050b3  jmp     loc_140004F47
0x1400050b8  mov     rcx, [rsp+710h+hKey]; hKey
0x1400050bd  call    cs:__imp_RegCloseKey
0x1400050c3  mov     [rsp+710h+lpdwDisposition], rdi; lpdwDisposition
0x1400050c8  lea     rax, [rsp+710h+hKey]
0x1400050cd  mov     [rsp+710h+phkResult], rax; phkResult
0x1400050d2  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows NT\\Curren"...
0x1400050d9  mov     [rsp+710h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x1400050de  xor     r9d, r9d; lpClass
0x1400050e1  mov     [rsp+710h+samDesired], r14d; samDesired
0x1400050e6  xor     r8d, r8d; Reserved
0x1400050e9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400050f0  mov     [rsp+710h+dwOptions], edi; dwOptions
0x1400050f4  mov     [rsp+710h+hKey], rdi
0x1400050f9  call    cs:__imp_RegCreateKeyExW
0x1400050ff  test    eax, eax
0x140005101  jz      short loc_14000510C
0x140005103  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows NT\\Curren"...
0x14000510a  jmp     short loc_1400050A9
0x14000510c  mov     rcx, [rsp+710h+hKey]; hKey
0x140005111  call    cs:__imp_RegCloseKey
0x140005117  mov     [rsp+710h+hKey], rdi
0x14000511c  xor     r8d, r8d
0x14000511f  mov     rcx, rsi
0x140005122  call    SdbOpenDatabaseEx
0x140005127  mov     r14, rax
0x14000512a  test    rax, rax
0x14000512d  jnz     short loc_14000513E
0x14000512f  mov     ecx, 3EAh; unsigned int
0x140005134  mov     rdx, rsi
0x140005137  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x14000513c  jmp     short loc_1400051B4
0x14000513e  xor     edx, edx
0x140005140  mov     r8d, 7001h
0x140005146  mov     rcx, r14
0x140005149  call    SdbFindFirstTag
0x14000514e  mov     [rsp+710h+var_6C0], eax
0x140005152  test    eax, eax
0x140005154  jnz     short loc_14000515D
0x140005156  mov     ecx, 3EBh
0x14000515b  jmp     short loc_140005134
0x14000515d  lea     r8, [rbp+610h+var_660]; unsigned __int16 *
0x140005161  mov     rdx, r14; struct _DB *
0x140005164  mov     rcx, rsi; unsigned __int16 *
0x140005167  call    ?GetInternalNameFromPdb@@YAHPEBGPEAU_DB@@PEAGK@Z; GetInternalNameFromPdb(ushort const *,_DB *,ushort *,ulong)
0x14000516c  test    eax, eax
0x14000516e  jnz     short loc_1400051D8
0x140005170  lea     rcx, [rbp+610h+var_250]
0x140005177  mov     edx, 100h
0x14000517c  lea     rax, [rbp+610h+var_660]
0x140005180  test    r12, r12
0x140005183  jz      short loc_1400051A4
0x140005185  movzx   r8d, word ptr [rcx]
0x140005189  test    r8w, r8w
0x14000518d  jz      short loc_1400051A4
0x14000518f  mov     [rax], r8w
0x140005193  add     rcx, 2
0x140005197  add     rax, 2
0x14000519b  dec     r12
0x14000519e  sub     rdx, 1
0x1400051a2  jnz     short loc_140005180
0x1400051a4  test    rdx, rdx
0x1400051a7  lea     rcx, [rax-2]
0x1400051ab  cmovnz  rcx, rax
0x1400051af  mov     [rcx], di
0x1400051b2  jnz     short loc_1400051D8
0x1400051b4  mov     esi, edi
0x1400051b6  test    r13d, r13d
0x1400051b9  jz      loc_140005480
0x1400051bf  test    r14, r14
0x1400051c2  jz      loc_140005469
0x1400051c8  mov     rcx, r14
0x1400051cb  call    SdbCloseDatabase
0x1400051d0  mov     r14, rdi
0x1400051d3  jmp     loc_140005469
0x1400051d8  mov     edx, [rsp+710h+var_6C0]
0x1400051dc  mov     r8d, 7007h
0x1400051e2  mov     rcx, r14
0x1400051e5  mov     esi, 1
0x1400051ea  call    SdbFindFirstTag
0x1400051ef  mov     r12d, eax
0x1400051f2  jmp     loc_140005297
0x1400051f7  mov     r8d, 6001h
0x1400051fd  mov     edx, r12d
0x140005200  mov     rcx, r14
0x140005203  call    SdbFindFirstTag
0x140005208  test    eax, eax
0x14000520a  jnz     short loc_140005226
0x14000520c  lea     eax, [r13-1]
0x140005210  mov     esi, edi
0x140005212  cmp     eax, 1
0x140005215  jbe     short loc_14000527C
0x140005217  mov     ecx, 3F2h; unsigned int
0x14000521c  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140005221  jmp     loc_140005489
0x140005226  mov     edx, eax
0x140005228  mov     rcx, r14
0x14000522b  call    SdbGetStringTagPtr
0x140005230  test    rax, rax
0x140005233  jnz     short loc_140005247
0x140005235  lea     eax, [r13-1]
0x140005239  mov     esi, edi
0x14000523b  cmp     eax, 1
0x14000523e  jbe     short loc_14000527C
0x140005240  mov     ecx, 3F3h
0x140005245  jmp     short loc_14000521C
0x140005247  lea     rdx, [rbp+610h+var_460]; unsigned __int16 *
0x14000524e  mov     rcx, rax; lpSubKey
0x140005251  test    r13d, r13d
0x140005254  jnz     short loc_14000526C
0x140005256  xor     r9d, r9d; int
0x140005259  mov     r8, rbx; unsigned __int64
0x14000525c  call    ?InstallSdbEntry@@YAHPEBG0_KH@Z; InstallSdbEntry(ushort const *,ushort const *,unsigned __int64,int)
0x140005261  test    eax, eax
0x140005263  jnz     short loc_14000527C
0x140005265  mov     esi, edi
0x140005267  jmp     loc_140005480
0x14000526c  xor     r8d, r8d; int
0x14000526f  call    ?UninstallSdbEntry@@YAHPEBG0H@Z; UninstallSdbEntry(ushort const *,ushort const *,int)
0x140005274  test    eax, eax
0x140005276  jz      loc_140005489
  ... truncated ...
```
