# ChangeDefaultHost(int)

- ea: `0x18000494c`
- end: `0x180004c31`
- name: `?ChangeDefaultHost@@YAJH@Z`
- size: `741`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004c40`

## callees

- `0x18000494c`
- `0x180004c50`
- `0x180004d28`
- `0x18000d1c0`

## import_xrefs

- `msvcrt!sprintf_s` at `0x1800049f7`
- `msvcrt!sprintf_s` at `0x180004a52`
- `msvcrt!sprintf_s` at `0x180004a8d`
- `msvcrt!sprintf_s` at `0x1800049f7`
- `msvcrt!sprintf_s` at `0x180004a52`
- `msvcrt!sprintf_s` at `0x180004a8d`
- `msvcrt!strcat_s` at `0x180004a66`
- `msvcrt!strcat_s` at `0x180004a66`
- `USER32!LoadStringA` at `0x180004acf`
- `USER32!LoadStringA` at `0x180004b07`
- `USER32!LoadStringA` at `0x180004b4c`
- `USER32!LoadStringA` at `0x180004b79`
- `USER32!LoadStringA` at `0x180004acf`
- `USER32!LoadStringA` at `0x180004b07`
- `USER32!LoadStringA` at `0x180004b4c`
- `USER32!LoadStringA` at `0x180004b79`
- `KERNEL32!GetLastError` at `0x180004a16`
- `KERNEL32!GetLastError` at `0x180004a16`
- `KERNEL32!GetWindowsDirectoryA` at `0x180004a0c`
- `KERNEL32!GetWindowsDirectoryA` at `0x180004a0c`
- `ADVAPI32!RegEnumKeyExA` at `0x180004bd2`
- `ADVAPI32!RegEnumKeyExA` at `0x180004bd2`

## string_xrefs

- `0x180004a58`: `\Command`
- `0x1800049dd`: `%SystemRoot%\System32`
- `0x1800049fd`: `%SystemRoot%\System32`

## pseudocode

```c
signed int __fastcall ChangeDefaultHost(int a1)
{
  signed int result; // eax
  CHAR *v3; // r9
  bool v4; // cc
  void *v5; // rsp
  void *v6; // rsp
  int StringA; // eax
  char *v8; // r15
  char *v9; // r12
  void *v10; // rsp
  void *v11; // rsp
  DWORD v12; // edi
  CHAR v13[1984]; // [rsp+20h] [rbp-1000h] BYREF
  CHAR v14[1984]; // [rsp+820h] [rbp-800h] BYREF
  DWORD cchName[4]; // [rsp+1020h] [rbp+0h] BYREF
  CHAR Destination[272]; // [rsp+1030h] [rbp+10h] BYREF
  char v17[272]; // [rsp+1140h] [rbp+120h] BYREF
  char Buffer[272]; // [rsp+1250h] [rbp+230h] BYREF
  CHAR Name[272]; // [rsp+1360h] [rbp+340h] BYREF

  cchName[0] = 0;
  result = TaRegSetEXPAND_SZ(HKEY_CLASSES_ROOT, ".wsf", 0, (const BYTE *)"WSFFile");
  if ( result < 0 )
    return result;
  result = TaRegSetEXPAND_SZ(HKEY_CLASSES_ROOT, "WSFFile", 0, (const BYTE *)"Windows Script Host Script");
  if ( result < 0 )
    return result;
  if ( Global::g_fWindowsNT )
  {
    sprintf_s(Buffer, 0x104u, "%s\\%s \"%%1\" %%*", "%SystemRoot%\\System32", "WScript.exe");
    v3 = "%SystemRoot%\\System32";
  }
  else
  {
    if ( !GetWindowsDirectoryA(Destination, 0x104u) )
    {
      result = GetLastError();
      v4 = result <= 0;
LABEL_7:
      if ( !v4 )
        return (unsigned __int16)result | 0x80070000;
      return result;
    }
    sprintf_s(Buffer, 0x104u, "%s\\%s \"%%1\" %%*", Destination, "WScript.exe");
    strcat_s(Destination, 0x104u, "\\Command");
    v3 = Destination;
  }
  sprintf_s(v17, 0x104u, "%s\\%s \"%%1\" %%*", v3, "CScript.exe");
  if ( a1 == 67 )
  {
    v10 = alloca(2048);
    v14[LoadStringA(Global::g_hResource, 4512 - Global::g_fWindowsNT, v14, 2048)] = 0;
    v11 = alloca(2048);
    StringA = LoadStringA(Global::g_hResource, 0x119Eu, v13, 2048);
    v8 = v17;
    v9 = Buffer;
  }
  else
  {
    if ( a1 != 87 )
      return -2147024809;
    v5 = alloca(2048);
    v14[LoadStringA(Global::g_hResource, 0x119Eu, v14, 2048)] = 0;
    v6 = alloca(2048);
    StringA = LoadStringA(Global::g_hResource, 4512 - Global::g_fWindowsNT, v13, 2048);
    v8 = Buffer;
    v9 = v17;
  }
  v12 = 0;
  v13[StringA] = 0;
  while ( 1 )
  {
    cchName[0] = 260;
    result = RegEnumKeyExA(HKEY_CLASSES_ROOT, v12, Name, cchName, 0, 0, 0, 0);
    if ( result == 259 )
      return 0;
    v4 = result <= 0;
    if ( result )
      goto LABEL_7;
    if ( Name[0] == 46 )
      change_host(Name, v14, v8, v13, v9);
    ++v12;
  }
}

