# SxGetAllSystemVolumes(CSxStringList * *,CSxStringList * *,CSxStringList * *,ushort const *)

- ea: `0x1800aec54`
- end: `0x1800af3c2`
- name: `?SxGetAllSystemVolumes@@YAJPEAPEAVCSxStringList@@00PEBG@Z`
- size: `1902`
- prototype: `__int64 __fastcall(struct CSxStringList **, struct CSxStringList **, struct CSxStringList **, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `25`
- tags: `loader_planting, service_task`

## callers

- `0x18003a048`

## callees

- `0x1800081d8`
- `0x18000b56c`
- `0x18000b5cc`
- `0x18000d984`
- `0x180012914`
- `0x180012958`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f660`
- `0x180090400`
- `0x180091678`
- `0x180092124`
- `0x180099764`
- `0x18009a08c`
- `0x18009a20c`
- `0x18009a24c`
- `0x18009a26c`
- `0x18009a608`
- `0x18009ae34`
- `0x1800aeb8c`
- `0x1800aec14`
- `0x1800aec54`
- `0x1800af3c8`
- `0x1800c97da`
- `0x1800c9830`

## import_xrefs

- `bcd!BcdOpenObject` at `0x1800aeee5`
- `bcd!BcdOpenObject` at `0x1800aeee5`
- `bcd!BcdCloseObject` at `0x1800af251`
- `bcd!BcdCloseObject` at `0x1800af31a`
- `bcd!BcdCloseObject` at `0x1800af251`
- `bcd!BcdCloseObject` at `0x1800af31a`
- `bcd!BcdCloseStore` at `0x1800af303`
- `bcd!BcdCloseStore` at `0x1800af303`
- `bcd!BcdEnumerateObjects` at `0x1800aee61`
- `bcd!BcdEnumerateObjects` at `0x1800aee61`
- `bcd!BcdOpenSystemStore` at `0x1800aee15`
- `bcd!BcdOpenSystemStore` at `0x1800aee15`
- `ole32!CoTaskMemFree` at `0x1800aef0a`
- `ole32!CoTaskMemFree` at `0x1800aef35`
- `ole32!CoTaskMemFree` at `0x1800aeff4`
- `ole32!CoTaskMemFree` at `0x1800af0d1`
- `ole32!CoTaskMemFree` at `0x1800af2eb`
- `ole32!CoTaskMemFree` at `0x1800af2f4`
- `ole32!CoTaskMemFree` at `0x1800af32c`
- `ole32!CoTaskMemFree` at `0x1800aef0a`
- `ole32!CoTaskMemFree` at `0x1800aef35`
- `ole32!CoTaskMemFree` at `0x1800aeff4`
- `ole32!CoTaskMemFree` at `0x1800af0d1`
- `ole32!CoTaskMemFree` at `0x1800af2eb`
- `ole32!CoTaskMemFree` at `0x1800af2f4`
- `ole32!CoTaskMemFree` at `0x1800af32c`
- `ole32!CoTaskMemRealloc` at `0x1800aee82`
- `ole32!CoTaskMemRealloc` at `0x1800aee82`

## pseudocode

