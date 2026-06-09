# CUserVaultMgr::Delete(void)

- ea: `0x18002eb70`
- end: `0x18002eca6`
- name: `?Delete@CUserVaultMgr@@QEAAXXZ`
- size: `310`
- prototype: `void __fastcall(CUserVaultMgr *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x18003c484`

## callees

- `0x180012210`
- `0x18002eb70`
- `0x18002ecac`
- `0x18002ef94`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ec83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ec83`
- `ntdll!RtlReleaseResource` at `0x18002ec9f`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002eb8a`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002eb8a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CUserVaultMgr::Delete(CUserVaultMgr *this)
{
  struct _RTL_RESOURCE *v2; // rbp
  _QWORD **v3; // rsi
  __int64 v4; // rax
  _QWORD *v5; // rbx
  __int64 v6; // rcx
  __int64 v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  _QWORD *v10; // rcx
  _QWORD *v11; // rbx
  void *v12; // rcx
  __int64 i; // [rsp+60h] [rbp+8h] BYREF

  v2 = (struct _RTL_RESOURCE *)((char *)this + 72);
  RtlAcquireResourceExclusive((PRTL_RESOURCE)((char *)this + 72), 1u);
  v3 = (_QWORD **)((char *)this + 16);
  v4 = **((_QWORD **)this + 2);
  for ( i = v4; ; v4 = i )
  {
    v5 = *v3;
    if ( (_QWORD *)v4 == *v3 )
      break;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v4 + 48) + 8LL))(*(_QWORD *)(v4 + 48));
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,CUserVault *>>>,std::_Iterator_base0>::operator++(&i);
  }
  std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,CUserVault *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<_GUID const,CUserVault *>,void *>>>(
    (char *)this + 16,
    (char *)this + 16,
    v5[1]);
  v5[1] = v5;
  *v5 = v5;
  v5[2] = v5;
  *((_QWORD *)this + 3) = 0;
  v6 = *((_QWORD *)this + 4);
  if ( v6 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
    *((_QWORD *)this + 4) = 0;
  }
  v7 = *((_QWORD *)this + 5);
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
    *((_QWORD *)this + 5) = 0;
  }
  v8 = (void *)*((_QWORD *)this + 6);
  if ( v8 )
  {
    VaultFreeInternal(v8);
    *((_QWORD *)this + 6) = 0;
  }
  v9 = (void *)*((_QWORD *)this + 7);
  if ( v9 )
  {
    VaultFreeInternal(v9);
    *((_QWORD *)this + 7) = 0;
  }
  v10 = (_QWORD *)*((_QWORD *)this + 1);
  if ( v10 )
  {
    do
    {
      v11 = (_QWORD *)v10[1];
      VaultFreeInternal(v10);
      v10 = v11;
    }
    while ( v11 );
  }
  *((_QWORD *)this + 1) = 0;
  v12 = (void *)*((_QWORD *)this + 23);
  if ( v12 )
  {
    CloseHandle(v12);
    *((_QWORD *)this + 23) = 0;
  }
  RtlReleaseResource(v2);
}

