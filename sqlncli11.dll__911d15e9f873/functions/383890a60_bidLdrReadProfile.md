# _bidLdrReadProfile

- ea: `0x383890a60`
- end: `0x383890b56`
- name: `_bidLdrReadProfile`
- size: `246`
- prototype: `__int64 __fastcall(LPCWSTR lpRootPathName)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x383893e30`

## callees

- `0x3838434c0`
- `0x383890a60`
- `0x38391b390`
- `0x38391b4a0`

## import_xrefs

- `MSVCR100!wcsncpy_s` at `0x383890afc`
- `MSVCR100!wcsncpy_s` at `0x3838be545`
- `MSVCR100!wcsncpy_s` at `0x383890afc`
- `MSVCR100!wcsncpy_s` at `0x3838be545`
- `KERNEL32!OutputDebugStringW` at `0x3838be584`
- `KERNEL32!OutputDebugStringW` at `0x3838be58f`
- `KERNEL32!OutputDebugStringW` at `0x3838be59c`
- `KERNEL32!OutputDebugStringW` at `0x3838be5a7`
- `KERNEL32!OutputDebugStringW` at `0x3838be5b4`
- `KERNEL32!OutputDebugStringW` at `0x3838be5bd`
- `KERNEL32!OutputDebugStringW` at `0x3838be5ca`
- `KERNEL32!OutputDebugStringW` at `0x3838be584`
- `KERNEL32!OutputDebugStringW` at `0x3838be58f`
- `KERNEL32!OutputDebugStringW` at `0x3838be59c`
- `KERNEL32!OutputDebugStringW` at `0x3838be5a7`
- `KERNEL32!OutputDebugStringW` at `0x3838be5b4`
- `KERNEL32!OutputDebugStringW` at `0x3838be5bd`
- `KERNEL32!OutputDebugStringW` at `0x3838be5ca`
- `KERNEL32!GetModuleFileNameW` at `0x3838be472`
- `KERNEL32!GetModuleFileNameW` at `0x3838be472`
- `KERNEL32!lstrlenW` at `0x3838be4ad`
- `KERNEL32!lstrlenW` at `0x3838be4ad`
- `ADVAPI32!RegOpenKeyExW` at `0x383890adf`
- `ADVAPI32!RegOpenKeyExW` at `0x383890adf`
- `ADVAPI32!RegQueryValueExW` at `0x3838be441`
- `ADVAPI32!RegQueryValueExW` at `0x3838be441`
- `ADVAPI32!RegCloseKey` at `0x3838be550`
- `ADVAPI32!RegCloseKey` at `0x3838be550`

## string_xrefs

- `0x3838be513`: `:Path`

## pseudocode

