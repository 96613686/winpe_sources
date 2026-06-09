# CredSerializationHelper::SerializeDATokenCredentials(IExecutionContextLite *,ushort const *,ulong,ushort const *,ulong,ushort const *,ulong,ushort const *,ulong,ushort const *,ulong,bool,uchar * *,ulong *)

- ea: `0x18004c46c`
- end: `0x18004c6fc`
- name: `?SerializeDATokenCredentials@CredSerializationHelper@@SAJPEAVIExecutionContextLite@@PEBGK1K1K1K1K_NPEAPEAEPEAK@Z`
- size: `656`
- prototype: `__int64 __fastcall(struct IExecutionContextLite *, const unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned int, bool, unsigned __int8 **, unsigned int *)`
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
- `0x18004c46c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18004c560`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18004c560`

## string_xrefs

- `0x18004c69b`: `pDAToken != nullptr && daTokenLengthCharacters != 0`
- `0x18004c4b2`: `CredSerializationHelper::SerializeDATokenCredentials`
- `0x18004c674`: `CredSerializationHelper::SerializeDATokenCredentials`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CredSerializationHelper::SerializeDATokenCredentials(
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
        int a12,
        unsigned __int8 **a13,
        unsigned int *a14)
{
  unsigned __int8 **v17; // rbx
  unsigned int *v18; // rdi
  _QWORD *v19; // rsi
  const unsigned __int16 *v20; // rdx
  const unsigned __int16 *v21; // rcx
  const char *v22; // rax
  unsigned int v23; // r8d
  unsigned int v24; // ebx
  char *v26; // [rsp+20h] [rbp-50h]
  void *v27; // [rsp+30h] [rbp-40h] BYREF
  __int64 v28; // [rsp+38h] [rbp-38h] BYREF
  _QWORD *v29; // [rsp+40h] [rbp-30h]
  _QWORD v30[5]; // [rsp+48h] [rbp-28h] BYREF

  a12 = 0;
  v27 = 0;
  v28 = 4;
  v29 = 0;
  v30[0] = "CredSerializationHelper::SerializeDATokenCredentials";
  v30[1] = &a12;
  v30[2] = 0;
  v30[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\serialization\\credserializationhelper.cpp",
    "CredSerializationHelper::SerializeDATokenCredentials",
    (const char *)0x1A5,
    0,
    (const unsigned __int16 *)v26);
  if ( !a2 || !a3 )
  {
    v22 = "pDAToken != nullptr && daTokenLengthCharacters != 0";
    v23 = 423;
    goto LABEL_20;
  }
  if ( !a4 || !a5 )
  {
    v22 = "pDAExpiryTime != nullptr && daExpiryTimeLengthCharacters != 0";
    v23 = 424;
    goto LABEL_20;
  }
  if ( !a6 || !a7 )
  {
    v22 = "pDACreationTime != nullptr && daCreationTimeLengthCharacters != 0";
    v23 = 425;
    goto LABEL_20;
  }
  v17 = a13;
  if ( !a13 || (v18 = a14) == 0 )
  {
    v22 = "ppEncoded != nullptr && pEncodedSizeBytes != nullptr";
    v23 = 426;
LABEL_20:
    a12 = -2147418113;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\serialization\\credserializationhelper.cpp",
      "CredSerializationHelper::SerializeDATokenCredentials",
      v23,
      -2147418113,
      v22);
    goto LABEL_21;
  }
  *a13 = 0;
  *v18 = 0;
  v28 = 0x500000004LL;
  v19 = malloc(0x78u);
  v29 = v19;
  if ( v19 )
  {
    CMIDLPtr<unsigned short *>::Clear(&v27);
    v27 = v19;
    *(_DWORD *)v29 = 8;
    v29[2] = a2;
    *((_DWORD *)v29 + 2) = a3;
    *((_DWORD *)v29 + 6) = 9;
    v29[5] = a4;
    *((_DWORD *)v29 + 8) = a5;
    *((_DWORD *)v29 + 12) = 10;
    v29[8] = a6;
    *((_DWORD *)v29 + 14) = a7;
    *((_DWORD *)v29 + 18) = 11;
    v20 = &qword_180063440;
    v21 = &qword_180063440;
    if ( a8 )
      v21 = a8;
    v29[11] = v21;
    *((_DWORD *)v29 + 20) = a9;
    *((_DWORD *)v29 + 24) = 12;
    if ( a10 )
      v20 = a10;
    v29[14] = v20;
    *((_DWORD *)v29 + 26) = a11;
    a12 = CredSerializationHelper::SerializeCredentials(a1, (struct _WLIDCredentialBag *)&v28, 0, v17, v18);
  }
  else
  {
    a12 = -2147024882;
  }
LABEL_21:
  v24 = a12;
  CTraceFuncW<long>::~CTraceFuncW<long>(v30);
  CMIDLPtr<unsigned short *>::Clear(&v27);
  return v24;
}

```