```

## disassembly

```asm
0x18000494c  push    rbp
0x18000494e  push    rbx
0x18000494f  push    rsi
0x180004950  push    rdi
0x180004951  push    r12
0x180004953  push    r14
0x180004955  push    r15
0x180004957  sub     rsp, 4A0h
0x18000495e  lea     rbp, [rsp+40h]
0x180004963  mov     rax, cs:__security_cookie
0x18000496a  xor     rax, rbp
0x18000496d  mov     [rbp+490h+var_40], rax
0x180004974  mov     edi, ecx
0x180004976  mov     [rbp+490h+cchName], 0
0x18000497d  mov     rbx, 0FFFFFFFF80000000h
0x180004984  lea     r9, aWsffile; "WSFFile"
0x18000498b  mov     rcx, rbx; HKEY
0x18000498e  lea     rdx, aWsf_1; ".wsf"
0x180004995  xor     r8d, r8d; char *
0x180004998  call    ?TaRegSetEXPAND_SZ@@YAJPEAUHKEY__@@PEBD11@Z; TaRegSetEXPAND_SZ(HKEY__ *,char const *,char const *,char const *)
0x18000499d  test    eax, eax
0x18000499f  js      loc_180004C10
0x1800049a5  lea     r9, aWindowsScriptH; "Windows Script Host Script"
0x1800049ac  xor     r8d, r8d; char *
0x1800049af  lea     rdx, aWsffile; "WSFFile"
0x1800049b6  mov     rcx, rbx; HKEY
0x1800049b9  call    ?TaRegSetEXPAND_SZ@@YAJPEAUHKEY__@@PEBD11@Z; TaRegSetEXPAND_SZ(HKEY__ *,char const *,char const *,char const *)
0x1800049be  test    eax, eax
0x1800049c0  js      loc_180004C10
0x1800049c6  cmp     cs:?g_fWindowsNT@Global@@2_NA, 0; bool Global::g_fWindowsNT
0x1800049cd  mov     ebx, 104h
0x1800049d2  jz      short loc_180004A06
0x1800049d4  lea     rax, aWscriptExe; "WScript.exe"
0x1800049db  mov     edx, ebx; BufferCount
0x1800049dd  lea     r9, aSystemrootSyst_0; "%SystemRoot%\\System32"
0x1800049e4  mov     [rsp+4D0h+var_4B0], rax
0x1800049e9  lea     r8, aSS1; "%s\\%s \"%%1\" %%*"
0x1800049f0  lea     rcx, [rbp+490h+Buffer]; Buffer
0x1800049f7  call    cs:__imp_sprintf_s
0x1800049fd  lea     r9, aSystemrootSyst_0; "%SystemRoot%\\System32"
0x180004a04  jmp     short loc_180004A70
0x180004a06  mov     edx, ebx; uSize
0x180004a08  lea     rcx, [rbp+490h+Destination]; lpBuffer
0x180004a0c  call    cs:__imp_GetWindowsDirectoryA
0x180004a12  test    eax, eax
0x180004a14  jnz     short loc_180004A31
0x180004a16  call    cs:__imp_GetLastError
0x180004a1c  test    eax, eax
0x180004a1e  jle     loc_180004C10
0x180004a24  movzx   eax, ax
0x180004a27  or      eax, 80070000h
0x180004a2c  jmp     loc_180004C10
0x180004a31  lea     rax, aWscriptExe; "WScript.exe"
0x180004a38  mov     rdx, rbx; BufferCount
0x180004a3b  lea     r9, [rbp+490h+Destination]
0x180004a3f  mov     [rsp+4D0h+var_4B0], rax
0x180004a44  lea     r8, aSS1; "%s\\%s \"%%1\" %%*"
0x180004a4b  lea     rcx, [rbp+490h+Buffer]; Buffer
0x180004a52  call    cs:__imp_sprintf_s
0x180004a58  lea     r8, Source; "\\Command"
0x180004a5f  mov     rdx, rbx; SizeInBytes
0x180004a62  lea     rcx, [rbp+490h+Destination]; Destination
0x180004a66  call    cs:__imp_strcat_s
0x180004a6c  lea     r9, [rbp+490h+Destination]
0x180004a70  lea     rax, aCscriptExe; "CScript.exe"
0x180004a77  mov     rdx, rbx; BufferCount
0x180004a7a  lea     r8, aSS1; "%s\\%s \"%%1\" %%*"
0x180004a81  mov     [rsp+4D0h+var_4B0], rax
0x180004a86  lea     rcx, [rbp+490h+var_370]; Buffer
0x180004a8d  call    cs:__imp_sprintf_s
0x180004a93  cmp     edi, 43h ; 'C'
0x180004a96  jz      loc_180004B1D
0x180004a9c  cmp     edi, 57h ; 'W'
0x180004a9f  jz      short loc_180004AAB
0x180004aa1  mov     eax, 80070057h
0x180004aa6  jmp     loc_180004C10
0x180004aab  mov     eax, [rsp+4D0h+var_4D0]
0x180004aae  mov     edi, 800h
0x180004ab3  sub     rsp, rdi
0x180004ab6  lea     rsi, [rsp+0CD0h+var_C90]
0x180004abb  mov     eax, [rsi]
0x180004abd  mov     rcx, cs:?g_hResource@Global@@2PEAUHINSTANCE__@@EA; hInstance
0x180004ac4  mov     r9d, edi; cchBufferMax
0x180004ac7  mov     r8, rsi; lpBuffer
0x180004aca  mov     edx, 119Eh; uID
0x180004acf  call    cs:__imp_LoadStringA
0x180004ad5  movsxd  rcx, eax
0x180004ad8  mov     eax, [rsp+0CD0h+var_CD0]
0x180004adb  mov     byte ptr [rcx+rsi], 0
0x180004adf  sub     rsp, rdi
0x180004ae2  lea     r14, [rsp+14D0h+var_1490]
0x180004ae7  mov     eax, [r14]
0x180004aea  mov     al, cs:?g_fWindowsNT@Global@@2_NA; bool Global::g_fWindowsNT
0x180004af0  mov     r9d, edi; cchBufferMax
0x180004af3  mov     rcx, cs:?g_hResource@Global@@2PEAUHINSTANCE__@@EA; hInstance
0x180004afa  neg     al
0x180004afc  mov     r8, r14; lpBuffer
0x180004aff  sbb     edx, edx
0x180004b01  add     edx, 11A0h; uID
0x180004b07  call    cs:__imp_LoadStringA
0x180004b0d  lea     r15, [rbp+490h+Buffer]
0x180004b14  lea     r12, [rbp+490h+var_370]
0x180004b1b  jmp     short loc_180004B8D
0x180004b1d  mov     eax, [rsp+4D0h+var_4D0]
0x180004b20  mov     edi, 800h
0x180004b25  sub     rsp, rdi
0x180004b28  lea     rsi, [rsp+0CD0h+var_C90]
0x180004b2d  mov     eax, [rsi]
0x180004b2f  mov     al, cs:?g_fWindowsNT@Global@@2_NA; bool Global::g_fWindowsNT
0x180004b35  mov     r9d, edi; cchBufferMax
0x180004b38  mov     rcx, cs:?g_hResource@Global@@2PEAUHINSTANCE__@@EA; hInstance
0x180004b3f  neg     al
0x180004b41  mov     r8, rsi; lpBuffer
0x180004b44  sbb     edx, edx
0x180004b46  add     edx, 11A0h; uID
0x180004b4c  call    cs:__imp_LoadStringA
0x180004b52  movsxd  rcx, eax
0x180004b55  mov     eax, [rsp+0CD0h+var_CD0]
0x180004b58  mov     byte ptr [rcx+rsi], 0
0x180004b5c  sub     rsp, rdi
0x180004b5f  lea     r14, [rsp+14D0h+var_1490]
0x180004b64  mov     eax, [r14]
0x180004b67  mov     rcx, cs:?g_hResource@Global@@2PEAUHINSTANCE__@@EA; hInstance
0x180004b6e  mov     r9d, edi; cchBufferMax
0x180004b71  mov     r8, r14; lpBuffer
0x180004b74  mov     edx, 119Eh; uID
0x180004b79  call    cs:__imp_LoadStringA
0x180004b7f  lea     r15, [rbp+490h+var_370]
0x180004b86  lea     r12, [rbp+490h+Buffer]
0x180004b8d  movsxd  rcx, eax
0x180004b90  xor     edi, edi
0x180004b92  mov     byte ptr [rcx+r14], 0
0x180004b97  mov     [rsp+14D0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180004ba0  lea     r9, [rbp+490h+cchName]; lpcchName
0x180004ba4  mov     [rsp+14D0h+lpcchClass], 0; lpcchClass
0x180004bad  lea     r8, [rbp+490h+Name]; lpName
0x180004bb4  mov     [rsp+14D0h+lpClass], 0; lpClass
0x180004bbd  mov     edx, edi; dwIndex
0x180004bbf  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180004bc6  mov     [rsp+14D0h+lpReserved], 0; lpReserved
0x180004bcf  mov     [rbp+490h+cchName], ebx
0x180004bd2  call    cs:__imp_RegEnumKeyExA
0x180004bd8  cmp     eax, 103h
0x180004bdd  jz      short loc_180004C0E
0x180004bdf  test    eax, eax
0x180004be1  jnz     loc_180004A1E
0x180004be7  cmp     [rbp+490h+Name], 2Eh ; '.'
0x180004bee  jnz     short loc_180004C0A
0x180004bf0  mov     r9, r14; char *
0x180004bf3  mov     [rsp+14D0h+lpReserved], r12; char *
0x180004bf8  mov     r8, r15; char *
0x180004bfb  lea     rcx, [rbp+490h+Name]; String2
0x180004c02  mov     rdx, rsi; char *
0x180004c05  call    change_host
0x180004c0a  inc     edi
0x180004c0c  jmp     short loc_180004B97
0x180004c0e  xor     eax, eax
0x180004c10  mov     rcx, [rbp+490h+var_40]
0x180004c17  xor     rcx, rbp; StackCookie
0x180004c1a  call    __security_check_cookie
0x180004c1f  lea     rsp, [rbp+460h]
0x180004c26  pop     r15
0x180004c28  pop     r14
0x180004c2a  pop     r12
0x180004c2c  pop     rdi
0x180004c2d  pop     rsi
0x180004c2e  pop     rbx
0x180004c2f  pop     rbp
0x180004c30  retn
```
