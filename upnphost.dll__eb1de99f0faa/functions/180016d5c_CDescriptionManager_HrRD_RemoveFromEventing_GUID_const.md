# CDescriptionManager::HrRD_RemoveFromEventing(_GUID const &)

- ea: `0x180016d5c`
- end: `0x180016f47`
- name: `?HrRD_RemoveFromEventing@CDescriptionManager@@AEAAJAEBU_GUID@@@Z`
- size: `491`
- prototype: `__int64 __fastcall(CDescriptionManager *__hidden this, const struct _GUID *)`
- caller_count: `4`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000f750`
- `0x18001b060`
- `0x18001c410`
- `0x18001d4b0`

## callees

- `0x18001169c`
- `0x1800117bc`
- `0x1800117d0`
- `0x180013cb4`
- `0x180015ab0`
- `0x180016d5c`
- `0x180025330`
- `0x180030c30`
- `0x180038ce4`
- `0x180039a84`
- `0x180055010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180016e3f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180016e3f`

## string_xrefs

- `0x180016e78`: `ddd:serviceList/ddd:service`

## pseudocode

```c
__int64 __fastcall CDescriptionManager::HrRD_RemoveFromEventing(CDescriptionManager *this, const struct _GUID *a2)
{
  int v4; // ebx
  __int64 Key; // rax
  __int64 v7; // rax
  __int64 v8; // [rsp+20h] [rbp-20h] BYREF
  void *Block; // [rsp+28h] [rbp-18h] BYREF
  __int64 v10; // [rsp+30h] [rbp-10h] BYREF
  __int64 v11; // [rsp+38h] [rbp-8h] BYREF
  __int64 v12; // [rsp+70h] [rbp+30h] BYREF
  __int64 v13; // [rsp+78h] [rbp+38h] BYREF

  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids);
  SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(&v11);
  v4 = CDescriptionManager::HrLoadDocumentAndRootNode(this, a2, &v11);
  if ( v4 >= 0 )
  {
    SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(&v10);
    v4 = HrSelectNodes(L"//ddd:device", &v11, &v10);
    if ( v4 >= 0 )
    {
      while ( v4 >= 0 )
      {
        SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(&v12);
        Key = LKRhash::CTypedHashTable<CNoRefHashTable,URL_HASH_ENTRY,char const *,LKRhash::CLKRHashTable>::_ExtractKey((__int64)&v10);
        if ( (*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)Key + 72LL))(Key, &v12) )
        {
          ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>((__int64)&v12);
          break;
        }
        Block = 0;
        v4 = HrSelectNodeText((OLECHAR *)L"ddd:UDN");
        if ( v4 >= 0 )
        {
          SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(&v8);
          v4 = HrSelectNodes(L"ddd:serviceList/ddd:service", &v12, &v8);
          if ( v4 >= 0 )
          {
            while ( v4 >= 0 )
            {
              SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(&v13);
              v7 = LKRhash::CTypedHashTable<CNoRefHashTable,URL_HASH_ENTRY,char const *,LKRhash::CLKRHashTable>::_ExtractKey((__int64)&v8);
              if ( (*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v7 + 72LL))(v7, &v13) )
              {
                ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>((__int64)&v13);
                break;
              }
              v4 = HrRegisterServiceWithEventing(&v13, &Block, 0);
              ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>((__int64)&v13);
            }
          }
          ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>((__int64)&v8);
        }
        free(Block);
        ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>((__int64)&v12);
      }
    }
    ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>((__int64)&v10);
  }
  if ( v4 && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids, (unsigned int)v4);
  ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>((__int64)&v11);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180016d5c  mov     [rsp-18h+arg_0], rbx
