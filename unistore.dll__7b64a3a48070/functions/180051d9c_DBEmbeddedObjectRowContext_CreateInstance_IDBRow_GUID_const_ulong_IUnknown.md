# DBEmbeddedObjectRowContext::CreateInstance(IDBRow *,_GUID const &,ulong,IUnknown * *)

- ea: `0x180051d9c`
- end: `0x1800520c4`
- name: `?CreateInstance@DBEmbeddedObjectRowContext@@SAJPEAVIDBRow@@AEBU_GUID@@KPEAPEAUIUnknown@@@Z`
- size: `808`
- prototype: `static int(struct IDBRow *, const struct _GUID *, unsigned int, struct IUnknown **)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180005c40`
- `0x180051be0`

## callees

- `0x180004440`
- `0x180006600`
- `0x1800068f0`
- `0x180028ef4`
- `0x180051d9c`
- `0x1800520cc`
- `0x180052654`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180051e1c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180051f2a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180051f6d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052034`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180051e1c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180051f2a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180051f6d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180052034`

## string_xrefs

- `0x180051ee5`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbtrack.cpp`
- `0x180051f3f`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbtrack.cpp`
- `0x180051f84`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbtrack.cpp`
- `0x180052060`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbtrack.cpp`
- `0x1800520a1`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbtrack.cpp`
- `0x180052047`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\objectimpl.h`

## pseudocode

```c
__int64 __fastcall DBEmbeddedObjectRowContext::CreateInstance(
        struct IDBRow *a1,
        const struct _GUID *a2,
        int a3,
        struct IUnknown **a4)
{
  int v8; // eax
  unsigned int Instance; // ebx
  __int64 (__fastcall *v10)(struct IDBRow *, __int64, _DWORD *, HLOCAL *, _QWORD); // rbx
  int v11; // eax
  __int64 v12; // rbx
  int v13; // edi
  unsigned int v14; // esi
  unsigned int v15; // eax
  int v16; // eax
  unsigned int v17; // edi
  __int64 v19; // r9
  __int64 v20; // r9
  __int64 v21; // rcx
  __int64 v22; // rdx
  int v23; // eax
  unsigned int v24; // edi
  __int64 v25; // [rsp+30h] [rbp-28h] BYREF
  __int64 v26; // [rsp+38h] [rbp-20h] BYREF
  _DWORD v27[2]; // [rsp+40h] [rbp-18h] BYREF
  __int64 v28; // [rsp+48h] [rbp-10h] BYREF
  HLOCAL hMem; // [rsp+B8h] [rbp+60h] BYREF

  v27[0] = 537067539;
  v27[1] = 537133075;
  hMem = 0;
  v25 = 0;
  if ( !a4 )
  {
    v19 = 2757;
    Instance = -2147467261;
    goto LABEL_21;
  }
  if ( (a3 & 0x10004000) == 0x10004000 )
  {
    Instance = DBNonTrackingContext::GetInstance(a2, a4);
LABEL_23:
    if ( hMem )
      LocalFree(hMem);
    return Instance;
  }
  v8 = (*(__int64 (__fastcall **)(struct IDBRow *, __int64 *))(*(_QWORD *)a1 + 24LL))(a1, &v25);
  Instance = v8;
  if ( v8 < 0 )
  {
    v20 = 2766;
LABEL_42:
    v22 = 1;
    v21 = (unsigned int)v8;
    goto LABEL_26;
  }
  v10 = *(__int64 (__fastcall **)(struct IDBRow *, __int64, _DWORD *, HLOCAL *, _QWORD))(*(_QWORD *)a1 + 40LL);
  if ( hMem )
    LocalFree(hMem);
  hMem = 0;
  v8 = v10(a1, 2, v27, &hMem, 0);
  Instance = v8;
  if ( v8 < 0 )
  {
    v20 = 2769;
    goto LABEL_42;
  }
  if ( (*((_WORD *)hMem + 3) & 0x100) != 0 )
  {
    Instance = -2147467259;
    v20 = 2770;
    v21 = 2147500037LL;
    v22 = 0;
LABEL_26:
    Log_UnistoreHREvent_0(
      v21,
      v22,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbtrack.cpp",
      v20);
LABEL_27:
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v25);
    auto_local_array_ptr<unsigned char>::~auto_local_array_ptr<unsigned char>(&hMem);
    return Instance;
  }
  if ( (*((_WORD *)hMem + 15) & 0x100) != 0 )
  {
    v19 = 2771;
    Instance = -2147467259;
LABEL_21:
    Log_UnistoreHREvent_0(
      Instance,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbtrack.cpp",
      v19);
    if ( v25 )
      (*(void (**)(void))(*(_QWORD *)v25 + 16LL))();
    goto LABEL_23;
  }
  v26 = 0;
  v28 = 0;
  v11 = CUSObjectInternal<DBEmbeddedObjectRowContext>::CreateInstance(&v28);
  Instance = v11;
  if ( v11 < 0 )
  {
    Log_UnistoreHREvent_0(
      (unsigned int)v11,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\objectimpl.h",
      452);
    Log_UnistoreHREvent_0(
      Instance,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbtrack.cpp",
      2776);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v26);
    goto LABEL_27;
  }
  v12 = v28;
  if ( v28 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 8LL))(v28);
  v26 = v12;
  v13 = *((_DWORD *)hMem + 8);
  v14 = *((_DWORD *)hMem + 2);
  v15 = (*(__int64 (__fastcall **)(struct IDBRow *))(*(_QWORD *)a1 + 32LL))(a1);
  v16 = DBEmbeddedObjectRowContext::Initialize(v12, v25, v15, v14, v13, a3);
  v17 = v16;
  if ( v16 < 0 )
  {
    Log_UnistoreHREvent_0(
      (unsigned int)v16,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbtrack.cpp",
      2777);
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    if ( hMem )
      LocalFree(hMem);
    return v17;
  }
  v23 = (**(__int64 (__fastcall ***)(__int64, const struct _GUID *, struct IUnknown **))v12)(v12, a2, a4);
  v24 = v23;
  if ( v23 < 0 )
  {
    Log_UnistoreHREvent_0(
      (unsigned int)v23,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbtrack.cpp",
      2778);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v26);
    Instance = v24;
    goto LABEL_27;
  }
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  if ( hMem )
    LocalFree(hMem);
  return 0;
}

```