```c
__int64 __fastcall SxGetAllSystemVolumes(
        struct CSxStringList **a1,
        struct CSxStringList **a2,
        struct CSxStringList **a3,
        const unsigned __int16 *a4)
{
  struct CSxStringEntry *v7; // rbx
  char *v8; // r14
  void *v9; // rsi
  __int16 v10; // ax
  unsigned int v11; // eax
  unsigned int v12; // eax
  char *v13; // rax
  __int64 v14; // rdi
  unsigned int v15; // eax
  int v16; // r15d
  int BcdElementData; // eax
  unsigned int v18; // r8d
  int DosVolumeName; // eax
  int v20; // eax
  bool v21; // sf
  int v22; // eax
  const unsigned __int16 **v23; // rdi
  unsigned __int16 v24; // dx
  unsigned __int16 v25; // dx
  const unsigned __int16 *v26; // r15
  int v27; // r14d
  int v28; // eax
  struct CSxStringList *v29; // rax
  unsigned int v30; // edi
  struct CSxStringEntry *v32; // [rsp+30h] [rbp-D0h] BYREF
  int VolumeIdentifier; // [rsp+38h] [rbp-C8h] BYREF
  __int16 v34; // [rsp+3Ch] [rbp-C4h]
  __int16 v35; // [rsp+3Eh] [rbp-C2h]
  LPVOID pv; // [rsp+70h] [rbp-90h] BYREF
  int v37; // [rsp+78h] [rbp-88h]
  void *v38; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v39; // [rsp+88h] [rbp-78h] BYREF
  char *v40; // [rsp+90h] [rbp-70h]
  unsigned __int8 *v41; // [rsp+98h] [rbp-68h] BYREF
  SIZE_T cb; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v43; // [rsp+A8h] [rbp-58h] BYREF
  struct CSxStringList *v44; // [rsp+B0h] [rbp-50h] BYREF
  struct CSxStringList *v45; // [rsp+B8h] [rbp-48h] BYREF
  struct CSxStringList *v46; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v47; // [rsp+C8h] [rbp-38h] BYREF
  CSxVolumeLocator *v48; // [rsp+D0h] [rbp-30h] BYREF
  LPCWSTR lpszVolumeName[2]; // [rsp+D8h] [rbp-28h] BYREF
  struct CSxStringList **v50; // [rsp+E8h] [rbp-18h]
  unsigned __int16 v51[264]; // [rsp+F0h] [rbp-10h] BYREF

  v50 = a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_b036215b3564316a9a5ab27768cd0679_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&VolumeIdentifier, "SxGetAllSystemVolumes", 68, 1);
  v7 = 0;
  v43 = 0;
  v8 = 0;
  v38 = 0;
  v40 = 0;
  v9 = 0;
  lpszVolumeName[0] = (LPCWSTR)qword_1800E8530;
  cb = 0;
  v39 = 0;
  v47 = 0;
  v46 = 0;
  v45 = 0;
  v44 = 0;
  lpszVolumeName[1] = 0;
  v48 = 0;
  v41 = 0;
  memset_0(v51, 0, 0x20Au);
  if ( a1 )
    *a1 = 0;
  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
  v10 = 99;
  if ( !a1 || (v34 = 99, v10 = 100, !a2) || (v34 = 100, v10 = 101, !a3) )
  {
    VolumeIdentifier = -2147024809;
LABEL_68:
    v35 = v10;
    goto LABEL_69;
  }
  VolumeIdentifier = 0;
  v34 = 101;
  VolumeIdentifier = CSxStringList::CreateInstance(&v46);
  v10 = 103;
  if ( VolumeIdentifier < 0 )
    goto LABEL_68;
  v34 = 103;
  VolumeIdentifier = CSxStringList::CreateInstance(&v45);
  v10 = 104;
  if ( VolumeIdentifier < 0 )
    goto LABEL_68;
  v34 = 104;
  VolumeIdentifier = CSxStringList::CreateInstance(&v44);
  v10 = 105;
  if ( VolumeIdentifier < 0 )
    goto LABEL_68;
  v34 = 105;
  VolumeIdentifier = CSxVolumeLocator::CreateInstance(&v48);
  v10 = 106;
  if ( VolumeIdentifier < 0 )
    goto LABEL_68;
  v34 = 106;
  v11 = BcdOpenSystemStore(&v43);
  VolumeIdentifier = HRESULTFromNTSTATUS(v11);
  v10 = 108;
  if ( VolumeIdentifier < 0 )
    goto LABEL_68;
  v34 = 108;
  while ( 1 )
  {
    v47 = 0x1020000300000001LL;
    v39 = 0;
    v12 = BcdEnumerateObjects(v43, &v47, v8, &cb, &v39);
    if ( v12 != -1073741789 && v12 != -2147483643 && v12 != -1073741820 )
      break;
    v13 = (char *)CoTaskMemRealloc(v8, (unsigned int)cb);
    if ( !v13 )
    {
      VolumeIdentifier = -2147024882;
      v35 = 132;
      goto LABEL_69;
    }
    VolumeIdentifier = 0;
    v8 = v13;
    v34 = 132;
    v40 = v13;
  }
  VolumeIdentifier = HRESULTFromNTSTATUS(v12);
  v10 = 135;
  if ( VolumeIdentifier < 0 )
    goto LABEL_68;
  v34 = 135;
  v14 = 0;
  while ( 1 )
  {
    v37 = v14;
    if ( (unsigned int)v14 >= v39 )
      break;
    v15 = BcdOpenObject(v43, &v8[24 * v14], &v38);
    VolumeIdentifier = HRESULTFromNTSTATUS(v15);
    if ( VolumeIdentifier < 0 )
    {
      v35 = 140;
      goto LABEL_69;
    }
    v34 = 140;
    v16 = 0;
    CoTaskMemFree(v9);
    pv = 0;
    if ( (int)SxGetBcdElementData(v38, 0x46000010u, &pv) >= 0 )
      v16 = *(unsigned __int8 *)pv;
    CoTaskMemFree(pv);
    pv = 0;
    BcdElementData = SxGetBcdElementData(v38, 0x21000001u, &pv);
    v9 = pv;
    if ( BcdElementData >= 0 && *(_DWORD *)pv == 2 )
    {
      VolumeIdentifier = CBsString::Set(
                           (CBsString *)lpszVolumeName,
                           L"\\\\?\\GLOBALROOT",
                           (const unsigned __int16 *)pv + 10,
                           L"\\");
      v10 = 169;
      if ( VolumeIdentifier < 0 )
        goto LABEL_68;
      v34 = 169;
      VolumeIdentifier = SxGetVolumeIdentifier(lpszVolumeName[0], &v41, (unsigned int *)&cb + 1);
      v10 = 170;
      if ( VolumeIdentifier < 0 )
        goto LABEL_68;
      v34 = 170;
      VolumeIdentifier = CSxVolumeLocator::FindVolumeById(v48, v41, HIDWORD(cb), (struct CBsString *)lpszVolumeName);
      v10 = 172;
      if ( VolumeIdentifier < 0 )
        goto LABEL_68;
      v34 = 172;
      CoTaskMemFree(v41);
      v41 = 0;
      DosVolumeName = SxGetDosVolumeName(lpszVolumeName[0], v51, v18);
      VolumeIdentifier = DosVolumeName;
      if ( DosVolumeName < 0 )
      {
        v10 = 184;
        goto LABEL_68;
      }
      v34 = 184;
      if ( !DosVolumeName )
      {
        v32 = 0;
        v20 = CSxStringEntry::CreateInstance(&v32);
        v7 = v32;
        v21 = v20 < 0;
        VolumeIdentifier = v20;
        v10 = 191;
        if ( v21 )
          goto LABEL_68;
        v34 = 191;
        VolumeIdentifier = CBsString::Set((struct CSxStringEntry *)((char *)v32 + 8), v51);
        v10 = 193;
        if ( VolumeIdentifier < 0 )
          goto LABEL_68;
        v34 = 193;
        VolumeIdentifier = CSxList<CSxExtensionSetList,CSxExtensionSet>::InsertTail(v46, v7);
        v10 = 194;
        if ( VolumeIdentifier < 0 )
          goto LABEL_68;
        v34 = 194;
        if ( v7 )
          CSxStringEntry::Release(v7);
        v32 = 0;
        VolumeIdentifier = CSxStringEntry::CreateInstance(&v32);
        v10 = 197;
        if ( VolumeIdentifier < 0 )
        {
          v7 = v32;
          goto LABEL_68;
        }
        v34 = 197;
        CoTaskMemFree(v9);
        pv = 0;
        v22 = SxGetBcdElementData(v38, 0x22000002u, &pv);
        v7 = v32;
        v21 = v22 < 0;
        VolumeIdentifier = v22;
        v10 = 201;
        if ( v21
          || (v23 = (const unsigned __int16 **)((char *)v32 + 8),
              v34 = 201,
              VolumeIdentifier = CBsString::Set((struct CSxStringEntry *)((char *)v32 + 8), v51),
              v10 = 203,
              VolumeIdentifier < 0) )
        {
          v9 = pv;
          goto LABEL_68;
        }
        v34 = 203;
        CBsString::UnTrailing((struct CSxStringEntry *)((char *)v7 + 8), v24);
        v9 = pv;
        VolumeIdentifier = CBsString::Append((struct CSxStringEntry *)((char *)v7 + 8), (const unsigned __int16 *)pv);
        v10 = 205;
        if ( VolumeIdentifier < 0 )
          goto LABEL_68;
        v34 = 205;
        CBsString::UnTrailing((struct CSxStringEntry *)((char *)v7 + 8), v25);
        VolumeIdentifier = CSxList<CSxExtensionSetList,CSxExtensionSet>::InsertTail(v45, v7);
        v10 = 207;
        if ( VolumeIdentifier < 0 )
          goto LABEL_68;
        v34 = 207;
        if ( v16 )
        {
          v26 = *v23;
          v27 = CBsString::ReverseFind((struct CSxStringEntry *)((char *)v7 + 8), 0x5Cu);
          if ( v27 != -1 )
          {
            if ( v7 )
              CSxStringEntry::Release(v7);
            v32 = 0;
            v28 = CSxStringEntry::CreateInstance(&v32);
            v7 = v32;
            v21 = v28 < 0;
            VolumeIdentifier = v28;
            v10 = 229;
            if ( v21
              || (v34 = 229,
                  VolumeIdentifier = CBsString::Set((struct CSxStringEntry *)((char *)v32 + 8), v26, v27 + 1),
                  v10 = 230,
                  VolumeIdentifier < 0)
              || (v34 = 230,
                  VolumeIdentifier = CBsString::Append((struct CSxStringEntry *)((char *)v7 + 8), L"sources"),
                  v10 = 231,
                  VolumeIdentifier < 0) )
            {
              v8 = v40;
              goto LABEL_68;
            }
            v34 = 231;
            CSxList<CSxExtensionSetList,CSxExtensionSet>::InsertTail(v44, v7);
          }
          v8 = v40;
        }
        LODWORD(v14) = v37;
      }
    }
    if ( v7 )
      CSxStringEntry::Release(v7);
    v7 = 0;
    BcdCloseObject(v38);
    v14 = (unsigned int)(v14 + 1);
    v38 = 0;
  }
  v29 = v46;
  v46 = 0;
  *v50 = v29;
  *a2 = v45;
  v45 = 0;
  *a3 = v44;
  v44 = 0;
  VolumeIdentifier = 0;
  v34 = 245;
LABEL_69:
  CoTaskMemFree(v8);
  CoTaskMemFree(v9);
  if ( v43 )
  {
    BcdCloseStore();
    v43 = 0;
  }
  if ( v38 )
  {
    BcdCloseObject(v38);
    v38 = 0;
  }
  CoTaskMemFree(v41);
  v41 = 0;
  v30 = VolumeIdentifier;
  if ( v48 )
    CSxVolumeLocator::Release(v48);
  CBsString::_Release((CBsString *)lpszVolumeName);
  if ( v44 )
    CSxStringList::Release(v44);
  if ( v45 )
    CSxStringList::Release(v45);
  if ( v46 )
    CSxStringList::Release(v46);
  if ( v7 )
    CSxStringEntry::Release(v7);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&VolumeIdentifier);
  return v30;
}

```

