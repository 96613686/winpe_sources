# CheckEventMetadataManifest

- ea: `0x180018484`
- end: `0x180018a33`
- name: `CheckEventMetadataManifest`
- size: `1455`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, service_task`

## callers

- `0x180004fb0`

## callees

- `0x18000746c`
- `0x1800086f4`
- `0x18000872c`
- `0x180009570`
- `0x180009a34`
- `0x180009bdc`
- `0x18000adf0`
- `0x18000b390`
- `0x18000bf6c`
- `0x180011fe0`
- `0x180012434`
- `0x180017c40`
- `0x180018380`
- `0x180018484`
- `0x1800207c0`
- `0x18002bf40`
- `0x18002bfa4`
- `0x18002c004`
- `0x18002c064`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall CheckEventMetadataManifest(__int64 a1, __int64 a2, __int64 a3, __int64 a4, _DWORD *a5)
{
  _DWORD *v8; // r13
  int v9; // r12d
  unsigned int Config; // ebx
  const struct _GUID *v11; // r9
  __int64 v12; // rdx
  int v13; // r14d
  const struct DWORDResource *Level; // rax
  int v15; // r12d
  int v16; // r13d
  unsigned __int64 i; // r12
  const struct QWORDResource *Keyword; // rax
  int v19; // eax
  int v20; // r12d
  const struct TaskResource *Task; // rax
  int v22; // esi
  const struct DWORDResource *Opcode; // rdx
  int v25; // [rsp+30h] [rbp-D0h] BYREF
  struct PUBLISHER_LOOKUP_ENTRY near **v26; // [rsp+38h] [rbp-C8h] BYREF
  int v27; // [rsp+40h] [rbp-C0h]
  char v28; // [rsp+44h] [rbp-BCh]
  void ***v29; // [rsp+48h] [rbp-B8h]
  HINSTANCE lpSource; // [rsp+50h] [rbp-B0h]
  void **v31; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v32; // [rsp+60h] [rbp-A0h]
  wchar_t *v33[2]; // [rsp+68h] [rbp-98h] BYREF
  DWORD dwMessageId[2]; // [rsp+78h] [rbp-88h]
  wchar_t *v35[2]; // [rsp+80h] [rbp-80h] BYREF
  DWORD v36[2]; // [rsp+90h] [rbp-70h]
  wchar_t *v37[2]; // [rsp+98h] [rbp-68h] BYREF
  DWORD v38[2]; // [rsp+A8h] [rbp-58h]
  wchar_t *v39[2]; // [rsp+B0h] [rbp-50h] BYREF
  DWORD v40[2]; // [rsp+C0h] [rbp-40h]
  void **v41; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v42; // [rsp+D0h] [rbp-30h]
  __int128 v43; // [rsp+E0h] [rbp-20h]
  _QWORD v44[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v45; // [rsp+100h] [rbp+0h] BYREF
  wchar_t *v46[2]; // [rsp+110h] [rbp+10h]
  DWORD v47[2]; // [rsp+120h] [rbp+20h]
  __int64 v48; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v49[24]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v50[48]; // [rsp+148h] [rbp+48h] BYREF
  __int64 v51; // [rsp+178h] [rbp+78h]

  v8 = a5;
  v32 = (__int64)a5;
  v42 = 0;
  v43 = 0;
  v41 = &PublisherManifestTdhConfig::`vftable';
  *(_OWORD *)v33 = 0;
  *(_QWORD *)dwMessageId = 0;
  *(_OWORD *)v37 = 0;
  *(_QWORD *)v38 = 0;
  *(_OWORD *)v35 = 0;
  *(_QWORD *)v36 = 0;
  v45 = 0;
  *(_OWORD *)v46 = 0;
  *(_QWORD *)v47 = 0;
  *(_OWORD *)v39 = 0;
  *(_QWORD *)v40 = 0;
  v9 = 0;
  v25 = 0;
  if ( a1 )
  {
    v31 = &ModuleLoaderImpl::`vftable';
    v44[0] = &ManifestResourceLoaderImpl::`vftable';
    v44[1] = a1 + 8;
    v29 = &v31;
    v26 = &g_EnvironmentTable;
    v27 = 2;
    v28 = 0;
    PublisherLookupNLoader<PublisherManifestResource>::PublisherLookupNLoader<PublisherManifestResource>(v49, v44);
    lpSource = 0;
    Config = PublisherManifestTdhConfig::ReadConfig((PublisherManifestTdhConfig *)&v41, v11);
    if ( Config )
      goto LABEL_64;
    if ( *((_QWORD *)&v43 + 1) )
    {
      Config = PublisherLookupNLoader<HINSTANCE__ *>::LookupNLoad(&v26);
      if ( Config )
        goto LABEL_64;
    }
    if ( *((_QWORD *)&v42 + 1) )
    {
      Config = PublisherLookupNLoader<PublisherManifestResource>::LookupNLoad(v49);
      if ( !Config )
      {
        v13 = 0;
        if ( *(_BYTE *)(a3 + 36) != *(_BYTE *)(a2 + 4) )
        {
          if ( *(_DWORD *)(a3 + 56) )
          {
            Config = TdhpGetStringSize(a3 + *(unsigned int *)(a3 + 56), 0, &v25);
            if ( Config )
              goto LABEL_64;
            v9 = v25;
          }
          Level = PublisherManifestResource::FindLevel((PublisherManifestResource *)v50, *(_BYTE *)(a2 + 4));
          if ( Level )
          {
            dwMessageId[0] = *((_DWORD *)Level + 1);
            Config = PublisherManifestResource::GetResourceString(
                       (PublisherManifestResource *)v50,
                       *((_DWORD *)Level + 2),
                       (const wchar_t **)&v33[1]);
            if ( Config )
              goto LABEL_64;
            Config = TdhpGetResourceName(
                       lpSource,
                       dwMessageId[0],
                       v33[1],
                       (wchar_t **)(a4 + 8),
                       (unsigned int *)(a4 + 596),
                       (unsigned __int8 *)(a4 + 893));
            if ( Config )
              goto LABEL_64;
          }
          v13 = *(_DWORD *)(a4 + 596) - v9;
        }
        if ( *(_BYTE *)(a3 + 35) != *(_BYTE *)(a2 + 3) )
        {
          if ( *(_DWORD *)(a3 + 60) )
          {
            Config = TdhpGetStringSize(a3 + *(unsigned int *)(a3 + 60), 0, &v25);
            if ( Config )
              goto LABEL_64;
            v15 = v25;
          }
          else
          {
            v15 = 0;
            v25 = 0;
          }
          if ( v51 )
          {
            if ( (unsigned int)*(unsigned __int8 *)(a2 + 3) < *(_DWORD *)(v51 + 8) )
            {
              v12 = v51 + 16LL * *(unsigned __int8 *)(a2 + 3) + 12;
              if ( v12 )
              {
                v36[1] = *(_DWORD *)(v12 + 12);
                Config = PublisherManifestResource::GetResourceString(
                           (PublisherManifestResource *)v50,
                           *(_DWORD *)(v12 + 4),
                           (const wchar_t **)&v35[1]);
                if ( Config )
                  goto LABEL_64;
                Config = TdhpGetResourceName(
                           lpSource,
                           v36[1],
                           v35[1],
                           (wchar_t **)(a4 + 16),
                           (unsigned int *)(a4 + 600),
                           (unsigned __int8 *)(a4 + 894));
                if ( Config )
                  goto LABEL_64;
              }
            }
          }
          v13 += *(_DWORD *)(a4 + 600) - v15;
        }
        if ( *(_QWORD *)(a3 + 40) != *(_QWORD *)(a2 + 8) )
        {
          if ( *(_DWORD *)(a3 + 64) )
          {
            LOBYTE(v12) = 1;
            Config = TdhpGetStringSize(a3 + *(unsigned int *)(a3 + 64), v12, &v25);
            if ( Config )
              goto LABEL_64;
          }
          else
          {
            v25 = 0;
          }
          v16 = 0;
          v48 = *(_QWORD *)(a2 + 8);
          *(_DWORD *)(a4 + 860) = std::bitset<64>::count(&v48);
          for ( i = 0; i < 0x40; ++i )
          {
            if ( (unsigned __int8)std::bitset<64>::test(&v48, i) )
            {
              Keyword = PublisherManifestResource::FindKeyword((PublisherManifestResource *)v50, 1LL << i);
              if ( Keyword )
              {
                v38[0] = *((_DWORD *)Keyword + 2);
                Config = PublisherManifestResource::GetResourceString(
                           (PublisherManifestResource *)v50,
                           *((_DWORD *)Keyword + 3),
                           (const wchar_t **)&v37[1]);
                if ( Config )
                  goto LABEL_64;
                Config = TdhpGetResourceName(
                           lpSource,
                           v38[0],
                           v37[1],
                           (wchar_t **)(a4 + 24 + 8 * i),
                           (unsigned int *)(a4 + 604 + 4 * i),
                           (unsigned __int8 *)(i + a4 + 895));
                if ( Config )
                  goto LABEL_64;
                v16 += *(_DWORD *)(a4 + 4 * i + 604);
              }
            }
          }
          v19 = v16 + 2;
          if ( !v16 )
            v19 = 0;
          v13 += v19 - v25;
          v8 = (_DWORD *)v32;
        }
        if ( *(_WORD *)(a3 + 38) != *(_WORD *)(a2 + 6) )
        {
          if ( *(_DWORD *)(a3 + 68) )
          {
            Config = TdhpGetStringSize(a3 + *(unsigned int *)(a3 + 68), 0, &v25);
            if ( Config )
              goto LABEL_64;
            v20 = v25;
          }
          else
          {
            v20 = 0;
            v25 = 0;
          }
          Task = PublisherManifestResource::FindTask((PublisherManifestResource *)v50, *(_WORD *)(a2 + 6));
          if ( Task )
          {
            Config = PublisherManifestResource::GetTaskResource(
                       (PublisherManifestResource *)v50,
                       Task,
                       (struct TaskResourceData *)&v45);
            if ( Config )
              goto LABEL_64;
            Config = TdhpGetResourceName(
                       lpSource,
                       v47[0],
                       v46[1],
                       (wchar_t **)(a4 + 536),
                       (unsigned int *)(a4 + 864),
                       (unsigned __int8 *)(a4 + 959));
            if ( Config )
              goto LABEL_64;
          }
          v13 += *(_DWORD *)(a4 + 864) - v20;
        }
        if ( *(_WORD *)(a3 + 38) != *(_WORD *)(a2 + 6) || *(_BYTE *)(a3 + 37) != *(_BYTE *)(a2 + 5) )
        {
          if ( *(_DWORD *)(a3 + 72) )
          {
            Config = TdhpGetStringSize(a3 + *(unsigned int *)(a3 + 72), 0, &v25);
            if ( Config )
              goto LABEL_64;
            v22 = v25;
          }
          else
          {
            v22 = 0;
          }
          Opcode = PublisherManifestResource::FindOpcode(
                     (PublisherManifestResource *)v50,
                     *(_WORD *)(a2 + 6),
                     *(_BYTE *)(a2 + 5));
          if ( Opcode
            || (Opcode = PublisherManifestResource::FindOpcode((PublisherManifestResource *)v50, 0, *(_BYTE *)(a2 + 5))) != 0 )
          {
            v40[0] = *((_DWORD *)Opcode + 1);
            Config = PublisherManifestResource::GetResourceString(
                       (PublisherManifestResource *)v50,
                       *((_DWORD *)Opcode + 2),
                       (const wchar_t **)&v39[1]);
            if ( Config )
              goto LABEL_64;
            Config = TdhpGetResourceName(
                       lpSource,
                       v40[0],
                       v39[1],
                       (wchar_t **)(a4 + 544),
                       (unsigned int *)(a4 + 868),
                       (unsigned __int8 *)(a4 + 960));
            if ( Config )
              goto LABEL_64;
          }
          v13 += *(_DWORD *)(a4 + 868) - v22;
        }
        *v8 = v13;
      }
    }
    else
    {
      Config = 4316;
    }
LABEL_64:
    PublisherLookupNLoader<PublisherManifestResource>::~PublisherLookupNLoader<PublisherManifestResource>(v49);
    PublisherLookupNLoader<HINSTANCE__ *>::~PublisherLookupNLoader<HINSTANCE__ *>(&v26);
    goto LABEL_65;
  }
  Config = 87;
