# CNotification::SchdpInitializeNotification(IXMLDOMNode *)

- ea: `0x180002de0`
- end: `0x1800030fa`
- name: `?SchdpInitializeNotification@CNotification@@AEAAJPEAUIXMLDOMNode@@@Z`
- size: `794`
- prototype: `__int64 __fastcall(CNotification *__hidden this, struct IXMLDOMNode *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180002850`
- `0x180005260`

## callees

- `0x180002de0`
- `0x180003554`
- `0x18000b13c`
- `0x18000b234`
- `0x18000b498`
- `0x18000b884`
- `0x18000d010`

## import_xrefs

- `msvcrt!_wtoi` at `0x180002ed5`
- `msvcrt!_wtoi` at `0x180002f8d`
- `msvcrt!_wtoi` at `0x180002ed5`
- `msvcrt!_wtoi` at `0x180002f8d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800030c0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800030da`
- `OLEAUT32!__imp_SysFreeString` at `0x1800030c0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800030da`

## pseudocode

```c
__int64 __fastcall CNotification::SchdpInitializeNotification(struct IXMLDOMNode *this, struct IXMLDOMNode *a2)
{
  struct IXMLDOMNode *v2; // rdi
  int ChildNodes; // eax
  struct IXMLDOMNodeList *v5; // r14
  unsigned int v6; // ebx
  int v7; // r9d
  int v8; // r8d
  int v9; // eax
  int v10; // r8d
  int v11; // eax
  int v12; // eax
  unsigned int v13; // eax
  int v14; // eax
  unsigned int v15; // eax
  int v16; // eax
  wchar_t *String; // [rsp+20h] [rbp-20h] BYREF
  BSTR bstrString; // [rsp+28h] [rbp-18h] BYREF
  struct IXMLDOMNodeList *v20; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v21; // [rsp+80h] [rbp+40h] BYREF
  struct IXMLDOMNode *v22; // [rsp+88h] [rbp+48h] BYREF

  v20 = 0;
  v2 = 0;
  String = 0;
  bstrString = 0;
  v21 = 0;
  v22 = 0;
  ChildNodes = SdpXmlGetChildNodes(this, a2, &v20, &v21);
  v5 = v20;
  v6 = ChildNodes;
  if ( ChildNodes >= 0 )
  {
    v9 = SdpXmlNextNode(v20, &v22);
    v6 = v9;
    if ( v9 < 0 )
    {
      v10 = 194;
LABEL_5:
      SdpDebugTrace(1u, L"CNotification::SchdpInitializeNotification", v10, v9);
      v2 = v22;
      goto LABEL_40;
    }
    v2 = v22;
    v11 = SdpXmlCheckNode(v22, L"EventID");
    v6 = v11;
    if ( v11 < 0 )
    {
      v7 = v11;
LABEL_38:
      v8 = 195;
      goto LABEL_39;
    }
    if ( v11 == 1 || !v2 )
    {
      v7 = -2147467259;
      v6 = -2147467259;
      goto LABEL_38;
    }
    v12 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, wchar_t **))v2->lpVtbl->get_text)(v2, &String);
    v6 = v12;
    if ( v12 < 0 )
    {
      v8 = 198;
      goto LABEL_12;
    }
    v13 = _wtoi(String);
    if ( v13 > 0xFFFF )
    {
      v6 = -2147024362;
      LOWORD(this->lpVtbl) = -1;
      v7 = -2147024362;
      v8 = 201;
      goto LABEL_39;
    }
    LOWORD(this->lpVtbl) = v13;
    ((void (__fastcall *)(struct IXMLDOMNode *))v2->lpVtbl->Release)(v2);
    v22 = 0;
    v9 = SdpXmlNextNode(v5, &v22);
    v6 = v9;
    if ( v9 < 0 )
    {
      v10 = 206;
      goto LABEL_5;
    }
    v2 = v22;
    v14 = SdpXmlCheckNode(v22, L"EventVersion");
    v6 = v14;
    if ( v14 >= 0 )
    {
      if ( v14 != 1 && v2 )
      {
        v12 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))v2->lpVtbl->get_text)(v2, &bstrString);
        v6 = v12;
        if ( v12 >= 0 )
        {
          v15 = _wtoi(bstrString);
          if ( v15 > 0xFF )
          {
            v6 = -2147024362;
            BYTE2(this->lpVtbl) = 0;
            v7 = -2147024362;
            v8 = 213;
            goto LABEL_39;
          }
          BYTE2(this->lpVtbl) = v15;
          ((void (__fastcall *)(struct IXMLDOMNode *))v2->lpVtbl->Release)(v2);
          v22 = 0;
          v9 = SdpXmlNextNode(v5, &v22);
          v6 = v9;
          if ( v9 < 0 )
          {
            v10 = 218;
            goto LABEL_5;
          }
          v2 = v22;
          v16 = SdpXmlCheckNode(v22, L"EventData");
          v6 = v16;
          if ( v16 >= 0 )
          {
            if ( v16 != 1 && v2 )
            {
              v12 = CNotification::SchdpInitializePayload((CNotification *)this, v2);
              v6 = v12;
              if ( v12 >= 0 )
                goto LABEL_40;
              v8 = 222;
              goto LABEL_12;
            }
            v7 = -2147467259;
            v6 = -2147467259;
          }
          else
          {
            v7 = v16;
          }
          v8 = 219;
          goto LABEL_39;
        }
        v8 = 210;
LABEL_12:
        v7 = v12;
        goto LABEL_39;
      }
      v7 = -2147467259;
      v6 = -2147467259;
    }
    else
    {
      v7 = v14;
    }
    v8 = 207;
    goto LABEL_39;
  }
  v7 = ChildNodes;
  v8 = 191;
LABEL_39:
  SdpDebugTrace(1u, L"CNotification::SchdpInitializeNotification", v8, v7);
LABEL_40:
  if ( v5 )
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v5->lpVtbl->Release)(v5);
  if ( v2 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v2->lpVtbl->Release)(v2);
  if ( String )
  {
    SysFreeString(String);
    String = 0;
  }
  if ( bstrString )
    SysFreeString(bstrString);
  return v6;
}

```

