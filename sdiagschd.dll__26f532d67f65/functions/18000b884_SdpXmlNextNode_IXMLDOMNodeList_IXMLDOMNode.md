# SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)

- ea: `0x18000b884`
- end: `0x18000b99f`
- name: `?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z`
- size: `283`
- prototype: `__int64 __fastcall(struct IXMLDOMNodeList *, struct IXMLDOMNode **)`
- caller_count: `11`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180002de0`
- `0x180003100`
- `0x180003384`
- `0x180003554`
- `0x180003e10`
- `0x1800040b4`
- `0x180004c48`
- `0x180005404`
- `0x1800060bc`
- `0x1800062c4`
- `0x18000b498`

## callees

- `0x18000b13c`
- `0x18000b884`
- `0x18000d010`

## string_xrefs

- `0x18000b965`: `SdpXmlNextNode`

## pseudocode

```c
__int64 __fastcall SdpXmlNextNode(struct IXMLDOMNodeList *a1, struct IXMLDOMNode **a2)
{
  struct IXMLDOMNode *v4; // rcx
  int v5; // r9d
  int v6; // r8d
  unsigned int v7; // ebx
  int v8; // eax
  struct IXMLDOMNode *v9; // rcx
  struct IXMLDOMNodeVtbl *lpVtbl; // rax
  int v12; // [rsp+40h] [rbp+20h] BYREF
  struct IXMLDOMNode *v13; // [rsp+50h] [rbp+30h] BYREF

  v4 = 0;
  v13 = 0;
  v12 = 1;
  if ( a1 )
  {
    if ( a2 )
    {
      while ( 1 )
      {
        if ( v4 )
        {
          ((void (__fastcall *)(struct IXMLDOMNode *))v4->lpVtbl->Release)(v4);
          v13 = 0;
        }
        v8 = ((__int64 (__fastcall *)(struct IXMLDOMNodeList *, struct IXMLDOMNode **))a1->lpVtbl->nextNode)(a1, &v13);
        v7 = v8;
        if ( v8 < 0 )
          break;
        v9 = v13;
        if ( v8 == 1 || !v13 )
        {
          v7 = -2147467259;
          goto LABEL_19;
        }
        v8 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, int *))v13->lpVtbl->get_nodeType)(v13, &v12);
        v7 = v8;
        if ( v8 < 0 )
        {
          v6 = 1064;
          goto LABEL_16;
        }
        v4 = v13;
        if ( v12 == 1 )
        {
          lpVtbl = v13->lpVtbl;
          *a2 = v13;
          ((void (*)(void))lpVtbl->AddRef)();
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
  v9 = v13;
LABEL_19:
  if ( v9 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v9->lpVtbl->Release)(v9);
  return v7;
}

```

## disassembly

```asm
0x18000b884  mov     [rsp-18h+arg_8], rbx
0x18000b889  mov     [rsp-18h+arg_18], rsi
0x18000b88e  push    rbp
0x18000b88f  push    rdi
0x18000b890  push    r14
0x18000b892  mov     rbp, rsp
0x18000b895  sub     rsp, 20h
0x18000b899  mov     rdi, rcx
0x18000b89c  mov     rsi, rdx
0x18000b89f  xor     ecx, ecx
0x18000b8a1  mov     [rbp+arg_10], rcx
0x18000b8a5  lea     r14d, [rcx+1]
0x18000b8a9  mov     [rbp+arg_0], r14d
0x18000b8ad  test    rdi, rdi
0x18000b8b0  jnz     short loc_18000B8C6
0x18000b8b2  mov     r9d, 80070057h
0x18000b8b8  mov     r8d, 419h
0x18000b8be  mov     ebx, r9d
0x18000b8c1  jmp     loc_18000B965
0x18000b8c6  test    rsi, rsi
0x18000b8c9  jnz     short loc_18000B8DF
0x18000b8cb  mov     r9d, 80070057h
0x18000b8d1  mov     r8d, 41Ah
0x18000b8d7  mov     ebx, r9d
0x18000b8da  jmp     loc_18000B965
0x18000b8df  test    rcx, rcx
0x18000b8e2  jz      short loc_18000B8F5
0x18000b8e4  mov     rax, [rcx]
0x18000b8e7  mov     rax, [rax+10h]
0x18000b8eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8f0  and     [rbp+arg_10], 0
0x18000b8f5  mov     rax, [rdi]
0x18000b8f8  lea     rdx, [rbp+arg_10]
0x18000b8fc  mov     rcx, rdi
0x18000b8ff  mov     rax, [rax+48h]
0x18000b903  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b908  mov     ebx, eax
0x18000b90a  test    eax, eax
0x18000b90c  js      short loc_18000B95C
0x18000b90e  mov     rcx, [rbp+arg_10]
0x18000b912  cmp     eax, r14d
0x18000b915  jz      short loc_18000B955
0x18000b917  test    rcx, rcx
0x18000b91a  jz      short loc_18000B955
0x18000b91c  mov     rax, [rcx]
0x18000b91f  lea     rdx, [rbp+arg_0]
0x18000b923  mov     rax, [rax+50h]
0x18000b927  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b92c  mov     ebx, eax
0x18000b92e  test    eax, eax
0x18000b930  js      short loc_18000B94D
0x18000b932  mov     rcx, [rbp+arg_10]
0x18000b936  cmp     [rbp+arg_0], r14d
0x18000b93a  jnz     short loc_18000B8DF
0x18000b93c  mov     rax, [rcx]
0x18000b93f  mov     [rsi], rcx
0x18000b942  mov     rax, [rax+8]
0x18000b946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b94b  jmp     short loc_18000B974
0x18000b94d  mov     r8d, 428h
0x18000b953  jmp     short loc_18000B962
0x18000b955  mov     ebx, 80004005h
0x18000b95a  jmp     short loc_18000B978
0x18000b95c  mov     r8d, 420h; int
0x18000b962  mov     r9d, eax; int
0x18000b965  lea     rdx, aSdpxmlnextnode; "SdpXmlNextNode"
0x18000b96c  mov     ecx, r14d; Level
0x18000b96f  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000b974  mov     rcx, [rbp+arg_10]
0x18000b978  test    rcx, rcx
0x18000b97b  jz      short loc_18000B989
0x18000b97d  mov     rax, [rcx]
0x18000b980  mov     rax, [rax+10h]
0x18000b984  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b989  mov     rsi, [rsp+20h+arg_18]
0x18000b98e  mov     eax, ebx
0x18000b990  mov     rbx, [rsp+20h+arg_8]
0x18000b995  add     rsp, 20h
0x18000b999  pop     r14
0x18000b99b  pop     rdi
0x18000b99c  pop     rbp
0x18000b99d  retn
```
