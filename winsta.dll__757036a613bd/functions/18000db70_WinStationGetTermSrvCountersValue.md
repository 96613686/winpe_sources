# WinStationGetTermSrvCountersValue

- ea: `0x18000db70`
- end: `0x18000dcbb`
- name: `WinStationGetTermSrvCountersValue`
- size: `331`
- prototype: `__int64 __fastcall(CPublicBinding *this, unsigned int, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000d51c`

## callees

- `0x180005c30`
- `0x180005fcc`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x18000db70`
- `0x18002ca70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dcb1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dcb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dc85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dc85`
- `RPCRT4!I_RpcExceptionFilter` at `0x180030590`
- `RPCRT4!I_RpcExceptionFilter` at `0x180030590`
- `RPCRT4!NdrClientCall3` at `0x18000dbe3`
- `RPCRT4!NdrClientCall3` at `0x18000dbe3`

## string_xrefs

- `0x18000dc5e`: `Failed to open binding`

## pseudocode

```c
unsigned __int8 __fastcall WinStationGetTermSrvCountersValue(CPublicBinding *this, unsigned int a2, void *a3)
{
  void *v6; // rax
  int Pointer; // ebx
  unsigned __int8 TermSrvCountersValue; // bl
  DWORD v10; // eax
  unsigned __int16 v11[32]; // [rsp+38h] [rbp-40h] BYREF

  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v11, this, 0);
  if ( CSmartPublicBinding::operator void *(v11) )
  {
    v6 = CSmartPublicBinding::operator void *(v11);
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180032200, 0xBu, 0, v6, a3, a2).Pointer;
    if ( Pointer == -2147023174 )
    {
      TermSrvCountersValue = Legacy_WinStationGetTermSrvCountersValue(this, a2, a3);
      if ( !TermSrvCountersValue )
        GetLastError();
    }
    else if ( Pointer < 0 )
    {
      _DbgPrintMessage(8, "RpcGetSessionCounters failed: 0x%x in %s", Pointer, "WinStationGetTermSrvCountersValue");
      v10 = ConvertHRESULT2WIN32(Pointer);
      SetLastError(v10);
      TermSrvCountersValue = 0;
    }
    else
    {
      TermSrvCountersValue = 1;
    }
  }
  else
  {
    TermSrvCountersValue = 0;
    _DbgPrintMessage(8, "Failed to open binding");
  }
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v11);
  return TermSrvCountersValue;
}

```

## disassembly

```asm
0x18000db70  mov     rax, rsp
0x18000db73  mov     [rax+18h], r8
0x18000db77  mov     [rax+10h], edx
0x18000db7a  mov     [rax+8], rcx
0x18000db7e  push    rbx
0x18000db7f  push    rsi
0x18000db80  push    rdi
0x18000db81  push    r14
0x18000db83  sub     rsp, 58h
0x18000db87  mov     rsi, r8
0x18000db8a  mov     r14d, edx
0x18000db8d  mov     rdi, rcx
0x18000db90  xor     r8d, r8d; int
0x18000db93  mov     rdx, rcx; void *
0x18000db96  lea     rcx, [rax-40h]; this
0x18000db9a  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x18000db9f  lea     rcx, [rsp+78h+var_40]; unsigned __int16 *
0x18000dba4  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18000dba9  test    rax, rax
0x18000dbac  jz      loc_18000DC5C
0x18000dbb2  lea     rcx, [rsp+78h+var_40]; unsigned __int16 *
0x18000dbb7  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18000dbbc  mov     [rsp+78h+arg_18], 0
0x18000dbc8  mov     [rsp+78h+var_50], r14d
0x18000dbcd  mov     [rsp+78h+var_58], rsi
0x18000dbd2  mov     r9, rax
0x18000dbd5  xor     r8d, r8d; pReturnValue
0x18000dbd8  lea     edx, [r8+0Bh]; nProcNum
0x18000dbdc  lea     rcx, stru_180032200; pProxyInfo
0x18000dbe3  call    cs:__imp_NdrClientCall3
0x18000dbe9  mov     rbx, rax
0x18000dbec  mov     [rsp+78h+arg_18], rax
0x18000dbf4  mov     [rsp+78h+var_48], eax
0x18000dbf8  jmp     short loc_18000DC38
0x18000dbfa  test    eax, eax
0x18000dbfc  jle     short loc_18000DC06
0x18000dbfe  movzx   eax, ax
0x18000dc01  or      eax, 80070000h
0x18000dc06  mov     ebx, eax
0x18000dc08  mov     [rsp+78h+var_48], eax
0x18000dc0c  mov     r8d, eax
0x18000dc0f  lea     rdx, aRpcgetsessionc_0; "RpcGetSessionCounters threw an exceptio"...
0x18000dc16  mov     ecx, 8; int
0x18000dc1b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000dc20  mov     rsi, [rsp+78h+arg_10]
0x18000dc28  mov     r14d, [rsp+78h+arg_8]
0x18000dc30  mov     rdi, [rsp+78h+arg_0]
0x18000dc38  cmp     ebx, 800706BAh
0x18000dc3e  jz      short loc_18000DC71
0x18000dc40  test    ebx, ebx
0x18000dc42  js      short loc_18000DC8D
0x18000dc44  mov     bl, 1
0x18000dc46  lea     rcx, [rsp+78h+var_40]; this
0x18000dc4b  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18000dc50  mov     al, bl
0x18000dc52  add     rsp, 58h
0x18000dc56  pop     r14
0x18000dc58  pop     rdi
0x18000dc59  pop     rsi
0x18000dc5a  pop     rbx
0x18000dc5b  retn
0x18000dc5c  xor     bl, bl
0x18000dc5e  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x18000dc65  mov     ecx, 8; int
0x18000dc6a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000dc6f  jmp     short loc_18000DC46
0x18000dc71  mov     r8, rsi; void *
0x18000dc74  mov     edx, r14d; unsigned int
0x18000dc77  mov     rcx, rdi; this
0x18000dc7a  call    ?Legacy_WinStationGetTermSrvCountersValue@@YAEPEAXK0@Z; Legacy_WinStationGetTermSrvCountersValue(void *,ulong,void *)
0x18000dc7f  mov     bl, al
0x18000dc81  test    al, al
0x18000dc83  jnz     short loc_18000DC46
0x18000dc85  call    cs:__imp_GetLastError
0x18000dc8b  jmp     short loc_18000DC46
0x18000dc8d  lea     r9, aWinstationgett_0; "WinStationGetTermSrvCountersValue"
0x18000dc94  mov     r8d, ebx
0x18000dc97  lea     rdx, aRpcgetsessionc; "RpcGetSessionCounters failed: 0x%x in %"...
0x18000dc9e  mov     ecx, 8; int
0x18000dca3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000dca8  mov     ecx, ebx; int
0x18000dcaa  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18000dcaf  mov     ecx, eax; dwErrCode
0x18000dcb1  call    cs:__imp_SetLastError
0x18000dcb7  xor     bl, bl
0x18000dcb9  jmp     short loc_18000DC46
0x180030582  push    rbp
0x180030584  sub     rsp, 30h
0x180030588  mov     rbp, rdx
0x18003058b  mov     rcx, [rcx]
0x18003058e  mov     ecx, [rcx]; ExceptionCode
0x180030590  call    cs:__imp_I_RpcExceptionFilter
0x180030596  nop
0x180030597  add     rsp, 30h
0x18003059b  pop     rbp
0x18003059c  retn
```
