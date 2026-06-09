# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x1800058d0`
- end: `0x180005977`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180002e2c`
- `0x180002eec`
- `0x180002fe8`
- `0x180008118`

## callees

- `0x180002ab4`
- `0x1800058d0`
- `0x180005980`
- `0x18000d010`

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
0x1800058d0  push    rbx
0x1800058d2  sub     rsp, 0C0h
0x1800058d9  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x1800058e0  mov     rbx, rcx
0x1800058e3  test    rax, rax
0x1800058e6  jz      short loc_1800058ED
0x1800058e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058ed  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800058f4  test    rax, rax
0x1800058f7  jz      short loc_180005901
0x1800058f9  mov     rcx, rbx
0x1800058fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005901  xor     edx, edx; Val
0x180005903  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180005908  mov     r8d, 98h; Size
0x18000590e  call    memset_0
0x180005913  mov     rcx, [rbx+88h]
0x18000591a  mov     r8d, 1; struct _CONTEXT *
0x180005920  mov     [rsp+0C8h+var_90], r8d
0x180005925  mov     [rsp+0C8h+var_A8], 0C0000409h
0x18000592d  mov     [rsp+0C8h+var_A4], r8d
0x180005932  mov     [rsp+0C8h+var_88], 7
0x18000593b  test    rcx, rcx
0x18000593e  jnz     short loc_18000594B
0x180005940  lea     rcx, [rsp+0C8h+var_A8]; this
0x180005945  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x18000594b  movsxd  rax, dword ptr [rbx+8]
0x18000594f  xor     r8d, r8d; struct _CONTEXT *
0x180005952  mov     [rsp+0C8h+var_80], rax
0x180005957  mov     eax, [rbx+40h]
0x18000595a  mov     [rsp+0C8h+var_98], rcx
0x18000595f  lea     rcx, [rsp+0C8h+var_A8]; this
0x180005964  mov     [rsp+0C8h+var_78], rax
0x180005969  mov     [rsp+0C8h+var_90], 3
0x180005971  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
