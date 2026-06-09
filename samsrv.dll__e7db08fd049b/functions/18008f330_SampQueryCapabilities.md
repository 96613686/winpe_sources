# SampQueryCapabilities

- ea: `0x18008f330`
- end: `0x18008f587`
- name: `SampQueryCapabilities`
- size: `599`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `13`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000ae10`
- `0x18004f2e0`
- `0x18005ba50`
- `0x180065fb4`
- `0x1800683fc`
- `0x1800888c0`
- `0x18008f300`
- `0x1800a3bf0`
- `0x1800a71e0`
- `0x1800a76d0`
- `0x1800a7940`
- `0x1800a7d70`
- `0x1800ae430`

## callees

- `0x1800028e0`
- `0x180006170`
- `0x1800066f0`
- `0x180012a28`
- `0x18001f900`
- `0x180021400`
- `0x180027ef8`
- `0x180027f2c`
- `0x18002cd80`
- `0x18002d720`
- `0x18008f330`

## import_xrefs

- `ntdll!RtlSubAuthorityCountSid` at `0x18008f3fa`
- `ntdll!RtlSubAuthorityCountSid` at `0x18008f3fa`
- `ntdll!RtlSubAuthoritySid` at `0x18008f410`
- `ntdll!RtlSubAuthoritySid` at `0x18008f410`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008f528`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008f528`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtLookupLocalKrbTgt` at `0x18008f4d1`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtLookupLocalKrbTgt` at `0x18008f4d1`

## pseudocode

```c
__int64 __fastcall SampQueryCapabilities(char a1, char a2)
{
  _QWORD *v2; // rbx
  __int64 v5; // rdx
  __int64 v6; // rcx
  bool v7; // zf
  __int64 result; // rax
  __int32 v9; // esi
  PUCHAR v10; // rax
  PULONG v11; // rax
  struct _PSAMP_DEFINED_DOMAINS *v12; // rdi
  unsigned int v13; // ebx
  char v14; // al
  int AccountContext2; // eax
  __int64 v16; // r8
  __int64 v17; // r9
  struct _DSNAME *v18; // rdi
  __int64 v19; // r14
  int v20; // eax
  int v21; // r8d
  PVOID HandleId; // [rsp+70h] [rbp-98h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp-90h] BYREF
  _BYTE v24[56]; // [rsp+80h] [rbp-88h] BYREF
  int v25; // [rsp+B8h] [rbp-50h]

  v2 = 0;
  HandleId = 0;
  if ( !(unsigned __int8)SampUsingDsData() || SampServiceState != 2 || !SampComputerObjectDsName )
    return 0;
  if ( a2 )
    _InterlockedExchange(&dword_1800F0AF4, 0);
  if ( !dword_1800F0AF4 )
  {
    v9 = 0;
    if ( (unsigned __int8)SampDsIsRunning(v6, v5) )
    {
      hMem = 0;
      memset_0(v24, 0, 0x50u);
      if ( !a1 && (int)SampExtMaybeBeginDsTransactionDs(0) < 0 )
      {
LABEL_30:
        SampExtMaybeEndDsTransactionDs(3);
        return (unsigned int)dword_1800F0AF0;
      }
      v10 = RtlSubAuthorityCountSid((char *)SampComputerObjectDsName + 24);
      v11 = RtlSubAuthoritySid((char *)SampComputerObjectDsName + 24, (unsigned int)*v10 - 1);
      v12 = SampDefinedDomains;
      v13 = *v11;
      v14 = SampUsingDsData();
      AccountContext2 = SampCreateAccountContext2(
                          *(_QWORD *)((char *)v12 + (v14 != 0 ? 0xAA0 : 0) + 1360),
                          4u,
                          v13,
                          0,
                          0,
                          3,
                          1u,
                          0,
                          0,
                          1,
                          0,
                          0,
                          0,
                          (__int64 *)&HandleId);
      v2 = HandleId;
      if ( AccountContext2 < 0 || (int)SampRetrieveUserV1aFixed(HandleId, v24, v16, v17) < 0 )
        goto LABEL_27;
      v18 = SampComputerObjectDsName;
      v19 = v2[22];
      v20 = SampShouldCallNtdsaApiSet();
      v21 = v20;
      if ( v20 != -1073741637 )
      {
        if ( v20 >= 0 )
          v21 = NtdsaExtLookupLocalKrbTgt(v19, v18, &hMem);
        if ( (int)(v21 + 0x80000000) >= 0 && v21 != -1073741151 )
        {
LABEL_27:
          if ( v2 )
            SampDeleteContext(v2);
          if ( a1 )
            return (unsigned int)dword_1800F0AF0;
          goto LABEL_30;
        }
      }
      if ( (v25 & 0x100) == 0 || hMem )
      {
        if ( (v25 & 0x100000) != 0 || hMem )
        {
          v9 = 1;
          if ( hMem )
            LocalFree(hMem);
        }
      }
      else
      {
        v9 = 2;
      }
    }
    _InterlockedExchange(&dword_1800F0AF0, v9);
    _InterlockedExchange(&dword_1800F0AF4, v9 != 0);
    goto LABEL_27;
  }
  v7 = (unsigned __int8)SampDsIsRunning(v6, v5) == 0;
  result = (unsigned int)dword_1800F0AF0;
  if ( v7 )
    return dword_1800F0AF0 | 4u;
  return result;
}

