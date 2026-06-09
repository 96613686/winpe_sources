# InternalGetConnectionProperty

- ea: `0x180003034`
- end: `0x1800031d1`
- name: `InternalGetConnectionProperty`
- size: `413`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180003e30`

## callees

- `0x180003034`
- `0x180005db0`
- `0x180005fcc`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x1800230b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003153`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800031a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003153`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800031a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000317a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000317a`
- `RPCRT4!I_RpcExceptionFilter` at `0x180030000`
- `RPCRT4!I_RpcExceptionFilter` at `0x180030000`
- `RPCRT4!NdrClientCall3` at `0x180003108`
- `RPCRT4!NdrClientCall3` at `0x180003108`

## string_xrefs

- `0x18000318f`: `Failed to open binding`

## pseudocode

```c
bool __fastcall InternalGetConnectionProperty(ULONG SessionId, __int64 a2, _QWORD *a3)
{
  CPublicBinding *v6; // rax
  void *v7; // rax
  CLIENT_CALL_RETURN v8; // rax
  signed int Pointer; // ebx
  bool v10; // sf
  DWORD v11; // eax
  bool v12; // bl
  signed int LastError; // eax
  __int64 v15; // [rsp+48h] [rbp-20h] BYREF
  CPublicBinding *v16; // [rsp+50h] [rbp-18h]
  CLIENT_CALL_RETURN v17; // [rsp+88h] [rbp+20h] BYREF

  v15 = 1;
  LODWORD(v17.Pointer) = 0;
  v6 = (CPublicBinding *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v6 )
    v6 = CPublicBinding::CPublicBinding(v6, 0, 0, (unsigned int *)&v17);
  v16 = v6;
  if ( v6 )
  {
    HIDWORD(v15) = 1;
  }
  else
  {
    SetLastError(0xEu);
    _DbgPrintMessage(8, "new CPublicBinding");
  }
  if ( CSmartPublicBinding::operator void *((unsigned __int16 *)&v15) )
  {
    if ( a3 )
    {
      *a3 = 0;
      if ( SessionId == -1 )
        SessionId = NtCurrentPeb()->SessionId;
      v7 = CSmartPublicBinding::operator void *((unsigned __int16 *)&v15);
      v17.Simple = 0;
      v8.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180032140, 4u, 0, v7, SessionId, a2, a3).Pointer;
      Pointer = (signed int)v8.Pointer;
      v17.Pointer = v8.Pointer;
    }
    else
    {
      Pointer = -2147024809;
      _DbgPrintMessage(8, "ppProperyValue is NULL");
    }
  }
  else
  {
    LastError = GetLastError();
    Pointer = LastError;
    if ( LastError > 0 )
      Pointer = (unsigned __int16)LastError | 0x80070000;
    _DbgPrintMessage(8, "Failed to open binding");
  }
  v10 = Pointer < 0;
  if ( Pointer < 0 )
  {
    v11 = ConvertHRESULT2WIN32(Pointer);
    SetLastError(v11);
    v10 = Pointer < 0;
  }
  v12 = !v10;
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)&v15);
  return v12;
}

```

## disassembly

