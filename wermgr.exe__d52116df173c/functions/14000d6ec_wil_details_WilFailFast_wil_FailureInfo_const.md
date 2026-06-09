# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x14000d6ec`
- end: `0x14000d793`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x140003df4`
- `0x140004090`
- `0x14000e49c`
- `0x14000fa90`

## callees

- `0x140002fbc`
- `0x14000d6ec`
- `0x14000d79c`
- `0x14001e010`

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
0x14000d6ec  push    rbx
0x14000d6ee  sub     rsp, 0C0h
0x14000d6f5  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x14000d6fc  mov     rbx, rcx
0x14000d6ff  test    rax, rax
0x14000d702  jz      short loc_14000D709
0x14000d704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d709  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000d710  test    rax, rax
0x14000d713  jz      short loc_14000D71D
0x14000d715  mov     rcx, rbx
0x14000d718  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d71d  xor     edx, edx; Val
0x14000d71f  lea     rcx, [rsp+0C8h+var_A8]; void *
0x14000d724  mov     r8d, 98h; Size
0x14000d72a  call    memset_0
0x14000d72f  mov     rcx, [rbx+88h]
0x14000d736  mov     r8d, 1; struct _CONTEXT *
0x14000d73c  mov     [rsp+0C8h+var_90], r8d
0x14000d741  mov     [rsp+0C8h+var_A8], 0C0000409h
0x14000d749  mov     [rsp+0C8h+var_A4], r8d
0x14000d74e  mov     [rsp+0C8h+var_88], 7
0x14000d757  test    rcx, rcx
0x14000d75a  jnz     short loc_14000D767
0x14000d75c  lea     rcx, [rsp+0C8h+var_A8]; this
0x14000d761  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x14000d767  movsxd  rax, dword ptr [rbx+8]
0x14000d76b  xor     r8d, r8d; struct _CONTEXT *
0x14000d76e  mov     [rsp+0C8h+var_80], rax
0x14000d773  mov     eax, [rbx+40h]
0x14000d776  mov     [rsp+0C8h+var_98], rcx
0x14000d77b  lea     rcx, [rsp+0C8h+var_A8]; this
0x14000d780  mov     [rsp+0C8h+var_78], rax
0x14000d785  mov     [rsp+0C8h+var_90], 3
0x14000d78d  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
