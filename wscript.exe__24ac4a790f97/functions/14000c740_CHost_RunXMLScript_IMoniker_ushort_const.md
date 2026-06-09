# CHost::RunXMLScript(IMoniker *,ushort const *)

- ea: `0x14000c740`
- end: `0x14000ccc3`
- name: `?RunXMLScript@CHost@@IEAAJPEAUIMoniker@@PEBG@Z`
- size: `1411`
- prototype: `__int64 __fastcall(CHost *__hidden this, struct IMoniker *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000757c`

## callees

- `0x140001008`
- `0x14000c740`
- `0x14000cf0c`
- `0x14000e534`
- `0x14000e578`
- `0x1400175a0`
- `0x140018010`

## import_xrefs

- `KERNEL32!GetUserDefaultLCID` at `0x14000c838`
- `KERNEL32!GetUserDefaultLCID` at `0x14000c838`
- `ole32!CoGetClassObject` at `0x14000c92c`
- `ole32!CoGetClassObject` at `0x14000c92c`
- `ole32!CreateBindCtx` at `0x14000ca90`
- `ole32!CreateBindCtx` at `0x14000ca90`
- `ole32!CoCreateInstance` at `0x14000c7fc`
- `ole32!CoCreateInstance` at `0x14000c81f`
- `ole32!CoCreateInstance` at `0x14000c7fc`
- `ole32!CoCreateInstance` at `0x14000c81f`

## pseudocode

