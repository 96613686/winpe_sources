# CSWbemPrivilegeSet::`scalar deleting destructor'(uint)

- ea: `0x18000f920`
- end: `0x18000fa2d`
- name: `??_GCSWbemPrivilegeSet@@UEAAPEAXI@Z`
- size: `269`
- prototype: `void *__fastcall(CSWbemPrivilegeSet *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x18000f920`
- `0x18000fa40`
- `0x18000fa98`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000f9bf`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f9bf`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000f997`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000f9cf`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000f997`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000f9cf`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
CSWbemPrivilegeSet *__fastcall CSWbemPrivilegeSet::`scalar deleting destructor'(
        CSWbemPrivilegeSet *this,
        char a2,
        __int64 a3,
        __int64 a4)
{
  __int64 **v6; // rax
  __int64 *v7; // r8
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v11; // rdi
  __int64 *v12; // [rsp+50h] [rbp+8h] BYREF

  *(_QWORD *)this = &CSWbemPrivilegeSet::`vftable'{for `ISWbemPrivilegeSet'};
  *((_QWORD *)this + 1) = &CSWbemPrivilegeSet::`vftable'{for `ISupportErrorInfo'};
  *((_QWORD *)this + 2) = &CSWbemPrivilegeSet::`vftable'{for `IProvideClassInfo'};
  while ( 1 )
  {
    v6 = (__int64 **)*((_QWORD *)this + 14);
    v7 = *v6;
    if ( *v6 == (__int64 *)v6 )
      break;
    v11 = v7[5];
    std::_Tree<std::_Tmap_traits<enum WbemPrivilegeEnum,CSWbemPrivilege *,std::less<int>,CWbemAllocator<CSWbemPrivilege *>,0>>::erase(
      (__int64 ***)this + 14,
      &v12,
      v7);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  _InterlockedDecrement(&g_cObj);
  std::_Tree<std::_Tmap_traits<enum WbemPrivilegeEnum,CSWbemPrivilege *,std::less<int>,CWbemAllocator<CSWbemPrivilege *>,0>>::_Erase(
    (__int64)this + 112,
    *(void **)(*((_QWORD *)this + 14) + 8LL),
    (__int64)v7,
    a4);
  *(_QWORD *)(*((_QWORD *)this + 14) + 8LL) = *((_QWORD *)this + 14);
  **((_QWORD **)this + 14) = *((_QWORD *)this + 14);
  *(_QWORD *)(*((_QWORD *)this + 14) + 16LL) = *((_QWORD *)this + 14);
  *((_QWORD *)this + 15) = 0;
  CWin32DefaultArena::WbemMemFree(*((void **)this + 14));
  *((_QWORD *)this + 4) = &CDispatchHelp::`vftable';
  v8 = *((_QWORD *)this + 7);
  if ( v8 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    *((_QWORD *)this + 7) = 0;
  }
  v9 = *((_QWORD *)this + 8);
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    *((_QWORD *)this + 8) = 0;
  }
  SysFreeString(*((BSTR *)this + 5));
  if ( (a2 & 1) != 0 )
    CWin32DefaultArena::WbemMemFree(this);
  return this;
}

```

## disassembly

```asm
0x18000f920  push    rbx
0x18000f922  push    rbp
0x18000f923  push    rsi
0x18000f924  push    rdi
0x18000f925  sub     rsp, 28h
0x18000f929  mov     ebp, edx
0x18000f92b  mov     rbx, rcx
0x18000f92e  lea     rax, ??_7CSWbemPrivilegeSet@@6BISWbemPrivilegeSet@@@; const CSWbemPrivilegeSet::`vftable'{for `ISWbemPrivilegeSet'}
0x18000f935  mov     [rcx], rax
0x18000f938  lea     rax, ??_7CSWbemPrivilegeSet@@6BISupportErrorInfo@@@; const CSWbemPrivilegeSet::`vftable'{for `ISupportErrorInfo'}
0x18000f93f  mov     [rcx+8], rax
0x18000f943  lea     rax, ??_7CSWbemPrivilegeSet@@6BIProvideClassInfo@@@; const CSWbemPrivilegeSet::`vftable'{for `IProvideClassInfo'}
0x18000f94a  mov     [rcx+10h], rax
0x18000f94e  mov     rax, [rbx+70h]
0x18000f952  mov     r8, [rax]
0x18000f955  cmp     r8, rax
0x18000f958  jnz     loc_18000F9E2
0x18000f95e  lock dec cs:?g_cObj@@3JA; long g_cObj
0x18000f965  mov     rdx, [rbx+70h]
0x18000f969  mov     rdx, [rdx+8]
0x18000f96d  lea     rcx, [rbx+70h]
0x18000f971  call    ?_Erase@?$_Tree@V?$_Tmap_traits@W4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@U?$less@H@std@@V?$CWbemAllocator@PEAVCSWbemPrivilege@@@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBW4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<WbemPrivilegeEnum,CSWbemPrivilege *,std::less<int>,CWbemAllocator<CSWbemPrivilege *>,0>>::_Erase(std::_Tree_node<std::pair<WbemPrivilegeEnum const,CSWbemPrivilege *>,void *> *)
0x18000f976  mov     rax, [rbx+70h]
0x18000f97a  mov     [rax+8], rax
0x18000f97e  mov     rax, [rbx+70h]
0x18000f982  mov     [rax], rax
0x18000f985  mov     rax, [rbx+70h]
0x18000f989  mov     [rax+10h], rax
0x18000f98d  xor     edi, edi
0x18000f98f  mov     [rbx+78h], rdi
0x18000f993  mov     rcx, [rbx+70h]
0x18000f997  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000f99d  nop
0x18000f99e  lea     rax, ??_7CDispatchHelp@@6B@; const CDispatchHelp::`vftable'
0x18000f9a5  mov     [rbx+20h], rax
0x18000f9a9  mov     rcx, [rbx+38h]
0x18000f9ad  test    rcx, rcx
0x18000f9b0  jnz     short loc_18000FA08
0x18000f9b2  mov     rcx, [rbx+40h]
0x18000f9b6  test    rcx, rcx
0x18000f9b9  jnz     short loc_18000FA1A
0x18000f9bb  mov     rcx, [rbx+28h]; bstrString
0x18000f9bf  call    cs:__imp_SysFreeString
0x18000f9c5  nop
0x18000f9c6  test    bpl, 1
0x18000f9ca  jz      short loc_18000F9D6
0x18000f9cc  mov     rcx, rbx
0x18000f9cf  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000f9d5  nop
0x18000f9d6  mov     rax, rbx
0x18000f9d9  add     rsp, 28h
0x18000f9dd  pop     rdi
0x18000f9de  pop     rsi
0x18000f9df  pop     rbp
0x18000f9e0  pop     rbx
0x18000f9e1  retn
0x18000f9e2  mov     rdi, [r8+28h]
0x18000f9e6  lea     rdx, [rsp+48h+arg_0]
0x18000f9eb  lea     rcx, [rbx+70h]
0x18000f9ef  call    ?erase@?$_Tree@V?$_Tmap_traits@W4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@U?$less@H@std@@V?$CWbemAllocator@PEAVCSWbemPrivilege@@@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@@std@@@std@@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<WbemPrivilegeEnum,CSWbemPrivilege *,std::less<int>,CWbemAllocator<CSWbemPrivilege *>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<WbemPrivilegeEnum const,CSWbemPrivilege *>>>>)
0x18000f9f4  mov     rax, [rdi]
0x18000f9f7  mov     rcx, rdi
0x18000f9fa  mov     rax, [rax+10h]
0x18000f9fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa03  jmp     loc_18000F94E
0x18000fa08  mov     rax, [rcx]
0x18000fa0b  mov     rax, [rax+10h]
0x18000fa0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa14  mov     [rbx+38h], rdi
0x18000fa18  jmp     short loc_18000F9B2
0x18000fa1a  mov     rax, [rcx]
0x18000fa1d  mov     rax, [rax+10h]
0x18000fa21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa26  mov     [rbx+40h], rdi
0x18000fa2a  jmp     short loc_18000F9BB
```
