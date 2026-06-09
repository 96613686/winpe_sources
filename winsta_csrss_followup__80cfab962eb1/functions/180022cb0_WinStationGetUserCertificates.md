# WinStationGetUserCertificates

- ea: `0x180022cb0`
- end: `0x180022ee6`
- name: `WinStationGetUserCertificates`
- size: `566`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task`

## callees

- `0x1800041a0`
- `0x180004558`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`
- `0x180022cb0`
- `0x180025cc6`
- `0x180029960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022ec1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022ec1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022d0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022d0a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022e0d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022e31`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022e0d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022e31`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022e94`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022e94`
- `RPCRT4!NdrClientCall3` at `0x180022d8c`
- `RPCRT4!NdrClientCall3` at `0x180022d8c`

## string_xrefs

- `0x180022dbb`: `RpcRevertFromServicesSession threw an exception: 0x%x`

## pseudocode

```c
bool __fastcall WinStationGetUserCertificates(HLOCAL *a1)
{
  signed int Pointer; // ebx
  signed int LastError; // eax
  ULONG SessionId; // ebx
  void *v5; // rax
  HLOCAL v6; // rax
  void *v7; // rcx
  bool v8; // sf
  DWORD v9; // eax
  bool v10; // bl
  unsigned __int16 v12[20]; // [rsp+50h] [rbp-28h] BYREF
  SIZE_T uBytes; // [rsp+88h] [rbp+10h] BYREF
  int v14; // [rsp+90h] [rbp+18h] BYREF
  void *Src; // [rsp+98h] [rbp+20h] BYREF

  Src = 0;
  LODWORD(uBytes) = 0;
  v14 = 0;
  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v12, 0, 1);
  if ( a1 )
  {
    *a1 = 0;
    if ( CSmartPublicBinding::operator void *(v12) )
    {
      SessionId = NtCurrentPeb()->SessionId;
      v5 = CSmartPublicBinding::operator void *(v12);
      Pointer = (unsigned int)NdrClientCall3(
                                (MIDL_STUBLESS_PROXY_INFO *)&stru_180035078,
                                0xAu,
                                0,
                                v5,
                                SessionId,
                                &v14,
                                &Src,
                                &uBytes).Pointer;
      if ( Pointer >= 0 )
      {
        if ( v14 && Src && (_DWORD)uBytes )
        {
          v6 = LocalAlloc(0x40u, 0x10u);
          *a1 = v6;
          if ( v6
            && (*((_QWORD *)*a1 + 1) = LocalAlloc(0x40u, (unsigned int)uBytes), (v7 = (void *)*((_QWORD *)*a1 + 1)) != 0) )
          {
            memcpy_0(v7, Src, (unsigned int)uBytes);
            *(_DWORD *)*a1 = v14;
            *((_DWORD *)*a1 + 1) = uBytes;
            Pointer = 0;
          }
          else
          {
            Pointer = -2147024882;
          }
        }
        else
        {
          Pointer = -2147023728;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      Pointer = LastError;
      if ( LastError > 0 )
        Pointer = (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    Pointer = -2147024809;
  }
  if ( Src )
    LocalFree(Src);
  v8 = Pointer < 0;
  if ( Pointer < 0 )
  {
    if ( a1 )
    {
      WinStationFreeUserCertificates(*a1);
      *a1 = 0;
    }
    v9 = ConvertHRESULT2WIN32(Pointer);
    SetLastError(v9);
    v8 = Pointer < 0;
  }
  v10 = !v8;
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v12);
  return v10;
}

```

## disassembly

```asm
0x180022cb0  mov     rax, rsp
0x180022cb3  mov     [rax+8], rcx
0x180022cb7  push    rbx
0x180022cb8  push    rsi
0x180022cb9  sub     rsp, 68h
0x180022cbd  mov     rsi, rcx
0x180022cc0  mov     qword ptr [rax+20h], 0
0x180022cc8  mov     dword ptr [rax+10h], 0
0x180022ccf  mov     dword ptr [rax+18h], 0
0x180022cd6  xor     edx, edx; void *
0x180022cd8  lea     r8d, [rdx+1]; int
0x180022cdc  lea     rcx, [rax-28h]; this
0x180022ce0  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x180022ce5  test    rsi, rsi
0x180022ce8  jnz     short loc_180022CF4
0x180022cea  mov     ebx, 80070057h
0x180022cef  jmp     loc_180022E87
0x180022cf4  mov     qword ptr [rsi], 0
0x180022cfb  lea     rcx, [rsp+78h+var_28]; unsigned __int16 *
0x180022d00  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180022d05  test    rax, rax
0x180022d08  jnz     short loc_180022D2E
0x180022d0a  call    cs:__imp_GetLastError
0x180022d11  nop     dword ptr [rax+rax+00h]
0x180022d16  mov     ebx, eax
0x180022d18  test    eax, eax
0x180022d1a  jle     loc_180022E87
0x180022d20  movzx   ebx, ax
0x180022d23  or      ebx, 80070000h
0x180022d29  jmp     loc_180022E87
0x180022d2e  mov     rax, gs:60h
0x180022d37  mov     ebx, [rax+2C0h]
0x180022d3d  lea     rcx, [rsp+78h+var_28]; unsigned __int16 *
0x180022d42  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180022d47  mov     [rsp+78h+var_30], 0
0x180022d50  lea     rcx, [rsp+78h+uBytes]
0x180022d58  mov     [rsp+78h+var_40], rcx
0x180022d5d  lea     rcx, [rsp+78h+Src]
0x180022d65  mov     [rsp+78h+var_48], rcx
0x180022d6a  lea     rcx, [rsp+78h+arg_10]
0x180022d72  mov     [rsp+78h+var_50], rcx
0x180022d77  mov     [rsp+78h+var_58], ebx
0x180022d7b  mov     r9, rax
0x180022d7e  xor     r8d, r8d; pReturnValue
0x180022d81  lea     edx, [r8+0Ah]; nProcNum
0x180022d85  lea     rcx, stru_180035078; pProxyInfo
0x180022d8c  call    cs:__imp_NdrClientCall3
0x180022d93  nop     dword ptr [rax+rax+00h]
0x180022d98  mov     rbx, rax
0x180022d9b  mov     [rsp+78h+var_30], rax
0x180022da0  mov     [rsp+78h+var_38], eax
0x180022da4  jmp     short loc_180022DD4
0x180022da6  test    eax, eax
0x180022da8  jle     short loc_180022DB2
0x180022daa  movzx   eax, ax
0x180022dad  or      eax, 80070000h
0x180022db2  mov     ebx, eax
0x180022db4  mov     [rsp+78h+var_38], eax
0x180022db8  mov     r8d, eax
0x180022dbb  lea     rdx, aRpcrevertfroms; "RpcRevertFromServicesSession threw an e"...
0x180022dc2  mov     ecx, 8; int
0x180022dc7  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180022dcc  mov     rsi, [rsp+78h+arg_0]
0x180022dd4  test    ebx, ebx
0x180022dd6  js      loc_180022E87
0x180022ddc  cmp     [rsp+78h+arg_10], 0
0x180022de4  jz      loc_180022E82
0x180022dea  cmp     [rsp+78h+Src], 0
0x180022df3  jz      loc_180022E82
0x180022df9  cmp     dword ptr [rsp+78h+uBytes], 0
0x180022e01  jz      short loc_180022E82
0x180022e03  mov     edx, 10h; uBytes
0x180022e08  lea     ebx, [rdx+30h]
0x180022e0b  mov     ecx, ebx; uFlags
0x180022e0d  call    cs:__imp_LocalAlloc
0x180022e14  nop     dword ptr [rax+rax+00h]
0x180022e19  mov     [rsi], rax
0x180022e1c  test    rax, rax
0x180022e1f  jnz     short loc_180022E28
0x180022e21  mov     ebx, 8007000Eh
0x180022e26  jmp     short loc_180022E87
0x180022e28  mov     edx, dword ptr [rsp+78h+uBytes]; uBytes
0x180022e2f  mov     ecx, ebx; uFlags
0x180022e31  call    cs:__imp_LocalAlloc
0x180022e38  nop     dword ptr [rax+rax+00h]
0x180022e3d  mov     rcx, [rsi]
0x180022e40  mov     [rcx+8], rax
0x180022e44  mov     rax, [rsi]
0x180022e47  mov     rcx, [rax+8]; void *
0x180022e4b  test    rcx, rcx
0x180022e4e  jz      short loc_180022E21
0x180022e50  mov     r8d, dword ptr [rsp+78h+uBytes]; Size
0x180022e58  mov     rdx, [rsp+78h+Src]; Src
0x180022e60  call    memcpy_0
0x180022e65  mov     rcx, [rsi]
0x180022e68  mov     eax, [rsp+78h+arg_10]
0x180022e6f  mov     [rcx], eax
0x180022e71  mov     rcx, [rsi]
0x180022e74  mov     eax, dword ptr [rsp+78h+uBytes]
0x180022e7b  mov     [rcx+4], eax
0x180022e7e  xor     ebx, ebx
0x180022e80  jmp     short loc_180022E87
0x180022e82  mov     ebx, 80070490h
0x180022e87  mov     rcx, [rsp+78h+Src]; hMem
0x180022e8f  test    rcx, rcx
0x180022e92  jz      short loc_180022EA0
0x180022e94  call    cs:__imp_LocalFree
0x180022e9b  nop     dword ptr [rax+rax+00h]
0x180022ea0  test    ebx, ebx
0x180022ea2  jns     short loc_180022ECF
0x180022ea4  test    rsi, rsi
0x180022ea7  jz      short loc_180022EB8
0x180022ea9  mov     rcx, [rsi]; hMem
0x180022eac  call    WinStationFreeUserCertificates
0x180022eb1  mov     qword ptr [rsi], 0
0x180022eb8  mov     ecx, ebx; int
0x180022eba  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180022ebf  mov     ecx, eax; dwErrCode
0x180022ec1  call    cs:__imp_SetLastError
0x180022ec8  nop     dword ptr [rax+rax+00h]
0x180022ecd  test    ebx, ebx
0x180022ecf  setns   bl
0x180022ed2  lea     rcx, [rsp+78h+var_28]; this
0x180022ed7  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180022edc  mov     al, bl
0x180022ede  add     rsp, 68h
0x180022ee2  pop     rsi
0x180022ee3  pop     rbx
0x180022ee4  retn
0x18003377f  push    rbp
0x180033781  sub     rsp, 40h
0x180033785  mov     rbp, rdx
0x180033788  mov     rcx, [rcx]
0x18003378b  mov     ecx, [rcx]; ExceptionCode
0x18003378d  call    cs:__imp_I_RpcExceptionFilter
0x180033794  nop     dword ptr [rax+rax+00h]
0x180033799  nop
0x18003379a  add     rsp, 40h
0x18003379e  pop     rbp
0x18003379f  retn
```
