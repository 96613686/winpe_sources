# InitState(void)

- ea: `0x180008730`
- end: `0x180008917`
- name: `?InitState@@YAJXZ`
- size: `487`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800084f0`

## callees

- `0x180008730`
- `0x18000b940`
- `0x18000f9dc`
- `0x18001b020`
- `0x18001b048`
- `0x1800211a0`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180008904`
- `ntdll!RtlLeaveCriticalSection` at `0x180008904`
- `ntdll!RtlEnterCriticalSection` at `0x18000874c`
- `ntdll!RtlEnterCriticalSection` at `0x18000874c`
- `RPCRT4!I_RpcExceptionFilter` at `0x180022350`
- `RPCRT4!I_RpcExceptionFilter` at `0x180022350`
- `RPCRT4!I_RpcMapWin32Status` at `0x180008868`
- `RPCRT4!I_RpcMapWin32Status` at `0x180008868`
- `RPCRT4!NdrClientCall3` at `0x180008852`
- `RPCRT4!NdrClientCall3` at `0x180008852`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180008898`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180008898`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800088ec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800088ec`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800087f2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800087f2`

## string_xrefs

- `0x180008891`: `sspicli.dll`

## pseudocode

```c
__int64 InitState(void)
{
  CLIENT_CALL_RETURN v0; // rbx
  int RpcConnection; // eax
  _QWORD *v2; // rcx
  int v4; // [rsp+50h] [rbp+8h] BYREF
  __int64 v5; // [rsp+58h] [rbp+10h] BYREF
  CLIENT_CALL_RETURN v6; // [rsp+60h] [rbp+18h]

  LODWORD(v0.Pointer) = 0;
  v5 = 0;
  v4 = 0;
  RtlEnterCriticalSection(&csSecurity);
  if ( SecDllClient )
    goto LABEL_16;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_7b25146ef51239e0444a068fecac4892_Traceguids);
  RpcConnection = CreateRpcConnection(0, 2, (__int64)&v5, (__int64)&SecLsaPackageCount, (__int64)&v4);
  LODWORD(v0.Pointer) = RpcConnection;
  if ( RpcConnection < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        &WPP_7b25146ef51239e0444a068fecac4892_Traceguids,
        (unsigned int)RpcConnection);
    goto LABEL_16;
  }
  v2 = LocalAlloc(0x40u, 0x28u);
  SecDllClient = v2;
  if ( v2 )
  {
    v2[3] = v5;
    if ( (v4 & 0x10000) == 0
      || (SecpSetSession(),
          v6.Simple = 0,
          v0.Pointer = NdrClientCall3(
                         (MIDL_STUBLESS_PROXY_INFO *)&sspirpc_ProxyInfo,
                         0x10u,
                         0,
                         v5,
                         &SecpLsaInprocDispatch).Pointer,
          v6.Pointer = v0.Pointer,
          SLODWORD(v0.Simple) >= 0) )
    {
      SecLsaMode = v4;
      LoadLibraryExW(L"sspicli.dll", 0, 0x800u);
      DllState |= 0x40000000u;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_7b25146ef51239e0444a068fecac4892_Traceguids);
LABEL_16:
      if ( SLODWORD(v0.Simple) >= 0 )
        goto LABEL_21;
    }
  }
  else
  {
    LODWORD(v0.Pointer) = -2146893056;
  }
  if ( v5 )
    DisconnectRpcConnection();
  if ( SecDllClient )
  {
    LocalFree(SecDllClient);
    SecDllClient = 0;
  }
LABEL_21:
  RtlLeaveCriticalSection(&csSecurity);
  return LODWORD(v0.Pointer);
}

```

## disassembly

