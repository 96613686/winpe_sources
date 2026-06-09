# NAdvancedLibrary::THashTable<TLPCMgr::TDispatcher,TLPCMgr::TWorkCrewForUniqueProcess::TDispatcherAdapter,unsigned __int64,NAdvancedLibrary::TCopyCritsec,NAdvancedLibrary::TDefaultLockAdaptor>::RefCountReturnNode(NAdvancedLibrary::THashElementBase *)

- ea: `0x1400121f0`
- end: `0x140012227`
- name: `?RefCountReturnNode@?$THashTable@VTDispatcher@TLPCMgr@@VTDispatcherAdapter@TWorkCrewForUniqueProcess@2@_KVTCopyCritsec@NAdvancedLibrary@@VTDefaultLockAdaptor@6@@NAdvancedLibrary@@MEBAJPEAVTHashElementBase@2@@Z`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400121f0`

## pseudocode

```c
__int64 __fastcall NAdvancedLibrary::THashTable<TLPCMgr::TDispatcher,TLPCMgr::TWorkCrewForUniqueProcess::TDispatcherAdapter,unsigned __int64,NAdvancedLibrary::TCopyCritsec,NAdvancedLibrary::TDefaultLockAdaptor>::RefCountReturnNode(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // r9
  unsigned int v3; // r8d
  signed __int32 v4; // edx

  v2 = *(_QWORD *)(a2 + 32);
  v3 = 1;
  if ( v2 )
  {
    v3 = 0x7FFFFFFF;
    while ( 1 )
    {
      v4 = *(_DWORD *)(v2 + 8);
      if ( v4 == 0x7FFFFFFF )
        break;
      if ( v4 == _InterlockedCompareExchange((volatile signed __int32 *)(v2 + 8), v4 + 1, v4) )
        return (unsigned int)(v4 + 1);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x1400121f0  mov     r9, [rdx+20h]
0x1400121f4  mov     r8d, 1
0x1400121fa  test    r9, r9
0x1400121fd  jz      short loc_140012223
0x1400121ff  mov     r8d, 7FFFFFFFh
0x140012205  jmp     short loc_140012214
0x140012207  lea     ecx, [rdx+1]
0x14001220a  mov     eax, edx
0x14001220c  lock cmpxchg [r9+8], ecx
0x140012212  jz      short loc_14001221F
0x140012214  mov     edx, [r9+8]
0x140012218  cmp     edx, r8d
0x14001221b  jnz     short loc_140012207
0x14001221d  jmp     short loc_140012223
0x14001221f  lea     r8d, [rdx+1]
0x140012223  mov     eax, r8d
0x140012226  retn
```
