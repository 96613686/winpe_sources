# CClassData::PrivilegedLaunchService(CToken *,ulong,ulong *)

- ea: `0x180073580`
- end: `0x180073aaf`
- name: `?PrivilegedLaunchService@CClassData@@QEAAJPEAVCToken@@KPEAK@Z`
- size: `1327`
- prototype: `__int64 __fastcall(CClassData *__hidden this, struct CToken *, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18009a6ec`
- `0x1800a19ec`

## callees

- `0x180011db0`
- `0x1800307c0`
- `0x180034260`
- `0x18003ca38`
- `0x18004a3f4`
- `0x180073580`
- `0x1800855d8`
- `0x1800a780c`
- `0x1800b7ac0`
- `0x1800b8428`
- `0x18010698c`
- `0x180112d00`
- `0x180114010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073611`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800737b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800737f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073611`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800737b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800737f9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180073967`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180073967`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800736c8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800736c8`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800737a4`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800737a4`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800735fd`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800735fd`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800736e1`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007394f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800736e1`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007394f`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1800737e2`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1800738cc`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1800737e2`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1800738cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180073a03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180073a70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180073a03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180073a70`

## string_xrefs

- `0x180073654`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x180073923`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x1800739d7`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x180073648`: `CClassData::PrivilegedLaunchService`
- `0x18007391c`: `CClassData::PrivilegedLaunchService`
- `0x1800739ce`: `CClassData::PrivilegedLaunchService`
- `0x18007365b`: `Service:%ws %!WINERROR!`

## pseudocode

