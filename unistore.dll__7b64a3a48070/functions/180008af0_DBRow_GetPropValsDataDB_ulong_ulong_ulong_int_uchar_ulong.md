# DBRow::GetPropValsDataDB(ulong *,ulong *,ulong,int,uchar * *,ulong *)

- ea: `0x180008af0`
- end: `0x180008fe9`
- name: `?GetPropValsDataDB@DBRow@@IEAAJPEAK0KHPEAPEAE0@Z`
- size: `1273`
- prototype: `__int64 __usercall@<rax>(DBRow *__hidden this@<rcx>, unsigned int *@<rdx>, unsigned int *@<r8>, unsigned int@<r9d>, int, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002ea70`
- `0x18007eef0`

## callees

- `0x180004440`
- `0x1800068f0`
- `0x18000866c`
- `0x1800086bc`
- `0x180008770`
- `0x180008af0`
- `0x180009b40`
- `0x18000ab20`
- `0x18000b350`
- `0x180050150`
- `0x18006f180`
- `0x1800c6010`

## string_xrefs

- `0x180008b48`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180008de7`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180008e34`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180008ea0`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180008ebe`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180008f3e`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180008fc9`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180008fa5`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x180008f6a`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\jetinterophelper.h`
- `0x180008d40`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\DBSession.h`
- `0x180008dd5`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\DBSession.h`
- `0x180008e69`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\DBSession.h`
- `0x180008e89`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\DBSession.h`

## pseudocode

```c
__int64 __fastcall DBRow::GetPropValsDataDB(
        DBRow *this,
        unsigned int *a2,
        unsigned int *a3,
        unsigned int a4,
        int a5,
        unsigned __int8 **a6,
        unsigned int *a7)
{
  unsigned __int8 **v10; // r14
  unsigned int *v11; // r12
  int v12; // eax
  unsigned int v13; // ebx
  int v14; // eax
  __int64 v15; // rcx
  unsigned int v16; // eax
  __int64 v17; // rcx
  unsigned int v18; // ebx
  int v19; // eax
  int v20; // eax
  BOOL v21; // ebx
  int StoreId; // eax
  unsigned int v23; // r15d
  unsigned int v24; // edx
  int IsStoreProtected; // eax
  __int64 v26; // rcx
  int v27; // eax
  __int64 v29; // r9
  __int64 v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // r9
  __int64 v33; // r9
  __int64 v34; // rcx
  int *v35; // [rsp+20h] [rbp-58h]
  unsigned int v36; // [rsp+30h] [rbp-48h] BYREF
  int v37; // [rsp+34h] [rbp-44h] BYREF
  int v38; // [rsp+38h] [rbp-40h] BYREF
  __int64 v39; // [rsp+40h] [rbp-38h] BYREF
  __int64 v40; // [rsp+48h] [rbp-30h] BYREF
  __int64 v41; // [rsp+50h] [rbp-28h]
  struct TableHandleInfo *v42; // [rsp+58h] [rbp-20h] BYREF
  __int64 v43; // [rsp+60h] [rbp-18h] BYREF
  ProtectedStoreCache *v44; // [rsp+B8h] [rbp+40h] BYREF
  unsigned int v45; // [rsp+C8h] [rbp+50h] BYREF

  v45 = a4;
  v38 = 0;
  if ( !a2 )
  {
    v45 = 0;
    goto LABEL_62;
  }
  v10 = a6;
  v45 = *a2;
  if ( !a6 )
  {
LABEL_62:
    Log_UnistoreHREvent_0(
      2147942487LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      7985);
    return 2147942487LL;
  }
  if ( *a6 )
    Log_AssertionEvent(
      this,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      7986);
  v11 = (unsigned int *)&v38;
  v39 = 0;
  if ( a7 )
    v11 = a7;
  v12 = (*(__int64 (__fastcall **)(DBRow *, __int64 *))(*(_QWORD *)this + 24LL))(this, &v39);
  v13 = v12;
  if ( v12 < 0 )
  {
    Log_UnistoreHREvent_0(
      (unsigned int)v12,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      7994);
    if ( v39 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
      return v13;
    }
    return v13;
  }
  v40 = 0;
  v41 = 0;
  v14 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v39 + 160LL))(v39, &v40);
  v13 = v14;
  if ( v14 < 0 )
  {
    v33 = 834;
    v34 = (unsigned int)v14;
    goto LABEL_53;
  }
  v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v40 + 32LL))(v40);
  if ( g_breakOnJetError == -1912 )
    Log_AssertionEvent(
      v15,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\jetinterophelper.h",
      25);
  if ( v13 != -2134374536 )
  {
    if ( (v13 & 0x80000000) == 0 )
    {
      HIDWORD(v41) = 1;
      goto LABEL_14;
    }
    v33 = 838;
    v34 = v13;
LABEL_53:
    Log_UnistoreHREvent_0(
      v34,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\DBSession.h",
      v33);
    Log_UnistoreHREvent_0(
      v13,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      7997);
    goto LABEL_47;
  }