```c
__int64 __fastcall CHost::RunXMLScript(CHost *this, struct IMoniker *a2, const unsigned __int16 *a3)
{
  LPVOID *ppv; // rsi
  __int64 v5; // rcx
  _DWORD *v6; // r12
  _DWORD *v7; // r13
  _QWORD *v8; // r15
  __int64 v9; // rcx
  HRESULT ClassObject; // ebx
  LCID UserDefaultLCID; // eax
  LPVOID v12; // rcx
  LPVOID v13; // rbx
  _DWORD *v14; // rax
  _DWORD *v15; // r14
  LPVOID v16; // rbx
  _DWORD *v17; // rax
  int v18; // eax
  unsigned int v19; // r8d
  __int64 v20; // rdx
  int v21; // eax
  int Error; // eax
  LPVOID v23; // r8
  const unsigned __int16 *v24; // rsi
  int v25; // eax
  __int64 v27; // [rsp+40h] [rbp-49h] BYREF
  LPBC ppbc; // [rsp+48h] [rbp-41h] BYREF
  __int64 v29; // [rsp+50h] [rbp-39h] BYREF
  __int64 v30; // [rsp+58h] [rbp-31h] BYREF
  LPVOID v31; // [rsp+60h] [rbp-29h] BYREF
  __int64 v32; // [rsp+68h] [rbp-21h] BYREF
  struct IMoniker *v33; // [rsp+70h] [rbp-19h]
  const unsigned __int16 *v34; // [rsp+78h] [rbp-11h]
  __int128 v35; // [rsp+80h] [rbp-9h] BYREF
  __int64 v36; // [rsp+90h] [rbp+7h]
  __int128 v37; // [rsp+98h] [rbp+Fh] BYREF

  v34 = a3;
  v33 = a2;
  ppv = (LPVOID *)((char *)this + 680);
  v36 = 0;
  v27 = 0;
  v5 = *((_QWORD *)this + 85);
  v29 = 0;
  v31 = 0;
  v6 = 0;
  v32 = 0;
  v7 = 0;
  v30 = 0;
  ppbc = 0;
  v37 = 0;
  v35 = 0;
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    *ppv = 0;
  }
  v8 = (_QWORD *)((char *)this + 32);
  v9 = *((_QWORD *)this + 4);
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    *v8 = 0;
  }
  if ( CoCreateInstance(&CLSID_ScriptletContext2, 0, 1u, &IID_IScriptletContext, ppv) >= 0
    || (ClassObject = CoCreateInstance(&CLSID_ScriptletContext, 0, 1u, &IID_IScriptletContext, ppv), ClassObject >= 0) )
  {
    LOWORD(v35) = 3;
    UserDefaultLCID = GetUserDefaultLCID();
    v12 = *ppv;
    DWORD2(v35) = UserDefaultLCID;
    ClassObject = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, __int128 *))(*(_QWORD *)v12 + 56LL))(
                    v12,
                    1,
                    0,
                    &v35);
    if ( ClassObject >= 0 )
    {
      v13 = *ppv;
      v14 = operator new(0x18u);
      v15 = v14;
      if ( v14
        && (v14[4] = 1,
            *(_QWORD *)v14 = &XMLScrServProv::`vftable',
            *((_QWORD *)v14 + 1) = v13,
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v13 + 8LL))(v13),
            v16 = *ppv,
            v6 = v15,
            (v17 = operator new(0x38u)) != 0) )
      {
        v17[12] = 0;
        *(_QWORD *)v17 = &XMLScrSite::`vftable'{for `IScriptletSite'};
        v7 = v17;
        v17[6] = 1;
        *((_QWORD *)v17 + 1) = &XMLScrSite::`vftable'{for `IScriptletSitePoll'};
        *((_QWORD *)v17 + 2) = &XMLScrSite::`vftable'{for `IScriptletSiteWSH'};
        *((_QWORD *)v17 + 4) = this;
        *((_QWORD *)v17 + 5) = v16;
        ClassObject = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)*ppv + 24LL))(*ppv);
        if ( ClassObject >= 0 )
        {
          ClassObject = CoGetClassObject(&CLSID_ScriptletConstructor, 1u, 0, &IID_IClassFactory3, &v31);
          if ( ClassObject >= 0 )
          {
            ClassObject = (*(__int64 (__fastcall **)(LPVOID, _DWORD *, _QWORD, GUID *, __int64 *))(*(_QWORD *)v31 + 40LL))(
                            v31,
                            v15,
                            0,
                            &IID_IScriptletConstructor,
                            &v27);
            if ( ClassObject >= 0 )
            {
              v18 = (*((_BYTE *)this + 71) != 0 ? 34 : 2) | 0x40;
              if ( !*((_DWORD *)this + 19) )
                v18 = *((_BYTE *)this + 71) != 0 ? 34 : 2;
              if ( *((_DWORD *)this + 19) != 1 || *((_BYTE *)this + 68) )
                v18 |= 0x80u;
              v19 = v18 | 0x100;
              if ( !*((_BYTE *)this + 74) )
                v19 = v18;
              v20 = v19;
              LODWORD(v20) = v19 | 0x200;
              if ( !*((_BYTE *)this + 75) )
                v20 = v19;
              ClassObject = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v27 + 24LL))(v27, v20);
              if ( ClassObject >= 0 )
              {
                ClassObject = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v27)(
                                v27,
                                &IID_IScriptletConstructorWSH,
                                &v29);
                if ( ClassObject >= 0 )
                {
                  ClassObject = (**(__int64 (__fastcall ***)(__int64, __int64 *, char *))v27)(
                                  v27,
                                  qword_14001C0D0,
                                  (char *)this + 32);
                  if ( ClassObject >= 0 )
                  {
                    ClassObject = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64))(*(_QWORD *)v29 + 24LL))(
                                    v29,
                                    L"WScript",
                                    2);
                    if ( ClassObject >= 0 )
                    {
                      ClassObject = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64))(*(_QWORD *)v29 + 24LL))(
                                      v29,
                                      L"WSH",
                                      2);
                      if ( ClassObject >= 0 )
                      {
                        ClassObject = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v27)(
                                        v27,
                                        &IID_IPersistMoniker,
                                        &v30);
                        if ( ClassObject >= 0 )
                        {
                          ClassObject = CreateBindCtx(0, &ppbc);
                          if ( ClassObject >= 0 )
                          {
                            v37 = 0x10u;
                            ClassObject = ((__int64 (__fastcall *)(LPBC, __int128 *))ppbc->lpVtbl->SetBindOptions)(
                                            ppbc,
                                            &v37);
                            if ( ClassObject >= 0 )
                            {
                              v21 = (*(__int64 (__fastcall **)(__int64, __int64, struct IMoniker *, LPBC, _DWORD))(*(_QWORD *)v30 + 40LL))(
                                      v30,
                                      1,
                                      v33,
                                      ppbc,
                                      0);
                              ClassObject = v21;
                              if ( v21 >= 0 )
                              {
                                if ( !*((_BYTE *)this + 69)
                                  || (ClassObject = CTimer::Start(*((CTimer **)this + 81), *((_DWORD *)this + 11)),
                                      ClassObject >= 0) )
                                {
                                  v23 = *ppv;
                                  v24 = v34;
                                  v25 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, LPVOID, _QWORD, GUID *, __int64 *))(*(_QWORD *)v27 + 32LL))(
                                          v27,
                                          v34,
                                          v23,
                                          0,
                                          &IID_IUnknown,
                                          &v32);
                                  ClassObject = v25;
                                  if ( v25 >= 0 )
                                  {
                                    ClassObject = 0;
                                    goto LABEL_44;
                                  }
                                  if ( v25 == -2147024809 )
                                  {
                                    Error = (*(__int64 (__fastcall **)(CHost *, _QWORD, __int64, const unsigned __int16 *, const OLECHAR *))(*(_QWORD *)this + 8LL))(
                                              this,
                                              (unsigned int)(Global::g_lResourceBase + 21),
                                              3319,
                                              v24,
                                              &Default);
LABEL_38:
                                    ClassObject = Error;
                                    if ( Error >= 0 )
                                      goto LABEL_44;
                                  }
                                }
                              }
                              else if ( v21 != -2147352319 )
                              {
                                Error = CHost::ReportLoadError(this, -2147024894);
                                goto LABEL_38;
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
      else
      {
        ClassObject = -2147024882;
      }
    }
  }
  if ( *v8 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v8 + 16LL))(*v8);
    *v8 = 0;
  }
