# WinStationReportUIResult

- ea: `0x18002bf50`
- end: `0x18002c02a`
- name: `WinStationReportUIResult`
- size: `218`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800041a0`
- `0x180004558`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`
- `0x18002bf50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bf9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bf9c`
- `RPCRT4!NdrClientCall3` at `0x18002bfe7`
- `RPCRT4!NdrClientCall3` at `0x18002bfe7`

## string_xrefs

- `0x18002bf8d`: `Failed to open binding`

## pseudocode

```c
__int64 __fastcall WinStationReportUIResult(__int64 a1, unsigned int a2, unsigned int a3)
{
  DWORD LastError; // ebx
  void *v7; // rax
  int Pointer; // [rsp+38h] [rbp-20h]
  unsigned __int16 v10[12]; // [rsp+40h] [rbp-18h] BYREF
  unsigned __int64 v11; // [rsp+78h] [rbp+20h] BYREF

  v11 = 0;
  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v10, 0, 0);
  if ( CSmartPublicBinding::operator void *(v10) )
  {
    v11 = __PAIR64__(a3, a2);
    v7 = CSmartPublicBinding::operator void *(v10);
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800351D0, 6u, 0, v7, a1, &v11).Pointer;
    LastError = ConvertHRESULT2WIN32(Pointer);
  }
  else
  {
    _DbgPrintMessage(8, "Failed to open binding");
    LastError = GetLastError();
  }
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v10);
  return LastError;
}

```

## disassembly

```asm
0x18002bf50  mov     rax, rsp
0x18002bf53  mov     [rax+8], rbx
0x18002bf57  mov     [rax+10h], rsi
0x18002bf5b  push    rdi
0x18002bf5c  sub     rsp, 50h
0x18002bf60  mov     ebx, r8d
0x18002bf63  mov     edi, edx
0x18002bf65  mov     rsi, rcx
0x18002bf68  mov     qword ptr [rax+20h], 0
0x18002bf70  xor     r8d, r8d; int
0x18002bf73  xor     edx, edx; void *
0x18002bf75  lea     rcx, [rax-18h]; this
0x18002bf79  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x18002bf7e  lea     rcx, [rsp+58h+var_18]; unsigned __int16 *
0x18002bf83  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002bf88  test    rax, rax
0x18002bf8b  jnz     short loc_18002BFAC
0x18002bf8d  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x18002bf94  lea     ecx, [rax+8]; int
0x18002bf97  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002bf9c  call    cs:__imp_GetLastError
0x18002bfa3  nop     dword ptr [rax+rax+00h]
0x18002bfa8  mov     ebx, eax
0x18002bfaa  jmp     short loc_18002C00D
0x18002bfac  mov     [rsp+58h+arg_18], edi
0x18002bfb0  mov     [rsp+58h+arg_1C], ebx
0x18002bfb4  lea     rcx, [rsp+58h+var_18]; unsigned __int16 *
0x18002bfb9  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002bfbe  mov     [rsp+58h+var_20], 0
0x18002bfc7  lea     rcx, [rsp+58h+arg_18]
0x18002bfcc  mov     [rsp+58h+var_30], rcx
0x18002bfd1  mov     [rsp+58h+var_38], rsi
0x18002bfd6  mov     r9, rax
0x18002bfd9  xor     r8d, r8d; pReturnValue
0x18002bfdc  lea     edx, [r8+6]; nProcNum
0x18002bfe0  lea     rcx, stru_1800351D0; pProxyInfo
0x18002bfe7  call    cs:__imp_NdrClientCall3
0x18002bfee  nop     dword ptr [rax+rax+00h]
0x18002bff3  mov     [rsp+58h+var_20], rax
0x18002bff8  mov     ecx, eax; int
0x18002bffa  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18002bfff  mov     ebx, eax
0x18002c001  mov     [rsp+58h+var_28], eax
0x18002c005  jmp     short loc_18002C00D
0x18002c007  mov     ebx, eax
0x18002c009  mov     [rsp+58h+var_28], eax
0x18002c00d  lea     rcx, [rsp+58h+var_18]; this
0x18002c012  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18002c017  mov     eax, ebx
0x18002c019  mov     rbx, [rsp+58h+arg_0]
0x18002c01e  mov     rsi, [rsp+58h+arg_8]
0x18002c023  add     rsp, 50h
0x18002c027  pop     rdi
0x18002c028  retn
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
