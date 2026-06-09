# WinStationShadowStop

- ea: `0x180023d20`
- end: `0x180023e63`
- name: `WinStationShadowStop`
- size: `323`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800041a0`
- `0x180004558`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`
- `0x18000a784`
- `0x180023d20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023d8f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023d8f`
- `RPCRT4!NdrClientCall3` at `0x180023dd3`
- `RPCRT4!NdrClientCall3` at `0x180023dd3`

## string_xrefs

- `0x180023d56`: `Failed to open binding`

## pseudocode

```c
char __fastcall WinStationShadowStop(void *a1, ULONG SessionId)
{
  char v4; // di
  DWORD v5; // ecx
  void *v6; // rax
  int Pointer; // ebx
  unsigned __int16 v9[16]; // [rsp+38h] [rbp-20h] BYREF

  v4 = 0;
  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v9, a1, 1);
  if ( CSmartPublicBinding::operator void *(v9) )
  {
    if ( SessionId == -1 )
    {
      if ( !(unsigned int)IsLocalServer(a1) )
      {
        _DbgPrintMessage(4, "LOGONID_CURRENT specified for a remote server!");
        v5 = 87;
LABEL_6:
        SetLastError(v5);
        goto LABEL_11;
      }
      SessionId = NtCurrentPeb()->SessionId;
    }
    v6 = CSmartPublicBinding::operator void *(v9);
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180035078, 7u, 0, v6, SessionId).Pointer;
    if ( Pointer >= 0 )
    {
      v4 = 1;
      goto LABEL_11;
    }
    _DbgPrintMessage(8, "Session.ShadowStop failed: 0x%x in %s", Pointer, "WinStationShadowStop");
    v5 = ConvertHRESULT2WIN32(Pointer);
    goto LABEL_6;
  }
  _DbgPrintMessage(8, "Failed to open binding");
LABEL_11:
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v9);
  return v4;
}

```

## disassembly

```asm
0x180023d20  mov     [rsp+arg_0], rbx
0x180023d25  mov     [rsp+arg_8], rsi
0x180023d2a  push    rdi
0x180023d2b  sub     rsp, 50h
0x180023d2f  mov     ebx, edx
0x180023d31  mov     rsi, rcx
0x180023d34  xor     edi, edi
0x180023d36  lea     r8d, [rdi+1]; int
0x180023d3a  mov     rdx, rcx; void *
0x180023d3d  lea     rcx, [rsp+58h+var_20]; this
0x180023d42  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x180023d47  lea     rcx, [rsp+58h+var_20]; unsigned __int16 *
0x180023d4c  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180023d51  test    rax, rax
0x180023d54  jnz     short loc_180023D6A
0x180023d56  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x180023d5d  lea     ecx, [rdi+8]; int
0x180023d60  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180023d65  jmp     loc_180023E45
0x180023d6a  cmp     ebx, 0FFFFFFFFh
0x180023d6d  jnz     short loc_180023DAF
0x180023d6f  mov     rcx, rsi; void *
0x180023d72  call    ?IsLocalServer@@YAHPEAX@Z; IsLocalServer(void *)
0x180023d77  test    eax, eax
0x180023d79  jnz     short loc_180023DA0
0x180023d7b  lea     rdx, aLogonidCurrent; "LOGONID_CURRENT specified for a remote "...
0x180023d82  lea     ecx, [rax+4]; int
0x180023d85  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180023d8a  mov     ecx, 57h ; 'W'; dwErrCode
0x180023d8f  call    cs:__imp_SetLastError
0x180023d96  nop     dword ptr [rax+rax+00h]
0x180023d9b  jmp     loc_180023E45
0x180023da0  mov     rax, gs:60h
0x180023da9  mov     ebx, [rax+2C0h]
0x180023daf  lea     rcx, [rsp+58h+var_20]; unsigned __int16 *
0x180023db4  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180023db9  mov     [rsp+58h+arg_18], rdi
0x180023dbe  mov     [rsp+58h+var_38], ebx
0x180023dc2  mov     r9, rax
0x180023dc5  xor     r8d, r8d; pReturnValue
0x180023dc8  lea     edx, [r8+7]; nProcNum
0x180023dcc  lea     rcx, stru_180035078; pProxyInfo
0x180023dd3  call    cs:__imp_NdrClientCall3
0x180023dda  nop     dword ptr [rax+rax+00h]
0x180023ddf  mov     rbx, rax
0x180023de2  mov     [rsp+58h+arg_18], rax
0x180023de7  mov     [rsp+58h+var_28], eax
0x180023deb  jmp     short loc_180023E15
0x180023ded  test    eax, eax
0x180023def  jle     short loc_180023DF9
0x180023df1  movzx   eax, ax
0x180023df4  or      eax, 80070000h
0x180023df9  mov     ebx, eax
0x180023dfb  mov     [rsp+58h+var_28], eax
0x180023dff  mov     r8d, eax
0x180023e02  lea     rdx, aRpcshadowstopT; "RpcShadowStop threw an exception: 0x%x"
0x180023e09  mov     ecx, 8; int
0x180023e0e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180023e13  xor     edi, edi
0x180023e15  test    ebx, ebx
0x180023e17  jns     short loc_180023E42
0x180023e19  lea     r9, aWinstationshad_9; "WinStationShadowStop"
0x180023e20  mov     r8d, ebx
0x180023e23  lea     rdx, aSessionShadows; "Session.ShadowStop failed: 0x%x in %s"
0x180023e2a  mov     ecx, 8; int
0x180023e2f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180023e34  mov     ecx, ebx; int
0x180023e36  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180023e3b  mov     ecx, eax
0x180023e3d  jmp     loc_180023D8F
0x180023e42  mov     dil, 1
0x180023e45  lea     rcx, [rsp+58h+var_20]; this
0x180023e4a  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180023e4f  mov     al, dil
0x180023e52  mov     rbx, [rsp+58h+arg_0]
0x180023e57  mov     rsi, [rsp+58h+arg_8]
0x180023e5c  add     rsp, 50h
0x180023e60  pop     rdi
0x180023e61  retn
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
