# CSpRegistryIsolator::GenerateUniqueRegKeyName(HSTRING__ * *)

- ea: `0x1800107d8`
- end: `0x180010ac7`
- name: `?GenerateUniqueRegKeyName@CSpRegistryIsolator@@AEAAJPEAPEAUHSTRING__@@@Z`
- size: `751`
- prototype: `__int64 __fastcall(CSpRegistryIsolator *__hidden this, HSTRING *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800103e0`

## callees

- `0x1800107d8`
- `0x180010ad0`
- `0x180026508`
- `0x180026ae4`
- `0x180045938`
- `0x180079e30`
- `0x18007aae4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180010828`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180010828`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010a0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010a41`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010a70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010a0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010a41`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010a70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180010a26`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180010a26`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180010907`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180010907`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x1800108bc`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x1800108bc`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x1800108dd`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x1800108dd`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x180010935`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x180010965`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x180010935`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x180010965`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180010947`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180010977`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180010947`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180010977`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x180010891`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x180010891`

## string_xrefs

- `0x18001091d`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\tokenfilemanager.cpp`
- `0x180010a57`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\registryisolator.cpp`
- `0x180010a8f`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\registryisolator.cpp`

## pseudocode

```c
__int64 __fastcall CSpRegistryIsolator::GenerateUniqueRegKeyName(CSpRegistryIsolator *this, HSTRING *a2)
{
  DWORD ModuleFileNameW; // eax
  unsigned __int64 v4; // rdi
  __int64 v5; // rbx
  const char *v6; // r9
  __int64 v7; // rdx
  HRESULT Win32Error; // ebx
  __int64 v9; // rdx
  int dwFlags; // [rsp+20h] [rbp-E0h]
  DWORD pdwDataLen; // [rsp+30h] [rbp-D0h] BYREF
  HCRYPTHASH phHash; // [rsp+38h] [rbp-C8h] BYREF
  HCRYPTPROV phProv; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING string; // [rsp+48h] [rbp-B8h] BYREF
  BYTE pbData[16]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v17; // [rsp+60h] [rbp-A0h]
  WCHAR Filename[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR sourceString[264]; // [rsp+280h] [rbp+180h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4B8h] [rbp+3B8h]

  memset_0(Filename, 0, 0x20Au);
  ModuleFileNameW = GetModuleFileNameW(0, Filename, 0x104u);
  if ( !ModuleFileNameW || ModuleFileNameW == 260 )
  {
    Win32Error = SpHrFromLastWin32Error();
    if ( Win32Error < 0 )
    {
      v9 = 103;
      goto LABEL_36;
    }
    return (unsigned int)Win32Error;
  }
  v4 = -1;
  *(_OWORD *)pbData = 0;
  v5 = -1;
  v17 = 0;
  do
    ++v5;
  while ( Filename[v5] );
  phProv = 0;
  phHash = 0;
  pdwDataLen = 32;
  if ( !CryptAcquireContextW(&phProv, 0, 0, 0x18u, 0xF0000040) )
  {
    v7 = 311;
    goto LABEL_13;
  }
  if ( !CryptCreateHash(phProv, 0x800Cu, 0, 0, &phHash) )
  {
    v7 = 312;
    goto LABEL_13;
  }
  if ( !CryptHashData(phHash, (const BYTE *)Filename, v5, 0) )
  {
    v7 = 313;
    goto LABEL_13;
  }
  if ( !CryptGetHashParam(phHash, 2u, pbData, &pdwDataLen, 0) )
  {
    v7 = 314;
LABEL_13:
    Win32Error = wil::details::in1diag3::Return_GetLastError(
                   retaddr,
                   (void *)v7,
                   (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\tokenfilemanager.cpp",
                   v6);
    if ( phHash )
      CryptDestroyHash(phHash);
    if ( phProv )
      CryptReleaseContext(phProv, 0);
    if ( Win32Error < 0 )
    {
      v9 = 106;
LABEL_36:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\registryisolator.cpp",
        (const char *)(unsigned int)Win32Error,
        dwFlags);
      return (unsigned int)Win32Error;
    }
    goto LABEL_23;
  }
  if ( phHash )
    CryptDestroyHash(phHash);
  if ( phProv )
    CryptReleaseContext(phProv, 0);
LABEL_23:
  memset_0(sourceString, 0, 0x20Au);
  pdwDataLen = 261;
  if ( !Base64Encode(pbData, 32, sourceString, (int *)&pdwDataLen, 3u) )
  {
    Win32Error = -2147418113;
    v9 = 110;
    goto LABEL_36;
  }
  if ( (unsigned __int64)(int)pdwDataLen > 0x104 )
  {
    Win32Error = -2147418113;
    v9 = 111;
    goto LABEL_36;
  }
  string = 0;
  do
    ++v4;
  while ( sourceString[v4] );
  if ( v4 > 0xFFFFFFFF )
  {
    Win32Error = -2147024362;
  }
  else
  {
    WindowsDeleteString(0);
    string = 0;
    Win32Error = WindowsCreateString(sourceString, v4, &string);
    if ( Win32Error >= 0 )
    {
      *a2 = string;
      string = 0;
      WindowsDeleteString(0);
      return 0;
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x72,
    (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\registryisolator.cpp",
    (const char *)(unsigned int)Win32Error,
    dwFlags);
  WindowsDeleteString(string);
  return (unsigned int)Win32Error;
}

```

