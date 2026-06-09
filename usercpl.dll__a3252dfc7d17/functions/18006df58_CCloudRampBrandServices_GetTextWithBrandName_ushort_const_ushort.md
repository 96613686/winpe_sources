# CCloudRampBrandServices::GetTextWithBrandName(ushort const *,ushort * *)

- ea: `0x18006df58`
- end: `0x18006e1fa`
- name: `?GetTextWithBrandName@CCloudRampBrandServices@@SAJPEBGPEAPEAG@Z`
- size: `674`
- prototype: `__int64 __fastcall(PCNZWCH sourceString, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18006de1c`

## callees

- `0x180026218`
- `0x18006df58`
- `0x1800772c0`

## import_xrefs

- `msvcrt!wcsstr` at `0x18006e0e9`
- `msvcrt!wcsstr` at `0x18006e0e9`
- `SHLWAPI!__imp_SHLoadIndirectString` at `0x18006dfbe`
- `SHLWAPI!__imp_SHLoadIndirectString` at `0x18006dfbe`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006e00e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006e051`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006e12f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006e00e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006e051`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006e12f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e1c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e1c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006e0aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006e175`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006e1ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006e0aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006e175`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006e1ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsReplaceString` at `0x18006e161`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsReplaceString` at `0x18006e161`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18006e097`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18006e097`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006e0dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006e191`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006e0dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006e191`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006e023`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006e066`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006e144`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006e023`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006e066`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006e144`

## string_xrefs

- `0x18006dfb4`: `@%SystemRoot%\System32\SettingSyncCore.dll,-1024`

## pseudocode

