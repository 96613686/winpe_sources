# DBVolume::Mount(IDBManager *,ushort const *,ulong)

- ea: `0x1800191e0`
- end: `0x180019460`
- name: `?Mount@DBVolume@@IEAAJPEAVIDBManager@@PEBGK@Z`
- size: `640`
- prototype: `__int64 __fastcall(DBVolume *__hidden this, struct IDBManager *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800674ec`

## callees

- `0x180004440`
- `0x1800068f0`
- `0x1800086bc`
- `0x1800191e0`
- `0x180019468`
- `0x180019520`
- `0x18001a834`
- `0x18001c1a0`
- `0x180025c88`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019305`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019305`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019386`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019407`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019434`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019386`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019407`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019434`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001928d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001928d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180019276`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180019276`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180019259`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180019259`

## string_xrefs

- `0x180019237`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x1800192ca`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180019367`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x1800193bf`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x1800193e8`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`

## pseudocode

```c
__int64 __fastcall DBVolume::Mount(DBVolume *this, struct IDBManager *a2, const unsigned __int16 *a3, int a4)
{
  __int64 v7; // r9
  unsigned int v8; // ebx
  PTP_TIMER ThreadpoolTimer; // rbx
  struct _TP_TIMER *v11; // rax
  signed int LastError; // eax
  int DefaultSession; // eax
  struct _RTL_CRITICAL_SECTION *v14; // r15
  struct IDBSession *v15; // rbx
  int v16; // eax
  unsigned int v17; // r14d
  __int64 v18; // r9
  __int64 v19; // rax
  int v20; // eax
  int v21; // eax
  unsigned int v22; // esi
  _QWORD v23[2]; // [rsp+30h] [rbp-10h] BYREF
  struct IDBSession *v24; // [rsp+70h] [rbp+30h] BYREF

  *((_QWORD *)this + 2) = a2;
  *((_QWORD *)this + 10) = (*(__int64 (__fastcall **)(struct IDBManager *))(*(_QWORD *)a2 + 64LL))(a2);
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           (char *)this + 40,
                           a3) )
  {
    v7 = 3816;
    v8 = -2147024882;
LABEL_3:
    Log_UnistoreHREvent_0(
      v8,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      v7);
    return v8;
  }
  ThreadpoolTimer = CreateThreadpoolTimer(DBVolume::s_SessionCacheResetTimerCallback, this, 0);
  v11 = (struct _TP_TIMER *)*((_QWORD *)this + 24);
  if ( ThreadpoolTimer == v11 )
  {
    ThreadpoolTimer = (PTP_TIMER)*((_QWORD *)this + 24);
  }
  else
  {
    if ( v11 )
      CloseThreadpoolTimer(*((PTP_TIMER *)this + 24));
    *((_QWORD *)this + 24) = ThreadpoolTimer;
  }
  if ( !ThreadpoolTimer )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    v7 = 3820;
    goto LABEL_3;
  }
  v24 = 0;
  DefaultSession = DBVolume::_GetDefaultSession(this, &v24);
  v8 = DefaultSession;
  if ( DefaultSession < 0 )
  {
    Log_UnistoreHREvent_0(
      (unsigned int)DefaultSession,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      3823);
    if ( v24 )
      (*(void (__fastcall **)(struct IDBSession *))(*(_QWORD *)v24 + 16LL))(v24);
    return v8;
  }
  v14 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 200);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 5);
  v15 = v24;
  auto_DBSession::auto_DBSession((auto_DBSession *)v23, v24);
  v16 = auto_DBSession::SetSessionContext((auto_DBSession *)v23);
  v17 = v16;
  if ( v16 < 0 )
  {
    v18 = 3829;
LABEL_25:
    Log_UnistoreHREvent_0(
      (unsigned int)v16,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      v18);
LABEL_31:
    auto_DBSession::~auto_DBSession((auto_DBSession *)v23);
    LeaveCriticalSection(v14);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v24);
    return v17;
  }
  v19 = *(_QWORD *)v23[0];
  if ( a4 == 1 )
  {
    v16 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *))(v19 + 56))(v23[0], a3);
    v17 = v16;
    if ( v16 < 0 )
    {
      v18 = 3837;
      goto LABEL_25;
    }
  }
  else
  {
    v20 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, bool))(v19 + 48))(v23[0], a3, a4 == 5);
    v17 = v20;
    if ( v20 < 0 )
    {
      Log_UnistoreHREvent_0(
        (unsigned int)v20,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
        3833);
      auto_DBSession::~auto_DBSession((auto_DBSession *)v23);
      LeaveCriticalSection((LPCRITICAL_SECTION)this + 5);
      if ( v15 )
        (*(void (__fastcall **)(struct IDBSession *))(*(_QWORD *)v15 + 16LL))(v15);
      return v17;
    }
  }
  v21 = DBVolume::_EnsureIdHighWaterMarks(this);
  v22 = v21;
  if ( v21 >= 0 )
  {
    v17 = 0;
    goto LABEL_31;
  }
  Log_UnistoreHREvent_0(
    (unsigned int)v21,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
    3840);
  auto_DBSession::~auto_DBSession((auto_DBSession *)v23);
  LeaveCriticalSection(v14);
  if ( v15 )
    (*(void (__fastcall **)(struct IDBSession *))(*(_QWORD *)v15 + 16LL))(v15);
  return v22;
}

