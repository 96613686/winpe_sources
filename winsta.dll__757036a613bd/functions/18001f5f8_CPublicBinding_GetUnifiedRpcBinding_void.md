# CPublicBinding::GetUnifiedRpcBinding(void)

- ea: `0x18001f5f8`
- end: `0x18001f68e`
- name: `?GetUnifiedRpcBinding@CPublicBinding@@QEAAPEAXXZ`
- size: `150`
- prototype: `void *__fastcall(CPublicBinding *__hidden this)`
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, service_task`

## callers

- `0x180005db0`
- `0x1800063e0`
- `0x1800067b0`
- `0x1800083b0`

## callees

- `0x180005fcc`
- `0x180007890`
- `0x18000c0e8`
- `0x18000e8b8`
- `0x1800139dc`
- `0x18001f5f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f62e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f67a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f62e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f67a`

## string_xrefs

- `0x18001f646`: `\pipe\UNIFIED_API_service`

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
0x18001f5f8  mov     [rsp+arg_0], rbx
0x18001f5fd  push    rdi
0x18001f5fe  sub     rsp, 30h
0x18001f602  lea     rbx, [rcx+18h]
0x18001f606  cmp     qword ptr [rbx], 0
0x18001f60a  jnz     short loc_18001F680
0x18001f60c  cmp     dword ptr [rcx+30h], 1
0x18001f610  jnz     short loc_18001F642
0x18001f612  cmp     cs:?pNetsrvSid@CPublicBinding@@1PEAXEA, 0; void * CPublicBinding::pNetsrvSid
0x18001f61a  jnz     short loc_18001F638
0x18001f61c  call    ?CreateLocalSids@CPublicBinding@@SAJXZ; CPublicBinding::CreateLocalSids(void)
0x18001f621  test    eax, eax
0x18001f623  jns     short loc_18001F638
0x18001f625  mov     ecx, eax; int
0x18001f627  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18001f62c  mov     ecx, eax; dwErrCode
0x18001f62e  call    cs:__imp_SetLastError
0x18001f634  xor     eax, eax
0x18001f636  jmp     short loc_18001F683
0x18001f638  call    ?OpenLocalUnifiedRpc@@YAPEAXPEAX@Z; OpenLocalUnifiedRpc(void *)
0x18001f63d  mov     [rbx], rax
0x18001f640  jmp     short loc_18001F680
0x18001f642  mov     r8, [rcx+28h]; unsigned __int16 *
0x18001f646  lea     r9, aPipeUnifiedApi; "\\pipe\\UNIFIED_API_service"
0x18001f64d  lea     rcx, ObjUuid; "484809d6-4239-471b-b5bc-61df8c23ac48"
0x18001f654  mov     [rsp+38h+var_10], rbx; void **
0x18001f659  call    ?BindSecure@CRpcUtils@@SAJPEBG0000PEAPEAX@Z; CRpcUtils::BindSecure(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,void * *)
0x18001f65e  mov     edi, eax
0x18001f660  test    eax, eax
0x18001f662  jz      short loc_18001F680
0x18001f664  mov     r8d, eax
0x18001f667  lea     rdx, aCrpcutilsBinds; "CRpcUtils::BindSecure failed: %d"
0x18001f66e  mov     ecx, 8; int
0x18001f673  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001f678  mov     ecx, edi; dwErrCode
0x18001f67a  call    cs:__imp_SetLastError
0x18001f680  mov     rax, [rbx]
0x18001f683  mov     rbx, [rsp+38h+arg_0]
0x18001f688  add     rsp, 30h
0x18001f68c  pop     rdi
0x18001f68d  retn
```
