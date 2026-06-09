# CSWbemServices::AssociatorsOfAsync(IDispatch *,ushort *,ushort *,ushort *,ushort *,ushort *,short,short,ushort *,ushort *,long,IDispatch *,IDispatch *)

- ea: `0x1800296a0`
- end: `0x18002989c`
- name: `?AssociatorsOfAsync@CSWbemServices@@UEAAJPEAUIDispatch@@PEAG1111FF11J00@Z`
- size: `508`
- prototype: `__int64 __fastcall(CSWbemServices *__hidden this, struct IDispatch *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, __int16, __int16, unsigned __int16 *, unsigned __int16 *, int, struct IDispatch *, struct IDispatch *)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800036b0`
- `0x1800036e0`
- `0x1800050dc`
- `0x180006300`
- `0x1800077d0`
- `0x18000cd1c`
- `0x180014f20`
- `0x1800184d4`
- `0x180028d54`
- `0x180029248`
- `0x1800296a0`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180029750`
- `OLEAUT32!__imp_SysAllocString` at `0x180029750`
- `OLEAUT32!__imp_SysFreeString` at `0x180029841`
- `OLEAUT32!__imp_SysFreeString` at `0x18002984a`
- `OLEAUT32!__imp_SysFreeString` at `0x180029841`
- `OLEAUT32!__imp_SysFreeString` at `0x18002984a`

## pseudocode

```c
__int64 __fastcall CSWbemServices::AssociatorsOfAsync(
        CSWbemServices *this,
        struct IDispatch *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        __int16 a8,
        __int16 a9,
        unsigned __int16 *a10,
        unsigned __int16 *a11,
        unsigned int a12,
        struct IDispatch *a13,
        struct IDispatch *a14)
{
  int v18; // ebx
  CSWbemSecurity *v19; // rcx
  struct IUnknown *Proxy; // rsi
  struct IWbemObjectSink *v21; // rbp
  struct IWbemContext *IWbemContext; // r14
  OLECHAR *v23; // r12
  unsigned __int16 *v24; // rax
  CSWbemSecurity *v25; // rcx
  OLECHAR *v26; // r15
  __int64 v27; // r9
  CSWbemSecurity *v28; // rcx
  CWbemObjectSink *v30; // [rsp+50h] [rbp-58h] BYREF
  void *v31; // [rsp+58h] [rbp-50h] BYREF
  bool v32; // [rsp+C0h] [rbp+18h] BYREF

