# WinStationReportUIResult

- ea: `0x18002a260`
- end: `0x18002a32d`
- name: `WinStationReportUIResult`
- size: `205`
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
- `0x18002a260`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a2ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a2ac`
- `RPCRT4!NdrClientCall3` at `0x18002a2f1`
- `RPCRT4!NdrClientCall3` at `0x18002a2f1`

## string_xrefs

- `0x18002a29d`: `Failed to open binding`

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
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800321A0, 6u, 0, v7, a1, &v11).Pointer;
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
0x18002a260  mov     rax, rsp
0x18002a263  mov     [rax+8], rbx
0x18002a267  mov     [rax+10h], rsi
0x18002a26b  push    rdi
0x18002a26c  sub     rsp, 50h
0x18002a270  mov     ebx, r8d
0x18002a273  mov     edi, edx
0x18002a275  mov     rsi, rcx
0x18002a278  mov     qword ptr [rax+20h], 0
0x18002a280  xor     r8d, r8d; int
0x18002a283  xor     edx, edx; void *
0x18002a285  lea     rcx, [rax-18h]; this
0x18002a289  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x18002a28e  lea     rcx, [rsp+58h+var_18]; unsigned __int16 *
0x18002a293  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002a298  test    rax, rax
0x18002a29b  jnz     short loc_18002A2B6
0x18002a29d  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x18002a2a4  lea     ecx, [rax+8]; int
0x18002a2a7  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002a2ac  call    cs:__imp_GetLastError
0x18002a2b2  mov     ebx, eax
0x18002a2b4  jmp     short loc_18002A311
0x18002a2b6  mov     [rsp+58h+arg_18], edi
0x18002a2ba  mov     [rsp+58h+arg_1C], ebx
0x18002a2be  lea     rcx, [rsp+58h+var_18]; unsigned __int16 *
0x18002a2c3  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002a2c8  mov     [rsp+58h+var_20], 0
0x18002a2d1  lea     rcx, [rsp+58h+arg_18]
0x18002a2d6  mov     [rsp+58h+var_30], rcx
0x18002a2db  mov     [rsp+58h+var_38], rsi
0x18002a2e0  mov     r9, rax
0x18002a2e3  xor     r8d, r8d; pReturnValue
0x18002a2e6  lea     edx, [r8+6]; nProcNum
0x18002a2ea  lea     rcx, stru_1800321A0; pProxyInfo
0x18002a2f1  call    cs:__imp_NdrClientCall3
0x18002a2f7  mov     [rsp+58h+var_20], rax
0x18002a2fc  mov     ecx, eax; int
0x18002a2fe  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18002a303  mov     ebx, eax
0x18002a305  mov     [rsp+58h+var_28], eax
0x18002a309  jmp     short loc_18002A311
0x18002a30b  mov     ebx, eax
0x18002a30d  mov     [rsp+58h+var_28], eax
0x18002a311  lea     rcx, [rsp+58h+var_18]; this
0x18002a316  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18002a31b  mov     eax, ebx
0x18002a31d  mov     rbx, [rsp+58h+arg_0]
0x18002a322  mov     rsi, [rsp+58h+arg_8]
0x18002a327  add     rsp, 50h
0x18002a32b  pop     rdi
0x18002a32c  retn
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
