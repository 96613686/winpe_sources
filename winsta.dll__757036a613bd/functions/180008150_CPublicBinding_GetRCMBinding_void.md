# CPublicBinding::GetRCMBinding(void)

- ea: `0x180008150`
- end: `0x1800081ec`
- name: `?GetRCMBinding@CPublicBinding@@QEAAPEAXXZ`
- size: `156`
- prototype: `void *__fastcall(CPublicBinding *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, service_task`

## callers

- `0x1800063e0`
- `0x180007d10`

## callees

- `0x180005fcc`
- `0x180007890`
- `0x180008150`
- `0x180009310`
- `0x18000c0e8`
- `0x18000e8b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008194`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800081df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008194`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800081df`

## string_xrefs

- `0x1800081a6`: `\pipe\TermSrv_API_service`

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
0x180008150  push    rbx
0x180008152  sub     rsp, 30h
0x180008156  cmp     qword ptr [rcx+8], 0
0x18000815b  lea     rbx, [rcx+8]
0x18000815f  jnz     short loc_180008179
0x180008161  cmp     dword ptr [rcx+30h], 1
0x180008165  jnz     short loc_1800081A2
0x180008167  cmp     cs:?pNetsrvSid@CPublicBinding@@1PEAXEA, 0; void * CPublicBinding::pNetsrvSid
0x18000816f  jz      short loc_180008182
0x180008171  call    ?OpenLocalRCM@@YAPEAXPEAX@Z; OpenLocalRCM(void *)
0x180008176  mov     [rbx], rax
0x180008179  mov     rax, [rbx]
0x18000817c  add     rsp, 30h
0x180008180  pop     rbx
0x180008181  retn
0x180008182  call    ?CreateLocalSids@CPublicBinding@@SAJXZ; CPublicBinding::CreateLocalSids(void)
0x180008187  test    eax, eax
0x180008189  jns     short loc_180008171
0x18000818b  mov     ecx, eax; int
0x18000818d  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180008192  mov     ecx, eax; dwErrCode
0x180008194  call    cs:__imp_SetLastError
0x18000819a  xor     eax, eax
0x18000819c  add     rsp, 30h
0x1800081a0  pop     rbx
0x1800081a1  retn
0x1800081a2  mov     r8, [rcx+28h]; unsigned __int16 *
0x1800081a6  lea     r9, aPipeTermsrvApi; "\\pipe\\TermSrv_API_service"
0x1800081ad  lea     rcx, ObjUuid; "484809d6-4239-471b-b5bc-61df8c23ac48"
0x1800081b4  mov     [rsp+38h+arg_0], rdi
0x1800081b9  mov     [rsp+38h+var_10], rbx; void **
0x1800081be  call    ?BindSecure@CRpcUtils@@SAJPEBG0000PEAPEAX@Z; CRpcUtils::BindSecure(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,void * *)
0x1800081c3  mov     edi, eax
0x1800081c5  test    eax, eax
0x1800081c7  jz      short loc_1800081E5
0x1800081c9  mov     r8d, eax
0x1800081cc  lea     rdx, aCrpcutilsBinds; "CRpcUtils::BindSecure failed: %d"
0x1800081d3  mov     ecx, 8; int
0x1800081d8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800081dd  mov     ecx, edi; dwErrCode
0x1800081df  call    cs:__imp_SetLastError
0x1800081e5  mov     rdi, [rsp+38h+arg_0]
0x1800081ea  jmp     short loc_180008179
```
