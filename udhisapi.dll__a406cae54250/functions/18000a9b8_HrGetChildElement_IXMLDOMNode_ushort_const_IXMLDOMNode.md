# HrGetChildElement(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)

- ea: `0x18000a9b8`
- end: `0x18000aba8`
- name: `?HrGetChildElement@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z`
- size: `496`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, char *, struct IXMLDOMNode **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000abb0`

## callees

- `0x1800038ec`
- `0x180009bcc`
- `0x18000a9b8`
- `0x18000c010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000aa6e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000aa6e`

## pseudocode

```c
__int64 __fastcall HrGetChildElement(struct IXMLDOMNode *a1, char *a2, struct IXMLDOMNode **a3)
{
  struct IXMLDOMNode *v5; // rbx
  int v6; // eax
  unsigned int v7; // edi
  struct IXMLDOMNodeVtbl *lpVtbl; // rcx
  int v9; // eax
  BSTR v10; // rax
  int v11; // edx
  int v12; // ebp
  _QWORD *v13; // rcx
  int v14; // edx
  const char *v15; // r9
  int v17; // [rsp+60h] [rbp+8h] BYREF
  BSTR bstrString; // [rsp+70h] [rbp+18h] BYREF
  struct IXMLDOMNode *v19; // [rsp+78h] [rbp+20h] BYREF

  v5 = a1;
  if ( a1 )
  {
    ((void (__fastcall *)(struct IXMLDOMNode *))a1->lpVtbl->AddRef)(a1);
    while ( 1 )
    {
      v17 = 0;
      v19 = 0;
      v6 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, int *))v5->lpVtbl->get_nodeType)(v5, &v17);
      v7 = v6;
      if ( v6 < 0 )
        break;
      if ( v17 == 1 )
      {
        lpVtbl = v5->lpVtbl;
        bstrString = 0;
        v9 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))lpVtbl->get_baseName)(v5, &bstrString);
        if ( v9 < 0 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              19,
              (unsigned int)WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids,
              (unsigned int)"OBJ: FIsThisTheNodeName - get_baseName",
              v9);
        }
        else
        {
          v10 = bstrString;
          do
          {
            v11 = *(BSTR)((char *)v10 + a2 - (char *)bstrString);
            v12 = *v10 - v11;
            if ( v12 )
              break;
            ++v10;
          }
          while ( v11 );
          SysFreeString(bstrString);
          if ( !v12 )
          {
LABEL_16:
            *a3 = v5;
            return v7;
          }
        }
      }
      v6 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, struct IXMLDOMNode **))v5->lpVtbl->get_nextSibling)(v5, &v19);
      v7 = v6;
      if ( v6 < 0 )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v14 = 37;
          v15 = "HrGetChildElement - get_nextSibling";
LABEL_23:
          WPP_SF_sd(v13[2], v14, (unsigned int)WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids, (_DWORD)v15, v6);
          goto LABEL_24;
        }
        goto LABEL_24;
      }
      ((void (__fastcall *)(struct IXMLDOMNode *))v5->lpVtbl->Release)(v5);
      v5 = v19;
      if ( !v19 )
        goto LABEL_16;
    }
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v14 = 36;
      v15 = "HrGetChildElement - get_nodeType";
      goto LABEL_23;
    }
LABEL_24:
    ((void (__fastcall *)(struct IXMLDOMNode *))v5->lpVtbl->Release)(v5);
    *a3 = 0;
    v7 = -2147467259;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        38,
        (unsigned int)WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids,
        (_DWORD)a2,
        5);
  }
  else
  {
    *a3 = 0;
    return 1;
  }
  return v7;
}

