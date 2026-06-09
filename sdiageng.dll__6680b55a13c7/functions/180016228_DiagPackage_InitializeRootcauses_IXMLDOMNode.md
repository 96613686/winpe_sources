# DiagPackage::InitializeRootcauses(IXMLDOMNode *)

- ea: `0x180016228`
- end: `0x180016459`
- name: `?InitializeRootcauses@DiagPackage@@AEAAJPEAUIXMLDOMNode@@@Z`
- size: `561`
- prototype: `__int64 __fastcall(DiagPackage *__hidden this, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180016630`

## callees

- `0x1800012b0`
- `0x180001be4`
- `0x180016148`
- `0x180016228`
- `0x180026fa0`
- `0x180028038`
- `0x1800286a4`
- `0x1800290bc`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall DiagPackage::InitializeRootcauses(DiagPackage *this, struct IXMLDOMNode *a2)
{
  struct IXMLDOMNode *v3; // rsi
  unsigned int v4; // ebx
  int ChildNodes; // eax
  struct IXMLDOMNodeList *v6; // r12
  int v7; // r9d
  int v8; // r8d
  unsigned __int64 v9; // r14
  __int64 v10; // rax
  bool v11; // cf
  size_t v12; // rax
  _QWORD *v13; // rax
  _QWORD *v14; // rdi
  __int64 v15; // r15
  int v16; // eax
  int v17; // eax
  int v18; // eax
  _QWORD *v20; // [rsp+78h] [rbp+48h] BYREF
  struct IXMLDOMNode *v21; // [rsp+80h] [rbp+50h] BYREF
  struct IXMLDOMNodeList *v22; // [rsp+88h] [rbp+58h] BYREF

  v22 = 0;
  v3 = 0;
  v21 = 0;
  LODWORD(v20) = 0;
  if ( !a2 )
  {
    v4 = -2147024809;
    SdpDebugTrace(1u, L"DiagPackage::InitializeRootcauses", 1480, -2147024809);
    return v4;
  }
  ChildNodes = SdpXmlGetChildNodes(0, a2, &v22, (unsigned int *)&v20);
  v4 = ChildNodes;
  v6 = v22;
  if ( ChildNodes >= 0 )
  {
    v9 = (unsigned int)v20;
    if ( (_DWORD)v20 )
    {
      v10 = 144LL * (unsigned int)v20;
      if ( !is_mul_ok((unsigned int)v20, 0x90u) )
        v10 = -1;
      v11 = __CFADD__(v10, 8);
      v12 = v10 + 8;
      if ( v11 )
        v12 = -1;
      v13 = operator new[](v12);
      v20 = v13;
      if ( v13 )
      {
        *v13 = v9;
        v14 = v13 + 1;
        `eh vector constructor iterator'(
          v13 + 1,
          0x90u,
          v9,
          (void (*)(void *))Rootcause::Rootcause,
          (void (*)(void *))Rootcause::~Rootcause);
      }
      else
      {
        v14 = 0;
      }
      *((_QWORD *)this + 3) = v14;
      if ( v14 )
      {
        v15 = 0;
        if ( (_DWORD)v9 )
        {
          while ( 1 )
          {
            if ( v3 )
            {
              ((void (__fastcall *)(struct IXMLDOMNode *))v3->lpVtbl->Release)(v3);
              v21 = 0;
            }
            v16 = SdpXmlNextNode(v6, &v21);
            v4 = v16;
            if ( v16 < 0 )
              break;
            v3 = v21;
            v17 = SdpXmlCheckNode(v21, L"Rootcause");
            v4 = v17;
            if ( v17 < 0 )
            {
              v7 = v17;
              goto LABEL_35;
            }
            if ( v17 == 1 || !v3 )
            {
              v4 = -2147467259;
              v7 = -2147467259;
LABEL_35:
              v8 = 1498;
              goto LABEL_5;
            }
            v18 = DiagPackage::InitializeRootcause(this, v3, (struct Rootcause *)(*((_QWORD *)this + 3) + 144 * v15));
            v4 = v18;
            if ( v18 < 0 )
            {
              v7 = v18;
              v8 = 1501;
              goto LABEL_5;
            }
            v15 = (unsigned int)(v15 + 1);
            if ( (unsigned int)v15 >= (unsigned int)v9 )
              goto LABEL_26;
          }
          SdpDebugTrace(1u, L"DiagPackage::InitializeRootcauses", 1497, v16);
          v3 = v21;
        }
        else
        {
LABEL_26:
          *((_DWORD *)this + 8) = v9;
        }
        goto LABEL_27;
      }
      v4 = -2147024882;
      v7 = -2147024882;
      v8 = 1491;
    }
    else
    {
      v7 = -2147024809;
      v4 = -2147024809;
      v8 = 1487;
    }
  }
  else
  {
    v7 = ChildNodes;
    v8 = 1483;
  }
LABEL_5:
  SdpDebugTrace(1u, L"DiagPackage::InitializeRootcauses", v8, v7);
LABEL_27:
  if ( v6 )
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v6->lpVtbl->Release)(v6);
  if ( v3 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v3->lpVtbl->Release)(v3);
  return v4;
}

```

## disassembly

```asm
0x180016228  mov     [rsp-38h+arg_0], rbx
0x18001622d  push    rbp
0x18001622e  push    rsi
0x18001622f  push    rdi
0x180016230  push    r12
0x180016232  push    r13
0x180016234  push    r14
0x180016236  push    r15
0x180016238  mov     rbp, rsp
0x18001623b  sub     rsp, 30h
0x18001623f  mov     r13, rcx
0x180016242  mov     [rbp+arg_18], 0
0x18001624a  xor     esi, esi
0x18001624c  mov     [rbp+arg_10], rsi
0x180016250  mov     dword ptr [rbp+arg_8], esi
0x180016253  test    rdx, rdx
0x180016256  jnz     short loc_18001627B
0x180016258  mov     r9d, 80070057h; int
0x18001625e  mov     ebx, r9d
0x180016261  mov     r8d, 5C8h; int
0x180016267  lea     rdx, aDiagpackageIni; "DiagPackage::InitializeRootcauses"
0x18001626e  lea     ecx, [rsi+1]; Level
0x180016271  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180016276  jmp     loc_1800163FD
0x18001627b  lea     r9, [rbp+arg_8]; unsigned int *
0x18001627f  lea     r8, [rbp+arg_18]; struct IXMLDOMNodeList **
0x180016283  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x180016285  call    ?SdpXmlGetChildNodes@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@PEAK@Z; SdpXmlGetChildNodes(IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *,ulong *)
0x18001628a  mov     ebx, eax
0x18001628c  mov     r12, [rbp+arg_18]
0x180016290  test    eax, eax
0x180016292  jns     short loc_1800162B3
0x180016294  mov     r9d, eax; int
0x180016297  mov     r8d, 5CBh; int
0x18001629d  mov     ecx, 1; Level
0x1800162a2  lea     rdx, aDiagpackageIni; "DiagPackage::InitializeRootcauses"
0x1800162a9  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800162ae  jmp     loc_1800163D4
0x1800162b3  mov     r14d, dword ptr [rbp+arg_8]
0x1800162b7  test    r14d, r14d
0x1800162ba  jnz     short loc_1800162CD
0x1800162bc  mov     r9d, 80070057h
0x1800162c2  mov     ebx, r9d
0x1800162c5  mov     r8d, 5CFh
0x1800162cb  jmp     short loc_18001629D
0x1800162cd  mov     eax, 90h
0x1800162d2  mul     r14
0x1800162d5  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800162dc  cmovb   rax, rcx
0x1800162e0  add     rax, 8
0x1800162e4  cmovb   rax, rcx
0x1800162e8  mov     rcx, rax; unsigned __int64
0x1800162eb  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800162f0  mov     [rbp+arg_8], rax
0x1800162f4  test    rax, rax
0x1800162f7  jz      short loc_180016325
0x1800162f9  mov     [rax], r14
0x1800162fc  lea     rdi, [rax+8]
0x180016300  lea     rax, ??1Rootcause@@QEAA@XZ; Rootcause::~Rootcause(void)
0x180016307  mov     [rsp+30h+var_10], rax; void (*)(void *)
0x18001630c  lea     r9, ??0Rootcause@@QEAA@XZ; void (*)(void *)
0x180016313  mov     r8, r14; unsigned __int64
0x180016316  mov     edx, 90h; unsigned __int64
0x18001631b  mov     rcx, rdi; void *
0x18001631e  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180016323  jmp     short loc_180016327
0x180016325  xor     edi, edi
0x180016327  mov     [r13+18h], rdi
0x18001632b  test    rdi, rdi
0x18001632e  jnz     short loc_180016343
0x180016330  mov     ebx, 8007000Eh
0x180016335  mov     r9d, ebx
0x180016338  mov     r8d, 5D3h
0x18001633e  jmp     loc_18001629D
0x180016343  xor     r15d, r15d
0x180016346  test    r14d, r14d
0x180016349  jz      loc_1800163D0
0x18001634f  lea     edi, [r15+1]
0x180016353  test    rsi, rsi
0x180016356  jz      short loc_18001636F
0x180016358  mov     rax, [rsi]
0x18001635b  mov     rcx, rsi
0x18001635e  mov     rax, [rax+10h]
0x180016362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016367  mov     [rbp+arg_10], 0
0x18001636f  lea     rdx, [rbp+arg_10]; struct IXMLDOMNode **
0x180016373  mov     rcx, r12; struct IXMLDOMNodeList *
0x180016376  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x18001637b  mov     ebx, eax
0x18001637d  test    eax, eax
0x18001637f  js      loc_180016439
0x180016385  lea     rdx, aRootcause; "Rootcause"
0x18001638c  mov     rsi, [rbp+arg_10]
0x180016390  mov     rcx, rsi; struct IXMLDOMNode *
0x180016393  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x180016398  mov     ebx, eax
0x18001639a  test    eax, eax
0x18001639c  js      loc_180016429
0x1800163a2  cmp     eax, edi
0x1800163a4  jz      short loc_18001641F
0x1800163a6  test    rsi, rsi
0x1800163a9  jz      short loc_18001641F
0x1800163ab  lea     r8, [r15+r15*8]
0x1800163af  shl     r8, 4
0x1800163b3  add     r8, [r13+18h]; struct Rootcause *
0x1800163b7  mov     rdx, rsi; struct IXMLDOMNode *
0x1800163ba  mov     rcx, r13; this
0x1800163bd  call    ?InitializeRootcause@DiagPackage@@AEAAJPEAUIXMLDOMNode@@PEAVRootcause@@@Z; DiagPackage::InitializeRootcause(IXMLDOMNode *,Rootcause *)
0x1800163c2  mov     ebx, eax
0x1800163c4  test    eax, eax
0x1800163c6  js      short loc_180016414
0x1800163c8  add     r15d, edi
0x1800163cb  cmp     r15d, r14d
0x1800163ce  jb      short loc_180016353
0x1800163d0  mov     [r13+20h], r14d
0x1800163d4  test    r12, r12
0x1800163d7  jz      short loc_1800163E9
0x1800163d9  mov     rax, [r12]
0x1800163dd  mov     rcx, r12
0x1800163e0  mov     rax, [rax+10h]
0x1800163e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800163e9  test    rsi, rsi
0x1800163ec  jz      short loc_1800163FD
0x1800163ee  mov     rax, [rsi]
0x1800163f1  mov     rcx, rsi
0x1800163f4  mov     rax, [rax+10h]
0x1800163f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800163fd  mov     eax, ebx
0x1800163ff  mov     rbx, [rsp+30h+arg_0]
0x180016404  add     rsp, 30h
0x180016408  pop     r15
0x18001640a  pop     r14
0x18001640c  pop     r13
0x18001640e  pop     r12
0x180016410  pop     rdi
0x180016411  pop     rsi
0x180016412  pop     rbp
0x180016413  retn
0x180016414  mov     r9d, eax
0x180016417  mov     r8d, 5DDh
0x18001641d  jmp     short loc_180016432
0x18001641f  mov     ebx, 80004005h
0x180016424  mov     r9d, ebx
0x180016427  jmp     short loc_18001642C
0x180016429  mov     r9d, eax
0x18001642c  mov     r8d, 5DAh
0x180016432  mov     ecx, edi
0x180016434  jmp     loc_1800162A2
0x180016439  mov     r9d, eax; int
0x18001643c  mov     r8d, 5D9h; int
0x180016442  lea     rdx, aDiagpackageIni; "DiagPackage::InitializeRootcauses"
0x180016449  mov     ecx, edi; Level
0x18001644b  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180016450  mov     rsi, [rbp+arg_10]
0x180016454  jmp     loc_1800163D4
```
