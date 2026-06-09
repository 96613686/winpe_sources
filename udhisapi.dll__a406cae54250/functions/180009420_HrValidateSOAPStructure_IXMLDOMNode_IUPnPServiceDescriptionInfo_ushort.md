# HrValidateSOAPStructure(IXMLDOMNode *,IUPnPServiceDescriptionInfo *,ushort *)

- ea: `0x180009420`
- end: `0x1800096a9`
- name: `?HrValidateSOAPStructure@@YAJPEAUIXMLDOMNode@@PEAUIUPnPServiceDescriptionInfo@@PEAG@Z`
- size: `649`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, struct IUPnPServiceDescriptionInfo *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x180006764`

## callees

- `0x18000249c`
- `0x1800038ec`
- `0x180008e38`
- `0x180009200`
- `0x180009420`
- `0x180009d2c`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall HrValidateSOAPStructure(
        struct IXMLDOMNode *a1,
        struct IUPnPServiceDescriptionInfo *a2,
        unsigned __int16 *a3,
        unsigned int a4)
{
  struct IXMLDOMNodeVtbl *lpVtbl; // rax
  int v7; // r12d
  int v8; // r15d
  int v9; // ebx
  const unsigned __int16 *v10; // r8
  unsigned int v11; // r9d
  struct IXMLDOMNode *v12; // rax
  const unsigned __int16 *v13; // r8
  unsigned int v14; // r9d
  int v15; // eax
  _QWORD *v16; // rcx
  int v17; // edx
  const char *v18; // r9
  bool v19; // zf
  _QWORD *v20; // rcx
  int v21; // edx
  const char *v22; // r9
  int v24; // [rsp+20h] [rbp-20h]
  int v25; // [rsp+20h] [rbp-20h]
  struct IXMLDOMNode *v26; // [rsp+30h] [rbp-10h] BYREF
  struct IXMLDOMNode *v28; // [rsp+88h] [rbp+48h] BYREF

  if ( !FIsThisTheNodeNameWithNamespace(a1, L"Envelope", a3, a4, v24) )
  {
    v9 = -2147467259;
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return (unsigned int)v9;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_38;
    v21 = 43;
    v22 = "HrValidateSOAPStructure(): Root element is not a SOAP envelope";
LABEL_36:
    WPP_SF_sd(v20[2], v21, (unsigned int)WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids, (_DWORD)v22, 5);
    goto LABEL_37;
  }
  lpVtbl = a1->lpVtbl;
  v28 = 0;
  v7 = 0;
  v8 = 0;
  v9 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, struct IXMLDOMNode **))lpVtbl->get_firstChild)(a1, &v28);
  if ( v9 < 0 )
  {
LABEL_30:
    v19 = v9 == 0;
LABEL_31:
    if ( v19 )
      return (unsigned int)v9;
LABEL_37:
    v20 = WPP_GLOBAL_Control;
    goto LABEL_38;
  }
  v12 = v28;
  while ( v12 )
  {
    v26 = 0;
    if ( FIsThisTheNodeNameWithNamespace(v12, L"Header", v10, v11, v25) )
    {
      if ( !v7 )
      {
        v7 = 1;
        v15 = HrValidateSOAPHeader(v28);
LABEL_8:
        v9 = v15;
        goto LABEL_19;
      }
      v9 = -2147467259;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_22;
      v17 = 38;
      v18 = "HrValidateSOAPStructure(): Duplicate header element found";
    }
    else
    {
      if ( !FIsThisTheNodeNameWithNamespace(v28, L"Body", v13, v14, v25) )
        goto LABEL_20;
      if ( !v8 )
      {
        v8 = 1;
        v15 = HrValidateBody(v28, a2, a3);
        goto LABEL_8;
      }
      v9 = -2147467259;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_22:
        ((void (__fastcall *)(struct IXMLDOMNode *))v28->lpVtbl->Release)(v28);
        v19 = v9 == 0;
        goto LABEL_31;
      }
      v17 = 39;
      v18 = "HrValidateSOAPStructure(): Duplicate body element found";
    }
    WPP_SF_sd(v16[2], v17, (unsigned int)WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids, (_DWORD)v18, 5);
LABEL_19:
    if ( v9 < 0 )
      goto LABEL_22;
LABEL_20:
    v9 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, struct IXMLDOMNode **))v28->lpVtbl->get_nextSibling)(v28, &v26);
    ((void (__fastcall *)(struct IXMLDOMNode *))v28->lpVtbl->Release)(v28);
    v12 = v26;
    v28 = v26;
    if ( v9 < 0 )
      goto LABEL_30;
  }
  if ( v8 )
  {
    v9 = 0;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
      return (unsigned int)v9;
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids);
    goto LABEL_30;
  }
  v9 = -2147467259;
  v20 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v21 = 41;
      v22 = "HrValidateSOAPStrucutre(): Request was missing body element";
      goto LABEL_36;
    }
LABEL_38:
    if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 1) != 0 )
      WPP_SF_sd(
        v20[2],
        44,
        (unsigned int)WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids,
        (unsigned int)"HrValidateSOAPStructure(): Exiting",
        v9);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180009420  mov     [rsp-28h+arg_0], rbx
0x180009425  mov     [rsp-28h+arg_10], rdi
0x18000942a  mov     [rsp-28h+arg_8], rdx
0x18000942f  push    rbp
0x180009430  push    r12
0x180009432  push    r13
0x180009434  push    r14
0x180009436  push    r15
0x180009438  mov     rbp, rsp
0x18000943b  sub     rsp, 40h
0x18000943f  lea     rdx, aEnvelope; "Envelope"
0x180009446  mov     r13, r8
0x180009449  mov     rbx, rcx
0x18000944c  call    ?FIsThisTheNodeNameWithNamespace@@YAHPEAUIXMLDOMNode@@PEBG1KH@Z; FIsThisTheNodeNameWithNamespace(IXMLDOMNode *,ushort const *,ushort const *,ulong,int)
0x180009451  test    eax, eax
0x180009453  jz      loc_18000961B
0x180009459  mov     rax, [rbx]
0x18000945c  lea     rdx, [rbp+arg_18]
0x180009460  mov     rcx, rbx
0x180009463  mov     [rbp+arg_18], 0
0x18000946b  xor     r12d, r12d
0x18000946e  xor     r15d, r15d
0x180009471  mov     rax, [rax+68h]
0x180009475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000947a  lea     r14, WPP_GLOBAL_Control
0x180009481  mov     ebx, eax
0x180009483  test    eax, eax
0x180009485  js      loc_180009615
0x18000948b  mov     rax, [rbp+arg_18]
0x18000948f  mov     edi, 80004005h
0x180009494  test    rax, rax
0x180009497  jz      loc_1800095B5
0x18000949d  lea     rdx, aHeader; "Header"
0x1800094a4  mov     [rbp+var_10], 0
0x1800094ac  mov     rcx, rax; struct IXMLDOMNode *
0x1800094af  call    ?FIsThisTheNodeNameWithNamespace@@YAHPEAUIXMLDOMNode@@PEBG1KH@Z; FIsThisTheNodeNameWithNamespace(IXMLDOMNode *,ushort const *,ushort const *,ulong,int)
0x1800094b4  test    eax, eax
0x1800094b6  jz      short loc_1800094FD
0x1800094b8  test    r12d, r12d
0x1800094bb  jnz     short loc_1800094D3
0x1800094bd  mov     rcx, [rbp+arg_18]; struct IXMLDOMNode *
0x1800094c1  mov     r12d, 1
0x1800094c7  call    ?HrValidateSOAPHeader@@YAJPEAUIXMLDOMNode@@@Z; HrValidateSOAPHeader(IXMLDOMNode *)
0x1800094cc  mov     ebx, eax
0x1800094ce  jmp     loc_180009562
0x1800094d3  mov     ebx, edi
0x1800094d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800094dc  cmp     rcx, r14
0x1800094df  jz      loc_1800095A1
0x1800094e5  test    byte ptr [rcx+1Ch], 1
0x1800094e9  jz      loc_1800095A1
0x1800094ef  mov     edx, 26h ; '&'
0x1800094f4  lea     r9, aHrvalidatesoap; "HrValidateSOAPStructure(): Duplicate he"...
0x1800094fb  jmp     short loc_18000954E
0x1800094fd  mov     rcx, [rbp+arg_18]; struct IXMLDOMNode *
0x180009501  lea     rdx, aBody; "Body"
0x180009508  call    ?FIsThisTheNodeNameWithNamespace@@YAHPEAUIXMLDOMNode@@PEBG1KH@Z; FIsThisTheNodeNameWithNamespace(IXMLDOMNode *,ushort const *,ushort const *,ulong,int)
0x18000950d  test    eax, eax
0x18000950f  jz      short loc_180009566
0x180009511  test    r15d, r15d
0x180009514  jnz     short loc_18000952E
0x180009516  mov     rdx, [rbp+arg_8]; struct IUPnPServiceDescriptionInfo *
0x18000951a  mov     r8, r13; unsigned __int16 *
0x18000951d  mov     rcx, [rbp+arg_18]; struct IXMLDOMNode *
0x180009521  mov     r15d, 1
0x180009527  call    ?HrValidateBody@@YAJPEAUIXMLDOMNode@@PEAUIUPnPServiceDescriptionInfo@@PEAG@Z; HrValidateBody(IXMLDOMNode *,IUPnPServiceDescriptionInfo *,ushort *)
0x18000952c  jmp     short loc_1800094CC
0x18000952e  mov     ebx, edi
0x180009530  mov     rcx, cs:WPP_GLOBAL_Control
0x180009537  cmp     rcx, r14
0x18000953a  jz      short loc_1800095A1
0x18000953c  test    byte ptr [rcx+1Ch], 1
0x180009540  jz      short loc_1800095A1
0x180009542  mov     edx, 27h ; '''
0x180009547  lea     r9, aHrvalidatesoap_5; "HrValidateSOAPStructure(): Duplicate bo"...
0x18000954e  mov     rcx, [rcx+10h]
0x180009552  lea     r8, WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids
0x180009559  mov     [rsp+40h+var_20], edi
0x18000955d  call    WPP_SF_sd
0x180009562  test    ebx, ebx
0x180009564  js      short loc_1800095A1
0x180009566  mov     rcx, [rbp+arg_18]
0x18000956a  lea     rdx, [rbp+var_10]
0x18000956e  mov     rax, [rcx]
0x180009571  mov     rax, [rax+80h]
0x180009578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000957d  mov     rcx, [rbp+arg_18]
0x180009581  mov     ebx, eax
0x180009583  mov     rax, [rcx]
0x180009586  mov     rax, [rax+10h]
0x18000958a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000958f  mov     rax, [rbp+var_10]
0x180009593  mov     [rbp+arg_18], rax
0x180009597  test    ebx, ebx
0x180009599  jns     loc_180009494
0x18000959f  jmp     short loc_180009615
0x1800095a1  mov     rcx, [rbp+arg_18]
0x1800095a5  mov     rax, [rcx]
0x1800095a8  mov     rax, [rax+10h]
0x1800095ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095b1  test    ebx, ebx
0x1800095b3  js      short loc_180009617
0x1800095b5  test    r15d, r15d
0x1800095b8  jnz     short loc_1800095E3
0x1800095ba  mov     ebx, edi
0x1800095bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800095c3  cmp     rcx, r14
0x1800095c6  jz      loc_18000968D
0x1800095cc  test    byte ptr [rcx+1Ch], 1
0x1800095d0  jz      loc_180009662
0x1800095d6  lea     edx, [r15+29h]
0x1800095da  lea     r9, aHrvalidatesoap_7; "HrValidateSOAPStrucutre(): Request was "...
0x1800095e1  jmp     short loc_180009647
0x1800095e3  xor     ebx, ebx
0x1800095e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800095ec  cmp     rcx, r14
0x1800095ef  jz      loc_18000968D
0x1800095f5  test    dword ptr [rcx+1Ch], 400h
0x1800095fc  jz      loc_18000968D
0x180009602  mov     rcx, [rcx+10h]
0x180009606  lea     edx, [rbx+2Ah]
0x180009609  lea     r8, WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids
0x180009610  call    WPP_SF_
0x180009615  test    ebx, ebx
0x180009617  jz      short loc_18000968D
0x180009619  jmp     short loc_18000965B
0x18000961b  mov     edi, 80004005h
0x180009620  mov     ebx, edi
0x180009622  mov     rcx, cs:WPP_GLOBAL_Control
0x180009629  lea     r14, WPP_GLOBAL_Control
0x180009630  cmp     rcx, r14
0x180009633  jz      short loc_18000968D
0x180009635  test    byte ptr [rcx+1Ch], 1
0x180009639  jz      short loc_180009662
0x18000963b  mov     edx, 2Bh ; '+'
0x180009640  lea     r9, aHrvalidatesoap_0; "HrValidateSOAPStructure(): Root element"...
0x180009647  mov     rcx, [rcx+10h]
0x18000964b  lea     r8, WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids
0x180009652  mov     [rsp+40h+var_20], edi
0x180009656  call    WPP_SF_sd
0x18000965b  mov     rcx, cs:WPP_GLOBAL_Control
0x180009662  cmp     rcx, r14
0x180009665  jz      short loc_18000968D
0x180009667  test    byte ptr [rcx+1Ch], 1
0x18000966b  jz      short loc_18000968D
0x18000966d  mov     rcx, [rcx+10h]
0x180009671  lea     r9, aHrvalidatesoap_3; "HrValidateSOAPStructure(): Exiting"
0x180009678  mov     edx, 2Ch ; ','
0x18000967d  mov     [rsp+40h+var_20], ebx
0x180009681  lea     r8, WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids
0x180009688  call    WPP_SF_sd
0x18000968d  lea     r11, [rsp+40h+var_s0]
0x180009692  mov     eax, ebx
0x180009694  mov     rbx, [r11+30h]
0x180009698  mov     rdi, [r11+40h]
0x18000969c  mov     rsp, r11
0x18000969f  pop     r15
0x1800096a1  pop     r14
0x1800096a3  pop     r13
0x1800096a5  pop     r12
0x1800096a7  pop     rbp
0x1800096a8  retn
```
