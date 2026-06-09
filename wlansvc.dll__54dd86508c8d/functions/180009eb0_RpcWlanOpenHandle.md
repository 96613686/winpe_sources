# RpcWlanOpenHandle

- ea: `0x180009eb0`
- end: `0x18000a3ba`
- name: `RpcWlanOpenHandle`
- size: `1290`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180009eb0`
- `0x18000a3c0`
- `0x18000a3f0`
- `0x18000a5a8`
- `0x18000a704`
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

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000a345`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000a345`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a177`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a177`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009f10`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009f10`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180009f78`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180009f78`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000a146`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000a146`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall RpcWlanOpenHandle(__int64 a1, int a2, _DWORD *a3, _QWORD *a4)
{
  LPCRITICAL_SECTION v4; // rbx
  __int64 v5; // r9
  int v6; // r8d
  _QWORD *OwningThread; // rcx
  _QWORD *i; // rax
  _QWORD *v9; // r14
  PTP_WORK ThreadpoolWork; // rax
  const char *v11; // r9
  struct _TP_WORK *v12; // r12
  HANDLE *v13; // r9
  __int64 v14; // r13
  unsigned __int64 j; // rcx
  ULONG_PTR SpinCount; // rdx
  _QWORD *v17; // rdi
  _QWORD *v18; // r15
  wlansvc::rpc_server::details::WlanRpcClientContext *v19; // rcx
  _QWORD *v20; // rax
  __int64 v21; // rdx
  float v22; // xmm0_4
  __int64 LockSemaphore; // rcx
  float v24; // xmm1_4
  _QWORD *v25; // rdx
  ULONG_PTR v26; // rcx
  __int64 v27; // rax
  _QWORD *v28; // r8
  wlansvc::rpc_server::details::WlanRpcClientContext *v29; // rsi
  __int64 v30; // rdi
  wlansvc::rpc_server::details::WlanRpcClientContext *v31; // rbx
  wil *v32; // rcx
  __int64 result; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  wil *v36; // rcx
  wil *v37; // rcx
  unsigned int v38; // [rsp+20h] [rbp-98h]
  unsigned int v39; // [rsp+20h] [rbp-98h]
  wlansvc::rpc_server::details::WlanRpcClientContext *v40; // [rsp+30h] [rbp-88h] BYREF
  wlansvc::rpc_server::details::WlanRpcClientContext *v41; // [rsp+38h] [rbp-80h]
  HANDLE *p_OwningThread; // [rsp+40h] [rbp-78h]
  _QWORD *v43; // [rsp+48h] [rbp-70h]
  PTP_WORK v44; // [rsp+50h] [rbp-68h]
  _QWORD *v45; // [rsp+58h] [rbp-60h]
  HANDLE *v46; // [rsp+60h] [rbp-58h]
  wlansvc::rpc_server::details::WlanRpcClientContext *v47; // [rsp+68h] [rbp-50h]
  PTP_WORK v48; // [rsp+70h] [rbp-48h]
  _QWORD *v49; // [rsp+78h] [rbp-40h]
  LPCRITICAL_SECTION v50[2]; // [rsp+80h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  try
  {
    if ( !a3 || !a4 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x76B,
        (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\server\\rpcsrv.cpp",
        (const char *)0x57,
        v38);
    *a4 = 0;
    v4 = lpCriticalSection;
    wlansvc::rpc_server::details::WlanRpcServerContext::CreateClientContext(
      (_DWORD)lpCriticalSection,
      (unsigned int)&v40,
      a2,
      0,
      0);
    EnterCriticalSection(v4);
    v50[0] = v4;
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
        v39);
    }
    v5 = *((unsigned int *)v40 + 97);
    v6 = 0;
    OwningThread = v4[3].OwningThread;
    for ( i = (_QWORD *)*OwningThread; i != OwningThread; i = (_QWORD *)*i )
    {
      if ( *(_DWORD *)(i[3] + 388LL) == (_DWORD)v5 && (unsigned int)++v6 >= 0x14 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 105)
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 24, &WPP_b841df4553e83e4110d3867191ccdd26_Traceguids, v5);
        }
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x3C7,
          (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\server\\rpcsrv.cpp",
          (const char *)0x4C4,
          v39);
      }
    }
    v9 = operator new(8u);
    *v9 = 0;
    v45 = v9;
    ThreadpoolWork = CreateThreadpoolWork(
                       wlansvc::rpc_server::details::WlanRpcServerContext::ClientCleanupWorkCallback,
                       v9,
                       (PTP_CALLBACK_ENVIRON)&v4[1]);
    v12 = ThreadpoolWork;
    v44 = ThreadpoolWork;
    if ( !ThreadpoolWork )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x2A3,
        (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\server\\rpcsrv.cpp",
        v11);
    v41 = v40;
    v13 = (HANDLE *)*((_QWORD *)v40 + 47);
    v46 = v13;
    p_OwningThread = v13;
    v40 = 0;
    v47 = v41;
    v48 = ThreadpoolWork;
    v44 = 0;
    v45 = 0;
    v49 = v9;
    v14 = 0xCBF29CE484222325uLL;
    for ( j = 0; j < 8; ++j )
      v14 = 0x100000001B3LL * (*((unsigned __int8 *)&p_OwningThread + j) ^ (unsigned __int64)v14);
    SpinCount = v4[3].SpinCount;
    v17 = *(_QWORD **)(SpinCount + 16 * ((__int64)v4[4].OwningThread & v14) + 8);
    v18 = v4[3].OwningThread;
    if ( v17 != v18 )
    {
      while ( v13 != (HANDLE *)v17[2] )
      {
        if ( v17 == *(_QWORD **)(SpinCount + 16 * ((__int64)v4[4].OwningThread & v14)) )
        {
          v18 = v17;
          goto LABEL_14;
        }
        v17 = (_QWORD *)v17[1];
      }
      goto LABEL_24;
    }
LABEL_14:
    if ( v4[3].LockSemaphore == (HANDLE)0x555555555555555LL )
      std::_Xlength_error("unordered_map/set too long");
    p_OwningThread = &v4[3].OwningThread;
    v43 = 0;
    v17 = std::_Allocate<16,std::_Default_allocate_traits>(0x30u);
    v43 = v17;
    v17[2] = v46;
    v19 = v41;
    v41 = 0;
    v47 = 0;
    v17[3] = v19;
    v17[4] = v12;
    v12 = 0;
    v48 = 0;
    v20 = v9;
    v9 = 0;
    v49 = 0;
    v17[5] = v20;
    v21 = (__int64)v4[3].LockSemaphore + 1;
    if ( v21 < 0 )
      v22 = (float)(v21 & 1 | (unsigned int)((unsigned __int64)v21 >> 1))
          + (float)(v21 & 1 | (unsigned int)((unsigned __int64)v21 >> 1));
    else
      v22 = (float)(int)v21;
    LockSemaphore = (__int64)v4[4].LockSemaphore;
    if ( LockSemaphore < 0 )
    {
      v34 = (__int64)v4[4].LockSemaphore & 1 | ((unsigned __int64)LockSemaphore >> 1);
      v24 = (float)(int)v34 + (float)(int)v34;
    }
    else
    {
      v24 = (float)(int)LockSemaphore;
    }
    if ( (float)(v22 / v24) > *(float *)&v4[3].LockCount )
    {
      v35 = std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Desired_grow_bucket_count(&v4[3].LockCount);
      std::_Hash<std::_Umap_traits<unsigned __int64,wlansvc::rpc_server::details::WlanRpcServerContext::WlanRpcClientMapEntry,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,wlansvc::rpc_server::details::WlanRpcServerContext::WlanRpcClientMapEntry>>,0>>::_Forced_rehash(
        &v4[3].LockCount,
        v35);
      v18 = (_QWORD *)*std::_Hash<std::_Umap_traits<unsigned __int64,wlansvc::rpc_server::details::WlanRpcServerContext::WlanRpcClientMapEntry,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,wlansvc::rpc_server::details::WlanRpcServerContext::WlanRpcClientMapEntry>>,0>>::_Find_last<unsigned __int64>(
                         &v4[3].LockCount,
                         v50,
                         v17 + 2,
                         v14);
    }
    v25 = (_QWORD *)v18[1];
    ++v4[3].LockSemaphore;
    *v17 = v18;
    v17[1] = v25;
    *v25 = v17;
    v18[1] = v17;
    v26 = v4[3].SpinCount;
    v27 = 2 * (v14 & (__int64)v4[4].OwningThread);
    v28 = *(_QWORD **)(v26 + 16 * (v14 & (__int64)v4[4].OwningThread));
    if ( v28 == v4[3].OwningThread )
    {
      *(_QWORD *)(v26 + 16 * (v14 & (__int64)v4[4].OwningThread)) = v17;
    }
    else
    {
      if ( v28 == v18 )
      {
        *(_QWORD *)(v26 + 16 * (v14 & (__int64)v4[4].OwningThread)) = v17;
LABEL_24:
        if ( v9 )
        {
          std::unique_ptr<wlansvc::rpc_server::details::WlanRpcClientContext>::~unique_ptr<wlansvc::rpc_server::details::WlanRpcClientContext>(v9);
          operator delete(v9, (const struct std::nothrow_t *)8);
        }
        if ( v12 )
          CloseThreadpoolWork(v12);
        v29 = v41;
        if ( v41 )
        {
          wlansvc::rpc_server::details::WlanRpcClientContext::~WlanRpcClientContext(v41);
          operator delete(v29, (const struct std::nothrow_t *)0x248);
        }
        v30 = v17[3];
        if ( v4 )
          LeaveCriticalSection(v4);
        v31 = v40;
        if ( v40 )
        {
          wlansvc::rpc_server::details::WlanRpcClientContext::~WlanRpcClientContext(v40);
          operator delete(v31, (const struct std::nothrow_t *)0x248);
        }
        *a4 = v30;
        *a3 = *(_DWORD *)(v30 + 384);
        v32 = (wil *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        {
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 12), 81, &WPP_b841df4553e83e4110d3867191ccdd26_Traceguids);
        }
        return 0;
      }
      if ( *(_QWORD **)(v26 + 16 * (v14 & (__int64)v4[4].OwningThread) + 8) != v25 )
        goto LABEL_24;
    }
    *(_QWORD *)(v26 + 8 * v27 + 8) = v17;
    goto LABEL_24;
  }
  catch ( ... )
  {
    if ( (int)wil::ResultFromCaughtException(v32) < 0 )
    {
      if ( (wil::ResultFromCaughtException(v36) & 0x1FFF0000) == 0x70000 )
        return (unsigned __int16)wil::ResultFromCaughtException(v37);
      else
        return (unsigned int)wil::ResultFromCaughtException(v37);
    }
    else
    {
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180009eb0  mov     rax, rsp
0x180009eb3  mov     [rax+8], rbx
0x180009eb7  mov     [rax+10h], rsi
0x180009ebb  mov     [rax+20h], r9
0x180009ebf  mov     [rax+18h], r8
0x180009ec3  push    rdi
0x180009ec4  push    r12
0x180009ec6  push    r13
0x180009ec8  push    r14
0x180009eca  push    r15
0x180009ecc  sub     rsp, 90h
0x180009ed3  mov     rax, r9
0x180009ed6  xor     edi, edi
0x180009ed8  test    r8, r8
0x180009edb  jz      loc_18000A38E
0x180009ee1  test    rax, rax
0x180009ee4  jz      loc_18000A38E
0x180009eea  mov     [r9], rdi
0x180009eed  mov     rbx, cs:lpCriticalSection
0x180009ef4  mov     byte ptr [rsp+0B8h+var_98], dil; unsigned int
0x180009ef9  xor     r9d, r9d
0x180009efc  mov     r8d, edx
0x180009eff  lea     rdx, [rsp+0B8h+var_88]
0x180009f04  mov     rcx, rbx
0x180009f07  call    ?CreateClientContext@WlanRpcServerContext@details@rpc_server@wlansvc@@AEAA?AV?$unique_ptr@VWlanRpcClientContext@details@rpc_server@wlansvc@@U?$default_delete@VWlanRpcClientContext@details@rpc_server@wlansvc@@@std@@@std@@K_N0@Z; wlansvc::rpc_server::details::WlanRpcServerContext::CreateClientContext(ulong,bool,bool)
0x180009f0c  nop
0x180009f0d  mov     rcx, rbx; lpCriticalSection
0x180009f10  call    cs:__imp_EnterCriticalSection
0x180009f16  mov     [rsp+0B8h+var_38], rbx
0x180009f1e  cmp     qword ptr [rbx+90h], 400h
0x180009f29  jnb     loc_18000A2D8
0x180009f2f  mov     rax, [rsp+0B8h+var_88]
0x180009f34  mov     r9d, [rax+184h]
0x180009f3b  mov     r8d, edi
0x180009f3e  lea     rsi, [rbx+80h]
0x180009f45  mov     rcx, [rsi+8]
0x180009f49  mov     rax, [rcx]
0x180009f4c  cmp     rax, rcx
0x180009f4f  jnz     loc_18000A218
0x180009f55  mov     ecx, 8; Size
0x180009f5a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009f5f  mov     r14, rax
0x180009f62  mov     [rax], rdi
0x180009f65  mov     [rsp+0B8h+var_60], rax
0x180009f6a  lea     r8, [rbx+28h]; pcbe
0x180009f6e  mov     rdx, rax; pv
0x180009f71  lea     rcx, ?ClientCleanupWorkCallback@WlanRpcServerContext@details@rpc_server@wlansvc@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180009f78  call    cs:__imp_CreateThreadpoolWork
0x180009f7e  mov     r12, rax
0x180009f81  mov     [rsp+0B8h+var_68], rax
0x180009f86  mov     rcx, [rsp+0B8h]; this
0x180009f8e  test    rax, rax
0x180009f91  jz      loc_18000A32C
0x180009f97  mov     r8, [rsp+0B8h+var_88]
0x180009f9c  mov     [rsp+0B8h+var_80], r8
0x180009fa1  mov     r9, [r8+178h]
0x180009fa8  mov     [rsp+0B8h+var_58], r9
0x180009fad  mov     [rsp+0B8h+var_78], r9
0x180009fb2  mov     [rsp+0B8h+var_88], rdi
0x180009fb7  mov     [rsp+0B8h+var_50], r8
0x180009fbc  mov     [rsp+0B8h+var_48], rax
0x180009fc1  mov     [rsp+0B8h+var_68], rdi
0x180009fc6  mov     [rsp+0B8h+var_60], 0
0x180009fcf  mov     [rsp+0B8h+var_40], r14
0x180009fd4  mov     r13, 0CBF29CE484222325h
0x180009fde  mov     rcx, rdi
0x180009fe1  movzx   eax, byte ptr [rsp+rcx+0B8h+var_78]
0x180009fe6  xor     r13, rax
0x180009fe9  mov     rdx, 100000001B3h
0x180009ff3  imul    r13, rdx
0x180009ff7  inc     rcx
0x180009ffa  cmp     rcx, 8
0x180009ffe  jb      short loc_180009FE1
0x18000a000  mov     rcx, r13
0x18000a003  and     rcx, [rsi+30h]
0x18000a007  mov     rdx, [rsi+18h]
0x18000a00b  mov     rax, rcx
0x18000a00e  add     rax, rax
0x18000a011  mov     rdi, [rdx+rax*8+8]
0x18000a016  mov     r15, [rsi+8]
0x18000a01a  cmp     rdi, r15
0x18000a01d  jz      short loc_18000A03C
0x18000a01f  add     rcx, rcx
0x18000a022  mov     rax, [rdx+rcx*8]
0x18000a026  cmp     r9, [rdi+10h]
0x18000a02a  jz      loc_18000A124
0x18000a030  cmp     rdi, rax
0x18000a033  jnz     loc_18000A28A
0x18000a039  mov     r15, rdi
0x18000a03c  mov     rax, 555555555555555h
0x18000a046  cmp     [rsi+10h], rax
0x18000a04a  jz      loc_18000A33E
0x18000a050  lea     rax, [rsi+8]
0x18000a054  mov     [rsp+0B8h+var_78], rax
0x18000a059  mov     [rsp+0B8h+var_70], 0
0x18000a062  mov     ecx, 30h ; '0'
0x18000a067  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000a06c  mov     rdi, rax
0x18000a06f  mov     [rsp+0B8h+var_70], rax
0x18000a074  mov     rax, [rsp+0B8h+var_58]
0x18000a079  mov     [rdi+10h], rax
0x18000a07d  mov     rcx, [rsp+0B8h+var_80]
0x18000a082  xor     eax, eax
0x18000a084  mov     [rsp+0B8h+var_80], rax
0x18000a089  mov     [rsp+0B8h+var_50], rax
0x18000a08e  mov     [rdi+18h], rcx
0x18000a092  mov     [rdi+20h], r12
0x18000a096  xor     r12d, r12d
0x18000a099  mov     [rsp+0B8h+var_48], r12
0x18000a09e  mov     rax, r14
0x18000a0a1  xor     r14d, r14d
0x18000a0a4  mov     [rsp+0B8h+var_40], r14
0x18000a0a9  mov     [rdi+28h], rax
0x18000a0ad  mov     rdx, [rsi+10h]
0x18000a0b1  add     rdx, 1
0x18000a0b5  xorps   xmm0, xmm0
0x18000a0b8  js      loc_18000A2A1
0x18000a0be  cvtsi2ss xmm0, rdx
0x18000a0c3  mov     rcx, [rsi+38h]
0x18000a0c7  xorps   xmm1, xmm1
0x18000a0ca  test    rcx, rcx
0x18000a0cd  js      loc_18000A2BE
0x18000a0d3  cvtsi2ss xmm1, rcx
0x18000a0d8  divss   xmm0, xmm1
0x18000a0dc  comiss  xmm0, dword ptr [rsi]
0x18000a0df  ja      loc_18000A34C
0x18000a0e5  mov     rdx, [r15+8]
0x18000a0e9  inc     qword ptr [rsi+10h]
0x18000a0ed  mov     [rdi], r15
0x18000a0f0  mov     [rdi+8], rdx
0x18000a0f4  mov     [rdx], rdi
0x18000a0f7  mov     [r15+8], rdi
0x18000a0fb  mov     rcx, [rsi+18h]
0x18000a0ff  mov     rax, [rsi+30h]
0x18000a103  and     rax, r13
0x18000a106  add     rax, rax
0x18000a109  mov     r8, [rcx+rax*8]
0x18000a10d  cmp     r8, [rsi+8]
0x18000a111  jz      loc_18000A293
0x18000a117  cmp     r8, r15
0x18000a11a  jnz     loc_18000A37E
0x18000a120  mov     [rcx+rax*8], rdi
0x18000a124  test    r14, r14
0x18000a127  jz      short loc_18000A13E
0x18000a129  mov     rcx, r14
0x18000a12c  call    ??1?$unique_ptr@VWlanRpcClientContext@details@rpc_server@wlansvc@@U?$default_delete@VWlanRpcClientContext@details@rpc_server@wlansvc@@@std@@@std@@QEAA@XZ; std::unique_ptr<wlansvc::rpc_server::details::WlanRpcClientContext>::~unique_ptr<wlansvc::rpc_server::details::WlanRpcClientContext>(void)
0x18000a131  mov     edx, 8; struct std::nothrow_t *
0x18000a136  mov     rcx, r14; void *
0x18000a139  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000a13e  test    r12, r12
0x18000a141  jz      short loc_18000A14C
0x18000a143  mov     rcx, r12; pwk
0x18000a146  call    cs:__imp_CloseThreadpoolWork
0x18000a14c  mov     rsi, [rsp+0B8h+var_80]
0x18000a151  test    rsi, rsi
0x18000a154  jz      short loc_18000A16B
0x18000a156  mov     rcx, rsi; this
0x18000a159  call    ??1WlanRpcClientContext@details@rpc_server@wlansvc@@QEAA@XZ; wlansvc::rpc_server::details::WlanRpcClientContext::~WlanRpcClientContext(void)
0x18000a15e  mov     edx, 248h; struct std::nothrow_t *
0x18000a163  mov     rcx, rsi; void *
0x18000a166  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000a16b  mov     rdi, [rdi+18h]
0x18000a16f  test    rbx, rbx
0x18000a172  jz      short loc_18000A17E
0x18000a174  mov     rcx, rbx; lpCriticalSection
0x18000a177  call    cs:__imp_LeaveCriticalSection
0x18000a17d  nop
0x18000a17e  mov     rbx, [rsp+0B8h+var_88]
0x18000a183  test    rbx, rbx
0x18000a186  jz      short loc_18000A19D
0x18000a188  mov     rcx, rbx; this
0x18000a18b  call    ??1WlanRpcClientContext@details@rpc_server@wlansvc@@QEAA@XZ; wlansvc::rpc_server::details::WlanRpcClientContext::~WlanRpcClientContext(void)
0x18000a190  mov     edx, 248h; struct std::nothrow_t *
0x18000a195  mov     rcx, rbx; void *
0x18000a198  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000a19d  mov     rax, [rsp+0B8h+arg_18]
0x18000a1a5  mov     [rax], rdi
0x18000a1a8  mov     eax, [rdi+180h]
0x18000a1ae  mov     rcx, [rsp+0B8h+arg_10]
0x18000a1b6  mov     [rcx], eax
0x18000a1b8  lea     rax, WPP_GLOBAL_Control
0x18000a1bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a1c6  cmp     rcx, rax
0x18000a1c9  jz      short loc_18000A1F9
0x18000a1cb  cmp     byte ptr [rcx+69h], 3
0x18000a1cf  jb      short loc_18000A1F9
0x18000a1d1  test    byte ptr [rcx+6Ch], 1
0x18000a1d5  jz      short loc_18000A1F9
0x18000a1d7  mov     edx, 51h ; 'Q'
0x18000a1dc  mov     eax, [rdi+180h]
0x18000a1e2  mov     [rsp+0B8h+var_98], eax
0x18000a1e6  mov     r9, rdi
0x18000a1e9  lea     r8, WPP_b841df4553e83e4110d3867191ccdd26_Traceguids
0x18000a1f0  mov     rcx, [rcx+60h]
0x18000a1f4  call    WPP_SF_qD
0x18000a1f9  xor     eax, eax
0x18000a1fb  lea     r11, [rsp+0B8h+var_28]
0x18000a203  mov     rbx, [r11+30h]
0x18000a207  mov     rsi, [r11+38h]
0x18000a20b  mov     rsp, r11
0x18000a20e  pop     r15
0x18000a210  pop     r14
0x18000a212  pop     r13
0x18000a214  pop     r12
0x18000a216  pop     rdi
0x18000a217  retn
0x18000a218  mov     rdx, [rax+18h]
0x18000a21c  cmp     [rdx+184h], r9d
0x18000a223  jz      short loc_18000A22D
0x18000a225  mov     rax, [rax]
0x18000a228  jmp     loc_180009F4C
0x18000a22d  inc     r8d
0x18000a230  cmp     r8d, 14h
0x18000a234  jb      short loc_18000A225
0x18000a236  lea     rax, WPP_GLOBAL_Control
0x18000a23d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a244  cmp     rcx, rax
0x18000a247  jz      short loc_18000A26A
0x18000a249  cmp     byte ptr [rcx+69h], 1
0x18000a24d  jb      short loc_18000A26A
0x18000a24f  test    byte ptr [rcx+6Ch], 1
0x18000a253  jz      short loc_18000A26A
0x18000a255  mov     edx, 18h
0x18000a25a  lea     r8, WPP_b841df4553e83e4110d3867191ccdd26_Traceguids
0x18000a261  mov     rcx, [rcx+60h]
0x18000a265  call    WPP_SF_d
0x18000a26a  mov     rcx, [rsp+0B8h]; this
0x18000a272  mov     r9d, 4C4h; char *
0x18000a278  lea     r8, aOnecoreuapNetW_7; "onecoreuap\\net\\wlan\\autocfg\\server"...
0x18000a27f  mov     edx, 3C7h; void *
0x18000a284  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18000a28a  mov     rdi, [rdi+8]
0x18000a28e  jmp     loc_18000A026
0x18000a293  mov     [rcx+rax*8], rdi
0x18000a297  mov     [rcx+rax*8+8], rdi
0x18000a29c  jmp     loc_18000A124
0x18000a2a1  mov     rcx, rdx
0x18000a2a4  shr     rcx, 1
0x18000a2a7  mov     rax, rdx
0x18000a2aa  and     eax, 1
0x18000a2ad  or      rcx, rax
0x18000a2b0  cvtsi2ss xmm0, rcx
0x18000a2b5  addss   xmm0, xmm0
0x18000a2b9  jmp     loc_18000A0C3
0x18000a2be  mov     rax, rcx
0x18000a2c1  shr     rax, 1
0x18000a2c4  and     ecx, 1
0x18000a2c7  or      rax, rcx
0x18000a2ca  cvtsi2ss xmm1, rax
0x18000a2cf  addss   xmm1, xmm1
0x18000a2d3  jmp     loc_18000A0D8
0x18000a2d8  lea     rax, WPP_GLOBAL_Control
0x18000a2df  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a2e6  cmp     rcx, rax
0x18000a2e9  jz      short loc_18000A30C
0x18000a2eb  cmp     byte ptr [rcx+69h], 1
0x18000a2ef  jb      short loc_18000A30C
0x18000a2f1  test    byte ptr [rcx+6Ch], 1
0x18000a2f5  jz      short loc_18000A30C
0x18000a2f7  mov     edx, 17h
0x18000a2fc  lea     r8, WPP_b841df4553e83e4110d3867191ccdd26_Traceguids
0x18000a303  mov     rcx, [rcx+60h]
0x18000a307  call    WPP_SF_
0x18000a30c  mov     rcx, [rsp+0B8h]; this
0x18000a314  mov     r9d, 4C4h; char *
0x18000a31a  lea     r8, aOnecoreuapNetW_7; "onecoreuap\\net\\wlan\\autocfg\\server"...
0x18000a321  mov     edx, 3BBh; void *
0x18000a326  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18000a32c  lea     r8, aOnecoreuapNetW_7; "onecoreuap\\net\\wlan\\autocfg\\server"...
0x18000a333  mov     edx, 2A3h; void *
0x18000a338  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000a33e  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x18000a345  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000a34c  mov     rcx, rsi
0x18000a34f  call    ?_Desired_grow_bucket_count@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@IEBA_K_K@Z; std::_Hash<std::_Umap_traits<std::wstring,ulong,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::_Desired_grow_bucket_count(unsigned __int64)
0x18000a354  mov     rdx, rax
0x18000a357  mov     rcx, rsi
0x18000a35a  call    ?_Forced_rehash@?$_Hash@V?$_Umap_traits@_KUWlanRpcClientMapEntry@WlanRpcServerContext@details@rpc_server@wlansvc@@V?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@U?$pair@$$CB_KUWlanRpcClientMapEntry@WlanRpcServerContext@details@rpc_server@wlansvc@@@std@@@7@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Umap_traits<unsigned __int64,wlansvc::rpc_server::details::WlanRpcServerContext::WlanRpcClientMapEntry,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,wlansvc::rpc_server::details::WlanRpcServerContext::WlanRpcClientMapEntry>>,0>>::_Forced_rehash(unsigned __int64)
0x18000a35f  mov     r9, r13
0x18000a362  lea     r8, [rdi+10h]
0x18000a366  lea     rdx, [rsp+0B8h+var_38]
0x18000a36e  mov     rcx, rsi
0x18000a371  call    ??$_Find_last@_K@?$_Hash@V?$_Umap_traits@_KUWlanRpcClientMapEntry@WlanRpcServerContext@details@rpc_server@wlansvc@@V?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@U?$pair@$$CB_KUWlanRpcClientMapEntry@WlanRpcServerContext@details@rpc_server@wlansvc@@@std@@@7@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CB_KUWlanRpcClientMapEntry@WlanRpcServerContext@details@rpc_server@wlansvc@@@std@@PEAX@std@@@1@AEB_K_K@Z; std::_Hash<std::_Umap_traits<unsigned __int64,wlansvc::rpc_server::details::WlanRpcServerContext::WlanRpcClientMapEntry,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,wlansvc::rpc_server::details::WlanRpcServerContext::WlanRpcClientMapEntry>>,0>>::_Find_last<unsigned __int64>(unsigned __int64 const &,unsigned __int64)
0x18000a376  mov     r15, [rax]
0x18000a379  jmp     loc_18000A0E5
0x18000a37e  cmp     [rcx+rax*8+8], rdx
0x18000a383  jnz     loc_18000A124
0x18000a389  jmp     loc_18000A297
0x18000a38e  mov     rcx, [rsp+0B8h]; this
0x18000a396  mov     r9d, 57h ; 'W'; char *
0x18000a39c  lea     r8, aOnecoreuapNetW_7; "onecoreuap\\net\\wlan\\autocfg\\server"...
0x18000a3a3  mov     edx, 76Bh; void *
0x18000a3a8  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18000a3ae  mov     eax, dword ptr [rsp+0B8h+arg_10]
0x18000a3b5  jmp     loc_18000A1FB
```
