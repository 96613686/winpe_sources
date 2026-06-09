# CCSPNodeImpl::Copy(IConfigManager2URI *,ICSPNode * *,ulong *)

- ea: `0x1800199f0`
- end: `0x180019a14`
- name: `?Copy@CCSPNodeImpl@@UEAAJPEAUIConfigManager2URI@@PEAPEAUICSPNode@@PEAK@Z`
- size: `36`
- prototype: `__int64 __fastcall(CCSPNodeImpl *__hidden this, struct IConfigManager2URI *, struct ICSPNode **, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x1800199f0`

## pseudocode

```c
__int64 __fastcall CCSPNodeImpl::Copy(
        CCSPNodeImpl *this,
        struct IConfigManager2URI *a2,
        struct ICSPNode **a3,
        unsigned int *a4)
{
  __int64 result; // rax

  if ( !a3 || !a4 )
    return 2147942487LL;
  *a3 = 0;
  result = 2248146961LL;
  *a4 = 0;
  return result;
}

```

## disassembly

```asm
0x1800199f0  test    r8, r8
0x1800199f3  jz      short loc_180019A0E
0x1800199f5  test    r9, r9
0x1800199f8  jz      short loc_180019A0E
0x1800199fa  mov     qword ptr [r8], 0
0x180019a01  mov     eax, 86000011h
0x180019a06  mov     dword ptr [r9], 0
0x180019a0d  retn
0x180019a0e  mov     eax, 80070057h
0x180019a13  retn
```
