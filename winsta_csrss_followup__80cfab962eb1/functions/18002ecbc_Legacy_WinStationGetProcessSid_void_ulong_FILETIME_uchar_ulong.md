# Legacy_WinStationGetProcessSid(void *,ulong,_FILETIME,uchar *,ulong *)

- ea: `0x18002ecbc`
- end: `0x18002edd9`
- name: `?Legacy_WinStationGetProcessSid@@YAEPEAXKU_FILETIME@@PEAEPEAK@Z`
- size: `285`
- prototype: `unsigned __int8 __usercall@<al>(CPublicBinding *this@<rcx>, unsigned int@<edx>, struct _FILETIME@<r8>, unsigned __int8 *@<r9>, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800112a0`

## callees

- `0x180005b40`
- `0x18002ecbc`
- `0x18002fbf4`
- `0x18003154c`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18002ed82`
- `ntdll!RtlNtStatusToDosError` at `0x18002ed82`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ece8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ed90`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002eda2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ece8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ed90`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002eda2`
- `RPCRT4!NdrClientCall3` at `0x18002ed5f`
- `RPCRT4!NdrClientCall3` at `0x18002ed5f`

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
  DWORD v16; // eax
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
                  (MIDL_STUBLESS_PROXY_INFO *)&stru_18003D150,
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
0x18002ecbc  mov     rax, rsp
0x18002ecbf  push    rbx
0x18002ecc0  push    rsi
0x18002ecc1  push    rdi
0x18002ecc2  push    r12
0x18002ecc4  push    r14
0x18002ecc6  push    r15
0x18002ecc8  sub     rsp, 68h
0x18002eccc  mov     r15, r9
0x18002eccf  mov     rbx, r8
0x18002ecd2  mov     r12d, edx
0x18002ecd5  mov     r14, rcx
0x18002ecd8  mov     dword ptr [rax+8], 0
0x18002ecdf  test    rcx, rcx
0x18002ece2  jnz     short loc_18002ECFB
0x18002ece4  lea     ecx, [r14+57h]; dwErrCode
0x18002ece8  call    cs:__imp_SetLastError
0x18002ecef  nop     dword ptr [rax+rax+00h]
0x18002ecf4  xor     al, al
0x18002ecf6  jmp     loc_18002EDCA
0x18002ecfb  mov     [rsp+98h+var_40], r14
0x18002ed00  lea     rcx, [rsp+98h+var_40]; this
0x18002ed05  call    ?Open@CSmartWinStation@@QEAAHXZ; CSmartWinStation::Open(void)
0x18002ed0a  test    eax, eax
0x18002ed0c  jz      short loc_18002ECF4
0x18002ed0e  mov     rdi, [rsp+98h+arg_20]
0x18002ed16  mov     esi, [rdi]
0x18002ed18  mov     rcx, r14; this
0x18002ed1b  call    ?GetLegacyBinding@CPublicBinding@@QEAAPEAXXZ; CPublicBinding::GetLegacyBinding(void)
0x18002ed20  mov     [rsp+98h+var_40], 0
0x18002ed29  mov     [rsp+98h+var_50], rdi
0x18002ed2e  mov     [rsp+98h+var_58], esi
0x18002ed32  mov     [rsp+98h+var_60], r15
0x18002ed37  lea     rcx, [rsp+98h+Status]
0x18002ed3f  mov     [rsp+98h+var_68], rcx
0x18002ed44  mov     [rsp+98h+var_70], rbx
0x18002ed49  mov     [rsp+98h+var_78], r12d
0x18002ed4e  mov     r9, rax
0x18002ed51  xor     r8d, r8d; pReturnValue
0x18002ed54  lea     edx, [r8+2Ch]; nProcNum
0x18002ed58  lea     rcx, stru_18003D150; pProxyInfo
0x18002ed5f  call    cs:__imp_NdrClientCall3
0x18002ed66  nop     dword ptr [rax+rax+00h]
0x18002ed6b  mov     rbx, rax
0x18002ed6e  mov     [rsp+98h+var_40], rax
0x18002ed73  mov     [rsp+98h+var_48], al
0x18002ed77  test    al, al
0x18002ed79  jnz     short loc_18002ED9C
0x18002ed7b  mov     ecx, [rsp+98h+Status]; Status
0x18002ed82  call    cs:__imp_RtlNtStatusToDosError
0x18002ed89  nop     dword ptr [rax+rax+00h]
0x18002ed8e  mov     ecx, eax; dwErrCode
0x18002ed90  call    cs:__imp_SetLastError
0x18002ed97  nop     dword ptr [rax+rax+00h]
0x18002ed9c  jmp     short loc_18002EDC8
0x18002ed9e  mov     ebx, eax
0x18002eda0  mov     ecx, eax; dwErrCode
0x18002eda2  call    cs:__imp_SetLastError
0x18002eda9  nop     dword ptr [rax+rax+00h]
0x18002edae  mov     r8d, ebx
0x18002edb1  lea     rdx, aRpcExceptionD; "RPC Exception %d"
0x18002edb8  mov     ecx, 8; int
0x18002edbd  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002edc2  xor     bl, bl
0x18002edc4  mov     [rsp+98h+var_48], bl
0x18002edc8  mov     al, bl
0x18002edca  add     rsp, 68h
0x18002edce  pop     r15
0x18002edd0  pop     r14
0x18002edd2  pop     r12
0x18002edd4  pop     rdi
0x18002edd5  pop     rsi
0x18002edd6  pop     rbx
0x18002edd7  retn
0x1800337cf  push    rbp
0x1800337d1  sub     rsp, 50h
0x1800337d5  mov     rbp, rdx
0x1800337d8  mov     rcx, [rcx]
0x1800337db  mov     ecx, [rcx]; ExceptionCode
0x1800337dd  call    cs:__imp_I_RpcExceptionFilter
0x1800337e4  nop     dword ptr [rax+rax+00h]
0x1800337e9  nop
0x1800337ea  add     rsp, 50h
0x1800337ee  pop     rbp
0x1800337ef  retn
```
