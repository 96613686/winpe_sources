# HrGetBase64DecodedValue(IXMLDOMNode *,tagVARIANT *)

- ea: `0x18000a6f4`
- end: `0x18000a8ad`
- name: `?HrGetBase64DecodedValue@@YAJPEAUIXMLDOMNode@@PEAUtagVARIANT@@@Z`
- size: `441`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000afb4`

## callees

- `0x1800024c4`
- `0x18000a6f4`
- `0x18000af2c`
- `0x18000bac1`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a85d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a85d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000a782`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000a782`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a75f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a7c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a75f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a7c6`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a84f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a84f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000a837`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000a837`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18000a803`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18000a803`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000a822`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000a822`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18000a7e6`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18000a7e6`
- `CRYPT32!CryptStringToBinaryW` at `0x18000a750`
- `CRYPT32!CryptStringToBinaryW` at `0x18000a7bc`
- `CRYPT32!CryptStringToBinaryW` at `0x18000a750`
- `CRYPT32!CryptStringToBinaryW` at `0x18000a7bc`

## pseudocode

```c
__int64 __fastcall HrGetBase64DecodedValue(struct IXMLDOMNode *a1, struct tagVARIANT *a2)
{
  BYTE *v3; // rsi
  int TextValueFromElement; // ebx
  signed int LastError; // eax
  signed int v6; // eax
  SAFEARRAY *Vector; // rax
  SAFEARRAY *v8; // rdi
  void *ppvData; // [rsp+40h] [rbp-10h] BYREF
  DWORD cElements; // [rsp+80h] [rbp+30h] BYREF
  LPCWSTR pszString; // [rsp+88h] [rbp+38h] BYREF

  pszString = 0;
  cElements = 0;
  v3 = 0;
  TextValueFromElement = HrGetTextValueFromElement(a1, (unsigned __int16 **)&pszString);
  if ( !TextValueFromElement )
  {
    if ( CryptStringToBinaryW(pszString, 0, 1u, 0, &cElements, 0, 0) )
      goto LABEL_7;
    LastError = GetLastError();
    TextValueFromElement = LastError;
    if ( LastError == 234 )
      goto LABEL_7;
    if ( LastError > 0 )
      TextValueFromElement = (unsigned __int16)LastError | 0x80070000;
    if ( !TextValueFromElement )
    {
LABEL_7:
      v3 = (BYTE *)malloc(cElements);
      if ( !v3 )
        goto LABEL_16;
      if ( CryptStringToBinaryW(pszString, 0, 1u, v3, &cElements, 0, 0) )
        goto LABEL_12;
      v6 = GetLastError();
      TextValueFromElement = v6;
      if ( v6 > 0 )
        TextValueFromElement = (unsigned __int16)v6 | 0x80070000;
      if ( !TextValueFromElement )
      {
LABEL_12:
        Vector = SafeArrayCreateVector(0x11u, 0, cElements);
        v8 = Vector;
        if ( Vector )
        {
          ppvData = 0;
          TextValueFromElement = SafeArrayAccessData(Vector, &ppvData);
          if ( TextValueFromElement )
          {
            SafeArrayDestroy(v8);
          }
          else
          {
            memcpy_0(ppvData, v3, cElements);
            SafeArrayUnaccessData(v8);
            a2->llVal = (LONGLONG)v8;
            a2->vt = 8209;
          }
          goto LABEL_17;
        }
LABEL_16:
        TextValueFromElement = -2147024882;
      }
    }
  }
LABEL_17:
  if ( pszString )
    SysFreeString((BSTR)pszString);
  if ( v3 )
    free(v3);
  if ( TextValueFromElement < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids,
      (unsigned int)TextValueFromElement);
  }
  return (unsigned int)TextValueFromElement;
}

```

## disassembly

