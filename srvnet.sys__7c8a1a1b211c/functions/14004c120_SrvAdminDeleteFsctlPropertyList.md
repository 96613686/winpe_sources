# SrvAdminDeleteFsctlPropertyList

- ea: `0x14004c120`
- end: `0x14004c175`
- name: `SrvAdminDeleteFsctlPropertyList`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140021d88`

## callees

- `0x140007ec0`
- `0x14004c120`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x14004c130`
- `ntoskrnl!ExDeleteResourceLite` at `0x14004c130`

## pseudocode

```c
__int64 SrvAdminDeleteFsctlPropertyList()
{
  __int64 result; // rax

  if ( UserDefinedFsctlPropertyListLock )
  {
    ExDeleteResourceLite(UserDefinedFsctlPropertyListLock);
    result = SrvNetWskNotifyCleanupProviderContext(UserDefinedFsctlPropertyListLock);
    UserDefinedFsctlPropertyListLock = 0;
  }
  if ( UserDefinedFsctlPropertyList )
  {
    result = SrvNetWskNotifyCleanupProviderContext(UserDefinedFsctlPropertyList);
    UserDefinedFsctlPropertyList = 0;
  }
  return result;
}

```

## disassembly

```asm
0x14004c120  sub     rsp, 28h
0x14004c124  mov     rcx, cs:UserDefinedFsctlPropertyListLock; Resource
0x14004c12b  test    rcx, rcx
0x14004c12e  jz      short loc_14004C153
0x14004c130  call    cs:__imp_ExDeleteResourceLite
0x14004c137  nop     dword ptr [rax+rax+00h]
0x14004c13c  mov     rcx, cs:UserDefinedFsctlPropertyListLock
0x14004c143  call    SrvNetWskNotifyCleanupProviderContext
0x14004c148  mov     cs:UserDefinedFsctlPropertyListLock, 0
0x14004c153  mov     rcx, cs:UserDefinedFsctlPropertyList
0x14004c15a  test    rcx, rcx
0x14004c15d  jz      short loc_14004C16F
0x14004c15f  call    SrvNetWskNotifyCleanupProviderContext
0x14004c164  mov     cs:UserDefinedFsctlPropertyList, 0
0x14004c16f  add     rsp, 28h
0x14004c173  retn
```
