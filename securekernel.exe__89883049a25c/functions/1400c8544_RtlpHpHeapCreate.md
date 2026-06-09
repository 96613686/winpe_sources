# RtlpHpHeapCreate

- ea: `0x1400c8544`
- end: `0x1400c8911`
- name: `RtlpHpHeapCreate`
- size: `973`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x140014dd0`
- `0x1400b5cb0`
- `0x1400c9034`

## callees

- `0x1400c8304`
- `0x1400c8544`
- `0x1400c8918`
- `0x1400c9114`
- `0x1400cb6d8`
- `0x1400cb804`
- `0x1400ce494`
- `0x1400ce518`
- `0x1400ce9a8`
- `0x1400d1014`
- `0x1400d2ae8`
- `0x1400d2be8`
- `0x1400ff474`

## pseudocode

```c
__int64 __fastcall RtlpHpHeapCreate(unsigned int a1, __int64 a2, __int64 a3, __int128 *a4)
{
  __int64 v6; // rsi
  unsigned __int32 v7; // r14d
  signed __int32 v8; // eax
  __int64 v9; // rax
  __int128 v10; // xmm0
  int v11; // ecx
  int v12; // edi
  int v13; // r9d
  bool v14; // zf
  char v15; // bl
  char v16; // cl
  char *v17; // rax
  int v18; // r9d
  char *v19; // rdx
  char *v20; // rdx
  __int64 v22; // [rsp+50h] [rbp-41h]
  __int128 v23; // [rsp+58h] [rbp-39h] BYREF
  __int64 v24; // [rsp+68h] [rbp-29h] BYREF
  int v25; // [rsp+70h] [rbp-21h]
  int v26; // [rsp+74h] [rbp-1Dh]
  __int64 (__fastcall *v27)(); // [rsp+78h] [rbp-19h]
  __int64 (__fastcall *v28)(); // [rsp+80h] [rbp-11h]
  __int64 (__fastcall *v29)(); // [rsp+88h] [rbp-9h]
  __int64 (__fastcall *v30)(); // [rsp+90h] [rbp-1h]
  __int128 v31; // [rsp+98h] [rbp+7h]
  __int64 v32; // [rsp+A8h] [rbp+17h]
  ULONG_PTR v33; // [rsp+100h] [rbp+6Fh]
  unsigned __int8 v34; // [rsp+108h] [rbp+77h]

  if ( (int)RtlpHpRegisterEnvironment(a4, 1) < 0 )
    return 0;
  v7 = dword_1401484C8;
  if ( !dword_1401484C8 )
  {
    v7 = SkeNumberProcessors;
    if ( !(_DWORD)SkeNumberProcessors )
      v7 = 1;
    v8 = _InterlockedCompareExchange(&dword_1401484C8, v7, 0);
    if ( v8 )
      v7 = v8;
  }
  if ( (a1 & 0x2000000) != 0 )
    v7 = 1;
  v23 = *a4;
  v9 = RtlpHpHeapAllocate(a1, v7, &v23);
  v6 = v9;
  if ( v9 )
  {
    v10 = *a4;
    v11 = 0;
    *(_DWORD *)(v9 + 16) = -571548178;
    *(_DWORD *)(v9 + 20) = a1;
    *(_OWORD *)v9 = v10;
    *(_QWORD *)(v9 + 272) = 0;
    v34 = *((_BYTE *)a4 + 1);
    v33 = v9;
    if ( (unsigned __int8)(v34 - 2) <= 2u )
      v11 = 16;
    v12 = v11 | 4;
    v23 = v10;
    if ( (a1 & 0x4000000) == 0 )
      v12 = v11;
    RtlpHpSegContextInitialize(
      v9 + 320,
      0x100000,
      v9,
      v9 + 960,
      v9 + 704,
      v9 + 800,
      v9 + 128,
      v9 + 168,
      (__int64)&v23,
      v12);
    LODWORD(v22) = v12;
    v23 = *a4;
    RtlpHpSegContextInitialize(v6 + 512, 0x1000000, v6, 0, 0, 0, v6 + 128, v6 + 184, (__int64)&v23, v22);
    *(_QWORD *)(v6 + 72) = 0;
    *(_QWORD *)(v6 + 80) = 0;
    v14 = (*(_DWORD *)(v6 + 20) & 0x20000000) == 0;
    *(_QWORD *)(v6 + 64) = 0;
    *(_QWORD *)(v6 + 232) = 0;
    if ( !v14 )
    {
      *(_DWORD *)(v6 + 24) = 0;
      _InterlockedAnd((volatile signed __int32 *)(v6 + 20), 0xFFFFFFDF);
    }
    v26 = 0;
    v15 = *(_BYTE *)a4;
    v16 = *(_BYTE *)a4;
    v32 = v6 + 128;
    v25 = v15 & 1;
    v24 = v6 + 320;
    v27 = RtlpHpSegVsAllocate;
    v28 = RtlpHpSegSuballocatorFree;
    v29 = RtlpHpSegSuballocatorCommit;
    v30 = RtlpHpSegSuballocatorDecommit;
    *((_QWORD *)&v31 + 1) = 0;
    *(_QWORD *)&v31 = RtlpHpSegLfhExtendContext;
    v17 = &byte_14014C214;
    if ( (v16 & 6) != 4 )
      v17 = &byte_14015A99C;
    RtlpHpVsContextInitialize(v6 + 704, (unsigned int)&v24, v7, v13, (__int64)v17);
    v27 = RtlpHpSegLfhAllocate;
    v28 = RtlpHpSegSuballocatorFree;
    v29 = RtlpHpSegSuballocatorCommit;
    v30 = RtlpHpSegSuballocatorDecommit;
    *(_QWORD *)&v31 = RtlpHpSegLfhExtendContext;
    *((_QWORD *)&v31 + 1) = RtlpHpSegTlsCleanup;
    RtlpHpLfhContextInitialize(v6 + 960, &v24, v7);
    v18 = *(_DWORD *)(v6 + 336);
    v27 = RtlpHpSegPgAllocate;
    v28 = RtlpHpSegSuballocatorFree;
    v19 = byte_14014C215;
    v29 = RtlpHpSegSuballocatorCommit;
    v30 = RtlpHpSegSuballocatorDecommit;
    v31 = 0;
    if ( (v15 & 6) != 4 )
      v19 = byte_14015A99D;
    v23 = *a4;
    RtlpHpPgContextInitialize(v6 + 800, (unsigned int)&v24, (unsigned int)&v23, v18, v34, (__int64)v19, v6);
    RtlRunOnceInitialize((PRTL_RUN_ONCE)(v6 + 112));
    if ( (int)RtlpHpLfhContextStart(v6 + 960) < 0 || (int)RtlpHpVsContextStart(v6 + 704) < 0 )
      goto LABEL_29;
    if ( (a1 & 0x400000) == 0 )
    {
      v20 = byte_14014C210;
      if ( (v15 & 6) != 4 )
        v20 = byte_14015A998;
      if ( (int)RtlpHpLfhContextEnable(v6 + 960, v20) < 0 )
        goto LABEL_29;
    }
    if ( (int)RtlpHpSegContextReserve(v6 + 320, 0, 0) >= 0 )
    {
      _InterlockedAnd((volatile signed __int32 *)(v6 + 20), 0xFFFFFF7F);
    }
    else
    {
LABEL_29:
      v6 = 0;
      RtlpHpHeapDestroy(v33);
    }
  }
  else
  {
    RtlpHpRegisterEnvironment(a4, 0);
  }
  return v6;
}

