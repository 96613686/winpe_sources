# std::_Tree_buy<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,std::allocator<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>>::_Buynode<std::pair<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>(std::pair<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>> &&)

- ea: `0x180012ecc`
- end: `0x180012f37`
- name: `??$_Buynode@U?$pair@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@?$_Tree_buy@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@PEAX@1@$$QEAU?$pair@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@1@@Z`
- size: `107`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180015950`

## callees

- `0x18001cc68`
- `0x18001cd64`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall std::_Tree_buy<std::pair<unsigned long const,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>::_Buynode<std::pair<unsigned long,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>(
        _QWORD *a1,
        unsigned int *a2)
{
  _QWORD *v3; // rbx
  __int64 v4; // rcx
  __int64 v5; // rax
  __int64 v6; // rcx
  _QWORD *result; // rax

  v3 = std::_Tree_buy<std::pair<unsigned long const,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>::_Buynode0(a1);
  *((_WORD *)v3 + 12) = 0;
  v4 = *a2;
  *((_DWORD *)v3 + 8) = v4;
  v3[5] = 0;
  v3[6] = 0;
  try
  {
    v5 = std::_Tree_alloc<0,std::_Tree_base_types<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>>>::_Buyheadnode(v4);
    v3[5] = v5;
    v3[5] = *((_QWORD *)a2 + 1);
    *((_QWORD *)a2 + 1) = v5;
    v6 = v3[6];
    v3[6] = *((_QWORD *)a2 + 2);
    *((_QWORD *)a2 + 2) = v6;
    result = v3;
  }
  catch ( ... )
  {
    std::_Tree_buy<unsigned short const *>::_Freenode0(v6, v3);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x180012ecc  push    rdi
0x180012ece  sub     rsp, 30h
0x180012ed2  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180012edb  mov     [rsp+38h+arg_0], rbx
0x180012ee0  mov     rdi, rdx
0x180012ee3  call    ?_Buynode0@?$_Tree_buy@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@PEAX@2@XZ; std::_Tree_buy<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>::_Buynode0(void)
0x180012ee8  mov     rbx, rax
0x180012eeb  mov     [rsp+38h+arg_8], rax
0x180012ef0  xor     eax, eax
0x180012ef2  mov     [rbx+18h], ax
0x180012ef6  mov     ecx, [rdi]
0x180012ef8  mov     [rbx+20h], ecx
0x180012efb  mov     [rbx+28h], rax
0x180012eff  mov     [rbx+30h], rax
0x180012f03  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@V?$allocator@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>>>::_Buyheadnode(void)
0x180012f08  mov     [rbx+28h], rax
0x180012f0c  mov     rcx, [rdi+8]
0x180012f10  mov     [rbx+28h], rcx
0x180012f14  mov     [rdi+8], rax
0x180012f18  mov     rcx, [rbx+30h]
0x180012f1c  mov     rax, [rdi+10h]
0x180012f20  mov     [rbx+30h], rax
0x180012f24  mov     [rdi+10h], rcx
0x180012f28  mov     rax, rbx
0x180012f2b  mov     rbx, [rsp+38h+arg_0]
0x180012f30  add     rsp, 30h
0x180012f34  pop     rdi
0x180012f35  retn
```
