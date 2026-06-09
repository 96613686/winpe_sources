# CUWFCspNextSessionNode::Add(IConfigManager2URI *,ConfigDataType,tagVARIANT,ICSPNode * *,ulong *)

- ea: `0x18000e610`
- end: `0x18000e8ce`
- name: `?Add@CUWFCspNextSessionNode@@UEAAJPEAUIConfigManager2URI@@W4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAK@Z`
- size: `702`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int128 *, struct ICSPNode **, unsigned int *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000745c`
- `0x180007b90`
- `0x180007fc4`
- `0x18000b4dc`
- `0x18000b61c`
- `0x18000e610`
- `0x18000e9f0`
- `0x1800198d0`
- `0x180019d6c`
- `0x18001a210`
- `0x18001b010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000e6a8`
- `OLEAUT32!__imp_VariantInit` at `0x18000e6a8`
- `uwfcfgmgmt!UwfCfgAddRegExclusion` at `0x18000e855`
- `uwfcfgmgmt!UwfCfgAddRegExclusion` at `0x18000e855`
- `uwfcfgmgmt!UwfCfgAddFileExclusion` at `0x18000e7f6`
- `uwfcfgmgmt!UwfCfgAddFileExclusion` at `0x18000e7f6`
- `uwfcfgmgmt!UwfCfgAddVolume` at `0x18000e824`
- `uwfcfgmgmt!UwfCfgAddVolume` at `0x18000e824`

## pseudocode

```c
__int64 __fastcall CUWFCspNextSessionNode::Add(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int128 *a4,
        struct ICSPNode **a5,
        unsigned int *a6)
{
  int NodeInstance; // ebx
  const struct CspNodeMapBase *v11; // rcx
  const struct CSP_NODE_DATA *NodeMapEntryForURI; // rax
  __int64 v13; // xmm1_8
  int v14; // eax
  struct IConfigManager2URI *v16; // [rsp+30h] [rbp-D0h] BYREF
  const unsigned __int16 *v17; // [rsp+38h] [rbp-C8h] BYREF
  const unsigned __int16 *v18; // [rsp+40h] [rbp-C0h] BYREF
  const unsigned __int16 *v19; // [rsp+48h] [rbp-B8h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v21; // [rsp+70h] [rbp-90h] BYREF
  __int64 v22; // [rsp+80h] [rbp-80h]
  _QWORD v23[42]; // [rsp+90h] [rbp-70h] BYREF

  wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((__int64)v23);
  v23[0] = &UwfTraceLoggingProvider<2>::ConfigurationActivity::`vftable';
  UwfTraceLoggingProvider<2>::ConfigurationActivity::StartActivity(v23, L"UWFCspNextSessionNodeAdd");
  v16 = 0;
  v17 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v19 = 0;
  v18 = 0;
  VariantInit(&pvarg);
  if ( a2 && a5 && a6 )
  {
    *a5 = 0;
    *a6 = 0;
    NodeInstance = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, struct IConfigManager2URI **))(**(_QWORD **)(a1 + 24) + 168LL))(
                     *(_QWORD *)(a1 + 24),
                     a2,
                     0,
                     0,
                     &v16);
    if ( NodeInstance < 0 )
      goto LABEL_22;
    v11 = *(const struct CspNodeMapBase **)(*(_QWORD *)(a1 + 16) + 32LL);
    if ( v11 && (NodeMapEntryForURI = CspGetNodeMapEntryForURI(v11, v16)) != 0 )
    {
      NodeInstance = CUWFCspNextSessionNode::CreateNodeInstance(
                       *(struct CConfigServiceProvider2Impl **)(a1 + 16),
                       v16,
                       NodeMapEntryForURI,
                       1,
                       a5,
                       a6);
      if ( NodeInstance < 0 )
        goto LABEL_22;
      switch ( *(_DWORD *)(a1 + 44) )
      {
        case '%':
          NodeInstance = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, __int64, const unsigned __int16 **))(*(_QWORD *)v16 + 88LL))(
                           v16,
                           3,
                           &v19);
          if ( NodeInstance >= 0 )
          {
            v14 = UwfCfgAddRegExclusion(v19);
            goto LABEL_12;
          }
          break;
        case '*':
          NodeInstance = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, __int64, const unsigned __int16 **))(*(_QWORD *)v16 + 88LL))(
                           v16,
                           3,
                           &v17);
          if ( NodeInstance >= 0 )
          {
            v14 = UwfCfgAddVolume(v17);
            goto LABEL_12;
          }
          break;
        case '0':
          NodeInstance = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, __int64, const unsigned __int16 **))(*(_QWORD *)v16 + 88LL))(
                           v16,
                           3,
                           &v17);
          if ( NodeInstance >= 0 )
          {
            NodeInstance = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, __int64, const unsigned __int16 **))(*(_QWORD *)v16 + 88LL))(
                             v16,
                             5,
                             &v18);
            if ( NodeInstance >= 0 )
            {
              v14 = UwfCfgAddFileExclusion(v17, v18);
              goto LABEL_12;
            }
          }
          break;
        default:
          v13 = *((_QWORD *)a4 + 2);
          v21 = *a4;
          v22 = v13;
          v14 = CCSPNodeImpl::Add(a1, a2, a3, (__int64)&v21, a5, a6);
LABEL_12:
          NodeInstance = v14;
          break;
      }
    }
    else
    {
      NodeInstance = -2046820335;
    }
  }
  else
  {
    NodeInstance = -2147024809;
  }
LABEL_22:
  wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
    v23,
    (unsigned int)NodeInstance);
  UwfTraceLoggingProvider<2>::ConfigurationActivity::Stop<unsigned long>((__int64)v23, *(_DWORD *)(a1 + 44));
  if ( v16 )
    (*(void (__fastcall **)(struct IConfigManager2URI *))(*(_QWORD *)v16 + 16LL))(v16);
  UwfTraceLoggingProvider<2>::ConfigurationActivity::~ConfigurationActivity(v23);
  return (unsigned int)NodeInstance;
}

```

## disassembly

```asm
0x18000e610  mov     [rsp-8+arg_10], rbx
0x18000e615  push    rbp
0x18000e616  push    rsi
0x18000e617  push    rdi
0x18000e618  push    r12
0x18000e61a  push    r13
0x18000e61c  push    r14
0x18000e61e  push    r15
0x18000e620  lea     rbp, [rsp-0F0h]
0x18000e628  sub     rsp, 1F0h
0x18000e62f  mov     rax, cs:__security_cookie
0x18000e636  xor     rax, rsp
0x18000e639  mov     [rbp+120h+var_40], rax
0x18000e640  mov     rsi, [rbp+120h+arg_20]
0x18000e647  mov     rdi, rcx
0x18000e64a  mov     r14, [rbp+120h+arg_28]
0x18000e651  lea     rcx, [rbp+120h+var_190]
0x18000e655  mov     r12, r9
0x18000e658  mov     r13d, r8d
0x18000e65b  mov     r15, rdx
0x18000e65e  call    ??0?$ActivityBase@V?$UwfTraceLoggingProvider@$01@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000e663  lea     rax, ??_7ConfigurationActivity@?$UwfTraceLoggingProvider@$01@@6B@; const UwfTraceLoggingProvider<2>::ConfigurationActivity::`vftable'
0x18000e66a  lea     rdx, aUwfcspnextsess_0; "UWFCspNextSessionNodeAdd"
0x18000e671  mov     [rbp+120h+var_190], rax
0x18000e675  lea     rcx, [rbp+120h+var_190]
0x18000e679  call    ?StartActivity@ConfigurationActivity@?$UwfTraceLoggingProvider@$01@@QEAAXPEBG@Z; UwfTraceLoggingProvider<2>::ConfigurationActivity::StartActivity(ushort const *)
0x18000e67e  xor     ebx, ebx
0x18000e680  lea     rcx, [rsp+220h+pvarg]; pvarg
0x18000e685  xorps   xmm0, xmm0
0x18000e688  mov     [rsp+220h+var_1F0], rbx
0x18000e68d  xor     eax, eax
0x18000e68f  mov     [rsp+220h+var_1E8], rbx
0x18000e694  movups  xmmword ptr [rsp+220h+pvarg], xmm0
0x18000e699  mov     qword ptr [rsp+220h+pvarg+10h], rax
0x18000e69e  mov     [rsp+220h+var_1D8], rbx
0x18000e6a3  mov     [rsp+220h+var_1E0], rbx
0x18000e6a8  call    cs:__imp_VariantInit
0x18000e6ae  test    r15, r15
0x18000e6b1  jz      loc_18000E867
0x18000e6b7  test    rsi, rsi
0x18000e6ba  jz      loc_18000E867
0x18000e6c0  test    r14, r14
0x18000e6c3  jz      loc_18000E867
0x18000e6c9  mov     [rsi], rbx
0x18000e6cc  lea     rdx, [rsp+220h+var_1F0]
0x18000e6d1  mov     [r14], ebx
0x18000e6d4  xor     r9d, r9d
0x18000e6d7  mov     rcx, [rdi+18h]
0x18000e6db  xor     r8d, r8d
0x18000e6de  mov     [rsp+220h+var_200], rdx
0x18000e6e3  mov     rdx, r15
0x18000e6e6  mov     rax, [rcx]
0x18000e6e9  mov     rax, [rax+0A8h]
0x18000e6f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6f5  mov     ebx, eax
0x18000e6f7  test    eax, eax
0x18000e6f9  js      loc_18000E86C
0x18000e6ff  mov     rax, [rdi+10h]
0x18000e703  mov     rcx, [rax+20h]; struct CspNodeMapBase *
0x18000e707  test    rcx, rcx
0x18000e70a  jz      loc_18000E860
0x18000e710  mov     rdx, [rsp+220h+var_1F0]; struct IConfigManager2URI *
0x18000e715  call    ?CspGetNodeMapEntryForURI@@YAPEBUCSP_NODEMAP_ENTRY@@PEBVCspNodeMapBase@@PEAUIConfigManager2URI@@@Z; CspGetNodeMapEntryForURI(CspNodeMapBase const *,IConfigManager2URI *)
0x18000e71a  test    rax, rax
0x18000e71d  jz      loc_18000E860
0x18000e723  mov     rdx, [rsp+220h+var_1F0]; struct IConfigManager2URI *
0x18000e728  mov     r9d, 1; int
0x18000e72e  mov     rcx, [rdi+10h]; struct CConfigServiceProvider2Impl *
0x18000e732  mov     r8, rax; struct CSP_NODE_DATA *
0x18000e735  mov     [rsp+220h+var_1F8], r14; unsigned int *
0x18000e73a  mov     [rsp+220h+var_200], rsi; struct ICSPNode **
0x18000e73f  call    ?CreateNodeInstance@CUWFCspNextSessionNode@@SAJPEAVCConfigServiceProvider2Impl@@PEAUIConfigManager2URI@@PEBUCSP_NODE_DATA@@HPEAPEAUICSPNode@@PEAK@Z; CUWFCspNextSessionNode::CreateNodeInstance(CConfigServiceProvider2Impl *,IConfigManager2URI *,CSP_NODE_DATA const *,int,ICSPNode * *,ulong *)
0x18000e744  mov     ebx, eax
0x18000e746  test    eax, eax
0x18000e748  js      loc_18000E86C
0x18000e74e  cmp     dword ptr [rdi+2Ch], 25h ; '%'
0x18000e752  jz      loc_18000E82F
0x18000e758  cmp     dword ptr [rdi+2Ch], 2Ah ; '*'
0x18000e75c  jz      loc_18000E7FE
0x18000e762  cmp     dword ptr [rdi+2Ch], 30h ; '0'
0x18000e766  jz      short loc_18000E7A2
0x18000e768  movups  xmm0, xmmword ptr [r12]
0x18000e76d  lea     r9, [rsp+220h+var_1B0]
0x18000e772  mov     [rsp+220h+var_1F8], r14
0x18000e777  movsd   xmm1, qword ptr [r12+10h]
0x18000e77e  mov     r8d, r13d
0x18000e781  mov     rdx, r15
0x18000e784  movaps  [rsp+220h+var_1B0], xmm0
0x18000e789  mov     rcx, rdi
0x18000e78c  movsd   [rbp+120h+var_1A0], xmm1
0x18000e791  mov     [rsp+220h+var_200], rsi
0x18000e796  call    ?Add@CCSPNodeImpl@@UEAAJPEAUIConfigManager2URI@@W4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAK@Z; CCSPNodeImpl::Add(IConfigManager2URI *,ConfigDataType,tagVARIANT,ICSPNode * *,ulong *)
0x18000e79b  mov     ebx, eax
0x18000e79d  jmp     loc_18000E86C
0x18000e7a2  mov     rcx, [rsp+220h+var_1F0]
0x18000e7a7  lea     r8, [rsp+220h+var_1E8]
0x18000e7ac  mov     edx, 3
0x18000e7b1  mov     rax, [rcx]
0x18000e7b4  mov     rax, [rax+58h]
0x18000e7b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7bd  mov     ebx, eax
0x18000e7bf  test    eax, eax
0x18000e7c1  js      loc_18000E86C
0x18000e7c7  mov     rcx, [rsp+220h+var_1F0]
0x18000e7cc  lea     r8, [rsp+220h+var_1E0]
0x18000e7d1  mov     edx, 5
0x18000e7d6  mov     rax, [rcx]
0x18000e7d9  mov     rax, [rax+58h]
0x18000e7dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7e2  mov     ebx, eax
0x18000e7e4  test    eax, eax
0x18000e7e6  js      loc_18000E86C
0x18000e7ec  mov     rdx, [rsp+220h+var_1E0]
0x18000e7f1  mov     rcx, [rsp+220h+var_1E8]
0x18000e7f6  call    cs:__imp_?UwfCfgAddFileExclusion@@YAJPEBG0@Z; UwfCfgAddFileExclusion(ushort const *,ushort const *)
0x18000e7fc  jmp     short loc_18000E79B
0x18000e7fe  mov     rcx, [rsp+220h+var_1F0]
0x18000e803  lea     r8, [rsp+220h+var_1E8]
0x18000e808  mov     edx, 3
0x18000e80d  mov     rax, [rcx]
0x18000e810  mov     rax, [rax+58h]
0x18000e814  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e819  mov     ebx, eax
0x18000e81b  test    eax, eax
0x18000e81d  js      short loc_18000E86C
0x18000e81f  mov     rcx, [rsp+220h+var_1E8]
0x18000e824  call    cs:__imp_?UwfCfgAddVolume@@YAJPEBG@Z; UwfCfgAddVolume(ushort const *)
0x18000e82a  jmp     loc_18000E79B
0x18000e82f  mov     rcx, [rsp+220h+var_1F0]
0x18000e834  lea     r8, [rsp+220h+var_1D8]
0x18000e839  mov     edx, 3
0x18000e83e  mov     rax, [rcx]
0x18000e841  mov     rax, [rax+58h]
0x18000e845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e84a  mov     ebx, eax
0x18000e84c  test    eax, eax
0x18000e84e  js      short loc_18000E86C
0x18000e850  mov     rcx, [rsp+220h+var_1D8]
0x18000e855  call    cs:__imp_?UwfCfgAddRegExclusion@@YAJPEBG@Z; UwfCfgAddRegExclusion(ushort const *)
0x18000e85b  jmp     loc_18000E79B
0x18000e860  mov     ebx, 86000011h
0x18000e865  jmp     short loc_18000E86C
0x18000e867  mov     ebx, 80070057h
0x18000e86c  mov     edx, ebx
0x18000e86e  lea     rcx, [rbp+120h+var_190]
0x18000e872  call    ?SetStopResult@?$ActivityBase@V?$UwfTraceLoggingProvider@$01@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXJPEAJ@Z; wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x18000e877  mov     edx, [rdi+2Ch]
0x18000e87a  lea     rcx, [rbp+120h+var_190]
0x18000e87e  call    ??$Stop@K@ConfigurationActivity@?$UwfTraceLoggingProvider@$01@@QEAAXK@Z; UwfTraceLoggingProvider<2>::ConfigurationActivity::Stop<ulong>(ulong)
0x18000e883  mov     rcx, [rsp+220h+var_1F0]
0x18000e888  test    rcx, rcx
0x18000e88b  jz      short loc_18000E899
0x18000e88d  mov     rax, [rcx]
0x18000e890  mov     rax, [rax+10h]
0x18000e894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e899  lea     rcx, [rbp+120h+var_190]
0x18000e89d  call    ??1ConfigurationActivity@?$UwfTraceLoggingProvider@$01@@QEAA@XZ; UwfTraceLoggingProvider<2>::ConfigurationActivity::~ConfigurationActivity(void)
0x18000e8a2  mov     eax, ebx
0x18000e8a4  mov     rcx, [rbp+120h+var_40]
0x18000e8ab  xor     rcx, rsp; StackCookie
0x18000e8ae  call    __security_check_cookie
0x18000e8b3  mov     rbx, [rsp+220h+arg_10]
0x18000e8bb  add     rsp, 1F0h
0x18000e8c2  pop     r15
0x18000e8c4  pop     r14
0x18000e8c6  pop     r13
0x18000e8c8  pop     r12
0x18000e8ca  pop     rdi
0x18000e8cb  pop     rsi
0x18000e8cc  pop     rbp
0x18000e8cd  retn
```
