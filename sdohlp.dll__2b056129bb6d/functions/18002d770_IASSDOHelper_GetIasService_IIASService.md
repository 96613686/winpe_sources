# IASSDOHelper::GetIasService(IIASService * *)

- ea: `0x18002d770`
- end: `0x18002da6e`
- name: `?GetIasService@IASSDOHelper@@UEAAJPEAPEAUIIASService@@@Z`
- size: `766`
- prototype: `__int64 __fastcall(IASSDOHelper *__hidden this, struct IIASService **)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x180024cac`
- `0x180027584`
- `0x18002cd00`
- `0x18002d08c`
- `0x18002d278`
- `0x18002d770`
- `0x18002ee50`
- `0x18002efa0`
- `0x18002f904`
- `0x18003d7ac`
- `0x180042a80`
- `0x180058010`

## string_xrefs

- `0x18002d90c`: `m_pMachine->GetServiceSDO failed with %!hresult!`
- `0x18002d9e1`: `pService->Initialize failed with %!hresult!`
- `0x18002da2a`: `Failed to initialize exim component: %!hresult!`

## pseudocode

```c
__int64 __fastcall IASSDOHelper::GetIasService(IASSDOHelper *this, struct IIASService **a2)
{
  struct IIASService *v2; // rsi
  int v5; // ebx
  int v6; // edx
  __int64 v7; // rbx
  __int64 (__fastcall *v8)(__int64, _QWORD, _QWORD *, __int64 (__fastcall ****)(_QWORD, GUID *, char *)); // r15
  _QWORD *v9; // r8
  struct IUnknown *v10; // rbx
  __int64 (__fastcall ***v12)(_QWORD, GUID *, char *); // [rsp+78h] [rbp+48h] BYREF
  struct IUnknown *v13; // [rsp+80h] [rbp+50h] BYREF
  struct IUnknown *v14; // [rsp+88h] [rbp+58h] BYREF

  v2 = 0;
  v12 = 0;
  v13 = 0;
  if ( !a2 )
  {
    v5 = -2147467261;
    goto LABEL_37;
  }
  v5 = (*(__int64 (__fastcall **)(_QWORD, __int64 (__fastcall ****)(_QWORD, GUID *, char *)))(**((_QWORD **)this + 9)
                                                                                            + 64LL))(
         *((_QWORD *)this + 9),
         &v12);
  if ( v5 >= 0 )
  {
    v5 = (**v12)(v12, &GUID_d432e5f4_53d8_11d2_9a3a_00c04fb998ac, (char *)this + 104);
    if ( v5 >= 0 )
    {
      ATL::CComPtrBase<IIASItem>::Release(&v12);
      v7 = *((_QWORD *)this + 9);
      v8 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *, __int64 (__fastcall ****)(_QWORD, GUID *, char *)))(*(_QWORD *)v7 + 72LL);
      v9 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)&v14, L"IAS");
      if ( v9 )
        v9 = (_QWORD *)*v9;
      v5 = v8(v7, 0, v9, &v12);
      _bstr_t::_Free((_bstr_t *)&v14);
      if ( v5 >= 0 )
      {
        v5 = (**v12)(v12, &IID_ISdoServiceControl, (char *)this + 112);
        if ( v5 >= 0 )
        {
          v5 = (**v12)(v12, &IID_ISdo, (char *)this + 88);
          if ( v5 >= 0 )
          {
            v14 = 0;
            v5 = ATL::CComObject<IASService>::CreateInstance(&v14);
            if ( v5 >= 0 )
            {
              v10 = v14;
              if ( v14 )
              {
                ATL::AtlComPtrAssign(&v13, v14);
                v2 = (struct IIASService *)v13;
              }
              v5 = IASItem::Initialize(
                     (IASItem *)&v10[2],
                     *((struct ISdo **)this + 11),
                     *((struct ISdo **)this + 11),
                     *((struct ISdoMachine **)this + 9),
                     *((struct ISdoDictionaryOld **)this + 13));
              if ( v5 >= 0 )
              {
                v5 = IASExim::Initialize((LPVOID *)this + 15);
                if ( v5 >= 0 )
                {
                  v13 = 0;
                  *a2 = v2;
                  goto LABEL_37;
                }
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
                  && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
                {
                  WppDbgPrint("Failed to initialize exim component: %!hresult!");
                  v6 = 20;
                  goto LABEL_8;
                }
              }
              else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                     && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
                     && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
              {
                WppDbgPrint("pService->Initialize failed with %!hresult!");
                v6 = 19;
                goto LABEL_8;
              }
            }
          }
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
             && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        WppDbgPrint("m_pMachine->GetServiceSDO failed with %!hresult!");
        v6 = 18;
        goto LABEL_8;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
           && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("QI(ISdoDictionaryOld) failed with %!hresult!");
      v6 = 17;
      goto LABEL_8;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WppDbgPrint("m_pMachine->GetDictionarySDO failed with %!hresult!");
    v6 = 16;
LABEL_8:
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v6,
      (unsigned int)WPP_b2e5ba8d027733d341583b07c20330d3_Traceguids,
      (unsigned int)"NPSSDO",
      v5);
  }
LABEL_37:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v13);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v12);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002d770  push    rbp
0x18002d772  push    rbx
0x18002d773  push    rsi
0x18002d774  push    rdi
0x18002d775  push    r12
0x18002d777  push    r14
0x18002d779  push    r15
0x18002d77b  mov     rbp, rsp
0x18002d77e  sub     rsp, 30h
0x18002d782  xor     esi, esi
0x18002d784  mov     [rbp+arg_8], 0
0x18002d78c  mov     [rbp+arg_10], rsi
0x18002d790  mov     r14, rdx
0x18002d793  mov     rdi, rcx
0x18002d796  test    rdx, rdx
0x18002d799  jnz     short loc_18002D7A5
0x18002d79b  mov     ebx, 80004003h
0x18002d7a0  jmp     loc_18002DA4B
0x18002d7a5  mov     rcx, [rcx+48h]
0x18002d7a9  lea     rdx, [rbp+arg_8]
0x18002d7ad  mov     rax, [rcx]
0x18002d7b0  mov     rax, [rax+40h]
0x18002d7b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d7b9  mov     ebx, eax
0x18002d7bb  test    eax, eax
0x18002d7bd  jns     short loc_18002D827
0x18002d7bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d7c6  lea     rax, WPP_GLOBAL_Control
0x18002d7cd  cmp     rcx, rax
0x18002d7d0  jz      loc_18002DA4B
0x18002d7d6  cmp     byte ptr [rcx+19h], 2
0x18002d7da  jb      loc_18002DA4B
0x18002d7e0  test    dword ptr [rcx+1Ch], 400h
0x18002d7e7  jz      loc_18002DA4B
0x18002d7ed  mov     edx, ebx
0x18002d7ef  lea     rcx, aMPmachineGetdi; "m_pMachine->GetDictionarySDO failed wit"...
0x18002d7f6  call    WppDbgPrint
0x18002d7fb  mov     edx, 10h
0x18002d800  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d807  lea     r9, aNpssdo; "NPSSDO"
0x18002d80e  lea     r8, WPP_b2e5ba8d027733d341583b07c20330d3_Traceguids
0x18002d815  mov     dword ptr [rsp+30h+var_10], ebx
0x18002d819  mov     rcx, [rcx+10h]
0x18002d81d  call    WPP_SF_sd
0x18002d822  jmp     loc_18002DA4B
0x18002d827  mov     rcx, [rbp+arg_8]
0x18002d82b  lea     r8, [rdi+68h]
0x18002d82f  lea     rdx, _GUID_d432e5f4_53d8_11d2_9a3a_00c04fb998ac
0x18002d836  mov     rax, [rcx]
0x18002d839  mov     rax, [rax]
0x18002d83c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d841  mov     ebx, eax
0x18002d843  test    eax, eax
0x18002d845  jns     short loc_18002D88D
0x18002d847  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d84e  lea     rax, WPP_GLOBAL_Control
0x18002d855  cmp     rcx, rax
0x18002d858  jz      loc_18002DA4B
0x18002d85e  cmp     byte ptr [rcx+19h], 2
0x18002d862  jb      loc_18002DA4B
0x18002d868  test    dword ptr [rcx+1Ch], 400h
0x18002d86f  jz      loc_18002DA4B
0x18002d875  mov     edx, ebx
0x18002d877  lea     rcx, aQiIsdodictiona; "QI(ISdoDictionaryOld) failed with %!hre"...
0x18002d87e  call    WppDbgPrint
0x18002d883  mov     edx, 11h
0x18002d888  jmp     loc_18002D800
0x18002d88d  lea     rcx, [rbp+arg_8]
0x18002d891  call    ?Release@?$CComPtrBase@UIIASItem@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IIASItem>::Release(void)
0x18002d896  mov     rbx, [rdi+48h]
0x18002d89a  lea     rdx, aIas; "IAS"
0x18002d8a1  lea     rcx, [rbp+arg_18]; this
0x18002d8a5  mov     rax, [rbx]
0x18002d8a8  mov     r15, [rax+48h]
0x18002d8ac  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18002d8b1  mov     r8, [rax]
0x18002d8b4  test    r8, r8
0x18002d8b7  jz      short loc_18002D8BC
0x18002d8b9  mov     r8, [r8]
0x18002d8bc  lea     r9, [rbp+arg_8]
0x18002d8c0  xor     edx, edx
0x18002d8c2  mov     rcx, rbx
0x18002d8c5  mov     rax, r15
0x18002d8c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d8cd  lea     rcx, [rbp+arg_18]; this
0x18002d8d1  mov     ebx, eax
0x18002d8d3  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18002d8d8  test    ebx, ebx
0x18002d8da  jns     short loc_18002D922
0x18002d8dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d8e3  lea     rax, WPP_GLOBAL_Control
0x18002d8ea  cmp     rcx, rax
0x18002d8ed  jz      loc_18002DA4B
0x18002d8f3  cmp     byte ptr [rcx+19h], 2
0x18002d8f7  jb      loc_18002DA4B
0x18002d8fd  test    dword ptr [rcx+1Ch], 400h
0x18002d904  jz      loc_18002DA4B
0x18002d90a  mov     edx, ebx
0x18002d90c  lea     rcx, aMPmachineGetse; "m_pMachine->GetServiceSDO failed with %"...
0x18002d913  call    WppDbgPrint
0x18002d918  mov     edx, 12h
0x18002d91d  jmp     loc_18002D800
0x18002d922  mov     rcx, [rbp+arg_8]
0x18002d926  lea     r8, [rdi+70h]
0x18002d92a  lea     rdx, IID_ISdoServiceControl
0x18002d931  mov     rax, [rcx]
0x18002d934  mov     rax, [rax]
0x18002d937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d93c  mov     ebx, eax
0x18002d93e  test    eax, eax
0x18002d940  js      loc_18002DA4B
0x18002d946  mov     rcx, [rbp+arg_8]
0x18002d94a  lea     r8, [rdi+58h]
0x18002d94e  lea     rdx, IID_ISdo
0x18002d955  mov     rax, [rcx]
0x18002d958  mov     rax, [rax]
0x18002d95b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d960  mov     ebx, eax
0x18002d962  test    eax, eax
0x18002d964  js      loc_18002DA4B
0x18002d96a  lea     rcx, [rbp+arg_18]
0x18002d96e  mov     [rbp+arg_18], rsi
0x18002d972  call    ?CreateInstance@?$CComObject@VIASService@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<IASService>::CreateInstance(ATL::CComObject<IASService> * *)
0x18002d977  mov     ebx, eax
0x18002d979  test    eax, eax
0x18002d97b  js      loc_18002DA4B
0x18002d981  mov     rbx, [rbp+arg_18]
0x18002d985  test    rbx, rbx
0x18002d988  jz      short loc_18002D99A
0x18002d98a  mov     rdx, rbx; struct IUnknown *
0x18002d98d  lea     rcx, [rbp+arg_10]; struct IUnknown **
0x18002d991  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18002d996  mov     rsi, [rbp+arg_10]
0x18002d99a  mov     r8, [rdi+58h]; struct ISdo *
0x18002d99e  lea     rcx, [rbx+10h]; this
0x18002d9a2  mov     rax, [rdi+68h]
0x18002d9a6  mov     rdx, r8; struct ISdo *
0x18002d9a9  mov     r9, [rdi+48h]; struct ISdoMachine *
0x18002d9ad  mov     [rsp+30h+var_10], rax; struct ISdoDictionaryOld *
0x18002d9b2  call    ?Initialize@IASItem@@QEAAJPEAUISdo@@0PEAUISdoMachine@@PEAUISdoDictionaryOld@@@Z; IASItem::Initialize(ISdo *,ISdo *,ISdoMachine *,ISdoDictionaryOld *)
0x18002d9b7  mov     ebx, eax
0x18002d9b9  test    eax, eax
0x18002d9bb  jns     short loc_18002D9F7
0x18002d9bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d9c4  lea     rax, WPP_GLOBAL_Control
0x18002d9cb  cmp     rcx, rax
0x18002d9ce  jz      short loc_18002DA4B
0x18002d9d0  cmp     byte ptr [rcx+19h], 2
0x18002d9d4  jb      short loc_18002DA4B
0x18002d9d6  test    dword ptr [rcx+1Ch], 400h
0x18002d9dd  jz      short loc_18002DA4B
0x18002d9df  mov     edx, ebx
0x18002d9e1  lea     rcx, aPserviceInitia; "pService->Initialize failed with %!hres"...
0x18002d9e8  call    WppDbgPrint
0x18002d9ed  mov     edx, 13h
0x18002d9f2  jmp     loc_18002D800
0x18002d9f7  lea     rcx, [rdi+78h]; ppv
0x18002d9fb  call    ?Initialize@IASExim@@QEAAJXZ; IASExim::Initialize(void)
0x18002da00  mov     ebx, eax
0x18002da02  test    eax, eax
0x18002da04  jns     short loc_18002DA40
0x18002da06  mov     rcx, cs:WPP_GLOBAL_Control
0x18002da0d  lea     rax, WPP_GLOBAL_Control
0x18002da14  cmp     rcx, rax
0x18002da17  jz      short loc_18002DA4B
0x18002da19  cmp     byte ptr [rcx+19h], 2
0x18002da1d  jb      short loc_18002DA4B
0x18002da1f  test    dword ptr [rcx+1Ch], 400h
0x18002da26  jz      short loc_18002DA4B
0x18002da28  mov     edx, ebx
0x18002da2a  lea     rcx, aFailedToInitia; "Failed to initialize exim component: %!"...
0x18002da31  call    WppDbgPrint
0x18002da36  mov     edx, 14h
0x18002da3b  jmp     loc_18002D800
0x18002da40  mov     [rbp+arg_10], 0
0x18002da48  mov     [r14], rsi
0x18002da4b  lea     rcx, [rbp+arg_10]
0x18002da4f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002da54  lea     rcx, [rbp+arg_8]
0x18002da58  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002da5d  mov     eax, ebx
0x18002da5f  add     rsp, 30h
0x18002da63  pop     r15
0x18002da65  pop     r14
0x18002da67  pop     r12
0x18002da69  pop     rdi
0x18002da6a  pop     rsi
0x18002da6b  pop     rbx
0x18002da6c  pop     rbp
0x18002da6d  retn
```
