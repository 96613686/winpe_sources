# CRootCause::SchdpInitializeDisplayInformation(IXMLDOMNode *)

- ea: `0x180005e30`
- end: `0x180005f59`
- name: `?SchdpInitializeDisplayInformation@CRootCause@@AEAAJPEAUIXMLDOMNode@@@Z`
- size: `297`
- prototype: `int(CRootCause *__hidden this, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180005b70`

## callees

- `0x180005e30`
- `0x18000b13c`
- `0x18000b608`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall CRootCause::SchdpInitializeDisplayInformation(CRootCause *this, struct IXMLDOMDocument2 *a2)
{
  struct IXMLDOMNode *v4; // rdi
  int Node; // eax
  struct IXMLDOMNode *v6; // rsi
  unsigned int v7; // ebx
  int v8; // r8d
  int v9; // eax
  struct IXMLDOMNode *v11; // [rsp+50h] [rbp+18h] BYREF
  struct IXMLDOMNode *v12; // [rsp+58h] [rbp+20h] BYREF

  v12 = 0;
  v4 = 0;
  v11 = 0;
  Node = SdpXmlGetNode(L"./DisplayInformation/Name", 0, a2, &v12);
  v6 = v12;
  v7 = Node;
  if ( Node < 0 )
  {
    v8 = 135;
LABEL_9:
    SdpDebugTrace(1u, L"CRootCause::SchdpInitializeDisplayInformation", v8, Node);
    goto LABEL_10;
  }
  Node = ((__int64 (__fastcall *)(struct IXMLDOMNode *, char *))v12->lpVtbl->get_text)(v12, (char *)this + 8);
  v7 = Node;
  if ( Node < 0 )
  {
    v8 = 138;
    goto LABEL_9;
  }
  v9 = SdpXmlGetNode(L"./DisplayInformation/Description", 0, a2, &v11);
  v7 = v9;
  if ( v9 < 0 )
  {
    SdpDebugTrace(1u, L"CRootCause::SchdpInitializeDisplayInformation", 144, v9);
    v4 = v11;
    goto LABEL_10;
  }
  v4 = v11;
  Node = ((__int64 (__fastcall *)(struct IXMLDOMNode *, char *))v11->lpVtbl->get_text)(v11, (char *)this + 16);
  v7 = Node;
  if ( Node < 0 )
  {
    v8 = 147;
    goto LABEL_9;
  }
LABEL_10:
  if ( v6 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v6->lpVtbl->Release)(v6);
  if ( v4 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v4->lpVtbl->Release)(v4);
  return v7;
}

```

## disassembly

```asm
0x180005e30  mov     rax, rsp
0x180005e33  mov     [rax+8], rbx
0x180005e37  mov     [rax+10h], rbp
0x180005e3b  push    rsi
0x180005e3c  push    rdi
0x180005e3d  push    r14
0x180005e3f  sub     rsp, 20h
0x180005e43  and     qword ptr [rax+20h], 0
0x180005e48  lea     r9, [rax+20h]; struct IXMLDOMNode **
0x180005e4c  mov     rbp, rdx
0x180005e4f  mov     r14, rcx
0x180005e52  mov     r8, rdx; struct IXMLDOMNode *
0x180005e55  lea     rcx, aDisplayinforma; "./DisplayInformation/Name"
0x180005e5c  xor     edi, edi
0x180005e5e  xor     edx, edx; struct IXMLDOMDocument2 *
0x180005e60  mov     [rax+18h], rdi
0x180005e64  call    ?SdpXmlGetNode@@YAJPEBGPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAU2@@Z; SdpXmlGetNode(ushort const *,IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNode * *)
0x180005e69  mov     rsi, [rsp+38h+arg_18]
0x180005e6e  mov     ebx, eax
0x180005e70  test    eax, eax
0x180005e72  jns     short loc_180005E7F
0x180005e74  mov     r8d, 87h
0x180005e7a  jmp     loc_180005F07
0x180005e7f  mov     rax, [rsi]
0x180005e82  lea     rdx, [r14+8]
0x180005e86  mov     rcx, rsi
0x180005e89  mov     rax, [rax+0D0h]
0x180005e90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e95  mov     ebx, eax
0x180005e97  test    eax, eax
0x180005e99  jns     short loc_180005EA3
0x180005e9b  mov     r8d, 8Ah
0x180005ea1  jmp     short loc_180005F07
0x180005ea3  lea     r9, [rsp+38h+arg_10]; struct IXMLDOMNode **
0x180005ea8  mov     r8, rbp; struct IXMLDOMNode *
0x180005eab  xor     edx, edx; struct IXMLDOMDocument2 *
0x180005ead  lea     rcx, aDisplayinforma_0; "./DisplayInformation/Description"
0x180005eb4  call    ?SdpXmlGetNode@@YAJPEBGPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAU2@@Z; SdpXmlGetNode(ushort const *,IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNode * *)
0x180005eb9  mov     ebx, eax
0x180005ebb  test    eax, eax
0x180005ebd  jns     short loc_180005EE0
0x180005ebf  mov     r9d, eax; int
0x180005ec2  lea     rdx, aCrootcauseSchd_0; "CRootCause::SchdpInitializeDisplayInfor"...
0x180005ec9  mov     r8d, 90h; int
0x180005ecf  mov     ecx, 1; Level
0x180005ed4  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180005ed9  mov     rdi, [rsp+38h+arg_10]
0x180005ede  jmp     short loc_180005F1B
0x180005ee0  mov     rdi, [rsp+38h+arg_10]
0x180005ee5  lea     rdx, [r14+10h]
0x180005ee9  mov     rcx, rdi
0x180005eec  mov     rax, [rdi]
0x180005eef  mov     rax, [rax+0D0h]
0x180005ef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005efb  mov     ebx, eax
0x180005efd  test    eax, eax
0x180005eff  jns     short loc_180005F1B
0x180005f01  mov     r8d, 93h; int
0x180005f07  mov     r9d, eax; int
0x180005f0a  lea     rdx, aCrootcauseSchd_0; "CRootCause::SchdpInitializeDisplayInfor"...
0x180005f11  mov     ecx, 1; Level
0x180005f16  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180005f1b  test    rsi, rsi
0x180005f1e  jz      short loc_180005F2F
0x180005f20  mov     rax, [rsi]
0x180005f23  mov     rcx, rsi
0x180005f26  mov     rax, [rax+10h]
0x180005f2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f2f  test    rdi, rdi
0x180005f32  jz      short loc_180005F43
0x180005f34  mov     rax, [rdi]
0x180005f37  mov     rcx, rdi
0x180005f3a  mov     rax, [rax+10h]
0x180005f3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f43  mov     rbp, [rsp+38h+arg_8]
0x180005f48  mov     eax, ebx
0x180005f4a  mov     rbx, [rsp+38h+arg_0]
0x180005f4f  add     rsp, 20h
0x180005f53  pop     r14
0x180005f55  pop     rdi
0x180005f56  pop     rsi
0x180005f57  retn
```
