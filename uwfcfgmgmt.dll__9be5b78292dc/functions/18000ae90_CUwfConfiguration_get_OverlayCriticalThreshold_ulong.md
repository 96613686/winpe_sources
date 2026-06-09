# CUwfConfiguration::get_OverlayCriticalThreshold(ulong *)

- ea: `0x18000ae90`
- end: `0x18000aebb`
- name: `?get_OverlayCriticalThreshold@CUwfConfiguration@@QEAAJPEAK@Z`
- size: `43`
- prototype: `int __fastcall(CUwfConfiguration *this, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180016fd0`
- `0x1800184b0`

## callees

- `0x18000ae90`
- `0x18000e0f0`

## pseudocode

```c
int __fastcall CUwfConfiguration::get_OverlayCriticalThreshold(CUwfConfiguration *this, unsigned int *a2)
{
  if ( a2 )
    return CUwfRegKey::QueryDWORDValue((CUwfConfiguration *)((char *)this + 24), L"OverlayCriticalThreshold", a2);
  else
    return -2147467261;
}

```

## disassembly

```asm
0x18000ae90  sub     rsp, 28h
0x18000ae94  test    rdx, rdx
0x18000ae97  jnz     short loc_18000AEA3
0x18000ae99  mov     eax, 80004003h
0x18000ae9e  add     rsp, 28h
0x18000aea2  retn
0x18000aea3  mov     r8, rdx; unsigned int *
0x18000aea6  add     rcx, 18h; this
0x18000aeaa  lea     rdx, aOverlaycritica; "OverlayCriticalThreshold"
0x18000aeb1  call    ?QueryDWORDValue@CUwfRegKey@@QEAAJPEBGPEAK@Z; CUwfRegKey::QueryDWORDValue(ushort const *,ulong *)
0x18000aeb6  add     rsp, 28h
0x18000aeba  retn
```
