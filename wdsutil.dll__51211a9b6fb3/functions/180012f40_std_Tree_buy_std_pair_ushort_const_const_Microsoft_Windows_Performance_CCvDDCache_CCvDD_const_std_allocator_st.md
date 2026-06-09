# std::_Tree_buy<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::_Buynode<std::pair<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>(std::pair<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *> &&)

- ea: `0x180012f40`
- end: `0x180012f78`
- name: `??$_Buynode@U?$pair@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@?$_Tree_buy@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@1@$$QEAU?$pair@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@1@@Z`
- size: `56`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180015a30`

## callees

- `0x18001cdb8`

## pseudocode

```c
__int64 __fastcall std::_Tree_buy<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>::_Buynode<std::pair<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>(
        __int64 a1,
        _QWORD *a2)
{
  __int64 result; // rax

  result = std::_Tree_buy<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>>::_Buynode0(a1);
  *(_WORD *)(result + 24) = 0;
  *(_QWORD *)(result + 32) = *a2;
  *(_QWORD *)(result + 40) = a2[1];
  return result;
}

```

## disassembly

```asm
0x180012f40  push    rbx
0x180012f42  sub     rsp, 30h
0x180012f46  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180012f4f  mov     rbx, rdx
0x180012f52  call    ?_Buynode0@?$_Tree_buy@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@V?$allocator@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@PEAX@2@XZ; std::_Tree_buy<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>>::_Buynode0(void)
0x180012f57  mov     [rsp+38h+arg_8], rax
0x180012f5c  mov     word ptr [rax+18h], 0
0x180012f62  mov     rcx, [rbx]
0x180012f65  mov     [rax+20h], rcx
0x180012f69  mov     rcx, [rbx+8]
0x180012f6d  mov     [rax+28h], rcx
0x180012f71  add     rsp, 30h
0x180012f75  pop     rbx
0x180012f76  retn
```
