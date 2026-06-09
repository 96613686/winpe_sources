# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x140004860`
- end: `0x140004907`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140001f48`
- `0x1400021b0`
- `0x140002444`

## callees

- `0x140001a63`
- `0x140004860`
- `0x140004910`
- `0x140015010`

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
0x140004860  push    rbx
0x140004862  sub     rsp, 0C0h
0x140004869  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x140004870  mov     rbx, rcx
0x140004873  test    rax, rax
0x140004876  jz      short loc_14000487D
0x140004878  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000487d  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140004884  test    rax, rax
0x140004887  jz      short loc_140004891
0x140004889  mov     rcx, rbx
0x14000488c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004891  xor     edx, edx; Val
0x140004893  lea     rcx, [rsp+0C8h+var_A8]; void *
0x140004898  mov     r8d, 98h; Size
0x14000489e  call    memset_0
0x1400048a3  mov     rcx, [rbx+88h]
0x1400048aa  mov     r8d, 1; struct _CONTEXT *
0x1400048b0  mov     [rsp+0C8h+var_90], r8d
0x1400048b5  mov     [rsp+0C8h+var_A8], 0C0000409h
0x1400048bd  mov     [rsp+0C8h+var_A4], r8d
0x1400048c2  mov     [rsp+0C8h+var_88], 7
0x1400048cb  test    rcx, rcx
0x1400048ce  jnz     short loc_1400048DB
0x1400048d0  lea     rcx, [rsp+0C8h+var_A8]; this
0x1400048d5  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x1400048db  movsxd  rax, dword ptr [rbx+8]
0x1400048df  xor     r8d, r8d; struct _CONTEXT *
0x1400048e2  mov     [rsp+0C8h+var_80], rax
0x1400048e7  mov     eax, [rbx+40h]
0x1400048ea  mov     [rsp+0C8h+var_98], rcx
0x1400048ef  lea     rcx, [rsp+0C8h+var_A8]; this
0x1400048f4  mov     [rsp+0C8h+var_78], rax
0x1400048f9  mov     [rsp+0C8h+var_90], 3
0x140004901  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
