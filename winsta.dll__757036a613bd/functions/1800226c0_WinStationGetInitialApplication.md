# WinStationGetInitialApplication

- ea: `0x1800226c0`
- end: `0x1800227e8`
- name: `WinStationGetInitialApplication`
- size: `296`
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
- `0x1800226c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800227c4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800227c4`
- `RPCRT4!NdrClientCall3` at `0x180022760`
- `RPCRT4!NdrClientCall3` at `0x180022760`

## string_xrefs

- `0x1800226f8`: `Failed to open binding`

## pseudocode

```c
char __fastcall WinStationGetInitialApplication(ULONG SessionId, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  char v9; // di
  void *v10; // rax
  int Pointer; // ebx
  DWORD v12; // eax
  ULONG v14; // [rsp+20h] [rbp-78h]
  unsigned __int16 v15[28]; // [rsp+60h] [rbp-38h] BYREF

  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v15, 0, 1);
  v9 = 0;
  if ( CSmartPublicBinding::operator void *(v15) )
  {
    if ( SessionId == -1 )
      SessionId = NtCurrentPeb()->SessionId;
    v10 = CSmartPublicBinding::operator void *(v15);
    v14 = SessionId;
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180032140, 3u, 0, v10, v14, a2, a3, a4, a5).Pointer;
    if ( Pointer >= 0 )
    {
      v9 = 1;
    }
    else
    {
      _DbgPrintMessage(8, "RpcGetInitialApplication failed: 0x%x in %s", Pointer, "WinStationGetInitialApplication");
      v12 = ConvertHRESULT2WIN32(Pointer);
      SetLastError(v12);
    }
  }
  else
  {
    _DbgPrintMessage(8, "Failed to open binding");
  }
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v15);
  return v9;
}

```

## disassembly

```asm
0x1800226c0  push    rbx
0x1800226c2  push    rsi
0x1800226c3  push    rdi
0x1800226c4  push    r14
0x1800226c6  push    r15
0x1800226c8  sub     rsp, 70h
0x1800226cc  mov     rsi, r9
0x1800226cf  mov     r14, r8
0x1800226d2  mov     r15, rdx
0x1800226d5  mov     ebx, ecx
0x1800226d7  xor     edx, edx; void *
0x1800226d9  lea     r8d, [rdx+1]; int
0x1800226dd  lea     rcx, [rsp+98h+var_38]; this
0x1800226e2  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x1800226e7  lea     rcx, [rsp+98h+var_38]; unsigned __int16 *
0x1800226ec  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800226f1  xor     edi, edi
0x1800226f3  test    rax, rax
0x1800226f6  jnz     short loc_18002270C
0x1800226f8  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x1800226ff  lea     ecx, [rdi+8]; int
0x180022702  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180022707  jmp     loc_1800227CF
0x18002270c  cmp     ebx, 0FFFFFFFFh
0x18002270f  jnz     short loc_180022720
0x180022711  mov     rax, gs:60h
0x18002271a  mov     ebx, [rax+2C0h]
0x180022720  lea     rcx, [rsp+98h+var_38]; unsigned __int16 *
0x180022725  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002272a  mov     [rsp+98h+var_40], rdi
0x18002272f  mov     rcx, [rsp+98h+arg_20]
0x180022737  mov     [rsp+98h+var_58], rcx
0x18002273c  mov     [rsp+98h+var_60], rsi
0x180022741  mov     [rsp+98h+var_68], r14
0x180022746  mov     [rsp+98h+var_70], r15
0x18002274b  mov     [rsp+98h+var_78], ebx
0x18002274f  mov     r9, rax
0x180022752  xor     r8d, r8d; pReturnValue
0x180022755  lea     edx, [r8+3]; nProcNum
0x180022759  lea     rcx, stru_180032140; pProxyInfo
0x180022760  call    cs:__imp_NdrClientCall3
0x180022766  mov     rbx, rax
0x180022769  mov     [rsp+98h+var_40], rax
0x18002276e  mov     [rsp+98h+var_48], eax
0x180022772  jmp     short loc_18002279C
0x180022774  test    eax, eax
0x180022776  jle     short loc_180022780
0x180022778  movzx   eax, ax
0x18002277b  or      eax, 80070000h
0x180022780  mov     ebx, eax
0x180022782  mov     [rsp+98h+var_48], eax
0x180022786  mov     r8d, eax
0x180022789  lea     rdx, aRpcgetinitiala_0; "RpcGetInitialApplication threw an excep"...
0x180022790  mov     ecx, 8; int
0x180022795  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002279a  xor     edi, edi
0x18002279c  test    ebx, ebx
0x18002279e  jns     short loc_1800227CC
0x1800227a0  lea     r9, aWinstationgeti_0; "WinStationGetInitialApplication"
0x1800227a7  mov     r8d, ebx
0x1800227aa  lea     rdx, aRpcgetinitiala; "RpcGetInitialApplication failed: 0x%x i"...
0x1800227b1  mov     ecx, 8; int
0x1800227b6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800227bb  mov     ecx, ebx; int
0x1800227bd  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x1800227c2  mov     ecx, eax; dwErrCode
0x1800227c4  call    cs:__imp_SetLastError
0x1800227ca  jmp     short loc_1800227CF
0x1800227cc  mov     dil, 1
0x1800227cf  lea     rcx, [rsp+98h+var_38]; this
0x1800227d4  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x1800227d9  mov     al, dil
0x1800227dc  add     rsp, 70h
0x1800227e0  pop     r15
0x1800227e2  pop     r14
0x1800227e4  pop     rdi
0x1800227e5  pop     rsi
0x1800227e6  pop     rbx
0x1800227e7  retn
0x1800308b7  push    rbp
0x1800308b9  sub     rsp, 50h
0x1800308bd  mov     rbp, rdx
0x1800308c0  mov     rcx, [rcx]
0x1800308c3  mov     ecx, [rcx]; ExceptionCode
0x1800308c5  call    cs:__imp_I_RpcExceptionFilter
0x1800308cb  nop
0x1800308cc  add     rsp, 50h
0x1800308d0  pop     rbp
0x1800308d1  retn
```
