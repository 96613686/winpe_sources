# CWerComReportKeyValueList<&WerComListConstCountFunc<54>(void *,ulong *),&WerpGetDynamicParameter(void *,ulong,ushort const * *,ushort const * *)>::`vector deleting destructor'(uint)

- ea: `0x180009810`
- end: `0x18000987b`
- name: `??_E?$CWerComReportKeyValueList@$1??$WerComListConstCountFunc@$0DG@@@YAJPEAXPEAK@Z$1?WerpGetDynamicParameter@@YAJ0KPEAPEBG2@Z@@UEAAPEAXI@Z`
- size: `107`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001674`
- `0x180007624`
- `0x180009810`
- `0x180013010`

## pseudocode

```c
_QWORD *__fastcall CWerComReportKeyValueList<&long WerComListConstCountFunc<54>(void *,unsigned long *),&long WerpGetDynamicParameter(void *,unsigned long,unsigned short const * *,unsigned short const * *)>::`vector deleting destructor'(
        _QWORD *Block,
        char a2)
{
  __int64 v4; // rcx

  *Block = &CWerComReportKeyValueList<&long WerComListConstCountFunc<54>(void *,unsigned long *),&long WerpGetDynamicParameter(void *,unsigned long,unsigned short const * *,unsigned short const * *)>::`vftable'{for `CManagedObj'};
  Block[3] = &CWerComReportKeyValueList<&long WerComListConstCountFunc<54>(void *,unsigned long *),&long WerpGetDynamicParameter(void *,unsigned long,unsigned short const * *,unsigned short const * *)>::`vftable'{for `IWerKeyValueList'};
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
0x180009810  mov     [rsp+arg_0], rbx
0x180009815  push    rdi
0x180009816  sub     rsp, 20h
0x18000981a  lea     rax, ??_7?$CWerComReportKeyValueList@$1??$WerComListConstCountFunc@$0DG@@@YAJPEAXPEAK@Z$1?WerpGetDynamicParameter@@YAJ0KPEAPEBG2@Z@@6BCManagedObj@@@; const CWerComReportKeyValueList<&WerComListConstCountFunc<54>(void *,ulong *),&WerpGetDynamicParameter(void *,ulong,ushort const * *,ushort const * *)>::`vftable'{for `CManagedObj'}
0x180009821  mov     rbx, rcx
0x180009824  mov     [rcx], rax
0x180009827  mov     edi, edx
0x180009829  lea     rax, ??_7?$CWerComReportKeyValueList@$1??$WerComListConstCountFunc@$0DG@@@YAJPEAXPEAK@Z$1?WerpGetDynamicParameter@@YAJ0KPEAPEBG2@Z@@6BIWerKeyValueList@@@; const CWerComReportKeyValueList<&WerComListConstCountFunc<54>(void *,ulong *),&WerpGetDynamicParameter(void *,ulong,ushort const * *,ushort const * *)>::`vftable'{for `IWerKeyValueList'}
0x180009830  mov     [rcx+18h], rax
0x180009834  mov     rcx, [rcx+28h]
0x180009838  test    rcx, rcx
0x18000983b  jz      short loc_180009849
0x18000983d  mov     rax, [rcx]
0x180009840  mov     rax, [rax+10h]
0x180009844  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009849  lea     rax, ??_7CManagedObj@@6B@; const CManagedObj::`vftable'
0x180009850  lea     rcx, ?ms_instance@CObjectManager@@1V1@A; this
0x180009857  mov     [rbx], rax
0x18000985a  call    ?UnLockServer@CObjectManager@@QEAAXXZ; CObjectManager::UnLockServer(void)
0x18000985f  test    dil, 1
0x180009863  jz      short loc_18000986D
0x180009865  mov     rcx, rbx; Block
0x180009868  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000986d  mov     rax, rbx
0x180009870  mov     rbx, [rsp+28h+arg_0]
0x180009875  add     rsp, 20h
0x180009879  pop     rdi
0x18000987a  retn
```
