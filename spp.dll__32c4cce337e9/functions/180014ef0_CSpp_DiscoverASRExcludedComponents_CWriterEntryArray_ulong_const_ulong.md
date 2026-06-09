# CSpp::_DiscoverASRExcludedComponents(CWriterEntryArray *,ulong const *,ulong)

- ea: `0x180014ef0`
- end: `0x180015495`
- name: `?_DiscoverASRExcludedComponents@CSpp@@AEAAJPEAVCWriterEntryArray@@PEBKK@Z`
- size: `1445`
- prototype: `__int64 __fastcall(CSpp *__hidden this, struct CWriterEntryArray *, const unsigned int *, unsigned int)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180010e68`

## callees

- `0x1800074e4`
- `0x180007650`
- `0x180008c74`
- `0x18000907c`
- `0x18000c804`
- `0x18000cc50`
- `0x18000e080`
- `0x18000e308`
- `0x18000e48c`
- `0x18000e54c`
- `0x180014ef0`
- `0x180020710`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002aad4`
- `0x1800352ec`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18001529f`
- `msvcrt!_wcsnicmp` at `0x18001529f`
- `msvcrt!wcstoul` at `0x1800152bb`
- `msvcrt!wcstoul` at `0x1800152bb`

## string_xrefs

- `0x180014f50`: `CSpp::_DiscoverASRExcludedComponents`

## pseudocode

