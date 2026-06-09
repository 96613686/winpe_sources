# DBManager::SetRowPropValsInternal(IDBSession *,ulong,UnifiedStoreCursorLocation &,int,ushort const *,ulong,uchar *,ulong *)

- ea: `0x180029c10`
- end: `0x18002a53b`
- name: `?SetRowPropValsInternal@DBManager@@SAJPEAVIDBSession@@KAEAVUnifiedStoreCursorLocation@@HPEBGKPEAEPEAK@Z`
- size: `2347`
- prototype: `static int(struct IDBSession *, unsigned int, struct UnifiedStoreCursorLocation *, int, const unsigned __int16 *, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180006ce0`
- `0x18001d9b0`

## callees

- `0x180004440`
- `0x1800068f0`
- `0x18000866c`
- `0x180029c10`
- `0x18002a550`
- `0x18002ac20`
- `0x180033dc0`
- `0x180050150`
- `0x18005ca58`
- `0x18006f180`
- `0x18008016c`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029e89`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029e97`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029eaa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029eb8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029ec6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029ed8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029ee6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029f3b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029f4a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029f58`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029f6f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029f7d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029f8a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029ffc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a0e9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a0f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a106`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a115`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a17e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a18d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a19c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a1aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a1b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a1ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a1f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a208`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a217`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a226`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a27c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a28a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a298`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a2a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a303`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a311`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a31f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a32e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a33c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a3af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a3be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a3cc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a3da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a3e9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a3f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a405`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a436`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a444`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a453`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a461`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a46f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a47e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a48c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a49a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029e89`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029e97`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029eaa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029eb8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029ec6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029ed8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029ee6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029f3b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029f4a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029f58`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029f6f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029f7d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029f8a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029ffc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a0e9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a0f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a106`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a115`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a17e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a18d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a19c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a1aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a1b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a1ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a1f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a208`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a217`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a226`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a27c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a28a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a298`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a2a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a303`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a311`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a31f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a32e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a33c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a3af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a3be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a3cc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a3da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a3e9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a3f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a405`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a436`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a444`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a453`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a461`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a46f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a47e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a48c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a49a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a14a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a23f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a2d3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a14a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a23f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a2d3`

## string_xrefs

- `0x180029d40`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180029ef4`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180029f98`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18002a0c4`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18002a162`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18002a1ce`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18002a260`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18002a2e9`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18002a399`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18002a41b`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18002a4fa`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18002a0b2`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\DBSession.h`

## pseudocode

```c
__int64 __fastcall DBManager::SetRowPropValsInternal(
        struct IDBSession *a1,
        unsigned int a2,
        struct UnifiedStoreCursorLocation *a3,
        int a4,
        unsigned __int16 *a5,
        unsigned int a6,
        unsigned __int8 *a7,
        unsigned int *a8)
{
  _DWORD *v9; // r14
  unsigned __int8 **v10; // rax
  int v11; // eax
  unsigned int v12; // ebx
  unsigned int v13; // r11d
  int v14; // ecx
  struct _USPROPVALEx *v15; // r12
  struct _USPROPVAL *v16; // r13
  HLOCAL v17; // r15
  unsigned int v18; // edi
  int v20; // eax
  unsigned int v21; // ebx
  unsigned int *v22; // rax
  int v23; // eax
  struct IDBSession *v24; // rcx
  HLOCAL v25; // rsi
  unsigned int *v26; // rbx
  char *v27; // rdi
  unsigned int *v28; // rdi
  char *v29; // rbx
  struct _USPROPVAL *v30; // rcx
  int v31; // eax
  unsigned int v32; // edi
  unsigned int v33; // r9d
  __int64 i; // r8
  __int64 v35; // rcx
  unsigned int v36; // eax
  __int64 j; // r8
  __int64 v38; // r10
  int v39; // ecx
  __int64 v40; // r9
  __int64 v41; // rcx
  __int64 v42; // rdx
  HLOCAL v43; // rax
  char *v44; // rax
  __int64 v45; // rdx
  unsigned __int8 *v46; // r9
  __int64 v47; // rax
  struct IDBSession *v48; // rcx
  unsigned int v49; // [rsp+68h] [rbp-59h] BYREF
  int v50; // [rsp+6Ch] [rbp-55h]
  HLOCAL v51; // [rsp+70h] [rbp-51h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp-49h] BYREF
  HLOCAL v53; // [rsp+80h] [rbp-41h] BYREF
  struct IDBSession *v54; // [rsp+88h] [rbp-39h] BYREF
  HLOCAL v55; // [rsp+90h] [rbp-31h] BYREF
  unsigned int v56; // [rsp+98h] [rbp-29h] BYREF
  unsigned int v57; // [rsp+9Ch] [rbp-25h] BYREF
  HLOCAL v58; // [rsp+A0h] [rbp-21h] BYREF
  _DWORD *v59; // [rsp+A8h] [rbp-19h] BYREF

  v56 = 0;
  v58 = 0;
  v53 = 0;
  v9 = 0;
  v49 = 0;
  v59 = 0;
  v57 = 0;
  if ( !a1 || !a6 || !a7 )
  {
    Log_UnistoreHREvent_0(
      2147942487LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      3404);
    return 2147942487LL;
  }
  hMem = 0;
  v55 = 0;
  v10 = (unsigned __int8 **)&v53;
  v51 = 0;
  if ( !a4 )
    v10 = (unsigned __int8 **)&v58;
  v11 = DBManager::SplitFileStreamPropVals(
          a2,
          a4,
          a6,
          a7,
          &v56,
          v10,
          (unsigned int **)&v51,
          &v57,
          &v49,
          (struct _USPROPVAL **)&v55,
          (unsigned int **)&hMem);
  v12 = v11;
  if ( v11 < 0 )
  {
    Log_UnistoreHREvent_0(
      (unsigned int)v11,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      3419);
    if ( hMem )
      LocalFree(hMem);
    if ( v55 )
      LocalFree(v55);
    if ( v51 )
      LocalFree(v51);
    if ( v53 )
      LocalFree(v53);
    if ( v58 )
      LocalFree(v58);
    return v12;
  }
  v13 = v49;
  v14 = 0;
  v15 = (struct _USPROPVALEx *)v53;
  v16 = (struct _USPROPVAL *)v58;
  v17 = 0;
  v18 = v56;
  v50 = 0;
  if ( v56 )
  {
    if ( v49 )
    {
      v14 = 1;
      v50 = 1;
    }
    if ( a8 )
    {
      if ( v14 )
      {
        v17 = LocalAlloc(0x40u, 4LL * v56);
        if ( !v17 )
        {
          Log_UnistoreHREvent_0(
            2147942414LL,
            0,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
            3432);
          if ( hMem )
            LocalFree(hMem);
          if ( v55 )
            LocalFree(v55);
          if ( v51 )
            LocalFree(v51);
          if ( v15 )
            goto LABEL_102;
          goto LABEL_103;
        }
      }
    }
  }
  else if ( *(_DWORD *)a3 )
  {
    goto LABEL_30;
  }
  v53 = 0;
  v54 = a1;
  (*(void (__fastcall **)(struct IDBSession *))(*(_QWORD *)a1 + 8LL))(a1);
  v48 = v54;
  if ( !v54 )
  {
    v21 = -2147418113;
    v40 = 764;
    v41 = 2147549183LL;
    v42 = 0;
    goto LABEL_83;
  }
  if ( v53 )
  {
    auto_TableHandle::Close((auto_TableHandle *)&v53);
    v48 = v54;
  }
  v20 = (*(__int64 (__fastcall **)(struct IDBSession *, _QWORD, _QWORD, HLOCAL *))(*(_QWORD *)v48 + 64LL))(
          v48,
          a2,
          0,
          &v53);
  v21 = v20;
  if ( v20 < 0 )
  {
    v40 = 771;
    v42 = 1;
    v41 = (unsigned int)v20;
LABEL_83:
    Log_UnistoreHREvent_0(
      v41,
      v42,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\DBSession.h",
      v40);
    Log_UnistoreHREvent_0(
      v21,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      3436);
    auto_TableHandle::~auto_TableHandle((auto_TableHandle *)&v53);
    if ( hMem )
      LocalFree(hMem);
    if ( v55 )
      LocalFree(v55);
    if ( v17 )
      LocalFree(v17);
    if ( v51 )
      LocalFree(v51);
    if ( !v15 )
      goto LABEL_59;
    goto LABEL_58;
  }
  v22 = a8;
  if ( a4 )
  {
    if ( v50 )
      v22 = (unsigned int *)v17;
    v21 = DBManager::SetRowPropValsDBEx((struct TableHandleInfo *const)v53, a3, v18, v15, v22);
  }
  else
  {
    if ( v50 )
      v22 = (unsigned int *)v17;
    if ( !*(_DWORD *)a3 || v18 && v16 )
    {
      v23 = ESEWriteRecordProps((struct TableHandleInfo *)v53, a3, a5, v18, v16, v22);
      v21 = v23;
      if ( v23 < 0 )
        Log_UnistoreHREvent_0(
          (unsigned int)v23,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
          3332);
      else
        v21 = 0;
    }
    else
    {
      Log_AssertionEvent(
        a3,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
        3330);
      v21 = -2147024809;
    }
  }
  if ( (v21 & 0x80000000) != 0 )
  {
    Log_UnistoreHREvent_0(
      v21,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      3457);
    if ( v54 && v53 )
    {
      (*(void (**)(void))(*(_QWORD *)v54 + 80LL))();
      v53 = 0;
    }
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v54);
    if ( hMem )
      LocalFree(hMem);
    if ( v55 )
      LocalFree(v55);
    if ( v17 )
      LocalFree(v17);
    if ( v51 )
      LocalFree(v51);
    if ( !v15 )
      goto LABEL_59;
LABEL_58:
    LocalFree(v15);
LABEL_59:
    if ( v16 )
      LocalFree(v16);
    return v21;
  }
  v24 = v54;
  if ( v54 )
  {
    if ( v53 )
    {
      (*(void (**)(void))(*(_QWORD *)v54 + 80LL))();
      v24 = v54;
      v53 = 0;
    }
    if ( v24 )
      (*(void (__fastcall **)(struct IDBSession *))(*(_QWORD *)v24 + 16LL))(v24);
  }
  v14 = v50;
  v13 = v49;
