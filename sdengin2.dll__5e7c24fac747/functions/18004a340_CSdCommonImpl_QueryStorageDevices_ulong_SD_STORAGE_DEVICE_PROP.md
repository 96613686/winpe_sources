# CSdCommonImpl::QueryStorageDevices(ulong *,_SD_STORAGE_DEVICE_PROP * *)

- ea: `0x18004a340`
- end: `0x18004a7f1`
- name: `?QueryStorageDevices@CSdCommonImpl@@UEAAJPEAKPEAPEAU_SD_STORAGE_DEVICE_PROP@@@Z`
- size: `1201`
- prototype: `__int64 __fastcall(CSdCommonImpl *__hidden this, unsigned int *, struct _SD_STORAGE_DEVICE_PROP **)`
- caller_count: `0`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callees

- `0x180011be0`
- `0x180026288`
- `0x180047a6c`
- `0x180047ad8`
- `0x180048814`
- `0x18004a340`
- `0x18004a878`
- `0x18004a8b8`
- `0x18006fe84`
- `0x18006ff8c`
- `0x180070b28`
- `0x180070b84`
- `0x180086ef8`
- `0x18009130c`
- `0x18009984c`
- `0x18009a22c`
- `0x1800c97da`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18004a735`
- `KERNEL32!LeaveCriticalSection` at `0x18004a735`
- `ole32!CoTaskMemFree` at `0x18004a5cf`
- `ole32!CoTaskMemFree` at `0x18004a770`
- `ole32!CoTaskMemFree` at `0x18004a781`
- `ole32!CoTaskMemFree` at `0x18004a5cf`
- `ole32!CoTaskMemFree` at `0x18004a770`
- `ole32!CoTaskMemFree` at `0x18004a781`
- `ole32!CoTaskMemAlloc` at `0x18004a433`
- `ole32!CoTaskMemAlloc` at `0x18004a433`

## string_xrefs

- `0x18004a37a`: `CSdCommonImpl::QueryStorageDevices`

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
  struct CSdStringIndexMap *v16; // rbx
  const unsigned __int16 *v17; // rdx
  const unsigned __int16 *v18; // r8
  CSdStringIndexMap *v19; // rcx
  CSdStringIndexMap *v20; // rcx
  __int64 k; // rbx
  unsigned int v22; // ebx
  int v24; // [rsp+28h] [rbp-59h]
  unsigned int v25; // [rsp+2Ch] [rbp-55h] BYREF
  unsigned int v26; // [rsp+30h] [rbp-51h] BYREF
  struct CSdStringIndexEntry *v27; // [rsp+38h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-41h] BYREF
  int AllVolumeNames; // [rsp+48h] [rbp-39h] BYREF
  __int16 v30; // [rsp+4Ch] [rbp-35h]
  __int16 v31; // [rsp+4Eh] [rbp-33h]
  struct _SD_STORAGE_DEVICE_PROP *v32; // [rsp+80h] [rbp-1h] BYREF
  struct CSdStringIndexMap *v33; // [rsp+88h] [rbp+7h] BYREF
  struct CSdStringIndexMap *v34; // [rsp+90h] [rbp+Fh] BYREF
  struct _SD_STORAGE_DEVICE_PROP *v35; // [rsp+98h] [rbp+17h] BYREF
  unsigned int v38; // [rsp+100h] [rbp+7Fh] BYREF

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&AllVolumeNames,
    "CSdCommonImpl::QueryStorageDevices",
    519,
    1);
  v38 = 0;
  v32 = 0;
  v26 = 0;
  v6 = 0;
  v35 = 0;
  v7 = 0;
  v34 = 0;
  v8 = 0;
  v33 = 0;
  v9 = 0;
  v27 = 0;
  pv = 0;
  v25 = 0;
  if ( a3 )
    *a3 = 0;
  if ( a2 )
    *a2 = 0;
  v10 = 539;
  if ( !a3 || (v30 = 539, v10 = 540, !a2) )
  {
    AllVolumeNames = -2147024809;
LABEL_7:
    v31 = v10;
    goto LABEL_52;
  }
  AllVolumeNames = 0;
  v30 = 540;
  AllVolumeNames = QueryStorageDevices(&v38, &v32);
  v10 = 542;
  if ( AllVolumeNames < 0 )
    goto LABEL_7;
  v30 = 542;
  v11 = v38;
  if ( v38 )
  {
    v6 = (struct _SD_STORAGE_DEVICE_PROP *)CoTaskMemAlloc(144LL * v38);
    v35 = v6;
    v10 = 549;
    if ( !v6 )
    {
      AllVolumeNames = -2147024882;
      goto LABEL_7;
    }
    AllVolumeNames = 0;
    v30 = 549;
    memset_0(v6, 0, 144 * v11);
    v26 = v11;
    AllVolumeNames = CSdStringIndexMap::CreateInstance(&v34);
    if ( AllVolumeNames < 0 )
    {
      v31 = 556;
      v7 = (volatile signed __int32 *)v34;
      goto LABEL_52;
    }
    v30 = 556;
    AllVolumeNames = CSdStringIndexMap::CreateInstance(&v33);
    v7 = (volatile signed __int32 *)v34;
    v8 = (volatile signed __int32 *)v33;
    v10 = 557;
    if ( AllVolumeNames < 0 )
      goto LABEL_7;
    v30 = 557;
    for ( i = 0; ; i = (unsigned int)(v24 + 1) )
    {
      v24 = i;
      if ( (unsigned int)i >= (unsigned int)v11 )
        break;
      v13 = (const unsigned __int16 **)((char *)v32 + 144 * i);
      v33 = (struct CSdStringIndexMap *)v13;
      AllVolumeNames = CopyStorageDeviceProp(
                         (struct _SD_STORAGE_DEVICE_PROP *)((char *)v6 + 144 * i),
                         (const struct _SD_STORAGE_DEVICE_PROP *)v13);
      v10 = 567;
      if ( AllVolumeNames < 0 )
        goto LABEL_7;
      v30 = 567;
      IsPathUNC = SdIsPathUNC(v13[1]);
      AllVolumeNames = IsPathUNC;
      if ( IsPathUNC < 0 )
      {
        v10 = 572;
        goto LABEL_7;
      }
      v30 = 572;
      if ( IsPathUNC )
      {
        AllVolumeNames = SxGetAllVolumeNames(v13[1], (unsigned __int16 ***)&pv, &v25);
        v10 = 581;
        if ( AllVolumeNames < 0 )
          goto LABEL_7;
        for ( j = 0; ; j = (unsigned int)(j + 1) )
        {
          v30 = v10;
          if ( (unsigned int)j >= v25 )
            break;
          if ( v9 )
          {
            v27 = 0;
            CSdStringIndexEntry::Release(v9);
          }
          AllVolumeNames = CSdStringIndexEntry::CreateInstance(&v27);
          v9 = v27;
          v10 = 593;
          if ( AllVolumeNames < 0 )
            goto LABEL_7;
          v30 = 593;
          AllVolumeNames = CBsString::Attach(
                             (struct CSdStringIndexEntry *)((char *)v27 + 8),
                             (unsigned __int16 **)pv + j);
          v10 = 594;
          if ( AllVolumeNames < 0 )
            goto LABEL_7;
          v30 = 594;
          *((_DWORD *)v9 + 6) = v24;
          AllVolumeNames = CSxRefMap<CSdMediaMap,CSdMedia>::Insert(v7 + 2, v9);
          v10 = 596;
          if ( AllVolumeNames < 0 )
            goto LABEL_7;
        }
        CoTaskMemFree(pv);
        pv = 0;
        v16 = v33;
        if ( *((_DWORD *)v33 + 14) == 13 )
        {
          if ( v9 )
          {
            v27 = 0;
            CSdStringIndexEntry::Release(v9);
          }
          AllVolumeNames = CSdStringIndexEntry::CreateInstance(&v27);
          v9 = v27;
          v10 = 619;
          if ( AllVolumeNames < 0 )
            goto LABEL_7;
          v30 = 619;
          v17 = (const unsigned __int16 *)&Data;
          if ( *((_QWORD *)v16 + 3) )
            v17 = (const unsigned __int16 *)*((_QWORD *)v16 + 3);
          v18 = (const unsigned __int16 *)&Data;
          if ( *((_QWORD *)v16 + 4) )
            v18 = (const unsigned __int16 *)*((_QWORD *)v16 + 4);
          AllVolumeNames = CBsString::Set((struct CSdStringIndexEntry *)((char *)v27 + 8), v17, v18);
          v10 = 622;
          if ( AllVolumeNames < 0 )
            goto LABEL_7;
          v30 = 622;
          *((_DWORD *)v9 + 6) = v24;
          AllVolumeNames = CSxRefMap<CSdMediaMap,CSdMedia>::Insert(v8 + 2, v9);
          v10 = 624;
          if ( AllVolumeNames < 0 )
            goto LABEL_7;
          v30 = 624;
        }
      }
    }
  }
  ATL::CComSafeDeleteCriticalSection::Lock((CSdCommonImpl *)((char *)this + 24));
  CleanupStorageDevicePropArray((unsigned int *)this + 44, (struct _SD_STORAGE_DEVICE_PROP **)this + 23);
  *((_DWORD *)this + 44) = v38;
  *((_QWORD *)this + 23) = v32;
  v38 = 0;
  v32 = 0;
  if ( v7 )
    _InterlockedIncrement(v7 + 6);
  v19 = (CSdStringIndexMap *)*((_QWORD *)this + 24);
  if ( v19 )
  {
    *((_QWORD *)this + 24) = 0;
    CSdStringIndexMap::Release(v19);
  }
  *((_QWORD *)this + 24) = v7;
  if ( v8 )
    _InterlockedIncrement(v8 + 6);
  v20 = (CSdStringIndexMap *)*((_QWORD *)this + 25);
  if ( v20 )
  {
    *((_QWORD *)this + 25) = 0;
    CSdStringIndexMap::Release(v20);
  }
  *((_QWORD *)this + 25) = v8;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  *a2 = v26;
  *a3 = v6;
  v26 = 0;
  v35 = 0;
LABEL_52:
  if ( pv )
  {
    for ( k = 0; (unsigned int)k < v25; k = (unsigned int)(k + 1) )
      CoTaskMemFree(*((LPVOID *)pv + k));
    CoTaskMemFree(pv);
  }
  CleanupStorageDevicePropArray(&v38, &v32);
  CleanupStorageDevicePropArray(&v26, &v35);
  v22 = AllVolumeNames;
  if ( v9 )
    CSdStringIndexEntry::Release(v9);
  if ( v8 )
    CSdStringIndexMap::Release((CSdStringIndexMap *)v8);
  if ( v7 )
    CSdStringIndexMap::Release((CSdStringIndexMap *)v7);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&AllVolumeNames);
  return v22;
}

```

