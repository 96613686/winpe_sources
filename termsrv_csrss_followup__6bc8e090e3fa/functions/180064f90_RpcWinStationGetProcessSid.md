# RpcWinStationGetProcessSid

- ea: `0x180064f90`
- end: `0x180065174`
- name: `RpcWinStationGetProcessSid`
- size: `484`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation`

## callees

- `0x180009940`
- `0x18000ba50`
- `0x18000f760`
- `0x180033f60`
- `0x180063598`
- `0x180064f90`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800650cf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800650cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065101`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065101`
- `RPCRT4!RpcRevertToSelf` at `0x180065138`
- `RPCRT4!RpcRevertToSelf` at `0x180065138`

## string_xrefs

- `0x1800650b6`: `WinStationGetProcessSid`
- `0x180064fc7`: `RpcWinStationGetProcessSid`
- `0x180065008`: `RpcWinStationGetProcessSid`
- `0x18006503e`: `RpcWinStationGetProcessSid`
- `0x18006506c`: `RpcWinStationGetProcessSid`
- `0x180065065`: `pProcessUserSid`

## pseudocode

```c
char __fastcall RpcWinStationGetProcessSid(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        unsigned int *a4,
        __int64 a5,
        int a6,
        _DWORD *a7)
{
  char v11; // di
  unsigned int v12; // ecx
  const char *v13; // r8
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  int v17; // [rsp+30h] [rbp-2A8h] BYREF
  _DWORD v18[3]; // [rsp+34h] [rbp-2A4h] BYREF
  _BYTE v19[592]; // [rsp+40h] [rbp-298h] BYREF

  v11 = 0;
  CRpcCallTrace::CRpcCallTrace((CRpcCallTrace *)v19, 0, "RpcWinStationGetProcessSid");
  v18[0] = 0;
  if ( !(unsigned int)CAutoImpersonate::Impersonate((CAutoImpersonate *)v18) )
  {
    v12 = -1073741790;
    goto LABEL_5;
  }
  if ( !a1 )
  {
    _DbgPrintMessage(8, "Missing paramter %s in %s", "hServer", "RpcWinStationGetProcessSid");
    v12 = -1073741811;
LABEL_5:
    if ( !a4 )
      goto LABEL_24;
    goto LABEL_23;
  }
  if ( !a4 )
  {
    _DbgPrintMessage(8, "Missing paramter %s in %s", "pResult", "RpcWinStationGetProcessSid");
    goto LABEL_24;
  }
  if ( a5 )
  {
    if ( a7 )
    {
      if ( CRCMLegacyRpc::fRpcShuttingDown )
      {
        v12 = -1073741536;
      }
      else
      {
        v17 = a6;
        ProcAddress = GetProcAddress(*((HMODULE *)g_pRCMLegacyRpc + 215), "WinStationGetProcessSid");
        if ( ProcAddress
          && (v11 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64, __int64, int *))ProcAddress)(0, a2, a3, a5, &v17)) != 0 )
        {
          v12 = 0;
        }
        else
        {
          LastError = GetLastError();
          v12 = LastError;
          if ( LastError > 0 )
            v12 = (unsigned __int16)LastError | 0x80070000;
          if ( v12 == -2147024774 )
            *a7 = v17;
        }
      }
      goto LABEL_23;
    }
    v13 = "pdwSizeNeeded";
  }
  else
  {
    v13 = "pProcessUserSid";
  }
  _DbgPrintMessage(8, "Missing paramter %s in %s", v13, "RpcWinStationGetProcessSid");
  v12 = -1073741811;
LABEL_23:
  *a4 = v12;
LABEL_24:
  if ( v18[0] )
    RpcRevertToSelf();
  CRpcCallTrace::~CRpcCallTrace((CRpcCallTrace *)v19);
  return v11;
}

