# DBVolume::GetNextPrimaryId(US_TABLEID,int *,ulong *)

- ea: `0x18001d4a0`
- end: `0x18001d986`
- name: `?GetNextPrimaryId@DBVolume@@EEAAJW4US_TABLEID@@PEAHPEAK@Z`
- size: `1254`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180004440`
- `0x1800068f0`
- `0x18000866c`
- `0x1800086bc`
- `0x180008ff0`
- `0x18000ab20`
- `0x18000f530`
- `0x180010ea0`
- `0x18001a180`
- `0x18001a2c0`
- `0x18001d274`
- `0x18001d4a0`
- `0x18001d98c`
- `0x18001e2f4`
- `0x180062288`
- `0x180067c1c`
- `0x18006f180`
- `0x180080c18`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d54c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d54c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d568`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d6da`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d80e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d568`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d6da`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d80e`

## string_xrefs

- `0x18001d4f7`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18001d57e`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18001d63a`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18001d6cb`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18001d754`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18001d76a`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18001d7bd`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18001d7fb`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18001d8c6`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18001d8dd`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18001d902`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`

## pseudocode

```c
__int64 __fastcall DBVolume::GetNextPrimaryId(
        struct _RTL_CRITICAL_SECTION *a1,
        unsigned int a2,
        _DWORD *a3,
        unsigned int *a4)
{
  int v7; // r10d
  __int64 v8; // rcx
  int TableHandle; // eax
  unsigned int v10; // ebx
  char *v11; // r15
  __int64 v12; // rcx
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rax
  PRTL_CRITICAL_SECTION_DEBUG v14; // rax
  int v15; // ebx
  int v16; // eax
  int updated; // r14d
  int v18; // eax
  unsigned int v19; // edx
  int v20; // r8d
  int v21; // r9d
  __int64 v22; // r9
  int Key; // eax
  int HresultFromJetError; // eax
  __int64 v26; // r9
  __int64 v27; // rdx
  __int64 v28; // rcx
  int v29; // eax
  int v30; // eax
  struct _RTL_CRITICAL_SECTION *v31; // [rsp+30h] [rbp-30h] BYREF
  int v32; // [rsp+38h] [rbp-28h]
  struct TableHandleInfo *v33[2]; // [rsp+40h] [rbp-20h] BYREF
  _QWORD v34[2]; // [rsp+50h] [rbp-10h] BYREF
  unsigned int v35; // [rsp+A8h] [rbp+48h] BYREF
  unsigned int v36; // [rsp+B0h] [rbp+50h] BYREF

  v35 = a2;
  *a3 = 0;
  if ( (unsigned int)GetIdProp(a2) != 17170435 || !v7 )
  {
    if ( !((unsigned int (__fastcall *)(struct _RTL_CRITICAL_SECTION *))a1->DebugInfo[1].CriticalSection)(a1) )
      Log_AssertionEvent(
        v8,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
        4848);
    v34[0] = 0;
    v34[1] = 0;
    *(_OWORD *)v33 = 0;
    TableHandle = GetTableHandle(53, 0, a1, v34, v33);
    v10 = TableHandle;
    if ( TableHandle < 0 )
    {
      Log_UnistoreHREvent_0(
        (unsigned int)TableHandle,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
        4854);
      goto LABEL_16;
    }
    v11 = (char *)a1 + 64 * (__int64)(int)v35;
    EnterCriticalSection(a1 + 5);
    if ( *((_DWORD *)v11 + 66) )
    {
LABEL_6:
      LeaveCriticalSection(a1 + 5);
      if ( !*((_DWORD *)v11 + 66) )
        Log_AssertionEvent(
          v12,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
          4898);
      DebugInfo = a1->DebugInfo;
      v31 = a1;
      ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *))DebugInfo->CriticalSection)(a1);
      v14 = a1->DebugInfo;
      v15 = 0;
      v32 = 0;
      v16 = (*(__int64 (__fastcall **)(struct _RTL_CRITICAL_SECTION *, __int64, _QWORD, _QWORD, _QWORD))&v14[3].EntryCount)(
              a1,
              4,
              0,
              0,
              0);
      updated = v16;
      if ( v16 >= 0 )
      {
        v15 = 1;
        v32 = 1;
      }
      else if ( v16 != -2147221303 )
      {
        Log_UnistoreHREvent_0(
          (unsigned int)v16,
          0,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
          917);
        Log_UnistoreHREvent_0(
          (unsigned int)updated,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
          4902);
        ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v31);
        goto LABEL_15;
      }
      v18 = UnistoreJetGotoBookmarkEx(v33[0], (const struct UnifiedStoreCursorLocation *)(v11 + 264), 0);
      updated = v18;
      if ( v18 < 0 )
      {
        Log_UnistoreHREvent_0(
          (unsigned int)v18,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
          859);
        v22 = 4905;
      }
      else
      {
        v36 = 0;
        updated = ESEEscrowUpdate(v33[0], v19, v20, v21, (int *)&v36);
        if ( updated < 0 )
        {
          v22 = 4910;
        }
        else
        {
          updated = DBVolume::_MaybeUpdateHighWaterMark(a1, v35, v36);
          if ( updated >= 0 )
          {
            if ( v35 )
            {
              if ( v35 == 50 )
              {
                updated = RegistrySetDWORD(
                            HKEY_CURRENT_USER,
                            L"Software\\Microsoft\\Unified Store",
                            L"LastStoreGroupingId",
                            v36);
                if ( updated < 0 )
                {
                  v22 = 4920;
                  goto LABEL_14;
                }
              }
            }
            else
            {
              updated = RegistrySetDWORD(HKEY_CURRENT_USER, L"Software\\Microsoft\\Unified Store", L"LastStoreId", v36);
              if ( updated < 0 )
              {
                v22 = 4916;
                goto LABEL_14;
              }
            }
            if ( v15 )
            {
              v29 = (*(__int64 (__fastcall **)(struct _RTL_CRITICAL_SECTION *, __int64, _QWORD, _QWORD))&a1->DebugInfo[3].Flags)(
                      a1,
                      1,
                      0,
                      0);
              v10 = v29;
              if ( v29 < 0 )
              {
                Log_UnistoreHREvent_0(
                  (unsigned int)v29,
                  1,
                  "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
                  940);
                Log_UnistoreHREvent_0(
                  v10,
                  1,
                  "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
                  4923);
                DBAutoTopLevelTransact::~DBAutoTopLevelTransact((DBAutoTopLevelTransact *)&v31);
                goto LABEL_16;
              }
              v32 = 0;
            }
            *a4 = v36;
            *a3 = 1;
            ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v31);
            v10 = 0;
LABEL_16:
            auto_TableHandle::~auto_TableHandle((auto_TableHandle *)v33);
            auto_DBSession::~auto_DBSession((auto_DBSession *)v34);
            return v10;
          }
          v22 = 4912;
        }
      }
