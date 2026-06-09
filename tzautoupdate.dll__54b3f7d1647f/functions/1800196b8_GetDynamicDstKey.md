# GetDynamicDstKey

- ea: `0x1800196b8`
- end: `0x1800196f7`
- name: `GetDynamicDstKey`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800195d8`

## callees

- `0x1800196b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800196df`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800196df`

## pseudocode

```c
HKEY __fastcall GetDynamicDstKey(HKEY a1)
{
  HKEY phkResult; // [rsp+48h] [rbp+10h] BYREF

  phkResult = 0;
  if ( RegOpenKeyExW(a1, L"Dynamic DST", 0, 0x20019u, &phkResult) )
    return 0;
  else
    return phkResult;
}

```

## disassembly

```asm
0x1800196b8  sub     rsp, 38h
0x1800196bc  lea     rax, [rsp+38h+arg_8]
0x1800196c1  mov     [rsp+38h+arg_8], 0
0x1800196ca  mov     r9d, 20019h; samDesired
0x1800196d0  mov     [rsp+38h+phkResult], rax; phkResult
0x1800196d5  xor     r8d, r8d; ulOptions
0x1800196d8  lea     rdx, aDynamicDst; "Dynamic DST"
0x1800196df  call    cs:__imp_RegOpenKeyExW
0x1800196e5  test    eax, eax
0x1800196e7  jz      short loc_1800196ED
0x1800196e9  xor     eax, eax
0x1800196eb  jmp     short loc_1800196F2
0x1800196ed  mov     rax, [rsp+38h+arg_8]
0x1800196f2  add     rsp, 38h
0x1800196f6  retn
```
