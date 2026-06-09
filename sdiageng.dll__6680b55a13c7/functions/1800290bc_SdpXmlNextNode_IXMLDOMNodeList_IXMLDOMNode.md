# SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)

- ea: `0x1800290bc`
- end: `0x1800291d9`
- name: `?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z`
- size: `285`
- prototype: `__int64 __fastcall(struct IXMLDOMNodeList *, struct IXMLDOMNode **)`
- caller_count: `26`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180002d20`
- `0x1800038c4`
- `0x180003b2c`
- `0x180003e50`
- `0x1800040e8`
- `0x180015c14`
- `0x180016228`
- `0x180016630`
- `0x18001a0bc`
- `0x18001a530`
- `0x18001bf34`
- `0x18001c6e8`
- `0x18001d20c`
- `0x18001dc28`
- `0x18001f010`
- `0x18001fc10`
- `0x180020648`
- `0x1800208f4`
- `0x180020c7c`
- `0x180022ce0`
- `0x180023020`
- `0x180023680`
- `0x180025ff0`
- `0x180026790`
- `0x1800286a4`
- `0x180028f24`

## callees

- `0x180026fa0`
- `0x1800290bc`
- `0x18002a010`

## string_xrefs

- `0x1800291a0`: `SdpXmlNextNode`

## pseudocode

```c
__int64 __fastcall SdpXmlNextNode(struct IXMLDOMNodeList *a1, struct IXMLDOMNode **a2)
{
  struct IXMLDOMNode *v4; // rcx
  int v5; // r9d
  unsigned int v6; // r8d
  unsigned int v7; // ebx
  int v8; // eax
  struct IXMLDOMNode *v9; // rcx
  int v11; // [rsp+40h] [rbp+20h] BYREF
  struct IXMLDOMNode *v12; // [rsp+50h] [rbp+30h] BYREF

  v4 = 0;
  v12 = 0;
  v11 = 1;
  if ( a1 )
  {
    if ( a2 )
    {
      while ( 1 )
      {
        if ( v4 )
        {
          ((void (__fastcall *)(struct IXMLDOMNode *))v4->lpVtbl->Release)(v4);
          v12 = 0;
        }
        v8 = ((__int64 (__fastcall *)(struct IXMLDOMNodeList *, struct IXMLDOMNode **))a1->lpVtbl->nextNode)(a1, &v12);
        v7 = v8;
        if ( v8 < 0 )
          break;
        v9 = v12;
        if ( v8 == 1 || !v12 )
        {
          v7 = -2147467259;
          goto LABEL_19;
        }
        v8 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, int *))v12->lpVtbl->get_nodeType)(v12, &v11);
        v7 = v8;
        if ( v8 < 0 )
        {
          v6 = 1064;
          goto LABEL_16;
        }
        v4 = v12;
        if ( v11 == 1 )
        {
          *a2 = v12;
          ((void (__fastcall *)(struct IXMLDOMNode *))v4->lpVtbl->AddRef)(v4);
          goto LABEL_18;
        }
      }
      v6 = 1056;
LABEL_16:
      v5 = v8;
    }
    else
    {
      v5 = -2147024809;
      v6 = 1050;
      v7 = -2147024809;
    }
  }
  else
  {
    v5 = -2147024809;
    v6 = 1049;
    v7 = -2147024809;
  }
  SdpDebugTrace(1u, L"SdpXmlNextNode", v6, v5);
LABEL_18:
  v9 = v12;
LABEL_19:
  if ( v9 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v9->lpVtbl->Release)(v9);
  return v7;
}

```

## disassembly

```asm
0x1800290bc  mov     [rsp-18h+arg_8], rbx
0x1800290c1  mov     [rsp-18h+arg_18], rsi
0x1800290c6  push    rbp
0x1800290c7  push    rdi
0x1800290c8  push    r14
0x1800290ca  mov     rbp, rsp
0x1800290cd  sub     rsp, 20h
0x1800290d1  mov     rdi, rcx
0x1800290d4  mov     rsi, rdx
0x1800290d7  xor     ecx, ecx
0x1800290d9  mov     [rbp+arg_10], rcx
0x1800290dd  lea     r14d, [rcx+1]
0x1800290e1  mov     [rbp+arg_0], r14d
0x1800290e5  test    rdi, rdi
0x1800290e8  jnz     short loc_1800290FE
0x1800290ea  mov     r9d, 80070057h
0x1800290f0  mov     r8d, 419h
0x1800290f6  mov     ebx, r9d
0x1800290f9  jmp     loc_1800291A0
0x1800290fe  test    rsi, rsi
0x180029101  jnz     short loc_180029117
0x180029103  mov     r9d, 80070057h
0x180029109  mov     r8d, 41Ah
0x18002910f  mov     ebx, r9d
0x180029112  jmp     loc_1800291A0
0x180029117  test    rcx, rcx
0x18002911a  jz      short loc_180029130
0x18002911c  mov     rax, [rcx]
0x18002911f  mov     rax, [rax+10h]
0x180029123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029128  mov     [rbp+arg_10], 0
0x180029130  mov     rax, [rdi]
0x180029133  lea     rdx, [rbp+arg_10]
0x180029137  mov     rcx, rdi
0x18002913a  mov     rax, [rax+48h]
0x18002913e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029143  mov     ebx, eax
0x180029145  test    eax, eax
0x180029147  js      short loc_180029197
0x180029149  mov     rcx, [rbp+arg_10]
0x18002914d  cmp     eax, r14d
0x180029150  jz      short loc_180029190
0x180029152  test    rcx, rcx
0x180029155  jz      short loc_180029190
0x180029157  mov     rax, [rcx]
0x18002915a  lea     rdx, [rbp+arg_0]
0x18002915e  mov     rax, [rax+50h]
0x180029162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029167  mov     ebx, eax
0x180029169  test    eax, eax
0x18002916b  js      short loc_180029188
0x18002916d  mov     rcx, [rbp+arg_10]
0x180029171  cmp     [rbp+arg_0], r14d
0x180029175  jnz     short loc_180029117
0x180029177  mov     [rsi], rcx
0x18002917a  mov     rax, [rcx]
0x18002917d  mov     rax, [rax+8]
0x180029181  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029186  jmp     short loc_1800291AF
0x180029188  mov     r8d, 428h
0x18002918e  jmp     short loc_18002919D
0x180029190  mov     ebx, 80004005h
0x180029195  jmp     short loc_1800291B3
0x180029197  mov     r8d, 420h; int
0x18002919d  mov     r9d, eax; int
0x1800291a0  lea     rdx, aSdpxmlnextnode; "SdpXmlNextNode"
0x1800291a7  mov     ecx, r14d; Level
0x1800291aa  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800291af  mov     rcx, [rbp+arg_10]
0x1800291b3  test    rcx, rcx
0x1800291b6  jz      short loc_1800291C4
0x1800291b8  mov     rax, [rcx]
0x1800291bb  mov     rax, [rax+10h]
0x1800291bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800291c4  mov     rsi, [rsp+20h+arg_18]
0x1800291c9  mov     eax, ebx
0x1800291cb  mov     rbx, [rsp+20h+arg_8]
0x1800291d0  add     rsp, 20h
0x1800291d4  pop     r14
0x1800291d6  pop     rdi
0x1800291d7  pop     rbp
0x1800291d8  retn
```