```

## disassembly

```asm
0x18002eb70  push    rbx
0x18002eb72  push    rbp
0x18002eb73  push    rsi
0x18002eb74  push    rdi
0x18002eb75  sub     rsp, 38h
0x18002eb79  mov     rdi, rcx
0x18002eb7c  lea     rbp, [rcx+48h]
0x18002eb80  mov     [rsp+58h+var_38], rbp
0x18002eb85  mov     dl, 1; Wait
0x18002eb87  mov     rcx, rbp; Resource
0x18002eb8a  call    cs:__imp_RtlAcquireResourceExclusive
0x18002eb90  mov     [rsp+58h+var_30], 1
0x18002eb95  lea     rsi, [rdi+10h]
0x18002eb99  mov     rax, [rsi]
0x18002eb9c  mov     rax, [rax]
0x18002eb9f  mov     [rsp+58h+arg_0], rax
0x18002eba4  mov     rbx, [rsi]
0x18002eba7  cmp     rax, rbx
0x18002ebaa  jz      short loc_18002EBCD
0x18002ebac  mov     rcx, [rax+30h]
0x18002ebb0  mov     rax, [rcx]
0x18002ebb3  mov     rax, [rax+8]
0x18002ebb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ebbc  lea     rcx, [rsp+58h+arg_0]
0x18002ebc1  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEAVCUserVault@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,CUserVault *>>>,std::_Iterator_base0>::operator++(void)
0x18002ebc6  mov     rax, [rsp+58h+arg_0]
0x18002ebcb  jmp     short loc_18002EBA4
0x18002ebcd  mov     r8, [rbx+8]
0x18002ebd1  mov     rdx, rsi
0x18002ebd4  mov     rcx, rsi
0x18002ebd7  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@PEAVCUserVault@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEAVCUserVault@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@PEAVCUserVault@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@PEAVCUserVault@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,CUserVault *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<_GUID const,CUserVault *>,void *>>>(std::allocator<std::_Tree_node<std::pair<_GUID const,CUserVault *>,void *>> &,std::_Tree_node<std::pair<_GUID const,CUserVault *>,void *> *)
0x18002ebdc  mov     [rbx+8], rbx
0x18002ebe0  mov     [rbx], rbx
0x18002ebe3  mov     [rbx+10h], rbx
0x18002ebe7  mov     qword ptr [rsi+8], 0
0x18002ebef  mov     rcx, [rdi+20h]
0x18002ebf3  test    rcx, rcx
0x18002ebf6  jz      short loc_18002EC0C
0x18002ebf8  mov     rax, [rcx]
0x18002ebfb  mov     rax, [rax+8]
0x18002ebff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec04  mov     qword ptr [rdi+20h], 0
0x18002ec0c  mov     rcx, [rdi+28h]
0x18002ec10  test    rcx, rcx
0x18002ec13  jz      short loc_18002EC29
0x18002ec15  mov     rax, [rcx]
0x18002ec18  mov     rax, [rax+8]
0x18002ec1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec21  mov     qword ptr [rdi+28h], 0
0x18002ec29  mov     rcx, [rdi+30h]; hMem
0x18002ec2d  test    rcx, rcx
0x18002ec30  jz      short loc_18002EC3F
0x18002ec32  call    ?VaultFreeInternal@@YAXPEAE@Z; VaultFreeInternal(uchar *)
0x18002ec37  mov     qword ptr [rdi+30h], 0
0x18002ec3f  mov     rcx, [rdi+38h]; hMem
0x18002ec43  test    rcx, rcx
0x18002ec46  jz      short loc_18002EC55
0x18002ec48  call    ?VaultFreeInternal@@YAXPEAE@Z; VaultFreeInternal(uchar *)
0x18002ec4d  mov     qword ptr [rdi+38h], 0
0x18002ec55  mov     rcx, [rdi+8]; hMem
0x18002ec59  test    rcx, rcx
0x18002ec5c  jz      short loc_18002EC6F
0x18002ec5e  mov     rbx, [rcx+8]
0x18002ec62  call    ?VaultFreeInternal@@YAXPEAE@Z; VaultFreeInternal(uchar *)
0x18002ec67  mov     rcx, rbx
0x18002ec6a  test    rbx, rbx
0x18002ec6d  jnz     short loc_18002EC5E
0x18002ec6f  mov     qword ptr [rdi+8], 0
0x18002ec77  mov     rcx, [rdi+0B8h]; hObject
0x18002ec7e  test    rcx, rcx
0x18002ec81  jz      short loc_18002EC94
0x18002ec83  call    cs:__imp_CloseHandle
0x18002ec89  mov     qword ptr [rdi+0B8h], 0
0x18002ec94  mov     rcx, rbp
0x18002ec97  add     rsp, 38h
0x18002ec9b  pop     rdi
0x18002ec9c  pop     rsi
0x18002ec9d  pop     rbp
0x18002ec9e  pop     rbx
0x18002ec9f  jmp     cs:__imp_RtlReleaseResource
```
