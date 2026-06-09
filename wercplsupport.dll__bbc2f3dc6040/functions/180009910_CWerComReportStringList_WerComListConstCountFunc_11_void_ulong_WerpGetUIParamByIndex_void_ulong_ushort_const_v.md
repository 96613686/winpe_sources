# CWerComReportStringList<&WerComListConstCountFunc<11>(void *,ulong *),&WerpGetUIParamByIndex(void *,ulong,ushort const * *)>::`vector deleting destructor'(uint)

- ea: `0x180009910`
- end: `0x18000997b`
- name: `??_E?$CWerComReportStringList@$1??$WerComListConstCountFunc@$0L@@@YAJPEAXPEAK@Z$1?WerpGetUIParamByIndex@@YAJ0KPEAPEBG@Z@@UEAAPEAXI@Z`
- size: `107`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001674`
- `0x180007624`
- `0x180009910`
- `0x180013010`

## pseudocode

```c
_QWORD *__fastcall CWerComReportStringList<&long WerComListConstCountFunc<11>(void *,unsigned long *),&long WerpGetUIParamByIndex(void *,unsigned long,unsigned short const * *)>::`vector deleting destructor'(
        _QWORD *Block,
        char a2)
{
  __int64 v4; // rcx

  *Block = &CWerComReportStringList<&long WerComListConstCountFunc<11>(void *,unsigned long *),&long WerpGetUIParamByIndex(void *,unsigned long,unsigned short const * *)>::`vftable'{for `CManagedObj'};
  Block[3] = &CWerComReportStringList<&long WerComListConstCountFunc<11>(void *,unsigned long *),&long WerpGetUIParamByIndex(void *,unsigned long,unsigned short const * *)>::`vftable'{for `IWerStringList'};
  v4 = Block[5];
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  *Block = &CManagedObj::`vftable';
  CObjectManager::UnLockServer((CObjectManager *)&CObjectManager::ms_instance);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180009910  mov     [rsp+arg_0], rbx
0x180009915  push    rdi
0x180009916  sub     rsp, 20h
0x18000991a  lea     rax, ??_7?$CWerComReportStringList@$1??$WerComListConstCountFunc@$0L@@@YAJPEAXPEAK@Z$1?WerpGetUIParamByIndex@@YAJ0KPEAPEBG@Z@@6BCManagedObj@@@; const CWerComReportStringList<&WerComListConstCountFunc<11>(void *,ulong *),&WerpGetUIParamByIndex(void *,ulong,ushort const * *)>::`vftable'{for `CManagedObj'}
0x180009921  mov     rbx, rcx
0x180009924  mov     [rcx], rax
0x180009927  mov     edi, edx
0x180009929  lea     rax, ??_7?$CWerComReportStringList@$1??$WerComListConstCountFunc@$0L@@@YAJPEAXPEAK@Z$1?WerpGetUIParamByIndex@@YAJ0KPEAPEBG@Z@@6BIWerStringList@@@; const CWerComReportStringList<&WerComListConstCountFunc<11>(void *,ulong *),&WerpGetUIParamByIndex(void *,ulong,ushort const * *)>::`vftable'{for `IWerStringList'}
0x180009930  mov     [rcx+18h], rax
0x180009934  mov     rcx, [rcx+28h]
0x180009938  test    rcx, rcx
0x18000993b  jz      short loc_180009949
0x18000993d  mov     rax, [rcx]
0x180009940  mov     rax, [rax+10h]
0x180009944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009949  lea     rax, ??_7CManagedObj@@6B@; const CManagedObj::`vftable'
0x180009950  lea     rcx, ?ms_instance@CObjectManager@@1V1@A; this
0x180009957  mov     [rbx], rax
0x18000995a  call    ?UnLockServer@CObjectManager@@QEAAXXZ; CObjectManager::UnLockServer(void)
0x18000995f  test    dil, 1
0x180009963  jz      short loc_18000996D
0x180009965  mov     rcx, rbx; Block
0x180009968  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000996d  mov     rax, rbx
0x180009970  mov     rbx, [rsp+28h+arg_0]
0x180009975  add     rsp, 20h
0x180009979  pop     rdi
0x18000997a  retn
```
