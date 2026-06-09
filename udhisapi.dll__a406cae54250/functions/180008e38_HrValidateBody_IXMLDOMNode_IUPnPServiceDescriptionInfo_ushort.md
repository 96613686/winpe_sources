# HrValidateBody(IXMLDOMNode *,IUPnPServiceDescriptionInfo *,ushort *)

- ea: `0x180008e38`
- end: `0x180009068`
- name: `?HrValidateBody@@YAJPEAUIXMLDOMNode@@PEAUIUPnPServiceDescriptionInfo@@PEAG@Z`
- size: `560`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, struct IUPnPServiceDescriptionInfo *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x180009420`

## callees

- `0x18000249c`
- `0x1800038ec`
- `0x180008800`
- `0x180008a4c`
- `0x180008e38`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall HrValidateBody(struct IXMLDOMNode *a1, struct IUPnPServiceDescriptionInfo *a2, unsigned __int16 *a3)
{
  struct IXMLDOMNodeVtbl *lpVtbl; // rax
  int v6; // eax
  int v7; // ebx
  int v8; // eax
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  _QWORD *v11; // rcx
  struct IXMLDOMNode *v13; // [rsp+50h] [rbp+20h] BYREF
  struct IXMLDOMNodeList *v14; // [rsp+68h] [rbp+38h] BYREF

  lpVtbl = a1->lpVtbl;
  v13 = 0;
  v6 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, struct IXMLDOMNode **))lpVtbl->get_firstChild)(a1, &v13);
  v7 = v6;
  if ( v6 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return (unsigned int)v7;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_28;
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      30,
      (unsigned int)WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids,
      (unsigned int)"HrValidateBody(): Failed to get first child of body element",
      v6);
    goto LABEL_27;
  }
  if ( v13 )
  {
    v7 = HrValidateActionName(v13, a3);
    if ( v7 < 0 )
      goto LABEL_18;
    v14 = 0;
    v7 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, struct IXMLDOMNodeList **))v13->lpVtbl->get_childNodes)(
           v13,
           &v14);
    if ( v7 < 0 )
      goto LABEL_18;
    v7 = HrValidateArguments(v13, v14, a2);
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v14->lpVtbl->Release)(v14);
    if ( v7 < 0 )
      goto LABEL_18;
    v14 = 0;
    v8 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, struct IXMLDOMNodeList **))v13->lpVtbl->get_nextSibling)(
           v13,
           &v14);
    if ( v8 == 1 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
        goto LABEL_18;
      v10 = 26;
    }
    else
    {
      if ( v8 < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            28,
            (unsigned int)WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids,
            (unsigned int)"HrValidateBody(): get_nextSibling failed",
            v8);
        goto LABEL_18;
      }
      ((void (__fastcall *)(struct IXMLDOMNodeList *))v14->lpVtbl->Release)(v14);
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
      {
LABEL_18:
        ((void (__fastcall *)(struct IXMLDOMNode *))v13->lpVtbl->Release)(v13);
        goto LABEL_22;
      }
      v10 = 27;
    }
    WPP_SF_(v9[2], v10, WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids);
    goto LABEL_18;
  }
  v7 = -2147467259;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return (unsigned int)v7;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      29,
      (unsigned int)WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids,
      (unsigned int)"HrValidateBody(): Body element was empty",
      5);
LABEL_22:
    if ( !v7 )
      return (unsigned int)v7;
LABEL_27:
    v11 = WPP_GLOBAL_Control;
  }
LABEL_28:
  if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 )
    WPP_SF_sd(
      v11[2],
      31,
      (unsigned int)WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids,
      (unsigned int)"HrValidateBody(): Exiting",
      v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180008e38  mov     [rsp-18h+arg_8], rbx
0x180008e3d  mov     [rsp-18h+arg_10], rsi
0x180008e42  push    rbp
0x180008e43  push    rdi
0x180008e44  push    r15
0x180008e46  mov     rbp, rsp
0x180008e49  sub     rsp, 30h
0x180008e4d  mov     rax, [rcx]
0x180008e50  mov     rsi, rdx
0x180008e53  lea     rdx, [rbp+arg_0]
0x180008e57  mov     [rbp+arg_0], 0
0x180008e5f  mov     rdi, r8
0x180008e62  mov     rax, [rax+68h]
0x180008e66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e6b  lea     r15, WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids
0x180008e72  mov     ebx, eax
0x180008e74  test    eax, eax
0x180008e76  js      loc_180008FF0
0x180008e7c  mov     rcx, [rbp+arg_0]; struct IXMLDOMNode *
0x180008e80  test    rcx, rcx
0x180008e83  jz      loc_180008FAC
0x180008e89  mov     rdx, rdi; unsigned __int16 *
0x180008e8c  call    ?HrValidateActionName@@YAJPEAUIXMLDOMNode@@PEAG@Z; HrValidateActionName(IXMLDOMNode *,ushort *)
0x180008e91  lea     rdi, WPP_GLOBAL_Control
0x180008e98  mov     ebx, eax
0x180008e9a  test    eax, eax
0x180008e9c  js      loc_180008F9A
0x180008ea2  mov     rcx, [rbp+arg_0]
0x180008ea6  lea     rdx, [rbp+arg_18]
0x180008eaa  mov     [rbp+arg_18], 0
0x180008eb2  mov     rax, [rcx]
0x180008eb5  mov     rax, [rax+60h]
0x180008eb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ebe  mov     ebx, eax
0x180008ec0  test    eax, eax
0x180008ec2  js      loc_180008F9A
0x180008ec8  mov     rdx, [rbp+arg_18]; struct IXMLDOMNodeList *
0x180008ecc  mov     r8, rsi; struct IUPnPServiceDescriptionInfo *
0x180008ecf  mov     rcx, [rbp+arg_0]; struct IXMLDOMNode *
0x180008ed3  call    ?HrValidateArguments@@YAJPEAUIXMLDOMNode@@PEAUIXMLDOMNodeList@@PEAUIUPnPServiceDescriptionInfo@@@Z; HrValidateArguments(IXMLDOMNode *,IXMLDOMNodeList *,IUPnPServiceDescriptionInfo *)
0x180008ed8  mov     rcx, [rbp+arg_18]
0x180008edc  mov     ebx, eax
0x180008ede  mov     rax, [rcx]
0x180008ee1  mov     rax, [rax+10h]
0x180008ee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008eea  test    ebx, ebx
0x180008eec  js      loc_180008F9A
0x180008ef2  mov     rcx, [rbp+arg_0]
0x180008ef6  lea     rdx, [rbp+arg_18]
0x180008efa  mov     [rbp+arg_18], 0
0x180008f02  mov     rax, [rcx]
0x180008f05  mov     rax, [rax+80h]
0x180008f0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f11  cmp     eax, 1
0x180008f14  jnz     short loc_180008F30
0x180008f16  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f1d  cmp     rcx, rdi
0x180008f20  jz      short loc_180008F9A
0x180008f22  test    dword ptr [rcx+1Ch], 400h
0x180008f29  jz      short loc_180008F9A
0x180008f2b  lea     edx, [rax+19h]
0x180008f2e  jmp     short loc_180008F5E
0x180008f30  test    eax, eax
0x180008f32  js      short loc_180008F6C
0x180008f34  mov     rcx, [rbp+arg_18]
0x180008f38  mov     rax, [rcx]
0x180008f3b  mov     rax, [rax+10h]
0x180008f3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f44  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f4b  cmp     rcx, rdi
0x180008f4e  jz      short loc_180008F9A
0x180008f50  test    dword ptr [rcx+1Ch], 400h
0x180008f57  jz      short loc_180008F9A
0x180008f59  mov     edx, 1Bh
0x180008f5e  mov     rcx, [rcx+10h]
0x180008f62  mov     r8, r15
0x180008f65  call    WPP_SF_
0x180008f6a  jmp     short loc_180008F9A
0x180008f6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f73  cmp     rcx, rdi
0x180008f76  jz      short loc_180008F9A
0x180008f78  test    byte ptr [rcx+1Ch], 1
0x180008f7c  jz      short loc_180008F9A
0x180008f7e  mov     rcx, [rcx+10h]
0x180008f82  lea     r9, aHrvalidatebody_1; "HrValidateBody(): get_nextSibling faile"...
0x180008f89  mov     edx, 1Ch
0x180008f8e  mov     [rsp+30h+var_10], eax
0x180008f92  mov     r8, r15
0x180008f95  call    WPP_SF_sd
0x180008f9a  mov     rcx, [rbp+arg_0]
0x180008f9e  mov     rax, [rcx]
0x180008fa1  mov     rax, [rax+10h]
0x180008fa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008faa  jmp     short loc_180008FEA
0x180008fac  mov     ebx, 80004005h
0x180008fb1  mov     rcx, cs:WPP_GLOBAL_Control
0x180008fb8  lea     rdi, WPP_GLOBAL_Control
0x180008fbf  cmp     rcx, rdi
0x180008fc2  jz      loc_180009053
0x180008fc8  test    byte ptr [rcx+1Ch], 1
0x180008fcc  jz      short loc_18000902C
0x180008fce  mov     rcx, [rcx+10h]
0x180008fd2  lea     r9, aHrvalidatebody_0; "HrValidateBody(): Body element was empt"...
0x180008fd9  mov     edx, 1Dh
0x180008fde  mov     [rsp+30h+var_10], ebx
0x180008fe2  mov     r8, r15
0x180008fe5  call    WPP_SF_sd
0x180008fea  test    ebx, ebx
0x180008fec  jz      short loc_180009053
0x180008fee  jmp     short loc_180009025
0x180008ff0  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ff7  lea     rdi, WPP_GLOBAL_Control
0x180008ffe  cmp     rcx, rdi
0x180009001  jz      short loc_180009053
0x180009003  test    byte ptr [rcx+1Ch], 1
0x180009007  jz      short loc_18000902C
0x180009009  mov     rcx, [rcx+10h]
0x18000900d  lea     r9, aHrvalidatebody_2; "HrValidateBody(): Failed to get first c"...
0x180009014  mov     edx, 1Eh
0x180009019  mov     [rsp+30h+var_10], eax
0x18000901d  mov     r8, r15
0x180009020  call    WPP_SF_sd
0x180009025  mov     rcx, cs:WPP_GLOBAL_Control
0x18000902c  cmp     rcx, rdi
0x18000902f  jz      short loc_180009053
0x180009031  test    byte ptr [rcx+1Ch], 1
0x180009035  jz      short loc_180009053
0x180009037  mov     rcx, [rcx+10h]
0x18000903b  lea     r9, aHrvalidatebody; "HrValidateBody(): Exiting"
0x180009042  mov     edx, 1Fh
0x180009047  mov     [rsp+30h+var_10], ebx
0x18000904b  mov     r8, r15
0x18000904e  call    WPP_SF_sd
0x180009053  mov     rsi, [rsp+30h+arg_10]
0x180009058  mov     eax, ebx
0x18000905a  mov     rbx, [rsp+30h+arg_8]
0x18000905f  add     rsp, 30h
0x180009063  pop     r15
0x180009065  pop     rdi
0x180009066  pop     rbp
0x180009067  retn
```