```c
__int64 __fastcall CClassData::PrivilegedLaunchService(
        CClassData *this,
        struct CToken *a2,
        unsigned int a3,
        unsigned int *a4)
{
  CClassData *v6; // rcx
  const WCHAR *v7; // rax
  SC_HANDLE v8; // r13
  signed int LastError; // ebx
  unsigned __int16 *v10; // rax
  __int64 v12; // rax
  unsigned __int16 *v13; // rdi
  DWORD v14; // ebx
  __int64 v15; // rcx
  __int64 v16; // rax
  unsigned __int64 v17; // rsi
  __int64 v18; // rax
  const unsigned __int16 *v19; // r8
  __int64 v20; // r10
  unsigned __int16 *v21; // rcx
  __int64 v22; // rax
  LPCWSTR *v23; // r8
  BOOL started; // r15d
  signed int v25; // r14d
  __int64 v26; // rdx
  unsigned __int64 v27; // rsi
  DWORD *v28; // rbx
  unsigned __int64 v29; // rcx
  __int64 v30; // rcx
  unsigned __int64 v31; // rcx
  void *v32; // rsp
  void *v33; // rsp
  _DWORD *v34; // rax
  signed int v35; // edi
  __int64 v36; // rcx
  __int64 v37; // rax
  void (__fastcall *v38)(CClassData *, DWORD *); // rbx
  const unsigned __int16 *v39; // rax
  const unsigned __int16 *v40; // rdx
  __int64 v41; // [rsp+0h] [rbp-40h] BYREF
  unsigned int v42[2]; // [rsp+28h] [rbp-18h]
  __int64 v43; // [rsp+30h] [rbp-10h]
  DWORD cbBufSize[2]; // [rsp+40h] [rbp+0h] BYREF
  unsigned int v45; // [rsp+48h] [rbp+8h] BYREF
  unsigned int *v46; // [rsp+50h] [rbp+10h]
  struct CToken *v47; // [rsp+58h] [rbp+18h]
  _QWORD v48[16]; // [rsp+70h] [rbp+30h] BYREF

  v45 = a3;
  v47 = a2;
  v46 = a4;
  memset_0(v48, 0, sizeof(v48));
  if ( !CClassData::Service(this) )
    return 2147942487LL;
  *a4 = 0;
  v7 = CClassData::Service(v6);
  v8 = OpenServiceW(g_hServiceController, v7, 0xA0000000);
  if ( !v8 )
  {
    LastError = GetLastError();
    if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
    {
      v10 = CClassData::Service(this);
      LODWORD(v43) = LastError;
      ComTraceMessageT<unsigned __int64,unsigned long>(
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
        (unsigned int)"CClassData::PrivilegedLaunchService",
        3508,
        0,
        (__int64)L"Service:%ws %!WINERROR!",
        v10,
        v43);
    }
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
    return (unsigned int)LastError;
  }
  v12 = *((_QWORD *)this + 11);
  v13 = 0;
  v14 = 0;
  if ( v12 && *(_QWORD *)(v12 + 24) )
  {
    v15 = *(_QWORD *)(v12 + 24);
    v16 = -1;
    do
      ++v16;
    while ( *(_WORD *)(v15 + 2 * v16) );
    v17 = v16 + 1;
    v13 = (unsigned __int16 *)HeapAlloc(g_hHeap, 0, 2 * (v16 + 1));
    if ( !v13 )
    {
      CloseServiceHandle(v8);
      return 2147942414LL;
    }
    v18 = *((_QWORD *)this + 11);
    if ( v18 )
      v19 = *(const unsigned __int16 **)(v18 + 24);
    else
      v19 = 0;
    StringCchCopyW(v13, v17, v19);
    while ( v14 < 0x10 )
    {
      if ( v13[(unsigned int)v20] )
      {
        do
        {
          if ( v13[(unsigned int)v20] != 32 && v13[(unsigned int)v20] != 9 )
            break;
          v20 = (unsigned int)(v20 + 1);
        }
        while ( v13[v20] );
      }
      v21 = &v13[(unsigned int)v20];
      if ( *v21 )
      {
        v22 = v14++;
        v48[v22] = v21;
        if ( *v21 )
        {
          do
          {
            if ( v13[(unsigned int)v20] == 32 )
              break;
            if ( v13[(unsigned int)v20] == 9 )
              break;
            v20 = (unsigned int)(v20 + 1);
          }
          while ( v13[v20] );
        }
      }
      if ( v13[(unsigned int)v20] )
      {
        v13[(unsigned int)v20] = 0;
        LODWORD(v20) = v20 + 1;
      }
      if ( !v13[(unsigned int)v20] )
        goto LABEL_33;
    }
    return 2147942487LL;
  }
LABEL_33:
  v23 = (LPCWSTR *)v48;
  if ( !v14 )
    v23 = 0;
  started = StartServiceW(v8, v14, v23);
  v25 = GetLastError();
  if ( started )
  {
    cbBufSize[0] = 0;
    started = QueryServiceStatusEx(v8, SC_STATUS_PROCESS_INFO, 0, 0, cbBufSize);
    if ( !started && GetLastError() == 122 )
    {
      v27 = cbBufSize[0];
      v28 = 0;
      if ( cbBufSize[0] )
      {
        if ( cbBufSize[0] <= (unsigned __int64)g_ulMaxStackAllocSize )
        {
          v29 = cbBufSize[0] + g_ulAdditionalProbeSize + 8;
          if ( v29 >= cbBufSize[0] )
          {
            if ( (unsigned int)VerifyStackAvailable(v29, v26) )
            {
              v30 = v27 + 23;
              if ( v27 + 23 <= v27 + 8 )
                v30 = 0xFFFFFFFFFFFFFF0LL;
              v31 = v30 & 0xFFFFFFFFFFFFFFF0uLL;
              v32 = alloca(v31);
              v33 = alloca(v31);
              v28 = cbBufSize;
              if ( &v41 != (__int64 *)-64LL )
              {
                cbBufSize[0] = 1801679955;
                v28 = &v45;
                if ( &v45 )
                  goto LABEL_50;
              }
            }
          }
        }
      }
      if ( v27 + 8 >= v27 )
      {
        v34 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
        if ( !v34 )
          goto LABEL_59;
        *v34 = 1885431112;
        v28 = v34 + 2;
      }
      if ( v28 )
      {
LABEL_50:
        started = QueryServiceStatusEx(v8, SC_STATUS_PROCESS_INFO, (LPBYTE)v28, cbBufSize[0], cbBufSize);
        if ( started )
        {
          *v46 = v28[7];
        }
        else if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
        {
          ComTraceMessageT<>(
            (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
            (unsigned int)"CClassData::PrivilegedLaunchService",
            3603,
            0,
            (__int64)L"Failure");
        }
        if ( v28 && *(v28 - 2) == 1885431112 )
          ((void (*)(void))g_pfnFree)();
      }
    }
  }
LABEL_59:
  CloseServiceHandle(v8);
  HeapFree(g_hHeap, 0, v13);
  if ( started )
    return 0;
  if ( v25 > 0 )
    v35 = (unsigned __int16)v25 | 0x80070000;
  else
    v35 = v25;
  if ( v35 >= 0 )
  {
    if ( !gfEnableTracing )
      goto LABEL_70;
    v36 = 3;
LABEL_68:
    if ( (unsigned __int8)IsWppLevelEnabled(v36) )
      goto LABEL_69;
    goto LABEL_70;
  }
  if ( dword_1801574B8 )
  {
LABEL_69:
    v42[0] = v35;
    ComTraceHr(
      v35,
      "onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
      "CClassData::PrivilegedLaunchService",
      3621,
      L"hr:%!HRESULT!",
      *(_QWORD *)v42);
    goto LABEL_70;
  }
  if ( gfEnableTracing )
  {
    v36 = 0;
    goto LABEL_68;
  }
LABEL_70:
  if ( ((v25 - 1056) & 0xFFFFFFFD) != 0 )
  {
    v37 = *(_QWORD *)this;
    *(_QWORD *)cbBufSize = 0;
    v38 = *(void (__fastcall **)(CClassData *, DWORD *))(v37 + 80);
    WindowsDeleteString(0);
    *(_QWORD *)cbBufSize = 0;
    v38(this, cbBufSize);
    v39 = CClassData::Service(this);
    LogServiceStartError(*(HSTRING *)cbBufSize, v45, v47, v39, v40, v25);
    WindowsDeleteString(*(HSTRING *)cbBufSize);
  }
  return (unsigned int)v35;
}

```

