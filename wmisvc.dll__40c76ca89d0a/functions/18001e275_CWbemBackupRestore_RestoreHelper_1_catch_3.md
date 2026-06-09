# _CWbemBackupRestore::RestoreHelper_::_1_::catch$3

- ea: `0x18001e275`
- end: `0x18001e2e2`
- name: `_CWbemBackupRestore::RestoreHelper_::_1_::catch$3`
- size: `109`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180012c34`
- `0x18001e275`

## import_xrefs

- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001e290`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001e290`
- `wbemcomn!GetMemLogObject` at `0x18001e282`
- `wbemcomn!GetMemLogObject` at `0x18001e282`

## pseudocode

```c
__int64 CWbemBackupRestore::RestoreHelper_::_1_::catch_3()
{
  CMemoryLog *MemLogObject; // rax

  MemLogObject = GetMemLogObject();
  CMemoryLog::Write(MemLogObject, -2147217402);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_da0c108f5fb630a241f44bac5f55929c_Traceguids, 2147749894LL);
  }
  return 0;
}

```

## disassembly

```asm
0x18001e275  mov     [rsp+arg_8], rdx
0x18001e27a  push    rbp
0x18001e27b  sub     rsp, 50h
0x18001e27f  mov     rbp, rdx
0x18001e282  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001e288  mov     edx, 80041006h
0x18001e28d  mov     rcx, rax
0x18001e290  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001e296  lea     rax, WPP_GLOBAL_Control
0x18001e29d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e2a4  cmp     rcx, rax
0x18001e2a7  jz      short loc_18001E2D1
0x18001e2a9  test    byte ptr [rcx+1Ch], 1
0x18001e2ad  jz      short loc_18001E2D1
0x18001e2af  cmp     byte ptr [rcx+19h], 2
0x18001e2b3  jb      short loc_18001E2D1
0x18001e2b5  mov     edx, 16h
0x18001e2ba  mov     r9d, 80041006h
0x18001e2c0  lea     r8, WPP_da0c108f5fb630a241f44bac5f55929c_Traceguids
0x18001e2c7  mov     rcx, [rcx+10h]
0x18001e2cb  call    WPP_SF_d
0x18001e2d0  nop
0x18001e2d1  mov     rax, 0
0x18001e2db  add     rsp, 50h
0x18001e2df  pop     rbp
0x18001e2e0  retn
```
