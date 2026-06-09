# CSmartPublicBinding::operator void *(void)

- ea: `0x180008e30`
- end: `0x180008f08`
- name: `??BCSmartPublicBinding@@QEAAPEAXXZ`
- size: `216`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `92`
- callee_count: `7`
- tags: `authz_impersonation, service_task`

## callers

- `0x1800011c0`
- `0x180001b68`
- `0x1800026e0`
- `0x1800027d4`
- `0x180003034`
- `0x18000375c`
- `0x180003ba8`
- `0x180003f10`
- `0x180004114`
- `0x1800046ec`
- `0x180004a30`
- `0x180005194`
- `0x1800067b0`
- `0x180008740`
- `0x1800094f0`
- `0x1800097b0`
- `0x180009da0`
- `0x18000a790`
- `0x18000aa20`
- `0x18000ad50`
- `0x18000b870`
- `0x18000c420`
- `0x18000c570`
- `0x18000c820`
- `0x18000ce54`
- `0x18000db70`
- `0x18000dcc4`
- `0x18000fca0`
- `0x1800101c0`
- `0x180010610`
- `0x180010d90`
- `0x180011170`
- `0x180011458`
- `0x180011730`
- `0x1800119d4`
- `0x180011cb0`
- `0x180012828`
- `0x180012b14`
- `0x180012f00`
- `0x180013088`
- `0x1800133e0`
- `0x180013d80`
- `0x18001f9b0`
- `0x18001fcb0`
- `0x18001fda0`
- `0x18001feb0`
- `0x18001ffbc`
- `0x1800200c0`
- `0x180020380`
- `0x1800206a0`

## callees

- `0x180005fcc`
- `0x180007890`
- `0x180008e30`
- `0x180008f10`
- `0x180009310`
- `0x18000c0e8`
- `0x18000e8b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008ea9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008ef8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008ea9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008ef8`

## string_xrefs

- `0x180008ebf`: `\pipe\TermSrv_API_service`

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
0x180008e30  sub     rsp, 38h
0x180008e34  mov     rdx, rcx; unsigned __int16 *
0x180008e37  mov     rcx, [rcx+8]; void *
0x180008e3b  test    rcx, rcx
0x180008e3e  jz      short loc_180008E90
0x180008e40  mov     rax, [rcx+18h]
0x180008e44  test    rax, rax
0x180008e47  jnz     short loc_180008E56
0x180008e49  cmp     [rdx], eax
0x180008e4b  jnz     short loc_180008E5B
0x180008e4d  add     rsp, 38h
0x180008e51  jmp     ?GetLSMBinding@CPublicBinding@@QEAAPEAXXZ; CPublicBinding::GetLSMBinding(void)
0x180008e56  add     rsp, 38h
0x180008e5a  retn
0x180008e5b  cmp     qword ptr [rcx+8], 0
0x180008e60  mov     [rsp+38h+arg_0], rbx
0x180008e65  lea     rbx, [rcx+8]
0x180008e69  jnz     short loc_180008E83
0x180008e6b  cmp     dword ptr [rcx+30h], 1
0x180008e6f  jnz     short loc_180008EBB
0x180008e71  cmp     cs:?pNetsrvSid@CPublicBinding@@1PEAXEA, 0; void * CPublicBinding::pNetsrvSid
0x180008e79  jz      short loc_180008E97
0x180008e7b  call    ?OpenLocalRCM@@YAPEAXPEAX@Z; OpenLocalRCM(void *)
0x180008e80  mov     [rbx], rax
0x180008e83  mov     rax, [rbx]
0x180008e86  mov     rbx, [rsp+38h+arg_0]
0x180008e8b  add     rsp, 38h
0x180008e8f  retn
0x180008e90  xor     eax, eax
0x180008e92  add     rsp, 38h
0x180008e96  retn
0x180008e97  call    ?CreateLocalSids@CPublicBinding@@SAJXZ; CPublicBinding::CreateLocalSids(void)
0x180008e9c  test    eax, eax
0x180008e9e  jns     short loc_180008E7B
0x180008ea0  mov     ecx, eax; int
0x180008ea2  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180008ea7  mov     ecx, eax; dwErrCode
0x180008ea9  call    cs:__imp_SetLastError
0x180008eaf  mov     rbx, [rsp+38h+arg_0]
0x180008eb4  xor     eax, eax
0x180008eb6  add     rsp, 38h
0x180008eba  retn
0x180008ebb  mov     r8, [rcx+28h]; unsigned __int16 *
0x180008ebf  lea     r9, aPipeTermsrvApi; "\\pipe\\TermSrv_API_service"
0x180008ec6  lea     rcx, ObjUuid; "484809d6-4239-471b-b5bc-61df8c23ac48"
0x180008ecd  mov     [rsp+38h+var_8], rdi
0x180008ed2  mov     [rsp+38h+var_10], rbx; void **
0x180008ed7  call    ?BindSecure@CRpcUtils@@SAJPEBG0000PEAPEAX@Z; CRpcUtils::BindSecure(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,void * *)
0x180008edc  mov     edi, eax
0x180008ede  test    eax, eax
0x180008ee0  jz      short loc_180008EFE
0x180008ee2  mov     r8d, eax
0x180008ee5  lea     rdx, aCrpcutilsBinds; "CRpcUtils::BindSecure failed: %d"
0x180008eec  mov     ecx, 8; int
0x180008ef1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180008ef6  mov     ecx, edi; dwErrCode
0x180008ef8  call    cs:__imp_SetLastError
0x180008efe  mov     rdi, [rsp+38h+var_8]
0x180008f03  jmp     loc_180008E83
```
