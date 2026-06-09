# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x18000b62c`
- end: `0x18000b6d3`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180002b48`
- `0x180002dc0`
- `0x180003070`

## callees

- `0x18000b62c`
- `0x18000b6dc`
- `0x18000d6d2`
- `0x18000e010`

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
0x18000b62c  push    rbx
0x18000b62e  sub     rsp, 0C0h
0x18000b635  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x18000b63c  mov     rbx, rcx
0x18000b63f  test    rax, rax
0x18000b642  jz      short loc_18000B649
0x18000b644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b649  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000b650  test    rax, rax
0x18000b653  jz      short loc_18000B65D
0x18000b655  mov     rcx, rbx
0x18000b658  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b65d  xor     edx, edx; Val
0x18000b65f  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18000b664  mov     r8d, 98h; Size
0x18000b66a  call    memset_0
0x18000b66f  mov     rcx, [rbx+88h]
0x18000b676  mov     r8d, 1; struct _CONTEXT *
0x18000b67c  mov     [rsp+0C8h+var_90], r8d
0x18000b681  mov     [rsp+0C8h+var_A8], 0C0000409h
0x18000b689  mov     [rsp+0C8h+var_A4], r8d
0x18000b68e  mov     [rsp+0C8h+var_88], 7
0x18000b697  test    rcx, rcx
0x18000b69a  jnz     short loc_18000B6A7
0x18000b69c  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000b6a1  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x18000b6a7  movsxd  rax, dword ptr [rbx+8]
0x18000b6ab  xor     r8d, r8d; struct _CONTEXT *
0x18000b6ae  mov     [rsp+0C8h+var_80], rax
0x18000b6b3  mov     eax, [rbx+40h]
0x18000b6b6  mov     [rsp+0C8h+var_98], rcx
0x18000b6bb  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000b6c0  mov     [rsp+0C8h+var_78], rax
0x18000b6c5  mov     [rsp+0C8h+var_90], 3
0x18000b6cd  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
