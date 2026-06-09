# HrValidateSOAPHeader(IXMLDOMNode *)

- ea: `0x180009200`
- end: `0x180009419`
- name: `?HrValidateSOAPHeader@@YAJPEAUIXMLDOMNode@@@Z`
- size: `537`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180009420`

## callees

- `0x18000249c`
- `0x1800038ec`
- `0x180009200`
- `0x18000ad54`
- `0x18000c010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000934f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000934f`
- `OLEAUT32!__imp_SysStringLen` at `0x180009273`
- `OLEAUT32!__imp_SysStringLen` at `0x180009273`

## pseudocode

```c
__int64 __fastcall HrValidateSOAPHeader(struct IXMLDOMNode *a1)
{
  struct IXMLDOMNodeVtbl *lpVtbl; // rax
  const unsigned __int16 *v2; // rdx
  int v3; // ebx
  struct IXMLDOMNode *v4; // rax
  int TextValueFromAttribute; // eax
  BSTR v6; // rdi
  _QWORD *v7; // rcx
  int v8; // edx
  const char *v9; // r9
  struct IXMLDOMNode *v11; // [rsp+60h] [rbp+30h] BYREF
  BSTR pbstr; // [rsp+68h] [rbp+38h] BYREF
  struct IXMLDOMNode *v13; // [rsp+70h] [rbp+40h] BYREF

  lpVtbl = a1->lpVtbl;
  v11 = 0;
  v3 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, struct IXMLDOMNode **))lpVtbl->get_firstChild)(a1, &v11);
  if ( v3 >= 0 )
  {
    v4 = v11;
    while ( v4 )
    {
      v13 = 0;
      pbstr = 0;
      TextValueFromAttribute = HrGetTextValueFromAttribute(v4, v2, &pbstr);
      v3 = TextValueFromAttribute;
      if ( TextValueFromAttribute < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            36,
            (unsigned int)WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids,
            (unsigned int)"HrValidateSOAPError(): Failed to get mustUnderstand attribute value",
            TextValueFromAttribute);
LABEL_29:
        ((void (__fastcall *)(struct IXMLDOMNode *))v11->lpVtbl->Release)(v11);
        goto LABEL_31;
      }
      v6 = pbstr;
      if ( !SysStringLen(pbstr) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids);
        goto LABEL_24;
      }
      if ( *v6 != 48 || v6[1] )
      {
        if ( *v6 != 49 || v6[1] )
        {
          v3 = -2147467259;
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v8 = 35;
            v9 = "HrValidateSOAPHeader(): Found header with invalid mustUnderstand attribute value";
            goto LABEL_22;
          }
        }
        else
        {
          v3 = -2147467259;
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v8 = 34;
            v9 = "HrValidateSOAPHeader(): Found header with mustUnderstand attribute set";
LABEL_22:
            WPP_SF_sd(v7[2], v8, (unsigned int)WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids, (_DWORD)v9, 5);
          }
        }
      }
      else
      {
        v3 = 0;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids);
      }
      SysFreeString(v6);
      if ( v3 < 0 )
        goto LABEL_29;
LABEL_24:
      v3 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, struct IXMLDOMNode **))v11->lpVtbl->get_nextSibling)(
             v11,
             &v13);
      ((void (__fastcall *)(struct IXMLDOMNode *))v11->lpVtbl->Release)(v11);
      v4 = v13;
      v11 = v13;
      if ( v3 < 0 )
        goto LABEL_31;
    }
  }
  if ( v3 )
  {
LABEL_31:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        37,
        (unsigned int)WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids,
        (unsigned int)"HrValidateSOAPHeader(): Exiting",
        v3);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180009200  mov     [rsp-28h+arg_18], rbx
