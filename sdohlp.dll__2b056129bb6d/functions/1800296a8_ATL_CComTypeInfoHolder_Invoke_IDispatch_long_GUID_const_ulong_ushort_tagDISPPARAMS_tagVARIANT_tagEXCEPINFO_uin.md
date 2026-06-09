# ATL::CComTypeInfoHolder::Invoke(IDispatch *,long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x1800296a8`
- end: `0x180029743`
- name: `?Invoke@CComTypeInfoHolder@ATL@@QEAAJPEAUIDispatch@@JAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `155`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, struct IDispatch *, int, const struct _GUID *, LCID lcid, unsigned __int16, struct tagDISPPARAMS *, struct tagVARIANT *, struct tagEXCEPINFO *, unsigned int *)`
- caller_count: `16`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800291e0`
- `0x180029250`
- `0x1800292c0`
- `0x180029330`
- `0x1800293a0`
- `0x180029410`
- `0x180029480`
- `0x1800294f0`
- `0x180029560`
- `0x1800295d0`
- `0x180029640`
- `0x18002edb0`
- `0x18002f9b0`
- `0x180030a00`
- `0x180035960`
- `0x1800359d0`

## callees

- `0x180027ef8`
- `0x1800296a8`
- `0x180058010`

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

  if ( !*((_QWORD *)this + 3) || (result = 0, !*((_QWORD *)this + 5)) )
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
0x1800296a8  mov     [rsp+arg_0], rbx
0x1800296ad  mov     [rsp+arg_8], rsi
0x1800296b2  push    rdi
0x1800296b3  sub     rsp, 50h
0x1800296b7  cmp     qword ptr [rcx+18h], 0
0x1800296bc  mov     edi, r8d
0x1800296bf  mov     rsi, rdx
0x1800296c2  mov     rbx, rcx
0x1800296c5  jz      short loc_1800296CF
0x1800296c7  xor     eax, eax
0x1800296c9  cmp     [rcx+28h], rax
0x1800296cd  jnz     short loc_1800296DB
0x1800296cf  mov     edx, [rsp+58h+lcid]; lcid
0x1800296d6  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x1800296db  mov     rcx, [rbx+18h]
0x1800296df  test    rcx, rcx
0x1800296e2  jz      short loc_180029733
0x1800296e4  mov     rdx, [rsp+58h+arg_48]
0x1800296ec  mov     r8d, edi
0x1800296ef  mov     rax, [rcx]
0x1800296f2  movzx   r9d, [rsp+58h+arg_28]
0x1800296fb  mov     [rsp+58h+var_20], rdx
0x180029700  mov     rdx, [rsp+58h+arg_40]
0x180029708  mov     rax, [rax+58h]
0x18002970c  mov     [rsp+58h+var_28], rdx
0x180029711  mov     rdx, [rsp+58h+arg_38]
0x180029719  mov     [rsp+58h+var_30], rdx
0x18002971e  mov     rdx, [rsp+58h+arg_30]
0x180029726  mov     [rsp+58h+var_38], rdx
0x18002972b  mov     rdx, rsi
0x18002972e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029733  mov     rbx, [rsp+58h+arg_0]
0x180029738  mov     rsi, [rsp+58h+arg_8]
0x18002973d  add     rsp, 50h
0x180029741  pop     rdi
0x180029742  retn
```
