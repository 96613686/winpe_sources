# CDescriptionManager::HrRD_RemoveFromEventing(_GUID const &)

- ea: `0x18000b0d0`
- end: `0x18000b2c2`
- name: `?HrRD_RemoveFromEventing@CDescriptionManager@@AEAAJAEBU_GUID@@@Z`
- size: `498`
- prototype: `__int64 __fastcall(CDescriptionManager *__hidden this, const struct _GUID *)`
- caller_count: `4`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c940`
- `0x18000fdc0`
- `0x1800112b0`
- `0x180011f70`

## callees

- `0x180003e08`
- `0x1800055a8`
- `0x1800056d8`
- `0x1800056f0`
- `0x180007db0`
- `0x180009d50`
- `0x18000b0d0`
- `0x180032220`
- `0x18003b1cc`
- `0x18003c018`
- `0x180059010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b1b4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b1b4`

## string_xrefs

- `0x18000b1f3`: `ddd:serviceList/ddd:service`

## pseudocode

```c
__int64 __fastcall CDescriptionManager::HrRD_RemoveFromEventing(CDescriptionManager *this, const struct _GUID *a2)
{
  int DocumentAndRootNode; // ebx
  __int64 Key; // rax
  __int64 v7; // rax
  _BYTE v8[8]; // [rsp+20h] [rbp-20h] BYREF
  void *Block; // [rsp+28h] [rbp-18h] BYREF
  _BYTE v10[8]; // [rsp+30h] [rbp-10h] BYREF
  _BYTE v11[8]; // [rsp+38h] [rbp-8h] BYREF
  char v12; // [rsp+70h] [rbp+30h] BYREF
  char v13; // [rsp+78h] [rbp+38h] BYREF

  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids);
  SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(v11);
  DocumentAndRootNode = CDescriptionManager::HrLoadDocumentAndRootNode(this, a2, v11);
  if ( DocumentAndRootNode >= 0 )
  {
    SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(v10);
    DocumentAndRootNode = HrSelectNodes(L"//ddd:device", v11, v10);
    if ( DocumentAndRootNode >= 0 )
    {
      while ( DocumentAndRootNode >= 0 )
      {
        SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(&v12);
        Key = LKRhash::CTypedHashTable<CNoRefHashTable,URL_HASH_ENTRY,char const *,LKRhash::CLKRHashTable>::_ExtractKey(v10);
        if ( (*(unsigned int (__fastcall **)(__int64, char *))(*(_QWORD *)Key + 72LL))(Key, &v12) )
        {
          ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(&v12);
          break;
        }
        Block = 0;
        DocumentAndRootNode = HrSelectNodeText((OLECHAR *)L"ddd:UDN");
        if ( DocumentAndRootNode >= 0 )
        {
          SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(v8);
          DocumentAndRootNode = HrSelectNodes(L"ddd:serviceList/ddd:service", &v12, v8);
          if ( DocumentAndRootNode >= 0 )
          {
            while ( DocumentAndRootNode >= 0 )
            {
              SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(&v13);
              v7 = LKRhash::CTypedHashTable<CNoRefHashTable,URL_HASH_ENTRY,char const *,LKRhash::CLKRHashTable>::_ExtractKey(v8);
              if ( (*(unsigned int (__fastcall **)(__int64, char *))(*(_QWORD *)v7 + 72LL))(v7, &v13) )
              {
                ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(&v13);
                break;
              }
              DocumentAndRootNode = HrRegisterServiceWithEventing(&v13, &Block, 0);
              ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(&v13);
            }
          }
          ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(v8);
        }
        free(Block);
        ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(&v12);
      }
    }
    ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(v10);
  }
  if ( DocumentAndRootNode
    && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      91,
      WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids,
      (unsigned int)DocumentAndRootNode);
  }
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(v11);
  return (unsigned int)DocumentAndRootNode;
}

