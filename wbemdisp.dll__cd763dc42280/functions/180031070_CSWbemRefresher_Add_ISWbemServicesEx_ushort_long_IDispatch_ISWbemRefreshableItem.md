# CSWbemRefresher::Add(ISWbemServicesEx *,ushort *,long,IDispatch *,ISWbemRefreshableItem * *)

- ea: `0x180031070`
- end: `0x18003123f`
- name: `?Add@CSWbemRefresher@@UEAAJPEAUISWbemServicesEx@@PEAGJPEAUIDispatch@@PEAPEAUISWbemRefreshableItem@@@Z`
- size: `463`
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
- `0x180031070`
- `0x1800315b4`
- `0x180036010`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180031167`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180031167`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CSWbemRefresher::Add(
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
  struct IWbemClassObject *v15; // rax
  CSWbemRefreshableItem *v16; // rbx
  int v18; // [rsp+40h] [rbp-30h] BYREF
  __int64 v19; // [rsp+48h] [rbp-28h] BYREF
  __int64 v20; // [rsp+50h] [rbp-20h] BYREF
  struct IWbemClassObject *v21[3]; // [rsp+58h] [rbp-18h] BYREF

  ResetLastErrors();
  if ( !a6 || !a2 || !a3 )
  {
    v10 = -2147217400;
LABEL_20:
    CDispatchHelp::RaiseException((CDispatchHelp *)&this[4], v10);
    return (unsigned int)v10;
  }
  v10 = -2147217407;
  v20 = 0;
  IWbemContext = CSWbemNamedValueSet::GetIWbemContext(a5, 0);
  ATL::CComPtr<IWbemContext>::Attach(&v20, IWbemContext);
  v19 = 0;
  IWbemServices = CSWbemServices::GetIWbemServices(a2);
  ATL::CComPtr<IWbemServices>::Attach(&v19, IWbemServices);
  v13 = v19;
  if ( v19 )
  {
    if ( !this[15].lpVtbl )
      CSWbemRefresher::CreateRefresher((CSWbemRefresher *)this);
    lpVtbl = this[15].lpVtbl;
    if ( lpVtbl )
    {
      v21[0] = 0;
      v18 = 0;
      v10 = (*((__int64 (__fastcall **)(struct ISWbemRefresherVtbl *, __int64, unsigned __int16 *, _QWORD, __int64, struct IWbemClassObject **, int *))lpVtbl->QueryInterface
             + 3))(
              lpVtbl,
              v13,
              a3,
              a4,
              v20,
              v21,
              &v18);
      if ( v10 >= 0 )
      {
        v15 = (struct IWbemClassObject *)CWin32DefaultArena::WbemMemAlloc(0x90u);
        v21[1] = v15;
        if ( v15 )
          v16 = CSWbemRefreshableItem::CSWbemRefreshableItem((struct IDispatch *)v15, this, v18, a2, v21[0], 0);
        else
          v16 = 0;
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
  ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(&v19);
  ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(&v20);
  if ( v10 < 0 )
    goto LABEL_20;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180031070  push    rbp
0x180031072  push    rbx
0x180031073  push    rsi
0x180031074  push    rdi
0x180031075  push    r13
0x180031077  push    r14
0x180031079  push    r15
0x18003107b  mov     rbp, rsp
0x18003107e  sub     rsp, 70h
0x180031082  mov     r13d, r9d
0x180031085  mov     r15, r8
0x180031088  mov     r14, rdx
0x18003108b  mov     rsi, rcx
0x18003108e  call    ?ResetLastErrors@@YAXXZ; ResetLastErrors(void)
0x180031093  cmp     [rbp+arg_28], 0
0x180031098  jz      loc_18003121E
0x18003109e  test    r14, r14
0x1800310a1  jz      loc_18003121E
0x1800310a7  test    r15, r15
0x1800310aa  jz      loc_18003121E
0x1800310b0  mov     edi, 80041001h
0x1800310b5  mov     [rbp+var_20], 0
0x1800310bd  xor     edx, edx; struct IServiceProvider *
0x1800310bf  mov     rcx, [rbp+arg_20]; struct IDispatch *
0x1800310c3  call    ?GetIWbemContext@CSWbemNamedValueSet@@SAPEAUIWbemContext@@PEAUIDispatch@@PEAUIServiceProvider@@@Z; CSWbemNamedValueSet::GetIWbemContext(IDispatch *,IServiceProvider *)
0x1800310c8  mov     rdx, rax
0x1800310cb  lea     rcx, [rbp+var_20]
0x1800310cf  call    ?Attach@?$CComPtr@UIWbemContext@@@ATL@@QEAAXPEAUIWbemContext@@@Z; ATL::CComPtr<IWbemContext>::Attach(IWbemContext *)
0x1800310d4  mov     [rbp+var_28], 0
0x1800310dc  mov     rcx, r14; struct IDispatch *
0x1800310df  call    ?GetIWbemServices@CSWbemServices@@SAPEAUIWbemServices@@PEAUIDispatch@@@Z; CSWbemServices::GetIWbemServices(IDispatch *)
0x1800310e4  mov     rdx, rax
0x1800310e7  lea     rcx, [rbp+var_28]
0x1800310eb  call    ?Attach@?$CComPtr@UIWbemServices@@@ATL@@QEAAXPEAUIWbemServices@@@Z; ATL::CComPtr<IWbemServices>::Attach(IWbemServices *)
0x1800310f0  mov     rbx, [rbp+var_28]
0x1800310f4  test    rbx, rbx
0x1800310f7  jz      loc_180031205
0x1800310fd  cmp     qword ptr [rsi+78h], 0
0x180031102  jnz     short loc_18003110C
0x180031104  mov     rcx, rsi; this
0x180031107  call    ?CreateRefresher@CSWbemRefresher@@AEAAXXZ; CSWbemRefresher::CreateRefresher(void)
0x18003110c  mov     rcx, [rsi+78h]
0x180031110  test    rcx, rcx
0x180031113  jz      loc_180031205
0x180031119  mov     [rbp+var_18], 0
0x180031121  mov     [rbp+var_30], 0
0x180031128  mov     rax, [rcx]
0x18003112b  lea     rdx, [rbp+var_30]
0x18003112f  mov     [rsp+70h+var_40], rdx
0x180031134  lea     rdx, [rbp+var_18]
0x180031138  mov     [rsp+70h+var_48], rdx
0x18003113d  mov     rdx, [rbp+var_20]
0x180031141  mov     [rsp+70h+var_50], rdx
0x180031146  mov     r9d, r13d
0x180031149  mov     r8, r15
0x18003114c  mov     rdx, rbx
0x18003114f  mov     rax, [rax+18h]
0x180031153  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031158  mov     edi, eax
0x18003115a  test    eax, eax
0x18003115c  js      loc_180031205
0x180031162  mov     ecx, 90h
0x180031167  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18003116d  mov     [rbp+var_10], rax
0x180031171  test    rax, rax
0x180031174  jz      short loc_18003119F
0x180031176  mov     [rsp+70h+var_48], 0; struct IWbemHiPerfEnum *
0x18003117f  mov     rcx, [rbp+var_18]
0x180031183  mov     [rsp+70h+var_50], rcx; struct IWbemClassObject *
0x180031188  mov     r9, r14; struct IDispatch *
0x18003118b  mov     r8d, [rbp+var_30]; int
0x18003118f  mov     rdx, rsi; struct ISWbemRefresher *
0x180031192  mov     rcx, rax; this
0x180031195  call    ??0CSWbemRefreshableItem@@QEAA@PEAUISWbemRefresher@@JPEAUIDispatch@@PEAUIWbemClassObject@@PEAUIWbemHiPerfEnum@@@Z; CSWbemRefreshableItem::CSWbemRefreshableItem(ISWbemRefresher *,long,IDispatch *,IWbemClassObject *,IWbemHiPerfEnum *)
0x18003119a  mov     rbx, rax
0x18003119d  jmp     short loc_1800311A1
0x18003119f  xor     ebx, ebx
0x1800311a1  test    rbx, rbx
0x1800311a4  jnz     short loc_1800311AD
0x1800311a6  mov     edi, 80041006h
0x1800311ab  jmp     short loc_180031205
0x1800311ad  mov     rax, [rbx]
0x1800311b0  mov     r8, [rbp+arg_28]
0x1800311b4  lea     rdx, IID_ISWbemRefreshableItem
0x1800311bb  mov     rcx, rbx
0x1800311be  mov     rax, [rax]
0x1800311c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800311c6  mov     edi, eax
0x1800311c8  test    eax, eax
0x1800311ca  js      short loc_1800311F0
0x1800311cc  lea     rcx, [rsi+88h]
0x1800311d3  lea     rdx, [rbp+var_30]
0x1800311d7  call    ??A?$map@JPEAVCSWbemRefreshableItem@@U?$less@J@std@@V?$CWbemAllocator@PEAVCSWbemRefreshableItem@@@@@std@@QEAAAEAPEAVCSWbemRefreshableItem@@AEBJ@Z; std::map<long,CSWbemRefreshableItem *,std::less<long>,CWbemAllocator<CSWbemRefreshableItem *>>::operator[](long const &)
0x1800311dc  mov     [rax], rbx
0x1800311df  mov     rax, [rbx]
0x1800311e2  mov     rcx, rbx
0x1800311e5  mov     rax, [rax+8]
0x1800311e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800311ee  jmp     short loc_180031205
0x1800311f0  mov     rax, [rbx]
0x1800311f3  mov     edx, 1
0x1800311f8  mov     rcx, rbx
0x1800311fb  mov     rax, [rax+68h]
0x1800311ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031204  nop
0x180031205  lea     rcx, [rbp+var_28]
0x180031209  call    ??1?$CComQIPtr@UISWbemObject@@$1?_GUID_76a6415a_cb41_11d1_8b02_00600806d9b6@@3U__s_GUID@@B@ATL@@QEAA@XZ; ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(void)
0x18003120e  nop
0x18003120f  lea     rcx, [rbp+var_20]
0x180031213  call    ??1?$CComQIPtr@UISWbemObject@@$1?_GUID_76a6415a_cb41_11d1_8b02_00600806d9b6@@3U__s_GUID@@B@ATL@@QEAA@XZ; ATL::CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>::~CComQIPtr<ISWbemObject,&__s_GUID const _GUID_76a6415a_cb41_11d1_8b02_00600806d9b6>(void)
0x180031218  test    edi, edi
0x18003121a  jns     short loc_18003122E
0x18003121c  jmp     short loc_180031223
0x18003121e  mov     edi, 80041008h
0x180031223  lea     rcx, [rsi+20h]; this
0x180031227  mov     edx, edi; int
0x180031229  call    ?RaiseException@CDispatchHelp@@QEAAXJ@Z; CDispatchHelp::RaiseException(long)
0x18003122e  mov     eax, edi
0x180031230  add     rsp, 70h
0x180031234  pop     r15
0x180031236  pop     r14
0x180031238  pop     r13
0x18003123a  pop     rdi
0x18003123b  pop     rsi
0x18003123c  pop     rbx
0x18003123d  pop     rbp
0x18003123e  retn
```
