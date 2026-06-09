# CWerComReportStringList<&WerpGetNumFiles(void *,ulong *),&GetFileNameByIndex(void *,ulong,ushort const * *)>::`scalar deleting destructor'(uint)

- ea: `0x180009990`
- end: `0x1800099fb`
- name: `??_G?$CWerComReportStringList@$1?WerpGetNumFiles@@YAJPEAXPEAK@Z$1?GetFileNameByIndex@@YAJ0KPEAPEBG@Z@@UEAAPEAXI@Z`
- size: `107`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001674`
- `0x180007624`
- `0x180009990`
- `0x180013010`

## pseudocode

```c
_QWORD *__fastcall CWerComReportStringList<&long WerpGetNumFiles(void *,unsigned long *),&long GetFileNameByIndex(void *,unsigned long,unsigned short const * *)>::`scalar deleting destructor'(
        _QWORD *Block,
        char a2)
{
  __int64 v4; // rcx

  *Block = &CWerComReportStringList<&long WerpGetNumFiles(void *,unsigned long *),&long GetFileNameByIndex(void *,unsigned long,unsigned short const * *)>::`vftable'{for `CManagedObj'};
  Block[3] = &CWerComReportStringList<&long WerpGetNumFiles(void *,unsigned long *),&long GetFileNameByIndex(void *,unsigned long,unsigned short const * *)>::`vftable'{for `IWerStringList'};
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
0x180009990  mov     [rsp+arg_0], rbx
0x180009995  push    rdi
0x180009996  sub     rsp, 20h
0x18000999a  lea     rax, ??_7?$CWerComReportStringList@$1?WerpGetNumFiles@@YAJPEAXPEAK@Z$1?GetFileNameByIndex@@YAJ0KPEAPEBG@Z@@6BCManagedObj@@@; const CWerComReportStringList<&WerpGetNumFiles(void *,ulong *),&GetFileNameByIndex(void *,ulong,ushort const * *)>::`vftable'{for `CManagedObj'}
0x1800099a1  mov     rbx, rcx
0x1800099a4  mov     [rcx], rax
0x1800099a7  mov     edi, edx
0x1800099a9  lea     rax, ??_7?$CWerComReportStringList@$1?WerpGetNumFiles@@YAJPEAXPEAK@Z$1?GetFileNameByIndex@@YAJ0KPEAPEBG@Z@@6BIWerStringList@@@; const CWerComReportStringList<&WerpGetNumFiles(void *,ulong *),&GetFileNameByIndex(void *,ulong,ushort const * *)>::`vftable'{for `IWerStringList'}
0x1800099b0  mov     [rcx+18h], rax
0x1800099b4  mov     rcx, [rcx+28h]
0x1800099b8  test    rcx, rcx
0x1800099bb  jz      short loc_1800099C9
0x1800099bd  mov     rax, [rcx]
0x1800099c0  mov     rax, [rax+10h]
0x1800099c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099c9  lea     rax, ??_7CManagedObj@@6B@; const CManagedObj::`vftable'
0x1800099d0  lea     rcx, ?ms_instance@CObjectManager@@1V1@A; this
0x1800099d7  mov     [rbx], rax
0x1800099da  call    ?UnLockServer@CObjectManager@@QEAAXXZ; CObjectManager::UnLockServer(void)
0x1800099df  test    dil, 1
0x1800099e3  jz      short loc_1800099ED
0x1800099e5  mov     rcx, rbx; Block
0x1800099e8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800099ed  mov     rax, rbx
0x1800099f0  mov     rbx, [rsp+28h+arg_0]
0x1800099f5  add     rsp, 20h
0x1800099f9  pop     rdi
0x1800099fa  retn
```
