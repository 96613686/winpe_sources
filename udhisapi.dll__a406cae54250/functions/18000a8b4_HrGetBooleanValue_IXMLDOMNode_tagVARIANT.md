# HrGetBooleanValue(IXMLDOMNode *,tagVARIANT *)

- ea: `0x18000a8b4`
- end: `0x18000a9af`
- name: `?HrGetBooleanValue@@YAJPEAUIXMLDOMNode@@PEAUtagVARIANT@@@Z`
- size: `251`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000afb4`

## callees

- `0x1800024c4`
- `0x18000a8b4`
- `0x18000af2c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000a8f2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000a908`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000a91e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000a934`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000a8f2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000a908`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000a91e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000a934`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a965`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a965`

## pseudocode

```c
__int64 __fastcall HrGetBooleanValue(struct IXMLDOMNode *a1, struct tagVARIANT *a2)
{
  int TextValueFromElement; // edi
  BSTR v4; // rcx
  BSTR bstrString; // [rsp+40h] [rbp+18h] BYREF

  bstrString = 0;
  TextValueFromElement = HrGetTextValueFromElement(a1, &bstrString);
  if ( !TextValueFromElement )
  {
    v4 = bstrString;
    a2->vt = 11;
    if ( (unsigned int)_o__wcsicmp(v4, L"yes") && (unsigned int)_o__wcsicmp(bstrString, L"true") )
    {
      if ( (unsigned int)_o__wcsicmp(bstrString, L"no") && (unsigned int)_o__wcsicmp(bstrString, L"false") )
      {
        TextValueFromElement = -2147467259;
        a2->vt = 0;
      }
      else
      {
        a2->iVal = 0;
      }
    }
    else
    {
      a2->iVal = -1;
    }
  }
  if ( bstrString )
    SysFreeString(bstrString);
  if ( TextValueFromElement < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids,
      (unsigned int)TextValueFromElement);
  }
  return (unsigned int)TextValueFromElement;
}

```

## disassembly

```asm
0x18000a8b4  mov     rax, rsp
0x18000a8b7  mov     [rax+8], rbp
0x18000a8bb  mov     [rax+10h], rsi
0x18000a8bf  push    rdi
0x18000a8c0  sub     rsp, 20h
0x18000a8c4  mov     rsi, rdx
0x18000a8c7  mov     qword ptr [rax+18h], 0
0x18000a8cf  lea     rdx, [rax+18h]; unsigned __int16 **
0x18000a8d3  call    ?HrGetTextValueFromElement@@YAJPEAUIXMLDOMNode@@PEAPEAG@Z; HrGetTextValueFromElement(IXMLDOMNode *,ushort * *)
0x18000a8d8  mov     edi, eax
0x18000a8da  mov     ebp, 0Bh
0x18000a8df  test    eax, eax
0x18000a8e1  jnz     short loc_18000A958
0x18000a8e3  mov     rcx, [rsp+28h+bstrString]
0x18000a8e8  lea     rdx, aYes; "yes"
0x18000a8ef  mov     [rsi], bp
0x18000a8f2  call    cs:__imp__o__wcsicmp
0x18000a8f8  test    eax, eax
0x18000a8fa  jz      short loc_18000A952
0x18000a8fc  mov     rcx, [rsp+28h+bstrString]
0x18000a901  lea     rdx, aTrue; "true"
0x18000a908  call    cs:__imp__o__wcsicmp
0x18000a90e  test    eax, eax
0x18000a910  jz      short loc_18000A952
0x18000a912  mov     rcx, [rsp+28h+bstrString]
0x18000a917  lea     rdx, aNo; "no"
0x18000a91e  call    cs:__imp__o__wcsicmp
0x18000a924  test    eax, eax
0x18000a926  jz      short loc_18000A94A
0x18000a928  mov     rcx, [rsp+28h+bstrString]
0x18000a92d  lea     rdx, aFalse; "false"
0x18000a934  call    cs:__imp__o__wcsicmp
0x18000a93a  test    eax, eax
0x18000a93c  jz      short loc_18000A94A
0x18000a93e  xor     eax, eax
0x18000a940  mov     edi, 80004005h
0x18000a945  mov     [rsi], ax
0x18000a948  jmp     short loc_18000A958
0x18000a94a  xor     eax, eax
0x18000a94c  mov     [rsi+8], ax
0x18000a950  jmp     short loc_18000A958
0x18000a952  mov     word ptr [rsi+8], 0FFFFh
0x18000a958  cmp     [rsp+28h+bstrString], 0
0x18000a95e  jz      short loc_18000A96B
0x18000a960  mov     rcx, [rsp+28h+bstrString]; bstrString
0x18000a965  call    cs:__imp_SysFreeString
0x18000a96b  test    edi, edi
0x18000a96d  jns     short loc_18000A99D
0x18000a96f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a976  lea     rax, WPP_GLOBAL_Control
0x18000a97d  cmp     rcx, rax
0x18000a980  jz      short loc_18000A99D
0x18000a982  test    byte ptr [rcx+1Ch], 1
0x18000a986  jz      short loc_18000A99D
0x18000a988  mov     rcx, [rcx+10h]
0x18000a98c  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x18000a993  mov     edx, ebp
0x18000a995  mov     r9d, edi
0x18000a998  call    WPP_SF_d
0x18000a99d  mov     rbp, [rsp+28h+arg_0]
0x18000a9a2  mov     eax, edi
0x18000a9a4  mov     rsi, [rsp+28h+arg_8]
0x18000a9a9  add     rsp, 20h
0x18000a9ad  pop     rdi
0x18000a9ae  retn
```
