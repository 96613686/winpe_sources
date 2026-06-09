# CPublicBinding::OpenSessionContextHandle(void)

- ea: `0x180005374`
- end: `0x1800053ea`
- name: `?OpenSessionContextHandle@CPublicBinding@@AEAAJXZ`
- size: `118`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE *this)`
- caller_count: `16`
- callee_count: `4`
- tags: ``

## callers

- `0x180005c30`
- `0x180005db0`
- `0x1800063e0`
- `0x1800067b0`
- `0x180007d10`
- `0x1800083b0`
- `0x180008740`
- `0x1800094f0`
- `0x1800097b0`
- `0x180009da0`
- `0x18000a790`
- `0x18000aa20`
- `0x18000ad50`
- `0x18000b870`
- `0x18000c820`
- `0x18000dcc4`

## callees

- `0x180005374`
- `0x180007890`
- `0x180008f10`
- `0x180011368`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005390`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005390`
- `RPCRT4!I_RpcExceptionFilter` at `0x180030176`
- `RPCRT4!I_RpcExceptionFilter` at `0x180030176`

## string_xrefs

- `0x1800053d0`: `RpcOpenSession threw an exception: 0x%x`

## pseudocode

```c
__int64 __fastcall CPublicBinding::OpenSessionContextHandle(RPC_BINDING_HANDLE *this)
{
  signed int LastError; // eax
  unsigned int v3; // ebx

  if ( !*this )
    CPublicBinding::GetLSMBinding(this);
  if ( *this )
  {
    return (unsigned int)RpcOpenSession(*this, 0, this + 7);
  }
  else
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v3;
}

```

## disassembly

```asm
0x180005374  push    rbx
0x180005376  sub     rsp, 30h
0x18000537a  mov     rbx, rcx
0x18000537d  cmp     qword ptr [rcx], 0
0x180005381  jnz     short loc_180005388
0x180005383  call    ?GetLSMBinding@CPublicBinding@@QEAAPEAXXZ; CPublicBinding::GetLSMBinding(void)
0x180005388  mov     rcx, [rbx]
0x18000538b  test    rcx, rcx
0x18000538e  jnz     short loc_1800053A7
0x180005390  call    cs:__imp_GetLastError
0x180005396  mov     ebx, eax
0x180005398  test    eax, eax
0x18000539a  jle     short loc_1800053E2
0x18000539c  movzx   ebx, ax
0x18000539f  or      ebx, 80070000h
0x1800053a5  jmp     short loc_1800053E2
0x1800053a7  lea     r8, [rbx+38h]
0x1800053ab  xor     edx, edx
0x1800053ad  call    RpcOpenSession
0x1800053b2  mov     ebx, eax
0x1800053b4  mov     [rsp+38h+var_18], eax
0x1800053b8  jmp     short loc_1800053E2
0x1800053ba  mov     ebx, eax
0x1800053bc  test    eax, eax
0x1800053be  jle     short loc_1800053C9
0x1800053c0  movzx   ebx, ax
0x1800053c3  or      ebx, 80070000h
0x1800053c9  mov     [rsp+38h+var_18], ebx
0x1800053cd  mov     r8d, ebx
0x1800053d0  lea     rdx, aRpcopensession_0; "RpcOpenSession threw an exception: 0x%x"
0x1800053d7  mov     ecx, 8; int
0x1800053dc  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800053e1  nop
0x1800053e2  mov     eax, ebx
0x1800053e4  add     rsp, 30h
0x1800053e8  pop     rbx
0x1800053e9  retn
0x180030168  push    rbp
0x18003016a  sub     rsp, 20h
0x18003016e  mov     rbp, rdx
0x180030171  mov     rcx, [rcx]
0x180030174  mov     ecx, [rcx]; ExceptionCode
0x180030176  call    cs:__imp_I_RpcExceptionFilter
0x18003017c  nop
0x18003017d  add     rsp, 20h
0x180030181  pop     rbp
0x180030182  retn
```