```c
__int64 __fastcall CSpp::_DiscoverASRExcludedComponents(
        CSpp *this,
        struct CWriterEntryArray *a2,
        const unsigned int *a3,
        unsigned int a4)
{
  __int64 v5; // rdx
  __int64 v6; // r8
  CWriterEntry *v7; // r15
  CWriterEntry *v8; // rbx
  __int64 v9; // rsi
  CVolumeEntryMap *v10; // r12
  struct CVolumeEntry *v11; // r14
  unsigned int v12; // edi
  int v13; // eax
  __int16 i; // ax
  int v15; // eax
  __int16 v16; // r10
  unsigned int v17; // edi
  unsigned int v18; // eax
  int v19; // eax
  __int64 v20; // rax
  int v21; // eax
  bool v22; // sf
  int v23; // eax
  int v24; // eax
  __int16 v25; // ax
  unsigned int v26; // r12d
  unsigned int v27; // r13d
  int v28; // eax
  __int64 v29; // rdi
  unsigned int v30; // eax
  unsigned int j; // ecx
  int v32; // eax
  int v33; // eax
  CVolumeEntry *v34; // rcx
  int v35; // eax
  const unsigned __int16 *v36; // rcx
  int IsVolumeOnSharedDiskAndOnline; // eax
  unsigned int v38; // edi
  struct CVolumeEntryMap *v40; // [rsp+28h] [rbp-69h] BYREF
  struct CVolumeEntry *v41; // [rsp+30h] [rbp-61h] BYREF
  __int64 v42; // [rsp+38h] [rbp-59h] BYREF
  int v43; // [rsp+40h] [rbp-51h] BYREF
  __int16 v44; // [rsp+44h] [rbp-4Dh]
  __int16 v45; // [rsp+46h] [rbp-4Bh]
  __int64 v46; // [rsp+78h] [rbp-19h] BYREF
  int v47; // [rsp+80h] [rbp-11h] BYREF
  CVolumeEntryMap *v48[2]; // [rsp+88h] [rbp-9h]
  CVolumeEntry *v49; // [rsp+98h] [rbp+7h] BYREF
  wchar_t *EndPtr; // [rsp+A0h] [rbp+Fh] BYREF
  CSpp *v51; // [rsp+F8h] [rbp+67h] BYREF
  unsigned int v52; // [rsp+100h] [rbp+6Fh]
  const unsigned int *v53; // [rsp+108h] [rbp+77h]
  unsigned int v54; // [rsp+110h] [rbp+7Fh]

  v54 = a4;
  v53 = a3;
  v51 = this;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 135, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v43, "CSpp::_DiscoverASRExcludedComponents", 8188, 1);
  v6 = 0;
  v46 = 0;
  v7 = 0;
  v42 = 0;
  v8 = 0;
  v40 = 0;
  v9 = 0;
  v47 = 0;
  v10 = 0;
  v41 = 0;
  v11 = 0;
  v49 = 0;
  EndPtr = 0;
  *(_OWORD *)v48 = 0;
  if ( a2 )
  {
    v12 = *((_DWORD *)a2 + 2);
    v52 = v12;
    v43 = 0;
    v44 = 8207;
    v13 = CVolumeEntryMap::CreateInstance(&v40);
    v6 = 0;
    v43 = v13;
    v22 = v13 < 0;
    i = 8210;
    if ( v22 )
    {
LABEL_7:
      v45 = i;
      goto LABEL_78;
    }
    v44 = 8210;
    while ( (unsigned int)v10 < v12 )
    {
      if ( v7 )
      {
        v46 = 0;
        CWriterEntry::Release(v7);
      }
      v15 = CSxRefArray<CWriterEntryArray,CWriterEntry>::Get(a2, (unsigned int)v10, &v46);
      v7 = (CWriterEntry *)v46;
      v6 = 0;
      v43 = v15;
      if ( v15 < 0 )
      {
LABEL_77:
        v45 = v16;
        goto LABEL_78;
      }
      v44 = v16;
      if ( *(_DWORD *)(v46 + 80) )
      {
        if ( *(_DWORD *)(v46 + 72) )
        {
          v25 = 8224;
LABEL_43:
          v43 = 0;
          v44 = v25;
          goto LABEL_78;
        }
        if ( v8 )
        {
          CWriterEntry::Release(v8);
          v6 = 0;
        }
        v8 = v7;
        v46 = 0;
        v7 = 0;
      }
      else if ( !*(_DWORD *)(v46 + 72) && *(_DWORD *)(v46 + 76) )
      {
        v17 = 0;
        v18 = *(_DWORD *)(*(_QWORD *)(v46 + 64) + 8LL);
        LODWORD(v51) = v18;
        while ( 1 )
        {
          if ( v17 >= v18 )
          {
            v12 = v52;
            goto LABEL_41;
          }
          if ( v9 )
          {
            v42 = 0;
            CComponentEntry::Release((CComponentEntry *)v9);
          }
          v19 = CSxRefArray<CWriterEntryArray,CWriterEntry>::Get(*((_QWORD *)v7 + 8), v17, &v42);
          v9 = v42;
          v6 = 0;
          v22 = v19 < 0;
          v43 = v19;
          i = 8245;
          if ( v22 )
            goto LABEL_7;
          v44 = 8245;
          if ( !*(_DWORD *)(v42 + 104) )
          {
            if ( *(_DWORD *)(v42 + 112) )
              break;
          }
LABEL_39:
          v18 = (unsigned int)v51;
          ++v17;
        }
        if ( v48[0] )
        {
          CVolumeEntryMap::Release(v48[0]);
          v6 = 0;
          v48[0] = 0;
        }
        v47 = 0;
        v48[1] = 0;
        v20 = *(_QWORD *)(v9 + 120);
        if ( v20 )
        {
          v48[0] = *(CVolumeEntryMap **)(v9 + 120);
          _InterlockedIncrement((volatile signed __int32 *)(v20 + 16));
          v47 = *((_DWORD *)v48[0] + 2);
          v48[1] = 0;
          v43 = 0;
          v44 = 8259;
          if ( v11 )
          {
            v41 = 0;
            CVolumeEntry::Release(v11);
          }
          v21 = CSxRefMap<CSxStringMap,CSxStringEntry>::CSxIter::Next(&v47, &v41);
          v6 = 0;
          v43 = v21;
          v22 = v21 < 0;
          for ( i = 8262; ; i = 8268 )
          {
            v11 = v41;
            if ( v22 )
              break;
            v44 = i;
            if ( v43 == 1 )
              goto LABEL_39;
            v23 = CSxRefMap<CVolumeOnDiskPropCacheMap,CVolumeOnDiskPropCacheEntry>::Insert(v40, v41, 0);
            v6 = 0;
            v43 = v23;
            v22 = v23 < 0;
            i = 8265;
            if ( v22 )
              break;
            v44 = 8265;
            if ( v11 )
            {
              v41 = 0;
              CVolumeEntry::Release(v11);
            }
            v24 = CSxRefMap<CSxStringMap,CSxStringEntry>::CSxIter::Next(&v47, &v41);
            v6 = 0;
            v43 = v24;
            v22 = v24 < 0;
          }
        }
        else
        {
          v43 = -2147024809;
          i = 8259;
        }
        goto LABEL_7;
      }
LABEL_41:
      LODWORD(v10) = (_DWORD)v10 + 1;
    }
    if ( !v8 )
    {
      v25 = 8279;
      goto LABEL_43;
    }
    v26 = 0;
    v27 = *(_DWORD *)(*((_QWORD *)v8 + 8) + 8LL);
    while ( v26 < v27 )
    {
      if ( v9 )
      {
        v42 = 0;
        CComponentEntry::Release((CComponentEntry *)v9);
      }
      v28 = CSxRefArray<CWriterEntryArray,CWriterEntry>::Get(*((_QWORD *)v8 + 8), v26, &v42);
      v9 = v42;
      v6 = 0;
      v43 = v28;
      if ( v28 < 0 )
        goto LABEL_77;
      v44 = v16;
      if ( !*(_DWORD *)(v42 + 104) && *(_DWORD *)(v42 + 92) )
      {
        if ( _wcsnicmp(*(const wchar_t **)(v42 + 8), L"harddisk", 8u) )
        {
          if ( v11 )
          {
            v41 = 0;
            CVolumeEntry::Release(v11);
          }
          v32 = CVolumeEntry::CreateInstance(&v41);
          v11 = v41;
          v6 = 0;
          v43 = v32;
          if ( v32 < 0 )
          {
            v45 = 8340;
            break;
          }
          v44 = 8340;
          v33 = CBsString::Set(
                  (struct CVolumeEntry *)((char *)v41 + 8),
                  L"\\\\?\\",
                  *(const unsigned __int16 **)(v9 + 8),
                  L"\\");
          v6 = 0;
          v43 = v33;
          v22 = v33 < 0;
          i = 8344;
          if ( v22 )
            goto LABEL_7;
          v34 = v49;
          v44 = 8344;
          if ( v49 )
          {
            v49 = 0;
            CVolumeEntry::Release(v34);
          }
          v35 = CSxRefMap<CPathCache,CPathCacheNode>::Find(v40, v11, &v49);
          v6 = 0;
          v43 = v35;
          if ( v35 < 0 )
          {
            i = 8347;
            goto LABEL_7;
          }
          v44 = 8347;
          if ( v35 == 1 )
            goto LABEL_73;
          v36 = (const unsigned __int16 *)*((_QWORD *)v11 + 1);
          LODWORD(v51) = 0;
          IsVolumeOnSharedDiskAndOnline = SxIsVolumeOnSharedDiskAndOnline(v36, (int *)&v51);
          v6 = 0;
          v43 = IsVolumeOnSharedDiskAndOnline;
          v22 = IsVolumeOnSharedDiskAndOnline < 0;
          i = 8363;
          if ( v22 )
            goto LABEL_7;
          v44 = 8363;
          if ( (_DWORD)v51 )
LABEL_73:
            *(_DWORD *)(v9 + 104) = 1;
        }
        else
        {
          v29 = *(_QWORD *)(v9 + 8);
          v30 = wcstoul((const wchar_t *)(v29 + 16), &EndPtr, 10);
          v6 = 0;
          v5 = v30;
          if ( *(_WORD *)(v29 + 16) && !*EndPtr )
          {
            for ( j = 0; j < v54; ++j )
            {
              if ( v53[j] == v30 )
              {
                *(_DWORD *)(v9 + 104) = 1;
                break;
              }
            }
            v6 = 0;
          }
        }
      }
      ++v26;
    }
LABEL_78:
    v10 = v40;
  }
  else
  {
    v43 = -2147024809;
    v45 = 8207;
  }
  v38 = v43;
  if ( v49 )
  {
    CVolumeEntry::Release(v49);
    v6 = 0;
  }
  if ( v11 )
  {
    CVolumeEntry::Release(v11);
    v6 = 0;
  }
  if ( v48[0] )
  {
    CVolumeEntryMap::Release(v48[0]);
    v6 = 0;
    v48[0] = 0;
  }
  v47 = 0;
  v48[1] = 0;
  if ( v10 )
    CVolumeEntryMap::Release(v10);
  if ( v9 )
    CComponentEntry::Release((CComponentEntry *)v9);
  if ( v8 )
    CWriterEntry::Release(v8);
  if ( v7 )
    CWriterEntry::Release(v7);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v43, v5, v6);
  return v38;
}

```

