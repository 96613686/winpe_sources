# CBthActiveConnector::_ThreadProc(void *)

- ea: `0x1800066f0`
- end: `0x180006707`
- name: `?_ThreadProc@CBthActiveConnector@@CAKPEAX@Z`
- size: `23`
- prototype: `__int64 __fastcall(CBthActiveConnector *Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180004620`
- `0x1800066f0`

## pseudocode

```c
__int64 __fastcall CBthActiveConnector::_ThreadProc(CBthActiveConnector *Parameter)
{
  if ( Parameter )
    return CBthActiveConnector::_Run(Parameter);
  else
    return 0;
}

```

## disassembly

```asm
0x1800066f0  sub     rsp, 28h
0x1800066f4  test    rcx, rcx
0x1800066f7  jnz     short loc_180006700
0x1800066f9  xor     eax, eax
0x1800066fb  add     rsp, 28h
0x1800066ff  retn
0x180006700  call    ?_Run@CBthActiveConnector@@AEAAJXZ; CBthActiveConnector::_Run(void)
0x180006705  jmp     short loc_1800066FB
```
