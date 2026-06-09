# LOG_SVC_CONFIG_PATH_MAPPER::QueryInterface(_GUID const &,void * *)

- ea: `0x18000caa0`
- end: `0x18000cb1b`
- name: `?QueryInterface@LOG_SVC_CONFIG_PATH_MAPPER@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `123`
- prototype: `__int64 __fastcall(LOG_SVC_CONFIG_PATH_MAPPER *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000caa0`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall LOG_SVC_CONFIG_PATH_MAPPER::QueryInterface(
        LOG_SVC_CONFIG_PATH_MAPPER *this,
        const struct _GUID *a2,
        void **a3)
{
  if ( *(_OWORD *)a2 == *(_OWORD *)&IID_IAppHostPathMapper )
  {
    (*(void (__fastcall **)(LOG_SVC_CONFIG_PATH_MAPPER *))(*(_QWORD *)this + 8LL))(this);
    *a3 = this;
    return 0;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IUnknown.Data4 )
  {
    *a3 = this;
    (*(void (__fastcall **)(LOG_SVC_CONFIG_PATH_MAPPER *))(*(_QWORD *)this + 8LL))(this);
    return 0;
  }
  *a3 = 0;
  return 2147500034LL;
}

```

## disassembly

```asm
0x18000caa0  mov     [rsp+arg_0], rbx
0x18000caa5  push    rdi
0x18000caa6  sub     rsp, 20h
0x18000caaa  mov     rax, [rdx]
0x18000caad  mov     rdi, r8
0x18000cab0  cmp     rax, qword ptr cs:IID_IAppHostPathMapper.Data1
0x18000cab7  mov     rbx, rcx
0x18000caba  jnz     short loc_18000CADA
0x18000cabc  mov     rax, [rdx+8]
0x18000cac0  cmp     rax, qword ptr cs:IID_IAppHostPathMapper.Data4
0x18000cac7  jnz     short loc_18000CADA
0x18000cac9  mov     rax, [rcx]
0x18000cacc  mov     rax, [rax+8]
0x18000cad0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cad5  mov     [rdi], rbx
0x18000cad8  jmp     short loc_18000CB02
0x18000cada  mov     rax, [rdx]
0x18000cadd  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x18000cae4  jnz     short loc_18000CB06
0x18000cae6  mov     rax, [rdx+8]
0x18000caea  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x18000caf1  jnz     short loc_18000CB06
0x18000caf3  mov     [r8], rbx
0x18000caf6  mov     rax, [rcx]
0x18000caf9  mov     rax, [rax+8]
0x18000cafd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb02  xor     eax, eax
0x18000cb04  jmp     short loc_18000CB10
0x18000cb06  xor     eax, eax
0x18000cb08  mov     [r8], rax
0x18000cb0b  mov     eax, 80004002h
0x18000cb10  mov     rbx, [rsp+28h+arg_0]
0x18000cb15  add     rsp, 20h
0x18000cb19  pop     rdi
0x18000cb1a  retn
```
