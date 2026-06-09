# Rootcause::InitializeResolvers(IXMLDOMNode *)

- ea: `0x18001a0bc`
- end: `0x18001a363`
- name: `?InitializeResolvers@Rootcause@@AEAAJPEAUIXMLDOMNode@@@Z`
- size: `679`
- prototype: `__int64 __fastcall(Rootcause *__hidden this, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18001a530`

## callees

- `0x1800012b0`
- `0x180001be4`
- `0x18001a0bc`
- `0x18001c6e8`
- `0x180026fa0`
- `0x180028038`
- `0x1800286a4`
- `0x1800290bc`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall Rootcause::InitializeResolvers(Rootcause *this, struct IXMLDOMNode *a2)
{
  struct IXMLDOMNode *v3; // rsi
  unsigned int v4; // ebx
  int ChildNodes; // eax
  struct IXMLDOMNodeList *v6; // r13
  int v7; // r9d
  int v8; // r8d
  __int64 v9; // r15
  __int64 v10; // rax
  bool v11; // cf
  size_t v12; // rax
  _QWORD *v13; // rax
  _QWORD *v14; // rdi
  __int64 v15; // r12
  int v16; // eax
  int v17; // eax
  Resolver *v18; // rcx
  int v19; // eax
  int v21; // r8d
  int v22; // r9d
  _QWORD *v23; // [rsp+78h] [rbp+48h] BYREF
  struct IXMLDOMNode *v24; // [rsp+80h] [rbp+50h] BYREF
  struct IXMLDOMNodeList *v25; // [rsp+88h] [rbp+58h] BYREF

  v25 = 0;
  v3 = 0;
  v24 = 0;
  LODWORD(v23) = 0;
  if ( !a2 )
  {
    v4 = -2147024809;
    SdpDebugTrace(1u, L"Rootcause::InitializeResolvers", 1123, -2147024809);
    return v4;
  }
  ChildNodes = SdpXmlGetChildNodes(0, a2, &v25, (unsigned int *)&v23);
  v4 = ChildNodes;
  v6 = v25;
  if ( ChildNodes >= 0 )
  {
    v9 = (unsigned int)v23;
    if ( !(_DWORD)v23 )
      goto LABEL_31;
    v10 = 80LL * (unsigned int)v23;
    if ( !is_mul_ok((unsigned int)v23, 0x50u) )
      v10 = -1;
    v11 = __CFADD__(v10, 8);
    v12 = v10 + 8;
    if ( v11 )
      v12 = -1;
    v13 = operator new[](v12);
    v23 = v13;
    if ( v13 )
    {
      *v13 = v9;
      v14 = v13 + 1;
      `eh vector constructor iterator'(
        v13 + 1,
        0x50u,
        (unsigned int)v9,
        (void (*)(void *))Resolver::Resolver,
        (void (*)(void *))Resolver::~Resolver);
    }
    else
    {
      v14 = 0;
    }
    *((_QWORD *)this + 2) = v14;
    if ( v14 )
    {
      if ( *(_QWORD *)this )
      {
        if ( *((_QWORD *)this + 5) )
        {
          v15 = 0;
          if ( !(_DWORD)v9 )
          {
LABEL_30:
            *((_DWORD *)this + 8) = v9;
            goto LABEL_31;
          }
          while ( 1 )
          {
            if ( v3 )
            {
              ((void (__fastcall *)(struct IXMLDOMNode *))v3->lpVtbl->Release)(v3);
              v24 = 0;
            }
            v16 = SdpXmlNextNode(v6, &v24);
            v4 = v16;
            if ( v16 < 0 )
            {
              SdpDebugTrace(1u, L"Rootcause::InitializeResolvers", 1145, v16);
              v3 = v24;
              goto LABEL_31;
            }
            v3 = v24;
            v17 = SdpXmlCheckNode(v24, L"Resolver");
            v4 = v17;
            if ( v17 < 0 )
              break;
            if ( v17 == 1 || !v3 )
            {
              v4 = -2147467259;
              v7 = -2147467259;
              goto LABEL_41;
            }
            if ( !*(_QWORD *)this )
            {
              v21 = 77;
              v22 = -2147024809;
              v4 = -2147024809;
              goto LABEL_38;
            }
            v18 = (Resolver *)(*((_QWORD *)this + 2) + 80 * v15);
            *(_QWORD *)v18 = *(_QWORD *)this;
            v19 = Resolver::ParseResolverXml(v18, v3);
            v4 = v19;
            if ( v19 < 0 )
            {
              v21 = 83;
              v22 = v19;
LABEL_38:
              SdpDebugTrace(1u, L"Resolver::Initialize", v21, v22);
              v7 = v4;
              v8 = 1149;
              goto LABEL_5;
            }
            v15 = (unsigned int)(v15 + 1);
            if ( (unsigned int)v15 >= (unsigned int)v9 )
              goto LABEL_30;
          }
          v7 = v17;
LABEL_41:
          v8 = 1146;
        }
        else
        {
          v7 = -2147467261;
          v4 = -2147467261;
          v8 = 1139;
        }
      }
      else
      {
        v7 = -2147467261;
        v4 = -2147467261;
        v8 = 1138;
      }
    }
    else
    {
      v4 = -2147024882;
      v7 = -2147024882;
      v8 = 1136;
    }
  }
  else
  {
    v7 = ChildNodes;
    v8 = 1126;
  }
LABEL_5:
  SdpDebugTrace(1u, L"Rootcause::InitializeResolvers", v8, v7);
LABEL_31:
  if ( v6 )
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v6->lpVtbl->Release)(v6);
  if ( v3 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v3->lpVtbl->Release)(v3);
  return v4;
}

```

## disassembly

```asm
0x18001a0bc  mov     [rsp-38h+arg_0], rbx
0x18001a0c1  push    rbp
0x18001a0c2  push    rsi
0x18001a0c3  push    rdi
0x18001a0c4  push    r12
0x18001a0c6  push    r13
0x18001a0c8  push    r14
0x18001a0ca  push    r15
0x18001a0cc  mov     rbp, rsp
0x18001a0cf  sub     rsp, 30h
0x18001a0d3  mov     r14, rcx
0x18001a0d6  mov     [rbp+arg_18], 0
0x18001a0de  xor     esi, esi
0x18001a0e0  mov     [rbp+arg_10], rsi
0x18001a0e4  mov     dword ptr [rbp+arg_8], esi
0x18001a0e7  test    rdx, rdx
0x18001a0ea  jnz     short loc_18001A10F
0x18001a0ec  mov     r9d, 80070057h; int
0x18001a0f2  mov     ebx, r9d
0x18001a0f5  mov     r8d, 463h; int
0x18001a0fb  lea     rdx, aRootcauseIniti; "Rootcause::InitializeResolvers"
0x18001a102  lea     ecx, [rsi+1]; Level
0x18001a105  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001a10a  jmp     loc_18001A2D7
0x18001a10f  lea     r9, [rbp+arg_8]; unsigned int *
0x18001a113  lea     r8, [rbp+arg_18]; struct IXMLDOMNodeList **
0x18001a117  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x18001a119  call    ?SdpXmlGetChildNodes@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@PEAK@Z; SdpXmlGetChildNodes(IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *,ulong *)
0x18001a11e  mov     ebx, eax
0x18001a120  mov     r13, [rbp+arg_18]
0x18001a124  test    eax, eax
0x18001a126  jns     short loc_18001A147
0x18001a128  mov     r9d, eax; int
0x18001a12b  mov     r8d, 466h; int
0x18001a131  mov     ecx, 1; Level
0x18001a136  lea     rdx, aRootcauseIniti; "Rootcause::InitializeResolvers"
0x18001a13d  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001a142  jmp     loc_18001A2AE
0x18001a147  mov     r15d, dword ptr [rbp+arg_8]
0x18001a14b  test    r15d, r15d
0x18001a14e  jz      loc_18001A2AE
0x18001a154  mov     eax, 50h ; 'P'
0x18001a159  mul     r15
0x18001a15c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001a163  cmovb   rax, rcx
0x18001a167  add     rax, 8
0x18001a16b  cmovb   rax, rcx
0x18001a16f  mov     rcx, rax; unsigned __int64
0x18001a172  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001a177  mov     [rbp+arg_8], rax
0x18001a17b  test    rax, rax
0x18001a17e  jz      short loc_18001A1AC
0x18001a180  mov     [rax], r15
0x18001a183  lea     rdi, [rax+8]
0x18001a187  lea     rax, ??1Resolver@@QEAA@XZ; Resolver::~Resolver(void)
0x18001a18e  mov     [rsp+30h+var_10], rax; void (*)(void *)
0x18001a193  lea     r9, ??0Resolver@@QEAA@XZ; void (*)(void *)
0x18001a19a  mov     r8d, r15d; unsigned __int64
0x18001a19d  mov     edx, 50h ; 'P'; unsigned __int64
0x18001a1a2  mov     rcx, rdi; void *
0x18001a1a5  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18001a1aa  jmp     short loc_18001A1AE
0x18001a1ac  xor     edi, edi
0x18001a1ae  mov     [r14+10h], rdi
0x18001a1b2  test    rdi, rdi
0x18001a1b5  jnz     short loc_18001A1CA
0x18001a1b7  mov     ebx, 8007000Eh
0x18001a1bc  mov     r9d, ebx
0x18001a1bf  mov     r8d, 470h
0x18001a1c5  jmp     loc_18001A131
0x18001a1ca  cmp     qword ptr [r14], 0
0x18001a1ce  jnz     short loc_18001A1E4
0x18001a1d0  mov     r9d, 80004003h
0x18001a1d6  mov     ebx, r9d
0x18001a1d9  mov     r8d, 472h
0x18001a1df  jmp     loc_18001A131
0x18001a1e4  cmp     qword ptr [r14+28h], 0
0x18001a1e9  jnz     short loc_18001A1FF
0x18001a1eb  mov     r9d, 80004003h
0x18001a1f1  mov     ebx, r9d
0x18001a1f4  mov     r8d, 473h
0x18001a1fa  jmp     loc_18001A131
0x18001a1ff  xor     r12d, r12d
0x18001a202  test    r15d, r15d
0x18001a205  jz      loc_18001A2AA
0x18001a20b  lea     edi, [r12+1]
0x18001a210  test    rsi, rsi
0x18001a213  jz      short loc_18001A22C
0x18001a215  mov     rax, [rsi]
0x18001a218  mov     rcx, rsi
0x18001a21b  mov     rax, [rax+10h]
0x18001a21f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a224  mov     [rbp+arg_10], 0
0x18001a22c  lea     rdx, [rbp+arg_10]; struct IXMLDOMNode **
0x18001a230  mov     rcx, r13; struct IXMLDOMNodeList *
0x18001a233  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x18001a238  mov     ebx, eax
0x18001a23a  test    eax, eax
0x18001a23c  js      loc_18001A343
0x18001a242  lea     rdx, aResolver; "Resolver"
0x18001a249  mov     rsi, [rbp+arg_10]
0x18001a24d  mov     rcx, rsi; struct IXMLDOMNode *
0x18001a250  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x18001a255  mov     ebx, eax
0x18001a257  test    eax, eax
0x18001a259  js      loc_18001A333
0x18001a25f  cmp     eax, edi
0x18001a261  jz      loc_18001A329
0x18001a267  test    rsi, rsi
0x18001a26a  jz      loc_18001A329
0x18001a270  mov     rdx, [r14]
0x18001a273  test    rdx, rdx
0x18001a276  jz      loc_18001A301
0x18001a27c  test    rsi, rsi
0x18001a27f  jz      short loc_18001A2F9
0x18001a281  lea     rcx, [r12+r12*4]
0x18001a285  shl     rcx, 4
0x18001a289  add     rcx, [r14+10h]; this
0x18001a28d  mov     [rcx], rdx
0x18001a290  mov     rdx, rsi; struct IXMLDOMNode *
0x18001a293  call    ?ParseResolverXml@Resolver@@AEAAJPEAUIXMLDOMNode@@@Z; Resolver::ParseResolverXml(IXMLDOMNode *)
0x18001a298  mov     ebx, eax
0x18001a29a  test    eax, eax
0x18001a29c  js      short loc_18001A2EE
0x18001a29e  add     r12d, edi
0x18001a2a1  cmp     r12d, r15d
0x18001a2a4  jb      loc_18001A210
0x18001a2aa  mov     [r14+20h], r15d
0x18001a2ae  test    r13, r13
0x18001a2b1  jz      short loc_18001A2C3
0x18001a2b3  mov     rax, [r13+0]
0x18001a2b7  mov     rcx, r13
0x18001a2ba  mov     rax, [rax+10h]
0x18001a2be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a2c3  test    rsi, rsi
0x18001a2c6  jz      short loc_18001A2D7
0x18001a2c8  mov     rax, [rsi]
0x18001a2cb  mov     rcx, rsi
0x18001a2ce  mov     rax, [rax+10h]
0x18001a2d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a2d7  mov     eax, ebx
0x18001a2d9  mov     rbx, [rsp+30h+arg_0]
0x18001a2de  add     rsp, 30h
0x18001a2e2  pop     r15
0x18001a2e4  pop     r14
0x18001a2e6  pop     r13
0x18001a2e8  pop     r12
0x18001a2ea  pop     rdi
0x18001a2eb  pop     rsi
0x18001a2ec  pop     rbp
0x18001a2ed  retn
0x18001a2ee  mov     r8d, 53h ; 'S'
0x18001a2f4  mov     r9d, eax
0x18001a2f7  jmp     short loc_18001A310
0x18001a2f9  mov     r8d, 4Eh ; 'N'
0x18001a2ff  jmp     short loc_18001A307
0x18001a301  mov     r8d, 4Dh ; 'M'; int
0x18001a307  mov     r9d, 80070057h; int
0x18001a30d  mov     ebx, r9d
0x18001a310  mov     ecx, edi; Level
0x18001a312  lea     rdx, aResolverInitia_0; "Resolver::Initialize"
0x18001a319  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001a31e  mov     r9d, ebx
0x18001a321  mov     r8d, 47Dh
0x18001a327  jmp     short loc_18001A33C
0x18001a329  mov     ebx, 80004005h
0x18001a32e  mov     r9d, ebx
0x18001a331  jmp     short loc_18001A336
0x18001a333  mov     r9d, eax
0x18001a336  mov     r8d, 47Ah
0x18001a33c  mov     ecx, edi
0x18001a33e  jmp     loc_18001A136
0x18001a343  mov     r9d, eax; int
0x18001a346  mov     r8d, 479h; int
0x18001a34c  lea     rdx, aRootcauseIniti; "Rootcause::InitializeResolvers"
0x18001a353  mov     ecx, edi; Level
0x18001a355  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001a35a  mov     rsi, [rbp+arg_10]
0x18001a35e  jmp     loc_18001A2AE
```
