# CSpp::CleanupUnusedSnapshots(void)

- ea: `0x1800057e0`
- end: `0x180005d10`
- name: `?CleanupUnusedSnapshots@CSpp@@UEAAJXZ`
- size: `1328`
- prototype: `__int64 __fastcall(CSpp *__hidden this)`
- caller_count: `0`
- callee_count: `21`
- tags: `broker_com_uri`

## callees

- `0x1800021f8`
- `0x18000232c`
- `0x1800057e0`
- `0x1800074e4`
- `0x180007544`
- `0x180008c74`
- `0x18000c894`
- `0x18000e308`
- `0x18000e34c`
- `0x18000f888`
- `0x18001e2dc`
- `0x180020570`
- `0x180020650`
- `0x180020710`
- `0x1800251cc`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002d1e0`
- `0x18003532c`
- `0x180035bd0`
- `0x180037010`

## import_xrefs

- `VSSAPI!CreateVssBackupComponentsInternal` at `0x180005a81`
- `VSSAPI!CreateVssBackupComponentsInternal` at `0x180005a81`

## pseudocode

```c
__int64 __fastcall CSpp::CleanupUnusedSnapshots(CSpp *this)
{
  struct CVolumeEntry *v2; // rbx
  CSxStringMap *v3; // rsi
  int v4; // eax
  __int16 v5; // ax
  bool v6; // sf
  __int16 v7; // ax
  int v8; // eax
  __int64 i; // r15
  __int64 v10; // rdi
  __int64 j; // r12
  int v12; // eax
  int v13; // eax
  CVolumeEntry *v14; // rcx
  __int64 v15; // rdx
  CSpp *v16; // rcx
  int v17; // ecx
  __int64 k; // r12
  __int64 v19; // rdi
  __int64 v20; // rax
  unsigned int m; // r13d
  __int64 v22; // r15
  __int64 v23; // r14
  int v24; // eax
  CVolumeEntry *v25; // rcx
  int v26; // eax
  __int64 v27; // rax
  int v28; // eax
  unsigned int v29; // edi
  __int64 v30; // rdx
  __int64 v31; // r8
  struct CSxStringMap *v33; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v34; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v35; // [rsp+4Ch] [rbp-B4h] BYREF
  struct CVolumeEntry *v36; // [rsp+50h] [rbp-B0h] BYREF
  int v37; // [rsp+58h] [rbp-A8h] BYREF
  __int16 v38; // [rsp+5Ch] [rbp-A4h]
  __int16 v39; // [rsp+5Eh] [rbp-A2h]
  struct IVssBackupComponents *v40; // [rsp+90h] [rbp-70h] BYREF
  CVolumeEntry *v41; // [rsp+98h] [rbp-68h] BYREF
  int v42; // [rsp+A0h] [rbp-60h]
  __int64 v43; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v44[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v45; // [rsp+C0h] [rbp-40h] BYREF
  _OWORD v46[2]; // [rsp+D0h] [rbp-30h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 212, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v37, "CSpp::CleanupUnusedSnapshots", 12282, 1);
  v2 = 0;
  v34 = 0;
  v3 = 0;
  v43 = 0;
  v35 = 0;
  v46[0] = GUID_NULL;
  v44[0] = 0;
  v33 = 0;
  v36 = 0;
  v41 = 0;
  ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(&v40);
  v42 = 0;
  v46[1] = GUID_NULL;
  if ( (unsigned int)SxIsSafeMode() || (unsigned int)SxIsWinPE() )
  {
    v37 = -2147023812;
    v7 = 12303;
  }
  else
  {
    v37 = 0;
    v38 = 12303;
    v4 = (*(__int64 (__fastcall **)(CSpp *, _QWORD, _OWORD *))(*(_QWORD *)this + 104LL))(this, 0, v46);
    if ( v4 == -2130706172 )
    {
      v37 = 1;
      v5 = 12311;
LABEL_8:
      v38 = v5;
      goto LABEL_63;
    }
    v37 = v4;
    v6 = v4 < 0;
    v7 = 12313;
    if ( !v6 )
    {
      v38 = 12313;
      v37 = CSxStringMap::CreateInstance(&v33);
      v7 = 12316;
      if ( v37 >= 0 )
      {
        v38 = 12316;
        v8 = (*(__int64 (__fastcall **)(CSpp *, _QWORD, unsigned int *, __int64 *))(*(_QWORD *)this + 96LL))(
               this,
               0,
               &v34,
               &v43);
        v3 = v33;
        v6 = v8 < 0;
        v37 = v8;
        v7 = 12321;
        if ( !v6 )
        {
          v38 = 12321;
          for ( i = 0; (unsigned int)i < v34; i = (unsigned int)(i + 1) )
          {
            v10 = v43 + 48 * i;
            if ( *(_DWORD *)(v10 + 16) != 1 || *(_DWORD *)(v10 + 20) )
            {
              for ( j = 0; (unsigned int)j < *(_DWORD *)(v10 + 24); j = (unsigned int)(j + 1) )
              {
                if ( !v2 )
                {
                  v12 = CVolumeEntry::CreateInstance(&v36);
                  v2 = v36;
                  v37 = v12;
                  if ( v12 < 0 )
                  {
                    v39 = 12342;
                    goto LABEL_63;
                  }
                  v38 = 12342;
                }
                v37 = CBsString::Set(
                        (struct CVolumeEntry *)((char *)v2 + 8),
                        *(const unsigned __int16 **)(*(_QWORD *)(v10 + 32) + 8 * j));
                v7 = 12345;
                if ( v37 < 0 )
                  goto LABEL_62;
                v38 = 12345;
                v13 = CSxRefMap<CWriterEntryMap,CWriterEntry>::Insert(v3, v2);
                v37 = v13;
                if ( v13 < 0 )
                {
                  v7 = 12346;
                  goto LABEL_62;
                }
                v38 = 12346;
                if ( !v13 )
                {
                  v14 = v2;
                  if ( v2 )
                  {
                    v2 = 0;
                    v36 = 0;
                    CVolumeEntry::Release(v14);
                  }
                }
              }
            }
          }
          v37 = (*(__int64 (__fastcall **)(CSpp *, unsigned int *, _QWORD *))(*(_QWORD *)this + 64LL))(this, &v35, v44);
          v7 = 12361;
          if ( v37 >= 0 )
          {
            v38 = 12361;
            v37 = CreateVssBackupComponentsInternal(&v40, v15);
            v7 = 12366;
            if ( v37 >= 0 )
            {
              v38 = 12366;
              v37 = (*(__int64 (__fastcall **)(struct IVssBackupComponents *, _QWORD))(*(_QWORD *)v40 + 40LL))(v40, 0);
              v7 = 12367;
              if ( v37 >= 0 )
              {
                v38 = 12367;
                v37 = CSpp::_SetSnapshotContext(v16, v40, 0);
                v7 = 12368;
                if ( v37 >= 0 )
                {
                  v17 = 0;
                  v38 = 12368;
                  LODWORD(v33) = 0;
                  for ( k = 0; (unsigned int)k < v35; k = (unsigned int)(k + 1) )
                  {
                    v19 = v44[0] + 144 * k;
                    v20 = *(_QWORD *)(v19 + 40) - *(_QWORD *)&v46[0];
                    if ( !v20 )
                      v20 = *(_QWORD *)(v19 + 48) - *((_QWORD *)&v46[0] + 1);
                    if ( !v20 )
                    {
                      for ( m = 0; m < *(_DWORD *)(v19 + 80); ++m )
                      {
                        v22 = *(_QWORD *)(v19 + 88);
                        v23 = 56LL * m;
                        if ( *(_QWORD *)(v23 + v22 + 16) && *(_QWORD *)(v23 + v22 + 24) )
                        {
                          if ( !v2 )
                          {
                            v24 = CVolumeEntry::CreateInstance(&v36);
                            v2 = v36;
                            v6 = v24 < 0;
                            v37 = v24;
                            v7 = 12399;
                            if ( v6 )
                              goto LABEL_62;
                            v38 = 12399;
                          }
                          v37 = CBsString::Set(
                                  (struct CVolumeEntry *)((char *)v2 + 8),
                                  *(const unsigned __int16 **)(v23 + v22 + 16));
                          v7 = 12405;
                          if ( v37 < 0 )
                            goto LABEL_62;
                          v25 = v41;
                          v38 = 12405;
                          if ( v41 )
                          {
                            v41 = 0;
                            CVolumeEntry::Release(v25);
                          }
                          v26 = CSxRefMap<CPathCache,CPathCacheNode>::Find(v3, v2, &v41);
                          v37 = v26;
                          if ( v26 < 0 )
                          {
                            v7 = 12407;
                            goto LABEL_62;
                          }
                          v38 = 12407;
                          if ( v26
                            && (v27 = *(_QWORD *)v40,
                                v45 = *(_OWORD *)(v23 + v22),
                                v28 = (*(__int64 (__fastcall **)(struct IVssBackupComponents *, __int128 *, __int64))(v27 + 312))(
                                        v40,
                                        &v45,
                                        3),
                                v28 < 0) )
                          {
                            Log_SPP_ERROR_SNAPSHOT_DELETION(
                              (struct CSxFunctionTracer *)&v37,
                              0x3089u,
                              *(const unsigned __int16 **)(v23 + v22 + 16),
                              *(const unsigned __int16 **)(v23 + v22 + 24),
                              v28);
                            v17 = 1;
                            LODWORD(v33) = 1;
                          }
                          else
                          {
                            v17 = (int)v33;
                          }
                        }
                      }
                    }
                  }
                  if ( !v17 )
                  {
                    v37 = 0;
                    v5 = 12436;
                    goto LABEL_8;
                  }
                  v37 = -2130706165;
                  v7 = 12434;
                }
              }
            }
          }
        }
      }
      else
      {
        v3 = v33;
      }
    }
  }
LABEL_62:
  v39 = v7;
LABEL_63:
  SppFreeClientPropArray(v34, &v43);
  SppFreeGroupPropArray(v35, v44);
  v29 = v37;
  ATL::CComPtr<IVssExamineWriterMetadata>::~CComPtr<IVssExamineWriterMetadata>();
  if ( v41 )
    CVolumeEntry::Release(v41);
  if ( v2 )
    CVolumeEntry::Release(v2);
  if ( v3 )
    CSxStringMap::Release(v3);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v37, v30, v31);
  return v29;
}

