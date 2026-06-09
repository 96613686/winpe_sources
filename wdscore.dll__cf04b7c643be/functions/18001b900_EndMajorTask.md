# EndMajorTask

- ea: `0x18001b900`
- end: `0x18001b936`
- name: `EndMajorTask`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x180019e68`
- `0x18001ab98`
- `0x18001b900`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001b90a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001b90a`

## pseudocode

```c
CTaskNameCollection *EndMajorTask()
{
  CTaskNameCollection *result; // rax

  result = (CTaskNameCollection *)TlsGetValue(g_dwMajorTaskStackTLSIndex);
  if ( result )
  {
    result = (CTaskNameCollection *)CStack<CTaskNameHolder *>::Pop(result);
    if ( result )
      return CTaskNameCollection::`scalar deleting destructor'(result);
  }
  return result;
}

```

## disassembly

```asm
0x18001b900  sub     rsp, 28h
0x18001b904  mov     ecx, cs:?g_dwMajorTaskStackTLSIndex@@3KA; dwTlsIndex
0x18001b90a  call    cs:__imp_TlsGetValue
0x18001b911  nop     dword ptr [rax+rax+00h]
0x18001b916  test    rax, rax
0x18001b919  jz      short loc_18001B930
0x18001b91b  mov     rcx, rax
0x18001b91e  call    ?Pop@?$CStack@PEAVCTaskNameHolder@@@@QEAAPEAVCTaskNameHolder@@XZ; CStack<CTaskNameHolder *>::Pop(void)
0x18001b923  test    rax, rax
0x18001b926  jz      short loc_18001B930
0x18001b928  mov     rcx, rax; this
0x18001b92b  call    ??_GCTaskNameCollection@@QEAAPEAXI@Z; CTaskNameCollection::`scalar deleting destructor'(uint)
0x18001b930  add     rsp, 28h
0x18001b934  retn
```
