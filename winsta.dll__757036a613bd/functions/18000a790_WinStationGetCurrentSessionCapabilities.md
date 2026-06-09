# WinStationGetCurrentSessionCapabilities

- ea: `0x18000a790`
- end: `0x18000aa18`
- name: `WinStationGetCurrentSessionCapabilities`
- size: `648`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `service_task`

## callees

- `0x180005374`
- `0x180005fcc`
- `0x180007890`
- `0x180008290`
- `0x180008340`
- `0x180008e30`
- `0x180009d10`
- `0x18000a790`
- `0x1800230b8`
- `0x1800230ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a93d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a9a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a9fc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a93d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a9a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a9fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a9b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a9b1`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800304c4`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800304c4`
- `RPCRT4!NdrClientCall3` at `0x18000a8da`
- `RPCRT4!NdrClientCall3` at `0x18000a8da`

## string_xrefs

- `0x18000a950`: `StringCchCopy failed: %x`

## pseudocode

```c
char __fastcall WinStationGetCurrentSessionCapabilities(int a1, _DWORD *a2)
{
  char v4; // di
  _QWORD *v5; // rax
  _QWORD *v6; // rbx
  _WORD *v7; // rcx
  __int64 v8; // rax
  int *v9; // r8
  __int64 v10; // rdx
  __int16 v11; // r9
  int v12; // r14d
  _WORD *v13; // rax
  void *v14; // rax
  int Pointer; // ebx
  DWORD v17; // ecx
  DWORD v18; // eax
  signed int LastError; // eax
  unsigned __int16 v20[4]; // [rsp+38h] [rbp-40h] BYREF
  _QWORD *v21; // [rsp+40h] [rbp-38h]

  v4 = 0;
  *a2 = 0;
  if ( !TestServiceStarted() )
  {
    v17 = 1352;
LABEL_22:
    SetLastError(v17);
    return v4;
  }
  if ( a1 != 1 )
  {
    v17 = 87;
    goto LABEL_22;
  }
  *(_QWORD *)v20 = 0;
  v5 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v6 = v5;
  if ( v5 )
  {
    *v5 = 0;
    v5[1] = 0;
    v5[2] = 0;
    v5[3] = 0;
    v5[4] = 0;
    v5[5] = 0;
    v5[6] = 1;
    v5[7] = 0;
    v7 = operator new[](2u, (const struct std::nothrow_t *)&std::nothrow);
    v6[5] = v7;
    if ( v7 )
    {
      v8 = 2147483646;
      v9 = &dword_18003D0CC;
      v10 = 1;
      do
      {
        if ( !v8 )
          break;
        v11 = *(_WORD *)v9;
        if ( !*(_WORD *)v9 )
          break;
        v9 = (int *)((char *)v9 + 2);
        *v7++ = v11;
        --v8;
        --v10;
      }
      while ( v10 );
      v12 = v10 == 0 ? 0x8007007A : 0;
      v13 = v7 - 1;
      if ( v10 )
        v13 = v7;
      *v13 = 0;
      if ( v10 )
      {
        if ( !v6[3] && !*((_DWORD *)v6 + 12) )
        {
          if ( (unsigned int)CPublicBinding::OpenSessionContextHandle((RPC_BINDING_HANDLE *)v6) == -2147023174 )
            *((_DWORD *)v6 + 13) = 1;
          CPublicBinding::CloseSessionContextHandle((CPublicBinding *)v6);
        }
      }
      else
      {
        ConvertHRESULT2WIN32(v12);
        _DbgPrintMessage(8, "StringCchCopy failed: %x", v12);
      }
    }
  }
  else
  {
    v6 = 0;
  }
  v21 = v6;
  if ( v6 )
  {
    *(_DWORD *)&v20[2] = 1;
  }
  else
  {
    SetLastError(0xEu);
    _DbgPrintMessage(8, "new CPublicBinding");
  }
  if ( CSmartPublicBinding::operator void *(v20) )
  {
    v14 = CSmartPublicBinding::operator void *(v20);
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180032230, 3u, 0, v14, 1, a2).Pointer;
    if ( Pointer < 0 )
    {
      _DbgPrintMessage(
        8,
        "RpcGetCurrentSessionCapabilities failed: 0x%x in %s",
        Pointer,
        "WinStationGetCurrentSessionCapabilities");
      v18 = ConvertHRESULT2WIN32(Pointer);
      SetLastError(v18);
    }
    else
    {
      v4 = 1;
    }
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    _DbgPrintMessage(8, "Can't bind to local LSM, error code 0x%08x", LastError);
  }
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v20);
  return v4;
}

```

