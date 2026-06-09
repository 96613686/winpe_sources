# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x140006280`
- end: `0x140006327`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x140001800`
- `0x140002e54`
- `0x1400030bc`
- `0x140003358`

## callees

- `0x1400028b8`
- `0x140006280`
- `0x140006330`
- `0x140016010`

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
0x140006280  push    rbx
0x140006282  sub     rsp, 0C0h
0x140006289  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x140006290  mov     rbx, rcx
0x140006293  test    rax, rax
0x140006296  jz      short loc_14000629D
0x140006298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000629d  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400062a4  test    rax, rax
0x1400062a7  jz      short loc_1400062B1
0x1400062a9  mov     rcx, rbx
0x1400062ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400062b1  xor     edx, edx; Val
0x1400062b3  lea     rcx, [rsp+0C8h+var_A8]; void *
0x1400062b8  mov     r8d, 98h; Size
0x1400062be  call    memset_0
0x1400062c3  mov     rcx, [rbx+88h]
0x1400062ca  mov     r8d, 1; struct _CONTEXT *
0x1400062d0  mov     [rsp+0C8h+var_90], r8d
0x1400062d5  mov     [rsp+0C8h+var_A8], 0C0000409h
0x1400062dd  mov     [rsp+0C8h+var_A4], r8d
0x1400062e2  mov     [rsp+0C8h+var_88], 7
0x1400062eb  test    rcx, rcx
0x1400062ee  jnz     short loc_1400062FB
0x1400062f0  lea     rcx, [rsp+0C8h+var_A8]; this
0x1400062f5  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x1400062fb  movsxd  rax, dword ptr [rbx+8]
0x1400062ff  xor     r8d, r8d; struct _CONTEXT *
0x140006302  mov     [rsp+0C8h+var_80], rax
0x140006307  mov     eax, [rbx+40h]
0x14000630a  mov     [rsp+0C8h+var_98], rcx
0x14000630f  lea     rcx, [rsp+0C8h+var_A8]; this
0x140006314  mov     [rsp+0C8h+var_78], rax
0x140006319  mov     [rsp+0C8h+var_90], 3
0x140006321  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
