# CTrkRpcConfig::RpcSecurityEnabled(void)

- ea: `0x18000aec4`
- end: `0x18000aedd`
- name: `?RpcSecurityEnabled@CTrkRpcConfig@@SAHXZ`
- size: `25`
- prototype: `_BOOL8 __fastcall(CMultiTsz *)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004f90`
- `0x18000aacc`
- `0x18000add0`
- `0x180010638`

## callees

- `0x18000aee4`

## pseudocode

```c
_BOOL8 __fastcall CTrkRpcConfig::RpcSecurityEnabled(CMultiTsz *a1)
{
  CMultiTsz::CalcNumStringsIf(a1);
  return dword_18001BE18 == 0;
}

```

## disassembly

```asm
0x18000aec4  sub     rsp, 28h
0x18000aec8  call    ?CalcNumStringsIf@CMultiTsz@@AEAAXXZ; CMultiTsz::CalcNumStringsIf(void)
0x18000aecd  xor     eax, eax
0x18000aecf  cmp     cs:dword_18001BE18, eax
0x18000aed5  setz    al
0x18000aed8  add     rsp, 28h
0x18000aedc  retn
```