```

## disassembly

```asm
0x18000a9b8  mov     [rsp+arg_8], rbx
0x18000a9bd  push    rbp
0x18000a9be  push    rsi
0x18000a9bf  push    rdi
0x18000a9c0  push    r12
0x18000a9c2  push    r14
0x18000a9c4  sub     rsp, 30h
0x18000a9c8  mov     rsi, r8
0x18000a9cb  mov     r14, rdx
0x18000a9ce  mov     rbx, rcx
0x18000a9d1  test    rcx, rcx
0x18000a9d4  jz      loc_18000AB8D
0x18000a9da  mov     rax, [rcx]
0x18000a9dd  mov     rax, [rax+8]
0x18000a9e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9e6  lea     r12, WPP_GLOBAL_Control
0x18000a9ed  mov     [rsp+58h+arg_0], 0
0x18000a9f5  lea     rdx, [rsp+58h+arg_0]
0x18000a9fa  mov     [rsp+58h+arg_18], 0
0x18000aa03  mov     rcx, rbx
0x18000aa06  mov     rax, [rbx]
0x18000aa09  mov     rax, [rax+50h]
0x18000aa0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa12  mov     edi, eax
0x18000aa14  test    eax, eax
0x18000aa16  js      loc_18000AB0E
0x18000aa1c  cmp     [rsp+58h+arg_0], 1
0x18000aa21  jnz     loc_18000AAAC
0x18000aa27  mov     rcx, [rbx]
0x18000aa2a  lea     rdx, [rsp+58h+bstrString]
0x18000aa2f  mov     [rsp+58h+bstrString], 0
0x18000aa38  mov     rax, [rcx+148h]
0x18000aa3f  mov     rcx, rbx
0x18000aa42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa47  test    eax, eax
0x18000aa49  js      short loc_18000AA7A
0x18000aa4b  mov     rax, [rsp+58h+bstrString]
0x18000aa50  mov     rcx, r14
0x18000aa53  sub     rcx, rax
0x18000aa56  movzx   ebp, word ptr [rax]
0x18000aa59  movzx   edx, word ptr [rax+rcx]
0x18000aa5d  sub     ebp, edx
0x18000aa5f  jnz     short loc_18000AA69
0x18000aa61  add     rax, 2
0x18000aa65  test    edx, edx
0x18000aa67  jnz     short loc_18000AA56
0x18000aa69  mov     rcx, [rsp+58h+bstrString]; bstrString
0x18000aa6e  call    cs:__imp_SysFreeString
0x18000aa74  test    ebp, ebp
0x18000aa76  jz      short loc_18000AAE6
0x18000aa78  jmp     short loc_18000AAAC
0x18000aa7a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aa81  cmp     rcx, r12
0x18000aa84  jz      short loc_18000AAAC
0x18000aa86  test    byte ptr [rcx+1Ch], 1
0x18000aa8a  jz      short loc_18000AAAC
0x18000aa8c  mov     rcx, [rcx+10h]
0x18000aa90  lea     r9, aObjFisthisthen; "OBJ: FIsThisTheNodeName - get_baseName"
0x18000aa97  mov     edx, 13h
0x18000aa9c  mov     [rsp+58h+var_38], eax
0x18000aaa0  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x18000aaa7  call    WPP_SF_sd
0x18000aaac  mov     rax, [rbx]
0x18000aaaf  lea     rdx, [rsp+58h+arg_18]
0x18000aab4  mov     rcx, rbx
0x18000aab7  mov     rax, [rax+80h]
0x18000aabe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aac3  mov     edi, eax
0x18000aac5  test    eax, eax
0x18000aac7  js      short loc_18000AAEE
0x18000aac9  mov     rax, [rbx]
0x18000aacc  mov     rcx, rbx
0x18000aacf  mov     rax, [rax+10h]
0x18000aad3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aad8  mov     rbx, [rsp+58h+arg_18]
0x18000aadd  test    rbx, rbx
0x18000aae0  jnz     loc_18000A9ED
0x18000aae6  mov     [rsi], rbx
0x18000aae9  jmp     loc_18000AB95
0x18000aaee  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aaf5  cmp     rcx, r12
0x18000aaf8  jz      short loc_18000AB40
0x18000aafa  test    byte ptr [rcx+1Ch], 1
0x18000aafe  jz      short loc_18000AB40
0x18000ab00  mov     edx, 25h ; '%'
0x18000ab05  lea     r9, aHrgetchildelem; "HrGetChildElement - get_nextSibling"
0x18000ab0c  jmp     short loc_18000AB2C
0x18000ab0e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ab15  cmp     rcx, r12
0x18000ab18  jz      short loc_18000AB40
0x18000ab1a  test    byte ptr [rcx+1Ch], 1
0x18000ab1e  jz      short loc_18000AB40
0x18000ab20  mov     edx, 24h ; '$'
0x18000ab25  lea     r9, aHrgetchildelem_0; "HrGetChildElement - get_nodeType"
0x18000ab2c  mov     rcx, [rcx+10h]
0x18000ab30  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x18000ab37  mov     [rsp+58h+var_38], eax
0x18000ab3b  call    WPP_SF_sd
0x18000ab40  mov     rax, [rbx]
0x18000ab43  mov     rcx, rbx
0x18000ab46  mov     rax, [rax+10h]
0x18000ab4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab4f  mov     qword ptr [rsi], 0
0x18000ab56  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ab5d  mov     ebx, 80004005h
0x18000ab62  mov     edi, ebx
0x18000ab64  cmp     rcx, r12
0x18000ab67  jz      short loc_18000AB95
0x18000ab69  test    byte ptr [rcx+1Ch], 1
0x18000ab6d  jz      short loc_18000AB95
0x18000ab6f  mov     rcx, [rcx+10h]
0x18000ab73  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x18000ab7a  mov     edx, 26h ; '&'
0x18000ab7f  mov     [rsp+58h+var_38], ebx
0x18000ab83  mov     r9, r14
0x18000ab86  call    WPP_SF_Sd
0x18000ab8b  jmp     short loc_18000AB95
0x18000ab8d  mov     [r8], rcx
0x18000ab90  mov     edi, 1
0x18000ab95  mov     rbx, [rsp+58h+arg_8]
0x18000ab9a  mov     eax, edi
0x18000ab9c  add     rsp, 30h
0x18000aba0  pop     r14
0x18000aba2  pop     r12
0x18000aba4  pop     rdi
0x18000aba5  pop     rsi
0x18000aba6  pop     rbp
0x18000aba7  retn
```
