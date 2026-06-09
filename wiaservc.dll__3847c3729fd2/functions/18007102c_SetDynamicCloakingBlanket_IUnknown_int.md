# SetDynamicCloakingBlanket(IUnknown *,int)

- ea: `0x18007102c`
- end: `0x1800712e2`
- name: `?SetDynamicCloakingBlanket@@YAJPEAUIUnknown@@H@Z`
- size: `694`
- prototype: `__int64 __fastcall(struct IUnknown *, int)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18006eee0`
- `0x18006f5ec`
- `0x18006f748`

## callees

- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x1800202b8`
- `0x18002de18`
- `0x18002def8`
- `0x18007102c`
- `0x180078010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18007125f`
- `ole32!CoTaskMemFree` at `0x18007125f`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180071283`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180071283`

## string_xrefs

- `0x180071107`: `QueryInterface for IClientSecurity failed (0x%08X)`
- `0x180071129`: `QueryInterface for IClientSecurity failed (0x%08X)`
- `0x180071291`: `CoImpersonateClient failed (0x%08X)`
- `0x1800712b5`: `CoImpersonateClient failed (0x%08X)`
- `0x180071208`: `IClientSecurity::SetBlanket (RPC_C_IMP_LEVEL_IMPERSONATE (previous: 0x%08X), EOAC_DYNAMIC_CLOAKING (previous: 0x%08X)) failed (0x%08X)`
- `0x180071234`: `IClientSecurity::SetBlanket (RPC_C_IMP_LEVEL_IMPERSONATE (previous: 0x%08X), EOAC_DYNAMIC_CLOAKING (previous: 0x%08X)) failed (0x%08X)`
- `0x18007118c`: `IClientSecurity::QueryBlanket failed (0x%08X)`
- `0x1800711ae`: `IClientSecurity::QueryBlanket failed (0x%08X)`

## pseudocode

```c
__int64 __fastcall SetDynamicCloakingBlanket(struct IUnknown *a1, int a2)
{
  int v4; // esi
  char *v5; // rbx
  void *v6; // rdx
  void **lpMem; // rax
  void *v8; // rdx
  __int64 v9; // rcx
  HRESULT v10; // edi
  char *v11; // rbx
  void *v12; // rdx
  void **v13; // rax
  void *v14; // rdx
  __int64 v15; // rcx
  char *v16; // rbx
  void *v17; // rdx
  char *v18; // rbx
  void *v19; // rdx
  char *v20; // rbx
  void *v21; // rdx
  void **v22; // rax
  void *v23; // rdx
  __int64 v24; // rcx
  unsigned int v26; // [rsp+50h] [rbp-20h] BYREF
  unsigned int v27; // [rsp+54h] [rbp-1Ch] BYREF
  __int64 v28; // [rsp+58h] [rbp-18h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-10h] BYREF
  __int64 v30; // [rsp+68h] [rbp-8h] BYREF
  int v31; // [rsp+B8h] [rbp+48h] BYREF
  int v32; // [rsp+C0h] [rbp+50h] BYREF
  int v33; // [rsp+C8h] [rbp+58h] BYREF

  v28 = 0;
  pv = 0;
  v27 = 0;
  v26 = 0;
  v33 = 0;
  v32 = 0;
  v31 = 0;
  v30 = 0;
  if ( a2 )
  {
    v4 = SafeCoRevertToSelf();
    if ( v4 < 0 )
    {
      v5 = (char *)WiaTrace_TraceLog("SafeCoRevertToSelf failed (0x%08X)");
      WriteDbgTraceErrorWI("SetDynamicCloakingBlanket", v5);
      WiaTrcLib::Free((WiaTrcLib *)v5, v6);
      lpMem = (void **)WiaTrace_Trace("SafeCoRevertToSelf failed (0x%08X)", v4);
      WiaTrace_ProcessTrace_Ex(v9, v8, (void *)"SetDynamicCloakingBlanket", 1, lpMem);
      v10 = v4;
      goto LABEL_13;
    }
  }
  else
  {
    v4 = 0;
  }
  v10 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a1->lpVtbl->QueryInterface)(
          a1,
          &IID_IClientSecurity,
          &v28);
  if ( v10 >= 0 )
  {
    v10 = (*(__int64 (__fastcall **)(__int64, struct IUnknown *, unsigned int *, unsigned int *, LPVOID *, int *, int *, __int64 *, int *))(*(_QWORD *)v28 + 24LL))(
            v28,
            a1,
            &v27,
            &v26,
            &pv,
            &v33,
            &v32,
            &v30,
            &v31);
    if ( v10 >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(__int64, struct IUnknown *, _QWORD, _QWORD, LPVOID, int, int, __int64, int))(*(_QWORD *)v28 + 32LL))(
              v28,
              a1,
              v27,
              v26,
              pv,
              v33,
              3,
              v30,
              64);
      if ( v10 >= 0 )
        goto LABEL_13;
      v18 = (char *)WiaTrace_TraceLog("IClientSecurity::SetBlanket (RPC_C_IMP_LEVEL_IMPERSONATE (previous: 0x%08X), EOAC_"
                                      "DYNAMIC_CLOAKING (previous: 0x%08X)) failed (0x%08X)");
      WriteDbgTraceErrorWI("SetDynamicCloakingBlanket", v18);
      WiaTrcLib::Free((WiaTrcLib *)v18, v19);
      v13 = (void **)WiaTrace_Trace(
                       "IClientSecurity::SetBlanket (RPC_C_IMP_LEVEL_IMPERSONATE (previous: 0x%08X), EOAC_DYNAMIC_CLOAKIN"
                       "G (previous: 0x%08X)) failed (0x%08X)",
                       v32,
                       v31,
                       v10);
    }
    else
    {
      v16 = (char *)WiaTrace_TraceLog("IClientSecurity::QueryBlanket failed (0x%08X)");
      WriteDbgTraceErrorWI("SetDynamicCloakingBlanket", v16);
      WiaTrcLib::Free((WiaTrcLib *)v16, v17);
      v13 = (void **)WiaTrace_Trace("IClientSecurity::QueryBlanket failed (0x%08X)", (unsigned int)v10);
    }
  }
  else
  {
    v11 = (char *)WiaTrace_TraceLog("QueryInterface for IClientSecurity failed (0x%08X)");
    WriteDbgTraceErrorWI("SetDynamicCloakingBlanket", v11);
    WiaTrcLib::Free((WiaTrcLib *)v11, v12);
    v13 = (void **)WiaTrace_Trace("QueryInterface for IClientSecurity failed (0x%08X)", (unsigned int)v10);
  }
  WiaTrace_ProcessTrace_Ex(v15, v14, (void *)"SetDynamicCloakingBlanket", 1, v13);