LABEL_30:
  v25 = v55;
  if ( !v13 )
  {
LABEL_31:
    v26 = (unsigned int *)v51;
    v27 = (char *)hMem;
    if ( a8 && v50 )
    {
      v33 = v57;
      for ( i = 0; (unsigned int)i < v33; a8[v35] = v36 )
      {
        v35 = v26[i];
        v36 = *((_DWORD *)v17 + i);
        i = (unsigned int)(i + 1);
      }
      for ( j = 0; (unsigned int)j < v13; a8[*(unsigned int *)&v27[v38]] = v39 )
      {
        v38 = 4 * j;
        v39 = v9[j];
        if ( v39 >= 0 )
          v39 = *((_DWORD *)v17 + (unsigned int)j + v33);
        j = (unsigned int)(j + 1);
      }
    }
    if ( v9 )
      LocalFree(v9);
    if ( v27 )
      LocalFree(v27);
    if ( v25 )
      LocalFree(v25);
    if ( v17 )
      LocalFree(v17);
    if ( v26 )
      LocalFree(v26);
    if ( v15 )
      LocalFree(v15);
    if ( v16 )
      LocalFree(v16);
    return 0;
  }
  v28 = a8;
  if ( a8 && v14 )
  {
    v43 = LocalAlloc(0x40u, 4LL * v13);
    auto_local_ptr<unsigned long>::operator=(&v59, v43);
    v9 = v59;
    if ( !v59 )
    {
      Log_UnistoreHREvent_0(
        2147942414LL,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
        3465);
      if ( hMem )
        LocalFree(hMem);
      if ( v25 )
        LocalFree(v25);
      if ( v17 )
        LocalFree(v17);
      if ( v51 )
        LocalFree(v51);
      if ( v15 )
LABEL_102:
        LocalFree(v15);
LABEL_103:
      if ( !v16 )
        return 2147942414LL;
LABEL_104:
      LocalFree(v16);
      return 2147942414LL;
    }
    v13 = v49;
    v29 = 0;
    goto LABEL_65;
  }
  v29 = 0;
  if ( v14 )
  {
LABEL_65:
    v28 = v9;
    v30 = (struct _USPROPVAL *)v25;
LABEL_66:
    v31 = DBManager::SetFileStreamProperties(a1, a2, a3, v13, v30, v28);
    v32 = v31;
    if ( v31 >= 0 )
    {
      if ( v29 )
        LocalFree(v29);
      v13 = v49;
      goto LABEL_31;
    }
    Log_UnistoreHREvent_0(
      (unsigned int)v31,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      3498);
    if ( v29 )
      LocalFree(v29);
    if ( v9 )
      LocalFree(v9);
    if ( hMem )
      LocalFree(hMem);
    if ( v25 )
      LocalFree(v25);
    if ( v17 )
      LocalFree(v17);
    if ( v51 )
      LocalFree(v51);
    if ( v15 )
      LocalFree(v15);
    if ( v16 )
      LocalFree(v16);
    return v32;
  }
  if ( !a4 )
  {
    v30 = (struct _USPROPVAL *)a7;
    goto LABEL_66;
  }
  v44 = (char *)LocalAlloc(0, 24LL * v13);
  v45 = 0;
  v29 = v44;
  if ( !v44 )
  {
    Log_UnistoreHREvent_0(
      2147942414LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      3476);
    if ( hMem )
      LocalFree(hMem);
    if ( v25 )
      LocalFree(v25);
    if ( v17 )
      LocalFree(v17);
    if ( v51 )
      LocalFree(v51);
    if ( v15 )
      LocalFree(v15);
    if ( !v16 )
      return 2147942414LL;
    goto LABEL_104;
  }
  v13 = v49;
  while ( 1 )
  {
    if ( (unsigned int)v45 >= v13 )
    {
      v30 = (struct _USPROPVAL *)v29;
      goto LABEL_66;
    }
    v46 = &a7[40 * v45];
    if ( (*((_WORD *)v46 + 3) & 0x800) != 0 )
      break;
    v47 = 3 * v45;
    v45 = (unsigned int)(v45 + 1);
    *(_OWORD *)&v29[8 * v47] = *(_OWORD *)v46;
    *(_QWORD *)&v29[8 * v47 + 16] = *((_QWORD *)v46 + 2);
  }
  Log_UnistoreHREvent_0(
    2147942487LL,
    0,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
    3480);
  LocalFree(v29);
  if ( hMem )
    LocalFree(hMem);
  if ( v25 )
    LocalFree(v25);
  if ( v17 )
    LocalFree(v17);
  if ( v51 )
    LocalFree(v51);
  if ( v15 )
    LocalFree(v15);
  if ( v16 )
    LocalFree(v16);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180029c10  mov     rax, rsp
