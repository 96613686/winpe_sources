# DiagPackage::BuildReportPXml(IXMLDOMDocument2 * *)

- ea: `0x180014f7c`
- end: `0x1800151f5`
- name: `?BuildReportPXml@DiagPackage@@AEAAJPEAPEAUIXMLDOMDocument2@@@Z`
- size: `633`
- prototype: `__int64 __fastcall(DiagPackage *__hidden this, struct IXMLDOMDocument2 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180017438`

## callees

- `0x180014f7c`
- `0x18001b9c8`
- `0x180026fa0`
- `0x180027ea4`
- `0x1800280f8`
- `0x18002827c`
- `0x180028f24`
- `0x18002a010`

## string_xrefs

- `0x180014fb7`: `DiagPackage::BuildReportPXml`
- `0x180014fed`: `DiagPackage::BuildReportPXml`
- `0x18001503d`: `DiagPackage::BuildReportPXml`
- `0x180015091`: `DiagPackage::BuildReportPXml`
- `0x1800151c4`: `DiagPackage::BuildReportPXml`
- `0x180014fd8`: `<?xml version="1.0" encoding="utf-8"?><Problem/>`

## pseudocode

```c
__int64 __fastcall DiagPackage::BuildReportPXml(DiagPackage *this, struct IXMLDOMDocument2 **a2)
{
  struct IXMLDOMDocument2 *v2; // rsi
  struct IXMLDOMElement *v3; // rdi
  unsigned int v6; // ebx
  int v7; // eax
  struct IXMLDOMDocument2 *v8; // r14
  int v9; // eax
  int v10; // r8d
  int v11; // r9d
  struct IXMLDOMDocument2 *v12; // r8
  int v13; // eax
  int v14; // r8d
  int v15; // r9d
  __int64 v16; // r12
  int RcReportXml; // eax
  struct IXMLDOMDocument2 *v18; // rcx
  struct IXMLDOMNode *v19; // r9
  struct IXMLDOMElement *v21; // [rsp+78h] [rbp+48h] BYREF
  struct IXMLDOMDocument2 *v22; // [rsp+80h] [rbp+50h] BYREF
  struct IXMLDOMDocument2 *v23; // [rsp+88h] [rbp+58h] BYREF

  v2 = 0;
  v23 = 0;
  v3 = 0;
  v22 = 0;
  v21 = 0;
  if ( !a2 )
  {
    v6 = -2147024809;
    SdpDebugTrace(1u, L"DiagPackage::BuildReportPXml", 2416, -2147024809);
    return v6;
  }
  v7 = SdpXmlCreate((OLECHAR *)L"<?xml version=\"1.0\" encoding=\"utf-8\"?><Problem/>", &v23);
  v6 = v7;
  if ( v7 >= 0 )
  {
    v8 = v23;
    v9 = SdpXmlCreateNode(v23, 0, L"DetectionInformation", 0, &v21);
    v6 = v9;
    if ( v9 < 0 )
    {
      v10 = 2434;
LABEL_7:
      v11 = v9;
LABEL_8:
      SdpDebugTrace(1u, L"DiagPackage::BuildReportPXml", v10, v11);
      v3 = v21;
      goto LABEL_27;
    }
    v12 = (struct IXMLDOMDocument2 *)*((_QWORD *)this + 16);
    if ( !v12 )
    {
      v11 = -2147467261;
      v10 = 2436;
      v6 = -2147467261;
      goto LABEL_8;
    }
    v3 = v21;
    v13 = SdpXmlAppend(0, v21, v12);
    v6 = v13;
    if ( v13 >= 0 )
    {
      if ( v3 )
      {
        ((void (__fastcall *)(struct IXMLDOMElement *))v3->lpVtbl->Release)(v3);
        v21 = 0;
      }
      v9 = SdpXmlCreateNode(v8, 0, L"RootCauseInformation", 0, &v21);
      v6 = v9;
      if ( v9 < 0 )
      {
        v10 = 2452;
        goto LABEL_7;
      }
      v3 = v21;
      v16 = 0;
      if ( !*((_DWORD *)this + 8) )
      {
LABEL_26:
        *a2 = v8;
        v8 = 0;
        goto LABEL_27;
      }
      while ( 1 )
      {
        if ( v2 )
        {
          ((void (__fastcall *)(struct IXMLDOMDocument2 *))v2->lpVtbl->Release)(v2);
          v2 = 0;
          v22 = 0;
        }
        if ( !*((_QWORD *)this + 3) )
          break;
        RcReportXml = Rootcause::get_RcReportXml((Rootcause *)(*((_QWORD *)this + 3) + 144 * v16), &v22);
        v6 = RcReportXml;
        if ( RcReportXml < 0 )
        {
          SdpDebugTrace(1u, L"DiagPackage::BuildReportPXml", 2459, RcReportXml);
          v2 = v22;
          goto LABEL_27;
        }
        v2 = v22;
        v13 = SdpXmlMerge(v18, (struct IXMLDOMNode *)v3, v22, v19);
        v6 = v13;
        if ( v13 < 0 )
        {
          v14 = 2462;
          goto LABEL_13;
        }
        v16 = (unsigned int)(v16 + 1);
        if ( (unsigned int)v16 >= *((_DWORD *)this + 8) )
          goto LABEL_26;
      }
      v15 = -2147467261;
      v14 = 2457;
      v6 = -2147467261;
    }
    else
    {
      v14 = 2440;
LABEL_13:
      v15 = v13;
    }
    SdpDebugTrace(1u, L"DiagPackage::BuildReportPXml", v14, v15);
    goto LABEL_27;
  }
  SdpDebugTrace(1u, L"DiagPackage::BuildReportPXml", 2423, v7);
  v8 = v23;
LABEL_27:
  if ( v8 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v8->lpVtbl->Release)(v8);
  if ( v2 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v2->lpVtbl->Release)(v2);
  if ( v3 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v3->lpVtbl->Release)(v3);
  return v6;
}

```

