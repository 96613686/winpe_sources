# Legacy_WinStationGetProcessSid(void *,ulong,_FILETIME,uchar *,ulong *)

- ea: `0x18002c96c`
- end: `0x18002ca6a`
- name: `?Legacy_WinStationGetProcessSid@@YAEPEAXKU_FILETIME@@PEAEPEAK@Z`
- size: `254`
- prototype: `unsigned __int8 __usercall@<al>(CPublicBinding *this@<rcx>, unsigned int@<edx>, struct _FILETIME@<r8>, unsigned __int8 *@<r9>, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800103a0`

## callees

- `0x180007890`
- `0x18002c96c`
- `0x18002d754`
- `0x18002eabc`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18002ca26`
- `ntdll!RtlNtStatusToDosError` at `0x18002ca26`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c998`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ca2e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ca3a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c998`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ca2e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ca3a`
- `RPCRT4!NdrClientCall3` at `0x18002ca09`
- `RPCRT4!NdrClientCall3` at `0x18002ca09`

## pseudocode

```c
char __fastcall Legacy_WinStationGetProcessSid(
        unsigned __int16 **this,
        int a2,
        struct _FILETIME a3,
        unsigned __int8 *a4,
        unsigned int *a5)
{
  const unsigned __int16 *v10; // rdx
  unsigned int *v11; // rdi
  unsigned int v12; // esi
  unsigned __int16 *LegacyBinding; // rax
  CLIENT_CALL_RETURN v14; // rax
  char Pointer; // bl
  ULONG v16; // eax
  unsigned __int16 **Simple; // [rsp+58h] [rbp-40h] BYREF
  NTSTATUS Status; // [rsp+A0h] [rbp+8h] BYREF

  Status = 0;
  if ( !this )
  {
    SetLastError(0x57u);
    return 0;
  }
  Simple = this;
  if ( !CSmartWinStation::Open(&Simple) )
    return 0;
  v11 = a5;
  v12 = *a5;
  LegacyBinding = CPublicBinding::GetLegacyBinding(this, v10);
  Simple = 0;
  v14.Pointer = NdrClientCall3(
                  (MIDL_STUBLESS_PROXY_INFO *)&stru_18003A150,
                  0x2Cu,
                  0,
                  LegacyBinding,
                  a2,
                  a3,
                  &Status,
                  a4,
                  v12,
                  v11).Pointer;
  Pointer = (char)v14.Pointer;
  Simple = (unsigned __int16 **)v14.Simple;
  if ( !LOBYTE(v14.Pointer) )
  {
    v16 = RtlNtStatusToDosError(Status);
    SetLastError(v16);
  }
  return Pointer;
}

```

## disassembly

```asm
0x18002c96c  mov     rax, rsp
0x18002c96f  push    rbx
0x18002c970  push    rsi
0x18002c971  push    rdi
0x18002c972  push    r12
0x18002c974  push    r14
0x18002c976  push    r15
0x18002c978  sub     rsp, 68h
0x18002c97c  mov     r15, r9
0x18002c97f  mov     rbx, r8
0x18002c982  mov     r12d, edx
0x18002c985  mov     r14, rcx
0x18002c988  mov     dword ptr [rax+8], 0
0x18002c98f  test    rcx, rcx
0x18002c992  jnz     short loc_18002C9A5
0x18002c994  lea     ecx, [r14+57h]; dwErrCode
0x18002c998  call    cs:__imp_SetLastError
0x18002c99e  xor     al, al
0x18002c9a0  jmp     loc_18002CA5C
0x18002c9a5  mov     [rsp+98h+var_40], r14
0x18002c9aa  lea     rcx, [rsp+98h+var_40]; this
0x18002c9af  call    ?Open@CSmartWinStation@@QEAAHXZ; CSmartWinStation::Open(void)
0x18002c9b4  test    eax, eax
0x18002c9b6  jz      short loc_18002C99E
0x18002c9b8  mov     rdi, [rsp+98h+arg_20]
0x18002c9c0  mov     esi, [rdi]
0x18002c9c2  mov     rcx, r14; this
0x18002c9c5  call    ?GetLegacyBinding@CPublicBinding@@QEAAPEAXXZ; CPublicBinding::GetLegacyBinding(void)
0x18002c9ca  mov     [rsp+98h+var_40], 0
0x18002c9d3  mov     [rsp+98h+var_50], rdi
0x18002c9d8  mov     [rsp+98h+var_58], esi
0x18002c9dc  mov     [rsp+98h+var_60], r15
0x18002c9e1  lea     rcx, [rsp+98h+Status]
0x18002c9e9  mov     [rsp+98h+var_68], rcx
0x18002c9ee  mov     [rsp+98h+var_70], rbx
0x18002c9f3  mov     [rsp+98h+var_78], r12d
0x18002c9f8  mov     r9, rax
0x18002c9fb  xor     r8d, r8d; pReturnValue
0x18002c9fe  lea     edx, [r8+2Ch]; nProcNum
0x18002ca02  lea     rcx, stru_18003A150; pProxyInfo
0x18002ca09  call    cs:__imp_NdrClientCall3
0x18002ca0f  mov     rbx, rax
0x18002ca12  mov     [rsp+98h+var_40], rax
0x18002ca17  mov     [rsp+98h+var_48], al
0x18002ca1b  test    al, al
0x18002ca1d  jnz     short loc_18002CA34
0x18002ca1f  mov     ecx, [rsp+98h+Status]; Status
0x18002ca26  call    cs:__imp_RtlNtStatusToDosError
0x18002ca2c  mov     ecx, eax; dwErrCode
0x18002ca2e  call    cs:__imp_SetLastError
0x18002ca34  jmp     short loc_18002CA5A
0x18002ca36  mov     ebx, eax
0x18002ca38  mov     ecx, eax; dwErrCode
0x18002ca3a  call    cs:__imp_SetLastError
0x18002ca40  mov     r8d, ebx
0x18002ca43  lea     rdx, aRpcExceptionD; "RPC Exception %d"
0x18002ca4a  mov     ecx, 8; int
0x18002ca4f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002ca54  xor     bl, bl
0x18002ca56  mov     [rsp+98h+var_48], bl
0x18002ca5a  mov     al, bl
0x18002ca5c  add     rsp, 68h
0x18002ca60  pop     r15
0x18002ca62  pop     r14
0x18002ca64  pop     r12
0x18002ca66  pop     rdi
0x18002ca67  pop     rsi
0x18002ca68  pop     rbx
0x18002ca69  retn
0x1800308b7  push    rbp
0x1800308b9  sub     rsp, 50h
0x1800308bd  mov     rbp, rdx
0x1800308c0  mov     rcx, [rcx]
0x1800308c3  mov     ecx, [rcx]; ExceptionCode
0x1800308c5  call    cs:__imp_I_RpcExceptionFilter
0x1800308cb  nop
0x1800308cc  add     rsp, 50h
0x1800308d0  pop     rbp
0x1800308d1  retn
```