0x180029c13  mov     [rax+20h], r9d
0x180029c17  mov     [rax+18h], r8
0x180029c1b  mov     [rax+10h], edx
0x180029c1e  mov     [rax+8], rcx
0x180029c22  push    rbp
0x180029c23  push    rsi
0x180029c24  push    rdi
0x180029c25  push    r14
0x180029c27  lea     rbp, [rax-3Fh]
0x180029c2b  sub     rsp, 0D8h
0x180029c32  xor     edi, edi
0x180029c34  mov     r10d, r9d
0x180029c37  mov     [rbp+37h+var_60], edi
0x180029c3a  mov     r11d, edx
0x180029c3d  mov     [rbp+37h+var_58], rdi
0x180029c41  mov     rsi, rcx
0x180029c44  mov     [rbp+37h+var_78], rdi
0x180029c48  mov     r14d, edi
0x180029c4b  mov     [rbp+37h+var_90], edi
0x180029c4e  mov     [rbp+37h+var_50], rdi
0x180029c52  mov     [rbp+37h+var_5C], edi
0x180029c55  test    rcx, rcx
0x180029c58  jz      loc_180029D3A
0x180029c5e  mov     r8d, [rbp+37h+arg_28]; unsigned int
0x180029c62  test    r8d, r8d
0x180029c65  jz      loc_180029D3A
0x180029c6b  mov     rcx, [rbp+37h+arg_30]
0x180029c6f  test    rcx, rcx
0x180029c72  jz      loc_180029D3A
0x180029c78  mov     [rax-28h], rbx
0x180029c7c  lea     rdx, [rbp+37h+var_58]
0x180029c80  test    r9d, r9d
0x180029c83  mov     [rbp+37h+hMem], rdi
0x180029c87  mov     r9, rcx; unsigned __int8 *
0x180029c8a  mov     [rbp+37h+var_68], rdi
0x180029c8e  lea     rax, [rbp+37h+var_78]
0x180029c92  mov     [rbp+37h+var_88], rdi
0x180029c96  cmovz   rax, rdx
0x180029c9a  mov     ecx, r11d; unsigned int
0x180029c9d  lea     rdx, [rbp+37h+hMem]
0x180029ca1  mov     [rsp+0F0h+var_A0], rdx; unsigned int **
0x180029ca6  lea     rdx, [rbp+37h+var_68]
0x180029caa  mov     [rsp+0F0h+var_A8], rdx; struct _USPROPVAL **
0x180029caf  lea     rdx, [rbp+37h+var_90]
0x180029cb3  mov     [rsp+0F0h+var_B0], rdx; unsigned int *
0x180029cb8  lea     rdx, [rbp+37h+var_5C]
0x180029cbc  mov     [rsp+0F0h+var_B8], rdx; unsigned int *
0x180029cc1  lea     rdx, [rbp+37h+var_88]
0x180029cc5  mov     [rsp+0F0h+var_C0], rdx; unsigned int **
0x180029cca  mov     edx, r10d; int
0x180029ccd  mov     [rsp+0F0h+var_C8], rax; unsigned __int8 **
0x180029cd2  lea     rax, [rbp+37h+var_60]
0x180029cd6  mov     [rsp+0F0h+var_D0], rax; unsigned int *
0x180029cdb  call    ?SplitFileStreamPropVals@DBManager@@SAJKHKPEAEPEAKPEAPEAEPEAPEAK11PEAPEAU_USPROPVAL@@3@Z; DBManager::SplitFileStreamPropVals(ulong,int,ulong,uchar *,ulong *,uchar * *,ulong * *,ulong *,ulong *,_USPROPVAL * *,ulong * *)
0x180029ce0  mov     ebx, eax
0x180029ce2  test    eax, eax
0x180029ce4  js      loc_18002A1C8
0x180029cea  mov     r11d, [rbp+37h+var_90]
0x180029cee  mov     ecx, edi
0x180029cf0  mov     [rsp+0F0h+var_28], r12
0x180029cf8  mov     r12, [rbp+37h+var_78]
0x180029cfc  mov     [rsp+0F0h+var_30], r13
0x180029d04  mov     r13, [rbp+37h+var_58]
0x180029d08  mov     [rsp+0F0h+var_38], r15
0x180029d10  mov     r15d, edi
0x180029d13  mov     edi, [rbp+37h+var_60]
0x180029d16  mov     [rbp+37h+var_8C], ecx
0x180029d19  test    edi, edi
0x180029d1b  jnz     loc_18002A06C
0x180029d21  mov     rax, [rbp+37h+arg_10]
0x180029d25  cmp     [rax], ecx
0x180029d27  jnz     loc_180029E5F
0x180029d2d  test    edi, edi
0x180029d2f  jz      loc_18002A07F
0x180029d35  jmp     loc_18002A075
0x180029d3a  mov     r9d, 0D4Ch
0x180029d40  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180029d47  xor     edx, edx
0x180029d49  mov     ecx, 80070057h
0x180029d4e  call    Log_UnistoreHREvent_0
0x180029d53  mov     eax, 80070057h
0x180029d58  add     rsp, 0D8h
0x180029d5f  pop     r14
0x180029d61  pop     rdi
0x180029d62  pop     rsi
0x180029d63  pop     rbp
0x180029d64  retn
0x180029d65  xor     eax, eax
0x180029d67  mov     r13, [rsp+0F0h+var_30]
0x180029d6f  mov     r12, [rsp+0F0h+var_28]
0x180029d77  mov     r15, [rsp+0F0h+var_38]
0x180029d7f  mov     rbx, [rsp+0F0h+var_20]
0x180029d87  add     rsp, 0D8h
0x180029d8e  pop     r14
0x180029d90  pop     rdi
0x180029d91  pop     rsi
0x180029d92  pop     rbp
0x180029d93  retn
0x180029d94  cmp     [rbp+37h+var_78], r14
0x180029d98  jnz     loc_18002A4A7
0x180029d9e  mov     rax, [rcx]
0x180029da1  lea     r9, [rbp+37h+var_78]
0x180029da5  mov     edx, [rbp+37h+arg_8]
0x180029da8  xor     r8d, r8d
0x180029dab  mov     rax, [rax+40h]
0x180029daf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029db4  mov     ebx, eax
0x180029db6  test    eax, eax
0x180029db8  js      loc_18002A4B9
0x180029dbe  mov     rax, [rbp+37h+arg_38]
0x180029dc2  cmp     [rbp+37h+arg_18], r14d
0x180029dc6  jnz     loc_18002A4CB
0x180029dcc  cmp     [rbp+37h+var_8C], r14d
0x180029dd0  mov     rcx, [rbp+37h+arg_10]
0x180029dd4  cmovnz  rax, r15
0x180029dd8  cmp     [rcx], r14d
0x180029ddb  jz      short loc_180029DEE
0x180029ddd  test    edi, edi
0x180029ddf  jz      loc_180029F92
0x180029de5  test    r13, r13
0x180029de8  jz      loc_180029F92
0x180029dee  mov     r8, [rbp+37h+arg_20]; unsigned __int16 *
0x180029df2  mov     rdx, rcx; struct UnifiedStoreCursorLocation *
0x180029df5  mov     rcx, [rbp+37h+var_78]; struct TableHandleInfo *
0x180029df9  mov     r9d, edi; unsigned int
0x180029dfc  mov     [rsp+0F0h+var_C8], rax; unsigned int *
0x180029e01  mov     [rsp+0F0h+var_D0], r13; struct _USPROPVAL *
0x180029e06  call    ?ESEWriteRecordProps@@YAJPEAUTableHandleInfo@@AEAVUnifiedStoreCursorLocation@@PEBGKPEAU_USPROPVAL@@PEAK@Z; ESEWriteRecordProps(TableHandleInfo *,UnifiedStoreCursorLocation &,ushort const *,ulong,_USPROPVAL *,ulong *)
0x180029e0b  mov     ebx, eax
0x180029e0d  test    eax, eax
0x180029e0f  js      loc_18002A4F4
0x180029e15  xor     edi, edi
0x180029e17  mov     ebx, edi
0x180029e19  test    ebx, ebx
0x180029e1b  js      loc_180029EEE
0x180029e21  mov     rcx, [rbp+37h+var_70]
0x180029e25  test    rcx, rcx
0x180029e28  jz      short loc_180029E58
0x180029e2a  mov     rdx, [rbp+37h+var_78]
0x180029e2e  test    rdx, rdx
0x180029e31  jz      short loc_180029E47
0x180029e33  mov     rax, [rcx]
0x180029e36  mov     rax, [rax+50h]
0x180029e3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e3f  mov     rcx, [rbp+37h+var_70]
0x180029e43  mov     [rbp+37h+var_78], rdi
0x180029e47  test    rcx, rcx
0x180029e4a  jz      short loc_180029E58
0x180029e4c  mov     rax, [rcx]
0x180029e4f  mov     rax, [rax+10h]
0x180029e53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e58  mov     ecx, [rbp+37h+var_8C]
0x180029e5b  mov     r11d, [rbp+37h+var_90]
0x180029e5f  mov     rsi, [rbp+37h+var_68]
0x180029e63  test    r11d, r11d
0x180029e66  jnz     loc_180029FB0
0x180029e6c  mov     rdx, [rbp+37h+arg_38]
0x180029e70  mov     rbx, [rbp+37h+var_88]
0x180029e74  mov     rdi, [rbp+37h+hMem]
0x180029e78  test    rdx, rdx
0x180029e7b  jnz     loc_18002A00B
0x180029e81  test    r14, r14
0x180029e84  jz      short loc_180029E8F
0x180029e86  mov     rcx, r14; hMem
0x180029e89  call    cs:__imp_LocalFree
0x180029e8f  test    rdi, rdi
0x180029e92  jz      short loc_180029E9D
0x180029e94  mov     rcx, rdi; hMem
0x180029e97  call    cs:__imp_LocalFree
0x180029e9d  test    rsi, rsi
0x180029ea0  jnz     short loc_180029EE3
0x180029ea2  test    r15, r15
0x180029ea5  jz      short loc_180029EB0
0x180029ea7  mov     rcx, r15; hMem
0x180029eaa  call    cs:__imp_LocalFree
0x180029eb0  test    rbx, rbx
0x180029eb3  jz      short loc_180029EBE
0x180029eb5  mov     rcx, rbx; hMem
0x180029eb8  call    cs:__imp_LocalFree
0x180029ebe  test    r12, r12
0x180029ec1  jz      short loc_180029ECC
0x180029ec3  mov     rcx, r12; hMem
0x180029ec6  call    cs:__imp_LocalFree
0x180029ecc  test    r13, r13
0x180029ecf  jz      loc_180029D65
0x180029ed5  mov     rcx, r13; hMem
0x180029ed8  call    cs:__imp_LocalFree
0x180029ede  jmp     loc_180029D65
0x180029ee3  mov     rcx, rsi; hMem
0x180029ee6  call    cs:__imp_LocalFree
0x180029eec  jmp     short loc_180029EA2
0x180029eee  mov     r9d, 0D81h
0x180029ef4  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180029efb  mov     edx, 1
0x180029f00  mov     ecx, ebx
0x180029f02  call    Log_UnistoreHREvent_0
0x180029f07  mov     rcx, [rbp+37h+var_70]
0x180029f0b  test    rcx, rcx
0x180029f0e  jz      short loc_180029F29
0x180029f10  mov     rdx, [rbp+37h+var_78]
0x180029f14  test    rdx, rdx
0x180029f17  jz      short loc_180029F29
0x180029f19  mov     rax, [rcx]
0x180029f1c  mov     rax, [rax+50h]
0x180029f20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f25  mov     [rbp+37h+var_78], rdi
0x180029f29  lea     rcx, [rbp+37h+var_70]; void *
0x180029f2d  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180029f32  mov     rcx, [rbp+37h+hMem]; hMem
0x180029f36  test    rcx, rcx
0x180029f39  jz      short loc_180029F41
0x180029f3b  call    cs:__imp_LocalFree
0x180029f41  mov     rcx, [rbp+37h+var_68]; hMem
0x180029f45  test    rcx, rcx
0x180029f48  jz      short loc_180029F50
0x180029f4a  call    cs:__imp_LocalFree
0x180029f50  test    r15, r15
0x180029f53  jz      short loc_180029F5E
0x180029f55  mov     rcx, r15; hMem
0x180029f58  call    cs:__imp_LocalFree
0x180029f5e  mov     rcx, [rbp+37h+var_88]; hMem
0x180029f62  test    rcx, rcx
0x180029f65  jnz     short loc_180029F8A
0x180029f67  test    r12, r12
0x180029f6a  jz      short loc_180029F75
0x180029f6c  mov     rcx, r12; hMem
0x180029f6f  call    cs:__imp_LocalFree
0x180029f75  test    r13, r13
0x180029f78  jz      short loc_180029F83
0x180029f7a  mov     rcx, r13; hMem
0x180029f7d  call    cs:__imp_LocalFree
0x180029f83  mov     eax, ebx
0x180029f85  jmp     loc_180029D67
0x180029f8a  call    cs:__imp_LocalFree
0x180029f90  jmp     short loc_180029F67
0x180029f92  mov     r8d, 0D02h
0x180029f98  lea     rdx, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180029f9f  call    Log_AssertionEvent
0x180029fa4  xor     edi, edi
0x180029fa6  mov     ebx, 80070057h
0x180029fab  jmp     loc_180029E19
0x180029fb0  mov     rdi, [rbp+37h+arg_38]
0x180029fb4  test    rdi, rdi
0x180029fb7  jnz     loc_18002A514
0x180029fbd  xor     ebx, ebx
0x180029fbf  test    ecx, ecx
0x180029fc1  jz      loc_18002A521
0x180029fc7  mov     rdi, r14
0x180029fca  mov     rcx, rsi
0x180029fcd  mov     r8, [rbp+37h+arg_10]; struct UnifiedStoreCursorLocation *
0x180029fd1  mov     r9d, r11d; unsigned int
0x180029fd4  mov     edx, [rbp+37h+arg_8]; unsigned int
0x180029fd7  mov     [rsp+0F0h+var_C8], rdi; unsigned int *
0x180029fdc  mov     [rsp+0F0h+var_D0], rcx; struct _USPROPVAL *
0x180029fe1  mov     rcx, [rbp+37h+arg_0]; struct IDBSession *
0x180029fe5  call    ?SetFileStreamProperties@DBManager@@SAJPEAVIDBSession@@KAEBVUnifiedStoreCursorLocation@@KPEAU_USPROPVAL@@PEAK@Z; DBManager::SetFileStreamProperties(IDBSession *,ulong,UnifiedStoreCursorLocation const &,ulong,_USPROPVAL *,ulong *)
0x180029fea  mov     edi, eax
0x180029fec  test    eax, eax
0x180029fee  js      loc_18002A415
0x180029ff4  test    rbx, rbx
0x180029ff7  jz      short loc_18002A002
0x180029ff9  mov     rcx, rbx; hMem
0x180029ffc  call    cs:__imp_LocalFree
0x18002a002  mov     r11d, [rbp+37h+var_90]
0x18002a006  jmp     loc_180029E6C
0x18002a00b  cmp     [rbp+37h+var_8C], 0
0x18002a00f  jz      loc_180029E81
0x18002a015  mov     r9d, [rbp+37h+var_5C]
0x18002a019  xor     r8d, r8d
0x18002a01c  test    r9d, r9d
0x18002a01f  jz      short loc_18002A034
0x18002a021  mov     ecx, [rbx+r8*4]
0x18002a025  mov     eax, [r15+r8*4]
0x18002a029  inc     r8d
0x18002a02c  mov     [rdx+rcx*4], eax
0x18002a02f  cmp     r8d, r9d
0x18002a032  jb      short loc_18002A021
0x18002a034  xor     r8d, r8d
0x18002a037  test    r11d, r11d
0x18002a03a  jz      loc_180029E81
0x18002a040  lea     r10, ds:0[r8*4]
0x18002a048  mov     ecx, [r10+r14]
0x18002a04c  test    ecx, ecx
0x18002a04e  js      short loc_18002A058
0x18002a050  lea     eax, [r8+r9]
0x18002a054  mov     ecx, [r15+rax*4]
0x18002a058  mov     eax, [r10+rdi]
0x18002a05c  inc     r8d
0x18002a05f  mov     [rdx+rax*4], ecx
0x18002a062  cmp     r8d, r11d
0x18002a065  jb      short loc_18002A040
0x18002a067  jmp     loc_180029E81
0x18002a06c  test    r11d, r11d
0x18002a06f  jnz     loc_18002A129
0x18002a075  cmp     [rbp+37h+arg_38], r14
0x18002a079  jnz     loc_18002A136
0x18002a07f  mov     [rbp+37h+var_78], r14
0x18002a083  mov     rcx, rsi
0x18002a086  mov     [rbp+37h+var_70], rsi
  ... truncated ...
```
