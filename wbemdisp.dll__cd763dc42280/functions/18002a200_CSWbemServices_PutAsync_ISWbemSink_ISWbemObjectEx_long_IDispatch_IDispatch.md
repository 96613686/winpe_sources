# CSWbemServices::PutAsync(ISWbemSink *,ISWbemObjectEx *,long,IDispatch *,IDispatch *)

- ea: `0x18002a200`
- end: `0x18002a4d0`
- name: `?PutAsync@CSWbemServices@@UEAAJPEAUISWbemSink@@PEAUISWbemObjectEx@@JPEAUIDispatch@@2@Z`
- size: `720`
- prototype: `__int64 __usercall@<rax>(CSWbemServices *__hidden this@<rcx>, struct ISWbemSink *@<rdx>, struct ISWbemObjectEx *@<r8>, int@<r9d>, struct IDispatch *, struct IDispatch *)`
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
- `0x180028d54`
- `0x180029248`
- `0x18002a200`
- `0x18002b4a0`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18002a27e`
- `OLEAUT32!__imp_VariantInit` at `0x18002a2e9`
- `OLEAUT32!__imp_VariantInit` at `0x18002a27e`
- `OLEAUT32!__imp_VariantInit` at `0x18002a2e9`
- `OLEAUT32!__imp_VariantClear` at `0x18002a3c7`
- `OLEAUT32!__imp_VariantClear` at `0x18002a48f`
- `OLEAUT32!__imp_VariantClear` at `0x18002a3c7`
- `OLEAUT32!__imp_VariantClear` at `0x18002a48f`

## pseudocode

```c
__int64 __fastcall CSWbemServices::PutAsync(
        CSWbemServices *this,
        struct IDispatch *a2,
        struct IDispatch *a3,
        unsigned int a4,
        struct IDispatch *a5,
        struct IDispatch *a6)
{
  int v10; // ebx
  CSWbemSecurity *v11; // rcx
  struct IUnknown *Proxy; // r14
  struct IWbemClassObject *IWbemClassObject; // rsi
  struct IWbemContext *IWbemContext; // r15
  struct IWbemObjectSink *v15; // r12
  CSWbemSecurity *v16; // rcx
  CSWbemSecurity *v17; // rcx
  struct IWbemObjectSink *v18; // r12
  CSWbemSecurity *v19; // rcx
  CSWbemSecurity *v20; // rcx
  CWbemObjectSink *v22; // [rsp+40h] [rbp-39h] BYREF
  CWbemObjectSink *v23; // [rsp+48h] [rbp-31h] BYREF
  VARIANTARG v24; // [rsp+50h] [rbp-29h] BYREF
  VARIANTARG pvarg; // [rsp+68h] [rbp-11h] BYREF
  bool v26; // [rsp+D0h] [rbp+57h] BYREF

