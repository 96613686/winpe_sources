# NMP_Open(void *,ushort *,ushort *,ushort *,ushort *,uint,uint,uint,void *,int,ulong,ulong,void *,void *)

- ea: `0x18006d4e0`
- end: `0x18006de0e`
- name: `?NMP_Open@@YAJPEAXPEAG111III0HKK00@Z`
- size: `2350`
- prototype: `__int64 __usercall@<rax>(PVOID pv@<rcx>, unsigned __int16 *@<rdx>, unsigned __int16 *@<r8>, unsigned __int16 *@<r9>, unsigned __int16 *, unsigned int, unsigned int, unsigned int, void *, int, unsigned int, unsigned int, void *, void *)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180011000`
- `0x1800295d8`
- `0x180031110`
- `0x18006d460`
- `0x18006d4e0`
- `0x18006de14`
- `0x18006dec4`
- `0x18006e110`
- `0x18006f7e8`
- `0x1800aa300`
- `0x1800aac88`
- `0x1800cec91`
- `0x1800ceda0`
- `0x1800d7010`

## import_xrefs

- `ntdll!_wcsicmp` at `0x18006dad8`
- `ntdll!_wcsicmp` at `0x18006dad8`
- `ntdll!RtlDllShutdownInProgress` at `0x18006d514`
- `ntdll!RtlDllShutdownInProgress` at `0x18006d514`
- `ntdll!_wcsnicmp` at `0x18006d5a1`
- `ntdll!_wcsnicmp` at `0x18006da8f`
- `ntdll!_wcsnicmp` at `0x18006d5a1`
- `ntdll!_wcsnicmp` at `0x18006da8f`
- `ntdll!RtlGetLastNtStatus` at `0x18006ddf3`
- `ntdll!RtlGetLastNtStatus` at `0x18006ddf3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006db38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006db38`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006db49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006db49`
- `api-ms-win-core-namedpipe-l1-1-0!SetNamedPipeHandleState` at `0x18006d7ab`
- `api-ms-win-core-namedpipe-l1-1-0!SetNamedPipeHandleState` at `0x18006d7ab`
- `api-ms-win-core-namedpipe-l1-1-0!WaitNamedPipeW` at `0x18006d92f`
- `api-ms-win-core-namedpipe-l1-1-0!WaitNamedPipeW` at `0x18006d92f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006d74a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006d943`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006d74a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006d943`
- `ext-ms-win-core-winrt-remote-l1-1-0!WaitRemotePipe` at `0x18006d9f0`
- `ext-ms-win-core-winrt-remote-l1-1-0!WaitRemotePipe` at `0x18006d9f0`
- `ext-ms-win-core-winrt-remote-l1-1-0!GetLocalEndPointMapperCrossVmPipeName` at `0x18006daf5`
- `ext-ms-win-core-winrt-remote-l1-1-0!GetLocalEndPointMapperCrossVmPipeName` at `0x18006daf5`
- `ext-ms-win-core-winrt-remote-l1-1-0!RemoteWinRTActivation` at `0x18006daad`
- `ext-ms-win-core-winrt-remote-l1-1-0!RemoteWinRTActivation` at `0x18006ddde`
- `ext-ms-win-core-winrt-remote-l1-1-0!RemoteWinRTActivation` at `0x18006daad`
- `ext-ms-win-core-winrt-remote-l1-1-0!RemoteWinRTActivation` at `0x18006ddde`
- `ext-ms-win-core-winrt-remote-l1-1-0!ValidateRemoteVmNamedPipeEndpoint` at `0x18006db1d`
- `ext-ms-win-core-winrt-remote-l1-1-0!ValidateRemoteVmNamedPipeEndpoint` at `0x18006db1d`
- `ext-ms-win-core-winrt-remote-l1-1-0!GetEndPointMapperCrossVmPipeNamespace` at `0x18006da77`
- `ext-ms-win-core-winrt-remote-l1-1-0!GetEndPointMapperCrossVmPipeNamespace` at `0x18006da77`

## pseudocode

