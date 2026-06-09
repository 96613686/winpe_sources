# XwpParseAPSSIDConfig

- ea: `0x180048080`
- end: `0x1800481e9`
- name: `XwpParseAPSSIDConfig`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800470b8`

## callees

- `0x180009654`
- `0x18000dea8`
- `0x18000fd24`
- `0x180014d9c`
- `0x180019370`
- `0x180048080`
- `0x1800481f0`
- `0x18004e92c`
- `0x18004ef98`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004816a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004816a`

## string_xrefs

- `0x1800480dc`: `WLANAPProfile:SSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall XwpParseAPSSIDConfig(struct IXMLDOMNode *a1, __int64 a2, _DWORD *a3, __int64 a4)
{
  void *v6; // rbx
  int v7; // r14d
  DWORD Nodes; // edi
  int v9; // esi
  _DWORD *v11; // rax
  struct IXMLDOMNode *v12; // [rsp+20h] [rbp-20h] BYREF
  struct IXMLDOMNodeList *v13; // [rsp+28h] [rbp-18h] BYREF
  SIZE_T dwBytes[2]; // [rsp+30h] [rbp-10h] BYREF
  int v15; // [rsp+88h] [rbp+48h] BYREF
  int v16; // [rsp+8Ch] [rbp+4Ch]

  v16 = HIDWORD(a4);
  v12 = 0;
  v13 = 0;
  v15 = 0;
  dwBytes[0] = 0;
  v6 = 0;
  v7 = 0;
  if ( a3 )
    *a3 = 0;
  Nodes = XcGetNodes(a1, L"WLANAPProfile:SSID", &v13, &v15);
  if ( Nodes )
    goto LABEL_6;
  v9 = v15;
  if ( v15 < 1 )
  {
    Nodes = 1206;
LABEL_6:
    if ( a3 )
      *a3 = 0;
    if ( v6 )
      Xc_Process_user_free(v6);
    goto LABEL_10;
  }
  Nodes = VariableListSize(0xCu, v15, 0x24u, dwBytes);
  if ( Nodes )
    goto LABEL_6;
  v11 = Xc_Process_user_allocate(dwBytes[0]);
  v6 = v11;
  if ( !v11 )
  {
    Nodes = GetLastError();
    if ( !Nodes )
      goto LABEL_10;
    goto LABEL_6;
  }
  *v11 = 3146112;
  v11[1] = v9;
  v11[2] = v9;
  while ( v7 < v9 )
  {
    Nodes = XcGetItem(v13, v7, &v12);
    if ( Nodes )
      goto LABEL_6;
    Nodes = XwpParseAPSSIDNode(v12);
    if ( Nodes )
      goto LABEL_6;
    ATL::CComPtrBase<IXMLDOMNode>::Release(&v12);
    ++v7;
  }
  *(_QWORD *)(a2 + 8) = v6;
LABEL_10:
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v13);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v12);
  return Nodes;
}

```

## disassembly