## disassembly

```asm
0x180051d9c  push    rbp
0x180051d9e  push    rbx
0x180051d9f  push    rsi
0x180051da0  push    rdi
0x180051da1  push    r12
0x180051da3  push    r13
0x180051da5  push    r14
0x180051da7  push    r15
0x180051da9  mov     rbp, rsp
0x180051dac  sub     rsp, 58h
0x180051db0  xor     edi, edi
0x180051db2  mov     [rbp+var_18], 20030013h
0x180051db9  mov     [rbp+var_14], 20040013h
0x180051dc0  mov     r15, r9
0x180051dc3  mov     [rbp+hMem], rdi
0x180051dc7  mov     r13d, r8d
0x180051dca  mov     [rbp+var_28], rdi
0x180051dce  mov     r12, rdx
0x180051dd1  mov     r14, rcx
0x180051dd4  test    r9, r9
0x180051dd7  jz      loc_180051F34
0x180051ddd  mov     ecx, 10004000h
0x180051de2  mov     eax, r8d
0x180051de5  and     eax, ecx
0x180051de7  cmp     eax, ecx
0x180051de9  jz      loc_180051FB5
0x180051def  mov     rax, [r14]
0x180051df2  lea     rdx, [rbp+var_28]
0x180051df6  mov     rcx, r14
0x180051df9  mov     rax, [rax+18h]
0x180051dfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051e02  mov     ebx, eax
0x180051e04  test    eax, eax
0x180051e06  js      loc_180052081
0x180051e0c  mov     rax, [r14]
0x180051e0f  mov     rcx, [rbp+hMem]; hMem
0x180051e13  mov     rbx, [rax+28h]
0x180051e17  test    rcx, rcx
0x180051e1a  jz      short loc_180051E22
0x180051e1c  call    cs:__imp_LocalFree
0x180051e22  lea     r9, [rbp+hMem]
0x180051e26  mov     [rbp+hMem], rdi
0x180051e2a  lea     r8, [rbp+var_18]
0x180051e2e  mov     [rsp+58h+var_38], rdi
0x180051e33  mov     edx, 2
0x180051e38  mov     rcx, r14
0x180051e3b  mov     rax, rbx
0x180051e3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051e43  mov     ebx, eax
0x180051e45  test    eax, eax
0x180051e47  js      loc_180052089
0x180051e4d  mov     rax, [rbp+hMem]
0x180051e51  mov     ecx, 100h
0x180051e56  test    [rax+6], cx
0x180051e5a  jnz     loc_180051F75
0x180051e60  test    [rax+1Eh], cx
0x180051e64  jnz     loc_180051FD4
0x180051e6a  lea     rcx, [rbp+var_10]
0x180051e6e  mov     [rbp+var_20], rdi
0x180051e72  mov     [rbp+var_10], rdi
0x180051e76  call    ?CreateInstance@?$CUSObjectInternal@VDBEmbeddedObjectRowContext@@@@SAJPEAPEAVDBEmbeddedObjectRowContext@@@Z; CUSObjectInternal<DBEmbeddedObjectRowContext>::CreateInstance(DBEmbeddedObjectRowContext * *)
0x180051e7b  mov     ebx, eax
0x180051e7d  test    eax, eax
0x180051e7f  js      loc_180052041
0x180051e85  mov     rbx, [rbp+var_10]
0x180051e89  test    rbx, rbx
0x180051e8c  jz      short loc_180051E9D
0x180051e8e  mov     rax, [rbx]
0x180051e91  mov     rcx, rbx
0x180051e94  mov     rax, [rax+8]
0x180051e98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051e9d  mov     rax, [rbp+hMem]
0x180051ea1  mov     rcx, r14
0x180051ea4  mov     [rbp+var_20], rbx
0x180051ea8  mov     edi, [rax+20h]
0x180051eab  mov     esi, [rax+8]
0x180051eae  mov     rax, [r14]
0x180051eb1  mov     rax, [rax+20h]
0x180051eb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051eba  mov     rdx, [rbp+var_28]
0x180051ebe  mov     r9d, esi
0x180051ec1  mov     r8d, eax
0x180051ec4  mov     [rsp+58h+var_30], r13d
0x180051ec9  mov     rcx, rbx
0x180051ecc  mov     dword ptr [rsp+58h+var_38], edi
0x180051ed0  call    ?Initialize@DBEmbeddedObjectRowContext@@AEAAJPEAVIDBVolume@@W4US_TABLEID@@1KK@Z; DBEmbeddedObjectRowContext::Initialize(IDBVolume *,US_TABLEID,US_TABLEID,ulong,ulong)
0x180051ed5  mov     edi, eax
0x180051ed7  test    eax, eax
0x180051ed9  jns     loc_180051FE4
0x180051edf  mov     r9d, 0AD9h
0x180051ee5  lea     r8, aOnecoreuapBase_24; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180051eec  mov     edx, 1
0x180051ef1  mov     ecx, eax
0x180051ef3  call    Log_UnistoreHREvent_0
0x180051ef8  test    rbx, rbx
0x180051efb  jz      short loc_180051F0C
0x180051efd  mov     rcx, [rbx]
0x180051f00  mov     rax, [rcx+10h]
0x180051f04  mov     rcx, rbx
0x180051f07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051f0c  mov     rcx, [rbp+var_28]
0x180051f10  test    rcx, rcx
0x180051f13  jz      short loc_180051F21
0x180051f15  mov     rax, [rcx]
0x180051f18  mov     rax, [rax+10h]
0x180051f1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051f21  mov     rcx, [rbp+hMem]; hMem
0x180051f25  test    rcx, rcx
0x180051f28  jz      short loc_180051F30
0x180051f2a  call    cs:__imp_LocalFree
0x180051f30  mov     eax, edi
0x180051f32  jmp     short loc_180051FA4
0x180051f34  mov     r9d, 0AC5h
0x180051f3a  mov     ebx, 80004003h
0x180051f3f  lea     r8, aOnecoreuapBase_24; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180051f46  xor     edx, edx
0x180051f48  mov     ecx, ebx
0x180051f4a  call    Log_UnistoreHREvent_0
0x180051f4f  mov     rcx, [rbp+var_28]
0x180051f53  test    rcx, rcx
0x180051f56  jz      short loc_180051F64
0x180051f58  mov     rax, [rcx]
0x180051f5b  mov     rax, [rax+10h]
0x180051f5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051f64  mov     rcx, [rbp+hMem]; hMem
0x180051f68  test    rcx, rcx
0x180051f6b  jz      short loc_180051FA2
0x180051f6d  call    cs:__imp_LocalFree
0x180051f73  jmp     short loc_180051FA2
0x180051f75  mov     ebx, 80004005h
0x180051f7a  mov     r9d, 0AD2h
0x180051f80  mov     ecx, ebx
0x180051f82  xor     edx, edx
0x180051f84  lea     r8, aOnecoreuapBase_24; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180051f8b  call    Log_UnistoreHREvent_0
0x180051f90  lea     rcx, [rbp+var_28]; void *
0x180051f94  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180051f99  lea     rcx, [rbp+hMem]
0x180051f9d  call    ??1?$auto_local_array_ptr@E@@QEAA@XZ; auto_local_array_ptr<uchar>::~auto_local_array_ptr<uchar>(void)
0x180051fa2  mov     eax, ebx
0x180051fa4  add     rsp, 58h
0x180051fa8  pop     r15
0x180051faa  pop     r14
0x180051fac  pop     r13
0x180051fae  pop     r12
0x180051fb0  pop     rdi
0x180051fb1  pop     rsi
0x180051fb2  pop     rbx
0x180051fb3  pop     rbp
0x180051fb4  retn
0x180051fb5  mov     rdx, r15; struct IUnknown **
0x180051fb8  mov     rcx, r12; struct _GUID *
0x180051fbb  call    ?GetInstance@DBNonTrackingContext@@SAJAEBU_GUID@@PEAPEAUIUnknown@@@Z; DBNonTrackingContext::GetInstance(_GUID const &,IUnknown * *)
0x180051fc0  mov     rcx, [rbp+var_28]
0x180051fc4  mov     ebx, eax
0x180051fc6  test    rcx, rcx
0x180051fc9  jz      short loc_180051F64
0x180051fcb  mov     rdx, [rcx]
0x180051fce  mov     rax, [rdx+10h]
0x180051fd2  jmp     short loc_180051F5F
0x180051fd4  mov     r9d, 0AD3h
0x180051fda  mov     ebx, 80004005h
0x180051fdf  jmp     loc_180051F3F
0x180051fe4  mov     rax, [rbx]
0x180051fe7  mov     r8, r15
0x180051fea  mov     rdx, r12
0x180051fed  mov     rcx, rbx
0x180051ff0  mov     rax, [rax]
0x180051ff3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051ff8  mov     edi, eax
0x180051ffa  test    eax, eax
0x180051ffc  js      loc_18005209B
0x180052002  test    rbx, rbx
0x180052005  jz      short loc_180052016
0x180052007  mov     rax, [rbx]
0x18005200a  mov     rcx, rbx
0x18005200d  mov     rax, [rax+10h]
0x180052011  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052016  mov     rcx, [rbp+var_28]
0x18005201a  test    rcx, rcx
0x18005201d  jz      short loc_18005202B
0x18005201f  mov     rax, [rcx]
0x180052022  mov     rax, [rax+10h]
0x180052026  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005202b  mov     rcx, [rbp+hMem]; hMem
0x18005202f  test    rcx, rcx
0x180052032  jz      short loc_18005203A
0x180052034  call    cs:__imp_LocalFree
0x18005203a  xor     eax, eax
0x18005203c  jmp     loc_180051FA4
0x180052041  mov     r9d, 1C4h
0x180052047  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18005204e  mov     edx, 1
0x180052053  mov     ecx, ebx
0x180052055  call    Log_UnistoreHREvent_0
0x18005205a  mov     r9d, 0AD8h
0x180052060  lea     r8, aOnecoreuapBase_24; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180052067  mov     edx, 1
0x18005206c  mov     ecx, ebx
0x18005206e  call    Log_UnistoreHREvent_0
0x180052073  lea     rcx, [rbp+var_20]; void *
0x180052077  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18005207c  jmp     loc_180051F90
0x180052081  mov     r9d, 0ACEh
0x180052087  jmp     short loc_18005208F
0x180052089  mov     r9d, 0AD1h
0x18005208f  mov     edx, 1
0x180052094  mov     ecx, eax
0x180052096  jmp     loc_180051F84
0x18005209b  mov     r9d, 0ADAh
0x1800520a1  lea     r8, aOnecoreuapBase_24; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800520a8  mov     edx, 1
0x1800520ad  mov     ecx, edi
0x1800520af  call    Log_UnistoreHREvent_0
0x1800520b4  lea     rcx, [rbp+var_20]; void *
0x1800520b8  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x1800520bd  mov     ebx, edi
0x1800520bf  jmp     loc_180051F90
```
