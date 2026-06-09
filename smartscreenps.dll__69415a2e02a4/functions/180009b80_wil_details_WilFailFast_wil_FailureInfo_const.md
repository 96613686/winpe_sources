# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x180009b80`
- end: `0x180009c27`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180006ecc`
- `0x180006f7c`
- `0x180007224`
- `0x18000a298`

## callees

- `0x180009b80`
- `0x180009c30`
- `0x18000c650`
- `0x18000e010`

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
0x180009b80  push    rbx
0x180009b82  sub     rsp, 0C0h
0x180009b89  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x180009b90  mov     rbx, rcx
0x180009b93  test    rax, rax
0x180009b96  jz      short loc_180009B9D
0x180009b98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b9d  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009ba4  test    rax, rax
0x180009ba7  jz      short loc_180009BB1
0x180009ba9  mov     rcx, rbx
0x180009bac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bb1  xor     edx, edx; Val
0x180009bb3  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180009bb8  mov     r8d, 98h; Size
0x180009bbe  call    memset
0x180009bc3  mov     rcx, [rbx+88h]
0x180009bca  mov     r8d, 1; struct _CONTEXT *
0x180009bd0  mov     [rsp+0C8h+var_90], r8d
0x180009bd5  mov     [rsp+0C8h+var_A8], 0C0000409h
0x180009bdd  mov     [rsp+0C8h+var_A4], r8d
0x180009be2  mov     [rsp+0C8h+var_88], 7
0x180009beb  test    rcx, rcx
0x180009bee  jnz     short loc_180009BFB
0x180009bf0  lea     rcx, [rsp+0C8h+var_A8]; this
0x180009bf5  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x180009bfb  movsxd  rax, dword ptr [rbx+8]
0x180009bff  xor     r8d, r8d; struct _CONTEXT *
0x180009c02  mov     [rsp+0C8h+var_80], rax
0x180009c07  mov     eax, [rbx+40h]
0x180009c0a  mov     [rsp+0C8h+var_98], rcx
0x180009c0f  lea     rcx, [rsp+0C8h+var_A8]; this
0x180009c14  mov     [rsp+0C8h+var_78], rax
0x180009c19  mov     [rsp+0C8h+var_90], 3
0x180009c21  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
