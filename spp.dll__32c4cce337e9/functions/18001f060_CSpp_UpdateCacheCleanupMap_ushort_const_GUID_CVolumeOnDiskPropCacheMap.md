# CSpp::_UpdateCacheCleanupMap(ushort const *,_GUID,CVolumeOnDiskPropCacheMap *)

- ea: `0x18001f060`
- end: `0x18001f316`
- name: `?_UpdateCacheCleanupMap@CSpp@@AEAAJPEBGU_GUID@@PEAVCVolumeOnDiskPropCacheMap@@@Z`
- size: `694`
- prototype: `__int64 __fastcall(CSpp *this, const unsigned __int16 *, struct _GUID *, PRTL_AVL_TABLE *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180004ff0`

## callees

- `0x1800074e4`
- `0x180007544`
- `0x180007718`
- `0x180007908`
- `0x18000c804`
- `0x18000e308`
- `0x18000e34c`
- `0x18000e4cc`
- `0x180017600`
- `0x18001a37c`
- `0x18001f060`
- `0x180020f38`
- `0x1800268b4`
- `0x1800269ac`
- `0x18003532c`
- `0x180035b76`

## import_xrefs

- `ntdll!RtlLookupElementGenericTableAvl` at `0x18001f188`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18001f188`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f2be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f2be`

## string_xrefs

- `0x18001f0b8`: `CSpp::_UpdateCacheCleanupMap`

## pseudocode

