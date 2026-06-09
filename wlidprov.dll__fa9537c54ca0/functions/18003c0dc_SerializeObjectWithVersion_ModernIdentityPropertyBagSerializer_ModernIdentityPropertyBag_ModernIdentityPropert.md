# SerializeObjectWithVersion<ModernIdentityPropertyBagSerializer,_ModernIdentityPropertyBag>(ModernIdentityPropertyBagSerializer &,_ModernIdentityPropertyBag &,ulong,uchar * *,ulong *)

- ea: `0x18003c0dc`
- end: `0x18003c37f`
- name: `??$SerializeObjectWithVersion@VModernIdentityPropertyBagSerializer@@U_ModernIdentityPropertyBag@@@@YAJAEAVModernIdentityPropertyBagSerializer@@AEAU_ModernIdentityPropertyBag@@KPEAPEAEPEAK@Z`
- size: `675`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18003f5c0`

## callees

- `0x180004b2c`
- `0x1800061a8`
- `0x1800090c0`
- `0x180009630`
- `0x18000a400`
- `0x18001173c`
- `0x180013434`
- `0x1800392b0`
- `0x18003bcf4`
- `0x18003c0dc`
- `0x180058010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18003c25c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18003c25c`

## string_xrefs

- `0x18003c2cc`: `hr = SafeCopyMemory(apLocalResultBuffer + sizeof(version), bufferSize - sizeof(version), pEncryptedOut.pbData, pEncryptedOut.cbData)`
- `0x18003c2db`: `hr = SafeCopyMemory(apLocalResultBuffer, bufferSize, &version, sizeof(version))`
- `0x18003c329`: `SerializeObjectWithVersion() completed with hr = 0x%x.`

## pseudocode

```c
__int64 __fastcall SerializeObjectWithVersion<ModernIdentityPropertyBagSerializer,_ModernIdentityPropertyBag>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4,
        _DWORD *a5)
{
  _DWORD *v8; // r15
  int v9; // eax
  __int64 v10; // rax
  __int64 v11; // rax
  signed int v12; // eax
  rsize_t v13; // rbx
  size_t v14; // rsi
  char *v15; // rbx
  const char *v16; // rax
  unsigned int v17; // r8d
  unsigned int v18; // r8d
  unsigned __int8 v19; // cl
  unsigned int v20; // ebx
  char *v22; // [rsp+20h] [rbp-81h]
  char *v23; // [rsp+20h] [rbp-81h]
  char *v24; // [rsp+50h] [rbp-51h] BYREF
  int Source; // [rsp+58h] [rbp-49h] BYREF
  __int64 v26; // [rsp+60h] [rbp-41h] BYREF
  rsize_t SourceSize[2]; // [rsp+68h] [rbp-39h] BYREF
  __int128 v28; // [rsp+78h] [rbp-29h] BYREF
  _QWORD v29[3]; // [rsp+88h] [rbp-19h] BYREF
  _QWORD v30[10]; // [rsp+A0h] [rbp-1h] BYREF
  int v31; // [rsp+110h] [rbp+6Fh] BYREF
  int v32; // [rsp+118h] [rbp+77h] BYREF

  Source = 1;
  v31 = 0;
  v26 = 0;
  v24 = 0;
  v32 = 0;
  v28 = 0;
  *(_OWORD *)SourceSize = 0;
  memset(v29, 0, sizeof(v29));
  v30[0] = "SerializeObjectWithVersion";
  v30[1] = &v31;
  v30[2] = 0;
  v30[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\Live\\identity\\Include\\SerializationDefinition.h",
    "SerializeObjectWithVersion",
    (const char *)0x109,
    0,
    (const unsigned __int16 *)v22);
  *a4 = 0;
  v8 = a5;
  *a5 = 0;
  v9 = SerializeObject<ModernIdentityPropertyBagSerializer,_ModernIdentityPropertyBag>(a1, a2, &v26, &v32);
  v31 = v9;
  if ( v9 < 0 )
    goto LABEL_16;
  LODWORD(v28) = v32;
  *((_QWORD *)&v28 + 1) = v26;
  v10 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 24LL))(*a1);
  if ( (*(unsigned int (__fastcall **)(__int64, __int128 *, _QWORD, _QWORD, _QWORD, _QWORD, int, rsize_t *))(*(_QWORD *)v10 + 8LL))(
         v10,
         &v28,
         0,
         0,
         0,
         0,
         1,
         SourceSize) )
  {
    v13 = SourceSize[1];
    Auto<unsigned char *,LocalAllocFunctor<unsigned char *>,DummyContext>::Clear(v29);
    v29[0] = v13;
    v14 = (unsigned int)(LODWORD(SourceSize[0]) + 4);
    v15 = (char *)malloc(v14);
    CMIDLPtr<unsigned short *>::Clear(&v24);
    v24 = v15;
    if ( !v15 )
    {
      v9 = -2147024882;
      v31 = -2147024882;
      goto LABEL_16;
    }
    if ( memcpy_s_3(v15, (unsigned int)v14, &Source, 4u) )
    {
      v16 = "hr = SafeCopyMemory(apLocalResultBuffer, bufferSize, &version, sizeof(version))";
      v17 = 308;
    }
    else
    {
      v31 = 0;
      if ( !memcpy_s_3(v15 + 4, v14 - 4, (const void *const)SourceSize[1], LODWORD(SourceSize[0])) )
      {
        v9 = 0;
        v31 = 0;
        v24 = 0;
        *a4 = v15;
        *v8 = v14;
        goto LABEL_15;
      }
      v16 = "hr = SafeCopyMemory(apLocalResultBuffer + sizeof(version), bufferSize - sizeof(version), pEncryptedOut.pbDat"
            "a, pEncryptedOut.cbData)";
      v17 = 309;
    }
    v31 = -2147418113;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\Live\\identity\\Include\\SerializationDefinition.h",
      "SerializeObjectWithVersion",
      v17,
      -2147418113,
      v16);
  }
  else
  {
    v11 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 24LL))(*a1);
    v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 120LL))(v11);
    if ( v12 > 0 )
      v12 = (unsigned __int16)v12 | 0x80070000;
    v31 = v12;
    LODWORD(v23) = v12;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\Live\\identity\\Include\\SerializationDefinition.h",
      0x126u,
      L"CryptProtectData failed. error=0x%x.",
      v23);
  }
  v9 = v31;