```c
__int64 __fastcall bidLdrReadProfile(wchar_t *lpRootPathName, BOOL *a2)
{
  __int64 result; // rax
  BOOL v5; // ecx
  WCHAR *v6; // rax
  int *v7; // rax
  BYTE Data[4]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR lpOutputString; // [rsp+40h] [rbp-C0h]
  LPCWSTR v12; // [rsp+48h] [rbp-B8h]
  wchar_t *v13; // [rsp+50h] [rbp-B0h]
  __int64 v14; // [rsp+58h] [rbp-A8h]
  BOOL v15; // [rsp+60h] [rbp-A0h]
  DWORD cbData[2]; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Filename[269]; // [rsp+70h] [rbp-90h] BYREF
  int v18; // [rsp+28Ah] [rbp+18Ah] BYREF

  v13 = lpRootPathName;
  lpOutputString = L"SOFTWARE\\Microsoft\\BidInterface\\Loader";
  hKey = 0;
  v12 = L"<NotFound>";
  v14 = 538;
  v15 = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\BidInterface\\Loader", 0, 0x20019u, &hKey) )
  {
    wcsncpy_s(lpRootPathName, 0x10Du, L"<NotFound>", 0xFFFFFFFFFFFFFFFFuLL);
    result = 0;
    v5 = 0;
    HIDWORD(v14) = 0;
    v15 = 0;
  }
  else
  {
    *(_DWORD *)Data = 0;
    cbData[0] = 4;
    Type = 0;
    v15 = !RegQueryValueExW(hKey, L":LdrMsg", 0, &Type, Data, cbData) && Type == 4 && *(_DWORD *)Data != 0;
    if ( GetModuleFileNameW(0, Filename, 0x10Du) - 1 <= 0x10B )
    {
      LOWORD(v18) = 0;
      v12 = Filename;
      if ( !(unsigned int)bidLdrReadStr(&hKey) )
      {
        v6 = (WCHAR *)&cbData[1] + lstrlenW(Filename) + 1;
        if ( v6 < Filename )
          goto LABEL_21;
        while ( *v6 != 92 && *v6 != 47 )
        {
          if ( --v6 < Filename )
            goto LABEL_21;
        }
        v7 = (int *)(v6 + 1);
        if ( v7 >= &v18 || (*v7 = 42, !(unsigned int)bidLdrReadStr(&hKey)) )
        {
LABEL_21:
          v12 = L":Path";
          if ( !(unsigned int)bidLdrReadStr(&hKey) )
          {
            v12 = L"<NotFound>";
            HIDWORD(v14) = 0;
            wcsncpy_s(lpRootPathName, 0x10Du, L"<NotFound>", 0xFFFFFFFFFFFFFFFFuLL);
          }
        }
      }
    }
    RegCloseKey(hKey);
    v5 = v15;
    result = HIDWORD(v14);
    hKey = 0;
  }
  lpRootPathName[269] = 0;
  if ( (_DWORD)result )
  {
    result = bidLdrIsPathLocal(lpRootPathName);
    v5 = v15;
    HIDWORD(v14) = result;
  }
  if ( v5 )
  {
    OutputDebugStringW(L"*** [HKLM\\");
    OutputDebugStringW(lpOutputString);
    OutputDebugStringW(L"\\\"");
    OutputDebugStringW(v12);
    OutputDebugStringW(L"\"] \n*** \"");
    OutputDebugStringW(lpRootPathName);
    OutputDebugStringW(L"\"\n");
    result = HIDWORD(v14);
    *a2 = v15;
  }
  else
  {
    *a2 = 0;
  }
  dword_383B23BF0 = result;
  return result;
}

```

## disassembly

