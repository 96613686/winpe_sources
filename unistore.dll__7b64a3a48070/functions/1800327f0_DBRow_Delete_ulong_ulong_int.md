# DBRow::Delete(ulong,ulong *,int *)

- ea: `0x1800327f0`
- end: `0x180032f2b`
- name: `?Delete@DBRow@@UEAAJKPEAKPEAH@Z`
- size: `1851`
- prototype: `__int64 __fastcall(DBRow *__hidden this, unsigned int, unsigned int *, int *)`
- caller_count: `0`
- callee_count: `23`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180004440`
- `0x1800068f0`
- `0x1800069e8`
- `0x18000866c`
- `0x1800086bc`
- `0x180009a90`
- `0x18000ab20`
- `0x1800125d0`
- `0x180022ee0`
- `0x180027db0`
- `0x1800325d0`
- `0x1800327b0`
- `0x1800327f0`
- `0x180032f34`
- `0x180033050`
- `0x180033324`
- `0x1800334d4`
- `0x18003373c`
- `0x1800396c8`
- `0x180039898`
- `0x18006f180`
- `0x180073a48`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180032ec7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180032ec7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003283a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003283a`

## string_xrefs

- `0x180032af8`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180032b5c`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180032c5d`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180032ced`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180032da1`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180032e3b`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180032e78`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180032ebb`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180032ed7`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180032d72`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x180032ef8`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\jetinterophelper.h`

## pseudocode

```c
__int64 __fastcall DBRow::Delete(DBRow *this, unsigned int a2, unsigned int *a3, int *a4)
{
  unsigned int v8; // eax
  __int64 v9; // rax
  int v10; // eax
  int v11; // ebx
  unsigned int v12; // r13d
  int v13; // eax
  unsigned int i; // ebx
  int v15; // eax
  int v16; // eax
  unsigned int v17; // eax
  int v18; // eax
  int v19; // eax
  int Instance; // eax
  __int64 v21; // rax
  unsigned int v22; // ebx
  unsigned int v23; // eax
  __int64 v24; // rcx
  int v25; // ebx
  int v26; // eax
  __int64 v27; // r9
  void (*v28)(void); // rax
  unsigned int v30; // r14d
  int v31; // r14d
  unsigned int v32; // eax
  __int64 v33; // r9
  unsigned int v34; // eax
  __int64 v35; // r9
  __int64 v36; // rcx
  void *v37; // rax
  __int64 v38; // r9
  __int64 v39; // rcx
  __int64 v40; // r9
  __int64 v41; // rcx
  __int64 v42; // rcx
  struct IDBVolume *v43; // [rsp+50h] [rbp-39h] BYREF
  __int64 v44; // [rsp+58h] [rbp-31h] BYREF
  struct TableHandleInfo *v45; // [rsp+60h] [rbp-29h] BYREF
  __int64 v46; // [rsp+68h] [rbp-21h] BYREF
  struct IDBVolume **v47; // [rsp+70h] [rbp-19h] BYREF
  char v48; // [rsp+78h] [rbp-11h]
  _QWORD v49[2]; // [rsp+80h] [rbp-9h] BYREF
  unsigned int PrimaryId; // [rsp+90h] [rbp+7h]
  int v51; // [rsp+94h] [rbp+Bh] BYREF
  struct DBLockManager *v52; // [rsp+98h] [rbp+Fh] BYREF
  ULONGLONG TickCount64; // [rsp+A0h] [rbp+17h] BYREF
  int v54; // [rsp+A8h] [rbp+1Fh]
  int v55; // [rsp+F0h] [rbp+67h] BYREF
  unsigned int v56; // [rsp+100h] [rbp+77h] BYREF
  unsigned int v57; // [rsp+108h] [rbp+7Fh] BYREF

  if ( a3 )
    v8 = *a3;
  else
    v8 = 0;
  v56 = v8;
  if ( a4 )
    *a4 = 0;
  v54 = 15;
  TickCount64 = GetTickCount64();
  if ( g_perfStatEnabled )
  {
    _InterlockedAdd(&dword_18010DAC8, 1u);
    _InterlockedIncrement(&dword_18010DAC0);
    while ( !dword_18010DAC4 && _InterlockedCompareExchange(&dword_18010DAC4, 1, 0) )
      ;
  }
  v9 = *(_QWORD *)this;
  v55 = -1;
  v43 = 0;
  v44 = 0;
  v10 = (*(__int64 (__fastcall **)(DBRow *, struct IDBVolume **))(v9 + 24))(this, &v43);
  v11 = v10;
  if ( v10 < 0 )
  {
    v27 = 7280;
LABEL_38:
    Log_UnistoreHREvent_0(
      (unsigned int)v10,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      v27);
    if ( !v44 )
      goto LABEL_41;
    v28 = *(void (**)(void))(*(_QWORD *)v44 + 16LL);
LABEL_40:
    v28();
LABEL_41:
    if ( v43 )
      (*(void (__fastcall **)(struct IDBVolume *))(*(_QWORD *)v43 + 16LL))(v43);
    goto LABEL_43;
  }
  v12 = (*(__int64 (__fastcall **)(struct IDBVolume *))(*(_QWORD *)v43 + 56LL))(v43);
  v10 = (*(__int64 (__fastcall **)(struct IDBVolume *, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v43 + 176LL))(
          v43,
          0,
          0,
          0,
          0);
  v11 = v10;
  if ( v10 < 0 )
  {
    v27 = 7286;
    goto LABEL_38;
  }
  v48 = 1;
  v47 = &v43;
  v13 = DBGetRowDeleteContext(this, a2, &v44);
  v11 = v13;
  if ( v13 < 0 )
  {
    v33 = 7292;
    goto LABEL_56;
  }
  for ( i = 0; ; ++i )
  {
    v15 = (*(__int64 (__fastcall **)(DBRow *))(*(_QWORD *)this + 32LL))(this);
    if ( i >= 0x2A )
    {
      v51 = v15;
      PrimaryId = UnifiedStoreCursorLocation::GetPrimaryId((DBRow *)((char *)this + 32));
      if ( (Microsoft_Windows_UserDataAccess_UnifiedStoreEnableBits & 0x20) != 0 )
      {
        v37 = _t_address();
        EtwTraceMessage(&ETWMESSAGE, v37, &v51);
      }
      v13 = DBRow::DeleteAllStreamProperties(this);
      v11 = v13;
      if ( v13 >= 0 )
      {
        v49[0] = 0;
        v49[1] = 0;
        v16 = auto_DBSession::Open((auto_DBSession *)v49, v43);
        v11 = v16;
        if ( v16 < 0 )
        {
          Log_UnistoreHREvent_0(
            (unsigned int)v16,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
            7332);
          goto LABEL_73;
        }
        v45 = 0;
        v46 = v49[0];
        if ( v49[0] )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v49[0] + 8LL))(v49[0]);
        v17 = (*(__int64 (__fastcall **)(DBRow *))(*(_QWORD *)this + 32LL))(this);
        v18 = auto_TableHandle::Open(&v45, v17, 0);
        v11 = v18;
        if ( v18 < 0 )
        {
          v35 = 7335;
          v36 = (unsigned int)v18;
        }
        else
        {
          v19 = UnistoreJetGotoBookmarkEx(v45, (DBRow *)((char *)this + 32), 0);
          v11 = v19;
          if ( v19 < 0 )
          {
            Log_UnistoreHREvent_0(
              (unsigned int)v19,
              1,
              "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
              859);
            if ( v11 != -2147024871 )
            {
              v38 = 7344;
LABEL_71:
              v39 = (unsigned int)v11;
LABEL_72:
              Log_UnistoreHREvent_0(
                v39,
                1,
                "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
                v38);
              auto_TableHandle::~auto_TableHandle((auto_TableHandle *)&v45);
LABEL_73:
              auto_DBSession::~auto_DBSession((auto_DBSession *)v49);
              goto LABEL_74;
            }
LABEL_65:
            v25 = 1;
LABEL_30:
            if ( v46 && v45 )
            {
              (*(void (**)(void))(*(_QWORD *)v46 + 80LL))();
              v45 = 0;
            }
            ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v46);
            auto_DBSession::~auto_DBSession((auto_DBSession *)v49);
            if ( v25 )
              goto LABEL_36;
            v26 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v44 + 24LL))(v44);
            v11 = v26;
            if ( v26 >= 0 )
            {
              ++v56;
LABEL_36:
              v10 = (*(__int64 (__fastcall **)(struct IDBVolume *, __int64, _QWORD, _QWORD))(*(_QWORD *)v43 + 184LL))(
                      v43,
                      1,
                      0,
                      0);
              v11 = v10;
              if ( v10 < 0 )
              {
                v27 = 7390;
                goto LABEL_38;
              }
              if ( a3 )
              {
                v34 = v56;
                *a3 = v56;
                if ( a4 )
                {
                  if ( v34 >= 0x3E8 )
                    *a4 = 1;
                }
              }
              if ( v44 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
              if ( v43 )
                (*(void (__fastcall **)(struct IDBVolume *))(*(_QWORD *)v43 + 16LL))(v43);
              v11 = 0;
              goto LABEL_43;
            }
            Log_UnistoreHREvent_0(
              (unsigned int)v26,
              1,
              "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
              7383);
            (*(void (__fastcall **)(struct IDBVolume *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v43 + 184LL))(v43, 0, 0, 0);
            goto LABEL_45;
          }
          v52 = 0;
          Instance = DBLockManager::GetInstance(&v52);
          v11 = Instance;
          if ( Instance < 0 )
          {
            v38 = 7347;
            v39 = (unsigned int)Instance;
            goto LABEL_72;
          }
          v21 = *(_QWORD *)this;
          v57 = 0;
          if ( (*(unsigned int (__fastcall **)(DBRow *, int *, unsigned int *))(v21 + 120))(this, &v55, &v57) == -2147024871 )
            goto LABEL_65;
          v22 = v57;
          v23 = (*(__int64 (__fastcall **)(DBRow *))(*(_QWORD *)this + 32LL))(this);
          v11 = TestRowLocked(v12, v52, v23, v22);
          if ( v11 >= 0 )
          {
            v11 = ESEDeleteRecord(v45);
            if ( g_breakOnJetError == -1603 )
              Log_AssertionEvent(
                v24,
                "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\jetinterophelper.h",
                25);
            if ( v11 != -2147024871 )
            {
              if ( v11 >= 0 )
              {
                v25 = 0;
                goto LABEL_30;
              }
              v38 = 7373;
              goto LABEL_71;
            }
            goto LABEL_65;
          }
          if ( (int)FailIfServiceIsShuttingDown() >= 0 )
          {
            if ( (unsigned int)GetCallerClientId() == -2 )
              Log_AssertionEvent(
                v41,
                "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
                332);
            if ( IsDebuggerPresent() )
            {
              Log_AssertionEvent(
                v42,
                "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
                339);
              __int2c();
            }
          }
          v35 = 7363;
          v36 = (unsigned int)v11;
        }
        Log_UnistoreHREvent_0(
          v36,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
          v35);
        auto_TableHandle::~auto_TableHandle((auto_TableHandle *)&v45);
        auto_DBSession::~auto_DBSession((auto_DBSession *)v49);
        (*(void (__fastcall **)(struct IDBVolume *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v43 + 184LL))(v43, 0, 0, 0);
LABEL_45:
        if ( !v44 )
          goto LABEL_41;
        v28 = *(void (**)(void))(*(_QWORD *)v44 + 16LL);
        goto LABEL_40;
      }
      v33 = 7326;
LABEL_56:
      Log_UnistoreHREvent_0(
        (unsigned int)v13,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
        v33);
LABEL_74:
      tlx::_UndoSolo__lambda_49291bcc4712adb16da2fae4f72e2bbd___::__UndoSolo__lambda_49291bcc4712adb16da2fae4f72e2bbd___(&v47);
      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v44);
      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v43);
      goto LABEL_43;
    }
    if ( dword_1800DB974[6 * i] == v15 || dword_1800DB974[6 * i] == -1 )
      break;
