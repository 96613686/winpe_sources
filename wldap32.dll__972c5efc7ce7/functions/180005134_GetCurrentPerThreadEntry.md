# GetCurrentPerThreadEntry

- ea: `0x180005134`
- end: `0x18000515b`
- name: `GetCurrentPerThreadEntry`
- size: `39`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180004740`
- `0x180004e60`
- `0x180005170`
- `0x18001ba9c`

## callees

- `0x180005134`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000513e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000513e`

## pseudocode

```c
_QWORD *GetCurrentPerThreadEntry()
{
  _QWORD *result; // rax

  result = TlsGetValue(GlobalTlsLastErrorIndex);
  if ( result )
    return (_QWORD *)result[1];
  return result;
}

```

## disassembly

```asm
0x180005134  sub     rsp, 28h
0x180005138  mov     ecx, cs:GlobalTlsLastErrorIndex; dwTlsIndex
0x18000513e  call    cs:__imp_TlsGetValue
0x180005145  nop     dword ptr [rax+rax+00h]
0x18000514a  test    rax, rax
0x18000514d  jnz     short loc_180005155
0x18000514f  add     rsp, 28h
0x180005153  retn
0x180005155  mov     rax, [rax+8]
0x180005159  jmp     short loc_18000514F
```