0x180016d61  push    rbp
0x180016d62  push    rsi
0x180016d63  push    rdi
0x180016d64  mov     rbp, rsp
0x180016d67  sub     rsp, 40h
0x180016d6b  mov     rbx, rdx
0x180016d6e  mov     rdi, rcx
0x180016d71  mov     rcx, cs:WPP_GLOBAL_Control
0x180016d78  lea     rsi, WPP_GLOBAL_Control
0x180016d7f  cmp     rcx, rsi
0x180016d82  jnz     loc_180016EE2
0x180016d88  lea     rcx, [rbp+var_8]; void *
0x180016d8c  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x180016d91  lea     r8, [rbp+var_8]
0x180016d95  mov     rdx, rbx
0x180016d98  mov     rcx, rdi
0x180016d9b  call    ?HrLoadDocumentAndRootNode@CDescriptionManager@@AEAAJAEBU_GUID@@AEAV?$SmartComPtr@UIXMLDOMNode@@@@@Z; CDescriptionManager::HrLoadDocumentAndRootNode(_GUID const &,SmartComPtr<IXMLDOMNode> &)
0x180016da0  mov     ebx, eax
0x180016da2  test    eax, eax
0x180016da4  jns     short loc_180016DC6
0x180016da6  test    ebx, ebx
0x180016da8  jnz     loc_180016F10
0x180016dae  lea     rcx, [rbp+var_8]
0x180016db2  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x180016db7  mov     eax, ebx
0x180016db9  mov     rbx, [rsp+40h+arg_0]
0x180016dbe  add     rsp, 40h
0x180016dc2  pop     rdi
0x180016dc3  pop     rsi
0x180016dc4  pop     rbp
0x180016dc5  retn
0x180016dc6  lea     rcx, [rbp+var_10]; void *
0x180016dca  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x180016dcf  lea     r8, [rbp+var_10]
0x180016dd3  lea     rdx, [rbp+var_8]
0x180016dd7  lea     rcx, aDddDevice; "//ddd:device"
0x180016dde  call    ?HrSelectNodes@@YAJPEBGAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEAV?$SmartComPtr@UIXMLDOMNodeList@@@@@Z; HrSelectNodes(ushort const *,SmartComPtr<IXMLDOMNode> &,SmartComPtr<IXMLDOMNodeList> &)
0x180016de3  mov     ebx, eax
0x180016de5  test    eax, eax
0x180016de7  js      short loc_180016E59
0x180016de9  test    ebx, ebx
0x180016deb  js      short loc_180016E59
0x180016ded  lea     rcx, [rbp+arg_10]; void *
0x180016df1  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x180016df6  lea     rcx, [rbp+var_10]
0x180016dfa  call    ?_ExtractKey@?$CTypedHashTable@VCNoRefHashTable@@VURL_HASH_ENTRY@@PEBDVCLKRHashTable@LKRhash@@@LKRhash@@CA?B_KPEBX@Z; LKRhash::CTypedHashTable<CNoRefHashTable,URL_HASH_ENTRY,char const *,LKRhash::CLKRHashTable>::_ExtractKey(void const *)
0x180016dff  mov     r8, rax
0x180016e02  lea     rdx, [rbp+arg_10]
0x180016e06  mov     rcx, [rax]
0x180016e09  mov     rax, [rcx+48h]
0x180016e0d  mov     rcx, r8
0x180016e10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e15  test    eax, eax
0x180016e17  jnz     short loc_180016E50
0x180016e19  lea     r8, [rbp+Block]
0x180016e1d  mov     [rbp+Block], 0
0x180016e25  lea     rdx, [rbp+arg_10]
0x180016e29  lea     rcx, aDddUdn_0; "ddd:UDN"
0x180016e30  call    ?HrSelectNodeText@@YAJPEBGAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEAVCUString@@@Z; HrSelectNodeText(ushort const *,SmartComPtr<IXMLDOMNode> &,CUString &)
0x180016e35  mov     ebx, eax
0x180016e37  test    eax, eax
0x180016e39  jns     short loc_180016E67
0x180016e3b  mov     rcx, [rbp+Block]; Block
0x180016e3f  call    cs:__imp_free
0x180016e45  lea     rcx, [rbp+arg_10]
0x180016e49  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x180016e4e  jmp     short loc_180016DE9
0x180016e50  lea     rcx, [rbp+arg_10]
0x180016e54  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x180016e59  lea     rcx, [rbp+var_10]
0x180016e5d  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x180016e62  jmp     loc_180016DA6
0x180016e67  lea     rcx, [rbp+var_20]; void *
0x180016e6b  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x180016e70  lea     r8, [rbp+var_20]
0x180016e74  lea     rdx, [rbp+arg_10]
0x180016e78  lea     rcx, aDddServicelist_0; "ddd:serviceList/ddd:service"
0x180016e7f  call    ?HrSelectNodes@@YAJPEBGAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEAV?$SmartComPtr@UIXMLDOMNodeList@@@@@Z; HrSelectNodes(ushort const *,SmartComPtr<IXMLDOMNode> &,SmartComPtr<IXMLDOMNodeList> &)
0x180016e84  mov     ebx, eax
0x180016e86  test    eax, eax
0x180016e88  jns     short loc_180016E95
0x180016e8a  lea     rcx, [rbp+var_20]
0x180016e8e  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x180016e93  jmp     short loc_180016E3B
0x180016e95  test    ebx, ebx
0x180016e97  js      short loc_180016E8A
0x180016e99  lea     rcx, [rbp+arg_18]; void *
0x180016e9d  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x180016ea2  lea     rcx, [rbp+var_20]
0x180016ea6  call    ?_ExtractKey@?$CTypedHashTable@VCNoRefHashTable@@VURL_HASH_ENTRY@@PEBDVCLKRHashTable@LKRhash@@@LKRhash@@CA?B_KPEBX@Z; LKRhash::CTypedHashTable<CNoRefHashTable,URL_HASH_ENTRY,char const *,LKRhash::CLKRHashTable>::_ExtractKey(void const *)
0x180016eab  mov     r8, rax
0x180016eae  lea     rdx, [rbp+arg_18]
0x180016eb2  mov     rcx, [rax]
0x180016eb5  mov     rax, [rcx+48h]
0x180016eb9  mov     rcx, r8
0x180016ebc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ec1  lea     rcx, [rbp+arg_18]
0x180016ec5  test    eax, eax
0x180016ec7  jnz     short loc_180016F06
0x180016ec9  xor     r8d, r8d
0x180016ecc  lea     rdx, [rbp+Block]
0x180016ed0  call    ?HrRegisterServiceWithEventing@@YAJAEAV?$SmartComPtr@UIXMLDOMNode@@@@AEBVCUString@@H@Z; HrRegisterServiceWithEventing(SmartComPtr<IXMLDOMNode> &,CUString const &,int)
0x180016ed5  lea     rcx, [rbp+arg_18]
0x180016ed9  mov     ebx, eax
0x180016edb  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x180016ee0  jmp     short loc_180016E95
0x180016ee2  test    byte ptr [rcx+1Ch], 40h
0x180016ee6  jz      loc_180016D88
0x180016eec  mov     rcx, [rcx+10h]
0x180016ef0  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x180016ef7  mov     edx, 5Ah ; 'Z'
0x180016efc  call    WPP_SF_
0x180016f01  jmp     loc_180016D88
0x180016f06  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x180016f0b  jmp     loc_180016E8A
0x180016f10  mov     rcx, cs:WPP_GLOBAL_Control
0x180016f17  cmp     rcx, rsi
0x180016f1a  jz      loc_180016DAE
0x180016f20  test    byte ptr [rcx+1Ch], 1
0x180016f24  jz      loc_180016DAE
0x180016f2a  mov     rcx, [rcx+10h]
0x180016f2e  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x180016f35  mov     edx, 5Bh ; '['
0x180016f3a  mov     r9d, ebx
0x180016f3d  call    WPP_SF_d
0x180016f42  jmp     loc_180016DAE
```
