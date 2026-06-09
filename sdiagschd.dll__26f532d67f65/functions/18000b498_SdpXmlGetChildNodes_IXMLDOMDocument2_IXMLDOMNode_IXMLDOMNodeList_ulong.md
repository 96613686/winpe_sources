# SdpXmlGetChildNodes(IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *,ulong *)

- ea: `0x18000b498`
- end: `0x18000b601`
- name: `?SdpXmlGetChildNodes@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@PEAK@Z`
- size: `361`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *, struct IXMLDOMNode *, struct IXMLDOMNodeList **, unsigned int *)`
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180002de0`
- `0x180003100`
- `0x180003384`
- `0x180003554`
- `0x180003e10`
- `0x1800040b4`

## callees

- `0x18000b13c`
- `0x18000b498`
- `0x18000b884`
- `0x18000d010`

## string_xrefs

- `0x18000b4d3`: `SdpXmlGetChildNodes`
- `0x18000b547`: `SdpXmlGetNumChildNodes`

## pseudocode

```c
__int64 __fastcall SdpXmlGetChildNodes(
        struct IXMLDOMNode *a1,
        struct IXMLDOMNode *a2,
        struct IXMLDOMNodeList **a3,
        unsigned int *a4)
{
  int v6; // r8d
  unsigned int v7; // ebx
  int v8; // r9d
  int v9; // eax
  struct IXMLDOMNodeList *v10; // rsi
  unsigned int v11; // edi
  struct IXMLDOMNodeList *v12; // rcx
  struct IXMLDOMNode *v14; // [rsp+40h] [rbp+8h] BYREF
  struct IXMLDOMNodeList *v15; // [rsp+50h] [rbp+18h] BYREF

  v14 = a1;
  v15 = 0;
  if ( a3 )
  {
    if ( a4 )
    {
      if ( !a2 )
      {
        v7 = -2147467261;
        v6 = 804;
        v8 = -2147467261;
        goto LABEL_4;
      }
      v9 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, struct IXMLDOMNodeList **))a2->lpVtbl->get_childNodes)(
             a2,
             &v15);
      v7 = v9;
      if ( v9 < 0 )
      {
        v8 = v9;
        v6 = 806;
        goto LABEL_4;
      }
      v10 = v15;
      v11 = 0;
      v14 = 0;
      if ( v15 )
      {
        while ( 1 )
        {
          SdpXmlNextNode(v10, &v14);
          if ( !v14 )
            break;
          ((void (__fastcall *)(struct IXMLDOMNode *))v14->lpVtbl->Release)(v14);
          v14 = 0;
          ++v11;
        }
        ((void (__fastcall *)(struct IXMLDOMNodeList *))v10->lpVtbl->reset)(v10);
        v12 = v15;
        v7 = 0;
        *a3 = v15;
        *a4 = v11;
        ((void (__fastcall *)(struct IXMLDOMNodeList *))v12->lpVtbl->AddRef)(v12);
        goto LABEL_16;
      }
      SdpDebugTrace(1u, L"SdpXmlGetNumChildNodes", 857, -2147024809);
      v6 = 810;
    }
    else
    {
      v6 = 791;
    }
  }
  else
  {
    v6 = 790;
  }
  v7 = -2147024809;
  v8 = -2147024809;
LABEL_4:
  SdpDebugTrace(1u, L"SdpXmlGetChildNodes", v6, v8);
LABEL_16:
  if ( v15 )
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v15->lpVtbl->Release)(v15);
  return v7;
}

```

## disassembly

