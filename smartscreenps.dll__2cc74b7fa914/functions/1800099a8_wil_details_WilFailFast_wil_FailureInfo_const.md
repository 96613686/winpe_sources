# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x1800099a8`
- end: `0x180009a4f`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180006ebc`
- `0x180006f6c`
- `0x180007200`
- `0x18000a058`

## callees

- `0x1800099a8`
- `0x180009a58`
- `0x18000c370`
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
0x1800099a8  push    rbx
0x1800099aa  sub     rsp, 0C0h
0x1800099b1  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x1800099b8  mov     rbx, rcx
0x1800099bb  test    rax, rax
0x1800099be  jz      short loc_1800099C5
0x1800099c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099c5  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800099cc  test    rax, rax
0x1800099cf  jz      short loc_1800099D9
0x1800099d1  mov     rcx, rbx
0x1800099d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099d9  xor     edx, edx; Val
0x1800099db  lea     rcx, [rsp+0C8h+var_A8]; void *
0x1800099e0  mov     r8d, 98h; Size
0x1800099e6  call    memset
0x1800099eb  mov     rcx, [rbx+88h]
0x1800099f2  mov     r8d, 1; struct _CONTEXT *
0x1800099f8  mov     [rsp+0C8h+var_90], r8d
0x1800099fd  mov     [rsp+0C8h+var_A8], 0C0000409h
0x180009a05  mov     [rsp+0C8h+var_A4], r8d
0x180009a0a  mov     [rsp+0C8h+var_88], 7
0x180009a13  test    rcx, rcx
0x180009a16  jnz     short loc_180009A23
0x180009a18  lea     rcx, [rsp+0C8h+var_A8]; this
0x180009a1d  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x180009a23  movsxd  rax, dword ptr [rbx+8]
0x180009a27  xor     r8d, r8d; struct _CONTEXT *
0x180009a2a  mov     [rsp+0C8h+var_80], rax
0x180009a2f  mov     eax, [rbx+40h]
0x180009a32  mov     [rsp+0C8h+var_98], rcx
0x180009a37  lea     rcx, [rsp+0C8h+var_A8]; this
0x180009a3c  mov     [rsp+0C8h+var_78], rax
0x180009a41  mov     [rsp+0C8h+var_90], 3
0x180009a49  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
