# WinStationEnumerateContainerSessions

- ea: `0x18001fcb0`
- end: `0x18001fd95`
- name: `WinStationEnumerateContainerSessions`
- size: `229`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180005c30`
- `0x180005fcc`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x18001fcb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001fd6a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001fd6a`
- `RPCRT4!NdrClientCall3` at `0x18001fd22`
- `RPCRT4!NdrClientCall3` at `0x18001fd22`

## string_xrefs

- `0x18001fce3`: `Failed to open binding`

## pseudocode

```c
char __fastcall WinStationEnumerateContainerSessions(__int64 a1, __int64 a2)
{
  int Pointer; // ebx
  void *v5; // rax
  DWORD v6; // eax
  unsigned __int16 v8[16]; // [rsp+38h] [rbp-20h] BYREF

  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v8, 0, 0);
  if ( CSmartPublicBinding::operator void *(v8) )
  {
    v5 = CSmartPublicBinding::operator void *(v8);
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180032290, 6u, 0, v5, a1, a2).Pointer;
  }
  else
  {
    Pointer = -2147467263;
    _DbgPrintMessage(8, "Failed to open binding");
  }
  if ( Pointer >= 0 )
  {
    CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v8);
    return 1;
  }
  else
  {
    v6 = ConvertHRESULT2WIN32(Pointer);
    SetLastError(v6);
    CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v8);
    return 0;
  }
}

```

## disassembly

```asm
0x18001fcb0  mov     [rsp+arg_0], rbx
0x18001fcb5  push    rdi
0x18001fcb6  sub     rsp, 50h
0x18001fcba  mov     rbx, rdx
0x18001fcbd  mov     rdi, rcx
0x18001fcc0  xor     r8d, r8d; int
0x18001fcc3  xor     edx, edx; void *
0x18001fcc5  lea     rcx, [rsp+58h+var_20]; this
0x18001fcca  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x18001fccf  lea     rcx, [rsp+58h+var_20]; unsigned __int16 *
0x18001fcd4  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18001fcd9  test    rax, rax
0x18001fcdc  jnz     short loc_18001FCF4
0x18001fcde  mov     ebx, 80004001h
0x18001fce3  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x18001fcea  lea     ecx, [rax+8]; int
0x18001fced  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001fcf2  jmp     short loc_18001FD5D
0x18001fcf4  lea     rcx, [rsp+58h+var_20]; unsigned __int16 *
0x18001fcf9  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18001fcfe  mov     [rsp+58h+arg_10], 0
0x18001fd07  mov     [rsp+58h+var_30], rbx
0x18001fd0c  mov     [rsp+58h+var_38], rdi
0x18001fd11  mov     r9, rax
0x18001fd14  xor     r8d, r8d; pReturnValue
0x18001fd17  lea     edx, [r8+6]; nProcNum
0x18001fd1b  lea     rcx, stru_180032290; pProxyInfo
0x18001fd22  call    cs:__imp_NdrClientCall3
0x18001fd28  mov     rbx, rax
0x18001fd2b  mov     [rsp+58h+arg_10], rax
0x18001fd30  mov     [rsp+58h+var_28], eax
0x18001fd34  jmp     short loc_18001FD5D
0x18001fd36  test    eax, eax
0x18001fd38  jle     short loc_18001FD42
0x18001fd3a  movzx   eax, ax
0x18001fd3d  or      eax, 80070000h
0x18001fd42  mov     ebx, eax
0x18001fd44  mov     [rsp+58h+var_28], eax
0x18001fd48  mov     r8d, eax
0x18001fd4b  lea     rdx, aRpcenumcontain; "RpcEnumContainerSessions threw an excep"...
0x18001fd52  mov     ecx, 8; int
0x18001fd57  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001fd5c  nop
0x18001fd5d  test    ebx, ebx
0x18001fd5f  jns     short loc_18001FD7E
0x18001fd61  mov     ecx, ebx; int
0x18001fd63  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18001fd68  mov     ecx, eax; dwErrCode
0x18001fd6a  call    cs:__imp_SetLastError
0x18001fd70  lea     rcx, [rsp+58h+var_20]; this
0x18001fd75  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18001fd7a  xor     al, al
0x18001fd7c  jmp     short loc_18001FD8A
0x18001fd7e  lea     rcx, [rsp+58h+var_20]; this
0x18001fd83  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18001fd88  mov     al, 1
0x18001fd8a  mov     rbx, [rsp+58h+arg_0]
0x18001fd8f  add     rsp, 50h
0x18001fd93  pop     rdi
0x18001fd94  retn
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
