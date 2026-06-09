# _CRegEventProvider::AccessCheck_::_1_::dtor$5

- ea: `0x180016030`
- end: `0x18001603c`
- name: `_CRegEventProvider::AccessCheck_::_1_::dtor$5`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x18000b740`

## pseudocode

```c
__int64 __fastcall CRegEventProvider::AccessCheck_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  return CUniquePointerArray<HKEY__ *>::~CUniquePointerArray<HKEY__ *>(a2 + 304);
}

```

## disassembly

```asm
0x180016030  lea     rcx, [rdx+130h]
0x180016037  jmp     ??1?$CUniquePointerArray@PEAUHKEY__@@@@QEAA@XZ; CUniquePointerArray<HKEY__ *>::~CUniquePointerArray<HKEY__ *>(void)
```
