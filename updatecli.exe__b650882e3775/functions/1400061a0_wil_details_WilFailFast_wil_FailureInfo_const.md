# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x1400061a0`
- end: `0x140006247`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x140002f78`
- `0x1400031e8`
- `0x14000347c`
- `0x140006aec`

## callees

- `0x140002c38`
- `0x1400061a0`
- `0x140006250`
- `0x14000c010`

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
0x1400061a0  push    rbx
0x1400061a2  sub     rsp, 0C0h
0x1400061a9  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x1400061b0  mov     rbx, rcx
0x1400061b3  test    rax, rax
0x1400061b6  jz      short loc_1400061BD
0x1400061b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400061bd  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400061c4  test    rax, rax
0x1400061c7  jz      short loc_1400061D1
0x1400061c9  mov     rcx, rbx
0x1400061cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400061d1  xor     edx, edx; Val
0x1400061d3  lea     rcx, [rsp+0C8h+var_A8]; void *
0x1400061d8  mov     r8d, 98h; Size
0x1400061de  call    memset_0
0x1400061e3  mov     rcx, [rbx+88h]
0x1400061ea  mov     r8d, 1; struct _CONTEXT *
0x1400061f0  mov     [rsp+0C8h+var_90], r8d
0x1400061f5  mov     [rsp+0C8h+var_A8], 0C0000409h
0x1400061fd  mov     [rsp+0C8h+var_A4], r8d
0x140006202  mov     [rsp+0C8h+var_88], 7
0x14000620b  test    rcx, rcx
0x14000620e  jnz     short loc_14000621B
0x140006210  lea     rcx, [rsp+0C8h+var_A8]; this
0x140006215  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x14000621b  movsxd  rax, dword ptr [rbx+8]
0x14000621f  xor     r8d, r8d; struct _CONTEXT *
0x140006222  mov     [rsp+0C8h+var_80], rax
0x140006227  mov     eax, [rbx+40h]
0x14000622a  mov     [rsp+0C8h+var_98], rcx
0x14000622f  lea     rcx, [rsp+0C8h+var_A8]; this
0x140006234  mov     [rsp+0C8h+var_78], rax
0x140006239  mov     [rsp+0C8h+var_90], 3
0x140006241  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
