# CCSPNodeImpl::~CCSPNodeImpl(void)

- ea: `0x180019848`
- end: `0x18001987c`
- name: `??1CCSPNodeImpl@@UEAA@XZ`
- size: `52`
- prototype: `void __fastcall(CCSPNodeImpl *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180007e9c`
- `0x18000cfd8`
- `0x18000e510`
- `0x180019890`

## callees

- `0x180019848`
- `0x18001b010`

## pseudocode

```c
void __fastcall CCSPNodeImpl::~CCSPNodeImpl(CCSPNodeImpl *this)
{
  __int64 v1; // rcx

  *(_QWORD *)this = &CCSPNodeImpl::`vftable'{for `ICSPNode'};
  *((_QWORD *)this + 1) = &CCSPNodeImpl::`vftable'{for `ICSPNodeTransactioning'};
  v1 = *((_QWORD *)this + 3);
  if ( v1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
}

```

## disassembly

```asm
0x180019848  sub     rsp, 28h
0x18001984c  lea     rax, ??_7CCSPNodeImpl@@6BICSPNode@@@; const CCSPNodeImpl::`vftable'{for `ICSPNode'}
0x180019853  mov     [rcx], rax
0x180019856  lea     rax, ??_7CCSPNodeImpl@@6BICSPNodeTransactioning@@@; const CCSPNodeImpl::`vftable'{for `ICSPNodeTransactioning'}
0x18001985d  mov     [rcx+8], rax
0x180019861  mov     rcx, [rcx+18h]
0x180019865  test    rcx, rcx
0x180019868  jz      short loc_180019877
0x18001986a  mov     rax, [rcx]
0x18001986d  mov     rax, [rax+10h]
0x180019871  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019876  nop
0x180019877  add     rsp, 28h
0x18001987b  retn
```
