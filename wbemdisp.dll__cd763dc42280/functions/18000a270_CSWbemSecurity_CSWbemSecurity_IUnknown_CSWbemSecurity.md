# CSWbemSecurity::CSWbemSecurity(IUnknown *,CSWbemSecurity *)

- ea: `0x18000a270`
- end: `0x18000a79f`
- name: `??0CSWbemSecurity@@QEAA@PEAUIUnknown@@PEAV0@@Z`
- size: `1327`
- prototype: `CSWbemSecurity *(CSWbemSecurity *__hidden this, struct IUnknown *, struct CSWbemSecurity *)`
- caller_count: `3`
- callee_count: `12`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180008800`
- `0x180009fd0`
- `0x18001f078`

## callees

- `0x180006550`
- `0x180006710`
- `0x180008de0`
- `0x18000a150`
- `0x18000a270`
- `0x18000a7b0`
- `0x18000b0ac`
- `0x18000fd64`
- `0x180013920`
- `0x1800197ec`
- `0x180019870`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000a30e`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a3d8`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a4c3`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a4e4`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a30e`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a3d8`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a4c3`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a4e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a588`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a588`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000a454`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000a454`
- `wbemcomn!_ThrowMemoryException_` at `0x18000a45e`
- `wbemcomn!_ThrowMemoryException_` at `0x18000a45e`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000a354`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000a42a`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000a6e9`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000a70e`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000a354`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000a42a`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000a6e9`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000a70e`

## string_xrefs

