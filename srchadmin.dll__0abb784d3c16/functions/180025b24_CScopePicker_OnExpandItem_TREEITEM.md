# CScopePicker::_OnExpandItem(_TREEITEM *)

- ea: `0x180025b24`
- end: `0x180025e32`
- name: `?_OnExpandItem@CScopePicker@@AEAAJPEAU_TREEITEM@@@Z`
- size: `782`
- prototype: `__int64 __fastcall(HWND *this, struct _TREEITEM *)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002506c`
- `0x1800263bc`

## callees

- `0x1800038ac`
- `0x18000420c`
- `0x18000dd40`
- `0x180016ccc`
- `0x180024950`
- `0x1800251d0`
- `0x1800253d0`
- `0x1800254e0`
- `0x180025b24`
- `0x180026c70`
- `0x18002cc10`
- `0x18002d2f0`
- `0x18002d3a0`
- `0x18002d918`
- `0x180032010`

## import_xrefs

- `SHELL32!__imp_ILFree` at `0x180025beb`
- `SHELL32!__imp_ILFree` at `0x180025beb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025ced`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025cfb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025dce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025ced`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025cfb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025dce`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180025b71`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180025e09`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180025b71`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180025e09`

## pseudocode

```c
__int64 __fastcall CScopePicker::_OnExpandItem(HWND *this, struct _TREEITEM *a2)
{
  int v4; // edi
  CScopePicker *v5; // rcx
  int PidlAbs; // ebx
  int IsUNCDisabledPolicy; // r12d
  CShellWrappers *v8; // rcx
  CShellWrappers *v9; // rcx
  unsigned int v10; // r15d
  CShellWrappers *v11; // rcx
  int PathFromChildPidl; // eax
  __int64 v13; // rcx
  void *v14; // rbx
  unsigned __int16 *v15; // rdi
  CScopePicker *v16; // rcx
  int v17; // ebx
  struct IShellFolder *v19; // [rsp+50h] [rbp-29h] BYREF
  struct _ITEMID_CHILD *v20; // [rsp+58h] [rbp-21h] BYREF
  __int64 v21; // [rsp+60h] [rbp-19h] BYREF
  LPARAM lParam[2]; // [rsp+68h] [rbp-11h] BYREF
  __int128 v23; // [rsp+78h] [rbp-1h]
  __int128 v24; // [rsp+88h] [rbp+Fh]
  __int64 v25; // [rsp+98h] [rbp+1Fh]
  LPITEMIDLIST pidl; // [rsp+E0h] [rbp+67h] BYREF
  LPVOID pv; // [rsp+E8h] [rbp+6Fh] BYREF
  enum __MIDL___MIDL_itf_searchapi_0000_0013_0001 v28; // [rsp+F0h] [rbp+77h] BYREF
  int v29; // [rsp+F8h] [rbp+7Fh] BYREF

  v23 = 0;
  v24 = 0;
  v25 = 0;
  lParam[1] = (LPARAM)a2;
  lParam[0] = 84;
  if ( !(unsigned int)SendMessageW(this[3], 0x113Eu, 0, (LPARAM)lParam) )
    return (unsigned int)-2147024809;
  if ( !v25 )
    return (unsigned int)-2147024883;
  v4 = 0;
  if ( HIDWORD(v24) != 1 || *(_DWORD *)(v25 + 16) )
  {
LABEL_37:
    SendMessageW(this[3], 0x1113u, 0, (LPARAM)a2);
    return (unsigned int)v4;
  }
  *(_DWORD *)(v25 + 16) = 1;
  v19 = 0;
  pidl = 0;
  PidlAbs = CScopePicker::_GetPidlAbs(this, a2, &pidl);
  if ( PidlAbs >= 0 )
  {
    PidlAbs = CShellWrappers::GetParentFolderFromAbsPidl(
                (CShellWrappers *)(this + 218),
                (const struct _ITEMIDLIST_ABSOLUTE *)pidl,
                &v19);
    ILFree(pidl);
  }
  v21 = 0;
  if ( !PidlAbs )
    PidlAbs = ((__int64 (__fastcall *)(struct IShellFolder *, _QWORD, _QWORD, __int64 *))v19->lpVtbl->EnumObjects)(
                v19,
                0,
                *((unsigned int *)this + 440),
                &v21);
  IsUNCDisabledPolicy = CScopePicker::_IsUNCDisabledPolicy(v5);
  v20 = 0;
LABEL_33:
  if ( !PidlAbs )
  {
    while ( 1 )
    {
      PidlAbs = (*(__int64 (__fastcall **)(__int64, __int64, struct _ITEMID_CHILD **))(*(_QWORD *)v21 + 24LL))(
                  v21,
                  1,
                  &v20);
      if ( PidlAbs )
        break;
      LODWORD(pv) = 0;
      LODWORD(pidl) = 0;
      PidlAbs = CShellWrappers::GetAttribsFromChildPidl(v8, v19, v20, (unsigned int *)&pv, (unsigned int *)&pidl);
      v10 = (unsigned int)pv;
      if ( PidlAbs )
        goto LABEL_22;
      if ( ((unsigned __int16)pv & 0x400) == 0 )
        goto LABEL_21;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddingCloudFileCheck>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AddingCloudFileCheck>::GetImpl'::`2'::impl) )
      {
        pv = 0;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &pv,
          0);
        PathFromChildPidl = CShellWrappers::GetPathFromChildPidl(v11, v19, v20, (unsigned __int16 **)&pv, 1);
        v14 = pv;
        if ( PathFromChildPidl >= 0 && pv )
        {
          if ( !(unsigned int)CShellWrappers::IsCloudFilesPlaceholder(v13, &pv) )
            goto LABEL_19;
          CoTaskMemFree(v14);
LABEL_21:
          PidlAbs = CShellWrappers::IsDisplayableObject(v9, v19, v20, (unsigned int)pidl);
          if ( PidlAbs != 1 )
          {
LABEL_22:
            v15 = 0;
            pv = 0;
            if ( PidlAbs >= 0 )
            {
              PidlAbs = CShellWrappers::GetPathFromChildPidl(v9, v19, v20, (unsigned __int16 **)&pv, 1);
              v15 = (unsigned __int16 *)pv;
            }
            v29 = 0;
            v28 = CLUSIONREASON_UNKNOWNSCOPE;
            if ( PidlAbs >= 0 )
            {
              PidlAbs = CCrawlScopeManagerWrapper::IncludedOrNot(
                          (CCrawlScopeManagerWrapper *)(this + 415),
                          v15,
                          &v29,
                          &v28);
              if ( PidlAbs >= 0 )
              {
                if ( v28 == CLUSIONREASON_GROUPPOLICY
                  || (v17 = 0, IsUNCDisabledPolicy) && CScopePicker::_IsUNCScopeRule(v16, v15) )
                {
                  v17 = 1;
                }
                PidlAbs = CScopePicker::_Attach(
                            this,
                            a2,
                            v19,
                            (const ITEMIDLIST *)v20,
                            v29,
                            v10,
                            (unsigned int)pidl,
                            v17,
                            0);
                if ( PidlAbs < 0 )
                  PidlAbs = 0;
              }
            }
            CoTaskMemFree(v15);
            goto LABEL_33;
          }
        }
        else if ( pv )
        {
LABEL_19:
          CoTaskMemFree(v14);
        }
      }
    }
  }
  v4 = 0;
  if ( PidlAbs < 0 )
    v4 = PidlAbs;
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v21);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v19);
  if ( v4 >= 0 )
    goto LABEL_37;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180025b24  push    rbp
