# ATL::CComTypeInfoHolder::Invoke(IDispatch *,long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x1800074c8`
- end: `0x180007566`
- name: `?Invoke@CComTypeInfoHolder@ATL@@QEAAJPEAUIDispatch@@JAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `158`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, struct IDispatch *, int, const struct _GUID *, LCID lcid, unsigned __int16, struct tagDISPPARAMS *, struct tagVARIANT *, struct tagEXCEPINFO *, unsigned int *)`
- caller_count: `20`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180007460`
- `0x180008550`
- `0x180009160`
- `0x18000a650`
- `0x18000bae0`
- `0x18000d230`
- `0x18000f680`
- `0x1800104e0`
- `0x180012160`
- `0x1800121d0`
- `0x180012240`
- `0x1800122b0`
- `0x180012320`
- `0x180014d40`
- `0x1800159e0`
- `0x180016ab0`
- `0x180017980`
- `0x180018800`
- `0x180019180`
- `0x180019bb0`

## callees

- `0x180007044`
- `0x1800074c8`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall ATL::CComTypeInfoHolder::Invoke(
        ATL::CComTypeInfoHolder *this,
        struct IDispatch *a2,
        unsigned int a3,
        const struct _GUID *a4,
        LCID lcid,
        unsigned __int16 a6,
        struct tagDISPPARAMS *a7,
        struct tagVARIANT *a8,
        struct tagEXCEPINFO *a9,
        unsigned int *a10)
{
  __int64 result; // rax
  __int64 v14; // rcx

  result = 0;
  if ( !*((_QWORD *)this + 3) || !*((_QWORD *)this + 5) )
    result = ATL::CComTypeInfoHolder::GetTI(this, lcid);
  v14 = *((_QWORD *)this + 3);
  if ( v14 )
    return (*(__int64 (__fastcall **)(__int64, struct IDispatch *, _QWORD, _QWORD, struct tagDISPPARAMS *, struct tagVARIANT *, struct tagEXCEPINFO *, unsigned int *))(*(_QWORD *)v14 + 88LL))(
             v14,
             a2,
             a3,
             a6,
             a7,
             a8,
             a9,
             a10);
  return result;
}

```

## disassembly

```asm
0x1800074c8  mov     [rsp+arg_0], rbx
0x1800074cd  mov     [rsp+arg_8], rsi
0x1800074d2  push    rdi
0x1800074d3  sub     rsp, 50h
0x1800074d7  xor     eax, eax
0x1800074d9  mov     edi, r8d
0x1800074dc  mov     rsi, rdx
0x1800074df  mov     rbx, rcx
0x1800074e2  cmp     [rcx+18h], rax
0x1800074e6  jz      short loc_1800074EE
0x1800074e8  cmp     [rcx+28h], rax
0x1800074ec  jnz     short loc_1800074FA
0x1800074ee  mov     edx, [rsp+58h+lcid]; lcid
0x1800074f5  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x1800074fa  mov     rcx, [rbx+18h]
0x1800074fe  test    rcx, rcx
0x180007501  jz      short loc_180007555
0x180007503  mov     rax, [rcx]
0x180007506  mov     r8d, edi
0x180007509  movzx   r9d, [rsp+58h+arg_28]
0x180007512  mov     rdx, rsi
0x180007515  mov     r10, [rax+58h]
0x180007519  mov     rax, [rsp+58h+arg_48]
0x180007521  mov     [rsp+58h+var_20], rax
0x180007526  mov     rax, [rsp+58h+arg_40]
0x18000752e  mov     [rsp+58h+var_28], rax
0x180007533  mov     rax, [rsp+58h+arg_38]
0x18000753b  mov     [rsp+58h+var_30], rax
0x180007540  mov     rax, [rsp+58h+arg_30]
0x180007548  mov     [rsp+58h+var_38], rax
0x18000754d  mov     rax, r10
0x180007550  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007555  mov     rbx, [rsp+58h+arg_0]
0x18000755a  mov     rsi, [rsp+58h+arg_8]
0x18000755f  add     rsp, 50h
0x180007563  pop     rdi
0x180007564  retn
```
