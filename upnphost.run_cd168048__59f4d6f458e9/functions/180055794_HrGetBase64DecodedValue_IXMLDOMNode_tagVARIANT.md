# HrGetBase64DecodedValue(IXMLDOMNode *,tagVARIANT *)

- ea: `0x180055794`
- end: `0x18005598d`
- name: `?HrGetBase64DecodedValue@@YAJPEAUIXMLDOMNode@@PEAUtagVARIANT@@@Z`
- size: `505`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x18001eac0`

## callees

- `0x18000c8e0`
- `0x18001ecac`
- `0x18003b1cc`
- `0x180055794`
- `0x180057cac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18005582e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18005582e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055805`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005587e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055805`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005587e`
- `OLEAUT32!__imp_SysFreeString` at `0x180055929`
- `OLEAUT32!__imp_SysFreeString` at `0x180055929`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18005590b`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18005590b`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800558cb`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800558cb`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800558f0`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800558f0`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800558a8`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800558a8`
- `CRYPT32!CryptStringToBinaryW` at `0x1800557f0`
- `CRYPT32!CryptStringToBinaryW` at `0x18005586e`
- `CRYPT32!CryptStringToBinaryW` at `0x1800557f0`
- `CRYPT32!CryptStringToBinaryW` at `0x18005586e`

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
0x180055794  mov     [rsp-18h+arg_0], rbx
0x180055799  mov     [rsp-18h+arg_8], rsi
0x18005579e  push    rbp
0x18005579f  push    rdi
0x1800557a0  push    r15
0x1800557a2  mov     rbp, rsp
0x1800557a5  sub     rsp, 50h
0x1800557a9  mov     r15, rdx
0x1800557ac  mov     [rbp+pszString], 0
0x1800557b4  lea     rdx, [rbp+pszString]; unsigned __int16 **
0x1800557b8  mov     [rbp+cElements], 0
0x1800557bf  xor     esi, esi
0x1800557c1  call    ?HrGetTextValueFromElement@@YAJPEAUIXMLDOMNode@@PEAPEAG@Z; HrGetTextValueFromElement(IXMLDOMNode *,ushort * *)
0x1800557c6  mov     ebx, eax
0x1800557c8  test    eax, eax
0x1800557ca  jnz     loc_18005591E
0x1800557d0  mov     rcx, [rbp+pszString]; pszString
0x1800557d4  lea     rax, [rbp+cElements]
0x1800557d8  mov     [rsp+50h+pdwFlags], rsi; pdwFlags
0x1800557dd  lea     r8d, [rsi+1]; dwFlags
0x1800557e1  mov     [rsp+50h+pdwSkip], rsi; pdwSkip
0x1800557e6  xor     r9d, r9d; pbBinary
0x1800557e9  xor     edx, edx; cchString
0x1800557eb  mov     [rsp+50h+pcbBinary], rax; pcbBinary
0x1800557f0  call    cs:__imp_CryptStringToBinaryW
0x1800557f7  nop     dword ptr [rax+rax+00h]
0x1800557fc  mov     edi, 80070000h
0x180055801  test    eax, eax
0x180055803  jnz     short loc_18005582B
0x180055805  call    cs:__imp_GetLastError
0x18005580c  nop     dword ptr [rax+rax+00h]
0x180055811  mov     ebx, eax
0x180055813  cmp     eax, 0EAh
0x180055818  jz      short loc_18005582B
0x18005581a  test    eax, eax
0x18005581c  jle     short loc_180055823
0x18005581e  movzx   ebx, ax
0x180055821  or      ebx, edi
0x180055823  test    ebx, ebx
0x180055825  jnz     loc_18005591E
0x18005582b  mov     ecx, [rbp+cElements]; Size
0x18005582e  call    cs:__imp_malloc
0x180055835  nop     dword ptr [rax+rax+00h]
0x18005583a  mov     rsi, rax
0x18005583d  test    rax, rax
0x180055840  jz      loc_180055919
0x180055846  mov     rcx, [rbp+pszString]; pszString
0x18005584a  lea     rax, [rbp+cElements]
0x18005584e  xor     edx, edx; cchString
0x180055850  mov     [rsp+50h+pdwFlags], 0; pdwFlags
0x180055859  mov     [rsp+50h+pdwSkip], 0; pdwSkip
0x180055862  mov     r9, rsi; pbBinary
0x180055865  mov     [rsp+50h+pcbBinary], rax; pcbBinary
0x18005586a  lea     r8d, [rdx+1]; dwFlags
0x18005586e  call    cs:__imp_CryptStringToBinaryW
0x180055875  nop     dword ptr [rax+rax+00h]
0x18005587a  test    eax, eax
0x18005587c  jnz     short loc_18005589D
0x18005587e  call    cs:__imp_GetLastError
0x180055885  nop     dword ptr [rax+rax+00h]
0x18005588a  mov     ebx, eax
0x18005588c  test    eax, eax
0x18005588e  jle     short loc_180055895
0x180055890  movzx   ebx, ax
0x180055893  or      ebx, edi
0x180055895  test    ebx, ebx
0x180055897  jnz     loc_18005591E
0x18005589d  mov     r8d, [rbp+cElements]; cElements
0x1800558a1  mov     ecx, 11h; vt
0x1800558a6  xor     edx, edx; lLbound
0x1800558a8  call    cs:__imp_SafeArrayCreateVector
0x1800558af  nop     dword ptr [rax+rax+00h]
0x1800558b4  mov     rdi, rax
0x1800558b7  test    rax, rax
0x1800558ba  jz      short loc_180055919
0x1800558bc  lea     rdx, [rbp+ppvData]; ppvData
0x1800558c0  mov     [rbp+ppvData], 0
0x1800558c8  mov     rcx, rax; psa
0x1800558cb  call    cs:__imp_SafeArrayAccessData
0x1800558d2  nop     dword ptr [rax+rax+00h]
0x1800558d7  mov     ebx, eax
0x1800558d9  test    eax, eax
0x1800558db  jnz     short loc_180055908
0x1800558dd  mov     r8d, [rbp+cElements]; Size
0x1800558e1  mov     rdx, rsi; Src
0x1800558e4  mov     rcx, [rbp+ppvData]; void *
0x1800558e8  call    memcpy_0
0x1800558ed  mov     rcx, rdi; psa
0x1800558f0  call    cs:__imp_SafeArrayUnaccessData
0x1800558f7  nop     dword ptr [rax+rax+00h]
0x1800558fc  mov     [r15+8], rdi
0x180055900  mov     word ptr [r15], 2011h
0x180055906  jmp     short loc_18005591E
0x180055908  mov     rcx, rdi; psa
0x18005590b  call    cs:__imp_SafeArrayDestroy
0x180055912  nop     dword ptr [rax+rax+00h]
0x180055917  jmp     short loc_18005591E
0x180055919  mov     ebx, 8007000Eh
0x18005591e  cmp     [rbp+pszString], 0
0x180055923  jz      short loc_180055935
0x180055925  mov     rcx, [rbp+pszString]; bstrString
0x180055929  call    cs:__imp_SysFreeString
0x180055930  nop     dword ptr [rax+rax+00h]
0x180055935  test    rsi, rsi
0x180055938  jz      short loc_180055942
0x18005593a  mov     rcx, rsi; void *
0x18005593d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180055942  test    ebx, ebx
0x180055944  jns     short loc_180055977
0x180055946  mov     rcx, cs:WPP_GLOBAL_Control
0x18005594d  lea     rax, WPP_GLOBAL_Control
0x180055954  cmp     rcx, rax
0x180055957  jz      short loc_180055977
0x180055959  test    byte ptr [rcx+1Ch], 1
0x18005595d  jz      short loc_180055977
0x18005595f  mov     rcx, [rcx+10h]
0x180055963  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x18005596a  mov     edx, 0Ah
0x18005596f  mov     r9d, ebx
0x180055972  call    WPP_SF_d
0x180055977  mov     rsi, [rsp+50h+arg_8]
0x18005597c  mov     eax, ebx
0x18005597e  mov     rbx, [rsp+50h+arg_0]
0x180055983  add     rsp, 50h
0x180055987  pop     r15
0x180055989  pop     rdi
0x18005598a  pop     rbp
0x18005598b  retn
```