## disassembly

```asm
0x1800107d8  mov     [rsp-8+arg_0], rbx
0x1800107dd  mov     [rsp-8+arg_10], rsi
0x1800107e2  push    rbp
0x1800107e3  push    rdi
0x1800107e4  push    r14
0x1800107e6  lea     rbp, [rsp-3A0h]
0x1800107ee  sub     rsp, 4A0h
0x1800107f5  mov     rax, cs:__security_cookie
0x1800107fc  xor     rax, rsp
0x1800107ff  mov     [rbp+3B0h+var_20], rax
0x180010806  mov     rsi, rdx
0x180010809  lea     rcx, [rsp+4B0h+Filename]; void *
0x18001080e  xor     edx, edx; Val
0x180010810  mov     r8d, 20Ah; Size
0x180010816  call    memset_0
0x18001081b  mov     r8d, 104h; nSize
0x180010821  lea     rdx, [rsp+4B0h+Filename]; lpFilename
0x180010826  xor     ecx, ecx; hModule
0x180010828  call    cs:__imp_GetModuleFileNameW
0x18001082e  xor     r14d, r14d
0x180010831  test    eax, eax
0x180010833  jz      loc_180010A78
0x180010839  cmp     eax, 104h
0x18001083e  jz      loc_180010A78
0x180010844  xorps   xmm0, xmm0
0x180010847  lea     rax, [rsp+4B0h+Filename]
0x18001084c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180010850  movups  xmmword ptr [rsp+4B0h+pbData], xmm0
0x180010855  mov     rbx, rdi
0x180010858  movups  [rsp+4B0h+var_450], xmm0
0x18001085d  inc     rbx
0x180010860  cmp     [rax+rbx*2], r14w
0x180010865  jnz     short loc_18001085D
0x180010867  mov     r9d, 18h; dwProvType
0x18001086d  mov     [rsp+4B0h+phProv], r14
0x180010872  xor     r8d, r8d; szProvider
0x180010875  mov     [rsp+4B0h+phHash], r14
0x18001087a  xor     edx, edx; szContainer
0x18001087c  mov     [rsp+4B0h+pdwDataLen], 20h ; ' '
0x180010884  lea     rcx, [rsp+4B0h+phProv]; phProv
0x180010889  mov     [rsp+4B0h+dwFlags], 0F0000040h; dwFlags
0x180010891  call    cs:__imp_CryptAcquireContextW
0x180010897  test    eax, eax
0x180010899  jnz     short loc_1800108A2
0x18001089b  mov     edx, 137h
0x1800108a0  jmp     short loc_180010916
0x1800108a2  mov     rcx, [rsp+4B0h+phProv]; hProv
0x1800108a7  lea     rax, [rsp+4B0h+phHash]
0x1800108ac  xor     r9d, r9d; dwFlags
0x1800108af  mov     qword ptr [rsp+4B0h+dwFlags], rax; phHash
0x1800108b4  xor     r8d, r8d; hKey
0x1800108b7  mov     edx, 800Ch; Algid
0x1800108bc  call    cs:__imp_CryptCreateHash
0x1800108c2  test    eax, eax
0x1800108c4  jnz     short loc_1800108CD
0x1800108c6  mov     edx, 138h
0x1800108cb  jmp     short loc_180010916
0x1800108cd  mov     rcx, [rsp+4B0h+phHash]; hHash
0x1800108d2  lea     rdx, [rsp+4B0h+Filename]; pbData
0x1800108d7  mov     r8d, ebx; dwDataLen
0x1800108da  xor     r9d, r9d; dwFlags
0x1800108dd  call    cs:__imp_CryptHashData
0x1800108e3  test    eax, eax
0x1800108e5  jnz     short loc_1800108EE
0x1800108e7  mov     edx, 139h
0x1800108ec  jmp     short loc_180010916
0x1800108ee  mov     rcx, [rsp+4B0h+phHash]; hHash
0x1800108f3  lea     r9, [rsp+4B0h+pdwDataLen]; pdwDataLen
0x1800108f8  lea     r8, [rsp+4B0h+pbData]; pbData
0x1800108fd  mov     [rsp+4B0h+dwFlags], r14d; dwFlags
0x180010902  mov     edx, 2; dwParam
0x180010907  call    cs:__imp_CryptGetHashParam
0x18001090d  test    eax, eax
0x18001090f  jnz     short loc_18001095B
0x180010911  mov     edx, 13Ah; void *
0x180010916  mov     rcx, [rbp+3B8h]; this
0x18001091d  lea     r8, aOnecoreuapEndu_265; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x180010924  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180010929  mov     rcx, [rsp+4B0h+phHash]; hHash
0x18001092e  mov     ebx, eax
0x180010930  test    rcx, rcx
0x180010933  jz      short loc_18001093B
0x180010935  call    cs:__imp_CryptDestroyHash
0x18001093b  mov     rcx, [rsp+4B0h+phProv]; hProv
0x180010940  test    rcx, rcx
0x180010943  jz      short loc_18001094D
0x180010945  xor     edx, edx; dwFlags
0x180010947  call    cs:__imp_CryptReleaseContext
0x18001094d  test    ebx, ebx
0x18001094f  jns     short loc_18001097D
0x180010951  mov     edx, 6Ah ; 'j'
0x180010956  jmp     loc_180010A88
0x18001095b  mov     rcx, [rsp+4B0h+phHash]; hHash
0x180010960  test    rcx, rcx
0x180010963  jz      short loc_18001096B
0x180010965  call    cs:__imp_CryptDestroyHash
0x18001096b  mov     rcx, [rsp+4B0h+phProv]; hProv
0x180010970  test    rcx, rcx
0x180010973  jz      short loc_18001097D
0x180010975  xor     edx, edx; dwFlags
0x180010977  call    cs:__imp_CryptReleaseContext
0x18001097d  xor     edx, edx; Val
0x18001097f  lea     rcx, [rbp+3B0h+sourceString]; void *
0x180010986  mov     r8d, 20Ah; Size
0x18001098c  call    memset_0
0x180010991  lea     r9, [rsp+4B0h+pdwDataLen]; int *
0x180010996  mov     [rsp+4B0h+pdwDataLen], 105h
0x18001099e  lea     r8, [rbp+3B0h+sourceString]; unsigned __int16 *
0x1800109a5  mov     [rsp+4B0h+dwFlags], 3; int
0x1800109ad  mov     edx, 20h ; ' '; int
0x1800109b2  lea     rcx, [rsp+4B0h+pbData]; unsigned __int8 *
0x1800109b7  call    ?Base64Encode@@YA_NPEBEHPEAGPEAHK@Z; Base64Encode(uchar const *,int,ushort *,int *,ulong)
0x1800109bc  test    al, al
0x1800109be  jnz     short loc_1800109CF
0x1800109c0  mov     ebx, 8000FFFFh
0x1800109c5  mov     edx, 6Eh ; 'n'
0x1800109ca  jmp     loc_180010A88
0x1800109cf  movsxd  rax, [rsp+4B0h+pdwDataLen]
0x1800109d4  cmp     rax, 104h
0x1800109da  jbe     short loc_1800109EB
0x1800109dc  mov     ebx, 8000FFFFh
0x1800109e1  mov     edx, 6Fh ; 'o'
0x1800109e6  jmp     loc_180010A88
0x1800109eb  mov     [rsp+4B0h+string], r14
0x1800109f0  lea     rax, [rbp+3B0h+sourceString]
0x1800109f7  inc     rdi
0x1800109fa  cmp     [rax+rdi*2], r14w
0x1800109ff  jnz     short loc_1800109F7
0x180010a01  mov     eax, 0FFFFFFFFh
0x180010a06  cmp     rdi, rax
0x180010a09  ja      short loc_180010A4B
0x180010a0b  xor     ecx, ecx; string
0x180010a0d  call    cs:__imp_WindowsDeleteString
0x180010a13  mov     edx, edi; length
0x180010a15  mov     [rsp+4B0h+string], r14
0x180010a1a  lea     r8, [rsp+4B0h+string]; string
0x180010a1f  lea     rcx, [rbp+3B0h+sourceString]; sourceString
0x180010a26  call    cs:__imp_WindowsCreateString
0x180010a2c  mov     ebx, eax
0x180010a2e  test    eax, eax
0x180010a30  js      short loc_180010A50
0x180010a32  mov     rax, [rsp+4B0h+string]
0x180010a37  xor     ecx, ecx; string
0x180010a39  mov     [rsi], rax
0x180010a3c  mov     [rsp+4B0h+string], r14
0x180010a41  call    cs:__imp_WindowsDeleteString
0x180010a47  xor     eax, eax
0x180010a49  jmp     short loc_180010AA0
0x180010a4b  mov     ebx, 80070216h
0x180010a50  mov     rcx, [rbp+3B8h]; this
0x180010a57  lea     r8, aOnecoreuapEndu_24; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x180010a5e  mov     r9d, ebx; char *
0x180010a61  mov     edx, 72h ; 'r'; void *
0x180010a66  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010a6b  mov     rcx, [rsp+4B0h+string]; string
0x180010a70  call    cs:__imp_WindowsDeleteString
0x180010a76  jmp     short loc_180010A9E
0x180010a78  call    ?SpHrFromLastWin32Error@@YAJXZ; SpHrFromLastWin32Error(void)
0x180010a7d  mov     ebx, eax
0x180010a7f  test    eax, eax
0x180010a81  jns     short loc_180010A9E
0x180010a83  mov     edx, 67h ; 'g'; void *
0x180010a88  mov     rcx, [rbp+3B8h]; this
0x180010a8f  lea     r8, aOnecoreuapEndu_24; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x180010a96  mov     r9d, ebx; char *
0x180010a99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010a9e  mov     eax, ebx
0x180010aa0  mov     rcx, [rbp+3B0h+var_20]
0x180010aa7  xor     rcx, rsp; StackCookie
0x180010aaa  call    __security_check_cookie
0x180010aaf  lea     r11, [rsp+4B0h+var_10]
0x180010ab7  mov     rbx, [r11+20h]
0x180010abb  mov     rsi, [r11+30h]
0x180010abf  mov     rsp, r11
0x180010ac2  pop     r14
0x180010ac4  pop     rdi
0x180010ac5  pop     rbp
0x180010ac6  retn
```
