# CRegistryKey::CRegistryKey(HKEY__ *)

- ea: `0x18000bc58`
- end: `0x18000bc73`
- name: `??0CRegistryKey@@QEAA@PEAUHKEY__@@@Z`
- size: `27`
- prototype: `CRegistryKey *__fastcall(CRegistryKey *__hidden this, HKEY)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000aa38`
- `0x18000af00`

## callees

- `0x1800040cc`

## pseudocode

```c
CRegistryKey *__fastcall CRegistryKey::CRegistryKey(CRegistryKey *this, HKEY a2)
{
  CRegistryKey *v2; // r8

  *(_QWORD *)this = a2;
  std::vector<_bstr_t>::vector<_bstr_t>((_QWORD *)this + 1);
  return v2;
}

```

## disassembly

```asm
0x18000bc58  sub     rsp, 28h
0x18000bc5c  mov     [rcx], rdx
0x18000bc5f  mov     r8, rcx
0x18000bc62  add     rcx, 8
0x18000bc66  call    ??0?$vector@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@std@@QEAA@XZ; std::vector<_bstr_t>::vector<_bstr_t>(void)
0x18000bc6b  mov     rax, r8
0x18000bc6e  add     rsp, 28h
0x18000bc72  retn
```
