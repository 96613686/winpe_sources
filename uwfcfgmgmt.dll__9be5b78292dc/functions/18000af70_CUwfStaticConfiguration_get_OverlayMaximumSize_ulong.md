# CUwfStaticConfiguration::get_OverlayMaximumSize(ulong *)

- ea: `0x18000af70`
- end: `0x18000af9b`
- name: `?get_OverlayMaximumSize@CUwfStaticConfiguration@@QEAAJPEAK@Z`
- size: `43`
- prototype: `int __fastcall(CUwfStaticConfiguration *this, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x1800169c4`
- `0x180017050`

## callees

- `0x18000af70`
- `0x18000e0f0`

## string_xrefs

- `0x18000af8a`: `OverlayMaximumSize`

## pseudocode

```c
int __fastcall CUwfStaticConfiguration::get_OverlayMaximumSize(CUwfStaticConfiguration *this, unsigned int *a2)
{
  if ( a2 )
    return CUwfRegKey::QueryDWORDValue((CUwfStaticConfiguration *)((char *)this + 16), L"OverlayMaximumSize", a2);
  else
    return -2147467261;
}

```

## disassembly

```asm
0x18000af70  sub     rsp, 28h
0x18000af74  test    rdx, rdx
0x18000af77  jnz     short loc_18000AF83
0x18000af79  mov     eax, 80004003h
0x18000af7e  add     rsp, 28h
0x18000af82  retn
0x18000af83  mov     r8, rdx; unsigned int *
0x18000af86  add     rcx, 10h; this
0x18000af8a  lea     rdx, aOverlaymaximum; "OverlayMaximumSize"
0x18000af91  call    ?QueryDWORDValue@CUwfRegKey@@QEAAJPEBGPEAK@Z; CUwfRegKey::QueryDWORDValue(ushort const *,ulong *)
0x18000af96  add     rsp, 28h
0x18000af9a  retn
```
