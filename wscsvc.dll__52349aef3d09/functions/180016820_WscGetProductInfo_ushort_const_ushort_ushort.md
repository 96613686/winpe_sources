# WscGetProductInfo(ushort const *,ushort * *,ushort * *)

- ea: `0x180016820`
- end: `0x180016ae0`
- name: `?WscGetProductInfo@@YAXPEBGPEAPEAG1@Z`
- size: `704`
- prototype: `void __fastcall(LPCWSTR lpSrc, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180024370`
- `0x18002698c`
- `0x180032054`
- `0x1800321f0`

## callees

- `0x180016820`
- `0x180016ae8`
- `0x180029e74`
- `0x180029ec0`
- `0x18002a756`
- `0x18003fbf2`
- `0x18003fc30`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLangID` at `0x18001690a`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLangID` at `0x180016991`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLangID` at `0x18001690a`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLangID` at `0x180016991`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001687c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001687c`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x18001689b`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x18001689b`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x1800168c4`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x1800168c4`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180016948`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18001696e`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180016a03`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180016abb`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180016948`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18001696e`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180016a03`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180016abb`

## string_xrefs

- `0x180016910`: `\StringFileInfo\%04X%04X\CompanyName`
- `0x180016967`: `\StringFileInfo\040904E4\CompanyName`

## pseudocode

```c
void __fastcall WscGetProductInfo(LPCWSTR lpSrc, unsigned __int16 **a2, unsigned __int16 **a3)
{
  DWORD FileVersionInfoSizeW; // eax
  DWORD v7; // edi
  void *v8; // rbx
  LANGID UserDefaultLangID; // ax
  unsigned int v10; // eax
  LANGID v11; // ax
  unsigned int v12; // ecx
  unsigned __int16 *v13; // rax
  __int64 v14; // r8
  unsigned __int16 *v15; // rax
  __int64 v16; // r8
  __int64 v17; // [rsp+20h] [rbp-E0h]
  unsigned int puLen; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID lpBuffer; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR SubBlock[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Dst[264]; // [rsp+250h] [rbp+150h] BYREF

  if ( a2 || a3 )
  {
    memset_0(Dst, 0, 0x208u);
    if ( ExpandEnvironmentStringsW(lpSrc, Dst, 0x104u) )
    {
      FileVersionInfoSizeW = GetFileVersionInfoSizeW(Dst, 0);
      v7 = FileVersionInfoSizeW;
      if ( FileVersionInfoSizeW )
      {
        v8 = operator new[](FileVersionInfoSizeW);
        if ( GetFileVersionInfoW(Dst, 0, v7, v8) )
        {
          lpBuffer = 0;
          puLen = 0;
          memset_0(SubBlock, 0, 0x208u);
          if ( a2 )
          {
            *a2 = 0;
            UserDefaultLangID = GetUserDefaultLangID();
            if ( (int)StringCchPrintfW(
                        SubBlock,
                        0x103u,
                        L"\\StringFileInfo\\%04X%04X\\CompanyName",
                        UserDefaultLangID,
                        1200) >= 0 )
            {
              VerQueryValueW(v8, SubBlock, &lpBuffer, &puLen);
              v10 = puLen;
              if ( puLen
                || (VerQueryValueW(v8, L"\\StringFileInfo\\040904E4\\CompanyName", &lpBuffer, &puLen), (v10 = puLen) != 0) )
              {
                v15 = (unsigned __int16 *)operator new[](saturated_mul(v10 + 1, 2u));
                v16 = puLen + 1;
                *a2 = v15;
                memset_0(v15, 0, 2 * v16);
                memcpy_0(*a2, lpBuffer, 2LL * puLen);
              }
              lpBuffer = 0;
              puLen = 0;
            }
          }
          if ( a3 )
          {
            *a3 = 0;
            v11 = GetUserDefaultLangID();
            LODWORD(v17) = 1200;
            if ( (int)StringCchPrintfW(SubBlock, 0x103u, L"\\StringFileInfo\\%04X%04X\\ProductVersion", v11, v17) >= 0 )
            {
              VerQueryValueW(v8, SubBlock, &lpBuffer, &puLen);
              v12 = puLen;
              if ( puLen
                || (VerQueryValueW(v8, L"\\StringFileInfo\\040904E4\\ProductVersion", &lpBuffer, &puLen),
                    (v12 = puLen) != 0) )
              {
                v13 = (unsigned __int16 *)operator new[](saturated_mul(v12 + 1, 2u));
                v14 = puLen + 1;
                *a3 = v13;
                memset_0(v13, 0, 2 * v14);
                memcpy_0(*a3, lpBuffer, 2LL * puLen);
              }
            }
          }
        }
        operator delete(v8);
      }
    }
  }
}

```

## disassembly

```asm
0x180016820  push    rbp
0x180016822  push    rbx
0x180016823  push    rsi
0x180016824  push    r14
0x180016826  lea     rbp, [rsp-378h]
0x18001682e  sub     rsp, 478h
0x180016835  mov     rax, cs:__security_cookie
0x18001683c  xor     rax, rsp
0x18001683f  mov     [rbp+390h+var_30], rax
0x180016846  mov     r14, r8
0x180016849  mov     rsi, rdx
0x18001684c  mov     rbx, rcx
0x18001684f  test    rdx, rdx
0x180016852  jz      loc_180016AD2
0x180016858  xor     edx, edx; Val
0x18001685a  lea     rcx, [rbp+390h+Dst]; void *
0x180016861  mov     r8d, 208h; Size
0x180016867  call    memset_0
0x18001686c  mov     r8d, 104h; nSize
0x180016872  lea     rdx, [rbp+390h+Dst]; lpDst
0x180016879  mov     rcx, rbx; lpSrc
0x18001687c  call    cs:__imp_ExpandEnvironmentStringsW
0x180016882  test    eax, eax
0x180016884  jz      loc_1800169D5
0x18001688a  xor     edx, edx; lpdwHandle
0x18001688c  mov     [rsp+490h+arg_18], rdi
0x180016894  lea     rcx, [rbp+390h+Dst]; lptstrFilename
0x18001689b  call    cs:__imp_GetFileVersionInfoSizeW
0x1800168a1  mov     edi, eax
0x1800168a3  test    eax, eax
0x1800168a5  jz      loc_1800169CD
0x1800168ab  mov     ecx, edi; unsigned __int64
0x1800168ad  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800168b2  mov     r9, rax; lpData
0x1800168b5  lea     rcx, [rbp+390h+Dst]; lptstrFilename
0x1800168bc  mov     r8d, edi; dwLen
0x1800168bf  xor     edx, edx; dwHandle
0x1800168c1  mov     rbx, rax
0x1800168c4  call    cs:__imp_GetFileVersionInfoW
0x1800168ca  test    eax, eax
0x1800168cc  jz      loc_1800169C5
0x1800168d2  xor     edi, edi
0x1800168d4  mov     [rsp+490h+var_20], r15
0x1800168dc  xor     edx, edx; Val
0x1800168de  mov     [rsp+490h+lpBuffer], rdi
0x1800168e3  mov     r8d, 208h; Size
0x1800168e9  mov     [rsp+490h+puLen], edi
0x1800168ed  lea     rcx, [rsp+490h+SubBlock]; void *
0x1800168f2  call    memset_0
0x1800168f7  mov     r15, 0FFFFFFFFFFFFFFFFh
0x1800168fe  test    rsi, rsi
0x180016901  jz      loc_180016989
0x180016907  mov     [rsi], rdi
0x18001690a  call    cs:__imp_GetUserDefaultLangID
0x180016910  lea     r8, aStringfileinfo_2; "\\StringFileInfo\\%04X%04X\\CompanyName"
0x180016917  mov     [rsp+490h+var_470], 4B0h
0x18001691f  movzx   r9d, ax
0x180016923  lea     rcx, [rsp+490h+SubBlock]; unsigned __int16 *
0x180016928  mov     edx, 103h; unsigned __int64
0x18001692d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180016932  test    eax, eax
0x180016934  js      short loc_180016989
0x180016936  lea     r9, [rsp+490h+puLen]; puLen
0x18001693b  mov     rcx, rbx; pBlock
0x18001693e  lea     r8, [rsp+490h+lpBuffer]; lplpBuffer
0x180016943  lea     rdx, [rsp+490h+SubBlock]; lpSubBlock
0x180016948  call    cs:__imp_VerQueryValueW
0x18001694e  mov     eax, [rsp+490h+puLen]
0x180016952  test    eax, eax
0x180016954  jnz     loc_180016A5E
0x18001695a  lea     r9, [rsp+490h+puLen]; puLen
0x18001695f  mov     rcx, rbx; pBlock
0x180016962  lea     r8, [rsp+490h+lpBuffer]; lplpBuffer
0x180016967  lea     rdx, SubBlock; "\\StringFileInfo\\040904E4\\CompanyName"
0x18001696e  call    cs:__imp_VerQueryValueW
0x180016974  mov     eax, [rsp+490h+puLen]
0x180016978  test    eax, eax
0x18001697a  jnz     loc_180016A5E
0x180016980  mov     [rsp+490h+lpBuffer], rdi
0x180016985  mov     [rsp+490h+puLen], edi
0x180016989  test    r14, r14
0x18001698c  jz      short loc_1800169BD
0x18001698e  mov     [r14], rdi
0x180016991  call    cs:__imp_GetUserDefaultLangID
0x180016997  lea     r8, aStringfileinfo; "\\StringFileInfo\\%04X%04X\\ProductVers"...
0x18001699e  mov     [rsp+490h+var_470], 4B0h
0x1800169a6  movzx   r9d, ax
0x1800169aa  lea     rcx, [rsp+490h+SubBlock]; unsigned __int16 *
0x1800169af  mov     edx, 103h; unsigned __int64
0x1800169b4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800169b9  test    eax, eax
0x1800169bb  jns     short loc_1800169F1
0x1800169bd  mov     r15, [rsp+490h+var_20]
0x1800169c5  mov     rcx, rbx; Block
0x1800169c8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800169cd  mov     rdi, [rsp+490h+arg_18]
0x1800169d5  mov     rcx, [rbp+390h+var_30]
0x1800169dc  xor     rcx, rsp; StackCookie
0x1800169df  call    __security_check_cookie
0x1800169e4  add     rsp, 478h
0x1800169eb  pop     r14
0x1800169ed  pop     rsi
0x1800169ee  pop     rbx
0x1800169ef  pop     rbp
0x1800169f0  retn
0x1800169f1  lea     r9, [rsp+490h+puLen]; puLen
0x1800169f6  mov     rcx, rbx; pBlock
0x1800169f9  lea     r8, [rsp+490h+lpBuffer]; lplpBuffer
0x1800169fe  lea     rdx, [rsp+490h+SubBlock]; lpSubBlock
0x180016a03  call    cs:__imp_VerQueryValueW
0x180016a09  mov     ecx, [rsp+490h+puLen]
0x180016a0d  test    ecx, ecx
0x180016a0f  jz      loc_180016AA7
0x180016a15  lea     edx, [rcx+1]
0x180016a18  mov     eax, 2
0x180016a1d  mul     rdx
0x180016a20  cmovb   rax, r15
0x180016a24  mov     rcx, rax; unsigned __int64
0x180016a27  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180016a2c  mov     r8d, [rsp+490h+puLen]
0x180016a31  xor     edx, edx; Val
0x180016a33  inc     r8d
0x180016a36  mov     [r14], rax
0x180016a39  add     r8, r8; Size
0x180016a3c  mov     rcx, rax; void *
0x180016a3f  call    memset_0
0x180016a44  mov     r8d, [rsp+490h+puLen]
0x180016a49  mov     rdx, [rsp+490h+lpBuffer]; Src
0x180016a4e  add     r8, r8; Size
0x180016a51  mov     rcx, [r14]; void *
0x180016a54  call    memcpy_0
0x180016a59  jmp     loc_1800169BD
0x180016a5e  lea     ecx, [rax+1]
0x180016a61  mov     eax, 2
0x180016a66  mul     rcx
0x180016a69  cmovb   rax, r15
0x180016a6d  mov     rcx, rax; unsigned __int64
0x180016a70  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180016a75  mov     r8d, [rsp+490h+puLen]
0x180016a7a  xor     edx, edx; Val
0x180016a7c  inc     r8d
0x180016a7f  mov     [rsi], rax
0x180016a82  add     r8, r8; Size
0x180016a85  mov     rcx, rax; void *
0x180016a88  call    memset_0
0x180016a8d  mov     r8d, [rsp+490h+puLen]
0x180016a92  mov     rdx, [rsp+490h+lpBuffer]; Src
0x180016a97  add     r8, r8; Size
0x180016a9a  mov     rcx, [rsi]; void *
0x180016a9d  call    memcpy_0
0x180016aa2  jmp     loc_180016980
0x180016aa7  lea     r9, [rsp+490h+puLen]; puLen
0x180016aac  mov     rcx, rbx; pBlock
0x180016aaf  lea     r8, [rsp+490h+lpBuffer]; lplpBuffer
0x180016ab4  lea     rdx, aStringfileinfo_0; "\\StringFileInfo\\040904E4\\ProductVers"...
0x180016abb  call    cs:__imp_VerQueryValueW
0x180016ac1  mov     ecx, [rsp+490h+puLen]
0x180016ac5  test    ecx, ecx
0x180016ac7  jz      loc_1800169BD
0x180016acd  jmp     loc_180016A15
0x180016ad2  test    r14, r14
0x180016ad5  jz      loc_1800169D5
0x180016adb  jmp     loc_180016858
```
