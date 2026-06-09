# HrGetBase64DecodedValue(IXMLDOMNode *,tagVARIANT *)

- ea: `0x180051f94`
- end: `0x18005214c`
- name: `?HrGetBase64DecodedValue@@YAJPEAUIXMLDOMNode@@PEAUtagVARIANT@@@Z`
- size: `440`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x18000c570`

## callees

- `0x18000c744`
- `0x180018738`
- `0x180038ce4`
- `0x180051f94`
- `0x18005430c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180052022`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180052022`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051fff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052066`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051fff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052066`
- `OLEAUT32!__imp_SysFreeString` at `0x1800520ef`
- `OLEAUT32!__imp_SysFreeString` at `0x1800520ef`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800520d7`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800520d7`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800520a3`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800520a3`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800520c2`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800520c2`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180052086`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180052086`
- `CRYPT32!CryptStringToBinaryW` at `0x180051ff0`
- `CRYPT32!CryptStringToBinaryW` at `0x18005205c`
- `CRYPT32!CryptStringToBinaryW` at `0x180051ff0`
- `CRYPT32!CryptStringToBinaryW` at `0x18005205c`

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
    operator delete(v3);
  if ( TextValueFromElement < 0
    && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[14] & 1) != 0 )
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
0x180051f94  mov     [rsp-18h+arg_0], rbx
0x180051f99  mov     [rsp-18h+arg_8], rsi
0x180051f9e  push    rbp
0x180051f9f  push    rdi
0x180051fa0  push    r15
0x180051fa2  mov     rbp, rsp
0x180051fa5  sub     rsp, 50h
0x180051fa9  mov     r15, rdx
0x180051fac  mov     [rbp+pszString], 0
0x180051fb4  lea     rdx, [rbp+pszString]; unsigned __int16 **
0x180051fb8  mov     [rbp+cElements], 0
0x180051fbf  xor     esi, esi
0x180051fc1  call    ?HrGetTextValueFromElement@@YAJPEAUIXMLDOMNode@@PEAPEAG@Z; HrGetTextValueFromElement(IXMLDOMNode *,ushort * *)
0x180051fc6  mov     ebx, eax
0x180051fc8  test    eax, eax
0x180051fca  jnz     loc_1800520E4
0x180051fd0  mov     rcx, [rbp+pszString]; pszString
0x180051fd4  lea     rax, [rbp+cElements]
0x180051fd8  mov     [rsp+50h+pdwFlags], rsi; pdwFlags
0x180051fdd  lea     r8d, [rsi+1]; dwFlags
0x180051fe1  mov     [rsp+50h+pdwSkip], rsi; pdwSkip
0x180051fe6  xor     r9d, r9d; pbBinary
0x180051fe9  xor     edx, edx; cchString
0x180051feb  mov     [rsp+50h+pcbBinary], rax; pcbBinary
0x180051ff0  call    cs:__imp_CryptStringToBinaryW
0x180051ff6  mov     edi, 80070000h
0x180051ffb  test    eax, eax
0x180051ffd  jnz     short loc_18005201F
0x180051fff  call    cs:__imp_GetLastError
0x180052005  mov     ebx, eax
0x180052007  cmp     eax, 0EAh
0x18005200c  jz      short loc_18005201F
0x18005200e  test    eax, eax
0x180052010  jle     short loc_180052017
0x180052012  movzx   ebx, ax
0x180052015  or      ebx, edi
0x180052017  test    ebx, ebx
0x180052019  jnz     loc_1800520E4
0x18005201f  mov     ecx, [rbp+cElements]; Size
0x180052022  call    cs:__imp_malloc
0x180052028  mov     rsi, rax
0x18005202b  test    rax, rax
0x18005202e  jz      loc_1800520DF
0x180052034  mov     rcx, [rbp+pszString]; pszString
0x180052038  lea     rax, [rbp+cElements]
0x18005203c  xor     edx, edx; cchString
0x18005203e  mov     [rsp+50h+pdwFlags], 0; pdwFlags
0x180052047  mov     [rsp+50h+pdwSkip], 0; pdwSkip
0x180052050  mov     r9, rsi; pbBinary
0x180052053  mov     [rsp+50h+pcbBinary], rax; pcbBinary
0x180052058  lea     r8d, [rdx+1]; dwFlags
0x18005205c  call    cs:__imp_CryptStringToBinaryW
0x180052062  test    eax, eax
0x180052064  jnz     short loc_18005207B
0x180052066  call    cs:__imp_GetLastError
0x18005206c  mov     ebx, eax
0x18005206e  test    eax, eax
0x180052070  jle     short loc_180052077
0x180052072  movzx   ebx, ax
0x180052075  or      ebx, edi
0x180052077  test    ebx, ebx
0x180052079  jnz     short loc_1800520E4
0x18005207b  mov     r8d, [rbp+cElements]; cElements
0x18005207f  mov     ecx, 11h; vt
0x180052084  xor     edx, edx; lLbound
0x180052086  call    cs:__imp_SafeArrayCreateVector
0x18005208c  mov     rdi, rax
0x18005208f  test    rax, rax
0x180052092  jz      short loc_1800520DF
0x180052094  lea     rdx, [rbp+ppvData]; ppvData
0x180052098  mov     [rbp+ppvData], 0
0x1800520a0  mov     rcx, rax; psa
0x1800520a3  call    cs:__imp_SafeArrayAccessData
0x1800520a9  mov     ebx, eax
0x1800520ab  test    eax, eax
0x1800520ad  jnz     short loc_1800520D4
0x1800520af  mov     r8d, [rbp+cElements]; Size
0x1800520b3  mov     rdx, rsi; Src
0x1800520b6  mov     rcx, [rbp+ppvData]; void *
0x1800520ba  call    memcpy_0
0x1800520bf  mov     rcx, rdi; psa
0x1800520c2  call    cs:__imp_SafeArrayUnaccessData
0x1800520c8  mov     [r15+8], rdi
0x1800520cc  mov     word ptr [r15], 2011h
0x1800520d2  jmp     short loc_1800520E4
0x1800520d4  mov     rcx, rdi; psa
0x1800520d7  call    cs:__imp_SafeArrayDestroy
0x1800520dd  jmp     short loc_1800520E4
0x1800520df  mov     ebx, 8007000Eh
0x1800520e4  cmp     [rbp+pszString], 0
0x1800520e9  jz      short loc_1800520F5
0x1800520eb  mov     rcx, [rbp+pszString]; bstrString
0x1800520ef  call    cs:__imp_SysFreeString
0x1800520f5  test    rsi, rsi
0x1800520f8  jz      short loc_180052102
0x1800520fa  mov     rcx, rsi; void *
0x1800520fd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180052102  test    ebx, ebx
0x180052104  jns     short loc_180052137
0x180052106  mov     rcx, cs:WPP_GLOBAL_Control
0x18005210d  lea     rax, WPP_GLOBAL_Control
0x180052114  cmp     rcx, rax
0x180052117  jz      short loc_180052137
0x180052119  test    byte ptr [rcx+1Ch], 1
0x18005211d  jz      short loc_180052137
0x18005211f  mov     rcx, [rcx+10h]
0x180052123  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x18005212a  mov     edx, 0Ah
0x18005212f  mov     r9d, ebx
0x180052132  call    WPP_SF_d
0x180052137  mov     rsi, [rsp+50h+arg_8]
0x18005213c  mov     eax, ebx
0x18005213e  mov     rbx, [rsp+50h+arg_0]
0x180052143  add     rsp, 50h
0x180052147  pop     r15
0x180052149  pop     rdi
0x18005214a  pop     rbp
0x18005214b  retn
```
