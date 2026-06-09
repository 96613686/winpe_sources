# WinStationShadowAccessCheck

- ea: `0x18001f9b0`
- end: `0x18001fac4`
- name: `WinStationShadowAccessCheck`
- size: `276`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x180005c30`
- `0x180005fcc`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x18001f9b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001fa9b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001fa9b`
- `RPCRT4!NdrClientCall3` at `0x18001fa2f`
- `RPCRT4!NdrClientCall3` at `0x18001fa2f`

## string_xrefs

- `0x18001f9e7`: `Failed to open binding`
- `0x18001fa5b`: `RpcShadowAccessCheck threw an exception: 0x%x`
- `0x18001fa77`: `WinStationShadowAccessCheck`
- `0x18001fa81`: `RpcShadowAccessCheck failed: 0x%x in %s`

## pseudocode

```c
char __fastcall WinStationShadowAccessCheck(int a1, _BYTE *a2)
{
  char v4; // di
  __int64 v5; // rax
  CLIENT_CALL_RETURN v6; // rbx
  DWORD v7; // eax
  int v9; // [rsp+20h] [rbp-48h]
  unsigned __int16 v10[24]; // [rsp+38h] [rbp-30h] BYREF
  char v11; // [rsp+80h] [rbp+18h] BYREF
  CLIENT_CALL_RETURN v12; // [rsp+88h] [rbp+20h]

  v4 = 0;
  v11 = 0;
  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v10, 0, 1);
  if ( CSmartPublicBinding::operator void *(v10) )
  {
    v5 = CSmartPublicBinding::operator void *(v10);
    v12.Simple = 0;
    v9 = a1;
    v6.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180032140, 9u, 0, v5, v9, &v11).Pointer;
    v12.Pointer = v6.Pointer;
    if ( SLODWORD(v6.Simple) >= 0 )
    {
      v4 = 1;
      *a2 = v11;
    }
    else
    {
      _DbgPrintMessage(8, "RpcShadowAccessCheck failed: 0x%x in %s", LODWORD(v6.Pointer), "WinStationShadowAccessCheck");
      v7 = ConvertHRESULT2WIN32(v6.Simple);
      SetLastError(v7);
    }
  }
  else
  {
    _DbgPrintMessage(8, "Failed to open binding");
  }
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v10);
  return v4;
}

```

## disassembly

```asm
0x18001f9b0  mov     rax, rsp
0x18001f9b3  mov     [rax+10h], rdx
0x18001f9b7  push    rbx
0x18001f9b8  push    rsi
0x18001f9b9  push    rdi
0x18001f9ba  sub     rsp, 50h
0x18001f9be  mov     rsi, rdx
0x18001f9c1  mov     ebx, ecx
0x18001f9c3  xor     edi, edi
0x18001f9c5  mov     [rax+18h], dil
0x18001f9c9  xor     edx, edx; void *
0x18001f9cb  lea     r8d, [rdi+1]; int
0x18001f9cf  lea     rcx, [rax-30h]; this
0x18001f9d3  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x18001f9d8  lea     rcx, [rsp+68h+var_30]; unsigned __int16 *
0x18001f9dd  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18001f9e2  test    rax, rax
0x18001f9e5  jnz     short loc_18001F9FB
0x18001f9e7  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x18001f9ee  lea     ecx, [rdi+8]; int
0x18001f9f1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001f9f6  jmp     loc_18001FAAF
0x18001f9fb  lea     rcx, [rsp+68h+var_30]; unsigned __int16 *
0x18001fa00  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18001fa05  mov     [rsp+68h+arg_18], rdi
0x18001fa0d  lea     rcx, [rsp+68h+arg_10]
0x18001fa15  mov     [rsp+68h+var_40], rcx
0x18001fa1a  mov     [rsp+68h+var_48], ebx
0x18001fa1e  mov     r9, rax
0x18001fa21  xor     r8d, r8d; pReturnValue
0x18001fa24  lea     edx, [r8+9]; nProcNum
0x18001fa28  lea     rcx, stru_180032140; pProxyInfo
0x18001fa2f  call    cs:__imp_NdrClientCall3
0x18001fa35  mov     rbx, rax
0x18001fa38  mov     [rsp+68h+arg_18], rax
0x18001fa40  mov     [rsp+68h+var_38], eax
0x18001fa44  jmp     short loc_18001FA73
0x18001fa46  test    eax, eax
0x18001fa48  jle     short loc_18001FA52
0x18001fa4a  movzx   eax, ax
0x18001fa4d  or      eax, 80070000h
0x18001fa52  mov     ebx, eax
0x18001fa54  mov     [rsp+68h+var_38], eax
0x18001fa58  mov     r8d, eax
0x18001fa5b  lea     rdx, aRpcshadowacces_0; "RpcShadowAccessCheck threw an exception"...
0x18001fa62  mov     ecx, 8; int
0x18001fa67  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001fa6c  xor     edi, edi
0x18001fa6e  mov     rsi, [rsp+68h+arg_8]
0x18001fa73  test    ebx, ebx
0x18001fa75  jns     short loc_18001FAA3
0x18001fa77  lea     r9, aWinstationshad_7; "WinStationShadowAccessCheck"
0x18001fa7e  mov     r8d, ebx
0x18001fa81  lea     rdx, aRpcshadowacces; "RpcShadowAccessCheck failed: 0x%x in %s"
0x18001fa88  mov     ecx, 8; int
0x18001fa8d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001fa92  mov     ecx, ebx; int
0x18001fa94  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18001fa99  mov     ecx, eax; dwErrCode
0x18001fa9b  call    cs:__imp_SetLastError
0x18001faa1  jmp     short loc_18001FAAF
0x18001faa3  mov     dil, 1
0x18001faa6  mov     cl, [rsp+68h+arg_10]
0x18001faad  mov     [rsi], cl
0x18001faaf  lea     rcx, [rsp+68h+var_30]; this
0x18001fab4  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18001fab9  mov     al, dil
0x18001fabc  add     rsp, 50h
0x18001fac0  pop     rdi
0x18001fac1  pop     rsi
0x18001fac2  pop     rbx
0x18001fac3  retn
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