```asm
0x180008730  mov     [rsp+arg_18], rbx
0x180008735  push    rsi
0x180008736  sub     rsp, 40h
0x18000873a  xor     ebx, ebx
0x18000873c  mov     [rsp+48h+arg_8], rbx
0x180008741  mov     [rsp+48h+arg_0], ebx
0x180008745  lea     rcx, csSecurity; CriticalSection
0x18000874c  call    cs:__imp_RtlEnterCriticalSection
0x180008752  cmp     cs:SecDllClient, rbx
0x180008759  jnz     loc_1800088CD
0x18000875f  lea     rsi, WPP_GLOBAL_Control
0x180008766  mov     rcx, cs:WPP_GLOBAL_Control
0x18000876d  cmp     rcx, rsi
0x180008770  jz      short loc_18000878B
0x180008772  test    byte ptr [rcx+1Ch], 4
0x180008776  jz      short loc_18000878B
0x180008778  lea     edx, [rbx+0Ch]
0x18000877b  lea     r8, WPP_7b25146ef51239e0444a068fecac4892_Traceguids
0x180008782  mov     rcx, [rcx+10h]
0x180008786  call    WPP_SF_
0x18000878b  lea     rax, [rsp+48h+arg_0]
0x180008790  mov     [rsp+48h+var_28], rax
0x180008795  lea     r9, SecLsaPackageCount
0x18000879c  lea     r8, [rsp+48h+arg_8]
0x1800087a1  mov     edx, 2
0x1800087a6  xor     ecx, ecx
0x1800087a8  call    CreateRpcConnection
0x1800087ad  mov     ebx, eax
0x1800087af  test    eax, eax
0x1800087b1  jns     short loc_1800087EA
0x1800087b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800087ba  cmp     rcx, rsi
0x1800087bd  jz      loc_1800088CD
0x1800087c3  test    byte ptr [rcx+1Ch], 1
0x1800087c7  jz      loc_1800088CD
0x1800087cd  mov     edx, 0Dh
0x1800087d2  mov     r9d, eax
0x1800087d5  lea     r8, WPP_7b25146ef51239e0444a068fecac4892_Traceguids
0x1800087dc  mov     rcx, [rcx+10h]
0x1800087e0  call    WPP_SF_D
0x1800087e5  jmp     loc_1800088CD
0x1800087ea  mov     edx, 28h ; '('; uBytes
0x1800087ef  lea     ecx, [rdx+18h]; uFlags
0x1800087f2  call    cs:__imp_LocalAlloc
0x1800087f8  mov     rcx, rax
0x1800087fb  mov     cs:SecDllClient, rax
0x180008802  test    rax, rax
0x180008805  jnz     short loc_180008811
0x180008807  mov     ebx, 80090300h
0x18000880c  jmp     loc_1800088D1
0x180008811  mov     rax, [rsp+48h+arg_8]
0x180008816  mov     [rcx+18h], rax
0x18000881a  test    [rsp+48h+arg_0], 10000h
0x180008822  jz      short loc_18000887F
0x180008824  call    SecpSetSession
0x180008829  nop
0x18000882a  mov     [rsp+48h+arg_10], 0
0x180008833  lea     rax, SecpLsaInprocDispatch
0x18000883a  mov     [rsp+48h+var_28], rax
0x18000883f  mov     r9, [rsp+48h+arg_8]
0x180008844  xor     r8d, r8d; pReturnValue
0x180008847  lea     edx, [r8+10h]; nProcNum
0x18000884b  lea     rcx, ?sspirpc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180008852  call    cs:__imp_NdrClientCall3
0x180008858  mov     rbx, rax
0x18000885b  mov     [rsp+48h+arg_10], rax
0x180008860  mov     [rsp+48h+var_18], eax
0x180008864  jmp     short loc_18000887B
0x180008866  mov     ecx, eax; Status
0x180008868  call    cs:__imp_I_RpcMapWin32Status
0x18000886e  mov     ebx, eax
0x180008870  mov     [rsp+48h+var_18], eax
0x180008874  lea     rsi, WPP_GLOBAL_Control
0x18000887b  test    ebx, ebx
0x18000887d  js      short loc_1800088D1
0x18000887f  mov     eax, [rsp+48h+arg_0]
0x180008883  mov     cs:SecLsaMode, eax
0x180008889  xor     edx, edx; hFile
0x18000888b  mov     r8d, 800h; dwFlags
0x180008891  lea     rcx, LibFileName; "sspicli.dll"
0x180008898  call    cs:__imp_LoadLibraryExW
0x18000889e  bts     cs:DllState, 1Eh
0x1800088a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800088ad  cmp     rcx, rsi
0x1800088b0  jz      short loc_1800088CD
0x1800088b2  test    byte ptr [rcx+1Ch], 4
0x1800088b6  jz      short loc_1800088CD
0x1800088b8  mov     edx, 0Eh
0x1800088bd  lea     r8, WPP_7b25146ef51239e0444a068fecac4892_Traceguids
0x1800088c4  mov     rcx, [rcx+10h]
0x1800088c8  call    WPP_SF_
0x1800088cd  test    ebx, ebx
0x1800088cf  jns     short loc_1800088FD
0x1800088d1  mov     rcx, [rsp+48h+arg_8]
0x1800088d6  test    rcx, rcx
0x1800088d9  jz      short loc_1800088E0
0x1800088db  call    DisconnectRpcConnection
0x1800088e0  mov     rcx, cs:SecDllClient; hMem
0x1800088e7  test    rcx, rcx
0x1800088ea  jz      short loc_1800088FD
0x1800088ec  call    cs:__imp_LocalFree
0x1800088f2  mov     cs:SecDllClient, 0
0x1800088fd  lea     rcx, csSecurity; CriticalSection
0x180008904  call    cs:__imp_RtlLeaveCriticalSection
0x18000890a  mov     eax, ebx
0x18000890c  mov     rbx, [rsp+48h+arg_18]
0x180008911  add     rsp, 40h
0x180008915  pop     rsi
0x180008916  retn
0x180022342  push    rbp
0x180022344  sub     rsp, 30h
0x180022348  mov     rbp, rdx
0x18002234b  mov     rcx, [rcx]
0x18002234e  mov     ecx, [rcx]; ExceptionCode
0x180022350  call    cs:__imp_I_RpcExceptionFilter
0x180022356  nop
0x180022357  add     rsp, 30h
0x18002235b  pop     rbp
0x18002235c  retn
```
