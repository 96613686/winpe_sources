# CServiceInfo::HrInitialize(_GUID const &,ushort const *,ushort const *,ushort const *,SmartComPtr<IUPnPDeviceControl> &,int)

- ea: `0x1800306c4`
- end: `0x1800309ea`
- name: `?HrInitialize@CServiceInfo@@QEAAJAEBU_GUID@@PEBG11AEAV?$SmartComPtr@UIUPnPDeviceControl@@@@H@Z`
- size: `806`
- prototype: `__int64 __usercall@<rax>(CUString *this@<rcx>, unsigned __int16 *, __int64, int)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e96c`

## callees

- `0x1800056d8`
- `0x1800056f0`
- `0x18000f8a0`
- `0x180015a9c`
- `0x1800209c8`
- `0x1800306c4`
- `0x18003a30c`
- `0x18003b1cc`
- `0x18003bf14`
- `0x18003c018`
- `0x18004ea68`
- `0x180050fa8`
- `0x180050fe0`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003096e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003097e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003096e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003097e`
- `OLEAUT32!__imp_SysAllocString` at `0x18003075d`
- `OLEAUT32!__imp_SysAllocString` at `0x18003076f`
- `OLEAUT32!__imp_SysAllocString` at `0x18003075d`
- `OLEAUT32!__imp_SysAllocString` at `0x18003076f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800307fa`
- `OLEAUT32!__imp_SysFreeString` at `0x18003080e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800307fa`
- `OLEAUT32!__imp_SysFreeString` at `0x18003080e`

## pseudocode

```c
__int64 __fastcall CServiceInfo::HrInitialize(
        LPVOID *this,
        __int64 a2,
        OLECHAR *a3,
        const OLECHAR *a4,
        unsigned __int16 *a5,
        struct IUnknown **a6,
        int a7)
{
  struct IUnknown **v10; // r15
  int Instance; // ebx
  OLECHAR *v12; // r12
  BSTR v13; // rax
  OLECHAR *v14; // rsi
  int v15; // eax
  int v16; // r12d
  struct IUnknown *v17; // rdx
  _QWORD *v18; // r15
  LPVOID v20; // [rsp+40h] [rbp-10h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-8h] BYREF
  LPVOID pv; // [rsp+A0h] [rbp+50h] BYREF

  if ( !a3 )
    return 2147500035LL;
  if ( !a4 )
    return 2147500035LL;
  v10 = a6;
  if ( !*a6 )
    return 2147500035LL;
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      (unsigned int)WPP_aff4041d6f30374a6fbca409bd8c9069_Traceguids,
      (_DWORD)a3,
      (__int64)a4);
  if ( a5 )
  {
    Instance = CUString::HrAssign((CUString *)this, a5);
    if ( Instance < 0 )
      goto LABEL_38;
  }
  v12 = SysAllocString(a3);
  v13 = SysAllocString(a4);
  v14 = v13;
  if ( v12 && v13 )
  {
    v15 = ((__int64 (__fastcall *)(struct IUnknown *, OLECHAR *, BSTR, char *))(*v10)->lpVtbl[1].AddRef)(
            *v10,
            v12,
            v13,
            (char *)this + 8);
    Instance = v15;
    if ( (v15 == -2147023174 || v15 == -2147417848 || (unsigned int)(v15 + 2147023170) <= 1)
      && (!*v10
       || ((unsigned __int64 (__fastcall *)(struct IUnknown *, __int64 *, void **))(*v10)->lpVtbl->QueryInterface)(
            *v10,
            bogusIID,
            &pBogusInterface) != -2147467262) )
    {
      HrUnregisterDeviceByUDN(a3);
    }
    goto LABEL_18;
  }
  Instance = -2147024882;
  if ( v12 )
