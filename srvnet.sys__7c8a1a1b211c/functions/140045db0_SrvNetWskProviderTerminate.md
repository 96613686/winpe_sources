# SrvNetWskProviderTerminate

- ea: `0x140045db0`
- end: `0x140045de9`
- name: `SrvNetWskProviderTerminate`
- size: `57`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140056be0`
- `0x14005b0a0`

## callees

- `0x140045db0`

## import_xrefs

- `NETIO!NmrDeregisterClient` at `0x140045dc4`
- `NETIO!NmrDeregisterClient` at `0x140045dc4`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x140045dd7`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x140045dd7`

## pseudocode

```c
NTSTATUS SrvNetWskProviderTerminate()
{
  NTSTATUS result; // eax

  if ( SrvNetWskNmrRegistered )
  {
    NmrDeregisterClient(SrvNetWskNpiClientHandle);
    return NmrWaitForClientDeregisterComplete(SrvNetWskNpiClientHandle);
  }
  return result;
}

```

## disassembly

```asm
0x140045db0  sub     rsp, 28h
0x140045db4  cmp     cs:SrvNetWskNmrRegistered, 0
0x140045dbb  jz      short loc_140045DE3
0x140045dbd  mov     rcx, cs:SrvNetWskNpiClientHandle; NmrClientHandle
0x140045dc4  call    cs:__imp_NmrDeregisterClient
0x140045dcb  nop     dword ptr [rax+rax+00h]
0x140045dd0  mov     rcx, cs:SrvNetWskNpiClientHandle; NmrClientHandle
0x140045dd7  call    cs:__imp_NmrWaitForClientDeregisterComplete
0x140045dde  nop     dword ptr [rax+rax+00h]
0x140045de3  add     rsp, 28h
0x140045de7  retn
```
