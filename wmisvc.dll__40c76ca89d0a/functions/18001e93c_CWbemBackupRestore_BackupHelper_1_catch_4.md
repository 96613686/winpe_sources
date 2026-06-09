# _CWbemBackupRestore::BackupHelper_::_1_::catch$4

- ea: `0x18001e93c`
- end: `0x18001e9a9`
- name: `_CWbemBackupRestore::BackupHelper_::_1_::catch$4`
- size: `109`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180012c34`
- `0x18001e93c`

## import_xrefs

- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001e957`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001e957`
- `wbemcomn!GetMemLogObject` at `0x18001e949`
- `wbemcomn!GetMemLogObject` at `0x18001e949`

## pseudocode

```c
__int64 CWbemBackupRestore::BackupHelper_::_1_::catch_4()
{
  CMemoryLog *MemLogObject; // rax

  MemLogObject = GetMemLogObject();
  CMemoryLog::Write(MemLogObject, -2147217402);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_da0c108f5fb630a241f44bac5f55929c_Traceguids, 2147749894LL);
  }
  return 0;
}

```

## disassembly

```asm
0x18001e93c  mov     [rsp+arg_8], rdx
0x18001e941  push    rbp
0x18001e942  sub     rsp, 40h
0x18001e946  mov     rbp, rdx
0x18001e949  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001e94f  mov     edx, 80041006h
0x18001e954  mov     rcx, rax
0x18001e957  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001e95d  lea     rax, WPP_GLOBAL_Control
0x18001e964  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e96b  cmp     rcx, rax
0x18001e96e  jz      short loc_18001E998
0x18001e970  test    byte ptr [rcx+1Ch], 1
0x18001e974  jz      short loc_18001E998
0x18001e976  cmp     byte ptr [rcx+19h], 2
0x18001e97a  jb      short loc_18001E998
0x18001e97c  mov     edx, 12h
0x18001e981  mov     r9d, 80041006h
0x18001e987  lea     r8, WPP_da0c108f5fb630a241f44bac5f55929c_Traceguids
0x18001e98e  mov     rcx, [rcx+10h]
0x18001e992  call    WPP_SF_d
0x18001e997  nop
0x18001e998  mov     rax, 0
0x18001e9a2  add     rsp, 40h
0x18001e9a6  pop     rbp
0x18001e9a7  retn
```
