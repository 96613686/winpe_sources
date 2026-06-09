# CSWbemPrivilegeSet::~CSWbemPrivilegeSet(void)

- ea: `0x18000f7d0`
- end: `0x18000f8d1`
- name: `??1CSWbemPrivilegeSet@@UEAA@XZ`
- size: `257`
- prototype: `void __fastcall(CSWbemPrivilegeSet *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18000e9a0`
- `0x18002f0c0`
- `0x180034e70`
- `0x1800359bc`

## callees

- `0x18000f7d0`
- `0x18000fa40`
- `0x18000fa98`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000f86f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f86f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000f847`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000f847`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CSWbemPrivilegeSet::~CSWbemPrivilegeSet(CSWbemPrivilegeSet *this, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 **v5; // rax
  __int64 *v6; // r8
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rdi
  __int64 *v10; // [rsp+30h] [rbp+8h] BYREF

  *(_QWORD *)this = &CSWbemPrivilegeSet::`vftable'{for `ISWbemPrivilegeSet'};
  *((_QWORD *)this + 1) = &CSWbemPrivilegeSet::`vftable'{for `ISupportErrorInfo'};
  *((_QWORD *)this + 2) = &CSWbemPrivilegeSet::`vftable'{for `IProvideClassInfo'};
  while ( 1 )
  {
    v5 = (__int64 **)*((_QWORD *)this + 14);
    v6 = *v5;
    if ( *v5 == (__int64 *)v5 )
      break;
    v9 = v6[5];
    std::_Tree<std::_Tmap_traits<enum WbemPrivilegeEnum,CSWbemPrivilege *,std::less<int>,CWbemAllocator<CSWbemPrivilege *>,0>>::erase(
      (__int64 ***)this + 14,
      &v10,
      v6);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  _InterlockedDecrement(&g_cObj);
  std::_Tree<std::_Tmap_traits<enum WbemPrivilegeEnum,CSWbemPrivilege *,std::less<int>,CWbemAllocator<CSWbemPrivilege *>,0>>::_Erase(
    (char *)this + 112,
    *(_QWORD *)(*((_QWORD *)this + 14) + 8LL),
    v6,
    a4);
  *(_QWORD *)(*((_QWORD *)this + 14) + 8LL) = *((_QWORD *)this + 14);
  **((_QWORD **)this + 14) = *((_QWORD *)this + 14);
  *(_QWORD *)(*((_QWORD *)this + 14) + 16LL) = *((_QWORD *)this + 14);
  *((_QWORD *)this + 15) = 0;
  CWin32DefaultArena::WbemMemFree(*((void **)this + 14));
  *((_QWORD *)this + 4) = &CDispatchHelp::`vftable';
  v7 = *((_QWORD *)this + 7);
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    *((_QWORD *)this + 7) = 0;
  }
  v8 = *((_QWORD *)this + 8);
  if ( v8 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    *((_QWORD *)this + 8) = 0;
  }
  SysFreeString(*((BSTR *)this + 5));
}

```

## disassembly

```asm
0x18000f7d0  mov     [rsp+arg_8], rbx
0x18000f7d5  mov     [rsp+arg_10], rsi
0x18000f7da  push    rdi
0x18000f7db  sub     rsp, 20h
0x18000f7df  mov     rbx, rcx
0x18000f7e2  lea     rax, ??_7CSWbemPrivilegeSet@@6BISWbemPrivilegeSet@@@; const CSWbemPrivilegeSet::`vftable'{for `ISWbemPrivilegeSet'}
0x18000f7e9  mov     [rcx], rax
0x18000f7ec  lea     rax, ??_7CSWbemPrivilegeSet@@6BISupportErrorInfo@@@; const CSWbemPrivilegeSet::`vftable'{for `ISupportErrorInfo'}
0x18000f7f3  mov     [rcx+8], rax
0x18000f7f7  lea     rax, ??_7CSWbemPrivilegeSet@@6BIProvideClassInfo@@@; const CSWbemPrivilegeSet::`vftable'{for `IProvideClassInfo'}
0x18000f7fe  mov     [rcx+10h], rax
0x18000f802  mov     rax, [rbx+70h]
0x18000f806  mov     r8, [rax]
0x18000f809  cmp     r8, rax
0x18000f80c  jnz     short loc_18000F886
0x18000f80e  lock dec cs:?g_cObj@@3JA; long g_cObj
0x18000f815  mov     rdx, [rbx+70h]
0x18000f819  mov     rdx, [rdx+8]
0x18000f81d  lea     rcx, [rbx+70h]
0x18000f821  call    ?_Erase@?$_Tree@V?$_Tmap_traits@W4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@U?$less@H@std@@V?$CWbemAllocator@PEAVCSWbemPrivilege@@@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBW4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<WbemPrivilegeEnum,CSWbemPrivilege *,std::less<int>,CWbemAllocator<CSWbemPrivilege *>,0>>::_Erase(std::_Tree_node<std::pair<WbemPrivilegeEnum const,CSWbemPrivilege *>,void *> *)
0x18000f826  mov     rax, [rbx+70h]
0x18000f82a  mov     [rax+8], rax
0x18000f82e  mov     rax, [rbx+70h]
0x18000f832  mov     [rax], rax
0x18000f835  mov     rax, [rbx+70h]
0x18000f839  mov     [rax+10h], rax
0x18000f83d  xor     edi, edi
0x18000f83f  mov     [rbx+78h], rdi
0x18000f843  mov     rcx, [rbx+70h]
0x18000f847  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000f84d  nop
0x18000f84e  lea     rax, ??_7CDispatchHelp@@6B@; const CDispatchHelp::`vftable'
0x18000f855  mov     [rbx+20h], rax
0x18000f859  mov     rcx, [rbx+38h]
0x18000f85d  test    rcx, rcx
0x18000f860  jnz     short loc_18000F8AC
0x18000f862  mov     rcx, [rbx+40h]
0x18000f866  test    rcx, rcx
0x18000f869  jnz     short loc_18000F8BE
0x18000f86b  mov     rcx, [rbx+28h]; bstrString
0x18000f86f  call    cs:__imp_SysFreeString
0x18000f875  nop
0x18000f876  mov     rbx, [rsp+28h+arg_8]
0x18000f87b  mov     rsi, [rsp+28h+arg_10]
0x18000f880  add     rsp, 20h
0x18000f884  pop     rdi
0x18000f885  retn
0x18000f886  mov     rdi, [r8+28h]
0x18000f88a  lea     rdx, [rsp+28h+arg_0]
0x18000f88f  lea     rcx, [rbx+70h]
0x18000f893  call    ?erase@?$_Tree@V?$_Tmap_traits@W4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@U?$less@H@std@@V?$CWbemAllocator@PEAVCSWbemPrivilege@@@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@@std@@@std@@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<WbemPrivilegeEnum,CSWbemPrivilege *,std::less<int>,CWbemAllocator<CSWbemPrivilege *>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<WbemPrivilegeEnum const,CSWbemPrivilege *>>>>)
0x18000f898  mov     rax, [rdi]
0x18000f89b  mov     rcx, rdi
0x18000f89e  mov     rax, [rax+10h]
0x18000f8a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8a7  jmp     loc_18000F802
0x18000f8ac  mov     rax, [rcx]
0x18000f8af  mov     rax, [rax+10h]
0x18000f8b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8b8  mov     [rbx+38h], rdi
0x18000f8bc  jmp     short loc_18000F862
0x18000f8be  mov     rax, [rcx]
0x18000f8c1  mov     rax, [rax+10h]
0x18000f8c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8ca  mov     [rbx+40h], rdi
0x18000f8ce  jmp     short loc_18000F86B
```