```c
__int64 __fastcall CSpp::_UpdateCacheCleanupMap(
        CSpp *this,
        const unsigned __int16 *a2,
        struct _GUID *a3,
        PRTL_AVL_TABLE *a4)
{
  volatile signed __int32 *v7; // rbx
  struct CSxStringMap **v8; // rdi
  CVolumeEntry *v9; // rsi
  __int16 v10; // ax
  bool v11; // zf
  int Instance; // eax
  bool v13; // sf
  volatile signed __int32 **v14; // rax
  CSpp *v15; // rcx
  struct CSxStringMap **v16; // r14
  CSxStringMap *v17; // rcx
  CSpp *v18; // rcx
  int v19; // eax
  int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // r8
  unsigned int v23; // r14d
  int SnapshotOnDiskPropCacheFileName; // [rsp+30h] [rbp-39h] BYREF
  __int16 v26; // [rsp+34h] [rbp-35h]
  __int16 v27; // [rsp+36h] [rbp-33h]
  struct CSxStringMap **Buffer; // [rsp+68h] [rbp-1h] BYREF
  struct CVolumeEntry *v29; // [rsp+70h] [rbp+7h] BYREF
  LPVOID pv; // [rsp+78h] [rbp+Fh] BYREF
  struct _GUID v31; // [rsp+80h] [rbp+17h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_S_guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a3);
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&SnapshotOnDiskPropCacheFileName,
    "CSpp::_UpdateCacheCleanupMap",
    9066,
    1);
  v7 = 0;
  v8 = 0;
  v9 = 0;
  Buffer = 0;
  *(_QWORD *)&v31.Data1 = 0;
  v10 = 9073;
  v29 = 0;
  pv = 0;
  if ( !a2 )
    goto LABEL_24;
  v26 = 9073;
  v11 = memcmp_0(a3, &GUID_NULL, 0x10u) == 0;
  v10 = 9074;
  if ( v11 )
    goto LABEL_24;
  v26 = 9074;
  v10 = 9075;
  if ( !a4 )
    goto LABEL_24;
  SnapshotOnDiskPropCacheFileName = 0;
  v26 = 9075;
  Instance = CVolumeOnDiskPropCacheEntry::CreateInstance((struct CVolumeOnDiskPropCacheEntry **)&Buffer);
  v8 = Buffer;
  v13 = Instance < 0;
  SnapshotOnDiskPropCacheFileName = Instance;
  v10 = 9077;
  if ( v13 )
    goto LABEL_25;
  v26 = 9077;
  SnapshotOnDiskPropCacheFileName = CBsString::Set((CBsString *)(Buffer + 1), a2);
  v10 = 9078;
  if ( SnapshotOnDiskPropCacheFileName < 0 )
    goto LABEL_25;
  v26 = 9078;
  Buffer = v8;
  if ( !v8 )
  {
    v10 = 9081;
LABEL_24:
    SnapshotOnDiskPropCacheFileName = -2147024809;
    goto LABEL_25;
  }
  v14 = (volatile signed __int32 **)RtlLookupElementGenericTableAvl(*a4, &Buffer);
  if ( v14 )
  {
    v7 = *v14;
    _InterlockedAdd(*v14, 1u);
    SnapshotOnDiskPropCacheFileName = 0;
    v10 = 9081;
  }
  else
  {
    SnapshotOnDiskPropCacheFileName = 1;
    v16 = v8 + 3;
    v26 = 9081;
    v17 = v8[3];
    if ( v17 )
    {
      *v16 = 0;
      CSxStringMap::Release(v17);
    }
    SnapshotOnDiskPropCacheFileName = CSxStringMap::CreateInstance(v8 + 3);
    v10 = 9087;
    if ( SnapshotOnDiskPropCacheFileName < 0 )
      goto LABEL_25;
    v26 = 9087;
    SnapshotOnDiskPropCacheFileName = CSpp::_EnumerateCacheFilesOnVolume(v18, a2, *v16);
    v10 = 9088;
    if ( SnapshotOnDiskPropCacheFileName < 0 )
      goto LABEL_25;
    v26 = 9088;
    v19 = CSxRefMap<CVolumeOnDiskPropCacheMap,CVolumeOnDiskPropCacheEntry>::Insert(a4, v8, &v31);
    v7 = *(volatile signed __int32 **)&v31.Data1;
    v13 = v19 < 0;
    SnapshotOnDiskPropCacheFileName = v19;
    v10 = 9090;
    if ( v13 )
      goto LABEL_25;
  }
  v31 = *a3;
  v26 = v10;
  SnapshotOnDiskPropCacheFileName = CSpp::_GetSnapshotOnDiskPropCacheFileName(v15, &v31, (unsigned __int16 **)&pv);
  v10 = 9094;
  if ( SnapshotOnDiskPropCacheFileName >= 0 )
  {
    v26 = 9094;
    v20 = CVolumeEntry::CreateInstance(&v29);
    v9 = v29;
    v13 = v20 < 0;
    SnapshotOnDiskPropCacheFileName = v20;
    v10 = 9096;
    if ( !v13 )
    {
      v26 = 9096;
      SnapshotOnDiskPropCacheFileName = CBsString::Set(
                                          (struct CVolumeEntry *)((char *)v29 + 8),
                                          (const unsigned __int16 *)pv);
      v10 = 9097;
      if ( SnapshotOnDiskPropCacheFileName >= 0 )
      {
        v26 = 9097;
        SnapshotOnDiskPropCacheFileName = CSxRefMap<CVolumeEntryMap,CVolumeEntry>::Delete(*((_QWORD *)v7 + 3), v9);
        v10 = 9100;
        if ( SnapshotOnDiskPropCacheFileName >= 0 )
        {
          v26 = 9100;
          goto LABEL_26;
        }
      }
    }
  }
LABEL_25:
  v27 = v10;
LABEL_26:
  CoTaskMemFree(pv);
  v23 = SnapshotOnDiskPropCacheFileName;
  if ( v9 )
    CVolumeEntry::Release(v9);
  if ( v7 )
    CVolumeOnDiskPropCacheEntry::Release((CVolumeOnDiskPropCacheEntry *)v7);
  if ( v8 )
    CVolumeOnDiskPropCacheEntry::Release((CVolumeOnDiskPropCacheEntry *)v8);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&SnapshotOnDiskPropCacheFileName, v21, v22);
  return v23;
}

```

## disassembly