LABEL_13:
  if ( pv )
    CoTaskMemFree(pv);
  if ( v28 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  if ( v4 >= 0 )
  {
    if ( a2 )
    {
      v10 = CoImpersonateClient();
      if ( v10 < 0 )
      {
        v20 = (char *)WiaTrace_TraceLog("CoImpersonateClient failed (0x%08X)");
        WriteDbgTraceErrorWI("SetDynamicCloakingBlanket", v20);
        WiaTrcLib::Free((WiaTrcLib *)v20, v21);
        v22 = (void **)WiaTrace_Trace("CoImpersonateClient failed (0x%08X)", v10);
        WiaTrace_ProcessTrace_Ex(v24, v23, (void *)"SetDynamicCloakingBlanket", 1, v22);
      }
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18007102c  push    rbp
0x18007102e  push    rbx
0x18007102f  push    rsi
0x180071030  push    rdi
0x180071031  push    r12
0x180071033  push    r13
0x180071035  push    r14
0x180071037  mov     rbp, rsp
0x18007103a  sub     rsp, 70h
0x18007103e  mov     [rbp+var_18], 0
0x180071046  mov     r14d, edx
0x180071049  mov     [rbp+pv], 0
0x180071051  mov     rbx, rcx
0x180071054  mov     [rbp+var_1C], 0
0x18007105b  lea     r12, aSetdynamiccloa_0; "SetDynamicCloakingBlanket"
0x180071062  mov     [rbp+var_20], 0
0x180071069  mov     r13d, 1
0x18007106f  mov     [rbp+arg_18], 0
0x180071076  mov     [rbp+arg_10], 0
0x18007107d  mov     [rbp+arg_8], 0
0x180071084  mov     [rbp+var_8], 0
0x18007108c  test    edx, edx
0x18007108e  jz      short loc_1800710E4
0x180071090  call    ?SafeCoRevertToSelf@@YAJXZ; SafeCoRevertToSelf(void)
0x180071095  mov     esi, eax
0x180071097  test    eax, eax
0x180071099  jns     short loc_1800710E6
0x18007109b  mov     edx, eax
0x18007109d  lea     rcx, aSafecorevertto_0; "SafeCoRevertToSelf failed (0x%08X)"
0x1800710a4  call    WiaTrace_TraceLog
0x1800710a9  mov     rdx, rax; char *
0x1800710ac  mov     rcx, r12; char *
0x1800710af  mov     rbx, rax
0x1800710b2  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800710b7  mov     rcx, rbx; this
0x1800710ba  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800710bf  mov     edx, esi
0x1800710c1  lea     rcx, aSafecorevertto_0; "SafeCoRevertToSelf failed (0x%08X)"
0x1800710c8  call    WiaTrace_Trace
0x1800710cd  mov     r9d, r13d; int
0x1800710d0  mov     [rsp+70h+lpMem], rax; lpMem
0x1800710d5  mov     r8, r12; int
0x1800710d8  call    WiaTrace_ProcessTrace_Ex
0x1800710dd  mov     edi, esi
0x1800710df  jmp     loc_180071256
0x1800710e4  xor     esi, esi
0x1800710e6  mov     rax, [rbx]
0x1800710e9  lea     r8, [rbp+var_18]
0x1800710ed  lea     rdx, IID_IClientSecurity
0x1800710f4  mov     rcx, rbx
0x1800710f7  mov     rax, [rax]
0x1800710fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800710ff  mov     edi, eax
0x180071101  test    eax, eax
0x180071103  jns     short loc_18007113C
0x180071105  mov     edx, eax
0x180071107  lea     rcx, aQueryinterface_1; "QueryInterface for IClientSecurity fail"...
0x18007110e  call    WiaTrace_TraceLog
0x180071113  mov     rdx, rax; char *
0x180071116  mov     rcx, r12; char *
0x180071119  mov     rbx, rax
0x18007111c  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180071121  mov     rcx, rbx; this
0x180071124  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180071129  lea     rcx, aQueryinterface_1; "QueryInterface for IClientSecurity fail"...
0x180071130  mov     edx, edi
0x180071132  call    WiaTrace_Trace
0x180071137  jmp     loc_180071246
0x18007113c  mov     rcx, [rbp+var_18]
0x180071140  lea     rdx, [rbp+arg_8]
0x180071144  mov     [rsp+70h+var_30], rdx
0x180071149  lea     r9, [rbp+var_20]
0x18007114d  lea     rdx, [rbp+var_8]
0x180071151  mov     [rsp+70h+var_38], rdx
0x180071156  lea     r8, [rbp+var_1C]
0x18007115a  mov     rax, [rcx]
0x18007115d  lea     rdx, [rbp+arg_10]
0x180071161  mov     [rsp+70h+var_40], rdx
0x180071166  lea     rdx, [rbp+arg_18]
0x18007116a  mov     [rsp+70h+var_48], rdx
0x18007116f  lea     rdx, [rbp+pv]
0x180071173  mov     [rsp+70h+lpMem], rdx
0x180071178  mov     rdx, rbx
0x18007117b  mov     rax, [rax+18h]
0x18007117f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071184  mov     edi, eax
0x180071186  test    eax, eax
0x180071188  jns     short loc_1800711BA
0x18007118a  mov     edx, eax
0x18007118c  lea     rcx, aIclientsecurit_0; "IClientSecurity::QueryBlanket failed (0"...
0x180071193  call    WiaTrace_TraceLog
0x180071198  mov     rdx, rax; char *
0x18007119b  mov     rcx, r12; char *
0x18007119e  mov     rbx, rax
0x1800711a1  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800711a6  mov     rcx, rbx; this
0x1800711a9  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800711ae  lea     rcx, aIclientsecurit_0; "IClientSecurity::QueryBlanket failed (0"...
0x1800711b5  jmp     loc_180071130
0x1800711ba  mov     rdx, [rbp+var_8]
0x1800711be  mov     rcx, [rbp+var_18]
0x1800711c2  mov     r9d, [rbp+var_20]
0x1800711c6  mov     r8d, [rbp+var_1C]
0x1800711ca  mov     dword ptr [rsp+70h+var_30], 40h ; '@'
0x1800711d2  mov     rax, [rcx]
0x1800711d5  mov     [rsp+70h+var_38], rdx
0x1800711da  mov     edx, [rbp+arg_18]
0x1800711dd  mov     dword ptr [rsp+70h+var_40], 3
0x1800711e5  mov     rax, [rax+20h]
0x1800711e9  mov     dword ptr [rsp+70h+var_48], edx
0x1800711ed  mov     rdx, [rbp+pv]
0x1800711f1  mov     [rsp+70h+lpMem], rdx
0x1800711f6  mov     rdx, rbx
0x1800711f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800711fe  mov     edi, eax
0x180071200  test    eax, eax
0x180071202  jns     short loc_180071256
0x180071204  mov     r8d, [rbp+arg_8]
0x180071208  lea     rcx, aIclientsecurit; "IClientSecurity::SetBlanket (RPC_C_IMP_"...
0x18007120f  mov     edx, [rbp+arg_10]
0x180071212  mov     r9d, eax
0x180071215  call    WiaTrace_TraceLog
0x18007121a  mov     rdx, rax; char *
0x18007121d  mov     rcx, r12; char *
0x180071220  mov     rbx, rax
0x180071223  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180071228  mov     rcx, rbx; this
0x18007122b  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180071230  mov     r8d, [rbp+arg_8]
0x180071234  lea     rcx, aIclientsecurit; "IClientSecurity::SetBlanket (RPC_C_IMP_"...
0x18007123b  mov     edx, [rbp+arg_10]
0x18007123e  mov     r9d, edi
0x180071241  call    WiaTrace_Trace
0x180071246  mov     r9d, r13d; int
0x180071249  mov     [rsp+70h+lpMem], rax; lpMem
0x18007124e  mov     r8, r12; int
0x180071251  call    WiaTrace_ProcessTrace_Ex
0x180071256  mov     rcx, [rbp+pv]; pv
0x18007125a  test    rcx, rcx
0x18007125d  jz      short loc_180071265
0x18007125f  call    cs:__imp_CoTaskMemFree
0x180071265  mov     rcx, [rbp+var_18]
0x180071269  test    rcx, rcx
0x18007126c  jz      short loc_18007127A
0x18007126e  mov     rax, [rcx]
0x180071271  mov     rax, [rax+10h]
0x180071275  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007127a  test    esi, esi
0x18007127c  js      short loc_1800712D1
0x18007127e  test    r14d, r14d
0x180071281  jz      short loc_1800712D1
0x180071283  call    cs:__imp_CoImpersonateClient
0x180071289  mov     edi, eax
0x18007128b  test    eax, eax
0x18007128d  jns     short loc_1800712D1
0x18007128f  mov     edx, eax
0x180071291  lea     rcx, aCoimpersonatec_0; "CoImpersonateClient failed (0x%08X)"
0x180071298  call    WiaTrace_TraceLog
0x18007129d  mov     rdx, rax; char *
0x1800712a0  mov     rcx, r12; char *
0x1800712a3  mov     rbx, rax
0x1800712a6  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800712ab  mov     rcx, rbx; this
0x1800712ae  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800712b3  mov     edx, edi
0x1800712b5  lea     rcx, aCoimpersonatec_0; "CoImpersonateClient failed (0x%08X)"
0x1800712bc  call    WiaTrace_Trace
0x1800712c1  mov     r9d, r13d; int
0x1800712c4  mov     [rsp+70h+lpMem], rax; lpMem
0x1800712c9  mov     r8, r12; int
0x1800712cc  call    WiaTrace_ProcessTrace_Ex
0x1800712d1  mov     eax, edi
0x1800712d3  add     rsp, 70h
0x1800712d7  pop     r14
0x1800712d9  pop     r13
0x1800712db  pop     r12
0x1800712dd  pop     rdi
0x1800712de  pop     rsi
0x1800712df  pop     rbx
0x1800712e0  pop     rbp
0x1800712e1  retn
```
