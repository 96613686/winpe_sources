# CPublicBinding::GetUnifiedRpcBinding(void)

- ea: `0x180020c90`
- end: `0x180020d37`
- name: `?GetUnifiedRpcBinding@CPublicBinding@@QEAAPEAXXZ`
- size: `167`
- prototype: `void *__fastcall(CPublicBinding *__hidden this)`
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, service_task`

## callers

- `0x180004330`
- `0x1800049a0`
- `0x180006000`
- `0x180006740`

## callees

- `0x180004558`
- `0x180005b40`
- `0x18000dc78`
- `0x18000eb30`
- `0x180014958`
- `0x180020c90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020cca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020d1c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020cca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020d1c`

## string_xrefs

- `0x180020ce8`: `\pipe\UNIFIED_API_service`

## pseudocode

```c
void *__fastcall CPublicBinding::GetUnifiedRpcBinding(const unsigned __int16 **this, const unsigned __int16 *a2)
{
  void **v2; // rbx
  int LocalSids; // eax
  DWORD v4; // eax
  DWORD v6; // eax
  DWORD v7; // edi
  const unsigned __int16 *v8; // [rsp+20h] [rbp-18h]

  v2 = (void **)(this + 3);
  if ( !this[3] )
  {
    if ( *((_DWORD *)this + 12) == 1 )
    {
      if ( !CPublicBinding::pNetsrvSid )
      {
        LocalSids = CPublicBinding::CreateLocalSids();
        if ( LocalSids < 0 )
        {
          v4 = ConvertHRESULT2WIN32(LocalSids);
          SetLastError(v4);
          return 0;
        }
      }
      *v2 = OpenLocalUnifiedRpc(this);
    }
    else
    {
      v6 = CRpcUtils::BindSecure(
             L"484809d6-4239-471b-b5bc-61df8c23ac48",
             a2,
             this[5],
             L"\\pipe\\UNIFIED_API_service",
             v8,
             v2);
      v7 = v6;
      if ( v6 )
      {
        _DbgPrintMessage(8, "CRpcUtils::BindSecure failed: %d", v6);
        SetLastError(v7);
      }
    }
  }
  return *v2;
}

```

## disassembly

```asm
0x180020c90  mov     [rsp+arg_0], rbx
0x180020c95  push    rdi
0x180020c96  sub     rsp, 30h
0x180020c9a  lea     rbx, [rcx+18h]
0x180020c9e  cmp     qword ptr [rbx], 0
0x180020ca2  jnz     loc_180020D28
0x180020ca8  cmp     dword ptr [rcx+30h], 1
0x180020cac  jnz     short loc_180020CE4
0x180020cae  cmp     cs:?pNetsrvSid@CPublicBinding@@1PEAXEA, 0; void * CPublicBinding::pNetsrvSid
0x180020cb6  jnz     short loc_180020CDA
0x180020cb8  call    ?CreateLocalSids@CPublicBinding@@SAJXZ; CPublicBinding::CreateLocalSids(void)
0x180020cbd  test    eax, eax
0x180020cbf  jns     short loc_180020CDA
0x180020cc1  mov     ecx, eax; int
0x180020cc3  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180020cc8  mov     ecx, eax; dwErrCode
0x180020cca  call    cs:__imp_SetLastError
0x180020cd1  nop     dword ptr [rax+rax+00h]
0x180020cd6  xor     eax, eax
0x180020cd8  jmp     short loc_180020D2B
0x180020cda  call    ?OpenLocalUnifiedRpc@@YAPEAXPEAX@Z; OpenLocalUnifiedRpc(void *)
0x180020cdf  mov     [rbx], rax
0x180020ce2  jmp     short loc_180020D28
0x180020ce4  mov     r8, [rcx+28h]; unsigned __int16 *
0x180020ce8  lea     r9, aPipeUnifiedApi; "\\pipe\\UNIFIED_API_service"
0x180020cef  lea     rcx, ObjUuid; "484809d6-4239-471b-b5bc-61df8c23ac48"
0x180020cf6  mov     [rsp+38h+var_10], rbx; void **
0x180020cfb  call    ?BindSecure@CRpcUtils@@SAJPEBG0000PEAPEAX@Z; CRpcUtils::BindSecure(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,void * *)
0x180020d00  mov     edi, eax
0x180020d02  test    eax, eax
0x180020d04  jz      short loc_180020D28
0x180020d06  mov     r8d, eax
0x180020d09  lea     rdx, aCrpcutilsBinds; "CRpcUtils::BindSecure failed: %d"
0x180020d10  mov     ecx, 8; int
0x180020d15  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180020d1a  mov     ecx, edi; dwErrCode
0x180020d1c  call    cs:__imp_SetLastError
0x180020d23  nop     dword ptr [rax+rax+00h]
0x180020d28  mov     rax, [rbx]
0x180020d2b  mov     rbx, [rsp+38h+arg_0]
0x180020d30  add     rsp, 30h
0x180020d34  pop     rdi
0x180020d35  retn
```