LABEL_15:
  if ( v9 >= 0 )
  {
    v18 = 321;
    v19 = 5;
    goto LABEL_18;
  }
LABEL_16:
  v18 = 317;
  v19 = 2;
LABEL_18:
  LODWORD(v23) = v9;
  TracePrintW(
    v19,
    "onecoreuap\\ds\\ext\\Live\\identity\\Include\\SerializationDefinition.h",
    v18,
    L"SerializeObjectWithVersion() completed with hr = 0x%x.",
    v23);
  v20 = v31;
  CTraceFuncW<long>::~CTraceFuncW<long>(v30);
  Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>(v29);
  CMIDLPtr<unsigned short *>::Clear(&v24);
  CMIDLPtr<unsigned short *>::Clear(&v26);
  return v20;
}

```

## disassembly

```asm
0x18003c0dc  mov     [rsp-8+arg_0], rbx
0x18003c0e1  mov     [rsp-8+arg_10], r8d
0x18003c0e6  push    rbp
0x18003c0e7  push    rsi
0x18003c0e8  push    rdi
0x18003c0e9  push    r12
0x18003c0eb  push    r13
0x18003c0ed  push    r14
0x18003c0ef  push    r15
0x18003c0f1  lea     rbp, [rsp-1Fh]
0x18003c0f6  sub     rsp, 0C0h
0x18003c0fd  mov     r14, r9
0x18003c100  mov     rbx, rdx
0x18003c103  mov     rdi, rcx
0x18003c106  mov     esi, 1
0x18003c10b  mov     [rbp+4Fh+Source], esi
0x18003c10e  xor     r12d, r12d
0x18003c111  mov     [rbp+4Fh+arg_10], r12d
0x18003c115  mov     [rbp+4Fh+var_90], r12
0x18003c119  mov     [rbp+4Fh+var_A0], r12
0x18003c11d  mov     [rbp+4Fh+arg_18], r12d
0x18003c121  xorps   xmm0, xmm0
0x18003c124  movups  [rbp+4Fh+var_78], xmm0
0x18003c128  xorps   xmm1, xmm1
0x18003c12b  movups  xmmword ptr [rbp+4Fh+SourceSize], xmm1
0x18003c12f  mov     [rbp+4Fh+var_68], r12
0x18003c133  mov     [rbp+4Fh+var_58], r12
0x18003c137  mov     [rbp+4Fh+var_60], r12
0x18003c13b  lea     rcx, aSerializeobjec; "SerializeObjectWithVersion"
0x18003c142  mov     [rbp+4Fh+var_50], rcx
0x18003c146  lea     rax, [rbp+4Fh+arg_10]
0x18003c14a  mov     [rbp+4Fh+var_48], rax
0x18003c14e  mov     [rbp+4Fh+var_40], r12
0x18003c152  mov     [rbp+4Fh+var_38], r12
0x18003c156  xor     r9d, r9d; unsigned int
0x18003c159  mov     r8d, 109h; char *
0x18003c15f  mov     rdx, rcx; char *
0x18003c162  lea     r13, aOnecoreuapDsEx_7; "onecoreuap\\ds\\ext\\Live\\identity\\In"...
0x18003c169  mov     rcx, r13; this
0x18003c16c  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18003c171  nop
0x18003c172  mov     [r14], r12
0x18003c175  mov     r15, [rbp+4Fh+arg_20]
0x18003c179  mov     [r15], r12d
0x18003c17c  lea     r9, [rbp+4Fh+arg_18]
0x18003c180  lea     r8, [rbp+4Fh+var_90]
0x18003c184  mov     rdx, rbx
0x18003c187  mov     rcx, rdi
0x18003c18a  call    ??$SerializeObject@VModernIdentityPropertyBagSerializer@@U_ModernIdentityPropertyBag@@@@YAJAEAVModernIdentityPropertyBagSerializer@@AEAU_ModernIdentityPropertyBag@@PEAPEAEPEAK@Z; SerializeObject<ModernIdentityPropertyBagSerializer,_ModernIdentityPropertyBag>(ModernIdentityPropertyBagSerializer &,_ModernIdentityPropertyBag &,uchar * *,ulong *)
0x18003c18f  mov     [rbp+4Fh+arg_10], eax
0x18003c192  test    eax, eax
0x18003c194  js      loc_18003C30D
0x18003c19a  mov     eax, [rbp+4Fh+arg_18]
0x18003c19d  mov     dword ptr [rbp+4Fh+var_78], eax
0x18003c1a0  mov     rax, [rbp+4Fh+var_90]
0x18003c1a4  mov     qword ptr [rbp+4Fh+var_78+8], rax
0x18003c1a8  mov     rcx, [rdi]
0x18003c1ab  mov     rax, [rcx]
0x18003c1ae  mov     rax, [rax+18h]
0x18003c1b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c1b7  mov     r10, rax
0x18003c1ba  mov     rcx, [rax]
0x18003c1bd  mov     rax, [rcx+8]
0x18003c1c1  lea     rcx, [rbp+4Fh+SourceSize]
0x18003c1c5  mov     [rsp+0F0h+var_B8], rcx
0x18003c1ca  mov     [rsp+0F0h+var_C0], esi
0x18003c1ce  mov     [rsp+0F0h+var_C8], r12
0x18003c1d3  mov     [rsp+0F0h+var_D0], r12
0x18003c1d8  xor     r9d, r9d
0x18003c1db  xor     r8d, r8d
0x18003c1de  lea     rdx, [rbp+4Fh+var_78]
0x18003c1e2  mov     rcx, r10
0x18003c1e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c1ea  test    eax, eax
0x18003c1ec  jnz     short loc_18003C241
0x18003c1ee  mov     rcx, [rdi]
0x18003c1f1  mov     rax, [rcx]
0x18003c1f4  mov     rax, [rax+18h]
0x18003c1f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c1fd  mov     rdx, rax
0x18003c200  mov     rcx, [rax]
0x18003c203  mov     rax, [rcx+78h]
0x18003c207  mov     rcx, rdx
0x18003c20a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c20f  test    eax, eax
0x18003c211  jle     short loc_18003C21B
0x18003c213  movzx   eax, ax
0x18003c216  or      eax, 80070000h
0x18003c21b  mov     [rbp+4Fh+arg_10], eax
0x18003c21e  mov     dword ptr [rsp+0F0h+var_D0], eax
0x18003c222  lea     r9, aCryptprotectda_0; "CryptProtectData failed. error=0x%x."
0x18003c229  mov     r8d, 126h; unsigned int
0x18003c22f  mov     rdx, r13; char *
0x18003c232  mov     ecx, 2; unsigned __int8
0x18003c237  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18003c23c  jmp     loc_18003C306
0x18003c241  mov     rbx, [rbp+4Fh+SourceSize+8]
0x18003c245  lea     rcx, [rbp+4Fh+var_68]
0x18003c249  call    ?Clear@?$Auto@PEAEV?$LocalAllocFunctor@PEAE@@VDummyContext@@@@QEAAXXZ; Auto<uchar *,LocalAllocFunctor<uchar *>,DummyContext>::Clear(void)
0x18003c24e  mov     [rbp+4Fh+var_68], rbx
0x18003c252  mov     esi, dword ptr [rbp+4Fh+SourceSize]
0x18003c255  add     esi, 4
0x18003c258  mov     edi, esi
0x18003c25a  mov     ecx, esi; Size
0x18003c25c  call    cs:__imp_malloc
0x18003c262  mov     rbx, rax
0x18003c265  lea     rcx, [rbp+4Fh+var_A0]
0x18003c269  call    ?Clear@?$CMIDLPtr@PEAG@@QEAAXXZ; CMIDLPtr<ushort *>::Clear(void)
0x18003c26e  mov     [rbp+4Fh+var_A0], rbx
0x18003c272  test    rbx, rbx
0x18003c275  jnz     short loc_18003C284
0x18003c277  mov     eax, 8007000Eh
0x18003c27c  mov     [rbp+4Fh+arg_10], eax
0x18003c27f  jmp     loc_18003C30D
0x18003c284  mov     r9d, 4; SourceSize
0x18003c28a  lea     r8, [rbp+4Fh+Source]; Source
0x18003c28e  mov     rdx, rdi; DestinationSize
0x18003c291  mov     rcx, rbx; Destination
0x18003c294  call    memcpy_s_3
0x18003c299  test    eax, eax
0x18003c29b  jnz     short loc_18003C2DB
0x18003c29d  mov     [rbp+4Fh+arg_10], r12d
0x18003c2a1  mov     r9d, dword ptr [rbp+4Fh+SourceSize]; SourceSize
0x18003c2a5  lea     rdx, [rsi-4]; DestinationSize
0x18003c2a9  lea     rcx, [rbx+4]; Destination
0x18003c2ad  mov     r8, [rbp+4Fh+SourceSize+8]; Source
0x18003c2b1  call    memcpy_s_3
0x18003c2b6  test    eax, eax
0x18003c2b8  jnz     short loc_18003C2CC
0x18003c2ba  mov     eax, r12d
0x18003c2bd  mov     [rbp+4Fh+arg_10], eax
0x18003c2c0  mov     [rbp+4Fh+var_A0], r12
0x18003c2c4  mov     [r14], rbx
0x18003c2c7  mov     [r15], esi
0x18003c2ca  jmp     short loc_18003C309
0x18003c2cc  lea     rax, aHrSafecopymemo_2; "hr = SafeCopyMemory(apLocalResultBuffer"...
0x18003c2d3  mov     r8d, 135h
0x18003c2d9  jmp     short loc_18003C2E8
0x18003c2db  lea     rax, aHrSafecopymemo_8; "hr = SafeCopyMemory(apLocalResultBuffer"...
0x18003c2e2  mov     r8d, 134h; unsigned int
0x18003c2e8  mov     r9d, 8000FFFFh; int
0x18003c2ee  mov     [rsp+0F0h+var_D0], rax; char *
0x18003c2f3  mov     [rbp+4Fh+arg_10], r9d
0x18003c2f7  lea     rdx, aSerializeobjec; "SerializeObjectWithVersion"
0x18003c2fe  mov     rcx, r13; char *
0x18003c301  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18003c306  mov     eax, [rbp+4Fh+arg_10]
0x18003c309  test    eax, eax
0x18003c30b  jns     short loc_18003C31A
0x18003c30d  mov     r8d, 13Dh
0x18003c313  mov     ecx, 2
0x18003c318  jmp     short loc_18003C325
0x18003c31a  mov     r8d, 141h; unsigned int
0x18003c320  mov     ecx, 5; unsigned __int8
0x18003c325  mov     dword ptr [rsp+0F0h+var_D0], eax
0x18003c329  lea     r9, aSerializeobjec_1; "SerializeObjectWithVersion() completed "...
0x18003c330  mov     rdx, r13; char *
0x18003c333  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18003c338  mov     ebx, [rbp+4Fh+arg_10]
0x18003c33b  lea     rcx, [rbp+4Fh+var_50]
0x18003c33f  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18003c344  nop
0x18003c345  lea     rcx, [rbp+4Fh+var_68]
0x18003c349  call    ??1?$Auto@PEAU_TOKEN_USER@@V?$LocalAllocFunctor@PEAU_TOKEN_USER@@@@VDummyContext@@@@QEAA@XZ; Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>(void)
0x18003c34e  nop
0x18003c34f  lea     rcx, [rbp+4Fh+var_A0]
0x18003c353  call    ?Clear@?$CMIDLPtr@PEAG@@QEAAXXZ; CMIDLPtr<ushort *>::Clear(void)
0x18003c358  nop
0x18003c359  lea     rcx, [rbp+4Fh+var_90]
0x18003c35d  call    ?Clear@?$CMIDLPtr@PEAG@@QEAAXXZ; CMIDLPtr<ushort *>::Clear(void)
0x18003c362  mov     eax, ebx
0x18003c364  mov     rbx, [rsp+0F0h+arg_0]
0x18003c36c  add     rsp, 0C0h
0x18003c373  pop     r15
0x18003c375  pop     r14
0x18003c377  pop     r13
0x18003c379  pop     r12
0x18003c37b  pop     rdi
0x18003c37c  pop     rsi
0x18003c37d  pop     rbp
0x18003c37e  retn
```
