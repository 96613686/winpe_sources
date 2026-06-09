# Rootcause::BuildResultResolutionsXml(Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *,IXMLDOMDocument2 * *)

- ea: `0x1800192ac`
- end: `0x180019553`
- name: `?BuildResultResolutionsXml@Rootcause@@AEAAJPEAU_SDIAG_ROOTCAUSE_INSTANCE@1@PEAPEAUIXMLDOMDocument2@@@Z`
- size: `679`
- prototype: `__int64 __fastcall(Rootcause *this, struct tagSAFEARRAY **, struct IXMLDOMDocument2 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x18001955c`

## callees

- `0x1800012a4`
- `0x180002280`
- `0x1800192ac`
- `0x18001c224`
- `0x18001cb90`
- `0x180026fa0`
- `0x180027ea4`
- `0x1800280f8`
- `0x18002a010`

## string_xrefs

- `0x1800192ed`: `Rootcause::BuildResultResolutionsXml`
- `0x180019352`: `Rootcause::BuildResultResolutionsXml`
- `0x1800193a5`: `Rootcause::BuildResultResolutionsXml`
- `0x180019385`: `<?xml version="1.0" encoding="utf-8"?><Resolutions/>`

## pseudocode

```c
__int64 __fastcall Rootcause::BuildResultResolutionsXml(
        Rootcause *this,
        struct tagSAFEARRAY **a2,
        struct IXMLDOMDocument2 **a3)
{
  unsigned __int16 *v3; // rbp
  int v6; // ebx
  int v7; // r8d
  int v8; // r9d
  const unsigned __int16 *v9; // rcx
  const unsigned __int16 *v10; // rdx
  int v11; // eax
  struct IXMLDOMDocument2 *v12; // rdi
  int v13; // eax
  struct IXMLDOMDocument2 *v14; // rsi
  int v15; // r8d
  int v16; // r9d
  __int64 v17; // r13
  char *v18; // rbx
  _QWORD *v19; // r12
  int v20; // eax
  struct IXMLDOMDocument2 *v22; // [rsp+20h] [rbp-48h] BYREF
  void *Block; // [rsp+88h] [rbp+20h] BYREF

  v3 = 0;
  v22 = 0;
  Block = 0;
  if ( !a3 )
  {
    v6 = -2147024809;
    v7 = 1435;
    v8 = -2147024809;
LABEL_3:
    SdpDebugTrace(1u, L"Rootcause::BuildResultResolutionsXml", v7, v8);
    return (unsigned int)v6;
  }
  v9 = (const unsigned __int16 *)*((_QWORD *)this + 5);
  if ( !v9 )
  {
    v8 = -2147467261;
    v7 = 1437;
    v6 = -2147467261;
    goto LABEL_3;
  }
  if ( !a2 )
  {
LABEL_12:
    v12 = 0;
    v13 = SdpXmlCreate((OLECHAR *)L"<?xml version=\"1.0\" encoding=\"utf-8\"?><Resolutions/>", &v22);
    v14 = v22;
    v6 = v13;
    if ( v13 >= 0 )
    {
      v17 = 0;
      if ( !*((_DWORD *)this + 8) )
      {
LABEL_34:
        *a3 = v14;
        ((void (__fastcall *)(struct IXMLDOMDocument2 *))v14->lpVtbl->AddRef)(v14);
        goto LABEL_35;
      }
      v18 = (char *)this + 16;
      v19 = (_QWORD *)((char *)this + 16);
      while ( 1 )
      {
        if ( v12 )
        {
          ((void (__fastcall *)(struct IXMLDOMDocument2 *))v12->lpVtbl->Release)(v12);
          v12 = 0;
          v19 = v18;
        }
        if ( a2 )
        {
          v13 = Resolver::RecordParameters((Resolver *)(*v19 + 80 * v17), a2[4], a2[5]);
          v6 = v13;
          if ( v13 < 0 )
          {
            v15 = 1459;
            goto LABEL_14;
          }
        }
        Block = 0;
        v20 = Resolver::BuildResultXml((Resolver *)(*v19 + 80 * v17), a2 == 0, v3, (struct IXMLDOMDocument2 **)&Block);
        v6 = v20;
        if ( v20 >= 0 )
        {
          v12 = (struct IXMLDOMDocument2 *)Block;
          (*(void (__fastcall **)(void *))(*(_QWORD *)Block + 8LL))(Block);
        }
        else
        {
          SdpDebugTrace(1u, L"Resolver::Describe", 175, v20);
        }
        if ( Block )
          (*(void (__fastcall **)(void *))(*(_QWORD *)Block + 16LL))(Block);
        if ( v6 < 0 )
          break;
        v13 = SdpXmlAppend(v14, 0, v12);
        v6 = v13;
        if ( v13 < 0 )
        {
          v15 = 1466;
          goto LABEL_14;
        }
        v17 = (unsigned int)(v17 + 1);
        if ( (unsigned int)v17 >= *((_DWORD *)this + 8) )
          goto LABEL_34;
        v18 = (char *)this + 16;
      }
      v16 = v6;
      v15 = 1463;
    }
    else
    {
      v15 = 1447;
LABEL_14:
      v16 = v13;
    }
    SdpDebugTrace(1u, L"Rootcause::BuildResultResolutionsXml", v15, v16);
LABEL_35:
    if ( v14 )
      ((void (__fastcall *)(struct IXMLDOMDocument2 *))v14->lpVtbl->Release)(v14);
    if ( v12 )
      ((void (__fastcall *)(struct IXMLDOMDocument2 *))v12->lpVtbl->Release)(v12);
    goto LABEL_39;
  }
  v10 = (const unsigned __int16 *)a2[2];
  if ( !v10 )
  {
    v8 = -2147467261;
    v7 = 1440;
    v6 = -2147467261;
    goto LABEL_3;
  }
  v11 = SdpCatId(v9, v10, (unsigned __int16 **)&Block);
  v6 = v11;
  if ( v11 >= 0 )
  {
    v3 = (unsigned __int16 *)Block;
    goto LABEL_12;
  }
  SdpDebugTrace(1u, L"Rootcause::BuildResultResolutionsXml", 1443, v11);
  v3 = (unsigned __int16 *)Block;
LABEL_39:
  if ( v3 )
    operator delete(v3);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800192ac  mov     rax, rsp
0x1800192af  mov     [rax+8], rbx
0x1800192b3  mov     [rax+18h], r8
0x1800192b7  push    rbp
0x1800192b8  push    rsi
0x1800192b9  push    rdi
0x1800192ba  push    r12
0x1800192bc  push    r13
0x1800192be  push    r14
0x1800192c0  push    r15
0x1800192c2  sub     rsp, 30h
0x1800192c6  xor     ebp, ebp
0x1800192c8  mov     qword ptr [rax-48h], 0
0x1800192d0  mov     [rax+20h], rbp
0x1800192d4  mov     r14, rdx
0x1800192d7  mov     r15, rcx
0x1800192da  test    r8, r8
0x1800192dd  jnz     short loc_180019303
0x1800192df  mov     ebx, 80070057h
0x1800192e4  mov     r8d, 59Bh; int
0x1800192ea  mov     r9d, ebx; int
0x1800192ed  lea     rdx, aRootcauseBuild_2; "Rootcause::BuildResultResolutionsXml"
0x1800192f4  mov     ecx, 1; Level
0x1800192f9  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800192fe  jmp     loc_18001953C
0x180019303  mov     rcx, [rcx+28h]; unsigned __int16 *
0x180019307  test    rcx, rcx
0x18001930a  jnz     short loc_18001931D
0x18001930c  mov     r9d, 80004003h
0x180019312  mov     r8d, 59Dh
0x180019318  mov     ebx, r9d
0x18001931b  jmp     short loc_1800192ED
0x18001931d  test    r14, r14
0x180019320  jz      short loc_18001937E
0x180019322  mov     rdx, [rdx+10h]; unsigned __int16 *
0x180019326  test    rdx, rdx
0x180019329  jnz     short loc_18001933C
0x18001932b  mov     r9d, 80004003h
0x180019331  mov     r8d, 5A0h
0x180019337  mov     ebx, r9d
0x18001933a  jmp     short loc_1800192ED
0x18001933c  lea     r8, [rsp+68h+Block]; unsigned __int16 **
0x180019344  call    ?SdpCatId@@YAJPEBG0PEAPEAG@Z; SdpCatId(ushort const *,ushort const *,ushort * *)
0x180019349  mov     ebx, eax
0x18001934b  test    eax, eax
0x18001934d  jns     short loc_180019376
0x18001934f  mov     r9d, eax; int
0x180019352  lea     rdx, aRootcauseBuild_2; "Rootcause::BuildResultResolutionsXml"
0x180019359  mov     r8d, 5A3h; int
0x18001935f  mov     ecx, 1; Level
0x180019364  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180019369  mov     rbp, [rsp+68h+Block]
0x180019371  jmp     loc_18001952F
0x180019376  mov     rbp, [rsp+68h+Block]
0x18001937e  lea     rdx, [rsp+68h+var_48]; struct IXMLDOMDocument2 **
0x180019383  xor     edi, edi
0x180019385  lea     rcx, aXmlVersion10En_23; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x18001938c  call    ?SdpXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; SdpXmlCreate(ushort const *,IXMLDOMDocument2 * *)
0x180019391  mov     rsi, [rsp+68h+var_48]
0x180019396  mov     ebx, eax
0x180019398  test    eax, eax
0x18001939a  jns     short loc_1800193BB
0x18001939c  mov     r8d, 5A7h; int
0x1800193a2  mov     r9d, eax; int
0x1800193a5  lea     rdx, aRootcauseBuild_2; "Rootcause::BuildResultResolutionsXml"
0x1800193ac  mov     ecx, 1; Level
0x1800193b1  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800193b6  jmp     loc_180019507
0x1800193bb  xor     r13d, r13d
0x1800193be  cmp     [r15+20h], edi
0x1800193c2  jbe     loc_1800194ED
0x1800193c8  lea     rbx, [r15+10h]
0x1800193cc  mov     r12, rbx
0x1800193cf  test    rdi, rdi
0x1800193d2  jz      short loc_1800193E8
0x1800193d4  mov     rax, [rdi]
0x1800193d7  mov     rcx, rdi
0x1800193da  mov     rax, [rax+10h]
0x1800193de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193e3  xor     edi, edi
0x1800193e5  mov     r12, rbx
0x1800193e8  test    r14, r14
0x1800193eb  jz      short loc_180019417
0x1800193ed  mov     r8, [r14+28h]; struct tagSAFEARRAY *
0x1800193f1  lea     rcx, ds:0[r13*4]
0x1800193f9  mov     rdx, [r14+20h]; struct tagSAFEARRAY *
0x1800193fd  add     rcx, r13
0x180019400  shl     rcx, 4
0x180019404  add     rcx, [r12]; this
0x180019408  call    ?RecordParameters@Resolver@@QEAAJPEAUtagSAFEARRAY@@0@Z; Resolver::RecordParameters(tagSAFEARRAY *,tagSAFEARRAY *)
0x18001940d  mov     ebx, eax
0x18001940f  test    eax, eax
0x180019411  js      loc_1800194C9
0x180019417  xor     edx, edx
0x180019419  mov     [rsp+68h+Block], 0
0x180019425  test    r14, r14
0x180019428  lea     rcx, ds:0[r13*4]
0x180019430  lea     r9, [rsp+68h+Block]; struct IXMLDOMDocument2 **
0x180019438  mov     r8, rbp; unsigned __int16 *
0x18001943b  setz    dl; int
0x18001943e  add     rcx, r13
0x180019441  shl     rcx, 4
0x180019445  add     rcx, [r12]; this
0x180019449  call    ?BuildResultXml@Resolver@@AEAAJHPEBGPEAPEAUIXMLDOMDocument2@@@Z; Resolver::BuildResultXml(int,ushort const *,IXMLDOMDocument2 * *)
0x18001944e  mov     ebx, eax
0x180019450  test    eax, eax
0x180019452  jns     short loc_180019470
0x180019454  mov     r9d, eax; int
0x180019457  lea     rdx, aResolverDescri; "Resolver::Describe"
0x18001945e  mov     r8d, 0AFh; int
0x180019464  mov     ecx, 1; Level
0x180019469  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001946e  jmp     short loc_180019487
0x180019470  mov     rdi, [rsp+68h+Block]
0x180019478  mov     rcx, rdi
0x18001947b  mov     rax, [rdi]
0x18001947e  mov     rax, [rax+8]
0x180019482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019487  mov     rcx, [rsp+68h+Block]
0x18001948f  test    rcx, rcx
0x180019492  jz      short loc_1800194A0
0x180019494  mov     rax, [rcx]
0x180019497  mov     rax, [rax+10h]
0x18001949b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800194a0  test    ebx, ebx
0x1800194a2  js      short loc_1800194DF
0x1800194a4  mov     r8, rdi; struct IXMLDOMDocument2 *
0x1800194a7  xor     edx, edx; struct IXMLDOMElement *
0x1800194a9  mov     rcx, rsi; struct IXMLDOMDocument2 *
0x1800194ac  call    ?SdpXmlAppend@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@0@Z; SdpXmlAppend(IXMLDOMDocument2 *,IXMLDOMElement *,IXMLDOMDocument2 *)
0x1800194b1  mov     ebx, eax
0x1800194b3  test    eax, eax
0x1800194b5  js      short loc_1800194D4
0x1800194b7  inc     r13d
0x1800194ba  cmp     r13d, [r15+20h]
0x1800194be  jnb     short loc_1800194ED
0x1800194c0  lea     rbx, [r15+10h]
0x1800194c4  jmp     loc_1800193CF
0x1800194c9  mov     r8d, 5B3h
0x1800194cf  jmp     loc_1800193A2
0x1800194d4  mov     r8d, 5BAh
0x1800194da  jmp     loc_1800193A2
0x1800194df  mov     r9d, ebx
0x1800194e2  mov     r8d, 5B7h
0x1800194e8  jmp     loc_1800193A5
0x1800194ed  mov     rax, [rsp+68h+arg_10]
0x1800194f5  mov     rcx, rsi
0x1800194f8  mov     [rax], rsi
0x1800194fb  mov     rax, [rsi]
0x1800194fe  mov     rax, [rax+8]
0x180019502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019507  test    rsi, rsi
0x18001950a  jz      short loc_18001951B
0x18001950c  mov     rax, [rsi]
0x18001950f  mov     rcx, rsi
0x180019512  mov     rax, [rax+10h]
0x180019516  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001951b  test    rdi, rdi
0x18001951e  jz      short loc_18001952F
0x180019520  mov     rax, [rdi]
0x180019523  mov     rcx, rdi
0x180019526  mov     rax, [rax+10h]
0x18001952a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001952f  test    rbp, rbp
0x180019532  jz      short loc_18001953C
0x180019534  mov     rcx, rbp; Block
0x180019537  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001953c  mov     eax, ebx
0x18001953e  mov     rbx, [rsp+68h+arg_0]
0x180019543  add     rsp, 30h
0x180019547  pop     r15
0x180019549  pop     r14
0x18001954b  pop     r13
0x18001954d  pop     r12
0x18001954f  pop     rdi
0x180019550  pop     rsi
0x180019551  pop     rbp
0x180019552  retn
```
