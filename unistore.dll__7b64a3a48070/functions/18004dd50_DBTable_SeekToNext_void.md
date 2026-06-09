# DBTable::SeekToNext(void)

- ea: `0x18004dd50`
- end: `0x18004e3de`
- name: `?SeekToNext@DBTable@@UEAAJXZ`
- size: `1678`
- prototype: `__int64 __fastcall(DBTable *__hidden this)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004440`
- `0x1800068f0`
- `0x18000866c`
- `0x1800086bc`
- `0x18000ab20`
- `0x18004bd20`
- `0x18004dd50`
- `0x180050150`
- `0x18006f180`
- `0x1800c5092`
- `0x1800c50aa`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004dd70`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004dd70`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004dfaf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004e065`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004e180`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004e21e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004e3ce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004dfaf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004e065`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004e180`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004e21e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004e3ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004de6c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004de6c`

## string_xrefs

- `0x18004de7d`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18004df3f`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18004df58`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18004e09e`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18004e261`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18004e27a`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18004e3a2`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18004e23f`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18004e29b`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\jetinterophelper.h`
- `0x18004df2d`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\DBSession.h`
- `0x18004e011`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\DBSession.h`
- `0x18004e0be`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\DBSession.h`
- `0x18004e130`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\DBSession.h`
- `0x18004e1ad`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\DBSession.h`
- `0x18004e1cb`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\DBSession.h`
- `0x18004e38b`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\EseHelper.h`

## pseudocode

```c
__int64 __fastcall DBTable::SeekToNext(DBTable *this)
{
  __int64 v2; // rcx
  unsigned int v3; // esi
  unsigned int v4; // r15d
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rcx
  struct TableHandleInfo *v8; // rbx
  struct TableHandleInfo *v9; // rcx
  int v10; // eax
  struct TableHandleInfo *v11; // rsi
  __int64 v12; // rcx
  int v13; // eax
  unsigned int v14; // esi
  int v15; // eax
  unsigned int v16; // esi
  struct TableHandleInfo *v17; // rsi
  __int64 v18; // rax
  unsigned __int64 v19; // r15
  unsigned __int64 v20; // r13
  unsigned __int64 v21; // rcx
  __int64 v22; // r9
  __int64 v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // r9
  struct TableHandleInfo *v26; // rcx
  struct TableHandleInfo *v28; // rcx
  int v29; // eax
  __int64 v30; // r9
  __int64 v31; // rcx
  int v32; // eax
  struct TableHandleInfo *v33; // rcx
  int v34; // eax
  unsigned int v35; // r15d
  __int64 v36; // rax
  unsigned __int64 v37; // r15
  unsigned __int64 v38; // r12
  __int64 v39; // r9
  struct TableHandleInfo *v40; // [rsp+30h] [rbp-20h] BYREF
  __int64 v41; // [rsp+38h] [rbp-18h]
  struct TableHandleInfo *v42[2]; // [rsp+40h] [rbp-10h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v2 = *((_QWORD *)this + 16);
  v3 = *((_DWORD *)this + 31);
  v4 = *((_DWORD *)this + 30);
  v40 = 0;
  v41 = 0;
  *(_OWORD *)v42 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, struct TableHandleInfo **))(*(_QWORD *)v2 + 160LL))(v2, &v40);
  v6 = v5;
  if ( v5 < 0 )
  {
    v30 = 834;
    v31 = (unsigned int)v5;
LABEL_55:
    Log_UnistoreHREvent_0(
      v31,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\DBSession.h",
      v30);
    v25 = 412;
    goto LABEL_28;
  }
  v6 = (*(__int64 (__fastcall **)(struct TableHandleInfo *))(*(_QWORD *)v40 + 32LL))(v40);
  if ( g_breakOnJetError == -1912 )
    Log_AssertionEvent(
      v7,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\jetinterophelper.h",
      25);
  if ( v6 == -2134374536 )
    goto LABEL_7;
  if ( (v6 & 0x80000000) != 0 )
  {
    v30 = 838;
    v31 = v6;
    goto LABEL_55;
  }
  HIDWORD(v41) = 1;
