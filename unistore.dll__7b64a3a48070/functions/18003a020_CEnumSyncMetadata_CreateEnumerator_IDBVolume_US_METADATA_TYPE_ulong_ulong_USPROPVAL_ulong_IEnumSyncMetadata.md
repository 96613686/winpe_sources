# CEnumSyncMetadata::CreateEnumerator(IDBVolume *,US_METADATA_TYPE,ulong,ulong,_USPROPVAL *,ulong,IEnumSyncMetadata * *)

- ea: `0x18003a020`
- end: `0x18003a3f6`
- name: `?CreateEnumerator@CEnumSyncMetadata@@SAJPEAVIDBVolume@@W4US_METADATA_TYPE@@KKPEAU_USPROPVAL@@KPEAPEAUIEnumSyncMetadata@@@Z`
- size: `982`
- prototype: ``
- caller_count: `4`
- callee_count: `13`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x180039b80`
- `0x18003a510`
- `0x18004b98c`
- `0x180067ee0`

## callees

- `0x180004440`
- `0x1800068f0`
- `0x1800230ac`
- `0x180028ef4`
- `0x18002e3d0`
- `0x18003a020`
- `0x18003bf70`
- `0x18003ec44`
- `0x180078a40`
- `0x180078a8c`
- `0x1800b76b8`
- `0x1800bf7e0`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a278`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a2c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a278`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a2c2`

## string_xrefs

- `0x18003a06c`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\enumsyncmetadata.cpp`
- `0x18003a0af`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\enumsyncmetadata.cpp`
- `0x18003a28a`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\enumsyncmetadata.cpp`
- `0x18003a2d2`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\enumsyncmetadata.cpp`
- `0x18003a320`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\enumsyncmetadata.cpp`
- `0x18003a39f`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\enumsyncmetadata.cpp`
- `0x18003a3c7`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\enumsyncmetadata.cpp`

## pseudocode

```c
__int64 __fastcall CEnumSyncMetadata::CreateEnumerator(
        __int64 a1,
        int a2,
        unsigned int a3,
        unsigned int a4,
        __int64 a5,
        unsigned int a6,
        __int64 **a7)
{
  __int64 *v8; // rbx
  __int64 v11; // r9
  unsigned int v12; // ebx
  __int64 (__fastcall *v14)(__int64, __int64, _QWORD, _QWORD, struct IUnknown **); // rdi
  __int64 v15; // rdx
  int v16; // eax
  unsigned int v17; // edi
  void *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // r8
  void *v21; // r13
  __int64 i; // r9
  int Instance; // eax
  __int64 *v24; // rdi
  __int64 v25; // rdx
  __int64 v26; // rcx
  void *v27; // r14
  void *v28; // rdi
  __int64 v29; // rax
  int v30; // eax
  int v31; // r15d
  struct IUnknown *v32; // rcx
  __int64 v33; // rdx
  __int64 v34; // r9
  int v35; // [rsp+30h] [rbp-38h] BYREF
  struct IUnknown *v36; // [rsp+38h] [rbp-30h] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp-28h] BYREF
  __int64 *v38; // [rsp+48h] [rbp-20h] BYREF
  _QWORD v39[3]; // [rsp+50h] [rbp-18h] BYREF

  v8 = 0;
  v38 = 0;
  v35 = 0;
  hMem = 0;
  v36 = 0;
  v39[0] = 0;
  if ( !a7 )
  {
    v12 = -2147467261;
    Log_UnistoreHREvent_0(
      2147500035LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\enumsyncmetadata.cpp",
      66);
    return v12;
  }
  if ( !a1 )
  {
    v11 = 67;
LABEL_4:
    v12 = -2147024809;
    Log_UnistoreHREvent_0(
      2147942487LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\enumsyncmetadata.cpp",
      v11);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v38);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v36);
    auto_local_array_ptr<unsigned char>::~auto_local_array_ptr<unsigned char>(&hMem);
    return v12;
  }
  if ( !a5 )
  {
    v11 = 68;
    goto LABEL_4;
  }
  if ( a6 > a4 )
  {
    v12 = -2147024809;
    Log_UnistoreHREvent_0(
      2147942487LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\enumsyncmetadata.cpp",
      69);
    return v12;
  }
  v14 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, struct IUnknown **))(*(_QWORD *)a1 + 32LL);
  if ( a2 )
  {
    v33 = (unsigned int)(a2 - 1);
    if ( (_DWORD)v33 )
    {
      if ( (_DWORD)v33 == 1 )
      {
        v15 = 34;
      }
      else
      {
        Log_AssertionEvent_25(a1, v33, 2127);
        v15 = 0xFFFFFFFFLL;
      }
    }
    else
    {
      v15 = 12;
    }
  }
  else
  {
    v15 = 13;
  }
  v16 = v14(a1, v15, a3, 0, &v36);
  v17 = v16;
  if ( v16 < 0 )
  {
    v34 = 72;
LABEL_48:
    Log_UnistoreHREvent_0(
      (unsigned int)v16,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\enumsyncmetadata.cpp",
      v34);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v38);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v36);
