# CVdsVolume::ShrinkFileSystem(unsigned __int64,unsigned __int64,unsigned __int64 *,CVdsServiceAsyncObject *)

- ea: `0x1400439b0`
- end: `0x140043eb8`
- name: `?ShrinkFileSystem@CVdsVolume@@QEAAJ_K0PEA_KPEAVCVdsServiceAsyncObject@@@Z`
- size: `1288`
- prototype: `__int64 __fastcall(CVdsVolume *__hidden this, unsigned __int64, unsigned __int64, unsigned __int64 *, struct CVdsServiceAsyncObject *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140043ec0`

## callees

- `0x140012c48`
- `0x140028fc8`
- `0x14002e123`
- `0x1400439b0`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140043e6b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140043e6b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140043a5e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140043a5e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140043ad3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140043ad3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140043c34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140043c5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140043c83`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140043caf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140043cd8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140043d02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140043e56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140043c34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140043c5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140043c83`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140043caf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140043cd8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140043d02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140043e56`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140043b4d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140043bb5`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140043b4d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140043bb5`
- `vdsutil!?SetCompletionStatus@CVdsAsyncObjectBase@@QEAAXJK@Z` at `0x140043d27`
- `vdsutil!?SetCompletionStatus@CVdsAsyncObjectBase@@QEAAXJK@Z` at `0x140043d27`
- `vdsutil!VdsTraceEx` at `0x140043aaa`
- `vdsutil!VdsTraceEx` at `0x140043d65`
- `vdsutil!VdsTraceEx` at `0x140043aaa`
- `vdsutil!VdsTraceEx` at `0x140043d65`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140043a48`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140043a48`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140043e77`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140043e77`

## string_xrefs

- `0x140043adf`: `CVdsVolume::ShrinkFileSystem: CoCreateInstance failed to launch shrink engine: %X`
- `0x140043d9c`: `CVdsVolume::ShrinkFileSystem: IVolumeShrink::Shrink() wait for completion failed: %X`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CVdsVolume::ShrinkFileSystem(
        CVdsVolume *this,
        __int64 a2,
        __int64 a3,
        unsigned __int64 *a4,
        struct CVdsServiceAsyncObject *a5)
{
  unsigned int v9; // ecx
  __int64 v10; // rax
  HRESULT Instance; // eax
  int v12; // ebx
  const char *v13; // r8
  __int64 v14; // r9
  unsigned int v15; // ecx
  int v16; // edi
  int v17; // esi
  unsigned int v18; // r14d
  unsigned int v19; // edi
  char *i; // rcx
  __int64 v21; // rbx
  __int64 v22; // rax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  __int64 v26; // rax
  LPVOID ppv[2]; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID pv[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v30; // [rsp+50h] [rbp-B0h] BYREF
  int v31; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v32; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v33; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v34[16]; // [rsp+70h] [rbp-90h] BYREF
  struct _GUID v35[4]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v36; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v37[232]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v38; // [rsp+1B8h] [rbp+B8h]

  v31 = 0;
  memset(v35, 0, 56);
  ppv[0] = 0;
  v32 = 0;
  memset_0(v37, 0, 0x280u);
  v36 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v34, 0x5Eu, "CVdsVolume::ShrinkFileSystem()");
  *a4 = 0;
  EnterCriticalSection(&g_GlobalCriticalSection);
  v10 = *((_QWORD *)this + 19);
  if ( v10 )
    *(_WORD *)(v10 + 2) |= 8u;
  CVdsService::SendVolumeNotification(v9, v35);
  Instance = (*(__int64 (__fastcall **)(_QWORD, struct _GUID *))(**((_QWORD **)this + 16) + 24LL))(
               *((_QWORD *)this + 16),
               v35);
  v12 = Instance;
  if ( Instance < 0 )
  {
    v13 = "CVdsVolume::ShrinkFileSystem: GetProperties failed: %X";
LABEL_5:
    v14 = (unsigned int)Instance;
LABEL_6:
    VdsTraceEx(94, 0, v13, v14);
    goto LABEL_60;
  }
  Instance = CoCreateInstance(&CLSID_CDefragEngine, 0, 4u, &IID_IDefragEngine, ppv);
  v12 = Instance;
  if ( Instance < 0 )
  {
    v13 = "CVdsVolume::ShrinkFileSystem: CoCreateInstance failed to launch shrink engine: %X";
    goto LABEL_5;
  }
  v16 = 0;
  while ( 1 )
  {
    v12 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64, __int64, __int128 *))(*(_QWORD *)ppv[0] + 88LL))(
            ppv[0],
            *(_QWORD *)&v35[3].Data1,
            *(_QWORD *)&v35[2].Data1 - a2,
            *(_QWORD *)&v35[2].Data1 - a3,
            &v36);
    if ( v12 != 1 )
      break;
    *(_OWORD *)pv = v36;
    v12 = (*(__int64 (__fastcall **)(LPVOID, LPVOID *))(*(_QWORD *)ppv[0] + 40LL))(ppv[0], pv);
    if ( v12 < 0 )
      goto LABEL_60;
    Sleep(0x1F4u);
    if ( (unsigned int)++v16 >= 0xA )
    {
      v12 = -2147211887;
      goto LABEL_60;
    }
  }
  if ( v12 < 0 )
  {
    if ( v12 == -1996488683 )
    {
      v12 = -2147211878;
    }
    else if ( v12 == -1996488698 )
    {
      v12 = -2147211879;
    }
    v13 = "CVdsVolume::ShrinkFileSystem: IVoluemShrink::Shrink() failed: %X";
LABEL_20:
    v14 = (unsigned int)v12;
    goto LABEL_6;
  }
  while ( 1 )
  {
    pv[0] = 0;
    v30 = 0;
    v17 = 0;
    v18 = 100;
    Sleep(0x1F4u);
    if ( (*(int (__fastcall **)(LPVOID, _QWORD, unsigned int *, LPVOID *))(*(_QWORD *)ppv[0] + 128LL))(
           ppv[0],
           *(_QWORD *)&v35[3].Data1,
           &v30,
           pv) >= 0 )
    {
      v19 = 0;
      for ( i = (char *)pv[0]; v19 < v30; ++v19 )
      {
        v21 = 208LL * v19;
        v22 = *(_QWORD *)&i[v21 + 12] - v36;
        if ( !v22 )
          v22 = *(_QWORD *)&i[v21 + 20] - *((_QWORD *)&v36 + 1);
        if ( !v22 && *(_DWORD *)&i[v21 + 8] == 1 )
        {
          v17 = 1;
          v18 = *(_DWORD *)&i[v21 + 28];
        }
        if ( *(_QWORD *)&i[v21 + 104] )
        {
          CoTaskMemFree(*(LPVOID *)&i[v21 + 104]);
          *(_QWORD *)((char *)pv[0] + v21 + 104) = 0;
          i = (char *)pv[0];
        }
        if ( *(_QWORD *)&i[v21 + 120] )
        {
          CoTaskMemFree(*(LPVOID *)&i[v21 + 120]);
          *(_QWORD *)((char *)pv[0] + v21 + 120) = 0;
          i = (char *)pv[0];
        }
        if ( *(_QWORD *)&i[v21 + 144] )
        {
          CoTaskMemFree(*(LPVOID *)&i[v21 + 144]);
          *(_QWORD *)((char *)pv[0] + v21 + 144) = 0;
          i = (char *)pv[0];
        }
        if ( *(_QWORD *)&i[v21 + 136] )
        {
          CoTaskMemFree(*(LPVOID *)&i[v21 + 136]);
          *(_QWORD *)((char *)pv[0] + v21 + 136) = 0;
          i = (char *)pv[0];
        }
        if ( *(_QWORD *)&i[v21 + 112] )
        {
          CoTaskMemFree(*(LPVOID *)&i[v21 + 112]);
          *(_QWORD *)((char *)pv[0] + v21 + 112) = 0;
          i = (char *)pv[0];
        }
      }
      if ( i )
      {
        CoTaskMemFree(i);
        pv[0] = 0;
      }
    }
    if ( *((_DWORD *)a5 + 30) )
      break;
    if ( !v17 )
      goto LABEL_46;
    CVdsAsyncObjectBase::SetCompletionStatus(a5, -2147212279, v18);
  }
  v33 = v36;
  v23 = (*(__int64 (__fastcall **)(LPVOID, __int128 *))(*(_QWORD *)ppv[0] + 40LL))(ppv[0], &v33);
  if ( v23 < 0 )
    VdsTraceEx(94, 0, "CVdsVolume::ShrinkFileSystem: IVolumeShrink::Shrink() Defrag Cancel operation failed: %X", v23);
LABEL_46:
  v33 = v36;
  v24 = (*(__int64 (__fastcall **)(LPVOID, __int128 *, int *))(*(_QWORD *)ppv[0] + 160LL))(ppv[0], &v33, &v31);
  v12 = v24;
  if ( v24 < 0 )
  {
    v14 = (unsigned int)v24;
    v13 = "CVdsVolume::ShrinkFileSystem: IVolumeShrink::Shrink() wait for completion failed: %X";
    goto LABEL_6;
  }
  v12 = v31;
  if ( v31 < 0 )
  {
    switch ( v31 )
    {
      case -1996488671:
        v12 = -2147211916;
        break;
      case -1996488683:
        v12 = -2147211878;
        break;
      case -1996488698:
      case -1996488686:
        v12 = -2147211879;
        break;
    }
    v13 = "CVdsVolume::ShrinkFileSystem: IVolumeShrink::Shrink() operation failed: %X";
    goto LABEL_20;
  }
  v25 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _BYTE *))(*(_QWORD *)ppv[0] + 136LL))(
          ppv[0],
          *(_QWORD *)&v35[3].Data1,
          v37);
  v12 = v25;
  if ( v25 < 0 )
  {
    v14 = (unsigned int)v25;
    v13 = "CVdsVolume::ShrinkFileSystem: IVoluemShrink::Shrink() getting volume statistics failed: %X";
    goto LABEL_6;
  }
  *a4 = *(_QWORD *)&v35[2].Data1 - v38;
LABEL_60:
  v26 = *((_QWORD *)this + 19);
  if ( v26 )
  {
    v15 = 65527;
    *(_WORD *)(v26 + 2) &= ~8u;
  }
  CVdsService::SendVolumeNotification(v15, v35);
  if ( *(_QWORD *)&v35[3].Data1 )
  {
    CoTaskMemFree(*(LPVOID *)&v35[3].Data1);
    *(_QWORD *)&v35[3].Data1 = 0;
  }
  LeaveCriticalSection(&g_GlobalCriticalSection);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v34);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v32);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)ppv);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1400439b0  push    rbp
0x1400439b2  push    rbx
0x1400439b3  push    rsi
0x1400439b4  push    rdi
0x1400439b5  push    r12
0x1400439b7  push    r13
0x1400439b9  push    r14
0x1400439bb  push    r15
0x1400439bd  lea     rbp, [rsp-268h]
0x1400439c5  sub     rsp, 368h
0x1400439cc  mov     rax, cs:__security_cookie
0x1400439d3  xor     rax, rsp
0x1400439d6  mov     [rbp+2A0h+var_48], rax
0x1400439dd  mov     r12, r9
0x1400439e0  mov     r14, r8
0x1400439e3  mov     rsi, rdx
0x1400439e6  mov     r13, rcx
0x1400439e9  mov     r15, [rbp+2A0h+arg_20]
0x1400439f0  mov     [rsp+3A0h+var_34C], 0
0x1400439f8  mov     dword ptr [rbp+2A0h+var_320], 0
0x1400439ff  xorps   xmm0, xmm0
0x140043a02  xor     eax, eax
0x140043a04  movups  xmmword ptr [rbp+2A0h+var_320+4], xmm0
0x140043a08  movups  [rbp+2A0h+var_30C], xmm0
0x140043a0c  movups  xmmword ptr [rbp+2A0h+var_2FC], xmm0
0x140043a10  mov     [rbp+2A0h+var_2EC], eax
0x140043a13  mov     [rsp+3A0h+var_370], rax
0x140043a18  mov     [rsp+3A0h+var_348], rax
0x140043a1d  xor     edx, edx; Val
0x140043a1f  mov     r8d, 280h; Size
0x140043a25  lea     rcx, [rbp+2A0h+var_2D0]; void *
0x140043a29  call    memset_0
0x140043a2e  xorps   xmm0, xmm0
0x140043a31  movups  [rbp+2A0h+var_2E0], xmm0
0x140043a35  lea     r8, aCvdsvolumeShri_12; "CVdsVolume::ShrinkFileSystem()"
0x140043a3c  mov     edi, 5Eh ; '^'
0x140043a41  mov     edx, edi
0x140043a43  lea     rcx, [rsp+3A0h+var_330]
0x140043a48  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140043a4e  nop
0x140043a4f  mov     qword ptr [r12], 0
0x140043a57  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140043a5e  call    cs:__imp_EnterCriticalSection
0x140043a64  nop
0x140043a65  mov     rax, [r13+98h]
0x140043a6c  test    rax, rax
0x140043a6f  jz      short loc_140043A76
0x140043a71  or      word ptr [rax+2], 8
0x140043a76  lea     rdx, [rbp+2A0h+var_320]; struct _GUID *
0x140043a7a  call    ?SendVolumeNotification@CVdsService@@SAXKAEAU_GUID@@@Z; CVdsService::SendVolumeNotification(ulong,_GUID &)
0x140043a7f  mov     rcx, [r13+80h]
0x140043a86  mov     rax, [rcx]
0x140043a89  lea     rdx, [rbp+2A0h+var_320]
0x140043a8d  mov     rax, [rax+18h]
0x140043a91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140043a96  mov     ebx, eax
0x140043a98  xor     edx, edx; pUnkOuter
0x140043a9a  test    eax, eax
0x140043a9c  jns     short loc_140043AB5
0x140043a9e  lea     r8, aCvdsvolumeShri_11; "CVdsVolume::ShrinkFileSystem: GetProper"...
0x140043aa5  mov     r9d, eax
0x140043aa8  mov     ecx, edi
0x140043aaa  call    cs:__imp_VdsTraceEx
0x140043ab0  jmp     loc_140043E2F
0x140043ab5  lea     rax, [rsp+3A0h+var_370]
0x140043aba  mov     [rsp+3A0h+ppv], rax; ppv
0x140043abf  lea     r9, IID_IDefragEngine; riid
0x140043ac6  mov     r8d, 4; dwClsContext
0x140043acc  lea     rcx, CLSID_CDefragEngine; rclsid
0x140043ad3  call    cs:__imp_CoCreateInstance
0x140043ad9  mov     ebx, eax
0x140043adb  test    eax, eax
0x140043add  jns     short loc_140043AEA
0x140043adf  lea     r8, aCvdsvolumeShri_22; "CVdsVolume::ShrinkFileSystem: CoCreateI"...
0x140043ae6  xor     edx, edx
0x140043ae8  jmp     short loc_140043AA5
0x140043aea  xor     edi, edi
0x140043aec  mov     rcx, [rsp+3A0h+var_370]
0x140043af1  mov     rax, [rcx]
0x140043af4  mov     r8, qword ptr [rbp+2A0h+var_30C+0Ch]
0x140043af8  mov     r9, r8
0x140043afb  sub     r9, r14
0x140043afe  sub     r8, rsi
0x140043b01  lea     rdx, [rbp+2A0h+var_2E0]
0x140043b05  mov     [rsp+3A0h+ppv], rdx
0x140043b0a  mov     rdx, [rbp+2A0h+var_2FC+0Ch]
0x140043b0e  mov     rax, [rax+58h]
0x140043b12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140043b17  mov     ebx, eax
0x140043b19  cmp     eax, 1
0x140043b1c  jnz     short loc_140043B64
0x140043b1e  mov     rcx, [rsp+3A0h+var_370]
0x140043b23  movaps  xmm0, [rbp+2A0h+var_2E0]
0x140043b27  movdqa  xmmword ptr [rsp+3A0h+pv], xmm0
0x140043b2d  mov     rax, [rcx]
0x140043b30  lea     rdx, [rsp+3A0h+pv]
0x140043b35  mov     rax, [rax+28h]
0x140043b39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140043b3e  mov     ebx, eax
0x140043b40  test    eax, eax
0x140043b42  js      loc_140043E2F
0x140043b48  mov     ecx, 1F4h; dwMilliseconds
0x140043b4d  call    cs:__imp_Sleep
0x140043b53  inc     edi
0x140043b55  cmp     edi, 0Ah
0x140043b58  jb      short loc_140043AEC
0x140043b5a  mov     ebx, 80042591h
0x140043b5f  jmp     loc_140043E2F
0x140043b64  test    ebx, ebx
0x140043b66  jns     short loc_140043B99
0x140043b68  cmp     ebx, 89000015h
0x140043b6e  jnz     short loc_140043B77
0x140043b70  mov     ebx, 8004259Ah
0x140043b75  jmp     short loc_140043B85
0x140043b77  mov     eax, 80042599h
0x140043b7c  cmp     ebx, 89000006h
0x140043b82  cmovz   ebx, eax
0x140043b85  lea     r8, aCvdsvolumeShri_20; "CVdsVolume::ShrinkFileSystem: IVoluemSh"...
0x140043b8c  mov     r9d, ebx
0x140043b8f  xor     edx, edx
0x140043b91  lea     ecx, [rdx+5Eh]
0x140043b94  jmp     loc_140043AAA
0x140043b99  mov     [rsp+3A0h+pv], 0
0x140043ba2  mov     [rsp+3A0h+var_350], 0
0x140043baa  xor     esi, esi
0x140043bac  mov     ecx, 1F4h; dwMilliseconds
0x140043bb1  lea     r14d, [rsi+64h]
0x140043bb5  call    cs:__imp_Sleep
0x140043bbb  mov     rcx, [rsp+3A0h+var_370]
0x140043bc0  mov     rax, [rcx]
0x140043bc3  lea     r9, [rsp+3A0h+pv]
0x140043bc8  lea     r8, [rsp+3A0h+var_350]
0x140043bcd  mov     rdx, [rbp+2A0h+var_2FC+0Ch]
0x140043bd1  mov     rax, [rax+80h]
0x140043bd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140043bdd  test    eax, eax
0x140043bdf  js      loc_140043D11
0x140043be5  xor     edi, edi
0x140043be7  mov     rcx, [rsp+3A0h+pv]
0x140043bec  cmp     [rsp+3A0h+var_350], esi
0x140043bf0  jbe     loc_140043CFD
0x140043bf6  mov     eax, edi
0x140043bf8  imul    rbx, rax, 0D0h
0x140043bff  mov     rax, [rbx+rcx+0Ch]
0x140043c04  sub     rax, qword ptr [rbp+2A0h+var_2E0]
0x140043c08  jnz     short loc_140043C13
0x140043c0a  mov     rax, [rbx+rcx+14h]
0x140043c0f  sub     rax, qword ptr [rbp+2A0h+var_2E0+8]
0x140043c13  test    rax, rax
0x140043c16  jnz     short loc_140043C27
0x140043c18  cmp     dword ptr [rbx+rcx+8], 1
0x140043c1d  jnz     short loc_140043C27
0x140043c1f  lea     esi, [rax+1]
0x140043c22  mov     r14d, [rbx+rcx+1Ch]
0x140043c27  mov     rax, [rbx+rcx+68h]
0x140043c2c  test    rax, rax
0x140043c2f  jz      short loc_140043C4D
0x140043c31  mov     rcx, rax; pv
0x140043c34  call    cs:__imp_CoTaskMemFree
0x140043c3a  mov     rax, [rsp+3A0h+pv]
0x140043c3f  mov     qword ptr [rbx+rax+68h], 0
0x140043c48  mov     rcx, [rsp+3A0h+pv]
0x140043c4d  mov     rax, [rbx+rcx+78h]
0x140043c52  test    rax, rax
0x140043c55  jz      short loc_140043C73
0x140043c57  mov     rcx, rax; pv
0x140043c5a  call    cs:__imp_CoTaskMemFree
0x140043c60  mov     rax, [rsp+3A0h+pv]
0x140043c65  mov     qword ptr [rbx+rax+78h], 0
0x140043c6e  mov     rcx, [rsp+3A0h+pv]
0x140043c73  mov     rax, [rbx+rcx+90h]
0x140043c7b  test    rax, rax
0x140043c7e  jz      short loc_140043C9F
0x140043c80  mov     rcx, rax; pv
0x140043c83  call    cs:__imp_CoTaskMemFree
0x140043c89  mov     rax, [rsp+3A0h+pv]
0x140043c8e  mov     qword ptr [rbx+rax+90h], 0
0x140043c9a  mov     rcx, [rsp+3A0h+pv]
0x140043c9f  mov     rax, [rbx+rcx+88h]
0x140043ca7  test    rax, rax
0x140043caa  jz      short loc_140043CCB
0x140043cac  mov     rcx, rax; pv
0x140043caf  call    cs:__imp_CoTaskMemFree
0x140043cb5  mov     rax, [rsp+3A0h+pv]
0x140043cba  mov     qword ptr [rbx+rax+88h], 0
0x140043cc6  mov     rcx, [rsp+3A0h+pv]
0x140043ccb  mov     rax, [rbx+rcx+70h]
0x140043cd0  test    rax, rax
0x140043cd3  jz      short loc_140043CF1
0x140043cd5  mov     rcx, rax; pv
0x140043cd8  call    cs:__imp_CoTaskMemFree
0x140043cde  mov     rax, [rsp+3A0h+pv]
0x140043ce3  mov     qword ptr [rbx+rax+70h], 0
0x140043cec  mov     rcx, [rsp+3A0h+pv]; pv
0x140043cf1  inc     edi
0x140043cf3  cmp     edi, [rsp+3A0h+var_350]
0x140043cf7  jb      loc_140043BF6
0x140043cfd  test    rcx, rcx
0x140043d00  jz      short loc_140043D11
0x140043d02  call    cs:__imp_CoTaskMemFree
0x140043d08  mov     [rsp+3A0h+pv], 0
0x140043d11  cmp     dword ptr [r15+78h], 0
0x140043d16  jnz     short loc_140043D32
0x140043d18  test    esi, esi
0x140043d1a  jz      short loc_140043D6B
0x140043d1c  mov     r8d, r14d
0x140043d1f  mov     edx, 80042409h
0x140043d24  mov     rcx, r15
0x140043d27  call    cs:__imp_?SetCompletionStatus@CVdsAsyncObjectBase@@QEAAXJK@Z; CVdsAsyncObjectBase::SetCompletionStatus(long,ulong)
0x140043d2d  jmp     loc_140043B99
0x140043d32  mov     rcx, [rsp+3A0h+var_370]
0x140043d37  movaps  xmm0, [rbp+2A0h+var_2E0]
0x140043d3b  movdqa  [rsp+3A0h+var_340], xmm0
0x140043d41  mov     rax, [rcx]
0x140043d44  lea     rdx, [rsp+3A0h+var_340]
0x140043d49  mov     rax, [rax+28h]
0x140043d4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140043d52  test    eax, eax
0x140043d54  jns     short loc_140043D6B
0x140043d56  mov     r9d, eax
0x140043d59  lea     r8, aCvdsvolumeShri; "CVdsVolume::ShrinkFileSystem: IVolumeSh"...
0x140043d60  xor     edx, edx
0x140043d62  lea     ecx, [rdx+5Eh]
0x140043d65  call    cs:__imp_VdsTraceEx
0x140043d6b  mov     rcx, [rsp+3A0h+var_370]
0x140043d70  movaps  xmm0, [rbp+2A0h+var_2E0]
0x140043d74  movdqa  [rsp+3A0h+var_340], xmm0
0x140043d7a  mov     rax, [rcx]
0x140043d7d  lea     r8, [rsp+3A0h+var_34C]
0x140043d82  lea     rdx, [rsp+3A0h+var_340]
0x140043d87  mov     rax, [rax+0A0h]
0x140043d8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140043d93  mov     ebx, eax
0x140043d95  test    eax, eax
0x140043d97  jns     short loc_140043DA8
0x140043d99  mov     r9d, eax
0x140043d9c  lea     r8, aCvdsvolumeShri_1; "CVdsVolume::ShrinkFileSystem: IVolumeSh"...
0x140043da3  jmp     loc_140043B8F
0x140043da8  mov     ebx, [rsp+3A0h+var_34C]
0x140043dac  test    ebx, ebx
0x140043dae  jns     short loc_140043DEF
0x140043db0  cmp     ebx, 89000021h
0x140043db6  jnz     short loc_140043DBF
0x140043db8  mov     ebx, 80042574h
0x140043dbd  jmp     short loc_140043DE3
0x140043dbf  cmp     ebx, 89000015h
0x140043dc5  jnz     short loc_140043DCE
0x140043dc7  mov     ebx, 8004259Ah
0x140043dcc  jmp     short loc_140043DE3
0x140043dce  cmp     ebx, 89000006h
0x140043dd4  jz      short loc_140043DDE
0x140043dd6  cmp     ebx, 89000012h
0x140043ddc  jnz     short loc_140043DE3
0x140043dde  mov     ebx, 80042599h
0x140043de3  lea     r8, aCvdsvolumeShri_24; "CVdsVolume::ShrinkFileSystem: IVolumeSh"...
0x140043dea  jmp     loc_140043B8C
0x140043def  mov     rcx, [rsp+3A0h+var_370]
0x140043df4  mov     rax, [rcx]
0x140043df7  lea     r8, [rbp+2A0h+var_2D0]
0x140043dfb  mov     rdx, [rbp+2A0h+var_2FC+0Ch]
0x140043dff  mov     rax, [rax+88h]
0x140043e06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140043e0b  mov     ebx, eax
0x140043e0d  test    eax, eax
0x140043e0f  jns     short loc_140043E20
0x140043e11  mov     r9d, eax
0x140043e14  lea     r8, aCvdsvolumeShri_13; "CVdsVolume::ShrinkFileSystem: IVoluemSh"...
0x140043e1b  jmp     loc_140043B8F
0x140043e20  mov     rax, qword ptr [rbp+2A0h+var_30C+0Ch]
0x140043e24  sub     rax, [rbp+2A0h+var_1E8]
0x140043e2b  mov     [r12], rax
0x140043e2f  mov     rax, [r13+98h]
0x140043e36  test    rax, rax
0x140043e39  jz      short loc_140043E44
0x140043e3b  mov     ecx, 0FFF7h; unsigned int
0x140043e40  and     [rax+2], cx
0x140043e44  lea     rdx, [rbp+2A0h+var_320]; struct _GUID *
0x140043e48  call    ?SendVolumeNotification@CVdsService@@SAXKAEAU_GUID@@@Z; CVdsService::SendVolumeNotification(ulong,_GUID &)
0x140043e4d  mov     rcx, [rbp+2A0h+var_2FC+0Ch]; pv
0x140043e51  test    rcx, rcx
0x140043e54  jz      short loc_140043E64
0x140043e56  call    cs:__imp_CoTaskMemFree
0x140043e5c  mov     [rbp+2A0h+var_2FC+0Ch], 0
0x140043e64  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140043e6b  call    cs:__imp_LeaveCriticalSection
0x140043e71  nop
0x140043e72  lea     rcx, [rsp+3A0h+var_330]
0x140043e77  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140043e7d  nop
0x140043e7e  lea     rcx, [rsp+3A0h+var_348]
0x140043e83  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140043e88  nop
0x140043e89  lea     rcx, [rsp+3A0h+var_370]
0x140043e8e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140043e93  mov     eax, ebx
0x140043e95  mov     rcx, [rbp+2A0h+var_48]
0x140043e9c  xor     rcx, rsp; StackCookie
0x140043e9f  call    __security_check_cookie
0x140043ea4  add     rsp, 368h
0x140043eab  pop     r15
  ... truncated ...
```
