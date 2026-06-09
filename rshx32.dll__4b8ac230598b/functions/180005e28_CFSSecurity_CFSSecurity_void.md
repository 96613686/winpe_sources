# CFSSecurity::~CFSSecurity(void)

- ea: `0x180005e28`
- end: `0x180005ea2`
- name: `??1CFSSecurity@@UEAA@XZ`
- size: `122`
- prototype: `void __fastcall(CFSSecurity *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180005eb0`

## callees

- `0x180005e28`
- `0x180006284`
- `0x18001e010`

## pseudocode

```c
void __fastcall CFSSecurity::~CFSSecurity(CFSSecurity *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &CFSSecurity::`vftable'{for `ISecurityInformation'};
  *((_QWORD *)this + 1) = &CSecurityInformation::`vftable'{for `IEffectivePermission'};
  *((_QWORD *)this + 2) = &CFSSecurity::`vftable'{for `IEffectivePermission2'};
  *((_QWORD *)this + 3) = &CNTFSSecurity::`vftable'{for `ISecurityObjectTypeInfo'};
  *((_QWORD *)this + 4) = &CFSSecurity::`vftable'{for `ISecurityInformation3'};
  *((_QWORD *)this + 5) = &CFSSecurity::`vftable'{for `ISecurityInformation4'};
  v2 = *((_QWORD *)this + 79);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 79) = 0;
  }
  CNTFSSecurity::~CNTFSSecurity(this);
}

```

## disassembly

```asm
0x180005e28  push    rbx
0x180005e2a  sub     rsp, 20h
0x180005e2e  lea     rax, ??_7CFSSecurity@@6BISecurityInformation@@@; const CFSSecurity::`vftable'{for `ISecurityInformation'}
0x180005e35  mov     rbx, rcx
0x180005e38  mov     [rcx], rax
0x180005e3b  lea     rax, ??_7CSecurityInformation@@6BIEffectivePermission@@@; const CSecurityInformation::`vftable'{for `IEffectivePermission'}
0x180005e42  mov     [rcx+8], rax
0x180005e46  lea     rax, ??_7CFSSecurity@@6BIEffectivePermission2@@@; const CFSSecurity::`vftable'{for `IEffectivePermission2'}
0x180005e4d  mov     [rcx+10h], rax
0x180005e51  lea     rax, ??_7CNTFSSecurity@@6BISecurityObjectTypeInfo@@@; const CNTFSSecurity::`vftable'{for `ISecurityObjectTypeInfo'}
0x180005e58  mov     [rcx+18h], rax
0x180005e5c  lea     rax, ??_7CFSSecurity@@6BISecurityInformation3@@@; const CFSSecurity::`vftable'{for `ISecurityInformation3'}
0x180005e63  mov     [rcx+20h], rax
0x180005e67  lea     rax, ??_7CFSSecurity@@6BISecurityInformation4@@@; const CFSSecurity::`vftable'{for `ISecurityInformation4'}
0x180005e6e  mov     [rcx+28h], rax
0x180005e72  mov     rcx, [rcx+278h]
0x180005e79  test    rcx, rcx
0x180005e7c  jz      short loc_180005E95
0x180005e7e  mov     rax, [rcx]
0x180005e81  mov     rax, [rax+10h]
0x180005e85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e8a  mov     qword ptr [rbx+278h], 0
0x180005e95  mov     rcx, rbx; this
0x180005e98  add     rsp, 20h
0x180005e9c  pop     rbx
0x180005e9d  jmp     ??1CNTFSSecurity@@UEAA@XZ; CNTFSSecurity::~CNTFSSecurity(void)
```
