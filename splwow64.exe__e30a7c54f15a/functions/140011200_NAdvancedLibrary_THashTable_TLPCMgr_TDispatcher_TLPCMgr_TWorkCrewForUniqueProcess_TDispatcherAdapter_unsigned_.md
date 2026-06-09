# NAdvancedLibrary::THashTable<TLPCMgr::TDispatcher,TLPCMgr::TWorkCrewForUniqueProcess::TDispatcherAdapter,unsigned __int64,NAdvancedLibrary::TCopyCritsec,NAdvancedLibrary::TDefaultLockAdaptor>::Delete(NAdvancedLibrary::THashElementBase *)

- ea: `0x140011200`
- end: `0x14001125f`
- name: `?Delete@?$THashTable@VTDispatcher@TLPCMgr@@VTDispatcherAdapter@TWorkCrewForUniqueProcess@2@_KVTCopyCritsec@NAdvancedLibrary@@VTDefaultLockAdaptor@6@@NAdvancedLibrary@@KAXPEAVTHashElementBase@2@@Z`
- size: `95`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x140001b90`
- `0x140011200`
- `0x140016010`

## pseudocode

```c
void __fastcall NAdvancedLibrary::THashTable<TLPCMgr::TDispatcher,TLPCMgr::TWorkCrewForUniqueProcess::TDispatcherAdapter,unsigned __int64,NAdvancedLibrary::TCopyCritsec,NAdvancedLibrary::TDefaultLockAdaptor>::Delete(
        _QWORD *Block)
{
  volatile signed __int32 *v1; // rdx
  signed __int32 v3; // r8d

  if ( Block )
  {
    v1 = (volatile signed __int32 *)Block[4];
    if ( v1 )
    {
      do
        v3 = *((_DWORD *)v1 + 2);
      while ( v3 != 0x7FFFFFFF && v3 != _InterlockedCompareExchange(v1 + 2, v3 - 1, v3) );
      if ( v3 == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v1 + 8LL))(v1);
    }
    operator delete(Block);
  }
}

```

## disassembly

```asm
0x140011200  test    rcx, rcx
0x140011203  jz      short locret_14001125E
0x140011205  push    rbx
0x140011206  sub     rsp, 20h
0x14001120a  mov     rdx, [rcx+20h]
0x14001120e  mov     rbx, rcx
0x140011211  test    rdx, rdx
0x140011214  jz      short loc_14001124C
0x140011216  mov     r9d, 7FFFFFFFh
0x14001121c  jmp     short loc_14001122C
0x14001121e  lea     ecx, [r8-1]
0x140011222  mov     eax, r8d
0x140011225  lock cmpxchg [rdx+8], ecx
0x14001122a  jz      short loc_140011235
0x14001122c  mov     r8d, [rdx+8]
0x140011230  cmp     r8d, r9d
0x140011233  jnz     short loc_14001121E
0x140011235  lea     eax, [r8-1]
0x140011239  test    eax, eax
0x14001123b  jnz     short loc_14001124C
0x14001123d  mov     rax, [rdx]
0x140011240  mov     rcx, rdx
0x140011243  mov     rax, [rax+8]
0x140011247  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001124c  mov     edx, 28h ; '('
0x140011251  mov     rcx, rbx; Block
0x140011254  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140011259  add     rsp, 20h
0x14001125d  pop     rbx
0x14001125e  retn
```
