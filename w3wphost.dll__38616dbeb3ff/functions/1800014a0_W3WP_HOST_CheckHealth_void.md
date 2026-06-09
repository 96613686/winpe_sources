# W3WP_HOST::CheckHealth(void)

- ea: `0x1800014a0`
- end: `0x1800016cf`
- name: `?CheckHealth@W3WP_HOST@@QEAAXXZ`
- size: `559`
- prototype: `void __fastcall(W3WP_HOST *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800013f0`

## callees

- `0x1800014a0`
- `0x180001720`
- `0x1800019f0`
- `0x180002090`
- `0x18000e010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x1800014dd`
- `iisutil!PuDbgPrint` at `0x1800015ed`
- `iisutil!PuDbgPrint` at `0x1800016ae`
- `iisutil!PuDbgPrint` at `0x1800014dd`
- `iisutil!PuDbgPrint` at `0x1800015ed`
- `iisutil!PuDbgPrint` at `0x1800016ae`

## string_xrefs

- `0x1800014d6`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x1800015db`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x1800016a7`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`

## pseudocode

```c
void __fastcall W3WP_HOST::CheckHealth(W3WP_HOST *this)
{
  W3WP_HOST *v1; // rbx
  __int64 v2; // rax
  void *v3; // rdi
  int v4; // ebp
  PROTOCOL_MANAGER_ENTRY **i; // r14
  int v6; // eax

  v1 = g_pW3WPHost;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
      3960,
      "W3WP_HOST::CheckHealth",
      "Process Model check health called\n");
  v2 = *((_QWORD *)v1 + 12);
  if ( v2 && *(_DWORD *)(v2 + 24) || _InterlockedCompareExchange((volatile signed __int32 *)v1 + 399, 1, 0) )
  {
    WP_IPM::ReportHealthy(*((WP_IPM **)v1 + 11));
    return;
  }
  v3 = operator new(0x18u);
  if ( !v3 )
  {
    v4 = -2147024882;
    _InterlockedCompareExchange((volatile signed __int32 *)v1 + 399, 0, 1);
LABEL_15:
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
        4045,
        "W3WP_HOST::CheckHealth",
        "CheckHealth call failed with error 0x%x \n",
        v4);
    return;
  }
  v4 = 0;
  _InterlockedIncrement(&CALLBACK_BASE::sm_CallbackInstanceCount);
  *((_QWORD *)v3 + 1) = 1;
  *(_QWORD *)v3 = &PING_CALLBACK::`vftable';
  *((_DWORD *)v3 + 4) = 1;
  for ( i = PROTOCOL_MANAGER_LIST::GetNextProtocolManagerEntry((W3WP_HOST *)((char *)v1 + 320), 0);
        i;
        i = PROTOCOL_MANAGER_LIST::GetNextProtocolManagerEntry((W3WP_HOST *)((char *)v1 + 320), i) )
  {
    _InterlockedIncrement((volatile signed __int32 *)v3 + 4);
    v6 = (*(__int64 (__fastcall **)(PROTOCOL_MANAGER_ENTRY *, void *))(*(_QWORD *)i[34] + 24LL))(i[34], v3);
    v4 = v6;
    if ( v6 < 0 && (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
        4001,
        "W3WP_HOST::CheckHealth",
        "HealthCheck call failed with error 0x%x \n",
        v6);
  }
  (*(void (__fastcall **)(void *, __int64))(*(_QWORD *)v3 + 16LL))(v3, 1);
  (*(void (__fastcall **)(void *))(*(_QWORD *)v3 + 8LL))(v3);
  _InterlockedCompareExchange((volatile signed __int32 *)v1 + 399, 0, 1);
  if ( v4 < 0 )
    goto LABEL_15;
}

```

## disassembly

