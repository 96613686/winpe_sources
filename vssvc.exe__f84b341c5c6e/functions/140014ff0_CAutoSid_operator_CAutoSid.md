# CAutoSid::operator==(CAutoSid &)

- ea: `0x140014ff0`
- end: `0x140015476`
- name: `??8CAutoSid@@QEAA_NAEAV0@@Z`
- size: `1158`
- prototype: `_BOOL8 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140011ae0`

## callees

- `0x140011a90`
- `0x1400137c0`
- `0x1400138e0`
- `0x140013c60`
- `0x140014ff0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x140015161`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x140015161`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14001509d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400151dc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140015308`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14001509d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400151dc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140015308`
- `VssTrace!__imp_VssTraceMessage` at `0x14001546b`
- `VssTrace!__imp_VssTraceMessage` at `0x14001546b`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x1400153c3`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x1400153ee`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x1400153c3`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x1400153ee`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x1400150dc`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x1400150dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400151a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400151b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400151c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400151d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140015280`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400152d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400152e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400152f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400152fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400151a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400151b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400151c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400151d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140015280`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400152d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400152e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400152f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400152fe`

## string_xrefs

- `0x140015018`: `base\stor\vss\modules\sec\security.cxx`
- `0x140015042`: `CAutoSid::operator ==`

## pseudocode

```c
_BOOL8 __fastcall CAutoSid::operator==(__int64 a1, __int64 a2)
{
  __int64 v4; // rax
  unsigned int v5; // r14d
  unsigned int v6; // ebx
  __int64 i; // rbx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rdx
  BOOL v11; // eax
  const wchar_t *v12; // rcx
  bool v13; // si
  DWORD v14; // eax
  const wchar_t *v15; // rcx
  DWORD v16; // edi
  bool v18; // bl
  __int64 v19; // [rsp+20h] [rbp-E0h]
  __int64 v20; // [rsp+28h] [rbp-D8h]
  __int64 v21; // [rsp+30h] [rbp-D0h]
  __int64 v22; // [rsp+38h] [rbp-C8h]
  __int64 v23; // [rsp+40h] [rbp-C0h]
  int v24; // [rsp+48h] [rbp-B8h]
  unsigned __int64 v25; // [rsp+50h] [rbp-B0h] BYREF
  int v26; // [rsp+58h] [rbp-A8h]
  const unsigned __int16 *v27; // [rsp+60h] [rbp-A0h]
  const unsigned __int16 *v28; // [rsp+68h] [rbp-98h]
  unsigned int v29; // [rsp+70h] [rbp-90h]
  unsigned int v30; // [rsp+74h] [rbp-8Ch]
  const wchar_t *v31; // [rsp+78h] [rbp-88h]
  unsigned int v32; // [rsp+80h] [rbp-80h]
  DWORD TickCount; // [rsp+84h] [rbp-7Ch]
  unsigned int v34; // [rsp+88h] [rbp-78h]
  LPVOID pv[2]; // [rsp+90h] [rbp-70h]
  LPVOID v36[2]; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  const unsigned __int16 *v38; // [rsp+C0h] [rbp-40h]
  const wchar_t *v39; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v40; // [rsp+D0h] [rbp-30h]
  int v41; // [rsp+D8h] [rbp-28h]
  int v42; // [rsp+DCh] [rbp-24h]
  int v43; // [rsp+E0h] [rbp-20h]
  LPVOID v44[2]; // [rsp+E8h] [rbp-18h]
  __int128 v45; // [rsp+F8h] [rbp-8h]
  __int128 v46; // [rsp+108h] [rbp+8h]
  __int128 v47; // [rsp+118h] [rbp+18h]
  __int128 v48; // [rsp+128h] [rbp+28h]
  __int128 v49; // [rsp+138h] [rbp+38h]
  __int128 v50; // [rsp+148h] [rbp+48h]
  __int64 v51; // [rsp+158h] [rbp+58h]
  int v52; // [rsp+160h] [rbp+60h]
  __int64 v53; // [rsp+1A0h] [rbp+A0h] BYREF

  v41 = 932;
  v42 = 11;
  v38 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
  v43 = 255;
  v40 = L"SECSECRC";
  v28 = L"SECSECRC";
  v39 = L"CAutoSid::operator ==";
  v31 = L"CAutoSid::operator ==";
  v52 = 0x1000000;
  *(_OWORD *)v44 = 0;
  v51 = 0;
  v45 = 0;
  v26 = 0;
  v46 = 0;
  v27 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
  v47 = 0;
  v29 = 932;
  v48 = 0;
  v30 = 11;
  v49 = 0;
  v50 = 0;
  *(_OWORD *)pv = 0;
  *(_OWORD *)v36 = 0;
  TickCount = GetTickCount();
  v34 = 255;
  v25 = 0xFFFFFFFF00000000uLL;
  v37 = 0;
  v53 = 0;
  if ( (int)VssGetTracingContextPerThread(&v53) < 0 || (int)VssSetTracingContextPerThread(&v25) < 0 )
  {
    v4 = v37;
  }
  else
  {
    v4 = v53;
    v37 = v53;
  }
  if ( v4 )
    v32 = *(_DWORD *)(v4 + 48) + 1;
  else
    v32 = 0;
  v5 = 160;
  v6 = 160;
  if ( v34 != 255 )
    v6 = v34;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v25, v30) )
    VssTraceMessage(v27, v28, v29, v32, v30, v31, L"ENTER", v6, 0);
  for ( i = 0; i != 15; ++i )
  {
    v8 = v44[i];
    if ( v8 )
    {
      CoTaskMemFree(v8);
      v44[i] = 0;
    }
  }
  v9 = *(void **)(a1 + 8);
  if ( !v9 )
  {
    v15 = L"TRUE";
    v13 = *(_QWORD *)(a2 + 8) == 0;
    if ( !v13 )
      v15 = L"FALSE";
    CVssFunctionTracer::TraceInternalWithFormat(
      (CVssFunctionTracer *)&v25,
      L"RETURN",
      0xAAu,
      L"Returning BOOL: %s",
      v15);
    CoTaskMemFree(pv[0]);
    pv[0] = 0;
    CoTaskMemFree(pv[1]);
    pv[1] = 0;
    CoTaskMemFree(v36[0]);
    v36[0] = 0;
    CoTaskMemFree(v36[1]);
    v36[1] = 0;
    v16 = GetTickCount() - TickCount;
    v24 = v26;
    LODWORD(v23) = v16;
    if ( v34 != 255 )
      v5 = v34;
    LODWORD(v22) = v16 % 0x3E8;
    LODWORD(v21) = v16 / 0x3E8 % 0x3C;
    LODWORD(v20) = v16 / 0xEA60 % 0x3C;
    LODWORD(v19) = v16 / 0x36EE80 % 0x3C;
    goto LABEL_25;
  }
  v10 = *(void **)(a2 + 8);
  if ( v10 )
  {
    v11 = EqualSid(v9, v10);
    v12 = L"TRUE";
    v13 = v11;
    if ( !v11 )
      v12 = L"FALSE";
    CVssFunctionTracer::TraceInternalWithFormat(
      (CVssFunctionTracer *)&v25,
      L"RETURN",
      0xAAu,
      L"Returning BOOL: %s",
      v12);
    CoTaskMemFree(pv[0]);
    pv[0] = 0;
    CoTaskMemFree(pv[1]);
    pv[1] = 0;
    CoTaskMemFree(v36[0]);
    v36[0] = 0;
    CoTaskMemFree(v36[1]);
    v36[1] = 0;
    v14 = GetTickCount();
    v24 = v26;
    LODWORD(v23) = v14 - TickCount;
    if ( v34 != 255 )
      v5 = v34;
    LODWORD(v22) = (v14 - TickCount) % 0x3E8;
    LODWORD(v21) = (v14 - TickCount) / 0x3E8 % 0x3C;
    LODWORD(v20) = (v14 - TickCount) / 0xEA60 % 0x3C;
    LODWORD(v19) = (v14 - TickCount) / 0x36EE80 % 0x3C;
LABEL_25:
    CVssFunctionTracer::TraceInternalWithFormat(
      (CVssFunctionTracer *)&v25,
      L"EXIT",
      v5,
      L"Time spent: %02ld:%02ld:%02ld-%04ld; total: %#x; HRESULT: %#x",
      v19,
      v20,
      v21,
      v22,
      v23,
      v24);
    VssSetTracingContextPerThread(v37);
    return v13;
  }
  v18 = CVssFunctionTracer::Exit((CVssFunctionTracer *)&v25, 0);
  CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v25);
  return v18;
}