```asm
0x180048080  mov     [rsp-28h+arg_0], rbx
0x180048085  mov     [rsp-28h+arg_8], rsi
0x18004808a  mov     qword ptr [rsp-28h+arg_18], r9
0x18004808f  push    rbp
0x180048090  push    rdi
0x180048091  push    r13
0x180048093  push    r14
0x180048095  push    r15
0x180048097  mov     rbp, rsp
0x18004809a  sub     rsp, 40h
0x18004809e  mov     r15, r8
0x1800480a1  mov     r13, rdx
0x1800480a4  mov     [rbp+var_20], 0
0x1800480ac  mov     [rbp+var_18], 0
0x1800480b4  mov     [rbp+arg_18], 0
0x1800480bb  mov     [rbp+dwBytes], 0
0x1800480c3  xor     ebx, ebx
0x1800480c5  xor     r14d, r14d
0x1800480c8  mov     [rbp+arg_10], r14d
0x1800480cc  test    r8, r8
0x1800480cf  jz      short loc_1800480D4
0x1800480d1  mov     [r8], ebx
0x1800480d4  lea     r9, [rbp+arg_18]; int *
0x1800480d8  lea     r8, [rbp+var_18]; struct IXMLDOMNodeList **
0x1800480dc  lea     rdx, aWlanapprofileS_1; "WLANAPProfile:SSID"
0x1800480e3  call    ?XcGetNodes@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAUIXMLDOMNodeList@@PEAJ@Z; XcGetNodes(IXMLDOMNode *,ushort const *,IXMLDOMNodeList * *,long *)
0x1800480e8  mov     edi, eax
0x1800480ea  test    eax, eax
0x1800480ec  jnz     short loc_1800480FC
0x1800480ee  movsxd  rsi, [rbp+arg_18]
0x1800480f2  cmp     esi, 1
0x1800480f5  jge     short loc_18004813E
0x1800480f7  mov     edi, 4B6h
0x1800480fc  test    r15, r15
0x1800480ff  jz      short loc_180048104
0x180048101  mov     [r15], r14d
0x180048104  test    rbx, rbx
0x180048107  jz      short loc_180048112
0x180048109  mov     rcx, rbx; lpMem
0x18004810c  call    ?Xc_Process_user_free@@YAXPEAX@Z; Xc_Process_user_free(void *)
0x180048111  nop
0x180048112  lea     rcx, [rbp+var_18]
0x180048116  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18004811b  nop
0x18004811c  lea     rcx, [rbp+var_20]
0x180048120  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180048125  mov     eax, edi
0x180048127  mov     rbx, [rsp+40h+arg_0]
0x18004812c  mov     rsi, [rsp+40h+arg_8]
0x180048131  add     rsp, 40h
0x180048135  pop     r15
0x180048137  pop     r14
0x180048139  pop     r13
0x18004813b  pop     rdi
0x18004813c  pop     rbp
0x18004813d  retn
0x18004813e  mov     rdx, rsi; unsigned __int64
0x180048141  lea     r9, [rbp+dwBytes]; unsigned __int64 *
0x180048145  mov     ecx, 0Ch; unsigned __int64
0x18004814a  lea     r8d, [rcx+18h]; unsigned __int64
0x18004814e  call    ?VariableListSize@@YAK_K00PEA_K@Z; VariableListSize(unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180048153  mov     edi, eax
0x180048155  test    eax, eax
0x180048157  jnz     short loc_1800480FC
0x180048159  mov     rcx, [rbp+dwBytes]; dwBytes
0x18004815d  call    ?Xc_Process_user_allocate@@YAPEAX_K@Z; Xc_Process_user_allocate(unsigned __int64)
0x180048162  mov     rbx, rax
0x180048165  test    rax, rax
0x180048168  jnz     short loc_180048178
0x18004816a  call    cs:__imp_GetLastError
0x180048170  mov     edi, eax
0x180048172  test    eax, eax
0x180048174  jz      short loc_180048112
0x180048176  jmp     short loc_1800480FC
0x180048178  mov     dword ptr [rax], 300180h
0x18004817e  mov     [rax+4], esi
0x180048181  mov     [rax+8], esi
0x180048184  cmp     r14d, esi
0x180048187  jge     short loc_1800481DF
0x180048189  lea     r8, [rbp+var_20]; struct IXMLDOMNode **
0x18004818d  mov     edx, r14d; int
0x180048190  mov     rcx, [rbp+var_18]; struct IXMLDOMNodeList *
0x180048194  call    ?XcGetItem@@YAKPEAUIXMLDOMNodeList@@JPEAPEAUIXMLDOMNode@@@Z; XcGetItem(IXMLDOMNodeList *,long,IXMLDOMNode * *)
0x180048199  mov     edi, eax
0x18004819b  test    eax, eax
0x18004819d  jnz     short loc_1800481D6
0x18004819f  movsxd  rax, r14d
0x1800481a2  lea     rcx, ds:3[rax*8]
0x1800481aa  add     rcx, rax
0x1800481ad  lea     rdx, [rbx+rcx*4]
0x1800481b1  lea     r9, [rbp+arg_18]
0x1800481b5  lea     r8, [rbp+arg_10]
0x1800481b9  mov     rcx, [rbp+var_20]; struct IXMLDOMNode *
0x1800481bd  call    XwpParseAPSSIDNode
0x1800481c2  mov     edi, eax
0x1800481c4  test    eax, eax
0x1800481c6  jnz     short loc_1800481D6
0x1800481c8  lea     rcx, [rbp+var_20]
0x1800481cc  call    ?Release@?$CComPtrBase@UIXMLDOMNode@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IXMLDOMNode>::Release(void)
0x1800481d1  inc     r14d
0x1800481d4  jmp     short loc_180048184
0x1800481d6  mov     r14d, [rbp+arg_10]
0x1800481da  jmp     loc_1800480FC
0x1800481df  mov     [r13+8], rbx
0x1800481e3  jmp     loc_180048112
```