```asm
0x18000a6f4  mov     [rsp-18h+arg_0], rbx
0x18000a6f9  mov     [rsp-18h+arg_8], rsi
0x18000a6fe  push    rbp
0x18000a6ff  push    rdi
0x18000a700  push    r15
0x18000a702  mov     rbp, rsp
0x18000a705  sub     rsp, 50h
0x18000a709  mov     r15, rdx
0x18000a70c  mov     [rbp+pszString], 0
0x18000a714  lea     rdx, [rbp+pszString]; unsigned __int16 **
0x18000a718  mov     [rbp+cElements], 0
0x18000a71f  xor     esi, esi
0x18000a721  call    ?HrGetTextValueFromElement@@YAJPEAUIXMLDOMNode@@PEAPEAG@Z; HrGetTextValueFromElement(IXMLDOMNode *,ushort * *)
0x18000a726  mov     ebx, eax
0x18000a728  test    eax, eax
0x18000a72a  jnz     loc_18000A844
0x18000a730  mov     rcx, [rbp+pszString]; pszString
0x18000a734  lea     rax, [rbp+cElements]
0x18000a738  mov     [rsp+50h+pdwFlags], rsi; pdwFlags
0x18000a73d  lea     r8d, [rsi+1]; dwFlags
0x18000a741  mov     [rsp+50h+pdwSkip], rsi; pdwSkip
0x18000a746  xor     r9d, r9d; pbBinary
0x18000a749  xor     edx, edx; cchString
0x18000a74b  mov     [rsp+50h+pcbBinary], rax; pcbBinary
0x18000a750  call    cs:__imp_CryptStringToBinaryW
0x18000a756  mov     edi, 80070000h
0x18000a75b  test    eax, eax
0x18000a75d  jnz     short loc_18000A77F
0x18000a75f  call    cs:__imp_GetLastError
0x18000a765  mov     ebx, eax
0x18000a767  cmp     eax, 0EAh
0x18000a76c  jz      short loc_18000A77F
0x18000a76e  test    eax, eax
0x18000a770  jle     short loc_18000A777
0x18000a772  movzx   ebx, ax
0x18000a775  or      ebx, edi
0x18000a777  test    ebx, ebx
0x18000a779  jnz     loc_18000A844
0x18000a77f  mov     ecx, [rbp+cElements]; Size
0x18000a782  call    cs:__imp_malloc
0x18000a788  mov     rsi, rax
0x18000a78b  test    rax, rax
0x18000a78e  jz      loc_18000A83F
0x18000a794  mov     rcx, [rbp+pszString]; pszString
0x18000a798  lea     rax, [rbp+cElements]
0x18000a79c  xor     edx, edx; cchString
0x18000a79e  mov     [rsp+50h+pdwFlags], 0; pdwFlags
0x18000a7a7  mov     [rsp+50h+pdwSkip], 0; pdwSkip
0x18000a7b0  mov     r9, rsi; pbBinary
0x18000a7b3  mov     [rsp+50h+pcbBinary], rax; pcbBinary
0x18000a7b8  lea     r8d, [rdx+1]; dwFlags
0x18000a7bc  call    cs:__imp_CryptStringToBinaryW
0x18000a7c2  test    eax, eax
0x18000a7c4  jnz     short loc_18000A7DB
0x18000a7c6  call    cs:__imp_GetLastError
0x18000a7cc  mov     ebx, eax
0x18000a7ce  test    eax, eax
0x18000a7d0  jle     short loc_18000A7D7
0x18000a7d2  movzx   ebx, ax
0x18000a7d5  or      ebx, edi
0x18000a7d7  test    ebx, ebx
0x18000a7d9  jnz     short loc_18000A844
0x18000a7db  mov     r8d, [rbp+cElements]; cElements
0x18000a7df  mov     ecx, 11h; vt
0x18000a7e4  xor     edx, edx; lLbound
0x18000a7e6  call    cs:__imp_SafeArrayCreateVector
0x18000a7ec  mov     rdi, rax
0x18000a7ef  test    rax, rax
0x18000a7f2  jz      short loc_18000A83F
0x18000a7f4  lea     rdx, [rbp+ppvData]; ppvData
0x18000a7f8  mov     [rbp+ppvData], 0
0x18000a800  mov     rcx, rax; psa
0x18000a803  call    cs:__imp_SafeArrayAccessData
0x18000a809  mov     ebx, eax
0x18000a80b  test    eax, eax
0x18000a80d  jnz     short loc_18000A834
0x18000a80f  mov     r8d, [rbp+cElements]; Size
0x18000a813  mov     rdx, rsi; Src
0x18000a816  mov     rcx, [rbp+ppvData]; void *
0x18000a81a  call    memcpy_0
0x18000a81f  mov     rcx, rdi; psa
0x18000a822  call    cs:__imp_SafeArrayUnaccessData
0x18000a828  mov     [r15+8], rdi
0x18000a82c  mov     word ptr [r15], 2011h
0x18000a832  jmp     short loc_18000A844
0x18000a834  mov     rcx, rdi; psa
0x18000a837  call    cs:__imp_SafeArrayDestroy
0x18000a83d  jmp     short loc_18000A844
0x18000a83f  mov     ebx, 8007000Eh
0x18000a844  cmp     [rbp+pszString], 0
0x18000a849  jz      short loc_18000A855
0x18000a84b  mov     rcx, [rbp+pszString]; bstrString
0x18000a84f  call    cs:__imp_SysFreeString
0x18000a855  test    rsi, rsi
0x18000a858  jz      short loc_18000A863
0x18000a85a  mov     rcx, rsi; Block
0x18000a85d  call    cs:__imp_free
0x18000a863  test    ebx, ebx
0x18000a865  jns     short loc_18000A898
0x18000a867  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a86e  lea     rax, WPP_GLOBAL_Control
0x18000a875  cmp     rcx, rax
0x18000a878  jz      short loc_18000A898
0x18000a87a  test    byte ptr [rcx+1Ch], 1
0x18000a87e  jz      short loc_18000A898
0x18000a880  mov     rcx, [rcx+10h]
0x18000a884  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x18000a88b  mov     edx, 0Ah
0x18000a890  mov     r9d, ebx
0x18000a893  call    WPP_SF_d
0x18000a898  mov     rsi, [rsp+50h+arg_8]
0x18000a89d  mov     eax, ebx
0x18000a89f  mov     rbx, [rsp+50h+arg_0]
0x18000a8a4  add     rsp, 50h
0x18000a8a8  pop     r15
0x18000a8aa  pop     rdi
0x18000a8ab  pop     rbp
0x18000a8ac  retn
```
