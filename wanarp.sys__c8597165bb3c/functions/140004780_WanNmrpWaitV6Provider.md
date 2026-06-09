# WanNmrpWaitV6Provider

- ea: `0x140004780`
- end: `0x1400047ae`
- name: `WanNmrpWaitV6Provider`
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
- `0x140004780`

## import_xrefs

- `NETIO!NmrWaitForProviderDeregisterComplete` at `0x140004790`
- `NETIO!NmrWaitForProviderDeregisterComplete` at `0x140004790`

## pseudocode

```c
__int64 WanNmrpWaitV6Provider()
{
  __int64 result; // rax

  if ( qword_1400092A0 )
  {
    NmrWaitForProviderDeregisterComplete(qword_1400092A0);
    return WanNmrDeregisterProviderComplete(&stru_140009258);
  }
  return result;
}

```

## disassembly

```asm
0x140004780  sub     rsp, 28h
0x140004784  mov     rcx, cs:qword_1400092A0; NmrProviderHandle
0x14000478b  test    rcx, rcx
0x14000478e  jz      short loc_1400047A8
0x140004790  call    cs:__imp_NmrWaitForProviderDeregisterComplete
0x140004797  nop     dword ptr [rax+rax+00h]
0x14000479c  lea     rcx, stru_140009258
0x1400047a3  call    WanNmrDeregisterProviderComplete
0x1400047a8  add     rsp, 28h
0x1400047ac  retn
```