- `0x18000a307`: `SWbemSecurity`
- `0x18000a3d1`: `SWbemPrivilegeSet`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
CSWbemSecurity *__fastcall CSWbemSecurity::CSWbemSecurity(
        CSWbemSecurity *this,
        struct IUnknown *a2,
        struct ISWbemSecurity *a3)
{
  struct IUnknown *v4; // rdi
  struct ISWbemSecurityVtbl *lpVtbl; // r15
  GUID *v7; // rax
  GUID *v8; // rbp
  __int64 v9; // rbx
  char *v10; // rbx
  CSWbemProxyCache *v11; // rcx
  struct _COAUTHIDENTITY *CoAuthIdentity; // rax
  struct ISWbemSecurityVtbl *v13; // rax
  const OLECHAR *QueryInterface; // rcx
  struct ISWbemSecurityVtbl *v15; // rax
  const OLECHAR *AddRef; // rcx
  struct ISWbemSecurityVtbl *v17; // rax
  char v18; // cl
  __int64 v19; // rbp
  __int64 v20; // r15
  char *v21; // rsi
  struct IUnknown *v22; // rdi
  int v24; // edi
  struct _RTL_CRITICAL_SECTION *v25; // rsi
  __int64 v26; // r8
  unsigned int (__fastcall ***v27)(_QWORD, GUID *, __int64 *); // r12
  struct IUnknown *v28; // rcx
  struct IUnknown *v29; // rax
  CSWbemPrivilegeSet *v30; // rax
  struct IUnknown *v31; // rax
  CSWbemProxyCache *v32; // rax
  __int64 i; // rax
  int v34; // [rsp+20h] [rbp-78h]
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+30h] [rbp-68h] BYREF
  char v36[88]; // [rsp+40h] [rbp-58h] BYREF
  struct IUnknown *v38; // [rsp+B0h] [rbp+18h] BYREF
  __int64 v39; // [rsp+B8h] [rbp+20h] BYREF

  v4 = a2;
  *(_QWORD *)this = &CSWbemSecurity::`vftable'{for `ISWbemSecurity'};
  *((_QWORD *)this + 1) = &CSWbemSecurity::`vftable'{for `ISupportErrorInfo'};
  *((_QWORD *)this + 2) = &CSWbemSecurity::`vftable'{for `ISWbemInternalSecurity'};
  *((_QWORD *)this + 3) = &CSWbemSecurity::`vftable'{for `IProvideClassInfo'};
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = &CDispatchHelp::`vftable';
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_DWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 10) = this;
  *(GUID *)((char *)this + 88) = IID_ISWbemSecurity;
  *(GUID *)((char *)this + 104) = CLSID_SWbemSecurity;
  *((_QWORD *)this + 6) = SysAllocString(L"SWbemSecurity");
  *((_DWORD *)this + 34) = 1;
  _InterlockedIncrement(&g_cObj);
  if ( a3 )
  {
    lpVtbl = a3[4].lpVtbl;
    if ( lpVtbl )
    {
      (*((void (__fastcall **)(struct ISWbemSecurityVtbl *))lpVtbl->QueryInterface + 1))(a3[4].lpVtbl);
      v7 = (GUID *)CWin32DefaultArena::WbemMemAlloc(0x88u);
      v8 = v7;
      v38 = (struct IUnknown *)v7;
      if ( v7 )
      {
        *(_QWORD *)&v7->Data1 = &CSWbemPrivilegeSet::`vftable'{for `ISWbemPrivilegeSet'};
        *(_QWORD *)v7->Data4 = &CSWbemPrivilegeSet::`vftable'{for `ISupportErrorInfo'};
        *(_QWORD *)&v7[1].Data1 = &CSWbemPrivilegeSet::`vftable'{for `IProvideClassInfo'};
        *(_QWORD *)&v7[2].Data1 = &CDispatchHelp::`vftable';
        *(_QWORD *)v7[3].Data4 = 0;
        *(_QWORD *)&v7[4].Data1 = 0;
        *(_QWORD *)v7[4].Data4 = 0;
        *(_QWORD *)v7[2].Data4 = 0;
        v7[3].Data1 = 0;
        *(_QWORD *)&v7[7].Data1 = 0;
        *(_QWORD *)v7[7].Data4 = 0;
        *(_QWORD *)&v7[7].Data1 = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<enum WbemPrivilegeEnum const,CSWbemPrivilege *>,CWbemAllocator<CSWbemPrivilege *>>>::_Buyheadnode();
        *(_QWORD *)v8[4].Data4 = v8;
        v8[5] = IID_ISWbemPrivilegeSet;
        v8[6] = CLSID_SWbemPrivilegeSet;
        *(_QWORD *)v8[2].Data4 = SysAllocString(L"SWbemPrivilegeSet");
        v8[8].Data1 = 1;
        v8[1].Data4[0] = 1;
        v9 = *(_QWORD *)lpVtbl[1].Release;
        while ( (ULONG (__stdcall *)(ISWbemSecurity *))v9 != lpVtbl[1].Release )
        {
          v24 = *(_DWORD *)(v9 + 32);
          v25 = *(struct _RTL_CRITICAL_SECTION **)(v9 + 40);
          ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v25->DebugInfo->CriticalSection)(v25);
          LODWORD(lpCriticalSection[0]) = v24;
          lpCriticalSection[1] = v25;
          LOBYTE(v34) = byte_180045B58;
          std::_Tree<std::_Tmap_traits<enum WbemPrivilegeEnum,CSWbemPrivilege *,std::less<int>,CWbemAllocator<CSWbemPrivilege *>,0>>::_Insert_nohint<std::pair<enum WbemPrivilegeEnum const,CSWbemPrivilege *>,std::_Nil>(
            &v8[7],
            v36,
            v26,
            lpCriticalSection,
            v34);
          if ( !*(_BYTE *)(v9 + 25) )
          {
            if ( *(_BYTE *)(*(_QWORD *)(v9 + 16) + 25LL) )
            {
              for ( i = *(_QWORD *)(v9 + 8); !*(_BYTE *)(i + 25); i = *(_QWORD *)(i + 8) )
              {
                if ( v9 != *(_QWORD *)(i + 16) )
                  break;
                v9 = i;
              }
              v9 = i;
            }
            else
            {
              v9 = std::_Tree_val<std::_Tree_simple_types<std::pair<enum WbemPrivilegeEnum const,CSWbemPrivilege *>>>::_Min();
            }
          }
        }
        _InterlockedIncrement(&g_cObj);
        v4 = a2;
      }
      else
      {
        v8 = 0;
      }
      *((_QWORD *)this + 4) = v8;
      (*((void (__fastcall **)(struct ISWbemSecurityVtbl *))lpVtbl->QueryInterface + 2))(lpVtbl);
    }
    v10 = (char *)CWin32DefaultArena::WbemMemAlloc(0x150u);
    v38 = (struct IUnknown *)v10;
    if ( v10 )
    {
      *(_QWORD *)v10 = &CSWbemProxyCache::`vftable';
      if ( !InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(v10 + 16), 0) )
        _ThrowMemoryException_();
      *((_DWORD *)v10 + 2) = 1;
      *((_QWORD *)v10 + 35) = 0;
      *((_QWORD *)v10 + 36) = 0;
      *((_QWORD *)v10 + 37) = 0;
      *((_QWORD *)v10 + 38) = 0;
      *((_QWORD *)v10 + 39) = 0;
      *((_WORD *)v10 + 160) = 1;
      v11 = (CSWbemProxyCache *)a3[15].lpVtbl;
      if ( v11 )
        CoAuthIdentity = CSWbemProxyCache::GetCoAuthIdentity(v11);
      else
        CoAuthIdentity = 0;
      *((_QWORD *)v10 + 35) = CoAuthIdentity;
      v13 = a3[15].lpVtbl;
      if ( v13 )
        QueryInterface = (const OLECHAR *)v13[3].QueryInterface;
      else
        QueryInterface = 0;
      *((_QWORD *)v10 + 36) = SysAllocString(QueryInterface);
      v15 = a3[15].lpVtbl;
      if ( v15 )
        AddRef = (const OLECHAR *)v15[3].AddRef;
      else
        AddRef = 0;
      *((_QWORD *)v10 + 37) = SysAllocString(AddRef);
      v17 = a3[15].lpVtbl;
      if ( v17 )
        v18 = BYTE1(v17[3].GetTypeInfo);
      else
        v18 = 0;
      v10[321] = v18;
      CSWbemProxyCache::InitializeCache((CSWbemProxyCache *)v10, v4, a3, 1, 1);
    }
    else
    {
      v10 = 0;
    }
    *((_QWORD *)this + 15) = v10;
    if ( v10 )
    {
      v19 = *((int *)v10 + 82);
      v20 = *((int *)v10 + 81);
      CInCritSec::CInCritSec((CInCritSec *)lpCriticalSection, (struct _RTL_CRITICAL_SECTION *)(v10 + 16));
      v21 = &v10[32 * v20 + 8 * v19];
      v22 = (struct IUnknown *)*((_QWORD *)v21 + 6);
      v38 = v22;
      if ( v22 )
      {
        ((void (__fastcall *)(struct IUnknown *))v22->lpVtbl->AddRef)(v22);
      }
      else
      {
        v27 = *(unsigned int (__fastcall ****)(_QWORD, GUID *, __int64 *))&v10[32 * *((int *)v10 + 81)
                                                                             + 48
                                                                             + 8 * *((int *)v10 + 82)];
        if ( !v27 )
          goto LABEL_24;
        v39 = 0;
        if ( !(**v27)(v27, &IID_IClientSecurity, &v39) )
        {
          if ( !(*(unsigned int (__fastcall **)(__int64, _QWORD, struct IUnknown **))(*(_QWORD *)v39 + 40LL))(
                  v39,
                  v27,
                  &v38) )
          {
            CSWbemProxyCache::SecureProxy(
              (CSWbemProxyCache *)v10,
              v38,
              (enum WbemAuthenticationLevelEnum)v20,
              (enum WbemImpersonationLevelEnum)v19);
            v28 = v38;
            *((_QWORD *)v21 + 6) = v38;
            ((void (__fastcall *)(struct IUnknown *))v28->lpVtbl->AddRef)(v28);
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
        }
      }
      v22 = v38;
LABEL_24:
      LeaveCriticalSection(lpCriticalSection[0]);
      *((_QWORD *)this + 16) = v22;
    }
  }
  else
  {
    v29 = (struct IUnknown *)CWin32DefaultArena::WbemMemAlloc(0x88u);
    v38 = v29;
    if ( v29 )
      v30 = CSWbemPrivilegeSet::CSWbemPrivilegeSet((CSWbemPrivilegeSet *)v29);
    else
      v30 = 0;
    *((_QWORD *)this + 4) = v30;
    v31 = (struct IUnknown *)CWin32DefaultArena::WbemMemAlloc(0x150u);
    v38 = v31;
    if ( v31 )
      v32 = CSWbemProxyCache::CSWbemProxyCache((CSWbemProxyCache *)v31, v4, 0);
    else
      v32 = 0;
    *((_QWORD *)this + 15) = v32;
    if ( v32 )
      *((_QWORD *)this + 16) = CSWbemProxyCache::GetProxy(
                                 v32,
                                 (enum WbemAuthenticationLevelEnum)*((_DWORD *)v32 + 81),
                                 (enum WbemImpersonationLevelEnum)*((_DWORD *)v32 + 82),
                                 0);
  }
  return this;
}

