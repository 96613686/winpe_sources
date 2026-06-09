# UmpoRpcReadProfileAlias

- ea: `0x180014c80`
- end: `0x180014cdc`
- name: `UmpoRpcReadProfileAlias`
- size: `92`
- prototype: `__int64 __fastcall(__int64, GUID *, BYTE *, DWORD, LPDWORD lpcbData)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180004b80`
- `0x1800141e8`
- `0x180014c80`

## pseudocode

```c
__int64 __fastcall UmpoRpcReadProfileAlias(__int64 a1, GUID *a2, BYTE *a3, DWORD a4, LPDWORD lpcbData)
{
  if ( !UmpoIsClientLocal() )
    return 5;
  if ( !UmpoPowerPolicyInitialized )
    return 21;
  *lpcbData = a4;
  return UmpoReadProfileAlias(a2, a3, lpcbData);
}

```

## disassembly

```asm
0x180014c80  mov     [rsp+arg_0], rbx
0x180014c85  mov     [rsp+arg_8], rsi
0x180014c8a  push    rdi
0x180014c8b  sub     rsp, 20h
0x180014c8f  mov     ebx, r9d
0x180014c92  mov     rdi, r8
0x180014c95  mov     rsi, rdx
0x180014c98  call    UmpoIsClientLocal
0x180014c9d  test    eax, eax
0x180014c9f  jnz     short loc_180014CA8
0x180014ca1  mov     eax, 5
0x180014ca6  jmp     short loc_180014CCC
0x180014ca8  mov     al, cs:UmpoPowerPolicyInitialized
0x180014cae  test    al, al
0x180014cb0  jnz     short loc_180014CB9
0x180014cb2  mov     eax, 15h
0x180014cb7  jmp     short loc_180014CCC
0x180014cb9  mov     r8, [rsp+28h+lpcbData]; lpcbData
0x180014cbe  mov     rdx, rdi; lpData
0x180014cc1  mov     rcx, rsi; Guid
0x180014cc4  mov     [r8], ebx
0x180014cc7  call    UmpoReadProfileAlias
0x180014ccc  mov     rbx, [rsp+28h+arg_0]
0x180014cd1  mov     rsi, [rsp+28h+arg_8]
0x180014cd6  add     rsp, 20h
0x180014cda  pop     rdi
0x180014cdb  retn
```
