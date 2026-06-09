# W3WP_HOST::CheckHealth(void)

- ea: `0x180001480`
- end: `0x180001692`
- name: `?CheckHealth@W3WP_HOST@@QEAAXXZ`
- size: `530`
- prototype: `void __fastcall(W3WP_HOST *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800013e0`

## callees

- `0x180001480`
- `0x1800016e0`
- `0x180001970`
- `0x180001f68`
- `0x18000d010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x1800014bd`
- `iisutil!PuDbgPrint` at `0x1800015bd`
- `iisutil!PuDbgPrint` at `0x180001677`
- `iisutil!PuDbgPrint` at `0x1800014bd`
- `iisutil!PuDbgPrint` at `0x1800015bd`
- `iisutil!PuDbgPrint` at `0x180001677`

## string_xrefs

- `0x1800014b6`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x1800015ab`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x180001670`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`

## pseudocode

```c
void __fastcall W3WP_HOST::CheckHealth(W3WP_HOST *this)
{
  W3WP_HOST *v1; // rbx
  __int64 v2; // rax
  void *v3; // rdi
  int v4; // ebp
  PROTOCOL_MANAGER_ENTRY **i; // r14

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
    _InterlockedCompareExchange((volatile signed __int32 *)v1 + 399, 0, 1);
LABEL_15:
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
        4045,
        "W3WP_HOST::CheckHealth",
        "CheckHealth call failed with error 0x%x \n");
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
    v4 = (*(__int64 (__fastcall **)(PROTOCOL_MANAGER_ENTRY *, void *))(*(_QWORD *)i[34] + 24LL))(i[34], v3);
    if ( v4 < 0 && (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
        4001,
        "W3WP_HOST::CheckHealth",
        "HealthCheck call failed with error 0x%x \n");
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
0x180001480  push    rbx
0x180001482  sub     rsp, 50h
0x180001486  test    byte ptr cs:g_dwDebugFlags, 3
0x18000148d  mov     rbx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x180001494  jz      short loc_1800014C3
0x180001496  mov     rcx, cs:g_pDebug
0x18000149d  lea     rax, aProcessModelCh; "Process Model check health called\n"
0x1800014a4  lea     r9, aW3wpHostCheckh; "W3WP_HOST::CheckHealth"
0x1800014ab  mov     [rsp+58h+var_38], rax
0x1800014b0  mov     r8d, 0F78h
0x1800014b6  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800014bd  call    cs:__imp_PuDbgPrint
0x1800014c3  mov     rax, [rbx+60h]
0x1800014c7  test    rax, rax
0x1800014ca  jz      short loc_1800014E0
0x1800014cc  cmp     dword ptr [rax+18h], 0
0x1800014d0  jz      short loc_1800014E0
0x1800014d2  mov     rcx, [rbx+58h]; this
0x1800014d6  add     rsp, 50h
0x1800014da  pop     rbx
0x1800014db  jmp     ?ReportHealthy@WP_IPM@@QEAAXXZ; WP_IPM::ReportHealthy(void)
0x1800014e0  mov     [rsp+58h+var_10], r12
0x1800014e5  xor     eax, eax
0x1800014e7  mov     r12d, 1
0x1800014ed  lock cmpxchg [rbx+63Ch], r12d
0x1800014f6  jnz     loc_18000167F
0x1800014fc  mov     [rsp+58h+arg_10], rdi
0x180001501  mov     ecx, 18h; Size
0x180001506  mov     [rsp+58h+arg_0], rbp
0x18000150b  mov     [rsp+58h+arg_8], rsi
0x180001510  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001515  xor     esi, esi
0x180001517  mov     rdi, rax
0x18000151a  test    rax, rax
0x18000151d  jz      loc_180001633
0x180001523  mov     [rsp+58h+var_20], r14
0x180001528  mov     ebp, esi
0x18000152a  mov     [rsp+58h+var_28], r15
0x18000152f  lock inc cs:?sm_CallbackInstanceCount@CALLBACK_BASE@@0JA; long CALLBACK_BASE::sm_CallbackInstanceCount
0x180001536  lea     rax, ??_7PING_CALLBACK@@6B@; const PING_CALLBACK::`vftable'
0x18000153d  mov     [rdi+8], r12
0x180001541  xor     edx, edx; struct PROTOCOL_MANAGER_ENTRY *
0x180001543  mov     [rdi], rax
0x180001546  lea     rcx, [rbx+140h]; this
0x18000154d  mov     [rdi+10h], r12d
0x180001551  call    ?GetNextProtocolManagerEntry@PROTOCOL_MANAGER_LIST@@QEAAPEAVPROTOCOL_MANAGER_ENTRY@@PEAV2@@Z; PROTOCOL_MANAGER_LIST::GetNextProtocolManagerEntry(PROTOCOL_MANAGER_ENTRY *)
0x180001556  mov     r14, rax
0x180001559  test    rax, rax
0x18000155c  jz      loc_1800015DF
0x180001562  mov     [rsp+58h+var_18], r13
0x180001567  lea     r13, aHealthcheckCal; "HealthCheck call failed with error 0x%x"...
0x18000156e  xchg    ax, ax
0x180001570  lock inc dword ptr [rdi+10h]
0x180001574  mov     rcx, [r14+110h]
0x18000157b  mov     rdx, [rcx]
0x18000157e  mov     rax, [rdx+18h]
0x180001582  mov     rdx, rdi
0x180001585  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000158a  mov     ebp, eax
0x18000158c  test    eax, eax
0x18000158e  jns     short loc_1800015C3
0x180001590  test    byte ptr cs:g_dwDebugFlags, 3
0x180001597  jz      short loc_1800015C3
0x180001599  mov     rcx, cs:g_pDebug
0x1800015a0  lea     r9, aW3wpHostCheckh; "W3WP_HOST::CheckHealth"
0x1800015a7  mov     [rsp+58h+var_30], eax
0x1800015ab  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800015b2  mov     r8d, 0FA1h
0x1800015b8  mov     [rsp+58h+var_38], r13
0x1800015bd  call    cs:__imp_PuDbgPrint
0x1800015c3  mov     rdx, r14; struct PROTOCOL_MANAGER_ENTRY *
0x1800015c6  lea     rcx, [rbx+140h]; this
0x1800015cd  call    ?GetNextProtocolManagerEntry@PROTOCOL_MANAGER_LIST@@QEAAPEAVPROTOCOL_MANAGER_ENTRY@@PEAV2@@Z; PROTOCOL_MANAGER_LIST::GetNextProtocolManagerEntry(PROTOCOL_MANAGER_ENTRY *)
0x1800015d2  mov     r14, rax
0x1800015d5  test    rax, rax
0x1800015d8  jnz     short loc_180001570
0x1800015da  mov     r13, [rsp+58h+var_18]
0x1800015df  mov     rdx, [rdi]
0x1800015e2  mov     rcx, rdi
0x1800015e5  mov     rax, [rdx+10h]
0x1800015e9  mov     edx, r12d
0x1800015ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800015f1  mov     rdx, [rdi]
0x1800015f4  mov     rcx, rdi
0x1800015f7  mov     rax, [rdx+8]
0x1800015fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001600  mov     eax, r12d
0x180001603  lock cmpxchg [rbx+63Ch], esi
0x18000160b  mov     r15, [rsp+58h+var_28]
0x180001610  mov     r14, [rsp+58h+var_20]
0x180001615  test    ebp, ebp
0x180001617  js      short loc_180001643
0x180001619  mov     rsi, [rsp+58h+arg_8]
0x18000161e  mov     rbp, [rsp+58h+arg_0]
0x180001623  mov     rdi, [rsp+58h+arg_10]
0x180001628  mov     r12, [rsp+58h+var_10]
0x18000162d  add     rsp, 50h
0x180001631  pop     rbx
0x180001632  retn
0x180001633  mov     ebp, 8007000Eh
0x180001638  mov     eax, r12d
0x18000163b  lock cmpxchg [rbx+63Ch], esi
0x180001643  test    byte ptr cs:g_dwDebugFlags, 3
0x18000164a  jz      short loc_180001619
0x18000164c  mov     rcx, cs:g_pDebug
0x180001653  lea     rax, aCheckhealthCal; "CheckHealth call failed with error 0x%x"...
0x18000165a  mov     [rsp+58h+var_30], ebp
0x18000165e  lea     r9, aW3wpHostCheckh; "W3WP_HOST::CheckHealth"
0x180001665  mov     r8d, 0FCDh
0x18000166b  mov     [rsp+58h+var_38], rax
0x180001670  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180001677  call    cs:__imp_PuDbgPrint
0x18000167d  jmp     short loc_180001619
0x18000167f  mov     rcx, [rbx+58h]; this
0x180001683  mov     r12, [rsp+58h+var_10]
0x180001688  add     rsp, 50h
0x18000168c  pop     rbx
0x18000168d  jmp     ?ReportHealthy@WP_IPM@@QEAAXXZ; WP_IPM::ReportHealthy(void)
```
