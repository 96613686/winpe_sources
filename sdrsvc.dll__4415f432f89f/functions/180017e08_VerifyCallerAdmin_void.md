# VerifyCallerAdmin(void)

- ea: `0x180017e08`
- end: `0x180017e89`
- name: `?VerifyCallerAdmin@@YAJXZ`
- size: `129`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000ff90`
- `0x1800101c0`

## callees

- `0x18001586c`
- `0x180015974`
- `0x180017e08`
- `0x18001f1ec`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180017e6d`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180017e6d`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180017e2b`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180017e2b`

## pseudocode

```c
__int64 VerifyCallerAdmin(void)
{
  unsigned int v0; // ebx
  int v2; // [rsp+20h] [rbp-48h] BYREF
  __int16 v3; // [rsp+24h] [rbp-44h]
  __int16 v4; // [rsp+26h] [rbp-42h]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v2, "VerifyCallerAdmin", 0x2ADu, 1u);
  if ( CoImpersonateClient() == -2147417833 )
  {
    v0 = 0;
    v2 = 0;
    v3 = 693;
  }
  else
  {
    v2 = VerifyCallerMembership(WinBuiltinAdministratorsSid);
    if ( v2 >= 0 )
      v3 = 697;
    else
      v4 = 697;
    CoRevertToSelf();
    v0 = v2;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v2);
  return v0;
}

```

## disassembly

```asm
0x180017e08  push    rbx
0x180017e0a  sub     rsp, 60h
0x180017e0e  mov     r9d, 1; unsigned __int16
0x180017e14  lea     rdx, aVerifycallerad; "VerifyCallerAdmin"
0x180017e1b  mov     r8d, 2ADh; unsigned __int16
0x180017e21  lea     rcx, [rsp+68h+var_48]; this
0x180017e26  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180017e2b  call    cs:__imp_CoImpersonateClient
0x180017e31  cmp     eax, 80010117h
0x180017e36  jnz     short loc_180017E4A
0x180017e38  xor     ebx, ebx
0x180017e3a  mov     eax, 2B5h
0x180017e3f  mov     [rsp+68h+var_48], ebx
0x180017e43  mov     [rsp+68h+var_44], ax
0x180017e48  jmp     short loc_180017E77
0x180017e4a  mov     ecx, 1Ah; WellKnownSidType
0x180017e4f  call    ?VerifyCallerMembership@@YAJW4WELL_KNOWN_SID_TYPE@@@Z; VerifyCallerMembership(WELL_KNOWN_SID_TYPE)
0x180017e54  mov     [rsp+68h+var_48], eax
0x180017e58  test    eax, eax
0x180017e5a  mov     eax, 2B9h
0x180017e5f  jns     short loc_180017E68
0x180017e61  mov     [rsp+68h+var_42], ax
0x180017e66  jmp     short loc_180017E6D
0x180017e68  mov     [rsp+68h+var_44], ax
0x180017e6d  call    cs:__imp_CoRevertToSelf
0x180017e73  mov     ebx, [rsp+68h+var_48]
0x180017e77  lea     rcx, [rsp+68h+var_48]; this
0x180017e7c  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180017e81  mov     eax, ebx
0x180017e83  add     rsp, 60h
0x180017e87  pop     rbx
0x180017e88  retn
```
