# std::_Tree_alloc<0,std::_Tree_base_types<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,std::allocator<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>>>::_Buyheadnode(void)

- ea: `0x18001cc1c`
- end: `0x18001cc5f`
- name: `?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@PEAX@2@XZ`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001486c`

## callees

- `0x180001374`
- `0x180001518`
- `0x18001cc1c`

## pseudocode

```c
_QWORD *std::_Tree_alloc<0,std::_Tree_base_types<std::pair<unsigned long const,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>>::_Buyheadnode()
{
  _QWORD *result; // rax

  result = operator new(0x38u);
  if ( !result )
    std::_Xbad_alloc();
  *result = result;
  result[1] = result;
  result[2] = result;
  *((_WORD *)result + 12) = 257;
  return result;
}

```

## disassembly

```asm
0x18001cc1c  mov     [rsp+arg_0], rcx
0x18001cc21  sub     rsp, 38h
0x18001cc25  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18001cc2e  mov     ecx, 38h ; '8'; Size
0x18001cc33  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001cc38  mov     [rsp+38h+arg_0], rax
0x18001cc3d  test    rax, rax
0x18001cc40  jz      short loc_18001CC59
0x18001cc42  mov     [rax], rax
0x18001cc45  mov     [rax+8], rax
0x18001cc49  mov     [rax+10h], rax
0x18001cc4d  mov     word ptr [rax+18h], 101h
0x18001cc53  add     rsp, 38h
0x18001cc57  retn
0x18001cc59  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