LABEL_14:
      Log_UnistoreHREvent_0(
        (unsigned int)updated,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
        v22);
      DBAutoTopLevelTransact::~DBAutoTopLevelTransact((DBAutoTopLevelTransact *)&v31);
LABEL_15:
      v10 = updated;
      goto LABEL_16;
    }
    Key = CommsESE_JetMakeKey(*((_QWORD *)v33[0] + 1), *((_QWORD *)v33[0] + 2), &v35, 4u, 0x101u);
    if ( Key < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(Key);
      v26 = 4871;
LABEL_20:
      v10 = HresultFromJetError;
      v27 = 0;
LABEL_21:
      v28 = (unsigned int)HresultFromJetError;
LABEL_22:
      Log_UnistoreHREvent_0(
        v28,
        v27,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
        v26);
      LeaveCriticalSection(a1 + 5);
      goto LABEL_16;
    }
    v10 = UnistoreJetSeek(v33[0], 1u);
    if ( v10 == -2147024871 )
    {
      if ( v35 )
      {
        Log_UnistoreHREvent_0(
          2147942425LL,
          0,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
          4879);
        LeaveCriticalSection(a1 + 5);
        v10 = -2147024871;
        goto LABEL_16;
      }
      HresultFromJetError = DBVolume::_CreateIdTableStoreRow((DBVolume *)a1);
      v10 = HresultFromJetError;
      if ( HresultFromJetError < 0 )
      {
        v26 = 4881;
LABEL_39:
        v27 = 1;
        goto LABEL_21;
      }
      v30 = CommsESE_JetMakeKey(*((_QWORD *)v33[0] + 1), *((_QWORD *)v33[0] + 2), &v35, 4u, 0x101u);
      if ( v30 < 0 )
      {
        HresultFromJetError = MakeHresultFromJetError(v30);
        v26 = 4888;
        goto LABEL_20;
      }
      v10 = UnistoreJetSeek(v33[0], 1u);
    }
    if ( (v10 & 0x80000000) != 0 )
    {
      v26 = 4892;
      v27 = 1;
      v28 = v10;
      goto LABEL_22;
    }
    HresultFromJetError = UnifiedStoreCursorLocation::CopyTo(
                            (struct TableHandleInfo *)((char *)v33[0] + 24),
                            (struct UnifiedStoreCursorLocation *)(v11 + 264),
                            0);
    v10 = HresultFromJetError;
    if ( HresultFromJetError >= 0 )
      goto LABEL_6;
    v26 = 4894;
    goto LABEL_39;
  }
  return 0;
}

