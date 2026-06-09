# VerifyCallerSystem(void)

- ea: `0x180017e90`
- end: `0x180017f11`
- name: `?VerifyCallerSystem@@YAJXZ`
- size: `129`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180010080`

## callees

- `0x18001586c`
- `0x180015974`
- `0x180017e90`
- `0x18001f1ec`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180017ef5`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180017ef5`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180017eb3`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180017eb3`

## pseudocode

```c
__int64 VerifyCallerSystem(void)
{
  unsigned int v0; // ebx
  int v2; // [rsp+20h] [rbp-48h] BYREF
  __int16 v3; // [rsp+24h] [rbp-44h]
  __int16 v4; // [rsp+26h] [rbp-42h]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v2, "VerifyCallerSystem", 0x292u, 1u);
  if ( CoImpersonateClient() == -2147417833 )
  {
    v0 = 0;
    v2 = 0;
    v3 = 666;
  }
  else
  {
    v2 = VerifyCallerMembership(WinLocalSystemSid);
    if ( v2 >= 0 )
      v3 = 670;
    else
      v4 = 670;
    CoRevertToSelf();
    v0 = v2;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v2);
  return v0;
}

```

## disassembly

```asm
0x180017e90  push    rbx
0x180017e92  sub     rsp, 60h
0x180017e96  mov     r9d, 1; unsigned __int16
0x180017e9c  lea     rdx, aVerifycallersy; "VerifyCallerSystem"
0x180017ea3  mov     r8d, 292h; unsigned __int16
0x180017ea9  lea     rcx, [rsp+68h+var_48]; this
0x180017eae  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180017eb3  call    cs:__imp_CoImpersonateClient
0x180017eb9  cmp     eax, 80010117h
0x180017ebe  jnz     short loc_180017ED2
0x180017ec0  xor     ebx, ebx
0x180017ec2  mov     eax, 29Ah
0x180017ec7  mov     [rsp+68h+var_48], ebx
0x180017ecb  mov     [rsp+68h+var_44], ax
0x180017ed0  jmp     short loc_180017EFF
0x180017ed2  mov     ecx, 16h; WellKnownSidType
0x180017ed7  call    ?VerifyCallerMembership@@YAJW4WELL_KNOWN_SID_TYPE@@@Z; VerifyCallerMembership(WELL_KNOWN_SID_TYPE)
0x180017edc  mov     [rsp+68h+var_48], eax
0x180017ee0  test    eax, eax
0x180017ee2  mov     eax, 29Eh
0x180017ee7  jns     short loc_180017EF0
0x180017ee9  mov     [rsp+68h+var_42], ax
0x180017eee  jmp     short loc_180017EF5
0x180017ef0  mov     [rsp+68h+var_44], ax
0x180017ef5  call    cs:__imp_CoRevertToSelf
0x180017efb  mov     ebx, [rsp+68h+var_48]
0x180017eff  lea     rcx, [rsp+68h+var_48]; this
0x180017f04  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180017f09  mov     eax, ebx
0x180017f0b  add     rsp, 60h
0x180017f0f  pop     rbx
0x180017f10  retn
```
