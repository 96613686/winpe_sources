# std::_Tree<std::_Tmap_traits<WbemPrivilegeEnum,CSWbemPrivilege *,std::less<int>,CWbemAllocator<CSWbemPrivilege *>,0>>::_Erase(std::_Tree_node<std::pair<WbemPrivilegeEnum const,CSWbemPrivilege *>,void *> *)

- ea: `0x18000fa40`
- end: `0x18000fa90`
- name: `?_Erase@?$_Tree@V?$_Tmap_traits@W4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@U?$less@H@std@@V?$CWbemAllocator@PEAVCSWbemPrivilege@@@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBW4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@@std@@PEAX@2@@Z`
- size: `80`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000d980`
- `0x18000e954`
- `0x18000f780`
- `0x18000f7d0`
- `0x18000f8e0`
- `0x18000f920`
- `0x18000fa40`
- `0x18003241c`
- `0x180035358`

## callees

- `0x18000fa40`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000fa70`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000fa70`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall std::_Tree<std::_Tmap_traits<enum WbemPrivilegeEnum,CSWbemPrivilege *,std::less<int>,CWbemAllocator<CSWbemPrivilege *>,0>>::_Erase(
        __int64 a1,
        void *a2,
        __int64 a3,
        __int64 a4)
{
  void *v4; // rdi
  _QWORD *v6; // rbx
  int result; // eax

  v4 = a2;
  v6 = a2;
  if ( !*((_BYTE *)a2 + 25) )
  {
    do
    {
      std::_Tree<std::_Tmap_traits<enum WbemPrivilegeEnum,CSWbemPrivilege *,std::less<int>,CWbemAllocator<CSWbemPrivilege *>,0>>::_Erase(
        a1,
        v6[2],
        a3,
        a4);
      v6 = (_QWORD *)*v6;
      result = CWin32DefaultArena::WbemMemFree(v4);
      v4 = v6;
    }
    while ( !*((_BYTE *)v6 + 25) );
  }
  return result;
}

```

## disassembly

```asm
0x18000fa40  mov     [rsp+arg_0], rbx
0x18000fa45  mov     [rsp+arg_8], rsi
0x18000fa4a  push    rdi
0x18000fa4b  sub     rsp, 20h
0x18000fa4f  mov     rdi, rdx
0x18000fa52  mov     rsi, rcx
0x18000fa55  mov     rbx, rdx
0x18000fa58  cmp     byte ptr [rdx+19h], 0
0x18000fa5c  jnz     short loc_18000FA80
0x18000fa5e  mov     rdx, [rbx+10h]
0x18000fa62  mov     rcx, rsi
0x18000fa65  call    ?_Erase@?$_Tree@V?$_Tmap_traits@W4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@U?$less@H@std@@V?$CWbemAllocator@PEAVCSWbemPrivilege@@@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBW4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<WbemPrivilegeEnum,CSWbemPrivilege *,std::less<int>,CWbemAllocator<CSWbemPrivilege *>,0>>::_Erase(std::_Tree_node<std::pair<WbemPrivilegeEnum const,CSWbemPrivilege *>,void *> *)
0x18000fa6a  mov     rbx, [rbx]
0x18000fa6d  mov     rcx, rdi
0x18000fa70  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000fa76  nop
0x18000fa77  mov     rdi, rbx
0x18000fa7a  cmp     byte ptr [rbx+19h], 0
0x18000fa7e  jz      short loc_18000FA5E
0x18000fa80  mov     rbx, [rsp+28h+arg_0]
0x18000fa85  mov     rsi, [rsp+28h+arg_8]
0x18000fa8a  add     rsp, 20h
0x18000fa8e  pop     rdi
0x18000fa8f  retn
```