## disassembly

```asm
0x1800aec54  mov     [rsp-8+arg_18], rbx
0x1800aec59  push    rbp
0x1800aec5a  push    rsi
0x1800aec5b  push    rdi
0x1800aec5c  push    r12
0x1800aec5e  push    r13
0x1800aec60  push    r14
0x1800aec62  push    r15
0x1800aec64  lea     rbp, [rsp-210h]
0x1800aec6c  sub     rsp, 310h
0x1800aec73  mov     rax, cs:__security_cookie
0x1800aec7a  xor     rax, rsp
0x1800aec7d  mov     [rbp+240h+var_40], rax
0x1800aec84  mov     r13, r8
0x1800aec87  mov     [rbp+240h+var_258], rcx
0x1800aec8b  mov     r12, rdx
0x1800aec8e  mov     rdi, rcx
0x1800aec91  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aec98  lea     rax, WPP_GLOBAL_Control
0x1800aec9f  cmp     rcx, rax
0x1800aeca2  jz      short loc_1800AECC2
0x1800aeca4  test    dword ptr [rcx+1Ch], 20000000h
0x1800aecab  jz      short loc_1800AECC2
0x1800aecad  mov     rcx, [rcx+10h]
0x1800aecb1  lea     r8, WPP_b036215b3564316a9a5ab27768cd0679_Traceguids
0x1800aecb8  mov     edx, 0Bh
0x1800aecbd  call    WPP_SF_
0x1800aecc2  mov     r15d, 1
0x1800aecc8  lea     rdx, aSxgetallsystem; "SxGetAllSystemVolumes"
0x1800aeccf  mov     r9d, r15d; unsigned __int16
0x1800aecd2  lea     rcx, [rsp+340h+var_308]; this
0x1800aecd7  lea     r8d, [r15+43h]; unsigned __int16
0x1800aecdb  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800aece0  xor     ebx, ebx
0x1800aece2  mov     [rbp+240h+var_298], 0
0x1800aecea  xor     r14d, r14d
0x1800aeced  mov     [rbp+240h+var_2C0], 0
0x1800aecf5  lea     rax, qword_1800E8530
0x1800aecfc  mov     [rbp+240h+var_2B0], r14
0x1800aed00  xor     esi, esi
0x1800aed02  mov     [rbp+240h+lpszVolumeName], rax
0x1800aed06  xor     edx, edx; Val
0x1800aed08  mov     dword ptr [rbp+240h+cb], r14d
0x1800aed0c  mov     r8d, 20Ah; Size
0x1800aed12  mov     [rbp+240h+var_2B8], r14d
0x1800aed16  lea     rcx, [rbp+240h+var_250]; void *
0x1800aed1a  mov     [rbp+240h+var_278], rsi
0x1800aed1e  mov     [rbp+240h+var_280], rbx
0x1800aed22  mov     [rbp+240h+var_288], rbx
0x1800aed26  mov     [rbp+240h+var_290], rbx
0x1800aed2a  mov     [rbp+240h+var_260], rbx
0x1800aed2e  mov     [rbp+240h+var_270], rbx
0x1800aed32  mov     [rbp+240h+var_2A8], rbx
0x1800aed36  mov     dword ptr [rbp+240h+cb+4], ebx
0x1800aed39  call    memset_0
0x1800aed3e  test    rdi, rdi
0x1800aed41  jz      short loc_1800AED46
0x1800aed43  mov     [rdi], rbx
0x1800aed46  test    r12, r12
0x1800aed49  jz      short loc_1800AED4F
0x1800aed4b  mov     [r12], rbx
0x1800aed4f  test    r13, r13
0x1800aed52  jz      short loc_1800AED58
0x1800aed54  mov     [r13+0], rbx
0x1800aed58  mov     eax, 63h ; 'c'
0x1800aed5d  test    rdi, rdi
0x1800aed60  jz      loc_1800AF2DB
0x1800aed66  mov     [rsp+340h+var_304], ax
0x1800aed6b  mov     eax, 64h ; 'd'
0x1800aed70  test    r12, r12
0x1800aed73  jz      loc_1800AF2DB
0x1800aed79  mov     [rsp+340h+var_304], ax
0x1800aed7e  mov     eax, 65h ; 'e'
0x1800aed83  test    r13, r13
0x1800aed86  jz      loc_1800AF2DB
0x1800aed8c  lea     rcx, [rbp+240h+var_280]; struct CSxStringList **
0x1800aed90  mov     [rsp+340h+var_308], ebx
0x1800aed94  mov     [rsp+340h+var_304], ax
0x1800aed99  call    ?CreateInstance@CSxStringList@@SAJPEAPEAV1@@Z; CSxStringList::CreateInstance(CSxStringList * *)
0x1800aed9e  mov     [rsp+340h+var_308], eax
0x1800aeda2  test    eax, eax
0x1800aeda4  mov     eax, 67h ; 'g'
0x1800aeda9  js      loc_1800AF2E3
0x1800aedaf  lea     rcx, [rbp+240h+var_288]; struct CSxStringList **
0x1800aedb3  mov     [rsp+340h+var_304], ax
0x1800aedb8  call    ?CreateInstance@CSxStringList@@SAJPEAPEAV1@@Z; CSxStringList::CreateInstance(CSxStringList * *)
0x1800aedbd  mov     [rsp+340h+var_308], eax
0x1800aedc1  test    eax, eax
0x1800aedc3  mov     eax, 68h ; 'h'
0x1800aedc8  js      loc_1800AF2E3
0x1800aedce  lea     rcx, [rbp+240h+var_290]; struct CSxStringList **
0x1800aedd2  mov     [rsp+340h+var_304], ax
0x1800aedd7  call    ?CreateInstance@CSxStringList@@SAJPEAPEAV1@@Z; CSxStringList::CreateInstance(CSxStringList * *)
0x1800aeddc  mov     [rsp+340h+var_308], eax
0x1800aede0  test    eax, eax
0x1800aede2  mov     eax, 69h ; 'i'
0x1800aede7  js      loc_1800AF2E3
0x1800aeded  lea     rcx, [rbp+240h+var_270]; struct CSxVolumeLocator **
0x1800aedf1  mov     [rsp+340h+var_304], ax
0x1800aedf6  call    ?CreateInstance@CSxVolumeLocator@@SAJPEAPEAV1@@Z; CSxVolumeLocator::CreateInstance(CSxVolumeLocator * *)
0x1800aedfb  mov     [rsp+340h+var_308], eax
0x1800aedff  test    eax, eax
0x1800aee01  mov     eax, 6Ah ; 'j'
0x1800aee06  js      loc_1800AF2E3
0x1800aee0c  lea     rcx, [rbp+240h+var_298]
0x1800aee10  mov     [rsp+340h+var_304], ax
0x1800aee15  call    cs:__imp_BcdOpenSystemStore
0x1800aee1b  mov     ecx, eax
0x1800aee1d  call    HRESULTFromNTSTATUS
0x1800aee22  mov     [rsp+340h+var_308], eax
0x1800aee26  test    eax, eax
0x1800aee28  mov     eax, 6Ch ; 'l'
0x1800aee2d  js      loc_1800AF2E3
0x1800aee33  mov     [rsp+340h+var_304], ax
0x1800aee38  lea     edi, [rax+18h]
0x1800aee3b  mov     rcx, [rbp+240h+var_298]
0x1800aee3f  lea     rax, [rbp+240h+var_2B8]
0x1800aee43  lea     r9, [rbp+240h+cb]
0x1800aee47  mov     [rsp+340h+var_320], rax
0x1800aee4c  mov     r8, r14
0x1800aee4f  mov     dword ptr [rbp+240h+var_278], r15d
0x1800aee53  lea     rdx, [rbp+240h+var_278]
0x1800aee57  mov     dword ptr [rbp+240h+var_278+4], 10200003h
0x1800aee5e  mov     [rbp+240h+var_2B8], ebx
0x1800aee61  call    cs:__imp_BcdEnumerateObjects
0x1800aee67  cmp     eax, 0C0000023h
0x1800aee6c  jz      short loc_1800AEE7C
0x1800aee6e  cmp     eax, 80000005h
0x1800aee73  jz      short loc_1800AEE7C
0x1800aee75  cmp     eax, 0C0000004h
0x1800aee7a  jnz     short loc_1800AEEA3
0x1800aee7c  mov     edx, dword ptr [rbp+240h+cb]; cb
0x1800aee7f  mov     rcx, r14; pv
0x1800aee82  call    cs:__imp_CoTaskMemRealloc
0x1800aee88  test    rax, rax
0x1800aee8b  jz      loc_1800AF2CC
0x1800aee91  mov     [rsp+340h+var_308], ebx
0x1800aee95  mov     r14, rax
0x1800aee98  mov     [rsp+340h+var_304], di
0x1800aee9d  mov     [rbp+240h+var_2B0], rax
0x1800aeea1  jmp     short loc_1800AEE3B
0x1800aeea3  mov     ecx, eax
0x1800aeea5  call    HRESULTFromNTSTATUS
0x1800aeeaa  mov     [rsp+340h+var_308], eax
0x1800aeeae  test    eax, eax
0x1800aeeb0  mov     eax, 87h
0x1800aeeb5  js      loc_1800AF2E3
0x1800aeebb  mov     [rsp+340h+var_304], ax
0x1800aeec0  xor     edi, edi
0x1800aeec2  mov     r15d, 8Ch
0x1800aeec8  mov     [rsp+340h+var_2C8], edi
0x1800aeecc  cmp     edi, [rbp+240h+var_2B8]
0x1800aeecf  jnb     loc_1800AF285
0x1800aeed5  lea     rcx, [rdi+rdi*2]
0x1800aeed9  lea     rdx, [r14+rcx*8]
0x1800aeedd  mov     rcx, [rbp+240h+var_298]
0x1800aeee1  lea     r8, [rbp+240h+var_2C0]
0x1800aeee5  call    cs:__imp_BcdOpenObject
0x1800aeeeb  mov     ecx, eax
0x1800aeeed  call    HRESULTFromNTSTATUS
0x1800aeef2  mov     [rsp+340h+var_308], eax
0x1800aeef6  test    eax, eax
0x1800aeef8  js      loc_1800AF27D
0x1800aeefe  mov     [rsp+340h+var_304], r15w
0x1800aef04  mov     rcx, rsi; pv
0x1800aef07  xor     r15d, r15d
0x1800aef0a  call    cs:__imp_CoTaskMemFree
0x1800aef10  mov     rcx, [rbp+240h+var_2C0]; void *
0x1800aef14  lea     r8, [rsp+340h+pv]; void **
0x1800aef19  mov     edx, 46000010h; unsigned int
0x1800aef1e  mov     [rsp+340h+pv], r15
0x1800aef23  call    ?SxGetBcdElementData@@YAJPEAXKPEAPEAX@Z; SxGetBcdElementData(void *,ulong,void * *)
0x1800aef28  mov     rcx, [rsp+340h+pv]; pv
0x1800aef2d  test    eax, eax
0x1800aef2f  js      short loc_1800AEF35
0x1800aef31  movzx   r15d, byte ptr [rcx]
0x1800aef35  call    cs:__imp_CoTaskMemFree
0x1800aef3b  mov     rcx, [rbp+240h+var_2C0]; void *
0x1800aef3f  lea     r8, [rsp+340h+pv]; void **
0x1800aef44  mov     edx, 21000001h; unsigned int
0x1800aef49  mov     [rsp+340h+pv], 0
0x1800aef52  call    ?SxGetBcdElementData@@YAJPEAXKPEAPEAX@Z; SxGetBcdElementData(void *,ulong,void * *)
0x1800aef57  mov     rsi, [rsp+340h+pv]
0x1800aef5c  test    eax, eax
0x1800aef5e  js      loc_1800AF23E
0x1800aef64  cmp     dword ptr [rsi], 2
0x1800aef67  jnz     loc_1800AF23E
0x1800aef6d  lea     r8, [rsi+14h]; unsigned __int16 *
0x1800aef71  lea     r9, Str; "\\"
0x1800aef78  lea     rdx, aGlobalroot; "\\\\?\\GLOBALROOT"
0x1800aef7f  lea     rcx, [rbp+240h+lpszVolumeName]; this
0x1800aef83  call    ?Set@CBsString@@QEAAJPEBG00@Z; CBsString::Set(ushort const *,ushort const *,ushort const *)
0x1800aef88  mov     [rsp+340h+var_308], eax
0x1800aef8c  test    eax, eax
0x1800aef8e  mov     eax, 0A9h
0x1800aef93  js      loc_1800AF2E3
0x1800aef99  mov     rcx, [rbp+240h+lpszVolumeName]; unsigned __int16 *
0x1800aef9d  lea     r8, [rbp+240h+cb+4]; unsigned int *
0x1800aefa1  lea     rdx, [rbp+240h+var_2A8]; unsigned __int8 **
0x1800aefa5  mov     [rsp+340h+var_304], ax
0x1800aefaa  call    ?SxGetVolumeIdentifier@@YAJPEBGPEAPEAEPEAK@Z; SxGetVolumeIdentifier(ushort const *,uchar * *,ulong *)
0x1800aefaf  mov     [rsp+340h+var_308], eax
0x1800aefb3  test    eax, eax
0x1800aefb5  mov     eax, 0AAh
0x1800aefba  js      loc_1800AF2E3
0x1800aefc0  mov     r8d, dword ptr [rbp+240h+cb+4]; unsigned int
0x1800aefc4  lea     r9, [rbp+240h+lpszVolumeName]; struct CBsString *
0x1800aefc8  mov     rdx, [rbp+240h+var_2A8]; unsigned __int8 *
0x1800aefcc  mov     rcx, [rbp+240h+var_270]; this
0x1800aefd0  mov     [rsp+340h+var_304], ax
0x1800aefd5  call    ?FindVolumeById@CSxVolumeLocator@@QEAAJPEAEKPEAVCBsString@@@Z; CSxVolumeLocator::FindVolumeById(uchar *,ulong,CBsString *)
0x1800aefda  mov     [rsp+340h+var_308], eax
0x1800aefde  test    eax, eax
0x1800aefe0  mov     eax, 0ACh
0x1800aefe5  js      loc_1800AF2E3
0x1800aefeb  mov     rcx, [rbp+240h+var_2A8]; pv
0x1800aefef  mov     [rsp+340h+var_304], ax
0x1800aeff4  call    cs:__imp_CoTaskMemFree
0x1800aeffa  mov     rcx, [rbp+240h+lpszVolumeName]; lpszVolumeName
0x1800aeffe  lea     rdx, [rbp+240h+var_250]; unsigned __int16 *
0x1800af002  mov     [rbp+240h+var_2A8], 0
0x1800af00a  call    ?SxGetDosVolumeName@@YAJPEBGPEAGK@Z; SxGetDosVolumeName(ushort const *,ushort *,ulong)
0x1800af00f  mov     [rsp+340h+var_308], eax
0x1800af013  test    eax, eax
0x1800af015  js      loc_1800AF276
0x1800af01b  mov     ecx, 0B8h
0x1800af020  mov     [rsp+340h+var_304], cx
0x1800af025  jnz     loc_1800AF23E
0x1800af02b  xor     edi, edi
0x1800af02d  lea     rcx, [rsp+340h+var_310]; struct CSxStringEntry **
0x1800af032  mov     [rsp+340h+var_310], rdi
0x1800af037  call    ?CreateInstance@CSxStringEntry@@SAJPEAPEAV1@@Z; CSxStringEntry::CreateInstance(CSxStringEntry * *)
0x1800af03c  mov     rbx, [rsp+340h+var_310]
0x1800af041  test    eax, eax
0x1800af043  mov     [rsp+340h+var_308], eax
0x1800af047  mov     eax, 0BFh
0x1800af04c  js      loc_1800AF2E3
0x1800af052  lea     rcx, [rbx+8]; this
0x1800af056  mov     [rsp+340h+var_304], ax
0x1800af05b  lea     rdx, [rbp+240h+var_250]; unsigned __int16 *
0x1800af05f  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x1800af064  mov     [rsp+340h+var_308], eax
0x1800af068  test    eax, eax
0x1800af06a  mov     eax, 0C1h
0x1800af06f  js      loc_1800AF2E3
0x1800af075  mov     rcx, [rbp+240h+var_280]
0x1800af079  mov     rdx, rbx
0x1800af07c  mov     [rsp+340h+var_304], ax
0x1800af081  call    ?InsertTail@?$CSxList@VCSxExtensionSetList@@VCSxExtensionSet@@@@QEAAJPEAVCSxExtensionSet@@@Z; CSxList<CSxExtensionSetList,CSxExtensionSet>::InsertTail(CSxExtensionSet *)
0x1800af086  mov     [rsp+340h+var_308], eax
0x1800af08a  test    eax, eax
0x1800af08c  mov     eax, 0C2h
0x1800af091  js      loc_1800AF2E3
0x1800af097  mov     [rsp+340h+var_304], ax
0x1800af09c  test    rbx, rbx
0x1800af09f  jz      short loc_1800AF0A9
0x1800af0a1  mov     rcx, rbx; this
0x1800af0a4  call    ?Release@CSxStringEntry@@QEAAKXZ; CSxStringEntry::Release(void)
0x1800af0a9  lea     rcx, [rsp+340h+var_310]; struct CSxStringEntry **
0x1800af0ae  mov     [rsp+340h+var_310], rdi
0x1800af0b3  call    ?CreateInstance@CSxStringEntry@@SAJPEAPEAV1@@Z; CSxStringEntry::CreateInstance(CSxStringEntry * *)
0x1800af0b8  mov     [rsp+340h+var_308], eax
0x1800af0bc  test    eax, eax
0x1800af0be  mov     eax, 0C5h
0x1800af0c3  js      loc_1800AF26F
0x1800af0c9  mov     rcx, rsi; pv
0x1800af0cc  mov     [rsp+340h+var_304], ax
0x1800af0d1  call    cs:__imp_CoTaskMemFree
0x1800af0d7  mov     rcx, [rbp+240h+var_2C0]; void *
0x1800af0db  lea     r8, [rsp+340h+pv]; void **
0x1800af0e0  mov     edx, 22000002h; unsigned int
0x1800af0e5  mov     [rsp+340h+pv], rdi
0x1800af0ea  call    ?SxGetBcdElementData@@YAJPEAXKPEAPEAX@Z; SxGetBcdElementData(void *,ulong,void * *)
0x1800af0ef  mov     rbx, [rsp+340h+var_310]
0x1800af0f4  test    eax, eax
0x1800af0f6  mov     [rsp+340h+var_308], eax
0x1800af0fa  mov     eax, 0C9h
0x1800af0ff  js      loc_1800AF268
0x1800af105  lea     rdi, [rbx+8]
0x1800af109  mov     [rsp+340h+var_304], ax
0x1800af10e  mov     rcx, rdi; this
0x1800af111  lea     rdx, [rbp+240h+var_250]; unsigned __int16 *
0x1800af115  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x1800af11a  mov     [rsp+340h+var_308], eax
0x1800af11e  test    eax, eax
0x1800af120  mov     eax, 0CBh
0x1800af125  js      loc_1800AF268
0x1800af12b  mov     rcx, rdi; this
0x1800af12e  mov     [rsp+340h+var_304], ax
0x1800af133  call    ?UnTrailing@CBsString@@QEAAXG@Z; CBsString::UnTrailing(ushort)
0x1800af138  mov     rsi, [rsp+340h+pv]
0x1800af13d  mov     rcx, rdi; this
0x1800af140  mov     rdx, rsi; unsigned __int16 *
0x1800af143  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x1800af148  mov     [rsp+340h+var_308], eax
0x1800af14c  test    eax, eax
0x1800af14e  mov     eax, 0CDh
0x1800af153  js      loc_1800AF2E3
0x1800af159  mov     rcx, rdi; this
0x1800af15c  mov     [rsp+340h+var_304], ax
  ... truncated ...
```