```

## disassembly

```asm
0x18008f330  push    rbx
0x18008f332  push    rbp
0x18008f333  push    rsi
0x18008f334  push    rdi
0x18008f335  push    r14
0x18008f337  sub     rsp, 0E0h
0x18008f33e  mov     rax, cs:__security_cookie
0x18008f345  xor     rax, rsp
0x18008f348  mov     [rsp+108h+var_38], rax
0x18008f350  xor     ebx, ebx
0x18008f352  mov     dil, dl
0x18008f355  mov     [rsp+108h+HandleId], rbx
0x18008f35a  mov     bpl, cl
0x18008f35d  call    SampUsingDsData
0x18008f362  test    al, al
0x18008f364  jz      loc_18008F567
0x18008f36a  cmp     cs:?SampServiceState@@3W4_SAMP_SERVICE_STATE@@A, 2; _SAMP_SERVICE_STATE SampServiceState
0x18008f371  jnz     loc_18008F567
0x18008f377  cmp     cs:?SampComputerObjectDsName@@3PEAU_DSNAME@@EA, rbx; _DSNAME * SampComputerObjectDsName
0x18008f37e  jz      loc_18008F567
0x18008f384  test    dil, dil
0x18008f387  jz      short loc_18008F391
0x18008f389  xor     eax, eax
0x18008f38b  xchg    eax, cs:dword_1800F0AF4
0x18008f391  cmp     cs:dword_1800F0AF4, ebx
0x18008f397  jz      short loc_18008F3B4
0x18008f399  call    SampDsIsRunning
0x18008f39e  test    al, al
0x18008f3a0  mov     eax, cs:dword_1800F0AF0
0x18008f3a6  jnz     loc_18008F569
0x18008f3ac  or      eax, 4
0x18008f3af  jmp     loc_18008F569
0x18008f3b4  xor     esi, esi
0x18008f3b6  call    SampDsIsRunning
0x18008f3bb  test    al, al
0x18008f3bd  jz      loc_18008F52E
0x18008f3c3  xor     edx, edx; Val
0x18008f3c5  mov     [rsp+108h+hMem], rbx
0x18008f3ca  lea     r8d, [rsi+50h]; Size
0x18008f3ce  lea     rcx, [rsp+108h+var_88]; void *
0x18008f3d6  call    memset_0
0x18008f3db  test    bpl, bpl
0x18008f3de  jnz     short loc_18008F3EF
0x18008f3e0  xor     ecx, ecx
0x18008f3e2  call    ?SampExtMaybeBeginDsTransactionDs@@YAJW4SAMP_DS_TRANSACTION_CONTROL@@@Z; SampExtMaybeBeginDsTransactionDs(SAMP_DS_TRANSACTION_CONTROL)
0x18008f3e7  test    eax, eax
0x18008f3e9  js      loc_18008F555
0x18008f3ef  mov     rcx, cs:?SampComputerObjectDsName@@3PEAU_DSNAME@@EA; _DSNAME * SampComputerObjectDsName
0x18008f3f6  add     rcx, 18h; Sid
0x18008f3fa  call    cs:__imp_RtlSubAuthorityCountSid
0x18008f400  mov     rcx, cs:?SampComputerObjectDsName@@3PEAU_DSNAME@@EA; _DSNAME * SampComputerObjectDsName
0x18008f407  add     rcx, 18h; Sid
0x18008f40b  movzx   edx, byte ptr [rax]
0x18008f40e  dec     edx; SubAuthority
0x18008f410  call    cs:__imp_RtlSubAuthoritySid
0x18008f416  mov     rdi, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x18008f41d  mov     ebx, [rax]
0x18008f41f  call    SampUsingDsData
0x18008f424  neg     al
0x18008f426  mov     r8d, ebx
0x18008f429  lea     rax, [rsp+108h+HandleId]
0x18008f42e  mov     [rsp+108h+var_A0], rax
0x18008f433  sbb     rcx, rcx
0x18008f436  mov     [rsp+108h+var_A8], rsi
0x18008f43b  and     ecx, 0AA0h
0x18008f441  mov     [rsp+108h+var_B0], sil
0x18008f446  xor     r9d, r9d
0x18008f449  mov     [rsp+108h+var_B8], sil
0x18008f44e  mov     [rsp+108h+var_C0], 1
0x18008f453  mov     rcx, [rcx+rdi+550h]
0x18008f45b  mov     [rsp+108h+var_C8], sil
0x18008f460  lea     edx, [r9+4]
0x18008f464  mov     [rsp+108h+var_D0], sil
0x18008f469  mov     [rsp+108h+var_D8], 1
0x18008f46e  mov     [rsp+108h+var_E0], 3
0x18008f476  mov     [rsp+108h+var_E8], rsi
0x18008f47b  call    SampCreateAccountContext2
0x18008f480  mov     rbx, [rsp+108h+HandleId]
0x18008f485  test    eax, eax
0x18008f487  js      loc_18008F543
0x18008f48d  lea     rdx, [rsp+108h+var_88]
0x18008f495  mov     rcx, rbx
0x18008f498  call    SampRetrieveUserV1aFixed
0x18008f49d  test    eax, eax
0x18008f49f  js      loc_18008F543
0x18008f4a5  mov     rdi, cs:?SampComputerObjectDsName@@3PEAU_DSNAME@@EA; _DSNAME * SampComputerObjectDsName
0x18008f4ac  mov     r14, [rbx+0B0h]
0x18008f4b3  call    ?SampShouldCallNtdsaApiSet@@YAJXZ; SampShouldCallNtdsaApiSet(void)
0x18008f4b8  mov     r8d, eax
0x18008f4bb  cmp     eax, 0C00000BBh
0x18008f4c0  jz      short loc_18008F4F0
0x18008f4c2  test    eax, eax
0x18008f4c4  js      short loc_18008F4DA
0x18008f4c6  lea     r8, [rsp+108h+hMem]
0x18008f4cb  mov     rdx, rdi
0x18008f4ce  mov     rcx, r14
0x18008f4d1  call    cs:__imp_NtdsaExtLookupLocalKrbTgt
0x18008f4d7  mov     r8d, eax
0x18008f4da  mov     ecx, 80000000h
0x18008f4df  lea     eax, [r8+rcx]
0x18008f4e3  test    ecx, eax
0x18008f4e5  jnz     short loc_18008F4F0
0x18008f4e7  cmp     r8d, 0C00002A1h
0x18008f4ee  jnz     short loc_18008F543
0x18008f4f0  test    [rsp+108h+var_50], 100h
0x18008f4fb  mov     rcx, [rsp+108h+hMem]; hMem
0x18008f500  jz      short loc_18008F50C
0x18008f502  test    rcx, rcx
0x18008f505  jnz     short loc_18008F50C
0x18008f507  lea     esi, [rcx+2]
0x18008f50a  jmp     short loc_18008F52E
0x18008f50c  test    [rsp+108h+var_50], 100000h
0x18008f517  jnz     short loc_18008F51E
0x18008f519  test    rcx, rcx
0x18008f51c  jz      short loc_18008F52E
0x18008f51e  mov     esi, 1
0x18008f523  test    rcx, rcx
0x18008f526  jz      short loc_18008F52E
0x18008f528  call    cs:__imp_LocalFree
0x18008f52e  xor     edx, edx
0x18008f530  mov     eax, esi
0x18008f532  xchg    eax, cs:dword_1800F0AF0
0x18008f538  test    esi, esi
0x18008f53a  setnz   dl
0x18008f53d  xchg    edx, cs:dword_1800F0AF4
0x18008f543  test    rbx, rbx
0x18008f546  jz      short loc_18008F550
0x18008f548  mov     rcx, rbx; HandleId
0x18008f54b  call    SampDeleteContext
0x18008f550  test    bpl, bpl
0x18008f553  jnz     short loc_18008F55F
0x18008f555  mov     ecx, 3
0x18008f55a  call    ?SampExtMaybeEndDsTransactionDs@@YAJW4SAMP_DS_TRANSACTION_CONTROL@@@Z; SampExtMaybeEndDsTransactionDs(SAMP_DS_TRANSACTION_CONTROL)
0x18008f55f  mov     eax, cs:dword_1800F0AF0
0x18008f565  jmp     short loc_18008F569
0x18008f567  xor     eax, eax
0x18008f569  mov     rcx, [rsp+108h+var_38]
0x18008f571  xor     rcx, rsp; StackCookie
0x18008f574  call    __security_check_cookie
0x18008f579  add     rsp, 0E0h
0x18008f580  pop     r14
0x18008f582  pop     rdi
0x18008f583  pop     rsi
0x18008f584  pop     rbp
0x18008f585  pop     rbx
0x18008f586  retn
```
