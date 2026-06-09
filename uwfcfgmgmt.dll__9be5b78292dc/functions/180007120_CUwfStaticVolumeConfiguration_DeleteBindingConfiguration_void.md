# CUwfStaticVolumeConfiguration::DeleteBindingConfiguration(void)

- ea: `0x180007120`
- end: `0x180007173`
- name: `?DeleteBindingConfiguration@CUwfStaticVolumeConfiguration@@QEAAJXZ`
- size: `83`
- prototype: `__int64 __fastcall(CUwfStaticVolumeConfiguration *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180007120`
- `0x1800071d0`
- `0x1800072b0`
- `0x18000e0f0`

## pseudocode

```c
__int64 __fastcall CUwfStaticVolumeConfiguration::DeleteBindingConfiguration(CUwfStaticVolumeConfiguration *this)
{
  int v2; // edi
  unsigned int v4; // [rsp+38h] [rbp+10h] BYREF

  v4 = 0;
  v2 = CUwfRegKey::QueryDWORDValue((CUwfStaticVolumeConfiguration *)((char *)this + 16), L"Binding", &v4);
  if ( v2 >= 0 )
  {
    if ( v4 )
      CUwfStaticVolumeConfiguration::DeleteTightBindingConfiguration(this);
    else
      CUwfStaticVolumeConfiguration::DeleteLooseBindingConfiguration(this);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180007120  mov     [rsp+arg_0], rbx
0x180007125  push    rdi
0x180007126  sub     rsp, 20h
0x18000712a  mov     rbx, rcx
0x18000712d  mov     [rsp+28h+arg_8], 0
0x180007135  add     rcx, 10h; this
0x180007139  lea     r8, [rsp+28h+arg_8]; unsigned int *
0x18000713e  lea     rdx, aBinding; "Binding"
0x180007145  call    ?QueryDWORDValue@CUwfRegKey@@QEAAJPEBGPEAK@Z; CUwfRegKey::QueryDWORDValue(ushort const *,ulong *)
0x18000714a  mov     edi, eax
0x18000714c  test    eax, eax
0x18000714e  js      short loc_180007166
0x180007150  cmp     [rsp+28h+arg_8], 0
0x180007155  mov     rcx, rbx; this
0x180007158  jnz     short loc_180007161
0x18000715a  call    ?DeleteLooseBindingConfiguration@CUwfStaticVolumeConfiguration@@AEAAXXZ; CUwfStaticVolumeConfiguration::DeleteLooseBindingConfiguration(void)
0x18000715f  jmp     short loc_180007166
0x180007161  call    ?DeleteTightBindingConfiguration@CUwfStaticVolumeConfiguration@@AEAAXXZ; CUwfStaticVolumeConfiguration::DeleteTightBindingConfiguration(void)
0x180007166  mov     rbx, [rsp+28h+arg_0]
0x18000716b  mov     eax, edi
0x18000716d  add     rsp, 20h
0x180007171  pop     rdi
0x180007172  retn
```
