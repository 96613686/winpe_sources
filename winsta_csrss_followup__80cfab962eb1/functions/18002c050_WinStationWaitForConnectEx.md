# _WinStationWaitForConnectEx

- ea: `0x18002c050`
- end: `0x18002c14f`
- name: `_WinStationWaitForConnectEx`
- size: `255`
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
- `0x18000e2c0`
- `0x18002c050`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c125`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c125`
- `RPCRT4!NdrClientCall3` at `0x18002c0bb`
- `RPCRT4!NdrClientCall3` at `0x18002c0bb`

## string_xrefs

- `0x18002c082`: `Failed to open binding`

## pseudocode

```c
char __fastcall WinStationWaitForConnectEx(__int64 a1)
{
  char v2; // di
  void *v3; // rax
  int Pointer; // ebx
  DWORD v5; // eax
  unsigned __int16 v7[12]; // [rsp+40h] [rbp-18h] BYREF

  WaitForLsmStart();
  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v7, 0, 0);
  v2 = 0;
  if ( CSmartPublicBinding::operator void *(v7) )
  {
    v3 = CSmartPublicBinding::operator void *(v7);
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800351D0, 2u, 0, v3, a1).Pointer;
    if ( Pointer >= 0 )
    {
      v2 = 1;
    }
    else
    {
      _DbgPrintMessage(8, "RpcConnectTerminal failed: 0x%x in %s", Pointer, "_WinStationWaitForConnectEx");
      v5 = ConvertHRESULT2WIN32(Pointer);
      SetLastError(v5);
    }
  }
  else
  {
    _DbgPrintMessage(8, "Failed to open binding");
  }
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v7);
  return v2;
}

```

## disassembly

```asm
0x18002c050  mov     [rsp+arg_8], rbx
0x18002c055  push    rdi
0x18002c056  sub     rsp, 50h
0x18002c05a  mov     rbx, rcx
0x18002c05d  call    ?WaitForLsmStart@@YAHXZ; WaitForLsmStart(void)
0x18002c062  xor     r8d, r8d; int
0x18002c065  xor     edx, edx; void *
0x18002c067  lea     rcx, [rsp+58h+var_18]; this
0x18002c06c  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x18002c071  lea     rcx, [rsp+58h+var_18]; unsigned __int16 *
0x18002c076  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002c07b  xor     edi, edi
0x18002c07d  test    rax, rax
0x18002c080  jnz     short loc_18002C096
0x18002c082  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x18002c089  lea     ecx, [rdi+8]; int
0x18002c08c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002c091  jmp     loc_18002C136
0x18002c096  lea     rcx, [rsp+58h+var_18]; unsigned __int16 *
0x18002c09b  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002c0a0  mov     [rsp+58h+var_20], rdi
0x18002c0a5  mov     [rsp+58h+var_38], rbx
0x18002c0aa  mov     r9, rax
0x18002c0ad  xor     r8d, r8d; pReturnValue
0x18002c0b0  lea     edx, [r8+2]; nProcNum
0x18002c0b4  lea     rcx, stru_1800351D0; pProxyInfo
0x18002c0bb  call    cs:__imp_NdrClientCall3
0x18002c0c2  nop     dword ptr [rax+rax+00h]
0x18002c0c7  mov     rbx, rax
0x18002c0ca  mov     [rsp+58h+var_20], rax
0x18002c0cf  mov     [rsp+58h+var_28], eax
0x18002c0d3  jmp     short loc_18002C0FD
0x18002c0d5  test    eax, eax
0x18002c0d7  jle     short loc_18002C0E1
0x18002c0d9  movzx   eax, ax
0x18002c0dc  or      eax, 80070000h
0x18002c0e1  mov     ebx, eax
0x18002c0e3  mov     [rsp+58h+var_28], eax
0x18002c0e7  mov     r8d, eax
0x18002c0ea  lea     rdx, aRpcconnectterm_0; "RpcConnectTerminal threw an exception: "...
0x18002c0f1  mov     ecx, 8; int
0x18002c0f6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002c0fb  xor     edi, edi
0x18002c0fd  test    ebx, ebx
0x18002c0ff  jns     short loc_18002C133
0x18002c101  lea     r9, aWinstationwait_3; "_WinStationWaitForConnectEx"
0x18002c108  mov     r8d, ebx
0x18002c10b  lea     rdx, aRpcconnectterm; "RpcConnectTerminal failed: 0x%x in %s"
0x18002c112  mov     ecx, 8; int
0x18002c117  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002c11c  mov     ecx, ebx; int
0x18002c11e  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18002c123  mov     ecx, eax; dwErrCode
0x18002c125  call    cs:__imp_SetLastError
0x18002c12c  nop     dword ptr [rax+rax+00h]
0x18002c131  jmp     short loc_18002C136
0x18002c133  mov     dil, 1
0x18002c136  lea     rcx, [rsp+58h+var_18]; this
0x18002c13b  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18002c140  mov     al, dil
0x18002c143  mov     rbx, [rsp+58h+arg_8]
0x18002c148  add     rsp, 50h
0x18002c14c  pop     rdi
0x18002c14d  retn
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