0x180009205  push    rbp
0x180009206  push    rsi
0x180009207  push    rdi
0x180009208  push    r14
0x18000920a  push    r15
0x18000920c  mov     rbp, rsp
0x18000920f  sub     rsp, 30h
0x180009213  mov     rax, [rcx]
0x180009216  lea     rdx, [rbp+arg_0]
0x18000921a  xor     esi, esi
0x18000921c  mov     [rbp+arg_0], rsi
0x180009220  mov     rax, [rax+68h]
0x180009224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009229  lea     r14, WPP_GLOBAL_Control
0x180009230  mov     ebx, eax
0x180009232  lea     r15, WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids
0x180009239  test    eax, eax
0x18000923b  js      loc_1800093D4
0x180009241  mov     rax, [rbp+arg_0]
0x180009245  test    rax, rax
0x180009248  jz      loc_1800093D4
0x18000924e  lea     r8, [rbp+pbstr]; unsigned __int16 **
0x180009252  mov     [rbp+arg_10], rsi
0x180009256  mov     rcx, rax; struct IXMLDOMNode *
0x180009259  mov     [rbp+pbstr], rsi
0x18000925d  call    ?HrGetTextValueFromAttribute@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAG@Z; HrGetTextValueFromAttribute(IXMLDOMNode *,ushort const *,ushort * *)
0x180009262  mov     ebx, eax
0x180009264  test    eax, eax
0x180009266  js      loc_180009394
0x18000926c  mov     rdi, [rbp+pbstr]
0x180009270  mov     rcx, rdi; pbstr
0x180009273  call    cs:__imp_SysStringLen
0x180009279  test    eax, eax
0x18000927b  jnz     short loc_1800092AE
0x18000927d  mov     rcx, cs:WPP_GLOBAL_Control
0x180009284  cmp     rcx, r14
0x180009287  jz      loc_180009359
0x18000928d  test    dword ptr [rcx+1Ch], 400h
0x180009294  jz      loc_180009359
0x18000929a  mov     rcx, [rcx+10h]
0x18000929e  lea     edx, [rax+20h]
0x1800092a1  mov     r8, r15
0x1800092a4  call    WPP_SF_
0x1800092a9  jmp     loc_180009359
0x1800092ae  cmp     word ptr [rdi], 30h ; '0'
0x1800092b2  jnz     short loc_1800092E8
0x1800092b4  cmp     [rdi+2], si
0x1800092b8  jnz     short loc_1800092E8
0x1800092ba  mov     ebx, esi
0x1800092bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800092c3  cmp     rcx, r14
0x1800092c6  jz      loc_18000934C
0x1800092cc  test    dword ptr [rcx+1Ch], 400h
0x1800092d3  jz      short loc_18000934C
0x1800092d5  mov     rcx, [rcx+10h]
0x1800092d9  mov     edx, 21h ; '!'
0x1800092de  mov     r8, r15
0x1800092e1  call    WPP_SF_
0x1800092e6  jmp     short loc_18000934C
0x1800092e8  cmp     word ptr [rdi], 31h ; '1'
0x1800092ec  jnz     short loc_180009319
0x1800092ee  cmp     [rdi+2], si
0x1800092f2  jnz     short loc_180009319
0x1800092f4  mov     ebx, 80004005h
0x1800092f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180009300  cmp     rcx, r14
0x180009303  jz      short loc_18000934C
0x180009305  test    byte ptr [rcx+1Ch], 1
0x180009309  jz      short loc_18000934C
0x18000930b  mov     edx, 22h ; '"'
0x180009310  lea     r9, aHrvalidatesoap_6; "HrValidateSOAPHeader(): Found header wi"...
0x180009317  jmp     short loc_18000933C
0x180009319  mov     ebx, 80004005h
0x18000931e  mov     rcx, cs:WPP_GLOBAL_Control
0x180009325  cmp     rcx, r14
0x180009328  jz      short loc_18000934C
0x18000932a  test    byte ptr [rcx+1Ch], 1
0x18000932e  jz      short loc_18000934C
0x180009330  mov     edx, 23h ; '#'
0x180009335  lea     r9, aHrvalidatesoap_4; "HrValidateSOAPHeader(): Found header wi"...
0x18000933c  mov     rcx, [rcx+10h]
0x180009340  mov     r8, r15
0x180009343  mov     [rsp+30h+var_10], ebx
0x180009347  call    WPP_SF_sd
0x18000934c  mov     rcx, rdi; bstrString
0x18000934f  call    cs:__imp_SysFreeString
0x180009355  test    ebx, ebx
0x180009357  js      short loc_1800093C2
0x180009359  mov     rcx, [rbp+arg_0]
0x18000935d  lea     rdx, [rbp+arg_10]
0x180009361  mov     rax, [rcx]
0x180009364  mov     rax, [rax+80h]
0x18000936b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009370  mov     rcx, [rbp+arg_0]
0x180009374  mov     ebx, eax
0x180009376  mov     rax, [rcx]
0x180009379  mov     rax, [rax+10h]
0x18000937d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009382  mov     rax, [rbp+arg_10]
0x180009386  mov     [rbp+arg_0], rax
0x18000938a  test    ebx, ebx
0x18000938c  jns     loc_180009245
0x180009392  jmp     short loc_1800093D8
0x180009394  mov     rcx, cs:WPP_GLOBAL_Control
0x18000939b  cmp     rcx, r14
0x18000939e  jz      short loc_1800093C2
0x1800093a0  test    byte ptr [rcx+1Ch], 1
0x1800093a4  jz      short loc_1800093C2
0x1800093a6  mov     rcx, [rcx+10h]
0x1800093aa  lea     r9, aHrvalidatesoap_2; "HrValidateSOAPError(): Failed to get mu"...
0x1800093b1  mov     edx, 24h ; '$'
0x1800093b6  mov     [rsp+30h+var_10], eax
0x1800093ba  mov     r8, r15
0x1800093bd  call    WPP_SF_sd
0x1800093c2  mov     rcx, [rbp+arg_0]
0x1800093c6  mov     rax, [rcx]
0x1800093c9  mov     rax, [rax+10h]
0x1800093cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093d2  jmp     short loc_1800093D8
0x1800093d4  test    ebx, ebx
0x1800093d6  jz      short loc_180009406
0x1800093d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800093df  cmp     rcx, r14
0x1800093e2  jz      short loc_180009406
0x1800093e4  test    byte ptr [rcx+1Ch], 1
0x1800093e8  jz      short loc_180009406
0x1800093ea  mov     rcx, [rcx+10h]
0x1800093ee  lea     r9, aHrvalidatesoap_8; "HrValidateSOAPHeader(): Exiting"
0x1800093f5  mov     edx, 25h ; '%'
0x1800093fa  mov     [rsp+30h+var_10], ebx
0x1800093fe  mov     r8, r15
0x180009401  call    WPP_SF_sd
0x180009406  mov     eax, ebx
0x180009408  mov     rbx, [rsp+30h+arg_18]
0x18000940d  add     rsp, 30h
0x180009411  pop     r15
0x180009413  pop     r14
0x180009415  pop     rdi
0x180009416  pop     rsi
0x180009417  pop     rbp
0x180009418  retn
```
