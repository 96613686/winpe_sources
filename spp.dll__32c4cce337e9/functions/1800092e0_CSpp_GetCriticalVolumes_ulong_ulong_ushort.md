# CSpp::GetCriticalVolumes(ulong,ulong *,ushort * * *)

- ea: `0x1800092e0`
- end: `0x180009849`
- name: `?GetCriticalVolumes@CSpp@@UEAAJKPEAKPEAPEAPEAG@Z`
- size: `1385`
- prototype: `__int64 __fastcall(CSpp *__hidden this, unsigned int, unsigned int *, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `24`
- tags: `broker_com_uri`

## callees

- `0x1800021f8`
- `0x18000232c`
- `0x180007344`
- `0x180007650`
- `0x18000907c`
- `0x1800092e0`
- `0x18000b5f4`
- `0x18000c804`
- `0x18000cc50`
- `0x18000e080`
- `0x18000e308`
- `0x18000e48c`
- `0x18000e54c`
- `0x18000e58c`
- `0x18001004c`
- `0x180016e24`
- `0x180017960`
- `0x18001b1e0`
- `0x180020710`
- `0x180020908`
- `0x180021088`
- `0x1800268b4`
- `0x1800269ac`
- `0x180037010`

## import_xrefs

- `VSSAPI!CreateVssBackupComponentsInternal` at `0x1800093d1`
- `VSSAPI!CreateVssBackupComponentsInternal` at `0x1800093d1`

## pseudocode

```c
__int64 __fastcall CSpp::GetCriticalVolumes(CSpp *this, char a2, unsigned int *a3, unsigned __int16 ***a4)
{
  __int64 v6; // rdx
  struct CSxVolumeInfoArray *v7; // r15
  __int64 v8; // rsi
  CComponentEntry *v9; // r13
  CVolumeEntry *v10; // rdi
  struct CVolumeEntryMap *v11; // r12
  __int16 v12; // ax
  int inited; // ebx
  __int16 v14; // ax
  CSpp *v15; // rcx
  CSpp *v16; // rcx
  int v17; // eax
  int Instance; // eax
  CSpp *v19; // rcx
  unsigned int v20; // eax
  unsigned int v21; // r10d
  int v22; // edx
  int v23; // r8d
  int v24; // r10d
  __int16 v25; // r11
  unsigned int v26; // r14d
  unsigned int v27; // eax
  int v28; // eax
  __int64 v29; // rax
  bool v30; // sf
  __int16 v31; // ax
  __int64 v32; // rdx
  __int64 v33; // r8
  int v35; // [rsp+38h] [rbp-69h]
  CVolumeEntry *v36; // [rsp+40h] [rbp-61h] BYREF
  int v37; // [rsp+48h] [rbp-59h] BYREF
  __int16 v38; // [rsp+4Ch] [rbp-55h]
  __int16 v39; // [rsp+4Eh] [rbp-53h]
  struct CVolumeEntryMap *v40; // [rsp+80h] [rbp-21h] BYREF
  struct CSxVolumeInfoArray *v41; // [rsp+88h] [rbp-19h] BYREF
  struct IVssBackupComponents *v42; // [rsp+90h] [rbp-11h] BYREF
  int v43; // [rsp+98h] [rbp-9h] BYREF
  CVolumeEntryMap *v44[2]; // [rsp+A0h] [rbp-1h]
  CComponentEntry *v45; // [rsp+B0h] [rbp+Fh] BYREF
  __int64 v46; // [rsp+B8h] [rbp+17h] BYREF
  unsigned __int64 v47[7]; // [rsp+C0h] [rbp+1Fh] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 186, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v37, "CSpp::GetCriticalVolumes", 10784, 1);
  ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(&v42);
  v7 = 0;
  v8 = 0;
  v41 = 0;
  v9 = 0;
  v47[0] = 0;
  v10 = 0;
  v46 = 0;
  v11 = 0;
  v45 = 0;
  v36 = 0;
  v40 = 0;
  v12 = 10800;
  v43 = 0;
  *(_OWORD *)v44 = 0;
  if ( a3 && (v38 = 10800, v12 = 10801, a4) )
  {
    v37 = 0;
    v38 = 10801;
    *a3 = 0;
    *a4 = 0;
    inited = CreateVssBackupComponentsInternal(&v42, v6);
    v37 = inited;
    v14 = 10809;
    if ( inited >= 0 )
    {
      v38 = 10809;
      inited = (*(__int64 (__fastcall **)(struct IVssBackupComponents *, _QWORD))(*(_QWORD *)v42 + 40LL))(v42, 0);
      v37 = inited;
      v14 = 10811;
      if ( inited >= 0 )
      {
        v38 = 10811;
        inited = CSpp::_InitTimer(v15, 0xFFFFFFFFLL, v47);
        v37 = inited;
        v14 = 10813;
        if ( inited >= 0 )
        {
          v38 = 10813;
          inited = CSpp::_EnableInterestingWriters(v16, 0, v42);
          v37 = inited;
          v14 = 10815;
          if ( inited >= 0 )
          {
            v38 = 10815;
            v17 = CSxVolumeInfoArray::CreateInstance(&v41);
            v7 = v41;
            inited = v17;
            v37 = v17;
            v30 = v17 < 0;
            v14 = 10818;
            if ( !v30 )
            {
              v38 = 10818;
              inited = CSpp::_GatherWriterMetadata(this, v42, v41, v47[0]);
              v37 = inited;
              v14 = 10819;
              if ( inited >= 0 )
              {
                v38 = 10819;
                Instance = CVolumeEntryMap::CreateInstance((LPVOID **)&v40);
                v11 = v40;
                inited = Instance;
                v37 = Instance;
                v30 = Instance < 0;
                v14 = 10824;
                if ( !v30 )
                {
                  v38 = 10824;
                  v20 = *((_DWORD *)v7 + 2);
                  v21 = 0;
                  LODWORD(v41) = v20;
                  while ( 1 )
                  {
                    v35 = v21;
                    if ( v21 >= v20 )
                      break;
                    if ( v8 )
                    {
                      v46 = 0;
                      CWriterEntry::Release((CWriterEntry *)v8);
                      v21 = v35;
                    }
                    v37 = CSxRefArray<CWriterEntryArray,CWriterEntry>::Get(v7, v21, &v46);
                    inited = v37;
                    if ( v37 < 0 )
                    {
                      v8 = v46;
                      v39 = v25;
                      goto LABEL_58;
                    }
                    v38 = v25;
                    v19 = (CSpp *)WPP_GLOBAL_Control;
                    v8 = v46;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
                    {
                      WPP_SF_Sdd(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        v22,
                        v23,
                        *(_QWORD *)(v46 + 8),
                        *(_DWORD *)(v46 + 80),
                        *(_DWORD *)(v46 + 76));
                      v24 = v35;
                    }
                    if ( !*(_DWORD *)(v8 + 80) && *(_DWORD *)(v8 + 76) )
                    {
                      v26 = 0;
                      v27 = *(_DWORD *)(*(_QWORD *)(v8 + 64) + 8LL);
                      LODWORD(v40) = v27;
                      while ( 1 )
                      {
                        if ( v26 >= v27 )
                        {
                          v24 = v35;
                          goto LABEL_49;
                        }
                        if ( v9 )
                        {
                          v45 = 0;
                          CComponentEntry::Release(v9);
                        }
                        v28 = CSxRefArray<CWriterEntryArray,CWriterEntry>::Get(*(_QWORD *)(v8 + 64), v26, &v45);
                        v9 = v45;
                        inited = v28;
                        v37 = v28;
                        v30 = v28 < 0;
                        v14 = 10853;
                        if ( v30 )
                          goto LABEL_8;
                        v38 = 10853;
                        if ( *((_DWORD *)v45 + 28) )
                          break;
LABEL_47:
                        v27 = (unsigned int)v40;
                        ++v26;
                      }
                      if ( v44[0] )
                      {
                        CVolumeEntryMap::Release(v44[0]);
                        v44[0] = 0;
                      }
                      v43 = 0;
                      v44[1] = 0;
                      v29 = *((_QWORD *)v9 + 15);
                      if ( !v29 )
                      {
                        inited = -2147024809;
                        v37 = -2147024809;
                        v14 = 10861;
                        goto LABEL_8;
                      }
                      v44[0] = *((CVolumeEntryMap **)v9 + 15);
                      _InterlockedIncrement((volatile signed __int32 *)(v29 + 16));
                      v43 = *((_DWORD *)v44[0] + 2);
                      v44[1] = 0;
                      v37 = 0;
                      v38 = 10861;
                      if ( v10 )
                      {
                        v36 = 0;
                        CVolumeEntry::Release(v10);
                      }
                      inited = CSxRefMap<CSxStringMap,CSxStringEntry>::CSxIter::Next(&v43, &v36);
                      v37 = inited;
                      v30 = inited < 0;
                      v31 = 10864;
                      while ( !v30 )
                      {
                        v38 = v31;
                        if ( inited == 1 )
                        {
                          v10 = v36;
                          goto LABEL_47;
                        }
                        v10 = v36;
                        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
                        {
                          WPP_SF_S(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            188,
                            &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids,
                            *((_QWORD *)v36 + 1));
                        }
                        inited = CSxRefMap<CVolumeOnDiskPropCacheMap,CVolumeOnDiskPropCacheEntry>::Insert(v11, v10, 0);
                        v37 = inited;
                        v14 = 10869;
                        if ( inited < 0 )
                          goto LABEL_8;
                        v38 = 10869;
                        if ( v10 )
                        {
                          v36 = 0;
                          CVolumeEntry::Release(v10);
                        }
                        inited = CSxRefMap<CSxStringMap,CSxStringEntry>::CSxIter::Next(&v43, &v36);
                        v37 = inited;
                        v30 = inited < 0;
                        v31 = 10872;
                      }
                      v10 = v36;
                      v39 = v31;
                      goto LABEL_58;
                    }
LABEL_49:
                    v20 = (unsigned int)v41;
                    v21 = v24 + 1;
                  }
                  if ( (a2 & 1) == 0 )
                  {
                    inited = CSpp::_AddASRCriticalVolumes(v19, v7, v11);
                    v37 = inited;
                    v14 = 10879;
                    if ( inited < 0 )
                      goto LABEL_8;
                    v38 = 10879;
                  }
                  inited = CVolumeEntryMap::GetVolumeNameArray(v11, a3, a4);
                  v37 = inited;
                  v14 = 10882;
                  if ( inited >= 0 )
                  {
                    v38 = 10882;
                    goto LABEL_58;
                  }
                }
              }
            }
          }
        }
      }
    }
LABEL_8:
    v39 = v14;
LABEL_58:
    if ( v44[0] )
    {
      CVolumeEntryMap::Release(v44[0]);
      v44[0] = 0;
    }
  }
  else
  {
    inited = -2147024809;
    v39 = v12;
    v37 = -2147024809;
  }
  v43 = 0;
  v44[1] = 0;
  if ( v11 )
    CVolumeEntryMap::Release(v11);
  if ( v10 )
    CVolumeEntry::Release(v10);
  if ( v9 )
    CComponentEntry::Release(v9);
  if ( v8 )
    CWriterEntry::Release((CWriterEntry *)v8);
  if ( v7 )
    CWriterEntryArray::Release(v7);
  ATL::CComPtr<IVssExamineWriterMetadata>::~CComPtr<IVssExamineWriterMetadata>();
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v37, v32, v33);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1800092e0  mov     rax, rsp
0x1800092e3  mov     [rax+8], rbx
0x1800092e7  mov     [rax+20h], r9
0x1800092eb  mov     [rax+18h], r8
0x1800092ef  mov     [rax+10h], edx
0x1800092f2  push    rbp
0x1800092f3  push    rsi
0x1800092f4  push    rdi
0x1800092f5  push    r12
0x1800092f7  push    r13
0x1800092f9  push    r14
0x1800092fb  push    r15
0x1800092fd  lea     rbp, [rax-5Fh]
0x180009301  sub     rsp, 0C0h
0x180009308  mov     rbx, r9
0x18000930b  mov     r14, rcx
0x18000930e  mov     rcx, cs:WPP_GLOBAL_Control
0x180009315  lea     rax, WPP_GLOBAL_Control
0x18000931c  cmp     rcx, rax
0x18000931f  jz      short loc_18000933F
0x180009321  test    dword ptr [rcx+1Ch], 20000000h
0x180009328  jz      short loc_18000933F
0x18000932a  mov     rcx, [rcx+10h]
0x18000932e  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x180009335  mov     edx, 0BAh
0x18000933a  call    WPP_SF_
0x18000933f  mov     r9d, 1; unsigned __int16
0x180009345  lea     rdx, aCsppGetcritica; "CSpp::GetCriticalVolumes"
0x18000934c  mov     r8d, 2A20h; unsigned __int16
0x180009352  lea     rcx, [rbp+57h+var_B0]; this
0x180009356  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000935b  lea     rcx, [rbp+57h+var_68]
0x18000935f  call    ??0?$CComPtr@VIVssBackupComponents@@@ATL@@QEAA@H@Z; ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(int)
0x180009364  mov     rcx, [rbp+57h+arg_10]
0x180009368  xor     r15d, r15d
0x18000936b  xor     esi, esi
0x18000936d  mov     [rbp+57h+var_70], r15
0x180009371  xor     r13d, r13d
0x180009374  mov     [rbp+57h+var_38], r15
0x180009378  xor     edi, edi
0x18000937a  mov     [rbp+57h+var_40], rsi
0x18000937e  xor     r12d, r12d
0x180009381  mov     [rbp+57h+var_48], r13
0x180009385  mov     [rbp+57h+var_B8], rdi
0x180009389  xorps   xmm0, xmm0
0x18000938c  mov     [rbp+57h+var_78], r12
0x180009390  mov     eax, 2A30h
0x180009395  mov     [rbp+57h+var_60], esi
0x180009398  movdqu  xmmword ptr [rbp+57h+var_58], xmm0
0x18000939d  test    rcx, rcx
0x1800093a0  jnz     short loc_1800093B3
0x1800093a2  mov     ebx, 80070057h
0x1800093a7  mov     [rbp+57h+var_AA], ax
0x1800093ab  mov     [rbp+57h+var_B0], ebx
0x1800093ae  jmp     loc_1800097CA
0x1800093b3  mov     [rbp+57h+var_AC], ax
0x1800093b7  mov     eax, 2A31h
0x1800093bc  test    rbx, rbx
0x1800093bf  jz      short loc_1800093A2
0x1800093c1  mov     [rbp+57h+var_B0], esi
0x1800093c4  mov     [rbp+57h+var_AC], ax
0x1800093c8  mov     [rcx], esi
0x1800093ca  lea     rcx, [rbp+57h+var_68]
0x1800093ce  mov     [rbx], rsi
0x1800093d1  call    cs:__imp_CreateVssBackupComponentsInternal
0x1800093d7  mov     ebx, eax
0x1800093d9  mov     [rbp+57h+var_B0], eax
0x1800093dc  test    eax, eax
0x1800093de  mov     eax, 2A39h
0x1800093e3  jns     short loc_1800093EE
0x1800093e5  mov     [rbp+57h+var_AA], ax
0x1800093e9  jmp     loc_1800097B4
0x1800093ee  mov     rcx, [rbp+57h+var_68]
0x1800093f2  xor     edx, edx
0x1800093f4  mov     [rbp+57h+var_AC], ax
0x1800093f8  mov     rax, [rcx]
0x1800093fb  mov     rax, [rax+28h]
0x1800093ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009404  mov     ebx, eax
0x180009406  mov     [rbp+57h+var_B0], eax
0x180009409  test    eax, eax
0x18000940b  mov     eax, 2A3Bh
0x180009410  js      short loc_1800093E5
0x180009412  lea     r8, [rbp+57h+var_38]; unsigned __int64 *
0x180009416  mov     [rbp+57h+var_AC], ax
0x18000941a  or      edx, 0FFFFFFFFh; unsigned int
0x18000941d  call    ?_InitTimer@CSpp@@AEAAJKPEA_K@Z; CSpp::_InitTimer(ulong,unsigned __int64 *)
0x180009422  mov     ebx, eax
0x180009424  mov     [rbp+57h+var_B0], eax
0x180009427  test    eax, eax
0x180009429  mov     eax, 2A3Dh
0x18000942e  js      short loc_1800093E5
0x180009430  mov     r8, [rbp+57h+var_68]; struct IVssBackupComponents *
0x180009434  xor     edx, edx; int
0x180009436  mov     [rbp+57h+var_AC], ax
0x18000943a  call    ?_EnableInterestingWriters@CSpp@@AEAAJHPEAVIVssBackupComponents@@@Z; CSpp::_EnableInterestingWriters(int,IVssBackupComponents *)
0x18000943f  mov     ebx, eax
0x180009441  mov     [rbp+57h+var_B0], eax
0x180009444  test    eax, eax
0x180009446  mov     eax, 2A3Fh
0x18000944b  js      short loc_1800093E5
0x18000944d  lea     rcx, [rbp+57h+var_70]; struct CSxVolumeInfoArray **
0x180009451  mov     [rbp+57h+var_AC], ax
0x180009455  call    ?CreateInstance@CSxVolumeInfoArray@@SAJPEAPEAV1@@Z; CSxVolumeInfoArray::CreateInstance(CSxVolumeInfoArray * *)
0x18000945a  mov     r15, [rbp+57h+var_70]
0x18000945e  mov     ebx, eax
0x180009460  mov     [rbp+57h+var_B0], eax
0x180009463  test    eax, eax
0x180009465  mov     eax, 2A42h
0x18000946a  js      loc_1800093E5
0x180009470  mov     r9, [rbp+57h+var_38]; unsigned __int64
0x180009474  mov     r8, r15; struct CWriterEntryArray *
0x180009477  mov     rdx, [rbp+57h+var_68]; struct IVssBackupComponents *
0x18000947b  mov     rcx, r14; this
0x18000947e  mov     [rbp+57h+var_AC], ax
0x180009482  call    ?_GatherWriterMetadata@CSpp@@AEAAJPEAVIVssBackupComponents@@PEAVCWriterEntryArray@@_K@Z; CSpp::_GatherWriterMetadata(IVssBackupComponents *,CWriterEntryArray *,unsigned __int64)
0x180009487  mov     ebx, eax
0x180009489  mov     [rbp+57h+var_B0], eax
0x18000948c  test    eax, eax
0x18000948e  mov     eax, 2A43h
0x180009493  js      loc_1800093E5
0x180009499  lea     rcx, [rbp+57h+var_78]; struct CVolumeEntryMap **
0x18000949d  mov     [rbp+57h+var_AC], ax
0x1800094a1  call    ?CreateInstance@CVolumeEntryMap@@SAJPEAPEAV1@@Z; CVolumeEntryMap::CreateInstance(CVolumeEntryMap * *)
0x1800094a6  mov     r12, [rbp+57h+var_78]
0x1800094aa  mov     ebx, eax
0x1800094ac  mov     [rbp+57h+var_B0], eax
0x1800094af  test    eax, eax
0x1800094b1  mov     eax, 2A48h
0x1800094b6  js      loc_1800093E5
0x1800094bc  mov     [rbp+57h+var_AC], ax
0x1800094c0  lea     r14, WPP_GLOBAL_Control
0x1800094c7  mov     eax, [r15+8]
0x1800094cb  xor     r10d, r10d
0x1800094ce  mov     dword ptr [rbp+57h+var_70], eax
0x1800094d1  mov     r11d, 2A4Eh
0x1800094d7  mov     [rbp+57h+var_C0], r10d
0x1800094db  cmp     r10d, eax
0x1800094de  jnb     loc_180009767
0x1800094e4  test    rsi, rsi
0x1800094e7  jz      short loc_180009503
0x1800094e9  mov     rcx, rsi; this
0x1800094ec  mov     [rbp+57h+var_40], 0
0x1800094f4  call    ?Release@CWriterEntry@@QEAAKXZ; CWriterEntry::Release(void)
0x1800094f9  mov     r10d, [rbp+57h+var_C0]
0x1800094fd  mov     r11d, 2A4Eh
0x180009503  lea     r8, [rbp+57h+var_40]
0x180009507  mov     edx, r10d
0x18000950a  mov     rcx, r15
0x18000950d  call    ?Get@?$CSxRefArray@VCWriterEntryArray@@VCWriterEntry@@@@QEAAJKPEAPEAVCWriterEntry@@@Z; CSxRefArray<CWriterEntryArray,CWriterEntry>::Get(ulong,CWriterEntry * *)
0x180009512  mov     [rbp+57h+var_B0], eax
0x180009515  mov     ebx, eax
0x180009517  test    eax, eax
0x180009519  js      loc_18000975C
0x18000951f  mov     [rbp+57h+var_AC], r11w
0x180009524  mov     rcx, cs:WPP_GLOBAL_Control
0x18000952b  mov     rsi, [rbp+57h+var_40]
0x18000952f  cmp     rcx, r14
0x180009532  jz      short loc_180009562
0x180009534  test    dword ptr [rcx+1Ch], 8000000h
0x18000953b  jz      short loc_180009562
0x18000953d  mov     eax, [rsi+4Ch]
0x180009540  mov     r9, [rsi+8]
0x180009544  mov     rcx, [rcx+10h]
0x180009548  mov     [rsp+28h], eax
0x18000954c  mov     eax, [rsi+50h]
0x18000954f  mov     [rsp+0F0h+var_D0], eax
0x180009553  call    WPP_SF_Sdd
0x180009558  mov     r10d, [rbp+57h+var_C0]
0x18000955c  mov     r11d, 2A4Eh
0x180009562  cmp     dword ptr [rsi+50h], 0
0x180009566  jnz     loc_18000972E
0x18000956c  cmp     dword ptr [rsi+4Ch], 0
0x180009570  jz      loc_18000972E
0x180009576  mov     rax, [rsi+40h]
0x18000957a  xor     r14d, r14d
0x18000957d  mov     eax, [rax+8]
0x180009580  mov     dword ptr [rbp+57h+var_78], eax
0x180009583  cmp     r14d, eax
0x180009586  jnb     loc_18000971D
0x18000958c  test    r13, r13
0x18000958f  jz      short loc_1800095A1
0x180009591  mov     rcx, r13; this
0x180009594  mov     [rbp+57h+var_48], 0
0x18000959c  call    ?Release@CComponentEntry@@QEAAKXZ; CComponentEntry::Release(void)
0x1800095a1  mov     rcx, [rsi+40h]
0x1800095a5  lea     r8, [rbp+57h+var_48]
0x1800095a9  mov     edx, r14d
0x1800095ac  call    ?Get@?$CSxRefArray@VCWriterEntryArray@@VCWriterEntry@@@@QEAAJKPEAPEAVCWriterEntry@@@Z; CSxRefArray<CWriterEntryArray,CWriterEntry>::Get(ulong,CWriterEntry * *)
0x1800095b1  mov     r13, [rbp+57h+var_48]
0x1800095b5  mov     ebx, eax
0x1800095b7  mov     [rbp+57h+var_B0], eax
0x1800095ba  test    eax, eax
0x1800095bc  mov     eax, 2A65h
0x1800095c1  js      loc_1800093E5
0x1800095c7  mov     [rbp+57h+var_AC], ax
0x1800095cb  cmp     dword ptr [r13+70h], 0
0x1800095d0  jz      loc_180009712
0x1800095d6  mov     rcx, [rbp+57h+var_58]; this
0x1800095da  test    rcx, rcx
0x1800095dd  jz      short loc_1800095EC
0x1800095df  call    ?Release@CVolumeEntryMap@@QEAAKXZ; CVolumeEntryMap::Release(void)
0x1800095e4  mov     [rbp+57h+var_58], 0
0x1800095ec  mov     [rbp+57h+var_60], 0
0x1800095f3  mov     [rbp+57h+var_58+8], 0
0x1800095fb  mov     rax, [r13+78h]
0x1800095ff  test    rax, rax
0x180009602  jz      loc_18000974A
0x180009608  cmp     [rbp+57h+var_58], 0
0x18000960d  jnz     loc_180009743
0x180009613  mov     [rbp+57h+var_58], rax
0x180009617  lock inc dword ptr [rax+10h]
0x18000961b  mov     rax, [rbp+57h+var_58]
0x18000961f  mov     ecx, [rax+8]
0x180009622  mov     [rbp+57h+var_60], ecx
0x180009625  mov     [rbp+57h+var_58+8], 0
0x18000962d  mov     [rbp+57h+var_B0], 0
0x180009634  mov     eax, 2A6Dh
0x180009639  mov     [rbp+57h+var_AC], ax
0x18000963d  test    rdi, rdi
0x180009640  jz      short loc_180009652
0x180009642  mov     rcx, rdi; this
0x180009645  mov     [rbp+57h+var_B8], 0
0x18000964d  call    ?Release@CVolumeEntry@@QEAAKXZ; CVolumeEntry::Release(void)
0x180009652  lea     rdx, [rbp+57h+var_B8]
0x180009656  lea     rcx, [rbp+57h+var_60]
0x18000965a  call    ?Next@CSxIter@?$CSxRefMap@VCSxStringMap@@VCSxStringEntry@@@@QEAAJPEAPEAVCSxStringEntry@@@Z; CSxRefMap<CSxStringMap,CSxStringEntry>::CSxIter::Next(CSxStringEntry * *)
0x18000965f  mov     ebx, eax
0x180009661  mov     [rbp+57h+var_B0], eax
0x180009664  test    eax, eax
0x180009666  mov     eax, 2A70h
0x18000966b  js      loc_180009739
0x180009671  mov     [rbp+57h+var_AC], ax
0x180009675  cmp     ebx, 1
0x180009678  jz      loc_18000970E
0x18000967e  mov     rcx, cs:WPP_GLOBAL_Control
0x180009685  lea     rax, WPP_GLOBAL_Control
0x18000968c  mov     rdi, [rbp+57h+var_B8]
0x180009690  cmp     rcx, rax
0x180009693  jz      short loc_1800096B7
0x180009695  test    dword ptr [rcx+1Ch], 8000000h
0x18000969c  jz      short loc_1800096B7
0x18000969e  mov     r9, [rdi+8]
0x1800096a2  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x1800096a9  mov     rcx, [rcx+10h]
0x1800096ad  mov     edx, 0BCh
0x1800096b2  call    WPP_SF_S
0x1800096b7  xor     r8d, r8d
0x1800096ba  mov     rdx, rdi
0x1800096bd  mov     rcx, r12
0x1800096c0  call    ?Insert@?$CSxRefMap@VCVolumeOnDiskPropCacheMap@@VCVolumeOnDiskPropCacheEntry@@@@QEAAJPEAVCVolumeOnDiskPropCacheEntry@@PEAPEAV2@@Z; CSxRefMap<CVolumeOnDiskPropCacheMap,CVolumeOnDiskPropCacheEntry>::Insert(CVolumeOnDiskPropCacheEntry *,CVolumeOnDiskPropCacheEntry * *)
0x1800096c5  mov     ebx, eax
0x1800096c7  mov     [rbp+57h+var_B0], eax
0x1800096ca  test    eax, eax
0x1800096cc  mov     eax, 2A75h
0x1800096d1  js      loc_1800093E5
0x1800096d7  mov     [rbp+57h+var_AC], ax
0x1800096db  test    rdi, rdi
0x1800096de  jz      short loc_1800096F0
0x1800096e0  mov     rcx, rdi; this
0x1800096e3  mov     [rbp+57h+var_B8], 0
0x1800096eb  call    ?Release@CVolumeEntry@@QEAAKXZ; CVolumeEntry::Release(void)
0x1800096f0  lea     rdx, [rbp+57h+var_B8]
0x1800096f4  lea     rcx, [rbp+57h+var_60]
0x1800096f8  call    ?Next@CSxIter@?$CSxRefMap@VCSxStringMap@@VCSxStringEntry@@@@QEAAJPEAPEAVCSxStringEntry@@@Z; CSxRefMap<CSxStringMap,CSxStringEntry>::CSxIter::Next(CSxStringEntry * *)
0x1800096fd  mov     ebx, eax
0x1800096ff  mov     [rbp+57h+var_B0], eax
0x180009702  test    eax, eax
0x180009704  mov     eax, 2A78h
0x180009709  jmp     loc_18000966B
0x18000970e  mov     rdi, [rbp+57h+var_B8]
0x180009712  mov     eax, dword ptr [rbp+57h+var_78]
0x180009715  inc     r14d
0x180009718  jmp     loc_180009583
0x18000971d  mov     r10d, [rbp+57h+var_C0]
0x180009721  lea     r14, WPP_GLOBAL_Control
0x180009728  mov     r11d, 2A4Eh
0x18000972e  mov     eax, dword ptr [rbp+57h+var_70]
0x180009731  inc     r10d
0x180009734  jmp     loc_1800094D7
0x180009739  mov     rdi, [rbp+57h+var_B8]
0x18000973d  mov     [rbp+57h+var_AA], ax
0x180009741  jmp     short loc_1800097B4
0x180009743  mov     ebx, 8000FFFFh
0x180009748  jmp     short loc_18000974F
0x18000974a  mov     ebx, 80070057h
0x18000974f  mov     [rbp+57h+var_B0], ebx
0x180009752  mov     eax, 2A6Dh
0x180009757  jmp     loc_1800093E5
0x18000975c  mov     rsi, [rbp+57h+var_40]
0x180009760  mov     [rbp+57h+var_AA], r11w
0x180009765  jmp     short loc_1800097B4
0x180009767  test    [rbp+57h+arg_8], 1
0x18000976b  jnz     short loc_18000978E
0x18000976d  mov     r8, r12; struct CVolumeEntryMap *
0x180009770  mov     rdx, r15; struct CWriterEntryArray *
0x180009773  call    ?_AddASRCriticalVolumes@CSpp@@AEAAJPEAVCWriterEntryArray@@PEAVCVolumeEntryMap@@@Z; CSpp::_AddASRCriticalVolumes(CWriterEntryArray *,CVolumeEntryMap *)
0x180009778  mov     ebx, eax
0x18000977a  mov     [rbp+57h+var_B0], eax
0x18000977d  test    eax, eax
  ... truncated ...
```
