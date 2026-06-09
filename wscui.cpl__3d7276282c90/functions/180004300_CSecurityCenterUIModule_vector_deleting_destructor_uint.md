# CSecurityCenterUIModule::`vector deleting destructor'(uint)

- ea: `0x180004300`
- end: `0x18000432f`
- name: `??_ECSecurityCenterUIModule@@UEAAPEAXI@Z`
- size: `47`
- prototype: `void *__fastcall(CSecurityCenterUIModule *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x1800019c0`
- `0x180001cc8`
- `0x180004300`

## pseudocode

```c
CSecurityCenterUIModule *__fastcall CSecurityCenterUIModule::`vector deleting destructor'(
        CSecurityCenterUIModule *this,
        char a2)
{
  ATL::CAtlDllModuleT<CSecurityCenterUIModule>::~CAtlDllModuleT<CSecurityCenterUIModule>(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180004300  mov     [rsp+arg_0], rbx
0x180004305  push    rdi
0x180004306  sub     rsp, 20h
0x18000430a  mov     ebx, edx
0x18000430c  mov     rdi, rcx
0x18000430f  call    ??1?$CAtlDllModuleT@VCSecurityCenterUIModule@@@ATL@@UEAA@XZ; ATL::CAtlDllModuleT<CSecurityCenterUIModule>::~CAtlDllModuleT<CSecurityCenterUIModule>(void)
0x180004314  test    bl, 1
0x180004317  jz      short loc_180004321
0x180004319  mov     rcx, rdi; Block
0x18000431c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004321  mov     rbx, [rsp+28h+arg_0]
0x180004326  mov     rax, rdi
0x180004329  add     rsp, 20h
0x18000432d  pop     rdi
0x18000432e  retn
```
