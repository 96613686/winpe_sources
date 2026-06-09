# _WinStationGetAllSessionsEx(void *,ulong,_EXECENVDATAEX * *,ulong *)

- ea: `0x180002c00`
- end: `0x180002d2d`
- name: `?_WinStationGetAllSessionsEx@@YAJPEAXKPEAPEAU_EXECENVDATAEX@@PEAK@Z`
- size: `301`
- prototype: `__int64 __fastcall(void *, unsigned int, struct _EXECENVDATAEX **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180002600`

## callees

- `0x180002c00`
- `0x1800041a0`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002cf3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002cf3`
- `RPCRT4!I_RpcExceptionFilter` at `0x180032e59`
- `RPCRT4!I_RpcExceptionFilter` at `0x180032e59`
- `RPCRT4!NdrClientCall3` at `0x180002c7d`
- `RPCRT4!NdrClientCall3` at `0x180002c7d`

## string_xrefs

- `0x180002ce2`: `Failed to open binding`

## pseudocode

```c
__int64 __fastcall _WinStationGetAllSessionsEx(void *a1, int a2, struct _EXECENVDATAEX **a3, unsigned int *a4)
{
  void *v7; // rax
  signed int Pointer; // ebx
  signed int LastError; // eax
  int v11; // [rsp+20h] [rbp-48h]
  unsigned __int16 v12[16]; // [rsp+48h] [rbp-20h] BYREF

  *a3 = 0;
  *a4 = 0;
  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v12, a1, 0);
  if ( CSmartPublicBinding::operator void *(v12) )
  {
    v7 = CSmartPublicBinding::operator void *(v12);
    v11 = a2;
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180035048, 0xBu, 0, v7, v11, a3, a4).Pointer;
    if ( Pointer < 0 )
      _DbgPrintMessage(8, "RpcGetAllSessionsEx failed: 0x%x in %s", Pointer, "_WinStationGetAllSessionsEx");
  }
  else
  {
    _DbgPrintMessage(8, "Failed to open binding");
    LastError = GetLastError();
    Pointer = LastError;
    if ( LastError > 0 )
      Pointer = (unsigned __int16)LastError | 0x80070000;
  }
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v12);
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180002c00  mov     [rsp+arg_0], rbx
0x180002c05  mov     [rsp+arg_8], rsi
0x180002c0a  push    rdi
0x180002c0b  sub     rsp, 60h
0x180002c0f  mov     rbx, r9
0x180002c12  mov     rdi, r8
0x180002c15  mov     esi, edx
0x180002c17  mov     qword ptr [r8], 0
0x180002c1e  mov     dword ptr [r9], 0
0x180002c25  xor     r8d, r8d; int
0x180002c28  mov     rdx, rcx; void *
0x180002c2b  lea     rcx, [rsp+68h+var_20]; this
0x180002c30  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x180002c35  lea     rcx, [rsp+68h+var_20]; unsigned __int16 *
0x180002c3a  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180002c3f  test    rax, rax
0x180002c42  jz      loc_180002CE2
0x180002c48  lea     rcx, [rsp+68h+var_20]; unsigned __int16 *
0x180002c4d  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180002c52  mov     [rsp+68h+arg_10], 0
0x180002c5e  mov     [rsp+68h+var_38], rbx
0x180002c63  mov     [rsp+68h+var_40], rdi
0x180002c68  mov     [rsp+68h+var_48], esi
0x180002c6c  mov     r9, rax
0x180002c6f  xor     r8d, r8d; pReturnValue
0x180002c72  lea     edx, [r8+0Bh]; nProcNum
0x180002c76  lea     rcx, stru_180035048; pProxyInfo
0x180002c7d  call    cs:__imp_NdrClientCall3
0x180002c84  nop     dword ptr [rax+rax+00h]
0x180002c89  mov     rbx, rax
0x180002c8c  mov     [rsp+68h+arg_10], rax
0x180002c94  mov     [rsp+68h+var_28], eax
0x180002c98  jmp     short loc_180002CC1
0x180002c9a  test    eax, eax
0x180002c9c  jle     short loc_180002CA6
0x180002c9e  movzx   eax, ax
0x180002ca1  or      eax, 80070000h
0x180002ca6  mov     ebx, eax
0x180002ca8  mov     [rsp+68h+var_28], eax
0x180002cac  mov     r8d, eax
0x180002caf  lea     rdx, aRpcgetallsessi; "RpcGetAllSessionsEx threw an exception:"...
0x180002cb6  mov     ecx, 8; int
0x180002cbb  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180002cc0  nop
0x180002cc1  test    ebx, ebx
0x180002cc3  js      short loc_180002D10
0x180002cc5  lea     rcx, [rsp+68h+var_20]; this
0x180002cca  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180002ccf  mov     eax, ebx
0x180002cd1  mov     rbx, [rsp+68h+arg_0]
0x180002cd6  mov     rsi, [rsp+68h+arg_8]
0x180002cdb  add     rsp, 60h
0x180002cdf  pop     rdi
0x180002ce0  retn
0x180002ce2  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x180002ce9  mov     ecx, 8; int
0x180002cee  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180002cf3  call    cs:__imp_GetLastError
0x180002cfa  nop     dword ptr [rax+rax+00h]
0x180002cff  mov     ebx, eax
0x180002d01  test    eax, eax
0x180002d03  jle     short loc_180002CC5
0x180002d05  movzx   ebx, ax
0x180002d08  or      ebx, 80070000h
0x180002d0e  jmp     short loc_180002CC5
0x180002d10  lea     r9, aWinstationgeta_4; "_WinStationGetAllSessionsEx"
0x180002d17  mov     r8d, ebx
0x180002d1a  lea     rdx, aRpcgetallsessi_2; "RpcGetAllSessionsEx failed: 0x%x in %s"
0x180002d21  mov     ecx, 8; int
0x180002d26  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180002d2b  jmp     short loc_180002CC5
0x180032e4b  push    rbp
0x180032e4d  sub     rsp, 40h
0x180032e51  mov     rbp, rdx
0x180032e54  mov     rcx, [rcx]
0x180032e57  mov     ecx, [rcx]; ExceptionCode
0x180032e59  call    cs:__imp_I_RpcExceptionFilter
0x180032e60  nop     dword ptr [rax+rax+00h]
0x180032e65  nop
0x180032e66  add     rsp, 40h
0x180032e6a  pop     rbp
0x180032e6b  retn
```