## disassembly

```asm
0x18000a790  push    rbx
0x18000a792  push    rdi
0x18000a793  push    r14
0x18000a795  push    r15
0x18000a797  sub     rsp, 58h
0x18000a79b  mov     r15, rdx
0x18000a79e  mov     ebx, ecx
0x18000a7a0  xor     edi, edi
0x18000a7a2  mov     [rdx], edi
0x18000a7a4  call    ?TestServiceStarted@@YAHK@Z; TestServiceStarted(ulong)
0x18000a7a9  test    eax, eax
0x18000a7ab  jz      loc_18000A938
0x18000a7b1  cmp     ebx, 1
0x18000a7b4  jnz     loc_18000A9DC
0x18000a7ba  mov     qword ptr [rsp+78h+var_40], rdi
0x18000a7bf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a7c6  lea     ecx, [rdi+40h]; unsigned __int64
0x18000a7c9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000a7ce  mov     rbx, rax
0x18000a7d1  test    rax, rax
0x18000a7d4  jz      loc_18000A9EF
0x18000a7da  mov     [rax], rdi
0x18000a7dd  mov     [rax+8], rdi
0x18000a7e1  mov     [rax+10h], rdi
0x18000a7e5  mov     [rax+18h], rdi
0x18000a7e9  mov     [rax+20h], rdi
0x18000a7ed  mov     [rax+28h], rdi
0x18000a7f1  mov     qword ptr [rax+30h], 1
0x18000a7f9  mov     [rax+38h], rdi
0x18000a7fd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a804  lea     ecx, [rdi+2]; unsigned __int64
0x18000a807  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000a80c  mov     rcx, rax
0x18000a80f  mov     [rbx+28h], rax
0x18000a813  test    rax, rax
0x18000a816  jz      short loc_18000A881
0x18000a818  mov     eax, 7FFFFFFEh
0x18000a81d  lea     r8, dword_18003D0CC
0x18000a824  lea     edx, [rdi+1]
0x18000a827  test    rax, rax
0x18000a82a  jz      short loc_18000A84B
0x18000a82c  movzx   r9d, word ptr [r8]
0x18000a830  test    r9w, r9w
0x18000a834  jz      short loc_18000A84B
0x18000a836  add     r8, 2
0x18000a83a  mov     [rcx], r9w
0x18000a83e  add     rcx, 2
0x18000a842  dec     rax
0x18000a845  sub     rdx, 1
0x18000a849  jnz     short loc_18000A827
0x18000a84b  mov     rax, rdx
0x18000a84e  neg     rax
0x18000a851  sbb     r14d, r14d
0x18000a854  not     r14d
0x18000a857  and     r14d, 8007007Ah
0x18000a85e  lea     rax, [rcx-2]
0x18000a862  test    rdx, rdx
0x18000a865  cmovnz  rax, rcx
0x18000a869  mov     [rax], di
0x18000a86c  jz      loc_18000A945
0x18000a872  cmp     [rbx+18h], rdi
0x18000a876  jnz     short loc_18000A881
0x18000a878  cmp     [rbx+30h], edi
0x18000a87b  jz      loc_18000A966
0x18000a881  mov     [rsp+78h+var_38], rbx
0x18000a886  test    rbx, rbx
0x18000a889  jz      loc_18000A9F7
0x18000a88f  mov     dword ptr [rsp+78h+var_40+4], 1
0x18000a897  lea     rcx, [rsp+78h+var_40]; unsigned __int16 *
0x18000a89c  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18000a8a1  test    rax, rax
0x18000a8a4  jz      loc_18000A9B1
0x18000a8aa  lea     rcx, [rsp+78h+var_40]; unsigned __int16 *
0x18000a8af  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18000a8b4  mov     [rsp+78h+arg_8], rdi
0x18000a8bc  mov     [rsp+78h+var_50], r15
0x18000a8c1  mov     [rsp+78h+var_58], 1
0x18000a8c9  mov     r9, rax
0x18000a8cc  xor     r8d, r8d; pReturnValue
0x18000a8cf  lea     edx, [r8+3]; nProcNum
0x18000a8d3  lea     rcx, stru_180032230; pProxyInfo
0x18000a8da  call    cs:__imp_NdrClientCall3
0x18000a8e0  mov     rbx, rax
0x18000a8e3  mov     [rsp+78h+arg_8], rax
0x18000a8eb  mov     [rsp+78h+var_48], eax
0x18000a8ef  jmp     short loc_18000A919
0x18000a8f1  test    eax, eax
0x18000a8f3  jle     short loc_18000A8FD
0x18000a8f5  movzx   eax, ax
0x18000a8f8  or      eax, 80070000h
0x18000a8fd  mov     ebx, eax
0x18000a8ff  mov     [rsp+78h+var_48], eax
0x18000a903  mov     r8d, eax
0x18000a906  lea     rdx, aRpcgetcurrents_11; "RpcGetCurrentSessionCapabilities threw "...
0x18000a90d  mov     ecx, 8; int
0x18000a912  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000a917  xor     edi, edi
0x18000a919  test    ebx, ebx
0x18000a91b  js      short loc_18000A982
0x18000a91d  mov     dil, 1
0x18000a920  lea     rcx, [rsp+78h+var_40]; this
0x18000a925  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18000a92a  mov     al, dil
0x18000a92d  add     rsp, 58h
0x18000a931  pop     r15
0x18000a933  pop     r14
0x18000a935  pop     rdi
0x18000a936  pop     rbx
0x18000a937  retn
0x18000a938  mov     ecx, 548h; dwErrCode
0x18000a93d  call    cs:__imp_SetLastError
0x18000a943  jmp     short loc_18000A92A
0x18000a945  mov     ecx, r14d; int
0x18000a948  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18000a94d  mov     r8d, r14d
0x18000a950  lea     rdx, aStringcchcopyF; "StringCchCopy failed: %x"
0x18000a957  mov     ecx, 8; int
0x18000a95c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000a961  jmp     loc_18000A881
0x18000a966  mov     rcx, rbx; this
0x18000a969  call    ?OpenSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::OpenSessionContextHandle(void)
0x18000a96e  cmp     eax, 800706BAh
0x18000a973  jz      short loc_18000A9E6
0x18000a975  mov     rcx, rbx; this
0x18000a978  call    ?CloseSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::CloseSessionContextHandle(void)
0x18000a97d  jmp     loc_18000A881
0x18000a982  lea     r9, aWinstationgetc_4; "WinStationGetCurrentSessionCapabilities"
0x18000a989  mov     r8d, ebx
0x18000a98c  lea     rdx, aRpcgetcurrents_7; "RpcGetCurrentSessionCapabilities failed"...
0x18000a993  mov     ecx, 8; int
0x18000a998  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000a99d  mov     ecx, ebx; int
0x18000a99f  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18000a9a4  mov     ecx, eax; dwErrCode
0x18000a9a6  call    cs:__imp_SetLastError
0x18000a9ac  jmp     loc_18000A920
0x18000a9b1  call    cs:__imp_GetLastError
0x18000a9b7  test    eax, eax
0x18000a9b9  jle     short loc_18000A9C3
0x18000a9bb  movzx   eax, ax
0x18000a9be  or      eax, 80070000h
0x18000a9c3  mov     r8d, eax
0x18000a9c6  lea     rdx, aCanTBindToLoca; "Can't bind to local LSM, error code 0x%"...
0x18000a9cd  mov     ecx, 8; int
0x18000a9d2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000a9d7  jmp     loc_18000A920
0x18000a9dc  mov     ecx, 57h ; 'W'
0x18000a9e1  jmp     loc_18000A93D
0x18000a9e6  mov     dword ptr [rbx+34h], 1
0x18000a9ed  jmp     short loc_18000A975
0x18000a9ef  mov     rbx, rdi
0x18000a9f2  jmp     loc_18000A881
0x18000a9f7  mov     ecx, 0Eh; dwErrCode
0x18000a9fc  call    cs:__imp_SetLastError
0x18000aa02  lea     rdx, aNewCpublicbind; "new CPublicBinding"
0x18000aa09  mov     ecx, 8; int
0x18000aa0e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000aa13  jmp     loc_18000A897
0x1800304b6  push    rbp
0x1800304b8  sub     rsp, 30h
0x1800304bc  mov     rbp, rdx
0x1800304bf  mov     rcx, [rcx]
0x1800304c2  mov     ecx, [rcx]; ExceptionCode
0x1800304c4  call    cs:__imp_I_RpcExceptionFilter
0x1800304ca  nop
0x1800304cb  add     rsp, 30h
0x1800304cf  pop     rbp
0x1800304d0  retn
```
