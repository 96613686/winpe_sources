# CSdCommonImpl::QueryStorageDevices(ulong *,_SD_STORAGE_DEVICE_PROP * *)

- ea: `0x18004bfd0`
- end: `0x18004c4a0`
- name: `?QueryStorageDevices@CSdCommonImpl@@UEAAJPEAKPEAPEAU_SD_STORAGE_DEVICE_PROP@@@Z`
- size: `1232`
- prototype: `__int64 __fastcall(CSdCommonImpl *__hidden this, unsigned int *, struct _SD_STORAGE_DEVICE_PROP **)`
- caller_count: `0`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001233c`
- `0x18002725c`
- `0x18004962c`
- `0x18004969c`
- `0x18004a428`
- `0x18004bfd0`
- `0x18004c528`
- `0x18004c568`
- `0x180072e08`
- `0x180072f14`
- `0x180073b44`
- `0x180073ba8`
- `0x18008a874`
- `0x180095468`
- `0x18009de6c`
- `0x18009e8e4`
- `0x1800cf56a`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18004c3d1`
- `KERNEL32!LeaveCriticalSection` at `0x18004c3d1`
- `ole32!CoTaskMemFree` at `0x18004c265`
- `ole32!CoTaskMemFree` at `0x18004c412`
- `ole32!CoTaskMemFree` at `0x18004c429`
- `ole32!CoTaskMemFree` at `0x18004c265`
- `ole32!CoTaskMemFree` at `0x18004c412`
- `ole32!CoTaskMemFree` at `0x18004c429`
- `ole32!CoTaskMemAlloc` at `0x18004c0c3`
- `ole32!CoTaskMemAlloc` at `0x18004c0c3`

## string_xrefs

- `0x18004c00a`: `CSdCommonImpl::QueryStorageDevices`

## pseudocode

