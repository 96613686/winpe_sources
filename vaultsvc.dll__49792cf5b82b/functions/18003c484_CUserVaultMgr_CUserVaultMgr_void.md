# CUserVaultMgr::~CUserVaultMgr(void)

- ea: `0x18003c484`
- end: `0x18003c4da`
- name: `??1CUserVaultMgr@@QEAA@XZ`
- size: `86`
- prototype: `void __fastcall(CUserVaultMgr *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18002f150`

## callees

- `0x18002eb70`
- `0x18003c454`
- `0x18003c484`

## import_xrefs

- `ntdll!RtlDeleteResource` at `0x18003c4c6`
- `ntdll!RtlDeleteResource` at `0x18003c4c6`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18003c4a3`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18003c4a3`

## pseudocode

```c
void __fastcall CUserVaultMgr::~CUserVaultMgr(CUserVaultMgr *this)
{
  *(_QWORD *)this = &CUserVaultMgr::`vftable';
  if ( *((_QWORD *)this + 22) )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion();
    *((_QWORD *)this + 22) = 0;
  }
  CUserVaultMgr::Delete(this);
  if ( *((_BYTE *)this + 71) )
    RtlDeleteResource((PRTL_RESOURCE)((char *)this + 72));
  std::_Tree<std::_Tmap_traits<_GUID,CUserVault *,GuidCmp,std::allocator<std::pair<_GUID const,CUserVault *>>,0>>::~_Tree<std::_Tmap_traits<_GUID,CUserVault *,GuidCmp,std::allocator<std::pair<_GUID const,CUserVault *>>,0>>((char *)this + 16);
}

```

## disassembly

```asm
0x18003c484  push    rbx
0x18003c486  sub     rsp, 20h
0x18003c48a  mov     rbx, rcx
0x18003c48d  lea     rax, ??_7CUserVaultMgr@@6B@; const CUserVaultMgr::`vftable'
0x18003c494  mov     [rcx], rax
0x18003c497  mov     rcx, [rcx+0B0h]
0x18003c49e  test    rcx, rcx
0x18003c4a1  jz      short loc_18003C4B4
0x18003c4a3  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18003c4a9  mov     qword ptr [rbx+0B0h], 0
0x18003c4b4  mov     rcx, rbx; this
0x18003c4b7  call    ?Delete@CUserVaultMgr@@QEAAXXZ; CUserVaultMgr::Delete(void)
0x18003c4bc  cmp     byte ptr [rbx+47h], 0
0x18003c4c0  jz      short loc_18003C4CC
0x18003c4c2  lea     rcx, [rbx+48h]; Resource
0x18003c4c6  call    cs:__imp_RtlDeleteResource
0x18003c4cc  lea     rcx, [rbx+10h]
0x18003c4d0  add     rsp, 20h
0x18003c4d4  pop     rbx
0x18003c4d5  jmp     ??1?$_Tree@V?$_Tmap_traits@U_GUID@@PEAVCUserVault@@UGuidCmp@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVCUserVault@@@std@@@std@@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<_GUID,CUserVault *,GuidCmp,std::allocator<std::pair<_GUID const,CUserVault *>>,0>>::~_Tree<std::_Tmap_traits<_GUID,CUserVault *,GuidCmp,std::allocator<std::pair<_GUID const,CUserVault *>>,0>>(void)
```