```asm
0x180003034  mov     rax, rsp
0x180003037  mov     [rax+8], rbx
0x18000303b  mov     [rax+10h], rsi
0x18000303f  push    rdi
0x180003040  sub     rsp, 60h
0x180003044  mov     rbx, r8
0x180003047  mov     rsi, rdx
0x18000304a  mov     edi, ecx
0x18000304c  mov     qword ptr [rax-20h], 1
0x180003054  mov     dword ptr [rax+20h], 0
0x18000305b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180003062  mov     ecx, 40h ; '@'; unsigned __int64
0x180003067  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000306c  test    rax, rax
0x18000306f  jz      short loc_180003086
0x180003071  lea     r9, [rsp+68h+arg_18]; unsigned int *
0x180003079  xor     r8d, r8d; int
0x18000307c  xor     edx, edx; unsigned __int16 *
0x18000307e  mov     rcx, rax; this
0x180003081  call    ??0CPublicBinding@@QEAA@PEBGHPEAK@Z; CPublicBinding::CPublicBinding(ushort const *,int,ulong *)
0x180003086  mov     [rsp+68h+var_18], rax
0x18000308b  test    rax, rax
0x18000308e  jz      loc_1800031A2
0x180003094  mov     [rsp+68h+var_1C], 1
0x18000309c  lea     rcx, [rsp+68h+var_20]; unsigned __int16 *
0x1800030a1  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800030a6  test    rax, rax
0x1800030a9  jz      loc_18000317A
0x1800030af  test    rbx, rbx
0x1800030b2  jz      loc_1800031C3
0x1800030b8  mov     qword ptr [rbx], 0
0x1800030bf  cmp     edi, 0FFFFFFFFh
0x1800030c2  jnz     short loc_1800030D3
0x1800030c4  mov     rax, gs:60h
0x1800030cd  mov     edi, [rax+2C0h]
0x1800030d3  lea     rcx, [rsp+68h+var_20]; unsigned __int16 *
0x1800030d8  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800030dd  mov     [rsp+68h+arg_18], 0
0x1800030e9  mov     [rsp+68h+var_38], rbx
0x1800030ee  mov     [rsp+68h+var_40], rsi
0x1800030f3  mov     [rsp+68h+var_48], edi
0x1800030f7  mov     r9, rax
0x1800030fa  xor     r8d, r8d; pReturnValue
0x1800030fd  lea     edx, [r8+4]; nProcNum
0x180003101  lea     rcx, stru_180032140; pProxyInfo
0x180003108  call    cs:__imp_NdrClientCall3
0x18000310e  mov     rbx, rax
0x180003111  mov     [rsp+68h+arg_18], rax
0x180003119  mov     [rsp+68h+var_28], eax
0x18000311d  jmp     short loc_180003146
0x18000311f  test    eax, eax
0x180003121  jle     short loc_18000312B
0x180003123  movzx   eax, ax
0x180003126  or      eax, 80070000h
0x18000312b  mov     ebx, eax
0x18000312d  mov     [rsp+68h+var_28], eax
0x180003131  mov     r8d, eax
0x180003134  lea     rdx, aRpcgetconnecti; "RpcGetConnectionProperty threw an excep"...
0x18000313b  mov     ecx, 8; int
0x180003140  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180003145  nop
0x180003146  test    ebx, ebx
0x180003148  jns     short loc_18000315B
0x18000314a  mov     ecx, ebx; int
0x18000314c  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180003151  mov     ecx, eax; dwErrCode
0x180003153  call    cs:__imp_SetLastError
0x180003159  test    ebx, ebx
0x18000315b  setns   bl
0x18000315e  lea     rcx, [rsp+68h+var_20]; this
0x180003163  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180003168  mov     al, bl
0x18000316a  mov     rbx, [rsp+68h+arg_0]
0x18000316f  mov     rsi, [rsp+68h+arg_8]
0x180003174  add     rsp, 60h
0x180003178  pop     rdi
0x180003179  retn
0x18000317a  call    cs:__imp_GetLastError
0x180003180  mov     ebx, eax
0x180003182  test    eax, eax
0x180003184  jle     short loc_18000318F
0x180003186  movzx   ebx, ax
0x180003189  or      ebx, 80070000h
0x18000318f  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x180003196  mov     ecx, 8; int
0x18000319b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800031a0  jmp     short loc_180003146
0x1800031a2  mov     ecx, 0Eh; dwErrCode
0x1800031a7  call    cs:__imp_SetLastError
0x1800031ad  lea     rdx, aNewCpublicbind; "new CPublicBinding"
0x1800031b4  mov     ecx, 8; int
0x1800031b9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800031be  jmp     loc_18000309C
0x1800031c3  mov     ebx, 80070057h
0x1800031c8  lea     rdx, aPpproperyvalue; "ppProperyValue is NULL"
0x1800031cf  jmp     short loc_180003196
0x18002fff2  push    rbp
0x18002fff4  sub     rsp, 40h
0x18002fff8  mov     rbp, rdx
0x18002fffb  mov     rcx, [rcx]
0x18002fffe  mov     ecx, [rcx]; ExceptionCode
0x180030000  call    cs:__imp_I_RpcExceptionFilter
0x180030006  nop
0x180030007  add     rsp, 40h
0x18003000b  pop     rbp
0x18003000c  retn
```