LABEL_18:
    SysFreeString(v12);
  if ( v14 )
    SysFreeString(v14);
  if ( Instance < 0 )
    goto LABEL_38;
  v16 = a7;
  if ( !a7 )
  {
    v18 = this + 1;
LABEL_26:
    Instance = ATL::CComPtrBase<IUPnPEventingManager>::CoCreateInstance(this + 2);
    if ( Instance >= 0 )
    {
      Instance = ATL::CComPtrBase<IUPnPAutomationProxy>::CoCreateInstance(this + 3);
      if ( Instance >= 0 )
      {
        SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(&ppv);
        Instance = ATL::CComPtrBase<IUPnPRegistrarPrivate>::CoCreateInstance(&ppv);
        if ( Instance >= 0 )
        {
          pv = 0;
          v20 = 0;
          Instance = (*(__int64 (__fastcall **)(LPVOID, __int64, OLECHAR *, const OLECHAR *, LPVOID *, LPVOID *))(*(_QWORD *)ppv + 56LL))(
                       ppv,
                       a2,
                       a3,
                       a4,
                       &pv,
                       &v20);
          if ( Instance >= 0 )
          {
            Instance = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, _QWORD, LPVOID, LPVOID, int))(*(_QWORD *)this[3]
                                                                                                 + 24LL))(
                         this[3],
                         a3,
                         *v18,
                         pv,
                         v20,
                         v16);
            if ( Instance >= 0 )
            {
              Instance = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, const OLECHAR *, LPVOID, _QWORD, int))(*(_QWORD *)this[2] + 24LL))(
                           this[2],
                           a3,
                           a4,
                           this[3],
                           *v18,
                           v16);
              if ( Instance == -2147467262 )
              {
                if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_aff4041d6f30374a6fbca409bd8c9069_Traceguids);
                ATL::CComPtrBase<IUPnPDynamicContentSource>::Release(this + 2);
                Instance = 0;
              }
            }
            CoTaskMemFree(pv);
            CoTaskMemFree(v20);
          }
        }
        ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(&ppv);
      }
    }
    goto LABEL_38;
  }
  v17 = *v10;
  v18 = this + 1;
  Instance = HrCopyProxyIdentity((struct IUnknown *)this[1], v17);
  if ( Instance >= 0 )
    goto LABEL_26;
LABEL_38:
  if ( Instance && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      WPP_aff4041d6f30374a6fbca409bd8c9069_Traceguids,
      (unsigned int)Instance);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800306c4  mov     [rsp-38h+arg_0], rbx