LABEL_13:
    ;
  }
  v30 = v55;
  if ( v55 != -1 )
    goto LABEL_51;
  v31 = (*(__int64 (__fastcall **)(DBRow *, int *, _QWORD))(*(_QWORD *)this + 120LL))(this, &v55, 0);
  if ( v31 < 0 )
  {
    v40 = 7304;
LABEL_83:
    Log_UnistoreHREvent_0(
      (unsigned int)v31,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      v40);
    goto LABEL_84;
  }
  v30 = v55;
LABEL_51:
  v32 = (*(__int64 (__fastcall **)(DBRow *))(*(_QWORD *)this + 32LL))(this);
  v31 = DBRow::CascadeDelete(&v56, v43, v32, v30, i, a2, &v56, a4);
  if ( v31 < 0 )
  {
    v40 = 7308;
    goto LABEL_83;
  }
  v31 = 0;
  if ( !a4 || !*a4 )
    goto LABEL_13;
  v48 = 0;
  v13 = (*(__int64 (__fastcall **)(struct IDBVolume *, __int64, _QWORD, _QWORD))(*(_QWORD *)v43 + 184LL))(v43, 1, 0, 0);
  v11 = v13;
  if ( v13 < 0 )
  {
    v33 = 7314;
    goto LABEL_56;
  }