```asm
0x18001f060  mov     [rsp-8+arg_0], rbx
0x18001f065  push    rbp
0x18001f066  push    rsi
0x18001f067  push    rdi
0x18001f068  push    r12
0x18001f06a  push    r13
0x18001f06c  push    r14
0x18001f06e  push    r15
0x18001f070  lea     rbp, [rsp-27h]
0x18001f075  sub     rsp, 90h
0x18001f07c  mov     r12, r9
0x18001f07f  mov     r13, r8
0x18001f082  mov     r15, rdx
0x18001f085  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f08c  lea     rax, WPP_GLOBAL_Control
0x18001f093  cmp     rcx, rax
0x18001f096  jz      short loc_18001F0B2
0x18001f098  test    dword ptr [rcx+1Ch], 20000000h
0x18001f09f  jz      short loc_18001F0B2
0x18001f0a1  mov     rcx, [rcx+10h]; LoggerHandle
0x18001f0a5  mov     r9, rdx
0x18001f0a8  mov     [rsp+0C0h+var_A0], r8; __int64
0x18001f0ad  call    WPP_SF_S_guid_
0x18001f0b2  mov     r14d, 1
0x18001f0b8  lea     rdx, aCsppUpdatecach; "CSpp::_UpdateCacheCleanupMap"
0x18001f0bf  mov     r9d, r14d; unsigned __int16
0x18001f0c2  lea     rcx, [rbp+57h+var_90]; this
0x18001f0c6  mov     r8d, 236Ah; unsigned __int16
0x18001f0cc  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001f0d1  xor     ebx, ebx
0x18001f0d3  xor     edi, edi
0x18001f0d5  xor     esi, esi
0x18001f0d7  mov     [rbp+57h+Buffer], rdi
0x18001f0db  mov     qword ptr [rbp+57h+var_40.Data1], rbx
0x18001f0df  mov     eax, 2371h
0x18001f0e4  mov     [rbp+57h+var_50], rsi
0x18001f0e8  mov     [rbp+57h+pv], rbx
0x18001f0ec  test    r15, r15
0x18001f0ef  jz      loc_18001F2AF
0x18001f0f5  lea     r8d, [r14+0Fh]; Size
0x18001f0f9  mov     [rbp+57h+var_8C], ax
0x18001f0fd  lea     rdx, GUID_NULL; Buf2
0x18001f104  mov     rcx, r13; Buf1
0x18001f107  call    memcmp_0
0x18001f10c  test    eax, eax
0x18001f10e  mov     eax, 2372h
0x18001f113  jz      loc_18001F2AF
0x18001f119  mov     [rbp+57h+var_8C], ax
0x18001f11d  mov     eax, 2373h
0x18001f122  test    r12, r12
0x18001f125  jz      loc_18001F2AF
0x18001f12b  lea     rcx, [rbp+57h+Buffer]; struct CVolumeOnDiskPropCacheEntry **
0x18001f12f  mov     [rbp+57h+var_90], ebx
0x18001f132  mov     [rbp+57h+var_8C], ax
0x18001f136  call    ?CreateInstance@CVolumeOnDiskPropCacheEntry@@SAJPEAPEAV1@@Z; CVolumeOnDiskPropCacheEntry::CreateInstance(CVolumeOnDiskPropCacheEntry * *)
0x18001f13b  mov     rdi, [rbp+57h+Buffer]
0x18001f13f  test    eax, eax
0x18001f141  mov     [rbp+57h+var_90], eax
0x18001f144  mov     eax, 2375h
0x18001f149  js      loc_18001F2B6
0x18001f14f  lea     rcx, [rdi+8]; this
0x18001f153  mov     [rbp+57h+var_8C], ax
0x18001f157  mov     rdx, r15; unsigned __int16 *
0x18001f15a  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18001f15f  mov     [rbp+57h+var_90], eax
0x18001f162  test    eax, eax
0x18001f164  mov     eax, 2376h
0x18001f169  js      loc_18001F2B6
0x18001f16f  mov     [rbp+57h+var_8C], ax
0x18001f173  mov     [rbp+57h+Buffer], rdi
0x18001f177  test    rdi, rdi
0x18001f17a  jz      loc_18001F2AA
0x18001f180  mov     rcx, [r12]; Table
0x18001f184  lea     rdx, [rbp+57h+Buffer]; Buffer
0x18001f188  call    cs:__imp_RtlLookupElementGenericTableAvl
0x18001f18e  test    rax, rax
0x18001f191  jnz     loc_18001F218
0x18001f197  mov     [rbp+57h+var_90], r14d
0x18001f19b  mov     eax, 2379h
0x18001f1a0  lea     r14, [rdi+18h]
0x18001f1a4  mov     [rbp+57h+var_8C], ax
0x18001f1a8  mov     rcx, [r14]; this
0x18001f1ab  test    rcx, rcx
0x18001f1ae  jz      short loc_18001F1B8
0x18001f1b0  mov     [r14], rbx
0x18001f1b3  call    ?Release@CSxStringMap@@QEAAKXZ; CSxStringMap::Release(void)
0x18001f1b8  mov     rcx, r14; struct CSxStringMap **
0x18001f1bb  call    ?CreateInstance@CSxStringMap@@SAJPEAPEAV1@@Z; CSxStringMap::CreateInstance(CSxStringMap * *)
0x18001f1c0  mov     [rbp+57h+var_90], eax
0x18001f1c3  test    eax, eax
0x18001f1c5  mov     eax, 237Fh
0x18001f1ca  js      loc_18001F2B6
0x18001f1d0  mov     [rbp+57h+var_8C], ax
0x18001f1d4  mov     rdx, r15; unsigned __int16 *
0x18001f1d7  mov     r8, [r14]; struct CSxStringMap *
0x18001f1da  call    ?_EnumerateCacheFilesOnVolume@CSpp@@AEAAJPEBGPEAVCSxStringMap@@@Z; CSpp::_EnumerateCacheFilesOnVolume(ushort const *,CSxStringMap *)
0x18001f1df  mov     [rbp+57h+var_90], eax
0x18001f1e2  test    eax, eax
0x18001f1e4  mov     eax, 2380h
0x18001f1e9  js      loc_18001F2B6
0x18001f1ef  lea     r8, [rbp+57h+var_40]
0x18001f1f3  mov     [rbp+57h+var_8C], ax
0x18001f1f7  mov     rdx, rdi
0x18001f1fa  mov     rcx, r12
0x18001f1fd  call    ?Insert@?$CSxRefMap@VCVolumeOnDiskPropCacheMap@@VCVolumeOnDiskPropCacheEntry@@@@QEAAJPEAVCVolumeOnDiskPropCacheEntry@@PEAPEAV2@@Z; CSxRefMap<CVolumeOnDiskPropCacheMap,CVolumeOnDiskPropCacheEntry>::Insert(CVolumeOnDiskPropCacheEntry *,CVolumeOnDiskPropCacheEntry * *)
0x18001f202  mov     rbx, qword ptr [rbp+57h+var_40.Data1]
0x18001f206  test    eax, eax
0x18001f208  mov     [rbp+57h+var_90], eax
0x18001f20b  mov     eax, 2382h
0x18001f210  js      loc_18001F2B6
0x18001f216  jmp     short loc_18001F227
0x18001f218  mov     rbx, [rax]
0x18001f21b  lock add [rbx], r14d
0x18001f21f  mov     [rbp+57h+var_90], esi
0x18001f222  mov     eax, 2379h
0x18001f227  movaps  xmm0, xmmword ptr [r13+0]
0x18001f22c  lea     r8, [rbp+57h+pv]; unsigned __int16 **
0x18001f230  lea     rdx, [rbp+57h+var_40]; struct _GUID
0x18001f234  movdqa  xmmword ptr [rbp+57h+var_40.Data1], xmm0
0x18001f239  mov     [rbp+57h+var_8C], ax
0x18001f23d  call    ?_GetSnapshotOnDiskPropCacheFileName@CSpp@@AEAAJU_GUID@@PEAPEAG@Z; CSpp::_GetSnapshotOnDiskPropCacheFileName(_GUID,ushort * *)
0x18001f242  mov     [rbp+57h+var_90], eax
0x18001f245  test    eax, eax
0x18001f247  mov     eax, 2386h
0x18001f24c  js      short loc_18001F2B6
0x18001f24e  lea     rcx, [rbp+57h+var_50]; struct CVolumeEntry **
0x18001f252  mov     [rbp+57h+var_8C], ax
0x18001f256  call    ?CreateInstance@CVolumeEntry@@SAJPEAPEAV1@@Z; CVolumeEntry::CreateInstance(CVolumeEntry * *)
0x18001f25b  mov     rsi, [rbp+57h+var_50]
0x18001f25f  test    eax, eax
0x18001f261  mov     [rbp+57h+var_90], eax
0x18001f264  mov     eax, 2388h
0x18001f269  js      short loc_18001F2B6
0x18001f26b  mov     rdx, [rbp+57h+pv]; unsigned __int16 *
0x18001f26f  lea     rcx, [rsi+8]; this
0x18001f273  mov     [rbp+57h+var_8C], ax
0x18001f277  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18001f27c  mov     [rbp+57h+var_90], eax
0x18001f27f  test    eax, eax
0x18001f281  mov     eax, 2389h
0x18001f286  js      short loc_18001F2B6
0x18001f288  mov     [rbp+57h+var_8C], ax
0x18001f28c  mov     rdx, rsi
0x18001f28f  mov     rcx, [rbx+18h]
0x18001f293  call    ?Delete@?$CSxRefMap@VCVolumeEntryMap@@VCVolumeEntry@@@@QEAAJPEAVCVolumeEntry@@@Z; CSxRefMap<CVolumeEntryMap,CVolumeEntry>::Delete(CVolumeEntry *)
0x18001f298  mov     [rbp+57h+var_90], eax
0x18001f29b  test    eax, eax
0x18001f29d  mov     eax, 238Ch
0x18001f2a2  js      short loc_18001F2B6
0x18001f2a4  mov     [rbp+57h+var_8C], ax
0x18001f2a8  jmp     short loc_18001F2BA
0x18001f2aa  mov     eax, 2379h
0x18001f2af  mov     [rbp+57h+var_90], 80070057h
0x18001f2b6  mov     [rbp+57h+var_8A], ax
0x18001f2ba  mov     rcx, [rbp+57h+pv]; pv
0x18001f2be  call    cs:__imp_CoTaskMemFree
0x18001f2c4  mov     r14d, [rbp+57h+var_90]
0x18001f2c8  test    rsi, rsi
0x18001f2cb  jz      short loc_18001F2D5
0x18001f2cd  mov     rcx, rsi; this
0x18001f2d0  call    ?Release@CVolumeEntry@@QEAAKXZ; CVolumeEntry::Release(void)
0x18001f2d5  test    rbx, rbx
0x18001f2d8  jz      short loc_18001F2E2
0x18001f2da  mov     rcx, rbx; this
0x18001f2dd  call    ?Release@CVolumeOnDiskPropCacheEntry@@QEAAKXZ; CVolumeOnDiskPropCacheEntry::Release(void)
0x18001f2e2  test    rdi, rdi
0x18001f2e5  jz      short loc_18001F2EF
0x18001f2e7  mov     rcx, rdi; this
0x18001f2ea  call    ?Release@CVolumeOnDiskPropCacheEntry@@QEAAKXZ; CVolumeOnDiskPropCacheEntry::Release(void)
0x18001f2ef  lea     rcx, [rbp+57h+var_90]; this
0x18001f2f3  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001f2f8  mov     rbx, [rsp+0C0h+arg_0]
0x18001f300  mov     eax, r14d
0x18001f303  add     rsp, 90h
0x18001f30a  pop     r15
0x18001f30c  pop     r14
0x18001f30e  pop     r13
0x18001f310  pop     r12
0x18001f312  pop     rdi
0x18001f313  pop     rsi
0x18001f314  pop     rbp
0x18001f315  retn
```
