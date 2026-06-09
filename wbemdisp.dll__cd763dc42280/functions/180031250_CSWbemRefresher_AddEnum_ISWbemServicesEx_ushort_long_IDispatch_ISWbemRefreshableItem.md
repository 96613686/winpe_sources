# CSWbemRefresher::AddEnum(ISWbemServicesEx *,ushort *,long,IDispatch *,ISWbemRefreshableItem * *)

- ea: `0x180031250`
- end: `0x180031434`
- name: `?AddEnum@CSWbemRefresher@@UEAAJPEAUISWbemServicesEx@@PEAGJPEAUIDispatch@@PEAPEAUISWbemRefreshableItem@@@Z`
- size: `484`
- prototype: `__int64 __usercall@<rax>(struct ISWbemRefresher *this@<rcx>, struct ISWbemServicesEx *@<rdx>, unsigned __int16 *@<r8>, int@<r9d>, struct IDispatch *, struct ISWbemRefreshableItem **)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800050dc`
- `0x180006300`
- `0x18000c0b0`
- `0x180014f20`
- `0x180018038`
- `0x180018130`
- `0x18001da8c`
- `0x1800308f0`
- `0x180030ec8`
- `0x180031250`
- `0x1800315b4`
- `0x180036010`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180031347`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180031347`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CSWbemRefresher::AddEnum(
        struct ISWbemRefresher *this,
        struct IDispatch *a2,
        unsigned __int16 *a3,
        unsigned int a4,
        struct IDispatch *a5,
        struct ISWbemRefreshableItem **a6)
{
  int v10; // edi
  struct IWbemContext *IWbemContext; // rax
  struct IWbemServices *IWbemServices; // rax
  __int64 v13; // rbx
  struct ISWbemRefresherVtbl *lpVtbl; // rcx
  struct IDispatch *v15; // rax
  CSWbemRefreshableItem *v16; // rbx
  int v18; // [rsp+40h] [rbp-30h] BYREF
  struct IWbemHiPerfEnum *v19; // [rsp+48h] [rbp-28h] BYREF
  __int64 v20; // [rsp+50h] [rbp-20h] BYREF
  __int64 v21[3]; // [rsp+58h] [rbp-18h] BYREF

