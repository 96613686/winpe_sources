# WinStationSetInformationW

- ea: `0x1800234e0`
- end: `0x18002360c`
- name: `WinStationSetInformationW`
- size: `300`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1800041a0`
- `0x180004558`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`
- `0x18000a784`
- `0x1800234e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800235d0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800235f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800235d0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800235f7`
- `RPCRT4!NdrClientCall3` at `0x180023567`
- `RPCRT4!NdrClientCall3` at `0x180023567`

## string_xrefs

- `0x180023525`: `Failed to open binding`
- `0x180023596`: `RpcPopSecurityDialog threw an exception: 0x%x`
- `0x1800235b6`: `RpcPopSecurityDialog failed: 0x%x in %s`

## pseudocode

```c
char __fastcall WinStationSetInformationW(void *a1)
{
  int v1; // edx
  int v2; // r8d
  __int64 v3; // rax
  int Pointer; // ebx
  DWORD v5; // eax
  unsigned __int16 v7[12]; // [rsp+30h] [rbp-18h] BYREF

  if ( (unsigned int)IsLocalServer(a1) && v1 == -1 && v2 == 13 )
  {
    CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v7, 0, 1);
    if ( CSmartPublicBinding::operator void *(v7) )
    {
      v3 = CSmartPublicBinding::operator void *(v7);
      Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180035140, 2u, 0, v3).Pointer;
      if ( Pointer < 0 )
      {
        _DbgPrintMessage(8, "RpcPopSecurityDialog failed: 0x%x in %s", Pointer, "WinStationSetInformationW");
        v5 = ConvertHRESULT2WIN32(Pointer);
        SetLastError(v5);
      }
    }
    else
    {
      _DbgPrintMessage(8, "Failed to open binding");
    }
    CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v7);
  }
  else
  {
    _DbgPrintMessage(4, "!!! Obsolete_WinStationSetInformationW deprecated");
    SetLastError(1u);
  }
  return 0;
}

```

## disassembly

```asm
0x1800234e0  push    rbx
0x1800234e2  sub     rsp, 40h
0x1800234e6  call    ?IsLocalServer@@YAHPEAX@Z; IsLocalServer(void *)
0x1800234eb  test    eax, eax
0x1800234ed  jz      loc_1800235E1
0x1800234f3  cmp     edx, 0FFFFFFFFh
0x1800234f6  jnz     loc_1800235E1
0x1800234fc  cmp     r8d, 0Dh
0x180023500  jnz     loc_1800235E1
0x180023506  xor     edx, edx; void *
0x180023508  lea     r8d, [rdx+1]; int
0x18002350c  lea     rcx, [rsp+48h+var_18]; this
0x180023511  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x180023516  lea     rcx, [rsp+48h+var_18]; unsigned __int16 *
0x18002351b  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180023520  test    rax, rax
0x180023523  jnz     short loc_180023543
0x180023525  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x18002352c  lea     ecx, [rax+8]; int
0x18002352f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180023534  lea     rcx, [rsp+48h+var_18]; this
0x180023539  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18002353e  jmp     loc_180023603
0x180023543  lea     rcx, [rsp+48h+var_18]; unsigned __int16 *
0x180023548  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002354d  mov     [rsp+48h+var_20], 0
0x180023556  mov     r9, rax
0x180023559  xor     r8d, r8d; pReturnValue
0x18002355c  lea     edx, [r8+2]; nProcNum
0x180023560  lea     rcx, stru_180035140; pProxyInfo
0x180023567  call    cs:__imp_NdrClientCall3
0x18002356e  nop     dword ptr [rax+rax+00h]
0x180023573  mov     rbx, rax
0x180023576  mov     [rsp+48h+var_20], rax
0x18002357b  mov     [rsp+48h+var_28], eax
0x18002357f  jmp     short loc_1800235A8
0x180023581  test    eax, eax
0x180023583  jle     short loc_18002358D
0x180023585  movzx   eax, ax
0x180023588  or      eax, 80070000h
0x18002358d  mov     ebx, eax
0x18002358f  mov     [rsp+48h+var_28], eax
0x180023593  mov     r8d, eax
0x180023596  lea     rdx, aRpcpopsecurity_0; "RpcPopSecurityDialog threw an exception"...
0x18002359d  mov     ecx, 8; int
0x1800235a2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800235a7  nop
0x1800235a8  test    ebx, ebx
0x1800235aa  jns     short loc_180023534
0x1800235ac  lea     r9, aWinstationseti_2; "WinStationSetInformationW"
0x1800235b3  mov     r8d, ebx
0x1800235b6  lea     rdx, aRpcpopsecurity; "RpcPopSecurityDialog failed: 0x%x in %s"
0x1800235bd  mov     ecx, 8; int
0x1800235c2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800235c7  mov     ecx, ebx; int
0x1800235c9  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x1800235ce  mov     ecx, eax; dwErrCode
0x1800235d0  call    cs:__imp_SetLastError
0x1800235d7  nop     dword ptr [rax+rax+00h]
0x1800235dc  jmp     loc_180023534
0x1800235e1  lea     rdx, aObsoleteWinsta_0; "!!! Obsolete_WinStationSetInformationW "...
0x1800235e8  mov     ecx, 4; int
0x1800235ed  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800235f2  mov     ecx, 1; dwErrCode
0x1800235f7  call    cs:__imp_SetLastError
0x1800235fe  nop     dword ptr [rax+rax+00h]
0x180023603  xor     al, al
0x180023605  add     rsp, 40h
0x180023609  pop     rbx
0x18002360a  retn
0x18003372f  push    rbp
0x180033731  sub     rsp, 20h
0x180033735  mov     rbp, rdx
0x180033738  mov     rcx, [rcx]
0x18003373b  mov     ecx, [rcx]; ExceptionCode
0x18003373d  call    cs:__imp_I_RpcExceptionFilter
0x180033744  nop     dword ptr [rax+rax+00h]
0x180033749  nop
0x18003374a  add     rsp, 20h
0x18003374e  pop     rbp
0x18003374f  retn
```
