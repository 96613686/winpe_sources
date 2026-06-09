# WinStationTerminateGlassReplacementSession

- ea: `0x1800206a0`
- end: `0x1800207eb`
- name: `WinStationTerminateGlassReplacementSession`
- size: `331`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180005c30`
- `0x180005fcc`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x1800206a0`
- `0x18002fe40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800207b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800207b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800206e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800206e1`
- `RPCRT4!NdrClientCall3` at `0x180020754`
- `RPCRT4!NdrClientCall3` at `0x180020754`

## string_xrefs

- `0x1800206fa`: `WinStationTerminateGlassReplacementSession`
- `0x18002076a`: `WinStationTerminateGlassReplacementSession`

## pseudocode

```c
bool __fastcall WinStationTerminateGlassReplacementSession(int a1)
{
  signed int LastError; // eax
  signed int v3; // ebx
  __int64 v4; // rax
  int Pointer; // eax
  DWORD v6; // eax
  int v8; // [rsp+20h] [rbp-58h]
  unsigned __int16 v9[8]; // [rsp+40h] [rbp-38h] BYREF
  __int128 v10; // [rsp+50h] [rbp-28h] BYREF

  v10 = 0;
  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v9, 0, 0);
  if ( CSmartPublicBinding::operator void *(v9) )
    goto LABEL_6;
  LastError = GetLastError();
  v3 = LastError;
  if ( LastError > 0 )
    v3 = (unsigned __int16)LastError | 0x80070000;
  if ( v3 >= 0 )
  {
LABEL_6:
    v10 = 0;
    v4 = CSmartPublicBinding::operator void *(v9);
    v8 = a1;
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180032260, 3u, 0, v4, v8, &v10).Pointer;
    v3 = Pointer;
    if ( Pointer < 0 )
      _DbgPrintMessage(
        8,
        "RpcTerminateSession failed: 0x%x in %s",
        Pointer,
        "WinStationTerminateGlassReplacementSession");
  }
  else
  {
    _DbgPrintMessage(8, "Bind( NULL ) failed: 0x%x in %s", v3, "WinStationTerminateGlassReplacementSession");
  }
  v6 = ConvertHRESULT2WIN32(v3);
  SetLastError(v6);
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v9);
  return v3 >= 0;
}

```

## disassembly

```asm
0x1800206a0  mov     [rsp+arg_8], rbx
0x1800206a5  push    rdi
0x1800206a6  sub     rsp, 70h
0x1800206aa  mov     rax, cs:__security_cookie
0x1800206b1  xor     rax, rsp
0x1800206b4  mov     [rsp+78h+var_18], rax
0x1800206b9  mov     edi, ecx
0x1800206bb  xorps   xmm0, xmm0
0x1800206be  movups  [rsp+78h+var_28], xmm0
0x1800206c3  xor     r8d, r8d; int
0x1800206c6  xor     edx, edx; void *
0x1800206c8  lea     rcx, [rsp+78h+var_38]; this
0x1800206cd  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x1800206d2  lea     rcx, [rsp+78h+var_38]; unsigned __int16 *
0x1800206d7  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800206dc  test    rax, rax
0x1800206df  jnz     short loc_18002071A
0x1800206e1  call    cs:__imp_GetLastError
0x1800206e7  mov     ebx, eax
0x1800206e9  test    eax, eax
0x1800206eb  jle     short loc_1800206F6
0x1800206ed  movzx   ebx, ax
0x1800206f0  or      ebx, 80070000h
0x1800206f6  test    ebx, ebx
0x1800206f8  jns     short loc_18002071A
0x1800206fa  lea     r9, aWinstationterm_1; "WinStationTerminateGlassReplacementSess"...
0x180020701  mov     r8d, ebx
0x180020704  lea     rdx, aBindNullFailed; "Bind( NULL ) failed: 0x%x in %s"
0x18002070b  mov     ecx, 8; int
0x180020710  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180020715  jmp     loc_1800207B0
0x18002071a  xorps   xmm0, xmm0
0x18002071d  movups  [rsp+78h+var_28], xmm0
0x180020722  lea     rcx, [rsp+78h+var_38]; unsigned __int16 *
0x180020727  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002072c  mov     [rsp+78h+var_40], 0
0x180020735  lea     rcx, [rsp+78h+var_28]
0x18002073a  mov     [rsp+78h+var_50], rcx
0x18002073f  mov     [rsp+78h+var_58], edi
0x180020743  mov     r9, rax
0x180020746  xor     r8d, r8d; pReturnValue
0x180020749  lea     edx, [r8+3]; nProcNum
0x18002074d  lea     rcx, stru_180032260; pProxyInfo
0x180020754  call    cs:__imp_NdrClientCall3
0x18002075a  mov     rbx, rax
0x18002075d  mov     [rsp+78h+var_40], rax
0x180020762  mov     [rsp+78h+var_48], eax
0x180020766  test    eax, eax
0x180020768  jns     short loc_180020787
0x18002076a  lea     r9, aWinstationterm_1; "WinStationTerminateGlassReplacementSess"...
0x180020771  mov     r8d, eax
0x180020774  lea     rdx, aRpcterminatese_0; "RpcTerminateSession failed: 0x%x in %s"
0x18002077b  mov     ecx, 8; int
0x180020780  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180020785  jmp     short loc_1800207B0
0x180020787  jmp     short loc_1800207B0
0x180020789  test    eax, eax
0x18002078b  jle     short loc_180020795
0x18002078d  movzx   eax, ax
0x180020790  or      eax, 80070000h
0x180020795  mov     ebx, eax
0x180020797  mov     [rsp+78h+var_48], eax
0x18002079b  mov     r8d, eax
0x18002079e  lea     rdx, aRpcterminatese; "RpcTerminateSession threw an exception:"...
0x1800207a5  mov     ecx, 8; int
0x1800207aa  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800207af  nop
0x1800207b0  mov     ecx, ebx; int
0x1800207b2  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x1800207b7  mov     ecx, eax; dwErrCode
0x1800207b9  call    cs:__imp_SetLastError
0x1800207bf  test    ebx, ebx
0x1800207c1  setns   bl
0x1800207c4  lea     rcx, [rsp+78h+var_38]; this
0x1800207c9  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x1800207ce  mov     al, bl
0x1800207d0  mov     rcx, [rsp+78h+var_18]
0x1800207d5  xor     rcx, rsp; StackCookie
0x1800207d8  call    __security_check_cookie
0x1800207dd  mov     rbx, [rsp+78h+arg_8]
0x1800207e5  add     rsp, 70h
0x1800207e9  pop     rdi
0x1800207ea  retn
0x180030851  push    rbp
0x180030853  sub     rsp, 30h
0x180030857  mov     rbp, rdx
0x18003085a  mov     rcx, [rcx]
0x18003085d  mov     ecx, [rcx]; ExceptionCode
0x18003085f  call    cs:__imp_I_RpcExceptionFilter
0x180030865  nop
0x180030866  add     rsp, 30h
0x18003086a  pop     rbp
0x18003086b  retn
```
