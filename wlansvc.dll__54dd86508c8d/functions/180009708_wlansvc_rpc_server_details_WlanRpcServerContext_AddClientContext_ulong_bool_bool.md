# wlansvc::rpc_server::details::WlanRpcServerContext::AddClientContext(ulong,bool,bool)

- ea: `0x180009708`
- end: `0x180009b23`
- name: `?AddClientContext@WlanRpcServerContext@details@rpc_server@wlansvc@@QEAAPEAVWlanRpcClientContext@234@K_N0@Z`
- size: `1051`
- prototype: `struct wlansvc::rpc_server::details::WlanRpcClientContext *__fastcall(wlansvc::rpc_server::details::WlanRpcServerContext *__hidden this, unsigned int, bool, bool)`
- caller_count: `3`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800091a0`
- `0x180128ab0`
- `0x180131880`

## callees

- `0x180009708`
- `0x18000a3c0`
- `0x18000a3f0`
- `0x18000a5a8`
- `0x18000a994`
- `0x18000aa0c`
- `0x18000b610`
- `0x180011530`
- `0x18007d770`
- `0x18007d77c`
- `0x180102bf4`
- `0x1801049ac`
- `0x18010680c`
- `0x1801158d8`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180009ad6`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180009ad6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800099a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800099a4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009747`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009747`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800097c7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800097c7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000997d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000997d`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
struct wlansvc::rpc_server::details::WlanRpcClientContext *__fastcall wlansvc::rpc_server::details::WlanRpcServerContext::AddClientContext(
        wlansvc::rpc_server::details::WlanRpcServerContext *this,
        int a2,
        char a3,
        int a4)
{
  LPCRITICAL_SECTION v4; // r14
  wlansvc::rpc_server::details::WlanRpcClientContext *v5; // rdi
  __int64 v6; // r9
  int v7; // r8d
  _QWORD *OwningThread; // rcx
  _QWORD *i; // rax
  _QWORD *v10; // rbx
  const char *v11; // r9
  struct _TP_WORK *ThreadpoolWork; // r12
  HANDLE *v13; // r9
  wlansvc::rpc_server::details::WlanRpcClientContext *v14; // r13
  _QWORD *v15; // rdx
  __int64 v16; // rdi
  unsigned __int64 j; // rcx
  ULONG_PTR SpinCount; // r8
  _QWORD *v19; // rbx
  _QWORD *v20; // r15
  __int64 v21; // r8
  float v22; // xmm0_4
  __int64 LockSemaphore; // rcx
  float v24; // xmm1_4
  _QWORD *v25; // rcx
  ULONG_PTR v26; // rax
  __int64 v27; // rdi
  _QWORD *v28; // r8
  __int64 v29; // rbx
  __int64 v31; // rax
  __int64 v32; // rax
  char v33; // [rsp+20h] [rbp-59h]
  unsigned int v34; // [rsp+20h] [rbp-59h]
  void *v35; // [rsp+40h] [rbp-39h]
  HANDLE *p_OwningThread; // [rsp+48h] [rbp-31h]
  _QWORD *v37; // [rsp+50h] [rbp-29h]
  struct _TP_WORK *v38; // [rsp+58h] [rbp-21h]
  _QWORD *v39; // [rsp+60h] [rbp-19h]
  HANDLE *v40; // [rsp+68h] [rbp-11h]
  wlansvc::rpc_server::details::WlanRpcClientContext *v41; // [rsp+70h] [rbp-9h]
  _QWORD *v42; // [rsp+78h] [rbp-1h]
  LPCRITICAL_SECTION v43[10]; // [rsp+80h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  wlansvc::rpc_server::details::WlanRpcClientContext *v45; // [rsp+E0h] [rbp+67h] BYREF

  v45 = this;
  v4 = lpCriticalSection;
  v33 = a4;
  LOBYTE(a4) = a3;
  wlansvc::rpc_server::details::WlanRpcServerContext::CreateClientContext(
    (_DWORD)lpCriticalSection,
    (unsigned int)&v45,
    a2,
    a4,
    v33);
  EnterCriticalSection(v4);
  v43[0] = v4;
  if ( v4[3].LockSemaphore >= (HANDLE)0x400 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105)
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 23, &WPP_b841df4553e83e4110d3867191ccdd26_Traceguids);
    }
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x3BB,
      (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\server\\rpcsrv.cpp",
      (const char *)0x4C4,
      v34);
  }
  v5 = v45;
  v41 = v45;
  v6 = *((unsigned int *)v45 + 97);
  v7 = 0;
  OwningThread = v4[3].OwningThread;
  for ( i = (_QWORD *)*OwningThread; i != OwningThread; i = (_QWORD *)*i )
  {
    if ( *(_DWORD *)(i[3] + 388LL) == (_DWORD)v6 && (unsigned int)++v7 >= 0x14 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105)
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 24, &WPP_b841df4553e83e4110d3867191ccdd26_Traceguids, v6);
      }
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x3C7,
        (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\server\\rpcsrv.cpp",
        (const char *)0x4C4,
        v34);
    }
  }
  v10 = operator new(8u);
  v42 = v10;
  *v10 = 0;
  v39 = v10;
  ThreadpoolWork = CreateThreadpoolWork(
                     wlansvc::rpc_server::details::WlanRpcServerContext::ClientCleanupWorkCallback,
                     v10,
                     (PTP_CALLBACK_ENVIRON)&v4[1]);
  v38 = ThreadpoolWork;
  if ( !ThreadpoolWork )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x2A3,
      (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\server\\rpcsrv.cpp",
      v11);
  v13 = (HANDLE *)*((_QWORD *)v5 + 47);
  v40 = v13;
  p_OwningThread = v13;
  v45 = 0;
  v14 = v5;
  v38 = 0;
  v39 = 0;
  v15 = v10;
  v35 = v10;
  v16 = 0xCBF29CE484222325uLL;
  for ( j = 0; j < 8; ++j )
    v16 = 0x100000001B3LL * (*((unsigned __int8 *)&p_OwningThread + j) ^ (unsigned __int64)v16);
  SpinCount = v4[3].SpinCount;
  v19 = *(_QWORD **)(SpinCount + 16 * ((__int64)v4[4].OwningThread & v16) + 8);
  v20 = v4[3].OwningThread;
  if ( v19 != v20 )
  {
    while ( v13 != (HANDLE *)v19[2] )
    {
      if ( v19 == *(_QWORD **)(SpinCount + 16 * ((__int64)v4[4].OwningThread & v16)) )
      {
        v20 = v19;
        goto LABEL_13;
      }
      v19 = (_QWORD *)v19[1];
    }
    goto LABEL_23;
  }
LABEL_13:
  if ( v4[3].LockSemaphore == (HANDLE)0x555555555555555LL )
    std::_Xlength_error("unordered_map/set too long");
  p_OwningThread = &v4[3].OwningThread;
  v37 = 0;
  v19 = std::_Allocate<16,std::_Default_allocate_traits>(0x30u);
  v37 = v19;
  v19[2] = v40;
  v14 = 0;
  v19[3] = v41;
  v19[4] = ThreadpoolWork;
  ThreadpoolWork = 0;
  v15 = 0;
  v35 = 0;
  v19[5] = v42;
  v21 = (__int64)v4[3].LockSemaphore + 1;
  if ( v21 < 0 )
    v22 = (float)(v21 & 1 | (unsigned int)((unsigned __int64)v21 >> 1))
        + (float)(v21 & 1 | (unsigned int)((unsigned __int64)v21 >> 1));
  else
    v22 = (float)(int)v21;
  LockSemaphore = (__int64)v4[4].LockSemaphore;
  if ( LockSemaphore < 0 )
  {
    v31 = (__int64)v4[4].LockSemaphore & 1 | ((unsigned __int64)LockSemaphore >> 1);
    v24 = (float)(int)v31 + (float)(int)v31;
  }
  else
  {
    v24 = (float)(int)LockSemaphore;
  }
  if ( (float)(v22 / v24) > *(float *)&v4[3].LockCount )
  {
    v32 = std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Desired_grow_bucket_count(&v4[3].LockCount);
    std::_Hash<std::_Umap_traits<unsigned __int64,wlansvc::rpc_server::details::WlanRpcServerContext::WlanRpcClientMapEntry,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,wlansvc::rpc_server::details::WlanRpcServerContext::WlanRpcClientMapEntry>>,0>>::_Forced_rehash(
      &v4[3].LockCount,
      v32);
    v20 = (_QWORD *)*std::_Hash<std::_Umap_traits<unsigned __int64,wlansvc::rpc_server::details::WlanRpcServerContext::WlanRpcClientMapEntry,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,wlansvc::rpc_server::details::WlanRpcServerContext::WlanRpcClientMapEntry>>,0>>::_Find_last<unsigned __int64>(
                       &v4[3].LockCount,
                       v43,
                       v19 + 2,
                       v16);
    v15 = 0;
  }
  v25 = (_QWORD *)v20[1];
  ++v4[3].LockSemaphore;
  *v19 = v20;
  v19[1] = v25;
  *v25 = v19;
  v20[1] = v19;
  v26 = v4[3].SpinCount;
  v27 = 2 * ((__int64)v4[4].OwningThread & v16);
  v28 = *(_QWORD **)(v26 + 8 * v27);
  if ( v28 == v4[3].OwningThread )
  {
    *(_QWORD *)(v26 + 8 * v27) = v19;
LABEL_38:
    *(_QWORD *)(v26 + 8 * v27 + 8) = v19;
    goto LABEL_23;
  }
  if ( v28 == v20 )
  {
    *(_QWORD *)(v26 + 8 * v27) = v19;
    goto LABEL_23;
  }
  if ( *(_QWORD **)(v26 + 8 * v27 + 8) == v25 )
    goto LABEL_38;
LABEL_23:
  if ( v15 )
  {
    std::unique_ptr<wlansvc::rpc_server::details::WlanRpcClientContext>::~unique_ptr<wlansvc::rpc_server::details::WlanRpcClientContext>(v15);
    operator delete(v35, (const struct std::nothrow_t *)8);
  }
  if ( ThreadpoolWork )
    CloseThreadpoolWork(ThreadpoolWork);
  if ( v14 )
  {
    wlansvc::rpc_server::details::WlanRpcClientContext::~WlanRpcClientContext(v14);
    operator delete(v14, (const struct std::nothrow_t *)0x248);
  }
  v29 = v19[3];
  LeaveCriticalSection(v4);
  return (struct wlansvc::rpc_server::details::WlanRpcClientContext *)v29;
}

```