```asm
0x383890a60  mov     [rsp-8+arg_10], rbx
0x383890a65  mov     [rsp-8+arg_18], rsi
0x383890a6a  push    rbp
0x383890a6b  push    rdi
0x383890a6c  push    r14
0x383890a6e  lea     rbp, [rsp-1A0h]
0x383890a76  sub     rsp, 2A0h
0x383890a7d  mov     rax, cs:__security_cookie
0x383890a84  xor     rax, rsp
0x383890a87  mov     [rbp+1B0h+var_20], rax
0x383890a8e  mov     rdi, rdx
0x383890a91  lea     rax, [rsp+2B0h+hKey]
0x383890a96  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\BidInterface\\Load"...
0x383890a9d  mov     rbx, rcx
0x383890aa0  xor     esi, esi
0x383890aa2  mov     [rsp+2B0h+var_260], rcx
0x383890aa7  lea     r14, aNotfound; "<NotFound>"
0x383890aae  mov     r9d, 20019h; samDesired
0x383890ab4  xor     r8d, r8d; ulOptions
0x383890ab7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x383890abe  mov     [rsp+2B0h+lpOutputString], rdx
0x383890ac3  mov     [rsp+2B0h+hKey], rsi
0x383890ac8  mov     [rsp+2B0h+var_268], r14
0x383890acd  mov     [rsp+2B0h+var_258], 21Ah
0x383890ad6  mov     [rsp+2B0h+var_250], esi
0x383890ada  mov     [rsp+2B0h+phkResult], rax; phkResult
0x383890adf  call    cs:__imp_RegOpenKeyExW
0x383890ae5  test    eax, eax
0x383890ae7  jz      loc_3838BE409
0x383890aed  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x383890af1  mov     r8, r14; Source
0x383890af4  mov     edx, 10Dh; SizeInWords
0x383890af9  mov     rcx, rbx; Destination
0x383890afc  call    cs:__imp_wcsncpy_s
0x383890b02  mov     eax, esi
0x383890b04  mov     ecx, esi
0x383890b06  mov     dword ptr [rsp+2B0h+var_258+4], eax
0x383890b0a  mov     [rsp+2B0h+var_250], ecx
0x383890b0e  jmp     short $+2
0x383890b10  mov     [rbx+21Ah], si
0x383890b17  test    eax, eax
0x383890b19  jnz     loc_3838BE568
0x383890b1f  test    ecx, ecx
0x383890b21  jnz     loc_3838BE57D
0x383890b27  mov     [rdi], ecx
0x383890b29  mov     cs:dword_383B23BF0, eax
0x383890b2f  mov     rcx, [rbp+1B0h+var_20]
0x383890b36  xor     rcx, rsp; StackCookie
0x383890b39  call    __security_check_cookie
0x383890b3e  lea     r11, [rsp+2B0h+var_10]
0x383890b46  mov     rbx, [r11+30h]
0x383890b4a  mov     rsi, [r11+38h]
0x383890b4e  mov     rsp, r11
0x383890b51  pop     r14
0x383890b53  pop     rdi
0x383890b54  pop     rbp
0x383890b55  retn
0x3838be409  mov     rcx, [rsp+2B0h+hKey]; hKey
0x3838be40e  lea     rax, [rsp+2B0h+cbData]
0x3838be413  lea     r9, [rsp+2B0h+Type]; lpType
0x3838be418  mov     [rsp+2B0h+lpcbData], rax; lpcbData
0x3838be41d  lea     rax, [rsp+2B0h+Data]
0x3838be422  lea     rdx, aLdrmsg; ":LdrMsg"
0x3838be429  xor     r8d, r8d; lpReserved
0x3838be42c  mov     dword ptr [rsp+2B0h+Data], esi
0x3838be430  mov     [rsp+2B0h+cbData], 4
0x3838be438  mov     [rsp+2B0h+phkResult], rax; lpData
0x3838be43d  mov     [rsp+2B0h+Type], esi
0x3838be441  call    cs:__imp_RegQueryValueExW
0x3838be447  test    eax, eax
0x3838be449  jnz     short loc_3838BE461
0x3838be44b  cmp     [rsp+2B0h+Type], 4
0x3838be450  jnz     short loc_3838BE461
0x3838be452  mov     eax, esi
0x3838be454  cmp     dword ptr [rsp+2B0h+Data], eax
0x3838be458  setnz   al
0x3838be45b  mov     [rsp+2B0h+var_250], eax
0x3838be45f  jmp     short loc_3838BE465
0x3838be461  mov     [rsp+2B0h+var_250], esi
0x3838be465  lea     rdx, [rsp+2B0h+Filename]; lpFilename
0x3838be46a  mov     r8d, 10Dh; nSize
0x3838be470  xor     ecx, ecx; hModule
0x3838be472  call    cs:__imp_GetModuleFileNameW
0x3838be478  dec     eax
0x3838be47a  cmp     eax, 10Bh
0x3838be47f  ja      loc_3838BE54B
0x3838be485  lea     rax, [rsp+2B0h+Filename]
0x3838be48a  lea     rcx, [rsp+2B0h+hKey]
0x3838be48f  mov     word ptr [rbp+1B0h+var_26], si
0x3838be496  mov     [rsp+2B0h+var_268], rax
0x3838be49b  call    _bidLdrReadStr
0x3838be4a0  test    eax, eax
0x3838be4a2  jnz     loc_3838BE54B
0x3838be4a8  lea     rcx, [rsp+2B0h+Filename]; lpString
0x3838be4ad  call    cs:__imp_lstrlenW
0x3838be4b3  movsxd  rcx, eax
0x3838be4b6  lea     rax, [rsp+rcx*2+2B0h+var_242]
0x3838be4bb  lea     rcx, [rsp+2B0h+Filename]
0x3838be4c0  cmp     rax, rcx
0x3838be4c3  jb      short loc_3838BE513
0x3838be4c5  nop     word ptr [rax+rax+00000000h]
0x3838be4d0  movzx   ecx, word ptr [rax]
0x3838be4d3  cmp     cx, 5Ch ; '\'
0x3838be4d7  jz      short loc_3838BE4EF
0x3838be4d9  cmp     cx, 2Fh ; '/'
0x3838be4dd  jz      short loc_3838BE4EF
0x3838be4df  lea     rcx, [rsp+2B0h+Filename]
0x3838be4e4  sub     rax, 2
0x3838be4e8  cmp     rax, rcx
0x3838be4eb  jnb     short loc_3838BE4D0
0x3838be4ed  jmp     short loc_3838BE513
0x3838be4ef  lea     rcx, [rbp+1B0h+var_26]
0x3838be4f6  add     rax, 2
0x3838be4fa  cmp     rax, rcx
0x3838be4fd  jnb     short loc_3838BE513
0x3838be4ff  lea     rcx, [rsp+2B0h+hKey]
0x3838be504  mov     dword ptr [rax], 2Ah ; '*'
0x3838be50a  call    _bidLdrReadStr
0x3838be50f  test    eax, eax
0x3838be511  jnz     short loc_3838BE54B
0x3838be513  lea     rax, aPath; ":Path"
0x3838be51a  lea     rcx, [rsp+2B0h+hKey]
0x3838be51f  mov     [rsp+2B0h+var_268], rax
0x3838be524  call    _bidLdrReadStr
0x3838be529  test    eax, eax
0x3838be52b  jnz     short loc_3838BE54B
0x3838be52d  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x3838be531  mov     r8, r14; Source
0x3838be534  mov     edx, 10Dh; SizeInWords
0x3838be539  mov     rcx, rbx; Destination
0x3838be53c  mov     [rsp+2B0h+var_268], r14
0x3838be541  mov     dword ptr [rsp+2B0h+var_258+4], esi
0x3838be545  call    cs:__imp_wcsncpy_s
0x3838be54b  mov     rcx, [rsp+2B0h+hKey]; hKey
0x3838be550  call    cs:__imp_RegCloseKey
0x3838be556  mov     ecx, [rsp+2B0h+var_250]
0x3838be55a  mov     eax, dword ptr [rsp+2B0h+var_258+4]
0x3838be55e  mov     [rsp+2B0h+hKey], rsi
0x3838be563  jmp     loc_383890B10
0x3838be568  mov     rcx, rbx; lpRootPathName
0x3838be56b  call    _bidLdrIsPathLocal
0x3838be570  mov     ecx, [rsp+2B0h+var_250]
0x3838be574  mov     dword ptr [rsp+2B0h+var_258+4], eax
0x3838be578  jmp     loc_383890B1F
0x3838be57d  lea     rcx, OutputString; "*** [HKLM\\"
0x3838be584  call    cs:__imp_OutputDebugStringW
0x3838be58a  mov     rcx, [rsp+2B0h+lpOutputString]; lpOutputString
0x3838be58f  call    cs:__imp_OutputDebugStringW
0x3838be595  lea     rcx, asc_3838BE620; "\\\""
0x3838be59c  call    cs:__imp_OutputDebugStringW
0x3838be5a2  mov     rcx, [rsp+2B0h+var_268]; lpOutputString
0x3838be5a7  call    cs:__imp_OutputDebugStringW
0x3838be5ad  lea     rcx, asc_3838BE628; "\"] \n*** \""
0x3838be5b4  call    cs:__imp_OutputDebugStringW
0x3838be5ba  mov     rcx, rbx; lpOutputString
0x3838be5bd  call    cs:__imp_OutputDebugStringW
0x3838be5c3  lea     rcx, asc_3838BE63C; "\"\n"
0x3838be5ca  call    cs:__imp_OutputDebugStringW
0x3838be5d0  mov     r11d, [rsp+2B0h+var_250]
0x3838be5d5  mov     eax, dword ptr [rsp+2B0h+var_258+4]
0x3838be5d9  mov     [rdi], r11d
0x3838be5dc  jmp     loc_383890B29
```
