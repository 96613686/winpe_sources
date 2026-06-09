# DBTable::SeekFirstRow(__MIDL___MIDL_itf_unistore_0000_0000_0002,ulong,ulong,_USPROPVAL const *,IDBRow * *)

- ea: `0x1800091f0`
- end: `0x180009a3d`
- name: `?SeekFirstRow@DBTable@@UEAAJW4__MIDL___MIDL_itf_unistore_0000_0000_0002@@KKPEBU_USPROPVAL@@PEAPEAVIDBRow@@@Z`
- size: `2125`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004440`
- `0x1800068f0`
- `0x180008638`
- `0x18000866c`
- `0x1800086bc`
- `0x1800091f0`
- `0x18004bc70`
- `0x18004bd20`
- `0x180050150`
- `0x18006f180`
- `0x180078a4c`
- `0x1800c5092`
- `0x1800c50aa`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009214`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009214`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000953b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009562`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800097f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009886`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000953b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009562`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800097f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009886`

## string_xrefs

- `0x1800093b4`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x1800093cd`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180009581`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x1800095e1`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x1800097ab`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x1800097c4`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180009817`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180009a19`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18000989c`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\jetinterophelper.h`
- `0x1800093a2`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\DBSession.h`
- `0x18000942e`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\DBSession.h`
- `0x1800094e1`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\DBSession.h`
- `0x1800096b8`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\DBSession.h`
- `0x180009725`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\DBSession.h`
- `0x180009747`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\DBSession.h`
- `0x180009765`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\DBSession.h`
- `0x180009783`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\DBSession.h`
- `0x180009800`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\EseHelper.h`
- `0x180009a02`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\EseHelper.h`

## pseudocode

