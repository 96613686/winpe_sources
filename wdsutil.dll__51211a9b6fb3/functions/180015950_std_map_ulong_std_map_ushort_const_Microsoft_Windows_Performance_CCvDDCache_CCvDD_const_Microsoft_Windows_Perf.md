# std::map<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<ulong>,std::allocator<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>>::operator[](ulong const &)

- ea: `0x180015950`
- end: `0x180015a28`
- name: `??A?$map@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@@std@@QEAAAEAV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@1@AEBK@Z`
- size: `216`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180015e34`
- `0x180016248`
- `0x180018de8`

## callees

- `0x180012ecc`
- `0x1800138cc`
- `0x1800150fc`
- `0x180015950`
- `0x18001cc68`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 *__fastcall std::map<unsigned long,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>::operator[](
        __int64 **a1,
        int *a2)
{
  __int64 *v4; // rax
  __int64 *v5; // rbx
  __int64 v6; // rax
  unsigned __int64 v8; // [rsp+38h] [rbp-40h] BYREF
  __int64 v9; // [rsp+40h] [rbp-38h]
  int v10; // [rsp+48h] [rbp-30h] BYREF
  __int128 v11; // [rsp+50h] [rbp-28h] BYREF
  __int64 *v12; // [rsp+A0h] [rbp+28h] BYREF

  v4 = (__int64 *)(*a1)[1];
  v5 = *a1;
  while ( !*((_BYTE *)v4 + 25) )
  {
    if ( *((_DWORD *)v4 + 8) >= (unsigned int)*a2 )
    {
      v5 = v4;
      v4 = (__int64 *)*v4;
    }
    else
    {
      v4 = (__int64 *)v4[2];
    }
  }
  if ( v5 == *a1 || (unsigned int)*a2 < *((_DWORD *)v5 + 8) )
  {
    v9 = 0;
    v8 = std::_Tree_alloc<0,std::_Tree_base_types<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>>>::_Buyheadnode();
    v10 = *a2;
    v11 = v8;
    v8 = std::_Tree_alloc<0,std::_Tree_base_types<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>>>::_Buyheadnode();
    v9 = 0;
    v6 = std::_Tree_buy<std::pair<unsigned long const,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>::_Buynode<std::pair<unsigned long,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>(
           a1,
           &v10);
    std::_Tree<std::_Tmap_traits<unsigned long,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>,0>>::_Insert_hint<std::pair<unsigned long const,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>> &,std::_Tree_node<std::pair<unsigned long const,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,void *> *>(
      (_DWORD)a1,
      (unsigned int)&v12,
      (_DWORD)v5,
      v6 + 32,
      v6);
    v5 = v12;
    std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::~_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>((void **)&v11);
    std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::~_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>((void **)&v8);
  }
  return v5 + 5;
}

```

## disassembly

```asm
0x180015950  push    rbp
0x180015952  push    rbx
0x180015953  push    rsi
0x180015954  push    rdi
0x180015955  mov     rbp, rsp
0x180015958  sub     rsp, 78h
0x18001595c  mov     [rbp+var_48], 0FFFFFFFFFFFFFFFEh
0x180015964  mov     rdi, rdx
0x180015967  mov     rsi, rcx
0x18001596a  mov     r8, [rcx]
0x18001596d  mov     rax, [r8+8]
0x180015971  mov     rbx, r8
0x180015974  xor     edx, edx
0x180015976  cmp     [rax+19h], dl
0x180015979  jnz     short loc_180015993
0x18001597b  mov     ecx, [rdi]
0x18001597d  cmp     [rax+20h], ecx
0x180015980  jnb     short loc_180015988
0x180015982  mov     rax, [rax+10h]
0x180015986  jmp     short loc_18001598E
0x180015988  mov     rbx, rax
0x18001598b  mov     rax, [rax]
0x18001598e  cmp     [rax+19h], dl
0x180015991  jz      short loc_18001597D
0x180015993  cmp     rbx, r8
0x180015996  jz      short loc_18001599F
0x180015998  mov     eax, [rbx+20h]
0x18001599b  cmp     [rdi], eax
0x18001599d  jnb     short loc_180015A1A
0x18001599f  mov     [rbp+var_40], rdx
0x1800159a3  mov     [rbp+var_38], rdx
0x1800159a7  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@V?$allocator@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>>>::_Buyheadnode(void)
0x1800159ac  mov     [rbp+var_40], rax
0x1800159b0  mov     eax, [rdi]
0x1800159b2  mov     [rbp+var_30], eax
0x1800159b5  xorps   xmm0, xmm0
0x1800159b8  movdqu  [rbp+var_28], xmm0
0x1800159bd  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@V?$allocator@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>>>::_Buyheadnode(void)
0x1800159c2  nop
0x1800159c3  mov     rcx, [rbp+var_40]
0x1800159c7  mov     qword ptr [rbp+var_28], rcx
0x1800159cb  mov     [rbp+var_40], rax
0x1800159cf  mov     rcx, qword ptr [rbp+var_28+8]
0x1800159d3  mov     rax, [rbp+var_38]
0x1800159d7  mov     qword ptr [rbp+var_28+8], rax
0x1800159db  mov     [rbp+var_38], rcx
0x1800159df  lea     rdx, [rbp+var_30]
0x1800159e3  mov     rcx, rsi
0x1800159e6  call    ??$_Buynode@U?$pair@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@?$_Tree_buy@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@PEAX@1@$$QEAU?$pair@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@1@@Z; std::_Tree_buy<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>::_Buynode<std::pair<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>(std::pair<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>> &&)
0x1800159eb  lea     r9, [rax+20h]
0x1800159ef  mov     [rsp+78h+var_58], rax
0x1800159f4  mov     r8, rbx
0x1800159f7  lea     rdx, [rbp+arg_0]
0x1800159fb  mov     rcx, rsi
0x1800159fe  call    ??$_Insert_hint@AEAU?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@PEAU?$_Tree_node@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@$0A@@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@@1@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@@1@AEAU?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@PEAX@1@@Z
0x180015a03  mov     rbx, [rbp+arg_0]
0x180015a07  lea     rcx, [rbp+var_28]
0x180015a0b  call    ??1?$_Tree@V?$_Tmap_traits@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::~_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>(void)
0x180015a10  nop
0x180015a11  lea     rcx, [rbp+var_40]
0x180015a15  call    ??1?$_Tree@V?$_Tmap_traits@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::~_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>(void)
0x180015a1a  lea     rax, [rbx+28h]
0x180015a1e  add     rsp, 78h
0x180015a22  pop     rdi
0x180015a23  pop     rsi
0x180015a24  pop     rbx
0x180015a25  pop     rbp
0x180015a26  retn
```