```

## disassembly

```asm
0x180064f90  push    rbx
0x180064f92  push    rbp
0x180064f93  push    rsi
0x180064f94  push    rdi
0x180064f95  push    r12
0x180064f97  push    r14
0x180064f99  push    r15
0x180064f9b  sub     rsp, 2A0h
0x180064fa2  mov     rax, cs:__security_cookie
0x180064fa9  xor     rax, rsp
0x180064fac  mov     [rsp+2D8h+var_48], rax
0x180064fb4  mov     rbp, [rsp+2D8h+arg_20]
0x180064fbc  mov     rbx, r8
0x180064fbf  mov     r14, [rsp+2D8h+arg_30]
0x180064fc7  lea     r8, aRpcwinstationg_0; "RpcWinStationGetProcessSid"
0x180064fce  mov     r12d, edx
0x180064fd1  mov     r15, rcx
0x180064fd4  xor     edx, edx; int
0x180064fd6  lea     rcx, [rsp+2D8h+var_298]; this
0x180064fdb  mov     rsi, r9
0x180064fde  xor     dil, dil
0x180064fe1  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x180064fe6  lea     rcx, [rsp+2D8h+var_2A4]; this
0x180064feb  mov     [rsp+2D8h+var_2A4], 0
0x180064ff3  call    ?Impersonate@CAutoImpersonate@@QEAAHXZ; CAutoImpersonate::Impersonate(void)
0x180064ff8  test    eax, eax
0x180064ffa  jnz     short loc_180065003
0x180064ffc  mov     ecx, 0C0000022h
0x180065001  jmp     short loc_18006502B
0x180065003  test    r15, r15
0x180065006  jnz     short loc_180065039
0x180065008  lea     r9, aRpcwinstationg_0; "RpcWinStationGetProcessSid"
0x18006500f  lea     r8, aHserver; "hServer"
0x180065016  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x18006501d  lea     ecx, [r15+8]; int
0x180065021  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180065026  mov     ecx, 0C000000Dh
0x18006502b  test    rsi, rsi
0x18006502e  jz      loc_180065131
0x180065034  jmp     loc_18006512F
0x180065039  test    rsi, rsi
0x18006503c  jnz     short loc_180065060
0x18006503e  lea     r9, aRpcwinstationg_0; "RpcWinStationGetProcessSid"
0x180065045  lea     r8, aPresult; "pResult"
0x18006504c  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x180065053  lea     ecx, [rsi+8]; int
0x180065056  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006505b  jmp     loc_180065131
0x180065060  test    rbp, rbp
0x180065063  jnz     short loc_18006508E
0x180065065  lea     r8, aPprocessusersi; "pProcessUserSid"
0x18006506c  lea     r9, aRpcwinstationg_0; "RpcWinStationGetProcessSid"
0x180065073  mov     ecx, 8; int
0x180065078  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x18006507f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180065084  mov     ecx, 0C000000Dh
0x180065089  jmp     loc_18006512F
0x18006508e  test    r14, r14
0x180065091  jnz     short loc_18006509C
0x180065093  lea     r8, aPdwsizeneeded; "pdwSizeNeeded"
0x18006509a  jmp     short loc_18006506C
0x18006509c  cmp     cs:?fRpcShuttingDown@CRCMLegacyRpc@@2HA, 0; int CRCMLegacyRpc::fRpcShuttingDown
0x1800650a3  jz      short loc_1800650AF
0x1800650a5  mov     ecx, 0C0000120h
0x1800650aa  jmp     loc_18006512F
0x1800650af  mov     rcx, cs:?g_pRCMLegacyRpc@@3PEAVCRCMLegacyRpc@@EA; CRCMLegacyRpc * g_pRCMLegacyRpc
0x1800650b6  lea     rdx, aWinstationgetp; "WinStationGetProcessSid"
0x1800650bd  mov     eax, [rsp+2D8h+arg_28]
0x1800650c4  mov     [rsp+2D8h+var_2A8], eax
0x1800650c8  mov     rcx, [rcx+6B8h]; hModule
0x1800650cf  call    cs:__imp_GetProcAddress
0x1800650d6  nop     dword ptr [rax+rax+00h]
0x1800650db  test    rax, rax
0x1800650de  jz      short loc_180065101
0x1800650e0  lea     rcx, [rsp+2D8h+var_2A8]
0x1800650e5  mov     r9, rbp
0x1800650e8  mov     [rsp+2D8h+var_2B8], rcx
0x1800650ed  mov     r8, rbx
0x1800650f0  xor     ecx, ecx
0x1800650f2  mov     edx, r12d
0x1800650f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800650fa  mov     dil, al
0x1800650fd  test    al, al
0x1800650ff  jnz     short loc_18006512D
0x180065101  call    cs:__imp_GetLastError
0x180065108  nop     dword ptr [rax+rax+00h]
0x18006510d  mov     ecx, eax
0x18006510f  test    eax, eax
0x180065111  jle     short loc_18006511C
0x180065113  movzx   ecx, ax
0x180065116  or      ecx, 80070000h
0x18006511c  cmp     ecx, 8007007Ah
0x180065122  jnz     short loc_18006512F
0x180065124  mov     eax, [rsp+2D8h+var_2A8]
0x180065128  mov     [r14], eax
0x18006512b  jmp     short loc_18006512F
0x18006512d  xor     ecx, ecx
0x18006512f  mov     [rsi], ecx
0x180065131  cmp     [rsp+2D8h+var_2A4], 0
0x180065136  jz      short loc_180065144
0x180065138  call    cs:__imp_RpcRevertToSelf
0x18006513f  nop     dword ptr [rax+rax+00h]
0x180065144  lea     rcx, [rsp+2D8h+var_298]; this
0x180065149  call    ??1CRpcCallTrace@@UEAA@XZ; CRpcCallTrace::~CRpcCallTrace(void)
0x18006514e  mov     al, dil
0x180065151  mov     rcx, [rsp+2D8h+var_48]
0x180065159  xor     rcx, rsp; StackCookie
0x18006515c  call    __security_check_cookie
0x180065161  add     rsp, 2A0h
0x180065168  pop     r15
0x18006516a  pop     r14
0x18006516c  pop     r12
0x18006516e  pop     rdi
0x18006516f  pop     rsi
0x180065170  pop     rbp
0x180065171  pop     rbx
0x180065172  retn
```
