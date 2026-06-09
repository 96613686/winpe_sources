# _RNvXCsdcpJtfrLhSH_7rgncoreNtB2_11RegionGuardNtNtNtCs9MWeMO1rkJG_4core3ops4drop4Drop4drop

- ea: `0x14000f3a0`
- end: `0x14000f3af`
- name: `_RNvXCsdcpJtfrLhSH_7rgncoreNtB2_11RegionGuardNtNtNtCs9MWeMO1rkJG_4core3ops4drop4Drop4drop`
- size: `15`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140005340`
- `0x1400101f0`
- `0x140011120`

## callees

- `0x14000b710`

## pseudocode

```c
unsigned __int64 __fastcall RNvXCsdcpJtfrLhSH_7rgncoreNtB2_11RegionGuardNtNtNtCs9MWeMO1rkJG_4core3ops4drop4Drop4drop(
        unsigned __int64 **a1)
{
  unsigned __int64 *v1; // rcx
  unsigned __int64 result; // rax

  v1 = *a1;
  if ( !v1[2] )
    return RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore16set_to_null_scan(v1);
  return result;
}

```

## disassembly

```asm
0x14000f3a0  mov     rcx, [rcx]
0x14000f3a3  cmp     qword ptr [rcx+10h], 0
0x14000f3a8  jz      _RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore16set_to_null_scan
0x14000f3ae  retn
```
