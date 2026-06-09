# WanNmrpWaitV4Provider

- ea: `0x14000474c`
- end: `0x14000477a`
- name: `WanNmrpWaitV4Provider`
- size: `46`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140017550`
- `0x14001aa04`

## callees

- `0x1400044a0`
- `0x14000474c`

## import_xrefs

- `NETIO!NmrWaitForProviderDeregisterComplete` at `0x14000475c`
- `NETIO!NmrWaitForProviderDeregisterComplete` at `0x14000475c`

## pseudocode

```c
__int64 WanNmrpWaitV4Provider()
{
  __int64 result; // rax

  if ( NmrProviderHandle )
  {
    NmrWaitForProviderDeregisterComplete(NmrProviderHandle);
    return WanNmrDeregisterProviderComplete(&ProviderCharacteristics);
  }
  return result;
}

```

## disassembly

```asm
0x14000474c  sub     rsp, 28h
0x140004750  mov     rcx, cs:NmrProviderHandle; NmrProviderHandle
0x140004757  test    rcx, rcx
0x14000475a  jz      short loc_140004774
0x14000475c  call    cs:__imp_NmrWaitForProviderDeregisterComplete
0x140004763  nop     dword ptr [rax+rax+00h]
0x140004768  lea     rcx, ProviderCharacteristics
0x14000476f  call    WanNmrDeregisterProviderComplete
0x140004774  add     rsp, 28h
0x140004778  retn
```
