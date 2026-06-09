# CConfigServiceProvider2Impl::QueryInterface(_GUID const &,void * *)

- ea: `0x1800197a0`
- end: `0x180019806`
- name: `?QueryInterface@CConfigServiceProvider2Impl@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `102`
- prototype: `__int64 __fastcall(CConfigServiceProvider2Impl *__hidden this, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x1800073e0`

## callees

- `0x1800197a0`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall CConfigServiceProvider2Impl::QueryInterface(
        CConfigServiceProvider2Impl *this,
        const struct _GUID *a2,
        void **a3)
{
  if ( !a3 )
    return 2147942487LL;
  if ( *(_QWORD *)&IID_IUnknown.Data1 == *(_QWORD *)&a2->Data1 && *(_QWORD *)IID_IUnknown.Data4 == *(_QWORD *)a2->Data4
    || *(_QWORD *)&GUID_f35e39dc_e18a_48c2_88cb_b3cf48ca6e83.Data1 == *(_QWORD *)&a2->Data1
    && *(_QWORD *)GUID_f35e39dc_e18a_48c2_88cb_b3cf48ca6e83.Data4 == *(_QWORD *)a2->Data4 )
  {
    *a3 = this;
    (*(void (__fastcall **)(CConfigServiceProvider2Impl *))(*(_QWORD *)this + 8LL))(this);
    return 0;
  }
  else
  {
    *a3 = 0;
    return 2147500034LL;
  }
}

```

## disassembly

```asm
0x1800197a0  sub     rsp, 28h
0x1800197a4  test    r8, r8
0x1800197a7  jnz     short loc_1800197B0
0x1800197a9  mov     eax, 80070057h
0x1800197ae  jmp     short loc_180019801
0x1800197b0  mov     rax, qword ptr cs:IID_IUnknown.Data1
0x1800197b7  cmp     rax, [rdx]
0x1800197ba  jnz     short loc_1800197C9
0x1800197bc  mov     rax, qword ptr cs:IID_IUnknown.Data4
0x1800197c3  cmp     rax, [rdx+8]
0x1800197c7  jz      short loc_1800197E2
0x1800197c9  mov     rax, qword ptr cs:_GUID_f35e39dc_e18a_48c2_88cb_b3cf48ca6e83.Data1
0x1800197d0  cmp     rax, [rdx]
0x1800197d3  jnz     short loc_1800197F5
0x1800197d5  mov     rax, qword ptr cs:_GUID_f35e39dc_e18a_48c2_88cb_b3cf48ca6e83.Data4
0x1800197dc  cmp     rax, [rdx+8]
0x1800197e0  jnz     short loc_1800197F5
0x1800197e2  mov     [r8], rcx
0x1800197e5  mov     rax, [rcx]
0x1800197e8  mov     rax, [rax+8]
0x1800197ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800197f1  xor     eax, eax
0x1800197f3  jmp     short loc_180019801
0x1800197f5  mov     qword ptr [r8], 0
0x1800197fc  mov     eax, 80004002h
0x180019801  add     rsp, 28h
0x180019805  retn
```