LABEL_7:
  v8 = v40;
  v9 = v42[1];
  LODWORD(v41) = 1;
  if ( v42[1] == v40 )
  {
    v8 = v42[1];
  }
  else
  {
    if ( v40 )
    {
      (*(void (__fastcall **)(struct TableHandleInfo *))(*(_QWORD *)v40 + 8LL))(v40);
      v9 = v42[1];
    }
    if ( v9 )
      (*(void (__fastcall **)(struct TableHandleInfo *))(*(_QWORD *)v9 + 16LL))(v9);
    v9 = v8;
    v42[1] = v8;
  }
  if ( v8 )
  {
    if ( v42[0] )
    {
      auto_TableHandle::Close((auto_TableHandle *)v42);
      v9 = v42[1];
    }
    v10 = (*(__int64 (__fastcall **)(struct TableHandleInfo *, _QWORD, _QWORD, struct TableHandleInfo **))(*(_QWORD *)v9 + 64LL))(
            v9,
            v4,
            v3,
            v42);
    v6 = v10;
    if ( v10 >= 0 )
    {
      v11 = v42[0];
      if ( *((_DWORD *)this + 8) != GetCurrentThreadId() )
        Log_AssertionEvent(
          v12,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
          5961);
      if ( !*((_DWORD *)this + 14) )
      {
        v35 = -2147024871;
        goto LABEL_77;
      }
      v13 = UnistoreJetGotoBookmarkEx(v11, (DBTable *)((char *)this + 56), 0);
      v14 = v13;
      if ( v13 < 0 )
      {
        Log_UnistoreHREvent_0(
          (unsigned int)v13,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
          859);
        if ( v14 != -2147024871 )
        {
          Log_UnistoreHREvent_0(
            v14,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
            5974);
          v35 = v14;
          Log_UnistoreHREvent_0(
            v14,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
            6141);
LABEL_77:
          if ( v42[1] && v42[0] )
          {
            (*(void (**)(void))(*(_QWORD *)v42[1] + 80LL))();
            v42[0] = 0;
          }
          ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v42[1]);
          auto_DBSession::~auto_DBSession((auto_DBSession *)&v40);
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
          return v35;
        }
      }
      v15 = (*(__int64 (__fastcall **)(_QWORD, struct TableHandleInfo *))(**((_QWORD **)this + 14) + 64LL))(
              *((_QWORD *)this + 14),
              v42[0]);
      v16 = v15;
      if ( v15 == -2147024871 )
      {
        *((_DWORD *)this + 14) = 0;
      }
      else
      {
        if ( v15 >= 0 )
        {
          v17 = v42[0];
          if ( !*((_DWORD *)v42[0] + 6) )
          {
            *((_DWORD *)this + 15) = -1;
            v32 = 0;
            goto LABEL_57;
          }
          *((_DWORD *)this + 14) = 0;
          *((_DWORD *)this + 15) = *((_DWORD *)v17 + 7);
          v18 = *((_QWORD *)this + 8);
          v19 = *((_QWORD *)v17 + 5) - *((_QWORD *)v17 + 4);
          v20 = *((_QWORD *)this + 9) - v18;
          if ( v19 > v20 )
          {
            if ( !(unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(
                                     (char *)this + 64,
                                     *((_QWORD *)v17 + 5) - *((_QWORD *)v17 + 4)) )
            {
              v39 = 399;
              goto LABEL_93;
            }
            memset_0(*((void **)this + 9), 0, v19 - v20);
            v21 = v19 + *((_QWORD *)this + 8);
          }
          else
          {
            v21 = v19 + v18;
          }
          *((_QWORD *)this + 9) = v21;
          memcpy_0(*((void **)this + 8), *((const void **)v17 + 4), *((_QWORD *)v17 + 5) - *((_QWORD *)v17 + 4));
          v36 = *((_QWORD *)this + 11);
          v37 = *((_QWORD *)v17 + 8) - *((_QWORD *)v17 + 7);
          v38 = *((_QWORD *)this + 12) - v36;
          if ( v37 <= v38 )
          {
LABEL_90:
            *((_QWORD *)this + 12) = v37 + v36;
            memcpy_0(*((void **)this + 11), *((const void **)v17 + 7), *((_QWORD *)v17 + 8) - *((_QWORD *)v17 + 7));
            v17 = v42[0];
            v32 = 1;
LABEL_57:
            *((_DWORD *)this + 14) = v32;
            v33 = v42[1];
            if ( v42[1] )
            {
              if ( v17 )
              {
                (*(void (__fastcall **)(struct TableHandleInfo *, struct TableHandleInfo *))(*(_QWORD *)v42[1] + 80LL))(
                  v42[1],
                  v17);
                v33 = v42[1];
                v42[0] = 0;
              }
              if ( v33 )
                (*(void (__fastcall **)(struct TableHandleInfo *))(*(_QWORD *)v33 + 16LL))(v33);
            }
            if ( !(_DWORD)v41 )
              goto LABEL_71;
            if ( !v40 )
              Log_AssertionEvent(
                v33,
                "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\DBSession.h",
                850);
            if ( HIDWORD(v41) )
            {
              v34 = (*(__int64 (__fastcall **)(struct TableHandleInfo *))(*(_QWORD *)v40 + 40LL))(v40);
              if ( v34 < 0 )
              {
                Log_UnistoreHREvent_0(
                  (unsigned int)v34,
                  1,
                  "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\DBSession.h",
                  853);
LABEL_71:
                if ( v40 )
                  (*(void (__fastcall **)(struct TableHandleInfo *))(*(_QWORD *)v40 + 16LL))(v40);
                LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
                return 0;
              }
              HIDWORD(v41) = 0;
            }
            if ( v40 )
            {
              (*(void (__fastcall **)(struct TableHandleInfo *))(*(_QWORD *)v40 + 16LL))(v40);
              v40 = 0;
            }
            LODWORD(v41) = 0;
            goto LABEL_71;
          }
          if ( (unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(
                                  (char *)this + 88,
                                  *((_QWORD *)v17 + 8) - *((_QWORD *)v17 + 7)) )
          {
            memset_0(*((void **)this + 12), 0, v37 - v38);
            v36 = *((_QWORD *)this + 11);
            goto LABEL_90;
          }
          v39 = 404;
LABEL_93:
          Log_UnistoreHREvent_0(
            2147942414LL,
            0,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\EseHelper.h",
            v39);
          Log_UnistoreHREvent_0(
            2147942414LL,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
            6151);
          auto_TableHandle::~auto_TableHandle((auto_TableHandle *)v42);
          auto_DBSession::~auto_DBSession((auto_DBSession *)&v40);
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
          return 2147942414LL;
        }
        Log_UnistoreHREvent_0(
          (unsigned int)v15,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
          6148);
      }
      v28 = v42[1];
      if ( v42[1] )
      {
        if ( v42[0] )
        {
          (*(void (**)(void))(*(_QWORD *)v42[1] + 80LL))();
          v28 = v42[1];
          v42[0] = 0;
        }
        if ( v28 )
          (*(void (__fastcall **)(struct TableHandleInfo *))(*(_QWORD *)v28 + 16LL))(v28);
      }
      if ( !(_DWORD)v41 )
        goto LABEL_50;
      if ( !v40 )
        Log_AssertionEvent(
          v28,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\DBSession.h",
          850);
      if ( HIDWORD(v41) )
      {
        v29 = (*(__int64 (__fastcall **)(struct TableHandleInfo *))(*(_QWORD *)v40 + 40LL))(v40);
        if ( v29 < 0 )
        {
          Log_UnistoreHREvent_0(
            (unsigned int)v29,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\DBSession.h",
            853);
LABEL_50:
          if ( v40 )
            (*(void (__fastcall **)(struct TableHandleInfo *))(*(_QWORD *)v40 + 16LL))(v40);
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
          return v16;
        }
        HIDWORD(v41) = 0;
      }
      if ( v40 )
      {
        (*(void (__fastcall **)(struct TableHandleInfo *))(*(_QWORD *)v40 + 16LL))(v40);
        v40 = 0;
      }
      LODWORD(v41) = 0;
      goto LABEL_50;
    }
    v22 = 771;
    v24 = 1;
    v23 = (unsigned int)v10;
  }
  else
  {
    v6 = -2147418113;
    v22 = 764;
    v23 = 2147549183LL;
    v24 = 0;
  }
  Log_UnistoreHREvent_0(
    v23,
    v24,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\DBSession.h",
    v22);
  v25 = 416;
LABEL_28:
  Log_UnistoreHREvent_0(
    v6,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
    v25);
  Log_UnistoreHREvent_0(
    v6,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
    6138);
  v26 = v42[1];
  if ( v42[1] )
  {
    if ( v42[0] )
    {
      (*(void (**)(void))(*(_QWORD *)v42[1] + 80LL))();
      v26 = v42[1];
      v42[0] = 0;
    }
    if ( v26 )
      (*(void (__fastcall **)(struct TableHandleInfo *))(*(_QWORD *)v26 + 16LL))(v26);
  }
  auto_DBSession::~auto_DBSession((auto_DBSession *)&v40);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  return v6;
}