0x180025b26  push    rbx
0x180025b27  push    rsi
0x180025b28  push    rdi
0x180025b29  push    r12
0x180025b2b  push    r14
0x180025b2d  push    r15
0x180025b2f  lea     rbp, [rsp-27h]
0x180025b34  sub     rsp, 0A0h
0x180025b3b  mov     r14, rdx
0x180025b3e  mov     rsi, rcx
0x180025b41  xorps   xmm0, xmm0
0x180025b44  xor     eax, eax
0x180025b46  movups  xmmword ptr [rbp+57h+lParam], xmm0
0x180025b4a  movups  [rbp+57h+var_58], xmm0
0x180025b4e  movups  [rbp+57h+var_48], xmm0
0x180025b52  mov     [rbp+57h+var_38], rax
0x180025b56  mov     [rbp+57h+lParam+8], rdx
0x180025b5a  mov     dword ptr [rbp+57h+lParam], 54h ; 'T'
0x180025b61  lea     r9, [rbp+57h+lParam]; lParam
0x180025b65  xor     r8d, r8d; wParam
0x180025b68  mov     edx, 113Eh; Msg
0x180025b6d  mov     rcx, [rcx+18h]; hWnd
0x180025b71  call    cs:__imp_SendMessageW
0x180025b77  test    eax, eax
0x180025b79  jnz     short loc_180025B85
0x180025b7b  mov     edi, 80070057h
0x180025b80  jmp     loc_180025E0F
0x180025b85  mov     rax, [rbp+57h+var_38]
0x180025b89  test    rax, rax
0x180025b8c  jnz     short loc_180025B98
0x180025b8e  mov     edi, 8007000Dh
0x180025b93  jmp     loc_180025E0F
0x180025b98  xor     edi, edi
0x180025b9a  cmp     dword ptr [rbp+57h+var_48+0Ch], 1
0x180025b9e  jnz     loc_180025DFA
0x180025ba4  cmp     [rax+10h], edi
0x180025ba7  jnz     loc_180025DFA
0x180025bad  mov     dword ptr [rax+10h], 1
0x180025bb4  mov     [rbp+57h+var_80], rdi
0x180025bb8  mov     [rbp+57h+pidl], rdi
0x180025bbc  lea     r8, [rbp+57h+pidl]; struct _ITEMIDLIST_ABSOLUTE **
0x180025bc0  mov     rdx, r14; struct _TREEITEM *
0x180025bc3  mov     rcx, rsi; this
0x180025bc6  call    ?_GetPidlAbs@CScopePicker@@AEAAJPEAU_TREEITEM@@PEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z; CScopePicker::_GetPidlAbs(_TREEITEM *,_ITEMIDLIST_ABSOLUTE * *)
0x180025bcb  mov     ebx, eax
0x180025bcd  test    eax, eax
0x180025bcf  js      short loc_180025BF1
0x180025bd1  lea     rcx, [rsi+6D0h]; this
0x180025bd8  lea     r8, [rbp+57h+var_80]; struct IShellFolder **
0x180025bdc  mov     rdx, [rbp+57h+pidl]; struct _ITEMIDLIST_ABSOLUTE *
0x180025be0  call    ?GetParentFolderFromAbsPidl@CShellWrappers@@QEAAJPEBU_ITEMIDLIST_ABSOLUTE@@PEAPEAUIShellFolder@@@Z; CShellWrappers::GetParentFolderFromAbsPidl(_ITEMIDLIST_ABSOLUTE const *,IShellFolder * *)
0x180025be5  mov     ebx, eax
0x180025be7  mov     rcx, [rbp+57h+pidl]; pidl
0x180025beb  call    cs:__imp_ILFree
0x180025bf1  mov     [rbp+57h+var_70], 0
0x180025bf9  test    ebx, ebx
0x180025bfb  jnz     short loc_180025C1C
0x180025bfd  mov     rcx, [rbp+57h+var_80]
0x180025c01  mov     rax, [rcx]
0x180025c04  lea     r9, [rbp+57h+var_70]
0x180025c08  mov     r8d, [rsi+6E0h]
0x180025c0f  xor     edx, edx
0x180025c11  mov     rax, [rax+20h]
0x180025c15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c1a  mov     ebx, eax
0x180025c1c  call    ?_IsUNCDisabledPolicy@CScopePicker@@AEAAHXZ; CScopePicker::_IsUNCDisabledPolicy(void)
0x180025c21  mov     r12d, eax
0x180025c24  mov     [rbp+57h+var_78], 0
0x180025c2c  jmp     loc_180025DD4
0x180025c31  mov     rcx, [rbp+57h+var_70]
0x180025c35  mov     rdx, [rcx]
0x180025c38  mov     rax, [rdx+18h]
0x180025c3c  xor     r9d, r9d
0x180025c3f  lea     r8, [rbp+57h+var_78]
0x180025c43  lea     edx, [r9+1]
0x180025c47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c4c  mov     ebx, eax
0x180025c4e  test    eax, eax
0x180025c50  jnz     loc_180025DDC
0x180025c56  mov     dword ptr [rbp+57h+pv], eax
0x180025c59  mov     dword ptr [rbp+57h+pidl], eax
0x180025c5c  lea     rax, [rbp+57h+pidl]
0x180025c60  mov     [rsp+0D0h+var_B0], rax; unsigned int *
0x180025c65  lea     r9, [rbp+57h+pv]; unsigned int *
0x180025c69  mov     r8, [rbp+57h+var_78]; struct _ITEMID_CHILD *
0x180025c6d  mov     rdx, [rbp+57h+var_80]; struct IShellFolder *
0x180025c71  call    ?GetAttribsFromChildPidl@CShellWrappers@@QEAAJPEAUIShellFolder@@PEBU_ITEMID_CHILD@@PEAK2@Z; CShellWrappers::GetAttribsFromChildPidl(IShellFolder *,_ITEMID_CHILD const *,ulong *,ulong *)
0x180025c76  mov     ebx, eax
0x180025c78  mov     r15d, dword ptr [rbp+57h+pv]
0x180025c7c  test    eax, eax
0x180025c7e  jnz     loc_180025D1D
0x180025c84  bt      r15d, 0Ah
0x180025c89  jnb     short loc_180025D01
0x180025c8b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AddingCloudFileCheck@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AddingCloudFileCheck@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddingCloudFileCheck> `wil::Feature<__WilFeatureTraits_Feature_AddingCloudFileCheck>::GetImpl(void)'::`2'::impl
0x180025c92  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AddingCloudFileCheck@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AddingCloudFileCheck>::__private_IsEnabled(void)
0x180025c97  test    al, al
0x180025c99  jz      short loc_180025C31
0x180025c9b  mov     [rbp+57h+pv], 0
0x180025ca3  xor     edx, edx
0x180025ca5  lea     rcx, [rbp+57h+pv]
0x180025ca9  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180025cae  mov     dword ptr [rsp+0D0h+var_B0], 1; int
0x180025cb6  lea     r9, [rbp+57h+pv]; unsigned __int16 **
0x180025cba  mov     r8, [rbp+57h+var_78]; struct _ITEMID_CHILD *
0x180025cbe  mov     rdx, [rbp+57h+var_80]; struct IShellFolder *
0x180025cc2  call    ?GetPathFromChildPidl@CShellWrappers@@QEAAJPEAUIShellFolder@@PEBU_ITEMID_CHILD@@PEAPEAGH@Z; CShellWrappers::GetPathFromChildPidl(IShellFolder *,_ITEMID_CHILD const *,ushort * *,int)
0x180025cc7  mov     rbx, [rbp+57h+pv]
0x180025ccb  test    eax, eax
0x180025ccd  js      loc_180025E23
0x180025cd3  test    rbx, rbx
0x180025cd6  jz      loc_180025E23
0x180025cdc  lea     rdx, [rbp+57h+pv]
0x180025ce0  call    ?IsCloudFilesPlaceholder@CShellWrappers@@QEAAHAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; CShellWrappers::IsCloudFilesPlaceholder(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180025ce5  nop
0x180025ce6  test    eax, eax
0x180025ce8  jnz     short loc_180025CF8
0x180025cea  mov     rcx, rbx; pv
0x180025ced  call    cs:__imp_CoTaskMemFree
0x180025cf3  jmp     loc_180025C31
0x180025cf8  mov     rcx, rbx; pv
0x180025cfb  call    cs:__imp_CoTaskMemFree
0x180025d01  mov     r9d, dword ptr [rbp+57h+pidl]; unsigned int
0x180025d05  mov     r8, [rbp+57h+var_78]; struct _ITEMID_CHILD *
0x180025d09  mov     rdx, [rbp+57h+var_80]; struct IShellFolder *
0x180025d0d  call    ?IsDisplayableObject@CShellWrappers@@QEAAJPEAUIShellFolder@@PEBU_ITEMID_CHILD@@K@Z; CShellWrappers::IsDisplayableObject(IShellFolder *,_ITEMID_CHILD const *,ulong)
0x180025d12  mov     ebx, eax
0x180025d14  cmp     eax, 1
0x180025d17  jz      loc_180025C31
0x180025d1d  xor     edi, edi
0x180025d1f  mov     [rbp+57h+pv], rdi
0x180025d23  test    ebx, ebx
0x180025d25  js      short loc_180025D46
0x180025d27  mov     dword ptr [rsp+0D0h+var_B0], 1; int
0x180025d2f  lea     r9, [rbp+57h+pv]; unsigned __int16 **
0x180025d33  mov     r8, [rbp+57h+var_78]; struct _ITEMID_CHILD *
0x180025d37  mov     rdx, [rbp+57h+var_80]; struct IShellFolder *
0x180025d3b  call    ?GetPathFromChildPidl@CShellWrappers@@QEAAJPEAUIShellFolder@@PEBU_ITEMID_CHILD@@PEAPEAGH@Z; CShellWrappers::GetPathFromChildPidl(IShellFolder *,_ITEMID_CHILD const *,ushort * *,int)
0x180025d40  mov     ebx, eax
0x180025d42  mov     rdi, [rbp+57h+pv]
0x180025d46  mov     [rbp+57h+arg_18], 0
0x180025d4d  mov     [rbp+57h+arg_10], 0
0x180025d54  test    ebx, ebx
0x180025d56  js      short loc_180025DCB
0x180025d58  lea     rcx, [rsi+0CF8h]; this
0x180025d5f  lea     r9, [rbp+57h+arg_10]; enum __MIDL___MIDL_itf_searchapi_0000_0013_0001 *
0x180025d63  lea     r8, [rbp+57h+arg_18]; int *
0x180025d67  mov     rdx, rdi; unsigned __int16 *
0x180025d6a  call    ?IncludedOrNot@CCrawlScopeManagerWrapper@@QEAAJPEBGPEAHPEAW4__MIDL___MIDL_itf_searchapi_0000_0013_0001@@@Z; CCrawlScopeManagerWrapper::IncludedOrNot(ushort const *,int *,__MIDL___MIDL_itf_searchapi_0000_0013_0001 *)
0x180025d6f  mov     ebx, eax
0x180025d71  test    eax, eax
0x180025d73  js      short loc_180025DCB
0x180025d75  cmp     [rbp+57h+arg_10], 3
0x180025d79  jz      short loc_180025D8E
0x180025d7b  xor     ebx, ebx
0x180025d7d  test    r12d, r12d
0x180025d80  jz      short loc_180025D93
0x180025d82  mov     rdx, rdi; unsigned __int16 *
0x180025d85  call    ?_IsUNCScopeRule@CScopePicker@@AEAAHPEBG@Z; CScopePicker::_IsUNCScopeRule(ushort const *)
0x180025d8a  test    eax, eax
0x180025d8c  jz      short loc_180025D93
0x180025d8e  mov     ebx, 1
0x180025d93  mov     eax, dword ptr [rbp+57h+pidl]
0x180025d96  mov     edx, [rbp+57h+arg_18]
0x180025d99  mov     [rsp+0D0h+var_90], 0; bool
0x180025d9e  mov     [rsp+0D0h+var_98], ebx; int
0x180025da2  mov     [rsp+0D0h+var_A0], eax; unsigned int
0x180025da6  mov     [rsp+0D0h+var_A8], r15d; unsigned int
0x180025dab  mov     dword ptr [rsp+0D0h+var_B0], edx; int
0x180025daf  mov     r9, [rbp+57h+var_78]; struct _ITEMIDLIST_RELATIVE *
0x180025db3  mov     r8, [rbp+57h+var_80]; struct IShellFolder *
0x180025db7  mov     rdx, r14; struct _TREEITEM *
0x180025dba  mov     rcx, rsi; this
0x180025dbd  call    ?_Attach@CScopePicker@@AEAAJPEAU_TREEITEM@@PEAUIShellFolder@@PEAU_ITEMIDLIST_RELATIVE@@HKKH_N@Z; CScopePicker::_Attach(_TREEITEM *,IShellFolder *,_ITEMIDLIST_RELATIVE *,int,ulong,ulong,int,bool)
0x180025dc2  mov     ebx, eax
0x180025dc4  xor     eax, eax
0x180025dc6  test    ebx, ebx
0x180025dc8  cmovs   ebx, eax
0x180025dcb  mov     rcx, rdi; pv
0x180025dce  call    cs:__imp_CoTaskMemFree
0x180025dd4  test    ebx, ebx
0x180025dd6  jz      loc_180025C31
0x180025ddc  xor     edi, edi
0x180025dde  test    ebx, ebx
0x180025de0  cmovs   edi, ebx
0x180025de3  lea     rcx, [rbp+57h+var_70]
0x180025de7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180025dec  nop
0x180025ded  lea     rcx, [rbp+57h+var_80]
0x180025df1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180025df6  test    edi, edi
0x180025df8  js      short loc_180025E0F
0x180025dfa  mov     r9, r14; lParam
0x180025dfd  xor     r8d, r8d; wParam
0x180025e00  mov     edx, 1113h; Msg
0x180025e05  mov     rcx, [rsi+18h]; hWnd
0x180025e09  call    cs:__imp_SendMessageW
0x180025e0f  mov     eax, edi
0x180025e11  add     rsp, 0A0h
0x180025e18  pop     r15
0x180025e1a  pop     r14
0x180025e1c  pop     r12
0x180025e1e  pop     rdi
0x180025e1f  pop     rsi
0x180025e20  pop     rbx
0x180025e21  pop     rbp
0x180025e22  retn
0x180025e23  test    rbx, rbx
0x180025e26  jz      loc_180025C31
0x180025e2c  jmp     loc_180025CEA
```
