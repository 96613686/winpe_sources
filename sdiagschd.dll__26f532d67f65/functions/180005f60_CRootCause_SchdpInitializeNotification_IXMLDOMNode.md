# CRootCause::SchdpInitializeNotification(IXMLDOMNode *)

- ea: `0x180005f60`
- end: `0x1800060b5`
- name: `?SchdpInitializeNotification@CRootCause@@AEAAJPEAUIXMLDOMNode@@@Z`
- size: `341`
- prototype: `int(CRootCause *__hidden this, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180005b70`

## callees

- `0x180001174`
- `0x180002850`
- `0x180005f60`
- `0x18000b13c`
- `0x18000b608`
- `0x18000d010`

## string_xrefs

- `0x180005fcc`: `./ExtensionPoint/Notification`

## pseudocode

```c
__int64 __fastcall CRootCause::SchdpInitializeNotification(CRootCause *this, struct IXMLDOMDocument2 *a2)
{
  int Node; // eax
  struct IXMLDOMNode *v5; // rsi
  unsigned int v6; // ebx
  int v7; // eax
  struct IXMLDOMNode *v8; // rdi
  char *v9; // rax
  int v10; // r8d
  int v11; // r9d
  int v12; // eax
  struct IXMLDOMNode *v14; // [rsp+50h] [rbp+18h] BYREF
  struct IXMLDOMNode *v15; // [rsp+58h] [rbp+20h] BYREF

  v15 = 0;
  v14 = 0;
  Node = SdpXmlGetNode(L"./Parameters", 0, a2, &v14);
  v5 = v14;
  v6 = Node;
  if ( Node < 0 )
  {
    SdpDebugTrace(1u, L"CRootCause::SchdpInitializeNotification", 189, Node);
    goto LABEL_15;
  }
  v7 = SdpXmlGetNode(L"./ExtensionPoint/Notification", 0, a2, &v15);
  v6 = v7;
  if ( v7 < 0 )
  {
    SdpDebugTrace(2u, L"CRootCause::SchdpInitializeNotification", 195, v7);
    v6 = 0;
  }
  v8 = v15;
  if ( v15 )
  {
    v9 = (char *)operator new(0x20u);
    if ( v9 )
    {
      *(_WORD *)v9 = 0;
      v9[2] = 0;
      *(_QWORD *)(v9 + 4) = 0;
      *((_DWORD *)v9 + 3) = 0;
      *((_QWORD *)v9 + 2) = 0;
      *((_QWORD *)v9 + 3) = 0;
    }
    else
    {
      v9 = 0;
    }
    *((_QWORD *)this + 4) = v9;
    if ( v9 )
    {
      v12 = CNotification::Initialize((CNotification *)v9, v8, v5);
      v6 = v12;
      if ( v12 >= 0 )
      {
LABEL_14:
        ((void (__fastcall *)(struct IXMLDOMNode *))v8->lpVtbl->Release)(v8);
        goto LABEL_15;
      }
      v11 = v12;
      v10 = 202;
    }
    else
    {
      v6 = -2147024882;
      v10 = 199;
      v11 = -2147024882;
    }
    SdpDebugTrace(1u, L"CRootCause::SchdpInitializeNotification", v10, v11);
    goto LABEL_14;
  }
LABEL_15:
  if ( v5 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v5->lpVtbl->Release)(v5);
  return v6;
}

```

## disassembly

