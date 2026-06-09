# CSWbemServices::ExecNotificationQuery(ushort *,ushort *,long,IDispatch *,ISWbemEventSource * *)

- ea: `0x18001d830`
- end: `0x18001d9d9`
- name: `?ExecNotificationQuery@CSWbemServices@@UEAAJPEAG0JPEAUIDispatch@@PEAPEAUISWbemEventSource@@@Z`
- size: `425`
- prototype: `__int64 __usercall@<rax>(CSWbemServices *__hidden this@<rcx>, unsigned __int16 *@<rdx>, unsigned __int16 *@<r8>, int@<r9d>, struct IDispatch *, struct ISWbemEventSource **)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800036b0`
- `0x1800036e0`
- `0x1800050dc`
- `0x180006300`
- `0x1800077d0`
- `0x180014f20`
- `0x1800184d4`
- `0x18001d1dc`
- `0x18001d830`
- `0x18001f078`
- `0x180036010`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001d90d`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001d90d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSWbemServices::ExecNotificationQuery(
        CSWbemServices *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned int a4,
        struct IDispatch *a5,
        struct ISWbemEventSource **a6)
{
  int v10; // ebx
  CSWbemSecurity *v11; // rcx
  struct IUnknown *Proxy; // r14
  struct IWbemContext *IWbemContext; // r15
  CSWbemSecurity *v14; // rcx
  struct IDispatch *v15; // rax
  CSWbemEventSource *v16; // rdi
  unsigned int v17; // edx
  bool v19; // [rsp+40h] [rbp-58h] BYREF
  struct IEnumWbemClassObject *v20; // [rsp+48h] [rbp-50h] BYREF
  void *v21[9]; // [rsp+50h] [rbp-48h] BYREF

  ResetLastErrors();
  if ( !a6 )
  {
    v10 = -2147217400;
LABEL_20:
    CDispatchHelp::RaiseException((CSWbemServices *)((char *)this + 56), v10);
    return (unsigned int)v10;
  }
  v10 = -2147217407;
  v11 = (CSWbemSecurity *)*((_QWORD *)this + 17);
  if ( !v11 )
    goto LABEL_20;
  Proxy = CSWbemSecurity::GetProxy(v11);
  if ( !Proxy )
    goto LABEL_20;
  v20 = 0;
  IWbemContext = CSWbemNamedValueSet::GetIWbemContext(a5, *((struct IServiceProvider **)this + 18));
  v19 = 0;
  v21[0] = 0;
  if ( (unsigned int)CSWbemSecurity::SetSecurity(*((CSWbemSecurity **)this + 17), &v19, v21) )
  {
    v10 = ((__int64 (__fastcall *)(struct IUnknown *, unsigned __int16 *, unsigned __int16 *, _QWORD, struct IWbemContext *, struct IEnumWbemClassObject **))Proxy->lpVtbl[7].AddRef)(
            Proxy,
            a3,
            a2,
            a4,
            IWbemContext,
            &v20);
    if ( v10 >= 0 )
    {
      v15 = (struct IDispatch *)CWin32DefaultArena::WbemMemAlloc(0x80u);
      v21[1] = v15;
      if ( v15 )
        v16 = CSWbemEventSource::CSWbemEventSource(v15, this, v20);
      else
        v16 = 0;
      if ( v16 )
      {
        v10 = (**(__int64 (__fastcall ***)(CSWbemEventSource *, GUID *, struct ISWbemEventSource **))v16)(
                v16,
                &IID_ISWbemEventSource,
                a6);
        if ( v10 < 0 )
          CSWbemEventSource::`scalar deleting destructor'(v16, v17);
      }
      else
      {
        v10 = -2147217402;
      }
      ((void (__fastcall *)(struct IEnumWbemClassObject *))v20->lpVtbl->Release)(v20);
    }
  }
  if ( v19 )
    CSWbemSecurity::ResetSecurity(v14, v21[0]);
  SetWbemError((const OLECHAR **)this);
  if ( IWbemContext )
    ((void (__fastcall *)(struct IWbemContext *))IWbemContext->lpVtbl->Release)(IWbemContext);
  ((void (__fastcall *)(struct IUnknown *))Proxy->lpVtbl->Release)(Proxy);
  if ( v10 < 0 )
    goto LABEL_20;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001d830  push    rbx