LABEL_65:
  v41 = &PublisherManifestConfig::`vftable';
  PublisherManifestConfig::Free((PublisherManifestConfig *)&v41);
  return Config;
}

```

## disassembly

```asm
0x180018484  push    rbp
0x180018486  push    rbx
0x180018487  push    rsi
0x180018488  push    rdi
0x180018489  push    r12
0x18001848b  push    r13
0x18001848d  push    r14
0x18001848f  push    r15
0x180018491  lea     rbp, [rsp-128h]
0x180018499  sub     rsp, 228h
0x1800184a0  mov     rax, cs:__security_cookie
0x1800184a7  xor     rax, rsp
0x1800184aa  mov     [rbp+160h+var_50], rax
0x1800184b1  mov     rdi, r9
0x1800184b4  mov     rsi, r8
0x1800184b7  mov     r15, rdx
0x1800184ba  mov     r13, [rbp+160h+arg_20]
0x1800184c1  mov     [rsp+260h+var_200], r13
0x1800184c6  xorps   xmm0, xmm0
0x1800184c9  movdqu  [rbp+160h+var_190], xmm0
0x1800184ce  xorps   xmm1, xmm1
0x1800184d1  movdqu  [rbp+160h+var_180], xmm1
0x1800184d6  lea     rax, ??_7PublisherManifestTdhConfig@@6B@; const PublisherManifestTdhConfig::`vftable'
0x1800184dd  mov     [rbp+160h+var_198], rax
0x1800184e1  xor     eax, eax
0x1800184e3  movups  xmmword ptr [rsp+260h+var_1F8], xmm0
0x1800184e8  mov     qword ptr [rsp+260h+dwMessageId], rax
0x1800184ed  movups  xmmword ptr [rbp+160h+var_1C8], xmm1
0x1800184f1  mov     qword ptr [rbp+160h+var_1B8], rax
0x1800184f5  movups  xmmword ptr [rbp+160h+var_1E0], xmm0
0x1800184f9  mov     qword ptr [rbp+160h+var_1D0], rax
0x1800184fd  movups  [rbp+160h+var_160], xmm1
0x180018501  movups  xmmword ptr [rbp+160h+var_150], xmm1
0x180018505  mov     qword ptr [rbp+160h+var_140], rax
0x180018509  movups  xmmword ptr [rbp+160h+var_1B0], xmm0
0x18001850d  mov     qword ptr [rbp+160h+var_1A0], rax
0x180018511  xor     r12d, r12d
0x180018514  mov     [rsp+260h+var_230], r12d
0x180018519  test    rcx, rcx
0x18001851c  jnz     short loc_180018526
0x18001851e  lea     ebx, [rax+57h]
0x180018521  jmp     loc_1800189FA
0x180018526  lea     rax, ??_7ModuleLoaderImpl@@6B@; const ModuleLoaderImpl::`vftable'
0x18001852d  mov     [rsp+260h+var_208], rax
0x180018532  lea     rax, ??_7ManifestResourceLoaderImpl@@6B@; const ManifestResourceLoaderImpl::`vftable'
0x180018539  mov     [rbp+160h+var_170], rax
0x18001853d  lea     r9, [rcx+8]
0x180018541  mov     [rbp+160h+var_168], r9
0x180018545  lea     rax, [rsp+260h+var_208]
0x18001854a  mov     [rsp+260h+var_218], rax
0x18001854f  lea     rax, ?g_EnvironmentTable@@3PAUPUBLISHER_LOOKUP_ENTRY@@A; PUBLISHER_LOOKUP_ENTRY near * g_EnvironmentTable
0x180018556  mov     [rsp+260h+var_228], rax
0x18001855b  mov     [rsp+260h+var_220], 2
0x180018563  mov     [rsp+260h+var_21C], r12b
0x180018568  lea     rdx, [rbp+160h+var_170]
0x18001856c  lea     rcx, [rbp+160h+var_130]
0x180018570  call    ??0?$PublisherLookupNLoader@VPublisherManifestResource@@@@QEAA@PEAV?$IPublisherLoader@VPublisherManifestResource@@@@PEAUPUBLISHER_LOOKUP_ENTRY@@K@Z; PublisherLookupNLoader<PublisherManifestResource>::PublisherLookupNLoader<PublisherManifestResource>(IPublisherLoader<PublisherManifestResource> *,PUBLISHER_LOOKUP_ENTRY *,ulong)
0x180018575  nop
0x180018576  mov     [rsp+260h+lpSource], 0
0x18001857f  mov     rdx, r9; struct _GUID *
0x180018582  lea     rcx, [rbp+160h+var_198]; this
0x180018586  call    ?ReadConfig@PublisherManifestTdhConfig@@UEAAKAEBU_GUID@@@Z; PublisherManifestTdhConfig::ReadConfig(_GUID const &)
0x18001858b  mov     ebx, eax
0x18001858d  test    eax, eax
0x18001858f  jnz     loc_1800189E5
0x180018595  mov     rdx, qword ptr [rbp+160h+var_180+8]
0x180018599  test    rdx, rdx
0x18001859c  jz      short loc_1800185B2
0x18001859e  lea     rcx, [rsp+260h+var_228]
0x1800185a3  call    ?LookupNLoad@?$PublisherLookupNLoader@PEAUHINSTANCE__@@@@QEAAKPEB_W@Z; PublisherLookupNLoader<HINSTANCE__ *>::LookupNLoad(wchar_t const *)
0x1800185a8  mov     ebx, eax
0x1800185aa  test    eax, eax
0x1800185ac  jnz     loc_1800189E5
0x1800185b2  mov     rdx, qword ptr [rbp+160h+var_190+8]
0x1800185b6  test    rdx, rdx
0x1800185b9  jnz     short loc_1800185C5
0x1800185bb  mov     ebx, 10DCh
0x1800185c0  jmp     loc_1800189E5
0x1800185c5  lea     rcx, [rbp+160h+var_130]
0x1800185c9  call    ?LookupNLoad@?$PublisherLookupNLoader@VPublisherManifestResource@@@@QEAAKPEB_W@Z; PublisherLookupNLoader<PublisherManifestResource>::LookupNLoad(wchar_t const *)
0x1800185ce  mov     ebx, eax
0x1800185d0  test    eax, eax
0x1800185d2  jnz     loc_1800189E5
0x1800185d8  xor     r14d, r14d
0x1800185db  mov     al, [r15+4]
0x1800185df  cmp     [rsi+24h], al
0x1800185e2  jz      loc_180018686
0x1800185e8  cmp     [rsi+38h], r14d
0x1800185ec  jz      short loc_18001860F
0x1800185ee  mov     ecx, [rsi+38h]
0x1800185f1  add     rcx, rsi
0x1800185f4  lea     r8, [rsp+260h+var_230]
0x1800185f9  xor     edx, edx
0x1800185fb  call    TdhpGetStringSize
0x180018600  mov     ebx, eax
0x180018602  test    eax, eax
0x180018604  jnz     loc_1800189E5
0x18001860a  mov     r12d, [rsp+260h+var_230]
0x18001860f  mov     dl, [r15+4]; unsigned __int8
0x180018613  lea     rcx, [rbp+160h+var_118]; this
0x180018617  call    ?FindLevel@PublisherManifestResource@@QEBAPEBUDWORDResource@@E@Z; PublisherManifestResource::FindLevel(uchar)
0x18001861c  test    rax, rax
0x18001861f  jz      short loc_18001867C
0x180018621  mov     ecx, [rax+4]
0x180018624  mov     [rsp+260h+dwMessageId], ecx
0x180018628  lea     r8, [rsp+260h+var_1F8+8]; wchar_t **
0x18001862d  mov     edx, [rax+8]; unsigned int
0x180018630  lea     rcx, [rbp+160h+var_118]; this
0x180018634  call    ?GetResourceString@PublisherManifestResource@@QEBAKKAEAPEB_W@Z; PublisherManifestResource::GetResourceString(ulong,wchar_t const * &)
0x180018639  mov     ebx, eax
0x18001863b  test    eax, eax
0x18001863d  jnz     loc_1800189E5
0x180018643  lea     rax, [rdi+37Dh]
0x18001864a  lea     rcx, [rdi+254h]
0x180018651  lea     r9, [rdi+8]; wchar_t **
0x180018655  mov     [rsp+260h+var_238], rax; unsigned __int8 *
0x18001865a  mov     [rsp+260h+var_240], rcx; unsigned int *
0x18001865f  mov     r8, [rsp+260h+var_1F8+8]; wchar_t *
0x180018664  mov     edx, [rsp+260h+dwMessageId]; dwMessageId
0x180018668  mov     rcx, [rsp+260h+lpSource]; lpSource
0x18001866d  call    ?TdhpGetResourceName@@YAKPEAUHINSTANCE__@@KPEB_WPEAPEA_WPEAKPEAE@Z; TdhpGetResourceName(HINSTANCE__ *,ulong,wchar_t const *,wchar_t * *,ulong *,uchar *)
0x180018672  mov     ebx, eax
0x180018674  test    eax, eax
0x180018676  jnz     loc_1800189E5
0x18001867c  mov     r14d, [rdi+254h]
0x180018683  sub     r14d, r12d
0x180018686  mov     al, [r15+3]
0x18001868a  cmp     [rsi+23h], al
0x18001868d  jz      loc_180018749
0x180018693  cmp     dword ptr [rsi+3Ch], 0
0x180018697  jnz     short loc_1800186A3
0x180018699  xor     r12d, r12d
0x18001869c  mov     [rsp+260h+var_230], r12d
0x1800186a1  jmp     short loc_1800186C4
0x1800186a3  mov     ecx, [rsi+3Ch]
0x1800186a6  add     rcx, rsi
0x1800186a9  lea     r8, [rsp+260h+var_230]
0x1800186ae  xor     edx, edx
0x1800186b0  call    TdhpGetStringSize
0x1800186b5  mov     ebx, eax
0x1800186b7  test    eax, eax
0x1800186b9  jnz     loc_1800189E5
0x1800186bf  mov     r12d, [rsp+260h+var_230]
0x1800186c4  mov     rcx, [rbp+160h+var_E8]
0x1800186c8  test    rcx, rcx
0x1800186cb  jz      short loc_18001873D
0x1800186cd  movzx   eax, byte ptr [r15+3]
0x1800186d2  cmp     eax, [rcx+8]
0x1800186d5  jnb     short loc_18001873D
0x1800186d7  mov     edx, eax
0x1800186d9  shl     rdx, 4
0x1800186dd  add     rdx, 0Ch
0x1800186e1  add     rdx, rcx
0x1800186e4  jz      short loc_18001873D
0x1800186e6  mov     eax, [rdx+0Ch]
0x1800186e9  mov     [rbp+160h+var_1D0+4], eax
0x1800186ec  lea     r8, [rbp+160h+var_1E0+8]; wchar_t **
0x1800186f0  mov     edx, [rdx+4]; unsigned int
0x1800186f3  lea     rcx, [rbp+160h+var_118]; this
0x1800186f7  call    ?GetResourceString@PublisherManifestResource@@QEBAKKAEAPEB_W@Z; PublisherManifestResource::GetResourceString(ulong,wchar_t const * &)
0x1800186fc  mov     ebx, eax
0x1800186fe  test    eax, eax
0x180018700  jnz     loc_1800189E5
0x180018706  lea     rax, [rdi+37Eh]
0x18001870d  lea     rcx, [rdi+258h]
0x180018714  lea     r9, [rdi+10h]; wchar_t **
0x180018718  mov     [rsp+260h+var_238], rax; unsigned __int8 *
0x18001871d  mov     [rsp+260h+var_240], rcx; unsigned int *
0x180018722  mov     r8, [rbp+160h+var_1E0+8]; wchar_t *
0x180018726  mov     edx, [rbp+160h+var_1D0+4]; dwMessageId
0x180018729  mov     rcx, [rsp+260h+lpSource]; lpSource
0x18001872e  call    ?TdhpGetResourceName@@YAKPEAUHINSTANCE__@@KPEB_WPEAPEA_WPEAKPEAE@Z; TdhpGetResourceName(HINSTANCE__ *,ulong,wchar_t const *,wchar_t * *,ulong *,uchar *)
0x180018733  mov     ebx, eax
0x180018735  test    eax, eax
0x180018737  jnz     loc_1800189E5
0x18001873d  mov     eax, [rdi+258h]
0x180018743  sub     eax, r12d
0x180018746  add     r14d, eax
0x180018749  mov     rax, [r15+8]
0x18001874d  cmp     [rsi+28h], rax
0x180018751  jz      loc_180018860
0x180018757  cmp     dword ptr [rsi+40h], 0
0x18001875b  jnz     short loc_180018767
0x18001875d  mov     [rsp+260h+var_230], 0
0x180018765  jmp     short loc_180018783
0x180018767  mov     ecx, [rsi+40h]
0x18001876a  add     rcx, rsi
0x18001876d  lea     r8, [rsp+260h+var_230]
0x180018772  mov     dl, 1
0x180018774  call    TdhpGetStringSize
0x180018779  mov     ebx, eax
0x18001877b  test    eax, eax
0x18001877d  jnz     loc_1800189E5
0x180018783  xor     r13d, r13d
0x180018786  mov     rax, [r15+8]
0x18001878a  mov     [rbp+160h+var_138], rax
0x18001878e  lea     rcx, [rbp+160h+var_138]
0x180018792  call    ?count@?$bitset@$0EA@@std@@QEBA_KXZ; std::bitset<64>::count(void)
0x180018797  mov     [rdi+35Ch], eax
0x18001879d  xor     r12d, r12d
0x1800187a0  cmp     r12, 40h ; '@'
0x1800187a4  jnb     loc_180018849
0x1800187aa  mov     rdx, r12
0x1800187ad  lea     rcx, [rbp+160h+var_138]
0x1800187b1  call    ?test@?$bitset@$0EA@@std@@QEBA_N_K@Z; std::bitset<64>::test(unsigned __int64)
0x1800187b6  test    al, al
0x1800187b8  jz      loc_180018841
0x1800187be  mov     rcx, r12
0x1800187c1  mov     edx, 1
0x1800187c6  shl     rdx, cl; unsigned __int64
0x1800187c9  lea     rcx, [rbp+160h+var_118]; this
0x1800187cd  call    ?FindKeyword@PublisherManifestResource@@QEBAPEBUQWORDResource@@_K@Z; PublisherManifestResource::FindKeyword(unsigned __int64)
0x1800187d2  test    rax, rax
0x1800187d5  jz      short loc_180018841
0x1800187d7  mov     ecx, [rax+8]
0x1800187da  mov     [rbp+160h+var_1B8], ecx
0x1800187dd  lea     r8, [rbp+160h+var_1C8+8]; wchar_t **
0x1800187e1  mov     edx, [rax+0Ch]; unsigned int
0x1800187e4  lea     rcx, [rbp+160h+var_118]; this
0x1800187e8  call    ?GetResourceString@PublisherManifestResource@@QEBAKKAEAPEB_W@Z; PublisherManifestResource::GetResourceString(ulong,wchar_t const * &)
0x1800187ed  mov     ebx, eax
0x1800187ef  test    eax, eax
0x1800187f1  jnz     loc_1800189E5
0x1800187f7  lea     rax, [rdi+37Fh]
0x1800187fe  add     rax, r12
0x180018801  lea     rcx, [rdi+25Ch]
0x180018808  lea     rcx, [rcx+r12*4]
0x18001880c  lea     r9, [rdi+18h]
0x180018810  lea     r9, [r9+r12*8]; wchar_t **
0x180018814  mov     [rsp+260h+var_238], rax; unsigned __int8 *
0x180018819  mov     [rsp+260h+var_240], rcx; unsigned int *
0x18001881e  mov     r8, [rbp+160h+var_1C8+8]; wchar_t *
0x180018822  mov     edx, [rbp+160h+var_1B8]; dwMessageId
0x180018825  mov     rcx, [rsp+260h+lpSource]; lpSource
0x18001882a  call    ?TdhpGetResourceName@@YAKPEAUHINSTANCE__@@KPEB_WPEAPEA_WPEAKPEAE@Z; TdhpGetResourceName(HINSTANCE__ *,ulong,wchar_t const *,wchar_t * *,ulong *,uchar *)
0x18001882f  mov     ebx, eax
0x180018831  test    eax, eax
0x180018833  jnz     loc_1800189E5
0x180018839  add     r13d, [rdi+r12*4+25Ch]
0x180018841  inc     r12
0x180018844  jmp     loc_1800187A0
0x180018849  lea     eax, [r13+2]
0x18001884d  test    r13d, r13d
0x180018850  cmovz   eax, r13d
0x180018854  sub     eax, [rsp+260h+var_230]
0x180018858  add     r14d, eax
0x18001885b  mov     r13, [rsp+260h+var_200]
0x180018860  movzx   eax, word ptr [r15+6]
0x180018865  cmp     [rsi+26h], ax
0x180018869  jz      loc_180018913
0x18001886f  cmp     dword ptr [rsi+44h], 0
0x180018873  jnz     short loc_18001887F
0x180018875  xor     r12d, r12d
0x180018878  mov     [rsp+260h+var_230], r12d
0x18001887d  jmp     short loc_1800188A0
0x18001887f  mov     ecx, [rsi+44h]
0x180018882  add     rcx, rsi
0x180018885  lea     r8, [rsp+260h+var_230]
0x18001888a  xor     edx, edx
0x18001888c  call    TdhpGetStringSize
0x180018891  mov     ebx, eax
0x180018893  test    eax, eax
0x180018895  jnz     loc_1800189E5
0x18001889b  mov     r12d, [rsp+260h+var_230]
0x1800188a0  movzx   edx, word ptr [r15+6]; unsigned __int16
0x1800188a5  lea     rcx, [rbp+160h+var_118]; this
0x1800188a9  call    ?FindTask@PublisherManifestResource@@QEBAPEBUTaskResource@@G@Z; PublisherManifestResource::FindTask(ushort)
0x1800188ae  test    rax, rax
0x1800188b1  jz      short loc_180018907
0x1800188b3  lea     r8, [rbp+160h+var_160]; struct TaskResourceData *
0x1800188b7  mov     rdx, rax; struct TaskResource *
0x1800188ba  lea     rcx, [rbp+160h+var_118]; this
0x1800188be  call    ?GetTaskResource@PublisherManifestResource@@QEBAKPEBUTaskResource@@AEAUTaskResourceData@@@Z; PublisherManifestResource::GetTaskResource(TaskResource const *,TaskResourceData &)
0x1800188c3  mov     ebx, eax
0x1800188c5  test    eax, eax
0x1800188c7  jnz     loc_1800189E5
0x1800188cd  lea     rax, [rdi+3BFh]
0x1800188d4  lea     rcx, [rdi+360h]
0x1800188db  lea     r9, [rdi+218h]; wchar_t **
0x1800188e2  mov     [rsp+260h+var_238], rax; unsigned __int8 *
0x1800188e7  mov     [rsp+260h+var_240], rcx; unsigned int *
0x1800188ec  mov     r8, [rbp+160h+var_150+8]; wchar_t *
0x1800188f0  mov     edx, [rbp+160h+var_140]; dwMessageId
0x1800188f3  mov     rcx, [rsp+260h+lpSource]; lpSource
0x1800188f8  call    ?TdhpGetResourceName@@YAKPEAUHINSTANCE__@@KPEB_WPEAPEA_WPEAKPEAE@Z; TdhpGetResourceName(HINSTANCE__ *,ulong,wchar_t const *,wchar_t * *,ulong *,uchar *)
0x1800188fd  mov     ebx, eax
0x1800188ff  test    eax, eax
0x180018901  jnz     loc_1800189E5
0x180018907  mov     eax, [rdi+360h]
0x18001890d  sub     eax, r12d
0x180018910  add     r14d, eax
0x180018913  movzx   eax, word ptr [r15+6]
0x180018918  cmp     [rsi+26h], ax
0x18001891c  jnz     short loc_18001892B
0x18001891e  mov     al, [r15+5]
0x180018922  cmp     [rsi+25h], al
0x180018925  jz      loc_1800189E1
0x18001892b  cmp     dword ptr [rsi+48h], 0
0x18001892f  jnz     short loc_180018935
0x180018931  xor     esi, esi
  ... truncated ...
```
