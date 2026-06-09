# GetDynamicDstKey

- ea: `0x180027548`
- end: `0x180027587`
- name: `GetDynamicDstKey`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180027468`

## callees

- `0x180027548`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002756f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002756f`

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
0x180027548  sub     rsp, 38h
0x18002754c  lea     rax, [rsp+38h+arg_8]
0x180027551  mov     [rsp+38h+arg_8], 0
0x18002755a  mov     r9d, 20019h; samDesired
0x180027560  mov     [rsp+38h+phkResult], rax; phkResult
0x180027565  xor     r8d, r8d; ulOptions
0x180027568  lea     rdx, aDynamicDst; "Dynamic DST"
0x18002756f  call    cs:__imp_RegOpenKeyExW
0x180027575  test    eax, eax
0x180027577  jz      short loc_18002757D
0x180027579  xor     eax, eax
0x18002757b  jmp     short loc_180027582
0x18002757d  mov     rax, [rsp+38h+arg_8]
0x180027582  add     rsp, 38h
0x180027586  retn
```
