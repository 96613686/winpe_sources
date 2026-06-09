# CUwfStaticVolumeConfiguration::ResetBindingConfiguration(void)

- ea: `0x180009100`
- end: `0x180009164`
- name: `?ResetBindingConfiguration@CUwfStaticVolumeConfiguration@@QEAAJXZ`
- size: `100`
- prototype: `__int64 __fastcall(HKEY *this)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180009100`
- `0x18000bc90`
- `0x18000e0f0`

## pseudocode

```c
__int64 __fastcall CUwfStaticVolumeConfiguration::ResetBindingConfiguration(HKEY *this)
{
  LSTATUS DWORDValue; // edx
  unsigned int v4; // [rsp+38h] [rbp+10h] BYREF

  v4 = 0;
  DWORDValue = CUwfRegKey::QueryDWORDValue(this + 2, L"Binding", (BYTE *)&v4);
  if ( DWORDValue < 0
    || (DWORDValue = CUwfStaticVolumeConfiguration::set_BindingType((CUwfStaticVolumeConfiguration *)this, v4 == 0),
        DWORDValue < 0)
    || (DWORDValue = CUwfStaticVolumeConfiguration::set_BindingType((CUwfStaticVolumeConfiguration *)this, v4),
        DWORDValue < 0) )
  {
    *((_DWORD *)this[3] + 4) = DWORDValue;
  }
  return (unsigned int)DWORDValue;
}

```

## disassembly

```asm
0x180009100  push    rbx
0x180009102  sub     rsp, 20h
0x180009106  mov     rbx, rcx
0x180009109  mov     [rsp+28h+arg_8], 0
0x180009111  add     rcx, 10h; this
0x180009115  lea     r8, [rsp+28h+arg_8]; unsigned int *
0x18000911a  lea     rdx, aBinding; "Binding"
0x180009121  call    ?QueryDWORDValue@CUwfRegKey@@QEAAJPEBGPEAK@Z; CUwfRegKey::QueryDWORDValue(ushort const *,ulong *)
0x180009126  mov     edx, eax
0x180009128  test    eax, eax
0x18000912a  js      short loc_180009155
0x18000912c  xor     edx, edx
0x18000912e  mov     rcx, rbx; this
0x180009131  cmp     [rsp+28h+arg_8], edx
0x180009135  setz    dl; unsigned int
0x180009138  call    ?set_BindingType@CUwfStaticVolumeConfiguration@@QEAAJK@Z; CUwfStaticVolumeConfiguration::set_BindingType(ulong)
0x18000913d  mov     edx, eax
0x18000913f  test    eax, eax
0x180009141  js      short loc_180009155
0x180009143  mov     edx, [rsp+28h+arg_8]; unsigned int
0x180009147  mov     rcx, rbx; this
0x18000914a  call    ?set_BindingType@CUwfStaticVolumeConfiguration@@QEAAJK@Z; CUwfStaticVolumeConfiguration::set_BindingType(ulong)
0x18000914f  mov     edx, eax
0x180009151  test    eax, eax
0x180009153  jns     short loc_18000915C
0x180009155  mov     rax, [rbx+18h]
0x180009159  mov     [rax+10h], edx
0x18000915c  mov     eax, edx
0x18000915e  add     rsp, 20h
0x180009162  pop     rbx
0x180009163  retn
```
