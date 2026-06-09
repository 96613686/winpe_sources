# RpcGetUserCredentials

- ea: `0x18005de80`
- end: `0x18005e3e3`
- name: `RpcGetUserCredentials`
- size: `1379`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180009940`
- `0x18000ba50`
- `0x18000f760`
- `0x1800139c0`
- `0x180018184`
- `0x180033330`
- `0x180033f60`
- `0x18003440c`
- `0x18005de80`
- `0x18006775c`
- `0x1800a1c40`
- `0x1800caed0`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e0af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e0af`
- `RPCRT4!RpcRevertToSelf` at `0x18005e303`
- `RPCRT4!RpcRevertToSelf` at `0x18005e303`
- `RPCRT4!RpcImpersonateClient` at `0x18005df38`
- `RPCRT4!RpcImpersonateClient` at `0x18005df38`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005e15b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005e222`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005e15b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005e222`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005e34a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005e359`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005e34a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005e359`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005e2c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005e2f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005e2c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005e2f2`
- `CRYPT32!CryptUnprotectMemory` at `0x18005e09f`
- `CRYPT32!CryptUnprotectMemory` at `0x18005e09f`

## string_xrefs

- `0x18005df57`: `RpcImpersonateClient failed: 0x%x`
- `0x18005e0f4`: `CUtils::GetComputerName failed: 0x%x in %s`

## pseudocode

```c
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
  v14 = (**v30)(v30, (GUID *)qword_1800E8758, &v36);
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
0x18005de80  push    rbp
0x18005de82  push    rbx
0x18005de83  push    rsi
0x18005de84  push    rdi
0x18005de85  push    r12
0x18005de87  push    r13
0x18005de89  push    r14
0x18005de8b  push    r15
0x18005de8d  lea     rbp, [rsp-228h]
0x18005de95  sub     rsp, 328h
0x18005de9c  mov     rax, cs:__security_cookie
0x18005dea3  xor     rax, rsp
0x18005dea6  mov     [rbp+260h+var_50], rax
0x18005dead  xor     r15d, r15d
0x18005deb0  lea     r12, aRpcgetusercred; "RpcGetUserCredentials"
0x18005deb7  mov     rsi, rdx
0x18005deba  mov     [rsp+360h+Block], r15
0x18005debf  xorps   xmm0, xmm0
0x18005dec2  mov     [rsp+360h+Block+8], r15
0x18005dec7  mov     r8, r12; char *
0x18005deca  mov     [rsp+360h+var_308], r15
0x18005decf  xor     edx, edx; int
0x18005ded1  mov     [rsp+360h+var_2F8], r15
0x18005ded6  lea     rcx, [rbp+260h+var_2C0]; this
0x18005deda  mov     [rsp+360h+var_300], r15
0x18005dedf  mov     r14d, r15d
0x18005dee2  mov     [rbp+260h+var_2D8], r15
0x18005dee6  mov     edi, r15d
0x18005dee9  mov     [rbp+260h+var_2E0], r15
0x18005deed  movups  [rbp+260h+Buf2], xmm0
0x18005def1  mov     [rsp+360h+pv], r15
0x18005def6  mov     [rsp+360h+pDataIn], r15
0x18005defb  mov     [rsp+360h+var_2F0], r15d
0x18005df00  mov     [rsp+360h+cbDataIn], r15d
0x18005df05  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x18005df0a  lea     r13d, [r15+8]
0x18005df0e  test    rsi, rsi
0x18005df11  jnz     short loc_18005DF36
0x18005df13  mov     r9, r12
0x18005df16  lea     r8, aPpcredentials; "ppCredentials"
0x18005df1d  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x18005df24  mov     ecx, r13d; int
0x18005df27  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005df2c  mov     ebx, 80070057h
0x18005df31  jmp     loc_18005E2B8
0x18005df36  xor     ecx, ecx; BindingHandle
0x18005df38  call    cs:__imp_RpcImpersonateClient
0x18005df3f  nop     dword ptr [rax+rax+00h]
0x18005df44  test    eax, eax
0x18005df46  jle     short loc_18005DF52
0x18005df48  movzx   eax, ax
0x18005df4b  or      eax, 80070000h
0x18005df50  test    eax, eax
0x18005df52  jns     short loc_18005DF70
0x18005df54  mov     r8d, eax
0x18005df57  lea     rdx, aRpcimpersonate_1; "RpcImpersonateClient failed: 0x%x"
0x18005df5e  mov     ecx, r13d; int
0x18005df61  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005df66  mov     ebx, 80070005h
0x18005df6b  jmp     loc_18005E2B8
0x18005df70  lea     rcx, [rsp+360h+var_2F8]; struct ITSSession **
0x18005df75  mov     r14d, 1
0x18005df7b  call    ?GetSessionFromRpcClientId@CRpcUtils@@SAJPEAPEAUITSSession@@@Z; CRpcUtils::GetSessionFromRpcClientId(ITSSession * *)
0x18005df80  mov     ebx, eax
0x18005df82  test    eax, eax
0x18005df84  jns     short loc_18005DFA0
0x18005df86  lea     rdx, aCrpcutilsGetse; "CRpcUtils::GetSessionFromRpcClientId fa"...
0x18005df8d  mov     ecx, r13d; int
0x18005df90  mov     r8d, eax
0x18005df93  mov     r9, r12
0x18005df96  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005df9b  jmp     loc_18005E2B8
0x18005dfa0  mov     rcx, [rsp+360h+var_2F8]
0x18005dfa5  lea     rdx, [rsp+360h+var_300]
0x18005dfaa  mov     rax, [rcx]
0x18005dfad  mov     rax, [rax+68h]
0x18005dfb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dfb6  mov     ebx, eax
0x18005dfb8  test    eax, eax
0x18005dfba  jns     short loc_18005DFC5
0x18005dfbc  lea     rdx, aGetterminalFai; "GetTerminal failed: 0x%x in %s"
0x18005dfc3  jmp     short loc_18005DF8D
0x18005dfc5  mov     rcx, [rsp+360h+var_2F8]
0x18005dfca  lea     rdx, [rbp+260h+Buf2]
0x18005dfce  mov     rax, [rcx]
0x18005dfd1  mov     rax, [rax+0A8h]
0x18005dfd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dfdd  test    eax, eax
0x18005dfdf  js      loc_18005E1C8
0x18005dfe5  mov     ebx, 10h
0x18005dfea  lea     rdx, [rbp+260h+Buf2]; Buf2
0x18005dfee  mov     r8d, ebx; Size
0x18005dff1  lea     rcx, TERMINAL_TYPE_WORKER; Buf1
0x18005dff8  call    memcmp_0
0x18005dffd  test    eax, eax
0x18005dfff  jnz     loc_18005E1C8
0x18005e005  mov     rcx, [rsp+360h+var_300]
0x18005e00a  lea     r8, [rsp+360h+var_330]
0x18005e00f  mov     [rsp+360h+var_330], r15
0x18005e014  lea     rdx, IID_IWorkerTerminal
0x18005e01b  mov     [rsp+360h+var_2EC], ebx
0x18005e01f  mov     rax, [rcx]
0x18005e022  mov     rax, [rax]
0x18005e025  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e02a  mov     ebx, eax
0x18005e02c  test    eax, eax
0x18005e02e  jns     short loc_18005E054
0x18005e030  lea     rdx, aQiIworkertermi; "QI( IWorkerTerminal ) failed: 0x%x in %"...
0x18005e037  mov     r8d, eax
0x18005e03a  mov     r9, r12
0x18005e03d  mov     ecx, r13d; int
0x18005e040  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005e045  lea     rcx, [rsp+360h+var_330]; void *
0x18005e04a  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18005e04f  jmp     loc_18005E2B8
0x18005e054  mov     rcx, [rsp+360h+var_330]
0x18005e059  lea     rdx, [rsp+360h+cbDataIn]
0x18005e05e  mov     [rsp+360h+var_340], rdx
0x18005e063  lea     r9, [rsp+360h+pDataIn]
0x18005e068  lea     r8, [rsp+360h+var_2F0]
0x18005e06d  lea     rdx, [rsp+360h+pv]
0x18005e072  mov     rax, [rcx]
0x18005e075  mov     rax, [rax+0E8h]
0x18005e07c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e081  mov     ebx, eax
0x18005e083  test    eax, eax
0x18005e085  jns     short loc_18005E090
0x18005e087  lea     rdx, aGetuserinforma; "GetUserInformation failed: 0x%x in %s"
0x18005e08e  jmp     short loc_18005E037
0x18005e090  mov     edx, [rsp+360h+cbDataIn]; cbDataIn
0x18005e094  mov     r8d, 2; dwFlags
0x18005e09a  mov     rcx, [rsp+360h+pDataIn]; pDataIn
0x18005e09f  call    cs:__imp_CryptUnprotectMemory
0x18005e0a6  nop     dword ptr [rax+rax+00h]
0x18005e0ab  test    eax, eax
0x18005e0ad  jnz     short loc_18005E0DD
0x18005e0af  call    cs:__imp_GetLastError
0x18005e0b6  nop     dword ptr [rax+rax+00h]
0x18005e0bb  mov     ebx, eax
0x18005e0bd  test    eax, eax
0x18005e0bf  jle     short loc_18005E0CA
0x18005e0c1  movzx   ebx, ax
0x18005e0c4  or      ebx, 80070000h
0x18005e0ca  test    ebx, ebx
0x18005e0cc  jns     short loc_18005E0DD
0x18005e0ce  mov     r8d, ebx
0x18005e0d1  lea     rdx, aCryptunprotect_1; "CryptUnprotectMemory failed: 0x%x in %s"
0x18005e0d8  jmp     loc_18005E03A
0x18005e0dd  lea     rdx, [rsp+360h+var_2EC]; unsigned int *
0x18005e0e2  lea     rcx, [rbp+260h+var_70]; unsigned __int16 *
0x18005e0e9  call    ?GetComputerNameW@CUtils@@SAJPEAGPEAK@Z; CUtils::GetComputerNameW(ushort *,ulong *)
0x18005e0ee  mov     ebx, eax
0x18005e0f0  test    eax, eax
0x18005e0f2  jns     short loc_18005E100
0x18005e0f4  lea     rdx, aCutilsGetcompu_0; "CUtils::GetComputerName failed: 0x%x in"...
0x18005e0fb  jmp     loc_18005E037
0x18005e100  mov     r8, [rsp+360h+pDataIn]; unsigned __int16 *
0x18005e105  lea     r9, [rbp+260h+var_2E0]; struct ICredentials **
0x18005e109  mov     rcx, [rsp+360h+pv]; unsigned __int16 *
0x18005e10e  lea     rdx, [rbp+260h+var_70]; unsigned __int16 *
0x18005e115  call    ?GetInstanceOfPasswordCredentials@CCredentialsFactory@@SAJPEBG00PEAPEAVICredentials@@@Z; CCredentialsFactory::GetInstanceOfPasswordCredentials(ushort const *,ushort const *,ushort const *,ICredentials * *)
0x18005e11a  mov     ebx, eax
0x18005e11c  test    eax, eax
0x18005e11e  jns     short loc_18005E12C
0x18005e120  lea     rdx, aGetinstanceofp_1; "GetInstanceOfPasswordCredentials failed"...
0x18005e127  jmp     loc_18005E037
0x18005e12c  mov     rcx, [rbp+260h+var_2E0]
0x18005e130  lea     rdx, [rsp+360h+Block]
0x18005e135  mov     rax, [rcx]
0x18005e138  mov     rax, [rax+18h]
0x18005e13c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e141  mov     ebx, eax
0x18005e143  test    eax, eax
0x18005e145  jns     short loc_18005E153
0x18005e147  lea     rdx, aPtrclientcrede; "ptrClientCredentials->GetCredentials fa"...
0x18005e14e  jmp     loc_18005E037
0x18005e153  mov     edx, 18h; uBytes
0x18005e158  lea     ecx, [rdx+28h]; uFlags
0x18005e15b  call    cs:__imp_LocalAlloc
0x18005e162  nop     dword ptr [rax+rax+00h]
0x18005e167  mov     rdi, rax
0x18005e16a  test    rax, rax
0x18005e16d  jnz     short loc_18005E179
0x18005e16f  mov     ebx, 8007000Eh
0x18005e174  jmp     loc_18005E045
0x18005e179  xorps   xmm0, xmm0
0x18005e17c  lea     rcx, [rdi+8]; unsigned __int8 **
0x18005e180  movups  xmmword ptr [rdi], xmm0
0x18005e183  xor     eax, eax
0x18005e185  mov     [rdi+10h], rax
0x18005e189  movups  xmm0, xmmword ptr [rsp+360h+Block]
0x18005e18e  movups  xmmword ptr [rdi], xmm0
0x18005e191  movsd   xmm1, [rsp+360h+var_308]
0x18005e197  movsd   qword ptr [rdi+10h], xmm1
0x18005e19c  mov     r8d, dword ptr [rsp+360h+Block+4]; unsigned int
0x18005e1a1  mov     rdx, [rsp+360h+Block+8]; unsigned __int8 *
0x18005e1a6  call    ?MIDL_mem_dup@CRpcUtils@@SAJPEAPEAEQEAEK@Z; CRpcUtils::MIDL_mem_dup(uchar * *,uchar * const,ulong)
0x18005e1ab  mov     ebx, eax
0x18005e1ad  test    eax, eax
0x18005e1af  jns     short loc_18005E1BD
0x18005e1b1  lea     rdx, aMidlMemDupFail; "MIDL_mem_dup failed: 0x%x in %s"
0x18005e1b8  jmp     loc_18005E037
0x18005e1bd  mov     [rsi], rdi
0x18005e1c0  mov     ebx, r15d
0x18005e1c3  jmp     loc_18005E045
0x18005e1c8  mov     rcx, [rsp+360h+var_300]
0x18005e1cd  lea     r8, [rbp+260h+var_2D8]
0x18005e1d1  lea     rdx, qword_1800E8758
0x18005e1d8  mov     rax, [rcx]
0x18005e1db  mov     rax, [rax]
0x18005e1de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e1e3  mov     ebx, eax
0x18005e1e5  cmp     eax, 80004002h
0x18005e1ea  jnz     short loc_18005E205
0x18005e1ec  lea     rdx, aTerminalIsNotR; "Terminal is not remote terminal, no use"...
0x18005e1f3  mov     ecx, r14d; int
0x18005e1f6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005e1fb  mov     ebx, 80070002h
0x18005e200  jmp     loc_18005E2B8
0x18005e205  test    eax, eax
0x18005e207  jns     short loc_18005E21A
0x18005e209  lea     rdx, aQiIremotetermi_0; "QI( IRemoteTerminal ) failed: 0x%x in %"...
0x18005e210  mov     ecx, 4
0x18005e215  jmp     loc_18005DF90
0x18005e21a  mov     edx, 18h; uBytes
0x18005e21f  lea     ecx, [rdx+28h]; uFlags
0x18005e222  call    cs:__imp_LocalAlloc
0x18005e229  nop     dword ptr [rax+rax+00h]
0x18005e22e  mov     rdi, rax
0x18005e231  test    rax, rax
0x18005e234  jnz     short loc_18005E23D
0x18005e236  mov     ebx, 8007000Eh
0x18005e23b  jmp     short loc_18005E2B8
0x18005e23d  xor     eax, eax
0x18005e23f  lea     rdx, [rsp+360h+Block]
0x18005e244  xorps   xmm0, xmm0
0x18005e247  movups  xmmword ptr [rdi], xmm0
0x18005e24a  mov     [rdi+10h], rax
0x18005e24e  mov     rcx, [rbp+260h+var_2D8]
0x18005e252  mov     rax, [rcx]
0x18005e255  mov     rax, [rax+108h]
0x18005e25c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e261  mov     ebx, eax
0x18005e263  test    eax, eax
0x18005e265  jns     short loc_18005E27D
0x18005e267  mov     r8d, eax
0x18005e26a  lea     rdx, aPtrremotetermi_15; "ptrRemoteTerminal->GetUserCredentials f"...
0x18005e271  mov     ecx, 4; int
0x18005e276  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005e27b  jmp     short loc_18005E2B8
0x18005e27d  movups  xmm0, xmmword ptr [rsp+360h+Block]
0x18005e282  lea     rcx, [rdi+8]; unsigned __int8 **
0x18005e286  movups  xmmword ptr [rdi], xmm0
0x18005e289  movsd   xmm1, [rsp+360h+var_308]
0x18005e28f  movsd   qword ptr [rdi+10h], xmm1
0x18005e294  mov     r8d, dword ptr [rsp+360h+Block+4]; unsigned int
0x18005e299  mov     rdx, [rsp+360h+Block+8]; unsigned __int8 *
0x18005e29e  call    ?MIDL_mem_dup@CRpcUtils@@SAJPEAPEAEQEAEK@Z; CRpcUtils::MIDL_mem_dup(uchar * *,uchar * const,ulong)
0x18005e2a3  mov     ebx, eax
0x18005e2a5  test    eax, eax
0x18005e2a7  jns     short loc_18005E2B5
0x18005e2a9  lea     rdx, aMidlMemDupFail; "MIDL_mem_dup failed: 0x%x in %s"
0x18005e2b0  jmp     loc_18005DF8D
0x18005e2b5  mov     [rsi], rdi
0x18005e2b8  mov     rcx, [rsp+360h+pv]; pv
0x18005e2bd  test    rcx, rcx
0x18005e2c0  jz      short loc_18005E2CE
0x18005e2c2  call    cs:__imp_CoTaskMemFree
0x18005e2c9  nop     dword ptr [rax+rax+00h]
0x18005e2ce  mov     rcx, [rsp+360h+pDataIn]
0x18005e2d3  test    rcx, rcx
0x18005e2d6  jz      short loc_18005E2FE
0x18005e2d8  mov     eax, [rsp+360h+cbDataIn]
0x18005e2dc  test    rax, rax
0x18005e2df  jz      short loc_18005E2F2
0x18005e2e1  mov     [rcx], r15b
0x18005e2e4  inc     rcx
0x18005e2e7  sub     rax, 1
0x18005e2eb  jnz     short loc_18005E2E1
0x18005e2ed  mov     rcx, [rsp+360h+pDataIn]; pv
0x18005e2f2  call    cs:__imp_CoTaskMemFree
0x18005e2f9  nop     dword ptr [rax+rax+00h]
0x18005e2fe  test    r14d, r14d
0x18005e301  jz      short loc_18005E338
0x18005e303  call    cs:__imp_RpcRevertToSelf
0x18005e30a  nop     dword ptr [rax+rax+00h]
0x18005e30f  test    eax, eax
0x18005e311  jle     short loc_18005E31D
0x18005e313  movzx   eax, ax
0x18005e316  or      eax, 80070000h
0x18005e31b  test    eax, eax
0x18005e31d  jns     short loc_18005E338
0x18005e31f  mov     r8d, eax
0x18005e322  lea     rdx, aRpcreverttosel_1; "RpcRevertToSelf failed: 0x%x"
0x18005e329  mov     ecx, r13d; int
0x18005e32c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005e331  mov     ebx, 80070005h
0x18005e336  jmp     short loc_18005E33C
0x18005e338  test    ebx, ebx
0x18005e33a  jns     short loc_18005E365
  ... truncated ...
```