```c
__int64 __fastcall CSdCommonImpl::QueryStorageDevices(
        CSdCommonImpl *this,
        unsigned int *a2,
        struct _SD_STORAGE_DEVICE_PROP **a3)
{
  struct _SD_STORAGE_DEVICE_PROP *v6; // r12
  volatile signed __int32 *v7; // r14
  volatile signed __int32 *v8; // r15
  struct CSdStringIndexEntry *v9; // rsi
  __int16 v10; // ax
  __int64 v11; // rdi
  __int64 i; // rax
  const unsigned __int16 **v13; // rbx
  int IsPathUNC; // eax
  __int64 j; // rbx
  __int64 v16; // r8
  struct CSdStringIndexMap *v17; // rbx
  const unsigned __int16 *v18; // rdx
  const unsigned __int16 *v19; // r8
  __int64 v20; // r8
  CSdStringIndexMap *v21; // rcx
  CSdStringIndexMap *v22; // rcx
  __int64 k; // rbx
  unsigned int v24; // ebx
  int v26; // [rsp+28h] [rbp-59h]
  unsigned int v27; // [rsp+2Ch] [rbp-55h] BYREF
  unsigned int v28; // [rsp+30h] [rbp-51h] BYREF
  struct CSdStringIndexEntry *v29; // [rsp+38h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-41h] BYREF
  int AllVolumeNames; // [rsp+48h] [rbp-39h] BYREF
  __int16 v32; // [rsp+4Ch] [rbp-35h]
  __int16 v33; // [rsp+4Eh] [rbp-33h]
  struct _SD_STORAGE_DEVICE_PROP *v34; // [rsp+80h] [rbp-1h] BYREF
  struct CSdStringIndexMap *v35; // [rsp+88h] [rbp+7h] BYREF
  struct CSdStringIndexMap *v36; // [rsp+90h] [rbp+Fh] BYREF
  struct _SD_STORAGE_DEVICE_PROP *v37; // [rsp+98h] [rbp+17h] BYREF
  unsigned int v40; // [rsp+100h] [rbp+7Fh] BYREF

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&AllVolumeNames,
    "CSdCommonImpl::QueryStorageDevices",
    0x207u,
    1u);
  v40 = 0;
  v34 = 0;
  v28 = 0;
  v6 = 0;
  v37 = 0;
  v7 = 0;
  v36 = 0;
  v8 = 0;
  v35 = 0;
  v9 = 0;
  v29 = 0;
  pv = 0;
  v27 = 0;
  if ( a3 )
    *a3 = 0;
  if ( a2 )
    *a2 = 0;
  v10 = 539;
  if ( !a3 || (v32 = 539, v10 = 540, !a2) )
  {
    AllVolumeNames = -2147024809;
LABEL_7:
    v33 = v10;
    goto LABEL_52;
  }
  AllVolumeNames = 0;
  v32 = 540;
  AllVolumeNames = QueryStorageDevices(&v40, &v34);
  v10 = 542;
  if ( AllVolumeNames < 0 )
    goto LABEL_7;
  v32 = 542;
  v11 = v40;
  if ( v40 )
  {
    v6 = (struct _SD_STORAGE_DEVICE_PROP *)CoTaskMemAlloc(144LL * v40);
    v37 = v6;
    v10 = 549;
    if ( !v6 )
    {
      AllVolumeNames = -2147024882;
      goto LABEL_7;
    }
    AllVolumeNames = 0;
    v32 = 549;
    memset_0(v6, 0, 144 * v11);
    v28 = v11;
    AllVolumeNames = CSdStringIndexMap::CreateInstance(&v36);
    if ( AllVolumeNames < 0 )
    {
      v33 = 556;
      v7 = (volatile signed __int32 *)v36;
      goto LABEL_52;
    }
    v32 = 556;
    AllVolumeNames = CSdStringIndexMap::CreateInstance(&v35);
    v7 = (volatile signed __int32 *)v36;
    v8 = (volatile signed __int32 *)v35;
    v10 = 557;
    if ( AllVolumeNames < 0 )
      goto LABEL_7;
    v32 = 557;
    for ( i = 0; ; i = (unsigned int)(v26 + 1) )
    {
      v26 = i;
      if ( (unsigned int)i >= (unsigned int)v11 )
        break;
      v13 = (const unsigned __int16 **)((char *)v34 + 144 * i);
      v35 = (struct CSdStringIndexMap *)v13;
      AllVolumeNames = CopyStorageDeviceProp(
                         (struct _SD_STORAGE_DEVICE_PROP *)((char *)v6 + 144 * i),
                         (const struct _SD_STORAGE_DEVICE_PROP *)v13);
      v10 = 567;
      if ( AllVolumeNames < 0 )
        goto LABEL_7;
      v32 = 567;
      IsPathUNC = SdIsPathUNC(v13[1]);
      AllVolumeNames = IsPathUNC;
      if ( IsPathUNC < 0 )
      {
        v10 = 572;
        goto LABEL_7;
      }
      v32 = 572;
      if ( IsPathUNC )
      {
        AllVolumeNames = SxGetAllVolumeNames(v13[1], (unsigned __int16 ***)&pv, &v27);
        v10 = 581;
        if ( AllVolumeNames < 0 )
          goto LABEL_7;
        for ( j = 0; ; j = (unsigned int)(j + 1) )
        {
          v32 = v10;
          if ( (unsigned int)j >= v27 )
            break;
          if ( v9 )
          {
            v29 = 0;
            CSdStringIndexEntry::Release(v9);
          }
          AllVolumeNames = CSdStringIndexEntry::CreateInstance(&v29);
          v9 = v29;
          v10 = 593;
          if ( AllVolumeNames < 0 )
            goto LABEL_7;
          v32 = 593;
          AllVolumeNames = CBsString::Attach(
                             (struct CSdStringIndexEntry *)((char *)v29 + 8),
                             (unsigned __int16 **)pv + j);
          v10 = 594;
          if ( AllVolumeNames < 0 )
            goto LABEL_7;
          v32 = 594;
          *((_DWORD *)v9 + 6) = v26;
          AllVolumeNames = CSxRefMap<CSdMediaMap,CSdMedia>::Insert((__int64)(v7 + 2), (__int64)v9, v16);
          v10 = 596;
          if ( AllVolumeNames < 0 )
            goto LABEL_7;
        }
        CoTaskMemFree(pv);
        pv = 0;
        v17 = v35;
        if ( *((_DWORD *)v35 + 14) == 13 )
        {
          if ( v9 )
          {
            v29 = 0;
            CSdStringIndexEntry::Release(v9);
          }
          AllVolumeNames = CSdStringIndexEntry::CreateInstance(&v29);
          v9 = v29;
          v10 = 619;
          if ( AllVolumeNames < 0 )
            goto LABEL_7;
          v32 = 619;
          v18 = (const unsigned __int16 *)&Data;
          if ( *((_QWORD *)v17 + 3) )
            v18 = (const unsigned __int16 *)*((_QWORD *)v17 + 3);
          v19 = (const unsigned __int16 *)&Data;
          if ( *((_QWORD *)v17 + 4) )
            v19 = (const unsigned __int16 *)*((_QWORD *)v17 + 4);
          AllVolumeNames = CBsString::Set((struct CSdStringIndexEntry *)((char *)v29 + 8), v18, v19);
          v10 = 622;
          if ( AllVolumeNames < 0 )
            goto LABEL_7;
          v32 = 622;
          *((_DWORD *)v9 + 6) = v26;
          AllVolumeNames = CSxRefMap<CSdMediaMap,CSdMedia>::Insert((__int64)(v8 + 2), (__int64)v9, v20);
          v10 = 624;
          if ( AllVolumeNames < 0 )
            goto LABEL_7;
          v32 = 624;
        }
      }
    }
  }
  ATL::CComSafeDeleteCriticalSection::Lock((CSdCommonImpl *)((char *)this + 24));
  CleanupStorageDevicePropArray((unsigned int *)this + 44, (struct _SD_STORAGE_DEVICE_PROP **)this + 23);
  *((_DWORD *)this + 44) = v40;
  *((_QWORD *)this + 23) = v34;
  v40 = 0;
  v34 = 0;
  if ( v7 )
    _InterlockedIncrement(v7 + 6);
  v21 = (CSdStringIndexMap *)*((_QWORD *)this + 24);
  if ( v21 )
  {
    *((_QWORD *)this + 24) = 0;
    CSdStringIndexMap::Release(v21);
  }
  *((_QWORD *)this + 24) = v7;
  if ( v8 )
    _InterlockedIncrement(v8 + 6);
  v22 = (CSdStringIndexMap *)*((_QWORD *)this + 25);
  if ( v22 )
  {
    *((_QWORD *)this + 25) = 0;
    CSdStringIndexMap::Release(v22);
  }
  *((_QWORD *)this + 25) = v8;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  *a2 = v28;
  *a3 = v6;
  v28 = 0;
  v37 = 0;
LABEL_52:
  if ( pv )
  {
    for ( k = 0; (unsigned int)k < v27; k = (unsigned int)(k + 1) )
      CoTaskMemFree(*((LPVOID *)pv + k));
    CoTaskMemFree(pv);
  }
  CleanupStorageDevicePropArray(&v40, &v34);
  CleanupStorageDevicePropArray(&v28, &v37);
  v24 = AllVolumeNames;
  if ( v9 )
    CSdStringIndexEntry::Release(v9);
  if ( v8 )
    CSdStringIndexMap::Release((CSdStringIndexMap *)v8);
  if ( v7 )
    CSdStringIndexMap::Release((CSdStringIndexMap *)v7);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&AllVolumeNames);
  return v24;
}

```

