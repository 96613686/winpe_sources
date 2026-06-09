# CWshShell::RegWrite(ushort *,tagVARIANT *,tagVARIANT *)

- ea: `0x180003af0`
- end: `0x180003db4`
- name: `?RegWrite@CWshShell@@UEAAJPEAGPEAUtagVARIANT@@1@Z`
- size: `708`
- prototype: `int(CWshShell *__hidden this, unsigned __int16 *, struct tagVARIANT *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x1800032e0`
- `0x180003af0`
- `0x180003dbc`
- `0x180005730`
- `0x180005938`
- `0x180005d20`
- `0x180010250`
- `0x1800102e0`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180003d11`
- `OLEAUT32!__imp_SysFreeString` at `0x180003d11`
- `ADVAPI32!RegSetValueExA` at `0x180003d45`
- `ADVAPI32!RegSetValueExA` at `0x180003d45`
- `ADVAPI32!RegCloseKey` at `0x180003c88`
- `ADVAPI32!RegCloseKey` at `0x180003d51`
- `ADVAPI32!RegCloseKey` at `0x180003c88`
- `ADVAPI32!RegCloseKey` at `0x180003d51`
- `KERNEL32!WideCharToMultiByte` at `0x180003b70`
- `KERNEL32!WideCharToMultiByte` at `0x180003bc5`
- `KERNEL32!WideCharToMultiByte` at `0x180003cba`
- `KERNEL32!WideCharToMultiByte` at `0x180003d08`
- `KERNEL32!WideCharToMultiByte` at `0x180003b70`
- `KERNEL32!WideCharToMultiByte` at `0x180003bc5`
- `KERNEL32!WideCharToMultiByte` at `0x180003cba`
- `KERNEL32!WideCharToMultiByte` at `0x180003d08`

## string_xrefs

- `0x180003d76`: `WshShell.RegWrite`

## pseudocode

```c
__int64 __fastcall CWshShell::RegWrite(
        CWshShell *this,
        unsigned __int16 *a2,
        struct tagVARIANT *a3,
        struct tagVARIANT *a4)
{
  __int64 result; // rax
  __int64 v7; // rdi
  int v8; // eax
  unsigned __int64 cbMultiByte; // rdx
  __int64 v10; // rax
  void *v11; // rsp
  DWORD v12; // ebx
  LSTATUS v13; // r15d
  LSTATUS v14; // ebx
  const BYTE *p_bVal; // rsi
  WCHAR *v16; // rbx
  int v17; // eax
  unsigned __int64 v18; // rdx
  __int64 v19; // rax
  void *v20; // rsp
  CHAR MultiByteStr[4]; // [rsp+40h] [rbp+0h] BYREF
  BYTE Data[4]; // [rsp+44h] [rbp+4h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+8h] BYREF
  LPCWCH lpWideCharStr; // [rsp+50h] [rbp+10h] BYREF
  LPCSTR lpValueName; // [rsp+58h] [rbp+18h] BYREF