  v10 = -2147217407;
  ResetLastErrors();
  v11 = (CSWbemSecurity *)*((_QWORD *)this + 17);
  if ( !v11 )
    goto LABEL_25;
  Proxy = CSWbemSecurity::GetProxy(v11);
  if ( !Proxy )
    goto LABEL_25;
  if ( a2 )
  {
    IWbemClassObject = CSWbemObject::GetIWbemClassObject(a3);
    if ( IWbemClassObject )
    {
      memset(&pvarg, 0, sizeof(pvarg));
      VariantInit(&pvarg);
      if ( !((unsigned int (__fastcall *)(struct IWbemClassObject *, const OLECHAR *, _QWORD, VARIANTARG *, _QWORD, _QWORD))IWbemClassObject->lpVtbl->Get)(
              IWbemClassObject,
              L"__GENUS",
              0,
              &pvarg,
              0,
              0) )
      {
        IWbemContext = CSWbemNamedValueSet::GetIWbemContext(a5, *((struct IServiceProvider **)this + 18));
        if ( pvarg.lVal == 1 )
        {
          memset(&v24, 0, sizeof(v24));
          VariantInit(&v24);
          if ( !((unsigned int (__fastcall *)(struct IWbemClassObject *, const OLECHAR *, _QWORD, VARIANTARG *, _QWORD, _QWORD))IWbemClassObject->lpVtbl->Get)(
                  IWbemClassObject,
                  L"__CLASS",
                  0,
                  &v24,
                  0,
                  0)
            && v24.vt == 8 )
          {
            v22 = 0;
            v15 = CWbemObjectSink::CreateObjectSink(&v22, this, a2, a6, 1, v24.bstrVal);
            if ( v15 )
            {
              v16 = (CSWbemSecurity *)*((_QWORD *)this + 17);
              v26 = 0;
              v23 = 0;
              if ( (unsigned int)CSWbemSecurity::SetSecurity(v16, &v26, (void **)&v23) )
                v10 = ((__int64 (__fastcall *)(struct IUnknown *, struct IWbemClassObject *, _QWORD, struct IWbemContext *, struct IWbemObjectSink *))Proxy->lpVtbl[3].QueryInterface)(
                        Proxy,
                        IWbemClassObject,
                        a4,
                        IWbemContext,
                        v15);
              CWbemObjectSink::ReleaseTheStubIfNecessary(v22, v10);
              if ( v26 )
                CSWbemSecurity::ResetSecurity(v17, v23);
            }
          }
          VariantClear(&v24);
        }
        else
        {
          v23 = 0;
          v18 = CWbemObjectSink::CreateObjectSink(&v23, this, a2, a6, 1, 0);
          if ( v18 )
          {
            v19 = (CSWbemSecurity *)*((_QWORD *)this + 17);
            v26 = 0;
            v22 = 0;
            if ( (unsigned int)CSWbemSecurity::SetSecurity(v19, &v26, (void **)&v22) )
              v10 = ((__int64 (__fastcall *)(struct IUnknown *, struct IWbemClassObject *, _QWORD, struct IWbemContext *, struct IWbemObjectSink *))Proxy->lpVtbl[5].QueryInterface)(
                      Proxy,
                      IWbemClassObject,
                      a4,
                      IWbemContext,
                      v18);
            CWbemObjectSink::ReleaseTheStubIfNecessary(v23, v10);
            if ( v26 )
              CSWbemSecurity::ResetSecurity(v20, v22);
          }
        }
        SetWbemError((const OLECHAR **)this);
        if ( IWbemContext )
          ((void (__fastcall *)(struct IWbemContext *))IWbemContext->lpVtbl->Release)(IWbemContext);
      }
      ((void (__fastcall *)(struct IWbemClassObject *))IWbemClassObject->lpVtbl->Release)(IWbemClassObject);
      VariantClear(&pvarg);
    }
  }
  else
  {
    v10 = -2147217400;
  }
  ((void (__fastcall *)(struct IUnknown *))Proxy->lpVtbl->Release)(Proxy);
  if ( v10 < 0 )
LABEL_25:
    CDispatchHelp::RaiseException((CSWbemServices *)((char *)this + 56), v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18002a200  push    rbp
0x18002a202  push    rbx
0x18002a203  push    rsi
0x18002a204  push    rdi
0x18002a205  push    r12
0x18002a207  push    r13
0x18002a209  push    r14
0x18002a20b  push    r15
0x18002a20d  lea     rbp, [rsp-0Fh]
0x18002a212  sub     rsp, 88h
0x18002a219  mov     r13d, r9d
0x18002a21c  mov     rsi, r8
0x18002a21f  mov     r12, rdx
0x18002a222  mov     rdi, rcx
0x18002a225  mov     ebx, 80041001h
0x18002a22a  call    ?ResetLastErrors@@YAXXZ; ResetLastErrors(void)
0x18002a22f  mov     rcx, [rdi+88h]; this
0x18002a236  test    rcx, rcx
0x18002a239  jz      loc_18002A4AF
0x18002a23f  call    ?GetProxy@CSWbemSecurity@@QEAAPEAUIUnknown@@XZ; CSWbemSecurity::GetProxy(void)
0x18002a244  mov     r14, rax
0x18002a247  test    rax, rax
0x18002a24a  jz      loc_18002A4AF
0x18002a250  test    r12, r12
0x18002a253  jz      loc_18002A497
0x18002a259  mov     rcx, rsi; struct IDispatch *
0x18002a25c  call    ?GetIWbemClassObject@CSWbemObject@@SAPEAUIWbemClassObject@@PEAUIDispatch@@@Z; CSWbemObject::GetIWbemClassObject(IDispatch *)
0x18002a261  mov     rsi, rax
0x18002a264  test    rax, rax
0x18002a267  jz      loc_18002A49C
0x18002a26d  xorps   xmm0, xmm0
0x18002a270  lea     rcx, [rbp+47h+pvarg]; pvarg
0x18002a274  xor     eax, eax
0x18002a276  movups  xmmword ptr [rbp+47h+pvarg], xmm0
0x18002a27a  mov     qword ptr [rbp+47h+pvarg+10h], rax
0x18002a27e  call    cs:__imp_VariantInit
0x18002a284  mov     rax, [rsi]
0x18002a287  lea     r9, [rbp+47h+pvarg]
0x18002a28b  mov     [rsp+0C0h+var_98], 0
0x18002a294  lea     rdx, aGenus; "__GENUS"
0x18002a29b  xor     r8d, r8d
0x18002a29e  mov     qword ptr [rsp+0C0h+var_A0], 0
0x18002a2a7  mov     rcx, rsi
0x18002a2aa  mov     rax, [rax+20h]
0x18002a2ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a2b3  test    eax, eax
0x18002a2b5  jnz     loc_18002A47C
0x18002a2bb  mov     rdx, [rdi+90h]; struct IServiceProvider *
0x18002a2c2  mov     rcx, [rbp+47h+arg_20]; struct IDispatch *
0x18002a2c6  call    ?GetIWbemContext@CSWbemNamedValueSet@@SAPEAUIWbemContext@@PEAUIDispatch@@PEAUIServiceProvider@@@Z; CSWbemNamedValueSet::GetIWbemContext(IDispatch *,IServiceProvider *)
0x18002a2cb  cmp     dword ptr [rbp+47h+pvarg+8], 1
0x18002a2cf  mov     r15, rax
0x18002a2d2  jnz     loc_18002A3D2
0x18002a2d8  xorps   xmm0, xmm0
0x18002a2db  lea     rcx, [rbp+47h+var_70]; pvarg
0x18002a2df  xor     eax, eax
0x18002a2e1  movups  xmmword ptr [rbp+47h+var_70], xmm0
0x18002a2e5  mov     qword ptr [rbp+47h+var_70+10h], rax
0x18002a2e9  call    cs:__imp_VariantInit
0x18002a2ef  mov     rax, [rsi]
0x18002a2f2  lea     r9, [rbp+47h+var_70]
0x18002a2f6  mov     [rsp+0C0h+var_98], 0
0x18002a2ff  lea     rdx, aClass; "__CLASS"
0x18002a306  xor     r8d, r8d
0x18002a309  mov     qword ptr [rsp+0C0h+var_A0], 0
0x18002a312  mov     rcx, rsi
0x18002a315  mov     rax, [rax+20h]
0x18002a319  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a31e  test    eax, eax
0x18002a320  jnz     loc_18002A3C3
0x18002a326  mov     eax, 8
0x18002a32b  cmp     ax, word ptr [rbp+47h+var_70]
0x18002a32f  jnz     loc_18002A3C3
0x18002a335  mov     rax, qword ptr [rbp+47h+var_70+8]
0x18002a339  lea     rcx, [rbp+47h+var_80]; struct CWbemObjectSink **
0x18002a33d  mov     r9, [rbp+47h+arg_28]; struct IDispatch *
0x18002a341  mov     r8, r12; struct IDispatch *
0x18002a344  mov     [rsp+0C0h+var_98], rax; unsigned __int16 *
0x18002a349  mov     rdx, rdi; struct CSWbemServices *
0x18002a34c  mov     [rsp+0C0h+var_A0], 1; bool
0x18002a351  mov     [rbp+47h+var_80], 0
0x18002a359  call    ?CreateObjectSink@CWbemObjectSink@@SAPEAUIWbemObjectSink@@PEAPEAV1@PEAVCSWbemServices@@PEAUIDispatch@@2_NPEAG@Z; CWbemObjectSink::CreateObjectSink(CWbemObjectSink * *,CSWbemServices *,IDispatch *,IDispatch *,bool,ushort *)
0x18002a35e  mov     r12, rax
0x18002a361  test    rax, rax
0x18002a364  jz      short loc_18002A3C3
0x18002a366  mov     rcx, [rdi+88h]; this
0x18002a36d  lea     r8, [rbp+47h+var_78]; void **
0x18002a371  lea     rdx, [rbp+47h+arg_0]; bool *
0x18002a375  mov     [rbp+47h+arg_0], 0
0x18002a379  mov     [rbp+47h+var_78], 0
0x18002a381  call    ?SetSecurity@CSWbemSecurity@@QEAAHAEA_NAEAPEAX@Z; CSWbemSecurity::SetSecurity(bool &,void * &)
0x18002a386  test    eax, eax
0x18002a388  jz      short loc_18002A3A9
0x18002a38a  mov     rax, [r14]
0x18002a38d  mov     r9, r15
0x18002a390  mov     r8d, r13d
0x18002a393  mov     qword ptr [rsp+0C0h+var_A0], r12
0x18002a398  mov     rdx, rsi
0x18002a39b  mov     rcx, r14
0x18002a39e  mov     rax, [rax+48h]
0x18002a3a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a3a7  mov     ebx, eax
0x18002a3a9  mov     rcx, [rbp+47h+var_80]; this
0x18002a3ad  mov     edx, ebx; int
0x18002a3af  call    ?ReleaseTheStubIfNecessary@CWbemObjectSink@@QEAAXJ@Z; CWbemObjectSink::ReleaseTheStubIfNecessary(long)
0x18002a3b4  cmp     [rbp+47h+arg_0], 0
0x18002a3b8  jz      short loc_18002A3C3
0x18002a3ba  mov     rdx, [rbp+47h+var_78]; void *
0x18002a3be  call    ?ResetSecurity@CSWbemSecurity@@QEAAXPEAX@Z; CSWbemSecurity::ResetSecurity(void *)
0x18002a3c3  lea     rcx, [rbp+47h+var_70]; pvarg
0x18002a3c7  call    cs:__imp_VariantClear
0x18002a3cd  jmp     loc_18002A460
0x18002a3d2  mov     r9, [rbp+47h+arg_28]; struct IDispatch *
0x18002a3d6  lea     rcx, [rbp+47h+var_78]; struct CWbemObjectSink **
0x18002a3da  mov     [rsp+0C0h+var_98], 0; unsigned __int16 *
0x18002a3e3  mov     r8, r12; struct IDispatch *
0x18002a3e6  mov     rdx, rdi; struct CSWbemServices *
0x18002a3e9  mov     [rsp+0C0h+var_A0], 1; bool
0x18002a3ee  mov     [rbp+47h+var_78], 0
0x18002a3f6  call    ?CreateObjectSink@CWbemObjectSink@@SAPEAUIWbemObjectSink@@PEAPEAV1@PEAVCSWbemServices@@PEAUIDispatch@@2_NPEAG@Z; CWbemObjectSink::CreateObjectSink(CWbemObjectSink * *,CSWbemServices *,IDispatch *,IDispatch *,bool,ushort *)
0x18002a3fb  mov     r12, rax
0x18002a3fe  test    rax, rax
0x18002a401  jz      short loc_18002A460
0x18002a403  mov     rcx, [rdi+88h]; this
0x18002a40a  lea     r8, [rbp+47h+var_80]; void **
0x18002a40e  lea     rdx, [rbp+47h+arg_0]; bool *
0x18002a412  mov     [rbp+47h+arg_0], 0
0x18002a416  mov     [rbp+47h+var_80], 0
0x18002a41e  call    ?SetSecurity@CSWbemSecurity@@QEAAHAEA_NAEAPEAX@Z; CSWbemSecurity::SetSecurity(bool &,void * &)
0x18002a423  test    eax, eax
0x18002a425  jz      short loc_18002A446
0x18002a427  mov     rcx, [r14]
0x18002a42a  mov     r9, r15
0x18002a42d  mov     r8d, r13d
0x18002a430  mov     qword ptr [rsp+0C0h+var_A0], r12
0x18002a435  mov     rdx, rsi
0x18002a438  mov     rax, [rcx+78h]
0x18002a43c  mov     rcx, r14
0x18002a43f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a444  mov     ebx, eax
0x18002a446  mov     rcx, [rbp+47h+var_78]; this
0x18002a44a  mov     edx, ebx; int
0x18002a44c  call    ?ReleaseTheStubIfNecessary@CWbemObjectSink@@QEAAXJ@Z; CWbemObjectSink::ReleaseTheStubIfNecessary(long)
0x18002a451  cmp     [rbp+47h+arg_0], 0
0x18002a455  jz      short loc_18002A460
0x18002a457  mov     rdx, [rbp+47h+var_80]; void *
0x18002a45b  call    ?ResetSecurity@CSWbemSecurity@@QEAAXPEAX@Z; CSWbemSecurity::ResetSecurity(void *)
0x18002a460  mov     rcx, rdi; this
0x18002a463  call    ?SetWbemError@@YAXPEAVCSWbemServices@@@Z; SetWbemError(CSWbemServices *)
0x18002a468  test    r15, r15
0x18002a46b  jz      short loc_18002A47C
0x18002a46d  mov     rax, [r15]
0x18002a470  mov     rcx, r15
0x18002a473  mov     rax, [rax+10h]
0x18002a477  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a47c  mov     rax, [rsi]
0x18002a47f  mov     rcx, rsi
0x18002a482  mov     rax, [rax+10h]
0x18002a486  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a48b  lea     rcx, [rbp+47h+pvarg]; pvarg
0x18002a48f  call    cs:__imp_VariantClear
0x18002a495  jmp     short loc_18002A49C
0x18002a497  mov     ebx, 80041008h
0x18002a49c  mov     rax, [r14]
0x18002a49f  mov     rcx, r14
0x18002a4a2  mov     rax, [rax+10h]
0x18002a4a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a4ab  test    ebx, ebx
0x18002a4ad  jns     short loc_18002A4BA
0x18002a4af  lea     rcx, [rdi+38h]; this
0x18002a4b3  mov     edx, ebx; int
0x18002a4b5  call    ?RaiseException@CDispatchHelp@@QEAAXJ@Z; CDispatchHelp::RaiseException(long)
0x18002a4ba  mov     eax, ebx
0x18002a4bc  add     rsp, 88h
0x18002a4c3  pop     r15
0x18002a4c5  pop     r14
0x18002a4c7  pop     r13
0x18002a4c9  pop     r12
0x18002a4cb  pop     rdi
0x18002a4cc  pop     rsi
0x18002a4cd  pop     rbx
0x18002a4ce  pop     rbp
0x18002a4cf  retn
```