LABEL_84:
  tlx::_UndoSolo__lambda_49291bcc4712adb16da2fae4f72e2bbd___::__UndoSolo__lambda_49291bcc4712adb16da2fae4f72e2bbd___(&v47);
  ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v44);
  ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v43);
  v11 = v31;
LABEL_43:
  PerfAutoStartStopTimeCounter::~PerfAutoStartStopTimeCounter((PerfAutoStartStopTimeCounter *)&TickCount64);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800327f0  mov     [rsp-8+arg_8], rbx
0x1800327f5  push    rbp
0x1800327f6  push    rsi
0x1800327f7  push    rdi
0x1800327f8  push    r12
0x1800327fa  push    r13
0x1800327fc  push    r14
0x1800327fe  push    r15
0x180032800  lea     rbp, [rsp-27h]
0x180032805  sub     rsp, 0B0h
0x18003280c  xor     r14d, r14d
0x18003280f  mov     rsi, r9
0x180032812  mov     r15, r8
0x180032815  mov     r12d, edx
0x180032818  mov     rdi, rcx
0x18003281b  test    r8, r8
0x18003281e  jnz     loc_180032B9C
0x180032824  mov     eax, r14d
0x180032827  mov     [rbp+57h+arg_10], eax
0x18003282a  test    rsi, rsi
0x18003282d  jnz     loc_180032DDF
0x180032833  mov     [rbp+57h+var_38], 0Fh
0x18003283a  call    cs:__imp_GetTickCount64
0x180032840  mov     [rbp+57h+var_40], rax
0x180032844  mov     r13d, 1
0x18003284a  mov     eax, cs:?g_perfStatEnabled@@3KC; ulong volatile g_perfStatEnabled
0x180032850  test    eax, eax
0x180032852  jnz     loc_180032DE7
0x180032858  mov     rax, [rdi]
0x18003285b  lea     rdx, [rbp+57h+var_90]
0x18003285f  mov     rcx, rdi
0x180032862  mov     [rbp+57h+arg_0], 0FFFFFFFFh
0x180032869  mov     [rbp+57h+var_90], r14
0x18003286d  mov     [rbp+57h+var_88], r14
0x180032871  mov     rax, [rax+18h]
0x180032875  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003287a  mov     ebx, eax
0x18003287c  test    eax, eax
0x18003287e  js      loc_180032CB6
0x180032884  mov     rcx, [rbp+57h+var_90]
0x180032888  mov     rax, [rcx]
0x18003288b  mov     rax, [rax+38h]
0x18003288f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032894  mov     rcx, [rbp+57h+var_90]
0x180032898  mov     r13d, eax
0x18003289b  xor     r9d, r9d
0x18003289e  mov     [rsp+0E0h+var_C0], r14
0x1800328a3  xor     r8d, r8d
0x1800328a6  mov     rdx, [rcx]
0x1800328a9  mov     rax, [rdx+0B0h]
0x1800328b0  xor     edx, edx
0x1800328b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800328b7  mov     ebx, eax
0x1800328b9  test    eax, eax
0x1800328bb  js      loc_180032CD0
0x1800328c1  lea     rax, [rbp+57h+var_90]
0x1800328c5  mov     [rbp+57h+var_68], 1
0x1800328c9  lea     r8, [rbp+57h+var_88]
0x1800328cd  mov     [rbp+57h+var_70], rax
0x1800328d1  mov     edx, r12d
0x1800328d4  mov     rcx, rdi
0x1800328d7  call    DBGetRowDeleteContext
0x1800328dc  mov     ebx, eax
0x1800328de  test    eax, eax
0x1800328e0  js      loc_180032E15
0x1800328e6  mov     ebx, r14d
0x1800328e9  mov     rax, [rdi]
0x1800328ec  mov     rcx, rdi
0x1800328ef  mov     rax, [rax+20h]
0x1800328f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800328f8  cmp     ebx, 2Ah ; '*'
0x1800328fb  jnb     short loc_180032921
0x1800328fd  mov     ecx, ebx
0x1800328ff  lea     rdx, [rcx+rcx*2]
0x180032903  lea     rcx, dword_1800DB974
0x18003290a  cmp     [rcx+rdx*8], eax
0x18003290d  jz      loc_180032BA4
0x180032913  cmp     dword ptr [rcx+rdx*8], 0FFFFFFFFh
0x180032917  jz      loc_180032BA4
0x18003291d  inc     ebx
0x18003291f  jmp     short loc_1800328E9
0x180032921  lea     rcx, [rdi+20h]; this
0x180032925  mov     [rbp+57h+var_4C], eax
0x180032928  call    ?GetPrimaryId@UnifiedStoreCursorLocation@@QEBAKXZ; UnifiedStoreCursorLocation::GetPrimaryId(void)
0x18003292d  test    byte ptr cs:Microsoft_Windows_UserDataAccess_UnifiedStoreEnableBits, 20h
0x180032934  mov     [rbp+57h+var_50], eax
0x180032937  jnz     loc_180032D1E
0x18003293d  xor     r12d, r12d
0x180032940  mov     rcx, rdi; this
0x180032943  call    ?DeleteAllStreamProperties@DBRow@@IEAAJXZ; DBRow::DeleteAllStreamProperties(void)
0x180032948  mov     ebx, eax
0x18003294a  test    eax, eax
0x18003294c  js      loc_180032E1D
0x180032952  mov     rdx, [rbp+57h+var_90]; struct IDBVolume *
0x180032956  lea     rcx, [rbp+57h+var_60]; this
0x18003295a  mov     [rbp+57h+var_60], r12
0x18003295e  mov     [rbp+57h+var_58], 0
0x180032966  call    ?Open@auto_DBSession@@QEAAJPEAVIDBVolume@@@Z; auto_DBSession::Open(IDBVolume *)
0x18003296b  mov     ebx, eax
0x18003296d  test    eax, eax
0x18003296f  js      loc_180032E72
0x180032975  mov     rcx, [rbp+57h+var_60]
0x180032979  mov     [rbp+57h+var_80], r12
0x18003297d  mov     [rbp+57h+var_78], rcx
0x180032981  test    rcx, rcx
0x180032984  jz      short loc_180032992
0x180032986  mov     rax, [rcx]
0x180032989  mov     rax, [rax+8]
0x18003298d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032992  mov     rax, [rdi]
0x180032995  mov     rcx, rdi
0x180032998  mov     rax, [rax+20h]
0x18003299c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800329a1  xor     r8d, r8d
0x1800329a4  lea     rcx, [rbp+57h+var_80]
0x1800329a8  mov     edx, eax
0x1800329aa  call    ?Open@auto_TableHandle@@QEAAJW4US_TABLEID@@K@Z; auto_TableHandle::Open(US_TABLEID,ulong)
0x1800329af  mov     ebx, eax
0x1800329b1  test    eax, eax
0x1800329b3  js      loc_180032CE0
0x1800329b9  mov     rcx, [rbp+57h+var_80]; struct TableHandleInfo *
0x1800329bd  lea     rdx, [rdi+20h]; struct UnifiedStoreCursorLocation *
0x1800329c1  xor     r8d, r8d; int *
0x1800329c4  call    ?UnistoreJetGotoBookmarkEx@@YAJPEAUTableHandleInfo@@AEBVUnifiedStoreCursorLocation@@PEAH@Z; UnistoreJetGotoBookmarkEx(TableHandleInfo *,UnifiedStoreCursorLocation const &,int *)
0x1800329c9  mov     ebx, eax
0x1800329cb  test    eax, eax
0x1800329cd  js      loc_180032D6D
0x1800329d3  lea     rcx, [rbp+57h+var_48]; struct DBLockManager **
0x1800329d7  mov     [rbp+57h+var_48], r12
0x1800329db  call    ?GetInstance@DBLockManager@@SAJPEAPEAV1@@Z; DBLockManager::GetInstance(DBLockManager * *)
0x1800329e0  mov     ebx, eax
0x1800329e2  test    eax, eax
0x1800329e4  js      loc_180032E90
0x1800329ea  mov     rax, [rdi]
0x1800329ed  lea     r8, [rbp+57h+arg_18]
0x1800329f1  lea     rdx, [rbp+57h+arg_0]
0x1800329f5  mov     [rbp+57h+arg_18], r12d
0x1800329f9  mov     rcx, rdi
0x1800329fc  mov     rax, [rax+78h]
0x180032a00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032a05  mov     r14d, 80070019h
0x180032a0b  cmp     eax, r14d
0x180032a0e  jz      loc_180032CC4
0x180032a14  mov     rax, [rdi]
0x180032a17  mov     rcx, rdi
0x180032a1a  mov     ebx, [rbp+57h+arg_18]
0x180032a1d  mov     rax, [rax+20h]
0x180032a21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032a26  mov     rdx, [rbp+57h+var_48]
0x180032a2a  mov     r9d, ebx
0x180032a2d  mov     r8d, eax
0x180032a30  mov     ecx, r13d
0x180032a33  call    _TestRowLocked
0x180032a38  mov     ebx, eax
0x180032a3a  test    eax, eax
0x180032a3c  js      loc_180032EA2
0x180032a42  mov     rcx, [rbp+57h+var_80]; struct TableHandleInfo *
0x180032a46  call    ?ESEDeleteRecord@@YAJPEAUTableHandleInfo@@@Z; ESEDeleteRecord(TableHandleInfo *)
0x180032a4b  cmp     cs:?g_breakOnJetError@@3JA, 0FFFFF9BDh; long g_breakOnJetError
0x180032a55  mov     ebx, eax
0x180032a57  jz      loc_180032EF2
0x180032a5d  cmp     ebx, r14d
0x180032a60  jz      loc_180032CC4
0x180032a66  test    ebx, ebx
0x180032a68  js      loc_180032F09
0x180032a6e  mov     ebx, r12d
0x180032a71  mov     edi, 1
0x180032a76  mov     rcx, [rbp+57h+var_78]
0x180032a7a  test    rcx, rcx
0x180032a7d  jz      short loc_180032A98
0x180032a7f  mov     rdx, [rbp+57h+var_80]
0x180032a83  test    rdx, rdx
0x180032a86  jz      short loc_180032A98
0x180032a88  mov     rax, [rcx]
0x180032a8b  mov     rax, [rax+50h]
0x180032a8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032a94  mov     [rbp+57h+var_80], r12
0x180032a98  lea     rcx, [rbp+57h+var_78]; void *
0x180032a9c  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180032aa1  lea     rcx, [rbp+57h+var_60]; this
0x180032aa5  call    ??1auto_DBSession@@QEAA@XZ; auto_DBSession::~auto_DBSession(void)
0x180032aaa  test    ebx, ebx
0x180032aac  jnz     short loc_180032ACB
0x180032aae  mov     rcx, [rbp+57h+var_88]
0x180032ab2  mov     rax, [rcx]
0x180032ab5  mov     rax, [rax+18h]
0x180032ab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032abe  mov     ebx, eax
0x180032ac0  test    eax, eax
0x180032ac2  js      loc_180032B56
0x180032ac8  add     [rbp+57h+arg_10], edi
0x180032acb  mov     rcx, [rbp+57h+var_90]
0x180032acf  xor     r9d, r9d
0x180032ad2  xor     r8d, r8d
0x180032ad5  mov     edx, edi
0x180032ad7  mov     rax, [rcx]
0x180032ada  mov     rax, [rax+0B8h]
0x180032ae1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032ae6  mov     ebx, eax
0x180032ae8  test    eax, eax
0x180032aea  jns     loc_180032C70
0x180032af0  mov     r9d, 1CDEh
0x180032af6  mov     edx, edi
0x180032af8  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180032aff  mov     ecx, eax
0x180032b01  call    Log_UnistoreHREvent_0
0x180032b06  mov     rcx, [rbp+57h+var_88]
0x180032b0a  test    rcx, rcx
0x180032b0d  jz      short loc_180032B1B
0x180032b0f  mov     rdx, [rcx]
0x180032b12  mov     rax, [rdx+10h]
0x180032b16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032b1b  mov     rcx, [rbp+57h+var_90]
0x180032b1f  test    rcx, rcx
0x180032b22  jz      short loc_180032B30
0x180032b24  mov     rax, [rcx]
0x180032b27  mov     rax, [rax+10h]
0x180032b2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032b30  lea     rcx, [rbp+57h+var_40]; this
0x180032b34  call    ??1PerfAutoStartStopTimeCounter@@QEAA@XZ; PerfAutoStartStopTimeCounter::~PerfAutoStartStopTimeCounter(void)
0x180032b39  mov     eax, ebx
0x180032b3b  mov     rbx, [rsp+0E0h+arg_8]
0x180032b43  add     rsp, 0B0h
0x180032b4a  pop     r15
0x180032b4c  pop     r14
0x180032b4e  pop     r13
0x180032b50  pop     r12
0x180032b52  pop     rdi
0x180032b53  pop     rsi
0x180032b54  pop     rbp
0x180032b55  retn
0x180032b56  mov     r9d, 1CD7h
0x180032b5c  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180032b63  mov     edx, edi
0x180032b65  mov     ecx, eax
0x180032b67  call    Log_UnistoreHREvent_0
0x180032b6c  mov     rcx, [rbp+57h+var_90]
0x180032b70  mov     rdx, [rcx]
0x180032b73  mov     rax, [rdx+0B8h]
0x180032b7a  xor     r9d, r9d
0x180032b7d  xor     r8d, r8d
0x180032b80  xor     edx, edx
0x180032b82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032b87  mov     rcx, [rbp+57h+var_88]
0x180032b8b  test    rcx, rcx
0x180032b8e  jz      short loc_180032B1B
0x180032b90  mov     rax, [rcx]
0x180032b93  mov     rax, [rax+10h]
0x180032b97  jmp     loc_180032B16
0x180032b9c  mov     eax, [r8]
0x180032b9f  jmp     loc_180032827
0x180032ba4  mov     r14d, [rbp+57h+arg_0]
0x180032ba8  cmp     r14d, 0FFFFFFFFh
0x180032bac  jnz     short loc_180032BD3
0x180032bae  mov     rax, [rdi]
0x180032bb1  lea     rdx, [rbp+57h+arg_0]
0x180032bb5  xor     r8d, r8d
0x180032bb8  mov     rcx, rdi
0x180032bbb  mov     rax, [rax+78h]
0x180032bbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032bc4  mov     r14d, eax
0x180032bc7  test    eax, eax
0x180032bc9  js      loc_180032E2D
0x180032bcf  mov     r14d, [rbp+57h+arg_0]
0x180032bd3  mov     rax, [rdi]
0x180032bd6  mov     rcx, rdi
0x180032bd9  mov     rax, [rax+20h]
0x180032bdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032be2  mov     rdx, [rbp+57h+var_90]
0x180032be6  lea     rcx, [rbp+57h+arg_10]
0x180032bea  mov     [rsp+0E0h+var_A8], rsi
0x180032bef  mov     r9d, r14d
0x180032bf2  mov     [rsp+0E0h+var_B0], rcx
0x180032bf7  mov     r8d, eax
0x180032bfa  mov     dword ptr [rsp+0E0h+var_B8], r12d
0x180032bff  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x180032c03  call    ?CascadeDelete@DBRow@@IEAAJPEAVIDBVolume@@W4US_TABLEID@@KKKPEAKPEAH@Z; DBRow::CascadeDelete(IDBVolume *,US_TABLEID,ulong,ulong,ulong,ulong *,int *)
0x180032c08  mov     r14d, eax
0x180032c0b  test    eax, eax
0x180032c0d  js      loc_180032E35
0x180032c13  xor     r14d, r14d
0x180032c16  test    rsi, rsi
0x180032c19  jz      loc_18003291D
0x180032c1f  cmp     [rsi], r14d
0x180032c22  jz      loc_18003291D
0x180032c28  mov     rcx, [rbp+57h+var_90]
0x180032c2c  lea     edi, [r14+1]
0x180032c30  xor     r9d, r9d
0x180032c33  mov     [rbp+57h+var_68], r14b
0x180032c37  xor     r8d, r8d
0x180032c3a  mov     edx, edi
0x180032c3c  mov     rax, [rcx]
0x180032c3f  mov     rax, [rax+0B8h]
0x180032c46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032c4b  mov     ebx, eax
0x180032c4d  test    eax, eax
0x180032c4f  jns     loc_180032E4F
0x180032c55  mov     r9d, 1C92h
0x180032c5b  mov     edx, edi
0x180032c5d  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
  ... truncated ...
```