```asm
0x18000b498  mov     rax, rsp
0x18000b49b  mov     [rax+10h], rbx
0x18000b49f  mov     [rax+20h], rsi
0x18000b4a3  mov     [rax+8], rcx
0x18000b4a7  push    rdi
0x18000b4a8  push    r14
0x18000b4aa  push    r15
0x18000b4ac  sub     rsp, 20h
0x18000b4b0  and     qword ptr [rax+18h], 0
0x18000b4b5  mov     r14, r9
0x18000b4b8  mov     r15, r8
0x18000b4bb  mov     r10, rdx
0x18000b4be  test    r8, r8
0x18000b4c1  jnz     short loc_18000B4E9
0x18000b4c3  mov     r8d, 316h; int
0x18000b4c9  mov     edi, 80070057h
0x18000b4ce  mov     ebx, edi
0x18000b4d0  mov     r9d, edi; int
0x18000b4d3  lea     rdx, aSdpxmlgetchild; "SdpXmlGetChildNodes"
0x18000b4da  mov     ecx, 1; Level
0x18000b4df  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000b4e4  jmp     loc_18000B5D4
0x18000b4e9  test    r14, r14
0x18000b4ec  jnz     short loc_18000B4F6
0x18000b4ee  mov     r8d, 317h
0x18000b4f4  jmp     short loc_18000B4C9
0x18000b4f6  test    r10, r10
0x18000b4f9  jnz     short loc_18000B50B
0x18000b4fb  mov     ebx, 80004003h
0x18000b500  mov     r8d, 324h
0x18000b506  mov     r9d, ebx
0x18000b509  jmp     short loc_18000B4D3
0x18000b50b  mov     rax, [rdx]
0x18000b50e  mov     rcx, r10
0x18000b511  lea     rdx, [rsp+38h+arg_10]
0x18000b516  mov     rax, [rax+60h]
0x18000b51a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b51f  mov     ebx, eax
0x18000b521  test    eax, eax
0x18000b523  jns     short loc_18000B530
0x18000b525  mov     r9d, eax
0x18000b528  mov     r8d, 326h
0x18000b52e  jmp     short loc_18000B4D3
0x18000b530  mov     rsi, [rsp+38h+arg_10]
0x18000b535  xor     edi, edi
0x18000b537  and     [rsp+38h+arg_0], 0
0x18000b53d  test    rsi, rsi
0x18000b540  jnz     short loc_18000B581
0x18000b542  mov     edi, 80070057h
0x18000b547  lea     rdx, aSdpxmlgetnumch; "SdpXmlGetNumChildNodes"
0x18000b54e  mov     r9d, edi; int
0x18000b551  lea     ecx, [rsi+1]; Level
0x18000b554  mov     r8d, 359h; int
0x18000b55a  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000b55f  mov     r8d, 32Ah
0x18000b565  jmp     loc_18000B4CE
0x18000b56a  mov     rax, [rbx]
0x18000b56d  mov     rcx, rbx
0x18000b570  mov     rax, [rax+10h]
0x18000b574  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b579  and     [rsp+38h+arg_0], 0
0x18000b57f  inc     edi
0x18000b581  lea     rdx, [rsp+38h+arg_0]; struct IXMLDOMNode **
0x18000b586  mov     rcx, rsi; struct IXMLDOMNodeList *
0x18000b589  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x18000b58e  mov     rbx, [rsp+38h+arg_0]
0x18000b593  test    rbx, rbx
0x18000b596  jnz     short loc_18000B56A
0x18000b598  mov     rax, [rsi]
0x18000b59b  mov     rcx, rsi
0x18000b59e  mov     rax, [rax+50h]
0x18000b5a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5a7  test    rbx, rbx
0x18000b5aa  jz      short loc_18000B5BB
0x18000b5ac  mov     rax, [rbx]
0x18000b5af  mov     rcx, rbx
0x18000b5b2  mov     rax, [rax+10h]
0x18000b5b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5bb  mov     rcx, [rsp+38h+arg_10]
0x18000b5c0  xor     ebx, ebx
0x18000b5c2  mov     [r15], rcx
0x18000b5c5  mov     [r14], edi
0x18000b5c8  mov     rax, [rcx]
0x18000b5cb  mov     rax, [rax+8]
0x18000b5cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5d4  mov     rcx, [rsp+38h+arg_10]
0x18000b5d9  test    rcx, rcx
0x18000b5dc  jz      short loc_18000B5EA
0x18000b5de  mov     rax, [rcx]
0x18000b5e1  mov     rax, [rax+10h]
0x18000b5e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5ea  mov     rsi, [rsp+38h+arg_18]
0x18000b5ef  mov     eax, ebx
0x18000b5f1  mov     rbx, [rsp+38h+arg_8]
0x18000b5f6  add     rsp, 20h
0x18000b5fa  pop     r15
0x18000b5fc  pop     r14
0x18000b5fe  pop     rdi
0x18000b5ff  retn
```
