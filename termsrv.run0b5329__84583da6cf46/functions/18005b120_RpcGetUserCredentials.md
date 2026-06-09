# RpcGetUserCredentials

- ea: `0x18005b120`
- end: `0x18005b646`
- name: `RpcGetUserCredentials`
- size: `1318`
- prototype: `__int64 __fastcall(__int64, unsigned __int8 ***)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000a210`
- `0x18000bad0`
- `0x18000f1a0`
- `0x180013150`
- `0x180016338`
- `0x180031674`
- `0x1800321f0`
- `0x18003269c`
- `0x18005b120`
- `0x18006459c`
- `0x18009d1d0`
- `0x1800c4e00`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b343`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b343`
- `RPCRT4!RpcRevertToSelf` at `0x18005b579`
- `RPCRT4!RpcRevertToSelf` at `0x18005b579`
- `RPCRT4!RpcImpersonateClient` at `0x18005b1d8`
- `RPCRT4!RpcImpersonateClient` at `0x18005b1d8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005b3e9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005b4aa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005b3e9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005b4aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b5ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b5c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b5ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b5c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005b544`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005b56e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005b544`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005b56e`
- `CRYPT32!CryptUnprotectMemory` at `0x18005b339`
- `CRYPT32!CryptUnprotectMemory` at `0x18005b339`

## string_xrefs

