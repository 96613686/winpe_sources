# SerializeObjectWithVersion<ModernAppTokenBagSerializer,_ModernAppTokenBag>(ModernAppTokenBagSerializer &,_ModernAppTokenBag &,ulong,uchar * *,ulong *)

- ea: `0x180017064`
- end: `0x180017307`
- name: `??$SerializeObjectWithVersion@VModernAppTokenBagSerializer@@U_ModernAppTokenBag@@@@YAJAEAVModernAppTokenBagSerializer@@AEAU_ModernAppTokenBag@@KPEAPEAEPEAK@Z`
- size: `675`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18003ea04`

## callees

- `0x180004b2c`
- `0x1800061a8`
- `0x1800090c0`
- `0x180009630`
- `0x18000a400`
- `0x18001173c`
- `0x180013434`
- `0x180017064`
- `0x1800392b0`
- `0x18003b90c`
- `0x180058010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800171e4`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800171e4`

## string_xrefs

- `0x180017254`: `hr = SafeCopyMemory(apLocalResultBuffer + sizeof(version), bufferSize - sizeof(version), pEncryptedOut.pbData, pEncryptedOut.cbData)`
- `0x180017263`: `hr = SafeCopyMemory(apLocalResultBuffer, bufferSize, &version, sizeof(version))`
- `0x1800172b1`: `SerializeObjectWithVersion() completed with hr = 0x%x.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SerializeObjectWithVersion<ModernAppTokenBagSerializer,_ModernAppTokenBag>(
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
  v9 = SerializeObject<ModernAppTokenBagSerializer,_ModernAppTokenBag>(a1, a2, &v26, &v32);
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
0x180017064  mov     [rsp-8+arg_0], rbx
0x180017069  mov     [rsp-8+arg_10], r8d
0x18001706e  push    rbp
0x18001706f  push    rsi
0x180017070  push    rdi
0x180017071  push    r12
0x180017073  push    r13
0x180017075  push    r14
0x180017077  push    r15
0x180017079  lea     rbp, [rsp-1Fh]
0x18001707e  sub     rsp, 0C0h
0x180017085  mov     r14, r9
0x180017088  mov     rbx, rdx
0x18001708b  mov     rdi, rcx
0x18001708e  mov     esi, 1
0x180017093  mov     [rbp+4Fh+Source], esi
0x180017096  xor     r12d, r12d
0x180017099  mov     [rbp+4Fh+arg_10], r12d
0x18001709d  mov     [rbp+4Fh+var_90], r12
0x1800170a1  mov     [rbp+4Fh+var_A0], r12
0x1800170a5  mov     [rbp+4Fh+arg_18], r12d
0x1800170a9  xorps   xmm0, xmm0
0x1800170ac  movups  [rbp+4Fh+var_78], xmm0
0x1800170b0  xorps   xmm1, xmm1
0x1800170b3  movups  xmmword ptr [rbp+4Fh+SourceSize], xmm1
0x1800170b7  mov     [rbp+4Fh+var_68], r12
0x1800170bb  mov     [rbp+4Fh+var_58], r12
0x1800170bf  mov     [rbp+4Fh+var_60], r12
0x1800170c3  lea     rcx, aSerializeobjec; "SerializeObjectWithVersion"
0x1800170ca  mov     [rbp+4Fh+var_50], rcx
0x1800170ce  lea     rax, [rbp+4Fh+arg_10]
0x1800170d2  mov     [rbp+4Fh+var_48], rax
0x1800170d6  mov     [rbp+4Fh+var_40], r12
0x1800170da  mov     [rbp+4Fh+var_38], r12
0x1800170de  xor     r9d, r9d; unsigned int
0x1800170e1  mov     r8d, 109h; char *
0x1800170e7  mov     rdx, rcx; char *
0x1800170ea  lea     r13, aOnecoreuapDsEx_7; "onecoreuap\\ds\\ext\\Live\\identity\\In"...
0x1800170f1  mov     rcx, r13; this
0x1800170f4  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x1800170f9  nop
0x1800170fa  mov     [r14], r12
0x1800170fd  mov     r15, [rbp+4Fh+arg_20]
0x180017101  mov     [r15], r12d
0x180017104  lea     r9, [rbp+4Fh+arg_18]
0x180017108  lea     r8, [rbp+4Fh+var_90]
0x18001710c  mov     rdx, rbx
0x18001710f  mov     rcx, rdi
0x180017112  call    ??$SerializeObject@VModernAppTokenBagSerializer@@U_ModernAppTokenBag@@@@YAJAEAVModernAppTokenBagSerializer@@AEAU_ModernAppTokenBag@@PEAPEAEPEAK@Z; SerializeObject<ModernAppTokenBagSerializer,_ModernAppTokenBag>(ModernAppTokenBagSerializer &,_ModernAppTokenBag &,uchar * *,ulong *)
0x180017117  mov     [rbp+4Fh+arg_10], eax
0x18001711a  test    eax, eax
0x18001711c  js      loc_180017295
0x180017122  mov     eax, [rbp+4Fh+arg_18]
0x180017125  mov     dword ptr [rbp+4Fh+var_78], eax
0x180017128  mov     rax, [rbp+4Fh+var_90]
0x18001712c  mov     qword ptr [rbp+4Fh+var_78+8], rax
0x180017130  mov     rcx, [rdi]
0x180017133  mov     rax, [rcx]
0x180017136  mov     rax, [rax+18h]
0x18001713a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001713f  mov     r10, rax
0x180017142  mov     rcx, [rax]
0x180017145  mov     rax, [rcx+8]
0x180017149  lea     rcx, [rbp+4Fh+SourceSize]
0x18001714d  mov     [rsp+0F0h+var_B8], rcx
0x180017152  mov     [rsp+0F0h+var_C0], esi
0x180017156  mov     [rsp+0F0h+var_C8], r12
0x18001715b  mov     [rsp+0F0h+var_D0], r12
0x180017160  xor     r9d, r9d
0x180017163  xor     r8d, r8d
0x180017166  lea     rdx, [rbp+4Fh+var_78]
0x18001716a  mov     rcx, r10
0x18001716d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017172  test    eax, eax
0x180017174  jnz     short loc_1800171C9
0x180017176  mov     rcx, [rdi]
0x180017179  mov     rax, [rcx]
0x18001717c  mov     rax, [rax+18h]
0x180017180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017185  mov     rdx, rax
0x180017188  mov     rcx, [rax]
0x18001718b  mov     rax, [rcx+78h]
0x18001718f  mov     rcx, rdx
0x180017192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017197  test    eax, eax
0x180017199  jle     short loc_1800171A3
0x18001719b  movzx   eax, ax
0x18001719e  or      eax, 80070000h
0x1800171a3  mov     [rbp+4Fh+arg_10], eax
0x1800171a6  mov     dword ptr [rsp+0F0h+var_D0], eax
0x1800171aa  lea     r9, aCryptprotectda_0; "CryptProtectData failed. error=0x%x."
0x1800171b1  mov     r8d, 126h; unsigned int
0x1800171b7  mov     rdx, r13; char *
0x1800171ba  mov     ecx, 2; unsigned __int8
0x1800171bf  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800171c4  jmp     loc_18001728E
0x1800171c9  mov     rbx, [rbp+4Fh+SourceSize+8]
0x1800171cd  lea     rcx, [rbp+4Fh+var_68]
0x1800171d1  call    ?Clear@?$Auto@PEAEV?$LocalAllocFunctor@PEAE@@VDummyContext@@@@QEAAXXZ; Auto<uchar *,LocalAllocFunctor<uchar *>,DummyContext>::Clear(void)
0x1800171d6  mov     [rbp+4Fh+var_68], rbx
0x1800171da  mov     esi, dword ptr [rbp+4Fh+SourceSize]
0x1800171dd  add     esi, 4
0x1800171e0  mov     edi, esi
0x1800171e2  mov     ecx, esi; Size
0x1800171e4  call    cs:__imp_malloc
0x1800171ea  mov     rbx, rax
0x1800171ed  lea     rcx, [rbp+4Fh+var_A0]
0x1800171f1  call    ?Clear@?$CMIDLPtr@PEAG@@QEAAXXZ; CMIDLPtr<ushort *>::Clear(void)
0x1800171f6  mov     [rbp+4Fh+var_A0], rbx
0x1800171fa  test    rbx, rbx
0x1800171fd  jnz     short loc_18001720C
0x1800171ff  mov     eax, 8007000Eh
0x180017204  mov     [rbp+4Fh+arg_10], eax
0x180017207  jmp     loc_180017295
0x18001720c  mov     r9d, 4; SourceSize
0x180017212  lea     r8, [rbp+4Fh+Source]; Source
0x180017216  mov     rdx, rdi; DestinationSize
0x180017219  mov     rcx, rbx; Destination
0x18001721c  call    memcpy_s_3
0x180017221  test    eax, eax
0x180017223  jnz     short loc_180017263
0x180017225  mov     [rbp+4Fh+arg_10], r12d
0x180017229  mov     r9d, dword ptr [rbp+4Fh+SourceSize]; SourceSize
0x18001722d  lea     rdx, [rsi-4]; DestinationSize
0x180017231  lea     rcx, [rbx+4]; Destination
0x180017235  mov     r8, [rbp+4Fh+SourceSize+8]; Source
0x180017239  call    memcpy_s_3
0x18001723e  test    eax, eax
0x180017240  jnz     short loc_180017254
0x180017242  mov     eax, r12d
0x180017245  mov     [rbp+4Fh+arg_10], eax
0x180017248  mov     [rbp+4Fh+var_A0], r12
0x18001724c  mov     [r14], rbx
0x18001724f  mov     [r15], esi
0x180017252  jmp     short loc_180017291
0x180017254  lea     rax, aHrSafecopymemo_2; "hr = SafeCopyMemory(apLocalResultBuffer"...
0x18001725b  mov     r8d, 135h
0x180017261  jmp     short loc_180017270
0x180017263  lea     rax, aHrSafecopymemo_8; "hr = SafeCopyMemory(apLocalResultBuffer"...
0x18001726a  mov     r8d, 134h; unsigned int
0x180017270  mov     r9d, 8000FFFFh; int
0x180017276  mov     [rsp+0F0h+var_D0], rax; char *
0x18001727b  mov     [rbp+4Fh+arg_10], r9d
0x18001727f  lea     rdx, aSerializeobjec; "SerializeObjectWithVersion"
0x180017286  mov     rcx, r13; char *
0x180017289  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18001728e  mov     eax, [rbp+4Fh+arg_10]
0x180017291  test    eax, eax
0x180017293  jns     short loc_1800172A2
0x180017295  mov     r8d, 13Dh
0x18001729b  mov     ecx, 2
0x1800172a0  jmp     short loc_1800172AD
0x1800172a2  mov     r8d, 141h; unsigned int
0x1800172a8  mov     ecx, 5; unsigned __int8
0x1800172ad  mov     dword ptr [rsp+0F0h+var_D0], eax
0x1800172b1  lea     r9, aSerializeobjec_1; "SerializeObjectWithVersion() completed "...
0x1800172b8  mov     rdx, r13; char *
0x1800172bb  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800172c0  mov     ebx, [rbp+4Fh+arg_10]
0x1800172c3  lea     rcx, [rbp+4Fh+var_50]
0x1800172c7  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800172cc  nop
0x1800172cd  lea     rcx, [rbp+4Fh+var_68]
0x1800172d1  call    ??1?$Auto@PEAU_TOKEN_USER@@V?$LocalAllocFunctor@PEAU_TOKEN_USER@@@@VDummyContext@@@@QEAA@XZ; Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>(void)
0x1800172d6  nop
0x1800172d7  lea     rcx, [rbp+4Fh+var_A0]
0x1800172db  call    ?Clear@?$CMIDLPtr@PEAG@@QEAAXXZ; CMIDLPtr<ushort *>::Clear(void)
0x1800172e0  nop
0x1800172e1  lea     rcx, [rbp+4Fh+var_90]
0x1800172e5  call    ?Clear@?$CMIDLPtr@PEAG@@QEAAXXZ; CMIDLPtr<ushort *>::Clear(void)
0x1800172ea  mov     eax, ebx
0x1800172ec  mov     rbx, [rsp+0F0h+arg_0]
0x1800172f4  add     rsp, 0C0h
0x1800172fb  pop     r15
0x1800172fd  pop     r14
0x1800172ff  pop     r13
0x180017301  pop     r12
0x180017303  pop     rdi
0x180017304  pop     rsi
0x180017305  pop     rbp
0x180017306  retn
```
