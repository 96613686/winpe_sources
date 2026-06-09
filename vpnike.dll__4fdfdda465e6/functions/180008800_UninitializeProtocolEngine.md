# UninitializeProtocolEngine

- ea: `0x180008800`
- end: `0x1800088bd`
- name: `UninitializeProtocolEngine`
- size: `189`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800082d0`

## callees

- `0x180002d8c`
- `0x180008800`
- `0x180063af0`
- `0x1800768d4`
- `0x180076b60`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008882`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008882`

## string_xrefs

- `0x180008843`: `UninitializeProtocolEngine`

## pseudocode

```c
__int64 __fastcall UninitializeProtocolEngine(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  VPNIKEProtocolEngine *v4; // rcx
  __int64 v5; // rax
  unsigned int v6; // ebx
  __int64 v8; // [rsp+20h] [rbp-48h] BYREF
  __int128 v9; // [rsp+28h] [rbp-40h]
  __int128 v10; // [rsp+38h] [rbp-30h]
  __int64 v11; // [rsp+48h] [rbp-20h]
  int v12; // [rsp+50h] [rbp-18h]
  int v13; // [rsp+54h] [rbp-14h]
  unsigned int v14; // [rsp+78h] [rbp+10h] BYREF

  v12 = -1;
  v14 = 0;
  v9 = 0;
  v8 = 0;
  v10 = 0;
  v11 = 0;
  v13 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v8,
      L"UninitializeProtocolEngine",
      &v14,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunction);
  if ( g_RasRpcInitialized )
  {
    UninitializeVpnIkeRpcServer(a1, a2, a3, a4, v8, v9, *((_QWORD *)&v9 + 1));
    g_RasRpcInitialized = 0;
  }
  v4 = VpnIkeProtocolEngine;
  if ( VpnIkeProtocolEngine )
  {
    v5 = *((_QWORD *)VpnIkeProtocolEngine + 1);
    if ( v5 )
    {
      WaitForSingleObject(*(HANDLE *)(v5 + 8), 0xFFFFFFFF);
      v4 = VpnIkeProtocolEngine;
    }
    (*(void (__fastcall **)(VPNIKEProtocolEngine *))(*(_QWORD *)v4 + 24LL))(v4);
    VPNIKEProtocolEngine::DestroyInstance();
    VpnIkeProtocolEngine = 0;
  }
  v6 = v14;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v8);
  return v6;
}

```

## disassembly

```asm
0x180008800  mov     rax, rsp
0x180008803  push    rbx
0x180008804  sub     rsp, 60h
0x180008808  xor     ebx, ebx
0x18000880a  mov     dword ptr [rax-18h], 0FFFFFFFFh
0x180008811  test    cs:byte_1800AA941, 8
0x180008818  xorps   xmm0, xmm0
0x18000881b  xorps   xmm1, xmm1
0x18000881e  mov     [rax+10h], ebx
0x180008821  movdqu  xmmword ptr [rax-40h], xmm0
0x180008826  mov     [rax-48h], rbx
0x18000882a  movdqu  xmmword ptr [rax-30h], xmm1
0x18000882f  mov     [rax-20h], rbx
0x180008833  mov     [rax-14h], ebx
0x180008836  jz      short loc_180008853
0x180008838  lea     r9, ?RasVpnIkeTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x18000883f  lea     r8, [rax+10h]; unsigned int *
0x180008843  lea     rdx, aUninitializepr_0; "UninitializeProtocolEngine"
0x18000884a  lea     rcx, [rax-48h]; this
0x18000884e  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x180008853  cmp     cs:?g_RasRpcInitialized@@3HA, ebx; int g_RasRpcInitialized
0x180008859  jz      short loc_180008866
0x18000885b  call    UninitializeVpnIkeRpcServer
0x180008860  mov     cs:?g_RasRpcInitialized@@3HA, ebx; int g_RasRpcInitialized
0x180008866  mov     rcx, cs:?VpnIkeProtocolEngine@@3PEAVVPNIKEProtocolEngine@@EA; VPNIKEProtocolEngine * VpnIkeProtocolEngine
0x18000886d  test    rcx, rcx
0x180008870  jz      short loc_1800088A7
0x180008872  mov     rax, [rcx+8]
0x180008876  test    rax, rax
0x180008879  jz      short loc_18000888F
0x18000887b  mov     rcx, [rax+8]; hHandle
0x18000887f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180008882  call    cs:__imp_WaitForSingleObject
0x180008888  mov     rcx, cs:?VpnIkeProtocolEngine@@3PEAVVPNIKEProtocolEngine@@EA; VPNIKEProtocolEngine * VpnIkeProtocolEngine
0x18000888f  mov     rax, [rcx]
0x180008892  mov     rax, [rax+18h]
0x180008896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000889b  call    ?DestroyInstance@VPNIKEProtocolEngine@@SAXXZ; VPNIKEProtocolEngine::DestroyInstance(void)
0x1800088a0  mov     cs:?VpnIkeProtocolEngine@@3PEAVVPNIKEProtocolEngine@@EA, rbx; VPNIKEProtocolEngine * VpnIkeProtocolEngine
0x1800088a7  mov     ebx, [rsp+68h+arg_8]
0x1800088ab  lea     rcx, [rsp+68h+var_48]; this
0x1800088b0  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x1800088b5  mov     eax, ebx
0x1800088b7  add     rsp, 60h
0x1800088bb  pop     rbx
0x1800088bc  retn
```
