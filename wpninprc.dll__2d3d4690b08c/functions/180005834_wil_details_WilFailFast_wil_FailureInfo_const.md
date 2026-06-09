# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x180005834`
- end: `0x1800058db`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800039c0`
- `0x180003c30`
- `0x180003ecc`

## callees

- `0x18000209e`
- `0x180005834`
- `0x1800058e4`
- `0x180007010`

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
0x180005834  push    rbx
0x180005836  sub     rsp, 0C0h
0x18000583d  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x180005844  mov     rbx, rcx
0x180005847  test    rax, rax
0x18000584a  jz      short loc_180005851
0x18000584c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005851  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005858  test    rax, rax
0x18000585b  jz      short loc_180005865
0x18000585d  mov     rcx, rbx
0x180005860  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005865  xor     edx, edx; Val
0x180005867  lea     rcx, [rsp+0C8h+var_A8]; void *
0x18000586c  mov     r8d, 98h; Size
0x180005872  call    memset_0
0x180005877  mov     rcx, [rbx+88h]
0x18000587e  mov     r8d, 1; struct _CONTEXT *
0x180005884  mov     [rsp+0C8h+var_90], r8d
0x180005889  mov     [rsp+0C8h+var_A8], 0C0000409h
0x180005891  mov     [rsp+0C8h+var_A4], r8d
0x180005896  mov     [rsp+0C8h+var_88], 7
0x18000589f  test    rcx, rcx
0x1800058a2  jnz     short loc_1800058AF
0x1800058a4  lea     rcx, [rsp+0C8h+var_A8]; this
0x1800058a9  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x1800058af  movsxd  rax, dword ptr [rbx+8]
0x1800058b3  xor     r8d, r8d; struct _CONTEXT *
0x1800058b6  mov     [rsp+0C8h+var_80], rax
0x1800058bb  mov     eax, [rbx+40h]
0x1800058be  mov     [rsp+0C8h+var_98], rcx
0x1800058c3  lea     rcx, [rsp+0C8h+var_A8]; this
0x1800058c8  mov     [rsp+0C8h+var_78], rax
0x1800058cd  mov     [rsp+0C8h+var_90], 3
0x1800058d5  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
