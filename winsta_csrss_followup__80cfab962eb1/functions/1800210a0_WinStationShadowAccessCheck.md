# WinStationShadowAccessCheck

- ea: `0x1800210a0`
- end: `0x1800211c1`
- name: `WinStationShadowAccessCheck`
- size: `289`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x1800041a0`
- `0x180004558`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`
- `0x1800210a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021191`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021191`
- `RPCRT4!NdrClientCall3` at `0x18002111f`
- `RPCRT4!NdrClientCall3` at `0x18002111f`

## string_xrefs

- `0x1800210d7`: `Failed to open binding`
- `0x180021151`: `RpcShadowAccessCheck threw an exception: 0x%x`
- `0x18002116d`: `WinStationShadowAccessCheck`
- `0x180021177`: `RpcShadowAccessCheck failed: 0x%x in %s`

## pseudocode

```c
char __fastcall WinStationShadowAccessCheck(int a1, _BYTE *a2)
{
  char v4; // di
  __int64 v5; // rax
  CLIENT_CALL_RETURN v6; // rbx
  DWORD v7; // eax
  int v9; // [rsp+20h] [rbp-48h]
  unsigned __int16 v10[24]; // [rsp+38h] [rbp-30h] BYREF
  char v11; // [rsp+80h] [rbp+18h] BYREF
  CLIENT_CALL_RETURN v12; // [rsp+88h] [rbp+20h]

  v4 = 0;
  v11 = 0;
  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v10, 0, 1);
  if ( CSmartPublicBinding::operator void *(v10) )
  {
    v5 = CSmartPublicBinding::operator void *(v10);
    v12.Simple = 0;
    v9 = a1;
    v6.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180035140, 9u, 0, v5, v9, &v11).Pointer;
    v12.Pointer = v6.Pointer;
    if ( SLODWORD(v6.Simple) >= 0 )
    {
      v4 = 1;
      *a2 = v11;
    }
    else
    {
      _DbgPrintMessage(8, "RpcShadowAccessCheck failed: 0x%x in %s", LODWORD(v6.Pointer), "WinStationShadowAccessCheck");
      v7 = ConvertHRESULT2WIN32(v6.Simple);
      SetLastError(v7);
    }
  }
  else
  {
    _DbgPrintMessage(8, "Failed to open binding");
  }
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v10);
  return v4;
}

```

## disassembly

```asm
0x1800210a0  mov     rax, rsp
0x1800210a3  mov     [rax+10h], rdx
0x1800210a7  push    rbx
0x1800210a8  push    rsi
0x1800210a9  push    rdi
0x1800210aa  sub     rsp, 50h
0x1800210ae  mov     rsi, rdx
0x1800210b1  mov     ebx, ecx
0x1800210b3  xor     edi, edi
0x1800210b5  mov     [rax+18h], dil
0x1800210b9  xor     edx, edx; void *
0x1800210bb  lea     r8d, [rdi+1]; int
0x1800210bf  lea     rcx, [rax-30h]; this
0x1800210c3  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x1800210c8  lea     rcx, [rsp+68h+var_30]; unsigned __int16 *
0x1800210cd  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800210d2  test    rax, rax
0x1800210d5  jnz     short loc_1800210EB
0x1800210d7  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x1800210de  lea     ecx, [rdi+8]; int
0x1800210e1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800210e6  jmp     loc_1800211AB
0x1800210eb  lea     rcx, [rsp+68h+var_30]; unsigned __int16 *
0x1800210f0  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800210f5  mov     [rsp+68h+arg_18], rdi
0x1800210fd  lea     rcx, [rsp+68h+arg_10]
0x180021105  mov     [rsp+68h+var_40], rcx
0x18002110a  mov     [rsp+68h+var_48], ebx
0x18002110e  mov     r9, rax
0x180021111  xor     r8d, r8d; pReturnValue
0x180021114  lea     edx, [r8+9]; nProcNum
0x180021118  lea     rcx, stru_180035140; pProxyInfo
0x18002111f  call    cs:__imp_NdrClientCall3
0x180021126  nop     dword ptr [rax+rax+00h]
0x18002112b  mov     rbx, rax
0x18002112e  mov     [rsp+68h+arg_18], rax
0x180021136  mov     [rsp+68h+var_38], eax
0x18002113a  jmp     short loc_180021169
0x18002113c  test    eax, eax
0x18002113e  jle     short loc_180021148
0x180021140  movzx   eax, ax
0x180021143  or      eax, 80070000h
0x180021148  mov     ebx, eax
0x18002114a  mov     [rsp+68h+var_38], eax
0x18002114e  mov     r8d, eax
0x180021151  lea     rdx, aRpcshadowacces_0; "RpcShadowAccessCheck threw an exception"...
0x180021158  mov     ecx, 8; int
0x18002115d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180021162  xor     edi, edi
0x180021164  mov     rsi, [rsp+68h+arg_8]
0x180021169  test    ebx, ebx
0x18002116b  jns     short loc_18002119F
0x18002116d  lea     r9, aWinstationshad_7; "WinStationShadowAccessCheck"
0x180021174  mov     r8d, ebx
0x180021177  lea     rdx, aRpcshadowacces; "RpcShadowAccessCheck failed: 0x%x in %s"
0x18002117e  mov     ecx, 8; int
0x180021183  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180021188  mov     ecx, ebx; int
0x18002118a  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18002118f  mov     ecx, eax; dwErrCode
0x180021191  call    cs:__imp_SetLastError
0x180021198  nop     dword ptr [rax+rax+00h]
0x18002119d  jmp     short loc_1800211AB
0x18002119f  mov     dil, 1
0x1800211a2  mov     cl, [rsp+68h+arg_10]
0x1800211a9  mov     [rsi], cl
0x1800211ab  lea     rcx, [rsp+68h+var_30]; this
0x1800211b0  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x1800211b5  mov     al, dil
0x1800211b8  add     rsp, 50h
0x1800211bc  pop     rdi
0x1800211bd  pop     rsi
0x1800211be  pop     rbx
0x1800211bf  retn
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
