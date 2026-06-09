# WinStationGetRedirectAuthInfo

- ea: `0x180021290`
- end: `0x180021395`
- name: `WinStationGetRedirectAuthInfo`
- size: `261`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180005c30`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x180021290`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800212d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800212d4`
- `RPCRT4!NdrClientCall3` at `0x180021344`
- `RPCRT4!NdrClientCall3` at `0x180021344`

## string_xrefs

- `0x1800212c5`: `Failed to open binding`

## pseudocode

```c
__int64 __fastcall WinStationGetRedirectAuthInfo(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  signed int LastError; // eax
  unsigned int Pointer; // ebx
  void *v12; // rax
  unsigned __int16 v14[28]; // [rsp+60h] [rbp-38h] BYREF

  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v14, 0, 1);
  if ( CSmartPublicBinding::operator void *(v14) )
  {
    v12 = CSmartPublicBinding::operator void *(v14);
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&stru_180032170,
                              8u,
                              0,
                              v12,
                              a1,
                              a2,
                              a3,
                              a4,
                              a5,
                              a6).Pointer;
  }
  else
  {
    _DbgPrintMessage(8, "Failed to open binding");
    LastError = GetLastError();
    Pointer = LastError;
    if ( LastError > 0 )
      Pointer = (unsigned __int16)LastError | 0x80070000;
  }
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v14);
  return Pointer;
}

```

## disassembly

```asm
0x180021290  push    rbx
0x180021292  push    rsi
0x180021293  push    rdi
0x180021294  push    r14
0x180021296  sub     rsp, 78h
0x18002129a  mov     rbx, r9
0x18002129d  mov     rdi, r8
0x1800212a0  mov     rsi, rdx
0x1800212a3  mov     r14, rcx
0x1800212a6  xor     edx, edx; void *
0x1800212a8  lea     r8d, [rdx+1]; int
0x1800212ac  lea     rcx, [rsp+98h+var_38]; this
0x1800212b1  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x1800212b6  lea     rcx, [rsp+98h+var_38]; unsigned __int16 *
0x1800212bb  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800212c0  test    rax, rax
0x1800212c3  jnz     short loc_1800212F2
0x1800212c5  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x1800212cc  lea     ecx, [rax+8]; int
0x1800212cf  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800212d4  call    cs:__imp_GetLastError
0x1800212da  mov     ebx, eax
0x1800212dc  test    eax, eax
0x1800212de  jle     loc_18002137F
0x1800212e4  movzx   ebx, ax
0x1800212e7  or      ebx, 80070000h
0x1800212ed  jmp     loc_18002137F
0x1800212f2  lea     rcx, [rsp+98h+var_38]; unsigned __int16 *
0x1800212f7  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800212fc  mov     [rsp+98h+var_40], 0
0x180021305  mov     rcx, [rsp+98h+arg_28]
0x18002130d  mov     [rsp+98h+var_50], rcx
0x180021312  mov     rcx, [rsp+98h+arg_20]
0x18002131a  mov     [rsp+98h+var_58], rcx
0x18002131f  mov     [rsp+98h+var_60], rbx
0x180021324  mov     [rsp+98h+var_68], rdi
0x180021329  mov     [rsp+98h+var_70], rsi
0x18002132e  mov     [rsp+98h+var_78], r14
0x180021333  mov     r9, rax
0x180021336  xor     r8d, r8d; pReturnValue
0x180021339  lea     edx, [r8+8]; nProcNum
0x18002133d  lea     rcx, stru_180032170; pProxyInfo
0x180021344  call    cs:__imp_NdrClientCall3
0x18002134a  mov     rbx, rax
0x18002134d  mov     [rsp+98h+var_40], rax
0x180021352  mov     [rsp+98h+var_48], eax
0x180021356  jmp     short loc_18002137F
0x180021358  test    eax, eax
0x18002135a  jle     short loc_180021364
0x18002135c  movzx   eax, ax
0x18002135f  or      eax, 80070000h
0x180021364  mov     ebx, eax
0x180021366  mov     [rsp+98h+var_48], eax
0x18002136a  mov     r8d, eax
0x18002136d  lea     rdx, aRpcgetredirect; "RpcGetRedirectAuthInfo threw an excepti"...
0x180021374  mov     ecx, 8; int
0x180021379  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002137e  nop
0x18002137f  lea     rcx, [rsp+98h+var_38]; this
0x180021384  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180021389  mov     eax, ebx
0x18002138b  add     rsp, 78h
0x18002138f  pop     r14
0x180021391  pop     rdi
0x180021392  pop     rsi
0x180021393  pop     rbx
0x180021394  retn
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
