# WinStationIsSessionPermitted

- ea: `0x18000e160`
- end: `0x18000e2af`
- name: `WinStationIsSessionPermitted`
- size: `335`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180004330`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`
- `0x18000e160`
- `0x18000e2c0`
- `0x1800249e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e28d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e28d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e270`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e270`
- `RPCRT4!I_RpcExceptionFilter` at `0x18003341e`
- `RPCRT4!I_RpcExceptionFilter` at `0x18003341e`
- `RPCRT4!NdrClientCall3` at `0x18000e211`
- `RPCRT4!NdrClientCall3` at `0x18000e211`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18000e174`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18000e174`

## string_xrefs

- `0x18000e25f`: `Failed to open binding`

## pseudocode

```c
__int64 WinStationIsSessionPermitted()
{
  DWORD Pointer; // ebx
  CPublicBinding *v2; // rax
  CPublicBinding *v3; // rax
  void *v4; // rax
  CLIENT_CALL_RETURN v5; // rax
  unsigned __int16 v6[4]; // [rsp+28h] [rbp-20h] BYREF
  CPublicBinding *v7; // [rsp+30h] [rbp-18h]
  CLIENT_CALL_RETURN v8; // [rsp+50h] [rbp+8h] BYREF

  WaitForLsmStart();
  if ( GetSystemMetrics(4096) )
  {
    *(_QWORD *)v6 = 1;
    LODWORD(v8.Pointer) = 0;
    v2 = (CPublicBinding *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v2 )
      v3 = CPublicBinding::CPublicBinding(v2, 0, 0, (unsigned int *)&v8);
    else
      v3 = 0;
    v7 = v3;
    if ( v3 )
    {
      *(_DWORD *)&v6[2] = 1;
    }
    else
    {
      SetLastError(0xEu);
      _DbgPrintMessage(8, "new CPublicBinding");
    }
    if ( CSmartPublicBinding::operator void *(v6) )
    {
      v4 = CSmartPublicBinding::operator void *(v6);
      v8.Simple = 0;
      v5.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800351A0, 0, 0, v4).Pointer;
      Pointer = (DWORD)v5.Pointer;
      v8.Pointer = v5.Pointer;
      if ( LODWORD(v5.Pointer) == 1722 )
        Pointer = 0;
    }
    else
    {
      _DbgPrintMessage(8, "Failed to open binding");
      Pointer = GetLastError();
    }
    CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v6);
  }
  else
  {
    return 0;
  }
  return Pointer;
}

```

## disassembly

```asm
0x18000e160  mov     [rsp+arg_8], rbx
0x18000e165  push    rdi
0x18000e166  sub     rsp, 40h
0x18000e16a  call    ?WaitForLsmStart@@YAHXZ; WaitForLsmStart(void)
0x18000e16f  mov     ecx, 1000h; nIndex
0x18000e174  call    cs:__imp_GetSystemMetrics
0x18000e17b  nop     dword ptr [rax+rax+00h]
0x18000e180  xor     edi, edi
0x18000e182  test    eax, eax
0x18000e184  jnz     short loc_18000E196
0x18000e186  mov     ebx, edi
0x18000e188  mov     eax, ebx
0x18000e18a  mov     rbx, [rsp+48h+arg_8]
0x18000e18f  add     rsp, 40h
0x18000e193  pop     rdi
0x18000e194  retn
0x18000e196  mov     qword ptr [rsp+48h+var_20], 1
0x18000e19f  mov     dword ptr [rsp+48h+arg_0], edi
0x18000e1a3  mov     ebx, 1
0x18000e1a8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000e1af  lea     ecx, [rbx+3Fh]; unsigned __int64
0x18000e1b2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000e1b7  test    rax, rax
0x18000e1ba  jz      loc_18000E280
0x18000e1c0  lea     r9, [rsp+48h+arg_0]; unsigned int *
0x18000e1c5  xor     r8d, r8d; int
0x18000e1c8  xor     edx, edx; unsigned __int16 *
0x18000e1ca  mov     rcx, rax; this
0x18000e1cd  call    ??0CPublicBinding@@QEAA@PEBGHPEAK@Z; CPublicBinding::CPublicBinding(ushort const *,int,ulong *)
0x18000e1d2  mov     [rsp+48h+var_18], rax
0x18000e1d7  test    rax, rax
0x18000e1da  jz      loc_18000E288
0x18000e1e0  mov     dword ptr [rsp+48h+var_20+4], ebx
0x18000e1e4  lea     rcx, [rsp+48h+var_20]; unsigned __int16 *
0x18000e1e9  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18000e1ee  test    rax, rax
0x18000e1f1  jz      short loc_18000E25F
0x18000e1f3  lea     rcx, [rsp+48h+var_20]; unsigned __int16 *
0x18000e1f8  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18000e1fd  mov     [rsp+48h+arg_0], rdi
0x18000e202  mov     r9, rax
0x18000e205  xor     r8d, r8d; pReturnValue
0x18000e208  xor     edx, edx; nProcNum
0x18000e20a  lea     rcx, stru_1800351A0; pProxyInfo
0x18000e211  call    cs:__imp_NdrClientCall3
0x18000e218  nop     dword ptr [rax+rax+00h]
0x18000e21d  mov     rbx, rax
0x18000e220  mov     [rsp+48h+arg_0], rax
0x18000e225  mov     [rsp+48h+var_28], eax
0x18000e229  jmp     short loc_18000E247
0x18000e22b  mov     ebx, eax
0x18000e22d  mov     [rsp+48h+var_28], eax
0x18000e231  mov     r8d, eax
0x18000e234  lea     rdx, aRpcissessionpe; "RpcIsSessionPermitted threw an exceptio"...
0x18000e23b  mov     ecx, 8; int
0x18000e240  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000e245  xor     edi, edi
0x18000e247  cmp     ebx, 6BAh
0x18000e24d  cmovz   ebx, edi
0x18000e250  lea     rcx, [rsp+48h+var_20]; this
0x18000e255  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18000e25a  jmp     loc_18000E188
0x18000e25f  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x18000e266  mov     ecx, 8; int
0x18000e26b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000e270  call    cs:__imp_GetLastError
0x18000e277  nop     dword ptr [rax+rax+00h]
0x18000e27c  mov     ebx, eax
0x18000e27e  jmp     short loc_18000E250
0x18000e280  mov     rax, rdi
0x18000e283  jmp     loc_18000E1D2
0x18000e288  mov     ecx, 0Eh; dwErrCode
0x18000e28d  call    cs:__imp_SetLastError
0x18000e294  nop     dword ptr [rax+rax+00h]
0x18000e299  lea     rdx, aNewCpublicbind; "new CPublicBinding"
0x18000e2a0  mov     ecx, 8; int
0x18000e2a5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000e2aa  jmp     loc_18000E1E4
0x180033410  push    rbp
0x180033412  sub     rsp, 20h
0x180033416  mov     rbp, rdx
0x180033419  mov     rcx, [rcx]
0x18003341c  mov     ecx, [rcx]; ExceptionCode
0x18003341e  call    cs:__imp_I_RpcExceptionFilter
0x180033425  nop     dword ptr [rax+rax+00h]
0x18003342a  nop
0x18003342b  add     rsp, 20h
0x18003342f  pop     rbp
0x180033430  retn
```
