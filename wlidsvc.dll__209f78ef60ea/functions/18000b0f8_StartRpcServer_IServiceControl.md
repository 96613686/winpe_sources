# StartRpcServer(IServiceControl *)

- ea: `0x18000b0f8`
- end: `0x18000b394`
- name: `?StartRpcServer@@YAJPEAVIServiceControl@@@Z`
- size: `668`
- prototype: `__int64 __fastcall(struct IServiceControl *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800bcff0`

## callees

- `0x180009f00`
- `0x18000a36c`
- `0x18000b0f8`
- `0x180019690`
- `0x180054fb4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b16d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b16d`
- `RPCRT4!RpcServerInterfaceGroupActivate` at `0x18000b2a9`
- `RPCRT4!RpcServerInterfaceGroupActivate` at `0x18000b359`
- `RPCRT4!RpcServerInterfaceGroupActivate` at `0x18000b2a9`
- `RPCRT4!RpcServerInterfaceGroupActivate` at `0x18000b359`
- `RPCRT4!RpcServerInterfaceGroupCreateW` at `0x18000b292`
- `RPCRT4!RpcServerInterfaceGroupCreateW` at `0x18000b346`
- `RPCRT4!RpcServerInterfaceGroupCreateW` at `0x18000b292`
- `RPCRT4!RpcServerInterfaceGroupCreateW` at `0x18000b346`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000b163`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000b163`

## string_xrefs

- `0x18000b190`: `onecoreuap\ds\ext\live\identity\ntservice\svc\wlidrpc.cpp`
- `0x18000b183`: `ConvertStringSecurityDescriptorToSecurityDescriptor returned 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall StartRpcServer(struct IServiceControl *a1)
{
  unsigned __int64 v1; // rdi
  PPTraceStatus *v2; // rcx
  bool v3; // zf
  char v4; // al
  signed int LastError; // eax
  unsigned int v6; // ebx
  PSECURITY_DESCRIPTOR SecurityDescriptor[3]; // [rsp+40h] [rbp-C0h] BYREF
  int v9; // [rsp+58h] [rbp-A8h] BYREF
  const wchar_t *v10; // [rsp+60h] [rbp-A0h]
  __int64 v11; // [rsp+68h] [rbp-98h]
  PSECURITY_DESCRIPTOR v12; // [rsp+70h] [rbp-90h]
  int v13; // [rsp+78h] [rbp-88h]
  int v14; // [rsp+80h] [rbp-80h] BYREF
  const wchar_t *v15; // [rsp+88h] [rbp-78h]
  const wchar_t *v16; // [rsp+90h] [rbp-70h]
  __int64 v17; // [rsp+98h] [rbp-68h]
  int v18; // [rsp+A0h] [rbp-60h]
  int v19; // [rsp+B0h] [rbp-50h] BYREF
  __int64 *v20; // [rsp+B8h] [rbp-48h]
  __int128 v21; // [rsp+C0h] [rbp-40h]
  int v22; // [rsp+D0h] [rbp-30h]
  __int64 v23; // [rsp+D4h] [rbp-2Ch]
  __int64 v24; // [rsp+E0h] [rbp-20h]
  __int64 v25; // [rsp+E8h] [rbp-18h]
  const wchar_t *v26; // [rsp+F0h] [rbp-10h]
  __int64 v27; // [rsp+F8h] [rbp-8h]
  int v28; // [rsp+100h] [rbp+0h] BYREF
  __int64 *v29; // [rsp+108h] [rbp+8h]
  __int128 v30; // [rsp+110h] [rbp+10h]
  int v31; // [rsp+120h] [rbp+20h]
  __int64 v32; // [rsp+124h] [rbp+24h]
  __int64 v33; // [rsp+130h] [rbp+30h]
  __int64 v34; // [rsp+138h] [rbp+38h]
  const wchar_t *v35; // [rsp+140h] [rbp+40h]
  PSECURITY_DESCRIPTOR v36; // [rsp+148h] [rbp+48h]
  int v37; // [rsp+150h] [rbp+50h]
  __int64 *v38; // [rsp+158h] [rbp+58h]
  __int128 v39; // [rsp+160h] [rbp+60h]
  int v40; // [rsp+170h] [rbp+70h]
  __int64 v41; // [rsp+174h] [rbp+74h]
  __int64 v42; // [rsp+180h] [rbp+80h]
  __int64 v43; // [rsp+188h] [rbp+88h]
  const wchar_t *v44; // [rsp+190h] [rbp+90h]
  __int64 v45; // [rsp+198h] [rbp+98h]

  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v1 = 2;
  if ( PPTraceStatus::GetAssertFlag(a1) == 1 || (v3 = PPTraceStatus::GetAssertFlag(v2) == 2, v4 = 0, v3) )
    v4 = 1;
  if ( !v4 )
    v1 = -(__int64)((Microsoft_Windows_LiveIdEnableBits & 0x20) != 0) & 2;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;GA;;;BA)(A;;GA;;;OW)(A;;GR;;;S-1-15-3-1024-1941919063-976504945-319178505"
          "9-2835515153-1936800635-1519032070-1452055454-2678282739)",
         1u,
         SecurityDescriptor,
         0) )
  {
    v28 = 0;
    v29 = qword_180129410;
    v30 = 0;
    v31 = 41;
    v32 = 1234;
    v33 = 0;
    v34 = 0;
    v35 = L"LiveIdSvc RPC Interface";
    v36 = SecurityDescriptor[0];
    v37 = 0;
    v38 = qword_180129470;
    v39 = 0;
    v40 = 41;
    v41 = 1234;
    v42 = 0;
    v43 = 0;
    v44 = L"OnlineProviderCert RPC Interface";
    v45 = 0;
    v9 = 0;
    v10 = L"ncalrpc";
    v11 = 0;
    v12 = SecurityDescriptor[0];
    v13 = 10;
    v6 = RpcServerInterfaceGroupCreateW(
           &v28,
           2,
           &v9,
           1,
           g_RpcIdleTimeoutSeconds,
           IdleCallback,
           &g_WLIDSvc,
           &qword_1801C35C0);
    if ( !v6 )
    {
      v6 = RpcServerInterfaceGroupActivate(qword_1801C35C0);
      if ( !v6 )
      {
        v19 = 0;
        v20 = qword_1801294D0;
        v21 = 0;
        v22 = 41;
        v23 = 1234;
        v24 = 0;
        v25 = 0;
        v26 = L"LiveIdSvcNotify RPC Interface";
        v27 = 0;
        v14 = 0;
        v15 = L"ncalrpc";
        v16 = L"liveidsvcnotify";
        v17 = 0;
        v18 = 10;
        v6 = RpcServerInterfaceGroupCreateW(&v19, 1, &v14, 1, -1, 0, &g_WLIDSvc, &qword_1801C35C8);
        if ( !v6 )
          v6 = RpcServerInterfaceGroupActivate(qword_1801C35C8);
      }
    }
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    TracePrintW(
      5u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\svc\\wlidrpc.cpp",
      0xB9u,
      L"ConvertStringSecurityDescriptorToSecurityDescriptor returned 0x%x",
      LastError);
    v6 = 1338;
  }
  ErrorVerifier::CheckAgainstList("StartRpcServer", v6, v1, &qword_180137BC8);
  Auto<_NGC_USER_ID_KEY_INFO *,LocalAllocFunctor<_NGC_USER_ID_KEY_INFO *>,DummyContext>::~Auto<_NGC_USER_ID_KEY_INFO *,LocalAllocFunctor<_NGC_USER_ID_KEY_INFO *>,DummyContext>(SecurityDescriptor);
  return v6;
}

```

