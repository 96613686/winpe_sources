# HrParseSOAPRequest(IXMLDOMNode *,tagUPNP_SOAP_REQUEST *)

- ea: `0x180005b68`
- end: `0x180005e59`
- name: `?HrParseSOAPRequest@@YAJPEAUIXMLDOMNode@@PEAUtagUPNP_SOAP_REQUEST@@@Z`
- size: `753`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, BSTR *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000512c`

## callees

- `0x180003728`
- `0x1800038ec`
- `0x180005b68`
- `0x18000abb0`
- `0x18000c010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180005d31`
- `OLEAUT32!__imp_SysFreeString` at `0x180005dd0`
- `OLEAUT32!__imp_SysFreeString` at `0x180005d31`
- `OLEAUT32!__imp_SysFreeString` at `0x180005dd0`

## pseudocode

```c
__int64 __fastcall HrParseSOAPRequest(struct IXMLDOMNode *a1, BSTR *a2, unsigned int a3)
{
  int NestedChildElement; // eax
  int v5; // ebx
  struct IXMLDOMNode *v6; // r14
  int v7; // eax
  int v8; // eax
  _QWORD *v9; // rcx
  int v10; // edx
  const char *v11; // r9
  _QWORD *v12; // rcx
  BSTR v13; // rcx
  OLECHAR *v15; // [rsp+30h] [rbp-10h] BYREF
  struct IXMLDOMNode *v16; // [rsp+38h] [rbp-8h] BYREF
  BSTR bstrString; // [rsp+70h] [rbp+30h] BYREF
  unsigned __int16 *v18; // [rsp+78h] [rbp+38h] BYREF

  v16 = 0;
  bstrString = 0;
  v18 = L"Body";
  v15 = 0;
  NestedChildElement = HrGetNestedChildElement(a1, (const unsigned __int16 *const *)&v18, a3, &v16);
  v5 = NestedChildElement;
  if ( !NestedChildElement )
  {
    v6 = v16;
    v18 = 0;
    v7 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, unsigned __int16 **))v16->lpVtbl->get_firstChild)(v16, &v18);
    v5 = v7;
    if ( v7 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          72,
          (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids,
          (unsigned int)"HrParseSOAPRequest(): Failed to get action element",
          v7);
      if ( v5 == 1 )
        v5 = -2147467259;
      goto LABEL_21;
    }
    v8 = (*(__int64 (__fastcall **)(unsigned __int16 *, BSTR *))(*(_QWORD *)v18 + 328LL))(v18, &bstrString);
    v5 = v8;
    if ( v8 < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_15;
      v10 = 71;
      v11 = "HrParseSOAPRequest(): Failed to get action name";
    }
    else
    {
      v8 = (*(__int64 (__fastcall **)(unsigned __int16 *, OLECHAR **))(*(_QWORD *)v18 + 96LL))(v18, &v15);
      v5 = v8;
      if ( v8 >= 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids, bstrString);
        goto LABEL_15;
      }
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_15:
        (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v18 + 16LL))(v18);
LABEL_21:
        ((void (__fastcall *)(struct IXMLDOMNode *))v6->lpVtbl->Release)(v6);
        v12 = WPP_GLOBAL_Control;
        goto LABEL_22;
      }
      v10 = 70;
      v11 = "HrParseSOAPRequest(): Failed to get argument list";
    }
    WPP_SF_sd(v9[2], v10, (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids, (_DWORD)v11, v8);
    goto LABEL_15;
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      73,
      (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids,
      (unsigned int)"HrParseSOAPRequest(): Failed to get Body element",
      NestedChildElement);
    v12 = WPP_GLOBAL_Control;
  }
  if ( v5 == 1 )
  {
    v5 = -2147467259;
    goto LABEL_34;
  }