LABEL_44:
  if ( ppbc )
    ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
  if ( v30 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  if ( v32 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  if ( v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  if ( v6 )
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v6 + 16LL))(v6);
  if ( v7 )
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v7 + 16LL))(v7);
  if ( v31 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v31 + 16LL))(v31);
  CTimer::Stop(*((CTimer **)this + 81));
  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 10, 0, 0) == -2147155970 )
    (*(void (__fastcall **)(CHost *))(*(_QWORD *)this + 64LL))(this);
  return (unsigned int)ClassObject;
}

```

## disassembly

```asm
0x14000c740  mov     [rsp-8+arg_18], rbx
0x14000c745  push    rbp
0x14000c746  push    rsi
0x14000c747  push    rdi
0x14000c748  push    r12
0x14000c74a  push    r13
0x14000c74c  push    r14
0x14000c74e  push    r15
0x14000c750  lea     rbp, [rsp-27h]
0x14000c755  sub     rsp, 0B0h
0x14000c75c  mov     rax, cs:__security_cookie
0x14000c763  xor     rax, rsp
0x14000c766  mov     [rbp+57h+var_38], rax
0x14000c76a  xor     r14d, r14d
0x14000c76d  mov     [rbp+57h+var_68], r8
0x14000c771  xor     eax, eax
0x14000c773  mov     [rbp+57h+var_70], rdx
0x14000c777  lea     rsi, [rcx+2A8h]
0x14000c77e  mov     [rbp+57h+var_50], rax
0x14000c782  mov     rdi, rcx
0x14000c785  mov     [rbp+57h+var_A0], r14
0x14000c789  mov     rcx, [rsi]
0x14000c78c  xorps   xmm0, xmm0
0x14000c78f  mov     [rbp+57h+var_90], r14
0x14000c793  xorps   xmm1, xmm1
0x14000c796  mov     [rbp+57h+var_80], r14
0x14000c79a  mov     r12d, r14d
0x14000c79d  mov     [rbp+57h+var_78], r14
0x14000c7a1  mov     r13d, r14d
0x14000c7a4  mov     [rbp+57h+var_88], r14
0x14000c7a8  mov     [rbp+57h+ppbc], r14
0x14000c7ac  movups  [rbp+57h+var_48], xmm0
0x14000c7b0  movups  [rbp+57h+var_60], xmm1
0x14000c7b4  test    rcx, rcx
0x14000c7b7  jz      short loc_14000C7C8
0x14000c7b9  mov     rax, [rcx]
0x14000c7bc  mov     rax, [rax+10h]
0x14000c7c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c7c5  mov     [rsi], r14
0x14000c7c8  lea     r15, [rdi+20h]
0x14000c7cc  mov     rcx, [r15]
0x14000c7cf  test    rcx, rcx
0x14000c7d2  jz      short loc_14000C7E3
0x14000c7d4  mov     rax, [rcx]
0x14000c7d7  mov     rax, [rax+10h]
0x14000c7db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c7e0  mov     [r15], r14
0x14000c7e3  xor     edx, edx; pUnkOuter
0x14000c7e5  mov     [rsp+0E0h+ppv], rsi; ppv
0x14000c7ea  lea     r9, IID_IScriptletContext; riid
0x14000c7f1  lea     rcx, CLSID_ScriptletContext2; rclsid
0x14000c7f8  lea     r8d, [rdx+1]; dwClsContext
0x14000c7fc  call    cs:__imp_CoCreateInstance
0x14000c802  test    eax, eax
0x14000c804  jns     short loc_14000C82F
0x14000c806  xor     edx, edx; pUnkOuter
0x14000c808  mov     [rsp+0E0h+ppv], rsi; ppv
0x14000c80d  lea     r9, IID_IScriptletContext; riid
0x14000c814  lea     rcx, CLSID_ScriptletContext; rclsid
0x14000c81b  lea     r8d, [rdx+1]; dwClsContext
0x14000c81f  call    cs:__imp_CoCreateInstance
0x14000c825  mov     ebx, eax
0x14000c827  test    eax, eax
0x14000c829  js      loc_14000CBAF
0x14000c82f  mov     eax, 3
0x14000c834  mov     word ptr [rbp+57h+var_60], ax
0x14000c838  call    cs:__imp_GetUserDefaultLCID
0x14000c83e  mov     rcx, [rsi]
0x14000c841  lea     r9, [rbp+57h+var_60]
0x14000c845  mov     dword ptr [rbp+57h+var_60+8], eax
0x14000c848  xor     r8d, r8d
0x14000c84b  mov     rax, [rcx]
0x14000c84e  lea     edx, [r8+1]
0x14000c852  mov     rax, [rax+38h]
0x14000c856  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c85b  mov     ebx, eax
0x14000c85d  test    eax, eax
0x14000c85f  js      loc_14000CBAF
0x14000c865  mov     rbx, [rsi]
0x14000c868  mov     ecx, 18h; Size
0x14000c86d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000c872  mov     r14, rax
0x14000c875  test    rax, rax
0x14000c878  jz      loc_14000CBA7
0x14000c87e  mov     dword ptr [r14+10h], 1
0x14000c886  lea     rax, ??_7XMLScrServProv@@6B@; const XMLScrServProv::`vftable'
0x14000c88d  mov     [r14], rax
0x14000c890  mov     [r14+8], rbx
0x14000c894  mov     rcx, [rbx]
0x14000c897  mov     rax, [rcx+8]
0x14000c89b  mov     rcx, rbx
0x14000c89e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c8a3  mov     rbx, [rsi]
0x14000c8a6  mov     ecx, 38h ; '8'; Size
0x14000c8ab  mov     r12, r14
0x14000c8ae  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000c8b3  mov     rdx, rax
0x14000c8b6  test    rax, rax
0x14000c8b9  jz      loc_14000CBA7
0x14000c8bf  mov     [rdx+30h], r13d
0x14000c8c3  lea     rax, ??_7XMLScrSite@@6BIScriptletSite@@@; const XMLScrSite::`vftable'{for `IScriptletSite'}
0x14000c8ca  mov     [rdx], rax
0x14000c8cd  mov     r13, rdx
0x14000c8d0  lea     rax, ??_7XMLScrSite@@6BIScriptletSitePoll@@@; const XMLScrSite::`vftable'{for `IScriptletSitePoll'}
0x14000c8d7  mov     dword ptr [rdx+18h], 1
0x14000c8de  mov     [rdx+8], rax
0x14000c8e2  lea     rax, ??_7XMLScrSite@@6BIScriptletSiteWSH@@@; const XMLScrSite::`vftable'{for `IScriptletSiteWSH'}
0x14000c8e9  mov     [rdx+10h], rax
0x14000c8ed  mov     [rdx+20h], rdi
0x14000c8f1  mov     [rdx+28h], rbx
0x14000c8f5  mov     rcx, [rsi]
0x14000c8f8  mov     rax, [rcx]
0x14000c8fb  mov     rax, [rax+18h]
0x14000c8ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c904  mov     ebx, eax
0x14000c906  test    eax, eax
0x14000c908  js      loc_14000CBAC
0x14000c90e  xor     r8d, r8d; pvReserved
0x14000c911  lea     rax, [rbp+57h+var_80]
0x14000c915  lea     r9, IID_IClassFactory3; riid
0x14000c91c  mov     [rsp+0E0h+ppv], rax; ppv
0x14000c921  lea     rcx, CLSID_ScriptletConstructor; rclsid
0x14000c928  lea     edx, [r8+1]; dwClsContext
0x14000c92c  call    cs:__imp_CoGetClassObject
0x14000c932  mov     ebx, eax
0x14000c934  test    eax, eax
0x14000c936  js      loc_14000CBAC
0x14000c93c  mov     rcx, [rbp+57h+var_80]
0x14000c940  lea     rdx, [rbp+57h+var_A0]
0x14000c944  mov     [rsp+0E0h+ppv], rdx
0x14000c949  lea     r9, IID_IScriptletConstructor
0x14000c950  xor     r8d, r8d
0x14000c953  mov     rdx, r14
0x14000c956  mov     rax, [rcx]
0x14000c959  mov     rax, [rax+28h]
0x14000c95d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c962  xor     r14d, r14d
0x14000c965  mov     ebx, eax
0x14000c967  test    eax, eax
0x14000c969  js      loc_14000CBAF
0x14000c96f  mov     al, [rdi+47h]
0x14000c972  neg     al
0x14000c974  sbb     ecx, ecx
0x14000c976  and     ecx, 20h
0x14000c979  add     ecx, 2
0x14000c97c  mov     eax, ecx
0x14000c97e  or      eax, 40h
0x14000c981  cmp     [rdi+4Ch], r14d
0x14000c985  cmovz   eax, ecx
0x14000c988  cmp     dword ptr [rdi+4Ch], 1
0x14000c98c  jnz     short loc_14000C994
0x14000c98e  cmp     [rdi+44h], r14b
0x14000c992  jz      short loc_14000C998
0x14000c994  bts     eax, 7
0x14000c998  mov     rcx, [rbp+57h+var_A0]
0x14000c99c  mov     r8d, eax
0x14000c99f  bts     r8d, 8
0x14000c9a4  cmp     [rdi+4Ah], r14b
0x14000c9a8  cmovz   r8d, eax
0x14000c9ac  mov     rax, [rcx]
0x14000c9af  mov     edx, r8d
0x14000c9b2  bts     edx, 9
0x14000c9b6  cmp     [rdi+4Bh], r14b
0x14000c9ba  mov     rax, [rax+18h]
0x14000c9be  cmovz   edx, r8d
0x14000c9c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c9c7  mov     ebx, eax
0x14000c9c9  test    eax, eax
0x14000c9cb  js      loc_14000CBAF
0x14000c9d1  mov     rcx, [rbp+57h+var_A0]
0x14000c9d5  lea     r8, [rbp+57h+var_90]
0x14000c9d9  lea     rdx, IID_IScriptletConstructorWSH
0x14000c9e0  mov     rax, [rcx]
0x14000c9e3  mov     rax, [rax]
0x14000c9e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c9eb  mov     ebx, eax
0x14000c9ed  test    eax, eax
0x14000c9ef  js      loc_14000CBAF
0x14000c9f5  mov     rcx, [rbp+57h+var_A0]
0x14000c9f9  lea     rdx, qword_14001C0D0
0x14000ca00  mov     r8, r15
0x14000ca03  mov     rax, [rcx]
0x14000ca06  mov     rax, [rax]
0x14000ca09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ca0e  mov     ebx, eax
0x14000ca10  test    eax, eax
0x14000ca12  js      loc_14000CBAF
0x14000ca18  mov     rcx, [rbp+57h+var_90]
0x14000ca1c  lea     rdx, ?GWSZ_WSCRIPT@@3QBGB; "WScript"
0x14000ca23  mov     r8d, 2
0x14000ca29  mov     rax, [rcx]
0x14000ca2c  mov     rax, [rax+18h]
0x14000ca30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ca35  mov     ebx, eax
0x14000ca37  test    eax, eax
0x14000ca39  js      loc_14000CBAF
0x14000ca3f  mov     rcx, [rbp+57h+var_90]
0x14000ca43  lea     rdx, ?GWSZ_WSH@@3QBGB; "WSH"
0x14000ca4a  mov     r8d, 2
0x14000ca50  mov     rax, [rcx]
0x14000ca53  mov     rax, [rax+18h]
0x14000ca57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ca5c  mov     ebx, eax
0x14000ca5e  test    eax, eax
0x14000ca60  js      loc_14000CBAF
0x14000ca66  mov     rcx, [rbp+57h+var_A0]
0x14000ca6a  lea     r8, [rbp+57h+var_88]
0x14000ca6e  lea     rdx, IID_IPersistMoniker
0x14000ca75  mov     rax, [rcx]
0x14000ca78  mov     rax, [rax]
0x14000ca7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ca80  mov     ebx, eax
0x14000ca82  test    eax, eax
0x14000ca84  js      loc_14000CBAF
0x14000ca8a  lea     rdx, [rbp+57h+ppbc]; ppbc
0x14000ca8e  xor     ecx, ecx; reserved
0x14000ca90  call    cs:__imp_CreateBindCtx
0x14000ca96  mov     ebx, eax
0x14000ca98  test    eax, eax
0x14000ca9a  js      loc_14000CBAF
0x14000caa0  mov     rcx, [rbp+57h+ppbc]
0x14000caa4  lea     rdx, [rbp+57h+var_48]
0x14000caa8  mov     qword ptr [rbp+57h+var_48], 10h
0x14000cab0  mov     qword ptr [rbp+57h+var_48+8], r14
0x14000cab4  mov     rax, [rcx]
0x14000cab7  mov     rax, [rax+30h]
0x14000cabb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cac0  mov     ebx, eax
0x14000cac2  test    eax, eax
0x14000cac4  js      loc_14000CBAF
0x14000caca  mov     rcx, [rbp+57h+var_88]
0x14000cace  mov     edx, 1
0x14000cad3  mov     r9, [rbp+57h+ppbc]
0x14000cad7  mov     r8, [rbp+57h+var_70]
0x14000cadb  mov     dword ptr [rsp+0E0h+ppv], r14d
0x14000cae0  mov     rax, [rcx]
0x14000cae3  mov     rax, [rax+28h]
0x14000cae7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000caec  mov     ebx, eax
0x14000caee  test    eax, eax
0x14000caf0  jns     short loc_14000CB0F
0x14000caf2  cmp     eax, 80020101h
0x14000caf7  jz      loc_14000CBAF
0x14000cafd  mov     edx, 80070002h; int
0x14000cb02  mov     rcx, rdi; this
0x14000cb05  call    ?ReportLoadError@CHost@@QEAAJJ@Z; CHost::ReportLoadError(long)
0x14000cb0a  jmp     loc_14000CB9A
0x14000cb0f  cmp     [rdi+45h], r14b
0x14000cb13  jz      short loc_14000CB2E
0x14000cb15  mov     edx, [rdi+2Ch]; unsigned int
0x14000cb18  mov     rcx, [rdi+288h]; this
0x14000cb1f  call    ?Start@CTimer@@QEAAJK@Z; CTimer::Start(ulong)
0x14000cb24  mov     ebx, eax
0x14000cb26  test    eax, eax
0x14000cb28  js      loc_14000CBAF
0x14000cb2e  mov     rcx, [rbp+57h+var_A0]
0x14000cb32  lea     rdx, [rbp+57h+var_78]
0x14000cb36  mov     r8, [rsi]
0x14000cb39  xor     r9d, r9d
0x14000cb3c  mov     rsi, [rbp+57h+var_68]
0x14000cb40  mov     [rsp+0E0h+var_B8], rdx
0x14000cb45  lea     rdx, IID_IUnknown
0x14000cb4c  mov     rax, [rcx]
0x14000cb4f  mov     [rsp+0E0h+ppv], rdx
0x14000cb54  mov     rdx, rsi
0x14000cb57  mov     rax, [rax+20h]
0x14000cb5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cb60  mov     ebx, eax
0x14000cb62  test    eax, eax
0x14000cb64  jns     short loc_14000CBA2
0x14000cb66  cmp     eax, 80070057h
0x14000cb6b  jnz     short loc_14000CBAF
0x14000cb6d  mov     rax, [rdi]
0x14000cb70  lea     rcx, Default
0x14000cb77  mov     edx, cs:?g_lResourceBase@Global@@2JA; long Global::g_lResourceBase
0x14000cb7d  mov     r9, rsi
0x14000cb80  mov     [rsp+0E0h+ppv], rcx
0x14000cb85  add     edx, 15h
0x14000cb88  mov     r8d, 0CF7h
0x14000cb8e  mov     rcx, rdi
0x14000cb91  mov     rax, [rax+8]
0x14000cb95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cb9a  mov     ebx, eax
0x14000cb9c  test    eax, eax
0x14000cb9e  jns     short loc_14000CBC6
0x14000cba0  jmp     short loc_14000CBAF
0x14000cba2  mov     ebx, r14d
0x14000cba5  jmp     short loc_14000CBC6
0x14000cba7  mov     ebx, 8007000Eh
0x14000cbac  xor     r14d, r14d
0x14000cbaf  mov     rcx, [r15]
0x14000cbb2  test    rcx, rcx
0x14000cbb5  jz      short loc_14000CBC6
0x14000cbb7  mov     rax, [rcx]
0x14000cbba  mov     rax, [rax+10h]
0x14000cbbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cbc3  mov     [r15], r14
0x14000cbc6  mov     rcx, [rbp+57h+ppbc]
0x14000cbca  test    rcx, rcx
0x14000cbcd  jz      short loc_14000CBDB
  ... truncated ...
```
