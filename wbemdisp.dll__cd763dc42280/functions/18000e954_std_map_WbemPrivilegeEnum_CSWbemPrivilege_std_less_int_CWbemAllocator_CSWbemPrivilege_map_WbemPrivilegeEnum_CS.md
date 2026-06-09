# std::map<WbemPrivilegeEnum,CSWbemPrivilege *,std::less<int>,CWbemAllocator<CSWbemPrivilege *>>::~map<WbemPrivilegeEnum,CSWbemPrivilege *,std::less<int>,CWbemAllocator<CSWbemPrivilege *>>(void)

- ea: `0x18000e954`
- end: `0x18000e995`
- name: `??1?$map@W4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@U?$less@H@std@@V?$CWbemAllocator@PEAVCSWbemPrivilege@@@@@std@@QEAA@XZ`
- size: `65`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180034960`
- `0x180034a80`
- `0x180034bc0`
- `0x180034cb0`
- `0x180034e10`
- `0x180035040`
- `0x1800351c0`

## callees

- `0x18000fa40`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000e988`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000e988`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
int __fastcall std::map<enum WbemPrivilegeEnum,CSWbemPrivilege *,std::less<int>,CWbemAllocator<CSWbemPrivilege *>>::~map<enum WbemPrivilegeEnum,CSWbemPrivilege *,std::less<int>,CWbemAllocator<CSWbemPrivilege *>>(
        void **a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  std::_Tree<std::_Tmap_traits<enum WbemPrivilegeEnum,CSWbemPrivilege *,std::less<int>,CWbemAllocator<CSWbemPrivilege *>,0>>::_Erase(
    (__int64)a1,
    *((void **)*a1 + 1),
    a3,
    a4);
  *((_QWORD *)*a1 + 1) = *a1;
  *(_QWORD *)*a1 = *a1;
  *((_QWORD *)*a1 + 2) = *a1;
  a1[1] = 0;
  return CWin32DefaultArena::WbemMemFree(*a1);
}

```

## disassembly

```asm
0x18000e954  push    rbx
0x18000e956  sub     rsp, 20h
0x18000e95a  mov     rbx, rcx
0x18000e95d  mov     rdx, [rcx]
0x18000e960  mov     rdx, [rdx+8]
0x18000e964  call    ?_Erase@?$_Tree@V?$_Tmap_traits@W4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@U?$less@H@std@@V?$CWbemAllocator@PEAVCSWbemPrivilege@@@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBW4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<WbemPrivilegeEnum,CSWbemPrivilege *,std::less<int>,CWbemAllocator<CSWbemPrivilege *>,0>>::_Erase(std::_Tree_node<std::pair<WbemPrivilegeEnum const,CSWbemPrivilege *>,void *> *)
0x18000e969  mov     rax, [rbx]
0x18000e96c  mov     [rax+8], rax
0x18000e970  mov     rax, [rbx]
0x18000e973  mov     [rax], rax
0x18000e976  mov     rax, [rbx]
0x18000e979  mov     [rax+10h], rax
0x18000e97d  mov     qword ptr [rbx+8], 0
0x18000e985  mov     rcx, [rbx]
0x18000e988  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000e98e  nop
0x18000e98f  add     rsp, 20h
0x18000e993  pop     rbx
0x18000e994  retn
```
