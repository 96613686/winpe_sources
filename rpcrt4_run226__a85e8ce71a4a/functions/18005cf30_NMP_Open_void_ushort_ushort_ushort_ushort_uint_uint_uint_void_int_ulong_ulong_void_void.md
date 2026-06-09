# NMP_Open(void *,ushort *,ushort *,ushort *,ushort *,uint,uint,uint,void *,int,ulong,ulong,void *,void *)

- ea: `0x18005cf30`
- end: `0x18005d7f7`
- name: `?NMP_Open@@YAJPEAXPEAG111III0HKK00@Z`
- size: `2247`
- prototype: `__int64 __usercall@<rax>(PVOID pv@<rcx>, unsigned __int16 *@<rdx>, unsigned __int16 *@<r8>, unsigned __int16 *@<r9>, unsigned __int16 *, unsigned int, unsigned int, unsigned int, void *, int, unsigned int, unsigned int, void *, void *)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x1800283bc`
- `0x18002fd80`
- `0x1800505f0`
- `0x18005ceb0`
- `0x18005cf30`
- `0x18005d800`
- `0x18005d88c`
- `0x18005da9c`
- `0x18007d5e0`
- `0x1800a6a40`
- `0x1800a73a8`
- `0x1800ca031`
- `0x1800ca140`
- `0x1800d2010`

## import_xrefs

