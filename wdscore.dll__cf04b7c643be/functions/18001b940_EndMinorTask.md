# EndMinorTask

- ea: `0x18001b940`
- end: `0x18001b984`
- name: `EndMinorTask`
- size: `68`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180019e90`
- `0x18001ab78`
- `0x18001ab98`
- `0x18001b940`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001b94a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001b94a`

## pseudocode

```c
CTaskNameHolder *EndMinorTask()
{
  CTaskNameHolder *result; // rax

  result = (CTaskNameHolder *)TlsGetValue(g_dwMajorTaskStackTLSIndex);
  if ( result )
  {
    result = (CTaskNameHolder *)CStack<CTaskNameCollection *>::Peek(result);
    if ( result )
    {
      result = (CTaskNameHolder *)CStack<CTaskNameHolder *>::Pop((_QWORD *)result + 2);
      if ( result )
        return CTaskNameHolder::`scalar deleting destructor'(result);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001b940  sub     rsp, 28h
0x18001b944  mov     ecx, cs:?g_dwMajorTaskStackTLSIndex@@3KA; dwTlsIndex
0x18001b94a  call    cs:__imp_TlsGetValue
0x18001b951  nop     dword ptr [rax+rax+00h]
0x18001b956  test    rax, rax
0x18001b959  jz      short loc_18001B97E
0x18001b95b  mov     rcx, rax
0x18001b95e  call    ?Peek@?$CStack@PEAVCTaskNameCollection@@@@QEAAPEAVCTaskNameCollection@@XZ; CStack<CTaskNameCollection *>::Peek(void)
0x18001b963  test    rax, rax
0x18001b966  jz      short loc_18001B97E
0x18001b968  lea     rcx, [rax+10h]
0x18001b96c  call    ?Pop@?$CStack@PEAVCTaskNameHolder@@@@QEAAPEAVCTaskNameHolder@@XZ; CStack<CTaskNameHolder *>::Pop(void)
0x18001b971  test    rax, rax
0x18001b974  jz      short loc_18001B97E
0x18001b976  mov     rcx, rax; this
0x18001b979  call    ??_GCTaskNameHolder@@QEAAPEAXI@Z; CTaskNameHolder::`scalar deleting destructor'(uint)
0x18001b97e  add     rsp, 28h
0x18001b982  retn
```