- `0x18005b1f1`: `RpcImpersonateClient failed: 0x%x`
- `0x18005b382`: `CUtils::GetComputerName failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RpcGetUserCredentials(__int64 a1, unsigned __int8 ***a2)
{
  int v3; // r14d
  unsigned __int8 **v4; // rdi
  signed int v5; // ebx
  int v6; // eax
  bool v7; // sf
  int SessionFromRpcClientId; // eax
  const char *v9; // rdx
  int ComputerNameW; // eax
  const char *v11; // rdx
  signed int LastError; // eax
  unsigned __int8 **v13; // rax
  int v14; // eax
  unsigned __int8 **v15; // rax
  int v16; // eax
  _BYTE *v17; // rcx
  __int64 v18; // rax
  int v19; // eax
  bool v20; // sf
  unsigned __int8 *v21; // rcx
  _BYTE *v22; // rcx
  __int64 v23; // rax
  __int64 v25; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbDataIn; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID pDataIn; // [rsp+40h] [rbp-C0h] BYREF
  void *Block[2]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int8 *v29; // [rsp+58h] [rbp-A8h]
  __int64 (__fastcall ***v30)(_QWORD, GUID *, __int64 *); // [rsp+60h] [rbp-A0h] BYREF
  struct ITSSession *v31; // [rsp+68h] [rbp-98h] BYREF
  int v32; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v33; // [rsp+74h] [rbp-8Ch] BYREF
  LPVOID pv; // [rsp+78h] [rbp-88h] BYREF
  struct ICredentials *v35; // [rsp+80h] [rbp-80h] BYREF
  __int64 v36; // [rsp+88h] [rbp-78h] BYREF
  __int128 Buf2; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v38[592]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v39[16]; // [rsp+2F0h] [rbp+1F0h] BYREF

  Block[0] = 0;
  Block[1] = 0;
  v29 = 0;
  v31 = 0;
  v30 = 0;
  v3 = 0;
  v36 = 0;
  v4 = 0;
  v35 = 0;
  Buf2 = 0;
  pv = 0;
  pDataIn = 0;
  v32 = 0;
  cbDataIn = 0;
  CRpcCallTrace::CRpcCallTrace((CRpcCallTrace *)v38, 0, "RpcGetUserCredentials");
  if ( !a2 )
  {
    _DbgPrintMessage(8, "Missing paramter %s in %s", "ppCredentials", "RpcGetUserCredentials");
    v5 = -2147024809;
    goto LABEL_48;
  }
  v6 = RpcImpersonateClient(0);
  v7 = v6 < 0;
  if ( v6 > 0 )
  {
    v6 = (unsigned __int16)v6 | 0x80070000;
    v7 = v6 < 0;
  }
  if ( v7 )
  {
    _DbgPrintMessage(8, "RpcImpersonateClient failed: 0x%x", v6);
    v5 = -2147024891;
    goto LABEL_48;
  }
  v3 = 1;
  SessionFromRpcClientId = CRpcUtils::GetSessionFromRpcClientId(&v31);
  v5 = SessionFromRpcClientId;
  if ( SessionFromRpcClientId < 0 )
  {
    v9 = "CRpcUtils::GetSessionFromRpcClientId failed: 0x%x in %s";
    goto LABEL_9;
  }
  SessionFromRpcClientId = (*(__int64 (__fastcall **)(struct ITSSession *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v31 + 104LL))(
                             v31,
                             &v30);
  v5 = SessionFromRpcClientId;
  if ( SessionFromRpcClientId < 0 )
  {
    v9 = "GetTerminal failed: 0x%x in %s";
    goto LABEL_9;
  }
  if ( (*(int (__fastcall **)(struct ITSSession *, __int128 *))(*(_QWORD *)v31 + 168LL))(v31, &Buf2) >= 0
    && !memcmp_0(TERMINAL_TYPE_WORKER, &Buf2, 0x10u) )
  {
    v25 = 0;
    v33 = 16;
    ComputerNameW = (**v30)(v30, &IID_IWorkerTerminal, &v25);
    v5 = ComputerNameW;
    if ( ComputerNameW >= 0 )
    {
      ComputerNameW = (*(__int64 (__fastcall **)(__int64, LPVOID *, int *, LPVOID *, DWORD *))(*(_QWORD *)v25 + 232LL))(
                        v25,
                        &pv,
                        &v32,
                        &pDataIn,
                        &cbDataIn);
      v5 = ComputerNameW;
      if ( ComputerNameW >= 0 )
      {
        if ( !CryptUnprotectMemory(pDataIn, cbDataIn, 2u) )
        {
          LastError = GetLastError();
          v5 = LastError;
          if ( LastError > 0 )
            v5 = (unsigned __int16)LastError | 0x80070000;
          if ( v5 < 0 )
          {
            _DbgPrintMessage(8, "CryptUnprotectMemory failed: 0x%x in %s", (unsigned int)v5, "RpcGetUserCredentials");
            goto LABEL_18;
          }
        }
        ComputerNameW = CUtils::GetComputerNameW(v39, &v33);
        v5 = ComputerNameW;
        if ( ComputerNameW >= 0 )
        {
          ComputerNameW = CCredentialsFactory::GetInstanceOfPasswordCredentials(
                            (const unsigned __int16 *)pv,
                            v39,
                            (const unsigned __int16 *)pDataIn,
                            &v35);
          v5 = ComputerNameW;
          if ( ComputerNameW >= 0 )
          {
            ComputerNameW = (*(__int64 (__fastcall **)(struct ICredentials *, void **))(*(_QWORD *)v35 + 24LL))(
                              v35,
                              Block);
            v5 = ComputerNameW;
            if ( ComputerNameW >= 0 )
            {
              v13 = (unsigned __int8 **)LocalAlloc(0x40u, 0x18u);
              v4 = v13;
              if ( !v13 )
              {
                v5 = -2147024882;
                goto LABEL_18;
              }
              *(_OWORD *)v13 = 0;
              v13[2] = 0;
              *(_OWORD *)v13 = *(_OWORD *)Block;
              v13[2] = v29;
              ComputerNameW = CRpcUtils::MIDL_mem_dup(v13 + 1, (unsigned __int8 *const)Block[1], HIDWORD(Block[0]));
              v5 = ComputerNameW;
              if ( ComputerNameW >= 0 )
              {
                *a2 = v4;
                v5 = 0;
                goto LABEL_18;
              }
              v11 = "MIDL_mem_dup failed: 0x%x in %s";
            }
            else
            {
              v11 = "ptrClientCredentials->GetCredentials failed: 0x%x in %s";
            }
          }
          else
          {
            v11 = "GetInstanceOfPasswordCredentials failed: 0x%x in %s";
          }
        }
        else
        {
          v11 = "CUtils::GetComputerName failed: 0x%x in %s";
        }
      }
      else
      {
        v11 = "GetUserInformation failed: 0x%x in %s";
      }
    }
    else
    {
      v11 = "QI( IWorkerTerminal ) failed: 0x%x in %s";
    }
    _DbgPrintMessage(8, v11, (unsigned int)ComputerNameW, "RpcGetUserCredentials");
LABEL_18:
    SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v25);
    goto LABEL_48;
  }
  v14 = (**v30)(v30, (GUID *)qword_1800E2708, &v36);
  v5 = v14;
  if ( v14 == -2147467262 )
  {
    _DbgPrintMessage(1, "Terminal is not remote terminal, no user credentials available.");
    v5 = -2147024894;
    goto LABEL_48;
  }
  if ( v14 < 0 )
  {
    _DbgPrintMessage(4, "QI( IRemoteTerminal ) failed: 0x%x in %s", (unsigned int)v14, "RpcGetUserCredentials");
    goto LABEL_48;
  }
  v15 = (unsigned __int8 **)LocalAlloc(0x40u, 0x18u);
  v4 = v15;
  if ( !v15 )
  {
    v5 = -2147024882;
    goto LABEL_48;
  }
  *(_OWORD *)v15 = 0;
  v15[2] = 0;
  v16 = (*(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v36 + 264LL))(v36, Block);
  v5 = v16;
  if ( v16 < 0 )
  {
    _DbgPrintMessage(4, "ptrRemoteTerminal->GetUserCredentials failed: 0x%x", v16);
    goto LABEL_48;
  }
  *(_OWORD *)v4 = *(_OWORD *)Block;
  v4[2] = v29;
  SessionFromRpcClientId = CRpcUtils::MIDL_mem_dup(v4 + 1, (unsigned __int8 *const)Block[1], HIDWORD(Block[0]));
  v5 = SessionFromRpcClientId;
  if ( SessionFromRpcClientId >= 0 )
  {
    *a2 = v4;
    goto LABEL_48;
  }
  v9 = "MIDL_mem_dup failed: 0x%x in %s";
LABEL_9:
  _DbgPrintMessage(8, v9, (unsigned int)SessionFromRpcClientId, "RpcGetUserCredentials");
LABEL_48:
  if ( pv )
    CoTaskMemFree(pv);
  v17 = pDataIn;
  if ( pDataIn )
  {
    v18 = cbDataIn;
    if ( cbDataIn )
    {
      do
      {
        *v17++ = 0;
        --v18;
      }
      while ( v18 );
      v17 = pDataIn;
    }
    CoTaskMemFree(v17);
  }
  if ( !v3 )
    goto LABEL_60;
  v19 = RpcRevertToSelf();
  v20 = v19 < 0;
  if ( v19 > 0 )
  {
    v19 = (unsigned __int16)v19 | 0x80070000;
    v20 = v19 < 0;
  }
  if ( v20 )
  {
    _DbgPrintMessage(8, "RpcRevertToSelf failed: 0x%x", v19);
    v5 = -2147024891;
  }
  else
  {
LABEL_60:
    if ( v5 >= 0 )
      goto LABEL_65;
  }
  if ( v4 )
  {
    v21 = v4[1];
    if ( v21 )
      LocalFree(v21);
    LocalFree(v4);
  }
LABEL_65:
  v22 = Block[1];
  if ( Block[1] )
  {
    v23 = HIDWORD(Block[0]);
    if ( HIDWORD(Block[0]) )
    {
      do
      {
        *v22++ = 0;
        --v23;
      }
      while ( v23 );
      v22 = Block[1];
    }
    operator delete(v22);
  }
  CRpcCallTrace::~CRpcCallTrace((CRpcCallTrace *)v38);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v35);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v36);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v30);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v31);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18005b120  push    rbp
0x18005b122  push    rbx
0x18005b123  push    rsi
0x18005b124  push    rdi
0x18005b125  push    r12
0x18005b127  push    r13
0x18005b129  push    r14
0x18005b12b  push    r15
0x18005b12d  lea     rbp, [rsp-228h]
0x18005b135  sub     rsp, 328h
0x18005b13c  mov     rax, cs:__security_cookie
0x18005b143  xor     rax, rsp
0x18005b146  mov     [rbp+260h+var_50], rax
0x18005b14d  xor     r15d, r15d
0x18005b150  lea     r12, aRpcgetusercred; "RpcGetUserCredentials"
0x18005b157  mov     rsi, rdx
0x18005b15a  mov     [rsp+360h+Block], r15
0x18005b15f  xorps   xmm0, xmm0
0x18005b162  mov     [rsp+360h+Block+8], r15
0x18005b167  mov     r8, r12; char *
0x18005b16a  mov     [rsp+360h+var_308], r15
0x18005b16f  xor     edx, edx; int
0x18005b171  mov     [rsp+360h+var_2F8], r15
0x18005b176  lea     rcx, [rbp+260h+var_2C0]; this
0x18005b17a  mov     [rsp+360h+var_300], r15
0x18005b17f  mov     r14d, r15d
0x18005b182  mov     [rbp+260h+var_2D8], r15
0x18005b186  mov     edi, r15d
0x18005b189  mov     [rbp+260h+var_2E0], r15
0x18005b18d  movups  [rbp+260h+Buf2], xmm0
0x18005b191  mov     [rsp+360h+pv], r15
0x18005b196  mov     [rsp+360h+pDataIn], r15
0x18005b19b  mov     [rsp+360h+var_2F0], r15d
0x18005b1a0  mov     [rsp+360h+cbDataIn], r15d
0x18005b1a5  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x18005b1aa  lea     r13d, [r15+8]
0x18005b1ae  test    rsi, rsi
0x18005b1b1  jnz     short loc_18005B1D6
0x18005b1b3  mov     r9, r12
0x18005b1b6  lea     r8, aPpcredentials; "ppCredentials"
0x18005b1bd  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x18005b1c4  mov     ecx, r13d; int
0x18005b1c7  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005b1cc  mov     ebx, 80070057h
0x18005b1d1  jmp     loc_18005B53A
0x18005b1d6  xor     ecx, ecx; BindingHandle
0x18005b1d8  call    cs:__imp_RpcImpersonateClient
0x18005b1de  test    eax, eax
0x18005b1e0  jle     short loc_18005B1EC
0x18005b1e2  movzx   eax, ax
0x18005b1e5  or      eax, 80070000h
0x18005b1ea  test    eax, eax
0x18005b1ec  jns     short loc_18005B20A
0x18005b1ee  mov     r8d, eax
0x18005b1f1  lea     rdx, aRpcimpersonate_1; "RpcImpersonateClient failed: 0x%x"
0x18005b1f8  mov     ecx, r13d; int
0x18005b1fb  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005b200  mov     ebx, 80070005h
0x18005b205  jmp     loc_18005B53A
0x18005b20a  lea     rcx, [rsp+360h+var_2F8]; struct ITSSession **
0x18005b20f  mov     r14d, 1
0x18005b215  call    ?GetSessionFromRpcClientId@CRpcUtils@@SAJPEAPEAUITSSession@@@Z; CRpcUtils::GetSessionFromRpcClientId(ITSSession * *)
0x18005b21a  mov     ebx, eax
0x18005b21c  test    eax, eax
0x18005b21e  jns     short loc_18005B23A
0x18005b220  lea     rdx, aCrpcutilsGetse; "CRpcUtils::GetSessionFromRpcClientId fa"...
0x18005b227  mov     ecx, r13d; int
0x18005b22a  mov     r8d, eax
0x18005b22d  mov     r9, r12
0x18005b230  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005b235  jmp     loc_18005B53A
0x18005b23a  mov     rcx, [rsp+360h+var_2F8]
0x18005b23f  lea     rdx, [rsp+360h+var_300]
0x18005b244  mov     rax, [rcx]
0x18005b247  mov     rax, [rax+68h]
0x18005b24b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b250  mov     ebx, eax
0x18005b252  test    eax, eax
0x18005b254  jns     short loc_18005B25F
0x18005b256  lea     rdx, aGetterminalFai; "GetTerminal failed: 0x%x in %s"
0x18005b25d  jmp     short loc_18005B227
0x18005b25f  mov     rcx, [rsp+360h+var_2F8]
0x18005b264  lea     rdx, [rbp+260h+Buf2]
0x18005b268  mov     rax, [rcx]
0x18005b26b  mov     rax, [rax+0A8h]
0x18005b272  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b277  test    eax, eax
0x18005b279  js      loc_18005B450
0x18005b27f  mov     ebx, 10h
0x18005b284  lea     rdx, [rbp+260h+Buf2]; Buf2
0x18005b288  mov     r8d, ebx; Size
0x18005b28b  lea     rcx, TERMINAL_TYPE_WORKER; Buf1
0x18005b292  call    memcmp_0
0x18005b297  test    eax, eax
0x18005b299  jnz     loc_18005B450
0x18005b29f  mov     rcx, [rsp+360h+var_300]
0x18005b2a4  lea     r8, [rsp+360h+var_330]
0x18005b2a9  mov     [rsp+360h+var_330], r15
0x18005b2ae  lea     rdx, IID_IWorkerTerminal
0x18005b2b5  mov     [rsp+360h+var_2EC], ebx
0x18005b2b9  mov     rax, [rcx]
0x18005b2bc  mov     rax, [rax]
0x18005b2bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b2c4  mov     ebx, eax
0x18005b2c6  test    eax, eax
0x18005b2c8  jns     short loc_18005B2EE
0x18005b2ca  lea     rdx, aQiIworkertermi; "QI( IWorkerTerminal ) failed: 0x%x in %"...
0x18005b2d1  mov     r8d, eax
0x18005b2d4  mov     r9, r12
0x18005b2d7  mov     ecx, r13d; int
0x18005b2da  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005b2df  lea     rcx, [rsp+360h+var_330]; void *
0x18005b2e4  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18005b2e9  jmp     loc_18005B53A
0x18005b2ee  mov     rcx, [rsp+360h+var_330]
0x18005b2f3  lea     rdx, [rsp+360h+cbDataIn]
0x18005b2f8  mov     [rsp+360h+var_340], rdx
0x18005b2fd  lea     r9, [rsp+360h+pDataIn]
0x18005b302  lea     r8, [rsp+360h+var_2F0]
0x18005b307  lea     rdx, [rsp+360h+pv]
0x18005b30c  mov     rax, [rcx]
0x18005b30f  mov     rax, [rax+0E8h]
0x18005b316  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b31b  mov     ebx, eax
0x18005b31d  test    eax, eax
0x18005b31f  jns     short loc_18005B32A
0x18005b321  lea     rdx, aGetuserinforma; "GetUserInformation failed: 0x%x in %s"
0x18005b328  jmp     short loc_18005B2D1
0x18005b32a  mov     edx, [rsp+360h+cbDataIn]; cbDataIn
0x18005b32e  mov     r8d, 2; dwFlags
0x18005b334  mov     rcx, [rsp+360h+pDataIn]; pDataIn
0x18005b339  call    cs:__imp_CryptUnprotectMemory
0x18005b33f  test    eax, eax
0x18005b341  jnz     short loc_18005B36B
0x18005b343  call    cs:__imp_GetLastError
0x18005b349  mov     ebx, eax
0x18005b34b  test    eax, eax
0x18005b34d  jle     short loc_18005B358
0x18005b34f  movzx   ebx, ax
0x18005b352  or      ebx, 80070000h
0x18005b358  test    ebx, ebx
0x18005b35a  jns     short loc_18005B36B
0x18005b35c  mov     r8d, ebx
0x18005b35f  lea     rdx, aCryptunprotect_1; "CryptUnprotectMemory failed: 0x%x in %s"
0x18005b366  jmp     loc_18005B2D4
0x18005b36b  lea     rdx, [rsp+360h+var_2EC]; unsigned int *
0x18005b370  lea     rcx, [rbp+260h+var_70]; unsigned __int16 *
0x18005b377  call    ?GetComputerNameW@CUtils@@SAJPEAGPEAK@Z; CUtils::GetComputerNameW(ushort *,ulong *)
0x18005b37c  mov     ebx, eax
0x18005b37e  test    eax, eax
0x18005b380  jns     short loc_18005B38E
0x18005b382  lea     rdx, aCutilsGetcompu_0; "CUtils::GetComputerName failed: 0x%x in"...
0x18005b389  jmp     loc_18005B2D1
0x18005b38e  mov     r8, [rsp+360h+pDataIn]; unsigned __int16 *
0x18005b393  lea     r9, [rbp+260h+var_2E0]; struct ICredentials **
0x18005b397  mov     rcx, [rsp+360h+pv]; unsigned __int16 *
0x18005b39c  lea     rdx, [rbp+260h+var_70]; unsigned __int16 *
0x18005b3a3  call    ?GetInstanceOfPasswordCredentials@CCredentialsFactory@@SAJPEBG00PEAPEAVICredentials@@@Z; CCredentialsFactory::GetInstanceOfPasswordCredentials(ushort const *,ushort const *,ushort const *,ICredentials * *)
0x18005b3a8  mov     ebx, eax
0x18005b3aa  test    eax, eax
0x18005b3ac  jns     short loc_18005B3BA
0x18005b3ae  lea     rdx, aGetinstanceofp_1; "GetInstanceOfPasswordCredentials failed"...
0x18005b3b5  jmp     loc_18005B2D1
0x18005b3ba  mov     rcx, [rbp+260h+var_2E0]
0x18005b3be  lea     rdx, [rsp+360h+Block]
0x18005b3c3  mov     rax, [rcx]
0x18005b3c6  mov     rax, [rax+18h]
0x18005b3ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b3cf  mov     ebx, eax
0x18005b3d1  test    eax, eax
0x18005b3d3  jns     short loc_18005B3E1
0x18005b3d5  lea     rdx, aPtrclientcrede; "ptrClientCredentials->GetCredentials fa"...
0x18005b3dc  jmp     loc_18005B2D1
0x18005b3e1  mov     edx, 18h; uBytes
0x18005b3e6  lea     ecx, [rdx+28h]; uFlags
0x18005b3e9  call    cs:__imp_LocalAlloc
0x18005b3ef  mov     rdi, rax
0x18005b3f2  test    rax, rax
0x18005b3f5  jnz     short loc_18005B401
0x18005b3f7  mov     ebx, 8007000Eh
0x18005b3fc  jmp     loc_18005B2DF
0x18005b401  xorps   xmm0, xmm0
0x18005b404  lea     rcx, [rdi+8]; unsigned __int8 **
0x18005b408  movups  xmmword ptr [rdi], xmm0
0x18005b40b  xor     eax, eax
0x18005b40d  mov     [rdi+10h], rax
0x18005b411  movups  xmm0, xmmword ptr [rsp+360h+Block]
0x18005b416  movups  xmmword ptr [rdi], xmm0
0x18005b419  movsd   xmm1, [rsp+360h+var_308]
0x18005b41f  movsd   qword ptr [rdi+10h], xmm1
0x18005b424  mov     r8d, dword ptr [rsp+360h+Block+4]; unsigned int
0x18005b429  mov     rdx, [rsp+360h+Block+8]; unsigned __int8 *
0x18005b42e  call    ?MIDL_mem_dup@CRpcUtils@@SAJPEAPEAEQEAEK@Z; CRpcUtils::MIDL_mem_dup(uchar * *,uchar * const,ulong)
0x18005b433  mov     ebx, eax
0x18005b435  test    eax, eax
0x18005b437  jns     short loc_18005B445
0x18005b439  lea     rdx, aMidlMemDupFail; "MIDL_mem_dup failed: 0x%x in %s"
0x18005b440  jmp     loc_18005B2D1
0x18005b445  mov     [rsi], rdi
0x18005b448  mov     ebx, r15d
0x18005b44b  jmp     loc_18005B2DF
0x18005b450  mov     rcx, [rsp+360h+var_300]
0x18005b455  lea     r8, [rbp+260h+var_2D8]
0x18005b459  lea     rdx, qword_1800E2708
0x18005b460  mov     rax, [rcx]
0x18005b463  mov     rax, [rax]
0x18005b466  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b46b  mov     ebx, eax
0x18005b46d  cmp     eax, 80004002h
0x18005b472  jnz     short loc_18005B48D
0x18005b474  lea     rdx, aTerminalIsNotR; "Terminal is not remote terminal, no use"...
0x18005b47b  mov     ecx, r14d; int
0x18005b47e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005b483  mov     ebx, 80070002h
0x18005b488  jmp     loc_18005B53A
0x18005b48d  test    eax, eax
0x18005b48f  jns     short loc_18005B4A2
0x18005b491  lea     rdx, aQiIremotetermi_0; "QI( IRemoteTerminal ) failed: 0x%x in %"...
0x18005b498  mov     ecx, 4
0x18005b49d  jmp     loc_18005B22A
0x18005b4a2  mov     edx, 18h; uBytes
0x18005b4a7  lea     ecx, [rdx+28h]; uFlags
0x18005b4aa  call    cs:__imp_LocalAlloc
0x18005b4b0  mov     rdi, rax
0x18005b4b3  test    rax, rax
0x18005b4b6  jnz     short loc_18005B4BF
0x18005b4b8  mov     ebx, 8007000Eh
0x18005b4bd  jmp     short loc_18005B53A
0x18005b4bf  xor     eax, eax
0x18005b4c1  lea     rdx, [rsp+360h+Block]
0x18005b4c6  xorps   xmm0, xmm0
0x18005b4c9  movups  xmmword ptr [rdi], xmm0
0x18005b4cc  mov     [rdi+10h], rax
0x18005b4d0  mov     rcx, [rbp+260h+var_2D8]
0x18005b4d4  mov     rax, [rcx]
0x18005b4d7  mov     rax, [rax+108h]
0x18005b4de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b4e3  mov     ebx, eax
0x18005b4e5  test    eax, eax
0x18005b4e7  jns     short loc_18005B4FF
0x18005b4e9  mov     r8d, eax
0x18005b4ec  lea     rdx, aPtrremotetermi_15; "ptrRemoteTerminal->GetUserCredentials f"...
0x18005b4f3  mov     ecx, 4; int
0x18005b4f8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005b4fd  jmp     short loc_18005B53A
0x18005b4ff  movups  xmm0, xmmword ptr [rsp+360h+Block]
0x18005b504  lea     rcx, [rdi+8]; unsigned __int8 **
0x18005b508  movups  xmmword ptr [rdi], xmm0
0x18005b50b  movsd   xmm1, [rsp+360h+var_308]
0x18005b511  movsd   qword ptr [rdi+10h], xmm1
0x18005b516  mov     r8d, dword ptr [rsp+360h+Block+4]; unsigned int
0x18005b51b  mov     rdx, [rsp+360h+Block+8]; unsigned __int8 *
0x18005b520  call    ?MIDL_mem_dup@CRpcUtils@@SAJPEAPEAEQEAEK@Z; CRpcUtils::MIDL_mem_dup(uchar * *,uchar * const,ulong)
0x18005b525  mov     ebx, eax
0x18005b527  test    eax, eax
0x18005b529  jns     short loc_18005B537
0x18005b52b  lea     rdx, aMidlMemDupFail; "MIDL_mem_dup failed: 0x%x in %s"
0x18005b532  jmp     loc_18005B227
0x18005b537  mov     [rsi], rdi
0x18005b53a  mov     rcx, [rsp+360h+pv]; pv
0x18005b53f  test    rcx, rcx
0x18005b542  jz      short loc_18005B54A
0x18005b544  call    cs:__imp_CoTaskMemFree
0x18005b54a  mov     rcx, [rsp+360h+pDataIn]
0x18005b54f  test    rcx, rcx
0x18005b552  jz      short loc_18005B574
0x18005b554  mov     eax, [rsp+360h+cbDataIn]
0x18005b558  test    rax, rax
0x18005b55b  jz      short loc_18005B56E
0x18005b55d  mov     [rcx], r15b
0x18005b560  inc     rcx
0x18005b563  sub     rax, 1
0x18005b567  jnz     short loc_18005B55D
0x18005b569  mov     rcx, [rsp+360h+pDataIn]; pv
0x18005b56e  call    cs:__imp_CoTaskMemFree
0x18005b574  test    r14d, r14d
0x18005b577  jz      short loc_18005B5A8
0x18005b579  call    cs:__imp_RpcRevertToSelf
0x18005b57f  test    eax, eax
0x18005b581  jle     short loc_18005B58D
0x18005b583  movzx   eax, ax
0x18005b586  or      eax, 80070000h
0x18005b58b  test    eax, eax
0x18005b58d  jns     short loc_18005B5A8
0x18005b58f  mov     r8d, eax
0x18005b592  lea     rdx, aRpcreverttosel_1; "RpcRevertToSelf failed: 0x%x"
0x18005b599  mov     ecx, r13d; int
0x18005b59c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005b5a1  mov     ebx, 80070005h
0x18005b5a6  jmp     short loc_18005B5AC
0x18005b5a8  test    ebx, ebx
0x18005b5aa  jns     short loc_18005B5C9
0x18005b5ac  test    rdi, rdi
0x18005b5af  jz      short loc_18005B5C9
0x18005b5b1  mov     rcx, [rdi+8]; hMem
0x18005b5b5  test    rcx, rcx
0x18005b5b8  jz      short loc_18005B5C0
0x18005b5ba  call    cs:__imp_LocalFree
0x18005b5c0  mov     rcx, rdi; hMem
0x18005b5c3  call    cs:__imp_LocalFree
  ... truncated ...
```