- `ntdll!_wcsicmp` at `0x18005d4eb`
- `ntdll!_wcsicmp` at `0x18005d4eb`
- `ntdll!RtlDllShutdownInProgress` at `0x18005cf64`
- `ntdll!RtlDllShutdownInProgress` at `0x18005cf64`
- `ntdll!_wcsnicmp` at `0x18005cfeb`
- `ntdll!_wcsnicmp` at `0x18005d4ae`
- `ntdll!_wcsnicmp` at `0x18005cfeb`
- `ntdll!_wcsnicmp` at `0x18005d4ae`
- `ntdll!RtlGetLastNtStatus` at `0x18005d7e2`
- `ntdll!RtlGetLastNtStatus` at `0x18005d7e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d539`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d539`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d544`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d544`
- `api-ms-win-core-namedpipe-l1-1-0!SetNamedPipeHandleState` at `0x18005d1e9`
- `api-ms-win-core-namedpipe-l1-1-0!SetNamedPipeHandleState` at `0x18005d1e9`
- `api-ms-win-core-namedpipe-l1-1-0!WaitNamedPipeW` at `0x18005d366`
- `api-ms-win-core-namedpipe-l1-1-0!WaitNamedPipeW` at `0x18005d366`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005d18e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005d374`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005d18e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005d374`
- `ext-ms-win-core-winrt-remote-l1-1-0!WaitRemotePipe` at `0x18005d41b`
- `ext-ms-win-core-winrt-remote-l1-1-0!WaitRemotePipe` at `0x18005d41b`
- `ext-ms-win-core-winrt-remote-l1-1-0!GetLocalEndPointMapperCrossVmPipeName` at `0x18005d502`
- `ext-ms-win-core-winrt-remote-l1-1-0!GetLocalEndPointMapperCrossVmPipeName` at `0x18005d502`
- `ext-ms-win-core-winrt-remote-l1-1-0!RemoteWinRTActivation` at `0x18005d4c6`
- `ext-ms-win-core-winrt-remote-l1-1-0!RemoteWinRTActivation` at `0x18005d7d3`
- `ext-ms-win-core-winrt-remote-l1-1-0!RemoteWinRTActivation` at `0x18005d4c6`
- `ext-ms-win-core-winrt-remote-l1-1-0!RemoteWinRTActivation` at `0x18005d7d3`
- `ext-ms-win-core-winrt-remote-l1-1-0!ValidateRemoteVmNamedPipeEndpoint` at `0x18005d524`
- `ext-ms-win-core-winrt-remote-l1-1-0!ValidateRemoteVmNamedPipeEndpoint` at `0x18005d524`
- `ext-ms-win-core-winrt-remote-l1-1-0!GetEndPointMapperCrossVmPipeNamespace` at `0x18005d49c`
- `ext-ms-win-core-winrt-remote-l1-1-0!GetEndPointMapperCrossVmPipeNamespace` at `0x18005d49c`

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
               CO_ConnectionThreadPoolCallback,
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
0x18005cf30  push    rbp
0x18005cf32  push    rbx
0x18005cf33  push    rsi
0x18005cf34  push    rdi
0x18005cf35  push    r12
0x18005cf37  push    r13
0x18005cf39  push    r14
0x18005cf3b  push    r15
0x18005cf3d  sub     rsp, 78h
0x18005cf41  lea     rbp, [rsp+30h]
0x18005cf46  mov     rax, cs:__security_cookie
0x18005cf4d  xor     rax, rbp
0x18005cf50  mov     [rbp+80h+var_50], rax
0x18005cf54  xor     r15d, r15d
0x18005cf57  mov     r13, r9
0x18005cf5a  mov     [rbp+80h+var_58], r15
0x18005cf5e  mov     r14, r8
0x18005cf61  mov     rsi, rcx
0x18005cf64  call    cs:__imp_RtlDllShutdownInProgress
0x18005cf6a  test    al, al
0x18005cf6c  jnz     loc_18005D3B7
0x18005cf72  cmp     [rbp+80h+arg_58], r15d
0x18005cf79  jnz     loc_18005D7ED
0x18005cf7f  cmp     [rbp+80h+arg_60], r15
0x18005cf86  jnz     loc_18005D7ED
0x18005cf8c  mov     rcx, [rbp+80h+arg_20]
0x18005cf93  mov     r12d, r15d
0x18005cf96  test    rcx, rcx
0x18005cf99  jnz     loc_18005D06D
0x18005cf9f  mov     ecx, 5Ch ; '\'
0x18005cfa4  cmp     [r14], cx
0x18005cfa8  jz      loc_18005D45F
0x18005cfae  mov     ebx, r15d
0x18005cfb1  mov     rcx, r14; String1
0x18005cfb4  mov     [rbp+80h+Mode], ebx
0x18005cfb7  call    ?NMP_IsLocalAlias@@YAHQEAG@Z; NMP_IsLocalAlias(ushort * const)
0x18005cfbc  mov     edi, eax
0x18005cfbe  mov     [rbp+80h+var_7C], eax
0x18005cfc1  call    IsGetLocalVmAliasNamePresent
0x18005cfc6  test    al, al
0x18005cfc8  jnz     loc_18005D49C
0x18005cfce  call    IsGetLocalVmAliasNamePresent
0x18005cfd3  test    al, al
0x18005cfd5  jnz     loc_18005D4C6
0x18005cfdb  mov     r8d, 6; MaxCount
0x18005cfe1  lea     rdx, aPipe; "\\pipe\\"
0x18005cfe8  mov     rcx, r13; String1
0x18005cfeb  call    cs:__imp__wcsnicmp
0x18005cff1  test    eax, eax
0x18005cff3  jnz     loc_18005D0C4
0x18005cff9  test    edi, edi
0x18005cffb  jz      short loc_18005D004
0x18005cffd  lea     r14, asc_1800E2440; "."
0x18005d004  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18005d008  mov     rax, rcx
0x18005d00b  inc     rax
0x18005d00e  cmp     [r14+rax*2], r15w
0x18005d013  jnz     short loc_18005D00B
0x18005d015  mov     [rbp+80h+var_60], rax
0x18005d019  mov     rdi, rcx
0x18005d01c  inc     rdi
0x18005d01f  cmp     [r13+rdi*2+0], r15w
0x18005d025  jnz     short loc_18005D01C
0x18005d027  add     eax, 3
0x18005d02a  add     eax, edi
0x18005d02c  lea     rbx, [rax+rax]
0x18005d030  test    rbx, rbx
0x18005d033  jnz     loc_18005D0D9
0x18005d039  lea     rcx, [rbx+8]
0x18005d03d  cmp     rcx, rbx
0x18005d040  jb      loc_18005D14F
0x18005d046  mov     rax, cs:g_pfnAllocate
0x18005d04d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d052  mov     r15, rax
0x18005d055  test    rax, rax
0x18005d058  jz      loc_18005D14F
0x18005d05e  mov     dword ptr [rax], 70616548h
0x18005d064  add     r15, 8
0x18005d068  jmp     loc_18005D14F
0x18005d06d  cmp     [rcx], r15w
0x18005d071  jz      loc_18005CF9F
0x18005d077  xor     eax, eax
0x18005d079  lea     rdx, [rbp+80h+var_70]
0x18005d07d  mov     [rbp+80h+var_70], rax
0x18005d081  mov     [rbp+80h+var_68], eax
0x18005d084  call    I_RpcParseSecurity
0x18005d089  mov     edi, eax
0x18005d08b  test    eax, eax
0x18005d08d  jnz     loc_18005D293
0x18005d093  mov     r12d, dword ptr [rbp+80h+var_70+4]
0x18005d097  mov     al, byte ptr [rbp+80h+var_68]
0x18005d09a  or      r12d, 10h
0x18005d09e  shl     r12d, 10h
0x18005d0a2  neg     al
0x18005d0a4  mov     al, byte ptr [rbp+80h+var_68+1]
0x18005d0a7  sbb     ecx, ecx
0x18005d0a9  and     ecx, 40000h
0x18005d0af  or      r12d, ecx
0x18005d0b2  neg     al
0x18005d0b4  sbb     ecx, ecx
0x18005d0b6  and     ecx, 80000h
0x18005d0bc  or      r12d, ecx
0x18005d0bf  jmp     loc_18005CF9F
0x18005d0c4  cmp     [r13+0], r15w
0x18005d0c9  jz      loc_18005D004
0x18005d0cf  mov     edi, 6AAh
0x18005d0d4  jmp     loc_18005D293
0x18005d0d9  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18005d0e0  ja      loc_18005D039
0x18005d0e6  mov     rcx, cs:g_ulAdditionalProbeSize
0x18005d0ed  add     rcx, 8
0x18005d0f1  add     rcx, rbx
0x18005d0f4  cmp     rcx, rbx
0x18005d0f7  jb      loc_18005D039
0x18005d0fd  call    VerifyStackAvailable
0x18005d102  test    eax, eax
0x18005d104  jz      loc_18005D039
0x18005d10a  lea     rax, [rbx+8]
0x18005d10e  lea     rcx, [rax+0Fh]
0x18005d112  cmp     rcx, rax
0x18005d115  ja      short loc_18005D121
0x18005d117  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18005d121  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18005d125  mov     rax, rcx
0x18005d128  call    __chkstk_0
0x18005d12d  sub     rsp, rcx
0x18005d130  lea     r15, [rsp+0B0h+Mode]
0x18005d135  test    r15, r15
0x18005d138  jz      loc_18005D039
0x18005d13e  mov     dword ptr [r15], 6B637453h
0x18005d145  add     r15, 8
0x18005d149  jz      loc_18005D039
0x18005d14f  test    r15, r15
0x18005d152  jz      loc_18005D28E
0x18005d158  mov     ebx, dword ptr [rbp+80h+var_60]
0x18005d15b  lea     rcx, [r15+4]; void *
0x18005d15f  xor     eax, eax
0x18005d161  mov     dword ptr [r15], 5C005Ch
0x18005d168  mov     rdx, r14; Src
0x18005d16b  mov     [rbp+80h+var_78], eax
0x18005d16e  lea     r8, [rbx+rbx]; Size
0x18005d172  call    memcpy_0
0x18005d177  lea     r8d, [rdi+1]
0x18005d17b  mov     rdx, r13; Src
0x18005d17e  lea     rcx, [rbx+2]
0x18005d182  add     r8, r8; Size
0x18005d185  lea     rcx, [r15+rcx*2]; void *
0x18005d189  call    memcpy_0
0x18005d18e  call    cs:__imp_GetTickCount64
0x18005d194  mov     r13d, [rbp+80h+Mode]
0x18005d198  mov     r14d, 2
0x18005d19e  mov     [rbp+80h+var_70], rax
0x18005d1a2  mov     dword ptr [rbp+80h+var_60], 0
0x18005d1a9  lea     r8, [rbp+80h+var_58]; void **
0x18005d1ad  mov     edx, r12d; unsigned int
0x18005d1b0  mov     rcx, r15; unsigned __int16 *
0x18005d1b3  call    ?NMP_CreateFile@@YAJPEAGKPEAPEAX@Z; NMP_CreateFile(ushort *,ulong,void * *)
0x18005d1b8  mov     rdi, [rbp+80h+var_58]
0x18005d1bc  test    eax, eax
0x18005d1be  mov     ebx, eax
0x18005d1c0  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18005d1c7  cmovnz  rdi, rax
0x18005d1cb  mov     [rbp+80h+var_58], rdi
0x18005d1cf  cmp     rdi, rax
0x18005d1d2  jz      loc_18005D2B2
0x18005d1d8  xor     r9d, r9d; lpCollectDataTimeout
0x18005d1db  mov     [rbp+80h+Mode], r14d
0x18005d1df  xor     r8d, r8d; lpMaxCollectionCount
0x18005d1e2  lea     rdx, [rbp+80h+Mode]; lpMode
0x18005d1e6  mov     rcx, rdi; hNamedPipe
0x18005d1e9  call    cs:__imp_SetNamedPipeHandleState
0x18005d1ef  test    eax, eax
0x18005d1f1  jz      loc_18005D539
0x18005d1f7  lea     rax, [rsi+90h]
0x18005d1fe  mov     r9d, 1; int
0x18005d204  mov     r8, rsi; pv
0x18005d207  mov     [rsp+0B0h+var_90], rax; struct RPC_THREAD_POOL_IO **
0x18005d20c  lea     rdx, ?CO_ConnectionThreadPoolCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z; pfnio
0x18005d213  mov     rcx, rdi; fl
0x18005d216  call    ?CreateIoEx@RPC_THREAD_POOL@@SAJPEAXP6AXPEAU_TP_CALLBACK_INSTANCE@@00K_KPEAU_TP_IO@@@Z0HPEAPEAVRPC_THREAD_POOL_IO@@@Z; RPC_THREAD_POOL::CreateIoEx(void *,void (*)(_TP_CALLBACK_INSTANCE *,void *,void *,ulong,unsigned __int64,_TP_IO *),void *,int,RPC_THREAD_POOL_IO * *)
0x18005d21b  xor     ecx, ecx
0x18005d21d  mov     ebx, eax
0x18005d21f  test    eax, eax
0x18005d221  jnz     loc_18005D541
0x18005d227  mov     eax, cs:?gPostSize@@3IA; uint gPostSize
0x18005d22d  mov     [rsi+28h], rdi
0x18005d231  mov     edi, ecx
0x18005d233  mov     [rsi+40h], eax
0x18005d236  mov     [rsi+10h], ecx
0x18005d239  mov     [rsi+80h], rcx
0x18005d240  mov     [rsi+44h], rcx
0x18005d244  mov     [rsi+60h], rcx
0x18005d248  mov     [rsi+68h], rcx
0x18005d24c  mov     [rsi+70h], rcx
0x18005d250  mov     [rsi+50h], rsi
0x18005d254  mov     [rsi+78h], rcx
0x18005d258  mov     [rsi+58h], rcx
0x18005d25c  mov     [rsi+30h], ecx
0x18005d25f  mov     [rsi+34h], ecx
0x18005d262  mov     [rsi+38h], rcx
0x18005d266  mov     [rsi+88h], rcx
0x18005d26d  mov     [rsi+98h], rcx
0x18005d274  lea     rcx, [r15-8]
0x18005d278  cmp     dword ptr [rcx], 70616548h
0x18005d27e  jnz     short loc_18005D293
0x18005d280  mov     rax, cs:g_pfnFree
0x18005d287  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d28c  jmp     short loc_18005D293
0x18005d28e  mov     edi, 0Eh
0x18005d293  mov     eax, edi
0x18005d295  mov     rcx, [rbp+80h+var_50]
0x18005d299  xor     rcx, rbp; StackCookie
0x18005d29c  call    __security_check_cookie
0x18005d2a1  lea     rsp, [rbp+48h]
0x18005d2a5  pop     r15
0x18005d2a7  pop     r14
0x18005d2a9  pop     r13
0x18005d2ab  pop     r12
0x18005d2ad  pop     rdi
0x18005d2ae  pop     rsi
0x18005d2af  pop     rbx
0x18005d2b0  pop     rbp
0x18005d2b1  retn
0x18005d2b2  mov     [rbp+80h+var_78], 1
0x18005d2b9  cmp     ebx, 0E7h
0x18005d2bf  jz      loc_18005D355
0x18005d2c5  mov     eax, [rbp+80h+var_7C]
0x18005d2c8  mov     r8d, 0BEh; unsigned __int16
0x18005d2ce  neg     eax
0x18005d2d0  mov     dword ptr [rsp+0B0h+var_90], r12d; unsigned int
0x18005d2d5  mov     r9, r15; unsigned __int16 *
0x18005d2d8  mov     edx, ebx; int
0x18005d2da  sbb     ecx, ecx
0x18005d2dc  add     ecx, 5; unsigned int
0x18005d2df  call    ?RpcpErrorAddRecord@@YAXKJGPEAGK@Z; RpcpErrorAddRecord(ulong,long,ushort,ushort *,ulong)
0x18005d2e4  mov     eax, 51Fh
0x18005d2e9  mov     edi, 0Eh
0x18005d2ee  cmp     ebx, eax
0x18005d2f0  jg      loc_18005D3C1
0x18005d2f6  jz      loc_18005D411
0x18005d2fc  cmp     ebx, 45h ; 'E'
0x18005d2ff  jg      loc_18005D5C5
0x18005d305  jz      loc_18005D7B3
0x18005d30b  cmp     ebx, 1Fh
0x18005d30e  jg      loc_18005D568
0x18005d314  jz      loc_18005D455
0x18005d31a  cmp     ebx, 4
0x18005d31d  jle     loc_18005D426
0x18005d323  cmp     ebx, 5
0x18005d326  jz      loc_18005D411
0x18005d32c  cmp     ebx, edi
0x18005d32e  jnz     loc_18005D557
0x18005d334  mov     r8d, 0C1h; unsigned __int16
0x18005d33a  mov     [rsp+0B0h+var_90], 0; struct tagParam *
0x18005d343  xor     r9d, r9d; int
0x18005d346  mov     edx, edi; int
0x18005d348  mov     ecx, r14d; unsigned int
0x18005d34b  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x18005d350  jmp     loc_18005D274
0x18005d355  mov     edx, 3E8h; nTimeOut
0x18005d35a  mov     rcx, r15; lpNamedPipeName
0x18005d35d  test    r13d, r13d
0x18005d360  jnz     loc_18005D41B
0x18005d366  call    cs:__imp_WaitNamedPipeW
0x18005d36c  mov     ebx, dword ptr [rbp+80h+var_60]
0x18005d36f  inc     ebx
0x18005d371  mov     dword ptr [rbp+80h+var_60], ebx
0x18005d374  call    cs:__imp_GetTickCount64
0x18005d37a  sub     rax, [rbp+80h+var_70]
0x18005d37e  cmp     rax, 9C40h
0x18005d384  jb      loc_18005D1A9
0x18005d38a  cmp     ebx, 14h
0x18005d38d  jbe     loc_18005D1A9
0x18005d393  mov     eax, [rbp+80h+var_7C]
0x18005d396  mov     edi, 6BBh
0x18005d39b  neg     eax
0x18005d39d  mov     r8d, 0BFh; unsigned __int16
0x18005d3a3  mov     r9, r15; unsigned __int16 *
0x18005d3a6  mov     edx, edi; int
0x18005d3a8  sbb     ecx, ecx
0x18005d3aa  add     ecx, 5; unsigned int
0x18005d3ad  call    ?RpcpErrorAddRecord@@YAXKJGPEAG@Z; RpcpErrorAddRecord(ulong,long,ushort,ushort *)
0x18005d3b2  jmp     loc_18005D274
0x18005d3b7  mov     eax, 0A4h
0x18005d3bc  jmp     loc_18005D295
0x18005d3c1  mov     eax, 574h
0x18005d3c6  cmp     ebx, eax
0x18005d3c8  jle     loc_18005D6A3
0x18005d3ce  mov     eax, 700h
0x18005d3d3  cmp     ebx, eax
0x18005d3d5  jle     loc_18005D769
0x18005d3db  mov     ecx, ebx
0x18005d3dd  sub     ecx, 701h
0x18005d3e3  jz      short loc_18005D411
0x18005d3e5  sub     ecx, 0Fh
0x18005d3e8  jz      short loc_18005D411
0x18005d3ea  sub     ecx, r14d
0x18005d3ed  jz      short loc_18005D411
0x18005d3ef  sub     ecx, 6
0x18005d3f2  jz      loc_18005D334
  ... truncated ...
```
