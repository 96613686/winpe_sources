# CSmartPublicBinding::operator void *(void)

- ea: `0x1800075a0`
- end: `0x180007688`
- name: `??BCSmartPublicBinding@@QEAAPEAXXZ`
- size: `232`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `93`
- callee_count: `7`
- tags: `authz_impersonation, service_task`

## callers

- `0x180001524`
- `0x1800016c8`
- `0x180001a10`
- `0x180001d80`
- `0x180002114`
- `0x180002464`
- `0x180002c00`
- `0x180003480`
- `0x1800049a0`
- `0x180006b20`
- `0x180006ed0`
- `0x180007d20`
- `0x180007fe0`
- `0x180008640`
- `0x1800090a0`
- `0x180009350`
- `0x1800096c0`
- `0x180009dec`
- `0x18000a7b0`
- `0x18000aac4`
- `0x18000b448`
- `0x18000b8d4`
- `0x18000c510`
- `0x18000c60c`
- `0x18000d360`
- `0x18000e000`
- `0x18000e160`
- `0x18000f410`
- `0x1800107c0`
- `0x180010bbc`
- `0x180010ea0`
- `0x180011550`
- `0x180011d30`
- `0x180011ef0`
- `0x1800124ec`
- `0x180012820`
- `0x180012b40`
- `0x18001369c`
- `0x180013994`
- `0x180013dd0`
- `0x180013fcc`
- `0x1800142c0`
- `0x180014d40`
- `0x1800210a0`
- `0x1800213c0`
- `0x1800214c0`
- `0x1800215e0`
- `0x1800216f8`
- `0x180021810`
- `0x180021af0`

## callees

- `0x180004558`
- `0x180005b40`
- `0x1800075a0`
- `0x180007690`
- `0x180007b10`
- `0x18000dc78`
- `0x18000eb30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000761c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007672`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000761c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007672`

## string_xrefs

- `0x180007639`: `\pipe\TermSrv_API_service`

## pseudocode

```c
void *__fastcall CSmartPublicBinding::operator void *(unsigned __int16 *a1)
{
  __int64 v2; // rcx
  void *result; // rax
  void **v4; // rbx
  int LocalSids; // eax
  DWORD v6; // eax
  DWORD v7; // eax
  DWORD v8; // edi
  const unsigned __int16 *v9; // [rsp+20h] [rbp-18h]

  v2 = *((_QWORD *)a1 + 1);
  if ( !v2 )
    return 0;
  result = *(void **)(v2 + 24);
  if ( !result )
  {
    if ( !*(_DWORD *)a1 )
      return CPublicBinding::GetLSMBinding((RPC_BINDING_HANDLE *)v2);
    v4 = (void **)(v2 + 8);
    if ( !*(_QWORD *)(v2 + 8) )
    {
      if ( *(_DWORD *)(v2 + 48) == 1 )
      {
        if ( !CPublicBinding::pNetsrvSid )
        {
          LocalSids = CPublicBinding::CreateLocalSids();
          if ( LocalSids < 0 )
          {
            v6 = ConvertHRESULT2WIN32(LocalSids);
            SetLastError(v6);
            return 0;
          }
        }
        *v4 = OpenLocalRCM((void *)v2);
      }
      else
      {
        v7 = CRpcUtils::BindSecure(
               L"484809d6-4239-471b-b5bc-61df8c23ac48",
               a1,
               *(const unsigned __int16 **)(v2 + 40),
               L"\\pipe\\TermSrv_API_service",
               v9,
               v4);
        v8 = v7;
        if ( v7 )
        {
          _DbgPrintMessage(8, "CRpcUtils::BindSecure failed: %d", v7);
          SetLastError(v8);
        }
      }
    }
    return *v4;
  }
  return result;
}

```

## disassembly

```asm
0x1800075a0  sub     rsp, 38h
0x1800075a4  mov     rdx, rcx; unsigned __int16 *
0x1800075a7  mov     rcx, [rcx+8]; void *
0x1800075ab  test    rcx, rcx
0x1800075ae  jz      short loc_180007602
0x1800075b0  mov     rax, [rcx+18h]
0x1800075b4  test    rax, rax
0x1800075b7  jnz     short loc_1800075C6
0x1800075b9  cmp     [rdx], eax
0x1800075bb  jnz     short loc_1800075CC
0x1800075bd  add     rsp, 38h
0x1800075c1  jmp     ?GetLSMBinding@CPublicBinding@@QEAAPEAXXZ; CPublicBinding::GetLSMBinding(void)
0x1800075c6  add     rsp, 38h
0x1800075ca  retn
0x1800075cc  cmp     qword ptr [rcx+8], 0
0x1800075d1  mov     [rsp+38h+arg_0], rbx
0x1800075d6  lea     rbx, [rcx+8]
0x1800075da  jnz     short loc_1800075F4
0x1800075dc  cmp     dword ptr [rcx+30h], 1
0x1800075e0  jnz     short loc_180007635
0x1800075e2  cmp     cs:?pNetsrvSid@CPublicBinding@@1PEAXEA, 0; void * CPublicBinding::pNetsrvSid
0x1800075ea  jz      short loc_18000760A
0x1800075ec  call    ?OpenLocalRCM@@YAPEAXPEAX@Z; OpenLocalRCM(void *)
0x1800075f1  mov     [rbx], rax
0x1800075f4  mov     rax, [rbx]
0x1800075f7  mov     rbx, [rsp+38h+arg_0]
0x1800075fc  add     rsp, 38h
0x180007600  retn
0x180007602  xor     eax, eax
0x180007604  add     rsp, 38h
0x180007608  retn
0x18000760a  call    ?CreateLocalSids@CPublicBinding@@SAJXZ; CPublicBinding::CreateLocalSids(void)
0x18000760f  test    eax, eax
0x180007611  jns     short loc_1800075EC
0x180007613  mov     ecx, eax; int
0x180007615  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18000761a  mov     ecx, eax; dwErrCode
0x18000761c  call    cs:__imp_SetLastError
0x180007623  nop     dword ptr [rax+rax+00h]
0x180007628  mov     rbx, [rsp+38h+arg_0]
0x18000762d  xor     eax, eax
0x18000762f  add     rsp, 38h
0x180007633  retn
0x180007635  mov     r8, [rcx+28h]; unsigned __int16 *
0x180007639  lea     r9, aPipeTermsrvApi; "\\pipe\\TermSrv_API_service"
0x180007640  lea     rcx, ObjUuid; "484809d6-4239-471b-b5bc-61df8c23ac48"
0x180007647  mov     [rsp+38h+var_8], rdi
0x18000764c  mov     [rsp+38h+var_10], rbx; void **
0x180007651  call    ?BindSecure@CRpcUtils@@SAJPEBG0000PEAPEAX@Z; CRpcUtils::BindSecure(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,void * *)
0x180007656  mov     edi, eax
0x180007658  test    eax, eax
0x18000765a  jz      short loc_18000767E
0x18000765c  mov     r8d, eax
0x18000765f  lea     rdx, aCrpcutilsBinds; "CRpcUtils::BindSecure failed: %d"
0x180007666  mov     ecx, 8; int
0x18000766b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180007670  mov     ecx, edi; dwErrCode
0x180007672  call    cs:__imp_SetLastError
0x180007679  nop     dword ptr [rax+rax+00h]
0x18000767e  mov     rdi, [rsp+38h+var_8]
0x180007683  jmp     loc_1800075F4
```
