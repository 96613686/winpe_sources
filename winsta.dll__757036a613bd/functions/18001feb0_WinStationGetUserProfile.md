# WinStationGetUserProfile

- ea: `0x18001feb0`
- end: `0x18001ffb3`
- name: `WinStationGetUserProfile`
- size: `259`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180005c30`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x18001feb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff09`
- `RPCRT4!NdrClientCall3` at `0x18001ff5f`
- `RPCRT4!NdrClientCall3` at `0x18001ff5f`

## string_xrefs

- `0x18001fefa`: `Failed to open binding`

## pseudocode

```c
__int64 __fastcall WinStationGetUserProfile(__int64 a1, _QWORD *a2, _QWORD *a3, _QWORD *a4)
{
  signed int LastError; // eax
  unsigned int Pointer; // ebx
  void *v10; // rax
  unsigned __int16 v12[32]; // [rsp+48h] [rbp-40h] BYREF

  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v12, 0, 1);
  if ( CSmartPublicBinding::operator void *(v12) )
  {
    v10 = CSmartPublicBinding::operator void *(v12);
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180032170, 2u, 0, v10, a1, a2, a3, a4).Pointer;
  }
  else
  {
    _DbgPrintMessage(8, "Failed to open binding");
    LastError = GetLastError();
    Pointer = LastError;
    if ( LastError > 0 )
      Pointer = (unsigned __int16)LastError | 0x80070000;
  }
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v12);
  return Pointer;
}

```

## disassembly

```asm
0x18001feb0  push    rbx
0x18001feb2  push    rsi
0x18001feb3  push    rdi
0x18001feb4  push    r14
0x18001feb6  sub     rsp, 68h
0x18001feba  mov     rbx, r9
0x18001febd  mov     rdi, r8
0x18001fec0  mov     rsi, rdx
0x18001fec3  mov     r14, rcx
0x18001fec6  mov     qword ptr [rdx], 0
0x18001fecd  mov     qword ptr [r8], 0
0x18001fed4  mov     qword ptr [r9], 0
0x18001fedb  xor     edx, edx; void *
0x18001fedd  lea     r8d, [rdx+1]; int
0x18001fee1  lea     rcx, [rsp+88h+var_40]; this
0x18001fee6  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x18001feeb  lea     rcx, [rsp+88h+var_40]; unsigned __int16 *
0x18001fef0  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18001fef5  test    rax, rax
0x18001fef8  jnz     short loc_18001FF24
0x18001fefa  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x18001ff01  lea     ecx, [rax+8]; int
0x18001ff04  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001ff09  call    cs:__imp_GetLastError
0x18001ff0f  mov     ebx, eax
0x18001ff11  test    eax, eax
0x18001ff13  jle     loc_18001FF9D
0x18001ff19  movzx   ebx, ax
0x18001ff1c  or      ebx, 80070000h
0x18001ff22  jmp     short loc_18001FF9D
0x18001ff24  lea     rcx, [rsp+88h+var_40]; unsigned __int16 *
0x18001ff29  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18001ff2e  mov     [rsp+88h+arg_0], 0
0x18001ff3a  mov     [rsp+88h+var_50], rbx
0x18001ff3f  mov     [rsp+88h+var_58], rdi
0x18001ff44  mov     [rsp+88h+var_60], rsi
0x18001ff49  mov     [rsp+88h+var_68], r14
0x18001ff4e  mov     r9, rax
0x18001ff51  xor     r8d, r8d; pReturnValue
0x18001ff54  lea     edx, [r8+2]; nProcNum
0x18001ff58  lea     rcx, stru_180032170; pProxyInfo
0x18001ff5f  call    cs:__imp_NdrClientCall3
0x18001ff65  mov     rbx, rax
0x18001ff68  mov     [rsp+88h+arg_0], rax
0x18001ff70  mov     [rsp+88h+var_48], eax
0x18001ff74  jmp     short loc_18001FF9D
0x18001ff76  test    eax, eax
0x18001ff78  jle     short loc_18001FF82
0x18001ff7a  movzx   eax, ax
0x18001ff7d  or      eax, 80070000h
0x18001ff82  mov     ebx, eax
0x18001ff84  mov     [rsp+88h+var_48], eax
0x18001ff88  mov     r8d, eax
0x18001ff8b  lea     rdx, aRpcgetuserprof; "RpcGetUserProfile threw an exception: 0"...
0x18001ff92  mov     ecx, 8; int
0x18001ff97  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001ff9c  nop
0x18001ff9d  lea     rcx, [rsp+88h+var_40]; this
0x18001ffa2  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18001ffa7  mov     eax, ebx
0x18001ffa9  add     rsp, 68h
0x18001ffad  pop     r14
0x18001ffaf  pop     rdi
0x18001ffb0  pop     rsi
0x18001ffb1  pop     rbx
0x18001ffb2  retn
0x180030873  push    rbp
0x180030875  sub     rsp, 40h
0x180030879  mov     rbp, rdx
0x18003087c  mov     rcx, [rcx]
0x18003087f  mov     ecx, [rcx]; ExceptionCode
0x180030881  call    cs:__imp_I_RpcExceptionFilter
0x180030887  nop
0x180030888  add     rsp, 40h
0x18003088c  pop     rbp
0x18003088d  retn
```