## disassembly

```asm
0x18000b0f8  push    rbp
0x18000b0fa  push    rbx
0x18000b0fb  push    rsi
0x18000b0fc  push    rdi
0x18000b0fd  push    r13
0x18000b0ff  lea     rbp, [rsp-0A0h]
0x18000b107  sub     rsp, 1A0h
0x18000b10e  xor     esi, esi
0x18000b110  mov     [rsp+1C0h+SecurityDescriptor], rsi
0x18000b115  mov     [rsp+1C0h+var_170], rsi
0x18000b11a  mov     [rsp+1C0h+var_178], rsi
0x18000b11f  lea     ebx, [rsi+2]
0x18000b122  mov     edi, ebx
0x18000b124  call    ?GetAssertFlag@PPTraceStatus@@YAKXZ; PPTraceStatus::GetAssertFlag(void)
0x18000b129  cmp     eax, 1
0x18000b12c  jz      short loc_18000B13A
0x18000b12e  call    ?GetAssertFlag@PPTraceStatus@@YAKXZ; PPTraceStatus::GetAssertFlag(void)
0x18000b133  cmp     eax, ebx
0x18000b135  mov     al, sil
0x18000b138  jnz     short loc_18000B13C
0x18000b13a  mov     al, 1
0x18000b13c  test    al, al
0x18000b13e  jnz     short loc_18000B150
0x18000b140  mov     al, cs:Microsoft_Windows_LiveIdEnableBits
0x18000b146  and     al, 20h
0x18000b148  neg     al
0x18000b14a  sbb     rax, rax
0x18000b14d  and     rdi, rax
0x18000b150  xor     r9d, r9d; SecurityDescriptorSize
0x18000b153  lea     r8, [rsp+1C0h+SecurityDescriptor]; SecurityDescriptor
0x18000b158  lea     edx, [r9+1]; StringSDRevision
0x18000b15c  lea     rcx, StringSecurityDescriptor; "D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;G"...
0x18000b163  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000b169  test    eax, eax
0x18000b16b  jnz     short loc_18000B1AB
0x18000b16d  call    cs:__imp_GetLastError
0x18000b173  test    eax, eax
0x18000b175  jle     short loc_18000B17F
0x18000b177  movzx   eax, ax
0x18000b17a  or      eax, 80070000h
0x18000b17f  mov     [rsp+1C0h+var_1A0], eax
0x18000b183  lea     r9, aConvertstrings_2; "ConvertStringSecurityDescriptorToSecuri"...
0x18000b18a  mov     r8d, 0B9h; unsigned int
0x18000b190  lea     rdx, aOnecoreuapDsEx_49; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18000b197  mov     ecx, 5; unsigned __int8
0x18000b19c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000b1a1  mov     ebx, 53Ah
0x18000b1a6  jmp     loc_18000B361
0x18000b1ab  mov     [rbp+0C0h+var_C0], esi
0x18000b1ae  lea     rax, qword_180129410
0x18000b1b5  mov     [rbp+0C0h+var_B8], rax
0x18000b1b9  xorps   xmm0, xmm0
0x18000b1bc  movdqa  [rbp+0C0h+var_B0], xmm0
0x18000b1c1  mov     [rbp+0C0h+var_A0], 29h ; ')'
0x18000b1c8  mov     [rbp+0C0h+var_9C], 4D2h
0x18000b1d0  mov     [rbp+0C0h+var_90], rsi
0x18000b1d4  mov     [rbp+0C0h+var_88], rsi
0x18000b1d8  lea     rax, aLiveidsvcRpcIn; "LiveIdSvc RPC Interface"
0x18000b1df  mov     [rbp+0C0h+var_80], rax
0x18000b1e3  mov     rax, [rsp+1C0h+SecurityDescriptor]
0x18000b1e8  mov     [rbp+0C0h+var_78], rax
0x18000b1ec  mov     [rbp+0C0h+var_70], esi
0x18000b1ef  lea     rcx, qword_180129470
0x18000b1f6  mov     [rbp+0C0h+var_68], rcx
0x18000b1fa  movdqa  [rbp+0C0h+var_60], xmm0
0x18000b1ff  mov     [rbp+0C0h+var_50], 29h ; ')'
0x18000b206  mov     [rbp+0C0h+var_4C], 4D2h
0x18000b20e  mov     [rbp+0C0h+var_40], rsi
0x18000b215  mov     [rbp+0C0h+var_38], rsi
0x18000b21c  lea     rcx, aOnlineprovider; "OnlineProviderCert RPC Interface"
0x18000b223  mov     [rbp+0C0h+var_30], rcx
0x18000b22a  mov     [rbp+0C0h+var_28], rsi
0x18000b231  mov     [rsp+1C0h+var_168], esi
0x18000b235  lea     r13, aNcalrpc; "ncalrpc"
0x18000b23c  mov     [rsp+1C0h+var_160], r13
0x18000b241  mov     [rsp+1C0h+var_158], rsi
0x18000b246  mov     [rsp+1C0h+var_150], rax
0x18000b24b  mov     [rsp+1C0h+var_148], 0Ah
0x18000b253  mov     eax, cs:?g_RpcIdleTimeoutSeconds@@3KA; ulong g_RpcIdleTimeoutSeconds
0x18000b259  lea     rcx, qword_1801C35C0
0x18000b260  mov     [rsp+1C0h+var_188], rcx
0x18000b265  lea     rcx, ?g_WLIDSvc@@3VCWLIDSvcModule@@A; CWLIDSvcModule g_WLIDSvc
0x18000b26c  mov     [rsp+1C0h+var_190], rcx
0x18000b271  lea     rcx, ?IdleCallback@@YAXPEAX0K@Z; IdleCallback(void *,void *,ulong)
0x18000b278  mov     [rsp+1C0h+var_198], rcx
0x18000b27d  mov     [rsp+1C0h+var_1A0], eax
0x18000b281  mov     r9d, 1
0x18000b287  lea     r8, [rsp+1C0h+var_168]
0x18000b28c  mov     edx, ebx
0x18000b28e  lea     rcx, [rbp+0C0h+var_C0]
0x18000b292  call    cs:__imp_RpcServerInterfaceGroupCreateW
0x18000b298  mov     ebx, eax
0x18000b29a  test    eax, eax
0x18000b29c  jnz     loc_18000B361
0x18000b2a2  mov     rcx, cs:qword_1801C35C0
0x18000b2a9  call    cs:__imp_RpcServerInterfaceGroupActivate
0x18000b2af  mov     ebx, eax
0x18000b2b1  test    eax, eax
0x18000b2b3  jnz     loc_18000B361
0x18000b2b9  mov     [rbp+0C0h+var_110], esi
0x18000b2bc  lea     rax, qword_1801294D0
0x18000b2c3  mov     [rbp+0C0h+var_108], rax
0x18000b2c7  xorps   xmm0, xmm0
0x18000b2ca  movdqa  [rbp+0C0h+var_100], xmm0
0x18000b2cf  mov     [rbp+0C0h+var_F0], 29h ; ')'
0x18000b2d6  mov     [rbp+0C0h+var_EC], 4D2h
0x18000b2de  mov     [rbp+0C0h+var_E0], rsi
0x18000b2e2  mov     [rbp+0C0h+var_D8], rsi
0x18000b2e6  lea     rax, aLiveidsvcnotif_0; "LiveIdSvcNotify RPC Interface"
0x18000b2ed  mov     [rbp+0C0h+var_D0], rax
0x18000b2f1  mov     [rbp+0C0h+var_C8], rsi
0x18000b2f5  mov     [rbp+0C0h+var_140], esi
0x18000b2f8  mov     [rbp+0C0h+var_138], r13
0x18000b2fc  lea     rax, aLiveidsvcnotif; "liveidsvcnotify"
0x18000b303  mov     [rbp+0C0h+var_130], rax
0x18000b307  mov     [rbp+0C0h+var_128], rsi
0x18000b30b  mov     [rbp+0C0h+var_120], 0Ah
0x18000b312  lea     rax, qword_1801C35C8
0x18000b319  mov     [rsp+1C0h+var_188], rax
0x18000b31e  lea     rax, ?g_WLIDSvc@@3VCWLIDSvcModule@@A; CWLIDSvcModule g_WLIDSvc
0x18000b325  mov     [rsp+1C0h+var_190], rax
0x18000b32a  mov     [rsp+1C0h+var_198], rsi
0x18000b32f  mov     [rsp+1C0h+var_1A0], 0FFFFFFFFh
0x18000b337  lea     r9d, [rbx+1]
0x18000b33b  lea     r8, [rbp+0C0h+var_140]
0x18000b33f  mov     edx, r9d
0x18000b342  lea     rcx, [rbp+0C0h+var_110]
0x18000b346  call    cs:__imp_RpcServerInterfaceGroupCreateW
0x18000b34c  mov     ebx, eax
0x18000b34e  test    eax, eax
0x18000b350  jnz     short loc_18000B361
0x18000b352  mov     rcx, cs:qword_1801C35C8
0x18000b359  call    cs:__imp_RpcServerInterfaceGroupActivate
0x18000b35f  mov     ebx, eax
0x18000b361  lea     r9, qword_180137BC8; int *
0x18000b368  mov     r8, rdi; unsigned __int64
0x18000b36b  mov     edx, ebx; int
0x18000b36d  lea     rcx, aStartrpcserver; "StartRpcServer"
0x18000b374  call    ?CheckAgainstList@ErrorVerifier@@SAXPEBDJ_KPEBJ@Z; ErrorVerifier::CheckAgainstList(char const *,long,unsigned __int64,long const *)
0x18000b379  nop
0x18000b37a  lea     rcx, [rsp+1C0h+SecurityDescriptor]
0x18000b37f  call    ??1?$Auto@PEAU_NGC_USER_ID_KEY_INFO@@V?$LocalAllocFunctor@PEAU_NGC_USER_ID_KEY_INFO@@@@VDummyContext@@@@QEAA@XZ; Auto<_NGC_USER_ID_KEY_INFO *,LocalAllocFunctor<_NGC_USER_ID_KEY_INFO *>,DummyContext>::~Auto<_NGC_USER_ID_KEY_INFO *,LocalAllocFunctor<_NGC_USER_ID_KEY_INFO *>,DummyContext>(void)
0x18000b384  mov     eax, ebx
0x18000b386  add     rsp, 1A0h
0x18000b38d  pop     r13
0x18000b38f  pop     rdi
0x18000b390  pop     rsi
0x18000b391  pop     rbx
0x18000b392  pop     rbp
0x18000b393  retn
```
