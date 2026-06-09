# std::_Tree_alloc<0,std::_Tree_base_types<std::pair<WbemPrivilegeEnum const,CSWbemPrivilege *>,CWbemAllocator<CSWbemPrivilege *>>>::_Buyheadnode(void)

- ea: `0x1800197ec`
- end: `0x180019826`
- name: `?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBW4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@@std@@V?$CWbemAllocator@PEAVCSWbemPrivilege@@@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBW4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@@std@@PEAX@2@XZ`
- size: `58`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006850`
- `0x180007bd0`
- `0x180009320`
- `0x18000a270`
- `0x1800103c0`
- `0x180010a9c`
- `0x180011b50`
- `0x1800196b4`
- `0x180030b44`

## callees

- `0x1800197ec`
- `0x18001a848`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800197fa`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800197fa`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *std::_Tree_alloc<0,std::_Tree_base_types<std::pair<enum WbemPrivilegeEnum const,CSWbemPrivilege *>,CWbemAllocator<CSWbemPrivilege *>>>::_Buyheadnode()
{
  _QWORD *result; // rax

  result = CWin32DefaultArena::WbemMemAlloc(0x30u);
  if ( !result )
    std::_Xbad_alloc();
  try
  {
    *result = result;
    result[1] = result;
    result[2] = result;
    *((_WORD *)result + 12) = 257;
  }
  catch ( ... )
  {
    CWin32DefaultArena::WbemMemFree(result);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x1800197ec  mov     [rsp+arg_0], rcx
0x1800197f1  sub     rsp, 28h
0x1800197f5  mov     ecx, 30h ; '0'
0x1800197fa  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180019800  mov     [rsp+28h+arg_0], rax
0x180019805  test    rax, rax
0x180019808  jnz     short loc_180019810
0x18001980a  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180019810  mov     [rax], rax
0x180019813  mov     [rax+8], rax
0x180019817  mov     [rax+10h], rax
0x18001981b  mov     word ptr [rax+18h], 101h
0x180019821  add     rsp, 28h
0x180019825  retn
```
