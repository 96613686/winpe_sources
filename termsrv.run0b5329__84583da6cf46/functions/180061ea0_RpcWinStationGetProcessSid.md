# RpcWinStationGetProcessSid

- ea: `0x180061ea0`
- end: `0x18006206e`
- name: `RpcWinStationGetProcessSid`
- size: `462`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation`

## callees

- `0x18000a210`
- `0x18000bad0`
- `0x18000f1a0`
- `0x1800321f0`
- `0x180060548`
- `0x180061ea0`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180061fdc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180061fdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062008`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062008`
- `RPCRT4!RpcRevertToSelf` at `0x180062039`
- `RPCRT4!RpcRevertToSelf` at `0x180062039`

## string_xrefs

- `0x180061fc3`: `WinStationGetProcessSid`
- `0x180061ed7`: `RpcWinStationGetProcessSid`
- `0x180061f18`: `RpcWinStationGetProcessSid`
- `0x180061f4e`: `RpcWinStationGetProcessSid`
- `0x180061f7c`: `RpcWinStationGetProcessSid`
- `0x180061f75`: `pProcessUserSid`

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
  if ( !CAutoImpersonate::Impersonate((CAutoImpersonate *)v18) )
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
0x180061ea0  push    rbx
0x180061ea2  push    rbp
0x180061ea3  push    rsi
0x180061ea4  push    rdi
0x180061ea5  push    r12
0x180061ea7  push    r14
0x180061ea9  push    r15
0x180061eab  sub     rsp, 2A0h
0x180061eb2  mov     rax, cs:__security_cookie
0x180061eb9  xor     rax, rsp
0x180061ebc  mov     [rsp+2D8h+var_48], rax
0x180061ec4  mov     rbp, [rsp+2D8h+arg_20]
0x180061ecc  mov     rbx, r8
0x180061ecf  mov     r14, [rsp+2D8h+arg_30]
0x180061ed7  lea     r8, aRpcwinstationg_0; "RpcWinStationGetProcessSid"
0x180061ede  mov     r12d, edx
0x180061ee1  mov     r15, rcx
0x180061ee4  xor     edx, edx; int
0x180061ee6  lea     rcx, [rsp+2D8h+var_298]; this
0x180061eeb  mov     rsi, r9
0x180061eee  xor     dil, dil
0x180061ef1  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x180061ef6  lea     rcx, [rsp+2D8h+var_2A4]; this
0x180061efb  mov     [rsp+2D8h+var_2A4], 0
0x180061f03  call    ?Impersonate@CAutoImpersonate@@QEAAHXZ; CAutoImpersonate::Impersonate(void)
0x180061f08  test    eax, eax
0x180061f0a  jnz     short loc_180061F13
0x180061f0c  mov     ecx, 0C0000022h
0x180061f11  jmp     short loc_180061F3B
0x180061f13  test    r15, r15
0x180061f16  jnz     short loc_180061F49
0x180061f18  lea     r9, aRpcwinstationg_0; "RpcWinStationGetProcessSid"
0x180061f1f  lea     r8, aHserver; "hServer"
0x180061f26  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x180061f2d  lea     ecx, [r15+8]; int
0x180061f31  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180061f36  mov     ecx, 0C000000Dh
0x180061f3b  test    rsi, rsi
0x180061f3e  jz      loc_180062032
0x180061f44  jmp     loc_180062030
0x180061f49  test    rsi, rsi
0x180061f4c  jnz     short loc_180061F70
0x180061f4e  lea     r9, aRpcwinstationg_0; "RpcWinStationGetProcessSid"
0x180061f55  lea     r8, aPresult; "pResult"
0x180061f5c  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x180061f63  lea     ecx, [rsi+8]; int
0x180061f66  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180061f6b  jmp     loc_180062032
0x180061f70  test    rbp, rbp
0x180061f73  jnz     short loc_180061F9E
0x180061f75  lea     r8, aPprocessusersi; "pProcessUserSid"
0x180061f7c  lea     r9, aRpcwinstationg_0; "RpcWinStationGetProcessSid"
0x180061f83  mov     ecx, 8; int
0x180061f88  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x180061f8f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180061f94  mov     ecx, 0C000000Dh
0x180061f99  jmp     loc_180062030
0x180061f9e  test    r14, r14
0x180061fa1  jnz     short loc_180061FAC
0x180061fa3  lea     r8, aPdwsizeneeded; "pdwSizeNeeded"
0x180061faa  jmp     short loc_180061F7C
0x180061fac  cmp     cs:?fRpcShuttingDown@CRCMLegacyRpc@@2HA, 0; int CRCMLegacyRpc::fRpcShuttingDown
0x180061fb3  jz      short loc_180061FBC
0x180061fb5  mov     ecx, 0C0000120h
0x180061fba  jmp     short loc_180062030
0x180061fbc  mov     rcx, cs:?g_pRCMLegacyRpc@@3PEAVCRCMLegacyRpc@@EA; CRCMLegacyRpc * g_pRCMLegacyRpc
0x180061fc3  lea     rdx, aWinstationgetp; "WinStationGetProcessSid"
0x180061fca  mov     eax, [rsp+2D8h+arg_28]
0x180061fd1  mov     [rsp+2D8h+var_2A8], eax
0x180061fd5  mov     rcx, [rcx+6B8h]; hModule
0x180061fdc  call    cs:__imp_GetProcAddress
0x180061fe2  test    rax, rax
0x180061fe5  jz      short loc_180062008
0x180061fe7  lea     rcx, [rsp+2D8h+var_2A8]
0x180061fec  mov     r9, rbp
0x180061fef  mov     [rsp+2D8h+var_2B8], rcx
0x180061ff4  mov     r8, rbx
0x180061ff7  xor     ecx, ecx
0x180061ff9  mov     edx, r12d
0x180061ffc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062001  mov     dil, al
0x180062004  test    al, al
0x180062006  jnz     short loc_18006202E
0x180062008  call    cs:__imp_GetLastError
0x18006200e  mov     ecx, eax
0x180062010  test    eax, eax
0x180062012  jle     short loc_18006201D
0x180062014  movzx   ecx, ax
0x180062017  or      ecx, 80070000h
0x18006201d  cmp     ecx, 8007007Ah
0x180062023  jnz     short loc_180062030
0x180062025  mov     eax, [rsp+2D8h+var_2A8]
0x180062029  mov     [r14], eax
0x18006202c  jmp     short loc_180062030
0x18006202e  xor     ecx, ecx
0x180062030  mov     [rsi], ecx
0x180062032  cmp     [rsp+2D8h+var_2A4], 0
0x180062037  jz      short loc_18006203F
0x180062039  call    cs:__imp_RpcRevertToSelf
0x18006203f  lea     rcx, [rsp+2D8h+var_298]; this
0x180062044  call    ??1CRpcCallTrace@@UEAA@XZ; CRpcCallTrace::~CRpcCallTrace(void)
0x180062049  mov     al, dil
0x18006204c  mov     rcx, [rsp+2D8h+var_48]
0x180062054  xor     rcx, rsp; StackCookie
0x180062057  call    __security_check_cookie
0x18006205c  add     rsp, 2A0h
0x180062063  pop     r15
0x180062065  pop     r14
0x180062067  pop     r12
0x180062069  pop     rdi
0x18006206a  pop     rsi
0x18006206b  pop     rbp
0x18006206c  pop     rbx
0x18006206d  retn
```
