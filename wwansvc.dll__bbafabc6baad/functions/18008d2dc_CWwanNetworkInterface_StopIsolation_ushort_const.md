# CWwanNetworkInterface::StopIsolation(ushort const *)

- ea: `0x18008d2dc`
- end: `0x18008d518`
- name: `?StopIsolation@CWwanNetworkInterface@@QEAAKPEBG@Z`
- size: `572`
- prototype: `unsigned int __fastcall(CWwanNetworkInterface *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18004acd0`
- `0x180059674`
- `0x18008bb44`

## callees

- `0x1800111ac`
- `0x180012300`
- `0x180014f1c`
- `0x180016c50`
- `0x1800196bc`
- `0x180072288`
- `0x18008b710`
- `0x18008bc0c`
- `0x18008d2dc`

## import_xrefs

- `FirewallAPI!NetworkIsolationCreateInterfaceContainer` at `0x18008d3fa`
- `FirewallAPI!NetworkIsolationCreateInterfaceContainer` at `0x18008d3fa`
- `FirewallAPI!NetworkIsolationDeleteInterfaceContainer` at `0x18008d3b6`
- `FirewallAPI!NetworkIsolationDeleteInterfaceContainer` at `0x18008d421`
- `FirewallAPI!NetworkIsolationDeleteInterfaceContainer` at `0x18008d3b6`
- `FirewallAPI!NetworkIsolationDeleteInterfaceContainer` at `0x18008d421`

## string_xrefs

- `0x18008d3c3`: `NetworkIsolationDeleteInterfaceContainer Failed %u`
- `0x18008d431`: `NetworkIsolationDeleteInterfaceContainer Failed %u`
- `0x18008d40a`: `NetworkIsolationCreateInterfaceContainer Failed %u`
- `0x18008d458`: `Stop isolation Completed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWwanNetworkInterface::StopIsolation(CWwanNetworkInterface *this, const unsigned __int16 *a2)
{
  const unsigned __int16 *v3; // rdx
  __int64 v5; // rdx
  _QWORD *v6; // r15
  unsigned __int64 v7; // r14
  unsigned int v8; // eax
  unsigned int InterfaceContainer; // eax
  unsigned int v10; // r14d
  unsigned int v11; // eax
  _QWORD *v12[2]; // [rsp+40h] [rbp-38h] BYREF
  __int64 v13; // [rsp+50h] [rbp-28h]
  __int64 v14; // [rsp+80h] [rbp+8h] BYREF
  __int64 v15; // [rsp+90h] [rbp+18h] BYREF

  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,WWAN_PROFILE>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,WWAN_PROFILE>>>>>>(v12);
  if ( !*((_DWORD *)this + 253) )
  {
    WwanLog::Verbose("CWwanNetworkInterface::StopIsolation", 0, L"Interface hasn't been isolated, skip");
    if ( v12[0] )
      std::_Deallocate<16>(v12[0], 8 * ((signed __int64)(v13 - (unsigned __int64)v12[0]) >> 3));
    return 0;
  }
  CWwanNetworkInterface::ClearIsolationRulesCache(this, v3);
  v5 = **((_QWORD **)this + 127);
  v14 = v5;
  while ( 1 )
  {
    if ( v5 == *((_QWORD *)this + 127) )
    {
      if ( *((_QWORD *)this + 128) )
      {
        v6 = v12[0];
        v7 = 0xEFBEFBEFBEFBEFBFuLL * (v12[1] - v12[0]);
        if ( !v7 )
        {
          v6 = 0;
          LODWORD(v7) = 0;
        }
        v8 = NetworkIsolationDeleteInterfaceContainer(this);
        if ( v8 )
          WwanLog::Error(
            "CWwanNetworkInterface::StopIsolation",
            0,
            L"NetworkIsolationDeleteInterfaceContainer Failed %u",
            v8);
        InterfaceContainer = NetworkIsolationCreateInterfaceContainer(
                               this,
                               L"Wwan interface isolation",
                               L"Wwan interface isolation",
                               0,
                               3,
                               v7,
                               v6);
        v10 = InterfaceContainer;
        if ( InterfaceContainer )
          WwanLog::Error(
            "CWwanNetworkInterface::StopIsolation",
            0,
            L"NetworkIsolationCreateInterfaceContainer Failed %u",
            InterfaceContainer);
      }
      else
      {
        v11 = NetworkIsolationDeleteInterfaceContainer(this);
        v10 = v11;
        if ( v11 )
          WwanLog::Error(
            "CWwanNetworkInterface::StopIsolation",
            0,
            L"NetworkIsolationDeleteInterfaceContainer Failed %u",
            v11);
        else
          *((_DWORD *)this + 253) = 0;
      }
      WwanLog::Info("CWwanNetworkInterface::StopIsolation", 0, L"Stop isolation Completed");
      if ( v12[0] )
        std::_Deallocate<16>(v12[0], 8 * ((signed __int64)(v13 - (unsigned __int64)v12[0]) >> 3));
      return v10;
    }
    try
    {
      std::copy<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<_tag_FW_RULE>>>,std::back_insert_iterator<std::vector<_tag_FW_RULE>>>(
        &v15,
        *(_QWORD *)(v5 + 64),
        *(_QWORD *)(v5 + 72),
        (__int64)v12);
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,WWAN_PROFILE>>>,std::_Iterator_base0>::operator++(&v14);
      v5 = v14;
    }
    catch ( std::bad_alloc )
    {
      if ( v12[0] )
        std::_Deallocate<16>(v12[0], 8 * ((signed __int64)(v13 - (unsigned __int64)v12[0]) >> 3));
      return 14;
    }
  }
}

```

