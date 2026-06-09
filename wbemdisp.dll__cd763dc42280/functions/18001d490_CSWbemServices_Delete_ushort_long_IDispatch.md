# CSWbemServices::Delete(ushort *,long,IDispatch *)

- ea: `0x18001d490`
- end: `0x18001d616`
- name: `?Delete@CSWbemServices@@UEAAJPEAGJPEAUIDispatch@@@Z`
- size: `390`
- prototype: `__int64 __fastcall(CSWbemServices *__hidden this, OLECHAR *psz, int, struct IDispatch *)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

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
- `0x18001d490`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001d4d0`
- `OLEAUT32!__imp_SysAllocString` at `0x18001d4d0`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d4ee`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d4ee`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CSWbemServices::Delete(CSWbemServices *this, OLECHAR *psz, unsigned int a3, struct IDispatch *a4)
{
  int v8; // edi
  OLECHAR *v9; // rbx
  struct IWbemServices *IWbemServices; // rax
  __int64 *v11; // rbx
  struct IWbemContext *IWbemContext; // r14
  CSWbemSecurity *v13; // rcx
  bool v14; // zf
  __int64 v15; // rax
  int v16; // eax
  __int64 *v18; // [rsp+30h] [rbp-30h] BYREF
  void *v19; // [rsp+38h] [rbp-28h] BYREF
  BSTR v20[3]; // [rsp+40h] [rbp-20h] BYREF
  int v21; // [rsp+5Ch] [rbp-4h]
  OLECHAR *v22; // [rsp+90h] [rbp+30h] BYREF

  v8 = -2147217407;
  ResetLastErrors();
  if ( !*((_QWORD *)this + 17) )
    goto LABEL_17;
  v9 = SysAllocString(psz);
  v22 = v9;
  CWbemPathCracker::CWbemPathCracker((CWbemPathCracker *)v20, (const struct ATL::CComBSTR *)&v22);
  SysFreeString(v9);
  if ( v21 && CWbemPathCracker::IsClassOrInstance((CWbemPathCracker *)v20) )
  {
    v18 = 0;
    IWbemServices = CSWbemServices::GetIWbemServices(this);
    ATL::CComPtr<IWbemServices>::Attach(&v18, IWbemServices);
    v11 = v18;
    if ( v18 )
    {
      IWbemContext = CSWbemNamedValueSet::GetIWbemContext(a4, *((struct IServiceProvider **)this + 18));
      LOBYTE(v22) = 0;
      v19 = 0;
      if ( (unsigned int)CSWbemSecurity::SetSecurity(*((CSWbemSecurity **)this + 17), (bool *)&v22, &v19) )
      {
        v14 = !CWbemPathCracker::IsInstance((CWbemPathCracker *)v20);
        v15 = *v11;
        if ( v14 )
          v16 = (*(__int64 (__fastcall **)(__int64 *, OLECHAR *, _QWORD, struct IWbemContext *, _QWORD))(v15 + 80))(
                  v11,
                  psz,
                  a3,
                  IWbemContext,
                  0);
        else
          v16 = (*(__int64 (__fastcall **)(__int64 *, OLECHAR *, _QWORD, struct IWbemContext *, _QWORD))(v15 + 128))(
                  v11,
                  psz,
                  a3,
                  IWbemContext,
                  0);
        v8 = v16;
      }
      if ( (_BYTE)v22 )
        CSWbemSecurity::ResetSecurity(v13, v19);
      SetWbemError((const OLECHAR **)this);
      if ( IWbemContext )
        ((void (__fastcall *)(struct IWbemContext *))IWbemContext->lpVtbl->Release)(IWbemContext);
    }
    ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>((__int64 *)&v18);
  }
  else
  {
    v8 = -2147217400;
  }
  CWbemPathCracker::~CWbemPathCracker(v20);
  if ( v8 < 0 )
LABEL_17:
    CDispatchHelp::RaiseException((CSWbemServices *)((char *)this + 56), v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001d490  mov     [rsp-28h+arg_8], rbx
0x18001d495  mov     [rsp-28h+arg_10], rsi
0x18001d49a  push    rbp
0x18001d49b  push    rdi
0x18001d49c  push    r12
0x18001d49e  push    r14
0x18001d4a0  push    r15
0x18001d4a2  mov     rbp, rsp
0x18001d4a5  sub     rsp, 60h
0x18001d4a9  mov     r14, r9
0x18001d4ac  mov     r12d, r8d
0x18001d4af  mov     r15, rdx
0x18001d4b2  mov     rsi, rcx
0x18001d4b5  mov     edi, 80041001h
0x18001d4ba  call    ?ResetLastErrors@@YAXXZ; ResetLastErrors(void)
0x18001d4bf  cmp     qword ptr [rsi+88h], 0
0x18001d4c7  jz      loc_18001D5F0
0x18001d4cd  mov     rcx, r15; psz
0x18001d4d0  call    cs:__imp_SysAllocString
0x18001d4d6  mov     rbx, rax
0x18001d4d9  mov     [rbp+arg_0], rax
0x18001d4dd  lea     rdx, [rbp+arg_0]; struct ATL::CComBSTR *
0x18001d4e1  lea     rcx, [rbp+var_20]; this
0x18001d4e5  call    ??0CWbemPathCracker@@QEAA@AEBVCComBSTR@ATL@@@Z; CWbemPathCracker::CWbemPathCracker(ATL::CComBSTR const &)
0x18001d4ea  nop
0x18001d4eb  mov     rcx, rbx; bstrString
0x18001d4ee  call    cs:__imp_SysFreeString
0x18001d4f4  cmp     [rbp+var_4], 0
0x18001d4f8  jz      loc_18001D5DE
0x18001d4fe  lea     rcx, [rbp+var_20]; this
0x18001d502  call    ?IsClassOrInstance@CWbemPathCracker@@QEAA_NXZ; CWbemPathCracker::IsClassOrInstance(void)
0x18001d507  test    al, al
0x18001d509  jz      loc_18001D5DE
0x18001d50f  mov     [rbp+var_30], 0
0x18001d517  mov     rcx, rsi; this
0x18001d51a  call    ?GetIWbemServices@CSWbemServices@@QEAAPEAUIWbemServices@@XZ; CSWbemServices::GetIWbemServices(void)
0x18001d51f  mov     rdx, rax
0x18001d522  lea     rcx, [rbp+var_30]
0x18001d526  call    ?Attach@?$CComPtr@UIWbemServices@@@ATL@@QEAAXPEAUIWbemServices@@@Z; ATL::CComPtr<IWbemServices>::Attach(IWbemServices *)
0x18001d52b  mov     rbx, [rbp+var_30]
0x18001d52f  test    rbx, rbx
0x18001d532  jz      loc_18001D5D3
0x18001d538  mov     rdx, [rsi+90h]; struct IServiceProvider *
0x18001d53f  mov     rcx, r14; struct IDispatch *
0x18001d542  call    ?GetIWbemContext@CSWbemNamedValueSet@@SAPEAUIWbemContext@@PEAUIDispatch@@PEAUIServiceProvider@@@Z; CSWbemNamedValueSet::GetIWbemContext(IDispatch *,IServiceProvider *)
0x18001d547  mov     r14, rax
0x18001d54a  mov     byte ptr [rbp+arg_0], 0
0x18001d54e  mov     [rbp+var_28], 0
0x18001d556  lea     r8, [rbp+var_28]; void **
0x18001d55a  lea     rdx, [rbp+arg_0]; bool *
0x18001d55e  mov     rcx, [rsi+88h]; this
0x18001d565  call    ?SetSecurity@CSWbemSecurity@@QEAAHAEA_NAEAPEAX@Z; CSWbemSecurity::SetSecurity(bool &,void * &)
0x18001d56a  test    eax, eax
0x18001d56c  jz      short loc_18001D5A7
0x18001d56e  lea     rcx, [rbp+var_20]; this
0x18001d572  call    ?IsInstance@CWbemPathCracker@@QEAA_NXZ; CWbemPathCracker::IsInstance(void)
0x18001d577  mov     [rsp+60h+var_40], 0
0x18001d580  mov     r9, r14
0x18001d583  mov     r8d, r12d
0x18001d586  mov     rdx, r15
0x18001d589  mov     rcx, rbx
0x18001d58c  test    al, al
0x18001d58e  mov     rax, [rbx]
0x18001d591  jz      short loc_18001D59C
0x18001d593  mov     rax, [rax+80h]
0x18001d59a  jmp     short loc_18001D5A0
0x18001d59c  mov     rax, [rax+50h]
0x18001d5a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d5a5  mov     edi, eax
0x18001d5a7  cmp     byte ptr [rbp+arg_0], 0
0x18001d5ab  jz      short loc_18001D5B6
0x18001d5ad  mov     rdx, [rbp+var_28]; void *
0x18001d5b1  call    ?ResetSecurity@CSWbemSecurity@@QEAAXPEAX@Z; CSWbemSecurity::ResetSecurity(void *)
0x18001d5b6  mov     rcx, rsi; this
0x18001d5b9  call    ?SetWbemError@@YAXPEAVCSWbemServices@@@Z; SetWbemError(CSWbemServices *)
0x18001d5be  test    r14, r14
0x18001d5c1  jz      short loc_18001D5D3
0x18001d5c3  mov     rax, [r14]
0x18001d5c6  mov     rcx, r14
0x18001d5c9  mov     rax, [rax+10h]
0x18001d5cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d5d2  nop
0x18001d5d3  lea     rcx, [rbp+var_30]
0x18001d5d7  call    ??1?$CComQIPtr@UISWbemObject@@$1?_GUID_76a6415a_cb41_11d1_8b02_00600806d9b6@@3U__s_GUID@@B@ATL@@QEAA@XZ; ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(void)
0x18001d5dc  jmp     short loc_18001D5E3
0x18001d5de  mov     edi, 80041008h
0x18001d5e3  lea     rcx, [rbp+var_20]; this
0x18001d5e7  call    ??1CWbemPathCracker@@UEAA@XZ; CWbemPathCracker::~CWbemPathCracker(void)
0x18001d5ec  test    edi, edi
0x18001d5ee  jns     short loc_18001D5FB
0x18001d5f0  lea     rcx, [rsi+38h]; this
0x18001d5f4  mov     edx, edi; int
0x18001d5f6  call    ?RaiseException@CDispatchHelp@@QEAAXJ@Z; CDispatchHelp::RaiseException(long)
0x18001d5fb  mov     eax, edi
0x18001d5fd  lea     r11, [rsp+60h+var_s0]
0x18001d602  mov     rbx, [r11+38h]
0x18001d606  mov     rsi, [r11+40h]
0x18001d60a  mov     rsp, r11
0x18001d60d  pop     r15
0x18001d60f  pop     r14
0x18001d611  pop     r12
0x18001d613  pop     rdi
0x18001d614  pop     rbp
0x18001d615  retn
```