0x18001d832  push    rsi
0x18001d833  push    rdi
0x18001d834  push    r12
0x18001d836  push    r13
0x18001d838  push    r14
0x18001d83a  push    r15
0x18001d83c  sub     rsp, 60h
0x18001d840  mov     edi, r9d
0x18001d843  mov     r12, r8
0x18001d846  mov     r13, rdx
0x18001d849  mov     rsi, rcx
0x18001d84c  call    ?ResetLastErrors@@YAXXZ; ResetLastErrors(void)
0x18001d851  cmp     [rsp+98h+arg_28], 0
0x18001d85a  jnz     short loc_18001D866
0x18001d85c  mov     ebx, 80041008h
0x18001d861  jmp     loc_18001D9BC
0x18001d866  mov     ebx, 80041001h
0x18001d86b  mov     rcx, [rsi+88h]; this
0x18001d872  test    rcx, rcx
0x18001d875  jz      loc_18001D9BC
0x18001d87b  call    ?GetProxy@CSWbemSecurity@@QEAAPEAUIUnknown@@XZ; CSWbemSecurity::GetProxy(void)
0x18001d880  mov     r14, rax
0x18001d883  test    rax, rax
0x18001d886  jz      loc_18001D9BC
0x18001d88c  mov     [rsp+98h+var_50], 0
0x18001d895  mov     rdx, [rsi+90h]; struct IServiceProvider *
0x18001d89c  mov     rcx, [rsp+98h+arg_20]; struct IDispatch *
0x18001d8a4  call    ?GetIWbemContext@CSWbemNamedValueSet@@SAPEAUIWbemContext@@PEAUIDispatch@@PEAUIServiceProvider@@@Z; CSWbemNamedValueSet::GetIWbemContext(IDispatch *,IServiceProvider *)
0x18001d8a9  mov     r15, rax
0x18001d8ac  mov     [rsp+98h+var_58], 0
0x18001d8b1  mov     [rsp+98h+var_48], 0
0x18001d8ba  lea     r8, [rsp+98h+var_48]; void **
0x18001d8bf  lea     rdx, [rsp+98h+var_58]; bool *
0x18001d8c4  mov     rcx, [rsi+88h]; this
0x18001d8cb  call    ?SetSecurity@CSWbemSecurity@@QEAAHAEA_NAEAPEAX@Z; CSWbemSecurity::SetSecurity(bool &,void * &)
0x18001d8d0  test    eax, eax
0x18001d8d2  jz      loc_18001D97C
0x18001d8d8  mov     rax, [r14]
0x18001d8db  lea     rcx, [rsp+98h+var_50]
0x18001d8e0  mov     [rsp+98h+var_70], rcx
0x18001d8e5  mov     [rsp+98h+var_78], r15
0x18001d8ea  mov     r9d, edi
0x18001d8ed  mov     r8, r13
0x18001d8f0  mov     rdx, r12
0x18001d8f3  mov     rcx, r14
0x18001d8f6  mov     rax, [rax+0B0h]
0x18001d8fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d902  mov     ebx, eax
0x18001d904  test    eax, eax
0x18001d906  js      short loc_18001D97C
0x18001d908  mov     ecx, 80h
0x18001d90d  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18001d913  mov     [rsp+98h+var_40], rax
0x18001d918  test    rax, rax
0x18001d91b  jz      short loc_18001D932
0x18001d91d  mov     r8, [rsp+98h+var_50]; struct IEnumWbemClassObject *
0x18001d922  mov     rdx, rsi; struct CSWbemServices *
0x18001d925  mov     rcx, rax; this
0x18001d928  call    ??0CSWbemEventSource@@QEAA@PEAVCSWbemServices@@PEAUIEnumWbemClassObject@@@Z; CSWbemEventSource::CSWbemEventSource(CSWbemServices *,IEnumWbemClassObject *)
0x18001d92d  mov     rdi, rax
0x18001d930  jmp     short loc_18001D934
0x18001d932  xor     edi, edi
0x18001d934  test    rdi, rdi
0x18001d937  jnz     short loc_18001D940
0x18001d939  mov     ebx, 80041006h
0x18001d93e  jmp     short loc_18001D96B
0x18001d940  mov     rax, [rdi]
0x18001d943  mov     r8, [rsp+98h+arg_28]
0x18001d94b  lea     rdx, IID_ISWbemEventSource
0x18001d952  mov     rcx, rdi
0x18001d955  mov     rax, [rax]
0x18001d958  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d95d  mov     ebx, eax
0x18001d95f  test    eax, eax
0x18001d961  jns     short loc_18001D96B
0x18001d963  mov     rcx, rdi; this
0x18001d966  call    ??_GCSWbemEventSource@@QEAAPEAXI@Z; CSWbemEventSource::`scalar deleting destructor'(uint)
0x18001d96b  mov     rcx, [rsp+98h+var_50]
0x18001d970  mov     rax, [rcx]
0x18001d973  mov     rax, [rax+10h]
0x18001d977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d97c  cmp     [rsp+98h+var_58], 0
0x18001d981  jz      short loc_18001D98D
0x18001d983  mov     rdx, [rsp+98h+var_48]; void *
0x18001d988  call    ?ResetSecurity@CSWbemSecurity@@QEAAXPEAX@Z; CSWbemSecurity::ResetSecurity(void *)
0x18001d98d  mov     rcx, rsi; this
0x18001d990  call    ?SetWbemError@@YAXPEAVCSWbemServices@@@Z; SetWbemError(CSWbemServices *)
0x18001d995  test    r15, r15
0x18001d998  jz      short loc_18001D9A9
0x18001d99a  mov     rax, [r15]
0x18001d99d  mov     rcx, r15
0x18001d9a0  mov     rax, [rax+10h]
0x18001d9a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d9a9  mov     rax, [r14]
0x18001d9ac  mov     rcx, r14
0x18001d9af  mov     rax, [rax+10h]
0x18001d9b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d9b8  test    ebx, ebx
0x18001d9ba  jns     short loc_18001D9C7
0x18001d9bc  lea     rcx, [rsi+38h]; this
0x18001d9c0  mov     edx, ebx; int
0x18001d9c2  call    ?RaiseException@CDispatchHelp@@QEAAXJ@Z; CDispatchHelp::RaiseException(long)
0x18001d9c7  mov     eax, ebx
0x18001d9c9  add     rsp, 60h
0x18001d9cd  pop     r15
0x18001d9cf  pop     r14
0x18001d9d1  pop     r13
0x18001d9d3  pop     r12
0x18001d9d5  pop     rdi
0x18001d9d6  pop     rsi
0x18001d9d7  pop     rbx
0x18001d9d8  retn
```
