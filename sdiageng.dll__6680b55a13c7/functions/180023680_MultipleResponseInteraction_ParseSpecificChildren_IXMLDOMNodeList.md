# MultipleResponseInteraction::ParseSpecificChildren(IXMLDOMNodeList *)

- ea: `0x180023680`
- end: `0x180023810`
- name: `?ParseSpecificChildren@MultipleResponseInteraction@@MEAAJPEAUIXMLDOMNodeList@@@Z`
- size: `400`
- prototype: `__int64 __fastcall(MultipleResponseInteraction *this, struct IXMLDOMNodeList *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003814`
- `0x180023680`
- `0x180026fa0`
- `0x180028038`
- `0x1800290bc`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall MultipleResponseInteraction::ParseSpecificChildren(
        MultipleResponseInteraction *this,
        struct IXMLDOMNodeList *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  int v6; // r8d
  struct IXMLDOMNode *v7; // rdi
  int v8; // eax
  int v9; // r9d
  int v10; // eax
  int v11; // r8d
  int v12; // eax
  struct IXMLDOMNode *v14; // [rsp+50h] [rbp+18h] BYREF

  v14 = 0;
  v4 = SdpXmlNextNode(a2, &v14);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = 682;
LABEL_3:
    SdpDebugTrace(1u, L"MultipleResponseInteraction::ParseSpecificChildren", v6, v4);
    v7 = v14;
    goto LABEL_24;
  }
  v7 = v14;
  v8 = SdpXmlCheckNode(v14, L"AllowDynamicResponses");
  v5 = v8;
  if ( v8 < 0 )
  {
    v9 = v8;
LABEL_22:
    v11 = 683;
    goto LABEL_23;
  }
  if ( v8 == 1 || !v7 )
  {
    v9 = -2147467259;
    v5 = -2147467259;
    goto LABEL_22;
  }
  v10 = SdpParseBooleanNode(v7, (int *)this + 24);
  v5 = v10;
  if ( v10 >= 0 )
  {
    ((void (__fastcall *)(struct IXMLDOMNode *))v7->lpVtbl->Release)(v7);
    v14 = 0;
    v4 = SdpXmlNextNode(a2, &v14);
    v5 = v4;
    if ( v4 < 0 )
    {
      v6 = 694;
      goto LABEL_3;
    }
    v7 = v14;
    v12 = SdpXmlCheckNode(v14, L"Choices");
    v5 = v12;
    if ( v12 >= 0 )
    {
      if ( v12 != 1 && v7 )
      {
        v10 = (*(__int64 (__fastcall **)(MultipleResponseInteraction *, struct IXMLDOMNode *))(*(_QWORD *)this + 80LL))(
                this,
                v7);
        v5 = v10;
        if ( v10 >= 0 )
          goto LABEL_24;
        v11 = 698;
        goto LABEL_10;
      }
      v9 = -2147467259;
      v5 = -2147467259;
    }
    else
    {
      v9 = v12;
    }
    v11 = 695;
    goto LABEL_23;
  }
  v11 = 686;
LABEL_10:
  v9 = v10;
LABEL_23:
  SdpDebugTrace(1u, L"MultipleResponseInteraction::ParseSpecificChildren", v11, v9);
LABEL_24:
  if ( v7 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v7->lpVtbl->Release)(v7);
  return v5;
}

