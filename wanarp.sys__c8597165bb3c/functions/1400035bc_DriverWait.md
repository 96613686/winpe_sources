# DriverWait

- ea: `0x1400035bc`
- end: `0x1400035de`
- name: `DriverWait`
- size: `34`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140017550`

## callees

- `0x1400035bc`

## import_xrefs

- `NETIO!NmrWaitForClientDeregisterComplete` at `0x1400035cc`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x1400035cc`

## pseudocode

```c
NTSTATUS DriverWait()
{
  NTSTATUS result; // eax

  if ( NmrClientHandle )
    return NmrWaitForClientDeregisterComplete(NmrClientHandle);
  return result;
}

```

## disassembly

```asm
0x1400035bc  sub     rsp, 28h
0x1400035c0  mov     rcx, qword ptr cs:NmrClientHandle; NmrClientHandle
0x1400035c7  test    rcx, rcx
0x1400035ca  jz      short loc_1400035D8
0x1400035cc  call    cs:__imp_NmrWaitForClientDeregisterComplete
0x1400035d3  nop     dword ptr [rax+rax+00h]
0x1400035d8  add     rsp, 28h
0x1400035dc  retn
```
