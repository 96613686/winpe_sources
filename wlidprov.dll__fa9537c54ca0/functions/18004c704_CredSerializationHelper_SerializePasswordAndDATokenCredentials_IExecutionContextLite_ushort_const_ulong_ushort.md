# CredSerializationHelper::SerializePasswordAndDATokenCredentials(IExecutionContextLite *,ushort const *,ulong,ushort const *,ulong,ushort const *,ulong,ushort const *,ulong,ushort const *,ulong,ushort const *,ulong,bool,uchar * *,ulong *)

- ea: `0x18004c704`
- end: `0x18004c9ec`
- name: `?SerializePasswordAndDATokenCredentials@CredSerializationHelper@@SAJPEAVIExecutionContextLite@@PEBGK1K1K1K1K1K_NPEAPEAEPEAK@Z`
- size: `744`
- prototype: `__int64 __fastcall(struct IExecutionContextLite *, const unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned int, bool, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800332a0`

## callees

- `0x1800061a8`
- `0x1800090c0`
- `0x180009630`
- `0x180013434`
- `0x18004c2a4`
- `0x18004c704`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18004c81b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18004c81b`

## string_xrefs

- `0x18004c74d`: `CredSerializationHelper::SerializePasswordAndDATokenCredentials`
- `0x18004c95c`: `CredSerializationHelper::SerializePasswordAndDATokenCredentials`
- `0x18004c983`: `pDAToken != nullptr && daTokenLengthCharacters != 0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CredSerializationHelper::SerializePasswordAndDATokenCredentials(
        struct IExecutionContextLite *a1,
        const unsigned __int16 *a2,
        int a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        const unsigned __int16 *a6,
        unsigned int a7,
        const unsigned __int16 *a8,
        unsigned int a9,
        const unsigned __int16 *a10,
        unsigned int a11,
        const unsigned __int16 *a12,
        unsigned int a13,
        int a14,
        unsigned __int8 **a15,
        unsigned int *a16)
{
  unsigned __int8 **v19; // rbx
  unsigned int *v20; // rdi
  _QWORD *v21; // rsi
  const unsigned __int16 *v22; // rdx
  const unsigned __int16 *v23; // rcx
  const char *v24; // rax
  unsigned int v25; // r8d
  unsigned int v26; // ebx
  char *v28; // [rsp+20h] [rbp-58h]
  void *v29; // [rsp+30h] [rbp-48h] BYREF
  __int64 v30; // [rsp+38h] [rbp-40h] BYREF
  _QWORD *v31; // [rsp+40h] [rbp-38h]
  _QWORD v32[6]; // [rsp+48h] [rbp-30h] BYREF

  a14 = 0;
  v29 = 0;
  v30 = 3;
  v31 = 0;
  v32[0] = "CredSerializationHelper::SerializePasswordAndDATokenCredentials";
  v32[1] = &a14;
  v32[2] = 0;
  v32[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\serialization\\credserializationhelper.cpp",
    "CredSerializationHelper::SerializePasswordAndDATokenCredentials",
    (const char *)0x173,
    0,
    (const unsigned __int16 *)v28);
  if ( !a2 || !a3 )
  {
    v24 = "pPassword != nullptr && passwordLengthCharacters != 0";
    v25 = 373;
    goto LABEL_23;
  }
  if ( !a4 || !a5 )
  {
    v24 = "pDAToken != nullptr && daTokenLengthCharacters != 0";
    v25 = 374;
    goto LABEL_23;
  }
  if ( !a6 || !a7 )
  {
    v24 = "pDAExpiryTime != nullptr && daExpiryTimeLengthCharacters != 0";
    v25 = 375;
    goto LABEL_23;
  }
  if ( !a8 || !a9 )
  {
    v24 = "pDACreationTime != nullptr && daCreationTimeLengthCharacters != 0";
    v25 = 376;
    goto LABEL_23;
  }
  v19 = a15;
  if ( !a15 || (v20 = a16) == 0 )
  {
    v24 = "ppEncoded != nullptr && pEncodedSizeBytes != nullptr";
    v25 = 377;
LABEL_23:
    a14 = -2147418113;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\serialization\\credserializationhelper.cpp",
      "CredSerializationHelper::SerializePasswordAndDATokenCredentials",
      v25,
      -2147418113,
      v24);
    goto LABEL_24;
  }
  *a15 = 0;
  *v20 = 0;
  v30 = 0x600000003LL;
  v21 = malloc(0x90u);
  v31 = v21;
  if ( v21 )
  {
    CMIDLPtr<unsigned short *>::Clear(&v29);
    v29 = v21;
    *(_DWORD *)v31 = 1;
    v31[2] = a2;
    *((_DWORD *)v31 + 2) = a3;
    *((_DWORD *)v31 + 6) = 8;
    v31[5] = a4;
    *((_DWORD *)v31 + 8) = a5;
    *((_DWORD *)v31 + 12) = 9;
    v31[8] = a6;
    *((_DWORD *)v31 + 14) = a7;
    *((_DWORD *)v31 + 18) = 10;
    v31[11] = a8;
    *((_DWORD *)v31 + 20) = a9;
    *((_DWORD *)v31 + 24) = 11;
    v22 = &qword_180063440;
    v23 = &qword_180063440;
    if ( a10 )
      v23 = a10;
    v31[14] = v23;
    *((_DWORD *)v31 + 26) = a11;
    *((_DWORD *)v31 + 30) = 12;
    if ( a12 )
      v22 = a12;
    v31[17] = v22;
    *((_DWORD *)v31 + 32) = a13;
    a14 = CredSerializationHelper::SerializeCredentials(a1, (struct _WLIDCredentialBag *)&v30, 0, v19, v20);
  }
  else
  {
    a14 = -2147024882;
  }