## disassembly

```asm
0x180014ef0  mov     rax, rsp
0x180014ef3  mov     [rax+20h], r9d
0x180014ef7  mov     [rax+18h], r8
0x180014efb  mov     [rax+8], rcx
0x180014eff  push    rbp
0x180014f00  push    rbx
0x180014f01  push    rsi
0x180014f02  push    rdi
0x180014f03  push    r12
0x180014f05  push    r13
0x180014f07  push    r14
0x180014f09  push    r15
0x180014f0b  lea     rbp, [rax-5Fh]
0x180014f0f  sub     rsp, 0A8h
0x180014f16  mov     r13, rdx
0x180014f19  mov     rcx, cs:WPP_GLOBAL_Control
0x180014f20  lea     rax, WPP_GLOBAL_Control
0x180014f27  cmp     rcx, rax
0x180014f2a  jz      short loc_180014F4A
0x180014f2c  test    dword ptr [rcx+1Ch], 20000000h
0x180014f33  jz      short loc_180014F4A
0x180014f35  mov     rcx, [rcx+10h]
0x180014f39  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x180014f40  mov     edx, 87h
0x180014f45  call    WPP_SF_
0x180014f4a  mov     r9d, 1; unsigned __int16
0x180014f50  lea     rdx, aCsppDiscoveras; "CSpp::_DiscoverASRExcludedComponents"
0x180014f57  mov     r8d, 1FFCh; unsigned __int16
0x180014f5d  lea     rcx, [rbp+57h+var_A8]; this
0x180014f61  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180014f66  xor     r8d, r8d
0x180014f69  xorps   xmm0, xmm0
0x180014f6c  mov     [rbp+57h+var_70], r8
0x180014f70  mov     r15d, r8d
0x180014f73  mov     [rbp+57h+var_B0], r8
0x180014f77  mov     ebx, r8d
0x180014f7a  mov     [rbp+57h+var_C0], r8
0x180014f7e  mov     esi, r8d
0x180014f81  mov     [rbp+57h+var_68], r8d
0x180014f85  mov     r12d, r8d
0x180014f88  mov     [rbp+57h+var_B8], r8
0x180014f8c  mov     r14d, r8d
0x180014f8f  mov     [rbp+57h+var_50], r8
0x180014f93  mov     eax, 200Fh
0x180014f98  mov     [rbp+57h+EndPtr], r8
0x180014f9c  movdqu  xmmword ptr [rbp+57h+var_60], xmm0
0x180014fa1  test    r13, r13
0x180014fa4  jnz     short loc_180014FB6
0x180014fa6  mov     [rbp+57h+var_A8], 80070057h
0x180014fad  mov     [rbp+57h+var_A2], ax
0x180014fb1  jmp     loc_180015401
0x180014fb6  mov     edi, [r13+8]
0x180014fba  lea     rcx, [rbp+57h+var_C0]; struct CVolumeEntryMap **
0x180014fbe  mov     [rbp+57h+arg_8], edi
0x180014fc1  mov     [rbp+57h+var_A8], r8d
0x180014fc5  mov     [rbp+57h+var_A4], ax
0x180014fc9  call    ?CreateInstance@CVolumeEntryMap@@SAJPEAPEAV1@@Z; CVolumeEntryMap::CreateInstance(CVolumeEntryMap * *)
0x180014fce  xor     r8d, r8d
0x180014fd1  mov     [rbp+57h+var_A8], eax
0x180014fd4  test    eax, eax
0x180014fd6  mov     eax, 2012h
0x180014fdb  jns     short loc_180014FE6
0x180014fdd  mov     [rbp+57h+var_A2], ax
0x180014fe1  jmp     loc_1800153FD
0x180014fe6  mov     [rbp+57h+var_A4], ax
0x180014fea  mov     r10d, 201Ah
0x180014ff0  cmp     r12d, edi
0x180014ff3  jnb     loc_180015213
0x180014ff9  test    r15, r15
0x180014ffc  jz      short loc_180015010
0x180014ffe  mov     rcx, r15; this
0x180015001  mov     [rbp+57h+var_70], r8
0x180015005  call    ?Release@CWriterEntry@@QEAAKXZ; CWriterEntry::Release(void)
0x18001500a  mov     r10d, 201Ah
0x180015010  lea     r8, [rbp+57h+var_70]
0x180015014  mov     edx, r12d
0x180015017  mov     rcx, r13
0x18001501a  call    ?Get@?$CSxRefArray@VCWriterEntryArray@@VCWriterEntry@@@@QEAAJKPEAPEAVCWriterEntry@@@Z; CSxRefArray<CWriterEntryArray,CWriterEntry>::Get(ulong,CWriterEntry * *)
0x18001501f  mov     r15, [rbp+57h+var_70]
0x180015023  xor     r8d, r8d
0x180015026  mov     [rbp+57h+var_A8], eax
0x180015029  test    eax, eax
0x18001502b  js      loc_1800153F8
0x180015031  mov     [rbp+57h+var_A4], r10w
0x180015036  cmp     [r15+50h], r8d
0x18001503a  jz      short loc_18001506B
0x18001503c  cmp     [r15+48h], r8d
0x180015040  jnz     loc_1800151E7
0x180015046  test    rbx, rbx
0x180015049  jz      short loc_18001505C
0x18001504b  mov     rcx, rbx; this
0x18001504e  call    ?Release@CWriterEntry@@QEAAKXZ; CWriterEntry::Release(void)
0x180015053  xor     r8d, r8d
0x180015056  mov     r10d, 201Ah
0x18001505c  mov     rbx, r15
0x18001505f  mov     [rbp+57h+var_70], r8
0x180015063  mov     r15, r8
0x180015066  jmp     loc_1800151DF
0x18001506b  cmp     [r15+48h], r8d
0x18001506f  jnz     loc_1800151DF
0x180015075  cmp     [r15+4Ch], r8d
0x180015079  jz      loc_1800151DF
0x18001507f  mov     rax, [r15+40h]
0x180015083  mov     edi, r8d
0x180015086  mov     eax, [rax+8]
0x180015089  mov     dword ptr [rbp+57h+arg_0], eax
0x18001508c  cmp     edi, eax
0x18001508e  jnb     loc_1800151D6
0x180015094  test    rsi, rsi
0x180015097  jz      short loc_1800150A5
0x180015099  mov     rcx, rsi; this
0x18001509c  mov     [rbp+57h+var_B0], r8
0x1800150a0  call    ?Release@CComponentEntry@@QEAAKXZ; CComponentEntry::Release(void)
0x1800150a5  mov     rcx, [r15+40h]
0x1800150a9  lea     r8, [rbp+57h+var_B0]
0x1800150ad  mov     edx, edi
0x1800150af  call    ?Get@?$CSxRefArray@VCWriterEntryArray@@VCWriterEntry@@@@QEAAJKPEAPEAVCWriterEntry@@@Z; CSxRefArray<CWriterEntryArray,CWriterEntry>::Get(ulong,CWriterEntry * *)
0x1800150b4  mov     rsi, [rbp+57h+var_B0]
0x1800150b8  xor     r8d, r8d
0x1800150bb  test    eax, eax
0x1800150bd  mov     [rbp+57h+var_A8], eax
0x1800150c0  mov     eax, 2035h
0x1800150c5  js      loc_180014FDD
0x1800150cb  mov     [rbp+57h+var_A4], ax
0x1800150cf  cmp     [rsi+68h], r8d
0x1800150d3  jnz     loc_1800151CC
0x1800150d9  cmp     [rsi+70h], r8d
0x1800150dd  jz      loc_1800151CC
0x1800150e3  mov     rcx, [rbp+57h+var_60]; this
0x1800150e7  test    rcx, rcx
0x1800150ea  jz      short loc_1800150F8
0x1800150ec  call    ?Release@CVolumeEntryMap@@QEAAKXZ; CVolumeEntryMap::Release(void)
0x1800150f1  xor     r8d, r8d
0x1800150f4  mov     [rbp+57h+var_60], r8
0x1800150f8  mov     [rbp+57h+var_68], r8d
0x1800150fc  mov     [rbp+57h+var_60+8], r8
0x180015100  mov     rax, [rsi+78h]
0x180015104  test    rax, rax
0x180015107  jz      loc_180015202
0x18001510d  cmp     [rbp+57h+var_60], r8
0x180015111  jnz     loc_1800151F9
0x180015117  mov     [rbp+57h+var_60], rax
0x18001511b  lock inc dword ptr [rax+10h]
0x18001511f  mov     rax, [rbp+57h+var_60]
0x180015123  mov     ecx, [rax+8]
0x180015126  mov     [rbp+57h+var_68], ecx
0x180015129  mov     [rbp+57h+var_60+8], r8
0x18001512d  mov     [rbp+57h+var_A8], r8d
0x180015131  mov     eax, 2043h
0x180015136  mov     [rbp+57h+var_A4], ax
0x18001513a  test    r14, r14
0x18001513d  jz      short loc_18001514B
0x18001513f  mov     rcx, r14; this
0x180015142  mov     [rbp+57h+var_B8], r8
0x180015146  call    ?Release@CVolumeEntry@@QEAAKXZ; CVolumeEntry::Release(void)
0x18001514b  lea     rdx, [rbp+57h+var_B8]
0x18001514f  lea     rcx, [rbp+57h+var_68]
0x180015153  call    ?Next@CSxIter@?$CSxRefMap@VCSxStringMap@@VCSxStringEntry@@@@QEAAJPEAPEAVCSxStringEntry@@@Z; CSxRefMap<CSxStringMap,CSxStringEntry>::CSxIter::Next(CSxStringEntry * *)
0x180015158  xor     r8d, r8d
0x18001515b  mov     [rbp+57h+var_A8], eax
0x18001515e  test    eax, eax
0x180015160  mov     eax, 2046h
0x180015165  mov     r14, [rbp+57h+var_B8]
0x180015169  js      loc_180014FDD
0x18001516f  cmp     [rbp+57h+var_A8], 1
0x180015173  mov     [rbp+57h+var_A4], ax
0x180015177  jz      short loc_1800151CC
0x180015179  mov     rcx, [rbp+57h+var_C0]
0x18001517d  xor     r8d, r8d
0x180015180  mov     rdx, r14
0x180015183  call    ?Insert@?$CSxRefMap@VCVolumeOnDiskPropCacheMap@@VCVolumeOnDiskPropCacheEntry@@@@QEAAJPEAVCVolumeOnDiskPropCacheEntry@@PEAPEAV2@@Z; CSxRefMap<CVolumeOnDiskPropCacheMap,CVolumeOnDiskPropCacheEntry>::Insert(CVolumeOnDiskPropCacheEntry *,CVolumeOnDiskPropCacheEntry * *)
0x180015188  xor     r8d, r8d
0x18001518b  mov     [rbp+57h+var_A8], eax
0x18001518e  test    eax, eax
0x180015190  mov     eax, 2049h
0x180015195  js      loc_180014FDD
0x18001519b  mov     [rbp+57h+var_A4], ax
0x18001519f  test    r14, r14
0x1800151a2  jz      short loc_1800151B0
0x1800151a4  mov     rcx, r14; this
0x1800151a7  mov     [rbp+57h+var_B8], r8
0x1800151ab  call    ?Release@CVolumeEntry@@QEAAKXZ; CVolumeEntry::Release(void)
0x1800151b0  lea     rdx, [rbp+57h+var_B8]
0x1800151b4  lea     rcx, [rbp+57h+var_68]
0x1800151b8  call    ?Next@CSxIter@?$CSxRefMap@VCSxStringMap@@VCSxStringEntry@@@@QEAAJPEAPEAVCSxStringEntry@@@Z; CSxRefMap<CSxStringMap,CSxStringEntry>::CSxIter::Next(CSxStringEntry * *)
0x1800151bd  xor     r8d, r8d
0x1800151c0  mov     [rbp+57h+var_A8], eax
0x1800151c3  test    eax, eax
0x1800151c5  mov     eax, 204Ch
0x1800151ca  jmp     short loc_180015165
0x1800151cc  mov     eax, dword ptr [rbp+57h+arg_0]
0x1800151cf  inc     edi
0x1800151d1  jmp     loc_18001508C
0x1800151d6  mov     edi, [rbp+57h+arg_8]
0x1800151d9  mov     r10d, 201Ah
0x1800151df  inc     r12d
0x1800151e2  jmp     loc_180014FF0
0x1800151e7  mov     eax, 2020h
0x1800151ec  mov     [rbp+57h+var_A8], r8d
0x1800151f0  mov     [rbp+57h+var_A4], ax
0x1800151f4  jmp     loc_1800153FD
0x1800151f9  mov     [rbp+57h+var_A8], 8000FFFFh
0x180015200  jmp     short loc_180015209
0x180015202  mov     [rbp+57h+var_A8], 80070057h
0x180015209  mov     eax, 2043h
0x18001520e  jmp     loc_180014FDD
0x180015213  test    rbx, rbx
0x180015216  jnz     short loc_18001521F
0x180015218  mov     eax, 2057h
0x18001521d  jmp     short loc_1800151EC
0x18001521f  mov     rax, [rbx+40h]
0x180015223  mov     edi, 2094h
0x180015228  mov     r12d, r8d
0x18001522b  mov     r13d, [rax+8]
0x18001522f  lea     r10d, [rdi-31h]
0x180015233  cmp     r12d, r13d
0x180015236  jnb     loc_1800153FD
0x18001523c  test    rsi, rsi
0x18001523f  jz      short loc_180015253
0x180015241  mov     rcx, rsi; this
0x180015244  mov     [rbp+57h+var_B0], r8
0x180015248  call    ?Release@CComponentEntry@@QEAAKXZ; CComponentEntry::Release(void)
0x18001524d  mov     r10d, 2063h
0x180015253  mov     rcx, [rbx+40h]
0x180015257  lea     r8, [rbp+57h+var_B0]
0x18001525b  mov     edx, r12d
0x18001525e  call    ?Get@?$CSxRefArray@VCWriterEntryArray@@VCWriterEntry@@@@QEAAJKPEAPEAVCWriterEntry@@@Z; CSxRefArray<CWriterEntryArray,CWriterEntry>::Get(ulong,CWriterEntry * *)
0x180015263  mov     rsi, [rbp+57h+var_B0]
0x180015267  xor     r8d, r8d
0x18001526a  mov     [rbp+57h+var_A8], eax
0x18001526d  test    eax, eax
0x18001526f  js      loc_1800153F8
0x180015275  mov     [rbp+57h+var_A4], r10w
0x18001527a  cmp     [rsi+68h], r8d
0x18001527e  jnz     loc_1800153E0
0x180015284  cmp     [rsi+5Ch], r8d
0x180015288  jz      loc_1800153E0
0x18001528e  mov     rcx, [rsi+8]; String1
0x180015292  lea     rdx, aHarddisk; "harddisk"
0x180015299  mov     r8d, 8; MaxCount
0x18001529f  call    cs:__imp__wcsnicmp
0x1800152a5  xor     ecx, ecx
0x1800152a7  test    eax, eax
0x1800152a9  jnz     short loc_180015306
0x1800152ab  mov     rdi, [rsi+8]
0x1800152af  lea     r8d, [rcx+0Ah]; Radix
0x1800152b3  lea     rdx, [rbp+57h+EndPtr]; EndPtr
0x1800152b7  lea     rcx, [rdi+10h]; String
0x1800152bb  call    cs:__imp_wcstoul
0x1800152c1  xor     r8d, r8d
0x1800152c4  mov     edx, eax
0x1800152c6  cmp     [rdi+10h], r8w
0x1800152cb  jz      loc_1800153D7
0x1800152d1  mov     rcx, [rbp+57h+EndPtr]
0x1800152d5  cmp     [rcx], r8w
0x1800152d9  jnz     loc_1800153D7
0x1800152df  mov     ecx, r8d
0x1800152e2  mov     r8, [rbp+57h+arg_10]
0x1800152e6  cmp     ecx, [rbp+57h+arg_18]
0x1800152e9  jnb     short loc_1800152FE
0x1800152eb  mov     eax, ecx
0x1800152ed  cmp     [r8+rax*4], edx
0x1800152f1  jz      short loc_1800152F7
0x1800152f3  inc     ecx
0x1800152f5  jmp     short loc_1800152E6
0x1800152f7  mov     dword ptr [rsi+68h], 1
0x1800152fe  xor     r8d, r8d
0x180015301  jmp     loc_1800153D7
0x180015306  test    r14, r14
0x180015309  jz      short loc_180015317
0x18001530b  mov     [rbp+57h+var_B8], rcx
0x18001530f  mov     rcx, r14; this
0x180015312  call    ?Release@CVolumeEntry@@QEAAKXZ; CVolumeEntry::Release(void)
0x180015317  lea     rcx, [rbp+57h+var_B8]; struct CVolumeEntry **
0x18001531b  call    ?CreateInstance@CVolumeEntry@@SAJPEAPEAV1@@Z; CVolumeEntry::CreateInstance(CVolumeEntry * *)
0x180015320  mov     r14, [rbp+57h+var_B8]
0x180015324  xor     r8d, r8d
0x180015327  mov     [rbp+57h+var_A8], eax
0x18001532a  test    eax, eax
0x18001532c  js      loc_1800153F2
0x180015332  mov     [rbp+57h+var_A4], di
0x180015336  lea     r9, asc_18003A0A0; "\\"
0x18001533d  mov     r8, [rsi+8]; unsigned __int16 *
0x180015341  lea     rdx, asc_18003AE20; "\\\\?\\"
0x180015348  lea     rcx, [r14+8]; this
0x18001534c  call    ?Set@CBsString@@QEAAJPEBG00@Z; CBsString::Set(ushort const *,ushort const *,ushort const *)
0x180015351  xor     r8d, r8d
0x180015354  mov     [rbp+57h+var_A8], eax
0x180015357  test    eax, eax
0x180015359  mov     eax, 2098h
0x18001535e  js      loc_180014FDD
0x180015364  mov     rcx, [rbp+57h+var_50]; this
0x180015368  mov     [rbp+57h+var_A4], ax
0x18001536c  test    rcx, rcx
0x18001536f  jz      short loc_18001537A
0x180015371  mov     [rbp+57h+var_50], r8
0x180015375  call    ?Release@CVolumeEntry@@QEAAKXZ; CVolumeEntry::Release(void)
0x18001537a  mov     rcx, [rbp+57h+var_C0]
0x18001537e  lea     r8, [rbp+57h+var_50]
0x180015382  mov     rdx, r14
  ... truncated ...
```
