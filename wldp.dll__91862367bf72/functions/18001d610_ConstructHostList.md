# ConstructHostList

- ea: `0x18001d610`
- end: `0x18001d9ac`
- name: `ConstructHostList`
- size: `924`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1800167a0`
- `0x180019ae0`
- `0x180019afc`
- `0x180019ddc`
- `0x18001d610`
- `0x18002d8b8`

## string_xrefs

- `0x18001d638`: `WindowsCommandPrompt`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ConstructHostList(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)
{
  void *v3; // rdx
  void *v4; // rcx
  __int64 result; // rax
  _BYTE v6[16]; // [rsp+20h] [rbp-128h] BYREF
  char v7; // [rsp+30h] [rbp-118h] BYREF
  int v8; // [rsp+31h] [rbp-117h]
  __int16 v9; // [rsp+35h] [rbp-113h]
  char v10; // [rsp+37h] [rbp-111h]
  const wchar_t *v11; // [rsp+38h] [rbp-110h]
  const wchar_t *v12; // [rsp+40h] [rbp-108h]
  char v13; // [rsp+50h] [rbp-F8h] BYREF
  int v14; // [rsp+51h] [rbp-F7h]
  __int16 v15; // [rsp+55h] [rbp-F3h]
  char v16; // [rsp+57h] [rbp-F1h]
  __int128 v17; // [rsp+58h] [rbp-F0h]
  char v18; // [rsp+68h] [rbp-E0h] BYREF
  int v19; // [rsp+69h] [rbp-DFh]
  __int16 v20; // [rsp+6Dh] [rbp-DBh]
  char v21; // [rsp+6Fh] [rbp-D9h]
  __int128 v22; // [rsp+70h] [rbp-D8h]
  char v23; // [rsp+80h] [rbp-C8h] BYREF
  int v24; // [rsp+81h] [rbp-C7h]
  __int16 v25; // [rsp+85h] [rbp-C3h]
  char v26; // [rsp+87h] [rbp-C1h]
  __int128 v27; // [rsp+88h] [rbp-C0h]
  char v28; // [rsp+98h] [rbp-B0h] BYREF
  int v29; // [rsp+99h] [rbp-AFh]
  __int16 v30; // [rsp+9Dh] [rbp-ABh]
  char v31; // [rsp+9Fh] [rbp-A9h]
  __int128 v32; // [rsp+A0h] [rbp-A8h]
  char v33; // [rsp+B0h] [rbp-98h] BYREF
  int v34; // [rsp+B1h] [rbp-97h]
  __int16 v35; // [rsp+B5h] [rbp-93h]
  char v36; // [rsp+B7h] [rbp-91h]
  __int128 v37; // [rsp+B8h] [rbp-90h]
  char v38; // [rsp+C8h] [rbp-80h] BYREF
  int v39; // [rsp+C9h] [rbp-7Fh]
  __int16 v40; // [rsp+CDh] [rbp-7Bh]
  char v41; // [rsp+CFh] [rbp-79h]
  __int128 v42; // [rsp+D0h] [rbp-78h]
  char v43; // [rsp+E0h] [rbp-68h] BYREF
  int v44; // [rsp+E1h] [rbp-67h]
  __int16 v45; // [rsp+E5h] [rbp-63h]
  char v46; // [rsp+E7h] [rbp-61h]
  __int128 v47; // [rsp+E8h] [rbp-60h]
  char v48; // [rsp+F8h] [rbp-50h] BYREF
  int v49; // [rsp+F9h] [rbp-4Fh]
  __int16 v50; // [rsp+FDh] [rbp-4Bh]
  char v51; // [rsp+FFh] [rbp-49h]
  __int128 v52; // [rsp+100h] [rbp-48h]
  char v53; // [rsp+110h] [rbp-38h] BYREF
  int v54; // [rsp+111h] [rbp-37h]
  __int16 v55; // [rsp+115h] [rbp-33h]
  char v56; // [rsp+117h] [rbp-31h]
  __int128 v57; // [rsp+118h] [rbp-30h]
  char v58; // [rsp+128h] [rbp-20h] BYREF
  int v59; // [rsp+129h] [rbp-1Fh]
  __int16 v60; // [rsp+12Dh] [rbp-1Bh]
  char v61; // [rsp+12Fh] [rbp-19h]
  __int128 v62; // [rsp+130h] [rbp-18h]
  void *v63; // [rsp+168h] [rbp+20h] BYREF

  try
  {
    std::make_unique<std::map<_GUID,WLDP_HOST_INFO,GUIDLess,std::allocator<std::pair<_GUID const,WLDP_HOST_INFO>>>,,0>(&v63);
    v7 = 1;
    v8 = 0;
    v9 = 0;
    v10 = 0;
    v11 = L"WindowsCommandPrompt";
    v12 = L"EnableAppControl";
    std::_Tree<std::_Tmap_traits<_GUID,WLDP_HOST_INFO,GUIDLess,std::allocator<std::pair<_GUID const,WLDP_HOST_INFO>>,0>>::emplace<_GUID const &,WLDP_HOST_INFO>(
      v63,
      v6,
      &WLDP_HOST_CMD,
      &v7);
    v13 = 1;
    v14 = 0;
    v15 = 0;
    v16 = 0;
    v17 = 0;
    std::_Tree<std::_Tmap_traits<_GUID,WLDP_HOST_INFO,GUIDLess,std::allocator<std::pair<_GUID const,WLDP_HOST_INFO>>,0>>::emplace<_GUID const &,WLDP_HOST_INFO>(
      v63,
      v6,
      &WLDP_HOST_POWERSHELL,
      &v13);
    v18 = 1;
    v19 = 0;
    v20 = 0;
    v21 = 0;
    v22 = 0;
    std::_Tree<std::_Tmap_traits<_GUID,WLDP_HOST_INFO,GUIDLess,std::allocator<std::pair<_GUID const,WLDP_HOST_INFO>>,0>>::emplace<_GUID const &,WLDP_HOST_INFO>(
      v63,
      v6,
      &WLDP_HOST_PYTHON,
      &v18);
    v23 = 1;
    v24 = 0;
    v25 = 0;
    v26 = 0;
    v27 = 0;
    std::_Tree<std::_Tmap_traits<_GUID,WLDP_HOST_INFO,GUIDLess,std::allocator<std::pair<_GUID const,WLDP_HOST_INFO>>,0>>::emplace<_GUID const &,WLDP_HOST_INFO>(
      v63,
      v6,
      &WLDP_HOST_WINDOWS_SCRIPT_HOST,
      &v23);
    v28 = 1;
    v29 = 0;
    v30 = 0;
    v31 = 0;
    v32 = 0;
    std::_Tree<std::_Tmap_traits<_GUID,WLDP_HOST_INFO,GUIDLess,std::allocator<std::pair<_GUID const,WLDP_HOST_INFO>>,0>>::emplace<_GUID const &,WLDP_HOST_INFO>(
      v63,
      v6,
      &WLDP_HOST_JAVASCRIPT,
      &v28);
    v33 = 1;
    v34 = 0;
    v35 = 0;
    v36 = 0;
    v37 = 0;
    std::_Tree<std::_Tmap_traits<_GUID,WLDP_HOST_INFO,GUIDLess,std::allocator<std::pair<_GUID const,WLDP_HOST_INFO>>,0>>::emplace<_GUID const &,WLDP_HOST_INFO>(
      v63,
      v6,
      &WLDP_HOST_HTML,
      &v33);
    v38 = 1;
    v39 = 0;
    v40 = 0;
    v41 = 0;
    v42 = 0;
    std::_Tree<std::_Tmap_traits<_GUID,WLDP_HOST_INFO,GUIDLess,std::allocator<std::pair<_GUID const,WLDP_HOST_INFO>>,0>>::emplace<_GUID const &,WLDP_HOST_INFO>(
      v63,
      v6,
      &WLDP_HOST_XML,
      &v38);
    v43 = 0;
    v44 = 0;
    v45 = 0;
    v46 = 0;
    v47 = 0;
    std::_Tree<std::_Tmap_traits<_GUID,WLDP_HOST_INFO,GUIDLess,std::allocator<std::pair<_GUID const,WLDP_HOST_INFO>>,0>>::emplace<_GUID const &,WLDP_HOST_INFO>(
      v63,
      v6,
      &WLDP_HOST_MSI,
      &v43);
    v48 = 0;
    v49 = 0;
    v50 = 0;
    v51 = 0;
    v52 = 0;
    std::_Tree<std::_Tmap_traits<_GUID,WLDP_HOST_INFO,GUIDLess,std::allocator<std::pair<_GUID const,WLDP_HOST_INFO>>,0>>::emplace<_GUID const &,WLDP_HOST_INFO>(
      v63,
      v6,
      &WLDP_HOST_OTHER,
      &v48);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WLDP_MCPB_InstallTime>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WLDP_MCPB_InstallTime>::GetImpl'::`2'::impl) )
    {
      v53 = 0;
      v54 = 0;
      v55 = 0;
      v56 = 0;
      v57 = 0;
      std::_Tree<std::_Tmap_traits<_GUID,WLDP_HOST_INFO,GUIDLess,std::allocator<std::pair<_GUID const,WLDP_HOST_INFO>>,0>>::emplace<_GUID const &,WLDP_HOST_INFO>(
        v63,
        v6,
        &WLDP_HOST_MCPB,
        &v53);
      v58 = 0;
      v59 = 0;
      v60 = 0;
      v61 = 0;
      v62 = 0;
      std::_Tree<std::_Tmap_traits<_GUID,WLDP_HOST_INFO,GUIDLess,std::allocator<std::pair<_GUID const,WLDP_HOST_INFO>>,0>>::emplace<_GUID const &,WLDP_HOST_INFO>(
        v63,
        v6,
        &WLDP_HOST_MSIX,
        &v58);
    }
    v3 = v63;
    v63 = 0;
    v4 = qword_18005B060;
    qword_18005B060 = v3;
    if ( v4 )
      std::map<_GUID,WLDP_HOST_INFO,GUIDLess,std::allocator<std::pair<_GUID const,WLDP_HOST_INFO>>>::`scalar deleting destructor'(v4);
    std::unique_ptr<std::map<_GUID,WLDP_HOST_INFO,GUIDLess,std::allocator<std::pair<_GUID const,WLDP_HOST_INFO>>>>::~unique_ptr<std::map<_GUID,WLDP_HOST_INFO,GUIDLess,std::allocator<std::pair<_GUID const,WLDP_HOST_INFO>>>>(&v63);
    result = 1;
  }
  catch ( ... )
  {
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001d610  mov     rax, rsp
0x18001d613  sub     rsp, 148h
0x18001d61a  lea     rcx, [rax+20h]
0x18001d61e  call    ??$make_unique@V?$map@U_GUID@@UWLDP_HOST_INFO@@UGUIDLess@@V?$allocator@U?$pair@$$CBU_GUID@@UWLDP_HOST_INFO@@@std@@@std@@@std@@$$V$0A@@std@@YA?AV?$unique_ptr@V?$map@U_GUID@@UWLDP_HOST_INFO@@UGUIDLess@@V?$allocator@U?$pair@$$CBU_GUID@@UWLDP_HOST_INFO@@@std@@@std@@@std@@U?$default_delete@V?$map@U_GUID@@UWLDP_HOST_INFO@@UGUIDLess@@V?$allocator@U?$pair@$$CBU_GUID@@UWLDP_HOST_INFO@@@std@@@std@@@std@@@2@@0@XZ; std::make_unique<std::map<_GUID,WLDP_HOST_INFO,GUIDLess,std::allocator<std::pair<_GUID const,WLDP_HOST_INFO>>>,,0>(void)
0x18001d623  nop
0x18001d624  mov     [rsp+148h+var_118], 1
0x18001d629  xor     eax, eax
0x18001d62b  mov     [rsp+148h+var_117], eax
0x18001d62f  mov     [rsp+148h+var_113], ax
0x18001d634  mov     [rsp+148h+var_111], al
0x18001d638  lea     rax, aWindowscommand; "WindowsCommandPrompt"
0x18001d63f  mov     [rsp+148h+var_110], rax
0x18001d644  lea     rax, aEnableappcontr; "EnableAppControl"
0x18001d64b  mov     [rsp+148h+var_108], rax
0x18001d650  lea     r9, [rsp+148h+var_118]
0x18001d655  lea     r8, WLDP_HOST_CMD
0x18001d65c  lea     rdx, [rsp+148h+var_128]
0x18001d661  mov     rcx, [rsp+148h+arg_18]
0x18001d669  call    ??$emplace@AEBU_GUID@@UWLDP_HOST_INFO@@@?$_Tree@V?$_Tmap_traits@U_GUID@@UWLDP_HOST_INFO@@UGUIDLess@@V?$allocator@U?$pair@$$CBU_GUID@@UWLDP_HOST_INFO@@@std@@@std@@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@UWLDP_HOST_INFO@@@std@@@std@@@std@@@std@@_N@1@AEBU_GUID@@$$QEAUWLDP_HOST_INFO@@@Z; std::_Tree<std::_Tmap_traits<_GUID,WLDP_HOST_INFO,GUIDLess,std::allocator<std::pair<_GUID const,WLDP_HOST_INFO>>,0>>::emplace<_GUID const &,WLDP_HOST_INFO>(_GUID const &,WLDP_HOST_INFO &&)
0x18001d66e  mov     [rsp+148h+var_F8], 1
0x18001d673  xor     eax, eax
0x18001d675  mov     [rsp+148h+var_F7], eax
0x18001d679  mov     [rsp+148h+var_F3], ax
0x18001d67e  mov     [rsp+148h+var_F1], al
0x18001d682  xorps   xmm0, xmm0
0x18001d685  movdqu  [rsp+148h+var_F0], xmm0
0x18001d68b  lea     r9, [rsp+148h+var_F8]
0x18001d690  lea     r8, WLDP_HOST_POWERSHELL
0x18001d697  lea     rdx, [rsp+148h+var_128]
0x18001d69c  mov     rcx, [rsp+148h+arg_18]
0x18001d6a4  call    ??$emplace@AEBU_GUID@@UWLDP_HOST_INFO@@@?$_Tree@V?$_Tmap_traits@U_GUID@@UWLDP_HOST_INFO@@UGUIDLess@@V?$allocator@U?$pair@$$CBU_GUID@@UWLDP_HOST_INFO@@@std@@@std@@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@UWLDP_HOST_INFO@@@std@@@std@@@std@@@std@@_N@1@AEBU_GUID@@$$QEAUWLDP_HOST_INFO@@@Z; std::_Tree<std::_Tmap_traits<_GUID,WLDP_HOST_INFO,GUIDLess,std::allocator<std::pair<_GUID const,WLDP_HOST_INFO>>,0>>::emplace<_GUID const &,WLDP_HOST_INFO>(_GUID const &,WLDP_HOST_INFO &&)
0x18001d6a9  mov     [rsp+148h+var_E0], 1
0x18001d6ae  xor     eax, eax
0x18001d6b0  mov     [rsp+148h+var_DF], eax
0x18001d6b4  mov     [rsp+148h+var_DB], ax
0x18001d6b9  mov     [rsp+148h+var_D9], al
0x18001d6bd  xorps   xmm0, xmm0
0x18001d6c0  movdqu  [rsp+148h+var_D8], xmm0
0x18001d6c6  lea     r9, [rsp+148h+var_E0]
0x18001d6cb  lea     r8, WLDP_HOST_PYTHON
0x18001d6d2  lea     rdx, [rsp+148h+var_128]
0x18001d6d7  mov     rcx, [rsp+148h+arg_18]
0x18001d6df  call    ??$emplace@AEBU_GUID@@UWLDP_HOST_INFO@@@?$_Tree@V?$_Tmap_traits@U_GUID@@UWLDP_HOST_INFO@@UGUIDLess@@V?$allocator@U?$pair@$$CBU_GUID@@UWLDP_HOST_INFO@@@std@@@std@@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@UWLDP_HOST_INFO@@@std@@@std@@@std@@@std@@_N@1@AEBU_GUID@@$$QEAUWLDP_HOST_INFO@@@Z; std::_Tree<std::_Tmap_traits<_GUID,WLDP_HOST_INFO,GUIDLess,std::allocator<std::pair<_GUID const,WLDP_HOST_INFO>>,0>>::emplace<_GUID const &,WLDP_HOST_INFO>(_GUID const &,WLDP_HOST_INFO &&)
0x18001d6e4  mov     [rsp+148h+var_C8], 1
0x18001d6ec  xor     eax, eax
0x18001d6ee  mov     [rsp+148h+var_C7], eax
0x18001d6f5  mov     [rsp+148h+var_C3], ax
0x18001d6fd  mov     [rsp+148h+var_C1], al
0x18001d704  xorps   xmm0, xmm0
0x18001d707  movdqu  [rsp+148h+var_C0], xmm0
0x18001d710  lea     r9, [rsp+148h+var_C8]
0x18001d718  lea     r8, WLDP_HOST_WINDOWS_SCRIPT_HOST
0x18001d71f  lea     rdx, [rsp+148h+var_128]
0x18001d724  mov     rcx, [rsp+148h+arg_18]
0x18001d72c  call    ??$emplace@AEBU_GUID@@UWLDP_HOST_INFO@@@?$_Tree@V?$_Tmap_traits@U_GUID@@UWLDP_HOST_INFO@@UGUIDLess@@V?$allocator@U?$pair@$$CBU_GUID@@UWLDP_HOST_INFO@@@std@@@std@@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@UWLDP_HOST_INFO@@@std@@@std@@@std@@@std@@_N@1@AEBU_GUID@@$$QEAUWLDP_HOST_INFO@@@Z; std::_Tree<std::_Tmap_traits<_GUID,WLDP_HOST_INFO,GUIDLess,std::allocator<std::pair<_GUID const,WLDP_HOST_INFO>>,0>>::emplace<_GUID const &,WLDP_HOST_INFO>(_GUID const &,WLDP_HOST_INFO &&)
0x18001d731  mov     [rsp+148h+var_B0], 1
0x18001d739  xor     eax, eax
0x18001d73b  mov     [rsp+148h+var_AF], eax
0x18001d742  mov     [rsp+148h+var_AB], ax
0x18001d74a  mov     [rsp+148h+var_A9], al
0x18001d751  xorps   xmm0, xmm0
0x18001d754  movdqu  [rsp+148h+var_A8], xmm0
0x18001d75d  lea     r9, [rsp+148h+var_B0]
0x18001d765  lea     r8, WLDP_HOST_JAVASCRIPT
0x18001d76c  lea     rdx, [rsp+148h+var_128]
0x18001d771  mov     rcx, [rsp+148h+arg_18]
0x18001d779  call    ??$emplace@AEBU_GUID@@UWLDP_HOST_INFO@@@?$_Tree@V?$_Tmap_traits@U_GUID@@UWLDP_HOST_INFO@@UGUIDLess@@V?$allocator@U?$pair@$$CBU_GUID@@UWLDP_HOST_INFO@@@std@@@std@@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@UWLDP_HOST_INFO@@@std@@@std@@@std@@@std@@_N@1@AEBU_GUID@@$$QEAUWLDP_HOST_INFO@@@Z; std::_Tree<std::_Tmap_traits<_GUID,WLDP_HOST_INFO,GUIDLess,std::allocator<std::pair<_GUID const,WLDP_HOST_INFO>>,0>>::emplace<_GUID const &,WLDP_HOST_INFO>(_GUID const &,WLDP_HOST_INFO &&)
0x18001d77e  mov     [rsp+148h+var_98], 1
0x18001d786  xor     eax, eax
0x18001d788  mov     [rsp+148h+var_97], eax
0x18001d78f  mov     [rsp+148h+var_93], ax
0x18001d797  mov     [rsp+148h+var_91], al
0x18001d79e  xorps   xmm0, xmm0
0x18001d7a1  movdqu  [rsp+148h+var_90], xmm0
0x18001d7aa  lea     r9, [rsp+148h+var_98]
0x18001d7b2  lea     r8, WLDP_HOST_HTML
0x18001d7b9  lea     rdx, [rsp+148h+var_128]
0x18001d7be  mov     rcx, [rsp+148h+arg_18]
0x18001d7c6  call    ??$emplace@AEBU_GUID@@UWLDP_HOST_INFO@@@?$_Tree@V?$_Tmap_traits@U_GUID@@UWLDP_HOST_INFO@@UGUIDLess@@V?$allocator@U?$pair@$$CBU_GUID@@UWLDP_HOST_INFO@@@std@@@std@@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@UWLDP_HOST_INFO@@@std@@@std@@@std@@@std@@_N@1@AEBU_GUID@@$$QEAUWLDP_HOST_INFO@@@Z; std::_Tree<std::_Tmap_traits<_GUID,WLDP_HOST_INFO,GUIDLess,std::allocator<std::pair<_GUID const,WLDP_HOST_INFO>>,0>>::emplace<_GUID const &,WLDP_HOST_INFO>(_GUID const &,WLDP_HOST_INFO &&)
0x18001d7cb  mov     [rsp+148h+var_80], 1
0x18001d7d3  xor     eax, eax
0x18001d7d5  mov     [rsp+148h+var_7F], eax
0x18001d7dc  mov     [rsp+148h+var_7B], ax
0x18001d7e4  mov     [rsp+148h+var_79], al
0x18001d7eb  xorps   xmm0, xmm0
0x18001d7ee  movdqu  [rsp+148h+var_78], xmm0
0x18001d7f7  lea     r9, [rsp+148h+var_80]
0x18001d7ff  lea     r8, WLDP_HOST_XML
0x18001d806  lea     rdx, [rsp+148h+var_128]
0x18001d80b  mov     rcx, [rsp+148h+arg_18]
0x18001d813  call    ??$emplace@AEBU_GUID@@UWLDP_HOST_INFO@@@?$_Tree@V?$_Tmap_traits@U_GUID@@UWLDP_HOST_INFO@@UGUIDLess@@V?$allocator@U?$pair@$$CBU_GUID@@UWLDP_HOST_INFO@@@std@@@std@@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@UWLDP_HOST_INFO@@@std@@@std@@@std@@@std@@_N@1@AEBU_GUID@@$$QEAUWLDP_HOST_INFO@@@Z; std::_Tree<std::_Tmap_traits<_GUID,WLDP_HOST_INFO,GUIDLess,std::allocator<std::pair<_GUID const,WLDP_HOST_INFO>>,0>>::emplace<_GUID const &,WLDP_HOST_INFO>(_GUID const &,WLDP_HOST_INFO &&)
0x18001d818  mov     [rsp+148h+var_68], 0
0x18001d820  xor     eax, eax
0x18001d822  mov     [rsp+148h+var_67], eax
0x18001d829  mov     [rsp+148h+var_63], ax
0x18001d831  mov     [rsp+148h+var_61], al
0x18001d838  xorps   xmm0, xmm0
0x18001d83b  movdqu  [rsp+148h+var_60], xmm0
0x18001d844  lea     r9, [rsp+148h+var_68]
0x18001d84c  lea     r8, WLDP_HOST_MSI
0x18001d853  lea     rdx, [rsp+148h+var_128]
0x18001d858  mov     rcx, [rsp+148h+arg_18]
0x18001d860  call    ??$emplace@AEBU_GUID@@UWLDP_HOST_INFO@@@?$_Tree@V?$_Tmap_traits@U_GUID@@UWLDP_HOST_INFO@@UGUIDLess@@V?$allocator@U?$pair@$$CBU_GUID@@UWLDP_HOST_INFO@@@std@@@std@@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@UWLDP_HOST_INFO@@@std@@@std@@@std@@@std@@_N@1@AEBU_GUID@@$$QEAUWLDP_HOST_INFO@@@Z; std::_Tree<std::_Tmap_traits<_GUID,WLDP_HOST_INFO,GUIDLess,std::allocator<std::pair<_GUID const,WLDP_HOST_INFO>>,0>>::emplace<_GUID const &,WLDP_HOST_INFO>(_GUID const &,WLDP_HOST_INFO &&)
0x18001d865  mov     [rsp+148h+var_50], 0
0x18001d86d  xor     eax, eax
0x18001d86f  mov     [rsp+148h+var_4F], eax
0x18001d876  mov     [rsp+148h+var_4B], ax
0x18001d87e  mov     [rsp+148h+var_49], al
0x18001d885  xorps   xmm0, xmm0
0x18001d888  movdqu  [rsp+148h+var_48], xmm0
0x18001d891  lea     r9, [rsp+148h+var_50]
0x18001d899  lea     r8, WLDP_HOST_OTHER
0x18001d8a0  lea     rdx, [rsp+148h+var_128]
0x18001d8a5  mov     rcx, [rsp+148h+arg_18]
0x18001d8ad  call    ??$emplace@AEBU_GUID@@UWLDP_HOST_INFO@@@?$_Tree@V?$_Tmap_traits@U_GUID@@UWLDP_HOST_INFO@@UGUIDLess@@V?$allocator@U?$pair@$$CBU_GUID@@UWLDP_HOST_INFO@@@std@@@std@@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@UWLDP_HOST_INFO@@@std@@@std@@@std@@@std@@_N@1@AEBU_GUID@@$$QEAUWLDP_HOST_INFO@@@Z; std::_Tree<std::_Tmap_traits<_GUID,WLDP_HOST_INFO,GUIDLess,std::allocator<std::pair<_GUID const,WLDP_HOST_INFO>>,0>>::emplace<_GUID const &,WLDP_HOST_INFO>(_GUID const &,WLDP_HOST_INFO &&)
0x18001d8b2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WLDP_MCPB_InstallTime@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WLDP_MCPB_InstallTime@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WLDP_MCPB_InstallTime> `wil::Feature<__WilFeatureTraits_Feature_WLDP_MCPB_InstallTime>::GetImpl(void)'::`2'::impl
0x18001d8b9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WLDP_MCPB_InstallTime@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WLDP_MCPB_InstallTime>::__private_IsEnabled(void)
0x18001d8be  test    al, al
0x18001d8c0  jz      loc_18001D960
0x18001d8c6  mov     [rsp+148h+var_38], 0
0x18001d8ce  xor     eax, eax
0x18001d8d0  mov     [rsp+148h+var_37], eax
0x18001d8d7  mov     [rsp+148h+var_33], ax
0x18001d8df  mov     [rsp+148h+var_31], al
0x18001d8e6  xorps   xmm0, xmm0
0x18001d8e9  movdqu  [rsp+148h+var_30], xmm0
0x18001d8f2  lea     r9, [rsp+148h+var_38]
0x18001d8fa  lea     r8, WLDP_HOST_MCPB
0x18001d901  lea     rdx, [rsp+148h+var_128]
0x18001d906  mov     rcx, [rsp+148h+arg_18]
0x18001d90e  call    ??$emplace@AEBU_GUID@@UWLDP_HOST_INFO@@@?$_Tree@V?$_Tmap_traits@U_GUID@@UWLDP_HOST_INFO@@UGUIDLess@@V?$allocator@U?$pair@$$CBU_GUID@@UWLDP_HOST_INFO@@@std@@@std@@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@UWLDP_HOST_INFO@@@std@@@std@@@std@@@std@@_N@1@AEBU_GUID@@$$QEAUWLDP_HOST_INFO@@@Z; std::_Tree<std::_Tmap_traits<_GUID,WLDP_HOST_INFO,GUIDLess,std::allocator<std::pair<_GUID const,WLDP_HOST_INFO>>,0>>::emplace<_GUID const &,WLDP_HOST_INFO>(_GUID const &,WLDP_HOST_INFO &&)
0x18001d913  mov     [rsp+148h+var_20], 0
0x18001d91b  xor     eax, eax
0x18001d91d  mov     [rsp+148h+var_1F], eax
0x18001d924  mov     [rsp+148h+var_1B], ax
0x18001d92c  mov     [rsp+148h+var_19], al
0x18001d933  xorps   xmm0, xmm0
0x18001d936  movdqu  [rsp+148h+var_18], xmm0
0x18001d93f  lea     r9, [rsp+148h+var_20]
0x18001d947  lea     r8, WLDP_HOST_MSIX
0x18001d94e  lea     rdx, [rsp+148h+var_128]
0x18001d953  mov     rcx, [rsp+148h+arg_18]
0x18001d95b  call    ??$emplace@AEBU_GUID@@UWLDP_HOST_INFO@@@?$_Tree@V?$_Tmap_traits@U_GUID@@UWLDP_HOST_INFO@@UGUIDLess@@V?$allocator@U?$pair@$$CBU_GUID@@UWLDP_HOST_INFO@@@std@@@std@@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@UWLDP_HOST_INFO@@@std@@@std@@@std@@@std@@_N@1@AEBU_GUID@@$$QEAUWLDP_HOST_INFO@@@Z; std::_Tree<std::_Tmap_traits<_GUID,WLDP_HOST_INFO,GUIDLess,std::allocator<std::pair<_GUID const,WLDP_HOST_INFO>>,0>>::emplace<_GUID const &,WLDP_HOST_INFO>(_GUID const &,WLDP_HOST_INFO &&)
0x18001d960  mov     rdx, [rsp+148h+arg_18]
0x18001d968  mov     [rsp+148h+arg_18], 0
0x18001d974  mov     rcx, cs:qword_18005B060; void *
0x18001d97b  mov     cs:qword_18005B060, rdx
0x18001d982  test    rcx, rcx
0x18001d985  jz      short loc_18001D98D
0x18001d987  call    ??_G?$map@U_GUID@@UWLDP_HOST_INFO@@UGUIDLess@@V?$allocator@U?$pair@$$CBU_GUID@@UWLDP_HOST_INFO@@@std@@@std@@@std@@QEAAPEAXI@Z; std::map<_GUID,WLDP_HOST_INFO,GUIDLess,std::allocator<std::pair<_GUID const,WLDP_HOST_INFO>>>::`scalar deleting destructor'(uint)
0x18001d98c  nop
0x18001d98d  lea     rcx, [rsp+148h+arg_18]
0x18001d995  call    ??1?$unique_ptr@V?$map@U_GUID@@UWLDP_HOST_INFO@@UGUIDLess@@V?$allocator@U?$pair@$$CBU_GUID@@UWLDP_HOST_INFO@@@std@@@std@@@std@@U?$default_delete@V?$map@U_GUID@@UWLDP_HOST_INFO@@UGUIDLess@@V?$allocator@U?$pair@$$CBU_GUID@@UWLDP_HOST_INFO@@@std@@@std@@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::map<_GUID,WLDP_HOST_INFO,GUIDLess,std::allocator<std::pair<_GUID const,WLDP_HOST_INFO>>>>::~unique_ptr<std::map<_GUID,WLDP_HOST_INFO,GUIDLess,std::allocator<std::pair<_GUID const,WLDP_HOST_INFO>>>>(void)
0x18001d99a  mov     eax, 1
0x18001d99f  jmp     short loc_18001D9A3
0x18001d9a1  xor     eax, eax
0x18001d9a3  add     rsp, 148h
0x18001d9aa  retn
```