```c
__int64 __fastcall NMP_Open(
        char *pv,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *LocalEndPointMapperCrossVmPipeName,
        unsigned __int16 *a5,
        unsigned int a6,
        unsigned int a7,
        unsigned int a8,
        void *a9,
        int a10,
        unsigned int a11,
        unsigned int a12,
        void *a13)
{
  unsigned __int16 *p_Mode; // r15
  int v17; // r12d
  DWORD v18; // ebx
  int IsLocalAlias; // edi
  __int64 v20; // rdx
  __int64 v21; // rax
  __int64 v22; // rdi
  unsigned __int64 v23; // rbx
  unsigned __int16 *v24; // rax
  unsigned int v25; // edi
  unsigned __int64 v26; // rcx
  __int64 v27; // rcx
  unsigned __int64 v28; // rcx
  void *v29; // rsp
  void *v30; // rsp
  __int64 v31; // rbx
  ULONGLONG TickCount64; // rax
  DWORD v33; // r13d
  int v34; // eax
  __int64 v35; // rdi
  int Io; // ebx
  unsigned int v37; // eax
  unsigned int v39; // ebx
  bool v40; // zf
  bool v41; // zf
  const wchar_t *EndPointMapperCrossVmPipeNamespace; // rax
  bool v43; // zf
  int v44; // ecx
  __int64 v45; // [rsp+0h] [rbp-30h] BYREF
  DWORD Mode; // [rsp+30h] [rbp+0h] BYREF
  int v47; // [rsp+34h] [rbp+4h]
  int v48; // [rsp+38h] [rbp+8h] BYREF
  ULONGLONG v49; // [rsp+40h] [rbp+10h] BYREF
  int v50; // [rsp+48h] [rbp+18h]
  __int64 v51; // [rsp+50h] [rbp+20h]
  void *v52; // [rsp+58h] [rbp+28h] BYREF

  p_Mode = 0;
  v52 = 0;
  if ( RtlDllShutdownInProgress() )
    return 164;
  if ( a12 || a13 )
    return 1764;
  v17 = 0;
  if ( a5 && *a5 )
  {
    v49 = 0;
    v50 = 0;
    v25 = I_RpcParseSecurity(a5, &v49);
    if ( v25 )
      return v25;
    v17 = (BYTE1(v50) != 0 ? 0x80000 : 0) | ((_BYTE)v50 != 0 ? 0x40000 : 0) | ((HIDWORD(v49) | 0x10) << 16);
  }
  if ( *a3 == 92 )
  {
    if ( a3[1] != 92 || !a3[2] || a3[3] == 92 )
    {
      v25 = 1707;
      RpcpErrorAddRecord(2u, 1707, 0xC0u, a3);
      return v25;
    }
    a3 += 2;
  }
  v18 = 0;
  Mode = 0;
  IsLocalAlias = NMP_IsLocalAlias(a3);
  v47 = IsLocalAlias;
  if ( (unsigned __int8)IsGetLocalVmAliasNamePresent() )
  {
    EndPointMapperCrossVmPipeNamespace = (const wchar_t *)GetEndPointMapperCrossVmPipeNamespace();
    v18 = _wcsnicmp(LocalEndPointMapperCrossVmPipeName, EndPointMapperCrossVmPipeNamespace, 9u) == 0;
    Mode = v18;
  }
  if ( (unsigned __int8)IsGetLocalVmAliasNamePresent() && (unsigned int)RemoteWinRTActivation() == 1 )
  {
    if ( v18 )
    {
      v25 = ValidateRemoteVmNamedPipeEndpoint(LocalEndPointMapperCrossVmPipeName);
      if ( v25 )
        return v25;
      goto LABEL_11;
    }
    if ( IsLocalAlias && !_wcsicmp(LocalEndPointMapperCrossVmPipeName, L"\\pipe\\epmapper") )
    {
      if ( !(unsigned __int8)IsGetLocalVmAliasNamePresent() )
        return 1722;
      LocalEndPointMapperCrossVmPipeName = (unsigned __int16 *)GetLocalEndPointMapperCrossVmPipeName();
      Mode = 1;
LABEL_11:
      a3 = L".";
      goto LABEL_12;
    }
  }
  if ( _wcsnicmp(LocalEndPointMapperCrossVmPipeName, L"\\pipe\\", 6u) )
  {
    if ( *LocalEndPointMapperCrossVmPipeName )
      return 1706;
    goto LABEL_12;
  }
  if ( IsLocalAlias )
    goto LABEL_11;
LABEL_12:
  v21 = -1;
  do
    ++v21;
  while ( a3[v21] );
  v51 = v21;
  v22 = -1;
  do
    ++v22;
  while ( LocalEndPointMapperCrossVmPipeName[v22] );
  v23 = 2LL * (unsigned int)(v22 + v21 + 3);
  if ( !v23 )
    goto LABEL_177;
  if ( v23 > g_ulMaxStackAllocSize )
    goto LABEL_177;
  v26 = v23 + g_ulAdditionalProbeSize + 8;
  if ( v26 < v23 || !(unsigned int)VerifyStackAvailable(v26, v20) )
    goto LABEL_177;
  v27 = v23 + 23;
  if ( v23 + 23 <= v23 + 8 )
    v27 = 0xFFFFFFFFFFFFFF0LL;
  v28 = v27 & 0xFFFFFFFFFFFFFFF0uLL;
  v29 = alloca(v28);
  v30 = alloca(v28);
  p_Mode = (unsigned __int16 *)&Mode;
  if ( &v45 == (__int64 *)-48LL || (Mode = 1801679955, (p_Mode = (unsigned __int16 *)&v48) == 0) )
  {
LABEL_177:
    if ( v23 + 8 >= v23 )
    {
      v24 = (unsigned __int16 *)((__int64 (*)(void))g_pfnAllocate)();
      p_Mode = v24;
      if ( v24 )
      {
        *(_DWORD *)v24 = 1885431112;
        p_Mode = v24 + 4;
      }
    }
  }
  if ( !p_Mode )
    return 14;
  v31 = (unsigned int)v51;
  *(_DWORD *)p_Mode = 6029404;
  v48 = 0;
  memcpy_0(p_Mode + 2, a3, 2 * v31);
  memcpy_0(&p_Mode[v31 + 2], LocalEndPointMapperCrossVmPipeName, 2LL * (unsigned int)(v22 + 1));
  TickCount64 = GetTickCount64();
  v33 = Mode;
  v49 = TickCount64;
  LODWORD(v51) = 0;
  do
  {
    v34 = NMP_CreateFile(p_Mode, v17, &v52);
    v35 = (__int64)v52;
    Io = v34;
    if ( v34 )
      v35 = -1;
    v52 = (void *)v35;
    if ( v35 == -1 )
    {
      v48 = 1;
    }
    else
    {
      Mode = 2;
      if ( SetNamedPipeHandleState((HANDLE)v35, &Mode, 0, 0) )
      {
        Io = RPC_THREAD_POOL::CreateIoEx(
               (HANDLE)v35,
               (PTP_WIN32_IO_CALLBACK)CO_ConnectionThreadPoolCallback,
               pv,
               1,
               (struct RPC_THREAD_POOL_IO **)pv + 18);
        if ( !Io )
        {
          v37 = gPostSize;
          *((_QWORD *)pv + 5) = v35;
          v25 = 0;
          *((_DWORD *)pv + 16) = v37;
          *((_DWORD *)pv + 4) = 0;
          *((_QWORD *)pv + 16) = 0;
          *(_QWORD *)(pv + 68) = 0;
          *((_QWORD *)pv + 12) = 0;
          *((_QWORD *)pv + 13) = 0;
          *((_QWORD *)pv + 14) = 0;
          *((_QWORD *)pv + 10) = pv;
          *((_QWORD *)pv + 15) = 0;
          *((_QWORD *)pv + 11) = 0;
          *((_DWORD *)pv + 12) = 0;
          *((_DWORD *)pv + 13) = 0;
          *((_QWORD *)pv + 7) = 0;
          *((_QWORD *)pv + 17) = 0;
          *((_QWORD *)pv + 19) = 0;
          goto LABEL_40;
        }
      }
      else
      {
        Io = GetLastError();
      }
      CloseHandle((HANDLE)v35);
      v52 = (void *)-1LL;
    }
    if ( Io != 231 )
    {
      RpcpErrorAddRecord(5 - (v47 != 0), Io, 0xBEu, p_Mode, v17);
      v25 = 14;
      if ( Io > 1311 )
      {
        if ( Io <= 1396 )
        {
          if ( Io == 1396 )
            goto LABEL_74;
          if ( Io > 1351 )
          {
            switch ( Io )
            {
              case 1352:
              case 1353:
              case 1354:
              case 1355:
                goto LABEL_74;
              case 1364:
                goto LABEL_84;
              case 1365:
              case 1380:
              case 1385:
                goto LABEL_74;
            }
            v40 = Io == 1395;
            goto LABEL_73;
          }
          if ( Io == 1351 )
            goto LABEL_84;
          if ( Io > 1328 )
          {
            if ( Io == 1329 || Io == 1330 || Io == 1331 )
              goto LABEL_74;
            v40 = Io == 1346;
            goto LABEL_73;
          }
          if ( Io == 1328 || Io == 1312 || Io == 1317 || Io == 1323 )
            goto LABEL_74;
          v44 = Io - 1326;
          v43 = Io == 1326;
        }
        else
        {
          if ( Io > 1792 )
          {
            switch ( Io )
            {
              case 1793:
              case 1808:
              case 1810:
                goto LABEL_74;
              case 1816:
LABEL_55:
                RpcpErrorAddRecord(2u, v25, 0xC1u, 0, 0);
                goto LABEL_40;
              case 1907:
                goto LABEL_74;
              case 1908:
                goto LABEL_84;
              case 1909:
              case 1931:
                goto LABEL_74;
            }
            v40 = Io == 1935;
            goto LABEL_73;
          }
          switch ( Io )
          {
            case 1792:
              goto LABEL_84;
            case 1397:
            case 1398:
              goto LABEL_74;
            case 1450:
            case 1453:
              goto LABEL_169;
            case 1455:
              goto LABEL_55;
            case 1786:
            case 1787:
              goto LABEL_74;
          }
          v44 = Io - 1788;
          v43 = Io == 1788;
        }
      }
      else
      {
        if ( Io == 1311 )
          goto LABEL_74;
        if ( Io <= 69 )
        {
          if ( Io != 69 )
          {
            if ( Io <= 31 )
            {
              if ( Io == 31 )
                goto LABEL_84;
              if ( Io <= 4 )
              {
                if ( Io == 4 )
                  goto LABEL_55;
                if ( Io != -2146435060 && Io != -2146435025 )
                {
                  if ( Io == 1 || Io == 2 )
                    goto LABEL_84;
                  v41 = Io == 3;
                  goto LABEL_82;
                }
              }
              else if ( Io != 5 )
              {
                if ( Io == 14 || Io == 8 )
                  goto LABEL_55;
                v41 = Io == 22;
LABEL_82:
                if ( !v41 )
                  goto LABEL_83;
LABEL_84:
                v25 = 1722;
                goto LABEL_55;
              }
              goto LABEL_74;
            }
            if ( Io == 51 || Io == 52 || Io == 53 || Io == 58 || Io == 59 || Io == 64 )
              goto LABEL_84;
            if ( Io != 65 )
            {
              if ( Io == 66 )
                goto LABEL_84;
              if ( Io != 67 )
                goto LABEL_83;
LABEL_112:
              v25 = 1707;
              goto LABEL_55;
            }
LABEL_74:
            v25 = 5;
            goto LABEL_55;
          }
LABEL_169:
          v25 = 1721;
          goto LABEL_55;
        }
        v25 = 1130;
        if ( Io <= 1130 )
        {
          if ( Io == 1130 )
            goto LABEL_55;
          if ( Io <= 161 )
          {
            if ( Io == 161 )
              goto LABEL_112;
            if ( Io == 70 || Io == 71 )
              goto LABEL_84;
            if ( Io != 86 )
            {
              if ( Io != 121 )
              {
                if ( Io == 123 )
                {
                  v25 = 1706;
                  goto LABEL_55;
                }
                goto LABEL_83;
              }
              goto LABEL_84;
            }
            goto LABEL_74;
          }
          switch ( Io )
          {
            case 233:
              goto LABEL_84;
            case 995:
              v25 = 1818;
              goto LABEL_55;
            case 998:
              goto LABEL_83;
          }
          v40 = Io == 1115;
LABEL_73:
          if ( !v40 )
          {
LABEL_83:
            if ( v48
              && Io == 6
              && (unsigned __int8)IsGetLocalVmAliasNamePresent()
              && (unsigned int)RemoteWinRTActivation() == 1 )
            {
              RtlGetLastNtStatus();
            }
            goto LABEL_84;
          }
          goto LABEL_74;
        }
        switch ( Io )
        {
          case 1214:
            goto LABEL_112;
          case 1225:
          case 1229:
          case 1231:
          case 1232:
          case 1236:
            goto LABEL_84;
          case 1240:
            goto LABEL_74;
        }
        v44 = Io - 1264;
        v43 = Io == 1264;
      }
      if ( v43 )
        goto LABEL_74;
      v40 = v44 == 1;
      goto LABEL_73;
    }
    if ( v33 )
      WaitRemotePipe(p_Mode, 1000);
    else
      WaitNamedPipeW(p_Mode, 0x3E8u);
    v39 = v51 + 1;
    LODWORD(v51) = v51 + 1;
  }
  while ( GetTickCount64() - v49 < 0x9C40 || v39 <= 0x14 );
  v25 = 1723;
  RpcpErrorAddRecord(5 - (v47 != 0), 1723, 0xBFu, p_Mode);
LABEL_40:
  if ( *((_DWORD *)p_Mode - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  return v25;
}

```

