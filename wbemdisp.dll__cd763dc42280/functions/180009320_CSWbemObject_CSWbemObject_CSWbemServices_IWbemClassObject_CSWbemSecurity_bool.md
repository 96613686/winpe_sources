# CSWbemObject::CSWbemObject(CSWbemServices *,IWbemClassObject *,CSWbemSecurity *,bool)

- ea: `0x180009320`
- end: `0x180009b0e`
- name: `??0CSWbemObject@@QEAA@PEAVCSWbemServices@@PEAUIWbemClassObject@@PEAVCSWbemSecurity@@_N@Z`
- size: `2030`
- prototype: `CSWbemObject *__fastcall(CSWbemObject *__hidden this, struct CSWbemServices *, struct IWbemClassObject *, struct CSWbemSecurity *, bool)`
- caller_count: `19`
- callee_count: `9`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180002610`
- `0x180005bf0`
- `0x180008230`
- `0x18000bef0`
- `0x18000e9a0`
- `0x1800191d0`
- `0x1800192e0`
- `0x18001d630`
- `0x18001e408`
- `0x18001f270`
- `0x18001f740`
- `0x180028f80`
- `0x1800292f0`
- `0x18002b130`
- `0x18002c350`
- `0x18002c860`
- `0x1800308f0`
- `0x1800317c0`
- `0x180031a30`

## callees

- `0x180006550`
- `0x180008de0`
- `0x180009320`
- `0x18000fd64`
- `0x180013920`
- `0x1800197ec`
- `0x180019870`
- `0x180019d94`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180009483`
- `OLEAUT32!__imp_SysAllocString` at `0x180009552`
- `OLEAUT32!__imp_SysAllocString` at `0x18000961c`
- `OLEAUT32!__imp_SysAllocString` at `0x180009852`
- `OLEAUT32!__imp_SysAllocString` at `0x180009483`
- `OLEAUT32!__imp_SysAllocString` at `0x180009552`
- `OLEAUT32!__imp_SysAllocString` at `0x18000961c`
- `OLEAUT32!__imp_SysAllocString` at `0x180009852`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000987f`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000987f`
- `OLEAUT32!__imp_SysFreeString` at `0x180009b02`
- `OLEAUT32!__imp_SysFreeString` at `0x180009b02`
- `OLEAUT32!__imp_SysStringLen` at `0x180009873`
- `OLEAUT32!__imp_SysStringLen` at `0x180009873`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009832`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009832`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800093ca`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800094b5`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000958e`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800098a9`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800098ea`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180009ac6`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800093ca`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800094b5`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000958e`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800098a9`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800098ea`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180009ac6`

## string_xrefs