```

## disassembly

```asm
0x180023680  mov     rax, rsp
0x180023683  mov     [rax+8], rbx
0x180023687  mov     [rax+10h], rbp
0x18002368b  push    rsi
0x18002368c  push    rdi
0x18002368d  push    r14
0x18002368f  sub     rsp, 20h
0x180023693  mov     rbp, rdx
0x180023696  mov     qword ptr [rax+18h], 0
0x18002369e  mov     r14, rcx
0x1800236a1  lea     rdx, [rax+18h]; struct IXMLDOMNode **
0x1800236a5  mov     rcx, rbp; struct IXMLDOMNodeList *
0x1800236a8  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x1800236ad  mov     ebx, eax
0x1800236af  test    eax, eax
0x1800236b1  jns     short loc_1800236D7
0x1800236b3  mov     r8d, 2AAh; int
0x1800236b9  mov     ecx, 1; Level
0x1800236be  lea     rdx, aMultiplerespon_11; "MultipleResponseInteraction::ParseSpeci"...
0x1800236c5  mov     r9d, eax; int
0x1800236c8  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800236cd  mov     rdi, [rsp+38h+arg_10]
0x1800236d2  jmp     loc_1800237E7
0x1800236d7  mov     rdi, [rsp+38h+arg_10]
0x1800236dc  lea     rdx, aAllowdynamicre; "AllowDynamicResponses"
0x1800236e3  mov     rcx, rdi; struct IXMLDOMNode *
0x1800236e6  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x1800236eb  mov     ebx, eax
0x1800236ed  test    eax, eax
0x1800236ef  jns     short loc_1800236FE
0x1800236f1  mov     r9d, eax
0x1800236f4  mov     ecx, 1
0x1800236f9  jmp     loc_1800237D5
0x1800236fe  mov     esi, 1
0x180023703  cmp     eax, esi
0x180023705  jz      loc_1800237CA
0x18002370b  test    rdi, rdi
0x18002370e  jz      loc_1800237CA
0x180023714  lea     rdx, [r14+60h]; int *
0x180023718  mov     rcx, rdi; struct IXMLDOMNode *
0x18002371b  call    ?SdpParseBooleanNode@@YAJPEAUIXMLDOMNode@@PEAH@Z; SdpParseBooleanNode(IXMLDOMNode *,int *)
0x180023720  mov     ebx, eax
0x180023722  test    eax, eax
0x180023724  jns     short loc_180023736
0x180023726  mov     r8d, 2AEh
0x18002372c  mov     r9d, eax
0x18002372f  mov     ecx, esi
0x180023731  jmp     loc_1800237DB
0x180023736  mov     rax, [rdi]
0x180023739  mov     rcx, rdi
0x18002373c  mov     rax, [rax+10h]
0x180023740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023745  lea     rdx, [rsp+38h+arg_10]; struct IXMLDOMNode **
0x18002374a  mov     [rsp+38h+arg_10], 0
0x180023753  mov     rcx, rbp; struct IXMLDOMNodeList *
0x180023756  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x18002375b  mov     ebx, eax
0x18002375d  test    eax, eax
0x18002375f  jns     short loc_18002376E
0x180023761  mov     r8d, 2B6h
0x180023767  mov     ecx, esi
0x180023769  jmp     loc_1800236BE
0x18002376e  mov     rdi, [rsp+38h+arg_10]
0x180023773  lea     rdx, aChoices; "Choices"
0x18002377a  mov     rcx, rdi; struct IXMLDOMNode *
0x18002377d  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x180023782  mov     ebx, eax
0x180023784  test    eax, eax
0x180023786  jns     short loc_180023793
0x180023788  mov     r9d, eax
0x18002378b  mov     r8d, 2B7h
0x180023791  jmp     short loc_18002372F
0x180023793  cmp     eax, esi
0x180023795  jz      short loc_1800237BF
0x180023797  test    rdi, rdi
0x18002379a  jz      short loc_1800237BF
0x18002379c  mov     rax, [r14]
0x18002379f  mov     rdx, rdi
0x1800237a2  mov     rcx, r14
0x1800237a5  mov     rax, [rax+50h]
0x1800237a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800237ae  mov     ebx, eax
0x1800237b0  test    eax, eax
0x1800237b2  jns     short loc_1800237E7
0x1800237b4  mov     r8d, 2BAh
0x1800237ba  jmp     loc_18002372C
0x1800237bf  mov     r9d, 80004005h
0x1800237c5  mov     ebx, r9d
0x1800237c8  jmp     short loc_18002378B
0x1800237ca  mov     r9d, 80004005h; int
0x1800237d0  mov     ecx, esi; Level
0x1800237d2  mov     ebx, r9d
0x1800237d5  mov     r8d, 2ABh; int
0x1800237db  lea     rdx, aMultiplerespon_11; "MultipleResponseInteraction::ParseSpeci"...
0x1800237e2  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800237e7  test    rdi, rdi
0x1800237ea  jz      short loc_1800237FB
0x1800237ec  mov     rax, [rdi]
0x1800237ef  mov     rcx, rdi
0x1800237f2  mov     rax, [rax+10h]
0x1800237f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800237fb  mov     rbp, [rsp+38h+arg_8]
0x180023800  mov     eax, ebx
0x180023802  mov     rbx, [rsp+38h+arg_0]
0x180023807  add     rsp, 20h
0x18002380b  pop     r14
0x18002380d  pop     rdi
0x18002380e  pop     rsi
0x18002380f  retn
```
