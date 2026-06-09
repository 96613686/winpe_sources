# SxGetAllSystemVolumes(CSxStringList * *,CSxStringList * *,CSxStringList * *,ushort const *)

- ea: `0x1800b448c`
- end: `0x1800b4c4f`
- name: `?SxGetAllSystemVolumes@@YAJPEAPEAVCSxStringList@@00PEBG@Z`
- size: `1987`
- prototype: `__int64 __fastcall(struct CSxStringList **, struct CSxStringList **, struct CSxStringList **, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `25`
- tags: `loader_planting, service_task`

## callers

- `0x18003b664`

## callees

- `0x180008370`
- `0x18000b894`
- `0x18000b8f4`
- `0x18000de10`
- `0x18001316c`
- `0x1800131b0`
- `0x180072e08`
- `0x180072f14`
- `0x180093698`
- `0x1800944f4`
- `0x180095808`
- `0x180096308`
- `0x18009dd7c`
- `0x18009e718`
- `0x18009e8c4`
- `0x18009e904`
- `0x18009e924`
- `0x18009ece8`
- `0x18009f560`
- `0x1800b43c4`
- `0x1800b444c`
- `0x1800b448c`
- `0x1800b4c58`
- `0x1800cf56a`
- `0x1800cf5c0`

## import_xrefs

- `bcd!BcdOpenObject` at `0x1800b472f`
- `bcd!BcdOpenObject` at `0x1800b472f`
- `bcd!BcdCloseObject` at `0x1800b4ab9`
- `bcd!BcdCloseObject` at `0x1800b4b9a`
- `bcd!BcdCloseObject` at `0x1800b4ab9`
- `bcd!BcdCloseObject` at `0x1800b4b9a`
- `bcd!BcdCloseStore` at `0x1800b4b7d`
- `bcd!BcdCloseStore` at `0x1800b4b7d`
- `bcd!BcdEnumerateObjects` at `0x1800b469f`
- `bcd!BcdEnumerateObjects` at `0x1800b469f`
- `bcd!BcdOpenSystemStore` at `0x1800b464d`
- `bcd!BcdOpenSystemStore` at `0x1800b464d`
- `ole32!CoTaskMemFree` at `0x1800b475a`
- `ole32!CoTaskMemFree` at `0x1800b478b`
- `ole32!CoTaskMemFree` at `0x1800b4850`
- `ole32!CoTaskMemFree` at `0x1800b4933`
- `ole32!CoTaskMemFree` at `0x1800b4b59`
- `ole32!CoTaskMemFree` at `0x1800b4b68`
- `ole32!CoTaskMemFree` at `0x1800b4bb2`
- `ole32!CoTaskMemFree` at `0x1800b475a`
- `ole32!CoTaskMemFree` at `0x1800b478b`
- `ole32!CoTaskMemFree` at `0x1800b4850`
- `ole32!CoTaskMemFree` at `0x1800b4933`
- `ole32!CoTaskMemFree` at `0x1800b4b59`
- `ole32!CoTaskMemFree` at `0x1800b4b68`
- `ole32!CoTaskMemFree` at `0x1800b4bb2`
- `ole32!CoTaskMemRealloc` at `0x1800b46c6`
- `ole32!CoTaskMemRealloc` at `0x1800b46c6`

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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_b036215b3564316a9a5ab27768cd0679_Traceguids, a4);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&VolumeIdentifier, "SxGetAllSystemVolumes", 0x44u, 1u);
  v7 = 0;
  v43 = 0;
  v8 = 0;
  v38 = 0;
  v40 = 0;
  v9 = 0;
  lpszVolumeName[0] = (LPCWSTR)qword_1800EE510;
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
0x1800b448c  mov     [rsp-8+arg_18], rbx
0x1800b4491  push    rbp
0x1800b4492  push    rsi
0x1800b4493  push    rdi
0x1800b4494  push    r12
0x1800b4496  push    r13
0x1800b4498  push    r14
0x1800b449a  push    r15
0x1800b449c  lea     rbp, [rsp-210h]
0x1800b44a4  sub     rsp, 310h
0x1800b44ab  mov     rax, cs:__security_cookie
0x1800b44b2  xor     rax, rsp
0x1800b44b5  mov     [rbp+240h+var_40], rax
0x1800b44bc  mov     r13, r8
0x1800b44bf  mov     [rbp+240h+var_258], rcx
0x1800b44c3  mov     r12, rdx
0x1800b44c6  mov     rdi, rcx
0x1800b44c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b44d0  lea     rax, WPP_GLOBAL_Control
0x1800b44d7  cmp     rcx, rax
0x1800b44da  jz      short loc_1800B44FA
0x1800b44dc  test    dword ptr [rcx+1Ch], 20000000h
0x1800b44e3  jz      short loc_1800B44FA
0x1800b44e5  mov     rcx, [rcx+10h]
0x1800b44e9  lea     r8, WPP_b036215b3564316a9a5ab27768cd0679_Traceguids
0x1800b44f0  mov     edx, 0Bh
0x1800b44f5  call    WPP_SF_
0x1800b44fa  mov     r15d, 1
0x1800b4500  lea     rdx, aSxgetallsystem; "SxGetAllSystemVolumes"
0x1800b4507  mov     r9d, r15d; unsigned __int16
0x1800b450a  lea     rcx, [rsp+340h+var_308]; this
0x1800b450f  lea     r8d, [r15+43h]; unsigned __int16
0x1800b4513  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800b4518  xor     ebx, ebx
0x1800b451a  mov     [rbp+240h+var_298], 0
0x1800b4522  xor     r14d, r14d
0x1800b4525  mov     [rbp+240h+var_2C0], 0
0x1800b452d  lea     rax, qword_1800EE510
0x1800b4534  mov     [rbp+240h+var_2B0], r14
0x1800b4538  xor     esi, esi
0x1800b453a  mov     [rbp+240h+lpszVolumeName], rax
0x1800b453e  xor     edx, edx; Val
0x1800b4540  mov     dword ptr [rbp+240h+cb], r14d
0x1800b4544  mov     r8d, 20Ah; Size
0x1800b454a  mov     [rbp+240h+var_2B8], r14d
0x1800b454e  lea     rcx, [rbp+240h+var_250]; void *
0x1800b4552  mov     [rbp+240h+var_278], rsi
0x1800b4556  mov     [rbp+240h+var_280], rbx
0x1800b455a  mov     [rbp+240h+var_288], rbx
0x1800b455e  mov     [rbp+240h+var_290], rbx
0x1800b4562  mov     [rbp+240h+var_260], rbx
0x1800b4566  mov     [rbp+240h+var_270], rbx
0x1800b456a  mov     [rbp+240h+var_2A8], rbx
0x1800b456e  mov     dword ptr [rbp+240h+cb+4], ebx
0x1800b4571  call    memset_0
0x1800b4576  test    rdi, rdi
0x1800b4579  jz      short loc_1800B457E
0x1800b457b  mov     [rdi], rbx
0x1800b457e  test    r12, r12
0x1800b4581  jz      short loc_1800B4587
0x1800b4583  mov     [r12], rbx
0x1800b4587  test    r13, r13
0x1800b458a  jz      short loc_1800B4590
0x1800b458c  mov     [r13+0], rbx
0x1800b4590  mov     eax, 63h ; 'c'
0x1800b4595  test    rdi, rdi
0x1800b4598  jz      loc_1800B4B49
0x1800b459e  mov     [rsp+340h+var_304], ax
0x1800b45a3  mov     eax, 64h ; 'd'
0x1800b45a8  test    r12, r12
0x1800b45ab  jz      loc_1800B4B49
0x1800b45b1  mov     [rsp+340h+var_304], ax
0x1800b45b6  mov     eax, 65h ; 'e'
0x1800b45bb  test    r13, r13
0x1800b45be  jz      loc_1800B4B49
0x1800b45c4  lea     rcx, [rbp+240h+var_280]; struct CSxStringList **
0x1800b45c8  mov     [rsp+340h+var_308], ebx
0x1800b45cc  mov     [rsp+340h+var_304], ax
0x1800b45d1  call    ?CreateInstance@CSxStringList@@SAJPEAPEAV1@@Z; CSxStringList::CreateInstance(CSxStringList * *)
0x1800b45d6  mov     [rsp+340h+var_308], eax
0x1800b45da  test    eax, eax
0x1800b45dc  mov     eax, 67h ; 'g'
0x1800b45e1  js      loc_1800B4B51
0x1800b45e7  lea     rcx, [rbp+240h+var_288]; struct CSxStringList **
0x1800b45eb  mov     [rsp+340h+var_304], ax
0x1800b45f0  call    ?CreateInstance@CSxStringList@@SAJPEAPEAV1@@Z; CSxStringList::CreateInstance(CSxStringList * *)
0x1800b45f5  mov     [rsp+340h+var_308], eax
0x1800b45f9  test    eax, eax
0x1800b45fb  mov     eax, 68h ; 'h'
0x1800b4600  js      loc_1800B4B51
0x1800b4606  lea     rcx, [rbp+240h+var_290]; struct CSxStringList **
0x1800b460a  mov     [rsp+340h+var_304], ax
0x1800b460f  call    ?CreateInstance@CSxStringList@@SAJPEAPEAV1@@Z; CSxStringList::CreateInstance(CSxStringList * *)
0x1800b4614  mov     [rsp+340h+var_308], eax
0x1800b4618  test    eax, eax
0x1800b461a  mov     eax, 69h ; 'i'
0x1800b461f  js      loc_1800B4B51
0x1800b4625  lea     rcx, [rbp+240h+var_270]; struct CSxVolumeLocator **
0x1800b4629  mov     [rsp+340h+var_304], ax
0x1800b462e  call    ?CreateInstance@CSxVolumeLocator@@SAJPEAPEAV1@@Z; CSxVolumeLocator::CreateInstance(CSxVolumeLocator * *)
0x1800b4633  mov     [rsp+340h+var_308], eax
0x1800b4637  test    eax, eax
0x1800b4639  mov     eax, 6Ah ; 'j'
0x1800b463e  js      loc_1800B4B51
0x1800b4644  lea     rcx, [rbp+240h+var_298]
0x1800b4648  mov     [rsp+340h+var_304], ax
0x1800b464d  call    cs:__imp_BcdOpenSystemStore
0x1800b4654  nop     dword ptr [rax+rax+00h]
0x1800b4659  mov     ecx, eax
0x1800b465b  call    HRESULTFromNTSTATUS
0x1800b4660  mov     [rsp+340h+var_308], eax
0x1800b4664  test    eax, eax
0x1800b4666  mov     eax, 6Ch ; 'l'
0x1800b466b  js      loc_1800B4B51
0x1800b4671  mov     [rsp+340h+var_304], ax
0x1800b4676  lea     edi, [rax+18h]
0x1800b4679  mov     rcx, [rbp+240h+var_298]
0x1800b467d  lea     rax, [rbp+240h+var_2B8]
0x1800b4681  lea     r9, [rbp+240h+cb]
0x1800b4685  mov     [rsp+340h+var_320], rax
0x1800b468a  mov     r8, r14
0x1800b468d  mov     dword ptr [rbp+240h+var_278], r15d
0x1800b4691  lea     rdx, [rbp+240h+var_278]
0x1800b4695  mov     dword ptr [rbp+240h+var_278+4], 10200003h
0x1800b469c  mov     [rbp+240h+var_2B8], ebx
0x1800b469f  call    cs:__imp_BcdEnumerateObjects
0x1800b46a6  nop     dword ptr [rax+rax+00h]
0x1800b46ab  cmp     eax, 0C0000023h
0x1800b46b0  jz      short loc_1800B46C0
0x1800b46b2  cmp     eax, 80000005h
0x1800b46b7  jz      short loc_1800B46C0
0x1800b46b9  cmp     eax, 0C0000004h
0x1800b46be  jnz     short loc_1800B46ED
0x1800b46c0  mov     edx, dword ptr [rbp+240h+cb]; cb
0x1800b46c3  mov     rcx, r14; pv
0x1800b46c6  call    cs:__imp_CoTaskMemRealloc
0x1800b46cd  nop     dword ptr [rax+rax+00h]
0x1800b46d2  test    rax, rax
0x1800b46d5  jz      loc_1800B4B3A
0x1800b46db  mov     [rsp+340h+var_308], ebx
0x1800b46df  mov     r14, rax
0x1800b46e2  mov     [rsp+340h+var_304], di
0x1800b46e7  mov     [rbp+240h+var_2B0], rax
0x1800b46eb  jmp     short loc_1800B4679
0x1800b46ed  mov     ecx, eax
0x1800b46ef  call    HRESULTFromNTSTATUS
0x1800b46f4  mov     [rsp+340h+var_308], eax
0x1800b46f8  test    eax, eax
0x1800b46fa  mov     eax, 87h
0x1800b46ff  js      loc_1800B4B51
0x1800b4705  mov     [rsp+340h+var_304], ax
0x1800b470a  xor     edi, edi
0x1800b470c  mov     r15d, 8Ch
0x1800b4712  mov     [rsp+340h+var_2C8], edi
0x1800b4716  cmp     edi, [rbp+240h+var_2B8]
0x1800b4719  jnb     loc_1800B4AF3
0x1800b471f  lea     rcx, [rdi+rdi*2]
0x1800b4723  lea     rdx, [r14+rcx*8]
0x1800b4727  mov     rcx, [rbp+240h+var_298]
0x1800b472b  lea     r8, [rbp+240h+var_2C0]
0x1800b472f  call    cs:__imp_BcdOpenObject
0x1800b4736  nop     dword ptr [rax+rax+00h]
0x1800b473b  mov     ecx, eax
0x1800b473d  call    HRESULTFromNTSTATUS
0x1800b4742  mov     [rsp+340h+var_308], eax
0x1800b4746  test    eax, eax
0x1800b4748  js      loc_1800B4AEB
0x1800b474e  mov     [rsp+340h+var_304], r15w
0x1800b4754  mov     rcx, rsi; pv
0x1800b4757  xor     r15d, r15d
0x1800b475a  call    cs:__imp_CoTaskMemFree
0x1800b4761  nop     dword ptr [rax+rax+00h]
0x1800b4766  mov     rcx, [rbp+240h+var_2C0]; void *
0x1800b476a  lea     r8, [rsp+340h+pv]; void **
0x1800b476f  mov     edx, 46000010h; unsigned int
0x1800b4774  mov     [rsp+340h+pv], r15
0x1800b4779  call    ?SxGetBcdElementData@@YAJPEAXKPEAPEAX@Z; SxGetBcdElementData(void *,ulong,void * *)
0x1800b477e  mov     rcx, [rsp+340h+pv]; pv
0x1800b4783  test    eax, eax
0x1800b4785  js      short loc_1800B478B
0x1800b4787  movzx   r15d, byte ptr [rcx]
0x1800b478b  call    cs:__imp_CoTaskMemFree
0x1800b4792  nop     dword ptr [rax+rax+00h]
0x1800b4797  mov     rcx, [rbp+240h+var_2C0]; void *
0x1800b479b  lea     r8, [rsp+340h+pv]; void **
0x1800b47a0  mov     edx, 21000001h; unsigned int
0x1800b47a5  mov     [rsp+340h+pv], 0
0x1800b47ae  call    ?SxGetBcdElementData@@YAJPEAXKPEAPEAX@Z; SxGetBcdElementData(void *,ulong,void * *)
0x1800b47b3  mov     rsi, [rsp+340h+pv]
0x1800b47b8  test    eax, eax
0x1800b47ba  js      loc_1800B4AA6
0x1800b47c0  cmp     dword ptr [rsi], 2
0x1800b47c3  jnz     loc_1800B4AA6
0x1800b47c9  lea     r8, [rsi+14h]; unsigned __int16 *
0x1800b47cd  lea     r9, Str; "\\"
0x1800b47d4  lea     rdx, aGlobalroot; "\\\\?\\GLOBALROOT"
0x1800b47db  lea     rcx, [rbp+240h+lpszVolumeName]; this
0x1800b47df  call    ?Set@CBsString@@QEAAJPEBG00@Z; CBsString::Set(ushort const *,ushort const *,ushort const *)
0x1800b47e4  mov     [rsp+340h+var_308], eax
0x1800b47e8  test    eax, eax
0x1800b47ea  mov     eax, 0A9h
0x1800b47ef  js      loc_1800B4B51
0x1800b47f5  mov     rcx, [rbp+240h+lpszVolumeName]; unsigned __int16 *
0x1800b47f9  lea     r8, [rbp+240h+cb+4]; unsigned int *
0x1800b47fd  lea     rdx, [rbp+240h+var_2A8]; unsigned __int8 **
0x1800b4801  mov     [rsp+340h+var_304], ax
0x1800b4806  call    ?SxGetVolumeIdentifier@@YAJPEBGPEAPEAEPEAK@Z; SxGetVolumeIdentifier(ushort const *,uchar * *,ulong *)
0x1800b480b  mov     [rsp+340h+var_308], eax
0x1800b480f  test    eax, eax
0x1800b4811  mov     eax, 0AAh
0x1800b4816  js      loc_1800B4B51
0x1800b481c  mov     r8d, dword ptr [rbp+240h+cb+4]; unsigned int
0x1800b4820  lea     r9, [rbp+240h+lpszVolumeName]; struct CBsString *
0x1800b4824  mov     rdx, [rbp+240h+var_2A8]; unsigned __int8 *
0x1800b4828  mov     rcx, [rbp+240h+var_270]; this
0x1800b482c  mov     [rsp+340h+var_304], ax
0x1800b4831  call    ?FindVolumeById@CSxVolumeLocator@@QEAAJPEAEKPEAVCBsString@@@Z; CSxVolumeLocator::FindVolumeById(uchar *,ulong,CBsString *)
0x1800b4836  mov     [rsp+340h+var_308], eax
0x1800b483a  test    eax, eax
0x1800b483c  mov     eax, 0ACh
0x1800b4841  js      loc_1800B4B51
0x1800b4847  mov     rcx, [rbp+240h+var_2A8]; pv
0x1800b484b  mov     [rsp+340h+var_304], ax
0x1800b4850  call    cs:__imp_CoTaskMemFree
0x1800b4857  nop     dword ptr [rax+rax+00h]
0x1800b485c  mov     rcx, [rbp+240h+lpszVolumeName]; lpszVolumeName
0x1800b4860  lea     rdx, [rbp+240h+var_250]; unsigned __int16 *
0x1800b4864  mov     [rbp+240h+var_2A8], 0
0x1800b486c  call    ?SxGetDosVolumeName@@YAJPEBGPEAGK@Z; SxGetDosVolumeName(ushort const *,ushort *,ulong)
0x1800b4871  mov     [rsp+340h+var_308], eax
0x1800b4875  test    eax, eax
0x1800b4877  js      loc_1800B4AE4
0x1800b487d  mov     ecx, 0B8h
0x1800b4882  mov     [rsp+340h+var_304], cx
0x1800b4887  jnz     loc_1800B4AA6
0x1800b488d  xor     edi, edi
0x1800b488f  lea     rcx, [rsp+340h+var_310]; struct CSxStringEntry **
0x1800b4894  mov     [rsp+340h+var_310], rdi
0x1800b4899  call    ?CreateInstance@CSxStringEntry@@SAJPEAPEAV1@@Z; CSxStringEntry::CreateInstance(CSxStringEntry * *)
0x1800b489e  mov     rbx, [rsp+340h+var_310]
0x1800b48a3  test    eax, eax
0x1800b48a5  mov     [rsp+340h+var_308], eax
0x1800b48a9  mov     eax, 0BFh
0x1800b48ae  js      loc_1800B4B51
0x1800b48b4  lea     rcx, [rbx+8]; this
0x1800b48b8  mov     [rsp+340h+var_304], ax
0x1800b48bd  lea     rdx, [rbp+240h+var_250]; unsigned __int16 *
0x1800b48c1  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x1800b48c6  mov     [rsp+340h+var_308], eax
0x1800b48ca  test    eax, eax
0x1800b48cc  mov     eax, 0C1h
0x1800b48d1  js      loc_1800B4B51
0x1800b48d7  mov     rcx, [rbp+240h+var_280]
0x1800b48db  mov     rdx, rbx
0x1800b48de  mov     [rsp+340h+var_304], ax
0x1800b48e3  call    ?InsertTail@?$CSxList@VCSxExtensionSetList@@VCSxExtensionSet@@@@QEAAJPEAVCSxExtensionSet@@@Z; CSxList<CSxExtensionSetList,CSxExtensionSet>::InsertTail(CSxExtensionSet *)
0x1800b48e8  mov     [rsp+340h+var_308], eax
0x1800b48ec  test    eax, eax
0x1800b48ee  mov     eax, 0C2h
0x1800b48f3  js      loc_1800B4B51
0x1800b48f9  mov     [rsp+340h+var_304], ax
0x1800b48fe  test    rbx, rbx
0x1800b4901  jz      short loc_1800B490B
0x1800b4903  mov     rcx, rbx; this
0x1800b4906  call    ?Release@CSxStringEntry@@QEAAKXZ; CSxStringEntry::Release(void)
0x1800b490b  lea     rcx, [rsp+340h+var_310]; struct CSxStringEntry **
0x1800b4910  mov     [rsp+340h+var_310], rdi
0x1800b4915  call    ?CreateInstance@CSxStringEntry@@SAJPEAPEAV1@@Z; CSxStringEntry::CreateInstance(CSxStringEntry * *)
0x1800b491a  mov     [rsp+340h+var_308], eax
0x1800b491e  test    eax, eax
0x1800b4920  mov     eax, 0C5h
0x1800b4925  js      loc_1800B4ADD
0x1800b492b  mov     rcx, rsi; pv
0x1800b492e  mov     [rsp+340h+var_304], ax
0x1800b4933  call    cs:__imp_CoTaskMemFree
0x1800b493a  nop     dword ptr [rax+rax+00h]
0x1800b493f  mov     rcx, [rbp+240h+var_2C0]; void *
0x1800b4943  lea     r8, [rsp+340h+pv]; void **
0x1800b4948  mov     edx, 22000002h; unsigned int
0x1800b494d  mov     [rsp+340h+pv], rdi
0x1800b4952  call    ?SxGetBcdElementData@@YAJPEAXKPEAPEAX@Z; SxGetBcdElementData(void *,ulong,void * *)
0x1800b4957  mov     rbx, [rsp+340h+var_310]
0x1800b495c  test    eax, eax
0x1800b495e  mov     [rsp+340h+var_308], eax
0x1800b4962  mov     eax, 0C9h
0x1800b4967  js      loc_1800B4AD6
0x1800b496d  lea     rdi, [rbx+8]
0x1800b4971  mov     [rsp+340h+var_304], ax
0x1800b4976  mov     rcx, rdi; this
0x1800b4979  lea     rdx, [rbp+240h+var_250]; unsigned __int16 *
0x1800b497d  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x1800b4982  mov     [rsp+340h+var_308], eax
0x1800b4986  test    eax, eax
0x1800b4988  mov     eax, 0CBh
0x1800b498d  js      loc_1800B4AD6
0x1800b4993  mov     rcx, rdi; this
0x1800b4996  mov     [rsp+340h+var_304], ax
0x1800b499b  call    ?UnTrailing@CBsString@@QEAAXG@Z; CBsString::UnTrailing(ushort)
0x1800b49a0  mov     rsi, [rsp+340h+pv]
0x1800b49a5  mov     rcx, rdi; this
  ... truncated ...
```
