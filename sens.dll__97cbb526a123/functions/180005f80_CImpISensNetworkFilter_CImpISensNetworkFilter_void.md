# CImpISensNetworkFilter::~CImpISensNetworkFilter(void)

- ea: `0x180005f80`
- end: `0x18000602f`
- name: `??1CImpISensNetworkFilter@@QEAA@XZ`
- size: `175`
- prototype: `void __fastcall(CImpISensNetworkFilter *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800041fc`
- `0x180006500`

## callees

- `0x180005f80`
- `0x18000b010`

## pseudocode

```c
void __fastcall CImpISensNetworkFilter::~CImpISensNetworkFilter(CImpISensNetworkFilter *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx

  *(_QWORD *)this = &CImpISensNetworkFilter::`vftable'{for `ISensNetwork'};
  *((_QWORD *)this + 1) = &CImpISensNetworkFilter::`vftable'{for `IPublisherFilter'};
  _InterlockedDecrement(&g_cFilterObj);
  v2 = *((_QWORD *)this + 3);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = *((_QWORD *)this + 4);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = *((_QWORD *)this + 5);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v5 = *((_QWORD *)this + 6);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  v6 = *((_QWORD *)this + 7);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  v7 = *((_QWORD *)this + 8);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
}

```

## disassembly

```asm
0x180005f80  push    rbx
0x180005f82  sub     rsp, 20h
0x180005f86  lea     rax, ??_7CImpISensNetworkFilter@@6BISensNetwork@@@; const CImpISensNetworkFilter::`vftable'{for `ISensNetwork'}
0x180005f8d  mov     rbx, rcx
0x180005f90  mov     [rcx], rax
0x180005f93  lea     rax, ??_7CImpISensNetworkFilter@@6BIPublisherFilter@@@; const CImpISensNetworkFilter::`vftable'{for `IPublisherFilter'}
0x180005f9a  mov     [rcx+8], rax
0x180005f9e  lock dec cs:?g_cFilterObj@@3JA; long g_cFilterObj
0x180005fa5  mov     rcx, [rcx+18h]
0x180005fa9  test    rcx, rcx
0x180005fac  jz      short loc_180005FBA
0x180005fae  mov     rax, [rcx]
0x180005fb1  mov     rax, [rax+10h]
0x180005fb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fba  mov     rcx, [rbx+20h]
0x180005fbe  test    rcx, rcx
0x180005fc1  jz      short loc_180005FCF
0x180005fc3  mov     rax, [rcx]
0x180005fc6  mov     rax, [rax+10h]
0x180005fca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fcf  mov     rcx, [rbx+28h]
0x180005fd3  test    rcx, rcx
0x180005fd6  jz      short loc_180005FE4
0x180005fd8  mov     rax, [rcx]
0x180005fdb  mov     rax, [rax+10h]
0x180005fdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fe4  mov     rcx, [rbx+30h]
0x180005fe8  test    rcx, rcx
0x180005feb  jnz     short loc_180006005
0x180005fed  mov     rcx, [rbx+38h]
0x180005ff1  test    rcx, rcx
0x180005ff4  jnz     short loc_180006013
0x180005ff6  mov     rcx, [rbx+40h]
0x180005ffa  test    rcx, rcx
0x180005ffd  jnz     short loc_180006021
0x180005fff  add     rsp, 20h
0x180006003  pop     rbx
0x180006004  retn
0x180006005  mov     rax, [rcx]
0x180006008  mov     rax, [rax+10h]
0x18000600c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006011  jmp     short loc_180005FED
0x180006013  mov     rax, [rcx]
0x180006016  mov     rax, [rax+10h]
0x18000601a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000601f  jmp     short loc_180005FF6
0x180006021  mov     rax, [rcx]
0x180006024  mov     rax, [rax+10h]
0x180006028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000602d  jmp     short loc_180005FFF
```