LABEL_24:
  v26 = a14;
  CTraceFuncW<long>::~CTraceFuncW<long>(v32);
  CMIDLPtr<unsigned short *>::Clear(&v29);
  return v26;
}

```

## disassembly

```asm
0x18004c704  mov     rax, rsp
0x18004c707  mov     [rax+20h], r9
0x18004c70b  mov     [rax+18h], r8d
0x18004c70f  mov     [rax+10h], rdx
0x18004c713  mov     [rax+8], rcx
0x18004c717  push    rbp
0x18004c718  push    rbx
0x18004c719  push    rsi
0x18004c71a  push    rdi
0x18004c71b  push    r12
0x18004c71d  push    r13
0x18004c71f  push    r14
0x18004c721  push    r15
0x18004c723  mov     rbp, rsp
0x18004c726  sub     rsp, 78h
0x18004c72a  mov     rbx, r9
0x18004c72d  mov     edi, r8d
0x18004c730  mov     rsi, rdx
0x18004c733  xor     r13d, r13d
0x18004c736  mov     [rbp+arg_68], r13d
0x18004c73d  mov     [rbp+var_48], r13
0x18004c741  mov     [rbp+var_40], 3
0x18004c749  mov     [rbp+var_38], r13
0x18004c74d  lea     r15, aCredserializat_0; "CredSerializationHelper::SerializePassw"...
0x18004c754  mov     [rbp+var_30], r15
0x18004c758  lea     rax, [rbp+arg_68]
0x18004c75f  mov     [rbp+var_28], rax
0x18004c763  mov     [rbp+var_20], r13
0x18004c767  mov     [rbp+var_18], r13
0x18004c76b  xor     r9d, r9d; unsigned int
0x18004c76e  mov     r8d, 173h; char *
0x18004c774  mov     rdx, r15; char *
0x18004c777  lea     rcx, aOnecoreuapDsEx_21; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004c77e  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18004c783  nop
0x18004c784  test    rsi, rsi
0x18004c787  jz      loc_18004C992
0x18004c78d  test    edi, edi
0x18004c78f  jz      loc_18004C992
0x18004c795  test    rbx, rbx
0x18004c798  jz      loc_18004C983
0x18004c79e  mov     r14d, [rbp+arg_20]
0x18004c7a2  test    r14d, r14d
0x18004c7a5  jz      loc_18004C983
0x18004c7ab  mov     r15, [rbp+arg_28]
0x18004c7af  test    r15, r15
0x18004c7b2  jz      loc_18004C974
0x18004c7b8  mov     r12d, [rbp+arg_30]
0x18004c7bc  test    r12d, r12d
0x18004c7bf  jz      loc_18004C974
0x18004c7c5  mov     r13, [rbp+arg_38]
0x18004c7cc  xor     eax, eax
0x18004c7ce  test    r13, r13
0x18004c7d1  jz      loc_18004C965
0x18004c7d7  cmp     [rbp+arg_40], eax
0x18004c7dd  jz      loc_18004C965
0x18004c7e3  mov     rbx, [rbp+arg_70]
0x18004c7ea  test    rbx, rbx
0x18004c7ed  jz      loc_18004C94F
0x18004c7f3  mov     rdi, [rbp+arg_78]
0x18004c7fa  test    rdi, rdi
0x18004c7fd  jz      loc_18004C94F
0x18004c803  mov     [rbx], rax
0x18004c806  mov     [rdi], eax
0x18004c808  mov     dword ptr [rbp+var_40], 3
0x18004c80f  mov     dword ptr [rbp+var_40+4], 6
0x18004c816  mov     ecx, 90h; Size
0x18004c81b  call    cs:__imp_malloc
0x18004c821  mov     rsi, rax
0x18004c824  mov     [rbp+var_38], rax
0x18004c828  test    rax, rax
0x18004c82b  jnz     short loc_18004C83C
0x18004c82d  mov     [rbp+arg_68], 8007000Eh
0x18004c837  jmp     loc_18004C9C0
0x18004c83c  lea     rcx, [rbp+var_48]
0x18004c840  call    ?Clear@?$CMIDLPtr@PEAG@@QEAAXXZ; CMIDLPtr<ushort *>::Clear(void)
0x18004c845  mov     [rbp+var_48], rsi
0x18004c849  mov     rax, [rbp+var_38]
0x18004c84d  mov     dword ptr [rax], 1
0x18004c853  mov     rax, [rbp+var_38]
0x18004c857  mov     rcx, [rbp+arg_8]
0x18004c85b  mov     [rax+10h], rcx
0x18004c85f  mov     rax, [rbp+var_38]
0x18004c863  mov     ecx, [rbp+arg_10]
0x18004c866  mov     [rax+8], ecx
0x18004c869  mov     rax, [rbp+var_38]
0x18004c86d  mov     dword ptr [rax+18h], 8
0x18004c874  mov     rax, [rbp+var_38]
0x18004c878  mov     rcx, [rbp+arg_18]
0x18004c87c  mov     [rax+28h], rcx
0x18004c880  mov     rax, [rbp+var_38]
0x18004c884  mov     [rax+20h], r14d
0x18004c888  mov     rax, [rbp+var_38]
0x18004c88c  mov     dword ptr [rax+30h], 9
0x18004c893  mov     rax, [rbp+var_38]
0x18004c897  mov     [rax+40h], r15
0x18004c89b  mov     rax, [rbp+var_38]
0x18004c89f  mov     [rax+38h], r12d
0x18004c8a3  mov     rax, [rbp+var_38]
0x18004c8a7  mov     dword ptr [rax+48h], 0Ah
0x18004c8ae  mov     rax, [rbp+var_38]
0x18004c8b2  mov     [rax+58h], r13
0x18004c8b6  mov     rax, [rbp+var_38]
0x18004c8ba  mov     ecx, [rbp+arg_40]
0x18004c8c0  mov     [rax+50h], ecx
0x18004c8c3  mov     rax, [rbp+var_38]
0x18004c8c7  mov     dword ptr [rax+60h], 0Bh
0x18004c8ce  mov     rax, [rbp+arg_48]
0x18004c8d5  lea     rdx, qword_180063440
0x18004c8dc  mov     rcx, rdx
0x18004c8df  test    rax, rax
0x18004c8e2  cmovnz  rcx, rax
0x18004c8e6  mov     rax, [rbp+var_38]
0x18004c8ea  mov     [rax+70h], rcx
0x18004c8ee  mov     ecx, [rbp+arg_50]
0x18004c8f4  mov     rax, [rbp+var_38]
0x18004c8f8  mov     [rax+68h], ecx
0x18004c8fb  mov     rax, [rbp+var_38]
0x18004c8ff  mov     dword ptr [rax+78h], 0Ch
0x18004c906  mov     rax, [rbp+arg_58]
0x18004c90d  test    rax, rax
0x18004c910  cmovnz  rdx, rax
0x18004c914  mov     rax, [rbp+var_38]
0x18004c918  mov     [rax+88h], rdx
0x18004c91f  mov     ecx, [rbp+arg_60]
0x18004c925  mov     rax, [rbp+var_38]
0x18004c929  mov     [rax+80h], ecx
0x18004c92f  mov     [rsp+78h+var_58], rdi; unsigned int *
0x18004c934  mov     r9, rbx; unsigned __int8 **
0x18004c937  xor     r8d, r8d; bool
0x18004c93a  lea     rdx, [rbp+var_40]; struct _WLIDCredentialBag *
0x18004c93e  mov     rcx, [rbp+arg_0]; struct IExecutionContextLite *
0x18004c942  call    ?SerializeCredentials@CredSerializationHelper@@SAJPEAVIExecutionContextLite@@PEAU_WLIDCredentialBag@@_NPEAPEAEPEAK@Z; CredSerializationHelper::SerializeCredentials(IExecutionContextLite *,_WLIDCredentialBag *,bool,uchar * *,ulong *)
0x18004c947  mov     [rbp+arg_68], eax
0x18004c94d  jmp     short loc_18004C9C0
0x18004c94f  lea     rax, aPpencodedNullp; "ppEncoded != nullptr && pEncodedSizeByt"...
0x18004c956  mov     r8d, 179h
0x18004c95c  lea     rdx, aCredserializat_0; "CredSerializationHelper::SerializePassw"...
0x18004c963  jmp     short loc_18004C9A2
0x18004c965  lea     rax, aPdacreationtim; "pDACreationTime != nullptr && daCreatio"...
0x18004c96c  mov     r8d, 178h
0x18004c972  jmp     short loc_18004C95C
0x18004c974  lea     rax, aPdaexpirytimeN; "pDAExpiryTime != nullptr && daExpiryTim"...
0x18004c97b  mov     r8d, 177h
0x18004c981  jmp     short loc_18004C95C
0x18004c983  lea     rax, aPdatokenNullpt; "pDAToken != nullptr && daTokenLengthCha"...
0x18004c98a  mov     r8d, 176h
0x18004c990  jmp     short loc_18004C99F
0x18004c992  lea     rax, aPpasswordNullp; "pPassword != nullptr && passwordLengthC"...
0x18004c999  mov     r8d, 175h; unsigned int
0x18004c99f  mov     rdx, r15; char *
0x18004c9a2  mov     r9d, 8000FFFFh; int
0x18004c9a8  mov     [rsp+78h+var_58], rax; char *
0x18004c9ad  mov     [rbp+arg_68], r9d
0x18004c9b4  lea     rcx, aOnecoreuapDsEx_21; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004c9bb  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18004c9c0  mov     ebx, [rbp+arg_68]
0x18004c9c6  lea     rcx, [rbp+var_30]
0x18004c9ca  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18004c9cf  nop
0x18004c9d0  lea     rcx, [rbp+var_48]
0x18004c9d4  call    ?Clear@?$CMIDLPtr@PEAG@@QEAAXXZ; CMIDLPtr<ushort *>::Clear(void)
0x18004c9d9  mov     eax, ebx
0x18004c9db  add     rsp, 78h
0x18004c9df  pop     r15
0x18004c9e1  pop     r14
0x18004c9e3  pop     r13
0x18004c9e5  pop     r12
0x18004c9e7  pop     rdi
0x18004c9e8  pop     rsi
0x18004c9e9  pop     rbx
0x18004c9ea  pop     rbp
0x18004c9eb  retn
```