LABEL_42:
    auto_local_array_ptr<unsigned char>::~auto_local_array_ptr<unsigned char>(&hMem);
    return v17;
  }
  v16 = USCopyPropVals(a4, a5, 1, (unsigned int)&hMem, (__int64)&v35);
  v17 = v16;
  if ( v16 < 0 )
  {
    v34 = 75;
    goto LABEL_48;
  }
  v18 = operator new[](saturated_mul(a6, 4u));
  v21 = v18;
  if ( !v18 )
  {
    v12 = -2147024882;
    Log_UnistoreHREvent_0(
      2147942414LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\enumsyncmetadata.cpp",
      80);
    if ( v36 )
      ((void (__fastcall *)(struct IUnknown *))v36->lpVtbl->Release)(v36);
    if ( hMem )
      LocalFree(hMem);
    return v12;
  }
  for ( i = 0; (unsigned int)i < a6; i = (unsigned int)(i + 1) )
  {
    v19 = *(unsigned int *)(a5 + 24 * i);
    *((_DWORD *)v18 + i) = v19;
  }
  Instance = CUSObjectInternal<CEnumSyncMetadata>::CreateInstance(v39, v19, v20, i);
  v17 = Instance;
  if ( Instance < 0 )
  {
    Log_UnistoreHREvent_0(
      (unsigned int)Instance,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\enumsyncmetadata.cpp",
      89);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v38);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v36);
    operator delete(v21);
    goto LABEL_42;
  }
  v24 = (__int64 *)v39[0];
  if ( v39[0] )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v39[0] + 8LL))(v39[0]);
    v8 = v24;
    v38 = v24;
  }
  if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)a1 + 56LL))(a1) )
    Log_AssertionEvent_30(v26, v25, 93);
  *((_DWORD *)v8 + 19) = *(_DWORD *)(a5 + 8);
  ATL::CComPtr<IDBFilter>::operator=(v8 + 3, a1);
  if ( (struct IUnknown *)v8[4] != v36 )
    ATL::AtlComPtrAssign((struct IUnknown **)v8 + 4, v36);
  v27 = (void *)v8[6];
  v8[6] = (__int64)hMem;
  *((_DWORD *)v8 + 14) = a4;
  *((_DWORD *)v8 + 18) = a6;
  v28 = (void *)v8[8];
  v8[8] = (__int64)v21;
  v29 = *v8;
  hMem = v27;
  v30 = (*(__int64 (__fastcall **)(__int64 *))(v29 + 40))(v8);
  v31 = v30;
  if ( v30 < 0 )
  {
    Log_UnistoreHREvent_0(
      (unsigned int)v30,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\enumsyncmetadata.cpp",
      104);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v38);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v36);
    if ( v28 )
      operator delete(v28);
    v17 = v31;
    goto LABEL_42;
  }
  v32 = v36;
  *a7 = v8;
  if ( v32 )
    ((void (__fastcall *)(struct IUnknown *))v32->lpVtbl->Release)(v32);
  if ( v28 )
    operator delete(v28);
  if ( v27 )
    LocalFree(v27);
  return 0;
}