## disassembly

```asm
0x180073580  push    rbp
0x180073582  push    rsi
0x180073583  push    rdi
0x180073584  push    r12
0x180073586  push    r13
0x180073588  push    r14
0x18007358a  push    r15
0x18007358c  sub     rsp, 100h
0x180073593  lea     rbp, [rsp+40h]
0x180073598  mov     [rbp+0F0h+arg_10], rbx
0x18007359f  mov     rax, cs:__security_cookie
0x1800735a6  xor     rax, rbp
0x1800735a9  mov     [rbp+0F0h+var_40], rax
0x1800735b0  mov     rbx, r9
0x1800735b3  mov     [rbp+0F0h+var_E8], r8d
0x1800735b7  mov     [rbp+0F0h+var_D8], rdx
0x1800735bb  mov     r12, rcx
0x1800735be  xor     edx, edx; Val
0x1800735c0  mov     [rbp+0F0h+var_E0], rbx
0x1800735c4  mov     r8d, 80h; Size
0x1800735ca  lea     rcx, [rbp+0F0h+var_C0]; void *
0x1800735ce  call    memset_0
0x1800735d3  mov     rcx, r12; this
0x1800735d6  call    ?Service@CClassData@@QEBAPEAGXZ; CClassData::Service(void)
0x1800735db  xor     esi, esi
0x1800735dd  test    rax, rax
0x1800735e0  jz      loc_180073A80
0x1800735e6  mov     [rbx], esi
0x1800735e8  call    ?Service@CClassData@@QEBAPEAGXZ; CClassData::Service(void)
0x1800735ed  mov     rcx, cs:?g_hServiceController@@3PEAUSC_HANDLE__@@EA; hSCManager
0x1800735f4  mov     rdx, rax; lpServiceName
0x1800735f7  mov     r8d, 0A0000000h; dwDesiredAccess
0x1800735fd  call    cs:__imp_OpenServiceW
0x180073604  nop     dword ptr [rax+rax+00h]
0x180073609  mov     r13, rax
0x18007360c  test    rax, rax
0x18007360f  jnz     short loc_180073689
0x180073611  call    cs:__imp_GetLastError
0x180073618  nop     dword ptr [rax+rax+00h]
0x18007361d  mov     ebx, eax
0x18007361f  mov     eax, cs:dword_1801574B8
0x180073625  test    eax, eax
0x180073627  jnz     short loc_18007363C
0x180073629  cmp     cs:?gfEnableTracing@@3HA, esi; int gfEnableTracing
0x18007362f  jz      short loc_180073675
0x180073631  xor     ecx, ecx
0x180073633  call    IsWppLevelEnabled
0x180073638  test    al, al
0x18007363a  jz      short loc_180073675
0x18007363c  mov     rcx, r12; this
0x18007363f  call    ?Service@CClassData@@QEBAPEAGXZ; CClassData::Service(void)
0x180073644  mov     dword ptr [rsp+130h+var_100], ebx
0x180073648  lea     rdx, aCclassdataPriv; "CClassData::PrivilegedLaunchService"
0x18007364f  mov     qword ptr [rsp+130h+var_108], rax
0x180073654  lea     rcx, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x18007365b  lea     rax, aServiceWsWiner; "Service:%ws %!WINERROR!"
0x180073662  xor     r9d, r9d
0x180073665  mov     r8d, 0DB4h
0x18007366b  mov     [rsp+130h+pcbBytesNeeded], rax
0x180073670  call    ??$ComTraceMessageT@_KK@@YAXPEBD0HW4TraceLevel@@PEBG_KK@Z; ComTraceMessageT<unsigned __int64,ulong>(char const *,char const *,int,TraceLevel,ushort const *,unsigned __int64,ulong)
0x180073675  test    ebx, ebx
0x180073677  jle     short loc_180073682
0x180073679  movzx   ebx, bx
0x18007367c  or      ebx, 80070000h
0x180073682  mov     eax, ebx
0x180073684  jmp     loc_180073A85
0x180073689  mov     rax, [r12+58h]
0x18007368e  mov     rdi, rsi
0x180073691  mov     ebx, esi
0x180073693  test    rax, rax
0x180073696  jz      loc_180073795
0x18007369c  cmp     [rax+18h], rsi
0x1800736a0  jz      loc_180073795
0x1800736a6  mov     rcx, [rax+18h]
0x1800736aa  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800736ae  inc     rax
0x1800736b1  cmp     [rcx+rax*2], si
0x1800736b5  jnz     short loc_1800736AE
0x1800736b7  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800736be  lea     rsi, [rax+1]
0x1800736c2  lea     r8, [rsi+rsi]; dwBytes
0x1800736c6  xor     edx, edx; dwFlags
0x1800736c8  call    cs:__imp_HeapAlloc
0x1800736cf  nop     dword ptr [rax+rax+00h]
0x1800736d4  xor     ecx, ecx
0x1800736d6  mov     rdi, rax
0x1800736d9  test    rax, rax
0x1800736dc  jnz     short loc_1800736F7
0x1800736de  mov     rcx, r13; hSCObject
0x1800736e1  call    cs:__imp_CloseServiceHandle
0x1800736e8  nop     dword ptr [rax+rax+00h]
0x1800736ed  mov     eax, 8007000Eh
0x1800736f2  jmp     loc_180073A85
0x1800736f7  mov     rax, [r12+58h]
0x1800736fc  mov     r10d, ecx
0x1800736ff  test    rax, rax
0x180073702  jz      short loc_18007370A
0x180073704  mov     r8, [rax+18h]
0x180073708  jmp     short loc_18007370D
0x18007370a  mov     r8, rcx; unsigned __int16 *
0x18007370d  mov     rdx, rsi; unsigned __int64
0x180073710  mov     rcx, rdi; unsigned __int16 *
0x180073713  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180073718  xor     esi, esi
0x18007371a  cmp     ebx, 10h
0x18007371d  jnb     loc_180073A80
0x180073723  mov     eax, r10d
0x180073726  cmp     [rdi+rax*2], si
0x18007372a  jz      short loc_180073747
0x18007372c  mov     eax, r10d
0x18007372f  cmp     word ptr [rdi+rax*2], 20h ; ' '
0x180073734  jz      short loc_18007373D
0x180073736  cmp     word ptr [rdi+rax*2], 9
0x18007373b  jnz     short loc_180073747
0x18007373d  inc     r10d
0x180073740  cmp     [rdi+r10*2], si
0x180073745  jnz     short loc_18007372C
0x180073747  mov     eax, r10d
0x18007374a  lea     rcx, [rdi+rax*2]
0x18007374e  cmp     [rcx], si
0x180073751  jz      short loc_18007377C
0x180073753  mov     eax, ebx
0x180073755  inc     ebx
0x180073757  mov     [rbp+rax*8+0F0h+var_C0], rcx
0x18007375c  cmp     [rcx], si
0x18007375f  jz      short loc_18007377C
0x180073761  mov     eax, r10d
0x180073764  cmp     word ptr [rdi+rax*2], 20h ; ' '
0x180073769  jz      short loc_18007377C
0x18007376b  cmp     word ptr [rdi+rax*2], 9
0x180073770  jz      short loc_18007377C
0x180073772  inc     r10d
0x180073775  cmp     [rdi+r10*2], si
0x18007377a  jnz     short loc_180073761
0x18007377c  mov     ecx, r10d
0x18007377f  cmp     [rdi+rcx*2], si
0x180073783  jz      short loc_18007378C
0x180073785  mov     [rdi+rcx*2], si
0x180073789  inc     r10d
0x18007378c  mov     eax, r10d
0x18007378f  cmp     [rdi+rax*2], si
0x180073793  jnz     short loc_18007371A
0x180073795  test    ebx, ebx
0x180073797  lea     r8, [rbp+0F0h+var_C0]
0x18007379b  mov     edx, ebx; dwNumServiceArgs
0x18007379d  mov     rcx, r13; hService
0x1800737a0  cmovz   r8, rsi; lpServiceArgVectors
0x1800737a4  call    cs:__imp_StartServiceW
0x1800737ab  nop     dword ptr [rax+rax+00h]
0x1800737b0  mov     r15d, eax
0x1800737b3  call    cs:__imp_GetLastError
0x1800737ba  nop     dword ptr [rax+rax+00h]
0x1800737bf  mov     r14d, eax
0x1800737c2  test    r15d, r15d
0x1800737c5  jz      loc_18007394C
0x1800737cb  lea     rax, [rbp+0F0h+cbBufSize]
0x1800737cf  mov     [rbp+0F0h+cbBufSize], esi
0x1800737d2  xor     r9d, r9d; cbBufSize
0x1800737d5  mov     [rsp+130h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1800737da  xor     r8d, r8d; lpBuffer
0x1800737dd  xor     edx, edx; InfoLevel
0x1800737df  mov     rcx, r13; hService
0x1800737e2  call    cs:__imp_QueryServiceStatusEx
0x1800737e9  nop     dword ptr [rax+rax+00h]
0x1800737ee  mov     r15d, eax
0x1800737f1  test    eax, eax
0x1800737f3  jnz     loc_18007394C
0x1800737f9  call    cs:__imp_GetLastError
0x180073800  nop     dword ptr [rax+rax+00h]
0x180073805  cmp     eax, 7Ah ; 'z'
0x180073808  jnz     loc_18007394C
0x18007380e  mov     esi, [rbp+0F0h+cbBufSize]
0x180073811  xor     ebx, ebx
0x180073813  test    rsi, rsi
0x180073816  jz      short loc_180073879
0x180073818  cmp     rsi, cs:g_ulMaxStackAllocSize
0x18007381f  ja      short loc_180073879
0x180073821  mov     rcx, cs:g_ulAdditionalProbeSize
0x180073828  add     rcx, 8
0x18007382c  add     rcx, rsi
0x18007382f  cmp     rcx, rsi
0x180073832  jb      short loc_180073879
0x180073834  call    VerifyStackAvailable
0x180073839  test    eax, eax
0x18007383b  jz      short loc_180073879
0x18007383d  lea     rax, [rsi+8]
0x180073841  lea     rcx, [rax+0Fh]
0x180073845  cmp     rcx, rax
0x180073848  ja      short loc_180073854
0x18007384a  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180073854  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180073858  mov     rax, rcx
0x18007385b  call    _alloca_probe
0x180073860  sub     rsp, rcx
0x180073863  lea     rbx, [rsp+130h+cbBufSize]
0x180073868  test    rbx, rbx
0x18007386b  jz      short loc_180073879
0x18007386d  mov     dword ptr [rbx], 6B637453h
0x180073873  add     rbx, 8
0x180073877  jnz     short loc_1800738B5
0x180073879  lea     rcx, [rsi+8]
0x18007387d  cmp     rcx, rsi
0x180073880  jb      short loc_1800738A8
0x180073882  mov     rax, cs:g_pfnAllocate
0x180073889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007388e  xor     esi, esi
0x180073890  mov     rbx, rax
0x180073893  test    rax, rax
0x180073896  jz      loc_18007394C
0x18007389c  mov     dword ptr [rax], 70616548h
0x1800738a2  add     rbx, 8
0x1800738a6  jmp     short loc_1800738AA
0x1800738a8  xor     esi, esi
0x1800738aa  test    rbx, rbx
0x1800738ad  jz      loc_18007394C
0x1800738b3  jmp     short loc_1800738B7
0x1800738b5  xor     esi, esi
0x1800738b7  mov     r9d, [rbp+0F0h+cbBufSize]; cbBufSize
0x1800738bb  lea     rax, [rbp+0F0h+cbBufSize]
0x1800738bf  mov     r8, rbx; lpBuffer
0x1800738c2  mov     [rsp+130h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1800738c7  xor     edx, edx; InfoLevel
0x1800738c9  mov     rcx, r13; hService
0x1800738cc  call    cs:__imp_QueryServiceStatusEx
0x1800738d3  nop     dword ptr [rax+rax+00h]
0x1800738d8  mov     r15d, eax
0x1800738db  test    eax, eax
0x1800738dd  jz      short loc_1800738EA
0x1800738df  mov     rcx, [rbp+0F0h+var_E0]
0x1800738e3  mov     eax, [rbx+1Ch]
0x1800738e6  mov     [rcx], eax
0x1800738e8  jmp     short loc_18007392F
0x1800738ea  mov     eax, cs:dword_1801574B8
0x1800738f0  test    eax, eax
0x1800738f2  jnz     short loc_180073907
0x1800738f4  cmp     cs:?gfEnableTracing@@3HA, esi; int gfEnableTracing
0x1800738fa  jz      short loc_18007392F
0x1800738fc  xor     ecx, ecx
0x1800738fe  call    IsWppLevelEnabled
0x180073903  test    al, al
0x180073905  jz      short loc_18007392F
0x180073907  lea     rax, aFailure; "Failure"
0x18007390e  xor     r9d, r9d
0x180073911  mov     r8d, 0E13h
0x180073917  mov     [rsp+130h+pcbBytesNeeded], rax
0x18007391c  lea     rdx, aCclassdataPriv; "CClassData::PrivilegedLaunchService"
0x180073923  lea     rcx, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x18007392a  call    ??$ComTraceMessageT@$$V@@YAXPEBD0HW4TraceLevel@@PEBG@Z; ComTraceMessageT<>(char const *,char const *,int,TraceLevel,ushort const *)
0x18007392f  test    rbx, rbx
0x180073932  jz      short loc_18007394C
0x180073934  lea     rcx, [rbx-8]
0x180073938  cmp     dword ptr [rcx], 70616548h
0x18007393e  jnz     short loc_18007394C
0x180073940  mov     rax, cs:g_pfnFree
0x180073947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007394c  mov     rcx, r13; hSCObject
0x18007394f  call    cs:__imp_CloseServiceHandle
0x180073956  nop     dword ptr [rax+rax+00h]
0x18007395b  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180073962  mov     r8, rdi; lpMem
0x180073965  xor     edx, edx; dwFlags
0x180073967  call    cs:__imp_HeapFree
0x18007396e  nop     dword ptr [rax+rax+00h]
0x180073973  test    r15d, r15d
0x180073976  jz      short loc_18007397F
0x180073978  xor     eax, eax
0x18007397a  jmp     loc_180073A85
0x18007397f  test    r14d, r14d
0x180073982  jg      short loc_180073989
0x180073984  mov     edi, r14d
0x180073987  jmp     short loc_180073993
0x180073989  movzx   edi, r14w
0x18007398d  or      edi, 80070000h
0x180073993  test    edi, edi
0x180073995  jns     loc_180073A32
0x18007399b  mov     eax, cs:dword_1801574B8
0x1800739a1  test    eax, eax
0x1800739a3  jnz     short loc_1800739B8
0x1800739a5  cmp     cs:?gfEnableTracing@@3HA, esi; int gfEnableTracing
0x1800739ab  jz      short loc_1800739E3
0x1800739ad  xor     ecx, ecx
0x1800739af  call    IsWppLevelEnabled
0x1800739b4  test    al, al
0x1800739b6  jz      short loc_1800739E3
0x1800739b8  lea     rax, aHrHresult; "hr:%!HRESULT!"
0x1800739bf  mov     [rsp+130h+var_108], edi
0x1800739c3  mov     r9d, 0E25h; int
0x1800739c9  mov     [rsp+130h+pcbBytesNeeded], rax; unsigned __int16 *
0x1800739ce  lea     r8, aCclassdataPriv; "CClassData::PrivilegedLaunchService"
0x1800739d5  mov     ecx, edi; int
0x1800739d7  lea     rdx, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x1800739de  call    ?ComTraceHr@@YAXJPEBD0HPEBGZZ; ComTraceHr(long,char const *,char const *,int,ushort const *,...)
0x1800739e3  lea     eax, [r14-420h]
0x1800739ea  test    eax, 0FFFFFFFDh
0x1800739ef  jz      loc_180073A7C
0x1800739f5  mov     rax, [r12]
0x1800739f9  xor     ecx, ecx; string
0x1800739fb  mov     qword ptr [rbp+0F0h+cbBufSize], rsi
0x1800739ff  mov     rbx, [rax+50h]
0x180073a03  call    cs:__imp_WindowsDeleteString
  ... truncated ...
```