```

## disassembly

```asm
0x1400c8544  mov     rax, rsp
0x1400c8547  mov     [rax+8], rbx
0x1400c854b  mov     [rax+18h], r8
0x1400c854f  mov     [rax+10h], rdx
0x1400c8553  push    rbp
0x1400c8554  push    rsi
0x1400c8555  push    rdi
0x1400c8556  push    r12
0x1400c8558  push    r13
0x1400c855a  push    r14
0x1400c855c  push    r15
0x1400c855e  lea     rbp, [rax-5Fh]
0x1400c8562  sub     rsp, 0B0h
0x1400c8569  mov     r12d, ecx
0x1400c856c  mov     ebx, 1
0x1400c8571  mov     edx, ebx
0x1400c8573  mov     rcx, r9
0x1400c8576  mov     r15, r9
0x1400c8579  call    RtlpHpRegisterEnvironment
0x1400c857e  test    eax, eax
0x1400c8580  jns     short loc_1400C8589
0x1400c8582  xor     esi, esi
0x1400c8584  jmp     loc_1400C88F2
0x1400c8589  mov     r14d, cs:dword_1401484C8
0x1400c8590  test    r14d, r14d
0x1400c8593  jnz     short loc_1400C85B2
0x1400c8595  mov     r14d, cs:SkeNumberProcessors
0x1400c859c  test    r14d, r14d
0x1400c859f  cmovz   r14d, ebx
0x1400c85a3  xor     eax, eax
0x1400c85a5  lock cmpxchg cs:dword_1401484C8, r14d
0x1400c85ae  cmovnz  r14d, eax
0x1400c85b2  movups  xmm0, xmmword ptr [r15]
0x1400c85b6  bt      r12d, 19h
0x1400c85bb  lea     r8, [rbp+57h+var_90]
0x1400c85bf  mov     ecx, r12d
0x1400c85c2  cmovb   r14d, ebx
0x1400c85c6  mov     edx, r14d
0x1400c85c9  movdqu  [rbp+57h+var_90], xmm0
0x1400c85ce  call    RtlpHpHeapAllocate
0x1400c85d3  mov     rsi, rax
0x1400c85d6  test    rax, rax
0x1400c85d9  jnz     short loc_1400C85EA
0x1400c85db  xor     edx, edx
0x1400c85dd  mov     rcx, r15
0x1400c85e0  call    RtlpHpRegisterEnvironment
0x1400c85e5  jmp     loc_1400C88F2
0x1400c85ea  movups  xmm0, xmmword ptr [r15]
0x1400c85ee  xor     ecx, ecx
0x1400c85f0  mov     dword ptr [rax+10h], 0DDEEDDEEh
0x1400c85f7  mov     [rax+14h], r12d
0x1400c85fb  lea     r9, [rbp+57h+var_90]
0x1400c85ff  movdqu  xmmword ptr [rax], xmm0
0x1400c8603  mov     qword ptr [rax+110h], 0
0x1400c860e  lea     r8, [rsi+320h]
0x1400c8615  mov     al, [r15+1]
0x1400c8619  lea     edx, [rcx+10h]
0x1400c861c  mov     [rbp+57h+arg_10], al
0x1400c861f  lea     rbx, [rsi+0A8h]
0x1400c8626  sub     al, 2
0x1400c8628  mov     [rbp+57h+arg_8], rsi
0x1400c862c  cmp     al, 2
0x1400c862e  lea     r13, [rsi+140h]
0x1400c8635  lea     rax, [rsi+2C0h]
0x1400c863c  cmovbe  ecx, edx
0x1400c863f  lea     rdx, [rsi+80h]
0x1400c8646  mov     edi, ecx
0x1400c8648  or      edi, 4
0x1400c864b  bt      r12d, 1Ah
0x1400c8650  movdqu  [rbp+57h+var_90], xmm0
0x1400c8655  cmovnb  edi, ecx
0x1400c8658  mov     rcx, r13
0x1400c865b  mov     [rsp+48h], edi
0x1400c865f  mov     qword ptr [rsp+0E0h+var_A0], r9
0x1400c8664  lea     r9, [rsi+3C0h]
0x1400c866b  mov     [rsp+0E0h+var_A8], rbx
0x1400c8670  mov     [rsp+0E0h+var_B0], rdx
0x1400c8675  mov     edx, 100000h
0x1400c867a  mov     [rsp+0E0h+var_B8], r8
0x1400c867f  mov     r8, rsi
0x1400c8682  mov     [rsp+0E0h+var_C0], rax
0x1400c8687  call    RtlpHpSegContextInitialize
0x1400c868c  movups  xmm0, xmmword ptr [r15]
0x1400c8690  mov     [rsp+48h], edi
0x1400c8694  lea     rdx, [rbp+57h+var_90]
0x1400c8698  mov     qword ptr [rsp+0E0h+var_A0], rdx
0x1400c869d  lea     rax, [rbx+10h]
0x1400c86a1  mov     [rsp+0E0h+var_A8], rax
0x1400c86a6  lea     rdi, [rsi+80h]
0x1400c86ad  xor     ebx, ebx
0x1400c86af  mov     [rsp+0E0h+var_B0], rdi
0x1400c86b4  mov     [rsp+0E0h+var_B8], rbx
0x1400c86b9  lea     rcx, [r13+0C0h]
0x1400c86c0  xor     r9d, r9d
0x1400c86c3  mov     [rsp+0E0h+var_C0], rbx
0x1400c86c8  mov     r8, rsi
0x1400c86cb  mov     edx, 1000000h
0x1400c86d0  movdqu  [rbp+57h+var_90], xmm0
0x1400c86d5  call    RtlpHpSegContextInitialize
0x1400c86da  mov     [rsi+48h], rbx
0x1400c86de  mov     [rsi+50h], rbx
0x1400c86e2  test    dword ptr [rsi+14h], 20000000h
0x1400c86e9  mov     [rsi+40h], rbx
0x1400c86ed  mov     [rsi+0E8h], rbx
0x1400c86f4  jz      short loc_1400C86FE
0x1400c86f6  mov     [rsi+18h], ebx
0x1400c86f9  lock and dword ptr [rsi+14h], 0FFFFFFDFh
0x1400c86fe  xorps   xmm0, xmm0
0x1400c8701  mov     [rbp+57h+var_74], ebx
0x1400c8704  movzx   ebx, byte ptr [r15]
0x1400c8708  lea     rdx, byte_14015A99C
0x1400c870f  movups  [rbp+57h+var_70], xmm0
0x1400c8713  mov     eax, ebx
0x1400c8715  mov     cl, bl
0x1400c8717  and     eax, 1
0x1400c871a  mov     [rbp+57h+var_40], rdi
0x1400c871e  mov     [rbp+57h+var_78], eax
0x1400c8721  lea     rdi, [rsi+2C0h]
0x1400c8728  movups  [rbp+57h+var_60], xmm0
0x1400c872c  and     cl, 6
0x1400c872f  mov     [rbp+57h+var_80], r13
0x1400c8733  cmp     cl, 4
0x1400c8736  lea     rax, RtlpHpSegVsAllocate
0x1400c873d  mov     qword ptr [rbp+57h+var_70], rax
0x1400c8741  mov     r8d, r14d
0x1400c8744  lea     rax, RtlpHpSegSuballocatorFree
0x1400c874b  mov     rcx, rdi
0x1400c874e  mov     qword ptr [rbp+57h+var_70+8], rax
0x1400c8752  lea     rax, RtlpHpSegSuballocatorCommit
0x1400c8759  mov     qword ptr [rbp+57h+var_60], rax
0x1400c875d  lea     rax, RtlpHpSegSuballocatorDecommit
0x1400c8764  mov     qword ptr [rbp+57h+var_60+8], rax
0x1400c8768  lea     rax, RtlpHpSegLfhExtendContext
0x1400c876f  movups  [rbp+57h+var_50], xmm0
0x1400c8773  mov     qword ptr [rbp+57h+var_50], rax
0x1400c8777  lea     rax, byte_14014C214
0x1400c877e  cmovnz  rax, rdx
0x1400c8782  lea     rdx, [rbp+57h+var_80]
0x1400c8786  mov     [rsp+0E0h+var_C0], rax
0x1400c878b  call    RtlpHpVsContextInitialize
0x1400c8790  xorps   xmm0, xmm0
0x1400c8793  lea     rax, RtlpHpSegLfhAllocate
0x1400c879a  movups  [rbp+57h+var_70], xmm0
0x1400c879e  mov     qword ptr [rbp+57h+var_70], rax
0x1400c87a2  lea     rdx, [rbp+57h+var_80]
0x1400c87a6  movups  [rbp+57h+var_60], xmm0
0x1400c87aa  lea     rax, RtlpHpSegSuballocatorFree
0x1400c87b1  mov     r8d, r14d
0x1400c87b4  mov     qword ptr [rbp+57h+var_70+8], rax
0x1400c87b8  lea     r14, [rsi+3C0h]
0x1400c87bf  movups  [rbp+57h+var_50], xmm0
0x1400c87c3  lea     rax, RtlpHpSegSuballocatorCommit
0x1400c87ca  mov     rcx, r14
0x1400c87cd  mov     qword ptr [rbp+57h+var_60], rax
0x1400c87d1  lea     rax, RtlpHpSegSuballocatorDecommit
0x1400c87d8  mov     qword ptr [rbp+57h+var_60+8], rax
0x1400c87dc  lea     rax, RtlpHpSegLfhExtendContext
0x1400c87e3  mov     qword ptr [rbp+57h+var_50], rax
0x1400c87e7  lea     rax, RtlpHpSegTlsCleanup
0x1400c87ee  mov     qword ptr [rbp+57h+var_50+8], rax
0x1400c87f2  call    RtlpHpLfhContextInitialize
0x1400c87f7  mov     r9d, [rsi+150h]
0x1400c87fe  lea     rax, RtlpHpSegPgAllocate
0x1400c8805  xorps   xmm0, xmm0
0x1400c8808  mov     [rsp+0E0h+var_B0], rsi
0x1400c880d  movups  [rbp+57h+var_70], xmm0
0x1400c8811  mov     qword ptr [rbp+57h+var_70], rax
0x1400c8815  lea     rcx, byte_14015A99D
0x1400c881c  movups  [rbp+57h+var_60], xmm0
0x1400c8820  lea     rax, RtlpHpSegSuballocatorFree
0x1400c8827  mov     qword ptr [rbp+57h+var_70+8], rax
0x1400c882b  lea     rdx, byte_14014C215
0x1400c8832  lea     rax, RtlpHpSegSuballocatorCommit
0x1400c8839  mov     qword ptr [rbp+57h+var_60], rax
0x1400c883d  lea     r8, [rbp+57h+var_90]
0x1400c8841  lea     rax, RtlpHpSegSuballocatorDecommit
0x1400c8848  mov     qword ptr [rbp+57h+var_60+8], rax
0x1400c884c  mov     al, bl
0x1400c884e  and     al, 6
0x1400c8850  cmp     al, 4
0x1400c8852  movzx   eax, [rbp+57h+arg_10]
0x1400c8856  movups  [rbp+57h+var_50], xmm0
0x1400c885a  cmovnz  rdx, rcx
0x1400c885e  movups  xmm0, xmmword ptr [r15]
0x1400c8862  mov     [rsp+0E0h+var_B8], rdx
0x1400c8867  lea     rdx, [rbp+57h+var_80]
0x1400c886b  mov     dword ptr [rsp+0E0h+var_C0], eax
0x1400c886f  movdqu  [rbp+57h+var_90], xmm0
0x1400c8874  lea     rcx, [rsi+320h]
0x1400c887b  call    RtlpHpPgContextInitialize
0x1400c8880  lea     rcx, [rsi+70h]; RunOnce
0x1400c8884  call    RtlRunOnceInitialize
0x1400c8889  mov     rcx, r14
0x1400c888c  call    RtlpHpLfhContextStart
0x1400c8891  test    eax, eax
0x1400c8893  js      short loc_1400C88DD
0x1400c8895  mov     rcx, rdi
0x1400c8898  call    RtlpHpVsContextStart
0x1400c889d  test    eax, eax
0x1400c889f  js      short loc_1400C88DD
0x1400c88a1  bt      r12d, 16h
0x1400c88a6  jb      short loc_1400C88CC
0x1400c88a8  lea     rax, byte_14015A998
0x1400c88af  and     bl, 6
0x1400c88b2  cmp     bl, 4
0x1400c88b5  lea     rdx, byte_14014C210
0x1400c88bc  mov     rcx, r14
0x1400c88bf  cmovnz  rdx, rax
0x1400c88c3  call    RtlpHpLfhContextEnable
0x1400c88c8  test    eax, eax
0x1400c88ca  js      short loc_1400C88DD
0x1400c88cc  xor     r8d, r8d
0x1400c88cf  xor     edx, edx
0x1400c88d1  mov     rcx, r13
0x1400c88d4  call    RtlpHpSegContextReserve
0x1400c88d9  test    eax, eax
0x1400c88db  jns     short loc_1400C88EA
0x1400c88dd  mov     rcx, [rbp+57h+arg_8]
0x1400c88e1  xor     esi, esi
0x1400c88e3  call    RtlpHpHeapDestroy
0x1400c88e8  jmp     short loc_1400C88F2
0x1400c88ea  lock and dword ptr [rsi+14h], 0FFFFFF7Fh
0x1400c88f2  mov     rbx, [rsp+0E0h+arg_0]
0x1400c88fa  mov     rax, rsi
0x1400c88fd  add     rsp, 0B0h
0x1400c8904  pop     r15
0x1400c8906  pop     r14
0x1400c8908  pop     r13
0x1400c890a  pop     r12
0x1400c890c  pop     rdi
0x1400c890d  pop     rsi
0x1400c890e  pop     rbp
0x1400c890f  retn
```
