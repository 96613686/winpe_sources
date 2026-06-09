# CConfigServiceProvider2Impl::~CConfigServiceProvider2Impl(void)

- ea: `0x18001943c`
- end: `0x180019470`
- name: `??1CConfigServiceProvider2Impl@@UEAA@XZ`
- size: `52`
- prototype: `void __fastcall(CConfigServiceProvider2Impl *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180007254`
- `0x180019480`

## callees

- `0x18001943c`
- `0x18001b010`

## pseudocode

```c
void __fastcall CConfigServiceProvider2Impl::~CConfigServiceProvider2Impl(CConfigServiceProvider2Impl *this)
{
  __int64 v1; // rcx

  *(_QWORD *)this = &CConfigServiceProvider2Impl::`vftable'{for `IConfigServiceProvider2'};
  *((_QWORD *)this + 1) = &CConfigServiceProvider2Impl::`vftable'{for `ICSPValidate'};
  v1 = *((_QWORD *)this + 2);
  if ( v1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
}

```

## disassembly

```asm
0x18001943c  sub     rsp, 28h
0x180019440  lea     rax, ??_7CConfigServiceProvider2Impl@@6BIConfigServiceProvider2@@@; const CConfigServiceProvider2Impl::`vftable'{for `IConfigServiceProvider2'}
0x180019447  mov     [rcx], rax
0x18001944a  lea     rax, ??_7CConfigServiceProvider2Impl@@6BICSPValidate@@@; const CConfigServiceProvider2Impl::`vftable'{for `ICSPValidate'}
0x180019451  mov     [rcx+8], rax
0x180019455  mov     rcx, [rcx+10h]
0x180019459  test    rcx, rcx
0x18001945c  jz      short loc_18001946B
0x18001945e  mov     rax, [rcx]
0x180019461  mov     rax, [rax+10h]
0x180019465  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001946a  nop
0x18001946b  add     rsp, 28h
0x18001946f  retn
```