```

## disassembly

```asm
0x18000b0d0  mov     [rsp-18h+arg_0], rbx
0x18000b0d5  push    rbp
0x18000b0d6  push    rsi
0x18000b0d7  push    rdi
0x18000b0d8  mov     rbp, rsp
0x18000b0db  sub     rsp, 40h
0x18000b0df  mov     rbx, rdx
0x18000b0e2  mov     rdi, rcx
0x18000b0e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b0ec  lea     rsi, WPP_GLOBAL_Control
0x18000b0f3  cmp     rcx, rsi
0x18000b0f6  jnz     loc_18000B25D
0x18000b0fc  lea     rcx, [rbp+var_8]; void *
0x18000b100  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x18000b105  lea     r8, [rbp+var_8]
0x18000b109  mov     rdx, rbx
0x18000b10c  mov     rcx, rdi
0x18000b10f  call    ?HrLoadDocumentAndRootNode@CDescriptionManager@@AEAAJAEBU_GUID@@AEAV?$SmartComPtr@UIXMLDOMNode@@@@@Z; CDescriptionManager::HrLoadDocumentAndRootNode(_GUID const &,SmartComPtr<IXMLDOMNode> &)
0x18000b114  mov     ebx, eax
0x18000b116  test    eax, eax
0x18000b118  jns     short loc_18000B13B
0x18000b11a  test    ebx, ebx
0x18000b11c  jnz     loc_18000B28B
0x18000b122  lea     rcx, [rbp+var_8]
0x18000b126  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x18000b12b  mov     eax, ebx
0x18000b12d  mov     rbx, [rsp+40h+arg_0]
0x18000b132  add     rsp, 40h
0x18000b136  pop     rdi
0x18000b137  pop     rsi
0x18000b138  pop     rbp
0x18000b139  retn
0x18000b13b  lea     rcx, [rbp+var_10]; void *
0x18000b13f  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x18000b144  lea     r8, [rbp+var_10]
0x18000b148  lea     rdx, [rbp+var_8]
0x18000b14c  lea     rcx, aDddDevice; "//ddd:device"
0x18000b153  call    ?HrSelectNodes@@YAJPEBGAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEAV?$SmartComPtr@UIXMLDOMNodeList@@@@@Z; HrSelectNodes(ushort const *,SmartComPtr<IXMLDOMNode> &,SmartComPtr<IXMLDOMNodeList> &)
0x18000b158  mov     ebx, eax
0x18000b15a  test    eax, eax
0x18000b15c  js      short loc_18000B1D4
0x18000b15e  test    ebx, ebx
0x18000b160  js      short loc_18000B1D4
0x18000b162  lea     rcx, [rbp+arg_10]; void *
0x18000b166  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x18000b16b  lea     rcx, [rbp+var_10]
0x18000b16f  call    ?_ExtractKey@?$CTypedHashTable@VCNoRefHashTable@@VURL_HASH_ENTRY@@PEBDVCLKRHashTable@LKRhash@@@LKRhash@@CA?B_KPEBX@Z; LKRhash::CTypedHashTable<CNoRefHashTable,URL_HASH_ENTRY,char const *,LKRhash::CLKRHashTable>::_ExtractKey(void const *)
0x18000b174  mov     r8, rax
0x18000b177  lea     rdx, [rbp+arg_10]
0x18000b17b  mov     rcx, [rax]
0x18000b17e  mov     rax, [rcx+48h]
0x18000b182  mov     rcx, r8
0x18000b185  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b18a  test    eax, eax
0x18000b18c  jnz     short loc_18000B1CB
0x18000b18e  lea     r8, [rbp+Block]
0x18000b192  mov     [rbp+Block], 0
0x18000b19a  lea     rdx, [rbp+arg_10]
0x18000b19e  lea     rcx, aDddUdn_0; "ddd:UDN"
0x18000b1a5  call    ?HrSelectNodeText@@YAJPEBGAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEAVCUString@@@Z; HrSelectNodeText(ushort const *,SmartComPtr<IXMLDOMNode> &,CUString &)
0x18000b1aa  mov     ebx, eax
0x18000b1ac  test    eax, eax
0x18000b1ae  jns     short loc_18000B1E2
0x18000b1b0  mov     rcx, [rbp+Block]; Block
0x18000b1b4  call    cs:__imp_free
0x18000b1bb  nop     dword ptr [rax+rax+00h]
0x18000b1c0  lea     rcx, [rbp+arg_10]
0x18000b1c4  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x18000b1c9  jmp     short loc_18000B15E
0x18000b1cb  lea     rcx, [rbp+arg_10]
0x18000b1cf  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x18000b1d4  lea     rcx, [rbp+var_10]
0x18000b1d8  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x18000b1dd  jmp     loc_18000B11A
0x18000b1e2  lea     rcx, [rbp+var_20]; void *
0x18000b1e6  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x18000b1eb  lea     r8, [rbp+var_20]
0x18000b1ef  lea     rdx, [rbp+arg_10]
0x18000b1f3  lea     rcx, aDddServicelist_0; "ddd:serviceList/ddd:service"
0x18000b1fa  call    ?HrSelectNodes@@YAJPEBGAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEAV?$SmartComPtr@UIXMLDOMNodeList@@@@@Z; HrSelectNodes(ushort const *,SmartComPtr<IXMLDOMNode> &,SmartComPtr<IXMLDOMNodeList> &)
0x18000b1ff  mov     ebx, eax
0x18000b201  test    eax, eax
0x18000b203  jns     short loc_18000B210
0x18000b205  lea     rcx, [rbp+var_20]
0x18000b209  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x18000b20e  jmp     short loc_18000B1B0
0x18000b210  test    ebx, ebx
0x18000b212  js      short loc_18000B205
0x18000b214  lea     rcx, [rbp+arg_18]; void *
0x18000b218  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x18000b21d  lea     rcx, [rbp+var_20]
0x18000b221  call    ?_ExtractKey@?$CTypedHashTable@VCNoRefHashTable@@VURL_HASH_ENTRY@@PEBDVCLKRHashTable@LKRhash@@@LKRhash@@CA?B_KPEBX@Z; LKRhash::CTypedHashTable<CNoRefHashTable,URL_HASH_ENTRY,char const *,LKRhash::CLKRHashTable>::_ExtractKey(void const *)
0x18000b226  mov     r8, rax
0x18000b229  lea     rdx, [rbp+arg_18]
0x18000b22d  mov     rcx, [rax]
0x18000b230  mov     rax, [rcx+48h]
0x18000b234  mov     rcx, r8
0x18000b237  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b23c  lea     rcx, [rbp+arg_18]
0x18000b240  test    eax, eax
0x18000b242  jnz     short loc_18000B281
0x18000b244  xor     r8d, r8d
0x18000b247  lea     rdx, [rbp+Block]
0x18000b24b  call    ?HrRegisterServiceWithEventing@@YAJAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEBVCUString@@H@Z; HrRegisterServiceWithEventing(SmartComPtr<IXMLDOMNode> &,CUString const &,int)
0x18000b250  lea     rcx, [rbp+arg_18]
0x18000b254  mov     ebx, eax
0x18000b256  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x18000b25b  jmp     short loc_18000B210
0x18000b25d  test    byte ptr [rcx+1Ch], 40h
0x18000b261  jz      loc_18000B0FC
0x18000b267  mov     rcx, [rcx+10h]
0x18000b26b  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x18000b272  mov     edx, 5Ah ; 'Z'
0x18000b277  call    WPP_SF_
0x18000b27c  jmp     loc_18000B0FC
0x18000b281  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x18000b286  jmp     loc_18000B205
0x18000b28b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b292  cmp     rcx, rsi
0x18000b295  jz      loc_18000B122
0x18000b29b  test    byte ptr [rcx+1Ch], 1
0x18000b29f  jz      loc_18000B122
0x18000b2a5  mov     rcx, [rcx+10h]
0x18000b2a9  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x18000b2b0  mov     edx, 5Bh ; '['
0x18000b2b5  mov     r9d, ebx
0x18000b2b8  call    WPP_SF_d
0x18000b2bd  jmp     loc_18000B122
```
