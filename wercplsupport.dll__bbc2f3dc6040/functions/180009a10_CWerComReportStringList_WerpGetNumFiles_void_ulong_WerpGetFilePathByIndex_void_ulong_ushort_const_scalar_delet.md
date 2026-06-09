# CWerComReportStringList<&WerpGetNumFiles(void *,ulong *),&WerpGetFilePathByIndex(void *,ulong,ushort const * *)>::`scalar deleting destructor'(uint)

- ea: `0x180009a10`
- end: `0x180009a7b`
- name: `??_G?$CWerComReportStringList@$1?WerpGetNumFiles@@YAJPEAXPEAK@Z$1?WerpGetFilePathByIndex@@YAJ0KPEAPEBG@Z@@UEAAPEAXI@Z`
- size: `107`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001674`
- `0x180007624`
- `0x180009a10`
- `0x180013010`

## pseudocode

```c
_QWORD *__fastcall CWerComReportStringList<&long WerpGetNumFiles(void *,unsigned long *),&long WerpGetFilePathByIndex(void *,unsigned long,unsigned short const * *)>::`scalar deleting destructor'(
        _QWORD *Block,
        char a2)
{
  __int64 v4; // rcx

  *Block = &CWerComReportStringList<&long WerpGetNumFiles(void *,unsigned long *),&long WerpGetFilePathByIndex(void *,unsigned long,unsigned short const * *)>::`vftable'{for `CManagedObj'};
  Block[3] = &CWerComReportStringList<&long WerpGetNumFiles(void *,unsigned long *),&long WerpGetFilePathByIndex(void *,unsigned long,unsigned short const * *)>::`vftable'{for `IWerStringList'};
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
0x180009a10  mov     [rsp+arg_0], rbx
0x180009a15  push    rdi
0x180009a16  sub     rsp, 20h
0x180009a1a  lea     rax, ??_7?$CWerComReportStringList@$1?WerpGetNumFiles@@YAJPEAXPEAK@Z$1?WerpGetFilePathByIndex@@YAJ0KPEAPEBG@Z@@6BCManagedObj@@@; const CWerComReportStringList<&WerpGetNumFiles(void *,ulong *),&WerpGetFilePathByIndex(void *,ulong,ushort const * *)>::`vftable'{for `CManagedObj'}
0x180009a21  mov     rbx, rcx
0x180009a24  mov     [rcx], rax
0x180009a27  mov     edi, edx
0x180009a29  lea     rax, ??_7?$CWerComReportStringList@$1?WerpGetNumFiles@@YAJPEAXPEAK@Z$1?WerpGetFilePathByIndex@@YAJ0KPEAPEBG@Z@@6BIWerStringList@@@; const CWerComReportStringList<&WerpGetNumFiles(void *,ulong *),&WerpGetFilePathByIndex(void *,ulong,ushort const * *)>::`vftable'{for `IWerStringList'}
0x180009a30  mov     [rcx+18h], rax
0x180009a34  mov     rcx, [rcx+28h]
0x180009a38  test    rcx, rcx
0x180009a3b  jz      short loc_180009A49
0x180009a3d  mov     rax, [rcx]
0x180009a40  mov     rax, [rax+10h]
0x180009a44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a49  lea     rax, ??_7CManagedObj@@6B@; const CManagedObj::`vftable'
0x180009a50  lea     rcx, ?ms_instance@CObjectManager@@1V1@A; this
0x180009a57  mov     [rbx], rax
0x180009a5a  call    ?UnLockServer@CObjectManager@@QEAAXXZ; CObjectManager::UnLockServer(void)
0x180009a5f  test    dil, 1
0x180009a63  jz      short loc_180009A6D
0x180009a65  mov     rcx, rbx; Block
0x180009a68  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009a6d  mov     rax, rbx
0x180009a70  mov     rbx, [rsp+28h+arg_0]
0x180009a75  add     rsp, 20h
0x180009a79  pop     rdi
0x180009a7a  retn
```
