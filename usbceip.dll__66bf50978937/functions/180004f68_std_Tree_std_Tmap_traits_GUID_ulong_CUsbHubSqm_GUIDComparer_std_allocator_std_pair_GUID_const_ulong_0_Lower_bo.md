# std::_Tree<std::_Tmap_traits<_GUID,ulong,CUsbHubSqm::GUIDComparer,std::allocator<std::pair<_GUID const,ulong>>,0>>::_Lower_bound_duplicate<_GUID>(std::_Tree_node<std::pair<_GUID const,ulong>,void *> * const,_GUID const &)

- ea: `0x180004f68`
- end: `0x180004f90`
- name: `??$_Lower_bound_duplicate@U_GUID@@@?$_Tree@V?$_Tmap_traits@U_GUID@@KUGUIDComparer@CUsbHubSqm@@V?$allocator@U?$pair@$$CBU_GUID@@K@std@@@std@@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBU_GUID@@K@std@@PEAX@1@AEBU_GUID@@@Z`
- size: `40`
- prototype: `bool __fastcall(__int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004f98`
- `0x180005258`

## callees

- `0x180004f68`
- `0x1800051e0`

## pseudocode

```c
bool __fastcall std::_Tree<std::_Tmap_traits<_GUID,unsigned long,CUsbHubSqm::GUIDComparer,std::allocator<std::pair<_GUID const,unsigned long>>,0>>::_Lower_bound_duplicate<_GUID>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  return !*(_BYTE *)(a2 + 25) && !(unsigned __int8)CUsbHubSqm::GUIDComparer::operator()(a1, a3, a2 + 28);
}

```

## disassembly

```asm
0x180004f68  sub     rsp, 28h
0x180004f6c  cmp     byte ptr [rdx+19h], 0
0x180004f70  mov     rax, r8
0x180004f73  jnz     short loc_180004F89
0x180004f75  lea     r8, [rdx+1Ch]
0x180004f79  mov     rdx, rax
0x180004f7c  call    ??RGUIDComparer@CUsbHubSqm@@QEBA_NAEBU_GUID@@0@Z; CUsbHubSqm::GUIDComparer::operator()(_GUID const &,_GUID const &)
0x180004f81  test    al, al
0x180004f83  jnz     short loc_180004F89
0x180004f85  mov     al, 1
0x180004f87  jmp     short loc_180004F8B
0x180004f89  xor     al, al
0x180004f8b  add     rsp, 28h
0x180004f8f  retn
```