## disassembly

```asm
0x18008d2dc  mov     [rsp+arg_8], rbx
0x18008d2e1  mov     [rsp+arg_18], rsi
0x18008d2e6  push    rdi
0x18008d2e7  push    r14
0x18008d2e9  push    r15
0x18008d2eb  sub     rsp, 60h
0x18008d2ef  mov     rdi, rcx
0x18008d2f2  lea     rcx, [rsp+78h+var_38]
0x18008d2f7  call    ??$?0AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UWWAN_PROFILE@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UWWAN_PROFILE@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UWWAN_PROFILE@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,WWAN_PROFILE>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,WWAN_PROFILE>>>>>>(std::allocator<std::pair<std::wstring const,WWAN_PROFILE>> const &)
0x18008d2fc  nop
0x18008d2fd  xor     ebx, ebx
0x18008d2ff  cmp     [rdi+3F4h], ebx
0x18008d305  jnz     short loc_18008D354
0x18008d307  lea     r8, aInterfaceHasnT; "Interface hasn't been isolated, skip"
0x18008d30e  xor     edx, edx; struct _GUID *
0x18008d310  lea     rcx, aCwwannetworkin_12; "CWwanNetworkInterface::StopIsolation"
0x18008d317  call    ?Verbose@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Verbose(char const *,_GUID const *,ushort const *,...)
0x18008d31c  nop
0x18008d31d  mov     rcx, [rsp+78h+var_38]
0x18008d322  test    rcx, rcx
0x18008d325  jz      short loc_18008D34D
0x18008d327  mov     rax, [rsp+78h+var_28]
0x18008d32c  sub     rax, rcx
0x18008d32f  sar     rax, 3
0x18008d333  mov     rsi, 0EFBEFBEFBEFBEFBFh
0x18008d33d  imul    rax, rsi
0x18008d341  imul    rdx, rax, 1F8h
0x18008d348  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18008d34d  xor     eax, eax
0x18008d34f  jmp     loc_18008D502
0x18008d354  mov     rcx, rdi; this
0x18008d357  call    ?ClearIsolationRulesCache@CWwanNetworkInterface@@AEAAKPEBG@Z; CWwanNetworkInterface::ClearIsolationRulesCache(ushort const *)
0x18008d35c  nop
0x18008d35d  mov     rdx, [rdi+3F8h]
0x18008d364  mov     rdx, [rdx]
0x18008d367  mov     [rsp+78h+arg_0], rdx
0x18008d36f  cmp     rdx, [rdi+3F8h]
0x18008d376  jnz     loc_18008D499
0x18008d37c  mov     rcx, rdi
0x18008d37f  cmp     [rdi+400h], rbx
0x18008d386  jbe     loc_18008D421
0x18008d38c  mov     r15, [rsp+78h+var_38]
0x18008d391  mov     r14, [rsp+78h+var_30]
0x18008d396  sub     r14, r15
0x18008d399  sar     r14, 3
0x18008d39d  mov     rsi, 0EFBEFBEFBEFBEFBFh
0x18008d3a7  imul    r14, rsi
0x18008d3ab  test    r14, r14
0x18008d3ae  cmovz   r15, rbx
0x18008d3b2  cmovz   r14d, ebx
0x18008d3b6  call    cs:__imp_NetworkIsolationDeleteInterfaceContainer
0x18008d3bc  test    eax, eax
0x18008d3be  jz      short loc_18008D3D8
0x18008d3c0  mov     r9d, eax
0x18008d3c3  lea     r8, aNetworkisolati_1; "NetworkIsolationDeleteInterfaceContaine"...
0x18008d3ca  xor     edx, edx; struct _GUID *
0x18008d3cc  lea     rcx, aCwwannetworkin_12; "CWwanNetworkInterface::StopIsolation"
0x18008d3d3  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18008d3d8  mov     [rsp+78h+var_48], r15
0x18008d3dd  mov     [rsp+78h+var_50], r14d
0x18008d3e2  mov     [rsp+78h+var_58], 3
0x18008d3ea  xor     r9d, r9d
0x18008d3ed  lea     rdx, aWwanInterfaceI_0; "Wwan interface isolation"
0x18008d3f4  mov     r8, rdx
0x18008d3f7  mov     rcx, rdi
0x18008d3fa  call    cs:__imp_NetworkIsolationCreateInterfaceContainer
0x18008d400  mov     r14d, eax
0x18008d403  test    eax, eax
0x18008d405  jz      short loc_18008D458
0x18008d407  mov     r9d, eax
0x18008d40a  lea     r8, aNetworkisolati_2; "NetworkIsolationCreateInterfaceContaine"...
0x18008d411  xor     edx, edx; struct _GUID *
0x18008d413  lea     rcx, aCwwannetworkin_12; "CWwanNetworkInterface::StopIsolation"
0x18008d41a  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18008d41f  jmp     short loc_18008D458
0x18008d421  call    cs:__imp_NetworkIsolationDeleteInterfaceContainer
0x18008d427  mov     r14d, eax
0x18008d42a  test    eax, eax
0x18008d42c  jz      short loc_18008D448
0x18008d42e  mov     r9d, eax
0x18008d431  lea     r8, aNetworkisolati_1; "NetworkIsolationDeleteInterfaceContaine"...
0x18008d438  xor     edx, edx; struct _GUID *
0x18008d43a  lea     rcx, aCwwannetworkin_12; "CWwanNetworkInterface::StopIsolation"
0x18008d441  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18008d446  jmp     short loc_18008D44E
0x18008d448  mov     [rdi+3F4h], ebx
0x18008d44e  mov     rsi, 0EFBEFBEFBEFBEFBFh
0x18008d458  lea     r8, aStopIsolationC; "Stop isolation Completed"
0x18008d45f  xor     edx, edx; struct _GUID *
0x18008d461  lea     rcx, aCwwannetworkin_12; "CWwanNetworkInterface::StopIsolation"
0x18008d468  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18008d46d  nop
0x18008d46e  mov     rcx, [rsp+78h+var_38]
0x18008d473  test    rcx, rcx
0x18008d476  jz      short loc_18008D494
0x18008d478  mov     rax, [rsp+78h+var_28]
0x18008d47d  sub     rax, rcx
0x18008d480  sar     rax, 3
0x18008d484  imul    rax, rsi
0x18008d488  imul    rdx, rax, 1F8h
0x18008d48f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18008d494  mov     eax, r14d
0x18008d497  jmp     short loc_18008D502
0x18008d499  lea     r9, [rsp+78h+var_38]
0x18008d49e  mov     r8, [rdx+48h]
0x18008d4a2  mov     rdx, [rdx+40h]
0x18008d4a6  lea     rcx, [rsp+78h+arg_10]
0x18008d4ae  call    ??$copy@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@U_tag_FW_RULE@@@std@@@std@@@std@@V?$back_insert_iterator@V?$vector@U_tag_FW_RULE@@V?$allocator@U_tag_FW_RULE@@@std@@@std@@@2@@std@@YA?AV?$back_insert_iterator@V?$vector@U_tag_FW_RULE@@V?$allocator@U_tag_FW_RULE@@@std@@@std@@@0@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@U_tag_FW_RULE@@@std@@@std@@@0@0V10@@Z; std::copy<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<_tag_FW_RULE>>>,std::back_insert_iterator<std::vector<_tag_FW_RULE>>>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<_tag_FW_RULE>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<_tag_FW_RULE>>>,std::back_insert_iterator<std::vector<_tag_FW_RULE>>)
0x18008d4b3  lea     rcx, [rsp+78h+arg_0]
0x18008d4bb  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKUWWAN_PROFILE@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,WWAN_PROFILE>>>,std::_Iterator_base0>::operator++(void)
0x18008d4c0  mov     rdx, [rsp+78h+arg_0]
0x18008d4c8  jmp     loc_18008D36F
0x18008d4cd  mov     rcx, [rsp+78h+var_38]
0x18008d4d2  test    rcx, rcx
0x18008d4d5  jz      short loc_18008D4FD
0x18008d4d7  mov     rax, [rsp+78h+var_28]
0x18008d4dc  sub     rax, rcx
0x18008d4df  sar     rax, 3
0x18008d4e3  mov     rsi, 0EFBEFBEFBEFBEFBFh
0x18008d4ed  imul    rax, rsi
0x18008d4f1  imul    rdx, rax, 1F8h
0x18008d4f8  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18008d4fd  mov     eax, 0Eh
0x18008d502  lea     r11, [rsp+78h+var_18]
0x18008d507  mov     rbx, [r11+28h]
0x18008d50b  mov     rsi, [r11+38h]
0x18008d50f  mov     rsp, r11
0x18008d512  pop     r15
0x18008d514  pop     r14
0x18008d516  pop     rdi
0x18008d517  retn
```
