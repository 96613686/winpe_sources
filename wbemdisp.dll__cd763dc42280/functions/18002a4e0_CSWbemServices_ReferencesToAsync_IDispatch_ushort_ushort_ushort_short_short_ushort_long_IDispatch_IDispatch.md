# CSWbemServices::ReferencesToAsync(IDispatch *,ushort *,ushort *,ushort *,short,short,ushort *,long,IDispatch *,IDispatch *)

- ea: `0x18002a4e0`
- end: `0x18002a6bf`
- name: `?ReferencesToAsync@CSWbemServices@@UEAAJPEAUIDispatch@@PEAG11FF1J00@Z`
- size: `479`
- prototype: `__int64 __usercall@<rax>(CSWbemServices *__hidden this@<rcx>, struct IDispatch *@<rdx>, unsigned __int16 *@<r8>, unsigned __int16 *@<r9>, unsigned __int16 *, __int16, __int16, unsigned __int16 *, int, struct IDispatch *, struct IDispatch *)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800036b0`
- `0x1800036e0`
- `0x1800050dc`
- `0x180006300`
- `0x1800077d0`
- `0x180014f20`
- `0x1800184d4`
- `0x1800257ec`
- `0x180028d54`
- `0x180029248`
- `0x18002a4e0`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002a594`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a59d`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a5d4`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a594`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a59d`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a5d4`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a670`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a67a`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a670`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a67a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSWbemServices::ReferencesToAsync(
        CSWbemServices *this,
        struct IDispatch *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        __int16 a6,
        __int16 a7,
        unsigned __int16 *a8,
        unsigned int a9,
        struct IDispatch *a10,
        struct IDispatch *a11)
{
  int v14; // esi
  CSWbemSecurity *v15; // rcx
  struct IUnknown *Proxy; // r15
  struct IWbemObjectSink *v17; // r13
  struct IWbemContext *IWbemContext; // r12
  const OLECHAR *v19; // rax
  BSTR v20; // rbx
  const OLECHAR *v21; // rax
  BSTR v22; // rdi
  __int64 v23; // r9
  CSWbemSecurity *v24; // rcx
  CWbemObjectSink *v26; // [rsp+40h] [rbp-20h] BYREF
  void *v27[3]; // [rsp+48h] [rbp-18h] BYREF
  bool v28; // [rsp+B0h] [rbp+50h] BYREF
  unsigned __int16 *v29; // [rsp+B8h] [rbp+58h]

  v29 = a4;
  ResetLastErrors();
  if ( !a3 )
  {
    v14 = -2147217400;
LABEL_15:
    CDispatchHelp::RaiseException((CSWbemServices *)((char *)this + 56), v14);
    return (unsigned int)v14;
  }
  v14 = -2147217407;
  v15 = (CSWbemSecurity *)*((_QWORD *)this + 17);
  if ( !v15 )
    goto LABEL_15;
  Proxy = CSWbemSecurity::GetProxy(v15);
  if ( !Proxy )
    goto LABEL_15;
  v26 = 0;
  v17 = CWbemObjectSink::CreateObjectSink(&v26, this, a2, a11, 0, 0);
  if ( v17 )
  {
    IWbemContext = CSWbemNamedValueSet::GetIWbemContext(a10, *((struct IServiceProvider **)this + 18));
    v19 = SysAllocString(L"WQL");
    v20 = SysAllocString(v19);
    v27[1] = v20;
    v21 = FormatReferencesQuery(a3, v29, a5, a6, a7, a8);
    v22 = SysAllocString(v21);
    v27[2] = v22;
    v28 = 0;
    v27[0] = 0;
    if ( (unsigned int)CSWbemSecurity::SetSecurity(*((CSWbemSecurity **)this + 17), &v28, v27) )
    {
      v23 = a9;
      LODWORD(v23) = a9 | 0x100;
      v14 = ((__int64 (__fastcall *)(struct IUnknown *, BSTR, BSTR, __int64, struct IWbemContext *, struct IWbemObjectSink *))Proxy->lpVtbl[7].QueryInterface)(
              Proxy,
              v20,
              v22,
              v23,
              IWbemContext,
              v17);
    }
    CWbemObjectSink::ReleaseTheStubIfNecessary(v26, v14);
    if ( v28 )
      CSWbemSecurity::ResetSecurity(v24, v27[0]);
    SetWbemError((const OLECHAR **)this);
    if ( IWbemContext )
      ((void (__fastcall *)(struct IWbemContext *))IWbemContext->lpVtbl->Release)(IWbemContext);
    SysFreeString(v22);
    SysFreeString(v20);
  }
  else
  {
    v14 = -2147217400;
  }
  ((void (__fastcall *)(struct IUnknown *))Proxy->lpVtbl->Release)(Proxy);
  if ( v14 < 0 )
    goto LABEL_15;
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18002a4e0  mov     [rsp-38h+arg_0], rbx
0x18002a4e5  mov     [rsp-38h+arg_18], r9
0x18002a4ea  push    rbp
0x18002a4eb  push    rsi
0x18002a4ec  push    rdi
0x18002a4ed  push    r12
0x18002a4ef  push    r13
0x18002a4f1  push    r14
0x18002a4f3  push    r15
0x18002a4f5  mov     rbp, rsp
0x18002a4f8  sub     rsp, 60h
0x18002a4fc  mov     rdi, r8
0x18002a4ff  mov     rbx, rdx
0x18002a502  mov     r14, rcx
0x18002a505  call    ?ResetLastErrors@@YAXXZ; ResetLastErrors(void)
0x18002a50a  test    rdi, rdi
0x18002a50d  jnz     short loc_18002A519
0x18002a50f  mov     esi, 80041008h
0x18002a514  jmp     loc_18002A69A
0x18002a519  mov     esi, 80041001h
0x18002a51e  mov     rcx, [r14+88h]; this
0x18002a525  test    rcx, rcx
0x18002a528  jz      loc_18002A69A
0x18002a52e  call    ?GetProxy@CSWbemSecurity@@QEAAPEAUIUnknown@@XZ; CSWbemSecurity::GetProxy(void)
0x18002a533  mov     r15, rax
0x18002a536  test    rax, rax
0x18002a539  jz      loc_18002A69A
0x18002a53f  mov     [rbp+var_20], 0
0x18002a547  mov     [rsp+60h+var_38], 0; unsigned __int16 *
0x18002a550  mov     [rsp+60h+var_40], 0; bool
0x18002a555  mov     r9, [rbp+arg_50]; struct IDispatch *
0x18002a55c  mov     r8, rbx; struct IDispatch *
0x18002a55f  mov     rdx, r14; struct CSWbemServices *
0x18002a562  lea     rcx, [rbp+var_20]; struct CWbemObjectSink **
0x18002a566  call    ?CreateObjectSink@CWbemObjectSink@@SAPEAUIWbemObjectSink@@PEAPEAV1@PEAVCSWbemServices@@PEAUIDispatch@@2_NPEAG@Z; CWbemObjectSink::CreateObjectSink(CWbemObjectSink * *,CSWbemServices *,IDispatch *,IDispatch *,bool,ushort *)
0x18002a56b  mov     r13, rax
0x18002a56e  test    rax, rax
0x18002a571  jz      loc_18002A682
0x18002a577  mov     rdx, [r14+90h]; struct IServiceProvider *
0x18002a57e  mov     rcx, [rbp+arg_48]; struct IDispatch *
0x18002a585  call    ?GetIWbemContext@CSWbemNamedValueSet@@SAPEAUIWbemContext@@PEAUIDispatch@@PEAUIServiceProvider@@@Z; CSWbemNamedValueSet::GetIWbemContext(IDispatch *,IServiceProvider *)
0x18002a58a  mov     r12, rax
0x18002a58d  lea     rcx, aWql; "WQL"
0x18002a594  call    cs:__imp_SysAllocString
0x18002a59a  mov     rcx, rax; psz
0x18002a59d  call    cs:__imp_SysAllocString
0x18002a5a3  mov     rbx, rax
0x18002a5a6  mov     [rbp+var_10], rax
0x18002a5aa  mov     rax, [rbp+arg_38]
0x18002a5ae  mov     [rsp+60h+var_38], rax; unsigned __int16 *
0x18002a5b3  movzx   eax, [rbp+arg_30]
0x18002a5b7  mov     word ptr [rsp+60h+var_40], ax; __int16
0x18002a5bc  movzx   r9d, [rbp+arg_28]; __int16
0x18002a5c1  mov     r8, [rbp+arg_20]; unsigned __int16 *
0x18002a5c5  mov     rdx, [rbp+arg_18]; unsigned __int16 *
0x18002a5c9  mov     rcx, rdi; unsigned __int16 *
0x18002a5cc  call    ?FormatReferencesQuery@@YAPEAGPEAG00FF0@Z; FormatReferencesQuery(ushort *,ushort *,ushort *,short,short,ushort *)
0x18002a5d1  mov     rcx, rax; psz
0x18002a5d4  call    cs:__imp_SysAllocString
0x18002a5da  mov     rdi, rax
0x18002a5dd  mov     [rbp+var_8], rax
0x18002a5e1  mov     [rbp+arg_10], 0
0x18002a5e5  mov     [rbp+var_18], 0
0x18002a5ed  lea     r8, [rbp+var_18]; void **
0x18002a5f1  lea     rdx, [rbp+arg_10]; bool *
0x18002a5f5  mov     rcx, [r14+88h]; this
0x18002a5fc  call    ?SetSecurity@CSWbemSecurity@@QEAAHAEA_NAEAPEAX@Z; CSWbemSecurity::SetSecurity(bool &,void * &)
0x18002a601  test    eax, eax
0x18002a603  jz      short loc_18002A635
0x18002a605  mov     rax, [r15]
0x18002a608  mov     r9d, [rbp+arg_40]
0x18002a60f  bts     r9d, 8
0x18002a614  mov     [rsp+60h+var_38], r13
0x18002a619  mov     qword ptr [rsp+60h+var_40], r12
0x18002a61e  mov     r8, rdi
0x18002a621  mov     rdx, rbx
0x18002a624  mov     rcx, r15
0x18002a627  mov     rax, [rax+0A8h]
0x18002a62e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a633  mov     esi, eax
0x18002a635  mov     edx, esi; int
0x18002a637  mov     rcx, [rbp+var_20]; this
0x18002a63b  call    ?ReleaseTheStubIfNecessary@CWbemObjectSink@@QEAAXJ@Z; CWbemObjectSink::ReleaseTheStubIfNecessary(long)
0x18002a640  cmp     [rbp+arg_10], 0
0x18002a644  jz      short loc_18002A64F
0x18002a646  mov     rdx, [rbp+var_18]; void *
0x18002a64a  call    ?ResetSecurity@CSWbemSecurity@@QEAAXPEAX@Z; CSWbemSecurity::ResetSecurity(void *)
0x18002a64f  mov     rcx, r14; this
0x18002a652  call    ?SetWbemError@@YAXPEAVCSWbemServices@@@Z; SetWbemError(CSWbemServices *)
0x18002a657  test    r12, r12
0x18002a65a  jz      short loc_18002A66D
0x18002a65c  mov     rax, [r12]
0x18002a660  mov     rcx, r12
0x18002a663  mov     rax, [rax+10h]
0x18002a667  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a66c  nop
0x18002a66d  mov     rcx, rdi; bstrString
0x18002a670  call    cs:__imp_SysFreeString
0x18002a676  nop
0x18002a677  mov     rcx, rbx; bstrString
0x18002a67a  call    cs:__imp_SysFreeString
0x18002a680  jmp     short loc_18002A687
0x18002a682  mov     esi, 80041008h
0x18002a687  mov     rax, [r15]
0x18002a68a  mov     rcx, r15
0x18002a68d  mov     rax, [rax+10h]
0x18002a691  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a696  test    esi, esi
0x18002a698  jns     short loc_18002A6A5
0x18002a69a  lea     rcx, [r14+38h]; this
0x18002a69e  mov     edx, esi; int
0x18002a6a0  call    ?RaiseException@CDispatchHelp@@QEAAXJ@Z; CDispatchHelp::RaiseException(long)
0x18002a6a5  mov     eax, esi
0x18002a6a7  mov     rbx, [rsp+60h+arg_0]
0x18002a6af  add     rsp, 60h
0x18002a6b3  pop     r15
0x18002a6b5  pop     r14
0x18002a6b7  pop     r13
0x18002a6b9  pop     r12
0x18002a6bb  pop     rdi
0x18002a6bc  pop     rsi
0x18002a6bd  pop     rbp
0x18002a6be  retn
```
