# WinStationTerminateGlassReplacementSession

- ea: `0x180021e40`
- end: `0x180021f9e`
- name: `WinStationTerminateGlassReplacementSession`
- size: `350`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800041a0`
- `0x180004558`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`
- `0x180021e40`
- `0x180032c20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021f65`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021f65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021e81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021e81`
- `RPCRT4!NdrClientCall3` at `0x180021efa`
- `RPCRT4!NdrClientCall3` at `0x180021efa`

## string_xrefs

- `0x180021ea0`: `WinStationTerminateGlassReplacementSession`
- `0x180021f16`: `WinStationTerminateGlassReplacementSession`

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
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180035260, 3u, 0, v4, v8, &v10).Pointer;
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
0x180021e40  mov     [rsp+arg_8], rbx
0x180021e45  push    rdi
0x180021e46  sub     rsp, 70h
0x180021e4a  mov     rax, cs:__security_cookie
0x180021e51  xor     rax, rsp
0x180021e54  mov     [rsp+78h+var_18], rax
0x180021e59  mov     edi, ecx
0x180021e5b  xorps   xmm0, xmm0
0x180021e5e  movups  [rsp+78h+var_28], xmm0
0x180021e63  xor     r8d, r8d; int
0x180021e66  xor     edx, edx; void *
0x180021e68  lea     rcx, [rsp+78h+var_38]; this
0x180021e6d  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x180021e72  lea     rcx, [rsp+78h+var_38]; unsigned __int16 *
0x180021e77  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180021e7c  test    rax, rax
0x180021e7f  jnz     short loc_180021EC0
0x180021e81  call    cs:__imp_GetLastError
0x180021e88  nop     dword ptr [rax+rax+00h]
0x180021e8d  mov     ebx, eax
0x180021e8f  test    eax, eax
0x180021e91  jle     short loc_180021E9C
0x180021e93  movzx   ebx, ax
0x180021e96  or      ebx, 80070000h
0x180021e9c  test    ebx, ebx
0x180021e9e  jns     short loc_180021EC0
0x180021ea0  lea     r9, aWinstationterm_1; "WinStationTerminateGlassReplacementSess"...
0x180021ea7  mov     r8d, ebx
0x180021eaa  lea     rdx, aBindNullFailed; "Bind( NULL ) failed: 0x%x in %s"
0x180021eb1  mov     ecx, 8; int
0x180021eb6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180021ebb  jmp     loc_180021F5C
0x180021ec0  xorps   xmm0, xmm0
0x180021ec3  movups  [rsp+78h+var_28], xmm0
0x180021ec8  lea     rcx, [rsp+78h+var_38]; unsigned __int16 *
0x180021ecd  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180021ed2  mov     [rsp+78h+var_40], 0
0x180021edb  lea     rcx, [rsp+78h+var_28]
0x180021ee0  mov     [rsp+78h+var_50], rcx
0x180021ee5  mov     [rsp+78h+var_58], edi
0x180021ee9  mov     r9, rax
0x180021eec  xor     r8d, r8d; pReturnValue
0x180021eef  lea     edx, [r8+3]; nProcNum
0x180021ef3  lea     rcx, stru_180035260; pProxyInfo
0x180021efa  call    cs:__imp_NdrClientCall3
0x180021f01  nop     dword ptr [rax+rax+00h]
0x180021f06  mov     rbx, rax
0x180021f09  mov     [rsp+78h+var_40], rax
0x180021f0e  mov     [rsp+78h+var_48], eax
0x180021f12  test    eax, eax
0x180021f14  jns     short loc_180021F33
0x180021f16  lea     r9, aWinstationterm_1; "WinStationTerminateGlassReplacementSess"...
0x180021f1d  mov     r8d, eax
0x180021f20  lea     rdx, aRpcterminatese_0; "RpcTerminateSession failed: 0x%x in %s"
0x180021f27  mov     ecx, 8; int
0x180021f2c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180021f31  jmp     short loc_180021F5C
0x180021f33  jmp     short loc_180021F5C
0x180021f35  test    eax, eax
0x180021f37  jle     short loc_180021F41
0x180021f39  movzx   eax, ax
0x180021f3c  or      eax, 80070000h
0x180021f41  mov     ebx, eax
0x180021f43  mov     [rsp+78h+var_48], eax
0x180021f47  mov     r8d, eax
0x180021f4a  lea     rdx, aRpcterminatese; "RpcTerminateSession threw an exception:"...
0x180021f51  mov     ecx, 8; int
0x180021f56  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180021f5b  nop
0x180021f5c  mov     ecx, ebx; int
0x180021f5e  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180021f63  mov     ecx, eax; dwErrCode
0x180021f65  call    cs:__imp_SetLastError
0x180021f6c  nop     dword ptr [rax+rax+00h]
0x180021f71  test    ebx, ebx
0x180021f73  setns   bl
0x180021f76  lea     rcx, [rsp+78h+var_38]; this
0x180021f7b  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180021f80  mov     al, bl
0x180021f82  mov     rcx, [rsp+78h+var_18]
0x180021f87  xor     rcx, rsp; StackCookie
0x180021f8a  call    __security_check_cookie
0x180021f8f  mov     rbx, [rsp+78h+arg_8]
0x180021f97  add     rsp, 70h
0x180021f9b  pop     rdi
0x180021f9c  retn
0x180033757  push    rbp
0x180033759  sub     rsp, 30h
0x18003375d  mov     rbp, rdx
0x180033760  mov     rcx, [rcx]
0x180033763  mov     ecx, [rcx]; ExceptionCode
0x180033765  call    cs:__imp_I_RpcExceptionFilter
0x18003376c  nop     dword ptr [rax+rax+00h]
0x180033771  nop
0x180033772  add     rsp, 30h
0x180033776  pop     rbp
0x180033777  retn
```