## disassembly

```asm
0x180009708  mov     [rsp-8+arg_0], rcx
0x18000970d  push    rbp
0x18000970e  push    rbx
0x18000970f  push    rsi
0x180009710  push    rdi
0x180009711  push    r12
0x180009713  push    r13
0x180009715  push    r14
0x180009717  push    r15
0x180009719  lea     rbp, [rsp-1Fh]
0x18000971e  sub     rsp, 98h
0x180009725  mov     r14, cs:lpCriticalSection
0x18000972c  mov     byte ptr [rsp+0D0h+var_B0], r9b; unsigned int
0x180009731  mov     r9b, r8b
0x180009734  mov     r8d, edx
0x180009737  lea     rdx, [rbp+57h+arg_0]
0x18000973b  mov     rcx, r14
0x18000973e  call    ?CreateClientContext@WlanRpcServerContext@details@rpc_server@wlansvc@@AEAA?AV?$unique_ptr@VWlanRpcClientContext@details@rpc_server@wlansvc@@U?$default_delete@VWlanRpcClientContext@details@rpc_server@wlansvc@@@std@@@std@@K_N0@Z; wlansvc::rpc_server::details::WlanRpcServerContext::CreateClientContext(ulong,bool,bool)
0x180009743  nop
0x180009744  mov     rcx, r14; lpCriticalSection
0x180009747  call    cs:__imp_EnterCriticalSection
0x18000974d  mov     [rbp+57h+var_50], r14
0x180009751  cmp     qword ptr [r14+90h], 400h
0x18000975c  jnb     loc_180009A6D
0x180009762  mov     rdi, [rbp+57h+arg_0]
0x180009766  mov     [rbp+57h+var_60], rdi
0x18000976a  mov     r9d, [rdi+184h]
0x180009771  xor     r8d, r8d
0x180009774  lea     rsi, [r14+80h]
0x18000977b  mov     rcx, [rsi+8]
0x18000977f  mov     rax, [rcx]
0x180009782  cmp     rax, rcx
0x180009785  jz      short loc_18000979D
0x180009787  mov     rdx, [rax+18h]
0x18000978b  cmp     [rdx+184h], r9d
0x180009792  jz      loc_1800099C2
0x180009798  mov     rax, [rax]
0x18000979b  jmp     short loc_180009782
0x18000979d  mov     ecx, 8; Size
0x1800097a2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800097a7  mov     rbx, rax
0x1800097aa  mov     [rbp+57h+var_58], rax
0x1800097ae  mov     qword ptr [rax], 0
0x1800097b5  mov     [rbp+57h+var_70], rax
0x1800097b9  lea     r8, [r14+28h]; pcbe
0x1800097bd  mov     rdx, rax; pv
0x1800097c0  lea     rcx, ?ClientCleanupWorkCallback@WlanRpcServerContext@details@rpc_server@wlansvc@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800097c7  call    cs:__imp_CreateThreadpoolWork
0x1800097cd  mov     r12, rax
0x1800097d0  mov     [rbp+57h+var_78], rax
0x1800097d4  mov     rcx, [rbp+5Fh]; this
0x1800097d8  test    rax, rax
0x1800097db  jz      loc_180009ABD
0x1800097e1  mov     r9, [rdi+178h]
0x1800097e8  mov     [rbp+57h+var_68], r9
0x1800097ec  mov     [rbp+57h+var_88], r9
0x1800097f0  mov     [rbp+57h+arg_0], 0
0x1800097f8  mov     r13, rdi
0x1800097fb  mov     [rbp+57h+var_A0], rdi
0x1800097ff  mov     [rbp+57h+var_98], rax
0x180009803  mov     [rbp+57h+var_78], 0
0x18000980b  mov     [rbp+57h+var_70], 0
0x180009813  mov     rdx, rbx
0x180009816  mov     [rbp+57h+var_90], rbx
0x18000981a  mov     rdi, 0CBF29CE484222325h
0x180009824  xor     ecx, ecx
0x180009826  movzx   eax, byte ptr [rbp+rcx+57h+var_88]
0x18000982b  xor     rdi, rax
0x18000982e  mov     r8, 100000001B3h
0x180009838  imul    rdi, r8
0x18000983c  inc     rcx
0x18000983f  cmp     rcx, 8
0x180009843  jb      short loc_180009826
0x180009845  mov     rcx, rdi
0x180009848  and     rcx, [rsi+30h]
0x18000984c  mov     r8, [rsi+18h]
0x180009850  mov     rax, rcx
0x180009853  add     rax, rax
0x180009856  mov     rbx, [r8+rax*8+8]
0x18000985b  mov     r15, [rsi+8]
0x18000985f  cmp     rbx, r15
0x180009862  jz      short loc_180009881
0x180009864  add     rcx, rcx
0x180009867  mov     rax, [r8+rcx*8]
0x18000986b  cmp     r9, [rbx+10h]
0x18000986f  jz      loc_18000995A
0x180009875  cmp     rbx, rax
0x180009878  jnz     loc_180009A1F
0x18000987e  mov     r15, rbx
0x180009881  mov     rax, 555555555555555h
0x18000988b  cmp     [rsi+10h], rax
0x18000988f  jz      loc_180009ACF
0x180009895  lea     rax, [rsi+8]
0x180009899  mov     [rbp+57h+var_88], rax
0x18000989d  mov     [rbp+57h+var_80], 0
0x1800098a5  mov     ecx, 30h ; '0'
0x1800098aa  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800098af  mov     rbx, rax
0x1800098b2  mov     [rbp+57h+var_80], rax
0x1800098b6  mov     rax, [rbp+57h+var_68]
0x1800098ba  mov     [rbx+10h], rax
0x1800098be  xor     r13d, r13d
0x1800098c1  mov     [rbp+57h+var_A0], r13
0x1800098c5  mov     rax, [rbp+57h+var_60]
0x1800098c9  mov     [rbx+18h], rax
0x1800098cd  mov     [rbx+20h], r12
0x1800098d1  xor     r12d, r12d
0x1800098d4  mov     [rbp+57h+var_98], r12
0x1800098d8  xor     edx, edx
0x1800098da  mov     [rbp+57h+var_90], rdx
0x1800098de  mov     rax, [rbp+57h+var_58]
0x1800098e2  mov     [rbx+28h], rax
0x1800098e6  mov     r8, [rsi+10h]
0x1800098ea  add     r8, 1
0x1800098ee  xorps   xmm0, xmm0
0x1800098f1  js      loc_180009A36
0x1800098f7  cvtsi2ss xmm0, r8
0x1800098fc  mov     rcx, [rsi+38h]
0x180009900  xorps   xmm1, xmm1
0x180009903  test    rcx, rcx
0x180009906  js      loc_180009A53
0x18000990c  cvtsi2ss xmm1, rcx
0x180009911  divss   xmm0, xmm1
0x180009915  comiss  xmm0, dword ptr [rsi]
0x180009918  ja      loc_180009ADD
0x18000991e  mov     rcx, [r15+8]
0x180009922  inc     qword ptr [rsi+10h]
0x180009926  mov     [rbx], r15
0x180009929  mov     [rbx+8], rcx
0x18000992d  mov     [rcx], rbx
0x180009930  mov     [r15+8], rbx
0x180009934  mov     rax, [rsi+18h]
0x180009938  and     rdi, [rsi+30h]
0x18000993c  add     rdi, rdi
0x18000993f  mov     r8, [rax+rdi*8]
0x180009943  cmp     r8, [rsi+8]
0x180009947  jz      loc_180009A28
0x18000994d  cmp     r8, r15
0x180009950  jnz     loc_180009B12
0x180009956  mov     [rax+rdi*8], rbx
0x18000995a  test    rdx, rdx
0x18000995d  jz      short loc_180009975
0x18000995f  mov     rcx, rdx
0x180009962  call    ??1?$unique_ptr@VWlanRpcClientContext@details@rpc_server@wlansvc@@U?$default_delete@VWlanRpcClientContext@details@rpc_server@wlansvc@@@std@@@std@@QEAA@XZ; std::unique_ptr<wlansvc::rpc_server::details::WlanRpcClientContext>::~unique_ptr<wlansvc::rpc_server::details::WlanRpcClientContext>(void)
0x180009967  mov     edx, 8; struct std::nothrow_t *
0x18000996c  mov     rcx, [rbp+57h+var_90]; void *
0x180009970  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180009975  test    r12, r12
0x180009978  jz      short loc_180009983
0x18000997a  mov     rcx, r12; pwk
0x18000997d  call    cs:__imp_CloseThreadpoolWork
0x180009983  test    r13, r13
0x180009986  jz      short loc_18000999D
0x180009988  mov     rcx, r13; this
0x18000998b  call    ??1WlanRpcClientContext@details@rpc_server@wlansvc@@QEAA@XZ; wlansvc::rpc_server::details::WlanRpcClientContext::~WlanRpcClientContext(void)
0x180009990  mov     edx, 248h; struct std::nothrow_t *
0x180009995  mov     rcx, r13; void *
0x180009998  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000999d  mov     rbx, [rbx+18h]
0x1800099a1  mov     rcx, r14; lpCriticalSection
0x1800099a4  call    cs:__imp_LeaveCriticalSection
0x1800099aa  nop
0x1800099ab  mov     rax, rbx
0x1800099ae  add     rsp, 98h
0x1800099b5  pop     r15
0x1800099b7  pop     r14
0x1800099b9  pop     r13
0x1800099bb  pop     r12
0x1800099bd  pop     rdi
0x1800099be  pop     rsi
0x1800099bf  pop     rbx
0x1800099c0  pop     rbp
0x1800099c1  retn
0x1800099c2  inc     r8d
0x1800099c5  cmp     r8d, 14h
0x1800099c9  jb      loc_180009798
0x1800099cf  lea     rax, WPP_GLOBAL_Control
0x1800099d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800099dd  cmp     rcx, rax
0x1800099e0  jz      short loc_180009A03
0x1800099e2  cmp     byte ptr [rcx+69h], 1
0x1800099e6  jb      short loc_180009A03
0x1800099e8  test    byte ptr [rcx+6Ch], 1
0x1800099ec  jz      short loc_180009A03
0x1800099ee  mov     edx, 18h
0x1800099f3  lea     r8, WPP_b841df4553e83e4110d3867191ccdd26_Traceguids
0x1800099fa  mov     rcx, [rcx+60h]
0x1800099fe  call    WPP_SF_d
0x180009a03  mov     rcx, [rbp+5Fh]; this
0x180009a07  mov     r9d, 4C4h; char *
0x180009a0d  lea     r8, aOnecoreuapNetW_7; "onecoreuap\\net\\wlan\\autocfg\\server"...
0x180009a14  mov     edx, 3C7h; void *
0x180009a19  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180009a1f  mov     rbx, [rbx+8]
0x180009a23  jmp     loc_18000986B
0x180009a28  mov     [rax+rdi*8], rbx
0x180009a2c  mov     [rax+rdi*8+8], rbx
0x180009a31  jmp     loc_18000995A
0x180009a36  mov     rcx, r8
0x180009a39  shr     rcx, 1
0x180009a3c  mov     rax, r8
0x180009a3f  and     eax, 1
0x180009a42  or      rcx, rax
0x180009a45  cvtsi2ss xmm0, rcx
0x180009a4a  addss   xmm0, xmm0
0x180009a4e  jmp     loc_1800098FC
0x180009a53  mov     rax, rcx
0x180009a56  shr     rax, 1
0x180009a59  and     ecx, 1
0x180009a5c  or      rax, rcx
0x180009a5f  cvtsi2ss xmm1, rax
0x180009a64  addss   xmm1, xmm1
0x180009a68  jmp     loc_180009911
0x180009a6d  lea     rax, WPP_GLOBAL_Control
0x180009a74  mov     rcx, cs:WPP_GLOBAL_Control
0x180009a7b  cmp     rcx, rax
0x180009a7e  jz      short loc_180009AA1
0x180009a80  cmp     byte ptr [rcx+69h], 1
0x180009a84  jb      short loc_180009AA1
0x180009a86  test    byte ptr [rcx+6Ch], 1
0x180009a8a  jz      short loc_180009AA1
0x180009a8c  mov     edx, 17h
0x180009a91  lea     r8, WPP_b841df4553e83e4110d3867191ccdd26_Traceguids
0x180009a98  mov     rcx, [rcx+60h]
0x180009a9c  call    WPP_SF_
0x180009aa1  mov     rcx, [rbp+5Fh]; this
0x180009aa5  mov     r9d, 4C4h; char *
0x180009aab  lea     r8, aOnecoreuapNetW_7; "onecoreuap\\net\\wlan\\autocfg\\server"...
0x180009ab2  mov     edx, 3BBh; void *
0x180009ab7  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180009abd  lea     r8, aOnecoreuapNetW_7; "onecoreuap\\net\\wlan\\autocfg\\server"...
0x180009ac4  mov     edx, 2A3h; void *
0x180009ac9  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180009acf  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x180009ad6  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180009add  mov     rdx, r8
0x180009ae0  mov     rcx, rsi
0x180009ae3  call    ?_Desired_grow_bucket_count@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@IEBA_K_K@Z; std::_Hash<std::_Umap_traits<std::wstring,ulong,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::_Desired_grow_bucket_count(unsigned __int64)
0x180009ae8  mov     rdx, rax
0x180009aeb  mov     rcx, rsi
0x180009aee  call    ?_Forced_rehash@?$_Hash@V?$_Umap_traits@_KUWlanRpcClientMapEntry@WlanRpcServerContext@details@rpc_server@wlansvc@@V?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@U?$pair@$$CB_KUWlanRpcClientMapEntry@WlanRpcServerContext@details@rpc_server@wlansvc@@@std@@@7@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Umap_traits<unsigned __int64,wlansvc::rpc_server::details::WlanRpcServerContext::WlanRpcClientMapEntry,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,wlansvc::rpc_server::details::WlanRpcServerContext::WlanRpcClientMapEntry>>,0>>::_Forced_rehash(unsigned __int64)
0x180009af3  mov     r9, rdi
0x180009af6  lea     r8, [rbx+10h]
0x180009afa  lea     rdx, [rbp+57h+var_50]
0x180009afe  mov     rcx, rsi
0x180009b01  call    ??$_Find_last@_K@?$_Hash@V?$_Umap_traits@_KUWlanRpcClientMapEntry@WlanRpcServerContext@details@rpc_server@wlansvc@@V?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@U?$pair@$$CB_KUWlanRpcClientMapEntry@WlanRpcServerContext@details@rpc_server@wlansvc@@@std@@@7@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CB_KUWlanRpcClientMapEntry@WlanRpcServerContext@details@rpc_server@wlansvc@@@std@@PEAX@std@@@1@AEB_K_K@Z; std::_Hash<std::_Umap_traits<unsigned __int64,wlansvc::rpc_server::details::WlanRpcServerContext::WlanRpcClientMapEntry,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,wlansvc::rpc_server::details::WlanRpcServerContext::WlanRpcClientMapEntry>>,0>>::_Find_last<unsigned __int64>(unsigned __int64 const &,unsigned __int64)
0x180009b06  mov     r15, [rax]
0x180009b09  mov     rdx, [rbp+57h+var_90]
0x180009b0d  jmp     loc_18000991E
0x180009b12  cmp     [rax+rdi*8+8], rcx
0x180009b17  jnz     loc_18000995A
0x180009b1d  jmp     loc_180009A2C
```