  if ( !a2 || !a3 || !a4 )
    return 2147500035LL;
  *(_DWORD *)MultiByteStr = 0;
  result = get_reg_type(a4, MultiByteStr);
  if ( (int)result < 0 )
    return result;
  v7 = -1;
  v8 = WideCharToMultiByte(0, 0, a2, -1, 0, 0, 0, 0);
  cbMultiByte = v8;
  if ( !v8 )
    goto LABEL_38;
  v10 = v8 + 15LL;
  if ( cbMultiByte + 15 < cbMultiByte )
    v10 = 0xFFFFFFFFFFFFFF0LL;
  v11 = alloca(v10 & 0xFFFFFFFFFFFFFFF0uLL);
  WideCharToMultiByte(0, 0, a2, -1, MultiByteStr, cbMultiByte, 0, 0);
  if ( MultiByteStr )
  {
    v12 = 1;
    hKey = 0;
    lpValueName = 0;
    v13 = parse_key((unsigned __int8 *)MultiByteStr, 2u, &hKey, (const unsigned __int8 **)&lpValueName, 1);
    if ( v13 >= 0 )
    {
      *(_DWORD *)Data = 0;
      switch ( *(_DWORD *)MultiByteStr )
      {
        case 1:
        case 2:
          lpWideCharStr = 0;
          v14 = Variant_BSTR(a3, (unsigned __int16 **)&lpWideCharStr);
          if ( v14 < 0 )
            goto LABEL_25;
          v16 = (WCHAR *)lpWideCharStr;
          p_bVal = 0;
          v17 = WideCharToMultiByte(0, 0, lpWideCharStr, -1, 0, 0, 0, 0);
          v18 = v17;
          if ( v17 )
          {
            v19 = v17 + 15LL;
            if ( v18 + 15 < v18 )
              v19 = 0xFFFFFFFFFFFFFF0LL;
            v20 = alloca(v19 & 0xFFFFFFFFFFFFFFF0uLL);
            p_bVal = (const BYTE *)MultiByteStr;
            WideCharToMultiByte(0, 0, v16, -1, MultiByteStr, v18, 0, 0);
          }
          SysFreeString(v16);
          if ( p_bVal )
          {
            do
              ++v7;
            while ( p_bVal[v7] );
          }
          else
          {
            LODWORD(v7) = 0;
          }
          v12 = v7 + 1;
          break;
        case 3:
          switch ( a3->vt )
          {
            case 2u:
              v12 = 2;
              break;
            case 3u:
              v12 = 4;
              break;
            case 0x11u:
              break;
            default:
              v14 = -2147352571;
              goto LABEL_25;
          }
          p_bVal = &a3->bVal;
          break;
        case 4:
          v14 = Variant_I4(a3, (unsigned int *)Data);
          if ( v14 < 0 )
            goto LABEL_25;
          v12 = 4;
          p_bVal = Data;
          break;
        default:
          v14 = -2147418113;
LABEL_25:
          RegCloseKey(hKey);
          return (unsigned int)v14;
      }
      v14 = RegSetValueExA(hKey, lpValueName, 0, *(DWORD *)MultiByteStr, p_bVal, v12);
      RegCloseKey(hKey);
      if ( v14 > 0 )
        return (unsigned __int16)v14 | 0x80070000;
      return (unsigned int)v14;
    }
  }
  else
  {
LABEL_38:
    v13 = -2147024809;
  }
  Signal_Exception(&IID_IWshEnvironment, L"WshShell.RegWrite", 0x100Eu, a2);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180003af0  push    rbp
0x180003af2  push    rbx
0x180003af3  push    rsi
0x180003af4  push    rdi
0x180003af5  push    r12
0x180003af7  push    r14
0x180003af9  push    r15
0x180003afb  sub     rsp, 70h
0x180003aff  lea     rbp, [rsp+40h]
0x180003b04  mov     rax, cs:__security_cookie
0x180003b0b  xor     rax, rbp
0x180003b0e  mov     [rbp+60h+var_40], rax
0x180003b12  xor     r12d, r12d
0x180003b15  mov     rsi, r8
0x180003b18  mov     r14, rdx
0x180003b1b  test    rdx, rdx
0x180003b1e  jz      loc_180003D94
0x180003b24  test    r8, r8
0x180003b27  jz      loc_180003D94
0x180003b2d  test    r9, r9
0x180003b30  jz      loc_180003D94
0x180003b36  lea     rdx, [rbp+60h+MultiByteStr]
0x180003b3a  mov     dword ptr [rbp+60h+MultiByteStr], r12d
0x180003b3e  mov     rcx, r9
0x180003b41  call    get_reg_type
0x180003b46  test    eax, eax
0x180003b48  js      loc_180003D99
0x180003b4e  mov     [rsp+0A0h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x180003b53  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180003b57  mov     [rsp+0A0h+lpDefaultChar], r12; lpDefaultChar
0x180003b5c  mov     r9d, edi; cchWideChar
0x180003b5f  mov     [rsp+0A0h+cbMultiByte], r12d; cbMultiByte
0x180003b64  mov     r8, r14; lpWideCharStr
0x180003b67  xor     edx, edx; dwFlags
0x180003b69  mov     [rsp+0A0h+lpMultiByteStr], r12; lpMultiByteStr
0x180003b6e  xor     ecx, ecx; CodePage
0x180003b70  call    cs:__imp_WideCharToMultiByte
0x180003b76  movsxd  rdx, eax
0x180003b79  test    eax, eax
0x180003b7b  jz      loc_180003D6D
0x180003b81  lea     rax, [rdx+0Fh]
0x180003b85  mov     r8, 0FFFFFFFFFFFFFF0h
0x180003b8f  cmp     rax, rdx
0x180003b92  ja      short loc_180003B97
0x180003b94  mov     rax, r8
0x180003b97  and     rax, 0FFFFFFFFFFFFFFF0h
0x180003b9b  call    _alloca_probe
0x180003ba0  sub     rsp, rax
0x180003ba3  mov     r9d, edi; cchWideChar
0x180003ba6  mov     r8, r14; lpWideCharStr
0x180003ba9  xor     ecx, ecx; CodePage
0x180003bab  mov     [rsp+0A0h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x180003bb0  lea     r15, [rsp+0A0h+MultiByteStr]
0x180003bb5  mov     [rsp+0A0h+lpDefaultChar], r12; lpDefaultChar
0x180003bba  mov     [rsp+0A0h+cbMultiByte], edx; cbMultiByte
0x180003bbe  xor     edx, edx; dwFlags
0x180003bc0  mov     [rsp+0A0h+lpMultiByteStr], r15; lpMultiByteStr
0x180003bc5  call    cs:__imp_WideCharToMultiByte
0x180003bcb  test    r15, r15
0x180003bce  jz      loc_180003D6D
0x180003bd4  mov     ebx, 1
0x180003bd9  mov     [rbp+60h+hKey], r12
0x180003bdd  lea     r9, [rbp+60h+lpValueName]
0x180003be1  mov     [rbp+60h+lpValueName], r12
0x180003be5  lea     r8, [rbp+60h+hKey]
0x180003be9  mov     dword ptr [rsp+0A0h+lpMultiByteStr], ebx; int
0x180003bed  mov     rcx, r15; Str1
0x180003bf0  lea     edx, [rbx+1]; samDesired
0x180003bf3  call    parse_key
0x180003bf8  mov     r15d, eax
0x180003bfb  test    eax, eax
0x180003bfd  js      loc_180003D73
0x180003c03  mov     eax, dword ptr [rbp+60h+MultiByteStr]
0x180003c06  mov     dword ptr [rbp+60h+Data], r12d
0x180003c0a  sub     eax, ebx
0x180003c0c  jz      short loc_180003C6E
0x180003c0e  sub     eax, ebx
0x180003c10  jz      short loc_180003C6E
0x180003c12  sub     eax, ebx
0x180003c14  jz      short loc_180003C41
0x180003c16  cmp     eax, ebx
0x180003c18  jz      short loc_180003C21
0x180003c1a  mov     ebx, 8000FFFFh
0x180003c1f  jmp     short loc_180003C84
0x180003c21  lea     rdx, [rbp+60h+Data]; unsigned int *
0x180003c25  mov     rcx, rsi; pvarSrc
0x180003c28  call    ?Variant_I4@@YAJPEAUtagVARIANT@@PEAK@Z; Variant_I4(tagVARIANT *,ulong *)
0x180003c2d  mov     ebx, eax
0x180003c2f  test    eax, eax
0x180003c31  js      short loc_180003C84
0x180003c33  mov     ebx, 4
0x180003c38  lea     rsi, [rbp+60h+Data]
0x180003c3c  jmp     loc_180003D2D
0x180003c41  movzx   ecx, word ptr [rsi]
0x180003c44  sub     ecx, 2
0x180003c47  jz      short loc_180003C60
0x180003c49  sub     ecx, ebx
0x180003c4b  jz      short loc_180003C59
0x180003c4d  cmp     ecx, 0Eh
0x180003c50  jz      short loc_180003C65
0x180003c52  mov     ebx, 80020005h
0x180003c57  jmp     short loc_180003C84
0x180003c59  mov     ebx, 4
0x180003c5e  jmp     short loc_180003C65
0x180003c60  mov     ebx, 2
0x180003c65  add     rsi, 8
0x180003c69  jmp     loc_180003D2D
0x180003c6e  lea     rdx, [rbp+60h+lpWideCharStr]; unsigned __int16 **
0x180003c72  mov     [rbp+60h+lpWideCharStr], r12
0x180003c76  mov     rcx, rsi; pvarSrc
0x180003c79  call    ?Variant_BSTR@@YAJPEAUtagVARIANT@@PEAPEAG@Z; Variant_BSTR(tagVARIANT *,ushort * *)
0x180003c7e  mov     ebx, eax
0x180003c80  test    eax, eax
0x180003c82  jns     short loc_180003C95
0x180003c84  mov     rcx, [rbp+60h+hKey]; hKey
0x180003c88  call    cs:__imp_RegCloseKey
0x180003c8e  mov     eax, ebx
0x180003c90  jmp     loc_180003D99
0x180003c95  mov     rbx, [rbp+60h+lpWideCharStr]
0x180003c99  mov     r9d, edi; cchWideChar
0x180003c9c  mov     [rsp+0A0h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x180003ca1  mov     r8, rbx; lpWideCharStr
0x180003ca4  mov     [rsp+0A0h+lpDefaultChar], r12; lpDefaultChar
0x180003ca9  xor     edx, edx; dwFlags
0x180003cab  mov     [rsp+0A0h+cbMultiByte], r12d; cbMultiByte
0x180003cb0  xor     ecx, ecx; CodePage
0x180003cb2  mov     [rsp+0A0h+lpMultiByteStr], r12; lpMultiByteStr
0x180003cb7  mov     rsi, r12
0x180003cba  call    cs:__imp_WideCharToMultiByte
0x180003cc0  movsxd  rdx, eax
0x180003cc3  test    eax, eax
0x180003cc5  jz      short loc_180003D0E
0x180003cc7  lea     rax, [rdx+0Fh]
0x180003ccb  cmp     rax, rdx
0x180003cce  ja      short loc_180003CDA
0x180003cd0  mov     rax, 0FFFFFFFFFFFFFF0h
0x180003cda  and     rax, 0FFFFFFFFFFFFFFF0h
0x180003cde  call    _alloca_probe
0x180003ce3  sub     rsp, rax
0x180003ce6  mov     r9d, edi; cchWideChar
0x180003ce9  mov     r8, rbx; lpWideCharStr
0x180003cec  xor     ecx, ecx; CodePage
0x180003cee  mov     [rsp+0A0h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x180003cf3  lea     rsi, [rsp+0A0h+MultiByteStr]
0x180003cf8  mov     [rsp+0A0h+lpDefaultChar], r12; lpDefaultChar
0x180003cfd  mov     [rsp+0A0h+cbMultiByte], edx; cbMultiByte
0x180003d01  xor     edx, edx; dwFlags
0x180003d03  mov     [rsp+0A0h+lpMultiByteStr], rsi; lpMultiByteStr
0x180003d08  call    cs:__imp_WideCharToMultiByte
0x180003d0e  mov     rcx, rbx; bstrString
0x180003d11  call    cs:__imp_SysFreeString
0x180003d17  test    rsi, rsi
0x180003d1a  jz      short loc_180003D27
0x180003d1c  inc     rdi
0x180003d1f  cmp     [rsi+rdi], r12b
0x180003d23  jnz     short loc_180003D1C
0x180003d25  jmp     short loc_180003D2A
0x180003d27  mov     rdi, r12
0x180003d2a  lea     ebx, [rdi+1]
0x180003d2d  mov     r9d, dword ptr [rbp+60h+MultiByteStr]; dwType
0x180003d31  xor     r8d, r8d; Reserved
0x180003d34  mov     rdx, [rbp+60h+lpValueName]; lpValueName
0x180003d38  mov     rcx, [rbp+60h+hKey]; hKey
0x180003d3c  mov     [rsp+0A0h+cbMultiByte], ebx; cbData
0x180003d40  mov     [rsp+0A0h+lpMultiByteStr], rsi; lpData
0x180003d45  call    cs:__imp_RegSetValueExA
0x180003d4b  mov     rcx, [rbp+60h+hKey]; hKey
0x180003d4f  mov     ebx, eax
0x180003d51  call    cs:__imp_RegCloseKey
0x180003d57  test    ebx, ebx
0x180003d59  jle     loc_180003C8E
0x180003d5f  movzx   ebx, bx
0x180003d62  or      ebx, 80070000h
0x180003d68  jmp     loc_180003C8E
0x180003d6d  mov     r15d, 80070057h
0x180003d73  mov     r9, r14
0x180003d76  lea     rdx, aWshshellRegwri; "WshShell.RegWrite"
0x180003d7d  mov     r8d, 100Eh; unsigned int
0x180003d83  lea     rcx, IID_IWshEnvironment; struct _GUID *
0x180003d8a  call    ?Signal_Exception@@YAJAEBU_GUID@@PEBGIZZ; Signal_Exception(_GUID const &,ushort const *,uint,...)
0x180003d8f  mov     eax, r15d
0x180003d92  jmp     short loc_180003D99
0x180003d94  mov     eax, 80004003h
0x180003d99  mov     rcx, [rbp+60h+var_40]
0x180003d9d  xor     rcx, rbp; StackCookie
0x180003da0  call    __security_check_cookie
0x180003da5  lea     rsp, [rbp+30h]
0x180003da9  pop     r15
0x180003dab  pop     r14
0x180003dad  pop     r12
0x180003daf  pop     rdi
0x180003db0  pop     rsi
0x180003db1  pop     rbx
0x180003db2  pop     rbp
0x180003db3  retn
```