## disassembly

```asm
0x180014f7c  mov     [rsp-38h+arg_0], rbx
0x180014f81  push    rbp
0x180014f82  push    rsi
0x180014f83  push    rdi
0x180014f84  push    r12
0x180014f86  push    r13
0x180014f88  push    r14
0x180014f8a  push    r15
0x180014f8c  mov     rbp, rsp
0x180014f8f  sub     rsp, 30h
0x180014f93  xor     esi, esi
0x180014f95  mov     [rbp+arg_18], 0
0x180014f9d  xor     edi, edi
0x180014f9f  mov     [rbp+arg_10], rsi
0x180014fa3  mov     [rbp+arg_8], rdi
0x180014fa7  mov     r13, rdx
0x180014faa  mov     r15, rcx
0x180014fad  test    rdx, rdx
0x180014fb0  jnz     short loc_180014FD4
0x180014fb2  mov     ebx, 80070057h
0x180014fb7  lea     rdx, aDiagpackageBui_1; "DiagPackage::BuildReportPXml"
0x180014fbe  mov     r9d, ebx; int
0x180014fc1  lea     ecx, [rsi+1]; Level
0x180014fc4  mov     r8d, 970h; int
0x180014fca  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180014fcf  jmp     loc_18001519F
0x180014fd4  lea     rdx, [rbp+arg_18]; struct IXMLDOMDocument2 **
0x180014fd8  lea     rcx, aXmlVersion10En_12; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x180014fdf  call    ?SdpXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; SdpXmlCreate(ushort const *,IXMLDOMDocument2 * *)
0x180014fe4  mov     ebx, eax
0x180014fe6  test    eax, eax
0x180014fe8  jns     short loc_18001500D
0x180014fea  mov     r9d, eax; int
0x180014fed  lea     rdx, aDiagpackageBui_1; "DiagPackage::BuildReportPXml"
0x180014ff4  mov     r8d, 977h; int
0x180014ffa  mov     ecx, 1; Level
0x180014fff  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180015004  mov     r14, [rbp+arg_18]
0x180015008  jmp     loc_180015163
0x18001500d  mov     r14, [rbp+arg_18]
0x180015011  lea     rax, [rbp+arg_8]
0x180015015  mov     rcx, r14; struct IXMLDOMDocument2 *
0x180015018  mov     [rsp+30h+var_10], rax; struct IXMLDOMElement **
0x18001501d  xor     r9d, r9d; unsigned __int16 *
0x180015020  lea     r8, aDetectioninfor; "DetectionInformation"
0x180015027  xor     edx, edx; struct IXMLDOMElement *
0x180015029  call    ?SdpXmlCreateNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2PEAPEAU2@@Z; SdpXmlCreateNode(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x18001502e  mov     ebx, eax
0x180015030  test    eax, eax
0x180015032  jns     short loc_180015057
0x180015034  mov     r8d, 982h; int
0x18001503a  mov     r9d, eax; int
0x18001503d  lea     rdx, aDiagpackageBui_1; "DiagPackage::BuildReportPXml"
0x180015044  mov     ecx, 1; Level
0x180015049  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001504e  mov     rdi, [rbp+arg_8]
0x180015052  jmp     loc_180015163
0x180015057  mov     r8, [r15+80h]; struct IXMLDOMDocument2 *
0x18001505e  test    r8, r8
0x180015061  jnz     short loc_180015074
0x180015063  mov     r9d, 80004003h
0x180015069  mov     r8d, 984h
0x18001506f  mov     ebx, r9d
0x180015072  jmp     short loc_18001503D
0x180015074  mov     rdi, [rbp+arg_8]
0x180015078  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x18001507a  mov     rdx, rdi; struct IXMLDOMElement *
0x18001507d  call    ?SdpXmlAppend@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@0@Z; SdpXmlAppend(IXMLDOMDocument2 *,IXMLDOMElement *,IXMLDOMDocument2 *)
0x180015082  mov     ebx, eax
0x180015084  test    eax, eax
0x180015086  jns     short loc_1800150A7
0x180015088  mov     r8d, 988h; int
0x18001508e  mov     r9d, eax; int
0x180015091  lea     rdx, aDiagpackageBui_1; "DiagPackage::BuildReportPXml"
0x180015098  mov     ecx, 1; Level
0x18001509d  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800150a2  jmp     loc_180015163
0x1800150a7  test    rdi, rdi
0x1800150aa  jz      short loc_1800150BF
0x1800150ac  mov     rax, [rdi]
0x1800150af  mov     rcx, rdi
0x1800150b2  mov     rax, [rax+10h]
0x1800150b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800150bb  mov     [rbp+arg_8], rsi
0x1800150bf  lea     rax, [rbp+arg_8]
0x1800150c3  xor     r9d, r9d; unsigned __int16 *
0x1800150c6  lea     r8, aRootcauseinfor; "RootCauseInformation"
0x1800150cd  mov     [rsp+30h+var_10], rax; struct IXMLDOMElement **
0x1800150d2  xor     edx, edx; struct IXMLDOMElement *
0x1800150d4  mov     rcx, r14; struct IXMLDOMDocument2 *
0x1800150d7  call    ?SdpXmlCreateNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2PEAPEAU2@@Z; SdpXmlCreateNode(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x1800150dc  mov     ebx, eax
0x1800150de  test    eax, eax
0x1800150e0  jns     short loc_1800150ED
0x1800150e2  mov     r8d, 994h
0x1800150e8  jmp     loc_18001503A
0x1800150ed  mov     rdi, [rbp+arg_8]
0x1800150f1  xor     r12d, r12d
0x1800150f4  cmp     [r15+20h], esi
0x1800150f8  jbe     short loc_18001515C
0x1800150fa  test    rsi, rsi
0x1800150fd  jz      short loc_180015114
0x1800150ff  mov     rax, [rsi]
0x180015102  mov     rcx, rsi
0x180015105  mov     rax, [rax+10h]
0x180015109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001510e  xor     esi, esi
0x180015110  mov     [rbp+arg_10], rsi
0x180015114  cmp     qword ptr [r15+18h], 0
0x180015119  jz      loc_1800151E1
0x18001511f  lea     rcx, [r12+r12*8]
0x180015123  shl     rcx, 4
0x180015127  lea     rdx, [rbp+arg_10]; struct IXMLDOMDocument2 **
0x18001512b  add     rcx, [r15+18h]; this
0x18001512f  call    ?get_RcReportXml@Rootcause@@QEAAJPEAPEAUIXMLDOMDocument2@@@Z; Rootcause::get_RcReportXml(IXMLDOMDocument2 * *)
0x180015134  mov     ebx, eax
0x180015136  test    eax, eax
0x180015138  js      loc_1800151C1
0x18001513e  mov     rsi, [rbp+arg_10]
0x180015142  mov     rdx, rdi; struct IXMLDOMNode *
0x180015145  mov     r8, rsi; struct IXMLDOMDocument2 *
0x180015148  call    ?SdpXmlMerge@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@01@Z; SdpXmlMerge(IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMDocument2 *,IXMLDOMNode *)
0x18001514d  mov     ebx, eax
0x18001514f  test    eax, eax
0x180015151  js      short loc_1800151B6
0x180015153  inc     r12d
0x180015156  cmp     r12d, [r15+20h]
0x18001515a  jb      short loc_1800150FA
0x18001515c  mov     [r13+0], r14
0x180015160  xor     r14d, r14d
0x180015163  test    r14, r14
0x180015166  jz      short loc_180015177
0x180015168  mov     rax, [r14]
0x18001516b  mov     rcx, r14
0x18001516e  mov     rax, [rax+10h]
0x180015172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015177  test    rsi, rsi
0x18001517a  jz      short loc_18001518B
0x18001517c  mov     rax, [rsi]
0x18001517f  mov     rcx, rsi
0x180015182  mov     rax, [rax+10h]
0x180015186  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001518b  test    rdi, rdi
0x18001518e  jz      short loc_18001519F
0x180015190  mov     rax, [rdi]
0x180015193  mov     rcx, rdi
0x180015196  mov     rax, [rax+10h]
0x18001519a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001519f  mov     eax, ebx
0x1800151a1  mov     rbx, [rsp+30h+arg_0]
0x1800151a6  add     rsp, 30h
0x1800151aa  pop     r15
0x1800151ac  pop     r14
0x1800151ae  pop     r13
0x1800151b0  pop     r12
0x1800151b2  pop     rdi
0x1800151b3  pop     rsi
0x1800151b4  pop     rbp
0x1800151b5  retn
0x1800151b6  mov     r8d, 99Eh
0x1800151bc  jmp     loc_18001508E
0x1800151c1  mov     r9d, eax; int
0x1800151c4  lea     rdx, aDiagpackageBui_1; "DiagPackage::BuildReportPXml"
0x1800151cb  mov     r8d, 99Bh; int
0x1800151d1  mov     ecx, 1; Level
0x1800151d6  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800151db  mov     rsi, [rbp+arg_10]
0x1800151df  jmp     short loc_180015163
0x1800151e1  mov     r9d, 80004003h
0x1800151e7  mov     r8d, 999h
0x1800151ed  mov     ebx, r9d
0x1800151f0  jmp     loc_180015091
```
