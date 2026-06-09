# wil::details::WilFailFast(wil::FailureInfo const &)

- ea: `0x180007200`
- end: `0x1800072a7`
- name: `?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z`
- size: `167`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x1800061d0`
- `0x180006560`
- `0x1800068b4`
- `0x1800072b0`

## callees

- `0x1800071d4`
- `0x180007200`
- `0x180015430`
- `0x1800154b0`

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
0x180007200  push    rbx
0x180007202  sub     rsp, 0C0h
0x180007209  mov     rax, cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA
0x180007210  mov     rbx, rcx
0x180007213  test    rax, rax
0x180007216  jz      short loc_18000721D
0x180007218  call    _guard_dispatch_icall
0x18000721d  mov     rax, cs:?g_pfnFailfastWithContextCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007224  test    rax, rax
0x180007227  jz      short loc_180007231
0x180007229  mov     rcx, rbx
0x18000722c  call    _guard_dispatch_icall
0x180007231  xor     edx, edx; Val
0x180007233  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180007238  mov     r8d, 98h; Size
0x18000723e  call    memset
0x180007243  mov     rcx, [rbx+88h]
0x18000724a  mov     r8d, 1; struct _CONTEXT *
0x180007250  mov     [rsp+0C8h+var_90], r8d
0x180007255  mov     [rsp+0C8h+var_A8], 0C0000409h
0x18000725d  mov     [rsp+0C8h+var_A4], r8d
0x180007262  mov     [rsp+0C8h+var_88], 7
0x18000726b  test    rcx, rcx
0x18000726e  jnz     short loc_18000727B
0x180007270  lea     rcx, [rsp+0C8h+var_A8]; this
0x180007275  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x18000727b  movsxd  rax, dword ptr [rbx+8]
0x18000727f  xor     r8d, r8d; struct _CONTEXT *
0x180007282  mov     [rsp+0C8h+var_80], rax
0x180007287  mov     eax, [rbx+40h]
0x18000728a  mov     [rsp+0C8h+var_98], rcx
0x18000728f  lea     rcx, [rsp+0C8h+var_A8]; this
0x180007294  mov     [rsp+0C8h+var_78], rax
0x180007299  mov     [rsp+0C8h+var_90], 3
0x1800072a1  call    ?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z; wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
```
