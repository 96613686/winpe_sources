# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x14000cbf0`
- end: `0x14000cc97`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140007f20`
- `0x140008188`
- `0x140008424`

## callees

- `0x14000cbf0`
- `0x14000cca0`
- `0x14001094e`
- `0x140011010`

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
0x14000cbf0  push    rbx
0x14000cbf2  sub     rsp, 0C0h
0x14000cbf9  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x14000cc00  mov     rbx, rcx
0x14000cc03  test    rax, rax
0x14000cc06  jz      short loc_14000CC0D
0x14000cc08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cc0d  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000cc14  test    rax, rax
0x14000cc17  jz      short loc_14000CC21
0x14000cc19  mov     rcx, rbx
0x14000cc1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cc21  xor     edx, edx; Val
0x14000cc23  lea     rcx, [rsp+0C8h+var_A8]; void *
0x14000cc28  mov     r8d, 98h; Size
0x14000cc2e  call    memset_0
0x14000cc33  mov     rcx, [rbx+88h]
0x14000cc3a  mov     r8d, 1; struct _CONTEXT *
0x14000cc40  mov     [rsp+0C8h+var_90], r8d
0x14000cc45  mov     [rsp+0C8h+var_A8], 0C0000409h
0x14000cc4d  mov     [rsp+0C8h+var_A4], r8d
0x14000cc52  mov     [rsp+0C8h+var_88], 7
0x14000cc5b  test    rcx, rcx
0x14000cc5e  jnz     short loc_14000CC6B
0x14000cc60  lea     rcx, [rsp+0C8h+var_A8]; this
0x14000cc65  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x14000cc6b  movsxd  rax, dword ptr [rbx+8]
0x14000cc6f  xor     r8d, r8d; struct _CONTEXT *
0x14000cc72  mov     [rsp+0C8h+var_80], rax
0x14000cc77  mov     eax, [rbx+40h]
0x14000cc7a  mov     [rsp+0C8h+var_98], rcx
0x14000cc7f  lea     rcx, [rsp+0C8h+var_A8]; this
0x14000cc84  mov     [rsp+0C8h+var_78], rax
0x14000cc89  mov     [rsp+0C8h+var_90], 3
0x14000cc91  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
