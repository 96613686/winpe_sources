# CRegistry::CRegistry(void)

- ea: `0x1800034f0`
- end: `0x180003545`
- name: `??0CRegistry@@QEAA@XZ`
- size: `85`
- prototype: `CRegistry *__fastcall(CRegistry *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180002ea4`
- `0x1800174ec`

## callees

- `0x1800034f0`
- `0x180003ef0`
- `0x18000b410`

## pseudocode

```c
CRegistry *__fastcall CRegistry::CRegistry(CRegistry *this)
{
  *((_QWORD *)this + 3) = &dword_1800323BC;
  *((_BYTE *)this + 36) = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *(_QWORD *)this = 0;
  CRegistry::SetDefaultValues(this);
  if ( !CRegistry::s_fPlatformSet )
    CRegistry::s_fPlatformSet = CRegistry::SetPlatformID();
  return this;
}

```

## disassembly

```asm
0x1800034f0  mov     [rsp+arg_0], rcx
0x1800034f5  push    rbx
0x1800034f6  sub     rsp, 20h
0x1800034fa  mov     rbx, rcx
0x1800034fd  lea     rax, dword_1800323BC
0x180003504  mov     [rcx+18h], rax
0x180003508  mov     byte ptr [rcx+24h], 0
0x18000350c  mov     qword ptr [rcx+8], 0
0x180003514  mov     qword ptr [rcx+10h], 0
0x18000351c  mov     qword ptr [rcx], 0
0x180003523  call    ?SetDefaultValues@CRegistry@@AEAAXXZ; CRegistry::SetDefaultValues(void)
0x180003528  cmp     cs:?s_fPlatformSet@CRegistry@@0HA, 0; int CRegistry::s_fPlatformSet
0x18000352f  jnz     short loc_18000353C
0x180003531  call    ?SetPlatformID@CRegistry@@CAHXZ; CRegistry::SetPlatformID(void)
0x180003536  mov     cs:?s_fPlatformSet@CRegistry@@0HA, eax; int CRegistry::s_fPlatformSet
0x18000353c  mov     rax, rbx
0x18000353f  add     rsp, 20h
0x180003543  pop     rbx
0x180003544  retn
```
