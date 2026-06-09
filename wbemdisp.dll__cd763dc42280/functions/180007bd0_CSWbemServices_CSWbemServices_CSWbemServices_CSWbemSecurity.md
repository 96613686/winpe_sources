# CSWbemServices::CSWbemServices(CSWbemServices *,CSWbemSecurity *)

- ea: `0x180007bd0`
- end: `0x180008227`
- name: `??0CSWbemServices@@QEAA@PEAV0@PEAVCSWbemSecurity@@@Z`
- size: `1623`
- prototype: `CSWbemServices *__fastcall(CSWbemServices *__hidden this, struct CSWbemServices *, struct CSWbemSecurity *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800287bc`

## callees

- `0x180006550`
- `0x180007bd0`
- `0x180008de0`
- `0x18000fd64`
- `0x180013920`
- `0x1800197ec`
- `0x180019870`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180007ca4`
- `OLEAUT32!__imp_SysAllocString` at `0x180007d65`
- `OLEAUT32!__imp_SysAllocString` at `0x180007e2c`
- `OLEAUT32!__imp_SysAllocString` at `0x18000805b`
- `OLEAUT32!__imp_SysAllocString` at `0x180007ca4`
- `OLEAUT32!__imp_SysAllocString` at `0x180007d65`
- `OLEAUT32!__imp_SysAllocString` at `0x180007e2c`
- `OLEAUT32!__imp_SysAllocString` at `0x18000805b`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180008088`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180008088`
- `OLEAUT32!__imp_SysFreeString` at `0x18000821b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000821b`
- `OLEAUT32!__imp_SysStringLen` at `0x18000807c`
- `OLEAUT32!__imp_SysStringLen` at `0x18000807c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000803b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000803b`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180007cdc`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180007d9f`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800081e0`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180007cdc`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180007d9f`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800081e0`

## string_xrefs

- `0x180007c9d`: `SWbemServicesEx`
- `0x180007d5e`: `SWbemSecurity`
- `0x180007e25`: `SWbemPrivilegeSet`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
CSWbemServices *__fastcall CSWbemServices::CSWbemServices(
        CSWbemServices *this,
        struct CSWbemServices *a2,
        struct CSWbemSecurity *a3)
{
  struct CSWbemSecurity *v3; // rbx
  struct CSWbemServices *v4; // r13
  CSWbemServices *v5; // r15
  _QWORD *v6; // r12
  char *v7; // rax
  char *v8; // rdi
  __int64 v9; // rbx
  GUID *v10; // rax
  GUID *v11; // rsi
  __int64 v12; // r13
  __int64 v13; // rbx
  __int64 v14; // r15
  __int64 v15; // rsi
  __int64 v16; // rbx
  __int64 v17; // rbx
  __int64 v18; // rbx
  __int64 v19; // rsi
  int v20; // edi
  __int64 v21; // rcx
  __int64 v22; // r14
  __int64 v23; // r12
  __int64 v24; // rdi
  struct IUnknown *v25; // rdi
  OLECHAR *v26; // rcx
  UINT v27; // eax
  int v29; // esi
  __int64 v30; // r14
  __int64 v31; // r8
  unsigned int (__fastcall ***v32)(_QWORD, GUID *, _QWORD *); // rcx
  struct IUnknown *v33; // rcx
  __int64 i; // rax
  CSWbemPrivilegeSet *v35; // rax
  CSWbemPrivilegeSet *v36; // rax
  int v37; // [rsp+20h] [rbp-59h]
  struct IUnknown *v38; // [rsp+50h] [rbp-29h] BYREF
  enum WbemAuthenticationLevelEnum v39[2]; // [rsp+58h] [rbp-21h] BYREF
  _QWORD v40[2]; // [rsp+60h] [rbp-19h] BYREF
  unsigned int (__fastcall ***v41)(_QWORD, GUID *, _QWORD *); // [rsp+70h] [rbp-9h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+78h] [rbp-1h] BYREF
  _QWORD v43[10]; // [rsp+80h] [rbp+7h] BYREF
  struct CSWbemServices *v45; // [rsp+E8h] [rbp+6Fh] BYREF
  struct CSWbemSecurity *v46; // [rsp+F0h] [rbp+77h]
  __int64 v47; // [rsp+F8h] [rbp+7Fh] BYREF

  v46 = a3;
  v45 = a2;
  v3 = a3;
  v4 = a2;
  v5 = this;
  *(_QWORD *)this = &CSWbemServices::`vftable'{for `ISWbemServicesEx'};
  *((_QWORD *)this + 1) = &CSWbemServices::`vftable'{for `IDispatchEx'};
  *((_QWORD *)this + 2) = &CSWbemServices::`vftable'{for `ISupportErrorInfo'};
  *((_QWORD *)this + 3) = &CSWbemServices::`vftable'{for `ISWbemInternalServices'};
  *((_QWORD *)this + 4) = &CSWbemServices::`vftable'{for `IProvideClassInfo'};
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = &CDispatchHelp::`vftable';
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_DWORD *)this + 18) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_DWORD *)this + 40) = 0;
  _InterlockedIncrement(&g_cObj);
  *((_QWORD *)this + 12) = this;
  *(GUID *)((char *)this + 104) = IID_ISWbemServicesEx;
  *(GUID *)((char *)this + 120) = CLSID_SWbemServicesEx;
  *((_QWORD *)this + 8) = SysAllocString(L"SWbemServicesEx");
  if ( !v4 )
    return v5;
  v6 = (_QWORD *)*((_QWORD *)v4 + 17);
  if ( v6 )
  {
    (*(void (__fastcall **)(_QWORD))(*v6 + 8LL))(*((_QWORD *)v4 + 17));
    v7 = (char *)CWin32DefaultArena::WbemMemAlloc(0x90u);
    v8 = v7;
    lpCriticalSection = (LPCRITICAL_SECTION)v7;
    if ( v7 )
    {
      *(_QWORD *)v7 = &CSWbemSecurity::`vftable'{for `ISWbemSecurity'};
      *((_QWORD *)v7 + 1) = &CSWbemSecurity::`vftable'{for `ISupportErrorInfo'};
      *((_QWORD *)v7 + 2) = &CSWbemSecurity::`vftable'{for `ISWbemInternalSecurity'};
      *((_QWORD *)v7 + 3) = &CSWbemSecurity::`vftable'{for `IProvideClassInfo'};
      *((_QWORD *)v7 + 4) = 0;
      *((_QWORD *)v7 + 5) = &CDispatchHelp::`vftable';
      *((_QWORD *)v7 + 8) = 0;
      *((_QWORD *)v7 + 9) = 0;
      *((_QWORD *)v7 + 10) = 0;
      *((_QWORD *)v7 + 6) = 0;
      *((_DWORD *)v7 + 14) = 0;
      *((_QWORD *)v7 + 15) = 0;
      *((_QWORD *)v7 + 16) = 0;
      *((_QWORD *)v7 + 10) = v7;
      *(GUID *)(v7 + 88) = IID_ISWbemSecurity;
      *(GUID *)(v7 + 104) = CLSID_SWbemSecurity;
      *((_QWORD *)v7 + 6) = SysAllocString(L"SWbemSecurity");
      *((_DWORD *)v8 + 34) = 1;
      v9 = v6[4];
      v47 = v9;
      if ( v9 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
        v10 = (GUID *)CWin32DefaultArena::WbemMemAlloc(0x88u);
        v11 = v10;
        *(_QWORD *)v39 = v10;
        if ( v10 )
        {
          *(_QWORD *)&v10->Data1 = &CSWbemPrivilegeSet::`vftable'{for `ISWbemPrivilegeSet'};
          *(_QWORD *)v10->Data4 = &CSWbemPrivilegeSet::`vftable'{for `ISupportErrorInfo'};
          *(_QWORD *)&v10[1].Data1 = &CSWbemPrivilegeSet::`vftable'{for `IProvideClassInfo'};
          *(_QWORD *)&v10[2].Data1 = &CDispatchHelp::`vftable';
          *(_QWORD *)v10[3].Data4 = 0;
          *(_QWORD *)&v10[4].Data1 = 0;
          *(_QWORD *)v10[4].Data4 = 0;
          *(_QWORD *)v10[2].Data4 = 0;
          v10[3].Data1 = 0;
          v40[0] = v10 + 7;
          *(_QWORD *)&v10[7].Data1 = 0;
          *(_QWORD *)v10[7].Data4 = 0;
          *(_QWORD *)&v10[7].Data1 = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<enum WbemPrivilegeEnum const,CSWbemPrivilege *>,CWbemAllocator<CSWbemPrivilege *>>>::_Buyheadnode();
          *(_QWORD *)v11[4].Data4 = v11;
          v11[5] = IID_ISWbemPrivilegeSet;
          v11[6] = CLSID_SWbemPrivilegeSet;
          *(_QWORD *)v11[2].Data4 = SysAllocString(L"SWbemPrivilegeSet");
          v11[8].Data1 = 1;
          v11[1].Data4[0] = 1;
          v12 = v47;
          v13 = **(_QWORD **)(v47 + 112);
          v14 = v40[0];
          while ( v13 != *(_QWORD *)(v12 + 112) )
          {
            v29 = *(_DWORD *)(v13 + 32);
            v30 = *(_QWORD *)(v13 + 40);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 8LL))(v30);
            LODWORD(v43[0]) = v29;
            v43[1] = v30;
            LOBYTE(v37) = byte_180045B58;
            std::_Tree<std::_Tmap_traits<enum WbemPrivilegeEnum,CSWbemPrivilege *,std::less<int>,CWbemAllocator<CSWbemPrivilege *>,0>>::_Insert_nohint<std::pair<enum WbemPrivilegeEnum const,CSWbemPrivilege *>,std::_Nil>(
              v14,
              v40,
              v31,
              v43,
              v37);
            if ( !*(_BYTE *)(v13 + 25) )
            {
              if ( *(_BYTE *)(*(_QWORD *)(v13 + 16) + 25LL) )
              {
                for ( i = *(_QWORD *)(v13 + 8); !*(_BYTE *)(i + 25); i = *(_QWORD *)(i + 8) )
                {
                  if ( v13 != *(_QWORD *)(i + 16) )
                    break;
                  v13 = i;
                }
                v13 = i;
              }
              else
              {
                v13 = std::_Tree_val<std::_Tree_simple_types<std::pair<enum WbemPrivilegeEnum const,CSWbemPrivilege *>>>::_Min();
              }
            }
          }
          _InterlockedIncrement(&g_cObj);
          v5 = this;
          v4 = v45;
          v15 = *(_QWORD *)v39;
          v9 = v47;
        }
        else
        {
          v15 = 0;
        }
        *((_QWORD *)v8 + 4) = v15;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      }
      else
      {
        v35 = (CSWbemPrivilegeSet *)CWin32DefaultArena::WbemMemAlloc(0x88u);
        v45 = v35;
        if ( v35 )
          v36 = CSWbemPrivilegeSet::CSWbemPrivilegeSet(v35);
        else
          v36 = 0;
        *((_QWORD *)v8 + 4) = v36;
      }
      v16 = v6[15];
      if ( v16 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v16 + 8LL))(v6[15]);
      *((_QWORD *)v8 + 15) = v16;
      v17 = v6[16];
      if ( v17 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v17 + 8LL))(v6[16]);
      *((_QWORD *)v8 + 16) = v17;
      _InterlockedIncrement(&g_cObj);
      v3 = v46;
    }
    else
    {
      v8 = 0;
    }
    *((_QWORD *)v5 + 17) = v8;
    (*(void (__fastcall **)(_QWORD *))(*v6 + 16LL))(v6);
  }
  if ( v3 )
  {
    v18 = *((_QWORD *)v3 + 16);
    if ( v18 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 8LL))(v18);
      v19 = *((_QWORD *)v5 + 17);
      if ( !v19 )
        goto LABEL_31;
      LODWORD(v47) = 0;
      LODWORD(v45) = 0;
      v40[0] = 0;
      v20 = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))v18)(v18, &IID_IClientSecurity, v40);
      if ( !v20 )
      {
        v39[0] = wbemAuthenticationLevelDefault;
        LODWORD(v38) = 0;
        LODWORD(v41) = 0;
        v20 = (*(__int64 (__fastcall **)(_QWORD, __int64, enum WbemAuthenticationLevelEnum *, struct IUnknown **, _QWORD, __int64 *, struct CSWbemServices **, _QWORD, unsigned int (__fastcall ****)(_QWORD, GUID *, _QWORD *)))(*(_QWORD *)v40[0] + 24LL))(
                v40[0],
                v18,
                v39,
                &v38,
                0,
                &v47,
                &v45,
                0,
                &v41);
        if ( v20 == -2147023150 )
        {
          LODWORD(v47) = 1;
          LODWORD(v45) = 2;
          v20 = 0;
        }
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v40[0] + 16LL))(v40[0]);
      }
      if ( v20 )
        goto LABEL_31;
      v21 = *(_QWORD *)(v19 + 128);
      if ( v21 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
        *(_QWORD *)(v19 + 128) = 0;
      }
      v22 = *(_QWORD *)(v19 + 120);
      if ( !v22 )
        goto LABEL_31;
      v23 = (int)v45;
      v24 = (int)v47;
      v39[0] = v47;
      CInCritSec::CInCritSec((CInCritSec *)&lpCriticalSection, (struct _RTL_CRITICAL_SECTION *)(v22 + 16));
      v43[0] = v22 + 8 * (v23 + 4 * v24 + 6);
      v25 = *(struct IUnknown **)v43[0];
      v38 = v25;
      if ( v25 )
      {
        ((void (__fastcall *)(struct IUnknown *))v25->lpVtbl->AddRef)(v25);
      }
      else
      {
        v32 = *(unsigned int (__fastcall ****)(_QWORD, GUID *, _QWORD *))(v22
                                                                        + 8
                                                                        * (*(int *)(v22 + 328)
                                                                         + 4LL * *(int *)(v22 + 324))
                                                                        + 48);
        v41 = v32;
        if ( !v32 )
          goto LABEL_30;
        v40[0] = 0;
        if ( !(**v32)(v32, &IID_IClientSecurity, v40) )
        {
          if ( !(*(unsigned int (__fastcall **)(_QWORD, _QWORD, struct IUnknown **))(*(_QWORD *)v40[0] + 40LL))(
                  v40[0],
                  v41,
                  &v38) )
          {
            CSWbemProxyCache::SecureProxy((CSWbemProxyCache *)v22, v38, v39[0], (enum WbemImpersonationLevelEnum)v23);
            v33 = v38;
            *(_QWORD *)v43[0] = v38;
            ((void (__fastcall *)(struct IUnknown *))v33->lpVtbl->AddRef)(v33);
          }
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v40[0] + 16LL))(v40[0]);
        }
      }
      v25 = v38;
LABEL_30:
      LeaveCriticalSection(lpCriticalSection);
      *(_QWORD *)(v19 + 128) = v25;
LABEL_31:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
  }
  *((_QWORD *)v5 + 6) = SysAllocString(*((const OLECHAR **)v4 + 6));
  v26 = (OLECHAR *)*((_QWORD *)v5 + 5);
  if ( v26 != *((OLECHAR **)v4 + 5) )
  {
    if ( v26 )
      SysFreeString(v26);
    v27 = SysStringLen(*((BSTR *)v4 + 5));
    *((_QWORD *)v5 + 5) = SysAllocStringLen(*((const OLECHAR **)v4 + 5), v27);
  }
  return v5;
}

```

