# _WinStationGetAllSessionsEx(void *,ulong,_EXECENVDATAEX * *,ulong *)

- ea: `0x180005194`
- end: `0x1800052b4`
- name: `?_WinStationGetAllSessionsEx@@YAJPEAXKPEAPEAU_EXECENVDATAEX@@PEAK@Z`
- size: `288`
- prototype: `__int64 __fastcall(void *, unsigned int, struct _EXECENVDATAEX **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180004bb0`

## callees

- `0x180005194`
- `0x180005c30`
- `0x180007890`
- `0x180008290`
- `0x180008e30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005280`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005280`
- `RPCRT4!I_RpcExceptionFilter` at `0x180030154`
- `RPCRT4!I_RpcExceptionFilter` at `0x180030154`
- `RPCRT4!NdrClientCall3` at `0x180005211`
- `RPCRT4!NdrClientCall3` at `0x180005211`

## string_xrefs

- `0x18000526f`: `Failed to open binding`

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
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800320B0, 0xBu, 0, v7, v11, a3, a4).Pointer;
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
0x180005194  mov     [rsp+arg_0], rbx
0x180005199  mov     [rsp+arg_8], rsi
0x18000519e  push    rdi
0x18000519f  sub     rsp, 60h
0x1800051a3  mov     rbx, r9
0x1800051a6  mov     rdi, r8
0x1800051a9  mov     esi, edx
0x1800051ab  mov     qword ptr [r8], 0
0x1800051b2  mov     dword ptr [r9], 0
0x1800051b9  xor     r8d, r8d; int
0x1800051bc  mov     rdx, rcx; void *
0x1800051bf  lea     rcx, [rsp+68h+var_20]; this
0x1800051c4  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x1800051c9  lea     rcx, [rsp+68h+var_20]; unsigned __int16 *
0x1800051ce  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800051d3  test    rax, rax
0x1800051d6  jz      loc_18000526F
0x1800051dc  lea     rcx, [rsp+68h+var_20]; unsigned __int16 *
0x1800051e1  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800051e6  mov     [rsp+68h+arg_10], 0
0x1800051f2  mov     [rsp+68h+var_38], rbx
0x1800051f7  mov     [rsp+68h+var_40], rdi
0x1800051fc  mov     [rsp+68h+var_48], esi
0x180005200  mov     r9, rax
0x180005203  xor     r8d, r8d; pReturnValue
0x180005206  lea     edx, [r8+0Bh]; nProcNum
0x18000520a  lea     rcx, stru_1800320B0; pProxyInfo
0x180005211  call    cs:__imp_NdrClientCall3
0x180005217  mov     rbx, rax
0x18000521a  mov     [rsp+68h+arg_10], rax
0x180005222  mov     [rsp+68h+var_28], eax
0x180005226  jmp     short loc_18000524F
0x180005228  test    eax, eax
0x18000522a  jle     short loc_180005234
0x18000522c  movzx   eax, ax
0x18000522f  or      eax, 80070000h
0x180005234  mov     ebx, eax
0x180005236  mov     [rsp+68h+var_28], eax
0x18000523a  mov     r8d, eax
0x18000523d  lea     rdx, aRpcgetallsessi; "RpcGetAllSessionsEx threw an exception:"...
0x180005244  mov     ecx, 8; int
0x180005249  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000524e  nop
0x18000524f  test    ebx, ebx
0x180005251  js      short loc_180005297
0x180005253  lea     rcx, [rsp+68h+var_20]; this
0x180005258  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18000525d  mov     eax, ebx
0x18000525f  mov     rbx, [rsp+68h+arg_0]
0x180005264  mov     rsi, [rsp+68h+arg_8]
0x180005269  add     rsp, 60h
0x18000526d  pop     rdi
0x18000526e  retn
0x18000526f  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x180005276  mov     ecx, 8; int
0x18000527b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180005280  call    cs:__imp_GetLastError
0x180005286  mov     ebx, eax
0x180005288  test    eax, eax
0x18000528a  jle     short loc_180005253
0x18000528c  movzx   ebx, ax
0x18000528f  or      ebx, 80070000h
0x180005295  jmp     short loc_180005253
0x180005297  lea     r9, aWinstationgeta_4; "_WinStationGetAllSessionsEx"
0x18000529e  mov     r8d, ebx
0x1800052a1  lea     rdx, aRpcgetallsessi_2; "RpcGetAllSessionsEx failed: 0x%x in %s"
0x1800052a8  mov     ecx, 8; int
0x1800052ad  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800052b2  jmp     short loc_180005253
0x180030146  push    rbp
0x180030148  sub     rsp, 40h
0x18003014c  mov     rbp, rdx
0x18003014f  mov     rcx, [rcx]
0x180030152  mov     ecx, [rcx]; ExceptionCode
0x180030154  call    cs:__imp_I_RpcExceptionFilter
0x18003015a  nop
0x18003015b  add     rsp, 40h
0x18003015f  pop     rbp
0x180030160  retn
```
