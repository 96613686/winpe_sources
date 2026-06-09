# CPublicBinding::OpenSessionContextHandle(void)

- ea: `0x1800032b4`
- end: `0x180003331`
- name: `?OpenSessionContextHandle@CPublicBinding@@AEAAJXZ`
- size: `125`
- prototype: `__int64 __fastcall(CPublicBinding *__hidden this)`
- caller_count: `16`
- callee_count: `4`
- tags: ``

## callers

- `0x1800016c8`
- `0x180001a10`
- `0x180003480`
- `0x1800041a0`
- `0x180004330`
- `0x1800049a0`
- `0x180006000`
- `0x180006740`
- `0x180006b20`
- `0x180006ed0`
- `0x180007d20`
- `0x180007fe0`
- `0x180008640`
- `0x1800090a0`
- `0x180009350`
- `0x1800096c0`

## callees

- `0x180001694`
- `0x1800032b4`
- `0x180005b40`
- `0x180007690`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800032d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800032d0`
- `RPCRT4!I_RpcExceptionFilter` at `0x180032e81`
- `RPCRT4!I_RpcExceptionFilter` at `0x180032e81`

## string_xrefs

- `0x180003316`: `RpcOpenSession threw an exception: 0x%x`

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
0x1800032b4  push    rbx
0x1800032b6  sub     rsp, 30h
0x1800032ba  mov     rbx, rcx
0x1800032bd  cmp     qword ptr [rcx], 0
0x1800032c1  jnz     short loc_1800032C8
0x1800032c3  call    ?GetLSMBinding@CPublicBinding@@QEAAPEAXXZ; CPublicBinding::GetLSMBinding(void)
0x1800032c8  mov     rcx, [rbx]
0x1800032cb  test    rcx, rcx
0x1800032ce  jnz     short loc_1800032ED
0x1800032d0  call    cs:__imp_GetLastError
0x1800032d7  nop     dword ptr [rax+rax+00h]
0x1800032dc  mov     ebx, eax
0x1800032de  test    eax, eax
0x1800032e0  jle     short loc_180003328
0x1800032e2  movzx   ebx, ax
0x1800032e5  or      ebx, 80070000h
0x1800032eb  jmp     short loc_180003328
0x1800032ed  lea     r8, [rbx+38h]
0x1800032f1  xor     edx, edx
0x1800032f3  call    RpcOpenSession
0x1800032f8  mov     ebx, eax
0x1800032fa  mov     [rsp+38h+var_18], eax
0x1800032fe  jmp     short loc_180003328
0x180003300  mov     ebx, eax
0x180003302  test    eax, eax
0x180003304  jle     short loc_18000330F
0x180003306  movzx   ebx, ax
0x180003309  or      ebx, 80070000h
0x18000330f  mov     [rsp+38h+var_18], ebx
0x180003313  mov     r8d, ebx
0x180003316  lea     rdx, aRpcopensession_0; "RpcOpenSession threw an exception: 0x%x"
0x18000331d  mov     ecx, 8; int
0x180003322  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180003327  nop
0x180003328  mov     eax, ebx
0x18000332a  add     rsp, 30h
0x18000332e  pop     rbx
0x18000332f  retn
0x180032e73  push    rbp
0x180032e75  sub     rsp, 20h
0x180032e79  mov     rbp, rdx
0x180032e7c  mov     rcx, [rcx]
0x180032e7f  mov     ecx, [rcx]; ExceptionCode
0x180032e81  call    cs:__imp_I_RpcExceptionFilter
0x180032e88  nop     dword ptr [rax+rax+00h]
0x180032e8d  nop
0x180032e8e  add     rsp, 20h
0x180032e92  pop     rbp
0x180032e93  retn
```
