# _CRegEventProvider::AccessCheck_::_1_::dtor$21

- ea: `0x1800160b0`
- end: `0x1800160bc`
- name: `_CRegEventProvider::AccessCheck_::_1_::dtor$21`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x18000b758`

## pseudocode

```c
void __fastcall CRegEventProvider::AccessCheck_::_1_::dtor_21(__int64 a1, __int64 a2)
{
  CPointerArray<HKEY__ *,CUniqueManager<HKEY__ *>,CFlexArray>::~CPointerArray<HKEY__ *,CUniqueManager<HKEY__ *>,CFlexArray>((CFlexArray *)(a2 + 304));
}

```

## disassembly

```asm
0x1800160b0  lea     rcx, [rdx+130h]
0x1800160b7  jmp     ??1?$CPointerArray@PEAUHKEY__@@V?$CUniqueManager@PEAUHKEY__@@@@VCFlexArray@@@@QEAA@XZ; CPointerArray<HKEY__ *,CUniqueManager<HKEY__ *>,CFlexArray>::~CPointerArray<HKEY__ *,CUniqueManager<HKEY__ *>,CFlexArray>(void)
```
