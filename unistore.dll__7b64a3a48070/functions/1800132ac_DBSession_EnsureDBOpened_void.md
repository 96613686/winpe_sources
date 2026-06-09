# DBSession::_EnsureDBOpened(void)

- ea: `0x1800132ac`
- end: `0x18001347c`
- name: `?_EnsureDBOpened@DBSession@@AEAAJXZ`
- size: `464`
- prototype: `__int64 __fastcall(DBSession *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012ed0`

## callees

- `0x1800068f0`
- `0x18000f530`
- `0x180011ed0`
- `0x1800132ac`
- `0x180013524`
- `0x1800173d0`
- `0x180058490`
- `0x1800737b4`
- `0x1800acb54`
- `0x1800c50f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800133af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800133af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800133f6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800133f6`
- `ESENT!JetOpenDatabaseW` at `0x18001335f`
- `ESENT!JetOpenDatabaseW` at `0x18001335f`

## string_xrefs

- `0x1800133e0`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180013402`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbsession.cpp`
- `0x180013463`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbsession.cpp`

## pseudocode

```c
__int64 __fastcall DBSession::_EnsureDBOpened(DBSession *this)
{
  JET_DBID *v1; // rsi
  __int64 v3; // rdx
  __int64 v4; // rcx
  int v5; // edi
  unsigned int v6; // r8d
  JET_ERR v7; // ebx
  __int64 v9; // r8
  int USDeviceStoreFolderPath; // eax
  __int64 v11; // r9
  unsigned int HresultFromJetError; // ebx
  _RTL_CRITICAL_SECTION *v13; // [rsp+30h] [rbp-248h] BYREF
  char v14; // [rsp+38h] [rbp-240h]
  WCHAR szFilename[264]; // [rsp+40h] [rbp-238h] BYREF

  v1 = (JET_DBID *)((char *)this + 224);
  if ( *((_DWORD *)this + 56) != -1 )
    return 0;
  if ( !word_18010D410 )
  {
    v13 = &g_csGlobalLock;
    EnterCriticalSection(&g_csGlobalLock);
    v14 = 1;
    if ( !word_18010D410 )
    {
      USDeviceStoreFolderPath = GetUSDeviceStoreFolderPath(&word_18010D410, 0x104u, v9);
      v5 = USDeviceStoreFolderPath;
      if ( USDeviceStoreFolderPath < 0 )
      {
        Log_UnistoreHREvent_0(
          (unsigned int)USDeviceStoreFolderPath,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
          386);
        LeaveCriticalSection(&g_csGlobalLock);
        v11 = 2093;
LABEL_12:
        Log_UnistoreHREvent_0(
          (unsigned int)v5,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbsession.cpp",
          v11);
        return (unsigned int)v5;
      }
    }
    ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v13);
  }
  v5 = StringCchPrintfW(szFilename, 0x104u, L"%s%s", &word_18010D410, L"store.vol");
  if ( v5 < 0 )
  {
    v11 = 2097;
    goto LABEL_12;
  }
  if ( *((_QWORD *)this + 27) == -1 )
    Log_AssertionEvent_3(v4, v3, 2099);
  if ( *((_DWORD *)this + 50) )
  {
    v5 = CommsESE_JetAttachDatabaseW_Log(*((_QWORD *)this + 27), szFilename, v6);
    if ( v5 < 0 )
    {
      v11 = 2102;
      goto LABEL_12;
    }
  }
  v7 = JetOpenDatabaseW(*((_QWORD *)this + 27), szFilename, 0, v1, 0);
  CheckCorruption(v7);
  if ( v7 >= 0 )
    return 0;
  HresultFromJetError = MakeHresultFromJetError(v7);
  Log_UnistoreHREvent_0(
    HresultFromJetError,
    0,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbsession.cpp",
    2104);
  return HresultFromJetError;
}

