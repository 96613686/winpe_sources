# CSWbemServices::DeleteAsync(IDispatch *,ushort *,long,IDispatch *,IDispatch *)

- ea: `0x1800298b0`
- end: `0x180029a66`
- name: `?DeleteAsync@CSWbemServices@@UEAAJPEAUIDispatch@@PEAGJ00@Z`
- size: `438`
- prototype: `__int64 __usercall@<rax>(CSWbemServices *__hidden this@<rcx>, struct IDispatch *@<rdx>, OLECHAR *psz@<r8>, int@<r9d>, struct IDispatch *, struct IDispatch *)`
- caller_count: `0`
- callee_count: `17`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000311c`
- `0x1800036e0`
- `0x1800050dc`
- `0x180006300`
- `0x1800077d0`
- `0x18000c0b0`
- `0x1800109cc`
- `0x180010a4c`
- `0x18001148c`
- `0x180014f20`
- `0x18001643c`
- `0x180018130`
- `0x1800184d4`
- `0x180028d54`
- `0x180029248`
- `0x1800298b0`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180029914`
- `OLEAUT32!__imp_SysAllocString` at `0x180029914`
- `OLEAUT32!__imp_SysFreeString` at `0x180029932`
- `OLEAUT32!__imp_SysFreeString` at `0x180029932`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CSWbemServices::DeleteAsync(
        CSWbemServices *this,
        struct IDispatch *a2,
        OLECHAR *psz,
        unsigned int a4,
        struct IDispatch *a5,
        struct IDispatch *a6)
{
  int v10; // esi
  struct IWbemServices *IWbemServices; // rax
  __int64 *v12; // rdi
  OLECHAR *v13; // rbx
  struct IWbemObjectSink *v14; // r15
  struct IWbemContext *IWbemContext; // rbx
  bool v16; // zf
  __int64 v17; // rax
  int v18; // eax
  CSWbemSecurity *v19; // rcx
  __int64 *v21; // [rsp+30h] [rbp-48h] BYREF
  CWbemObjectSink *v22; // [rsp+38h] [rbp-40h] BYREF
  void *v23; // [rsp+40h] [rbp-38h] BYREF
  BSTR v24[3]; // [rsp+48h] [rbp-30h] BYREF
  int v25; // [rsp+64h] [rbp-14h]
  OLECHAR *v26; // [rsp+C0h] [rbp+48h] BYREF

