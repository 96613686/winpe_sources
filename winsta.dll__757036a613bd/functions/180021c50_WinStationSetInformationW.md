# WinStationSetInformationW

- ea: `0x180021c50`
- end: `0x180021d69`
- name: `WinStationSetInformationW`
- size: `281`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180004554`
- `0x180005c30`
- `0x180005fcc`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x180021c50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021d3a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021d5b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021d3a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021d5b`
- `RPCRT4!NdrClientCall3` at `0x180021cd7`
- `RPCRT4!NdrClientCall3` at `0x180021cd7`

## string_xrefs

- `0x180021c95`: `Failed to open binding`
- `0x180021d00`: `RpcPopSecurityDialog threw an exception: 0x%x`
- `0x180021d20`: `RpcPopSecurityDialog failed: 0x%x in %s`

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
      Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180032140, 2u, 0, v3).Pointer;
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
0x180021c50  push    rbx
0x180021c52  sub     rsp, 40h
0x180021c56  call    ?IsLocalServer@@YAHPEAX@Z; IsLocalServer(void *)
0x180021c5b  test    eax, eax
0x180021c5d  jz      loc_180021D45
0x180021c63  cmp     edx, 0FFFFFFFFh
0x180021c66  jnz     loc_180021D45
0x180021c6c  cmp     r8d, 0Dh
0x180021c70  jnz     loc_180021D45
0x180021c76  xor     edx, edx; void *
0x180021c78  lea     r8d, [rdx+1]; int
0x180021c7c  lea     rcx, [rsp+48h+var_18]; this
0x180021c81  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x180021c86  lea     rcx, [rsp+48h+var_18]; unsigned __int16 *
0x180021c8b  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180021c90  test    rax, rax
0x180021c93  jnz     short loc_180021CB3
0x180021c95  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x180021c9c  lea     ecx, [rax+8]; int
0x180021c9f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180021ca4  lea     rcx, [rsp+48h+var_18]; this
0x180021ca9  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180021cae  jmp     loc_180021D61
0x180021cb3  lea     rcx, [rsp+48h+var_18]; unsigned __int16 *
0x180021cb8  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180021cbd  mov     [rsp+48h+var_20], 0
0x180021cc6  mov     r9, rax
0x180021cc9  xor     r8d, r8d; pReturnValue
0x180021ccc  lea     edx, [r8+2]; nProcNum
0x180021cd0  lea     rcx, stru_180032140; pProxyInfo
0x180021cd7  call    cs:__imp_NdrClientCall3
0x180021cdd  mov     rbx, rax
0x180021ce0  mov     [rsp+48h+var_20], rax
0x180021ce5  mov     [rsp+48h+var_28], eax
0x180021ce9  jmp     short loc_180021D12
0x180021ceb  test    eax, eax
0x180021ced  jle     short loc_180021CF7
0x180021cef  movzx   eax, ax
0x180021cf2  or      eax, 80070000h
0x180021cf7  mov     ebx, eax
0x180021cf9  mov     [rsp+48h+var_28], eax
0x180021cfd  mov     r8d, eax
0x180021d00  lea     rdx, aRpcpopsecurity_0; "RpcPopSecurityDialog threw an exception"...
0x180021d07  mov     ecx, 8; int
0x180021d0c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180021d11  nop
0x180021d12  test    ebx, ebx
0x180021d14  jns     short loc_180021CA4
0x180021d16  lea     r9, aWinstationseti_2; "WinStationSetInformationW"
0x180021d1d  mov     r8d, ebx
0x180021d20  lea     rdx, aRpcpopsecurity; "RpcPopSecurityDialog failed: 0x%x in %s"
0x180021d27  mov     ecx, 8; int
0x180021d2c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180021d31  mov     ecx, ebx; int
0x180021d33  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180021d38  mov     ecx, eax; dwErrCode
0x180021d3a  call    cs:__imp_SetLastError
0x180021d40  jmp     loc_180021CA4
0x180021d45  lea     rdx, aObsoleteWinsta_0; "!!! Obsolete_WinStationSetInformationW "...
0x180021d4c  mov     ecx, 4; int
0x180021d51  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180021d56  mov     ecx, 1; dwErrCode
0x180021d5b  call    cs:__imp_SetLastError
0x180021d61  xor     al, al
0x180021d63  add     rsp, 40h
0x180021d67  pop     rbx
0x180021d68  retn
0x18003082f  push    rbp
0x180030831  sub     rsp, 20h
0x180030835  mov     rbp, rdx
0x180030838  mov     rcx, [rcx]
0x18003083b  mov     ecx, [rcx]; ExceptionCode
0x18003083d  call    cs:__imp_I_RpcExceptionFilter
0x180030843  nop
0x180030844  add     rsp, 20h
0x180030848  pop     rbp
0x180030849  retn
```
