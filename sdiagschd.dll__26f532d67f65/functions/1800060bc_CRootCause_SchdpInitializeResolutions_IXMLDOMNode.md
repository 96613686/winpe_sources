# CRootCause::SchdpInitializeResolutions(IXMLDOMNode *)

- ea: `0x1800060bc`
- end: `0x1800062bb`
- name: `?SchdpInitializeResolutions@CRootCause@@AEAAJPEAUIXMLDOMNode@@@Z`
- size: `511`
- prototype: `int(CRootCause *__hidden this, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180005b70`

## callees

- `0x1800011ac`
- `0x1800060bc`
- `0x180006b64`
- `0x180006ba8`
- `0x18000b13c`
- `0x18000b234`
- `0x18000b750`
- `0x18000b884`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall CRootCause::SchdpInitializeResolutions(CRootCause *this, struct IXMLDOMDocument2 *a2)
{
  struct IXMLDOMNode *v3; // rdi
  int Nodes; // eax
  struct IXMLDOMNodeList *v5; // r14
  unsigned int v6; // ebx
  int v7; // r8d
  int v8; // r9d
  int *v9; // r12
  unsigned __int64 v10; // rbp
  __int64 v11; // rax
  bool v12; // cf
  unsigned __int64 v13; // rax
  unsigned __int64 *v14; // rax
  _QWORD *v15; // rsi
  CResolution *v16; // r15
  int v17; // esi
  int v18; // eax
  int v19; // eax
  struct IXMLDOMNode *v21; // [rsp+70h] [rbp+18h] BYREF
  struct IXMLDOMNodeList *v22; // [rsp+78h] [rbp+20h] BYREF

  v22 = 0;
  v3 = 0;
  v21 = 0;
  Nodes = SdpXmlGetNodes(L"./Resolutions/Resolution", 0, a2, &v22);
  v5 = v22;
  v6 = Nodes;
  if ( Nodes < 0 )
  {
    v7 = 245;
LABEL_3:
    v8 = Nodes;
LABEL_4:
    SdpDebugTrace(1u, L"CRootCause::SchdpInitializeResolutions", v7, v8);
    goto LABEL_34;
  }
  v9 = (int *)((char *)this + 48);
  Nodes = ((__int64 (__fastcall *)(struct IXMLDOMNodeList *, char *))v22->lpVtbl->get_length)(v22, (char *)this + 48);
  v6 = Nodes;
  if ( Nodes < 0 )
  {
    v7 = 248;
    goto LABEL_3;
  }
  if ( *v9 )
  {
    v10 = *v9;
    v11 = 16 * v10;
    if ( !is_mul_ok(v10, 0x10u) )
      v11 = -1;
    v12 = __CFADD__(v11, 8);
    v13 = v11 + 8;
    if ( v12 )
      v13 = -1;
    v14 = (unsigned __int64 *)operator new[](v13);
    if ( v14 )
    {
      v15 = v14 + 1;
      *v14 = v10;
      v16 = (CResolution *)(v14 + 1);
      do
      {
        CResolution::CResolution(v16);
        v16 = (CResolution *)((char *)v16 + 16);
        --v10;
      }
      while ( v10 );
    }
    else
    {
      v15 = 0;
    }
    *((_QWORD *)this + 5) = v15;
    if ( !v15 )
    {
      v6 = -2147024882;
      v7 = 255;
      v8 = -2147024882;
      goto LABEL_4;
    }
    v17 = 0;
    if ( *v9 > 0 )
    {
      while ( 1 )
      {
        if ( v3 )
        {
          ((void (__fastcall *)(struct IXMLDOMNode *))v3->lpVtbl->Release)(v3);
          v21 = 0;
        }
        v18 = SdpXmlNextNode(v5, &v21);
        v6 = v18;
        if ( v18 < 0 )
          break;
        v3 = v21;
        v19 = SdpXmlCheckNode(v21, L"Resolution");
        v6 = v19;
        if ( v19 < 0 )
        {
          v8 = v19;
          goto LABEL_32;
        }
        if ( v19 == 1 || !v3 )
        {
          v6 = -2147467259;
          v8 = -2147467259;
LABEL_32:
          v7 = 262;
          goto LABEL_4;
        }
        Nodes = CResolution::Initialize(
                  (CResolution *)(*((_QWORD *)this + 5) + 16LL * v17),
                  *(unsigned __int16 **)this,
                  v3);
        v6 = Nodes;
        if ( Nodes < 0 )
        {
          v7 = 265;
          goto LABEL_3;
        }
        if ( ++v17 >= *v9 )
          goto LABEL_34;
      }
      SdpDebugTrace(1u, L"CRootCause::SchdpInitializeResolutions", 261, v18);
      v3 = v21;
    }
  }
LABEL_34:
  if ( v5 )
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v5->lpVtbl->Release)(v5);
  if ( v3 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v3->lpVtbl->Release)(v3);
  return v6;
}

