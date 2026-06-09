# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x1800059f0`
- end: `0x180005a97`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800030b0`
- `0x180003318`
- `0x1800035b4`

## callees

- `0x1800059f0`
- `0x180005aa0`
- `0x18001d33a`
- `0x18001e010`

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
0x1800059f0  push    rbx
0x1800059f2  sub     rsp, 0C0h
0x1800059f9  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x180005a00  mov     rbx, rcx
0x180005a03  test    rax, rax
0x180005a06  jz      short loc_180005A0D
0x180005a08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a0d  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005a14  test    rax, rax
0x180005a17  jz      short loc_180005A21
0x180005a19  mov     rcx, rbx
0x180005a1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a21  xor     edx, edx; Val
0x180005a23  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180005a28  mov     r8d, 98h; Size
0x180005a2e  call    memset_0
0x180005a33  mov     rcx, [rbx+88h]
0x180005a3a  mov     r8d, 1; struct _CONTEXT *
0x180005a40  mov     [rsp+0C8h+var_90], r8d
0x180005a45  mov     [rsp+0C8h+var_A8], 0C0000409h
0x180005a4d  mov     [rsp+0C8h+var_A4], r8d
0x180005a52  mov     [rsp+0C8h+var_88], 7
0x180005a5b  test    rcx, rcx
0x180005a5e  jnz     short loc_180005A6B
0x180005a60  lea     rcx, [rsp+0C8h+var_A8]; this
0x180005a65  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x180005a6b  movsxd  rax, dword ptr [rbx+8]
0x180005a6f  xor     r8d, r8d; struct _CONTEXT *
0x180005a72  mov     [rsp+0C8h+var_80], rax
0x180005a77  mov     eax, [rbx+40h]
0x180005a7a  mov     [rsp+0C8h+var_98], rcx
0x180005a7f  lea     rcx, [rsp+0C8h+var_A8]; this
0x180005a84  mov     [rsp+0C8h+var_78], rax
0x180005a89  mov     [rsp+0C8h+var_90], 3
0x180005a91  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