0x1800306c9  mov     [rsp-38h+arg_8], rdx
0x1800306ce  push    rbp
0x1800306cf  push    rsi
0x1800306d0  push    rdi
0x1800306d1  push    r12
0x1800306d3  push    r13
0x1800306d5  push    r14
0x1800306d7  push    r15
0x1800306d9  mov     rbp, rsp
0x1800306dc  sub     rsp, 50h
0x1800306e0  mov     r13, r9
0x1800306e3  mov     rdi, r8
0x1800306e6  mov     r14, rcx
0x1800306e9  test    r8, r8
0x1800306ec  jz      loc_1800309CC
0x1800306f2  test    r9, r9
0x1800306f5  jz      loc_1800309CC
0x1800306fb  mov     r15, [rbp+arg_28]
0x1800306ff  cmp     qword ptr [r15], 0
0x180030703  jz      loc_1800309CC
0x180030709  mov     rcx, cs:WPP_GLOBAL_Control
0x180030710  lea     rsi, WPP_GLOBAL_Control
0x180030717  cmp     rcx, rsi
0x18003071a  jz      short loc_18003073F
0x18003071c  test    byte ptr [rcx+1Ch], 40h
0x180030720  jz      short loc_18003073F
0x180030722  mov     rcx, [rcx+10h]
0x180030726  mov     edx, 0Ah
0x18003072b  mov     [rsp+50h+var_30], r9
0x180030730  mov     r9, r8
0x180030733  lea     r8, WPP_aff4041d6f30374a6fbca409bd8c9069_Traceguids
0x18003073a  call    WPP_SF_SS
0x18003073f  mov     rdx, [rbp+arg_20]; unsigned __int16 *
0x180030743  test    rdx, rdx
0x180030746  jz      short loc_18003075A
0x180030748  mov     rcx, r14; this
0x18003074b  call    ?HrAssign@CUString@@QEAAJPEBG@Z; CUString::HrAssign(ushort const *)
0x180030750  mov     ebx, eax
0x180030752  test    eax, eax
0x180030754  js      loc_18003099A
0x18003075a  mov     rcx, rdi; psz
0x18003075d  call    cs:__imp_SysAllocString
0x180030764  nop     dword ptr [rax+rax+00h]
0x180030769  mov     rcx, r13; psz
0x18003076c  mov     r12, rax
0x18003076f  call    cs:__imp_SysAllocString
0x180030776  nop     dword ptr [rax+rax+00h]
0x18003077b  mov     rsi, rax
0x18003077e  test    r12, r12
0x180030781  jz      short loc_1800307ED
0x180030783  test    rax, rax
0x180030786  jz      short loc_1800307ED
0x180030788  mov     rcx, [r15]
0x18003078b  lea     r9, [r14+8]
0x18003078f  mov     r8, rsi
0x180030792  mov     rdx, [rcx]
0x180030795  mov     rax, [rdx+20h]
0x180030799  mov     rdx, r12
0x18003079c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800307a1  mov     ebx, eax
0x1800307a3  cmp     eax, 800706BAh
0x1800307a8  jz      short loc_1800307BB
0x1800307aa  cmp     eax, 80010108h
0x1800307af  jz      short loc_1800307BB
0x1800307b1  add     eax, 7FF8F942h
0x1800307b6  cmp     eax, 1
0x1800307b9  ja      short loc_1800307F7
0x1800307bb  mov     rcx, [r15]
0x1800307be  test    rcx, rcx
0x1800307c1  jz      short loc_1800307E3
0x1800307c3  mov     rax, [rcx]
0x1800307c6  lea     r8, ?pBogusInterface@@3PEAXEA; void * pBogusInterface
0x1800307cd  lea     rdx, bogusIID
0x1800307d4  mov     rax, [rax]
0x1800307d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800307dc  cmp     eax, 80004002h
0x1800307e1  jz      short loc_1800307F7
0x1800307e3  mov     rcx, rdi; unsigned __int16 *
0x1800307e6  call    ?HrUnregisterDeviceByUDN@@YAJPEAG@Z; HrUnregisterDeviceByUDN(ushort *)
0x1800307eb  jmp     short loc_1800307F7
0x1800307ed  mov     ebx, 8007000Eh
0x1800307f2  test    r12, r12
0x1800307f5  jz      short loc_180030806
0x1800307f7  mov     rcx, r12; bstrString
0x1800307fa  call    cs:__imp_SysFreeString
0x180030801  nop     dword ptr [rax+rax+00h]
0x180030806  test    rsi, rsi
0x180030809  jz      short loc_18003081A
0x18003080b  mov     rcx, rsi; bstrString
0x18003080e  call    cs:__imp_SysFreeString
0x180030815  nop     dword ptr [rax+rax+00h]
0x18003081a  test    ebx, ebx
0x18003081c  js      loc_180030993
0x180030822  mov     r12d, [rbp+arg_30]
0x180030826  test    r12d, r12d
0x180030829  jz      short loc_180030846
0x18003082b  mov     rdx, [r15]; struct IUnknown *
0x18003082e  lea     r15, [r14+8]
0x180030832  mov     rcx, [r15]; struct IUnknown *
0x180030835  call    ?HrCopyProxyIdentity@@YAJPEAUIUnknown@@0@Z; HrCopyProxyIdentity(IUnknown *,IUnknown *)
0x18003083a  mov     ebx, eax
0x18003083c  test    eax, eax
0x18003083e  js      loc_180030993
0x180030844  jmp     short loc_18003084A
0x180030846  lea     r15, [r14+8]
0x18003084a  lea     rsi, [r14+10h]
0x18003084e  mov     rcx, rsi; ppv
0x180030851  call    ?CoCreateInstance@?$CComPtrBase@UIUPnPEventingManager@@@ATL@@QEAAJAEBU_GUID@@PEAUIUnknown@@K@Z; ATL::CComPtrBase<IUPnPEventingManager>::CoCreateInstance(_GUID const &,IUnknown *,ulong)
0x180030856  mov     ebx, eax
0x180030858  test    eax, eax
0x18003085a  js      loc_180030993
0x180030860  lea     rcx, [r14+18h]; ppv
0x180030864  call    ?CoCreateInstance@?$CComPtrBase@UIUPnPAutomationProxy@@@ATL@@QEAAJAEBU_GUID@@PEAUIUnknown@@K@Z; ATL::CComPtrBase<IUPnPAutomationProxy>::CoCreateInstance(_GUID const &,IUnknown *,ulong)
0x180030869  mov     ebx, eax
0x18003086b  test    eax, eax
0x18003086d  js      loc_180030993
0x180030873  lea     rcx, [rbp+ppv]; void *
0x180030877  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x18003087c  lea     rcx, [rbp+ppv]; ppv
0x180030880  call    ?CoCreateInstance@?$CComPtrBase@UIUPnPRegistrarPrivate@@@ATL@@QEAAJAEBU_GUID@@PEAUIUnknown@@K@Z; ATL::CComPtrBase<IUPnPRegistrarPrivate>::CoCreateInstance(_GUID const &,IUnknown *,ulong)
0x180030885  mov     ebx, eax
0x180030887  test    eax, eax
0x180030889  js      loc_18003098A
0x18003088f  mov     rcx, [rbp+ppv]
0x180030893  lea     rdx, [rbp+var_10]
0x180030897  mov     [rsp+50h+var_28], rdx
0x18003089c  mov     r9, r13
0x18003089f  mov     [rbp+pv], 0
0x1800308a7  lea     rdx, [rbp+pv]
0x1800308ab  mov     [rbp+var_10], 0
0x1800308b3  mov     r8, rdi
0x1800308b6  mov     rax, [rcx]
0x1800308b9  mov     [rsp+50h+var_30], rdx
0x1800308be  mov     rdx, [rbp+arg_8]
0x1800308c2  mov     rax, [rax+38h]
0x1800308c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800308cb  mov     ebx, eax
0x1800308cd  test    eax, eax
0x1800308cf  js      loc_18003098A
0x1800308d5  mov     rdx, [rbp+var_10]
0x1800308d9  mov     rcx, [r14+18h]
0x1800308dd  mov     r9, [rbp+pv]
0x1800308e1  mov     r8, [r15]
0x1800308e4  mov     dword ptr [rsp+50h+var_28], r12d
0x1800308e9  mov     rax, [rcx]
0x1800308ec  mov     [rsp+50h+var_30], rdx
0x1800308f1  mov     rdx, rdi
0x1800308f4  mov     rax, [rax+18h]
0x1800308f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800308fd  mov     ebx, eax
0x1800308ff  test    eax, eax
0x180030901  js      short loc_18003096A
0x180030903  mov     rdx, [r15]
0x180030906  mov     r8, r13
0x180030909  mov     rcx, [rsi]
0x18003090c  mov     r9, [r14+18h]
0x180030910  mov     dword ptr [rsp+50h+var_28], r12d
0x180030915  mov     [rsp+50h+var_30], rdx
0x18003091a  mov     rdx, rdi
0x18003091d  mov     rax, [rcx]
0x180030920  mov     rax, [rax+18h]
0x180030924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030929  mov     ebx, eax
0x18003092b  cmp     eax, 80004002h
0x180030930  jnz     short loc_18003096A
0x180030932  mov     rcx, cs:WPP_GLOBAL_Control
0x180030939  lea     rax, WPP_GLOBAL_Control
0x180030940  cmp     rcx, rax
0x180030943  jz      short loc_180030960
0x180030945  test    byte ptr [rcx+1Ch], 40h
0x180030949  jz      short loc_180030960
0x18003094b  mov     rcx, [rcx+10h]
0x18003094f  lea     r8, WPP_aff4041d6f30374a6fbca409bd8c9069_Traceguids
0x180030956  mov     edx, 0Bh
0x18003095b  call    WPP_SF_
0x180030960  mov     rcx, rsi
0x180030963  call    ?Release@?$CComPtrBase@UIUPnPDynamicContentSource@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IUPnPDynamicContentSource>::Release(void)
0x180030968  xor     ebx, ebx
0x18003096a  mov     rcx, [rbp+pv]; pv
0x18003096e  call    cs:__imp_CoTaskMemFree
0x180030975  nop     dword ptr [rax+rax+00h]
0x18003097a  mov     rcx, [rbp+var_10]; pv
0x18003097e  call    cs:__imp_CoTaskMemFree
0x180030985  nop     dword ptr [rax+rax+00h]
0x18003098a  lea     rcx, [rbp+ppv]
0x18003098e  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x180030993  lea     rsi, WPP_GLOBAL_Control
0x18003099a  test    ebx, ebx
0x18003099c  jz      short loc_1800309C8
0x18003099e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800309a5  cmp     rcx, rsi
0x1800309a8  jz      short loc_1800309C8
0x1800309aa  test    byte ptr [rcx+1Ch], 1
0x1800309ae  jz      short loc_1800309C8
0x1800309b0  mov     rcx, [rcx+10h]
0x1800309b4  lea     r8, WPP_aff4041d6f30374a6fbca409bd8c9069_Traceguids
0x1800309bb  mov     edx, 0Ch
0x1800309c0  mov     r9d, ebx
0x1800309c3  call    WPP_SF_d
0x1800309c8  mov     eax, ebx
0x1800309ca  jmp     short loc_1800309D1
0x1800309cc  mov     eax, 80004003h
0x1800309d1  mov     rbx, [rsp+50h+arg_0]
0x1800309d9  add     rsp, 50h
0x1800309dd  pop     r15
0x1800309df  pop     r14
0x1800309e1  pop     r13
0x1800309e3  pop     r12
0x1800309e5  pop     rdi
0x1800309e6  pop     rsi
0x1800309e7  pop     rbp
0x1800309e8  retn
```