```

## disassembly

```asm
0x1800060bc  mov     rax, rsp
0x1800060bf  mov     [rax+8], rbx
0x1800060c3  push    rbp
0x1800060c4  push    rsi
0x1800060c5  push    rdi
0x1800060c6  push    r12
0x1800060c8  push    r13
0x1800060ca  push    r14
0x1800060cc  push    r15
0x1800060ce  sub     rsp, 20h
0x1800060d2  and     qword ptr [rax+20h], 0
0x1800060d7  lea     r9, [rax+20h]; struct IXMLDOMNodeList **
0x1800060db  mov     r13, rcx
0x1800060de  mov     r8, rdx; struct IXMLDOMNode *
0x1800060e1  xor     edi, edi
0x1800060e3  lea     rcx, aResolutionsRes; "./Resolutions/Resolution"
0x1800060ea  xor     edx, edx; struct IXMLDOMDocument2 *
0x1800060ec  mov     [rax+18h], rdi
0x1800060f0  call    ?SdpXmlGetNodes@@YAJPEBGPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@@Z; SdpXmlGetNodes(ushort const *,IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *)
0x1800060f5  mov     r14, [rsp+58h+arg_18]
0x1800060fa  mov     ebx, eax
0x1800060fc  test    eax, eax
0x1800060fe  jns     short loc_18000611F
0x180006100  mov     r8d, 0F5h; int
0x180006106  mov     r9d, eax; int
0x180006109  lea     rdx, aCrootcauseSchd_4; "CRootCause::SchdpInitializeResolutions"
0x180006110  mov     ecx, 1; Level
0x180006115  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000611a  jmp     loc_18000627B
0x18000611f  mov     rax, [r14]
0x180006122  lea     r12, [r13+30h]
0x180006126  mov     rdx, r12
0x180006129  mov     rcx, r14
0x18000612c  mov     rax, [rax+40h]
0x180006130  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006135  mov     ebx, eax
0x180006137  test    eax, eax
0x180006139  jns     short loc_180006143
0x18000613b  mov     r8d, 0F8h
0x180006141  jmp     short loc_180006106
0x180006143  cmp     [r12], edi
0x180006147  jz      loc_18000627B
0x18000614d  movsxd  rbp, dword ptr [r12]
0x180006151  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180006158  mov     eax, 10h
0x18000615d  mul     rbp
0x180006160  cmovo   rax, rcx
0x180006164  add     rax, 8
0x180006168  cmovb   rax, rcx
0x18000616c  mov     rcx, rax; unsigned __int64
0x18000616f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180006174  test    rax, rax
0x180006177  jz      short loc_180006197
0x180006179  lea     rsi, [rax+8]
0x18000617d  mov     [rax], rbp
0x180006180  mov     r15, rsi
0x180006183  mov     rcx, r15; this
0x180006186  call    ??0CResolution@@QEAA@XZ; CResolution::CResolution(void)
0x18000618b  add     r15, 10h
0x18000618f  sub     rbp, 1
0x180006193  jnz     short loc_180006183
0x180006195  jmp     short loc_180006199
0x180006197  xor     esi, esi
0x180006199  mov     [r13+28h], rsi
0x18000619d  test    rsi, rsi
0x1800061a0  jnz     short loc_1800061B5
0x1800061a2  mov     ebx, 8007000Eh
0x1800061a7  mov     r8d, 0FFh
0x1800061ad  mov     r9d, ebx
0x1800061b0  jmp     loc_180006109
0x1800061b5  xor     esi, esi
0x1800061b7  cmp     [r12], esi
0x1800061bb  jle     loc_18000627B
0x1800061c1  test    rdi, rdi
0x1800061c4  jz      short loc_1800061DB
0x1800061c6  mov     rax, [rdi]
0x1800061c9  mov     rcx, rdi
0x1800061cc  mov     rax, [rax+10h]
0x1800061d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061d5  and     [rsp+58h+arg_10], 0
0x1800061db  lea     rdx, [rsp+58h+arg_10]; struct IXMLDOMNode **
0x1800061e0  mov     rcx, r14; struct IXMLDOMNodeList *
0x1800061e3  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x1800061e8  mov     ebx, eax
0x1800061ea  test    eax, eax
0x1800061ec  js      short loc_18000625C
0x1800061ee  mov     rdi, [rsp+58h+arg_10]
0x1800061f3  lea     rdx, aResolution; "Resolution"
0x1800061fa  mov     rcx, rdi; struct IXMLDOMNode *
0x1800061fd  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x180006202  mov     ebx, eax
0x180006204  test    eax, eax
0x180006206  js      short loc_18000624E
0x180006208  cmp     eax, 1
0x18000620b  jz      short loc_180006244
0x18000620d  test    rdi, rdi
0x180006210  jz      short loc_180006244
0x180006212  mov     rdx, [r13+0]; unsigned __int16 *
0x180006216  mov     r8, rdi; struct IXMLDOMNode *
0x180006219  movsxd  rcx, esi
0x18000621c  shl     rcx, 4
0x180006220  add     rcx, [r13+28h]; this
0x180006224  call    ?Initialize@CResolution@@QEAAJPEAGPEAUIXMLDOMNode@@@Z; CResolution::Initialize(ushort *,IXMLDOMNode *)
0x180006229  mov     ebx, eax
0x18000622b  test    eax, eax
0x18000622d  js      short loc_180006239
0x18000622f  inc     esi
0x180006231  cmp     esi, [r12]
0x180006235  jl      short loc_1800061C1
0x180006237  jmp     short loc_18000627B
0x180006239  mov     r8d, 109h
0x18000623f  jmp     loc_180006106
0x180006244  mov     ebx, 80004005h
0x180006249  mov     r9d, ebx
0x18000624c  jmp     short loc_180006251
0x18000624e  mov     r9d, eax
0x180006251  mov     r8d, 106h
0x180006257  jmp     loc_180006109
0x18000625c  mov     r9d, eax; int
0x18000625f  lea     rdx, aCrootcauseSchd_4; "CRootCause::SchdpInitializeResolutions"
0x180006266  mov     r8d, 105h; int
0x18000626c  mov     ecx, 1; Level
0x180006271  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180006276  mov     rdi, [rsp+58h+arg_10]
0x18000627b  test    r14, r14
0x18000627e  jz      short loc_18000628F
0x180006280  mov     rax, [r14]
0x180006283  mov     rcx, r14
0x180006286  mov     rax, [rax+10h]
0x18000628a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000628f  test    rdi, rdi
0x180006292  jz      short loc_1800062A3
0x180006294  mov     rax, [rdi]
0x180006297  mov     rcx, rdi
0x18000629a  mov     rax, [rax+10h]
0x18000629e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062a3  mov     eax, ebx
0x1800062a5  mov     rbx, [rsp+58h+arg_0]
0x1800062aa  add     rsp, 20h
0x1800062ae  pop     r15
0x1800062b0  pop     r14
0x1800062b2  pop     r13
0x1800062b4  pop     r12
0x1800062b6  pop     rdi
0x1800062b7  pop     rsi
0x1800062b8  pop     rbp
0x1800062b9  retn
```
