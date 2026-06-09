# WinStationGetCurrentSessionConnectionProperty

- ea: `0x180011170`
- end: `0x1800112e4`
- name: `WinStationGetCurrentSessionConnectionProperty`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180003e30`

## callees

- `0x180005db0`
- `0x180005fcc`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x180011170`
- `0x1800230b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800112a4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800112d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800112a4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800112d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011277`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011277`
- `RPCRT4!I_RpcExceptionFilter` at `0x180030683`
- `RPCRT4!I_RpcExceptionFilter` at `0x180030683`
- `RPCRT4!NdrClientCall3` at `0x18001121e`
- `RPCRT4!NdrClientCall3` at `0x18001121e`

## string_xrefs

- `0x18001128c`: `Failed to open binding`

## pseudocode

```c
bool __fastcall WinStationGetCurrentSessionConnectionProperty(__int64 a1, _QWORD *a2)
{
  CPublicBinding *v4; // rax
  void *v5; // rax
  CLIENT_CALL_RETURN v6; // rax
  signed int Pointer; // ebx
  bool v8; // sf
  bool v9; // bl
  signed int LastError; // eax
  DWORD v12; // eax
  unsigned __int16 v13[4]; // [rsp+38h] [rbp-20h] BYREF
  CPublicBinding *v14; // [rsp+40h] [rbp-18h]
  CLIENT_CALL_RETURN v15; // [rsp+70h] [rbp+18h] BYREF

  *(_QWORD *)v13 = 1;
  LODWORD(v15.Pointer) = 0;
  v4 = (CPublicBinding *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v4 )
    v4 = CPublicBinding::CPublicBinding(v4, 0, 0, (unsigned int *)&v15);
  v14 = v4;
  if ( v4 )
  {
    *(_DWORD *)&v13[2] = 1;
  }
  else
  {
    SetLastError(0xEu);
    _DbgPrintMessage(8, "new CPublicBinding");
  }
  if ( CSmartPublicBinding::operator void *(v13) )
  {
    if ( a2 )
    {
      *a2 = 0;
      v5 = CSmartPublicBinding::operator void *(v13);
      v15.Simple = 0;
      v6.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180032080, 0, 0, v5, a1, a2).Pointer;
      Pointer = (signed int)v6.Pointer;
      v15.Pointer = v6.Pointer;
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
  v8 = Pointer < 0;
  if ( Pointer < 0 )
  {
    v12 = ConvertHRESULT2WIN32(Pointer);
    SetLastError(v12);
    v8 = Pointer < 0;
  }
  v9 = !v8;
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v13);
  return v9;
}

```

## disassembly

```asm
0x180011170  mov     [rsp+arg_0], rbx
0x180011175  push    rdi
0x180011176  sub     rsp, 50h
0x18001117a  mov     rbx, rdx
0x18001117d  mov     rdi, rcx
0x180011180  mov     qword ptr [rsp+58h+var_20], 1
0x180011189  mov     dword ptr [rsp+58h+arg_10], 0
0x180011191  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180011198  mov     ecx, 40h ; '@'; unsigned __int64
0x18001119d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800111a2  test    rax, rax
0x1800111a5  jz      short loc_1800111B9
0x1800111a7  lea     r9, [rsp+58h+arg_10]; unsigned int *
0x1800111ac  xor     r8d, r8d; int
0x1800111af  xor     edx, edx; unsigned __int16 *
0x1800111b1  mov     rcx, rax; this
0x1800111b4  call    ??0CPublicBinding@@QEAA@PEBGHPEAK@Z; CPublicBinding::CPublicBinding(ushort const *,int,ulong *)
0x1800111b9  mov     [rsp+58h+var_18], rax
0x1800111be  test    rax, rax
0x1800111c1  jz      loc_18001129F
0x1800111c7  mov     dword ptr [rsp+58h+var_20+4], 1
0x1800111cf  lea     rcx, [rsp+58h+var_20]; unsigned __int16 *
0x1800111d4  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800111d9  test    rax, rax
0x1800111dc  jz      loc_180011277
0x1800111e2  test    rbx, rbx
0x1800111e5  jz      loc_1800112C0
0x1800111eb  mov     qword ptr [rbx], 0
0x1800111f2  lea     rcx, [rsp+58h+var_20]; unsigned __int16 *
0x1800111f7  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800111fc  mov     [rsp+58h+arg_10], 0
0x180011205  mov     [rsp+58h+var_30], rbx
0x18001120a  mov     [rsp+58h+var_38], rdi
0x18001120f  mov     r9, rax
0x180011212  xor     r8d, r8d; pReturnValue
0x180011215  xor     edx, edx; nProcNum
0x180011217  lea     rcx, stru_180032080; pProxyInfo
0x18001121e  call    cs:__imp_NdrClientCall3
0x180011224  mov     rbx, rax
0x180011227  mov     [rsp+58h+arg_10], rax
0x18001122c  mov     [rsp+58h+var_28], eax
0x180011230  jmp     short loc_180011259
0x180011232  test    eax, eax
0x180011234  jle     short loc_18001123E
0x180011236  movzx   eax, ax
0x180011239  or      eax, 80070000h
0x18001123e  mov     ebx, eax
0x180011240  mov     [rsp+58h+var_28], eax
0x180011244  mov     r8d, eax
0x180011247  lea     rdx, aRpcgetcurrents_1; "RpcGetCurrentSessionConnectionProperty "...
0x18001124e  mov     ecx, 8; int
0x180011253  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180011258  nop
0x180011259  test    ebx, ebx
0x18001125b  js      short loc_1800112CE
0x18001125d  setns   bl
0x180011260  lea     rcx, [rsp+58h+var_20]; this
0x180011265  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18001126a  mov     al, bl
0x18001126c  mov     rbx, [rsp+58h+arg_0]
0x180011271  add     rsp, 50h
0x180011275  pop     rdi
0x180011276  retn
0x180011277  call    cs:__imp_GetLastError
0x18001127d  mov     ebx, eax
0x18001127f  test    eax, eax
0x180011281  jle     short loc_18001128C
0x180011283  movzx   ebx, ax
0x180011286  or      ebx, 80070000h
0x18001128c  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x180011293  mov     ecx, 8; int
0x180011298  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001129d  jmp     short loc_180011259
0x18001129f  mov     ecx, 0Eh; dwErrCode
0x1800112a4  call    cs:__imp_SetLastError
0x1800112aa  lea     rdx, aNewCpublicbind; "new CPublicBinding"
0x1800112b1  mov     ecx, 8; int
0x1800112b6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800112bb  jmp     loc_1800111CF
0x1800112c0  mov     ebx, 80070057h
0x1800112c5  lea     rdx, aPpproperyvalue; "ppProperyValue is NULL"
0x1800112cc  jmp     short loc_180011293
0x1800112ce  mov     ecx, ebx; int
0x1800112d0  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x1800112d5  mov     ecx, eax; dwErrCode
0x1800112d7  call    cs:__imp_SetLastError
0x1800112dd  test    ebx, ebx
0x1800112df  jmp     loc_18001125D
0x180030675  push    rbp
0x180030677  sub     rsp, 30h
0x18003067b  mov     rbp, rdx
0x18003067e  mov     rcx, [rcx]
0x180030681  mov     ecx, [rcx]; ExceptionCode
0x180030683  call    cs:__imp_I_RpcExceptionFilter
0x180030689  nop
0x18003068a  add     rsp, 30h
0x18003068e  pop     rbp
0x18003068f  retn
```
