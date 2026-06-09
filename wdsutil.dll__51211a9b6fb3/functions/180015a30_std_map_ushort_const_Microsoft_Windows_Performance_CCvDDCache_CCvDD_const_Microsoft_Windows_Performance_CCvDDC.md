# std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::operator[](ushort const * &&)

- ea: `0x180015a30`
- end: `0x180015ad9`
- name: `??A?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAAEAPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@$$QEAPEBG@Z`
- size: `169`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180015e34`
- `0x180016248`

## callees

- `0x180012f40`
- `0x180013ae0`
- `0x180015a30`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180015a50`
- `msvcrt!_wcsicmp` at `0x180015a7e`
- `msvcrt!_wcsicmp` at `0x180015a50`
- `msvcrt!_wcsicmp` at `0x180015a7e`

## pseudocode

```c
__int64 **__fastcall std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::operator[](
        __int64 ***a1,
        const wchar_t **a2)
{
  __int64 **v2; // rbx
  __int64 *v5; // rdi
  __int64 v6; // rax
  _QWORD v8[7]; // [rsp+30h] [rbp-38h] BYREF
  __int64 **v9; // [rsp+70h] [rbp+8h] BYREF

  v2 = *a1;
  v5 = (*a1)[1];
  while ( !*((_BYTE *)v5 + 25) )
  {
    if ( _wcsicmp((const wchar_t *)v5[4], *a2) >= 0 )
    {
      v2 = (__int64 **)v5;
      v5 = (__int64 *)*v5;
    }
    else
    {
      v5 = (__int64 *)v5[2];
    }
  }
  if ( v2 == *a1 || _wcsicmp(*a2, (const wchar_t *)v2[4]) < 0 )
  {
    v8[0] = *a2;
    v8[1] = 0;
    v6 = std::_Tree_buy<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>::_Buynode<std::pair<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>(
           a1,
           v8);
    std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Insert_hint<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *> &,std::_Tree_node<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *>(
      a1,
      &v9,
      (__int64 *)v2,
      (const wchar_t **)(v6 + 32),
      v6);
    v2 = v9;
  }
  return v2 + 5;
}

```

## disassembly

```asm
0x180015a30  push    rbx
0x180015a32  push    rsi
0x180015a33  push    rdi
0x180015a34  push    r14
0x180015a36  sub     rsp, 48h
0x180015a3a  mov     rbx, [rcx]
0x180015a3d  mov     r14, rdx
0x180015a40  mov     rsi, rcx
0x180015a43  mov     rdi, [rbx+8]
0x180015a47  jmp     short loc_180015A6C
0x180015a49  mov     rdx, [r14]; String2
0x180015a4c  mov     rcx, [rdi+20h]; String1
0x180015a50  call    cs:__imp__wcsicmp
0x180015a57  nop     dword ptr [rax+rax+00h]
0x180015a5c  test    eax, eax
0x180015a5e  jns     short loc_180015A66
0x180015a60  mov     rdi, [rdi+10h]
0x180015a64  jmp     short loc_180015A6C
0x180015a66  mov     rbx, rdi
0x180015a69  mov     rdi, [rdi]
0x180015a6c  cmp     byte ptr [rdi+19h], 0
0x180015a70  jz      short loc_180015A49
0x180015a72  cmp     rbx, [rsi]
0x180015a75  jz      short loc_180015A8E
0x180015a77  mov     rdx, [rbx+20h]; String2
0x180015a7b  mov     rcx, [r14]; String1
0x180015a7e  call    cs:__imp__wcsicmp
0x180015a85  nop     dword ptr [rax+rax+00h]
0x180015a8a  test    eax, eax
0x180015a8c  jns     short loc_180015ACA
0x180015a8e  mov     rax, [r14]
0x180015a91  lea     rdx, [rsp+68h+var_38]
0x180015a96  mov     rcx, rsi
0x180015a99  mov     [rsp+68h+var_38], rax
0x180015a9e  mov     [rsp+68h+var_30], 0
0x180015aa7  call    ??$_Buynode@U?$pair@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@?$_Tree_buy@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@1@$$QEAU?$pair@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@1@@Z; std::_Tree_buy<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>::_Buynode<std::pair<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>(std::pair<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *> &&)
0x180015aac  mov     r8, rbx
0x180015aaf  mov     [rsp+68h+var_48], rax
0x180015ab4  lea     rdx, [rsp+68h+arg_0]
0x180015ab9  mov     rcx, rsi
0x180015abc  lea     r9, [rax+20h]
0x180015ac0  call    ??$_Insert_hint@AEAU?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@1@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@1@AEAU?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@1@PEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@1@@Z; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Insert_hint<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *>(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> *)
0x180015ac5  mov     rbx, [rsp+68h+arg_0]
0x180015aca  lea     rax, [rbx+28h]
0x180015ace  add     rsp, 48h
0x180015ad2  pop     r14
0x180015ad4  pop     rdi
0x180015ad5  pop     rsi
0x180015ad6  pop     rbx
0x180015ad7  retn
```