## disassembly

```asm
0x18004bfd0  mov     rax, rsp
0x18004bfd3  mov     [rax+8], rbx
0x18004bfd7  mov     [rax+18h], r8
0x18004bfdb  mov     [rax+10h], rdx
0x18004bfdf  push    rbp
0x18004bfe0  push    rsi
0x18004bfe1  push    rdi
0x18004bfe2  push    r12
0x18004bfe4  push    r13
0x18004bfe6  push    r14
0x18004bfe8  push    r15
0x18004bfea  lea     rbp, [rax-5Fh]
0x18004bfee  sub     rsp, 0A0h
0x18004bff5  mov     rdi, r8
0x18004bff8  mov     rbx, rdx
0x18004bffb  mov     r13, rcx
0x18004bffe  mov     r9d, 1; unsigned __int16
0x18004c004  mov     r8d, 207h; unsigned __int16
0x18004c00a  lea     rdx, aCsdcommonimplQ_9; "CSdCommonImpl::QueryStorageDevices"
0x18004c011  lea     rcx, [rbp+57h+var_90]; this
0x18004c015  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18004c01a  mov     [rbp+57h+arg_18], 0
0x18004c021  mov     [rbp+57h+var_58], 0
0x18004c029  mov     [rbp+57h+var_A8], 0
0x18004c030  xor     r12d, r12d
0x18004c033  mov     [rbp+57h+var_40], r12
0x18004c037  xor     r14d, r14d
0x18004c03a  mov     [rbp+57h+var_48], r14
0x18004c03e  xor     r15d, r15d
0x18004c041  mov     [rbp+57h+var_50], r15
0x18004c045  xor     esi, esi
0x18004c047  mov     [rbp+57h+var_A0], rsi
0x18004c04b  mov     [rbp+57h+pv], rsi
0x18004c04f  mov     [rbp+57h+var_AC], esi
0x18004c052  test    rdi, rdi
0x18004c055  jz      short loc_18004C05A
0x18004c057  mov     [rdi], rsi
0x18004c05a  test    rbx, rbx
0x18004c05d  jz      short loc_18004C061
0x18004c05f  mov     [rbx], esi
0x18004c061  mov     eax, 21Bh
0x18004c066  test    rdi, rdi
0x18004c069  jnz     short loc_18004C07B
0x18004c06b  mov     [rbp+57h+var_90], 80070057h
0x18004c072  mov     [rbp+57h+var_8A], ax
0x18004c076  jmp     loc_18004C3FC
0x18004c07b  mov     [rbp+57h+var_8C], ax
0x18004c07f  mov     eax, 21Ch
0x18004c084  test    rbx, rbx
0x18004c087  jz      short loc_18004C06B
0x18004c089  mov     [rbp+57h+var_90], esi
0x18004c08c  mov     [rbp+57h+var_8C], ax
0x18004c090  lea     rdx, [rbp+57h+var_58]; struct _SD_STORAGE_DEVICE_PROP **
0x18004c094  lea     rcx, [rbp+57h+arg_18]; unsigned int *
0x18004c098  call    ?QueryStorageDevices@@YAJPEAKPEAPEAU_SD_STORAGE_DEVICE_PROP@@@Z; QueryStorageDevices(ulong *,_SD_STORAGE_DEVICE_PROP * *)
0x18004c09d  mov     [rbp+57h+var_90], eax
0x18004c0a0  test    eax, eax
0x18004c0a2  mov     eax, 21Eh
0x18004c0a7  js      short loc_18004C072
0x18004c0a9  mov     [rbp+57h+var_8C], ax
0x18004c0ad  mov     edi, [rbp+57h+arg_18]
0x18004c0b0  test    edi, edi
0x18004c0b2  jz      loc_18004C336
0x18004c0b8  lea     rbx, [rdi+rdi*8]
0x18004c0bc  shl     rbx, 4
0x18004c0c0  mov     rcx, rbx; cb
0x18004c0c3  call    cs:__imp_CoTaskMemAlloc
0x18004c0ca  nop     dword ptr [rax+rax+00h]
0x18004c0cf  mov     r12, rax
0x18004c0d2  mov     [rbp+57h+var_40], rax
0x18004c0d6  test    rax, rax
0x18004c0d9  mov     eax, 225h
0x18004c0de  jnz     short loc_18004C0E9
0x18004c0e0  mov     [rbp+57h+var_90], 8007000Eh
0x18004c0e7  jmp     short loc_18004C072
0x18004c0e9  mov     [rbp+57h+var_90], esi
0x18004c0ec  mov     [rbp+57h+var_8C], ax
0x18004c0f0  mov     r8, rbx; Size
0x18004c0f3  xor     edx, edx; Val
0x18004c0f5  mov     rcx, r12; void *
0x18004c0f8  call    memset_0
0x18004c0fd  mov     [rbp+57h+var_A8], edi
0x18004c100  lea     rcx, [rbp+57h+var_48]; struct CSdStringIndexMap **
0x18004c104  call    ?CreateInstance@CSdStringIndexMap@@SAJPEAPEAV1@@Z; CSdStringIndexMap::CreateInstance(CSdStringIndexMap * *)
0x18004c109  mov     [rbp+57h+var_90], eax
0x18004c10c  test    eax, eax
0x18004c10e  mov     eax, 22Ch
0x18004c113  jns     short loc_18004C122
0x18004c115  mov     [rbp+57h+var_8A], ax
0x18004c119  mov     r14, [rbp+57h+var_48]
0x18004c11d  jmp     loc_18004C3FC
0x18004c122  mov     [rbp+57h+var_8C], ax
0x18004c126  lea     rcx, [rbp+57h+var_50]; struct CSdStringIndexMap **
0x18004c12a  call    ?CreateInstance@CSdStringIndexMap@@SAJPEAPEAV1@@Z; CSdStringIndexMap::CreateInstance(CSdStringIndexMap * *)
0x18004c12f  mov     [rbp+57h+var_90], eax
0x18004c132  mov     r14, [rbp+57h+var_48]
0x18004c136  mov     r15, [rbp+57h+var_50]
0x18004c13a  test    eax, eax
0x18004c13c  mov     eax, 22Dh
0x18004c141  js      loc_18004C072
0x18004c147  mov     [rbp+57h+var_8C], ax
0x18004c14b  xor     eax, eax
0x18004c14d  mov     [rbp+57h+var_B0], eax
0x18004c150  cmp     eax, edi
0x18004c152  jnb     loc_18004C336
0x18004c158  lea     rcx, [rax+rax*8]
0x18004c15c  shl     rcx, 4
0x18004c160  mov     rbx, [rbp+57h+var_58]
0x18004c164  add     rbx, rcx
0x18004c167  mov     [rbp+57h+var_50], rbx
0x18004c16b  add     rcx, r12; struct _SD_STORAGE_DEVICE_PROP *
0x18004c16e  mov     rdx, rbx; struct _SD_STORAGE_DEVICE_PROP *
0x18004c171  call    ?CopyStorageDeviceProp@@YAJPEAU_SD_STORAGE_DEVICE_PROP@@PEBU1@@Z; CopyStorageDeviceProp(_SD_STORAGE_DEVICE_PROP *,_SD_STORAGE_DEVICE_PROP const *)
0x18004c176  mov     [rbp+57h+var_90], eax
0x18004c179  test    eax, eax
0x18004c17b  mov     eax, 237h
0x18004c180  js      loc_18004C072
0x18004c186  mov     [rbp+57h+var_8C], ax
0x18004c18a  mov     rcx, [rbx+8]; unsigned __int16 *
0x18004c18e  call    ?SdIsPathUNC@@YAJPEBG@Z; SdIsPathUNC(ushort const *)
0x18004c193  mov     [rbp+57h+var_90], eax
0x18004c196  test    eax, eax
0x18004c198  js      loc_18004C32C
0x18004c19e  mov     ecx, 23Ch
0x18004c1a3  mov     [rbp+57h+var_8C], cx
0x18004c1a7  jz      loc_18004C322
0x18004c1ad  lea     r8, [rbp+57h+var_AC]; unsigned int *
0x18004c1b1  lea     rdx, [rbp+57h+pv]; unsigned __int16 ***
0x18004c1b5  mov     rcx, [rbx+8]; unsigned __int16 *
0x18004c1b9  call    ?SxGetAllVolumeNames@@YAJPEBGPEAPEAPEAGPEAK@Z; SxGetAllVolumeNames(ushort const *,ushort * * *,ulong *)
0x18004c1be  mov     [rbp+57h+var_90], eax
0x18004c1c1  test    eax, eax
0x18004c1c3  mov     eax, 245h
0x18004c1c8  js      loc_18004C072
0x18004c1ce  xor     ebx, ebx
0x18004c1d0  mov     [rbp+57h+var_8C], ax
0x18004c1d4  cmp     ebx, [rbp+57h+var_AC]
0x18004c1d7  jnb     loc_18004C261
0x18004c1dd  test    rsi, rsi
0x18004c1e0  jz      short loc_18004C1F2
0x18004c1e2  mov     [rbp+57h+var_A0], 0
0x18004c1ea  mov     rcx, rsi; this
0x18004c1ed  call    ?Release@CSdStringIndexEntry@@QEAAKXZ; CSdStringIndexEntry::Release(void)
0x18004c1f2  lea     rcx, [rbp+57h+var_A0]; struct CSdStringIndexEntry **
0x18004c1f6  call    ?CreateInstance@CSdStringIndexEntry@@SAJPEAPEAV1@@Z; CSdStringIndexEntry::CreateInstance(CSdStringIndexEntry * *)
0x18004c1fb  mov     [rbp+57h+var_90], eax
0x18004c1fe  mov     rsi, [rbp+57h+var_A0]
0x18004c202  test    eax, eax
0x18004c204  mov     eax, 251h
0x18004c209  js      loc_18004C072
0x18004c20f  mov     [rbp+57h+var_8C], ax
0x18004c213  mov     rax, [rbp+57h+pv]
0x18004c217  lea     rdx, [rax+rbx*8]; unsigned __int16 **
0x18004c21b  lea     rcx, [rsi+8]; this
0x18004c21f  call    ?Attach@CBsString@@QEAAJPEAPEAG@Z; CBsString::Attach(ushort * *)
0x18004c224  mov     [rbp+57h+var_90], eax
0x18004c227  test    eax, eax
0x18004c229  mov     eax, 252h
0x18004c22e  js      loc_18004C072
0x18004c234  mov     [rbp+57h+var_8C], ax
0x18004c238  mov     eax, [rbp+57h+var_B0]
0x18004c23b  mov     [rsi+18h], eax
0x18004c23e  lea     rcx, [r14+8]
0x18004c242  mov     rdx, rsi
0x18004c245  call    ?Insert@?$CSxRefMap@VCSdMediaMap@@VCSdMedia@@@@QEAAJPEAVCSdMedia@@PEAPEAV2@@Z; CSxRefMap<CSdMediaMap,CSdMedia>::Insert(CSdMedia *,CSdMedia * *)
0x18004c24a  mov     [rbp+57h+var_90], eax
0x18004c24d  test    eax, eax
0x18004c24f  mov     eax, 254h
0x18004c254  js      loc_18004C072
0x18004c25a  inc     ebx
0x18004c25c  jmp     loc_18004C1D0
0x18004c261  mov     rcx, [rbp+57h+pv]; pv
0x18004c265  call    cs:__imp_CoTaskMemFree
0x18004c26c  nop     dword ptr [rax+rax+00h]
0x18004c271  mov     [rbp+57h+pv], 0
0x18004c279  mov     rbx, [rbp+57h+var_50]
0x18004c27d  cmp     dword ptr [rbx+38h], 0Dh
0x18004c281  jnz     loc_18004C322
0x18004c287  test    rsi, rsi
0x18004c28a  jz      short loc_18004C29C
0x18004c28c  mov     [rbp+57h+var_A0], 0
0x18004c294  mov     rcx, rsi; this
0x18004c297  call    ?Release@CSdStringIndexEntry@@QEAAKXZ; CSdStringIndexEntry::Release(void)
0x18004c29c  lea     rcx, [rbp+57h+var_A0]; struct CSdStringIndexEntry **
0x18004c2a0  call    ?CreateInstance@CSdStringIndexEntry@@SAJPEAPEAV1@@Z; CSdStringIndexEntry::CreateInstance(CSdStringIndexEntry * *)
0x18004c2a5  mov     [rbp+57h+var_90], eax
0x18004c2a8  mov     rsi, [rbp+57h+var_A0]
0x18004c2ac  test    eax, eax
0x18004c2ae  mov     eax, 26Bh
0x18004c2b3  js      loc_18004C072
0x18004c2b9  mov     [rbp+57h+var_8C], ax
0x18004c2bd  lea     rdx, Data
0x18004c2c4  cmp     qword ptr [rbx+18h], 0
0x18004c2c9  cmovnz  rdx, [rbx+18h]; unsigned __int16 *
0x18004c2ce  lea     r8, Data
0x18004c2d5  cmp     qword ptr [rbx+20h], 0
0x18004c2da  cmovnz  r8, [rbx+20h]; unsigned __int16 *
0x18004c2df  lea     rcx, [rsi+8]; this
0x18004c2e3  call    ?Set@CBsString@@QEAAJPEBG0@Z; CBsString::Set(ushort const *,ushort const *)
0x18004c2e8  mov     [rbp+57h+var_90], eax
0x18004c2eb  test    eax, eax
0x18004c2ed  mov     eax, 26Eh
0x18004c2f2  js      loc_18004C072
0x18004c2f8  mov     [rbp+57h+var_8C], ax
0x18004c2fc  mov     eax, [rbp+57h+var_B0]
0x18004c2ff  mov     [rsi+18h], eax
0x18004c302  lea     rcx, [r15+8]
0x18004c306  mov     rdx, rsi
0x18004c309  call    ?Insert@?$CSxRefMap@VCSdMediaMap@@VCSdMedia@@@@QEAAJPEAVCSdMedia@@PEAPEAV2@@Z; CSxRefMap<CSdMediaMap,CSdMedia>::Insert(CSdMedia *,CSdMedia * *)
0x18004c30e  mov     [rbp+57h+var_90], eax
0x18004c311  test    eax, eax
0x18004c313  mov     eax, 270h
0x18004c318  js      loc_18004C072
0x18004c31e  mov     [rbp+57h+var_8C], ax
0x18004c322  mov     eax, [rbp+57h+var_B0]
0x18004c325  inc     eax
0x18004c327  jmp     loc_18004C14D
0x18004c32c  mov     eax, 23Ch
0x18004c331  jmp     loc_18004C072
0x18004c336  lea     rcx, [r13+18h]; this
0x18004c33a  call    ?Lock@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Lock(void)
0x18004c33f  lea     rdi, [r13+0B8h]
0x18004c346  lea     rbx, [r13+0B0h]
0x18004c34d  mov     rdx, rdi; struct _SD_STORAGE_DEVICE_PROP **
0x18004c350  mov     rcx, rbx; unsigned int *
0x18004c353  call    ?CleanupStorageDevicePropArray@@YAXPEAKPEAPEAU_SD_STORAGE_DEVICE_PROP@@@Z; CleanupStorageDevicePropArray(ulong *,_SD_STORAGE_DEVICE_PROP * *)
0x18004c358  mov     eax, [rbp+57h+arg_18]
0x18004c35b  mov     [rbx], eax
0x18004c35d  mov     rax, [rbp+57h+var_58]
0x18004c361  mov     [rdi], rax
0x18004c364  mov     [rbp+57h+arg_18], 0
0x18004c36b  mov     [rbp+57h+var_58], 0
0x18004c373  test    r14, r14
0x18004c376  jz      short loc_18004C37D
0x18004c378  lock inc dword ptr [r14+18h]
0x18004c37d  mov     rcx, [r13+0C0h]; this
0x18004c384  test    rcx, rcx
0x18004c387  jz      short loc_18004C399
0x18004c389  mov     qword ptr [r13+0C0h], 0
0x18004c394  call    ?Release@CSdStringIndexMap@@QEAAKXZ; CSdStringIndexMap::Release(void)
0x18004c399  mov     [r13+0C0h], r14
0x18004c3a0  test    r15, r15
0x18004c3a3  jz      short loc_18004C3AA
0x18004c3a5  lock inc dword ptr [r15+18h]
0x18004c3aa  mov     rcx, [r13+0C8h]; this
0x18004c3b1  test    rcx, rcx
0x18004c3b4  jz      short loc_18004C3C6
0x18004c3b6  mov     qword ptr [r13+0C8h], 0
0x18004c3c1  call    ?Release@CSdStringIndexMap@@QEAAKXZ; CSdStringIndexMap::Release(void)
0x18004c3c6  mov     [r13+0C8h], r15
0x18004c3cd  lea     rcx, [r13+18h]; lpCriticalSection
0x18004c3d1  call    cs:__imp_LeaveCriticalSection
0x18004c3d8  nop     dword ptr [rax+rax+00h]
0x18004c3dd  mov     rax, [rbp+57h+arg_8]
0x18004c3e1  mov     ecx, [rbp+57h+var_A8]
0x18004c3e4  mov     [rax], ecx
0x18004c3e6  mov     rax, [rbp+57h+arg_10]
0x18004c3ea  mov     [rax], r12
0x18004c3ed  mov     [rbp+57h+var_A8], 0
0x18004c3f4  mov     [rbp+57h+var_40], 0
0x18004c3fc  cmp     [rbp+57h+pv], 0
0x18004c401  jz      short loc_18004C435
0x18004c403  xor     ebx, ebx
0x18004c405  cmp     [rbp+57h+var_AC], ebx
0x18004c408  jbe     short loc_18004C425
0x18004c40a  mov     rcx, [rbp+57h+pv]
0x18004c40e  mov     rcx, [rcx+rbx*8]; pv
0x18004c412  call    cs:__imp_CoTaskMemFree
0x18004c419  nop     dword ptr [rax+rax+00h]
0x18004c41e  inc     ebx
0x18004c420  cmp     ebx, [rbp+57h+var_AC]
0x18004c423  jb      short loc_18004C40A
0x18004c425  mov     rcx, [rbp+57h+pv]; pv
0x18004c429  call    cs:__imp_CoTaskMemFree
0x18004c430  nop     dword ptr [rax+rax+00h]
0x18004c435  lea     rdx, [rbp+57h+var_58]; struct _SD_STORAGE_DEVICE_PROP **
0x18004c439  lea     rcx, [rbp+57h+arg_18]; unsigned int *
0x18004c43d  call    ?CleanupStorageDevicePropArray@@YAXPEAKPEAPEAU_SD_STORAGE_DEVICE_PROP@@@Z; CleanupStorageDevicePropArray(ulong *,_SD_STORAGE_DEVICE_PROP * *)
0x18004c442  lea     rdx, [rbp+57h+var_40]; struct _SD_STORAGE_DEVICE_PROP **
0x18004c446  lea     rcx, [rbp+57h+var_A8]; unsigned int *
0x18004c44a  call    ?CleanupStorageDevicePropArray@@YAXPEAKPEAPEAU_SD_STORAGE_DEVICE_PROP@@@Z; CleanupStorageDevicePropArray(ulong *,_SD_STORAGE_DEVICE_PROP * *)
0x18004c44f  mov     ebx, [rbp+57h+var_90]
0x18004c452  test    rsi, rsi
0x18004c455  jz      short loc_18004C45F
0x18004c457  mov     rcx, rsi; this
0x18004c45a  call    ?Release@CSdStringIndexEntry@@QEAAKXZ; CSdStringIndexEntry::Release(void)
0x18004c45f  test    r15, r15
0x18004c462  jz      short loc_18004C46C
0x18004c464  mov     rcx, r15; this
0x18004c467  call    ?Release@CSdStringIndexMap@@QEAAKXZ; CSdStringIndexMap::Release(void)
0x18004c46c  test    r14, r14
0x18004c46f  jz      short loc_18004C479
0x18004c471  mov     rcx, r14; this
0x18004c474  call    ?Release@CSdStringIndexMap@@QEAAKXZ; CSdStringIndexMap::Release(void)
0x18004c479  lea     rcx, [rbp+57h+var_90]; this
0x18004c47d  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18004c482  mov     eax, ebx
0x18004c484  mov     rbx, [rsp+0D0h+arg_0]
0x18004c48c  add     rsp, 0A0h
0x18004c493  pop     r15
  ... truncated ...
```