```asm
0x180005f60  mov     rax, rsp
0x180005f63  mov     [rax+8], rbx
0x180005f67  mov     [rax+10h], rbp
0x180005f6b  push    rsi
0x180005f6c  push    rdi
0x180005f6d  push    r14
0x180005f6f  sub     rsp, 20h
0x180005f73  mov     rdi, rdx
0x180005f76  lea     r9, [rax+18h]; struct IXMLDOMNode **
0x180005f7a  mov     rbp, rcx
0x180005f7d  xor     r14d, r14d
0x180005f80  mov     r8, rdx; struct IXMLDOMNode *
0x180005f83  mov     [rax+20h], r14
0x180005f87  xor     edx, edx; struct IXMLDOMDocument2 *
0x180005f89  mov     [rax+18h], r14
0x180005f8d  lea     rcx, aParameters; "./Parameters"
0x180005f94  call    ?SdpXmlGetNode@@YAJPEBGPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAU2@@Z; SdpXmlGetNode(ushort const *,IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNode * *)
0x180005f99  mov     rsi, [rsp+38h+arg_10]
0x180005f9e  mov     ebx, eax
0x180005fa0  test    eax, eax
0x180005fa2  jns     short loc_180005FC2
0x180005fa4  mov     r9d, eax; int
0x180005fa7  lea     rdx, aCrootcauseSchd_3; "CRootCause::SchdpInitializeNotification"
0x180005fae  mov     r8d, 0BDh; int
0x180005fb4  lea     ecx, [r14+1]; Level
0x180005fb8  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180005fbd  jmp     loc_18000608B
0x180005fc2  lea     r9, [rsp+38h+arg_18]; struct IXMLDOMNode **
0x180005fc7  mov     r8, rdi; struct IXMLDOMNode *
0x180005fca  xor     edx, edx; struct IXMLDOMDocument2 *
0x180005fcc  lea     rcx, aExtensionpoint; "./ExtensionPoint/Notification"
0x180005fd3  call    ?SdpXmlGetNode@@YAJPEBGPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAU2@@Z; SdpXmlGetNode(ushort const *,IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNode * *)
0x180005fd8  mov     ebx, eax
0x180005fda  test    eax, eax
0x180005fdc  jns     short loc_180005FFB
0x180005fde  mov     r9d, eax; int
0x180005fe1  lea     rdx, aCrootcauseSchd_3; "CRootCause::SchdpInitializeNotification"
0x180005fe8  mov     r8d, 0C3h; int
0x180005fee  mov     ecx, 2; Level
0x180005ff3  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180005ff8  mov     ebx, r14d
0x180005ffb  mov     rdi, [rsp+38h+arg_18]
0x180006000  test    rdi, rdi
0x180006003  jz      loc_18000608B
0x180006009  mov     ecx, 20h ; ' '; Size
0x18000600e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006013  test    rax, rax
0x180006016  jz      short loc_180006032
0x180006018  mov     [rax], r14w
0x18000601c  mov     [rax+2], r14b
0x180006020  mov     [rax+4], r14
0x180006024  mov     [rax+0Ch], r14d
0x180006028  mov     [rax+10h], r14
0x18000602c  mov     [rax+18h], r14
0x180006030  jmp     short loc_180006035
0x180006032  mov     rax, r14
0x180006035  mov     [rbp+20h], rax
0x180006039  test    rax, rax
0x18000603c  jnz     short loc_18000604E
0x18000603e  mov     ebx, 8007000Eh
0x180006043  mov     r8d, 0C7h
0x180006049  mov     r9d, ebx
0x18000604c  jmp     short loc_18000606B
0x18000604e  mov     r8, rsi; struct IXMLDOMNode *
0x180006051  mov     rdx, rdi; struct IXMLDOMNode *
0x180006054  mov     rcx, rax; this
0x180006057  call    ?Initialize@CNotification@@QEAAJPEAUIXMLDOMNode@@0@Z; CNotification::Initialize(IXMLDOMNode *,IXMLDOMNode *)
0x18000605c  mov     ebx, eax
0x18000605e  test    eax, eax
0x180006060  jns     short loc_18000607C
0x180006062  mov     r9d, eax; int
0x180006065  mov     r8d, 0CAh; int
0x18000606b  lea     rdx, aCrootcauseSchd_3; "CRootCause::SchdpInitializeNotification"
0x180006072  mov     ecx, 1; Level
0x180006077  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000607c  mov     rax, [rdi]
0x18000607f  mov     rcx, rdi
0x180006082  mov     rax, [rax+10h]
0x180006086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000608b  test    rsi, rsi
0x18000608e  jz      short loc_18000609F
0x180006090  mov     rax, [rsi]
0x180006093  mov     rcx, rsi
0x180006096  mov     rax, [rax+10h]
0x18000609a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000609f  mov     rbp, [rsp+38h+arg_8]
0x1800060a4  mov     eax, ebx
0x1800060a6  mov     rbx, [rsp+38h+arg_0]
0x1800060ab  add     rsp, 20h
0x1800060af  pop     r14
0x1800060b1  pop     rdi
0x1800060b2  pop     rsi
0x1800060b3  retn
```