```

## disassembly

```asm
0x140014ff0  mov     [rsp-8+arg_8], rbx
0x140014ff5  mov     [rsp-8+arg_10], rsi
0x140014ffa  push    rbp
0x140014ffb  push    rdi
0x140014ffc  push    r12
0x140014ffe  push    r14
0x140015000  push    r15
0x140015002  lea     rbp, [rsp-70h]
0x140015007  sub     rsp, 170h
0x14001500e  xorps   xmm0, xmm0
0x140015011  mov     [rbp+90h+var_B8], 3A4h
0x140015018  lea     r8, aBaseStorVssMod_24; "base\\stor\\vss\\modules\\sec\\security"...
0x14001501f  mov     [rbp+90h+var_B4], 0Bh
0x140015026  mov     rsi, rdx
0x140015029  mov     [rbp+90h+var_D0], r8
0x14001502d  lea     rdx, aSecsecrc; "SECSECRC"
0x140015034  mov     [rbp+90h+var_B0], 0FFh
0x14001503b  mov     rdi, rcx
0x14001503e  mov     [rbp+90h+var_C0], rdx
0x140015042  lea     rcx, aCautosidOperat; "CAutoSid::operator =="
0x140015049  mov     [rsp+190h+var_128], rdx
0x14001504e  xor     eax, eax
0x140015050  mov     [rbp+90h+var_C8], rcx
0x140015054  xor     r15d, r15d
0x140015057  mov     [rsp+190h+var_118], rcx
0x14001505c  mov     [rbp+90h+var_30], 1000000h
0x140015063  movups  xmmword ptr [rbp+90h+var_A8], xmm0
0x140015067  mov     [rbp+90h+var_38], rax
0x14001506b  movups  [rbp+90h+var_98], xmm0
0x14001506f  mov     [rsp+190h+var_138], r15d
0x140015074  movups  [rbp+90h+var_88], xmm0
0x140015078  mov     [rsp+190h+var_130], r8
0x14001507d  movups  [rbp+90h+var_78], xmm0
0x140015081  mov     [rsp+190h+var_120], 3A4h
0x140015089  movups  [rbp+90h+var_68], xmm0
0x14001508d  mov     [rsp+190h+var_11C], 0Bh
0x140015095  movups  [rbp+90h+var_58], xmm0
0x140015099  movups  [rbp+90h+var_48], xmm0
0x14001509d  call    cs:__imp_GetTickCount
0x1400150a3  xorps   xmm0, xmm0
0x1400150a6  mov     [rsp+190h+var_13C], 0FFFFFFFFh
0x1400150ae  xorps   xmm1, xmm1
0x1400150b1  movdqa  xmmword ptr [rbp+90h+pv], xmm0
0x1400150b6  lea     rcx, [rbp+90h+arg_0]
0x1400150bd  movdqa  xmmword ptr [rbp+90h+var_F0], xmm1
0x1400150c2  mov     [rbp+90h+var_10C], eax
0x1400150c5  mov     [rbp+90h+var_108], 0FFh
0x1400150cc  mov     [rsp+190h+var_140], r15d
0x1400150d1  mov     [rbp+90h+var_E0], r15
0x1400150d5  mov     [rbp+90h+arg_0], r15
0x1400150dc  call    cs:__imp_VssGetTracingContextPerThread
0x1400150e2  test    eax, eax
0x1400150e4  jns     loc_1400153E9
0x1400150ea  mov     rax, [rbp+90h+var_E0]
0x1400150ee  test    rax, rax
0x1400150f1  jz      loc_140015428
0x1400150f7  mov     eax, [rax+30h]
0x1400150fa  inc     eax
0x1400150fc  mov     [rbp+90h+var_110], eax
0x1400150ff  cmp     [rbp+90h+var_108], 0FFh
0x140015106  lea     rcx, [rsp+190h+var_140]; this
0x14001510b  mov     edx, [rsp+190h+var_11C]; unsigned int
0x14001510f  mov     r14d, 0A0h
0x140015115  mov     ebx, r14d
0x140015118  cmovnz  ebx, [rbp+90h+var_108]
0x14001511c  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHK@Z; CVssFunctionTracer::IsTracingEnabled(ulong)
0x140015121  test    eax, eax
0x140015123  jnz     loc_140015431
0x140015129  mov     rbx, r15
0x14001512c  nop     dword ptr [rax+00h]
0x140015130  mov     rcx, [rbp+rbx*8+90h+var_A8]; pv
0x140015135  test    rcx, rcx
0x140015138  jnz     loc_140015280
0x14001513e  inc     rbx
0x140015141  cmp     rbx, 0Fh
0x140015145  jnz     short loc_140015130
0x140015147  mov     rcx, [rdi+8]; pSid1
0x14001514b  test    rcx, rcx
0x14001514e  jz      loc_140015290
0x140015154  mov     rdx, [rsi+8]; bool
0x140015158  test    rdx, rdx
0x14001515b  jz      loc_14001540C
0x140015161  call    cs:__imp_EqualSid
0x140015167  lea     rdx, aFalse; "FALSE"
0x14001516e  mov     r8d, 0AAh; unsigned int
0x140015174  test    eax, eax
0x140015176  lea     rcx, aTrue; "TRUE"
0x14001517d  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x140015184  setnz   sil
0x140015188  test    eax, eax
0x14001518a  cmovz   rcx, rdx
0x14001518e  lea     rdx, aReturn; "RETURN"
0x140015195  mov     [rsp+190h+var_170], rcx
0x14001519a  lea     rcx, [rsp+190h+var_140]; this
0x14001519f  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x1400151a4  mov     rcx, [rbp+90h+pv]; pv
0x1400151a8  call    cs:__imp_CoTaskMemFree
0x1400151ae  mov     rcx, [rbp+90h+pv+8]; pv
0x1400151b2  mov     [rbp+90h+pv], r15
0x1400151b6  call    cs:__imp_CoTaskMemFree
0x1400151bc  mov     rcx, [rbp+90h+var_F0]; pv
0x1400151c0  mov     [rbp+90h+pv+8], r15
0x1400151c4  call    cs:__imp_CoTaskMemFree
0x1400151ca  mov     rcx, [rbp+90h+var_F0+8]; pv
0x1400151ce  mov     [rbp+90h+var_F0], r15
0x1400151d2  call    cs:__imp_CoTaskMemFree
0x1400151d8  mov     [rbp+90h+var_F0+8], r15
0x1400151dc  call    cs:__imp_GetTickCount
0x1400151e2  mov     r8d, [rsp+190h+var_138]
0x1400151e7  mov     edi, eax
0x1400151e9  sub     edi, [rbp+90h+var_10C]
0x1400151ec  mov     eax, 10624DD3h
0x1400151f1  mul     edi
0x1400151f3  mov     [rsp+190h+var_148], r8d
0x1400151f8  mov     eax, 88888889h
0x1400151fd  mov     ebx, edx
0x1400151ff  mov     dword ptr [rsp+190h+var_150], edi
0x140015203  shr     ebx, 6
0x140015206  mul     ebx
0x140015208  mov     r11d, ebx
0x14001520b  shr     edx, 5
0x14001520e  imul    eax, edx, 3Ch ; '<'
0x140015211  sub     r11d, eax
0x140015214  mov     eax, 45E7B273h
0x140015219  mul     edi
0x14001521b  mov     eax, 88888889h
0x140015220  mov     r10d, edx
0x140015223  shr     r10d, 0Eh
0x140015227  mul     r10d
0x14001522a  mov     eax, 95217CB1h
0x14001522f  shr     edx, 5
0x140015232  imul    ecx, edx, 3Ch ; '<'
0x140015235  mul     edi
0x140015237  sub     r10d, ecx
0x14001523a  mov     eax, 88888889h
0x14001523f  mov     r9d, edx
0x140015242  mov     ecx, edi
0x140015244  shr     r9d, 15h
0x140015248  mul     r9d
0x14001524b  shr     edx, 5
0x14001524e  imul    eax, edx, 3Ch ; '<'
0x140015251  sub     r9d, eax
0x140015254  cmp     [rbp+90h+var_108], 0FFh
0x14001525b  cmovnz  r14d, [rbp+90h+var_108]
0x140015260  imul    eax, ebx, 3E8h
0x140015266  sub     ecx, eax
0x140015268  mov     dword ptr [rsp+190h+var_158], ecx
0x14001526c  mov     dword ptr [rsp+190h+var_160], r11d
0x140015271  mov     dword ptr [rsp+190h+var_168], r10d
0x140015276  mov     dword ptr [rsp+190h+var_170], r9d
0x14001527b  jmp     loc_1400153A4
0x140015280  call    cs:__imp_CoTaskMemFree
0x140015286  mov     [rbp+rbx*8+90h+var_A8], r15
0x14001528b  jmp     loc_14001513E
0x140015290  cmp     [rsi+8], r15
0x140015294  lea     rdx, aFalse; "FALSE"
0x14001529b  lea     rcx, aTrue; "TRUE"
0x1400152a2  mov     r8d, 0AAh; unsigned int
0x1400152a8  setz    sil
0x1400152ac  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x1400152b3  test    sil, sil
0x1400152b6  cmovz   rcx, rdx
0x1400152ba  lea     rdx, aReturn; "RETURN"
0x1400152c1  mov     [rsp+190h+var_170], rcx
0x1400152c6  lea     rcx, [rsp+190h+var_140]; this
0x1400152cb  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x1400152d0  mov     rcx, [rbp+90h+pv]; pv
0x1400152d4  call    cs:__imp_CoTaskMemFree
0x1400152da  mov     rcx, [rbp+90h+pv+8]; pv
0x1400152de  mov     [rbp+90h+pv], r15
0x1400152e2  call    cs:__imp_CoTaskMemFree
0x1400152e8  mov     rcx, [rbp+90h+var_F0]; pv
0x1400152ec  mov     [rbp+90h+pv+8], r15
0x1400152f0  call    cs:__imp_CoTaskMemFree
0x1400152f6  mov     rcx, [rbp+90h+var_F0+8]; pv
0x1400152fa  mov     [rbp+90h+var_F0], r15
0x1400152fe  call    cs:__imp_CoTaskMemFree
0x140015304  mov     [rbp+90h+var_F0+8], r15
0x140015308  call    cs:__imp_GetTickCount
0x14001530e  mov     r9d, [rsp+190h+var_138]
0x140015313  mov     edi, eax
0x140015315  sub     edi, [rbp+90h+var_10C]
0x140015318  mov     eax, 10624DD3h
0x14001531d  mul     edi
0x14001531f  mov     [rsp+190h+var_148], r9d
0x140015324  mov     eax, 88888889h
0x140015329  mov     ecx, edx
0x14001532b  mov     dword ptr [rsp+190h+var_150], edi
0x14001532f  shr     ecx, 6
0x140015332  mul     ecx
0x140015334  mov     ebx, ecx
0x140015336  shr     edx, 5
0x140015339  imul    eax, edx, 3Ch ; '<'
0x14001533c  sub     ebx, eax
0x14001533e  mov     eax, 45E7B273h
0x140015343  mul     edi
0x140015345  mov     eax, 88888889h
0x14001534a  mov     r11d, edx
0x14001534d  shr     r11d, 0Eh
0x140015351  mul     r11d
0x140015354  shr     edx, 5
0x140015357  imul    eax, edx, 3Ch ; '<'
0x14001535a  sub     r11d, eax
0x14001535d  mov     eax, 95217CB1h
0x140015362  mul     edi
0x140015364  mov     eax, 88888889h
0x140015369  mov     r10d, edx
0x14001536c  shr     r10d, 15h
0x140015370  mul     r10d
0x140015373  shr     edx, 5
0x140015376  imul    eax, edx, 3Ch ; '<'
0x140015379  sub     r10d, eax
0x14001537c  cmp     [rbp+90h+var_108], 0FFh
0x140015383  cmovnz  r14d, [rbp+90h+var_108]
0x140015388  imul    eax, ecx, 3E8h
0x14001538e  mov     ecx, edi
0x140015390  sub     ecx, eax
0x140015392  mov     dword ptr [rsp+190h+var_158], ecx
0x140015396  mov     dword ptr [rsp+190h+var_160], ebx
0x14001539a  mov     dword ptr [rsp+190h+var_168], r11d
0x14001539f  mov     dword ptr [rsp+190h+var_170], r10d
0x1400153a4  lea     r9, aTimeSpent02ld0; "Time spent: %02ld:%02ld:%02ld-%04ld; to"...
0x1400153ab  mov     r8d, r14d; unsigned int
0x1400153ae  lea     rdx, aExit; "EXIT"
0x1400153b5  lea     rcx, [rsp+190h+var_140]; this
0x1400153ba  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x1400153bf  mov     rcx, [rbp+90h+var_E0]
0x1400153c3  call    cs:__imp_VssSetTracingContextPerThread
0x1400153c9  movzx   eax, sil
0x1400153cd  lea     r11, [rsp+190h+var_20]
0x1400153d5  mov     rbx, [r11+38h]
0x1400153d9  mov     rsi, [r11+40h]
0x1400153dd  mov     rsp, r11
0x1400153e0  pop     r15
0x1400153e2  pop     r14
0x1400153e4  pop     r12
0x1400153e6  pop     rdi
0x1400153e7  pop     rbp
0x1400153e8  retn
0x1400153e9  lea     rcx, [rsp+190h+var_140]
0x1400153ee  call    cs:__imp_VssSetTracingContextPerThread
0x1400153f4  test    eax, eax
0x1400153f6  js      loc_1400150EA
0x1400153fc  mov     rax, [rbp+90h+arg_0]
0x140015403  mov     [rbp+90h+var_E0], rax
0x140015407  jmp     loc_1400150EE
0x14001540c  lea     rcx, [rsp+190h+var_140]; this
0x140015411  call    ?Exit@CVssFunctionTracer@@QEAA_N_N@Z; CVssFunctionTracer::Exit(bool)
0x140015416  lea     rcx, [rsp+190h+var_140]; this
0x14001541b  movzx   ebx, al
0x14001541e  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x140015423  movzx   eax, bl
0x140015426  jmp     short loc_1400153CD
0x140015428  mov     [rbp+90h+var_110], r15d
0x14001542c  jmp     loc_1400150FF
0x140015431  mov     r9d, [rbp+90h+var_110]
0x140015435  lea     rax, aEnter; "ENTER"
0x14001543c  mov     r8d, [rsp+190h+var_120]
0x140015441  mov     rdx, [rsp+190h+var_128]
0x140015446  mov     rcx, [rsp+190h+var_130]
0x14001544b  mov     [rsp+190h+var_150], r15
0x140015450  mov     dword ptr [rsp+190h+var_158], ebx
0x140015454  mov     [rsp+190h+var_160], rax
0x140015459  mov     rax, [rsp+190h+var_118]
0x14001545e  mov     [rsp+190h+var_168], rax
0x140015463  mov     eax, [rsp+190h+var_11C]
0x140015467  mov     dword ptr [rsp+190h+var_170], eax
0x14001546b  call    cs:__imp_VssTraceMessage
0x140015471  jmp     loc_140015129
```