## disassembly

```asm
0x18004c46c  mov     rax, rsp
0x18004c46f  mov     [rax+20h], rbx
0x18004c473  mov     [rax+18h], r8d
0x18004c477  mov     [rax+10h], rdx
0x18004c47b  mov     [rax+8], rcx
0x18004c47f  push    rbp
0x18004c480  push    rsi
0x18004c481  push    rdi
0x18004c482  push    r12
0x18004c484  push    r13
0x18004c486  push    r14
0x18004c488  push    r15
0x18004c48a  mov     rbp, rsp
0x18004c48d  sub     rsp, 70h
0x18004c491  mov     r13, r9
0x18004c494  mov     ebx, r8d
0x18004c497  mov     rdi, rdx
0x18004c49a  xor     esi, esi
0x18004c49c  mov     [rbp+arg_58], esi
0x18004c4a2  mov     [rbp+var_40], rsi
0x18004c4a6  mov     [rbp+var_38], 4
0x18004c4ae  mov     [rbp+var_30], rsi
0x18004c4b2  lea     r15, aCredserializat_6; "CredSerializationHelper::SerializeDATok"...
0x18004c4b9  mov     [rbp+var_28], r15
0x18004c4bd  lea     rax, [rbp+arg_58]
0x18004c4c4  mov     [rbp+var_20], rax
0x18004c4c8  mov     [rbp+var_18], rsi
0x18004c4cc  mov     [rbp+var_10], rsi
0x18004c4d0  xor     r9d, r9d; unsigned int
0x18004c4d3  mov     r8d, 1A5h; char *
0x18004c4d9  mov     rdx, r15; char *
0x18004c4dc  lea     rcx, aOnecoreuapDsEx_21; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004c4e3  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18004c4e8  nop
0x18004c4e9  test    rdi, rdi
0x18004c4ec  jz      loc_18004C69B
0x18004c4f2  test    ebx, ebx
0x18004c4f4  jz      loc_18004C69B
0x18004c4fa  test    r13, r13
0x18004c4fd  jz      loc_18004C68C
0x18004c503  mov     r14d, [rbp+arg_20]
0x18004c507  test    r14d, r14d
0x18004c50a  jz      loc_18004C68C
0x18004c510  mov     r15, [rbp+arg_28]
0x18004c514  test    r15, r15
0x18004c517  jz      loc_18004C67D
0x18004c51d  mov     r12d, [rbp+arg_30]
0x18004c521  test    r12d, r12d
0x18004c524  jz      loc_18004C67D
0x18004c52a  mov     rbx, [rbp+arg_60]
0x18004c531  test    rbx, rbx
0x18004c534  jz      loc_18004C667
0x18004c53a  mov     rdi, [rbp+arg_68]
0x18004c541  test    rdi, rdi
0x18004c544  jz      loc_18004C667
0x18004c54a  mov     [rbx], rsi
0x18004c54d  mov     [rdi], esi
0x18004c54f  mov     dword ptr [rbp+var_38], 4
0x18004c556  mov     dword ptr [rbp+var_38+4], 5
0x18004c55d  lea     ecx, [rsi+78h]; Size
0x18004c560  call    cs:__imp_malloc
0x18004c566  mov     rsi, rax
0x18004c569  mov     [rbp+var_30], rax
0x18004c56d  test    rax, rax
0x18004c570  jnz     short loc_18004C581
0x18004c572  mov     [rbp+arg_58], 8007000Eh
0x18004c57c  jmp     loc_18004C6C9
0x18004c581  lea     rcx, [rbp+var_40]
0x18004c585  call    ?Clear@?$CMIDLPtr@PEAG@@QEAAXXZ; CMIDLPtr<ushort *>::Clear(void)
0x18004c58a  mov     [rbp+var_40], rsi
0x18004c58e  mov     rax, [rbp+var_30]
0x18004c592  mov     dword ptr [rax], 8
0x18004c598  mov     rax, [rbp+var_30]
0x18004c59c  mov     rcx, [rbp+arg_8]
0x18004c5a0  mov     [rax+10h], rcx
0x18004c5a4  mov     rax, [rbp+var_30]
0x18004c5a8  mov     ecx, [rbp+arg_10]
0x18004c5ab  mov     [rax+8], ecx
0x18004c5ae  mov     rax, [rbp+var_30]
0x18004c5b2  mov     dword ptr [rax+18h], 9
0x18004c5b9  mov     rax, [rbp+var_30]
0x18004c5bd  mov     [rax+28h], r13
0x18004c5c1  mov     rax, [rbp+var_30]
0x18004c5c5  mov     [rax+20h], r14d
0x18004c5c9  mov     rax, [rbp+var_30]
0x18004c5cd  mov     dword ptr [rax+30h], 0Ah
0x18004c5d4  mov     rax, [rbp+var_30]
0x18004c5d8  mov     [rax+40h], r15
0x18004c5dc  mov     rax, [rbp+var_30]
0x18004c5e0  mov     [rax+38h], r12d
0x18004c5e4  mov     rax, [rbp+var_30]
0x18004c5e8  mov     dword ptr [rax+48h], 0Bh
0x18004c5ef  mov     rax, [rbp+arg_38]
0x18004c5f3  lea     rdx, qword_180063440
0x18004c5fa  mov     rcx, rdx
0x18004c5fd  test    rax, rax
0x18004c600  cmovnz  rcx, rax
0x18004c604  mov     rax, [rbp+var_30]
0x18004c608  mov     [rax+58h], rcx
0x18004c60c  mov     ecx, [rbp+arg_40]
0x18004c612  mov     rax, [rbp+var_30]
0x18004c616  mov     [rax+50h], ecx
0x18004c619  mov     rax, [rbp+var_30]
0x18004c61d  mov     dword ptr [rax+60h], 0Ch
0x18004c624  mov     rax, [rbp+arg_48]
0x18004c62b  test    rax, rax
0x18004c62e  cmovnz  rdx, rax
0x18004c632  mov     rax, [rbp+var_30]
0x18004c636  mov     [rax+70h], rdx
0x18004c63a  mov     ecx, [rbp+arg_50]
0x18004c640  mov     rax, [rbp+var_30]
0x18004c644  mov     [rax+68h], ecx
0x18004c647  mov     [rsp+70h+var_50], rdi; unsigned int *
0x18004c64c  mov     r9, rbx; unsigned __int8 **
0x18004c64f  xor     r8d, r8d; bool
0x18004c652  lea     rdx, [rbp+var_38]; struct _WLIDCredentialBag *
0x18004c656  mov     rcx, [rbp+arg_0]; struct IExecutionContextLite *
0x18004c65a  call    ?SerializeCredentials@CredSerializationHelper@@SAJPEAVIExecutionContextLite@@PEAU_WLIDCredentialBag@@_NPEAPEAEPEAK@Z; CredSerializationHelper::SerializeCredentials(IExecutionContextLite *,_WLIDCredentialBag *,bool,uchar * *,ulong *)
0x18004c65f  mov     [rbp+arg_58], eax
0x18004c665  jmp     short loc_18004C6C9
0x18004c667  lea     rax, aPpencodedNullp; "ppEncoded != nullptr && pEncodedSizeByt"...
0x18004c66e  mov     r8d, 1AAh
0x18004c674  lea     rdx, aCredserializat_6; "CredSerializationHelper::SerializeDATok"...
0x18004c67b  jmp     short loc_18004C6AB
0x18004c67d  lea     rax, aPdacreationtim; "pDACreationTime != nullptr && daCreatio"...
0x18004c684  mov     r8d, 1A9h
0x18004c68a  jmp     short loc_18004C674
0x18004c68c  lea     rax, aPdaexpirytimeN; "pDAExpiryTime != nullptr && daExpiryTim"...
0x18004c693  mov     r8d, 1A8h
0x18004c699  jmp     short loc_18004C6A8
0x18004c69b  lea     rax, aPdatokenNullpt; "pDAToken != nullptr && daTokenLengthCha"...
0x18004c6a2  mov     r8d, 1A7h; unsigned int
0x18004c6a8  mov     rdx, r15; char *
0x18004c6ab  mov     r9d, 8000FFFFh; int
0x18004c6b1  mov     [rsp+70h+var_50], rax; char *
0x18004c6b6  mov     [rbp+arg_58], r9d
0x18004c6bd  lea     rcx, aOnecoreuapDsEx_21; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004c6c4  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18004c6c9  mov     ebx, [rbp+arg_58]
0x18004c6cf  lea     rcx, [rbp+var_28]
0x18004c6d3  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18004c6d8  nop
0x18004c6d9  lea     rcx, [rbp+var_40]
0x18004c6dd  call    ?Clear@?$CMIDLPtr@PEAG@@QEAAXXZ; CMIDLPtr<ushort *>::Clear(void)
0x18004c6e2  mov     eax, ebx
0x18004c6e4  mov     rbx, [rsp+70h+arg_18]
0x18004c6ec  add     rsp, 70h
0x18004c6f0  pop     r15
0x18004c6f2  pop     r14
0x18004c6f4  pop     r13
0x18004c6f6  pop     r12
0x18004c6f8  pop     rdi
0x18004c6f9  pop     rsi
0x18004c6fa  pop     rbp
0x18004c6fb  retn
```