  ResetLastErrors();
  if ( !a6 || !a2 || !a3 )
  {
    v10 = -2147217400;
LABEL_22:
    CDispatchHelp::RaiseException((CDispatchHelp *)&this[4], v10);
    return (unsigned int)v10;
  }
  v10 = -2147217407;
  v21[0] = 0;
  IWbemContext = CSWbemNamedValueSet::GetIWbemContext(a5, 0);
  ATL::CComPtr<IWbemContext>::Attach(v21, IWbemContext);
  v20 = 0;
  IWbemServices = CSWbemServices::GetIWbemServices(a2);
  ATL::CComPtr<IWbemServices>::Attach(&v20, IWbemServices);
  v13 = v20;
  if ( v20 )
  {
    if ( !this[15].lpVtbl )
      CSWbemRefresher::CreateRefresher((CSWbemRefresher *)this);
    lpVtbl = this[15].lpVtbl;
    if ( lpVtbl )
    {
      v19 = 0;
      v18 = 0;
      v10 = (*((__int64 (__fastcall **)(struct ISWbemRefresherVtbl *, __int64, unsigned __int16 *, _QWORD, __int64, struct IWbemHiPerfEnum **, int *))lpVtbl->QueryInterface
             + 7))(
              lpVtbl,
              v13,
              a3,
              a4,
              v21[0],
              &v19,
              &v18);
      if ( v10 >= 0 )
      {
        v15 = (struct IDispatch *)CWin32DefaultArena::WbemMemAlloc(0x90u);
        v21[1] = (__int64)v15;
        if ( v15 )
          v16 = CSWbemRefreshableItem::CSWbemRefreshableItem(v15, this, v18, a2, 0, v19);
        else
          v16 = 0;
        if ( v19 )
          ((void (__fastcall *)(struct IWbemHiPerfEnum *))v19->lpVtbl->Release)(v19);
        if ( v16 )
        {
          v10 = (**(__int64 (__fastcall ***)(CSWbemRefreshableItem *, GUID *, struct ISWbemRefreshableItem **))v16)(
                  v16,
                  &IID_ISWbemRefreshableItem,
                  a6);
          if ( v10 < 0 )
          {
            (*(void (__fastcall **)(CSWbemRefreshableItem *, __int64))(*(_QWORD *)v16 + 104LL))(v16, 1);
          }
          else
          {
            *(_QWORD *)std::map<long,CSWbemRefreshableItem *,std::less<long>,CWbemAllocator<CSWbemRefreshableItem *>>::operator[](
                         &this[17],
                         &v18) = v16;
            (*(void (__fastcall **)(CSWbemRefreshableItem *))(*(_QWORD *)v16 + 8LL))(v16);
          }
        }
        else
        {
          v10 = -2147217402;
        }
      }
    }
  }
  ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(&v20);
  ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(v21);
  if ( v10 < 0 )
    goto LABEL_22;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180031250  push    rbp
0x180031252  push    rbx
0x180031253  push    rsi
0x180031254  push    rdi
0x180031255  push    r13
0x180031257  push    r14
0x180031259  push    r15
0x18003125b  mov     rbp, rsp
0x18003125e  sub     rsp, 70h
0x180031262  mov     r13d, r9d
0x180031265  mov     r15, r8
0x180031268  mov     r14, rdx
0x18003126b  mov     rsi, rcx
0x18003126e  call    ?ResetLastErrors@@YAXXZ; ResetLastErrors(void)
0x180031273  cmp     [rbp+arg_28], 0
0x180031278  jz      loc_180031413
0x18003127e  test    r14, r14
0x180031281  jz      loc_180031413
0x180031287  test    r15, r15
0x18003128a  jz      loc_180031413
0x180031290  mov     edi, 80041001h
0x180031295  mov     [rbp+var_18], 0
0x18003129d  xor     edx, edx; struct IServiceProvider *
0x18003129f  mov     rcx, [rbp+arg_20]; struct IDispatch *
0x1800312a3  call    ?GetIWbemContext@CSWbemNamedValueSet@@SAPEAUIWbemContext@@PEAUIDispatch@@PEAUIServiceProvider@@@Z; CSWbemNamedValueSet::GetIWbemContext(IDispatch *,IServiceProvider *)
0x1800312a8  mov     rdx, rax
0x1800312ab  lea     rcx, [rbp+var_18]
0x1800312af  call    ?Attach@?$CComPtr@UIWbemContext@@@ATL@@QEAAXPEAUIWbemContext@@@Z; ATL::CComPtr<IWbemContext>::Attach(IWbemContext *)
0x1800312b4  mov     [rbp+var_20], 0
0x1800312bc  mov     rcx, r14; struct IDispatch *
0x1800312bf  call    ?GetIWbemServices@CSWbemServices@@SAPEAUIWbemServices@@PEAUIDispatch@@@Z; CSWbemServices::GetIWbemServices(IDispatch *)
0x1800312c4  mov     rdx, rax
0x1800312c7  lea     rcx, [rbp+var_20]
0x1800312cb  call    ?Attach@?$CComPtr@UIWbemServices@@@ATL@@QEAAXPEAUIWbemServices@@@Z; ATL::CComPtr<IWbemServices>::Attach(IWbemServices *)
0x1800312d0  mov     rbx, [rbp+var_20]
0x1800312d4  test    rbx, rbx
0x1800312d7  jz      loc_1800313FA
0x1800312dd  cmp     qword ptr [rsi+78h], 0
0x1800312e2  jnz     short loc_1800312EC
0x1800312e4  mov     rcx, rsi; this
0x1800312e7  call    ?CreateRefresher@CSWbemRefresher@@AEAAXXZ; CSWbemRefresher::CreateRefresher(void)
0x1800312ec  mov     rcx, [rsi+78h]
0x1800312f0  test    rcx, rcx
0x1800312f3  jz      loc_1800313FA
0x1800312f9  mov     [rbp+var_28], 0
0x180031301  mov     [rbp+var_30], 0
0x180031308  mov     rax, [rcx]
0x18003130b  lea     rdx, [rbp+var_30]
0x18003130f  mov     [rsp+70h+var_40], rdx
0x180031314  lea     rdx, [rbp+var_28]
0x180031318  mov     [rsp+70h+var_48], rdx
0x18003131d  mov     rdx, [rbp+var_18]
0x180031321  mov     [rsp+70h+var_50], rdx
0x180031326  mov     r9d, r13d
0x180031329  mov     r8, r15
0x18003132c  mov     rdx, rbx
0x18003132f  mov     rax, [rax+38h]
0x180031333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031338  mov     edi, eax
0x18003133a  test    eax, eax
0x18003133c  js      loc_1800313FA
0x180031342  mov     ecx, 90h
0x180031347  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18003134d  mov     [rbp+var_10], rax
0x180031351  test    rax, rax
0x180031354  jz      short loc_18003137F
0x180031356  mov     rcx, [rbp+var_28]
0x18003135a  mov     [rsp+70h+var_48], rcx; struct IWbemHiPerfEnum *
0x18003135f  mov     [rsp+70h+var_50], 0; struct IWbemClassObject *
0x180031368  mov     r9, r14; struct IDispatch *
0x18003136b  mov     r8d, [rbp+var_30]; int
0x18003136f  mov     rdx, rsi; struct ISWbemRefresher *
0x180031372  mov     rcx, rax; this
0x180031375  call    ??0CSWbemRefreshableItem@@QEAA@PEAUISWbemRefresher@@JPEAUIDispatch@@PEAUIWbemClassObject@@PEAUIWbemHiPerfEnum@@@Z; CSWbemRefreshableItem::CSWbemRefreshableItem(ISWbemRefresher *,long,IDispatch *,IWbemClassObject *,IWbemHiPerfEnum *)
0x18003137a  mov     rbx, rax
0x18003137d  jmp     short loc_180031381
0x18003137f  xor     ebx, ebx
0x180031381  mov     rcx, [rbp+var_28]
0x180031385  test    rcx, rcx
0x180031388  jz      short loc_180031396
0x18003138a  mov     rax, [rcx]
0x18003138d  mov     rax, [rax+10h]
0x180031391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031396  test    rbx, rbx
0x180031399  jnz     short loc_1800313A2
0x18003139b  mov     edi, 80041006h
0x1800313a0  jmp     short loc_1800313FA
0x1800313a2  mov     rax, [rbx]
0x1800313a5  mov     r8, [rbp+arg_28]
0x1800313a9  lea     rdx, IID_ISWbemRefreshableItem
0x1800313b0  mov     rcx, rbx
0x1800313b3  mov     rax, [rax]
0x1800313b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800313bb  mov     edi, eax
0x1800313bd  test    eax, eax
0x1800313bf  js      short loc_1800313E5
0x1800313c1  lea     rcx, [rsi+88h]
0x1800313c8  lea     rdx, [rbp+var_30]
0x1800313cc  call    ??A?$map@JPEAVCSWbemRefreshableItem@@U?$less@J@std@@V?$CWbemAllocator@PEAVCSWbemRefreshableItem@@@@@std@@QEAAAEAPEAVCSWbemRefreshableItem@@AEBJ@Z; std::map<long,CSWbemRefreshableItem *,std::less<long>,CWbemAllocator<CSWbemRefreshableItem *>>::operator[](long const &)
0x1800313d1  mov     [rax], rbx
0x1800313d4  mov     rax, [rbx]
0x1800313d7  mov     rcx, rbx
0x1800313da  mov     rax, [rax+8]
0x1800313de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800313e3  jmp     short loc_1800313FA
0x1800313e5  mov     rax, [rbx]
0x1800313e8  mov     edx, 1
0x1800313ed  mov     rcx, rbx
0x1800313f0  mov     rax, [rax+68h]
0x1800313f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800313f9  nop
0x1800313fa  lea     rcx, [rbp+var_20]
0x1800313fe  call    ??1?$CComQIPtr@UISWbemObject@@$1?_GUID_76a6415a_cb41_11d1_8b02_00600806d9b6@@3U__s_GUID@@B@ATL@@QEAA@XZ; ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(void)
0x180031403  nop
0x180031404  lea     rcx, [rbp+var_18]
0x180031408  call    ??1?$CComQIPtr@UISWbemObject@@$1?_GUID_76a6415a_cb41_11d1_8b02_00600806d9b6@@3U__s_GUID@@B@ATL@@QEAA@XZ; ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(void)
0x18003140d  test    edi, edi
0x18003140f  jns     short loc_180031423
0x180031411  jmp     short loc_180031418
0x180031413  mov     edi, 80041008h
0x180031418  lea     rcx, [rsi+20h]; this
0x18003141c  mov     edx, edi; int
0x18003141e  call    ?RaiseException@CDispatchHelp@@QEAAXJ@Z; CDispatchHelp::RaiseException(long)
0x180031423  mov     eax, edi
0x180031425  add     rsp, 70h
0x180031429  pop     r15
0x18003142b  pop     r14
0x18003142d  pop     r13
0x18003142f  pop     rdi
0x180031430  pop     rsi
0x180031431  pop     rbx
0x180031432  pop     rbp
0x180031433  retn
```