## disassembly

```asm
0x18004a340  mov     rax, rsp
0x18004a343  mov     [rax+8], rbx
0x18004a347  mov     [rax+18h], r8
0x18004a34b  mov     [rax+10h], rdx
0x18004a34f  push    rbp
0x18004a350  push    rsi
0x18004a351  push    rdi
0x18004a352  push    r12
0x18004a354  push    r13
0x18004a356  push    r14
0x18004a358  push    r15
0x18004a35a  lea     rbp, [rax-5Fh]
0x18004a35e  sub     rsp, 0A0h
0x18004a365  mov     rdi, r8
0x18004a368  mov     rbx, rdx
0x18004a36b  mov     r13, rcx
0x18004a36e  mov     r9d, 1; unsigned __int16
0x18004a374  mov     r8d, 207h; unsigned __int16
0x18004a37a  lea     rdx, aCsdcommonimplQ_9; "CSdCommonImpl::QueryStorageDevices"
0x18004a381  lea     rcx, [rbp+57h+var_90]; this
0x18004a385  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18004a38a  mov     [rbp+57h+arg_18], 0
0x18004a391  mov     [rbp+57h+var_58], 0
0x18004a399  mov     [rbp+57h+var_A8], 0
0x18004a3a0  xor     r12d, r12d
0x18004a3a3  mov     [rbp+57h+var_40], r12
0x18004a3a7  xor     r14d, r14d
0x18004a3aa  mov     [rbp+57h+var_48], r14
0x18004a3ae  xor     r15d, r15d
0x18004a3b1  mov     [rbp+57h+var_50], r15
0x18004a3b5  xor     esi, esi
0x18004a3b7  mov     [rbp+57h+var_A0], rsi
0x18004a3bb  mov     [rbp+57h+pv], rsi
0x18004a3bf  mov     [rbp+57h+var_AC], esi
0x18004a3c2  test    rdi, rdi
0x18004a3c5  jz      short loc_18004A3CA
0x18004a3c7  mov     [rdi], rsi
0x18004a3ca  test    rbx, rbx
0x18004a3cd  jz      short loc_18004A3D1
0x18004a3cf  mov     [rbx], esi
0x18004a3d1  mov     eax, 21Bh
0x18004a3d6  test    rdi, rdi
0x18004a3d9  jnz     short loc_18004A3EB
0x18004a3db  mov     [rbp+57h+var_90], 80070057h
0x18004a3e2  mov     [rbp+57h+var_8A], ax
0x18004a3e6  jmp     loc_18004A75A
0x18004a3eb  mov     [rbp+57h+var_8C], ax
0x18004a3ef  mov     eax, 21Ch
0x18004a3f4  test    rbx, rbx
0x18004a3f7  jz      short loc_18004A3DB
0x18004a3f9  mov     [rbp+57h+var_90], esi
0x18004a3fc  mov     [rbp+57h+var_8C], ax
0x18004a400  lea     rdx, [rbp+57h+var_58]; struct _SD_STORAGE_DEVICE_PROP **
0x18004a404  lea     rcx, [rbp+57h+arg_18]; unsigned int *
0x18004a408  call    ?QueryStorageDevices@@YAJPEAKPEAPEAU_SD_STORAGE_DEVICE_PROP@@@Z; QueryStorageDevices(ulong *,_SD_STORAGE_DEVICE_PROP * *)
0x18004a40d  mov     [rbp+57h+var_90], eax
0x18004a410  test    eax, eax
0x18004a412  mov     eax, 21Eh
0x18004a417  js      short loc_18004A3E2
0x18004a419  mov     [rbp+57h+var_8C], ax
0x18004a41d  mov     edi, [rbp+57h+arg_18]
0x18004a420  test    edi, edi
0x18004a422  jz      loc_18004A69A
0x18004a428  lea     rbx, [rdi+rdi*8]
0x18004a42c  shl     rbx, 4
0x18004a430  mov     rcx, rbx; cb
0x18004a433  call    cs:__imp_CoTaskMemAlloc
0x18004a439  mov     r12, rax
0x18004a43c  mov     [rbp+57h+var_40], rax
0x18004a440  test    rax, rax
0x18004a443  mov     eax, 225h
0x18004a448  jnz     short loc_18004A453
0x18004a44a  mov     [rbp+57h+var_90], 8007000Eh
0x18004a451  jmp     short loc_18004A3E2
0x18004a453  mov     [rbp+57h+var_90], esi
0x18004a456  mov     [rbp+57h+var_8C], ax
0x18004a45a  mov     r8, rbx; Size
0x18004a45d  xor     edx, edx; Val
0x18004a45f  mov     rcx, r12; void *
0x18004a462  call    memset_0
0x18004a467  mov     [rbp+57h+var_A8], edi
0x18004a46a  lea     rcx, [rbp+57h+var_48]; struct CSdStringIndexMap **
0x18004a46e  call    ?CreateInstance@CSdStringIndexMap@@SAJPEAPEAV1@@Z; CSdStringIndexMap::CreateInstance(CSdStringIndexMap * *)
0x18004a473  mov     [rbp+57h+var_90], eax
0x18004a476  test    eax, eax
0x18004a478  mov     eax, 22Ch
0x18004a47d  jns     short loc_18004A48C
0x18004a47f  mov     [rbp+57h+var_8A], ax
0x18004a483  mov     r14, [rbp+57h+var_48]
0x18004a487  jmp     loc_18004A75A
0x18004a48c  mov     [rbp+57h+var_8C], ax
0x18004a490  lea     rcx, [rbp+57h+var_50]; struct CSdStringIndexMap **
0x18004a494  call    ?CreateInstance@CSdStringIndexMap@@SAJPEAPEAV1@@Z; CSdStringIndexMap::CreateInstance(CSdStringIndexMap * *)
0x18004a499  mov     [rbp+57h+var_90], eax
0x18004a49c  mov     r14, [rbp+57h+var_48]
0x18004a4a0  mov     r15, [rbp+57h+var_50]
0x18004a4a4  test    eax, eax
0x18004a4a6  mov     eax, 22Dh
0x18004a4ab  js      loc_18004A3E2
0x18004a4b1  mov     [rbp+57h+var_8C], ax
0x18004a4b5  xor     eax, eax
0x18004a4b7  mov     [rbp+57h+var_B0], eax
0x18004a4ba  cmp     eax, edi
0x18004a4bc  jnb     loc_18004A69A
0x18004a4c2  lea     rcx, [rax+rax*8]
0x18004a4c6  shl     rcx, 4
0x18004a4ca  mov     rbx, [rbp+57h+var_58]
0x18004a4ce  add     rbx, rcx
0x18004a4d1  mov     [rbp+57h+var_50], rbx
0x18004a4d5  add     rcx, r12; struct _SD_STORAGE_DEVICE_PROP *
0x18004a4d8  mov     rdx, rbx; struct _SD_STORAGE_DEVICE_PROP *
0x18004a4db  call    ?CopyStorageDeviceProp@@YAJPEAU_SD_STORAGE_DEVICE_PROP@@PEBU1@@Z; CopyStorageDeviceProp(_SD_STORAGE_DEVICE_PROP *,_SD_STORAGE_DEVICE_PROP const *)
0x18004a4e0  mov     [rbp+57h+var_90], eax
0x18004a4e3  test    eax, eax
0x18004a4e5  mov     eax, 237h
0x18004a4ea  js      loc_18004A3E2
0x18004a4f0  mov     [rbp+57h+var_8C], ax
0x18004a4f4  mov     rcx, [rbx+8]; unsigned __int16 *
0x18004a4f8  call    ?SdIsPathUNC@@YAJPEBG@Z; SdIsPathUNC(ushort const *)
0x18004a4fd  mov     [rbp+57h+var_90], eax
0x18004a500  test    eax, eax
0x18004a502  js      loc_18004A690
0x18004a508  mov     ecx, 23Ch
0x18004a50d  mov     [rbp+57h+var_8C], cx
0x18004a511  jz      loc_18004A686
0x18004a517  lea     r8, [rbp+57h+var_AC]; unsigned int *
0x18004a51b  lea     rdx, [rbp+57h+pv]; unsigned __int16 ***
0x18004a51f  mov     rcx, [rbx+8]; unsigned __int16 *
0x18004a523  call    ?SxGetAllVolumeNames@@YAJPEBGPEAPEAPEAGPEAK@Z; SxGetAllVolumeNames(ushort const *,ushort * * *,ulong *)
0x18004a528  mov     [rbp+57h+var_90], eax
0x18004a52b  test    eax, eax
0x18004a52d  mov     eax, 245h
0x18004a532  js      loc_18004A3E2
0x18004a538  xor     ebx, ebx
0x18004a53a  mov     [rbp+57h+var_8C], ax
0x18004a53e  cmp     ebx, [rbp+57h+var_AC]
0x18004a541  jnb     loc_18004A5CB
0x18004a547  test    rsi, rsi
0x18004a54a  jz      short loc_18004A55C
0x18004a54c  mov     [rbp+57h+var_A0], 0
0x18004a554  mov     rcx, rsi; this
0x18004a557  call    ?Release@CSdStringIndexEntry@@QEAAKXZ; CSdStringIndexEntry::Release(void)
0x18004a55c  lea     rcx, [rbp+57h+var_A0]; struct CSdStringIndexEntry **
0x18004a560  call    ?CreateInstance@CSdStringIndexEntry@@SAJPEAPEAV1@@Z; CSdStringIndexEntry::CreateInstance(CSdStringIndexEntry * *)
0x18004a565  mov     [rbp+57h+var_90], eax
0x18004a568  mov     rsi, [rbp+57h+var_A0]
0x18004a56c  test    eax, eax
0x18004a56e  mov     eax, 251h
0x18004a573  js      loc_18004A3E2
0x18004a579  mov     [rbp+57h+var_8C], ax
0x18004a57d  mov     rax, [rbp+57h+pv]
0x18004a581  lea     rdx, [rax+rbx*8]; unsigned __int16 **
0x18004a585  lea     rcx, [rsi+8]; this
0x18004a589  call    ?Attach@CBsString@@QEAAJPEAPEAG@Z; CBsString::Attach(ushort * *)
0x18004a58e  mov     [rbp+57h+var_90], eax
0x18004a591  test    eax, eax
0x18004a593  mov     eax, 252h
0x18004a598  js      loc_18004A3E2
0x18004a59e  mov     [rbp+57h+var_8C], ax
0x18004a5a2  mov     eax, [rbp+57h+var_B0]
0x18004a5a5  mov     [rsi+18h], eax
0x18004a5a8  lea     rcx, [r14+8]
0x18004a5ac  mov     rdx, rsi
0x18004a5af  call    ?Insert@?$CSxRefMap@VCSdMediaMap@@VCSdMedia@@@@QEAAJPEAVCSdMedia@@PEAPEAV2@@Z; CSxRefMap<CSdMediaMap,CSdMedia>::Insert(CSdMedia *,CSdMedia * *)
0x18004a5b4  mov     [rbp+57h+var_90], eax
0x18004a5b7  test    eax, eax
0x18004a5b9  mov     eax, 254h
0x18004a5be  js      loc_18004A3E2
0x18004a5c4  inc     ebx
0x18004a5c6  jmp     loc_18004A53A
0x18004a5cb  mov     rcx, [rbp+57h+pv]; pv
0x18004a5cf  call    cs:__imp_CoTaskMemFree
0x18004a5d5  mov     [rbp+57h+pv], 0
0x18004a5dd  mov     rbx, [rbp+57h+var_50]
0x18004a5e1  cmp     dword ptr [rbx+38h], 0Dh
0x18004a5e5  jnz     loc_18004A686
0x18004a5eb  test    rsi, rsi
0x18004a5ee  jz      short loc_18004A600
0x18004a5f0  mov     [rbp+57h+var_A0], 0
0x18004a5f8  mov     rcx, rsi; this
0x18004a5fb  call    ?Release@CSdStringIndexEntry@@QEAAKXZ; CSdStringIndexEntry::Release(void)
0x18004a600  lea     rcx, [rbp+57h+var_A0]; struct CSdStringIndexEntry **
0x18004a604  call    ?CreateInstance@CSdStringIndexEntry@@SAJPEAPEAV1@@Z; CSdStringIndexEntry::CreateInstance(CSdStringIndexEntry * *)
0x18004a609  mov     [rbp+57h+var_90], eax
0x18004a60c  mov     rsi, [rbp+57h+var_A0]
0x18004a610  test    eax, eax
0x18004a612  mov     eax, 26Bh
0x18004a617  js      loc_18004A3E2
0x18004a61d  mov     [rbp+57h+var_8C], ax
0x18004a621  lea     rdx, Data
0x18004a628  cmp     qword ptr [rbx+18h], 0
0x18004a62d  cmovnz  rdx, [rbx+18h]; unsigned __int16 *
0x18004a632  lea     r8, Data
0x18004a639  cmp     qword ptr [rbx+20h], 0
0x18004a63e  cmovnz  r8, [rbx+20h]; unsigned __int16 *
0x18004a643  lea     rcx, [rsi+8]; this
0x18004a647  call    ?Set@CBsString@@QEAAJPEBG0@Z; CBsString::Set(ushort const *,ushort const *)
0x18004a64c  mov     [rbp+57h+var_90], eax
0x18004a64f  test    eax, eax
0x18004a651  mov     eax, 26Eh
0x18004a656  js      loc_18004A3E2
0x18004a65c  mov     [rbp+57h+var_8C], ax
0x18004a660  mov     eax, [rbp+57h+var_B0]
0x18004a663  mov     [rsi+18h], eax
0x18004a666  lea     rcx, [r15+8]
0x18004a66a  mov     rdx, rsi
0x18004a66d  call    ?Insert@?$CSxRefMap@VCSdMediaMap@@VCSdMedia@@@@QEAAJPEAVCSdMedia@@PEAPEAV2@@Z; CSxRefMap<CSdMediaMap,CSdMedia>::Insert(CSdMedia *,CSdMedia * *)
0x18004a672  mov     [rbp+57h+var_90], eax
0x18004a675  test    eax, eax
0x18004a677  mov     eax, 270h
0x18004a67c  js      loc_18004A3E2
0x18004a682  mov     [rbp+57h+var_8C], ax
0x18004a686  mov     eax, [rbp+57h+var_B0]
0x18004a689  inc     eax
0x18004a68b  jmp     loc_18004A4B7
0x18004a690  mov     eax, 23Ch
0x18004a695  jmp     loc_18004A3E2
0x18004a69a  lea     rcx, [r13+18h]; this
0x18004a69e  call    ?Lock@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Lock(void)
0x18004a6a3  lea     rdi, [r13+0B8h]
0x18004a6aa  lea     rbx, [r13+0B0h]
0x18004a6b1  mov     rdx, rdi; struct _SD_STORAGE_DEVICE_PROP **
0x18004a6b4  mov     rcx, rbx; unsigned int *
0x18004a6b7  call    ?CleanupStorageDevicePropArray@@YAXPEAKPEAPEAU_SD_STORAGE_DEVICE_PROP@@@Z; CleanupStorageDevicePropArray(ulong *,_SD_STORAGE_DEVICE_PROP * *)
0x18004a6bc  mov     eax, [rbp+57h+arg_18]
0x18004a6bf  mov     [rbx], eax
0x18004a6c1  mov     rax, [rbp+57h+var_58]
0x18004a6c5  mov     [rdi], rax
0x18004a6c8  mov     [rbp+57h+arg_18], 0
0x18004a6cf  mov     [rbp+57h+var_58], 0
0x18004a6d7  test    r14, r14
0x18004a6da  jz      short loc_18004A6E1
0x18004a6dc  lock inc dword ptr [r14+18h]
0x18004a6e1  mov     rcx, [r13+0C0h]; this
0x18004a6e8  test    rcx, rcx
0x18004a6eb  jz      short loc_18004A6FD
0x18004a6ed  mov     qword ptr [r13+0C0h], 0
0x18004a6f8  call    ?Release@CSdStringIndexMap@@QEAAKXZ; CSdStringIndexMap::Release(void)
0x18004a6fd  mov     [r13+0C0h], r14
0x18004a704  test    r15, r15
0x18004a707  jz      short loc_18004A70E
0x18004a709  lock inc dword ptr [r15+18h]
0x18004a70e  mov     rcx, [r13+0C8h]; this
0x18004a715  test    rcx, rcx
0x18004a718  jz      short loc_18004A72A
0x18004a71a  mov     qword ptr [r13+0C8h], 0
0x18004a725  call    ?Release@CSdStringIndexMap@@QEAAKXZ; CSdStringIndexMap::Release(void)
0x18004a72a  mov     [r13+0C8h], r15
0x18004a731  lea     rcx, [r13+18h]; lpCriticalSection
0x18004a735  call    cs:__imp_LeaveCriticalSection
0x18004a73b  mov     rax, [rbp+57h+arg_8]
0x18004a73f  mov     ecx, [rbp+57h+var_A8]
0x18004a742  mov     [rax], ecx
0x18004a744  mov     rax, [rbp+57h+arg_10]
0x18004a748  mov     [rax], r12
0x18004a74b  mov     [rbp+57h+var_A8], 0
0x18004a752  mov     [rbp+57h+var_40], 0
0x18004a75a  cmp     [rbp+57h+pv], 0
0x18004a75f  jz      short loc_18004A787
0x18004a761  xor     ebx, ebx
0x18004a763  cmp     [rbp+57h+var_AC], ebx
0x18004a766  jbe     short loc_18004A77D
0x18004a768  mov     rcx, [rbp+57h+pv]
0x18004a76c  mov     rcx, [rcx+rbx*8]; pv
0x18004a770  call    cs:__imp_CoTaskMemFree
0x18004a776  inc     ebx
0x18004a778  cmp     ebx, [rbp+57h+var_AC]
0x18004a77b  jb      short loc_18004A768
0x18004a77d  mov     rcx, [rbp+57h+pv]; pv
0x18004a781  call    cs:__imp_CoTaskMemFree
0x18004a787  lea     rdx, [rbp+57h+var_58]; struct _SD_STORAGE_DEVICE_PROP **
0x18004a78b  lea     rcx, [rbp+57h+arg_18]; unsigned int *
0x18004a78f  call    ?CleanupStorageDevicePropArray@@YAXPEAKPEAPEAU_SD_STORAGE_DEVICE_PROP@@@Z; CleanupStorageDevicePropArray(ulong *,_SD_STORAGE_DEVICE_PROP * *)
0x18004a794  lea     rdx, [rbp+57h+var_40]; struct _SD_STORAGE_DEVICE_PROP **
0x18004a798  lea     rcx, [rbp+57h+var_A8]; unsigned int *
0x18004a79c  call    ?CleanupStorageDevicePropArray@@YAXPEAKPEAPEAU_SD_STORAGE_DEVICE_PROP@@@Z; CleanupStorageDevicePropArray(ulong *,_SD_STORAGE_DEVICE_PROP * *)
0x18004a7a1  mov     ebx, [rbp+57h+var_90]
0x18004a7a4  test    rsi, rsi
0x18004a7a7  jz      short loc_18004A7B1
0x18004a7a9  mov     rcx, rsi; this
0x18004a7ac  call    ?Release@CSdStringIndexEntry@@QEAAKXZ; CSdStringIndexEntry::Release(void)
0x18004a7b1  test    r15, r15
0x18004a7b4  jz      short loc_18004A7BE
0x18004a7b6  mov     rcx, r15; this
0x18004a7b9  call    ?Release@CSdStringIndexMap@@QEAAKXZ; CSdStringIndexMap::Release(void)
0x18004a7be  test    r14, r14
0x18004a7c1  jz      short loc_18004A7CB
0x18004a7c3  mov     rcx, r14; this
0x18004a7c6  call    ?Release@CSdStringIndexMap@@QEAAKXZ; CSdStringIndexMap::Release(void)
0x18004a7cb  lea     rcx, [rbp+57h+var_90]; this
0x18004a7cf  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18004a7d4  mov     eax, ebx
0x18004a7d6  mov     rbx, [rsp+0D0h+arg_0]
0x18004a7de  add     rsp, 0A0h
0x18004a7e5  pop     r15
0x18004a7e7  pop     r14
0x18004a7e9  pop     r13
0x18004a7eb  pop     r12
0x18004a7ed  pop     rdi
0x18004a7ee  pop     rsi
  ... truncated ...
```
