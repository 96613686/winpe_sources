# WinStationShadowStop2

- ea: `0x180022ef0`
- end: `0x180022ff6`
- name: `WinStationShadowStop2`
- size: `262`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800041a0`
- `0x180004558`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`
- `0x180022ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022fcc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022fcc`
- `RPCRT4!NdrClientCall3` at `0x180022f62`
- `RPCRT4!NdrClientCall3` at `0x180022f62`

## string_xrefs

- `0x180022f1b`: `Failed to open binding`

## pseudocode

```c
char WinStationShadowStop2()
{
  char v0; // di
  ULONG SessionId; // ebx
  void *v2; // rax
  int Pointer; // ebx
  DWORD v4; // eax
  ULONG v6; // [rsp+20h] [rbp-38h]
  unsigned __int16 v7[16]; // [rsp+38h] [rbp-20h] BYREF

  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v7, 0, 1);
  v0 = 0;
  if ( CSmartPublicBinding::operator void *(v7) )
  {
    SessionId = NtCurrentPeb()->SessionId;
    v2 = CSmartPublicBinding::operator void *(v7);
    v6 = SessionId;
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180035140, 0xAu, 0, v2, v6).Pointer;
    if ( Pointer >= 0 )
    {
      v0 = 1;
    }
    else
    {
      _DbgPrintMessage(8, "RpcShadowStop2 failed: 0x%x in %s", Pointer, "WinStationShadowStop2");
      v4 = ConvertHRESULT2WIN32(Pointer);
      SetLastError(v4);
    }
  }
  else
  {
    _DbgPrintMessage(8, "Failed to open binding");
  }
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v7);
  return v0;
}

```

## disassembly

```asm
0x180022ef0  mov     [rsp+arg_8], rbx
0x180022ef5  push    rdi
0x180022ef6  sub     rsp, 50h
0x180022efa  xor     edx, edx; void *
0x180022efc  lea     r8d, [rdx+1]; int
0x180022f00  lea     rcx, [rsp+58h+var_20]; this
0x180022f05  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x180022f0a  lea     rcx, [rsp+58h+var_20]; unsigned __int16 *
0x180022f0f  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180022f14  xor     edi, edi
0x180022f16  test    rax, rax
0x180022f19  jnz     short loc_180022F2F
0x180022f1b  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x180022f22  lea     ecx, [rdi+8]; int
0x180022f25  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180022f2a  jmp     loc_180022FDD
0x180022f2f  mov     rax, gs:60h
0x180022f38  mov     ebx, [rax+2C0h]
0x180022f3e  lea     rcx, [rsp+58h+var_20]; unsigned __int16 *
0x180022f43  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180022f48  mov     [rsp+58h+arg_0], rdi
0x180022f4d  mov     [rsp+58h+var_38], ebx
0x180022f51  mov     r9, rax
0x180022f54  xor     r8d, r8d; pReturnValue
0x180022f57  lea     edx, [r8+0Ah]; nProcNum
0x180022f5b  lea     rcx, stru_180035140; pProxyInfo
0x180022f62  call    cs:__imp_NdrClientCall3
0x180022f69  nop     dword ptr [rax+rax+00h]
0x180022f6e  mov     rbx, rax
0x180022f71  mov     [rsp+58h+arg_0], rax
0x180022f76  mov     [rsp+58h+var_28], eax
0x180022f7a  jmp     short loc_180022FA4
0x180022f7c  test    eax, eax
0x180022f7e  jle     short loc_180022F88
0x180022f80  movzx   eax, ax
0x180022f83  or      eax, 80070000h
0x180022f88  mov     ebx, eax
0x180022f8a  mov     [rsp+58h+var_28], eax
0x180022f8e  mov     r8d, eax
0x180022f91  lea     rdx, aRpcshadowstop2_0; "RpcShadowStop2 threw an exception: 0x%x"
0x180022f98  mov     ecx, 8; int
0x180022f9d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180022fa2  xor     edi, edi
0x180022fa4  test    ebx, ebx
0x180022fa6  jns     short loc_180022FDA
0x180022fa8  lea     r9, aWinstationshad_6; "WinStationShadowStop2"
0x180022faf  mov     r8d, ebx
0x180022fb2  lea     rdx, aRpcshadowstop2; "RpcShadowStop2 failed: 0x%x in %s"
0x180022fb9  mov     ecx, 8; int
0x180022fbe  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180022fc3  mov     ecx, ebx; int
0x180022fc5  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180022fca  mov     ecx, eax; dwErrCode
0x180022fcc  call    cs:__imp_SetLastError
0x180022fd3  nop     dword ptr [rax+rax+00h]
0x180022fd8  jmp     short loc_180022FDD
0x180022fda  mov     dil, 1
0x180022fdd  lea     rcx, [rsp+58h+var_20]; this
0x180022fe2  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180022fe7  mov     al, dil
0x180022fea  mov     rbx, [rsp+58h+arg_8]
0x180022fef  add     rsp, 50h
0x180022ff3  pop     rdi
0x180022ff4  retn
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