  ResetLastErrors();
  if ( !a3 )
  {
    v18 = -2147217400;
LABEL_14:
    CDispatchHelp::RaiseException((CSWbemServices *)((char *)this + 56), v18);
    return (unsigned int)v18;
  }
  v19 = (CSWbemSecurity *)*((_QWORD *)this + 17);
  v18 = -2147217407;
  if ( !v19 )
    goto LABEL_14;
  Proxy = CSWbemSecurity::GetProxy(v19);
  if ( !Proxy )
    goto LABEL_14;
  v30 = 0;
  v21 = CWbemObjectSink::CreateObjectSink(&v30, this, a2, a14, 0, 0);
  if ( v21 )
  {
    IWbemContext = CSWbemNamedValueSet::GetIWbemContext(a13, *((struct IServiceProvider **)this + 18));
    v23 = SysAllocString(L"WQL");
    v24 = FormatAssociatorsQuery(a3, a4, a5, a6, a7, a8, a9, a10, a11);
    v25 = (CSWbemSecurity *)*((_QWORD *)this + 17);
    v32 = 0;
    v26 = v24;
    v31 = 0;
    if ( (unsigned int)CSWbemSecurity::SetSecurity(v25, &v32, &v31) )
    {
      v27 = a12;
      LODWORD(v27) = a12 | 0x100;
      v18 = ((__int64 (__fastcall *)(struct IUnknown *, OLECHAR *, OLECHAR *, __int64, struct IWbemContext *, struct IWbemObjectSink *))Proxy->lpVtbl[7].QueryInterface)(
              Proxy,
              v23,
              v26,
              v27,
              IWbemContext,
              v21);
    }
    CWbemObjectSink::ReleaseTheStubIfNecessary(v30, v18);
    if ( v32 )
      CSWbemSecurity::ResetSecurity(v28, v31);
    SetWbemError((const OLECHAR **)this);
    SysFreeString(v26);
    SysFreeString(v23);
    if ( IWbemContext )
      ((void (__fastcall *)(struct IWbemContext *))IWbemContext->lpVtbl->Release)(IWbemContext);
  }
  else
  {
    v18 = -2147217400;
  }
  ((void (__fastcall *)(struct IUnknown *))Proxy->lpVtbl->Release)(Proxy);
  if ( v18 < 0 )
    goto LABEL_14;
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x1800296a0  push    rbx
0x1800296a2  push    rbp
0x1800296a3  push    rsi
0x1800296a4  push    rdi
0x1800296a5  push    r12
0x1800296a7  push    r13
0x1800296a9  push    r14
0x1800296ab  push    r15
0x1800296ad  sub     rsp, 68h
0x1800296b1  mov     r13, r9
0x1800296b4  mov     r15, r8
0x1800296b7  mov     rbp, rdx
0x1800296ba  mov     rdi, rcx
0x1800296bd  call    ?ResetLastErrors@@YAXXZ; ResetLastErrors(void)
0x1800296c2  test    r15, r15
0x1800296c5  jnz     short loc_1800296D1
0x1800296c7  mov     ebx, 80041008h
0x1800296cc  jmp     loc_18002987E
0x1800296d1  mov     rcx, [rdi+88h]; this
0x1800296d8  mov     ebx, 80041001h
0x1800296dd  test    rcx, rcx
0x1800296e0  jz      loc_18002987E
0x1800296e6  call    ?GetProxy@CSWbemSecurity@@QEAAPEAUIUnknown@@XZ; CSWbemSecurity::GetProxy(void)
0x1800296eb  mov     rsi, rax
0x1800296ee  test    rax, rax
0x1800296f1  jz      loc_18002987E
0x1800296f7  mov     r9, [rsp+0A8h+arg_68]; struct IDispatch *
0x1800296ff  lea     rcx, [rsp+0A8h+var_58]; struct CWbemObjectSink **
0x180029704  mov     [rsp+0A8h+var_80], 0; unsigned __int16 *
0x18002970d  mov     r8, rbp; struct IDispatch *
0x180029710  mov     rdx, rdi; struct CSWbemServices *
0x180029713  mov     byte ptr [rsp+0A8h+var_88], 0; bool
0x180029718  mov     [rsp+0A8h+var_58], 0
0x180029721  call    ?CreateObjectSink@CWbemObjectSink@@SAPEAUIWbemObjectSink@@PEAPEAV1@PEAVCSWbemServices@@PEAUIDispatch@@2_NPEAG@Z; CWbemObjectSink::CreateObjectSink(CWbemObjectSink * *,CSWbemServices *,IDispatch *,IDispatch *,bool,ushort *)
0x180029726  mov     rbp, rax
0x180029729  test    rax, rax
0x18002972c  jz      loc_180029866
0x180029732  mov     rdx, [rdi+90h]; struct IServiceProvider *
0x180029739  mov     rcx, [rsp+0A8h+arg_60]; struct IDispatch *
0x180029741  call    ?GetIWbemContext@CSWbemNamedValueSet@@SAPEAUIWbemContext@@PEAUIDispatch@@PEAUIServiceProvider@@@Z; CSWbemNamedValueSet::GetIWbemContext(IDispatch *,IServiceProvider *)
0x180029746  lea     rcx, aWql; "WQL"
0x18002974d  mov     r14, rax
0x180029750  call    cs:__imp_SysAllocString
0x180029756  mov     r9, [rsp+0A8h+arg_28]; unsigned __int16 *
0x18002975e  mov     rdx, r13; unsigned __int16 *
0x180029761  mov     r8, [rsp+0A8h+arg_20]; unsigned __int16 *
0x180029769  mov     r12, rax
0x18002976c  mov     rax, [rsp+0A8h+arg_50]
0x180029774  mov     rcx, r15; unsigned __int16 *
0x180029777  mov     [rsp+0A8h+var_68], rax; unsigned __int16 *
0x18002977c  mov     rax, [rsp+0A8h+arg_48]
0x180029784  mov     [rsp+0A8h+var_70], rax; unsigned __int16 *
0x180029789  movzx   eax, [rsp+0A8h+arg_40]
0x180029791  mov     [rsp+0A8h+var_78], ax; __int16
0x180029796  movzx   eax, [rsp+0A8h+arg_38]
0x18002979e  mov     word ptr [rsp+0A8h+var_80], ax; __int16
0x1800297a3  mov     rax, [rsp+0A8h+arg_30]
0x1800297ab  mov     [rsp+0A8h+var_88], rax; unsigned __int16 *
0x1800297b0  call    ?FormatAssociatorsQuery@@YAPEAGPEAG0000FF00@Z; FormatAssociatorsQuery(ushort *,ushort *,ushort *,ushort *,ushort *,short,short,ushort *,ushort *)
0x1800297b5  mov     rcx, [rdi+88h]; this
0x1800297bc  lea     r8, [rsp+0A8h+var_50]; void **
0x1800297c1  xor     r13d, r13d
0x1800297c4  lea     rdx, [rsp+0A8h+arg_10]; bool *
0x1800297cc  mov     [rsp+0A8h+arg_10], r13b
0x1800297d4  mov     r15, rax
0x1800297d7  mov     [rsp+0A8h+var_50], r13
0x1800297dc  call    ?SetSecurity@CSWbemSecurity@@QEAAHAEA_NAEAPEAX@Z; CSWbemSecurity::SetSecurity(bool &,void * &)
0x1800297e1  test    eax, eax
0x1800297e3  jz      short loc_180029816
0x1800297e5  mov     rax, [rsi]
0x1800297e8  mov     r8, r15
0x1800297eb  mov     r9d, [rsp+0A8h+arg_58]
0x1800297f3  mov     rdx, r12
0x1800297f6  bts     r9d, 8
0x1800297fb  mov     [rsp+0A8h+var_80], rbp
0x180029800  mov     rcx, rsi
0x180029803  mov     [rsp+0A8h+var_88], r14
0x180029808  mov     rax, [rax+0A8h]
0x18002980f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029814  mov     ebx, eax
0x180029816  mov     rcx, [rsp+0A8h+var_58]; this
0x18002981b  mov     edx, ebx; int
0x18002981d  call    ?ReleaseTheStubIfNecessary@CWbemObjectSink@@QEAAXJ@Z; CWbemObjectSink::ReleaseTheStubIfNecessary(long)
0x180029822  cmp     [rsp+0A8h+arg_10], r13b
0x18002982a  jz      short loc_180029836
0x18002982c  mov     rdx, [rsp+0A8h+var_50]; void *
0x180029831  call    ?ResetSecurity@CSWbemSecurity@@QEAAXPEAX@Z; CSWbemSecurity::ResetSecurity(void *)
0x180029836  mov     rcx, rdi; this
0x180029839  call    ?SetWbemError@@YAXPEAVCSWbemServices@@@Z; SetWbemError(CSWbemServices *)
0x18002983e  mov     rcx, r15; bstrString
0x180029841  call    cs:__imp_SysFreeString
0x180029847  mov     rcx, r12; bstrString
0x18002984a  call    cs:__imp_SysFreeString
0x180029850  test    r14, r14
0x180029853  jz      short loc_18002986B
0x180029855  mov     rax, [r14]
0x180029858  mov     rcx, r14
0x18002985b  mov     rax, [rax+10h]
0x18002985f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029864  jmp     short loc_18002986B
0x180029866  mov     ebx, 80041008h
0x18002986b  mov     rax, [rsi]
0x18002986e  mov     rcx, rsi
0x180029871  mov     rax, [rax+10h]
0x180029875  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002987a  test    ebx, ebx
0x18002987c  jns     short loc_180029889
0x18002987e  lea     rcx, [rdi+38h]; this
0x180029882  mov     edx, ebx; int
0x180029884  call    ?RaiseException@CDispatchHelp@@QEAAXJ@Z; CDispatchHelp::RaiseException(long)
0x180029889  mov     eax, ebx
0x18002988b  add     rsp, 68h
0x18002988f  pop     r15
0x180029891  pop     r14
0x180029893  pop     r13
0x180029895  pop     r12
0x180029897  pop     rdi
0x180029898  pop     rsi
0x180029899  pop     rbp
0x18002989a  pop     rbx
0x18002989b  retn
```