  v10 = -2147217407;
  ResetLastErrors();
  if ( !*((_QWORD *)this + 17) )
    goto LABEL_18;
  v21 = 0;
  IWbemServices = CSWbemServices::GetIWbemServices(this);
  ATL::CComPtr<IWbemServices>::Attach(&v21, IWbemServices);
  v12 = v21;
  if ( v21 )
  {
    v13 = SysAllocString(psz);
    v26 = v13;
    CWbemPathCracker::CWbemPathCracker((CWbemPathCracker *)v24, (const struct ATL::CComBSTR *)&v26);
    SysFreeString(v13);
    if ( v25
      && CWbemPathCracker::IsClassOrInstance((CWbemPathCracker *)v24)
      && (v22 = 0, (v14 = CWbemObjectSink::CreateObjectSink(&v22, this, a2, a6, 0, 0)) != 0) )
    {
      IWbemContext = CSWbemNamedValueSet::GetIWbemContext(a5, *((struct IServiceProvider **)this + 18));
      LOBYTE(v26) = 0;
      v23 = 0;
      if ( (unsigned int)CSWbemSecurity::SetSecurity(*((CSWbemSecurity **)this + 17), (bool *)&v26, &v23) )
      {
        v16 = !CWbemPathCracker::IsInstance((CWbemPathCracker *)v24);
        v17 = *v12;
        if ( v16 )
          v18 = (*(__int64 (__fastcall **)(__int64 *, OLECHAR *, _QWORD, struct IWbemContext *, struct IWbemObjectSink *))(v17 + 88))(
                  v12,
                  psz,
                  a4,
                  IWbemContext,
                  v14);
        else
          v18 = (*(__int64 (__fastcall **)(__int64 *, OLECHAR *, _QWORD, struct IWbemContext *, struct IWbemObjectSink *))(v17 + 136))(
                  v12,
                  psz,
                  a4,
                  IWbemContext,
                  v14);
        v10 = v18;
      }
      CWbemObjectSink::ReleaseTheStubIfNecessary(v22, v10);
      if ( (_BYTE)v26 )
        CSWbemSecurity::ResetSecurity(v19, v23);
      SetWbemError((const OLECHAR **)this);
      if ( IWbemContext )
        ((void (__fastcall *)(struct IWbemContext *))IWbemContext->lpVtbl->Release)(IWbemContext);
    }
    else
    {
      v10 = -2147217400;
    }
    CWbemPathCracker::~CWbemPathCracker(v24);
  }
  ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>((__int64 *)&v21);
  if ( v10 < 0 )
LABEL_18:
    CDispatchHelp::RaiseException((CSWbemServices *)((char *)this + 56), v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800298b0  push    rbp
0x1800298b2  push    rbx
0x1800298b3  push    rsi
0x1800298b4  push    rdi
0x1800298b5  push    r12
0x1800298b7  push    r13
0x1800298b9  push    r14
0x1800298bb  push    r15
0x1800298bd  mov     rbp, rsp
0x1800298c0  sub     rsp, 78h
0x1800298c4  mov     r13d, r9d
0x1800298c7  mov     r12, r8
0x1800298ca  mov     r15, rdx
0x1800298cd  mov     r14, rcx
0x1800298d0  mov     esi, 80041001h
0x1800298d5  call    ?ResetLastErrors@@YAXXZ; ResetLastErrors(void)
0x1800298da  cmp     qword ptr [r14+88h], 0
0x1800298e2  jz      loc_180029A48
0x1800298e8  mov     [rbp+var_48], 0
0x1800298f0  mov     rcx, r14; this
0x1800298f3  call    ?GetIWbemServices@CSWbemServices@@QEAAPEAUIWbemServices@@XZ; CSWbemServices::GetIWbemServices(void)
0x1800298f8  mov     rdx, rax
0x1800298fb  lea     rcx, [rbp+var_48]
0x1800298ff  call    ?Attach@?$CComPtr@UIWbemServices@@@ATL@@QEAAXPEAUIWbemServices@@@Z; ATL::CComPtr<IWbemServices>::Attach(IWbemServices *)
0x180029904  mov     rdi, [rbp+var_48]
0x180029908  test    rdi, rdi
0x18002990b  jz      loc_180029A3B
0x180029911  mov     rcx, r12; psz
0x180029914  call    cs:__imp_SysAllocString
0x18002991a  mov     rbx, rax
0x18002991d  mov     [rbp+arg_0], rax
0x180029921  lea     rdx, [rbp+arg_0]; struct ATL::CComBSTR *
0x180029925  lea     rcx, [rbp+var_30]; this
0x180029929  call    ??0CWbemPathCracker@@QEAA@AEBVCComBSTR@ATL@@@Z; CWbemPathCracker::CWbemPathCracker(ATL::CComBSTR const &)
0x18002992e  nop
0x18002992f  mov     rcx, rbx; bstrString
0x180029932  call    cs:__imp_SysFreeString
0x180029938  cmp     [rbp+var_14], 0
0x18002993c  jz      loc_180029A2C
0x180029942  lea     rcx, [rbp+var_30]; this
0x180029946  call    ?IsClassOrInstance@CWbemPathCracker@@QEAA_NXZ; CWbemPathCracker::IsClassOrInstance(void)
0x18002994b  test    al, al
0x18002994d  jz      loc_180029A2C
0x180029953  mov     [rbp+var_40], 0
0x18002995b  mov     [rsp+78h+var_50], 0; unsigned __int16 *
0x180029964  mov     [rsp+78h+var_58], 0; bool
0x180029969  mov     r9, [rbp+arg_28]; struct IDispatch *
0x18002996d  mov     r8, r15; struct IDispatch *
0x180029970  mov     rdx, r14; struct CSWbemServices *
0x180029973  lea     rcx, [rbp+var_40]; struct CWbemObjectSink **
0x180029977  call    ?CreateObjectSink@CWbemObjectSink@@SAPEAUIWbemObjectSink@@PEAPEAV1@PEAVCSWbemServices@@PEAUIDispatch@@2_NPEAG@Z; CWbemObjectSink::CreateObjectSink(CWbemObjectSink * *,CSWbemServices *,IDispatch *,IDispatch *,bool,ushort *)
0x18002997c  mov     r15, rax
0x18002997f  test    rax, rax
0x180029982  jz      loc_180029A2C
0x180029988  mov     rdx, [r14+90h]; struct IServiceProvider *
0x18002998f  mov     rcx, [rbp+arg_20]; struct IDispatch *
0x180029993  call    ?GetIWbemContext@CSWbemNamedValueSet@@SAPEAUIWbemContext@@PEAUIDispatch@@PEAUIServiceProvider@@@Z; CSWbemNamedValueSet::GetIWbemContext(IDispatch *,IServiceProvider *)
0x180029998  mov     rbx, rax
0x18002999b  mov     byte ptr [rbp+arg_0], 0
0x18002999f  mov     [rbp+var_38], 0
0x1800299a7  lea     r8, [rbp+var_38]; void **
0x1800299ab  lea     rdx, [rbp+arg_0]; bool *
0x1800299af  mov     rcx, [r14+88h]; this
0x1800299b6  call    ?SetSecurity@CSWbemSecurity@@QEAAHAEA_NAEAPEAX@Z; CSWbemSecurity::SetSecurity(bool &,void * &)
0x1800299bb  test    eax, eax
0x1800299bd  jz      short loc_1800299F4
0x1800299bf  lea     rcx, [rbp+var_30]; this
0x1800299c3  call    ?IsInstance@CWbemPathCracker@@QEAA_NXZ; CWbemPathCracker::IsInstance(void)
0x1800299c8  mov     qword ptr [rsp+78h+var_58], r15
0x1800299cd  mov     r9, rbx
0x1800299d0  mov     r8d, r13d
0x1800299d3  mov     rdx, r12
0x1800299d6  mov     rcx, rdi
0x1800299d9  test    al, al
0x1800299db  mov     rax, [rdi]
0x1800299de  jz      short loc_1800299E9
0x1800299e0  mov     rax, [rax+88h]
0x1800299e7  jmp     short loc_1800299ED
0x1800299e9  mov     rax, [rax+58h]
0x1800299ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800299f2  mov     esi, eax
0x1800299f4  mov     edx, esi; int
0x1800299f6  mov     rcx, [rbp+var_40]; this
0x1800299fa  call    ?ReleaseTheStubIfNecessary@CWbemObjectSink@@QEAAXJ@Z; CWbemObjectSink::ReleaseTheStubIfNecessary(long)
0x1800299ff  cmp     byte ptr [rbp+arg_0], 0
0x180029a03  jz      short loc_180029A0E
0x180029a05  mov     rdx, [rbp+var_38]; void *
0x180029a09  call    ?ResetSecurity@CSWbemSecurity@@QEAAXPEAX@Z; CSWbemSecurity::ResetSecurity(void *)
0x180029a0e  mov     rcx, r14; this
0x180029a11  call    ?SetWbemError@@YAXPEAVCSWbemServices@@@Z; SetWbemError(CSWbemServices *)
0x180029a16  test    rbx, rbx
0x180029a19  jz      short loc_180029A31
0x180029a1b  mov     rax, [rbx]
0x180029a1e  mov     rcx, rbx
0x180029a21  mov     rax, [rax+10h]
0x180029a25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029a2a  jmp     short loc_180029A31
0x180029a2c  mov     esi, 80041008h
0x180029a31  lea     rcx, [rbp+var_30]; this
0x180029a35  call    ??1CWbemPathCracker@@UEAA@XZ; CWbemPathCracker::~CWbemPathCracker(void)
0x180029a3a  nop
0x180029a3b  lea     rcx, [rbp+var_48]
0x180029a3f  call    ??1?$CComQIPtr@UISWbemObject@@$1?_GUID_76a6415a_cb41_11d1_8b02_00600806d9b6@@3U__s_GUID@@B@ATL@@QEAA@XZ; ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(void)
0x180029a44  test    esi, esi
0x180029a46  jns     short loc_180029A53
0x180029a48  lea     rcx, [r14+38h]; this
0x180029a4c  mov     edx, esi; int
0x180029a4e  call    ?RaiseException@CDispatchHelp@@QEAAXJ@Z; CDispatchHelp::RaiseException(long)
0x180029a53  mov     eax, esi
0x180029a55  add     rsp, 78h
0x180029a59  pop     r15
0x180029a5b  pop     r14
0x180029a5d  pop     r13
0x180029a5f  pop     r12
0x180029a61  pop     rdi
0x180029a62  pop     rsi
0x180029a63  pop     rbx
0x180029a64  pop     rbp
0x180029a65  retn
```