## disassembly

```asm
0x180007bd0  mov     [rsp-8+arg_10], r8
0x180007bd5  mov     [rsp-8+arg_8], rdx
0x180007bda  mov     [rsp-8+arg_0], rcx
0x180007bdf  push    rbp
0x180007be0  push    rbx
0x180007be1  push    rsi
0x180007be2  push    rdi
0x180007be3  push    r12
0x180007be5  push    r13
0x180007be7  push    r14
0x180007be9  push    r15
0x180007beb  lea     rbp, [rsp-1Fh]
0x180007bf0  sub     rsp, 98h
0x180007bf7  mov     rbx, r8
0x180007bfa  mov     r13, rdx
0x180007bfd  mov     r15, rcx
0x180007c00  lea     rax, ??_7CSWbemServices@@6BISWbemServicesEx@@@; const CSWbemServices::`vftable'{for `ISWbemServicesEx'}
0x180007c07  mov     [rcx], rax
0x180007c0a  lea     rax, ??_7CSWbemServices@@6BIDispatchEx@@@; const CSWbemServices::`vftable'{for `IDispatchEx'}
0x180007c11  mov     [rcx+8], rax
0x180007c15  lea     rax, ??_7CSWbemServices@@6BISupportErrorInfo@@@; const CSWbemServices::`vftable'{for `ISupportErrorInfo'}
0x180007c1c  mov     [rcx+10h], rax
0x180007c20  lea     rax, ??_7CSWbemServices@@6BISWbemInternalServices@@@; const CSWbemServices::`vftable'{for `ISWbemInternalServices'}
0x180007c27  mov     [rcx+18h], rax
0x180007c2b  lea     rax, ??_7CSWbemServices@@6BIProvideClassInfo@@@; const CSWbemServices::`vftable'{for `IProvideClassInfo'}
0x180007c32  mov     [rcx+20h], rax
0x180007c36  xor     r14d, r14d
0x180007c39  mov     [rcx+28h], r14
0x180007c3d  mov     [rcx+30h], r14
0x180007c41  lea     rsi, ??_7CDispatchHelp@@6B@; const CDispatchHelp::`vftable'
0x180007c48  mov     [rcx+38h], rsi
0x180007c4c  mov     [rcx+50h], r14
0x180007c50  mov     [rcx+58h], r14
0x180007c54  mov     [rcx+60h], r14
0x180007c58  mov     [rcx+40h], r14
0x180007c5c  mov     [rcx+48h], r14d
0x180007c60  mov     [rcx+88h], r14
0x180007c67  mov     [rcx+90h], r14
0x180007c6e  mov     [rcx+98h], r14
0x180007c75  mov     [rcx+0A0h], r14d
0x180007c7c  lock inc cs:?g_cObj@@3JA; long g_cObj
0x180007c83  movups  xmm1, xmmword ptr cs:CLSID_SWbemServicesEx.Data1
0x180007c8a  movups  xmm0, xmmword ptr cs:IID_ISWbemServicesEx.Data1
0x180007c91  mov     [rcx+60h], rcx
0x180007c95  movups  xmmword ptr [rcx+68h], xmm0
0x180007c99  movups  xmmword ptr [rcx+78h], xmm1
0x180007c9d  lea     rcx, aSwbemservicese; "SWbemServicesEx"
0x180007ca4  call    cs:__imp_SysAllocString
0x180007caa  mov     [r15+40h], rax
0x180007cae  test    r13, r13
0x180007cb1  jz      loc_180008092
0x180007cb7  mov     r12, [r13+88h]
0x180007cbe  test    r12, r12
0x180007cc1  jz      loc_180007EEC
0x180007cc7  mov     rax, [r12]
0x180007ccb  mov     rcx, r12
0x180007cce  mov     rax, [rax+8]
0x180007cd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cd7  mov     ecx, 90h
0x180007cdc  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180007ce2  mov     rdi, rax
0x180007ce5  mov     [rbp+57h+lpCriticalSection], rax
0x180007ce9  test    rax, rax
0x180007cec  jz      loc_1800081A6
0x180007cf2  lea     rax, ??_7CSWbemSecurity@@6BISWbemSecurity@@@; const CSWbemSecurity::`vftable'{for `ISWbemSecurity'}
0x180007cf9  mov     [rdi], rax
0x180007cfc  lea     rax, ??_7CSWbemSecurity@@6BISupportErrorInfo@@@; const CSWbemSecurity::`vftable'{for `ISupportErrorInfo'}
0x180007d03  mov     [rdi+8], rax
0x180007d07  lea     rax, ??_7CSWbemSecurity@@6BISWbemInternalSecurity@@@; const CSWbemSecurity::`vftable'{for `ISWbemInternalSecurity'}
0x180007d0e  mov     [rdi+10h], rax
0x180007d12  lea     rax, ??_7CSWbemSecurity@@6BIProvideClassInfo@@@; const CSWbemSecurity::`vftable'{for `IProvideClassInfo'}
0x180007d19  mov     [rdi+18h], rax
0x180007d1d  mov     [rdi+20h], r14
0x180007d21  mov     [rdi+28h], rsi
0x180007d25  mov     [rdi+40h], r14
0x180007d29  mov     [rdi+48h], r14
0x180007d2d  mov     [rdi+50h], r14
0x180007d31  mov     [rdi+30h], r14
0x180007d35  mov     [rdi+38h], r14d
0x180007d39  mov     [rdi+78h], r14
0x180007d3d  mov     [rdi+80h], r14
0x180007d44  movups  xmm1, xmmword ptr cs:CLSID_SWbemSecurity.Data1
0x180007d4b  movups  xmm0, xmmword ptr cs:IID_ISWbemSecurity.Data1
0x180007d52  mov     [rdi+50h], rdi
0x180007d56  movups  xmmword ptr [rdi+58h], xmm0
0x180007d5a  movups  xmmword ptr [rdi+68h], xmm1
0x180007d5e  lea     rcx, aSwbemsecurity; "SWbemSecurity"
0x180007d65  call    cs:__imp_SysAllocString
0x180007d6b  mov     [rdi+30h], rax
0x180007d6f  mov     dword ptr [rdi+88h], 1
0x180007d79  mov     rbx, [r12+20h]
0x180007d7e  mov     [rbp+57h+arg_18], rbx
0x180007d82  test    rbx, rbx
0x180007d85  jz      loc_1800081DB
0x180007d8b  mov     rax, [rbx]
0x180007d8e  mov     rcx, rbx
0x180007d91  mov     rax, [rax+8]
0x180007d95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d9a  mov     ecx, 88h
0x180007d9f  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180007da5  mov     rsi, rax
0x180007da8  mov     qword ptr [rbp+57h+var_78], rax
0x180007dac  test    rax, rax
0x180007daf  jz      loc_1800081AE
0x180007db5  lea     rax, ??_7CSWbemPrivilegeSet@@6BISWbemPrivilegeSet@@@; const CSWbemPrivilegeSet::`vftable'{for `ISWbemPrivilegeSet'}
0x180007dbc  mov     [rsi], rax
0x180007dbf  lea     rax, ??_7CSWbemPrivilegeSet@@6BISupportErrorInfo@@@; const CSWbemPrivilegeSet::`vftable'{for `ISupportErrorInfo'}
0x180007dc6  mov     [rsi+8], rax
0x180007dca  lea     rax, ??_7CSWbemPrivilegeSet@@6BIProvideClassInfo@@@; const CSWbemPrivilegeSet::`vftable'{for `IProvideClassInfo'}
0x180007dd1  mov     [rsi+10h], rax
0x180007dd5  lea     rax, ??_7CDispatchHelp@@6B@; const CDispatchHelp::`vftable'
0x180007ddc  mov     [rsi+20h], rax
0x180007de0  mov     [rsi+38h], r14
0x180007de4  mov     [rsi+40h], r14
0x180007de8  mov     [rsi+48h], r14
0x180007dec  mov     [rsi+28h], r14
0x180007df0  mov     [rsi+30h], r14d
0x180007df4  lea     rbx, [rsi+70h]
0x180007df8  mov     [rbp+57h+var_70], rbx
0x180007dfc  mov     [rbx], r14
0x180007dff  mov     [rbx+8], r14
0x180007e03  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBW4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@@std@@V?$CWbemAllocator@PEAVCSWbemPrivilege@@@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBW4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<WbemPrivilegeEnum const,CSWbemPrivilege *>,CWbemAllocator<CSWbemPrivilege *>>>::_Buyheadnode(void)
0x180007e08  mov     [rbx], rax
0x180007e0b  movups  xmm1, xmmword ptr cs:CLSID_SWbemPrivilegeSet.Data1
0x180007e12  movups  xmm0, xmmword ptr cs:IID_ISWbemPrivilegeSet.Data1
0x180007e19  mov     [rsi+48h], rsi
0x180007e1d  movups  xmmword ptr [rsi+50h], xmm0
0x180007e21  movups  xmmword ptr [rsi+60h], xmm1
0x180007e25  lea     rcx, aSwbemprivilege_0; "SWbemPrivilegeSet"
0x180007e2c  call    cs:__imp_SysAllocString
0x180007e32  mov     [rsi+28h], rax
0x180007e36  mov     dword ptr [rsi+80h], 1
0x180007e40  mov     byte ptr [rsi+18h], 1
0x180007e44  mov     r13, [rbp+57h+arg_18]
0x180007e48  mov     rbx, [r13+70h]
0x180007e4c  mov     rbx, [rbx]
0x180007e4f  mov     r15, [rbp+57h+var_70]
0x180007e53  cmp     rbx, [r13+70h]
0x180007e57  jnz     loc_1800080A9
0x180007e5d  lock inc cs:?g_cObj@@3JA; long g_cObj
0x180007e64  mov     r15, [rbp+57h+arg_0]
0x180007e68  mov     r13, [rbp+57h+arg_8]
0x180007e6c  mov     rsi, qword ptr [rbp+57h+var_78]
0x180007e70  mov     rbx, [rbp+57h+arg_18]
0x180007e74  xor     r14d, r14d
0x180007e77  mov     [rdi+20h], rsi
0x180007e7b  mov     rax, [rbx]
0x180007e7e  mov     rcx, rbx
0x180007e81  mov     rax, [rax+10h]
0x180007e85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e8a  mov     rbx, [r12+78h]
0x180007e8f  test    rbx, rbx
0x180007e92  jz      short loc_180007EA3
0x180007e94  mov     rax, [rbx]
0x180007e97  mov     rcx, rbx
0x180007e9a  mov     rax, [rax+8]
0x180007e9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ea3  mov     [rdi+78h], rbx
0x180007ea7  mov     rbx, [r12+80h]
0x180007eaf  test    rbx, rbx
0x180007eb2  jz      short loc_180007EC3
0x180007eb4  mov     rax, [rbx]
0x180007eb7  mov     rcx, rbx
0x180007eba  mov     rax, [rax+8]
0x180007ebe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ec3  mov     [rdi+80h], rbx
0x180007eca  lock inc cs:?g_cObj@@3JA; long g_cObj
0x180007ed1  mov     rbx, [rbp+57h+arg_10]
0x180007ed5  mov     [r15+88h], rdi
0x180007edc  mov     rax, [r12]
0x180007ee0  mov     rcx, r12
0x180007ee3  mov     rax, [rax+10h]
0x180007ee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007eec  test    rbx, rbx
0x180007eef  jz      loc_180008057
0x180007ef5  mov     rbx, [rbx+80h]
0x180007efc  test    rbx, rbx
0x180007eff  jz      loc_180008057
0x180007f05  mov     rax, [rbx]
0x180007f08  mov     rcx, rbx
0x180007f0b  mov     rax, [rax+8]
0x180007f0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f14  mov     rsi, [r15+88h]
0x180007f1b  test    rsi, rsi
0x180007f1e  jz      loc_180008048
0x180007f24  mov     dword ptr [rbp+57h+arg_18], r14d
0x180007f28  mov     dword ptr [rbp+57h+arg_8], r14d
0x180007f2c  mov     [rbp+57h+var_70], r14
0x180007f30  mov     rax, [rbx]
0x180007f33  lea     r8, [rbp+57h+var_70]
0x180007f37  lea     rdx, IID_IClientSecurity
0x180007f3e  mov     rcx, rbx
0x180007f41  mov     rax, [rax]
0x180007f44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f49  mov     edi, eax
0x180007f4b  test    eax, eax
0x180007f4d  jnz     short loc_180007FB8
0x180007f4f  mov     [rbp+57h+var_78], r14d
0x180007f53  mov     dword ptr [rbp+57h+var_80], r14d
0x180007f57  mov     dword ptr [rbp+57h+var_60], r14d
0x180007f5b  mov     rcx, [rbp+57h+var_70]
0x180007f5f  mov     rax, [rcx]
0x180007f62  lea     rdx, [rbp+57h+var_60]
0x180007f66  mov     [rsp+0D0h+var_90], rdx
0x180007f6b  mov     [rsp+0D0h+var_98], r14
0x180007f70  lea     rdx, [rbp+57h+arg_8]
0x180007f74  mov     [rsp+0D0h+var_A0], rdx
0x180007f79  lea     rdx, [rbp+57h+arg_18]
0x180007f7d  mov     [rsp+0D0h+var_A8], rdx
0x180007f82  mov     [rsp+0D0h+var_B0], r14
0x180007f87  lea     r9, [rbp+57h+var_80]
0x180007f8b  lea     r8, [rbp+57h+var_78]
0x180007f8f  mov     rdx, rbx
0x180007f92  mov     rax, [rax+18h]
0x180007f96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f9b  mov     edi, eax
0x180007f9d  cmp     eax, 800706D2h
0x180007fa2  jz      loc_180008205
0x180007fa8  mov     rcx, [rbp+57h+var_70]
0x180007fac  mov     rax, [rcx]
0x180007faf  mov     rax, [rax+10h]
0x180007fb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fb8  test    edi, edi
0x180007fba  jnz     loc_180008048
0x180007fc0  mov     rcx, [rsi+80h]
0x180007fc7  test    rcx, rcx
0x180007fca  jz      short loc_180007FDF
0x180007fcc  mov     rax, [rcx]
0x180007fcf  mov     rax, [rax+10h]
0x180007fd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fd8  mov     [rsi+80h], r14
0x180007fdf  mov     r14, [rsi+78h]
0x180007fe3  test    r14, r14
0x180007fe6  jz      short loc_180008048
0x180007fe8  movsxd  r12, dword ptr [rbp+57h+arg_8]
0x180007fec  movsxd  rdi, dword ptr [rbp+57h+arg_18]
0x180007ff0  mov     [rbp+57h+var_78], edi
0x180007ff3  lea     rdx, [r14+10h]; struct _RTL_CRITICAL_SECTION *
0x180007ff7  lea     rcx, [rbp+57h+lpCriticalSection]; this
0x180007ffb  call    ??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x180008000  nop
0x180008001  lea     rax, ds:6[rdi*4]
0x180008009  add     rax, r12
0x18000800c  lea     rax, [r14+rax*8]
0x180008010  mov     [rbp+57h+var_50], rax
0x180008014  mov     rdi, [rax]
0x180008017  mov     [rbp+57h+var_80], rdi
0x18000801b  test    rdi, rdi
0x18000801e  jz      loc_180008106
0x180008024  mov     rax, [rdi]
0x180008027  mov     rcx, rdi
0x18000802a  mov     rax, [rax+8]
0x18000802e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008033  mov     rdi, [rbp+57h+var_80]
0x180008037  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x18000803b  call    cs:__imp_LeaveCriticalSection
0x180008041  mov     [rsi+80h], rdi
0x180008048  mov     rax, [rbx]
0x18000804b  mov     rcx, rbx
0x18000804e  mov     rax, [rax+10h]
0x180008052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008057  mov     rcx, [r13+30h]; psz
0x18000805b  call    cs:__imp_SysAllocString
0x180008061  mov     [r15+30h], rax
0x180008065  mov     rcx, [r15+28h]; bstrString
0x180008069  cmp     rcx, [r13+28h]
0x18000806d  jz      short loc_180008092
0x18000806f  test    rcx, rcx
0x180008072  jnz     loc_18000821B
0x180008078  mov     rcx, [r13+28h]; pbstr
0x18000807c  call    cs:__imp_SysStringLen
0x180008082  mov     edx, eax; ui
0x180008084  mov     rcx, [r13+28h]; strIn
0x180008088  call    cs:__imp_SysAllocStringLen
0x18000808e  mov     [r15+28h], rax
0x180008092  mov     rax, r15
0x180008095  add     rsp, 98h
0x18000809c  pop     r15
0x18000809e  pop     r14
0x1800080a0  pop     r13
0x1800080a2  pop     r12
0x1800080a4  pop     rdi
0x1800080a5  pop     rsi
0x1800080a6  pop     rbx
0x1800080a7  pop     rbp
0x1800080a8  retn
0x1800080a9  mov     esi, [rbx+20h]
0x1800080ac  mov     r14, [rbx+28h]
0x1800080b0  mov     rax, [r14]
0x1800080b3  mov     rcx, r14
0x1800080b6  mov     rax, [rax+8]
0x1800080ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080bf  mov     dword ptr [rbp+57h+var_50], esi
0x1800080c2  mov     [rbp+57h+var_48], r14
0x1800080c6  movzx   eax, cs:byte_180045B58
0x1800080cd  mov     byte ptr [rsp+0D0h+var_B0], al
0x1800080d1  lea     r9, [rbp+57h+var_50]
0x1800080d5  lea     rdx, [rbp+57h+var_70]
0x1800080d9  mov     rcx, r15
0x1800080dc  call    ??$_Insert_nohint@U?$pair@$$CBW4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@@std@@U_Nil@2@@?$_Tree@V?$_Tmap_traits@W4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@U?$less@H@std@@V?$CWbemAllocator@PEAVCSWbemPrivilege@@@@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@@std@@@std@@@std@@@std@@_N@1@_N$$QEAU?$pair@$$CBW4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@@1@U_Nil@1@@Z; std::_Tree<std::_Tmap_traits<WbemPrivilegeEnum,CSWbemPrivilege *,std::less<int>,CWbemAllocator<CSWbemPrivilege *>,0>>::_Insert_nohint<std::pair<WbemPrivilegeEnum const,CSWbemPrivilege *>,std::_Nil>(bool,std::pair<WbemPrivilegeEnum const,CSWbemPrivilege *> &&,std::_Nil)
  ... truncated ...
```
