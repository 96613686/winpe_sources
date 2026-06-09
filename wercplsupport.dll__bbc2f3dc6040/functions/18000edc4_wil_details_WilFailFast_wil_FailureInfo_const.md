# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x18000edc4`
- end: `0x18000ee6b`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800088fc`
- `0x180008b5c`
- `0x180008df4`

## callees

- `0x18000edc4`
- `0x18000ee74`
- `0x18001218a`
- `0x180013010`

## pseudocode

```c
void __fastcall __noreturn wil::details::WilFailFast(wil::details *this, const struct wil::FailureInfo *a2)
{
  struct _EXCEPTION_RECORD *v3; // rdx
  unsigned int v4; // r9d
  __int64 v5; // rcx
  __int64 v6; // rax
  _DWORD v7[4]; // [rsp+20h] [rbp-A8h] BYREF
  __int64 v8; // [rsp+30h] [rbp-98h]
  int v9; // [rsp+38h] [rbp-90h]
  __int64 v10; // [rsp+40h] [rbp-88h]
  __int64 v11; // [rsp+48h] [rbp-80h]
  __int64 v12; // [rsp+50h] [rbp-78h]

  if ( wil::g_pfnWilFailFast )
    wil::g_pfnWilFailFast(this, a2);
  if ( wil::details::g_pfnFailfastWithContextCallback )
    wil::details::g_pfnFailfastWithContextCallback(this, a2);
  memset_0(v7, 0, 0x98u);
  v5 = *((_QWORD *)this + 17);
  v9 = 1;
  v7[0] = -1073740791;
  v7[1] = 1;
  v10 = 7;
  if ( !v5 )
    wil::details::WilRaiseFailFastException((wil::details *)v7, v3, (struct _CONTEXT *)1, v4);
  v11 = *((int *)this + 2);
  v6 = *((unsigned int *)this + 16);
  v8 = v5;
  v12 = v6;
  v9 = 3;
  wil::details::WilRaiseFailFastException((wil::details *)v7, v3, 0, v4);
}

```

## disassembly

```asm
0x18000edc4  push    rbx
0x18000edc6  sub     rsp, 0C0h
0x18000edcd  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x18000edd4  mov     rbx, rcx
0x18000edd7  test    rax, rax
0x18000edda  jz      short loc_18000EDE1
0x18000eddc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ede1  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000ede8  test    rax, rax
0x18000edeb  jz      short loc_18000EDF5
0x18000eded  mov     rcx, rbx
0x18000edf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000edf5  xor     edx, edx; Val
0x18000edf7  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18000edfc  mov     r8d, 98h; Size
0x18000ee02  call    memset_0
0x18000ee07  mov     rcx, [rbx+88h]
0x18000ee0e  mov     r8d, 1; struct _CONTEXT *
0x18000ee14  mov     [rsp+0C8h+var_90], r8d
0x18000ee19  mov     [rsp+0C8h+var_A8], 0C0000409h
0x18000ee21  mov     [rsp+0C8h+var_A4], r8d
0x18000ee26  mov     [rsp+0C8h+var_88], 7
0x18000ee2f  test    rcx, rcx
0x18000ee32  jnz     short loc_18000EE3F
0x18000ee34  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000ee39  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x18000ee3f  movsxd  rax, dword ptr [rbx+8]
0x18000ee43  xor     r8d, r8d; struct _CONTEXT *
0x18000ee46  mov     [rsp+0C8h+var_80], rax
0x18000ee4b  mov     eax, [rbx+40h]
0x18000ee4e  mov     [rsp+0C8h+var_98], rcx
0x18000ee53  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000ee58  mov     [rsp+0C8h+var_78], rax
0x18000ee5d  mov     [rsp+0C8h+var_90], 3
0x18000ee65  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
