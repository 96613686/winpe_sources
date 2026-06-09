# CClassData::PrivilegedLaunchService(CToken *,ulong,ulong *)

- ea: `0x18006ed30`
- end: `0x18006f20c`
- name: `?PrivilegedLaunchService@CClassData@@QEAAJPEAVCToken@@KPEAK@Z`
- size: `1244`
- prototype: `__int64 __fastcall(CClassData *__hidden this, struct CToken *, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800950e8`
- `0x18009c390`

## callees

- `0x18000b310`
- `0x1800262fc`
- `0x180034540`
- `0x180040918`
- `0x18006ed30`
- `0x180081210`
- `0x1800814c8`
- `0x1800a228c`
- `0x1800b27e0`
- `0x1800b3128`
- `0x1800fe1a0`
- `0x18010a000`
- `0x18010b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006edbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ef45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ef7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006edbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ef45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ef7f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006f0db`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006f0db`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006ee6c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006ee6c`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18006ef3c`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18006ef3c`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18006edad`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18006edad`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18006ee7f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18006f0c9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18006ee7f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18006f0c9`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18006ef6e`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18006f04c`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18006ef6e`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18006f04c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006f16d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006f1d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006f16d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006f1d4`

## string_xrefs

- `0x18006edf8`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18006f09d`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18006f145`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18006edec`: `CClassData::PrivilegedLaunchService`
- `0x18006f096`: `CClassData::PrivilegedLaunchService`
- `0x18006f13c`: `CClassData::PrivilegedLaunchService`
- `0x18006edff`: `Service:%ws %!WINERROR!`

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
    if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
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
        else if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
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
  if ( dword_18014E4B8 )
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
0x18006ed30  push    rbp
0x18006ed32  push    rsi
0x18006ed33  push    rdi
0x18006ed34  push    r12
0x18006ed36  push    r13
0x18006ed38  push    r14
0x18006ed3a  push    r15
0x18006ed3c  sub     rsp, 100h
0x18006ed43  lea     rbp, [rsp+40h]
0x18006ed48  mov     [rbp+0F0h+arg_10], rbx
0x18006ed4f  mov     rax, cs:__security_cookie
0x18006ed56  xor     rax, rbp
0x18006ed59  mov     [rbp+0F0h+var_40], rax
0x18006ed60  mov     rbx, r9
0x18006ed63  mov     [rbp+0F0h+var_E8], r8d
0x18006ed67  mov     [rbp+0F0h+var_D8], rdx
0x18006ed6b  mov     r12, rcx
0x18006ed6e  xor     edx, edx; Val
0x18006ed70  mov     [rbp+0F0h+var_E0], rbx
0x18006ed74  mov     r8d, 80h; Size
0x18006ed7a  lea     rcx, [rbp+0F0h+var_C0]; void *
0x18006ed7e  call    memset_0
0x18006ed83  mov     rcx, r12; this
0x18006ed86  call    ?Service@CClassData@@QEBAPEAGXZ; CClassData::Service(void)
0x18006ed8b  xor     esi, esi
0x18006ed8d  test    rax, rax
0x18006ed90  jz      loc_18006F1DE
0x18006ed96  mov     [rbx], esi
0x18006ed98  call    ?Service@CClassData@@QEBAPEAGXZ; CClassData::Service(void)
0x18006ed9d  mov     rcx, cs:?g_hServiceController@@3PEAUSC_HANDLE__@@EA; hSCManager
0x18006eda4  mov     rdx, rax; lpServiceName
0x18006eda7  mov     r8d, 0A0000000h; dwDesiredAccess
0x18006edad  call    cs:__imp_OpenServiceW
0x18006edb3  mov     r13, rax
0x18006edb6  test    rax, rax
0x18006edb9  jnz     short loc_18006EE2D
0x18006edbb  call    cs:__imp_GetLastError
0x18006edc1  mov     ebx, eax
0x18006edc3  mov     eax, cs:dword_18014E4B8
0x18006edc9  test    eax, eax
0x18006edcb  jnz     short loc_18006EDE0
0x18006edcd  cmp     cs:?gfEnableTracing@@3HA, esi; int gfEnableTracing
0x18006edd3  jz      short loc_18006EE19
0x18006edd5  xor     ecx, ecx
0x18006edd7  call    IsWppLevelEnabled
0x18006eddc  test    al, al
0x18006edde  jz      short loc_18006EE19
0x18006ede0  mov     rcx, r12; this
0x18006ede3  call    ?Service@CClassData@@QEBAPEAGXZ; CClassData::Service(void)
0x18006ede8  mov     dword ptr [rsp+130h+var_100], ebx
0x18006edec  lea     rdx, aCclassdataPriv; "CClassData::PrivilegedLaunchService"
0x18006edf3  mov     qword ptr [rsp+130h+var_108], rax
0x18006edf8  lea     rcx, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x18006edff  lea     rax, aServiceWsWiner; "Service:%ws %!WINERROR!"
0x18006ee06  xor     r9d, r9d
0x18006ee09  mov     r8d, 0DB4h
0x18006ee0f  mov     [rsp+130h+pcbBytesNeeded], rax
0x18006ee14  call    ??$ComTraceMessageT@_KK@@YAXPEBD0HW4TraceLevel@@PEBG_KK@Z; ComTraceMessageT<unsigned __int64,ulong>(char const *,char const *,int,TraceLevel,ushort const *,unsigned __int64,ulong)
0x18006ee19  test    ebx, ebx
0x18006ee1b  jle     short loc_18006EE26
0x18006ee1d  movzx   ebx, bx
0x18006ee20  or      ebx, 80070000h
0x18006ee26  mov     eax, ebx
0x18006ee28  jmp     loc_18006F1E3
0x18006ee2d  mov     rax, [r12+58h]
0x18006ee32  mov     rdi, rsi
0x18006ee35  mov     ebx, esi
0x18006ee37  test    rax, rax
0x18006ee3a  jz      loc_18006EF2D
0x18006ee40  cmp     [rax+18h], rsi
0x18006ee44  jz      loc_18006EF2D
0x18006ee4a  mov     rcx, [rax+18h]
0x18006ee4e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006ee52  inc     rax
0x18006ee55  cmp     [rcx+rax*2], si
0x18006ee59  jnz     short loc_18006EE52
0x18006ee5b  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18006ee62  lea     rsi, [rax+1]
0x18006ee66  lea     r8, [rsi+rsi]; dwBytes
0x18006ee6a  xor     edx, edx; dwFlags
0x18006ee6c  call    cs:__imp_HeapAlloc
0x18006ee72  xor     ecx, ecx
0x18006ee74  mov     rdi, rax
0x18006ee77  test    rax, rax
0x18006ee7a  jnz     short loc_18006EE8F
0x18006ee7c  mov     rcx, r13; hSCObject
0x18006ee7f  call    cs:__imp_CloseServiceHandle
0x18006ee85  mov     eax, 8007000Eh
0x18006ee8a  jmp     loc_18006F1E3
0x18006ee8f  mov     rax, [r12+58h]
0x18006ee94  mov     r10d, ecx
0x18006ee97  test    rax, rax
0x18006ee9a  jz      short loc_18006EEA2
0x18006ee9c  mov     r8, [rax+18h]
0x18006eea0  jmp     short loc_18006EEA5
0x18006eea2  mov     r8, rcx; unsigned __int16 *
0x18006eea5  mov     rdx, rsi; unsigned __int64
0x18006eea8  mov     rcx, rdi; unsigned __int16 *
0x18006eeab  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006eeb0  xor     esi, esi
0x18006eeb2  cmp     ebx, 10h
0x18006eeb5  jnb     loc_18006F1DE
0x18006eebb  mov     eax, r10d
0x18006eebe  cmp     [rdi+rax*2], si
0x18006eec2  jz      short loc_18006EEDF
0x18006eec4  mov     eax, r10d
0x18006eec7  cmp     word ptr [rdi+rax*2], 20h ; ' '
0x18006eecc  jz      short loc_18006EED5
0x18006eece  cmp     word ptr [rdi+rax*2], 9
0x18006eed3  jnz     short loc_18006EEDF
0x18006eed5  inc     r10d
0x18006eed8  cmp     [rdi+r10*2], si
0x18006eedd  jnz     short loc_18006EEC4
0x18006eedf  mov     eax, r10d
0x18006eee2  lea     rcx, [rdi+rax*2]
0x18006eee6  cmp     [rcx], si
0x18006eee9  jz      short loc_18006EF14
0x18006eeeb  mov     eax, ebx
0x18006eeed  inc     ebx
0x18006eeef  mov     [rbp+rax*8+0F0h+var_C0], rcx
0x18006eef4  cmp     [rcx], si
0x18006eef7  jz      short loc_18006EF14
0x18006eef9  mov     eax, r10d
0x18006eefc  cmp     word ptr [rdi+rax*2], 20h ; ' '
0x18006ef01  jz      short loc_18006EF14
0x18006ef03  cmp     word ptr [rdi+rax*2], 9
0x18006ef08  jz      short loc_18006EF14
0x18006ef0a  inc     r10d
0x18006ef0d  cmp     [rdi+r10*2], si
0x18006ef12  jnz     short loc_18006EEF9
0x18006ef14  mov     ecx, r10d
0x18006ef17  cmp     [rdi+rcx*2], si
0x18006ef1b  jz      short loc_18006EF24
0x18006ef1d  mov     [rdi+rcx*2], si
0x18006ef21  inc     r10d
0x18006ef24  mov     eax, r10d
0x18006ef27  cmp     [rdi+rax*2], si
0x18006ef2b  jnz     short loc_18006EEB2
0x18006ef2d  test    ebx, ebx
0x18006ef2f  lea     r8, [rbp+0F0h+var_C0]
0x18006ef33  mov     edx, ebx; dwNumServiceArgs
0x18006ef35  mov     rcx, r13; hService
0x18006ef38  cmovz   r8, rsi; lpServiceArgVectors
0x18006ef3c  call    cs:__imp_StartServiceW
0x18006ef42  mov     r15d, eax
0x18006ef45  call    cs:__imp_GetLastError
0x18006ef4b  mov     r14d, eax
0x18006ef4e  test    r15d, r15d
0x18006ef51  jz      loc_18006F0C6
0x18006ef57  lea     rax, [rbp+0F0h+cbBufSize]
0x18006ef5b  mov     [rbp+0F0h+cbBufSize], esi
0x18006ef5e  xor     r9d, r9d; cbBufSize
0x18006ef61  mov     [rsp+130h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18006ef66  xor     r8d, r8d; lpBuffer
0x18006ef69  xor     edx, edx; InfoLevel
0x18006ef6b  mov     rcx, r13; hService
0x18006ef6e  call    cs:__imp_QueryServiceStatusEx
0x18006ef74  mov     r15d, eax
0x18006ef77  test    eax, eax
0x18006ef79  jnz     loc_18006F0C6
0x18006ef7f  call    cs:__imp_GetLastError
0x18006ef85  cmp     eax, 7Ah ; 'z'
0x18006ef88  jnz     loc_18006F0C6
0x18006ef8e  mov     esi, [rbp+0F0h+cbBufSize]
0x18006ef91  xor     ebx, ebx
0x18006ef93  test    rsi, rsi
0x18006ef96  jz      short loc_18006EFF9
0x18006ef98  cmp     rsi, cs:g_ulMaxStackAllocSize
0x18006ef9f  ja      short loc_18006EFF9
0x18006efa1  mov     rcx, cs:g_ulAdditionalProbeSize
0x18006efa8  add     rcx, 8
0x18006efac  add     rcx, rsi
0x18006efaf  cmp     rcx, rsi
0x18006efb2  jb      short loc_18006EFF9
0x18006efb4  call    VerifyStackAvailable
0x18006efb9  test    eax, eax
0x18006efbb  jz      short loc_18006EFF9
0x18006efbd  lea     rax, [rsi+8]
0x18006efc1  lea     rcx, [rax+0Fh]
0x18006efc5  cmp     rcx, rax
0x18006efc8  ja      short loc_18006EFD4
0x18006efca  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18006efd4  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18006efd8  mov     rax, rcx
0x18006efdb  call    _alloca_probe
0x18006efe0  sub     rsp, rcx
0x18006efe3  lea     rbx, [rsp+130h+cbBufSize]
0x18006efe8  test    rbx, rbx
0x18006efeb  jz      short loc_18006EFF9
0x18006efed  mov     dword ptr [rbx], 6B637453h
0x18006eff3  add     rbx, 8
0x18006eff7  jnz     short loc_18006F035
0x18006eff9  lea     rcx, [rsi+8]
0x18006effd  cmp     rcx, rsi
0x18006f000  jb      short loc_18006F028
0x18006f002  mov     rax, cs:g_pfnAllocate
0x18006f009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f00e  xor     esi, esi
0x18006f010  mov     rbx, rax
0x18006f013  test    rax, rax
0x18006f016  jz      loc_18006F0C6
0x18006f01c  mov     dword ptr [rax], 70616548h
0x18006f022  add     rbx, 8
0x18006f026  jmp     short loc_18006F02A
0x18006f028  xor     esi, esi
0x18006f02a  test    rbx, rbx
0x18006f02d  jz      loc_18006F0C6
0x18006f033  jmp     short loc_18006F037
0x18006f035  xor     esi, esi
0x18006f037  mov     r9d, [rbp+0F0h+cbBufSize]; cbBufSize
0x18006f03b  lea     rax, [rbp+0F0h+cbBufSize]
0x18006f03f  mov     r8, rbx; lpBuffer
0x18006f042  mov     [rsp+130h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18006f047  xor     edx, edx; InfoLevel
0x18006f049  mov     rcx, r13; hService
0x18006f04c  call    cs:__imp_QueryServiceStatusEx
0x18006f052  mov     r15d, eax
0x18006f055  test    eax, eax
0x18006f057  jz      short loc_18006F064
0x18006f059  mov     rcx, [rbp+0F0h+var_E0]
0x18006f05d  mov     eax, [rbx+1Ch]
0x18006f060  mov     [rcx], eax
0x18006f062  jmp     short loc_18006F0A9
0x18006f064  mov     eax, cs:dword_18014E4B8
0x18006f06a  test    eax, eax
0x18006f06c  jnz     short loc_18006F081
0x18006f06e  cmp     cs:?gfEnableTracing@@3HA, esi; int gfEnableTracing
0x18006f074  jz      short loc_18006F0A9
0x18006f076  xor     ecx, ecx
0x18006f078  call    IsWppLevelEnabled
0x18006f07d  test    al, al
0x18006f07f  jz      short loc_18006F0A9
0x18006f081  lea     rax, aFailure; "Failure"
0x18006f088  xor     r9d, r9d
0x18006f08b  mov     r8d, 0E13h
0x18006f091  mov     [rsp+130h+pcbBytesNeeded], rax
0x18006f096  lea     rdx, aCclassdataPriv; "CClassData::PrivilegedLaunchService"
0x18006f09d  lea     rcx, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x18006f0a4  call    ??$ComTraceMessageT@$$V@@YAXPEBD0HW4TraceLevel@@PEBG@Z; ComTraceMessageT<>(char const *,char const *,int,TraceLevel,ushort const *)
0x18006f0a9  test    rbx, rbx
0x18006f0ac  jz      short loc_18006F0C6
0x18006f0ae  lea     rcx, [rbx-8]
0x18006f0b2  cmp     dword ptr [rcx], 70616548h
0x18006f0b8  jnz     short loc_18006F0C6
0x18006f0ba  mov     rax, cs:g_pfnFree
0x18006f0c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f0c6  mov     rcx, r13; hSCObject
0x18006f0c9  call    cs:__imp_CloseServiceHandle
0x18006f0cf  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18006f0d6  mov     r8, rdi; lpMem
0x18006f0d9  xor     edx, edx; dwFlags
0x18006f0db  call    cs:__imp_HeapFree
0x18006f0e1  test    r15d, r15d
0x18006f0e4  jz      short loc_18006F0ED
0x18006f0e6  xor     eax, eax
0x18006f0e8  jmp     loc_18006F1E3
0x18006f0ed  test    r14d, r14d
0x18006f0f0  jg      short loc_18006F0F7
0x18006f0f2  mov     edi, r14d
0x18006f0f5  jmp     short loc_18006F101
0x18006f0f7  movzx   edi, r14w
0x18006f0fb  or      edi, 80070000h
0x18006f101  test    edi, edi
0x18006f103  jns     loc_18006F196
0x18006f109  mov     eax, cs:dword_18014E4B8
0x18006f10f  test    eax, eax
0x18006f111  jnz     short loc_18006F126
0x18006f113  cmp     cs:?gfEnableTracing@@3HA, esi; int gfEnableTracing
0x18006f119  jz      short loc_18006F151
0x18006f11b  xor     ecx, ecx
0x18006f11d  call    IsWppLevelEnabled
0x18006f122  test    al, al
0x18006f124  jz      short loc_18006F151
0x18006f126  lea     rax, aHrHresult; "hr:%!HRESULT!"
0x18006f12d  mov     [rsp+130h+var_108], edi
0x18006f131  mov     r9d, 0E25h; int
0x18006f137  mov     [rsp+130h+pcbBytesNeeded], rax; unsigned __int16 *
0x18006f13c  lea     r8, aCclassdataPriv; "CClassData::PrivilegedLaunchService"
0x18006f143  mov     ecx, edi; int
0x18006f145  lea     rdx, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x18006f14c  call    ?ComTraceHr@@YAXJPEBD0HPEBGZZ; ComTraceHr(long,char const *,char const *,int,ushort const *,...)
0x18006f151  lea     eax, [r14-420h]
0x18006f158  test    eax, 0FFFFFFFDh
0x18006f15d  jz      short loc_18006F1DA
0x18006f15f  mov     rax, [r12]
0x18006f163  xor     ecx, ecx; string
0x18006f165  mov     qword ptr [rbp+0F0h+cbBufSize], rsi
0x18006f169  mov     rbx, [rax+50h]
0x18006f16d  call    cs:__imp_WindowsDeleteString
0x18006f173  lea     rdx, [rbp+0F0h+cbBufSize]
0x18006f177  mov     qword ptr [rbp+0F0h+cbBufSize], rsi
0x18006f17b  mov     rcx, r12
0x18006f17e  mov     rax, rbx
0x18006f181  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f186  mov     rdx, [r12+58h]
0x18006f18b  test    rdx, rdx
0x18006f18e  jz      short loc_18006F1A8
0x18006f190  mov     rdx, [rdx+18h]
0x18006f194  jmp     short loc_18006F1AB
0x18006f196  cmp     cs:?gfEnableTracing@@3HA, esi; int gfEnableTracing
  ... truncated ...
```
