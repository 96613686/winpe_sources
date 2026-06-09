# std::_Tree_buy<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,std::allocator<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>>::_Buynode0(void)

- ea: `0x18001cd64`
- end: `0x18001cdb1`
- name: `?_Buynode0@?$_Tree_buy@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@PEAX@2@XZ`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180012ecc`

## callees

- `0x180001374`
- `0x180001518`
- `0x18001cd64`

## pseudocode

```c
_QWORD *__fastcall std::_Tree_buy<std::pair<unsigned long const,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>::_Buynode0(
        _QWORD *a1)
{
  _QWORD *result; // rax

  result = operator new(0x38u);
  if ( !result )
    std::_Xbad_alloc();
  *result = *a1;
  result[1] = *a1;
  result[2] = *a1;
  return result;
}

```

## disassembly

```asm
0x18001cd64  push    rbx
0x18001cd66  sub     rsp, 30h
0x18001cd6a  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18001cd73  mov     rbx, rcx
0x18001cd76  mov     ecx, 38h ; '8'; Size
0x18001cd7b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001cd80  mov     rdx, rax
0x18001cd83  mov     [rsp+38h+arg_8], rax
0x18001cd88  test    rax, rax
0x18001cd8b  jz      short loc_18001CDAB
0x18001cd8d  mov     rax, [rbx]
0x18001cd90  mov     [rdx], rax
0x18001cd93  mov     rax, [rbx]
0x18001cd96  mov     [rdx+8], rax
0x18001cd9a  mov     rax, [rbx]
0x18001cd9d  mov     [rdx+10h], rax
0x18001cda1  mov     rax, rdx
0x18001cda4  add     rsp, 30h
0x18001cda8  pop     rbx
0x18001cda9  retn
0x18001cdab  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
