# CServiceInfo::HrInitialize(_GUID const &,ushort const *,ushort const *,ushort const *,SmartComPtr<IUPnPDeviceControl> &,int)

- ea: `0x18002edc4`
- end: `0x18002f0c5`
- name: `?HrInitialize@CServiceInfo@@QEAAJAEBU_GUID@@PEBG11AEAV?$SmartComPtr@UIUPnPDeviceControl@@@@H@Z`
- size: `769`
- prototype: `__int64 __usercall@<rax>(CUString *this@<rcx>, unsigned __int16 *, __int64, int)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x180019cf4`

## callees

- `0x18000e3ec`
- `0x1800117bc`
- `0x1800117d0`
- `0x18001ab90`
- `0x180020918`
- `0x18002edc4`
- `0x180037ef8`
- `0x180038ce4`
- `0x18003994c`
- `0x180039a84`
- `0x18004b78c`
- `0x18004db2c`
- `0x18004db5c`
- `0x180055010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f056`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f060`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f056`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f060`
- `OLEAUT32!__imp_SysAllocString` at `0x18002ee5d`
- `OLEAUT32!__imp_SysAllocString` at `0x18002ee69`
- `OLEAUT32!__imp_SysAllocString` at `0x18002ee5d`
- `OLEAUT32!__imp_SysAllocString` at `0x18002ee69`
- `OLEAUT32!__imp_SysFreeString` at `0x18002eeee`
- `OLEAUT32!__imp_SysFreeString` at `0x18002eefc`
- `OLEAUT32!__imp_SysFreeString` at `0x18002eeee`
- `OLEAUT32!__imp_SysFreeString` at `0x18002eefc`

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
  HRESULT Instance; // ebx
  OLECHAR *v12; // r12
  BSTR v13; // rax
  OLECHAR *v14; // rsi
  HRESULT v15; // eax
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
        ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>((__int64)&ppv);
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
0x18002edc4  mov     [rsp-38h+arg_0], rbx
0x18002edc9  mov     [rsp-38h+arg_8], rdx
0x18002edce  push    rbp
0x18002edcf  push    rsi
0x18002edd0  push    rdi
0x18002edd1  push    r12
0x18002edd3  push    r13
0x18002edd5  push    r14
0x18002edd7  push    r15
0x18002edd9  mov     rbp, rsp
0x18002eddc  sub     rsp, 50h
0x18002ede0  mov     r13, r9
0x18002ede3  mov     rdi, r8
0x18002ede6  mov     r14, rcx
0x18002ede9  test    r8, r8
0x18002edec  jz      loc_18002F0A8
0x18002edf2  test    r9, r9
0x18002edf5  jz      loc_18002F0A8
0x18002edfb  mov     r15, [rbp+arg_28]
0x18002edff  cmp     qword ptr [r15], 0
0x18002ee03  jz      loc_18002F0A8
0x18002ee09  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ee10  lea     rsi, WPP_GLOBAL_Control
0x18002ee17  cmp     rcx, rsi
0x18002ee1a  jz      short loc_18002EE3F
0x18002ee1c  test    byte ptr [rcx+1Ch], 40h
0x18002ee20  jz      short loc_18002EE3F
0x18002ee22  mov     rcx, [rcx+10h]
0x18002ee26  mov     edx, 0Ah
0x18002ee2b  mov     [rsp+50h+var_30], r9
0x18002ee30  mov     r9, r8
0x18002ee33  lea     r8, WPP_aff4041d6f30374a6fbca409bd8c9069_Traceguids
0x18002ee3a  call    WPP_SF_SS
0x18002ee3f  mov     rdx, [rbp+arg_20]; unsigned __int16 *
0x18002ee43  test    rdx, rdx
0x18002ee46  jz      short loc_18002EE5A
0x18002ee48  mov     rcx, r14; this
0x18002ee4b  call    ?HrAssign@CUString@@QEAAJPEBG@Z; CUString::HrAssign(ushort const *)
0x18002ee50  mov     ebx, eax
0x18002ee52  test    eax, eax
0x18002ee54  js      loc_18002F076
0x18002ee5a  mov     rcx, rdi; psz
0x18002ee5d  call    cs:__imp_SysAllocString
0x18002ee63  mov     rcx, r13; psz
0x18002ee66  mov     r12, rax
0x18002ee69  call    cs:__imp_SysAllocString
0x18002ee6f  mov     rsi, rax
0x18002ee72  test    r12, r12
0x18002ee75  jz      short loc_18002EEE1
0x18002ee77  test    rax, rax
0x18002ee7a  jz      short loc_18002EEE1
0x18002ee7c  mov     rcx, [r15]
0x18002ee7f  lea     r9, [r14+8]
0x18002ee83  mov     r8, rsi
0x18002ee86  mov     rdx, [rcx]
0x18002ee89  mov     rax, [rdx+20h]
0x18002ee8d  mov     rdx, r12
0x18002ee90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ee95  mov     ebx, eax
0x18002ee97  cmp     eax, 800706BAh
0x18002ee9c  jz      short loc_18002EEAF
0x18002ee9e  cmp     eax, 80010108h
0x18002eea3  jz      short loc_18002EEAF
0x18002eea5  add     eax, 7FF8F942h
0x18002eeaa  cmp     eax, 1
0x18002eead  ja      short loc_18002EEEB
0x18002eeaf  mov     rcx, [r15]
0x18002eeb2  test    rcx, rcx
0x18002eeb5  jz      short loc_18002EED7
0x18002eeb7  mov     rax, [rcx]
0x18002eeba  lea     r8, ?pBogusInterface@@3PEAXEA; void * pBogusInterface
0x18002eec1  lea     rdx, bogusIID
0x18002eec8  mov     rax, [rax]
0x18002eecb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eed0  cmp     eax, 80004002h
0x18002eed5  jz      short loc_18002EEEB
0x18002eed7  mov     rcx, rdi; unsigned __int16 *
0x18002eeda  call    ?HrUnregisterDeviceByUDN@@YAJPEAG@Z; HrUnregisterDeviceByUDN(ushort *)
0x18002eedf  jmp     short loc_18002EEEB
0x18002eee1  mov     ebx, 8007000Eh
0x18002eee6  test    r12, r12
0x18002eee9  jz      short loc_18002EEF4
0x18002eeeb  mov     rcx, r12; bstrString
0x18002eeee  call    cs:__imp_SysFreeString
0x18002eef4  test    rsi, rsi
0x18002eef7  jz      short loc_18002EF02
0x18002eef9  mov     rcx, rsi; bstrString
0x18002eefc  call    cs:__imp_SysFreeString
0x18002ef02  test    ebx, ebx
0x18002ef04  js      loc_18002F06F
0x18002ef0a  mov     r12d, [rbp+arg_30]
0x18002ef0e  test    r12d, r12d
0x18002ef11  jz      short loc_18002EF2E
0x18002ef13  mov     rdx, [r15]; struct IUnknown *
0x18002ef16  lea     r15, [r14+8]
0x18002ef1a  mov     rcx, [r15]; struct IUnknown *
0x18002ef1d  call    ?HrCopyProxyIdentity@@YAJPEAUIUnknown@@0@Z; HrCopyProxyIdentity(IUnknown *,IUnknown *)
0x18002ef22  mov     ebx, eax
0x18002ef24  test    eax, eax
0x18002ef26  js      loc_18002F06F
0x18002ef2c  jmp     short loc_18002EF32
0x18002ef2e  lea     r15, [r14+8]
0x18002ef32  lea     rsi, [r14+10h]
0x18002ef36  mov     rcx, rsi; ppv
0x18002ef39  call    ?CoCreateInstance@?$CComPtrBase@UIUPnPEventingManager@@@ATL@@QEAAJAEBU_GUID@@PEAUIUnknown@@K@Z; ATL::CComPtrBase<IUPnPEventingManager>::CoCreateInstance(_GUID const &,IUnknown *,ulong)
0x18002ef3e  mov     ebx, eax
0x18002ef40  test    eax, eax
0x18002ef42  js      loc_18002F06F
0x18002ef48  lea     rcx, [r14+18h]; ppv
0x18002ef4c  call    ?CoCreateInstance@?$CComPtrBase@UIUPnPAutomationProxy@@@ATL@@QEAAJAEBU_GUID@@PEAUIUnknown@@K@Z; ATL::CComPtrBase<IUPnPAutomationProxy>::CoCreateInstance(_GUID const &,IUnknown *,ulong)
0x18002ef51  mov     ebx, eax
0x18002ef53  test    eax, eax
0x18002ef55  js      loc_18002F06F
0x18002ef5b  lea     rcx, [rbp+ppv]; void *
0x18002ef5f  call    ??0?$SmartComPtr@UIUPnPDescriptionManager@@@@QEAA@XZ; SmartComPtr<IUPnPDescriptionManager>::SmartComPtr<IUPnPDescriptionManager>(void)
0x18002ef64  lea     rcx, [rbp+ppv]; ppv
0x18002ef68  call    ?CoCreateInstance@?$CComPtrBase@UIUPnPRegistrarPrivate@@@ATL@@QEAAJAEBU_GUID@@PEAUIUnknown@@K@Z; ATL::CComPtrBase<IUPnPRegistrarPrivate>::CoCreateInstance(_GUID const &,IUnknown *,ulong)
0x18002ef6d  mov     ebx, eax
0x18002ef6f  test    eax, eax
0x18002ef71  js      loc_18002F066
0x18002ef77  mov     rcx, [rbp+ppv]
0x18002ef7b  lea     rdx, [rbp+var_10]
0x18002ef7f  mov     [rsp+50h+var_28], rdx
0x18002ef84  mov     r9, r13
0x18002ef87  mov     [rbp+pv], 0
0x18002ef8f  lea     rdx, [rbp+pv]
0x18002ef93  mov     [rbp+var_10], 0
0x18002ef9b  mov     r8, rdi
0x18002ef9e  mov     rax, [rcx]
0x18002efa1  mov     [rsp+50h+var_30], rdx
0x18002efa6  mov     rdx, [rbp+arg_8]
0x18002efaa  mov     rax, [rax+38h]
0x18002efae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002efb3  mov     ebx, eax
0x18002efb5  test    eax, eax
0x18002efb7  js      loc_18002F066
0x18002efbd  mov     rdx, [rbp+var_10]
0x18002efc1  mov     rcx, [r14+18h]
0x18002efc5  mov     r9, [rbp+pv]
0x18002efc9  mov     r8, [r15]
0x18002efcc  mov     dword ptr [rsp+50h+var_28], r12d
0x18002efd1  mov     rax, [rcx]
0x18002efd4  mov     [rsp+50h+var_30], rdx
0x18002efd9  mov     rdx, rdi
0x18002efdc  mov     rax, [rax+18h]
0x18002efe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002efe5  mov     ebx, eax
0x18002efe7  test    eax, eax
0x18002efe9  js      short loc_18002F052
0x18002efeb  mov     rdx, [r15]
0x18002efee  mov     r8, r13
0x18002eff1  mov     rcx, [rsi]
0x18002eff4  mov     r9, [r14+18h]
0x18002eff8  mov     dword ptr [rsp+50h+var_28], r12d
0x18002effd  mov     [rsp+50h+var_30], rdx
0x18002f002  mov     rdx, rdi
0x18002f005  mov     rax, [rcx]
0x18002f008  mov     rax, [rax+18h]
0x18002f00c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f011  mov     ebx, eax
0x18002f013  cmp     eax, 80004002h
0x18002f018  jnz     short loc_18002F052
0x18002f01a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f021  lea     rax, WPP_GLOBAL_Control
0x18002f028  cmp     rcx, rax
0x18002f02b  jz      short loc_18002F048
0x18002f02d  test    byte ptr [rcx+1Ch], 40h
0x18002f031  jz      short loc_18002F048
0x18002f033  mov     rcx, [rcx+10h]
0x18002f037  lea     r8, WPP_aff4041d6f30374a6fbca409bd8c9069_Traceguids
0x18002f03e  mov     edx, 0Bh
0x18002f043  call    WPP_SF_
0x18002f048  mov     rcx, rsi
0x18002f04b  call    ?Release@?$CComPtrBase@UIUPnPDynamicContentSource@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IUPnPDynamicContentSource>::Release(void)
0x18002f050  xor     ebx, ebx
0x18002f052  mov     rcx, [rbp+pv]; pv
0x18002f056  call    cs:__imp_CoTaskMemFree
0x18002f05c  mov     rcx, [rbp+var_10]; pv
0x18002f060  call    cs:__imp_CoTaskMemFree
0x18002f066  lea     rcx, [rbp+ppv]
0x18002f06a  call    ??1?$CComPtr@UIUPnPDescriptionManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IUPnPDescriptionManager>::~CComPtr<IUPnPDescriptionManager>(void)
0x18002f06f  lea     rsi, WPP_GLOBAL_Control
0x18002f076  test    ebx, ebx
0x18002f078  jz      short loc_18002F0A4
0x18002f07a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f081  cmp     rcx, rsi
0x18002f084  jz      short loc_18002F0A4
0x18002f086  test    byte ptr [rcx+1Ch], 1
0x18002f08a  jz      short loc_18002F0A4
0x18002f08c  mov     rcx, [rcx+10h]
0x18002f090  lea     r8, WPP_aff4041d6f30374a6fbca409bd8c9069_Traceguids
0x18002f097  mov     edx, 0Ch
0x18002f09c  mov     r9d, ebx
0x18002f09f  call    WPP_SF_d
0x18002f0a4  mov     eax, ebx
0x18002f0a6  jmp     short loc_18002F0AD
0x18002f0a8  mov     eax, 80004003h
0x18002f0ad  mov     rbx, [rsp+50h+arg_0]
0x18002f0b5  add     rsp, 50h
0x18002f0b9  pop     r15
0x18002f0bb  pop     r14
0x18002f0bd  pop     r13
0x18002f0bf  pop     r12
0x18002f0c1  pop     rdi
0x18002f0c2  pop     rsi
0x18002f0c3  pop     rbp
0x18002f0c4  retn
```