LABEL_14:
  LODWORD(v41) = 1;
  v42 = 0;
  v43 = v40;
  if ( v40 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 8LL))(v40);
  v16 = (*(__int64 (__fastcall **)(DBRow *))(*(_QWORD *)this + 32LL))(this);
  v17 = v43;
  v18 = v16;
  if ( !v43 )
  {
    v13 = -2147418113;
    v29 = 764;
    v30 = 2147549183LL;
    v31 = 0;
LABEL_45:
    Log_UnistoreHREvent_0(
      v30,
      v31,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\DBSession.h",
      v29);
    v32 = 8000;
LABEL_46:
    Log_UnistoreHREvent_0(
      v13,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      v32);
    auto_TableHandle::~auto_TableHandle((auto_TableHandle *)&v42);
LABEL_47:
    auto_DBSession::~auto_DBSession((auto_DBSession *)&v40);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v39);
    return v13;
  }
  if ( v42 )
  {
    auto_TableHandle::Close((auto_TableHandle *)&v42);
    v17 = v43;
  }
  v19 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, struct TableHandleInfo **))(*(_QWORD *)v17 + 64LL))(
          v17,
          v18,
          0,
          &v42);
  v13 = v19;
  if ( v19 < 0 )
  {
    v29 = 771;
    v31 = 1;
    v30 = (unsigned int)v19;
    goto LABEL_45;
  }
  v20 = UnistoreJetGotoBookmarkEx(v42, (DBRow *)((char *)this + 32), 0);
  v13 = v20;
  if ( v20 < 0 )
  {
    Log_UnistoreHREvent_0(
      (unsigned int)v20,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
      859);
    v32 = 8002;
    goto LABEL_46;
  }
  LODWORD(v44) = 0;
  v21 = a5 != 0;
  StoreId = DBRow::_GetStoreId(this, (unsigned int *)&v44);
  v23 = StoreId;
  if ( StoreId >= 0 )
  {
    v24 = *((_DWORD *)this + 6);
    v36 = 0;
    v37 = 0;
    IsStoreProtected = ProtectedStoreCache::IsStoreProtected(
                         (ProtectedStoreCache *)(unsigned int)v44,
                         v24,
                         (unsigned int)&v36,
                         &v37,
                         v35);
    if ( IsStoreProtected < 0 )
      Log_UnistoreHREvent_0(
        (unsigned int)IsStoreProtected,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
        8016);
    v13 = ESEReadRecordProps(v42, (v36 != 0 ? 2 : 0) | v21 | (v37 != 0 ? 4 : 0), &v45, a3, v10, v11);
    if ( (v13 & 0x80000000) == 0 )
    {
      v26 = v43;
      *a2 = v45;
      if ( v26 )
      {
        if ( v42 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 80LL))(v26);
          v26 = v43;
          v42 = 0;
        }
        if ( v26 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      }
      if ( !(_DWORD)v41 )
        goto LABEL_39;
      if ( !v40 )
        Log_AssertionEvent(
          v26,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\DBSession.h",
          850);
      if ( HIDWORD(v41) )
      {
        v27 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v40 + 40LL))(v40);
        if ( v27 < 0 )
        {
          Log_UnistoreHREvent_0(
            (unsigned int)v27,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\DBSession.h",
            853);
LABEL_39:
          if ( v40 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
          if ( v39 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
          return 0;
        }
        HIDWORD(v41) = 0;
      }
      if ( v40 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
        v40 = 0;
      }
      LODWORD(v41) = 0;
      goto LABEL_39;
    }
    v32 = 8020;
    goto LABEL_46;
  }
  Log_UnistoreHREvent_0(
    (unsigned int)StoreId,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
    8012);
  if ( v43 && v42 )
  {
    (*(void (**)(void))(*(_QWORD *)v43 + 80LL))();
    v42 = 0;
  }
  ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v43);
  auto_DBSession::~auto_DBSession((auto_DBSession *)&v40);
  if ( v39 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  return v23;
}