LABEL_22:
  if ( v5 < 0 )
  {
LABEL_34:
    if ( bstrString )
    {
      SysFreeString(bstrString);
      v12 = WPP_GLOBAL_Control;
      bstrString = 0;
    }
    if ( v15 )
    {
      (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)v15 + 16LL))(v15);
      v12 = WPP_GLOBAL_Control;
      v15 = 0;
    }
    if ( v5 != -2147024882 )
      v5 = -2147180027;
    goto LABEL_40;
  }
  if ( *a2 )
  {
    SysFreeString(*a2);
    *a2 = 0;
  }
  v13 = a2[1];
  if ( v13 )
    (*(void (__fastcall **)(BSTR))(*(_QWORD *)v13 + 16LL))(v13);
  *a2 = bstrString;
  a2[1] = v15;
  if ( v5 )
  {
    v12 = WPP_GLOBAL_Control;
LABEL_40:
    if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 )
      WPP_SF_sd(
        v12[2],
        74,
        (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids,
        (unsigned int)"HrParseSOAPRequest(): Exiting",
        v5);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180005b68  mov     [rsp-18h+arg_0], rbx
0x180005b6d  mov     [rsp-18h+arg_8], rsi
0x180005b72  push    rbp
0x180005b73  push    rdi
0x180005b74  push    r14
0x180005b76  mov     rbp, rsp
0x180005b79  sub     rsp, 40h
0x180005b7d  mov     rsi, rdx
0x180005b80  mov     [rbp+var_8], 0
0x180005b88  lea     rax, aBody; "Body"
0x180005b8f  mov     [rbp+bstrString], 0
0x180005b97  lea     rdx, [rbp+arg_18]; unsigned __int16 **
0x180005b9b  mov     [rbp+arg_18], rax
0x180005b9f  lea     r9, [rbp+var_8]; struct IXMLDOMNode **
0x180005ba3  mov     [rbp+var_10], 0
0x180005bab  call    ?HrGetNestedChildElement@@YAJPEAUIXMLDOMNode@@PEBQEBGKPEAPEAU1@@Z; HrGetNestedChildElement(IXMLDOMNode *,ushort const * const *,ulong,IXMLDOMNode * *)
0x180005bb0  mov     ebx, eax
0x180005bb2  test    eax, eax
0x180005bb4  jnz     loc_180005D76
0x180005bba  mov     r14, [rbp+var_8]
0x180005bbe  lea     rdx, [rbp+arg_18]
0x180005bc2  mov     [rbp+arg_18], 0
0x180005bca  mov     rcx, r14
0x180005bcd  mov     rax, [r14]
0x180005bd0  mov     rax, [rax+68h]
0x180005bd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bd9  mov     ebx, eax
0x180005bdb  test    eax, eax
0x180005bdd  jnz     loc_180005CC7
0x180005be3  mov     rcx, [rbp+arg_18]
0x180005be7  lea     rdx, [rbp+bstrString]
0x180005beb  mov     rax, [rcx]
0x180005bee  mov     rax, [rax+148h]
0x180005bf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bfa  mov     ebx, eax
0x180005bfc  test    eax, eax
0x180005bfe  js      short loc_180005C7C
0x180005c00  mov     rcx, [rbp+arg_18]
0x180005c04  lea     rdx, [rbp+var_10]
0x180005c08  mov     rax, [rcx]
0x180005c0b  mov     rax, [rax+60h]
0x180005c0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c14  mov     ebx, eax
0x180005c16  test    eax, eax
0x180005c18  js      short loc_180005C55
0x180005c1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180005c21  lea     rdi, WPP_GLOBAL_Control
0x180005c28  cmp     rcx, rdi
0x180005c2b  jz      loc_180005CB5
0x180005c31  test    dword ptr [rcx+1Ch], 400h
0x180005c38  jz      short loc_180005CB5
0x180005c3a  mov     r9, [rbp+bstrString]
0x180005c3e  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x180005c45  mov     rcx, [rcx+10h]
0x180005c49  mov     edx, 45h ; 'E'
0x180005c4e  call    WPP_SF_S
0x180005c53  jmp     short loc_180005CB5
0x180005c55  mov     rcx, cs:WPP_GLOBAL_Control
0x180005c5c  lea     rdi, WPP_GLOBAL_Control
0x180005c63  cmp     rcx, rdi
0x180005c66  jz      short loc_180005CB5
0x180005c68  test    byte ptr [rcx+1Ch], 1
0x180005c6c  jz      short loc_180005CB5
0x180005c6e  mov     edx, 46h ; 'F'
0x180005c73  lea     r9, aHrparsesoapreq_1; "HrParseSOAPRequest(): Failed to get arg"...
0x180005c7a  jmp     short loc_180005CA1
0x180005c7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180005c83  lea     rdi, WPP_GLOBAL_Control
0x180005c8a  cmp     rcx, rdi
0x180005c8d  jz      short loc_180005CB5
0x180005c8f  test    byte ptr [rcx+1Ch], 1
0x180005c93  jz      short loc_180005CB5
0x180005c95  mov     edx, 47h ; 'G'
0x180005c9a  lea     r9, aHrparsesoapreq_2; "HrParseSOAPRequest(): Failed to get act"...
0x180005ca1  mov     rcx, [rcx+10h]
0x180005ca5  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x180005cac  mov     [rsp+40h+var_20], eax
0x180005cb0  call    WPP_SF_sd
0x180005cb5  mov     rcx, [rbp+arg_18]
0x180005cb9  mov     rax, [rcx]
0x180005cbc  mov     rax, [rax+10h]
0x180005cc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cc5  jmp     short loc_180005D0B
0x180005cc7  mov     rcx, cs:WPP_GLOBAL_Control
0x180005cce  lea     rdi, WPP_GLOBAL_Control
0x180005cd5  cmp     rcx, rdi
0x180005cd8  jz      short loc_180005D00
0x180005cda  test    byte ptr [rcx+1Ch], 1
0x180005cde  jz      short loc_180005D00
0x180005ce0  mov     rcx, [rcx+10h]
0x180005ce4  lea     r9, aHrparsesoapreq_3; "HrParseSOAPRequest(): Failed to get act"...
0x180005ceb  mov     edx, 48h ; 'H'
0x180005cf0  mov     [rsp+40h+var_20], ebx
0x180005cf4  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x180005cfb  call    WPP_SF_sd
0x180005d00  cmp     ebx, 1
0x180005d03  mov     eax, 80004005h
0x180005d08  cmovz   ebx, eax
0x180005d0b  mov     rax, [r14]
0x180005d0e  mov     rcx, r14
0x180005d11  mov     rax, [rax+10h]
0x180005d15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180005d21  test    ebx, ebx
0x180005d23  js      loc_180005DC4
0x180005d29  mov     rcx, [rsi]; bstrString
0x180005d2c  test    rcx, rcx
0x180005d2f  jz      short loc_180005D3E
0x180005d31  call    cs:__imp_SysFreeString
0x180005d37  mov     qword ptr [rsi], 0
0x180005d3e  mov     rcx, [rsi+8]
0x180005d42  test    rcx, rcx
0x180005d45  jz      short loc_180005D53
0x180005d47  mov     rax, [rcx]
0x180005d4a  mov     rax, [rax+10h]
0x180005d4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d53  mov     rax, [rbp+bstrString]
0x180005d57  mov     [rsi], rax
0x180005d5a  mov     rax, [rbp+var_10]
0x180005d5e  mov     [rsi+8], rax
0x180005d62  test    ebx, ebx
0x180005d64  jz      loc_180005E44
0x180005d6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180005d71  jmp     loc_180005E19
0x180005d76  mov     rcx, cs:WPP_GLOBAL_Control
0x180005d7d  lea     rdi, WPP_GLOBAL_Control
0x180005d84  cmp     rcx, rdi
0x180005d87  jz      short loc_180005DB6
0x180005d89  test    byte ptr [rcx+1Ch], 1
0x180005d8d  jz      short loc_180005DB6
0x180005d8f  mov     rcx, [rcx+10h]
0x180005d93  lea     r9, aHrparsesoapreq; "HrParseSOAPRequest(): Failed to get Bod"...
0x180005d9a  mov     edx, 49h ; 'I'
0x180005d9f  mov     [rsp+40h+var_20], ebx
0x180005da3  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x180005daa  call    WPP_SF_sd
0x180005daf  mov     rcx, cs:WPP_GLOBAL_Control
0x180005db6  cmp     ebx, 1
0x180005db9  jnz     loc_180005D21
0x180005dbf  mov     ebx, 80004005h
0x180005dc4  mov     rax, [rbp+bstrString]
0x180005dc8  test    rax, rax
0x180005dcb  jz      short loc_180005DE5
0x180005dcd  mov     rcx, rax; bstrString
0x180005dd0  call    cs:__imp_SysFreeString
0x180005dd6  mov     rcx, cs:WPP_GLOBAL_Control
0x180005ddd  mov     [rbp+bstrString], 0
0x180005de5  mov     rdx, [rbp+var_10]
0x180005de9  test    rdx, rdx
0x180005dec  jz      short loc_180005E0C
0x180005dee  mov     rax, [rdx]
0x180005df1  mov     rcx, rdx
0x180005df4  mov     rax, [rax+10h]
0x180005df8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dfd  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e04  mov     [rbp+var_10], 0
0x180005e0c  cmp     ebx, 8007000Eh
0x180005e12  jz      short loc_180005E19
0x180005e14  mov     ebx, 8004A205h
0x180005e19  cmp     rcx, rdi
0x180005e1c  jz      short loc_180005E44
0x180005e1e  test    byte ptr [rcx+1Ch], 1
0x180005e22  jz      short loc_180005E44
0x180005e24  mov     rcx, [rcx+10h]
0x180005e28  lea     r9, aHrparsesoapreq_0; "HrParseSOAPRequest(): Exiting"
0x180005e2f  mov     edx, 4Ah ; 'J'
0x180005e34  mov     [rsp+40h+var_20], ebx
0x180005e38  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x180005e3f  call    WPP_SF_sd
0x180005e44  mov     rsi, [rsp+40h+arg_8]
0x180005e49  mov     eax, ebx
0x180005e4b  mov     rbx, [rsp+40h+arg_0]
0x180005e50  add     rsp, 40h
0x180005e54  pop     r14
0x180005e56  pop     rdi
0x180005e57  pop     rbp
0x180005e58  retn
```