```

## disassembly

```asm
0x18000a270  mov     [rsp+arg_8], rdx
0x18000a275  mov     [rsp+arg_0], rcx
0x18000a27a  push    rbx
0x18000a27b  push    rbp
0x18000a27c  push    rsi
0x18000a27d  push    rdi
0x18000a27e  push    r12
0x18000a280  push    r13
0x18000a282  push    r14
0x18000a284  push    r15
0x18000a286  sub     rsp, 58h
0x18000a28a  mov     r13, r8
0x18000a28d  mov     rdi, rdx
0x18000a290  mov     r14, rcx
0x18000a293  lea     rax, ??_7CSWbemSecurity@@6BISWbemSecurity@@@; const CSWbemSecurity::`vftable'{for `ISWbemSecurity'}
0x18000a29a  mov     [rcx], rax
0x18000a29d  lea     rax, ??_7CSWbemSecurity@@6BISupportErrorInfo@@@; const CSWbemSecurity::`vftable'{for `ISupportErrorInfo'}
0x18000a2a4  mov     [rcx+8], rax
0x18000a2a8  lea     rax, ??_7CSWbemSecurity@@6BISWbemInternalSecurity@@@; const CSWbemSecurity::`vftable'{for `ISWbemInternalSecurity'}
0x18000a2af  mov     [rcx+10h], rax
0x18000a2b3  lea     rax, ??_7CSWbemSecurity@@6BIProvideClassInfo@@@; const CSWbemSecurity::`vftable'{for `IProvideClassInfo'}
0x18000a2ba  mov     [rcx+18h], rax
0x18000a2be  xor     esi, esi
0x18000a2c0  mov     [rcx+20h], rsi
0x18000a2c4  lea     rbx, ??_7CDispatchHelp@@6B@; const CDispatchHelp::`vftable'
0x18000a2cb  mov     [rcx+28h], rbx
0x18000a2cf  mov     [rcx+40h], rsi
0x18000a2d3  mov     [rcx+48h], rsi
0x18000a2d7  mov     [rcx+50h], rsi
0x18000a2db  mov     [rcx+30h], rsi
0x18000a2df  mov     [rcx+38h], esi
0x18000a2e2  mov     [rcx+78h], rsi
0x18000a2e6  mov     [rcx+80h], rsi
0x18000a2ed  movups  xmm1, xmmword ptr cs:CLSID_SWbemSecurity.Data1
0x18000a2f4  movups  xmm0, xmmword ptr cs:IID_ISWbemSecurity.Data1
0x18000a2fb  mov     [rcx+50h], rcx
0x18000a2ff  movups  xmmword ptr [rcx+58h], xmm0
0x18000a303  movups  xmmword ptr [rcx+68h], xmm1
0x18000a307  lea     rcx, aSwbemsecurity; "SWbemSecurity"
0x18000a30e  call    cs:__imp_SysAllocString
0x18000a314  mov     [r14+30h], rax
0x18000a318  mov     dword ptr [r14+88h], 1
0x18000a323  lock inc cs:?g_cObj@@3JA; long g_cObj
0x18000a32a  test    r13, r13
0x18000a32d  jz      loc_18000A6E4
0x18000a333  mov     r15, [r13+20h]
0x18000a337  test    r15, r15
0x18000a33a  jz      loc_18000A425
0x18000a340  mov     rax, [r15]
0x18000a343  mov     rcx, r15
0x18000a346  mov     rax, [rax+8]
0x18000a34a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a34f  mov     ecx, 88h
0x18000a354  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000a35a  mov     rbp, rax
0x18000a35d  mov     [rsp+98h+arg_10], rax
0x18000a365  test    rax, rax
0x18000a368  jz      loc_18000A6D4
0x18000a36e  lea     rax, ??_7CSWbemPrivilegeSet@@6BISWbemPrivilegeSet@@@; const CSWbemPrivilegeSet::`vftable'{for `ISWbemPrivilegeSet'}
0x18000a375  mov     [rbp+0], rax
0x18000a379  lea     rax, ??_7CSWbemPrivilegeSet@@6BISupportErrorInfo@@@; const CSWbemPrivilegeSet::`vftable'{for `ISupportErrorInfo'}
0x18000a380  mov     [rbp+8], rax
0x18000a384  lea     rax, ??_7CSWbemPrivilegeSet@@6BIProvideClassInfo@@@; const CSWbemPrivilegeSet::`vftable'{for `IProvideClassInfo'}
0x18000a38b  mov     [rbp+10h], rax
0x18000a38f  mov     [rbp+20h], rbx
0x18000a393  mov     [rbp+38h], rsi
0x18000a397  mov     [rbp+40h], rsi
0x18000a39b  mov     [rbp+48h], rsi
0x18000a39f  mov     [rbp+28h], rsi
0x18000a3a3  mov     [rbp+30h], esi
0x18000a3a6  mov     [rbp+70h], rsi
0x18000a3aa  mov     [rbp+78h], rsi
0x18000a3ae  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBW4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@@std@@V?$CWbemAllocator@PEAVCSWbemPrivilege@@@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBW4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<WbemPrivilegeEnum const,CSWbemPrivilege *>,CWbemAllocator<CSWbemPrivilege *>>>::_Buyheadnode(void)
0x18000a3b3  mov     [rbp+70h], rax
0x18000a3b7  movups  xmm1, xmmword ptr cs:CLSID_SWbemPrivilegeSet.Data1
0x18000a3be  movups  xmm0, xmmword ptr cs:IID_ISWbemPrivilegeSet.Data1
0x18000a3c5  mov     [rbp+48h], rbp
0x18000a3c9  movups  xmmword ptr [rbp+50h], xmm0
0x18000a3cd  movups  xmmword ptr [rbp+60h], xmm1
0x18000a3d1  lea     rcx, aSwbemprivilege_0; "SWbemPrivilegeSet"
0x18000a3d8  call    cs:__imp_SysAllocString
0x18000a3de  mov     [rbp+28h], rax
0x18000a3e2  mov     dword ptr [rbp+80h], 1
0x18000a3ec  mov     byte ptr [rbp+18h], 1
0x18000a3f0  mov     rbx, [r15+70h]
0x18000a3f4  mov     rbx, [rbx]
0x18000a3f7  cmp     rbx, [r15+70h]
0x18000a3fb  jnz     loc_18000A5A9
0x18000a401  lock inc cs:?g_cObj@@3JA; long g_cObj
0x18000a408  mov     rdi, [rsp+98h+arg_8]
0x18000a410  xor     esi, esi
0x18000a412  mov     [r14+20h], rbp
0x18000a416  mov     rax, [r15]
0x18000a419  mov     rcx, r15
0x18000a41c  mov     rax, [rax+10h]
0x18000a420  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a425  mov     ecx, 150h
0x18000a42a  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000a430  mov     rbx, rax
0x18000a433  mov     [rsp+98h+arg_10], rax
0x18000a43b  test    rax, rax
0x18000a43e  jz      loc_18000A60B
0x18000a444  lea     rax, ??_7CSWbemProxyCache@@6B@; const CSWbemProxyCache::`vftable'
0x18000a44b  mov     [rbx], rax
0x18000a44e  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000a452  xor     edx, edx; dwSpinCount
0x18000a454  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000a45a  test    eax, eax
0x18000a45c  jnz     short loc_18000A465
0x18000a45e  call    cs:__imp_?_ThrowMemoryException_@@YAXXZ; _ThrowMemoryException_(void)
0x18000a464  nop
0x18000a465  mov     dword ptr [rbx+8], 1
0x18000a46c  mov     [rbx+118h], rsi
0x18000a473  mov     [rbx+120h], rsi
0x18000a47a  mov     [rbx+128h], rsi
0x18000a481  mov     [rbx+130h], rsi
0x18000a488  mov     [rbx+138h], rsi
0x18000a48f  mov     word ptr [rbx+140h], 1
0x18000a498  mov     rcx, [r13+78h]; this
0x18000a49c  test    rcx, rcx
0x18000a49f  jnz     loc_18000A6CA
0x18000a4a5  mov     rax, rsi
0x18000a4a8  mov     [rbx+118h], rax
0x18000a4af  mov     rax, [r13+78h]
0x18000a4b3  test    rax, rax
0x18000a4b6  jz      loc_18000A6DC
0x18000a4bc  mov     rcx, [rax+120h]; psz
0x18000a4c3  call    cs:__imp_SysAllocString
0x18000a4c9  mov     [rbx+120h], rax
0x18000a4d0  mov     rax, [r13+78h]
0x18000a4d4  test    rax, rax
0x18000a4d7  jz      loc_18000A786
0x18000a4dd  mov     rcx, [rax+128h]; psz
0x18000a4e4  call    cs:__imp_SysAllocString
0x18000a4ea  mov     [rbx+128h], rax
0x18000a4f1  mov     rax, [r13+78h]
0x18000a4f5  test    rax, rax
0x18000a4f8  jz      loc_18000A755
0x18000a4fe  movzx   ecx, byte ptr [rax+141h]
0x18000a505  mov     [rbx+141h], cl
0x18000a50b  mov     byte ptr [rsp+98h+var_78], 1; bool
0x18000a510  mov     r9b, 1; bool
0x18000a513  mov     r8, r13; struct ISWbemSecurity *
0x18000a516  mov     rdx, rdi; struct IUnknown *
0x18000a519  mov     rcx, rbx; this
0x18000a51c  call    ?InitializeCache@CSWbemProxyCache@@AEAAXPEAUIUnknown@@PEAUISWbemSecurity@@_N2@Z; CSWbemProxyCache::InitializeCache(IUnknown *,ISWbemSecurity *,bool,bool)
0x18000a521  nop
0x18000a522  mov     [r14+78h], rbx
0x18000a526  test    rbx, rbx
0x18000a529  jz      short loc_18000A595
0x18000a52b  movsxd  rbp, dword ptr [rbx+148h]
0x18000a532  movsxd  r15, dword ptr [rbx+144h]
0x18000a539  lea     rdx, [rbx+10h]; struct _RTL_CRITICAL_SECTION *
0x18000a53d  lea     rcx, [rsp+98h+lpCriticalSection]; this
0x18000a542  call    ??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x18000a547  nop
0x18000a548  lea     rcx, ds:0[r15*4]
0x18000a550  add     rcx, rbp
0x18000a553  lea     rsi, [rbx+rcx*8]
0x18000a557  mov     rdi, [rsi+30h]
0x18000a55b  mov     [rsp+98h+arg_10], rdi
0x18000a563  test    rdi, rdi
0x18000a566  jz      loc_18000A613
0x18000a56c  mov     rax, [rdi]
0x18000a56f  mov     rcx, rdi
0x18000a572  mov     rax, [rax+8]
0x18000a576  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a57b  mov     rdi, [rsp+98h+arg_10]
0x18000a583  mov     rcx, [rsp+98h+lpCriticalSection]; lpCriticalSection
0x18000a588  call    cs:__imp_LeaveCriticalSection
0x18000a58e  mov     [r14+80h], rdi
0x18000a595  mov     rax, r14
0x18000a598  add     rsp, 58h
0x18000a59c  pop     r15
0x18000a59e  pop     r14
0x18000a5a0  pop     r13
0x18000a5a2  pop     r12
0x18000a5a4  pop     rdi
0x18000a5a5  pop     rsi
0x18000a5a6  pop     rbp
0x18000a5a7  pop     rbx
0x18000a5a8  retn
0x18000a5a9  mov     edi, [rbx+20h]
0x18000a5ac  mov     rsi, [rbx+28h]
0x18000a5b0  mov     rax, [rsi]
0x18000a5b3  mov     rcx, rsi
0x18000a5b6  mov     rax, [rax+8]
0x18000a5ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5bf  mov     dword ptr [rsp+98h+lpCriticalSection], edi
0x18000a5c3  mov     [rsp+98h+var_60], rsi
0x18000a5c8  movzx   eax, cs:byte_180045B58
0x18000a5cf  mov     byte ptr [rsp+98h+var_78], al
0x18000a5d3  lea     r9, [rsp+98h+lpCriticalSection]
0x18000a5d8  lea     rdx, [rsp+98h+var_58]
0x18000a5dd  lea     rcx, [rbp+70h]
0x18000a5e1  call    ??$_Insert_nohint@U?$pair@$$CBW4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@@std@@U_Nil@2@@?$_Tree@V?$_Tmap_traits@W4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@U?$less@H@std@@V?$CWbemAllocator@PEAVCSWbemPrivilege@@@@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@@std@@@std@@@std@@@std@@_N@1@_N$$QEAU?$pair@$$CBW4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@@1@U_Nil@1@@Z; std::_Tree<std::_Tmap_traits<WbemPrivilegeEnum,CSWbemPrivilege *,std::less<int>,CWbemAllocator<CSWbemPrivilege *>,0>>::_Insert_nohint<std::pair<WbemPrivilegeEnum const,CSWbemPrivilege *>,std::_Nil>(bool,std::pair<WbemPrivilegeEnum const,CSWbemPrivilege *> &&,std::_Nil)
0x18000a5e6  cmp     byte ptr [rbx+19h], 0
0x18000a5ea  jnz     loc_18000A3F7
0x18000a5f0  mov     rcx, [rbx+10h]
0x18000a5f4  cmp     byte ptr [rcx+19h], 0
0x18000a5f8  jnz     loc_18000A761
0x18000a5fe  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBW4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<WbemPrivilegeEnum const,CSWbemPrivilege *>>>::_Min(std::_Tree_node<std::pair<WbemPrivilegeEnum const,CSWbemPrivilege *>,void *> *)
0x18000a603  mov     rbx, rax
0x18000a606  jmp     loc_18000A3F7
0x18000a60b  mov     rbx, rsi
0x18000a60e  jmp     loc_18000A522
0x18000a613  movsxd  rcx, dword ptr [rbx+144h]
0x18000a61a  movsxd  rax, dword ptr [rbx+148h]
0x18000a621  lea     rcx, [rax+rcx*4]
0x18000a625  mov     r12, [rbx+rcx*8+30h]
0x18000a62a  test    r12, r12
0x18000a62d  jz      loc_18000A583
0x18000a633  mov     [rsp+98h+arg_18], 0
0x18000a63f  mov     rax, [r12]
0x18000a643  lea     r8, [rsp+98h+arg_18]
0x18000a64b  lea     rdx, IID_IClientSecurity
0x18000a652  mov     rcx, r12
0x18000a655  mov     rax, [rax]
0x18000a658  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a65d  test    eax, eax
0x18000a65f  jnz     loc_18000A57B
0x18000a665  mov     rcx, [rsp+98h+arg_18]
0x18000a66d  mov     rax, [rcx]
0x18000a670  lea     r8, [rsp+98h+arg_10]
0x18000a678  mov     rdx, r12
0x18000a67b  mov     rax, [rax+28h]
0x18000a67f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a684  test    eax, eax
0x18000a686  jnz     short loc_18000A6B6
0x18000a688  mov     r9d, ebp; enum WbemImpersonationLevelEnum
0x18000a68b  mov     r8d, r15d; enum WbemAuthenticationLevelEnum
0x18000a68e  mov     rdx, [rsp+98h+arg_10]; struct IUnknown *
0x18000a696  mov     rcx, rbx; this
0x18000a699  call    ?SecureProxy@CSWbemProxyCache@@QEAAXPEAUIUnknown@@W4WbemAuthenticationLevelEnum@@W4WbemImpersonationLevelEnum@@@Z; CSWbemProxyCache::SecureProxy(IUnknown *,WbemAuthenticationLevelEnum,WbemImpersonationLevelEnum)
0x18000a69e  mov     rcx, [rsp+98h+arg_10]
0x18000a6a6  mov     [rsi+30h], rcx
0x18000a6aa  mov     rax, [rcx]
0x18000a6ad  mov     rax, [rax+8]
0x18000a6b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6b6  mov     rcx, [rsp+98h+arg_18]
0x18000a6be  mov     rax, [rcx]
0x18000a6c1  mov     rax, [rax+10h]
0x18000a6c5  jmp     loc_18000A576
0x18000a6ca  call    ?GetCoAuthIdentity@CSWbemProxyCache@@QEAAPEAU_COAUTHIDENTITY@@XZ; CSWbemProxyCache::GetCoAuthIdentity(void)
0x18000a6cf  jmp     loc_18000A4A8
0x18000a6d4  mov     rbp, rsi
0x18000a6d7  jmp     loc_18000A412
0x18000a6dc  mov     rcx, rsi
0x18000a6df  jmp     loc_18000A4C3
0x18000a6e4  mov     ecx, 88h
0x18000a6e9  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000a6ef  mov     [rsp+98h+arg_10], rax
0x18000a6f7  test    rax, rax
0x18000a6fa  jz      short loc_18000A75C
0x18000a6fc  mov     rcx, rax; this
0x18000a6ff  call    ??0CSWbemPrivilegeSet@@QEAA@XZ; CSWbemPrivilegeSet::CSWbemPrivilegeSet(void)
0x18000a704  nop
0x18000a705  mov     [r14+20h], rax
0x18000a709  mov     ecx, 150h
0x18000a70e  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000a714  mov     [rsp+98h+arg_10], rax
0x18000a71c  test    rax, rax
0x18000a71f  jnz     short loc_18000A78E
0x18000a721  mov     rax, rsi
0x18000a724  mov     [r14+78h], rax
0x18000a728  test    rax, rax
0x18000a72b  jz      loc_18000A595
0x18000a731  xor     r9d, r9d; bool
0x18000a734  mov     r8d, [rax+148h]; enum WbemImpersonationLevelEnum
0x18000a73b  mov     edx, [rax+144h]; enum WbemAuthenticationLevelEnum
0x18000a741  mov     rcx, rax; this
0x18000a744  call    ?GetProxy@CSWbemProxyCache@@QEAAPEAUIUnknown@@W4WbemAuthenticationLevelEnum@@W4WbemImpersonationLevelEnum@@_N@Z; CSWbemProxyCache::GetProxy(WbemAuthenticationLevelEnum,WbemImpersonationLevelEnum,bool)
0x18000a749  mov     [r14+80h], rax
0x18000a750  jmp     loc_18000A595
0x18000a755  xor     cl, cl
0x18000a757  jmp     loc_18000A505
0x18000a75c  mov     rax, rsi
0x18000a75f  jmp     short loc_18000A705
0x18000a761  mov     rax, [rbx+8]
0x18000a765  cmp     byte ptr [rax+19h], 0
0x18000a769  jnz     short loc_18000A77E
0x18000a76b  cmp     rbx, [rax+10h]
0x18000a76f  jnz     short loc_18000A77E
0x18000a771  mov     rbx, rax
0x18000a774  mov     rax, [rax+8]
0x18000a778  cmp     byte ptr [rax+19h], 0
0x18000a77c  jz      short loc_18000A76B
0x18000a77e  mov     rbx, rax
0x18000a781  jmp     loc_18000A3F7
0x18000a786  mov     rcx, rsi
0x18000a789  jmp     loc_18000A4E4
0x18000a78e  xor     r8d, r8d; struct ISWbemSecurity *
0x18000a791  mov     rdx, rdi; struct IUnknown *
0x18000a794  mov     rcx, rax; this
0x18000a797  call    ??0CSWbemProxyCache@@QEAA@PEAUIUnknown@@PEAVCSWbemSecurity@@@Z; CSWbemProxyCache::CSWbemProxyCache(IUnknown *,CSWbemSecurity *)
0x18000a79c  jmp     short loc_18000A724
```
