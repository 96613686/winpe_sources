# WinStationShadowStop

- ea: `0x180022430`
- end: `0x180022566`
- name: `WinStationShadowStop`
- size: `310`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180004554`
- `0x180005c30`
- `0x180005fcc`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x180022430`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002249f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002249f`
- `RPCRT4!NdrClientCall3` at `0x1800224dd`
- `RPCRT4!NdrClientCall3` at `0x1800224dd`

## string_xrefs

- `0x180022466`: `Failed to open binding`

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
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800320E0, 7u, 0, v6, SessionId).Pointer;
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
0x180022430  mov     [rsp+arg_0], rbx
0x180022435  mov     [rsp+arg_8], rsi
0x18002243a  push    rdi
0x18002243b  sub     rsp, 50h
0x18002243f  mov     ebx, edx
0x180022441  mov     rsi, rcx
0x180022444  xor     edi, edi
0x180022446  lea     r8d, [rdi+1]; int
0x18002244a  mov     rdx, rcx; void *
0x18002244d  lea     rcx, [rsp+58h+var_20]; this
0x180022452  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x180022457  lea     rcx, [rsp+58h+var_20]; unsigned __int16 *
0x18002245c  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180022461  test    rax, rax
0x180022464  jnz     short loc_18002247A
0x180022466  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x18002246d  lea     ecx, [rdi+8]; int
0x180022470  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180022475  jmp     loc_180022549
0x18002247a  cmp     ebx, 0FFFFFFFFh
0x18002247d  jnz     short loc_1800224B9
0x18002247f  mov     rcx, rsi; void *
0x180022482  call    ?IsLocalServer@@YAHPEAX@Z; IsLocalServer(void *)
0x180022487  test    eax, eax
0x180022489  jnz     short loc_1800224AA
0x18002248b  lea     rdx, aLogonidCurrent; "LOGONID_CURRENT specified for a remote "...
0x180022492  lea     ecx, [rax+4]; int
0x180022495  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002249a  mov     ecx, 57h ; 'W'; dwErrCode
0x18002249f  call    cs:__imp_SetLastError
0x1800224a5  jmp     loc_180022549
0x1800224aa  mov     rax, gs:60h
0x1800224b3  mov     ebx, [rax+2C0h]
0x1800224b9  lea     rcx, [rsp+58h+var_20]; unsigned __int16 *
0x1800224be  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800224c3  mov     [rsp+58h+arg_18], rdi
0x1800224c8  mov     [rsp+58h+var_38], ebx
0x1800224cc  mov     r9, rax
0x1800224cf  xor     r8d, r8d; pReturnValue
0x1800224d2  lea     edx, [r8+7]; nProcNum
0x1800224d6  lea     rcx, stru_1800320E0; pProxyInfo
0x1800224dd  call    cs:__imp_NdrClientCall3
0x1800224e3  mov     rbx, rax
0x1800224e6  mov     [rsp+58h+arg_18], rax
0x1800224eb  mov     [rsp+58h+var_28], eax
0x1800224ef  jmp     short loc_180022519
0x1800224f1  test    eax, eax
0x1800224f3  jle     short loc_1800224FD
0x1800224f5  movzx   eax, ax
0x1800224f8  or      eax, 80070000h
0x1800224fd  mov     ebx, eax
0x1800224ff  mov     [rsp+58h+var_28], eax
0x180022503  mov     r8d, eax
0x180022506  lea     rdx, aRpcshadowstopT; "RpcShadowStop threw an exception: 0x%x"
0x18002250d  mov     ecx, 8; int
0x180022512  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180022517  xor     edi, edi
0x180022519  test    ebx, ebx
0x18002251b  jns     short loc_180022546
0x18002251d  lea     r9, aWinstationshad_9; "WinStationShadowStop"
0x180022524  mov     r8d, ebx
0x180022527  lea     rdx, aSessionShadows; "Session.ShadowStop failed: 0x%x in %s"
0x18002252e  mov     ecx, 8; int
0x180022533  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180022538  mov     ecx, ebx; int
0x18002253a  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18002253f  mov     ecx, eax
0x180022541  jmp     loc_18002249F
0x180022546  mov     dil, 1
0x180022549  lea     rcx, [rsp+58h+var_20]; this
0x18002254e  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180022553  mov     al, dil
0x180022556  mov     rbx, [rsp+58h+arg_0]
0x18002255b  mov     rsi, [rsp+58h+arg_8]
0x180022560  add     rsp, 50h
0x180022564  pop     rdi
0x180022565  retn
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