- `0x18000947c`: `SWbemServicesEx`
- `0x18000954b`: `SWbemSecurity`
- `0x180009615`: `SWbemPrivilegeSet`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
CSWbemObject *CSWbemObject::CSWbemObject(
        CSWbemObject *this,
        struct CSWbemServices *a2,
        struct IWbemClassObject *a3,
        struct CSWbemSecurity *a4,
        ...)
{
  struct CSWbemSecurity *v4; // rsi
  char *v7; // rax
  _QWORD *v8; // r15
  _QWORD *v9; // rbx
  char *v10; // rax
  char *v11; // r12
  CSWbemPrivilegeSet *v12; // r14
  GUID *v13; // rax
  GUID *v14; // rsi
  CSWbemPrivilegeSet *v15; // r15
  __int64 v16; // rbx
  GUID *v17; // r12
  struct IUnknown *v18; // rsi
  __int64 v19; // rsi
  __int64 v20; // rsi
  __int64 v21; // rbx
  __int64 v22; // r14
  int v23; // esi
  __int64 v24; // rcx
  __int64 v25; // r12
  __int64 v26; // rsi
  struct IUnknown *v27; // rsi
  OLECHAR *v28; // rcx
  UINT v29; // eax
  CSWbemPrivilegeSet *v30; // rsi
  __int64 v31; // rcx
  GUID *v32; // r14
  __int64 v33; // rcx
  int v35; // esi
  struct _RTL_CRITICAL_SECTION *v36; // r14
  __int64 v37; // r8
  unsigned int (__fastcall ***v38)(_QWORD, GUID *, _QWORD *); // rcx
  struct IUnknown *v39; // rcx
  __int64 i; // rax
  CSWbemPrivilegeSet *v41; // rax
  CSWbemPrivilegeSet *v42; // rax
  int v43; // [rsp+20h] [rbp-61h]
  struct IUnknown *v44; // [rsp+50h] [rbp-31h] BYREF
  _QWORD *v45; // [rsp+58h] [rbp-29h] BYREF
  _QWORD *v46; // [rsp+60h] [rbp-21h]
  unsigned int (__fastcall ***v47)(_QWORD, GUID *, _QWORD *); // [rsp+68h] [rbp-19h]
  struct IUnknown **v48; // [rsp+70h] [rbp-11h] BYREF
  LPCRITICAL_SECTION lpCriticalSection[10]; // [rsp+80h] [rbp-1h] BYREF
  CSWbemPrivilegeSet *v50; // [rsp+E0h] [rbp+5Fh] BYREF
  GUID *v51; // [rsp+E8h] [rbp+67h] BYREF
  char *v52; // [rsp+F0h] [rbp+6Fh] BYREF
  struct CSWbemSecurity *v53; // [rsp+F8h] [rbp+77h]
  __int64 v54; // [rsp+100h] [rbp+7Fh] BYREF
  va_list va; // [rsp+100h] [rbp+7Fh]
  va_list va1; // [rsp+108h] [rbp+87h] BYREF

  va_start(va1, a4);
  va_start(va, a4);
  v54 = va_arg(va1, _QWORD);
  v53 = a4;
  v4 = a4;
  *(_QWORD *)this = &CSWbemObject::`vftable'{for `ISWbemObjectEx'};
  *((_QWORD *)this + 1) = &CSWbemObject::`vftable'{for `IDispatchEx'};
  *((_QWORD *)this + 2) = &CSWbemObject::`vftable'{for `ISWbemInternalObject'};
  *((_QWORD *)this + 3) = &CSWbemObject::`vftable'{for `IObjectSafety'};
  *((_QWORD *)this + 4) = &CSWbemObject::`vftable'{for `ISupportErrorInfo'};
  *((_QWORD *)this + 5) = &CSWbemObject::`vftable'{for `IProvideClassInfo'};
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_BYTE *)this + 96) = 1;
  *((_QWORD *)this + 13) = 0;
  *((_DWORD *)this + 28) = 0;
  *((_BYTE *)this + 48) = v54;
  *((_QWORD *)this + 8) = a3;
  ((void (__fastcall *)(struct IWbemClassObject *))a3->lpVtbl->AddRef)(a3);
  *((_QWORD *)this + 10) = 0;
  if ( !a2 )
    goto LABEL_39;
  v7 = (char *)CWin32DefaultArena::WbemMemAlloc(0xA8u);
  v8 = v7;
  v46 = v7;
  if ( v7 )
  {
    *(_QWORD *)v7 = &CSWbemServices::`vftable'{for `ISWbemServicesEx'};
    *((_QWORD *)v7 + 1) = &CSWbemServices::`vftable'{for `IDispatchEx'};
    *((_QWORD *)v7 + 2) = &CSWbemServices::`vftable'{for `ISupportErrorInfo'};
    *((_QWORD *)v7 + 3) = &CSWbemServices::`vftable'{for `ISWbemInternalServices'};
    *((_QWORD *)v7 + 4) = &CSWbemServices::`vftable'{for `IProvideClassInfo'};
    *((_QWORD *)v7 + 5) = 0;
    *((_QWORD *)v7 + 6) = 0;
    *((_QWORD *)v7 + 7) = &CDispatchHelp::`vftable';
    *((_QWORD *)v7 + 10) = 0;
    *((_QWORD *)v7 + 11) = 0;
    *((_QWORD *)v7 + 12) = 0;
    *((_QWORD *)v7 + 8) = 0;
    *((_DWORD *)v7 + 18) = 0;
    *((_QWORD *)v7 + 17) = 0;
    *((_QWORD *)v7 + 18) = 0;
    *((_QWORD *)v7 + 19) = 0;
    *((_DWORD *)v7 + 40) = 0;
    _InterlockedIncrement(&g_cObj);
    *((_QWORD *)v7 + 12) = v7;
    *(GUID *)(v7 + 104) = IID_ISWbemServicesEx;
    *(GUID *)(v7 + 120) = CLSID_SWbemServicesEx;
    *((_QWORD *)v7 + 8) = SysAllocString(L"SWbemServicesEx");
    v9 = (_QWORD *)*((_QWORD *)a2 + 17);
    v45 = v9;
    if ( v9 )
    {
      (*(void (__fastcall **)(_QWORD *))(*v9 + 8LL))(v9);
      v10 = (char *)CWin32DefaultArena::WbemMemAlloc(0x90u);
      v11 = v10;
      v52 = v10;
      if ( v10 )
      {
        *(_QWORD *)v10 = &CSWbemSecurity::`vftable'{for `ISWbemSecurity'};
        *((_QWORD *)v10 + 1) = &CSWbemSecurity::`vftable'{for `ISupportErrorInfo'};
        *((_QWORD *)v10 + 2) = &CSWbemSecurity::`vftable'{for `ISWbemInternalSecurity'};
        *((_QWORD *)v10 + 3) = &CSWbemSecurity::`vftable'{for `IProvideClassInfo'};
        *((_QWORD *)v10 + 4) = 0;
        *((_QWORD *)v10 + 5) = &CDispatchHelp::`vftable';
        *((_QWORD *)v10 + 8) = 0;
        *((_QWORD *)v10 + 9) = 0;
        *((_QWORD *)v10 + 10) = 0;
        *((_QWORD *)v10 + 6) = 0;
        *((_DWORD *)v10 + 14) = 0;
        *((_QWORD *)v10 + 15) = 0;
        *((_QWORD *)v10 + 16) = 0;
        *((_QWORD *)v10 + 10) = v10;
        *(GUID *)(v10 + 88) = IID_ISWbemSecurity;
        *(GUID *)(v10 + 104) = CLSID_SWbemSecurity;
        *((_QWORD *)v10 + 6) = SysAllocString(L"SWbemSecurity");
        *((_DWORD *)v11 + 34) = 1;
        v12 = (CSWbemPrivilegeSet *)v9[4];
        v50 = v12;
        if ( v12 )
        {
          (*(void (__fastcall **)(CSWbemPrivilegeSet *))(*(_QWORD *)v12 + 8LL))(v12);
          v13 = (GUID *)CWin32DefaultArena::WbemMemAlloc(0x88u);
          v14 = v13;
          v44 = (struct IUnknown *)v13;
          if ( v13 )
          {
            *(_QWORD *)&v13->Data1 = &CSWbemPrivilegeSet::`vftable'{for `ISWbemPrivilegeSet'};
            *(_QWORD *)v13->Data4 = &CSWbemPrivilegeSet::`vftable'{for `ISupportErrorInfo'};
            *(_QWORD *)&v13[1].Data1 = &CSWbemPrivilegeSet::`vftable'{for `IProvideClassInfo'};
            *(_QWORD *)&v13[2].Data1 = &CDispatchHelp::`vftable';
            *(_QWORD *)v13[3].Data4 = 0;
            *(_QWORD *)&v13[4].Data1 = 0;
            *(_QWORD *)v13[4].Data4 = 0;
            *(_QWORD *)v13[2].Data4 = 0;
            v13[3].Data1 = 0;
            v51 = v13 + 7;
            *(_QWORD *)&v13[7].Data1 = 0;
            *(_QWORD *)v13[7].Data4 = 0;
            *(_QWORD *)&v13[7].Data1 = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<enum WbemPrivilegeEnum const,CSWbemPrivilege *>,CWbemAllocator<CSWbemPrivilege *>>>::_Buyheadnode();
            *(_QWORD *)v14[4].Data4 = v14;
            v14[5] = IID_ISWbemPrivilegeSet;
            v14[6] = CLSID_SWbemPrivilegeSet;
            *(_QWORD *)v14[2].Data4 = SysAllocString(L"SWbemPrivilegeSet");
            v14[8].Data1 = 1;
            v14[1].Data4[0] = 1;
            v15 = v12;
            v16 = **((_QWORD **)v12 + 14);
            v17 = v51;
            while ( v16 != *((_QWORD *)v15 + 14) )
            {
              v35 = *(_DWORD *)(v16 + 32);
              v36 = *(struct _RTL_CRITICAL_SECTION **)(v16 + 40);
              ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v36->DebugInfo->CriticalSection)(v36);
              LODWORD(lpCriticalSection[0]) = v35;
              lpCriticalSection[1] = v36;
              LOBYTE(v43) = byte_180045B58;
              std::_Tree<std::_Tmap_traits<enum WbemPrivilegeEnum,CSWbemPrivilege *,std::less<int>,CWbemAllocator<CSWbemPrivilege *>,0>>::_Insert_nohint<std::pair<enum WbemPrivilegeEnum const,CSWbemPrivilege *>,std::_Nil>(
                v17,
                &v48,
                v37,
                lpCriticalSection,
                v43);
              if ( !*(_BYTE *)(v16 + 25) )
              {
                if ( *(_BYTE *)(*(_QWORD *)(v16 + 16) + 25LL) )
                {
                  for ( i = *(_QWORD *)(v16 + 8); !*(_BYTE *)(i + 25); i = *(_QWORD *)(i + 8) )
                  {
                    if ( v16 != *(_QWORD *)(i + 16) )
                      break;
                    v16 = i;
                  }
                  v16 = i;
                }
                else
                {
                  v16 = std::_Tree_val<std::_Tree_simple_types<std::pair<enum WbemPrivilegeEnum const,CSWbemPrivilege *>>>::_Min();
                }
              }
            }
            _InterlockedIncrement(&g_cObj);
            v8 = v46;
            v11 = v52;
            v9 = v45;
            v18 = v44;
            v12 = v50;
          }
          else
          {
            v18 = 0;
          }
          *((_QWORD *)v11 + 4) = v18;
          (*(void (__fastcall **)(CSWbemPrivilegeSet *))(*(_QWORD *)v12 + 16LL))(v12);
        }
        else
        {
          v41 = (CSWbemPrivilegeSet *)CWin32DefaultArena::WbemMemAlloc(0x88u);
          v50 = v41;
          if ( v41 )
            v42 = CSWbemPrivilegeSet::CSWbemPrivilegeSet(v41);
          else
            v42 = 0;
          *((_QWORD *)v11 + 4) = v42;
        }
        v19 = v9[15];
        if ( v19 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v19 + 8LL))(v9[15]);
        *((_QWORD *)v11 + 15) = v19;
        v20 = v9[16];
        if ( v20 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v20 + 8LL))(v9[16]);
        *((_QWORD *)v11 + 16) = v20;
        _InterlockedIncrement(&g_cObj);
        v4 = v53;
      }
      else
      {
        v11 = 0;
      }
      v8[17] = v11;
      (*(void (__fastcall **)(_QWORD *))(*v9 + 16LL))(v9);
    }
    if ( !v4 )
      goto LABEL_33;
    v21 = *((_QWORD *)v4 + 16);
    if ( !v21 )
      goto LABEL_33;
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v21 + 8LL))(*((_QWORD *)v4 + 16));
    v22 = v8[17];
    if ( !v22 )
      goto LABEL_32;
    LODWORD(v50) = 0;
    LODWORD(v54) = 0;
    v45 = 0;
    v23 = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD **))v21)(v21, &IID_IClientSecurity, &v45);
    if ( !v23 )
    {
      LODWORD(v44) = 0;
      LODWORD(v52) = 0;
      LODWORD(v51) = 0;
      v23 = (*(__int64 (__fastcall **)(_QWORD *, __int64, struct IUnknown **, char **, _QWORD, CSWbemPrivilegeSet **, __int64 *, _QWORD, GUID **))(*v45 + 24LL))(
              v45,
              v21,
              &v44,
              &v52,
              0,
              &v50,
              (__int64 *)va,
              0,
              &v51);
      if ( v23 == -2147023150 )
      {
        LODWORD(v50) = 1;
        LODWORD(v54) = 2;
        v23 = 0;
      }
      (*(void (__fastcall **)(_QWORD *))(*v45 + 16LL))(v45);
    }
    if ( v23 )
      goto LABEL_32;
    v24 = *(_QWORD *)(v22 + 128);
    if ( v24 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      *(_QWORD *)(v22 + 128) = 0;
    }
    v25 = *(_QWORD *)(v22 + 120);
    if ( !v25 )
    {
LABEL_32:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
LABEL_33:
      v8[6] = SysAllocString(*((const OLECHAR **)a2 + 6));
      v28 = (OLECHAR *)v8[5];
      if ( v28 != *((OLECHAR **)a2 + 5) )
      {
        if ( v28 )
          SysFreeString(v28);
        v29 = SysStringLen(*((BSTR *)a2 + 5));
        v8[5] = SysAllocStringLen(*((const OLECHAR **)a2 + 5), v29);
      }
      goto LABEL_37;
    }
    v26 = (int)v54;
    LODWORD(v52) = v54;
    LODWORD(v51) = (_DWORD)v50;
    CInCritSec::CInCritSec((CInCritSec *)lpCriticalSection, (struct _RTL_CRITICAL_SECTION *)(v25 + 16));
    v48 = (struct IUnknown **)(v25 + 8 * (v26 + 6 + 4LL * (int)v51));
    v27 = *v48;
    v44 = v27;
    if ( v27 )
    {
      ((void (__fastcall *)(struct IUnknown *))v27->lpVtbl->AddRef)(v27);
    }
    else
    {
      v38 = *(unsigned int (__fastcall ****)(_QWORD, GUID *, _QWORD *))(v25
                                                                      + 8
                                                                      * (*(int *)(v25 + 328) + 4LL * *(int *)(v25 + 324))
                                                                      + 48);
      v47 = v38;
      if ( !v38 )
        goto LABEL_31;
      v45 = 0;
      if ( !(**v38)(v38, &IID_IClientSecurity, &v45) )
      {
        if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, struct IUnknown **))(*v45 + 40LL))(v45, v47, &v44) )
        {
          CSWbemProxyCache::SecureProxy(
            (CSWbemProxyCache *)v25,
            v44,
            (enum WbemAuthenticationLevelEnum)v51,
            (enum WbemImpersonationLevelEnum)v52);
          v39 = v44;
          *v48 = v44;
          ((void (__fastcall *)(struct IUnknown *))v39->lpVtbl->AddRef)(v39);
        }
        (*(void (__fastcall **)(_QWORD *))(*v45 + 16LL))(v45);
      }
    }
    v27 = v44;
LABEL_31:
    LeaveCriticalSection(lpCriticalSection[0]);
    *(_QWORD *)(v22 + 128) = v27;
    goto LABEL_32;
  }
  v8 = 0;
LABEL_37:
  *((_QWORD *)this + 7) = v8;
  if ( v8 )
    (*(void (__fastcall **)(_QWORD *))(*v8 + 8LL))(v8);
LABEL_39:
  v30 = (CSWbemPrivilegeSet *)CWin32DefaultArena::WbemMemAlloc(0x48u);
  v50 = v30;
  if ( v30 )
  {
    v31 = *((_QWORD *)this + 7);
    *(_QWORD *)v30 = &CWbemDispatchMgr::`vftable';
    *((_DWORD *)v30 + 2) = 0;
    *((_QWORD *)v30 + 3) = this;
    *((_QWORD *)v30 + 4) = v31;
    *((_QWORD *)v30 + 5) = 0;
    *((_QWORD *)v30 + 6) = 0;
    *((_QWORD *)v30 + 7) = 0;
    v32 = (GUID *)CWin32DefaultArena::WbemMemAlloc(0x28u);
    v51 = v32;
    if ( v32 )
    {
      *(_QWORD *)&v32->Data1 = &CWbemSchemaIDCache::`vftable';
      *(_DWORD *)v32->Data4 = 0;
      *(_QWORD *)&v32[1].Data1 = 0;
      *(_QWORD *)v32[1].Data4 = 0;
      *(_QWORD *)&v32[1].Data1 = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<ATL::CComBSTR const,CWbemDispID>,CWbemAllocator<CWbemDispID>>>::_Buyheadnode();
      *(_QWORD *)&v32[2].Data1 = v30;
    }
    else
    {
      v32 = 0;
    }
    *((_QWORD *)v30 + 8) = v32;
    v33 = *((_QWORD *)v30 + 4);
    if ( v33 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 8LL))(v33);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 8LL))(*((_QWORD *)this + 8));
    *((_QWORD *)v30 + 2) = *((_QWORD *)this + 8);
  }
  else
  {
    v30 = 0;
  }
  *((_QWORD *)this + 9) = v30;
  _InterlockedIncrement(&g_cObj);
  return this;
}

```

## disassembly

```asm
0x180009320  mov     [rsp-8+arg_18], r9
0x180009325  push    rbp
0x180009326  push    rbx
0x180009327  push    rsi
0x180009328  push    rdi
0x180009329  push    r12
0x18000932b  push    r13
0x18000932d  push    r14
0x18000932f  push    r15
0x180009331  lea     rbp, [rsp-17h]
0x180009336  sub     rsp, 98h
0x18000933d  mov     rsi, r9
0x180009340  mov     r13, rdx
0x180009343  mov     rdi, rcx
0x180009346  lea     rax, ??_7CSWbemObject@@6BISWbemObjectEx@@@; const CSWbemObject::`vftable'{for `ISWbemObjectEx'}
0x18000934d  mov     [rcx], rax
0x180009350  lea     rax, ??_7CSWbemObject@@6BIDispatchEx@@@; const CSWbemObject::`vftable'{for `IDispatchEx'}
0x180009357  mov     [rcx+8], rax
0x18000935b  lea     rax, ??_7CSWbemObject@@6BISWbemInternalObject@@@; const CSWbemObject::`vftable'{for `ISWbemInternalObject'}
0x180009362  mov     [rcx+10h], rax
0x180009366  lea     rax, ??_7CSWbemObject@@6BIObjectSafety@@@; const CSWbemObject::`vftable'{for `IObjectSafety'}
0x18000936d  mov     [rcx+18h], rax
0x180009371  lea     rax, ??_7CSWbemObject@@6BISupportErrorInfo@@@; const CSWbemObject::`vftable'{for `ISupportErrorInfo'}
0x180009378  mov     [rcx+20h], rax
0x18000937c  lea     rax, ??_7CSWbemObject@@6BIProvideClassInfo@@@; const CSWbemObject::`vftable'{for `IProvideClassInfo'}
0x180009383  mov     [rcx+28h], rax
0x180009387  xor     r12d, r12d
0x18000938a  mov     [rcx+38h], r12
0x18000938e  mov     [rcx+58h], r12
0x180009392  mov     byte ptr [rcx+60h], 1
0x180009396  mov     [rcx+68h], r12
0x18000939a  mov     [rcx+70h], r12d
0x18000939e  movzx   eax, byte ptr [rbp+4Fh+arg_20]
0x1800093a2  mov     [rcx+30h], al
0x1800093a5  mov     [rcx+40h], r8
0x1800093a9  mov     rax, [r8]
0x1800093ac  mov     rcx, r8
0x1800093af  mov     rax, [rax+8]
0x1800093b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093b8  mov     [rdi+50h], r12
0x1800093bc  test    r13, r13
0x1800093bf  jz      loc_1800098A4
0x1800093c5  mov     ecx, 0A8h
0x1800093ca  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800093d0  mov     r15, rax
0x1800093d3  mov     [rbp+4Fh+var_70], rax
0x1800093d7  test    rax, rax
0x1800093da  jz      loc_180009A94
0x1800093e0  lea     rax, ??_7CSWbemServices@@6BISWbemServicesEx@@@; const CSWbemServices::`vftable'{for `ISWbemServicesEx'}
0x1800093e7  mov     [r15], rax
0x1800093ea  lea     rax, ??_7CSWbemServices@@6BIDispatchEx@@@; const CSWbemServices::`vftable'{for `IDispatchEx'}
0x1800093f1  mov     [r15+8], rax
0x1800093f5  lea     rax, ??_7CSWbemServices@@6BISupportErrorInfo@@@; const CSWbemServices::`vftable'{for `ISupportErrorInfo'}
0x1800093fc  mov     [r15+10h], rax
0x180009400  lea     rax, ??_7CSWbemServices@@6BISWbemInternalServices@@@; const CSWbemServices::`vftable'{for `ISWbemInternalServices'}
0x180009407  mov     [r15+18h], rax
0x18000940b  lea     rax, ??_7CSWbemServices@@6BIProvideClassInfo@@@; const CSWbemServices::`vftable'{for `IProvideClassInfo'}
0x180009412  mov     [r15+20h], rax
0x180009416  mov     [r15+28h], r12
0x18000941a  mov     [r15+30h], r12
0x18000941e  lea     r14, ??_7CDispatchHelp@@6B@; const CDispatchHelp::`vftable'
0x180009425  mov     [r15+38h], r14
0x180009429  mov     [r15+50h], r12
0x18000942d  mov     [r15+58h], r12
0x180009431  mov     [r15+60h], r12
0x180009435  mov     [r15+40h], r12
0x180009439  mov     [r15+48h], r12d
0x18000943d  mov     [r15+88h], r12
0x180009444  mov     [r15+90h], r12
0x18000944b  mov     [r15+98h], r12
0x180009452  mov     [r15+0A0h], r12d
0x180009459  lock inc cs:?g_cObj@@3JA; long g_cObj
0x180009460  movups  xmm1, xmmword ptr cs:CLSID_SWbemServicesEx.Data1
0x180009467  movups  xmm0, xmmword ptr cs:IID_ISWbemServicesEx.Data1
0x18000946e  mov     [r15+60h], r15
0x180009472  movups  xmmword ptr [r15+68h], xmm0
0x180009477  movups  xmmword ptr [r15+78h], xmm1
0x18000947c  lea     rcx, aSwbemservicese; "SWbemServicesEx"
0x180009483  call    cs:__imp_SysAllocString
0x180009489  mov     [r15+40h], rax
0x18000948d  mov     rbx, [r13+88h]
0x180009494  mov     [rbp+4Fh+var_78], rbx
0x180009498  test    rbx, rbx
0x18000949b  jz      loc_1800096DF
0x1800094a1  mov     rax, [rbx]
0x1800094a4  mov     rcx, rbx
0x1800094a7  mov     rax, [rax+8]
0x1800094ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094b0  mov     ecx, 90h
0x1800094b5  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800094bb  mov     r12, rax
0x1800094be  mov     [rbp+4Fh+arg_10], rax
0x1800094c2  test    rax, rax
0x1800094c5  jz      loc_180009A84
0x1800094cb  lea     rax, ??_7CSWbemSecurity@@6BISWbemSecurity@@@; const CSWbemSecurity::`vftable'{for `ISWbemSecurity'}
0x1800094d2  mov     [r12], rax
0x1800094d6  lea     rax, ??_7CSWbemSecurity@@6BISupportErrorInfo@@@; const CSWbemSecurity::`vftable'{for `ISupportErrorInfo'}
0x1800094dd  mov     [r12+8], rax
0x1800094e2  lea     rax, ??_7CSWbemSecurity@@6BISWbemInternalSecurity@@@; const CSWbemSecurity::`vftable'{for `ISWbemInternalSecurity'}
0x1800094e9  mov     [r12+10h], rax
0x1800094ee  lea     rax, ??_7CSWbemSecurity@@6BIProvideClassInfo@@@; const CSWbemSecurity::`vftable'{for `IProvideClassInfo'}
0x1800094f5  mov     [r12+18h], rax
0x1800094fa  xor     esi, esi
0x1800094fc  mov     [r12+20h], rsi
0x180009501  mov     [r12+28h], r14
0x180009506  mov     [r12+40h], rsi
0x18000950b  mov     [r12+48h], rsi
0x180009510  mov     [r12+50h], rsi
0x180009515  mov     [r12+30h], rsi
0x18000951a  mov     [r12+38h], esi
0x18000951f  mov     [r12+78h], rsi
0x180009524  mov     [r12+80h], rsi
0x18000952c  movups  xmm1, xmmword ptr cs:CLSID_SWbemSecurity.Data1
0x180009533  movups  xmm0, xmmword ptr cs:IID_ISWbemSecurity.Data1
0x18000953a  mov     [r12+50h], r12
0x18000953f  movups  xmmword ptr [r12+58h], xmm0
0x180009545  movups  xmmword ptr [r12+68h], xmm1
0x18000954b  lea     rcx, aSwbemsecurity; "SWbemSecurity"
0x180009552  call    cs:__imp_SysAllocString
0x180009558  mov     [r12+30h], rax
0x18000955d  mov     dword ptr [r12+88h], 1
0x180009569  mov     r14, [rbx+20h]
0x18000956d  mov     [rbp+4Fh+arg_0], r14
0x180009571  test    r14, r14
0x180009574  jz      loc_180009AC1
0x18000957a  mov     rax, [r14]
0x18000957d  mov     rcx, r14
0x180009580  mov     rax, [rax+8]
0x180009584  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009589  mov     ecx, 88h
0x18000958e  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180009594  mov     rsi, rax
0x180009597  mov     [rbp+4Fh+var_80], rax
0x18000959b  test    rax, rax
0x18000959e  jz      loc_180009A8C
0x1800095a4  lea     rax, ??_7CSWbemPrivilegeSet@@6BISWbemPrivilegeSet@@@; const CSWbemPrivilegeSet::`vftable'{for `ISWbemPrivilegeSet'}
0x1800095ab  mov     [rsi], rax
0x1800095ae  lea     rax, ??_7CSWbemPrivilegeSet@@6BISupportErrorInfo@@@; const CSWbemPrivilegeSet::`vftable'{for `ISupportErrorInfo'}
0x1800095b5  mov     [rsi+8], rax
0x1800095b9  lea     rax, ??_7CSWbemPrivilegeSet@@6BIProvideClassInfo@@@; const CSWbemPrivilegeSet::`vftable'{for `IProvideClassInfo'}
0x1800095c0  mov     [rsi+10h], rax
0x1800095c4  lea     rax, ??_7CDispatchHelp@@6B@; const CDispatchHelp::`vftable'
0x1800095cb  mov     [rsi+20h], rax
0x1800095cf  xor     eax, eax
0x1800095d1  mov     [rsi+38h], rax
0x1800095d5  mov     [rsi+40h], rax
0x1800095d9  mov     [rsi+48h], rax
0x1800095dd  mov     [rsi+28h], rax
0x1800095e1  mov     [rsi+30h], eax
0x1800095e4  lea     rbx, [rsi+70h]
0x1800095e8  mov     [rbp+4Fh+arg_8], rbx
0x1800095ec  mov     [rbx], rax
0x1800095ef  mov     [rbx+8], rax
0x1800095f3  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBW4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@@std@@V?$CWbemAllocator@PEAVCSWbemPrivilege@@@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBW4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<WbemPrivilegeEnum const,CSWbemPrivilege *>,CWbemAllocator<CSWbemPrivilege *>>>::_Buyheadnode(void)
0x1800095f8  mov     [rbx], rax
0x1800095fb  movups  xmm1, xmmword ptr cs:CLSID_SWbemPrivilegeSet.Data1
0x180009602  movups  xmm0, xmmword ptr cs:IID_ISWbemPrivilegeSet.Data1
0x180009609  mov     [rsi+48h], rsi
0x18000960d  movups  xmmword ptr [rsi+50h], xmm0
0x180009611  movups  xmmword ptr [rsi+60h], xmm1
0x180009615  lea     rcx, aSwbemprivilege_0; "SWbemPrivilegeSet"
0x18000961c  call    cs:__imp_SysAllocString
0x180009622  mov     [rsi+28h], rax
0x180009626  mov     dword ptr [rsi+80h], 1
0x180009630  mov     byte ptr [rsi+18h], 1
0x180009634  mov     r15, r14
0x180009637  mov     rbx, [r14+70h]
0x18000963b  mov     rbx, [rbx]
0x18000963e  mov     r12, [rbp+4Fh+arg_8]
0x180009642  cmp     rbx, [r15+70h]
0x180009646  jnz     loc_180009976
0x18000964c  lock inc cs:?g_cObj@@3JA; long g_cObj
0x180009653  mov     r15, [rbp+4Fh+var_70]
0x180009657  mov     r12, [rbp+4Fh+arg_10]
0x18000965b  mov     rbx, [rbp+4Fh+var_78]
0x18000965f  mov     rsi, [rbp+4Fh+var_80]
0x180009663  mov     r14, [rbp+4Fh+arg_0]
0x180009667  mov     [r12+20h], rsi
0x18000966c  mov     rax, [r14]
0x18000966f  mov     rcx, r14
0x180009672  mov     rax, [rax+10h]
0x180009676  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000967b  mov     rsi, [rbx+78h]
0x18000967f  test    rsi, rsi
0x180009682  jz      short loc_180009693
0x180009684  mov     rax, [rsi]
0x180009687  mov     rcx, rsi
0x18000968a  mov     rax, [rax+8]
0x18000968e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009693  mov     [r12+78h], rsi
0x180009698  mov     rsi, [rbx+80h]
0x18000969f  test    rsi, rsi
0x1800096a2  jz      short loc_1800096B3
0x1800096a4  mov     rax, [rsi]
0x1800096a7  mov     rcx, rsi
0x1800096aa  mov     rax, [rax+8]
0x1800096ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096b3  mov     [r12+80h], rsi
0x1800096bb  lock inc cs:?g_cObj@@3JA; long g_cObj
0x1800096c2  mov     rsi, [rbp+4Fh+arg_18]
0x1800096c6  mov     [r15+88h], r12
0x1800096cd  mov     rax, [rbx]
0x1800096d0  mov     rcx, rbx
0x1800096d3  mov     rax, [rax+10h]
0x1800096d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096dc  xor     r12d, r12d
0x1800096df  test    rsi, rsi
0x1800096e2  jz      loc_18000984E
0x1800096e8  mov     rbx, [rsi+80h]
0x1800096ef  test    rbx, rbx
0x1800096f2  jz      loc_18000984E
0x1800096f8  mov     rax, [rbx]
0x1800096fb  mov     rcx, rbx
0x1800096fe  mov     rax, [rax+8]
0x180009702  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009707  mov     r14, [r15+88h]
0x18000970e  test    r14, r14
0x180009711  jz      loc_18000983F
0x180009717  mov     dword ptr [rbp+4Fh+arg_0], r12d
0x18000971b  mov     dword ptr [rbp+4Fh+arg_20], r12d
0x18000971f  mov     [rbp+4Fh+var_78], r12
0x180009723  mov     rax, [rbx]
0x180009726  lea     r8, [rbp+4Fh+var_78]
0x18000972a  lea     rdx, IID_IClientSecurity
0x180009731  mov     rcx, rbx
0x180009734  mov     rax, [rax]
0x180009737  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000973c  mov     esi, eax
0x18000973e  test    eax, eax
0x180009740  jnz     short loc_1800097AB
0x180009742  mov     dword ptr [rbp+4Fh+var_80], r12d
0x180009746  mov     dword ptr [rbp+4Fh+arg_10], r12d
0x18000974a  mov     dword ptr [rbp+4Fh+arg_8], r12d
0x18000974e  mov     rcx, [rbp+4Fh+var_78]
0x180009752  mov     rax, [rcx]
0x180009755  lea     rdx, [rbp+4Fh+arg_8]
0x180009759  mov     [rsp+0D0h+var_90], rdx
0x18000975e  mov     [rsp+0D0h+var_98], r12
0x180009763  lea     rdx, [rbp+4Fh+arg_20]
0x180009767  mov     [rsp+0D0h+var_A0], rdx
0x18000976c  lea     rdx, [rbp+4Fh+arg_0]
0x180009770  mov     [rsp+0D0h+var_A8], rdx
0x180009775  mov     [rsp+0D0h+var_B0], r12
0x18000977a  lea     r9, [rbp+4Fh+arg_10]
0x18000977e  lea     r8, [rbp+4Fh+var_80]
0x180009782  mov     rdx, rbx
0x180009785  mov     rax, [rax+18h]
0x180009789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000978e  mov     esi, eax
0x180009790  cmp     eax, 800706D2h
0x180009795  jz      loc_180009AEC
0x18000979b  mov     rcx, [rbp+4Fh+var_78]
0x18000979f  mov     rax, [rcx]
0x1800097a2  mov     rax, [rax+10h]
0x1800097a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097ab  test    esi, esi
0x1800097ad  jnz     loc_18000983F
0x1800097b3  mov     rcx, [r14+80h]
0x1800097ba  test    rcx, rcx
0x1800097bd  jz      short loc_1800097D2
0x1800097bf  mov     rax, [rcx]
0x1800097c2  mov     rax, [rax+10h]
0x1800097c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097cb  mov     [r14+80h], r12
0x1800097d2  mov     r12, [r14+78h]
0x1800097d6  test    r12, r12
0x1800097d9  jz      short loc_18000983F
0x1800097db  movsxd  rsi, dword ptr [rbp+4Fh+arg_20]
0x1800097df  mov     dword ptr [rbp+4Fh+arg_10], esi
0x1800097e2  mov     eax, dword ptr [rbp+4Fh+arg_0]
0x1800097e5  mov     dword ptr [rbp+4Fh+arg_8], eax
0x1800097e8  lea     rdx, [r12+10h]; struct _RTL_CRITICAL_SECTION *
0x1800097ed  lea     rcx, [rbp+4Fh+lpCriticalSection]; this
0x1800097f1  call    ??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x1800097f6  nop
0x1800097f7  movsxd  rcx, dword ptr [rbp+4Fh+arg_8]
0x1800097fb  lea     rax, [rsi+6]
0x1800097ff  lea     rax, [rax+rcx*4]
0x180009803  lea     rax, [r12+rax*8]
0x180009807  mov     [rbp+4Fh+var_60], rax
0x18000980b  mov     rsi, [rax]
0x18000980e  mov     [rbp+4Fh+var_80], rsi
0x180009812  test    rsi, rsi
0x180009815  jz      loc_1800099DB
0x18000981b  mov     rax, [rsi]
0x18000981e  mov     rcx, rsi
0x180009821  mov     rax, [rax+8]
0x180009825  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000982a  mov     rsi, [rbp+4Fh+var_80]
0x18000982e  mov     rcx, [rbp+4Fh+lpCriticalSection]; lpCriticalSection
0x180009832  call    cs:__imp_LeaveCriticalSection
0x180009838  mov     [r14+80h], rsi
0x18000983f  mov     rax, [rbx]
0x180009842  mov     rcx, rbx
0x180009845  mov     rax, [rax+10h]
0x180009849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000984e  mov     rcx, [r13+30h]; psz
0x180009852  call    cs:__imp_SysAllocString
0x180009858  mov     [r15+30h], rax
0x18000985c  mov     rcx, [r15+28h]; bstrString
  ... truncated ...
```