## disassembly

```asm
0x180002de0  mov     [rsp-28h+arg_0], rbx
0x180002de5  push    rbp
0x180002de6  push    rsi
0x180002de7  push    rdi
0x180002de8  push    r14
0x180002dea  push    r15
0x180002dec  mov     rbp, rsp
0x180002def  sub     rsp, 40h
0x180002df3  and     [rbp+var_10], 0
0x180002df8  lea     r9, [rbp+arg_10]; unsigned int *
0x180002dfc  xor     edi, edi
0x180002dfe  lea     r8, [rbp+var_10]; struct IXMLDOMNodeList **
0x180002e02  and     [rbp+String], rdi
0x180002e06  mov     r15, rcx
0x180002e09  and     [rbp+bstrString], rdi
0x180002e0d  and     [rbp+arg_10], edi
0x180002e10  mov     [rbp+arg_18], rdi
0x180002e14  call    ?SdpXmlGetChildNodes@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@PEAK@Z; SdpXmlGetChildNodes(IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *,ulong *)
0x180002e19  mov     r14, [rbp+var_10]
0x180002e1d  mov     ebx, eax
0x180002e1f  test    eax, eax
0x180002e21  jns     short loc_180002E34
0x180002e23  mov     r9d, eax
0x180002e26  lea     ecx, [rdi+1]
0x180002e29  mov     r8d, 0BFh
0x180002e2f  jmp     loc_180003083
0x180002e34  lea     rdx, [rbp+arg_18]; struct IXMLDOMNode **
0x180002e38  mov     rcx, r14; struct IXMLDOMNodeList *
0x180002e3b  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x180002e40  mov     ebx, eax
0x180002e42  test    eax, eax
0x180002e44  jns     short loc_180002E69
0x180002e46  mov     r8d, 0C2h; int
0x180002e4c  mov     ecx, 1; Level
0x180002e51  mov     r9d, eax; int
0x180002e54  lea     rdx, aCnotificationS_6; "CNotification::SchdpInitializeNotificat"...
0x180002e5b  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180002e60  mov     rdi, [rbp+arg_18]
0x180002e64  jmp     loc_18000308F
0x180002e69  mov     rdi, [rbp+arg_18]
0x180002e6d  lea     rdx, aEventid; "EventID"
0x180002e74  mov     rcx, rdi; struct IXMLDOMNode *
0x180002e77  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x180002e7c  mov     ebx, eax
0x180002e7e  test    eax, eax
0x180002e80  jns     short loc_180002E8F
0x180002e82  mov     r9d, eax
0x180002e85  mov     ecx, 1
0x180002e8a  jmp     loc_18000307D
0x180002e8f  mov     esi, 1
0x180002e94  cmp     eax, esi
0x180002e96  jz      loc_180003072
0x180002e9c  test    rdi, rdi
0x180002e9f  jz      loc_180003072
0x180002ea5  mov     rax, [rdi]
0x180002ea8  lea     rdx, [rbp+String]
0x180002eac  mov     rcx, rdi
0x180002eaf  mov     rax, [rax+0D0h]
0x180002eb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ebb  mov     ebx, eax
0x180002ebd  test    eax, eax
0x180002ebf  jns     short loc_180002ED1
0x180002ec1  mov     r8d, 0C6h
0x180002ec7  mov     r9d, eax
0x180002eca  mov     ecx, esi
0x180002ecc  jmp     loc_180003083
0x180002ed1  mov     rcx, [rbp+String]; String
0x180002ed5  call    cs:__imp__wtoi
0x180002edc  nop     dword ptr [rax+rax+00h]
0x180002ee1  mov     ecx, 0FFFFh
0x180002ee6  cmp     eax, ecx
0x180002ee8  ja      loc_18000305B
0x180002eee  mov     [r15], ax
0x180002ef2  test    rdi, rdi
0x180002ef5  jz      short loc_180002F0B
0x180002ef7  mov     rax, [rdi]
0x180002efa  mov     rcx, rdi
0x180002efd  mov     rax, [rax+10h]
0x180002f01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f06  and     [rbp+arg_18], 0
0x180002f0b  lea     rdx, [rbp+arg_18]; struct IXMLDOMNode **
0x180002f0f  mov     rcx, r14; struct IXMLDOMNodeList *
0x180002f12  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x180002f17  mov     ebx, eax
0x180002f19  test    eax, eax
0x180002f1b  jns     short loc_180002F2A
0x180002f1d  mov     r8d, 0CEh
0x180002f23  mov     ecx, esi
0x180002f25  jmp     loc_180002E51
0x180002f2a  mov     rdi, [rbp+arg_18]
0x180002f2e  lea     rdx, aEventversion; "EventVersion"
0x180002f35  mov     rcx, rdi; struct IXMLDOMNode *
0x180002f38  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x180002f3d  mov     ebx, eax
0x180002f3f  test    eax, eax
0x180002f41  jns     short loc_180002F51
0x180002f43  mov     r9d, eax
0x180002f46  mov     r8d, 0CFh
0x180002f4c  jmp     loc_180002ECA
0x180002f51  cmp     eax, esi
0x180002f53  jz      loc_18000304D
0x180002f59  test    rdi, rdi
0x180002f5c  jz      loc_18000304D
0x180002f62  mov     rax, [rdi]
0x180002f65  lea     rdx, [rbp+bstrString]
0x180002f69  mov     rcx, rdi
0x180002f6c  mov     rax, [rax+0D0h]
0x180002f73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f78  mov     ebx, eax
0x180002f7a  test    eax, eax
0x180002f7c  jns     short loc_180002F89
0x180002f7e  mov     r8d, 0D2h
0x180002f84  jmp     loc_180002EC7
0x180002f89  mov     rcx, [rbp+bstrString]; String
0x180002f8d  call    cs:__imp__wtoi
0x180002f94  nop     dword ptr [rax+rax+00h]
0x180002f99  cmp     eax, 0FFh
0x180002f9e  ja      loc_180003035
0x180002fa4  mov     [r15+2], al
0x180002fa8  test    rdi, rdi
0x180002fab  jz      short loc_180002FC1
0x180002fad  mov     rax, [rdi]
0x180002fb0  mov     rcx, rdi
0x180002fb3  mov     rax, [rax+10h]
0x180002fb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fbc  and     [rbp+arg_18], 0
0x180002fc1  lea     rdx, [rbp+arg_18]; struct IXMLDOMNode **
0x180002fc5  mov     rcx, r14; struct IXMLDOMNodeList *
0x180002fc8  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x180002fcd  mov     ebx, eax
0x180002fcf  test    eax, eax
0x180002fd1  jns     short loc_180002FDE
0x180002fd3  mov     r8d, 0DAh
0x180002fd9  jmp     loc_180002F23
0x180002fde  mov     rdi, [rbp+arg_18]
0x180002fe2  lea     rdx, aEventdata; "EventData"
0x180002fe9  mov     rcx, rdi; struct IXMLDOMNode *
0x180002fec  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x180002ff1  mov     ebx, eax
0x180002ff3  test    eax, eax
0x180002ff5  jns     short loc_180003005
0x180002ff7  mov     r9d, eax
0x180002ffa  mov     r8d, 0DBh
0x180003000  jmp     loc_180002ECA
0x180003005  cmp     eax, esi
0x180003007  jz      short loc_18000302A
0x180003009  test    rdi, rdi
0x18000300c  jz      short loc_18000302A
0x18000300e  mov     rdx, rdi; struct IXMLDOMNode *
0x180003011  mov     rcx, r15; this
0x180003014  call    ?SchdpInitializePayload@CNotification@@AEAAJPEAUIXMLDOMNode@@@Z; CNotification::SchdpInitializePayload(IXMLDOMNode *)
0x180003019  mov     ebx, eax
0x18000301b  test    eax, eax
0x18000301d  jns     short loc_18000308F
0x18000301f  mov     r8d, 0DEh
0x180003025  jmp     loc_180002EC7
0x18000302a  mov     r9d, 80004005h
0x180003030  mov     ebx, r9d
0x180003033  jmp     short loc_180002FFA
0x180003035  mov     ebx, 80070216h
0x18000303a  mov     byte ptr [r15+2], 0
0x18000303f  mov     r9d, ebx
0x180003042  mov     r8d, 0D5h
0x180003048  jmp     loc_180002ECA
0x18000304d  mov     r9d, 80004005h
0x180003053  mov     ebx, r9d
0x180003056  jmp     loc_180002F46
0x18000305b  mov     ebx, 80070216h
0x180003060  mov     [r15], cx
0x180003064  mov     r9d, ebx
0x180003067  mov     r8d, 0C9h
0x18000306d  jmp     loc_180002ECA
0x180003072  mov     r9d, 80004005h; int
0x180003078  mov     ecx, esi; Level
0x18000307a  mov     ebx, r9d
0x18000307d  mov     r8d, 0C3h; int
0x180003083  lea     rdx, aCnotificationS_6; "CNotification::SchdpInitializeNotificat"...
0x18000308a  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000308f  test    r14, r14
0x180003092  jz      short loc_1800030A3
0x180003094  mov     rax, [r14]
0x180003097  mov     rcx, r14
0x18000309a  mov     rax, [rax+10h]
0x18000309e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030a3  test    rdi, rdi
0x1800030a6  jz      short loc_1800030B7
0x1800030a8  mov     rax, [rdi]
0x1800030ab  mov     rcx, rdi
0x1800030ae  mov     rax, [rax+10h]
0x1800030b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030b7  mov     rcx, [rbp+String]; bstrString
0x1800030bb  test    rcx, rcx
0x1800030be  jz      short loc_1800030D1
0x1800030c0  call    cs:__imp_SysFreeString
0x1800030c7  nop     dword ptr [rax+rax+00h]
0x1800030cc  and     [rbp+String], 0
0x1800030d1  mov     rcx, [rbp+bstrString]; bstrString
0x1800030d5  test    rcx, rcx
0x1800030d8  jz      short loc_1800030E6
0x1800030da  call    cs:__imp_SysFreeString
0x1800030e1  nop     dword ptr [rax+rax+00h]
0x1800030e6  mov     eax, ebx
0x1800030e8  mov     rbx, [rsp+40h+arg_0]
0x1800030ed  add     rsp, 40h
0x1800030f1  pop     r15
0x1800030f3  pop     r14
0x1800030f5  pop     rdi
0x1800030f6  pop     rsi
0x1800030f7  pop     rbp
0x1800030f8  retn
```