```

## disassembly

```asm
0x1800057e0  push    rbp
0x1800057e2  push    rbx
0x1800057e3  push    rsi
0x1800057e4  push    rdi
0x1800057e5  push    r12
0x1800057e7  push    r13
0x1800057e9  push    r14
0x1800057eb  push    r15
0x1800057ed  lea     rbp, [rsp-8]
0x1800057f2  sub     rsp, 108h
0x1800057f9  mov     rax, cs:__security_cookie
0x180005800  xor     rax, rsp
0x180005803  mov     [rbp+40h+var_50], rax
0x180005807  mov     r14, rcx
0x18000580a  mov     rcx, cs:WPP_GLOBAL_Control
0x180005811  lea     rax, WPP_GLOBAL_Control
0x180005818  cmp     rcx, rax
0x18000581b  jz      short loc_18000583B
0x18000581d  test    dword ptr [rcx+1Ch], 20000000h
0x180005824  jz      short loc_18000583B
0x180005826  mov     rcx, [rcx+10h]
0x18000582a  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x180005831  mov     edx, 0D4h
0x180005836  call    WPP_SF_
0x18000583b  mov     r9d, 1; unsigned __int16
0x180005841  lea     rdx, aCsppCleanupunu; "CSpp::CleanupUnusedSnapshots"
0x180005848  mov     r8d, 2FFAh; unsigned __int16
0x18000584e  lea     rcx, [rsp+140h+var_E8]; this
0x180005853  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180005858  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000585f  xor     ebx, ebx
0x180005861  mov     [rsp+140h+var_F8], 0
0x180005869  xor     esi, esi
0x18000586b  mov     [rbp+40h+var_98], 0
0x180005873  lea     rcx, [rbp+40h+var_B0]
0x180005877  mov     [rsp+140h+var_F4], 0
0x18000587f  movdqu  [rbp+40h+var_70], xmm0
0x180005884  mov     [rbp+40h+var_90], 0
0x18000588c  mov     [rsp+140h+var_100], rsi
0x180005891  mov     [rsp+140h+var_F0], rbx
0x180005896  mov     [rbp+40h+var_A8], rbx
0x18000589a  call    ??0?$CComPtr@VIVssBackupComponents@@@ATL@@QEAA@H@Z; ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(int)
0x18000589f  mov     [rbp+40h+var_A0], ebx
0x1800058a2  movdqu  [rbp+40h+var_60], xmm0
0x1800058a7  call    ?SxIsSafeMode@@YAHXZ; SxIsSafeMode(void)
0x1800058ac  test    eax, eax
0x1800058ae  jnz     loc_180005C83
0x1800058b4  call    ?SxIsWinPE@@YAHXZ; SxIsWinPE(void)
0x1800058b9  test    eax, eax
0x1800058bb  jnz     loc_180005C83
0x1800058c1  mov     eax, 300Fh
0x1800058c6  mov     [rsp+140h+var_E8], ebx
0x1800058ca  mov     [rsp+140h+var_E4], ax
0x1800058cf  lea     r8, [rbp+40h+var_70]
0x1800058d3  mov     rax, [r14]
0x1800058d6  xor     edx, edx
0x1800058d8  mov     rcx, r14
0x1800058db  mov     rax, [rax+68h]
0x1800058df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058e4  cmp     eax, 81000104h
0x1800058e9  jnz     short loc_180005902
0x1800058eb  mov     [rsp+140h+var_E8], 1
0x1800058f3  mov     eax, 3017h
0x1800058f8  mov     [rsp+140h+var_E4], ax
0x1800058fd  jmp     loc_180005C95
0x180005902  mov     [rsp+140h+var_E8], eax
0x180005906  test    eax, eax
0x180005908  mov     eax, 3019h
0x18000590d  js      loc_180005C90
0x180005913  lea     rcx, [rsp+140h+var_100]; struct CSxStringMap **
0x180005918  mov     [rsp+140h+var_E4], ax
0x18000591d  call    ?CreateInstance@CSxStringMap@@SAJPEAPEAV1@@Z; CSxStringMap::CreateInstance(CSxStringMap * *)
0x180005922  mov     [rsp+140h+var_E8], eax
0x180005926  test    eax, eax
0x180005928  mov     eax, 301Ch
0x18000592d  jns     short loc_180005939
0x18000592f  mov     rsi, [rsp+140h+var_100]
0x180005934  jmp     loc_180005C90
0x180005939  mov     [rsp+140h+var_E4], ax
0x18000593e  lea     r9, [rbp+40h+var_98]
0x180005942  mov     rax, [r14]
0x180005945  lea     r8, [rsp+140h+var_F8]
0x18000594a  xor     edx, edx
0x18000594c  mov     rcx, r14
0x18000594f  mov     rax, [rax+60h]
0x180005953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005958  mov     rsi, [rsp+140h+var_100]
0x18000595d  test    eax, eax
0x18000595f  mov     [rsp+140h+var_E8], eax
0x180005963  mov     eax, 3021h
0x180005968  js      loc_180005C90
0x18000596e  mov     [rsp+140h+var_E4], ax
0x180005973  lea     r13d, [rax+15h]
0x180005977  xor     r15d, r15d
0x18000597a  cmp     r15d, [rsp+140h+var_F8]
0x18000597f  jnb     loc_180005A4F
0x180005985  lea     rdi, [r15+r15*2]
0x180005989  shl     rdi, 4
0x18000598d  add     rdi, [rbp+40h+var_98]
0x180005991  cmp     dword ptr [rdi+10h], 1
0x180005995  jnz     short loc_1800059A1
0x180005997  cmp     dword ptr [rdi+14h], 0
0x18000599b  jz      loc_180005A32
0x1800059a1  xor     r12d, r12d
0x1800059a4  cmp     r12d, [rdi+18h]
0x1800059a8  jnb     loc_180005A32
0x1800059ae  test    rbx, rbx
0x1800059b1  jnz     short loc_1800059D0
0x1800059b3  lea     rcx, [rsp+140h+var_F0]; struct CVolumeEntry **
0x1800059b8  call    ?CreateInstance@CVolumeEntry@@SAJPEAPEAV1@@Z; CVolumeEntry::CreateInstance(CVolumeEntry * *)
0x1800059bd  mov     rbx, [rsp+140h+var_F0]
0x1800059c2  mov     [rsp+140h+var_E8], eax
0x1800059c6  test    eax, eax
0x1800059c8  js      short loc_180005A3A
0x1800059ca  mov     [rsp+140h+var_E4], r13w
0x1800059d0  mov     rdx, [rdi+20h]
0x1800059d4  lea     rcx, [rbx+8]; this
0x1800059d8  mov     rdx, [rdx+r12*8]; unsigned __int16 *
0x1800059dc  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x1800059e1  mov     [rsp+140h+var_E8], eax
0x1800059e5  test    eax, eax
0x1800059e7  mov     eax, 3039h
0x1800059ec  js      loc_180005C90
0x1800059f2  mov     rdx, rbx
0x1800059f5  mov     [rsp+140h+var_E4], ax
0x1800059fa  mov     rcx, rsi
0x1800059fd  call    ?Insert@?$CSxRefMap@VCWriterEntryMap@@VCWriterEntry@@@@QEAAJPEAVCWriterEntry@@PEAPEAV2@@Z; CSxRefMap<CWriterEntryMap,CWriterEntry>::Insert(CWriterEntry *,CWriterEntry * *)
0x180005a02  mov     [rsp+140h+var_E8], eax
0x180005a06  test    eax, eax
0x180005a08  js      short loc_180005A45
0x180005a0a  mov     ecx, 303Ah
0x180005a0f  mov     [rsp+140h+var_E4], cx
0x180005a14  jnz     short loc_180005A2A
0x180005a16  mov     rcx, rbx; this
0x180005a19  test    rbx, rbx
0x180005a1c  jz      short loc_180005A2A
0x180005a1e  xor     ebx, ebx
0x180005a20  mov     [rsp+140h+var_F0], rbx
0x180005a25  call    ?Release@CVolumeEntry@@QEAAKXZ; CVolumeEntry::Release(void)
0x180005a2a  inc     r12d
0x180005a2d  jmp     loc_1800059A4
0x180005a32  inc     r15d
0x180005a35  jmp     loc_18000597A
0x180005a3a  mov     [rsp+140h+var_E2], r13w
0x180005a40  jmp     loc_180005C95
0x180005a45  mov     eax, 303Ah
0x180005a4a  jmp     loc_180005C90
0x180005a4f  mov     rax, [r14]
0x180005a52  lea     r8, [rbp+40h+var_90]
0x180005a56  lea     rdx, [rsp+140h+var_F4]
0x180005a5b  mov     rcx, r14
0x180005a5e  mov     rax, [rax+40h]
0x180005a62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a67  mov     [rsp+140h+var_E8], eax
0x180005a6b  test    eax, eax
0x180005a6d  mov     eax, 3049h
0x180005a72  js      loc_180005C90
0x180005a78  lea     rcx, [rbp+40h+var_B0]
0x180005a7c  mov     [rsp+140h+var_E4], ax
0x180005a81  call    cs:__imp_CreateVssBackupComponentsInternal
0x180005a87  mov     [rsp+140h+var_E8], eax
0x180005a8b  test    eax, eax
0x180005a8d  mov     eax, 304Eh
0x180005a92  js      loc_180005C90
0x180005a98  mov     rcx, [rbp+40h+var_B0]
0x180005a9c  xor     edx, edx
0x180005a9e  mov     [rsp+140h+var_E4], ax
0x180005aa3  mov     rax, [rcx]
0x180005aa6  mov     rax, [rax+28h]
0x180005aaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005aaf  mov     [rsp+140h+var_E8], eax
0x180005ab3  test    eax, eax
0x180005ab5  mov     eax, 304Fh
0x180005aba  js      loc_180005C90
0x180005ac0  mov     rdx, [rbp+40h+var_B0]; struct IVssBackupComponents *
0x180005ac4  xor     r8d, r8d; unsigned int
0x180005ac7  mov     [rsp+140h+var_E4], ax
0x180005acc  call    ?_SetSnapshotContext@CSpp@@AEAAJPEAVIVssBackupComponents@@K@Z; CSpp::_SetSnapshotContext(IVssBackupComponents *,ulong)
0x180005ad1  mov     [rsp+140h+var_E8], eax
0x180005ad5  test    eax, eax
0x180005ad7  mov     eax, 3050h
0x180005adc  js      loc_180005C90
0x180005ae2  xor     ecx, ecx
0x180005ae4  mov     [rsp+140h+var_E4], ax
0x180005ae9  mov     dword ptr [rsp+140h+var_100], ecx
0x180005aed  xor     r12d, r12d
0x180005af0  cmp     r12d, [rsp+140h+var_F4]
0x180005af5  jnb     loc_180005C5E
0x180005afb  lea     rdi, [r12+r12*8]
0x180005aff  shl     rdi, 4
0x180005b03  add     rdi, [rbp+40h+var_90]
0x180005b07  mov     rax, [rdi+28h]
0x180005b0b  sub     rax, qword ptr [rbp+40h+var_70]
0x180005b0f  jnz     short loc_180005B19
0x180005b11  mov     rax, [rdi+30h]
0x180005b15  sub     rax, qword ptr [rbp+40h+var_70+8]
0x180005b19  test    rax, rax
0x180005b1c  jnz     loc_180005C4F
0x180005b22  xor     r13d, r13d
0x180005b25  cmp     r13d, [rdi+50h]
0x180005b29  jnb     loc_180005C4F
0x180005b2f  mov     r15, [rdi+58h]
0x180005b33  mov     eax, r13d
0x180005b36  imul    r14, rax, 38h ; '8'
0x180005b3a  cmp     qword ptr [r14+r15+10h], 0
0x180005b40  jz      loc_180005C47
0x180005b46  cmp     qword ptr [r14+r15+18h], 0
0x180005b4c  jz      loc_180005C47
0x180005b52  test    rbx, rbx
0x180005b55  jnz     short loc_180005B7C
0x180005b57  lea     rcx, [rsp+140h+var_F0]; struct CVolumeEntry **
0x180005b5c  call    ?CreateInstance@CVolumeEntry@@SAJPEAPEAV1@@Z; CVolumeEntry::CreateInstance(CVolumeEntry * *)
0x180005b61  mov     rbx, [rsp+140h+var_F0]
0x180005b66  test    eax, eax
0x180005b68  mov     [rsp+140h+var_E8], eax
0x180005b6c  mov     eax, 306Fh
0x180005b71  js      loc_180005C90
0x180005b77  mov     [rsp+140h+var_E4], ax
0x180005b7c  mov     rdx, [r14+r15+10h]; unsigned __int16 *
0x180005b81  lea     rcx, [rbx+8]; this
0x180005b85  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180005b8a  mov     [rsp+140h+var_E8], eax
0x180005b8e  test    eax, eax
0x180005b90  mov     eax, 3075h
0x180005b95  js      loc_180005C90
0x180005b9b  mov     rcx, [rbp+40h+var_A8]; this
0x180005b9f  mov     [rsp+140h+var_E4], ax
0x180005ba4  test    rcx, rcx
0x180005ba7  jz      short loc_180005BB6
0x180005ba9  mov     [rbp+40h+var_A8], 0
0x180005bb1  call    ?Release@CVolumeEntry@@QEAAKXZ; CVolumeEntry::Release(void)
0x180005bb6  lea     r8, [rbp+40h+var_A8]
0x180005bba  mov     rdx, rbx
0x180005bbd  mov     rcx, rsi
0x180005bc0  call    ?Find@?$CSxRefMap@VCPathCache@@VCPathCacheNode@@@@QEAAJPEAVCPathCacheNode@@PEAPEAV2@@Z; CSxRefMap<CPathCache,CPathCacheNode>::Find(CPathCacheNode *,CPathCacheNode * *)
0x180005bc5  mov     [rsp+140h+var_E8], eax
0x180005bc9  test    eax, eax
0x180005bcb  js      loc_180005C57
0x180005bd1  mov     ecx, 3077h
0x180005bd6  mov     [rsp+140h+var_E4], cx
0x180005bdb  jz      short loc_180005C43
0x180005bdd  mov     rcx, [rbp+40h+var_B0]
0x180005be1  lea     rdx, [rbp+40h+var_60]
0x180005be5  movups  xmm0, xmmword ptr [r14+r15]
0x180005bea  mov     [rsp+140h+var_118], rdx
0x180005bef  xor     r9d, r9d
0x180005bf2  lea     rdx, [rbp+40h+var_A0]
0x180005bf6  mov     rax, [rcx]
0x180005bf9  mov     qword ptr [rsp+140h+var_120], rdx
0x180005bfe  lea     rdx, [rbp+40h+var_80]
0x180005c02  lea     r8d, [r9+3]
0x180005c06  movdqu  [rbp+40h+var_80], xmm0
0x180005c0b  mov     rax, [rax+138h]
0x180005c12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c17  test    eax, eax
0x180005c19  jns     short loc_180005C43
0x180005c1b  mov     r9, [r14+r15+18h]; unsigned __int16 *
0x180005c20  lea     rcx, [rsp+140h+var_E8]; this
0x180005c25  mov     r8, [r14+r15+10h]; unsigned __int16 *
0x180005c2a  mov     edx, 3089h; unsigned int
0x180005c2f  mov     [rsp+140h+var_120], eax; int
0x180005c33  call    ?Log_SPP_ERROR_SNAPSHOT_DELETION@@YAJPEAVCSxFunctionTracer@@KPEBG1J@Z; Log_SPP_ERROR_SNAPSHOT_DELETION(CSxFunctionTracer *,ulong,ushort const *,ushort const *,long)
0x180005c38  mov     ecx, 1
0x180005c3d  mov     dword ptr [rsp+140h+var_100], ecx
0x180005c41  jmp     short loc_180005C47
0x180005c43  mov     ecx, dword ptr [rsp+140h+var_100]
0x180005c47  inc     r13d
0x180005c4a  jmp     loc_180005B25
0x180005c4f  inc     r12d
0x180005c52  jmp     loc_180005AF0
0x180005c57  mov     eax, 3077h
0x180005c5c  jmp     short loc_180005C90
0x180005c5e  test    ecx, ecx
0x180005c60  jz      short loc_180005C71
0x180005c62  mov     [rsp+140h+var_E8], 8100010Bh
0x180005c6a  mov     eax, 3092h
0x180005c6f  jmp     short loc_180005C90
0x180005c71  mov     [rsp+140h+var_E8], 0
0x180005c79  mov     eax, 3094h
0x180005c7e  jmp     loc_1800058F8
0x180005c83  mov     [rsp+140h+var_E8], 8007043Ch
0x180005c8b  mov     eax, 300Fh
0x180005c90  mov     [rsp+140h+var_E2], ax
0x180005c95  mov     ecx, [rsp+140h+var_F8]
0x180005c99  lea     rdx, [rbp+40h+var_98]
0x180005c9d  call    SppFreeClientPropArray
0x180005ca2  mov     ecx, [rsp+140h+var_F4]
0x180005ca6  lea     rdx, [rbp+40h+var_90]
0x180005caa  call    SppFreeGroupPropArray
0x180005caf  mov     edi, [rsp+140h+var_E8]
0x180005cb3  lea     rcx, [rbp+40h+var_B0]
0x180005cb7  call    ??1?$CComPtr@VIVssExamineWriterMetadata@@@ATL@@QEAA@XZ; ATL::CComPtr<IVssExamineWriterMetadata>::~CComPtr<IVssExamineWriterMetadata>(void)
0x180005cbc  mov     rcx, [rbp+40h+var_A8]; this
0x180005cc0  test    rcx, rcx
0x180005cc3  jz      short loc_180005CCA
0x180005cc5  call    ?Release@CVolumeEntry@@QEAAKXZ; CVolumeEntry::Release(void)
0x180005cca  test    rbx, rbx
0x180005ccd  jz      short loc_180005CD7
0x180005ccf  mov     rcx, rbx; this
0x180005cd2  call    ?Release@CVolumeEntry@@QEAAKXZ; CVolumeEntry::Release(void)
  ... truncated ...
```