```

## disassembly

```asm
0x1800191e0  mov     [rsp-28h+arg_8], rbx
0x1800191e5  mov     [rsp-28h+arg_10], rsi
0x1800191ea  push    rbp
0x1800191eb  push    r12
0x1800191ed  push    r13
0x1800191ef  push    r14
0x1800191f1  push    r15
0x1800191f3  mov     rbp, rsp
0x1800191f6  sub     rsp, 40h
0x1800191fa  mov     [rcx+10h], rdx
0x1800191fe  mov     rsi, rcx
0x180019201  mov     rax, [rdx]
0x180019204  mov     rcx, rdx
0x180019207  mov     r12d, r9d
0x18001920a  mov     r13, r8
0x18001920d  mov     rax, [rax+40h]
0x180019211  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019216  lea     rcx, [rsi+28h]
0x18001921a  mov     [rsi+50h], rax
0x18001921e  mov     rdx, r13
0x180019221  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180019226  test    al, al
0x180019228  jnz     short loc_18001924C
0x18001922a  mov     r9d, 0EE8h
0x180019230  mov     ebx, 8007000Eh
0x180019235  xor     edx, edx
0x180019237  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001923e  mov     ecx, ebx
0x180019240  call    Log_UnistoreHREvent_0
0x180019245  mov     eax, ebx
0x180019247  jmp     loc_180019446
0x18001924c  xor     r8d, r8d; pcbe
0x18001924f  lea     rcx, ?s_SessionCacheResetTimerCallback@DBVolume@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180019256  mov     rdx, rsi; pv
0x180019259  call    cs:__imp_CreateThreadpoolTimer
0x18001925f  mov     rbx, rax
0x180019262  mov     rax, [rsi+0C0h]
0x180019269  cmp     rbx, rax
0x18001926c  jz      short loc_180019285
0x18001926e  test    rax, rax
0x180019271  jz      short loc_18001927C
0x180019273  mov     rcx, rax; pti
0x180019276  call    cs:__imp_CloseThreadpoolTimer
0x18001927c  mov     [rsi+0C0h], rbx
0x180019283  jmp     short loc_180019288
0x180019285  mov     rbx, rax
0x180019288  test    rbx, rbx
0x18001928b  jnz     short loc_1800192AA
0x18001928d  call    cs:__imp_GetLastError
0x180019293  mov     ebx, eax
0x180019295  test    eax, eax
0x180019297  jle     short loc_1800192A2
0x180019299  movzx   ebx, ax
0x18001929c  or      ebx, 80070000h
0x1800192a2  mov     r9d, 0EECh
0x1800192a8  jmp     short loc_180019235
0x1800192aa  lea     rdx, [rbp+arg_0]; struct IDBSession **
0x1800192ae  mov     [rbp+arg_0], 0
0x1800192b6  mov     rcx, rsi; this
0x1800192b9  call    ?_GetDefaultSession@DBVolume@@IEAAJPEAPEAVIDBSession@@@Z; DBVolume::_GetDefaultSession(IDBSession * *)
0x1800192be  mov     ebx, eax
0x1800192c0  test    eax, eax
0x1800192c2  jns     short loc_1800192FB
0x1800192c4  mov     r9d, 0EEFh
0x1800192ca  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800192d1  mov     edx, 1
0x1800192d6  mov     ecx, eax
0x1800192d8  call    Log_UnistoreHREvent_0
0x1800192dd  mov     rcx, [rbp+arg_0]
0x1800192e1  test    rcx, rcx
0x1800192e4  jz      loc_180019245
0x1800192ea  mov     rax, [rcx]
0x1800192ed  mov     rax, [rax+10h]
0x1800192f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800192f6  jmp     loc_180019245
0x1800192fb  lea     r15, [rsi+0C8h]
0x180019302  mov     rcx, r15; lpCriticalSection
0x180019305  call    cs:__imp_EnterCriticalSection
0x18001930b  mov     rbx, [rbp+arg_0]
0x18001930f  lea     rcx, [rbp+var_10]; this
0x180019313  mov     rdx, rbx; struct IDBSession *
0x180019316  call    ??0auto_DBSession@@QEAA@PEAVIDBSession@@@Z; auto_DBSession::auto_DBSession(IDBSession *)
0x18001931b  lea     rcx, [rbp+var_10]; this
0x18001931f  call    ?SetSessionContext@auto_DBSession@@QEAAJXZ; auto_DBSession::SetSessionContext(void)
0x180019324  mov     r14d, eax
0x180019327  test    eax, eax
0x180019329  jns     short loc_180019336
0x18001932b  mov     r9d, 0EF5h
0x180019331  jmp     loc_1800193BF
0x180019336  mov     rcx, [rbp+var_10]
0x18001933a  mov     rdx, r13
0x18001933d  mov     rax, [rcx]
0x180019340  cmp     r12d, 1
0x180019344  jz      short loc_1800193A9
0x180019346  mov     rax, [rax+30h]
0x18001934a  xor     r8d, r8d
0x18001934d  cmp     r12d, 5
0x180019351  setz    r8b
0x180019355  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001935a  mov     r14d, eax
0x18001935d  test    eax, eax
0x18001935f  jns     short loc_1800193D4
0x180019361  mov     r9d, 0EF9h
0x180019367  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001936e  mov     edx, 1
0x180019373  mov     ecx, eax
0x180019375  call    Log_UnistoreHREvent_0
0x18001937a  lea     rcx, [rbp+var_10]; this
0x18001937e  call    ??1auto_DBSession@@QEAA@XZ; auto_DBSession::~auto_DBSession(void)
0x180019383  mov     rcx, r15; lpCriticalSection
0x180019386  call    cs:__imp_LeaveCriticalSection
0x18001938c  test    rbx, rbx
0x18001938f  jz      loc_180019443
0x180019395  mov     rax, [rbx]
0x180019398  mov     rcx, rbx
0x18001939b  mov     rax, [rax+10h]
0x18001939f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193a4  jmp     loc_180019443
0x1800193a9  mov     rax, [rax+38h]
0x1800193ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193b2  mov     r14d, eax
0x1800193b5  test    eax, eax
0x1800193b7  jns     short loc_1800193D4
0x1800193b9  mov     r9d, 0EFDh
0x1800193bf  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800193c6  mov     edx, 1
0x1800193cb  mov     ecx, eax
0x1800193cd  call    Log_UnistoreHREvent_0
0x1800193d2  jmp     short loc_180019428
0x1800193d4  mov     rcx, rsi; this
0x1800193d7  call    ?_EnsureIdHighWaterMarks@DBVolume@@IEAAJXZ; DBVolume::_EnsureIdHighWaterMarks(void)
0x1800193dc  mov     esi, eax
0x1800193de  test    eax, eax
0x1800193e0  jns     short loc_180019425
0x1800193e2  mov     r9d, 0F00h
0x1800193e8  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800193ef  mov     edx, 1
0x1800193f4  mov     ecx, eax
0x1800193f6  call    Log_UnistoreHREvent_0
0x1800193fb  lea     rcx, [rbp+var_10]; this
0x1800193ff  call    ??1auto_DBSession@@QEAA@XZ; auto_DBSession::~auto_DBSession(void)
0x180019404  mov     rcx, r15; lpCriticalSection
0x180019407  call    cs:__imp_LeaveCriticalSection
0x18001940d  test    rbx, rbx
0x180019410  jz      short loc_180019421
0x180019412  mov     rax, [rbx]
0x180019415  mov     rcx, rbx
0x180019418  mov     rax, [rax+10h]
0x18001941c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019421  mov     eax, esi
0x180019423  jmp     short loc_180019446
0x180019425  xor     r14d, r14d
0x180019428  lea     rcx, [rbp+var_10]; this
0x18001942c  call    ??1auto_DBSession@@QEAA@XZ; auto_DBSession::~auto_DBSession(void)
0x180019431  mov     rcx, r15; lpCriticalSection
0x180019434  call    cs:__imp_LeaveCriticalSection
0x18001943a  lea     rcx, [rbp+arg_0]; void *
0x18001943e  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180019443  mov     eax, r14d
0x180019446  lea     r11, [rsp+40h+var_s0]
0x18001944b  mov     rbx, [r11+38h]
0x18001944f  mov     rsi, [r11+40h]
0x180019453  mov     rsp, r11
0x180019456  pop     r15
0x180019458  pop     r14
0x18001945a  pop     r13
0x18001945c  pop     r12
0x18001945e  pop     rbp
0x18001945f  retn
```