```

## disassembly

```asm
0x18003a020  mov     [rsp-40h+arg_18], r9d
0x18003a025  push    rbp
0x18003a026  push    rbx
0x18003a027  push    rsi
0x18003a028  push    rdi
0x18003a029  push    r12
0x18003a02b  push    r13
0x18003a02d  push    r14
0x18003a02f  push    r15
0x18003a031  mov     rbp, rsp
0x18003a034  sub     rsp, 68h
0x18003a038  xor     edi, edi
0x18003a03a  mov     r13d, r9d
0x18003a03d  mov     ebx, edi
0x18003a03f  mov     esi, r8d
0x18003a042  mov     r14, rcx
0x18003a045  mov     [rbp+var_20], rbx
0x18003a049  mov     [rbp+var_38], edi
0x18003a04c  mov     [rbp+hMem], rdi
0x18003a050  mov     [rbp+var_30], rdi
0x18003a054  mov     [rbp+var_18], rdi
0x18003a058  cmp     [rbp+arg_30], rdi
0x18003a05c  jz      short loc_18003A0AA
0x18003a05e  test    rcx, rcx
0x18003a061  jnz     short loc_18003A0DA
0x18003a063  lea     r9d, [rcx+43h]
0x18003a067  mov     ebx, 80070057h
0x18003a06c  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18003a073  mov     ecx, ebx
0x18003a075  xor     edx, edx
0x18003a077  call    Log_UnistoreHREvent_0
0x18003a07c  lea     rcx, [rbp+var_20]; void *
0x18003a080  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18003a085  lea     rcx, [rbp+var_30]; void *
0x18003a089  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18003a08e  lea     rcx, [rbp+hMem]
0x18003a092  call    ??1?$auto_local_array_ptr@E@@QEAA@XZ; auto_local_array_ptr<uchar>::~auto_local_array_ptr<uchar>(void)
0x18003a097  mov     eax, ebx
0x18003a099  add     rsp, 68h
0x18003a09d  pop     r15
0x18003a09f  pop     r14
0x18003a0a1  pop     r13
0x18003a0a3  pop     r12
0x18003a0a5  pop     rdi
0x18003a0a6  pop     rsi
0x18003a0a7  pop     rbx
0x18003a0a8  pop     rbp
0x18003a0a9  retn
0x18003a0aa  mov     ebx, 80004003h
0x18003a0af  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18003a0b6  mov     ecx, ebx
0x18003a0b8  mov     r9d, 42h ; 'B'
0x18003a0be  xor     edx, edx
0x18003a0c0  call    Log_UnistoreHREvent_0
0x18003a0c5  mov     rcx, [rbp+var_30]
0x18003a0c9  test    rcx, rcx
0x18003a0cc  jz      short loc_18003A097
0x18003a0ce  mov     rdx, [rcx]
0x18003a0d1  mov     rax, [rdx+10h]
0x18003a0d5  jmp     loc_18003A2FC
0x18003a0da  mov     r12, [rbp+arg_20]
0x18003a0de  test    r12, r12
0x18003a0e1  jz      loc_18003A363
0x18003a0e7  mov     r15d, [rbp+arg_28]
0x18003a0eb  cmp     r15d, r13d
0x18003a0ee  ja      loc_18003A2CD
0x18003a0f4  mov     rax, [rcx]
0x18003a0f7  mov     rdi, [rax+20h]
0x18003a0fb  test    edx, edx
0x18003a0fd  jnz     loc_18003A306
0x18003a103  mov     edx, 0Dh
0x18003a108  lea     rax, [rbp+var_30]
0x18003a10c  xor     r9d, r9d
0x18003a10f  mov     [rsp+68h+var_48], rax
0x18003a114  mov     r8d, esi
0x18003a117  mov     rax, rdi
0x18003a11a  mov     rcx, r14
0x18003a11d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a122  mov     edi, eax
0x18003a124  test    eax, eax
0x18003a126  js      loc_18003A38B
0x18003a12c  lea     rax, [rbp+var_38]
0x18003a130  mov     esi, 1
0x18003a135  mov     r8d, esi
0x18003a138  mov     [rsp+68h+var_48], rax
0x18003a13d  lea     r9, [rbp+hMem]
0x18003a141  mov     rdx, r12
0x18003a144  mov     ecx, r13d
0x18003a147  call    USCopyPropVals
0x18003a14c  mov     edi, eax
0x18003a14e  test    eax, eax
0x18003a150  js      loc_18003A397
0x18003a156  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18003a15d  lea     eax, [rsi+3]
0x18003a160  mul     r15
0x18003a163  cmovb   rax, rcx
0x18003a167  mov     rcx, rax; unsigned __int64
0x18003a16a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18003a16f  mov     r13, rax
0x18003a172  test    rax, rax
0x18003a175  jz      loc_18003A285
0x18003a17b  xor     r9d, r9d
0x18003a17e  test    r15d, r15d
0x18003a181  jz      short loc_18003A197
0x18003a183  lea     rcx, [r9+r9*2]
0x18003a187  mov     edx, [r12+rcx*8]
0x18003a18b  mov     [rax+r9*4], edx
0x18003a18f  add     r9d, esi
0x18003a192  cmp     r9d, r15d
0x18003a195  jb      short loc_18003A183
0x18003a197  lea     rcx, [rbp+var_18]
0x18003a19b  call    ?CreateInstance@?$CUSObjectInternal@VCEnumSyncMetadata@@@@SAJPEAPEAVCEnumSyncMetadata@@@Z; CUSObjectInternal<CEnumSyncMetadata>::CreateInstance(CEnumSyncMetadata * *)
0x18003a1a0  mov     edi, eax
0x18003a1a2  test    eax, eax
0x18003a1a4  js      loc_18003A3C1
0x18003a1aa  mov     rdi, [rbp+var_18]
0x18003a1ae  test    rdi, rdi
0x18003a1b1  jz      short loc_18003A1C9
0x18003a1b3  mov     rax, [rdi]
0x18003a1b6  mov     rcx, rdi
0x18003a1b9  mov     rax, [rax+8]
0x18003a1bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a1c2  mov     rbx, rdi
0x18003a1c5  mov     [rbp+var_20], rbx
0x18003a1c9  mov     rax, [r14]
0x18003a1cc  mov     rcx, r14
0x18003a1cf  mov     rax, [rax+38h]
0x18003a1d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a1d8  test    eax, eax
0x18003a1da  jnz     short loc_18003A1E5
0x18003a1dc  lea     r8d, [rax+5Dh]
0x18003a1e0  call    Log_AssertionEvent_30
0x18003a1e5  mov     eax, [r12+8]
0x18003a1ea  lea     rcx, [rbx+18h]
0x18003a1ee  mov     rdx, r14
0x18003a1f1  mov     [rbx+4Ch], eax
0x18003a1f4  call    ??4?$CComPtr@UIDBFilter@@@ATL@@QEAAPEAUIDBFilter@@PEAU2@@Z; ATL::CComPtr<IDBFilter>::operator=(IDBFilter *)
0x18003a1f9  mov     rdx, [rbp+var_30]; struct IUnknown *
0x18003a1fd  lea     rcx, [rbx+20h]; struct IUnknown **
0x18003a201  cmp     [rcx], rdx
0x18003a204  jz      short loc_18003A20B
0x18003a206  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18003a20b  mov     r14, [rbx+30h]
0x18003a20f  mov     rcx, rbx
0x18003a212  mov     rax, [rbp+hMem]
0x18003a216  mov     [rbx+30h], rax
0x18003a21a  mov     eax, [rbp+arg_18]
0x18003a21d  mov     [rbx+38h], eax
0x18003a220  mov     [rbx+48h], r15d
0x18003a224  mov     rdi, [rbx+40h]
0x18003a228  mov     [rbx+40h], r13
0x18003a22c  mov     rax, [rbx]
0x18003a22f  mov     [rbp+hMem], r14
0x18003a233  mov     rax, [rax+28h]
0x18003a237  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a23c  mov     r15d, eax
0x18003a23f  test    eax, eax
0x18003a241  js      loc_18003A31A
0x18003a247  mov     rax, [rbp+arg_30]
0x18003a24b  mov     rcx, [rbp+var_30]
0x18003a24f  mov     [rax], rbx
0x18003a252  test    rcx, rcx
0x18003a255  jz      short loc_18003A263
0x18003a257  mov     rax, [rcx]
0x18003a25a  mov     rax, [rax+10h]
0x18003a25e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a263  test    rdi, rdi
0x18003a266  jz      short loc_18003A270
0x18003a268  mov     rcx, rdi; Block
0x18003a26b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003a270  test    r14, r14
0x18003a273  jz      short loc_18003A27E
0x18003a275  mov     rcx, r14; hMem
0x18003a278  call    cs:__imp_LocalFree
0x18003a27e  xor     eax, eax
0x18003a280  jmp     loc_18003A099
0x18003a285  mov     ebx, 8007000Eh
0x18003a28a  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18003a291  mov     ecx, ebx
0x18003a293  mov     r9d, 50h ; 'P'
0x18003a299  xor     edx, edx
0x18003a29b  call    Log_UnistoreHREvent_0
0x18003a2a0  mov     rcx, [rbp+var_30]
0x18003a2a4  test    rcx, rcx
0x18003a2a7  jz      short loc_18003A2B5
0x18003a2a9  mov     rax, [rcx]
0x18003a2ac  mov     rax, [rax+10h]
0x18003a2b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a2b5  mov     rcx, [rbp+hMem]; hMem
0x18003a2b9  test    rcx, rcx
0x18003a2bc  jz      loc_18003A097
0x18003a2c2  call    cs:__imp_LocalFree
0x18003a2c8  jmp     loc_18003A097
0x18003a2cd  mov     ebx, 80070057h
0x18003a2d2  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18003a2d9  mov     ecx, ebx
0x18003a2db  mov     r9d, 45h ; 'E'
0x18003a2e1  xor     edx, edx
0x18003a2e3  call    Log_UnistoreHREvent_0
0x18003a2e8  mov     rcx, [rbp+var_30]
0x18003a2ec  test    rcx, rcx
0x18003a2ef  jz      loc_18003A097
0x18003a2f5  mov     rax, [rcx]
0x18003a2f8  mov     rax, [rax+10h]
0x18003a2fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a301  jmp     loc_18003A097
0x18003a306  sub     edx, 1
0x18003a309  jz      short loc_18003A381
0x18003a30b  cmp     edx, 1
0x18003a30e  jnz     short loc_18003A36E
0x18003a310  mov     edx, 22h ; '"'
0x18003a315  jmp     loc_18003A108
0x18003a31a  mov     r9d, 68h ; 'h'
0x18003a320  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18003a327  mov     edx, esi
0x18003a329  mov     ecx, r15d
0x18003a32c  call    Log_UnistoreHREvent_0
0x18003a331  lea     rcx, [rbp+var_20]; void *
0x18003a335  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18003a33a  lea     rcx, [rbp+var_30]; void *
0x18003a33e  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18003a343  test    rdi, rdi
0x18003a346  jz      short loc_18003A350
0x18003a348  mov     rcx, rdi; Block
0x18003a34b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003a350  mov     edi, r15d
0x18003a353  lea     rcx, [rbp+hMem]
0x18003a357  call    ??1?$auto_local_array_ptr@E@@QEAA@XZ; auto_local_array_ptr<uchar>::~auto_local_array_ptr<uchar>(void)
0x18003a35c  mov     eax, edi
0x18003a35e  jmp     loc_18003A099
0x18003a363  mov     r9d, 44h ; 'D'
0x18003a369  jmp     loc_18003A067
0x18003a36e  mov     r8d, 84Fh
0x18003a374  call    Log_AssertionEvent_25
0x18003a379  or      edx, 0FFFFFFFFh
0x18003a37c  jmp     loc_18003A108
0x18003a381  mov     edx, 0Ch
0x18003a386  jmp     loc_18003A108
0x18003a38b  mov     r9d, 48h ; 'H'
0x18003a391  lea     edx, [r9-47h]
0x18003a395  jmp     short loc_18003A39F
0x18003a397  mov     r9d, 4Bh ; 'K'
0x18003a39d  mov     edx, esi
0x18003a39f  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18003a3a6  mov     ecx, eax
0x18003a3a8  call    Log_UnistoreHREvent_0
0x18003a3ad  lea     rcx, [rbp+var_20]; void *
0x18003a3b1  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18003a3b6  lea     rcx, [rbp+var_30]; void *
0x18003a3ba  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18003a3bf  jmp     short loc_18003A353
0x18003a3c1  mov     r9d, 59h ; 'Y'
0x18003a3c7  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18003a3ce  mov     edx, esi
0x18003a3d0  mov     ecx, eax
0x18003a3d2  call    Log_UnistoreHREvent_0
0x18003a3d7  lea     rcx, [rbp+var_20]; void *
0x18003a3db  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18003a3e0  lea     rcx, [rbp+var_30]; void *
0x18003a3e4  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18003a3e9  mov     rcx, r13; Block
0x18003a3ec  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003a3f1  jmp     loc_18003A353
```