```

## disassembly

```asm
0x1800132ac  mov     [rsp+arg_8], rbx
0x1800132b1  mov     [rsp+arg_10], rbp
0x1800132b6  push    rsi
0x1800132b7  push    rdi
0x1800132b8  push    r15
0x1800132ba  sub     rsp, 260h
0x1800132c1  mov     rax, cs:__security_cookie
0x1800132c8  xor     rax, rsp
0x1800132cb  mov     [rsp+278h+var_28], rax
0x1800132d3  lea     rsi, [rcx+0E0h]
0x1800132da  mov     rbx, rcx
0x1800132dd  cmp     dword ptr [rsi], 0FFFFFFFFh
0x1800132e0  jnz     loc_180013376
0x1800132e6  xor     ebp, ebp
0x1800132e8  cmp     cs:word_18010D410, bp
0x1800132ef  jz      loc_1800133A0
0x1800132f5  lea     rax, ?gc_szUSVolumeName@@3QBGB; "store.vol"
0x1800132fc  mov     edx, 104h; unsigned __int64
0x180013301  lea     r9, word_18010D410
0x180013308  mov     qword ptr [rsp+278h+grbit], rax
0x18001330d  lea     r8, aSS_1; "%s%s"
0x180013314  lea     rcx, [rsp+278h+szFilename]; unsigned __int16 *
0x180013319  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001331e  mov     edi, eax
0x180013320  test    eax, eax
0x180013322  js      loc_18001342B
0x180013328  cmp     qword ptr [rbx+0D8h], 0FFFFFFFFFFFFFFFFh
0x180013330  jnz     short loc_18001333D
0x180013332  mov     r8d, 833h
0x180013338  call    Log_AssertionEvent_3
0x18001333d  cmp     [rbx+0C8h], ebp
0x180013343  jnz     loc_180013433
0x180013349  mov     rcx, [rbx+0D8h]; sesid
0x180013350  lea     rdx, [rsp+278h+szFilename]; szFilename
0x180013355  mov     r9, rsi; pdbid
0x180013358  mov     [rsp+278h+grbit], ebp; grbit
0x18001335c  xor     r8d, r8d; szConnect
0x18001335f  call    cs:__imp_JetOpenDatabaseW
0x180013365  mov     ecx, eax; int
0x180013367  mov     ebx, eax
0x180013369  call    ?CheckCorruption@@YAXJ@Z; CheckCorruption(long)
0x18001336e  test    ebx, ebx
0x180013370  js      loc_180013456
0x180013376  xor     eax, eax
0x180013378  mov     rcx, [rsp+278h+var_28]
0x180013380  xor     rcx, rsp; StackCookie
0x180013383  call    __security_check_cookie
0x180013388  lea     r11, [rsp+278h+var_18]
0x180013390  mov     rbx, [r11+28h]
0x180013394  mov     rbp, [r11+30h]
0x180013398  mov     rsp, r11
0x18001339b  pop     r15
0x18001339d  pop     rdi
0x18001339e  pop     rsi
0x18001339f  retn
0x1800133a0  lea     r15, ?g_csGlobalLock@@3VCComAutoCriticalSection@ATL@@A; ATL::CComAutoCriticalSection g_csGlobalLock
0x1800133a7  mov     rcx, r15; lpCriticalSection
0x1800133aa  mov     [rsp+278h+var_248], r15
0x1800133af  call    cs:__imp_EnterCriticalSection
0x1800133b5  cmp     cs:word_18010D410, bp
0x1800133bc  mov     [rsp+278h+var_240], 1
0x1800133c1  jnz     short loc_18001341C
0x1800133c3  mov     edx, 104h; unsigned __int64
0x1800133c8  lea     rcx, word_18010D410; unsigned __int16 *
0x1800133cf  call    ?GetUSDeviceStoreFolderPath@@YAJPEAG_K@Z; GetUSDeviceStoreFolderPath(ushort *,unsigned __int64)
0x1800133d4  mov     edi, eax
0x1800133d6  test    eax, eax
0x1800133d8  jns     short loc_18001341C
0x1800133da  mov     r9d, 182h
0x1800133e0  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800133e7  mov     edx, 1
0x1800133ec  mov     ecx, eax
0x1800133ee  call    Log_UnistoreHREvent_0
0x1800133f3  mov     rcx, r15; lpCriticalSection
0x1800133f6  call    cs:__imp_LeaveCriticalSection
0x1800133fc  mov     r9d, 82Dh
0x180013402  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180013409  mov     edx, 1
0x18001340e  mov     ecx, edi
0x180013410  call    Log_UnistoreHREvent_0
0x180013415  mov     eax, edi
0x180013417  jmp     loc_180013378
0x18001341c  lea     rcx, [rsp+278h+var_248]
0x180013421  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180013426  jmp     loc_1800132F5
0x18001342b  mov     r9d, 831h
0x180013431  jmp     short loc_180013402
0x180013433  mov     rcx, [rbx+0D8h]; unsigned __int64
0x18001343a  lea     rdx, [rsp+278h+szFilename]; unsigned __int16 *
0x18001343f  call    ?CommsESE_JetAttachDatabaseW_Log@@YAJ_KPEBGK@Z; CommsESE_JetAttachDatabaseW_Log(unsigned __int64,ushort const *,ulong)
0x180013444  mov     edi, eax
0x180013446  test    eax, eax
0x180013448  jns     loc_180013349
0x18001344e  mov     r9d, 836h
0x180013454  jmp     short loc_180013402
0x180013456  mov     ecx, ebx; int
0x180013458  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x18001345d  mov     r9d, 838h
0x180013463  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001346a  xor     edx, edx
0x18001346c  mov     ecx, eax
0x18001346e  mov     ebx, eax
0x180013470  call    Log_UnistoreHREvent_0
0x180013475  mov     eax, ebx
0x180013477  jmp     loc_180013378
```
