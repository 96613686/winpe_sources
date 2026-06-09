# GetCallerToken(ushort const *,void * *)

- ea: `0x180039d30`
- end: `0x180039e17`
- name: `?GetCallerToken@@YAJPEBGPEAPEAX@Z`
- size: `231`
- prototype: `__int64 __fastcall(const unsigned __int16 *, PHANDLE TokenHandle)`
- caller_count: `9`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18004c6d0`
- `0x18004d620`
- `0x18004d868`
- `0x1800755e8`
- `0x1800758e4`
- `0x180075f84`
- `0x1800763cc`
- `0x1800769dc`
- `0x180076dcc`

## callees

- `0x180039b6c`
- `0x180039d30`
- `0x18005790c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039d8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039d8e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180039d53`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180039d53`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180039d6a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180039d6a`
- `RPCRT4!RpcImpersonateClient` at `0x180039d47`
- `RPCRT4!RpcImpersonateClient` at `0x180039d47`
- `RPCRT4!RpcRevertToSelf` at `0x180039d74`
- `RPCRT4!RpcRevertToSelf` at `0x180039da3`
- `RPCRT4!RpcRevertToSelf` at `0x180039d74`
- `RPCRT4!RpcRevertToSelf` at `0x180039da3`

## pseudocode

```c
__int64 __fastcall GetCallerToken(const unsigned __int16 *a1, PHANDLE TokenHandle)
{
  RPC_STATUS v4; // eax
  EventManager *v5; // rcx
  RPC_STATUS v6; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  unsigned int v10; // ebx
  void *v11; // [rsp+20h] [rbp-58h]
  const struct _GUID *v12; // [rsp+28h] [rbp-50h]
  void **pExceptionObject; // [rsp+30h] [rbp-48h] BYREF
  char v14; // [rsp+38h] [rbp-40h]
  const unsigned __int16 *v15; // [rsp+40h] [rbp-38h]
  __int64 v16; // [rsp+48h] [rbp-30h]
  __int64 v17; // [rsp+50h] [rbp-28h]
  RPC_STATUS v18; // [rsp+58h] [rbp-20h]
  __int64 v19; // [rsp+5Ch] [rbp-1Ch]

  v4 = RpcImpersonateClient(0);
  v6 = v4;
  if ( v4 )
  {
    EventManager::EvtReport(v5, &IMPERSONATION_FAILURE, a1, v4, v11, v12);
    v14 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v18 = v6;
    v15 = &qword_1800A4718;
    v19 = -1;
    v16 = 0;
    v17 = 0;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, TokenHandle) )
  {
    RpcRevertToSelf();
    return 0;
  }
  else
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    RpcRevertToSelf();
    return v10;
  }
}

```

## disassembly

```asm
0x180039d30  mov     [rsp+arg_0], rbx
0x180039d35  mov     [rsp+arg_8], rsi
0x180039d3a  push    rdi
0x180039d3b  sub     rsp, 70h
0x180039d3f  mov     rsi, rcx
0x180039d42  mov     rdi, rdx
0x180039d45  xor     ecx, ecx; BindingHandle
0x180039d47  call    cs:__imp_RpcImpersonateClient
0x180039d4d  mov     ebx, eax
0x180039d4f  test    eax, eax
0x180039d51  jnz     short loc_180039DBD
0x180039d53  call    cs:__imp_GetCurrentThread
0x180039d59  mov     r9, rdi; TokenHandle
0x180039d5c  mov     edx, 8; DesiredAccess
0x180039d61  mov     rcx, rax; ThreadHandle
0x180039d64  mov     r8d, 1; OpenAsSelf
0x180039d6a  call    cs:__imp_OpenThreadToken
0x180039d70  test    eax, eax
0x180039d72  jz      short loc_180039D8E
0x180039d74  call    cs:__imp_RpcRevertToSelf
0x180039d7a  xor     eax, eax
0x180039d7c  lea     r11, [rsp+78h+var_8]
0x180039d81  mov     rbx, [r11+10h]
0x180039d85  mov     rsi, [r11+18h]
0x180039d89  mov     rsp, r11
0x180039d8c  pop     rdi
0x180039d8d  retn
0x180039d8e  call    cs:__imp_GetLastError
0x180039d94  mov     ebx, eax
0x180039d96  test    eax, eax
0x180039d98  jle     short loc_180039DA3
0x180039d9a  movzx   ebx, ax
0x180039d9d  or      ebx, 80070000h
0x180039da3  call    cs:__imp_RpcRevertToSelf
0x180039da9  lea     r11, [rsp+78h+var_8]
0x180039dae  mov     eax, ebx
0x180039db0  mov     rbx, [r11+10h]
0x180039db4  mov     rsi, [r11+18h]
0x180039db8  mov     rsp, r11
0x180039dbb  pop     rdi
0x180039dbc  retn
0x180039dbd  mov     r9d, ebx; unsigned int
0x180039dc0  lea     rdx, IMPERSONATION_FAILURE; struct _EVENT_DESCRIPTOR *
0x180039dc7  mov     r8, rsi; unsigned __int16 *
0x180039dca  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,void *,_GUID const *)
0x180039dcf  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180039dd6  mov     [rsp+78h+var_40], 0
0x180039ddb  mov     [rsp+78h+pExceptionObject], rax
0x180039de0  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180039de7  lea     rax, qword_1800A4718
0x180039dee  mov     [rsp+78h+var_20], ebx
0x180039df2  mov     [rsp+78h+var_38], rax
0x180039df7  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180039dfc  xor     eax, eax
0x180039dfe  mov     [rsp+78h+var_1C], 0FFFFFFFFFFFFFFFFh
0x180039e07  mov     [rsp+78h+var_30], rax
0x180039e0c  mov     [rsp+78h+var_28], rax
0x180039e11  call    _CxxThrowException_0
```
