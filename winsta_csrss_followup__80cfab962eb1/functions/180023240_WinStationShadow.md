# WinStationShadow

- ea: `0x180023240`
- end: `0x18002339a`
- name: `WinStationShadow`
- size: `346`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, __int16)`
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
- `0x180023240`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800232b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800232b4`
- `RPCRT4!NdrClientCall3` at `0x18002330e`
- `RPCRT4!NdrClientCall3` at `0x18002330e`

## string_xrefs

- `0x18002327b`: `Failed to open binding`

## pseudocode

```c
char __fastcall WinStationShadow(void *a1, __int64 a2, ULONG SessionId, unsigned __int8 a4, unsigned __int16 a5)
{
  int v5; // r14d
  char v9; // di
  DWORD v10; // ecx
  void *v11; // rax
  int Pointer; // ebx
  unsigned __int16 v14[28]; // [rsp+50h] [rbp-38h] BYREF

  v5 = a4;
  v9 = 0;
  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v14, a1, 1);
  if ( CSmartPublicBinding::operator void *(v14) )
  {
    if ( SessionId == -1 )
    {
      if ( !(unsigned int)IsLocalServer(a1) )
      {
        _DbgPrintMessage(4, "LOGONID_CURRENT specified for a remote server!");
        v10 = 87;
LABEL_6:
        SetLastError(v10);
        goto LABEL_11;
      }
      SessionId = NtCurrentPeb()->SessionId;
    }
    v11 = CSmartPublicBinding::operator void *(v14);
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&stru_180035078,
                              5u,
                              0,
                              v11,
                              a2,
                              SessionId,
                              v5,
                              a5).Pointer;
    if ( Pointer >= 0 )
    {
      v9 = 1;
      goto LABEL_11;
    }
    _DbgPrintMessage(8, "RpcShadow failed: 0x%x in %s", Pointer, "WinStationShadow");
    v10 = ConvertHRESULT2WIN32(Pointer);
    goto LABEL_6;
  }
  _DbgPrintMessage(8, "Failed to open binding");
LABEL_11:
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v14);
  return v9;
}

```

## disassembly

```asm
0x180023240  push    rbx
0x180023242  push    rsi
0x180023243  push    rdi
0x180023244  push    r14
0x180023246  push    r15
0x180023248  sub     rsp, 60h
0x18002324c  movzx   r14d, r9b
0x180023250  mov     ebx, r8d
0x180023253  mov     r15, rdx
0x180023256  mov     rsi, rcx
0x180023259  xor     edi, edi
0x18002325b  lea     r8d, [rdi+1]; int
0x18002325f  mov     rdx, rcx; void *
0x180023262  lea     rcx, [rsp+88h+var_38]; this
0x180023267  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x18002326c  lea     rcx, [rsp+88h+var_38]; unsigned __int16 *
0x180023271  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180023276  test    rax, rax
0x180023279  jnz     short loc_18002328F
0x18002327b  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x180023282  lea     ecx, [rdi+8]; int
0x180023285  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002328a  jmp     loc_180023380
0x18002328f  cmp     ebx, 0FFFFFFFFh
0x180023292  jnz     short loc_1800232D4
0x180023294  mov     rcx, rsi; void *
0x180023297  call    ?IsLocalServer@@YAHPEAX@Z; IsLocalServer(void *)
0x18002329c  test    eax, eax
0x18002329e  jnz     short loc_1800232C5
0x1800232a0  lea     rdx, aLogonidCurrent; "LOGONID_CURRENT specified for a remote "...
0x1800232a7  lea     ecx, [rax+4]; int
0x1800232aa  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800232af  mov     ecx, 57h ; 'W'; dwErrCode
0x1800232b4  call    cs:__imp_SetLastError
0x1800232bb  nop     dword ptr [rax+rax+00h]
0x1800232c0  jmp     loc_180023380
0x1800232c5  mov     rax, gs:60h
0x1800232ce  mov     ebx, [rax+2C0h]
0x1800232d4  lea     rcx, [rsp+88h+var_38]; unsigned __int16 *
0x1800232d9  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800232de  mov     [rsp+88h+var_40], rdi
0x1800232e3  movzx   ecx, [rsp+88h+arg_20]
0x1800232eb  mov     [rsp+88h+var_50], ecx
0x1800232ef  mov     [rsp+88h+var_58], r14d
0x1800232f4  mov     [rsp+88h+var_60], ebx
0x1800232f8  mov     [rsp+88h+var_68], r15
0x1800232fd  mov     r9, rax
0x180023300  xor     r8d, r8d; pReturnValue
0x180023303  lea     edx, [r8+5]; nProcNum
0x180023307  lea     rcx, stru_180035078; pProxyInfo
0x18002330e  call    cs:__imp_NdrClientCall3
0x180023315  nop     dword ptr [rax+rax+00h]
0x18002331a  mov     rbx, rax
0x18002331d  mov     [rsp+88h+var_40], rax
0x180023322  mov     [rsp+88h+var_48], eax
0x180023326  jmp     short loc_180023350
0x180023328  test    eax, eax
0x18002332a  jle     short loc_180023334
0x18002332c  movzx   eax, ax
0x18002332f  or      eax, 80070000h
0x180023334  mov     ebx, eax
0x180023336  mov     [rsp+88h+var_48], eax
0x18002333a  mov     r8d, eax
0x18002333d  lea     rdx, aRpcshadowThrew; "RpcShadow threw an exception: 0x%x"
0x180023344  mov     ecx, 8; int
0x180023349  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002334e  xor     edi, edi
0x180023350  test    ebx, ebx
0x180023352  jns     short loc_18002337D
0x180023354  lea     r9, aWinstationshad_10; "WinStationShadow"
0x18002335b  mov     r8d, ebx
0x18002335e  lea     rdx, aRpcshadowFaile; "RpcShadow failed: 0x%x in %s"
0x180023365  mov     ecx, 8; int
0x18002336a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002336f  mov     ecx, ebx; int
0x180023371  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180023376  mov     ecx, eax
0x180023378  jmp     loc_1800232B4
0x18002337d  mov     dil, 1
0x180023380  lea     rcx, [rsp+88h+var_38]; this
0x180023385  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18002338a  mov     al, dil
0x18002338d  add     rsp, 60h
0x180023391  pop     r15
0x180023393  pop     r14
0x180023395  pop     rdi
0x180023396  pop     rsi
0x180023397  pop     rbx
0x180023398  retn
0x18003377f  push    rbp
0x180033781  sub     rsp, 40h
0x180033785  mov     rbp, rdx
0x180033788  mov     rcx, [rcx]
0x18003378b  mov     ecx, [rcx]; ExceptionCode
0x18003378d  call    cs:__imp_I_RpcExceptionFilter
0x180033794  nop     dword ptr [rax+rax+00h]
0x180033799  nop
0x18003379a  add     rsp, 40h
0x18003379e  pop     rbp
0x18003379f  retn
```