```c
__int64 __fastcall CCloudRampBrandServices::GetTextWithBrandName(PCNZWCH sourceString, unsigned __int16 **a2)
{
  WCHAR *v4; // r14
  HRESULT v5; // esi
  unsigned __int64 v6; // rbx
  unsigned __int64 v7; // rbx
  HSTRING v8; // rbx
  unsigned __int64 v9; // rdx
  int v10; // r15d
  const wchar_t *v11; // rdi
  const wchar_t *StringRawBuffer; // rax
  unsigned __int64 v13; // rdi
  const WCHAR *v14; // rsi
  HSTRING v15; // rcx
  const unsigned __int16 *v16; // rax
  HSTRING newString; // [rsp+20h] [rbp-E0h] BYREF
  PCWSTR sourceStringa; // [rsp+28h] [rbp-D8h] BYREF
  HSTRING_HEADER v20; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING stringReplaceWith; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING_HEADER v22; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING string; // [rsp+68h] [rbp-98h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-90h] BYREF
  WCHAR pszOutBuf[264]; // [rsp+90h] [rbp-70h] BYREF

  *a2 = 0;
  sourceStringa = 0;
  v20.Reserved.Reserved1 = (PVOID)-1LL;
  *(_QWORD *)&v20.Reserved.Reserved2[8] = -1;
  v4 = 0;
  v5 = SHLoadIndirectString(L"@%SystemRoot%\\System32\\SettingSyncCore.dll,-1024", pszOutBuf, 0x104u, 0);
  if ( v5 >= 0 )
  {
    v5 = CoAllocString(pszOutBuf, (unsigned __int16 **)&sourceStringa);
    if ( v5 < 0 )
    {
      v4 = (WCHAR *)sourceStringa;
    }
    else
    {
      v6 = -1;
      do
        ++v6;
      while ( sourceString[v6] );
      if ( v6 > 0xFFFFFFFF )
      {
        LODWORD(v6) = -1;
        RaiseException(0xC000000D, 1u, 0, 0);
      }
      WindowsCreateStringReference(sourceString, v6, &hstringHeader, &string);
      v4 = (WCHAR *)sourceStringa;
      v7 = -1;
      do
        ++v7;
      while ( sourceStringa[v7] );
      if ( v7 > 0xFFFFFFFF )
      {
        LODWORD(v7) = -1;
        RaiseException(0xC000000D, 1u, 0, 0);
      }
      WindowsCreateStringReference(v4, v7, &v22, &stringReplaceWith);
      if ( sourceString )
      {
        v8 = 0;
        newString = 0;
        v9 = -1;
        do
          ++v9;
        while ( sourceString[v9] );
        if ( v9 > 0xFFFFFFFF )
        {
          v5 = -2147024362;
        }
        else
        {
          v5 = WindowsCreateString(sourceString, v9, &newString);
          if ( v5 >= 0 )
          {
            v8 = newString;
            WindowsDeleteString(0);
          }
        }
        if ( v5 >= 0 )
        {
          v10 = 0;
          while ( v5 >= 0 )
          {
            v11 = off_180080070[v10];
            StringRawBuffer = WindowsGetStringRawBuffer(v8, 0);
            if ( wcsstr(StringRawBuffer, v11) )
            {
              v13 = -1;
              v14 = off_180080070[v10];
              do
                ++v13;
              while ( v14[v13] );
              if ( v13 > 0xFFFFFFFF )
              {
                LODWORD(v13) = -1;
                RaiseException(0xC000000D, 1u, 0, 0);
              }
              WindowsCreateStringReference(v14, v13, &v20, (HSTRING *)&sourceStringa);
              newString = 0;
              v5 = WindowsReplaceString(v8, (HSTRING)sourceStringa, stringReplaceWith, &newString);
              if ( v5 >= 0 )
              {
                v15 = v8;
                v8 = newString;
                WindowsDeleteString(v15);
              }
            }
            if ( (unsigned int)++v10 >= 3 )
            {
              if ( v5 >= 0 )
              {
                v16 = WindowsGetStringRawBuffer(v8, 0);
                v5 = CoAllocString(v16, a2);
              }
              break;
            }
          }
        }
        if ( v8 )
          WindowsDeleteString(v8);
      }
      else
      {
        v5 = -2147467261;
      }
    }
  }
  if ( v4 )
    CoTaskMemFree(v4);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18006df58  mov     [rsp-8+arg_10], rbx
0x18006df5d  push    rbp
0x18006df5e  push    rsi
0x18006df5f  push    rdi
0x18006df60  push    r12
0x18006df62  push    r13
0x18006df64  push    r14
0x18006df66  push    r15
0x18006df68  lea     rbp, [rsp-1B0h]
0x18006df70  sub     rsp, 2B0h
0x18006df77  mov     rax, cs:__security_cookie
0x18006df7e  xor     rax, rsp
0x18006df81  mov     [rbp+1E0h+var_40], rax
0x18006df88  xor     r12d, r12d
0x18006df8b  mov     r13, rdx
0x18006df8e  mov     [rdx], r12
0x18006df91  mov     rdi, rcx
0x18006df94  or      r15, 0FFFFFFFFFFFFFFFFh
0x18006df98  mov     [rsp+2E0h+sourceString], r12
0x18006df9d  lea     rdx, [rbp+1E0h+pszOutBuf]; pszOutBuf
0x18006dfa1  mov     qword ptr [rsp+2E0h+var_2B0.Reserved], r15
0x18006dfa6  xor     r9d, r9d; ppvReserved
0x18006dfa9  mov     qword ptr [rsp+2E0h+var_2B0.Reserved+8], r15
0x18006dfae  mov     r8d, 104h; cchOutBuf
0x18006dfb4  lea     rcx, pszSource; "@%SystemRoot%\\System32\\SettingSyncCor"...
0x18006dfbb  mov     r14d, r12d
0x18006dfbe  call    cs:__imp_SHLoadIndirectString
0x18006dfc4  mov     esi, eax
0x18006dfc6  test    eax, eax
0x18006dfc8  js      loc_18006E1C0
0x18006dfce  lea     rdx, [rsp+2E0h+sourceString]; unsigned __int16 **
0x18006dfd3  lea     rcx, [rbp+1E0h+pszOutBuf]; unsigned __int16 *
0x18006dfd7  call    ?CoAllocString@@YAJPEBGPEAPEAG@Z; CoAllocString(ushort const *,ushort * *)
0x18006dfdc  mov     esi, eax
0x18006dfde  test    eax, eax
0x18006dfe0  js      loc_18006E1BB
0x18006dfe6  mov     rbx, r15
0x18006dfe9  inc     rbx
0x18006dfec  cmp     [rdi+rbx*2], r12w
0x18006dff1  jnz     short loc_18006DFE9
0x18006dff3  mov     esi, 0FFFFFFFFh
0x18006dff8  cmp     rbx, rsi
0x18006dffb  jbe     short loc_18006E014
0x18006dffd  xor     r9d, r9d; lpArguments
0x18006e000  xor     r8d, r8d; nNumberOfArguments
0x18006e003  mov     ecx, 0C000000Dh; dwExceptionCode
0x18006e008  mov     ebx, esi
0x18006e00a  lea     edx, [r9+1]; dwExceptionFlags
0x18006e00e  call    cs:__imp_RaiseException
0x18006e014  lea     r9, [rsp+2E0h+string]; string
0x18006e019  mov     edx, ebx; length
0x18006e01b  lea     r8, [rsp+2E0h+hstringHeader]; hstringHeader
0x18006e020  mov     rcx, rdi; sourceString
0x18006e023  call    cs:__imp_WindowsCreateStringReference
0x18006e029  mov     r14, [rsp+2E0h+sourceString]
0x18006e02e  mov     rbx, r15
0x18006e031  inc     rbx
0x18006e034  cmp     [r14+rbx*2], r12w
0x18006e039  jnz     short loc_18006E031
0x18006e03b  cmp     rbx, rsi
0x18006e03e  jbe     short loc_18006E057
0x18006e040  xor     r9d, r9d; lpArguments
0x18006e043  xor     r8d, r8d; nNumberOfArguments
0x18006e046  mov     ecx, 0C000000Dh; dwExceptionCode
0x18006e04b  mov     ebx, esi
0x18006e04d  lea     edx, [r9+1]; dwExceptionFlags
0x18006e051  call    cs:__imp_RaiseException
0x18006e057  lea     r9, [rsp+2E0h+stringReplaceWith]; string
0x18006e05c  mov     edx, ebx; length
0x18006e05e  lea     r8, [rsp+2E0h+var_290]; hstringHeader
0x18006e063  mov     rcx, r14; sourceString
0x18006e066  call    cs:__imp_WindowsCreateStringReference
0x18006e06c  test    rdi, rdi
0x18006e06f  jz      loc_18006E1B4
0x18006e075  mov     rbx, r12
0x18006e078  mov     [rsp+2E0h+newString], r12
0x18006e07d  mov     rdx, r15
0x18006e080  inc     rdx; length
0x18006e083  cmp     [rdi+rdx*2], r12w
0x18006e088  jnz     short loc_18006E080
0x18006e08a  cmp     rdx, rsi
0x18006e08d  ja      short loc_18006E0B2
0x18006e08f  lea     r8, [rsp+2E0h+newString]; string
0x18006e094  mov     rcx, rdi; sourceString
0x18006e097  call    cs:__imp_WindowsCreateString
0x18006e09d  mov     esi, eax
0x18006e09f  test    eax, eax
0x18006e0a1  js      short loc_18006E0B7
0x18006e0a3  mov     rbx, [rsp+2E0h+newString]
0x18006e0a8  xor     ecx, ecx; string
0x18006e0aa  call    cs:__imp_WindowsDeleteString
0x18006e0b0  jmp     short loc_18006E0B7
0x18006e0b2  mov     esi, 80070216h
0x18006e0b7  test    esi, esi
0x18006e0b9  js      loc_18006E1A4
0x18006e0bf  mov     r15d, r12d
0x18006e0c2  test    esi, esi
0x18006e0c4  js      loc_18006E1A4
0x18006e0ca  lea     rax, off_180080070; "SKYDRIVE_BRAND_NAME"
0x18006e0d1  movsxd  r12, r15d
0x18006e0d4  xor     edx, edx; length
0x18006e0d6  mov     rcx, rbx; string
0x18006e0d9  mov     rdi, [rax+r12*8]
0x18006e0dd  call    cs:__imp_WindowsGetStringRawBuffer
0x18006e0e3  mov     rcx, rax; Str
0x18006e0e6  mov     rdx, rdi; SubStr
0x18006e0e9  call    cs:__imp_wcsstr
0x18006e0ef  test    rax, rax
0x18006e0f2  jz      loc_18006E17B
0x18006e0f8  lea     rsi, off_180080070; "SKYDRIVE_BRAND_NAME"
0x18006e0ff  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18006e103  mov     rsi, [rsi+r12*8]
0x18006e107  xor     r12d, r12d
0x18006e10a  inc     rdi
0x18006e10d  cmp     [rsi+rdi*2], r12w
0x18006e112  jnz     short loc_18006E10A
0x18006e114  mov     eax, 0FFFFFFFFh
0x18006e119  cmp     rdi, rax
0x18006e11c  jbe     short loc_18006E135
0x18006e11e  xor     r9d, r9d; lpArguments
0x18006e121  xor     r8d, r8d; nNumberOfArguments
0x18006e124  mov     ecx, 0C000000Dh; dwExceptionCode
0x18006e129  mov     edi, eax
0x18006e12b  lea     edx, [r9+1]; dwExceptionFlags
0x18006e12f  call    cs:__imp_RaiseException
0x18006e135  lea     r9, [rsp+2E0h+sourceString]; string
0x18006e13a  mov     edx, edi; length
0x18006e13c  lea     r8, [rsp+2E0h+var_2B0]; hstringHeader
0x18006e141  mov     rcx, rsi; sourceString
0x18006e144  call    cs:__imp_WindowsCreateStringReference
0x18006e14a  mov     r8, [rsp+2E0h+stringReplaceWith]; stringReplaceWith
0x18006e14f  lea     r9, [rsp+2E0h+newString]; newString
0x18006e154  mov     rdx, [rsp+2E0h+sourceString]; stringReplaced
0x18006e159  mov     rcx, rbx; string
0x18006e15c  mov     [rsp+2E0h+newString], r12
0x18006e161  call    cs:__imp_WindowsReplaceString
0x18006e167  mov     esi, eax
0x18006e169  test    eax, eax
0x18006e16b  js      short loc_18006E17B
0x18006e16d  mov     rcx, rbx; string
0x18006e170  mov     rbx, [rsp+2E0h+newString]
0x18006e175  call    cs:__imp_WindowsDeleteString
0x18006e17b  inc     r15d
0x18006e17e  cmp     r15d, 3
0x18006e182  jb      loc_18006E0C2
0x18006e188  test    esi, esi
0x18006e18a  js      short loc_18006E1A4
0x18006e18c  xor     edx, edx; length
0x18006e18e  mov     rcx, rbx; string
0x18006e191  call    cs:__imp_WindowsGetStringRawBuffer
0x18006e197  mov     rcx, rax; unsigned __int16 *
0x18006e19a  mov     rdx, r13; unsigned __int16 **
0x18006e19d  call    ?CoAllocString@@YAJPEBGPEAPEAG@Z; CoAllocString(ushort const *,ushort * *)
0x18006e1a2  mov     esi, eax
0x18006e1a4  test    rbx, rbx
0x18006e1a7  jz      short loc_18006E1C0
0x18006e1a9  mov     rcx, rbx; string
0x18006e1ac  call    cs:__imp_WindowsDeleteString
0x18006e1b2  jmp     short loc_18006E1C0
0x18006e1b4  mov     esi, 80004003h
0x18006e1b9  jmp     short loc_18006E1C0
0x18006e1bb  mov     r14, [rsp+2E0h+sourceString]
0x18006e1c0  test    r14, r14
0x18006e1c3  jz      short loc_18006E1CE
0x18006e1c5  mov     rcx, r14; pv
0x18006e1c8  call    cs:__imp_CoTaskMemFree
0x18006e1ce  mov     eax, esi
0x18006e1d0  mov     rcx, [rbp+1E0h+var_40]
0x18006e1d7  xor     rcx, rsp; StackCookie
0x18006e1da  call    __security_check_cookie
0x18006e1df  mov     rbx, [rsp+2E0h+arg_10]
0x18006e1e7  add     rsp, 2B0h
0x18006e1ee  pop     r15
0x18006e1f0  pop     r14
0x18006e1f2  pop     r13
0x18006e1f4  pop     r12
0x18006e1f6  pop     rdi
0x18006e1f7  pop     rsi
0x18006e1f8  pop     rbp
0x18006e1f9  retn
```