## disassembly

```asm
0x18006d4e0  push    rbp
0x18006d4e2  push    rbx
0x18006d4e3  push    rsi
0x18006d4e4  push    rdi
0x18006d4e5  push    r12
0x18006d4e7  push    r13
0x18006d4e9  push    r14
0x18006d4eb  push    r15
0x18006d4ed  sub     rsp, 78h
0x18006d4f1  lea     rbp, [rsp+30h]
0x18006d4f6  mov     rax, cs:__security_cookie
0x18006d4fd  xor     rax, rbp
0x18006d500  mov     [rbp+80h+var_50], rax
0x18006d504  xor     r15d, r15d
0x18006d507  mov     r13, r9
0x18006d50a  mov     [rbp+80h+var_58], r15
0x18006d50e  mov     r14, r8
0x18006d511  mov     rsi, rcx
0x18006d514  call    cs:__imp_RtlDllShutdownInProgress
0x18006d51b  nop     dword ptr [rax+rax+00h]
0x18006d520  test    al, al
0x18006d522  jnz     loc_18006D98C
0x18006d528  cmp     [rbp+80h+arg_58], r15d
0x18006d52f  jnz     loc_18006DE04
0x18006d535  cmp     [rbp+80h+arg_60], r15
0x18006d53c  jnz     loc_18006DE04
0x18006d542  mov     rcx, [rbp+80h+arg_20]
0x18006d549  mov     r12d, r15d
0x18006d54c  test    rcx, rcx
0x18006d54f  jnz     loc_18006D629
0x18006d555  mov     ecx, 5Ch ; '\'
0x18006d55a  cmp     [r14], cx
0x18006d55e  jz      loc_18006DA3A
0x18006d564  mov     ebx, r15d
0x18006d567  mov     rcx, r14; String1
0x18006d56a  mov     [rbp+80h+Mode], ebx
0x18006d56d  call    ?NMP_IsLocalAlias@@YAHQEAG@Z; NMP_IsLocalAlias(ushort * const)
0x18006d572  mov     edi, eax
0x18006d574  mov     [rbp+80h+var_7C], eax
0x18006d577  call    IsGetLocalVmAliasNamePresent
0x18006d57c  test    al, al
0x18006d57e  jnz     loc_18006DA77
0x18006d584  call    IsGetLocalVmAliasNamePresent
0x18006d589  test    al, al
0x18006d58b  jnz     loc_18006DAAD
0x18006d591  mov     r8d, 6; MaxCount
0x18006d597  lea     rdx, aPipe; "\\pipe\\"
0x18006d59e  mov     rcx, r13; String1
0x18006d5a1  call    cs:__imp__wcsnicmp
0x18006d5a8  nop     dword ptr [rax+rax+00h]
0x18006d5ad  test    eax, eax
0x18006d5af  jnz     loc_18006D680
0x18006d5b5  test    edi, edi
0x18006d5b7  jz      short loc_18006D5C0
0x18006d5b9  lea     r14, asc_1800E72A8; "."
0x18006d5c0  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18006d5c4  mov     rax, rcx
0x18006d5c7  inc     rax
0x18006d5ca  cmp     [r14+rax*2], r15w
0x18006d5cf  jnz     short loc_18006D5C7
0x18006d5d1  mov     [rbp+80h+var_60], rax
0x18006d5d5  mov     rdi, rcx
0x18006d5d8  inc     rdi
0x18006d5db  cmp     [r13+rdi*2+0], r15w
0x18006d5e1  jnz     short loc_18006D5D8
0x18006d5e3  add     eax, 3
0x18006d5e6  add     eax, edi
0x18006d5e8  lea     rbx, [rax+rax]
0x18006d5ec  test    rbx, rbx
0x18006d5ef  jnz     loc_18006D695
0x18006d5f5  lea     rcx, [rbx+8]
0x18006d5f9  cmp     rcx, rbx
0x18006d5fc  jb      loc_18006D70B
0x18006d602  mov     rax, cs:g_pfnAllocate
0x18006d609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d60e  mov     r15, rax
0x18006d611  test    rax, rax
0x18006d614  jz      loc_18006D70B
0x18006d61a  mov     dword ptr [rax], 70616548h
0x18006d620  add     r15, 8
0x18006d624  jmp     loc_18006D70B
0x18006d629  cmp     [rcx], r15w
0x18006d62d  jz      loc_18006D555
0x18006d633  xor     eax, eax
0x18006d635  lea     rdx, [rbp+80h+var_70]
0x18006d639  mov     [rbp+80h+var_70], rax
0x18006d63d  mov     [rbp+80h+var_68], eax
0x18006d640  call    I_RpcParseSecurity
0x18006d645  mov     edi, eax
0x18006d647  test    eax, eax
0x18006d649  jnz     loc_18006D85B
0x18006d64f  mov     r12d, dword ptr [rbp+80h+var_70+4]
0x18006d653  mov     al, byte ptr [rbp+80h+var_68]
0x18006d656  or      r12d, 10h
0x18006d65a  shl     r12d, 10h
0x18006d65e  neg     al
0x18006d660  mov     al, byte ptr [rbp+80h+var_68+1]
0x18006d663  sbb     ecx, ecx
0x18006d665  and     ecx, 40000h
0x18006d66b  or      r12d, ecx
0x18006d66e  neg     al
0x18006d670  sbb     ecx, ecx
0x18006d672  and     ecx, 80000h
0x18006d678  or      r12d, ecx
0x18006d67b  jmp     loc_18006D555
0x18006d680  cmp     [r13+0], r15w
0x18006d685  jz      loc_18006D5C0
0x18006d68b  mov     edi, 6AAh
0x18006d690  jmp     loc_18006D85B
0x18006d695  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18006d69c  ja      loc_18006D5F5
0x18006d6a2  mov     rcx, cs:g_ulAdditionalProbeSize
0x18006d6a9  add     rcx, 8
0x18006d6ad  add     rcx, rbx
0x18006d6b0  cmp     rcx, rbx
0x18006d6b3  jb      loc_18006D5F5
0x18006d6b9  call    VerifyStackAvailable
0x18006d6be  test    eax, eax
0x18006d6c0  jz      loc_18006D5F5
0x18006d6c6  lea     rax, [rbx+8]
0x18006d6ca  lea     rcx, [rax+0Fh]
0x18006d6ce  cmp     rcx, rax
0x18006d6d1  ja      short loc_18006D6DD
0x18006d6d3  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18006d6dd  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18006d6e1  mov     rax, rcx
0x18006d6e4  call    __chkstk_0
0x18006d6e9  sub     rsp, rcx
0x18006d6ec  lea     r15, [rsp+0B0h+Mode]
0x18006d6f1  test    r15, r15
0x18006d6f4  jz      loc_18006D5F5
0x18006d6fa  mov     dword ptr [r15], 6B637453h
0x18006d701  add     r15, 8
0x18006d705  jz      loc_18006D5F5
0x18006d70b  test    r15, r15
0x18006d70e  jz      loc_18006D856
0x18006d714  mov     ebx, dword ptr [rbp+80h+var_60]
0x18006d717  lea     rcx, [r15+4]; void *
0x18006d71b  xor     eax, eax
0x18006d71d  mov     dword ptr [r15], 5C005Ch
0x18006d724  mov     rdx, r14; Src
0x18006d727  mov     [rbp+80h+var_78], eax
0x18006d72a  lea     r8, [rbx+rbx]; Size
0x18006d72e  call    memcpy_0
0x18006d733  lea     r8d, [rdi+1]
0x18006d737  mov     rdx, r13; Src
0x18006d73a  lea     rcx, [rbx+2]
0x18006d73e  add     r8, r8; Size
0x18006d741  lea     rcx, [r15+rcx*2]; void *
0x18006d745  call    memcpy_0
0x18006d74a  call    cs:__imp_GetTickCount64
0x18006d751  nop     dword ptr [rax+rax+00h]
0x18006d756  mov     r13d, [rbp+80h+Mode]
0x18006d75a  mov     r14d, 2
0x18006d760  mov     [rbp+80h+var_70], rax
0x18006d764  mov     dword ptr [rbp+80h+var_60], 0
0x18006d76b  lea     r8, [rbp+80h+var_58]; void **
0x18006d76f  mov     edx, r12d; unsigned int
0x18006d772  mov     rcx, r15; unsigned __int16 *
0x18006d775  call    ?NMP_CreateFile@@YAJPEAGKPEAPEAX@Z; NMP_CreateFile(ushort *,ulong,void * *)
0x18006d77a  mov     rdi, [rbp+80h+var_58]
0x18006d77e  test    eax, eax
0x18006d780  mov     ebx, eax
0x18006d782  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18006d789  cmovnz  rdi, rax
0x18006d78d  mov     [rbp+80h+var_58], rdi
0x18006d791  cmp     rdi, rax
0x18006d794  jz      loc_18006D87B
0x18006d79a  xor     r9d, r9d; lpCollectDataTimeout
0x18006d79d  mov     [rbp+80h+Mode], r14d
0x18006d7a1  xor     r8d, r8d; lpMaxCollectionCount
0x18006d7a4  lea     rdx, [rbp+80h+Mode]; lpMode
0x18006d7a8  mov     rcx, rdi; hNamedPipe
0x18006d7ab  call    cs:__imp_SetNamedPipeHandleState
0x18006d7b2  nop     dword ptr [rax+rax+00h]
0x18006d7b7  test    eax, eax
0x18006d7b9  jz      loc_18006DB38
0x18006d7bf  lea     rax, [rsi+90h]
0x18006d7c6  mov     r9d, 1; int
0x18006d7cc  mov     r8, rsi; pv
0x18006d7cf  mov     [rsp+0B0h+var_90], rax; struct RPC_THREAD_POOL_IO **
0x18006d7d4  lea     rdx, ?CO_ConnectionThreadPoolCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z; pfnio
0x18006d7db  mov     rcx, rdi; fl
0x18006d7de  call    ?CreateIoEx@RPC_THREAD_POOL@@SAJPEAXP6AXPEAU_TP_CALLBACK_INSTANCE@@00K_KPEAU_TP_IO@@@Z0HPEAPEAVRPC_THREAD_POOL_IO@@@Z; RPC_THREAD_POOL::CreateIoEx(void *,void (*)(_TP_CALLBACK_INSTANCE *,void *,void *,ulong,unsigned __int64,_TP_IO *),void *,int,RPC_THREAD_POOL_IO * *)
0x18006d7e3  xor     ecx, ecx
0x18006d7e5  mov     ebx, eax
0x18006d7e7  test    eax, eax
0x18006d7e9  jnz     loc_18006DB46
0x18006d7ef  mov     eax, cs:?gPostSize@@3IA; uint gPostSize
0x18006d7f5  mov     [rsi+28h], rdi
0x18006d7f9  mov     edi, ecx
0x18006d7fb  mov     [rsi+40h], eax
0x18006d7fe  mov     [rsi+10h], ecx
0x18006d801  mov     [rsi+80h], rcx
0x18006d808  mov     [rsi+44h], rcx
0x18006d80c  mov     [rsi+60h], rcx
0x18006d810  mov     [rsi+68h], rcx
0x18006d814  mov     [rsi+70h], rcx
0x18006d818  mov     [rsi+50h], rsi
0x18006d81c  mov     [rsi+78h], rcx
0x18006d820  mov     [rsi+58h], rcx
0x18006d824  mov     [rsi+30h], ecx
0x18006d827  mov     [rsi+34h], ecx
0x18006d82a  mov     [rsi+38h], rcx
0x18006d82e  mov     [rsi+88h], rcx
0x18006d835  mov     [rsi+98h], rcx
0x18006d83c  lea     rcx, [r15-8]
0x18006d840  cmp     dword ptr [rcx], 70616548h
0x18006d846  jnz     short loc_18006D85B
0x18006d848  mov     rax, cs:g_pfnFree
0x18006d84f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d854  jmp     short loc_18006D85B
0x18006d856  mov     edi, 0Eh
0x18006d85b  mov     eax, edi
0x18006d85d  mov     rcx, [rbp+80h+var_50]
0x18006d861  xor     rcx, rbp; StackCookie
0x18006d864  call    __security_check_cookie
0x18006d869  lea     rsp, [rbp+48h]
0x18006d86d  pop     r15
0x18006d86f  pop     r14
0x18006d871  pop     r13
0x18006d873  pop     r12
0x18006d875  pop     rdi
0x18006d876  pop     rsi
0x18006d877  pop     rbx
0x18006d878  pop     rbp
0x18006d879  retn
0x18006d87b  mov     [rbp+80h+var_78], 1
0x18006d882  cmp     ebx, 0E7h
0x18006d888  jz      loc_18006D91E
0x18006d88e  mov     eax, [rbp+80h+var_7C]
0x18006d891  mov     r8d, 0BEh; unsigned __int16
0x18006d897  neg     eax
0x18006d899  mov     dword ptr [rsp+0B0h+var_90], r12d; unsigned int
0x18006d89e  mov     r9, r15; unsigned __int16 *
0x18006d8a1  mov     edx, ebx; int
0x18006d8a3  sbb     ecx, ecx
0x18006d8a5  add     ecx, 5; unsigned int
0x18006d8a8  call    ?RpcpErrorAddRecord@@YAXKJGPEAGK@Z; RpcpErrorAddRecord(ulong,long,ushort,ushort *,ulong)
0x18006d8ad  mov     eax, 51Fh
0x18006d8b2  mov     edi, 0Eh
0x18006d8b7  cmp     ebx, eax
0x18006d8b9  jg      loc_18006D996
0x18006d8bf  jz      loc_18006D9E6
0x18006d8c5  cmp     ebx, 45h ; 'E'
0x18006d8c8  jg      loc_18006DBD0
0x18006d8ce  jz      loc_18006DDBE
0x18006d8d4  cmp     ebx, 1Fh
0x18006d8d7  jg      loc_18006DB73
0x18006d8dd  jz      loc_18006DA30
0x18006d8e3  cmp     ebx, 4
0x18006d8e6  jle     loc_18006DA01
0x18006d8ec  cmp     ebx, 5
0x18006d8ef  jz      loc_18006D9E6
0x18006d8f5  cmp     ebx, edi
0x18006d8f7  jnz     loc_18006DB62
0x18006d8fd  mov     r8d, 0C1h; unsigned __int16
0x18006d903  mov     [rsp+0B0h+var_90], 0; struct tagParam *
0x18006d90c  xor     r9d, r9d; int
0x18006d90f  mov     edx, edi; int
0x18006d911  mov     ecx, r14d; unsigned int
0x18006d914  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x18006d919  jmp     loc_18006D83C
0x18006d91e  mov     edx, 3E8h; nTimeOut
0x18006d923  mov     rcx, r15; lpNamedPipeName
0x18006d926  test    r13d, r13d
0x18006d929  jnz     loc_18006D9F0
0x18006d92f  call    cs:__imp_WaitNamedPipeW
0x18006d936  nop     dword ptr [rax+rax+00h]
0x18006d93b  mov     ebx, dword ptr [rbp+80h+var_60]
0x18006d93e  inc     ebx
0x18006d940  mov     dword ptr [rbp+80h+var_60], ebx
0x18006d943  call    cs:__imp_GetTickCount64
0x18006d94a  nop     dword ptr [rax+rax+00h]
0x18006d94f  sub     rax, [rbp+80h+var_70]
0x18006d953  cmp     rax, 9C40h
0x18006d959  jb      loc_18006D76B
0x18006d95f  cmp     ebx, 14h
0x18006d962  jbe     loc_18006D76B
0x18006d968  mov     eax, [rbp+80h+var_7C]
0x18006d96b  mov     edi, 6BBh
0x18006d970  neg     eax
0x18006d972  mov     r8d, 0BFh; unsigned __int16
0x18006d978  mov     r9, r15; unsigned __int16 *
0x18006d97b  mov     edx, edi; int
0x18006d97d  sbb     ecx, ecx
0x18006d97f  add     ecx, 5; unsigned int
0x18006d982  call    ?RpcpErrorAddRecord@@YAXKJGPEAG@Z; RpcpErrorAddRecord(ulong,long,ushort,ushort *)
0x18006d987  jmp     loc_18006D83C
0x18006d98c  mov     eax, 0A4h
0x18006d991  jmp     loc_18006D85D
0x18006d996  mov     eax, 574h
0x18006d99b  cmp     ebx, eax
0x18006d99d  jle     loc_18006DCAE
0x18006d9a3  mov     eax, 700h
0x18006d9a8  cmp     ebx, eax
0x18006d9aa  jle     loc_18006DD74
0x18006d9b0  mov     ecx, ebx
0x18006d9b2  sub     ecx, 701h
0x18006d9b8  jz      short loc_18006D9E6
  ... truncated ...
```