```c
__int64 __fastcall DBTable::SeekFirstRow(__int64 a1, unsigned int a2, unsigned int a3, int a4, __int64 a5, _QWORD *a6)
{
  __int64 v10; // rcx
  unsigned int v11; // r13d
  int v12; // eax
  unsigned int v13; // ebx
  __int64 v14; // rcx
  __int64 v15; // rbx
  __int64 v16; // rcx
  int v17; // eax
  int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // rbx
  __int64 v21; // rax
  unsigned __int64 v22; // rsi
  unsigned __int64 v23; // r12
  unsigned __int64 v24; // rcx
  __int64 v25; // r9
  __int64 v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // r9
  __int64 v29; // rcx
  int v30; // eax
  void (*v31)(void); // rax
  __int64 v32; // rcx
  int v33; // eax
  int v35; // eax
  _QWORD *v36; // r14
  int v37; // r12d
  __int64 v38; // rsi
  _DWORD *v39; // rax
  _DWORD *v40; // rbx
  __int64 v41; // rax
  int v42; // eax
  __int64 v43; // rcx
  int v44; // eax
  __int64 v45; // r9
  __int64 v46; // rcx
  __int64 v47; // rcx
  __int64 v48; // rax
  unsigned __int64 v49; // r14
  unsigned __int64 v50; // r12
  __int64 v51; // r9
  __int64 v52; // rax
  unsigned __int64 v53; // rsi
  unsigned __int64 v54; // r13
  __int64 v55; // [rsp+40h] [rbp-28h] BYREF
  __int64 v56; // [rsp+48h] [rbp-20h]
  __int128 v57; // [rsp+50h] [rbp-18h] BYREF
  _DWORD *v58; // [rsp+B0h] [rbp+48h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  v10 = *(_QWORD *)(a1 + 128);
  v11 = *(_DWORD *)(a1 + 124);
  v55 = 0;
  v56 = 0;
  LODWORD(v58) = *(_DWORD *)(a1 + 120);
  v57 = 0;
  v12 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v10 + 160LL))(v10, &v55);
  v13 = v12;
  if ( v12 < 0 )
  {
    v45 = 834;
    v46 = (unsigned int)v12;
    goto LABEL_89;
  }
  v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v55 + 32LL))(v55);
  if ( g_breakOnJetError == -1912 )
    Log_AssertionEvent(
      v14,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\jetinterophelper.h",
      25);
  if ( v13 != -2134374536 )
  {
    if ( (v13 & 0x80000000) == 0 )
    {
      HIDWORD(v56) = 1;
      goto LABEL_7;
    }
    v45 = 838;
    v46 = v13;
LABEL_89:
    Log_UnistoreHREvent_0(
      v46,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\DBSession.h",
      v45);
    v28 = 412;
LABEL_25:
    Log_UnistoreHREvent_0(
      v13,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      v28);
    Log_UnistoreHREvent_0(
      v13,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      5924);
    v29 = *((_QWORD *)&v57 + 1);
    if ( *((_QWORD *)&v57 + 1) )
    {
      if ( (_QWORD)v57 )
      {
        (*(void (**)(void))(**((_QWORD **)&v57 + 1) + 80LL))();
        v29 = *((_QWORD *)&v57 + 1);
        *(_QWORD *)&v57 = 0;
      }
      if ( v29 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    }
    if ( (_DWORD)v56 )
    {
      if ( !v55 )
        Log_AssertionEvent(
          v29,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\DBSession.h",
          850);
      if ( HIDWORD(v56) )
      {
        v30 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v55 + 40LL))(v55);
        if ( v30 < 0 )
        {
          Log_UnistoreHREvent_0(
            (unsigned int)v30,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\DBSession.h",
            853);
          goto LABEL_39;
        }
        HIDWORD(v56) = 0;
      }
      if ( v55 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
        v55 = 0;
      }
      LODWORD(v56) = 0;
    }
LABEL_39:
    if ( v55 )
    {
      v31 = *(void (**)(void))(*(_QWORD *)v55 + 16LL);
LABEL_58:
      v31();
    }
LABEL_59:
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
    return v13;
  }
LABEL_7:
  v15 = v55;
  v16 = *((_QWORD *)&v57 + 1);
  LODWORD(v56) = 1;
  if ( *((_QWORD *)&v57 + 1) == v55 )
  {
    v15 = *((_QWORD *)&v57 + 1);
  }
  else
  {
    if ( v55 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 8LL))(v55);
      v16 = *((_QWORD *)&v57 + 1);
    }
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    v16 = v15;
    *((_QWORD *)&v57 + 1) = v15;
  }
  if ( !v15 )
  {
    v13 = -2147418113;
    v25 = 764;
    v26 = 2147549183LL;
    v27 = 0;
LABEL_24:
    Log_UnistoreHREvent_0(
      v26,
      v27,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\DBSession.h",
      v25);
    v28 = 416;
    goto LABEL_25;
  }
  if ( (_QWORD)v57 )
  {
    auto_TableHandle::Close((auto_TableHandle *)&v57);
    v16 = *((_QWORD *)&v57 + 1);
  }
  v17 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int128 *))(*(_QWORD *)v16 + 64LL))(
          v16,
          (unsigned int)v58,
          v11,
          &v57);
  v13 = v17;
  if ( v17 < 0 )
  {
    v25 = 771;
    v27 = 1;
    v26 = (unsigned int)v17;
    goto LABEL_24;
  }
  v18 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, int, __int64))(**(_QWORD **)(a1 + 112) + 24LL))(
          *(_QWORD *)(a1 + 112),
          v57,
          a2,
          a3,
          a4,
          a5);
  v13 = v18;
  if ( v18 == -2147024871 )
  {
    *(_DWORD *)(a1 + 56) = 0;
    goto LABEL_42;
  }
  if ( v18 < 0 )
  {
    Log_UnistoreHREvent_0(
      (unsigned int)v18,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      5936);
LABEL_42:
    v32 = *((_QWORD *)&v57 + 1);
    if ( *((_QWORD *)&v57 + 1) )
    {
      if ( (_QWORD)v57 )
      {
        (*(void (**)(void))(**((_QWORD **)&v57 + 1) + 80LL))();
        v32 = *((_QWORD *)&v57 + 1);
        *(_QWORD *)&v57 = 0;
      }
      if ( v32 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    }
    if ( (_DWORD)v56 )
    {
      if ( !v55 )
        Log_AssertionEvent(
          v32,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\DBSession.h",
          850);
      if ( HIDWORD(v56) )
      {
        v33 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v55 + 40LL))(v55);
        if ( v33 < 0 )
        {
          Log_UnistoreHREvent_0(
            (unsigned int)v33,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\DBSession.h",
            853);
          goto LABEL_56;
        }
        HIDWORD(v56) = 0;
      }
      if ( v55 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
        v55 = 0;
      }
      LODWORD(v56) = 0;
    }
LABEL_56:
    if ( v55 )
    {
      v31 = *(void (**)(void))(*(_QWORD *)v55 + 16LL);
      goto LABEL_58;
    }
    goto LABEL_59;
  }
  v20 = v57;
  if ( !*(_DWORD *)(v57 + 24) )
  {
    *(_DWORD *)(a1 + 60) = -1;
    v35 = 0;
    goto LABEL_66;
  }
  *(_DWORD *)(a1 + 56) = 0;
  *(_DWORD *)(a1 + 60) = *(_DWORD *)(v20 + 28);
  v21 = *(_QWORD *)(a1 + 64);
  v22 = *(_QWORD *)(v20 + 40) - *(_QWORD *)(v20 + 32);
  v23 = *(_QWORD *)(a1 + 72) - v21;
  if ( v22 > v23 )
  {
    if ( !(unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(
                             a1 + 64,
                             *(_QWORD *)(v20 + 40) - *(_QWORD *)(v20 + 32)) )
    {
      v51 = 399;
      goto LABEL_96;
    }
    memset_0(*(void **)(a1 + 72), 0, v22 - v23);
    v24 = v22 + *(_QWORD *)(a1 + 64);
  }
  else
  {
    v24 = v22 + v21;
  }
  *(_QWORD *)(a1 + 72) = v24;
  memcpy_0(*(void **)(a1 + 64), *(const void **)(v20 + 32), *(_QWORD *)(v20 + 40) - *(_QWORD *)(v20 + 32));
  v48 = *(_QWORD *)(a1 + 88);
  v49 = *(_QWORD *)(v20 + 64) - *(_QWORD *)(v20 + 56);
  v50 = *(_QWORD *)(a1 + 96) - v48;
  if ( v49 <= v50 )
  {
LABEL_110:
    *(_QWORD *)(a1 + 96) = v49 + v48;
    memcpy_0(*(void **)(a1 + 88), *(const void **)(v20 + 56), *(_QWORD *)(v20 + 64) - *(_QWORD *)(v20 + 56));
    v35 = 1;
LABEL_66:
    v36 = a6;
    *(_DWORD *)(a1 + 56) = v35;
    if ( !v36 )
      goto LABEL_75;
    v37 = *(_DWORD *)(a1 + 120);
    v38 = *(_QWORD *)(a1 + 128);
    if ( !v35 )
      Log_AssertionEvent(
        v19,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
        6739);
    v39 = operator new(0x58u);
    v40 = v39;
    if ( v39 )
    {
      v39[2] = 0;
      *(_QWORD *)v39 = &DBRow::`vftable';
      *((_QWORD *)v39 + 2) = v38;
      if ( v38 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 8LL))(v38);
      v40[6] = v37;
      v40[7] = -1;
      UnifiedStoreCursorLocation::UnifiedStoreCursorLocation((UnifiedStoreCursorLocation *)(v40 + 8));
      v41 = *(_QWORD *)v40;
      v58 = v40;
      (*(void (__fastcall **)(_DWORD *))(v41 + 8))(v40);
      if ( !*(_DWORD *)(a1 + 56) )
      {
        v40[9] = -1;
        v42 = 0;
LABEL_74:
        v40[8] = v42;
        *v36 = v40;
LABEL_75:
        v43 = *((_QWORD *)&v57 + 1);
        if ( *((_QWORD *)&v57 + 1) )
        {
          if ( (_QWORD)v57 )
          {
            (*(void (**)(void))(**((_QWORD **)&v57 + 1) + 80LL))();
            v43 = *((_QWORD *)&v57 + 1);
            *(_QWORD *)&v57 = 0;
          }
          if ( v43 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
        }
        if ( !(_DWORD)v56 )
          goto LABEL_61;
        if ( !v55 )
          Log_AssertionEvent(
            v43,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\DBSession.h",
            850);
        if ( HIDWORD(v56) )
        {
          v44 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v55 + 40LL))(v55);
          if ( v44 < 0 )
          {
            Log_UnistoreHREvent_0(
              (unsigned int)v44,
              1,
              "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\DBSession.h",
              853);
LABEL_61:
            if ( v55 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
            LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
            return 0;
          }
          HIDWORD(v56) = 0;
        }
        if ( v55 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
          v55 = 0;
        }
        LODWORD(v56) = 0;
        goto LABEL_61;
      }
      v40[8] = 0;
      v40[9] = *(_DWORD *)(a1 + 60);
      v52 = *((_QWORD *)v40 + 5);
      v53 = *(_QWORD *)(a1 + 72) - *(_QWORD *)(a1 + 64);
      v54 = *((_QWORD *)v40 + 6) - v52;
      if ( v53 <= v54 )
      {
LABEL_116:
        *((_QWORD *)v40 + 6) = v53 + v52;
        memcpy_0(*((void **)v40 + 5), *(const void **)(a1 + 64), *(_QWORD *)(a1 + 72) - *(_QWORD *)(a1 + 64));
        v42 = 1;
        goto LABEL_74;
      }
      if ( (unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(
                              v40 + 10,
                              *(_QWORD *)(a1 + 72) - *(_QWORD *)(a1 + 64)) )
      {
        memset_0(*((void **)v40 + 6), 0, v53 - v54);
        v52 = *((_QWORD *)v40 + 5);
        goto LABEL_116;
      }
      Log_UnistoreHREvent_0(
        2147942414LL,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\EseHelper.h",
        399);
      Log_UnistoreHREvent_0(
        2147942414LL,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
        6744);
      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v58);
    }
    else
    {
      Log_UnistoreHREvent_0(
        2147942414LL,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
        6742);
    }
    Log_UnistoreHREvent_0(
      2147942414LL,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      5943);
    auto_TableHandle::~auto_TableHandle((auto_TableHandle *)&v57);
    auto_DBSession::~auto_DBSession((auto_DBSession *)&v55);
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
    return 2147942414LL;
  }
  if ( (unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(
                          a1 + 88,
                          *(_QWORD *)(v20 + 64) - *(_QWORD *)(v20 + 56)) )
  {
    memset_0(*(void **)(a1 + 96), 0, v49 - v50);
    v48 = *(_QWORD *)(a1 + 88);
    goto LABEL_110;
  }
  v51 = 404;
LABEL_96:
  Log_UnistoreHREvent_0(
    2147942414LL,
    0,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\EseHelper.h",
    v51);
  Log_UnistoreHREvent_0(
    2147942414LL,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
    5939);
  v47 = *((_QWORD *)&v57 + 1);
  if ( *((_QWORD *)&v57 + 1) )
  {
    if ( (_QWORD)v57 )
    {
      (*(void (**)(void))(**((_QWORD **)&v57 + 1) + 80LL))();
      v47 = *((_QWORD *)&v57 + 1);
      *(_QWORD *)&v57 = 0;
    }
    if ( v47 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
  }
  auto_DBSession::Close((auto_DBSession *)&v55);
  if ( v55 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  return 2147942414LL;
}

```

## disassembly

```asm
0x1800091f0  push    rbp
0x1800091f2  push    rbx
0x1800091f3  push    rsi
0x1800091f4  push    rdi
0x1800091f5  push    r12
0x1800091f7  push    r13
0x1800091f9  push    r14
0x1800091fb  push    r15
0x1800091fd  mov     rbp, rsp
0x180009200  sub     rsp, 68h
0x180009204  mov     rdi, rcx
0x180009207  mov     esi, r9d
0x18000920a  add     rcx, 10h; lpCriticalSection
0x18000920e  mov     r14d, r8d
0x180009211  mov     r12d, edx
0x180009214  call    cs:__imp_EnterCriticalSection
0x18000921a  mov     rcx, [rdi+80h]
0x180009221  lea     rdx, [rbp+var_28]
0x180009225  mov     r13d, [rdi+7Ch]
0x180009229  xor     eax, eax
0x18000922b  mov     [rbp+var_28], rax
0x18000922f  xorps   xmm0, xmm0
0x180009232  mov     [rbp+var_20], rax
0x180009236  mov     eax, [rdi+78h]
0x180009239  mov     dword ptr [rbp+arg_0], eax
0x18000923c  movdqu  [rbp+var_18], xmm0
0x180009241  mov     rax, [rcx]
0x180009244  mov     rax, [rax+0A0h]
0x18000924b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009250  mov     ebx, eax
0x180009252  test    eax, eax
0x180009254  js      loc_18000971D
0x18000925a  mov     rcx, [rbp+var_28]
0x18000925e  mov     rax, [rcx]
0x180009261  mov     rax, [rax+20h]
0x180009265  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000926a  cmp     cs:?g_breakOnJetError@@3JA, 0FFFFF888h; long g_breakOnJetError
0x180009274  mov     ebx, eax
0x180009276  jz      loc_180009896
0x18000927c  cmp     ebx, 80C80778h
0x180009282  jz      short loc_180009293
0x180009284  test    ebx, ebx
0x180009286  js      loc_18000979B
0x18000928c  mov     dword ptr [rbp+var_20+4], 1
0x180009293  mov     rbx, [rbp+var_28]
0x180009297  mov     rcx, qword ptr [rbp+var_18+8]
0x18000929b  mov     dword ptr [rbp+var_20], 1
0x1800092a2  cmp     rcx, rbx
0x1800092a5  jz      loc_18000938B
0x1800092ab  test    rbx, rbx
0x1800092ae  jz      short loc_1800092C3
0x1800092b0  mov     rax, [rbx]
0x1800092b3  mov     rcx, rbx
0x1800092b6  mov     rax, [rax+8]
0x1800092ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092bf  mov     rcx, qword ptr [rbp+var_18+8]
0x1800092c3  test    rcx, rcx
0x1800092c6  jz      short loc_1800092D4
0x1800092c8  mov     rax, [rcx]
0x1800092cb  mov     rax, [rax+10h]
0x1800092cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092d4  mov     rcx, rbx
0x1800092d7  mov     qword ptr [rbp+var_18+8], rbx
0x1800092db  test    rbx, rbx
0x1800092de  jz      loc_180009393
0x1800092e4  cmp     qword ptr [rbp+var_18], 0
0x1800092e9  jnz     loc_1800098AD
0x1800092ef  mov     rax, [rcx]
0x1800092f2  lea     r9, [rbp+var_18]
0x1800092f6  mov     edx, dword ptr [rbp+arg_0]
0x1800092f9  mov     r8d, r13d
0x1800092fc  mov     rax, [rax+40h]
0x180009300  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009305  mov     ebx, eax
0x180009307  test    eax, eax
0x180009309  js      loc_1800098BF
0x18000930f  mov     r8, [rbp+arg_20]
0x180009313  mov     r9d, r14d
0x180009316  mov     rcx, [rdi+70h]
0x18000931a  mov     rdx, qword ptr [rbp+var_18]
0x18000931e  mov     [rsp+68h+var_40], r8
0x180009323  mov     r8d, r12d
0x180009326  mov     [rsp+68h+var_48], esi
0x18000932a  mov     rax, [rcx]
0x18000932d  mov     rax, [rax+18h]
0x180009331  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009336  mov     ebx, eax
0x180009338  cmp     eax, 80070019h
0x18000933d  jz      loc_18000948C
0x180009343  test    eax, eax
0x180009345  js      loc_18000957B
0x18000934b  mov     rbx, qword ptr [rbp+var_18]
0x18000934f  xor     r13d, r13d
0x180009352  cmp     [rbx+18h], r13d
0x180009356  jz      loc_1800095B2
0x18000935c  mov     [rdi+38h], r13d
0x180009360  mov     eax, [rbx+1Ch]
0x180009363  mov     [rdi+3Ch], eax
0x180009366  mov     rsi, [rbx+28h]
0x18000936a  mov     rax, [rdi+40h]
0x18000936e  mov     r12, [rdi+48h]
0x180009372  sub     rsi, [rbx+20h]
0x180009376  sub     r12, rax
0x180009379  cmp     rsi, r12
0x18000937c  ja      loc_1800098D1
0x180009382  lea     rcx, [rsi+rax]
0x180009386  jmp     loc_1800098FD
0x18000938b  mov     rbx, rcx
0x18000938e  jmp     loc_1800092DB
0x180009393  mov     ebx, 8000FFFFh
0x180009398  mov     r9d, 2FCh
0x18000939e  mov     ecx, ebx
0x1800093a0  xor     edx, edx
0x1800093a2  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800093a9  call    Log_UnistoreHREvent_0
0x1800093ae  mov     r9d, 1A0h
0x1800093b4  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800093bb  mov     edx, 1
0x1800093c0  mov     ecx, ebx
0x1800093c2  call    Log_UnistoreHREvent_0
0x1800093c7  mov     r9d, 1724h
0x1800093cd  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800093d4  mov     edx, 1
0x1800093d9  mov     ecx, ebx
0x1800093db  call    Log_UnistoreHREvent_0
0x1800093e0  mov     rcx, qword ptr [rbp+var_18+8]
0x1800093e4  test    rcx, rcx
0x1800093e7  jz      short loc_18000941B
0x1800093e9  mov     rdx, qword ptr [rbp+var_18]
0x1800093ed  test    rdx, rdx
0x1800093f0  jz      short loc_18000940A
0x1800093f2  mov     rax, [rcx]
0x1800093f5  mov     rax, [rax+50h]
0x1800093f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093fe  mov     rcx, qword ptr [rbp+var_18+8]
0x180009402  mov     qword ptr [rbp+var_18], 0
0x18000940a  test    rcx, rcx
0x18000940d  jz      short loc_18000941B
0x18000940f  mov     rax, [rcx]
0x180009412  mov     rax, [rax+10h]
0x180009416  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000941b  cmp     dword ptr [rbp+var_20], 0
0x18000941f  jz      short loc_180009473
0x180009421  cmp     [rbp+var_28], 0
0x180009426  jnz     short loc_18000943A
0x180009428  mov     r8d, 352h
0x18000942e  lea     rdx, aOnecoreuapBase_36; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180009435  call    Log_AssertionEvent
0x18000943a  cmp     dword ptr [rbp+var_20+4], 0
0x18000943e  jz      short loc_18000945F
0x180009440  mov     rcx, [rbp+var_28]
0x180009444  mov     rax, [rcx]
0x180009447  mov     rax, [rax+28h]
0x18000944b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009450  test    eax, eax
0x180009452  js      loc_18000977D
0x180009458  mov     dword ptr [rbp+var_20+4], 0
0x18000945f  mov     rcx, [rbp+var_28]
0x180009463  test    rcx, rcx
0x180009466  jnz     loc_180009704
0x18000946c  mov     dword ptr [rbp+var_20], 0
0x180009473  mov     rcx, [rbp+var_28]
0x180009477  test    rcx, rcx
0x18000947a  jz      loc_180009537
0x180009480  mov     rdx, [rcx]
0x180009483  mov     rax, [rdx+10h]
0x180009487  jmp     loc_180009532
0x18000948c  mov     dword ptr [rdi+38h], 0
0x180009493  mov     rcx, qword ptr [rbp+var_18+8]
0x180009497  test    rcx, rcx
0x18000949a  jz      short loc_1800094CE
0x18000949c  mov     rdx, qword ptr [rbp+var_18]
0x1800094a0  test    rdx, rdx
0x1800094a3  jz      short loc_1800094BD
0x1800094a5  mov     rax, [rcx]
0x1800094a8  mov     rax, [rax+50h]
0x1800094ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094b1  mov     rcx, qword ptr [rbp+var_18+8]
0x1800094b5  mov     qword ptr [rbp+var_18], 0
0x1800094bd  test    rcx, rcx
0x1800094c0  jz      short loc_1800094CE
0x1800094c2  mov     rax, [rcx]
0x1800094c5  mov     rax, [rax+10h]
0x1800094c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094ce  cmp     dword ptr [rbp+var_20], 0
0x1800094d2  jz      short loc_180009522
0x1800094d4  cmp     [rbp+var_28], 0
0x1800094d9  jnz     short loc_1800094ED
0x1800094db  mov     r8d, 352h
0x1800094e1  lea     rdx, aOnecoreuapBase_36; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800094e8  call    Log_AssertionEvent
0x1800094ed  cmp     dword ptr [rbp+var_20+4], 0
0x1800094f1  jz      short loc_180009512
0x1800094f3  mov     rcx, [rbp+var_28]
0x1800094f7  mov     rax, [rcx]
0x1800094fa  mov     rax, [rax+28h]
0x1800094fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009503  test    eax, eax
0x180009505  js      loc_18000975F
0x18000950b  mov     dword ptr [rbp+var_20+4], 0
0x180009512  mov     rcx, [rbp+var_28]
0x180009516  test    rcx, rcx
0x180009519  jnz     short loc_180009599
0x18000951b  mov     dword ptr [rbp+var_20], 0
0x180009522  mov     rcx, [rbp+var_28]
0x180009526  test    rcx, rcx
0x180009529  jz      short loc_180009537
0x18000952b  mov     rax, [rcx]
0x18000952e  mov     rax, [rax+10h]
0x180009532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009537  lea     rcx, [rdi+10h]; lpCriticalSection
0x18000953b  call    cs:__imp_LeaveCriticalSection
0x180009541  mov     eax, ebx
0x180009543  jmp     short loc_18000956A
0x180009545  mov     dword ptr [rbp+var_20], r13d
0x180009549  mov     rcx, [rbp+var_28]
0x18000954d  test    rcx, rcx
0x180009550  jz      short loc_18000955E
0x180009552  mov     rax, [rcx]
0x180009555  mov     rax, [rax+10h]
0x180009559  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000955e  lea     rcx, [rdi+10h]; lpCriticalSection
0x180009562  call    cs:__imp_LeaveCriticalSection
0x180009568  xor     eax, eax
0x18000956a  add     rsp, 68h
0x18000956e  pop     r15
0x180009570  pop     r14
0x180009572  pop     r13
0x180009574  pop     r12
0x180009576  pop     rdi
0x180009577  pop     rsi
0x180009578  pop     rbx
0x180009579  pop     rbp
0x18000957a  retn
0x18000957b  mov     r9d, 1730h
0x180009581  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180009588  mov     edx, 1
0x18000958d  mov     ecx, ebx
0x18000958f  call    Log_UnistoreHREvent_0
0x180009594  jmp     loc_180009493
0x180009599  mov     rax, [rcx]
0x18000959c  mov     rax, [rax+10h]
0x1800095a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095a5  mov     [rbp+var_28], 0
0x1800095ad  jmp     loc_18000951B
0x1800095b2  mov     dword ptr [rdi+3Ch], 0FFFFFFFFh
0x1800095b9  mov     eax, r13d
0x1800095bc  mov     r14, [rbp+arg_28]
0x1800095c0  mov     [rdi+38h], eax
0x1800095c3  test    r14, r14
0x1800095c6  jz      loc_18000966A
0x1800095cc  mov     r12d, [rdi+78h]
0x1800095d0  mov     rsi, [rdi+80h]
0x1800095d7  test    eax, eax
0x1800095d9  jnz     short loc_1800095ED
0x1800095db  mov     r8d, 1A53h
0x1800095e1  lea     rdx, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800095e8  call    Log_AssertionEvent
0x1800095ed  mov     ecx, 58h ; 'X'; Size
0x1800095f2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800095f7  mov     rbx, rax
0x1800095fa  test    rax, rax
0x1800095fd  jz      loc_1800097A5
0x180009603  mov     [rax+8], r13d
0x180009607  lea     rax, ??_7DBRow@@6B@; const DBRow::`vftable'
0x18000960e  mov     [rbx], rax
0x180009611  mov     [rbx+10h], rsi
0x180009615  test    rsi, rsi
0x180009618  jz      short loc_180009629
0x18000961a  mov     rax, [rsi]
0x18000961d  mov     rcx, rsi
0x180009620  mov     rax, [rax+8]
0x180009624  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009629  lea     rcx, [rbx+20h]; this
0x18000962d  mov     [rbx+18h], r12d
0x180009631  mov     dword ptr [rbx+1Ch], 0FFFFFFFFh
0x180009638  call    ??0UnifiedStoreCursorLocation@@QEAA@XZ; UnifiedStoreCursorLocation::UnifiedStoreCursorLocation(void)
0x18000963d  mov     rax, [rbx]
0x180009640  mov     rcx, rbx
0x180009643  mov     [rbp+arg_0], rbx
0x180009647  mov     rax, [rax+8]
0x18000964b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009650  cmp     dword ptr [rdi+38h], 0
0x180009654  jnz     loc_18000998D
0x18000965a  mov     dword ptr [rbx+24h], 0FFFFFFFFh
0x180009661  mov     eax, r13d
0x180009664  mov     [rbx+20h], eax
0x180009667  mov     [r14], rbx
0x18000966a  mov     rcx, qword ptr [rbp+var_18+8]
0x18000966e  test    rcx, rcx
0x180009671  jz      short loc_1800096A1
0x180009673  mov     rdx, qword ptr [rbp+var_18]
0x180009677  test    rdx, rdx
0x18000967a  jz      short loc_180009690
0x18000967c  mov     rax, [rcx]
0x18000967f  mov     rax, [rax+50h]
0x180009683  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009688  mov     rcx, qword ptr [rbp+var_18+8]
0x18000968c  mov     qword ptr [rbp+var_18], r13
0x180009690  test    rcx, rcx
  ... truncated ...
```
