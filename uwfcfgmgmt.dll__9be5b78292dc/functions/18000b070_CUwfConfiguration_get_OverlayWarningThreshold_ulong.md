# CUwfConfiguration::get_OverlayWarningThreshold(ulong *)

- ea: `0x18000b070`
- end: `0x18000b09b`
- name: `?get_OverlayWarningThreshold@CUwfConfiguration@@QEAAJPEAK@Z`
- size: `43`
- prototype: `int __fastcall(CUwfConfiguration *this, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800170d0`
- `0x180019600`

## callees

- `0x18000b070`
- `0x18000e0f0`

## pseudocode

```c
int __fastcall CUwfConfiguration::get_OverlayWarningThreshold(CUwfConfiguration *this, unsigned int *a2)
{
  if ( a2 )
    return CUwfRegKey::QueryDWORDValue((CUwfConfiguration *)((char *)this + 24), L"OverlayWarningThreshold", a2);
  else
    return -2147467261;
}

```

## disassembly

```asm
0x18000b070  sub     rsp, 28h
0x18000b074  test    rdx, rdx
0x18000b077  jnz     short loc_18000B083
0x18000b079  mov     eax, 80004003h
0x18000b07e  add     rsp, 28h
0x18000b082  retn
0x18000b083  mov     r8, rdx; unsigned int *
0x18000b086  add     rcx, 18h; this
0x18000b08a  lea     rdx, aOverlaywarning; "OverlayWarningThreshold"
0x18000b091  call    ?QueryDWORDValue@CUwfRegKey@@QEAAJPEBGPEAK@Z; CUwfRegKey::QueryDWORDValue(ushort const *,ulong *)
0x18000b096  add     rsp, 28h
0x18000b09a  retn
```
