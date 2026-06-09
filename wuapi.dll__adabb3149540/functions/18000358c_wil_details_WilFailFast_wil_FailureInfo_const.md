# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x18000358c`
- end: `0x180003633`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x180004580`
- `0x180004a38`
- `0x180004b60`
- `0x180007d00`
- `0x18000a6c8`

## callees

- `0x180002354`
- `0x18000358c`
- `0x180015a00`
- `0x180015a80`

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
0x18000358c  push    rbx
0x18000358e  sub     rsp, 0C0h
0x180003595  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x18000359c  mov     rbx, rcx
0x18000359f  test    rax, rax
0x1800035a2  jz      short loc_1800035A9
0x1800035a4  call    _guard_dispatch_icall
0x1800035a9  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800035b0  test    rax, rax
0x1800035b3  jz      short loc_1800035BD
0x1800035b5  mov     rcx, rbx
0x1800035b8  call    _guard_dispatch_icall
0x1800035bd  xor     edx, edx; Val
0x1800035bf  lea     rcx, [rsp+0C8h+var_A8]; void *
0x1800035c4  mov     r8d, 98h; Size
0x1800035ca  call    memset
0x1800035cf  mov     rcx, [rbx+88h]
0x1800035d6  mov     r8d, 1; struct _CONTEXT *
0x1800035dc  mov     [rsp+0C8h+var_90], r8d
0x1800035e1  mov     [rsp+0C8h+var_A8], 0C0000409h
0x1800035e9  mov     [rsp+0C8h+var_A4], r8d
0x1800035ee  mov     [rsp+0C8h+var_88], 7
0x1800035f7  test    rcx, rcx
0x1800035fa  jnz     short loc_180003607
0x1800035fc  lea     rcx, [rsp+0C8h+var_A8]; this
0x180003601  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x180003607  movsxd  rax, dword ptr [rbx+8]
0x18000360b  xor     r8d, r8d; struct _CONTEXT *
0x18000360e  mov     [rsp+0C8h+var_80], rax
0x180003613  mov     eax, [rbx+40h]
0x180003616  mov     [rsp+0C8h+var_98], rcx
0x18000361b  lea     rcx, [rsp+0C8h+var_A8]; this
0x180003620  mov     [rsp+0C8h+var_78], rax
0x180003625  mov     [rsp+0C8h+var_90], 3
0x18000362d  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