```asm
0x1800014a0  push    rbx
0x1800014a2  sub     rsp, 50h
0x1800014a6  test    byte ptr cs:g_dwDebugFlags, 3
0x1800014ad  mov     rbx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x1800014b4  jz      short loc_1800014E9
0x1800014b6  mov     rcx, cs:g_pDebug
0x1800014bd  lea     rax, aProcessModelCh; "Process Model check health called\n"
0x1800014c4  lea     r9, aW3wpHostCheckh; "W3WP_HOST::CheckHealth"
0x1800014cb  mov     [rsp+58h+var_38], rax
0x1800014d0  mov     r8d, 0F78h
0x1800014d6  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800014dd  call    cs:__imp_PuDbgPrint
0x1800014e4  nop     dword ptr [rax+rax+00h]
0x1800014e9  mov     rax, [rbx+60h]
0x1800014ed  test    rax, rax
0x1800014f0  jz      short loc_180001506
0x1800014f2  cmp     dword ptr [rax+18h], 0
0x1800014f6  jz      short loc_180001506
0x1800014f8  mov     rcx, [rbx+58h]; this
0x1800014fc  add     rsp, 50h
0x180001500  pop     rbx
0x180001501  jmp     ?ReportHealthy@WP_IPM@@QEAAXXZ; WP_IPM::ReportHealthy(void)
0x180001506  mov     [rsp+58h+var_10], r12
0x18000150b  xor     eax, eax
0x18000150d  mov     r12d, 1
0x180001513  lock cmpxchg [rbx+63Ch], r12d
0x18000151c  jnz     loc_1800016BC
0x180001522  mov     [rsp+58h+arg_10], rdi
0x180001527  mov     ecx, 18h; Size
0x18000152c  mov     [rsp+58h+arg_0], rbp
0x180001531  mov     [rsp+58h+arg_8], rsi
0x180001536  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000153b  xor     esi, esi
0x18000153d  mov     rdi, rax
0x180001540  test    rax, rax
0x180001543  jz      loc_18000166A
0x180001549  mov     [rsp+58h+var_20], r14
0x18000154e  mov     ebp, esi
0x180001550  mov     [rsp+58h+var_28], r15
0x180001555  lock inc cs:?sm_CallbackInstanceCount@CALLBACK_BASE@@0JA; long CALLBACK_BASE::sm_CallbackInstanceCount
0x18000155c  lea     rax, ??_7PING_CALLBACK@@6B@; const PING_CALLBACK::`vftable'
0x180001563  mov     [rdi+8], r12
0x180001567  xor     edx, edx; struct PROTOCOL_MANAGER_ENTRY *
0x180001569  mov     [rdi], rax
0x18000156c  lea     rcx, [rbx+140h]; this
0x180001573  mov     [rdi+10h], r12d
0x180001577  call    ?GetNextProtocolManagerEntry@PROTOCOL_MANAGER_LIST@@QEAAPEAVPROTOCOL_MANAGER_ENTRY@@PEAV2@@Z; PROTOCOL_MANAGER_LIST::GetNextProtocolManagerEntry(PROTOCOL_MANAGER_ENTRY *)
0x18000157c  mov     r14, rax
0x18000157f  test    rax, rax
0x180001582  jz      loc_180001615
0x180001588  mov     [rsp+58h+var_18], r13
0x18000158d  lea     r13, aHealthcheckCal; "HealthCheck call failed with error 0x%x"...
0x180001594  nop     dword ptr [rax+00h]
0x180001598  nop     dword ptr [rax+rax+00000000h]
0x1800015a0  lock inc dword ptr [rdi+10h]
0x1800015a4  mov     rcx, [r14+110h]
0x1800015ab  mov     rdx, [rcx]
0x1800015ae  mov     rax, [rdx+18h]
0x1800015b2  mov     rdx, rdi
0x1800015b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800015ba  mov     ebp, eax
0x1800015bc  test    eax, eax
0x1800015be  jns     short loc_1800015F9
0x1800015c0  test    byte ptr cs:g_dwDebugFlags, 3
0x1800015c7  jz      short loc_1800015F9
0x1800015c9  mov     rcx, cs:g_pDebug
0x1800015d0  lea     r9, aW3wpHostCheckh; "W3WP_HOST::CheckHealth"
0x1800015d7  mov     [rsp+58h+var_30], eax
0x1800015db  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800015e2  mov     r8d, 0FA1h
0x1800015e8  mov     [rsp+58h+var_38], r13
0x1800015ed  call    cs:__imp_PuDbgPrint
0x1800015f4  nop     dword ptr [rax+rax+00h]
0x1800015f9  mov     rdx, r14; struct PROTOCOL_MANAGER_ENTRY *
0x1800015fc  lea     rcx, [rbx+140h]; this
0x180001603  call    ?GetNextProtocolManagerEntry@PROTOCOL_MANAGER_LIST@@QEAAPEAVPROTOCOL_MANAGER_ENTRY@@PEAV2@@Z; PROTOCOL_MANAGER_LIST::GetNextProtocolManagerEntry(PROTOCOL_MANAGER_ENTRY *)
0x180001608  mov     r14, rax
0x18000160b  test    rax, rax
0x18000160e  jnz     short loc_1800015A0
0x180001610  mov     r13, [rsp+58h+var_18]
0x180001615  mov     rdx, [rdi]
0x180001618  mov     rcx, rdi
0x18000161b  mov     rax, [rdx+10h]
0x18000161f  mov     edx, r12d
0x180001622  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001627  mov     rdx, [rdi]
0x18000162a  mov     rcx, rdi
0x18000162d  mov     rax, [rdx+8]
0x180001631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001636  mov     eax, r12d
0x180001639  lock cmpxchg [rbx+63Ch], esi
0x180001641  mov     r15, [rsp+58h+var_28]
0x180001646  mov     r14, [rsp+58h+var_20]
0x18000164b  test    ebp, ebp
0x18000164d  js      short loc_18000167A
0x18000164f  mov     rsi, [rsp+58h+arg_8]
0x180001654  mov     rbp, [rsp+58h+arg_0]
0x180001659  mov     rdi, [rsp+58h+arg_10]
0x18000165e  mov     r12, [rsp+58h+var_10]
0x180001663  add     rsp, 50h
0x180001667  pop     rbx
0x180001668  retn
0x18000166a  mov     ebp, 8007000Eh
0x18000166f  mov     eax, r12d
0x180001672  lock cmpxchg [rbx+63Ch], esi
0x18000167a  test    byte ptr cs:g_dwDebugFlags, 3
0x180001681  jz      short loc_18000164F
0x180001683  mov     rcx, cs:g_pDebug
0x18000168a  lea     rax, aCheckhealthCal; "CheckHealth call failed with error 0x%x"...
0x180001691  mov     [rsp+58h+var_30], ebp
0x180001695  lea     r9, aW3wpHostCheckh; "W3WP_HOST::CheckHealth"
0x18000169c  mov     r8d, 0FCDh
0x1800016a2  mov     [rsp+58h+var_38], rax
0x1800016a7  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800016ae  call    cs:__imp_PuDbgPrint
0x1800016b5  nop     dword ptr [rax+rax+00h]
0x1800016ba  jmp     short loc_18000164F
0x1800016bc  mov     rcx, [rbx+58h]; this
0x1800016c0  mov     r12, [rsp+58h+var_10]
0x1800016c5  add     rsp, 50h
0x1800016c9  pop     rbx
0x1800016ca  jmp     ?ReportHealthy@WP_IPM@@QEAAXXZ; WP_IPM::ReportHealthy(void)
```
