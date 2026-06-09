# TmpExpireNamespaceResourceManager

- ea: `0x14001d610`
- end: `0x14001d628`
- name: `TmpExpireNamespaceResourceManager`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14001d630`

## pseudocode

```c
__int64 __fastcall TmpExpireNamespaceResourceManager(__int64 a1)
{
  TmpNamespaceExpire(a1 + 384);
  return 0;
}

```

## disassembly

```asm
0x14001d610  sub     rsp, 28h
0x14001d614  add     rcx, 180h
0x14001d61b  call    TmpNamespaceExpire
0x14001d620  xor     eax, eax
0x14001d622  add     rsp, 28h
0x14001d626  retn
```
