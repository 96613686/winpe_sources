# CPublicBinding::GetRCMBinding(void)

- ea: `0x180006480`
- end: `0x18000652d`
- name: `?GetRCMBinding@CPublicBinding@@QEAAPEAXXZ`
- size: `173`
- prototype: `void *__fastcall(CPublicBinding *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task`

## callers

- `0x180006000`

## callees

- `0x180004558`
- `0x180005b40`
- `0x180006480`
- `0x180007b10`
- `0x18000dc78`
- `0x18000eb30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800064c5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006517`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800064c5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006517`

## string_xrefs

- `0x1800064de`: `\pipe\TermSrv_API_service`

## pseudocode

```c
void *__fastcall CPublicBinding::GetRCMBinding(CPublicBinding *this, const unsigned __int16 *a2)
{
  void **v2; // rbx
  int LocalSids; // eax
  DWORD v5; // eax
  DWORD v6; // eax
  DWORD v7; // edi
  const unsigned __int16 *v8; // [rsp+20h] [rbp-18h]

  v2 = (void **)((char *)this + 8);
  if ( *((_QWORD *)this + 1) )
    return *v2;
  if ( *((_DWORD *)this + 12) != 1 )
  {
    v6 = CRpcUtils::BindSecure(
           L"484809d6-4239-471b-b5bc-61df8c23ac48",
           a2,
           *((const unsigned __int16 **)this + 5),
           L"\\pipe\\TermSrv_API_service",
           v8,
           v2);
    v7 = v6;
    if ( v6 )
    {
      _DbgPrintMessage(8, "CRpcUtils::BindSecure failed: %d", v6);
      SetLastError(v7);
    }
    return *v2;
  }
  if ( CPublicBinding::pNetsrvSid || (LocalSids = CPublicBinding::CreateLocalSids(), LocalSids >= 0) )
  {
    *v2 = OpenLocalRCM(this);
    return *v2;
  }
  v5 = ConvertHRESULT2WIN32(LocalSids);
  SetLastError(v5);
  return 0;
}

```

## disassembly

```asm
0x180006480  push    rbx
0x180006482  sub     rsp, 30h
0x180006486  cmp     qword ptr [rcx+8], 0
0x18000648b  lea     rbx, [rcx+8]
0x18000648f  jnz     short loc_1800064A9
0x180006491  cmp     dword ptr [rcx+30h], 1
0x180006495  jnz     short loc_1800064DA
0x180006497  cmp     cs:?pNetsrvSid@CPublicBinding@@1PEAXEA, 0; void * CPublicBinding::pNetsrvSid
0x18000649f  jz      short loc_1800064B3
0x1800064a1  call    ?OpenLocalRCM@@YAPEAXPEAX@Z; OpenLocalRCM(void *)
0x1800064a6  mov     [rbx], rax
0x1800064a9  mov     rax, [rbx]
0x1800064ac  add     rsp, 30h
0x1800064b0  pop     rbx
0x1800064b1  retn
0x1800064b3  call    ?CreateLocalSids@CPublicBinding@@SAJXZ; CPublicBinding::CreateLocalSids(void)
0x1800064b8  test    eax, eax
0x1800064ba  jns     short loc_1800064A1
0x1800064bc  mov     ecx, eax; int
0x1800064be  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x1800064c3  mov     ecx, eax; dwErrCode
0x1800064c5  call    cs:__imp_SetLastError
0x1800064cc  nop     dword ptr [rax+rax+00h]
0x1800064d1  xor     eax, eax
0x1800064d3  add     rsp, 30h
0x1800064d7  pop     rbx
0x1800064d8  retn
0x1800064da  mov     r8, [rcx+28h]; unsigned __int16 *
0x1800064de  lea     r9, aPipeTermsrvApi; "\\pipe\\TermSrv_API_service"
0x1800064e5  lea     rcx, ObjUuid; "484809d6-4239-471b-b5bc-61df8c23ac48"
0x1800064ec  mov     [rsp+38h+arg_0], rdi
0x1800064f1  mov     [rsp+38h+var_10], rbx; void **
0x1800064f6  call    ?BindSecure@CRpcUtils@@SAJPEBG0000PEAPEAX@Z; CRpcUtils::BindSecure(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,void * *)
0x1800064fb  mov     edi, eax
0x1800064fd  test    eax, eax
0x1800064ff  jz      short loc_180006523
0x180006501  mov     r8d, eax
0x180006504  lea     rdx, aCrpcutilsBinds; "CRpcUtils::BindSecure failed: %d"
0x18000650b  mov     ecx, 8; int
0x180006510  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180006515  mov     ecx, edi; dwErrCode
0x180006517  call    cs:__imp_SetLastError
0x18000651e  nop     dword ptr [rax+rax+00h]
0x180006523  mov     rdi, [rsp+38h+arg_0]
0x180006528  jmp     loc_1800064A9
```
