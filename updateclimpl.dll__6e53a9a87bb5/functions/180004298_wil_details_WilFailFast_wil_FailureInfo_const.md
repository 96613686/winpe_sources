# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x180004298`
- end: `0x18000433f`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x180003b6c`
- `0x180006cf4`
- `0x180007274`
- `0x18000739c`
- `0x18000d1cc`
- `0x18000d66c`

## callees

- `0x18000426c`
- `0x180004298`
- `0x1800148e0`
- `0x180014960`

## pseudocode

```c
void __fastcall __noreturn wil::details::WilFailFast(wil::details *this, const struct wil::FailureInfo *a2)
{
  struct _EXCEPTION_RECORD *v3; // rdx
  unsigned int v4; // r9d
  __int64 v5; // rcx
  __int64 v6; // rax
  _QWORD v7[21]; // [rsp+20h] [rbp-A8h] BYREF

  if ( wil::g_pfnWilFailFast )
    wil::g_pfnWilFailFast(this, a2);
  if ( wil::details::g_pfnFailfastWithContextCallback )
    wil::details::g_pfnFailfastWithContextCallback(this, a2);
  memset(v7, 0, 0x98u);
  v5 = *((_QWORD *)this + 17);
  LODWORD(v7[3]) = 1;
  v7[0] = 0x1C0000409LL;
  v7[4] = 7;
  if ( !v5 )
    wil::details::WilRaiseFailFastException((wil::details *)v7, v3, (struct _CONTEXT *)1, v4);
  v7[5] = *((int *)this + 2);
  v6 = *((unsigned int *)this + 16);
  v7[2] = v5;
  v7[6] = v6;
  LODWORD(v7[3]) = 3;
  wil::details::WilRaiseFailFastException((wil::details *)v7, v3, 0, v4);
}

```

## disassembly

```asm
0x180004298  push    rbx
0x18000429a  sub     rsp, 0C0h
0x1800042a1  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x1800042a8  mov     rbx, rcx
0x1800042ab  test    rax, rax
0x1800042ae  jz      short loc_1800042B5
0x1800042b0  call    _guard_dispatch_icall
0x1800042b5  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800042bc  test    rax, rax
0x1800042bf  jz      short loc_1800042C9
0x1800042c1  mov     rcx, rbx
0x1800042c4  call    _guard_dispatch_icall
0x1800042c9  xor     edx, edx; Val
0x1800042cb  lea     rcx, [rsp+0C8h+var_A8]; void *
0x1800042d0  mov     r8d, 98h; Size
0x1800042d6  call    memset
0x1800042db  mov     rcx, [rbx+88h]
0x1800042e2  mov     r8d, 1; struct _CONTEXT *
0x1800042e8  mov     [rsp+0C8h+var_90], r8d
0x1800042ed  mov     [rsp+0C8h+var_A8], 0C0000409h
0x1800042f5  mov     [rsp+0C8h+var_A4], r8d
0x1800042fa  mov     [rsp+0C8h+var_88], 7
0x180004303  test    rcx, rcx
0x180004306  jnz     short loc_180004313
0x180004308  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000430d  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x180004313  movsxd  rax, dword ptr [rbx+8]
0x180004317  xor     r8d, r8d; struct _CONTEXT *
0x18000431a  mov     [rsp+0C8h+var_80], rax
0x18000431f  mov     eax, [rbx+40h]
0x180004322  mov     [rsp+0C8h+var_98], rcx
0x180004327  lea     rcx, [rsp+0C8h+var_A8]; this
0x18000432c  mov     [rsp+0C8h+var_78], rax
0x180004331  mov     [rsp+0C8h+var_90], 3
0x180004339  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