```

## disassembly

```asm
0x18004dd50  mov     [rsp-28h+arg_8], rbx
0x18004dd55  mov     [rsp-28h+arg_10], rsi
0x18004dd5a  push    rbp
0x18004dd5b  push    rdi
0x18004dd5c  push    r12
0x18004dd5e  push    r14
0x18004dd60  push    r15
0x18004dd62  mov     rbp, rsp
0x18004dd65  sub     rsp, 50h
0x18004dd69  mov     rdi, rcx
0x18004dd6c  add     rcx, 10h; lpCriticalSection
0x18004dd70  call    cs:__imp_EnterCriticalSection
0x18004dd76  mov     rcx, [rdi+80h]
0x18004dd7d  lea     rdx, [rbp+var_20]
0x18004dd81  mov     esi, [rdi+7Ch]
0x18004dd84  xor     r12d, r12d
0x18004dd87  mov     r15d, [rdi+78h]
0x18004dd8b  xorps   xmm0, xmm0
0x18004dd8e  mov     [rbp+var_20], r12
0x18004dd92  mov     [rbp+var_18], r12
0x18004dd96  movdqu  xmmword ptr [rbp+var_10], xmm0
0x18004dd9b  mov     rax, [rcx]
0x18004dd9e  mov     rax, [rax+0A0h]
0x18004dda5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ddaa  mov     ebx, eax
0x18004ddac  test    eax, eax
0x18004ddae  js      loc_18004E0B6
0x18004ddb4  mov     rcx, [rbp+var_20]
0x18004ddb8  mov     rax, [rcx]
0x18004ddbb  mov     rax, [rax+20h]
0x18004ddbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ddc4  cmp     cs:?g_breakOnJetError@@3JA, 0FFFFF888h; long g_breakOnJetError
0x18004ddce  mov     ebx, eax
0x18004ddd0  jz      loc_18004E295
0x18004ddd6  cmp     ebx, 80C80778h
0x18004dddc  jz      short loc_18004DDED
0x18004ddde  test    ebx, ebx
0x18004dde0  js      loc_18004E22C
0x18004dde6  mov     dword ptr [rbp+var_18+4], 1
0x18004dded  mov     rbx, [rbp+var_20]
0x18004ddf1  mov     rcx, [rbp+var_10+8]
0x18004ddf5  mov     dword ptr [rbp+var_18], 1
0x18004ddfc  cmp     rcx, rbx
0x18004ddff  jz      loc_18004DFBC
0x18004de05  test    rbx, rbx
0x18004de08  jz      short loc_18004DE1D
0x18004de0a  mov     rax, [rbx]
0x18004de0d  mov     rcx, rbx
0x18004de10  mov     rax, [rax+8]
0x18004de14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004de19  mov     rcx, [rbp+var_10+8]
0x18004de1d  test    rcx, rcx
0x18004de20  jz      short loc_18004DE2E
0x18004de22  mov     rax, [rcx]
0x18004de25  mov     rax, [rax+10h]
0x18004de29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004de2e  mov     rcx, rbx
0x18004de31  mov     [rbp+var_10+8], rbx
0x18004de35  test    rbx, rbx
0x18004de38  jz      loc_18004DF1E
0x18004de3e  cmp     [rbp+var_10], r12
0x18004de42  jnz     loc_18004E2AC
0x18004de48  mov     rax, [rcx]
0x18004de4b  lea     r9, [rbp+var_10]
0x18004de4f  mov     r8d, esi
0x18004de52  mov     edx, r15d
0x18004de55  mov     rax, [rax+40h]
0x18004de59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004de5e  mov     ebx, eax
0x18004de60  test    eax, eax
0x18004de62  js      loc_18004E2BE
0x18004de68  mov     rsi, [rbp+var_10]
0x18004de6c  call    cs:__imp_GetCurrentThreadId
0x18004de72  cmp     [rdi+20h], eax
0x18004de75  jz      short loc_18004DE89
0x18004de77  mov     r8d, 1749h
0x18004de7d  lea     rdx, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18004de84  call    Log_AssertionEvent
0x18004de89  cmp     [rdi+38h], r12d
0x18004de8d  jz      loc_18004E1E0
0x18004de93  xor     r8d, r8d; int *
0x18004de96  lea     rdx, [rdi+38h]; struct UnifiedStoreCursorLocation *
0x18004de9a  mov     rcx, rsi; struct TableHandleInfo *
0x18004de9d  call    ?UnistoreJetGotoBookmarkEx@@YAJPEAUTableHandleInfo@@AEBVUnifiedStoreCursorLocation@@PEAH@Z; UnistoreJetGotoBookmarkEx(TableHandleInfo *,UnifiedStoreCursorLocation const &,int *)
0x18004dea2  mov     esi, eax
0x18004dea4  mov     r15d, 80070019h
0x18004deaa  test    eax, eax
0x18004deac  js      loc_18004E239
0x18004deb2  mov     rcx, [rdi+70h]
0x18004deb6  mov     rdx, [rbp+var_10]
0x18004deba  mov     rax, [rcx]
0x18004debd  mov     rax, [rax+40h]
0x18004dec1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dec6  mov     esi, eax
0x18004dec8  cmp     eax, r15d
0x18004decb  jz      loc_18004DFC4
0x18004ded1  test    eax, eax
0x18004ded3  js      loc_18004E098
0x18004ded9  mov     rsi, [rbp+var_10]
0x18004dedd  mov     [rsp+50h+arg_0], r13
0x18004dee5  cmp     [rsi+18h], r12d
0x18004dee9  jz      loc_18004E0DA
0x18004deef  mov     [rdi+38h], r12d
0x18004def3  mov     eax, [rsi+1Ch]
0x18004def6  mov     [rdi+3Ch], eax
0x18004def9  mov     r15, [rsi+28h]
0x18004defd  mov     rax, [rdi+40h]
0x18004df01  mov     r13, [rdi+48h]
0x18004df05  sub     r15, [rsi+20h]
0x18004df09  sub     r13, rax
0x18004df0c  cmp     r15, r13
0x18004df0f  ja      loc_18004E2D0
0x18004df15  lea     rcx, [r15+rax]
0x18004df19  jmp     loc_18004E2FC
0x18004df1e  mov     ebx, 8000FFFFh
0x18004df23  mov     r9d, 2FCh
0x18004df29  mov     ecx, ebx
0x18004df2b  xor     edx, edx
0x18004df2d  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18004df34  call    Log_UnistoreHREvent_0
0x18004df39  mov     r9d, 1A0h
0x18004df3f  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18004df46  mov     edx, 1
0x18004df4b  mov     ecx, ebx
0x18004df4d  call    Log_UnistoreHREvent_0
0x18004df52  mov     r9d, 17FAh
0x18004df58  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18004df5f  mov     edx, 1
0x18004df64  mov     ecx, ebx
0x18004df66  call    Log_UnistoreHREvent_0
0x18004df6b  mov     rcx, [rbp+var_10+8]
0x18004df6f  test    rcx, rcx
0x18004df72  jz      short loc_18004DFA2
0x18004df74  mov     rdx, [rbp+var_10]
0x18004df78  test    rdx, rdx
0x18004df7b  jz      short loc_18004DF91
0x18004df7d  mov     rax, [rcx]
0x18004df80  mov     rax, [rax+50h]
0x18004df84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004df89  mov     rcx, [rbp+var_10+8]
0x18004df8d  mov     [rbp+var_10], r12
0x18004df91  test    rcx, rcx
0x18004df94  jz      short loc_18004DFA2
0x18004df96  mov     rdx, [rcx]
0x18004df99  mov     rax, [rdx+10h]
0x18004df9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dfa2  lea     rcx, [rbp+var_20]; this
0x18004dfa6  call    ??1auto_DBSession@@QEAA@XZ; auto_DBSession::~auto_DBSession(void)
0x18004dfab  lea     rcx, [rdi+10h]; lpCriticalSection
0x18004dfaf  call    cs:__imp_LeaveCriticalSection
0x18004dfb5  mov     eax, ebx
0x18004dfb7  jmp     loc_18004E06D
0x18004dfbc  mov     rbx, rcx
0x18004dfbf  jmp     loc_18004DE35
0x18004dfc4  mov     [rdi+38h], r12d
0x18004dfc8  mov     rcx, [rbp+var_10+8]
0x18004dfcc  test    rcx, rcx
0x18004dfcf  jz      short loc_18004DFFF
0x18004dfd1  mov     rdx, [rbp+var_10]
0x18004dfd5  test    rdx, rdx
0x18004dfd8  jz      short loc_18004DFEE
0x18004dfda  mov     rax, [rcx]
0x18004dfdd  mov     rax, [rax+50h]
0x18004dfe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dfe6  mov     rcx, [rbp+var_10+8]
0x18004dfea  mov     [rbp+var_10], r12
0x18004dfee  test    rcx, rcx
0x18004dff1  jz      short loc_18004DFFF
0x18004dff3  mov     rax, [rcx]
0x18004dff6  mov     rax, [rax+10h]
0x18004dffa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dfff  cmp     dword ptr [rbp+var_18], r12d
0x18004e003  jz      short loc_18004E04C
0x18004e005  cmp     [rbp+var_20], r12
0x18004e009  jnz     short loc_18004E01D
0x18004e00b  mov     r8d, 352h
0x18004e011  lea     rdx, aOnecoreuapBase_36; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18004e018  call    Log_AssertionEvent
0x18004e01d  cmp     dword ptr [rbp+var_18+4], r12d
0x18004e021  jz      short loc_18004E03F
0x18004e023  mov     rcx, [rbp+var_20]
0x18004e027  mov     rax, [rcx]
0x18004e02a  mov     rax, [rax+28h]
0x18004e02e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e033  test    eax, eax
0x18004e035  js      loc_18004E1A7
0x18004e03b  mov     dword ptr [rbp+var_18+4], r12d
0x18004e03f  mov     rcx, [rbp+var_20]
0x18004e043  test    rcx, rcx
0x18004e046  jnz     short loc_18004E086
0x18004e048  mov     dword ptr [rbp+var_18], r12d
0x18004e04c  mov     rcx, [rbp+var_20]
0x18004e050  test    rcx, rcx
0x18004e053  jz      short loc_18004E061
0x18004e055  mov     rax, [rcx]
0x18004e058  mov     rax, [rax+10h]
0x18004e05c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e061  lea     rcx, [rdi+10h]; lpCriticalSection
0x18004e065  call    cs:__imp_LeaveCriticalSection
0x18004e06b  mov     eax, esi
0x18004e06d  lea     r11, [rsp+50h+var_s0]
0x18004e072  mov     rbx, [r11+38h]
0x18004e076  mov     rsi, [r11+40h]
0x18004e07a  mov     rsp, r11
0x18004e07d  pop     r15
0x18004e07f  pop     r14
0x18004e081  pop     r12
0x18004e083  pop     rdi
0x18004e084  pop     rbp
0x18004e085  retn
0x18004e086  mov     rax, [rcx]
0x18004e089  mov     rax, [rax+10h]
0x18004e08d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e092  mov     [rbp+var_20], r12
0x18004e096  jmp     short loc_18004E048
0x18004e098  mov     r9d, 1804h
0x18004e09e  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18004e0a5  mov     edx, 1
0x18004e0aa  mov     ecx, esi
0x18004e0ac  call    Log_UnistoreHREvent_0
0x18004e0b1  jmp     loc_18004DFC8
0x18004e0b6  mov     r9d, 342h
0x18004e0bc  mov     ecx, eax
0x18004e0be  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18004e0c5  mov     edx, 1
0x18004e0ca  call    Log_UnistoreHREvent_0
0x18004e0cf  mov     r9d, 19Ch
0x18004e0d5  jmp     loc_18004DF3F
0x18004e0da  mov     dword ptr [rdi+3Ch], 0FFFFFFFFh
0x18004e0e1  mov     eax, r12d
0x18004e0e4  mov     [rdi+38h], eax
0x18004e0e7  mov     rcx, [rbp+var_10+8]
0x18004e0eb  test    rcx, rcx
0x18004e0ee  jz      short loc_18004E11D
0x18004e0f0  test    rsi, rsi
0x18004e0f3  jz      short loc_18004E10C
0x18004e0f5  mov     rax, [rcx]
0x18004e0f8  mov     rdx, rsi
0x18004e0fb  mov     rax, [rax+50h]
0x18004e0ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e104  mov     rcx, [rbp+var_10+8]
0x18004e108  mov     [rbp+var_10], r12
0x18004e10c  test    rcx, rcx
0x18004e10f  jz      short loc_18004E11D
0x18004e111  mov     rax, [rcx]
0x18004e114  mov     rax, [rax+10h]
0x18004e118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e11d  cmp     dword ptr [rbp+var_18], 0
0x18004e121  jz      short loc_18004E167
0x18004e123  cmp     [rbp+var_20], 0
0x18004e128  jnz     short loc_18004E13C
0x18004e12a  mov     r8d, 352h
0x18004e130  lea     rdx, aOnecoreuapBase_36; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18004e137  call    Log_AssertionEvent
0x18004e13c  cmp     dword ptr [rbp+var_18+4], 0
0x18004e140  jz      short loc_18004E15A
0x18004e142  mov     rcx, [rbp+var_20]
0x18004e146  mov     rax, [rcx]
0x18004e149  mov     rax, [rax+28h]
0x18004e14d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e152  test    eax, eax
0x18004e154  js      short loc_18004E1C5
0x18004e156  mov     dword ptr [rbp+var_18+4], r12d
0x18004e15a  mov     rcx, [rbp+var_20]
0x18004e15e  test    rcx, rcx
0x18004e161  jnz     short loc_18004E195
0x18004e163  mov     dword ptr [rbp+var_18], r12d
0x18004e167  mov     rcx, [rbp+var_20]
0x18004e16b  test    rcx, rcx
0x18004e16e  jz      short loc_18004E17C
0x18004e170  mov     rax, [rcx]
0x18004e173  mov     rax, [rax+10h]
0x18004e177  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e17c  lea     rcx, [rdi+10h]; lpCriticalSection
0x18004e180  call    cs:__imp_LeaveCriticalSection
0x18004e186  xor     eax, eax
0x18004e188  mov     r13, [rsp+50h+arg_0]
0x18004e190  jmp     loc_18004E06D
0x18004e195  mov     rax, [rcx]
0x18004e198  mov     rax, [rax+10h]
0x18004e19c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e1a1  mov     [rbp+var_20], r12
0x18004e1a5  jmp     short loc_18004E163
0x18004e1a7  mov     r9d, 355h
0x18004e1ad  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18004e1b4  mov     edx, 1
0x18004e1b9  mov     ecx, eax
0x18004e1bb  call    Log_UnistoreHREvent_0
0x18004e1c0  jmp     loc_18004E04C
0x18004e1c5  mov     r9d, 355h
0x18004e1cb  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18004e1d2  mov     edx, 1
0x18004e1d7  mov     ecx, eax
0x18004e1d9  call    Log_UnistoreHREvent_0
0x18004e1de  jmp     short loc_18004E167
0x18004e1e0  mov     r15d, 80070019h
0x18004e1e6  mov     rcx, [rbp+var_10+8]
0x18004e1ea  test    rcx, rcx
0x18004e1ed  jz      short loc_18004E208
0x18004e1ef  mov     rdx, [rbp+var_10]
  ... truncated ...
```
