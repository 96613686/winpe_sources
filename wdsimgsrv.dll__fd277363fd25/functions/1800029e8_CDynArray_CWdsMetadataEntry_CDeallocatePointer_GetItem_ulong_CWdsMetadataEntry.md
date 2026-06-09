# CDynArray<CWdsMetadataEntry *,CDeallocatePointer>::GetItem(ulong,CWdsMetadataEntry * &)

- ea: `0x1800029e8`
- end: `0x180002a03`
- name: `?GetItem@?$CDynArray@PEAVCWdsMetadataEntry@@VCDeallocatePointer@@@@QEAAKKAEAPEAVCWdsMetadataEntry@@@Z`
- size: `27`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180007c28`
- `0x18000891c`
- `0x1800092ec`
- `0x180009490`
- `0x18000d1b8`
- `0x18000df24`
- `0x18000f5f8`
- `0x18000f6b4`
- `0x18000f784`

## callees

- `0x1800029e8`

## pseudocode

```c
__int64 __fastcall CDynArray<CWdsMetadataEntry *,CDeallocatePointer>::GetItem(__int64 a1, unsigned int a2, _QWORD *a3)
{
  __int64 result; // rax

  result = 0;
  if ( a2 >= *(_DWORD *)(a1 + 12) )
    return 1413;
  *a3 = *(_QWORD *)(*(_QWORD *)a1 + 8LL * a2);
  return result;
}

```

## disassembly

```asm
0x1800029e8  xor     eax, eax
0x1800029ea  cmp     edx, [rcx+0Ch]
0x1800029ed  jb      short loc_1800029F6
0x1800029ef  mov     eax, 585h
0x1800029f4  retn
0x1800029f6  mov     rcx, [rcx]
0x1800029f9  mov     edx, edx
0x1800029fb  mov     rdx, [rcx+rdx*8]
0x1800029ff  mov     [r8], rdx
0x180002a02  retn
```
