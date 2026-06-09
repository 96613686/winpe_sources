# CWerComReportKeyValueList<&WerpGetNumSigParams(void *,ulong *),&WerpGetSigParamByIndex(void *,ulong,ushort const * *,ushort const * *)>::`vector deleting destructor'(uint)

- ea: `0x180009890`
- end: `0x1800098fb`
- name: `??_E?$CWerComReportKeyValueList@$1?WerpGetNumSigParams@@YAJPEAXPEAK@Z$1?WerpGetSigParamByIndex@@YAJ0KPEAPEBG2@Z@@UEAAPEAXI@Z`
- size: `107`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180001674`
- `0x180007624`
- `0x180009890`
- `0x180013010`

## pseudocode

```c
_QWORD *__fastcall CWerComReportKeyValueList<&long WerpGetNumSigParams(void *,unsigned long *),&long WerpGetSigParamByIndex(void *,unsigned long,unsigned short const * *,unsigned short const * *)>::`vector deleting destructor'(
        _QWORD *Block,
        char a2)
{
  __int64 v4; // rcx

  *Block = &CWerComReportKeyValueList<&long WerpGetNumSigParams(void *,unsigned long *),&long WerpGetSigParamByIndex(void *,unsigned long,unsigned short const * *,unsigned short const * *)>::`vftable'{for `CManagedObj'};
  Block[3] = &CWerComReportKeyValueList<&long WerpGetNumSigParams(void *,unsigned long *),&long WerpGetSigParamByIndex(void *,unsigned long,unsigned short const * *,unsigned short const * *)>::`vftable'{for `IWerKeyValueList'};
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
0x180009890  mov     [rsp+arg_0], rbx
0x180009895  push    rdi
0x180009896  sub     rsp, 20h
0x18000989a  lea     rax, ??_7?$CWerComReportKeyValueList@$1?WerpGetNumSigParams@@YAJPEAXPEAK@Z$1?WerpGetSigParamByIndex@@YAJ0KPEAPEBG2@Z@@6BCManagedObj@@@; const CWerComReportKeyValueList<&WerpGetNumSigParams(void *,ulong *),&WerpGetSigParamByIndex(void *,ulong,ushort const * *,ushort const * *)>::`vftable'{for `CManagedObj'}
0x1800098a1  mov     rbx, rcx
0x1800098a4  mov     [rcx], rax
0x1800098a7  mov     edi, edx
0x1800098a9  lea     rax, ??_7?$CWerComReportKeyValueList@$1?WerpGetNumSigParams@@YAJPEAXPEAK@Z$1?WerpGetSigParamByIndex@@YAJ0KPEAPEBG2@Z@@6BIWerKeyValueList@@@; const CWerComReportKeyValueList<&WerpGetNumSigParams(void *,ulong *),&WerpGetSigParamByIndex(void *,ulong,ushort const * *,ushort const * *)>::`vftable'{for `IWerKeyValueList'}
0x1800098b0  mov     [rcx+18h], rax
0x1800098b4  mov     rcx, [rcx+28h]
0x1800098b8  test    rcx, rcx
0x1800098bb  jz      short loc_1800098C9
0x1800098bd  mov     rax, [rcx]
0x1800098c0  mov     rax, [rax+10h]
0x1800098c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098c9  lea     rax, ??_7CManagedObj@@6B@; const CManagedObj::`vftable'
0x1800098d0  lea     rcx, ?ms_instance@CObjectManager@@1V1@A; this
0x1800098d7  mov     [rbx], rax
0x1800098da  call    ?UnLockServer@CObjectManager@@QEAAXXZ; CObjectManager::UnLockServer(void)
0x1800098df  test    dil, 1
0x1800098e3  jz      short loc_1800098ED
0x1800098e5  mov     rcx, rbx; Block
0x1800098e8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800098ed  mov     rax, rbx
0x1800098f0  mov     rbx, [rsp+28h+arg_0]
0x1800098f5  add     rsp, 20h
0x1800098f9  pop     rdi
0x1800098fa  retn
```