```

## disassembly

```asm
0x180008af0  mov     [rsp-30h+arg_18], r9d
0x180008af5  push    rbp
0x180008af6  push    rsi
0x180008af7  push    rdi
0x180008af8  push    r13
0x180008afa  push    r14
0x180008afc  push    r15
0x180008afe  mov     rbp, rsp
0x180008b01  sub     rsp, 78h
0x180008b05  xor     r15d, r15d
0x180008b08  mov     r13, r8
0x180008b0b  mov     [rbp+var_40], r15d
0x180008b0f  mov     rsi, rdx
0x180008b12  mov     rdi, rcx
0x180008b15  test    rdx, rdx
0x180008b18  jz      loc_180008F34
0x180008b1e  mov     r14, [rbp+arg_28]
0x180008b22  mov     eax, [rdx]
0x180008b24  mov     [rbp+arg_18], eax
0x180008b27  test    r14, r14
0x180008b2a  jz      loc_180008F38
0x180008b30  mov     [rsp+78h+arg_0], rbx
0x180008b38  mov     [rsp+78h+var_8], r12
0x180008b3d  cmp     [r14], r15
0x180008b40  jz      short loc_180008B54
0x180008b42  mov     r8d, 1F32h
0x180008b48  lea     rdx, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180008b4f  call    Log_AssertionEvent
0x180008b54  mov     rax, [rbp+arg_30]
0x180008b58  lea     r12, [rbp+var_40]
0x180008b5c  test    rax, rax
0x180008b5f  mov     [rbp+var_38], r15
0x180008b63  lea     rdx, [rbp+var_38]
0x180008b67  mov     rcx, rdi
0x180008b6a  cmovnz  r12, rax
0x180008b6e  mov     rax, [rdi]
0x180008b71  mov     rax, [rax+18h]
0x180008b75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b7a  mov     ebx, eax
0x180008b7c  test    eax, eax
0x180008b7e  js      loc_180008E2E
0x180008b84  mov     rcx, [rbp+var_38]
0x180008b88  lea     rdx, [rbp+var_30]
0x180008b8c  mov     [rbp+var_30], r15
0x180008b90  mov     [rbp+var_28], r15
0x180008b94  mov     rax, [rcx]
0x180008b97  mov     rax, [rax+0A0h]
0x180008b9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ba3  mov     ebx, eax
0x180008ba5  test    eax, eax
0x180008ba7  js      loc_180008E81
0x180008bad  mov     rcx, [rbp+var_30]
0x180008bb1  mov     rax, [rcx]
0x180008bb4  mov     rax, [rax+20h]
0x180008bb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bbd  cmp     cs:?g_breakOnJetError@@3JA, 0FFFFF888h; long g_breakOnJetError
0x180008bc7  mov     ebx, eax
0x180008bc9  jz      loc_180008F64
0x180008bcf  cmp     ebx, 80C80778h
0x180008bd5  jz      short loc_180008BE6
0x180008bd7  test    ebx, ebx
0x180008bd9  js      loc_180008F27
0x180008bdf  mov     dword ptr [rbp+var_28+4], 1
0x180008be6  mov     rcx, [rbp+var_30]
0x180008bea  mov     dword ptr [rbp+var_28], 1
0x180008bf1  mov     [rbp+var_20], r15
0x180008bf5  mov     [rbp+var_18], rcx
0x180008bf9  test    rcx, rcx
0x180008bfc  jz      short loc_180008C0A
0x180008bfe  mov     rax, [rcx]
0x180008c01  mov     rax, [rax+8]
0x180008c05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c0a  mov     rax, [rdi]
0x180008c0d  mov     rcx, rdi
0x180008c10  mov     rax, [rax+20h]
0x180008c14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c19  mov     rcx, [rbp+var_18]
0x180008c1d  mov     ebx, eax
0x180008c1f  test    rcx, rcx
0x180008c22  jz      loc_180008DC6
0x180008c28  cmp     [rbp+var_20], r15
0x180008c2c  jnz     loc_180008F7B
0x180008c32  mov     rax, [rcx]
0x180008c35  lea     r9, [rbp+var_20]
0x180008c39  xor     r8d, r8d
0x180008c3c  mov     edx, ebx
0x180008c3e  mov     rax, [rax+40h]
0x180008c42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c47  mov     ebx, eax
0x180008c49  test    eax, eax
0x180008c4b  js      loc_180008F8D
0x180008c51  mov     rcx, [rbp+var_20]; struct TableHandleInfo *
0x180008c55  lea     rdx, [rdi+20h]; struct UnifiedStoreCursorLocation *
0x180008c59  xor     r8d, r8d; int *
0x180008c5c  call    ?UnistoreJetGotoBookmarkEx@@YAJPEAUTableHandleInfo@@AEBVUnifiedStoreCursorLocation@@PEAH@Z; UnistoreJetGotoBookmarkEx(TableHandleInfo *,UnifiedStoreCursorLocation const &,int *)
0x180008c61  mov     ebx, eax
0x180008c63  test    eax, eax
0x180008c65  js      loc_180008F9F
0x180008c6b  cmp     [rbp+arg_20], r15d
0x180008c6f  lea     rdx, [rbp+arg_8]; unsigned int *
0x180008c73  mov     ebx, r15d
0x180008c76  mov     dword ptr [rbp+arg_8], r15d
0x180008c7a  mov     rcx, rdi; this
0x180008c7d  setnz   bl
0x180008c80  call    ?_GetStoreId@DBRow@@AEAAJPEAK@Z; DBRow::_GetStoreId(ulong *)
0x180008c85  mov     r15d, eax
0x180008c88  test    eax, eax
0x180008c8a  js      loc_180008EB8
0x180008c90  mov     edx, [rdi+18h]; unsigned int
0x180008c93  lea     r9, [rbp+var_44]; int *
0x180008c97  mov     ecx, dword ptr [rbp+arg_8]; this
0x180008c9a  lea     r8, [rbp+var_48]; unsigned int
0x180008c9e  xor     r15d, r15d
0x180008ca1  mov     [rbp+var_48], r15d
0x180008ca5  mov     [rbp+var_44], r15d
0x180008ca9  call    ?IsStoreProtected@ProtectedStoreCache@@YAJKKPEAH0@Z; ProtectedStoreCache::IsStoreProtected(ulong,ulong,int *,int *)
0x180008cae  test    eax, eax
0x180008cb0  js      loc_180008FC3
0x180008cb6  mov     eax, [rbp+var_48]
0x180008cb9  lea     r8, [rbp+arg_18]; unsigned int *
0x180008cbd  neg     eax
0x180008cbf  mov     [rsp+78h+var_50], r12; unsigned int *
0x180008cc4  mov     eax, [rbp+var_44]
0x180008cc7  mov     r9, r13; unsigned int *
0x180008cca  sbb     ecx, ecx
0x180008ccc  mov     [rsp+78h+var_58], r14; unsigned __int8 **
0x180008cd1  and     ecx, 2
0x180008cd4  or      ebx, ecx
0x180008cd6  mov     rcx, [rbp+var_20]; struct TableHandleInfo *
0x180008cda  neg     eax
0x180008cdc  sbb     edx, edx
0x180008cde  and     edx, 4
0x180008ce1  or      edx, ebx; unsigned int
0x180008ce3  call    ?ESEReadRecordProps@@YAJPEAUTableHandleInfo@@KPEAK1PEAPEAE1@Z; ESEReadRecordProps(TableHandleInfo *,ulong,ulong *,ulong *,uchar * *,ulong *)
0x180008ce8  mov     ebx, eax
0x180008cea  test    eax, eax
0x180008cec  js      loc_180008FDE
0x180008cf2  mov     rcx, [rbp+var_18]
0x180008cf6  mov     eax, [rbp+arg_18]
0x180008cf9  mov     [rsi], eax
0x180008cfb  test    rcx, rcx
0x180008cfe  jz      short loc_180008D2E
0x180008d00  mov     rdx, [rbp+var_20]
0x180008d04  test    rdx, rdx
0x180008d07  jz      short loc_180008D1D
0x180008d09  mov     rax, [rcx]
0x180008d0c  mov     rax, [rax+50h]
0x180008d10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d15  mov     rcx, [rbp+var_18]
0x180008d19  mov     [rbp+var_20], r15
0x180008d1d  test    rcx, rcx
0x180008d20  jz      short loc_180008D2E
0x180008d22  mov     rax, [rcx]
0x180008d25  mov     rax, [rax+10h]
0x180008d29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d2e  cmp     dword ptr [rbp+var_28], r15d
0x180008d32  jz      short loc_180008D7F
0x180008d34  cmp     [rbp+var_30], r15
0x180008d38  jnz     short loc_180008D4C
0x180008d3a  mov     r8d, 352h
0x180008d40  lea     rdx, aOnecoreuapBase_36; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180008d47  call    Log_AssertionEvent
0x180008d4c  cmp     dword ptr [rbp+var_28+4], r15d
0x180008d50  jz      short loc_180008D6E
0x180008d52  mov     rcx, [rbp+var_30]
0x180008d56  mov     rax, [rcx]
0x180008d59  mov     rax, [rax+28h]
0x180008d5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d62  test    eax, eax
0x180008d64  js      loc_180008E63
0x180008d6a  mov     dword ptr [rbp+var_28+4], r15d
0x180008d6e  mov     rcx, [rbp+var_30]
0x180008d72  test    rcx, rcx
0x180008d75  jnz     loc_180008E19
0x180008d7b  mov     dword ptr [rbp+var_28], r15d
0x180008d7f  mov     rcx, [rbp+var_30]
0x180008d83  test    rcx, rcx
0x180008d86  jz      short loc_180008D94
0x180008d88  mov     rax, [rcx]
0x180008d8b  mov     rax, [rax+10h]
0x180008d8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d94  mov     rcx, [rbp+var_38]
0x180008d98  test    rcx, rcx
0x180008d9b  jz      short loc_180008DA9
0x180008d9d  mov     rax, [rcx]
0x180008da0  mov     rax, [rax+10h]
0x180008da4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008da9  xor     eax, eax
0x180008dab  mov     rbx, [rsp+78h+arg_0]
0x180008db3  mov     r12, [rsp+78h+var_8]
0x180008db8  add     rsp, 78h
0x180008dbc  pop     r15
0x180008dbe  pop     r14
0x180008dc0  pop     r13
0x180008dc2  pop     rdi
0x180008dc3  pop     rsi
0x180008dc4  pop     rbp
0x180008dc5  retn
0x180008dc6  mov     ebx, 8000FFFFh
0x180008dcb  mov     r9d, 2FCh
0x180008dd1  mov     ecx, ebx
0x180008dd3  xor     edx, edx
0x180008dd5  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180008ddc  call    Log_UnistoreHREvent_0
0x180008de1  mov     r9d, 1F40h
0x180008de7  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180008dee  mov     edx, 1
0x180008df3  mov     ecx, ebx
0x180008df5  call    Log_UnistoreHREvent_0
0x180008dfa  lea     rcx, [rbp+var_20]; this
0x180008dfe  call    ??1auto_TableHandle@@QEAA@XZ; auto_TableHandle::~auto_TableHandle(void)
0x180008e03  lea     rcx, [rbp+var_30]; this
0x180008e07  call    ??1auto_DBSession@@QEAA@XZ; auto_DBSession::~auto_DBSession(void)
0x180008e0c  lea     rcx, [rbp+var_38]; void *
0x180008e10  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180008e15  mov     eax, ebx
0x180008e17  jmp     short loc_180008DAB
0x180008e19  mov     rax, [rcx]
0x180008e1c  mov     rax, [rax+10h]
0x180008e20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e25  mov     [rbp+var_30], r15
0x180008e29  jmp     loc_180008D7B
0x180008e2e  mov     r9d, 1F3Ah
0x180008e34  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180008e3b  mov     edx, 1
0x180008e40  mov     ecx, ebx
0x180008e42  call    Log_UnistoreHREvent_0
0x180008e47  mov     rcx, [rbp+var_38]
0x180008e4b  test    rcx, rcx
0x180008e4e  jz      short loc_180008E15
0x180008e50  mov     rdx, [rcx]
0x180008e53  mov     rax, [rdx+10h]
0x180008e57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e5c  mov     eax, ebx
0x180008e5e  jmp     loc_180008DAB
0x180008e63  mov     r9d, 355h
0x180008e69  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180008e70  mov     edx, 1
0x180008e75  mov     ecx, eax
0x180008e77  call    Log_UnistoreHREvent_0
0x180008e7c  jmp     loc_180008D7F
0x180008e81  mov     r9d, 342h
0x180008e87  mov     ecx, eax
0x180008e89  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180008e90  mov     edx, 1
0x180008e95  call    Log_UnistoreHREvent_0
0x180008e9a  mov     r9d, 1F3Dh
0x180008ea0  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180008ea7  mov     edx, 1
0x180008eac  mov     ecx, ebx
0x180008eae  call    Log_UnistoreHREvent_0
0x180008eb3  jmp     loc_180008E03
0x180008eb8  mov     r9d, 1F4Ch
0x180008ebe  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180008ec5  mov     edx, 1
0x180008eca  mov     ecx, r15d
0x180008ecd  call    Log_UnistoreHREvent_0
0x180008ed2  mov     rcx, [rbp+var_18]
0x180008ed6  test    rcx, rcx
0x180008ed9  jz      short loc_180008EF8
0x180008edb  mov     rdx, [rbp+var_20]
0x180008edf  test    rdx, rdx
0x180008ee2  jz      short loc_180008EF8
0x180008ee4  mov     rax, [rcx]
0x180008ee7  mov     rax, [rax+50h]
0x180008eeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ef0  mov     [rbp+var_20], 0
0x180008ef8  lea     rcx, [rbp+var_18]; void *
0x180008efc  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180008f01  lea     rcx, [rbp+var_30]; this
0x180008f05  call    ??1auto_DBSession@@QEAA@XZ; auto_DBSession::~auto_DBSession(void)
0x180008f0a  mov     rcx, [rbp+var_38]
0x180008f0e  test    rcx, rcx
0x180008f11  jz      short loc_180008F1F
0x180008f13  mov     rax, [rcx]
0x180008f16  mov     rax, [rax+10h]
0x180008f1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f1f  mov     eax, r15d
0x180008f22  jmp     loc_180008DAB
0x180008f27  mov     r9d, 346h
0x180008f2d  mov     ecx, ebx
0x180008f2f  jmp     loc_180008E89
0x180008f34  mov     [rbp+arg_18], r15d
0x180008f38  mov     r9d, 1F31h
0x180008f3e  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180008f45  xor     edx, edx
0x180008f47  mov     ecx, 80070057h
0x180008f4c  call    Log_UnistoreHREvent_0
0x180008f51  mov     eax, 80070057h
0x180008f56  add     rsp, 78h
0x180008f5a  pop     r15
0x180008f5c  pop     r14
0x180008f5e  pop     r13
0x180008f60  pop     rdi
0x180008f61  pop     rsi
0x180008f62  pop     rbp
0x180008f63  retn
0x180008f64  mov     r8d, 19h
0x180008f6a  lea     rdx, aOnecoreuapBase_19; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180008f71  call    Log_AssertionEvent
  ... truncated ...
```