```

## disassembly

```asm
0x18001d4a0  mov     [rsp-38h+arg_0], rbx
0x18001d4a5  mov     [rsp-38h+arg_8], edx
0x18001d4a9  push    rbp
0x18001d4aa  push    rsi
0x18001d4ab  push    rdi
0x18001d4ac  push    r12
0x18001d4ae  push    r13
0x18001d4b0  push    r14
0x18001d4b2  push    r15
0x18001d4b4  mov     rbp, rsp
0x18001d4b7  sub     rsp, 60h
0x18001d4bb  mov     rsi, rcx
0x18001d4be  xor     edi, edi
0x18001d4c0  mov     ecx, edx
0x18001d4c2  mov     [r8], edi
0x18001d4c5  mov     r13, r9
0x18001d4c8  mov     r12, r8
0x18001d4cb  mov     r10d, edx
0x18001d4ce  call    ?GetIdProp@@YAKW4US_TABLEID@@@Z; GetIdProp(US_TABLEID)
0x18001d4d3  cmp     eax, 1060003h
0x18001d4d8  jz      loc_18001D7A7
0x18001d4de  mov     rax, [rsi]
0x18001d4e1  mov     rcx, rsi
0x18001d4e4  mov     rax, [rax+38h]
0x18001d4e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d4ed  test    eax, eax
0x18001d4ef  jnz     short loc_18001D503
0x18001d4f1  mov     r8d, 12F0h
0x18001d4f7  lea     rdx, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001d4fe  call    Log_AssertionEvent
0x18001d503  xor     edx, edx
0x18001d505  mov     [rbp+var_10], rdi
0x18001d509  xorps   xmm0, xmm0
0x18001d50c  mov     [rbp+var_8], rdi
0x18001d510  lea     rax, [rbp+var_20]
0x18001d514  mov     r8, rsi
0x18001d517  lea     r9, [rbp+var_10]
0x18001d51b  mov     qword ptr [rsp+60h+var_40], rax
0x18001d520  lea     ecx, [rdx+35h]
0x18001d523  movdqu  xmmword ptr [rbp+var_20], xmm0
0x18001d528  call    ?GetTableHandle@@YAJW4US_TABLEID@@KPEAVIDBVolume@@AEAVauto_DBSession@@AEAVauto_TableHandle@@@Z; GetTableHandle(US_TABLEID,ulong,IDBVolume *,auto_DBSession &,auto_TableHandle &)
0x18001d52d  mov     ebx, eax
0x18001d52f  test    eax, eax
0x18001d531  js      loc_18001D7B7
0x18001d537  movsxd  r15, [rbp+arg_8]
0x18001d53b  lea     r14, [rsi+0C8h]
0x18001d542  shl     r15, 6
0x18001d546  mov     rcx, r14; lpCriticalSection
0x18001d549  add     r15, rsi
0x18001d54c  call    cs:__imp_EnterCriticalSection
0x18001d552  cmp     dword ptr [r15+108h], 0
0x18001d55a  mov     edi, 1
0x18001d55f  jz      loc_18001D68D
0x18001d565  mov     rcx, r14; lpCriticalSection
0x18001d568  call    cs:__imp_LeaveCriticalSection
0x18001d56e  cmp     dword ptr [r15+108h], 0
0x18001d576  jnz     short loc_18001D58A
0x18001d578  mov     r8d, 1322h
0x18001d57e  lea     rdx, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001d585  call    Log_AssertionEvent
0x18001d58a  mov     rax, [rsi]
0x18001d58d  mov     rcx, rsi
0x18001d590  mov     [rbp+var_30], rsi
0x18001d594  mov     rax, [rax+8]
0x18001d598  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d59d  mov     rax, [rsi]
0x18001d5a0  xor     ebx, ebx
0x18001d5a2  xor     r9d, r9d
0x18001d5a5  mov     [rbp+var_28], ebx
0x18001d5a8  xor     r8d, r8d
0x18001d5ab  mov     qword ptr [rsp+60h+var_40], rbx
0x18001d5b0  mov     rcx, rsi
0x18001d5b3  mov     rax, [rax+0B0h]
0x18001d5ba  lea     edx, [rbx+4]
0x18001d5bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d5c2  mov     r14d, eax
0x18001d5c5  test    eax, eax
0x18001d5c7  jns     loc_18001D683
0x18001d5cd  cmp     eax, 800400C9h
0x18001d5d2  jnz     loc_18001D8C0
0x18001d5d8  mov     rcx, [rbp+var_20]; struct TableHandleInfo *
0x18001d5dc  lea     rdx, [r15+108h]; struct UnifiedStoreCursorLocation *
0x18001d5e3  xor     r8d, r8d; int *
0x18001d5e6  call    ?UnistoreJetGotoBookmarkEx@@YAJPEAUTableHandleInfo@@AEBVUnifiedStoreCursorLocation@@PEAH@Z; UnistoreJetGotoBookmarkEx(TableHandleInfo *,UnifiedStoreCursorLocation const &,int *)
0x18001d5eb  mov     r14d, eax
0x18001d5ee  test    eax, eax
0x18001d5f0  js      loc_18001D8FC
0x18001d5f6  mov     rcx, [rbp+var_20]; struct TableHandleInfo *
0x18001d5fa  lea     rax, [rbp+arg_10]
0x18001d5fe  mov     qword ptr [rsp+60h+var_40], rax; int *
0x18001d603  mov     [rbp+arg_10], 0
0x18001d60a  call    ?ESEEscrowUpdate@@YAJPEAUTableHandleInfo@@KJHPEAJ@Z; ESEEscrowUpdate(TableHandleInfo *,ulong,long,int,long *)
0x18001d60f  mov     r14d, eax
0x18001d612  test    eax, eax
0x18001d614  js      loc_18001D71C
0x18001d61a  mov     r8d, [rbp+arg_10]
0x18001d61e  mov     rcx, rsi
0x18001d621  mov     edx, [rbp+arg_8]
0x18001d624  call    ?_MaybeUpdateHighWaterMark@DBVolume@@IEAAJW4US_TABLEID@@K@Z; DBVolume::_MaybeUpdateHighWaterMark(US_TABLEID,ulong)
0x18001d629  mov     r14d, eax
0x18001d62c  test    eax, eax
0x18001d62e  jns     loc_18001D6E5
0x18001d634  mov     r9d, 1330h
0x18001d63a  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001d641  mov     edx, edi
0x18001d643  mov     ecx, r14d
0x18001d646  call    Log_UnistoreHREvent_0
0x18001d64b  lea     rcx, [rbp+var_30]; this
0x18001d64f  call    ??1DBAutoTopLevelTransact@@QEAA@XZ; DBAutoTopLevelTransact::~DBAutoTopLevelTransact(void)
0x18001d654  mov     ebx, r14d
0x18001d657  lea     rcx, [rbp+var_20]; this
0x18001d65b  call    ??1auto_TableHandle@@QEAA@XZ; auto_TableHandle::~auto_TableHandle(void)
0x18001d660  lea     rcx, [rbp+var_10]; this
0x18001d664  call    ??1auto_DBSession@@QEAA@XZ; auto_DBSession::~auto_DBSession(void)
0x18001d669  mov     eax, ebx
0x18001d66b  mov     rbx, [rsp+60h+arg_0]
0x18001d673  add     rsp, 60h
0x18001d677  pop     r15
0x18001d679  pop     r14
0x18001d67b  pop     r13
0x18001d67d  pop     r12
0x18001d67f  pop     rdi
0x18001d680  pop     rsi
0x18001d681  pop     rbp
0x18001d682  retn
0x18001d683  mov     ebx, edi
0x18001d685  mov     [rbp+var_28], ebx
0x18001d688  jmp     loc_18001D5D8
0x18001d68d  mov     rcx, [rbp+var_20]
0x18001d691  lea     r8, [rbp+arg_8]; void *
0x18001d695  mov     r9d, 4; unsigned int
0x18001d69b  mov     [rsp+60h+var_40], 101h; JET_GRBIT
0x18001d6a3  mov     rdx, [rcx+10h]; unsigned __int64
0x18001d6a7  mov     rcx, [rcx+8]; unsigned __int64
0x18001d6ab  call    ?CommsESE_JetMakeKey@@YAJ_K0PEBXKK@Z; CommsESE_JetMakeKey(unsigned __int64,unsigned __int64,void const *,ulong,ulong)
0x18001d6b0  test    eax, eax
0x18001d6b2  jns     loc_18001D7D5
0x18001d6b8  mov     ecx, eax; int
0x18001d6ba  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x18001d6bf  mov     r9d, 1307h
0x18001d6c5  mov     ebx, eax
0x18001d6c7  xor     edx, edx
0x18001d6c9  mov     ecx, eax
0x18001d6cb  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001d6d2  call    Log_UnistoreHREvent_0
0x18001d6d7  mov     rcx, r14; lpCriticalSection
0x18001d6da  call    cs:__imp_LeaveCriticalSection
0x18001d6e0  jmp     loc_18001D657
0x18001d6e5  mov     eax, [rbp+arg_8]
0x18001d6e8  test    eax, eax
0x18001d6ea  jz      loc_18001D91E
0x18001d6f0  cmp     eax, 32h ; '2'
0x18001d6f3  jz      loc_18001D952
0x18001d6f9  test    ebx, ebx
0x18001d6fb  jnz     short loc_18001D727
0x18001d6fd  mov     eax, [rbp+arg_10]
0x18001d700  mov     [r13+0], eax
0x18001d704  mov     [r12], edi
0x18001d708  test    ebx, ebx
0x18001d70a  jnz     short loc_18001D788
0x18001d70c  lea     rcx, [rbp+var_30]; void *
0x18001d710  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18001d715  xor     ebx, ebx
0x18001d717  jmp     loc_18001D657
0x18001d71c  mov     r9d, 132Eh
0x18001d722  jmp     loc_18001D63A
0x18001d727  mov     rax, [rsi]
0x18001d72a  xor     r9d, r9d
0x18001d72d  xor     r8d, r8d
0x18001d730  mov     edx, edi
0x18001d732  mov     rcx, rsi
0x18001d735  mov     rax, [rax+0B8h]
0x18001d73c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d741  mov     ebx, eax
0x18001d743  test    eax, eax
0x18001d745  js      short loc_18001D74E
0x18001d747  xor     ebx, ebx
0x18001d749  mov     [rbp+var_28], ebx
0x18001d74c  jmp     short loc_18001D6FD
0x18001d74e  mov     r9d, 3ACh
0x18001d754  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001d75b  mov     edx, edi
0x18001d75d  mov     ecx, ebx
0x18001d75f  call    Log_UnistoreHREvent_0
0x18001d764  mov     r9d, 133Bh
0x18001d76a  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001d771  mov     edx, edi
0x18001d773  mov     ecx, ebx
0x18001d775  call    Log_UnistoreHREvent_0
0x18001d77a  lea     rcx, [rbp+var_30]; this
0x18001d77e  call    ??1DBAutoTopLevelTransact@@QEAA@XZ; DBAutoTopLevelTransact::~DBAutoTopLevelTransact(void)
0x18001d783  jmp     loc_18001D657
0x18001d788  mov     rax, [rsi]
0x18001d78b  xor     r9d, r9d
0x18001d78e  xor     r8d, r8d
0x18001d791  xor     edx, edx
0x18001d793  mov     rcx, rsi
0x18001d796  mov     rax, [rax+0B8h]
0x18001d79d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7a2  jmp     loc_18001D70C
0x18001d7a7  test    r10d, r10d
0x18001d7aa  jz      loc_18001D4DE
0x18001d7b0  xor     eax, eax
0x18001d7b2  jmp     loc_18001D66B
0x18001d7b7  mov     r9d, 12F6h
0x18001d7bd  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001d7c4  mov     edx, 1
0x18001d7c9  mov     ecx, eax
0x18001d7cb  call    Log_UnistoreHREvent_0
0x18001d7d0  jmp     loc_18001D657
0x18001d7d5  mov     rcx, [rbp+var_20]; struct TableHandleInfo *
0x18001d7d9  mov     edx, edi; unsigned int
0x18001d7db  call    ?UnistoreJetSeek@@YAJPEAUTableHandleInfo@@K@Z; UnistoreJetSeek(TableHandleInfo *,ulong)
0x18001d7e0  mov     ebx, eax
0x18001d7e2  mov     eax, 80070019h
0x18001d7e7  cmp     ebx, eax
0x18001d7e9  jnz     loc_18001D887
0x18001d7ef  cmp     [rbp+arg_8], 0
0x18001d7f3  jz      short loc_18001D81E
0x18001d7f5  mov     r9d, 130Fh
0x18001d7fb  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001d802  xor     edx, edx
0x18001d804  mov     ecx, eax
0x18001d806  call    Log_UnistoreHREvent_0
0x18001d80b  mov     rcx, r14; lpCriticalSection
0x18001d80e  call    cs:__imp_LeaveCriticalSection
0x18001d814  mov     ebx, 80070019h
0x18001d819  jmp     loc_18001D657
0x18001d81e  mov     rcx, rsi; this
0x18001d821  call    ?_CreateIdTableStoreRow@DBVolume@@IEAAJXZ; DBVolume::_CreateIdTableStoreRow(void)
0x18001d826  mov     ebx, eax
0x18001d828  test    eax, eax
0x18001d82a  jns     short loc_18001D841
0x18001d82c  mov     r9d, 1311h
0x18001d832  jmp     short loc_18001D83A
0x18001d834  mov     r9d, 131Eh
0x18001d83a  mov     edx, edi
0x18001d83c  jmp     loc_18001D6C9
0x18001d841  mov     rcx, [rbp+var_20]
0x18001d845  lea     r8, [rbp+arg_8]; void *
0x18001d849  mov     r9d, 4; unsigned int
0x18001d84f  mov     [rsp+60h+var_40], 101h; JET_GRBIT
0x18001d857  mov     rdx, [rcx+10h]; unsigned __int64
0x18001d85b  mov     rcx, [rcx+8]; unsigned __int64
0x18001d85f  call    ?CommsESE_JetMakeKey@@YAJ_K0PEBXKK@Z; CommsESE_JetMakeKey(unsigned __int64,unsigned __int64,void const *,ulong,ulong)
0x18001d864  test    eax, eax
0x18001d866  jns     short loc_18001D87A
0x18001d868  mov     ecx, eax; int
0x18001d86a  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x18001d86f  mov     r9d, 1318h
0x18001d875  jmp     loc_18001D6C5
0x18001d87a  mov     rcx, [rbp+var_20]; struct TableHandleInfo *
0x18001d87e  mov     edx, edi; unsigned int
0x18001d880  call    ?UnistoreJetSeek@@YAJPEAUTableHandleInfo@@K@Z; UnistoreJetSeek(TableHandleInfo *,ulong)
0x18001d885  mov     ebx, eax
0x18001d887  test    ebx, ebx
0x18001d889  jns     short loc_18001D89A
0x18001d88b  mov     r9d, 131Ch
0x18001d891  mov     edx, edi
0x18001d893  mov     ecx, ebx
0x18001d895  jmp     loc_18001D6CB
0x18001d89a  mov     rcx, [rbp+var_20]
0x18001d89e  lea     rdx, [r15+108h]; struct UnifiedStoreCursorLocation *
0x18001d8a5  add     rcx, 18h; this
0x18001d8a9  xor     r8d, r8d; int
0x18001d8ac  call    ?CopyTo@UnifiedStoreCursorLocation@@QEBAJAEAV1@H@Z; UnifiedStoreCursorLocation::CopyTo(UnifiedStoreCursorLocation &,int)
0x18001d8b1  mov     ebx, eax
0x18001d8b3  test    eax, eax
0x18001d8b5  jns     loc_18001D565
0x18001d8bb  jmp     loc_18001D834
0x18001d8c0  mov     r9d, 395h
0x18001d8c6  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001d8cd  xor     edx, edx
0x18001d8cf  mov     ecx, r14d
0x18001d8d2  call    Log_UnistoreHREvent_0
0x18001d8d7  mov     r9d, 1326h
0x18001d8dd  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001d8e4  mov     edx, edi
0x18001d8e6  mov     ecx, r14d
0x18001d8e9  call    Log_UnistoreHREvent_0
0x18001d8ee  lea     rcx, [rbp+var_30]; void *
0x18001d8f2  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18001d8f7  jmp     loc_18001D654
0x18001d8fc  mov     r9d, 35Bh
0x18001d902  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001d909  mov     edx, edi
0x18001d90b  mov     ecx, r14d
0x18001d90e  call    Log_UnistoreHREvent_0
0x18001d913  mov     r9d, 1329h
0x18001d919  jmp     loc_18001D63A
0x18001d91e  mov     r9d, [rbp+arg_10]; unsigned int
0x18001d922  lea     r8, ?c_wszUnistoreRegistryLastStoreId@@3QBGB; "LastStoreId"
0x18001d929  lea     rdx, ?c_wszUnistoreRegistryRoot@@3QBGB; "Software\\Microsoft\\Unified Store"
0x18001d930  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18001d937  call    ?RegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; RegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18001d93c  mov     r14d, eax
0x18001d93f  test    eax, eax
0x18001d941  jns     loc_18001D6F9
0x18001d947  mov     r9d, 1334h
0x18001d94d  jmp     loc_18001D63A
  ... truncated ...
```
