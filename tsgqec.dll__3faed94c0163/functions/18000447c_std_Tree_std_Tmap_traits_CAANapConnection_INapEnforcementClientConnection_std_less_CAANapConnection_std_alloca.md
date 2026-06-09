# std::_Tree<std::_Tmap_traits<CAANapConnection *,INapEnforcementClientConnection *,std::less<CAANapConnection *>,std::allocator<std::pair<CAANapConnection * const,INapEnforcementClientConnection *>>,0>>::_Erase(std::_Tree_node<std::pair<CAANapConnection * const,INapEnforcementClientConnection *>,void *> *)

- ea: `0x18000447c`
- end: `0x1800044cb`
- name: `?_Erase@?$_Tree@V?$_Tmap_traits@PEAVCAANapConnection@@PEAUINapEnforcementClientConnection@@U?$less@PEAVCAANapConnection@@@std@@V?$allocator@U?$pair@QEAVCAANapConnection@@PEAUINapEnforcementClientConnection@@@std@@@4@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@QEAVCAANapConnection@@PEAUINapEnforcementClientConnection@@@std@@PEAX@2@@Z`
- size: `79`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002b84`
- `0x18000447c`

## callees

- `0x18000447c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800044ac`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800044ac`

## pseudocode

```c
void __fastcall std::_Tree<std::_Tmap_traits<CAANapConnection *,INapEnforcementClientConnection *,std::less<CAANapConnection *>,std::allocator<std::pair<CAANapConnection * const,INapEnforcementClientConnection *>>,0>>::_Erase(
        __int64 a1,
        void *a2)
{
  void *v2; // rdi
  _QWORD *v4; // rbx

  v2 = a2;
  v4 = a2;
  if ( !*((_BYTE *)a2 + 25) )
  {
    do
    {
      std::_Tree<std::_Tmap_traits<CAANapConnection *,INapEnforcementClientConnection *,std::less<CAANapConnection *>,std::allocator<std::pair<CAANapConnection * const,INapEnforcementClientConnection *>>,0>>::_Erase(
        a1,
        v4[2]);
      v4 = (_QWORD *)*v4;
      operator delete(v2);
      v2 = v4;
    }
    while ( !*((_BYTE *)v4 + 25) );
  }
}

```

## disassembly

```asm
0x18000447c  mov     [rsp+arg_0], rbx
0x180004481  mov     [rsp+arg_8], rsi
0x180004486  push    rdi
0x180004487  sub     rsp, 20h
0x18000448b  cmp     byte ptr [rdx+19h], 0
0x18000448f  mov     rdi, rdx
0x180004492  mov     rsi, rcx
0x180004495  mov     rbx, rdx
0x180004498  jnz     short loc_1800044BB
0x18000449a  mov     rdx, [rbx+10h]
0x18000449e  mov     rcx, rsi
0x1800044a1  call    ?_Erase@?$_Tree@V?$_Tmap_traits@PEAVCAANapConnection@@PEAUINapEnforcementClientConnection@@U?$less@PEAVCAANapConnection@@@std@@V?$allocator@U?$pair@QEAVCAANapConnection@@PEAUINapEnforcementClientConnection@@@std@@@4@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@QEAVCAANapConnection@@PEAUINapEnforcementClientConnection@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<CAANapConnection *,INapEnforcementClientConnection *,std::less<CAANapConnection *>,std::allocator<std::pair<CAANapConnection * const,INapEnforcementClientConnection *>>,0>>::_Erase(std::_Tree_node<std::pair<CAANapConnection * const,INapEnforcementClientConnection *>,void *> *)
0x1800044a6  mov     rbx, [rbx]
0x1800044a9  mov     rcx, rdi
0x1800044ac  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800044b2  cmp     byte ptr [rbx+19h], 0
0x1800044b6  mov     rdi, rbx
0x1800044b9  jz      short loc_18000449A
0x1800044bb  mov     rbx, [rsp+28h+arg_0]
0x1800044c0  mov     rsi, [rsp+28h+arg_8]
0x1800044c5  add     rsp, 20h
0x1800044c9  pop     rdi
0x1800044ca  retn
```
