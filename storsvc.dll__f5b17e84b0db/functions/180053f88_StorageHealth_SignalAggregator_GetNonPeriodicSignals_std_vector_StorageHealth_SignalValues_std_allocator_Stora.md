# StorageHealth::SignalAggregator::GetNonPeriodicSignals(std::vector<StorageHealth::_SignalValues,std::allocator<StorageHealth::_SignalValues>> &,std::vector<StorageHealth::_SignalInfo,std::allocator<StorageHealth::_SignalInfo>> &,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x180053f88`
- end: `0x1800542a1`
- name: `?GetNonPeriodicSignals@SignalAggregator@StorageHealth@@AEAAJAEAV?$vector@U_SignalValues@StorageHealth@@V?$allocator@U_SignalValues@StorageHealth@@@std@@@std@@AEAV?$vector@U_SignalInfo@StorageHealth@@V?$allocator@U_SignalInfo@StorageHealth@@@std@@@4@AEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@4@@Z`
- size: `793`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180054558`

## callees

- `0x18000d030`
- `0x180012734`
- `0x18001c208`
- `0x18001f634`
- `0x18002ce80`
- `0x18002e740`
- `0x1800345bc`
- `0x18004b7c0`
- `0x18004d730`
- `0x180051384`
- `0x180052168`
- `0x180052d5c`
- `0x180053334`
- `0x180053d68`
- `0x180053f88`
- `0x18005516c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18005406c`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18005406c`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180054040`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180054058`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180054040`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180054058`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall StorageHealth::SignalAggregator::GetNonPeriodicSignals(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v7; // r12
  __int64 v8; // rdi
  int updated; // eax
  unsigned int v10; // esi
  unsigned int v12; // r14d
  unsigned __int64 v13; // rdi
  unsigned __int64 i; // rsi
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rcx
  unsigned __int64 v21; // rsi
  unsigned __int64 v22; // rdi
  __int64 v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // rdx
  FILETIME FileTime2; // [rsp+20h] [rbp-B9h] BYREF
  struct _FILETIME FileTime; // [rsp+28h] [rbp-B1h] BYREF
  _BYTE v29[40]; // [rsp+38h] [rbp-A1h] BYREF
  _BYTE v30[32]; // [rsp+60h] [rbp-79h] BYREF
  _BYTE v31[48]; // [rsp+80h] [rbp-59h] BYREF
  SYSTEMTIME SystemTime; // [rsp+B0h] [rbp-29h] BYREF
  _BYTE v33[32]; // [rsp+C0h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+5Fh]

  v7 = *a2;
  v8 = a2[1];
  SystemTime = *(SYSTEMTIME *)(*a2 + 4LL);
  updated = UpdateTimeOffset(&SystemTime, -*(_DWORD *)(a1 + 8));
  v10 = updated;
  if ( updated >= 0 )
  {
    v12 = 0;
    v13 = 0xAAAAAAAAAAAAAAABuLL * ((v8 - v7) >> 4);
    for ( i = 0; i < v13; ++i )
    {
      FileTime = 0;
      if ( !SystemTimeToFileTime((const SYSTEMTIME *)(*a2 + 4LL + 48 * i), &FileTime) )
      {
        v15 = 66;
        goto LABEL_11;
      }
      FileTime2 = 0;
      if ( !SystemTimeToFileTime(&SystemTime, &FileTime2) )
      {
        v15 = 70;
LABEL_11:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v15,
          (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagehealth\\TimeUtils.h",
          (const char *)0x80004005LL,
          FileTime2.dwLowDateTime);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x8D,
          (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagehealth\\signalaggregator.cpp",
          (const char *)0x80004005LL,
          FileTime2.dwLowDateTime);
        return 2147500037LL;
      }
      if ( CompareFileTime(&FileTime, &FileTime2) < 0 )
        break;
      ++v12;
    }
    StorageHealth::_SignalInfo::_SignalInfo((StorageHealth::_SignalInfo *)v30);
    std::wstring::assign(v30, L"nActiveDaysInWindow");
    std::wstring::assign(v31, L"NonPeriodic");
    v17 = *(_QWORD *)(a3 + 8);
    if ( v17 == *(_QWORD *)(a3 + 16) )
    {
      std::vector<StorageHealth::_SignalInfo>::_Emplace_reallocate<StorageHealth::_SignalInfo const &>(a3, v17, v30);
    }
    else
    {
      std::_Default_allocator_traits<std::allocator<StorageHealth::_SignalInfo>>::construct<StorageHealth::_SignalInfo,StorageHealth::_SignalInfo const &>(
        v16,
        v17,
        v30);
      *(_QWORD *)(a3 + 8) += 72LL;
    }
    v18 = std::to_wstring(v29, v12);
    std::vector<std::wstring>::push_back(a4, v18);
    std::wstring::_Tidy_deallocate(v29);
    std::wstring::wstring(v33, L"01/01/2000");
    FileTime = 0;
    FileTime2 = 0;
    v19 = std::wstring::wstring(v29, v33);
    if ( (int)StorageHealth::SignalAggregator::GetDeviceAge(v20, v19, &FileTime, &FileTime2) < 0 )
    {
      v21 = 0;
      v22 = 0;
    }
    else
    {
      v21 = *(unsigned __int64 *)&FileTime / 0x15180;
      v22 = *(unsigned __int64 *)&FileTime2 / 0x15180;
    }
    std::wstring::assign(v30, L"DeviceAge");
    std::wstring::assign(v31, L"NonPeriodic");
    v24 = *(_QWORD *)(a3 + 8);
    if ( v24 == *(_QWORD *)(a3 + 16) )
    {
      std::vector<StorageHealth::_SignalInfo>::_Emplace_reallocate<StorageHealth::_SignalInfo const &>(a3, v24, v30);
    }
    else
    {
      std::_Default_allocator_traits<std::allocator<StorageHealth::_SignalInfo>>::construct<StorageHealth::_SignalInfo,StorageHealth::_SignalInfo const &>(
        v23,
        v24,
        v30);
      *(_QWORD *)(a3 + 8) += 72LL;
    }
    std::_Integral_to_string<unsigned short,unsigned __int64>(v29, v21);
    std::vector<std::wstring>::push_back(a4, v29);
    std::wstring::_Tidy_deallocate(v29);
    std::wstring::assign(v30, L"DeviceCreationDateAge");
    std::wstring::assign(v31, L"NonPeriodic");
    v26 = *(_QWORD *)(a3 + 8);
    if ( v26 == *(_QWORD *)(a3 + 16) )
    {
      std::vector<StorageHealth::_SignalInfo>::_Emplace_reallocate<StorageHealth::_SignalInfo const &>(a3, v26, v30);
    }
    else
    {
      std::_Default_allocator_traits<std::allocator<StorageHealth::_SignalInfo>>::construct<StorageHealth::_SignalInfo,StorageHealth::_SignalInfo const &>(
        v25,
        v26,
        v30);
      *(_QWORD *)(a3 + 8) += 72LL;
    }
    std::_Integral_to_string<unsigned short,unsigned __int64>(v29, v22);
    std::vector<std::wstring>::push_back(a4, v29);
    std::wstring::_Tidy_deallocate(v29);
    std::wstring::_Tidy_deallocate(v33);
    StorageHealth::_SignalInfo::~_SignalInfo((StorageHealth::_SignalInfo *)v30);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x88,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagehealth\\signalaggregator.cpp",
      (const char *)(unsigned int)updated,
      FileTime2.dwLowDateTime);
    return v10;
  }
}

```

## disassembly

```asm
0x180053f88  push    rbp
0x180053f8a  push    rbx
0x180053f8b  push    rsi
0x180053f8c  push    rdi
0x180053f8d  push    r12
0x180053f8f  push    r13
0x180053f91  push    r14
0x180053f93  push    r15
0x180053f95  lea     rbp, [rsp-1Fh]
0x180053f9a  sub     rsp, 0F8h
0x180053fa1  mov     rax, cs:__security_cookie
0x180053fa8  xor     rax, rsp
0x180053fab  mov     [rbp+57h+var_50], rax
0x180053faf  mov     r13, r9
0x180053fb2  mov     rbx, r8
0x180053fb5  mov     r15, rdx
0x180053fb8  mov     r12, [rdx]
0x180053fbb  mov     rdi, [rdx+8]
0x180053fbf  movups  xmm0, xmmword ptr [r12+4]
0x180053fc5  movdqu  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x180053fca  mov     edx, [rcx+8]
0x180053fcd  neg     edx; int
0x180053fcf  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x180053fd3  call    ?UpdateTimeOffset@@YAJAEAU_SYSTEMTIME@@J@Z; UpdateTimeOffset(_SYSTEMTIME &,long)
0x180053fd8  mov     esi, eax
0x180053fda  test    eax, eax
0x180053fdc  jns     short loc_180053FFD
0x180053fde  mov     rcx, [rbp+5Fh]; this
0x180053fe2  mov     r9d, eax; char *
0x180053fe5  lea     r8, aOnecoreDrivers_4; "onecore\\drivers\\storage\\storsvc\\sto"...
0x180053fec  mov     edx, 88h; void *
0x180053ff1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053ff6  mov     eax, esi
0x180053ff8  jmp     loc_180054281
0x180053ffd  xor     r14d, r14d
0x180054000  sub     rdi, r12
0x180054003  sar     rdi, 4
0x180054007  mov     rax, 0AAAAAAAAAAAAAAABh
0x180054011  imul    rdi, rax
0x180054015  xor     r12d, r12d
0x180054018  mov     esi, r12d
0x18005401b  cmp     rsi, rdi
0x18005401e  jnb     loc_1800540C1
0x180054024  mov     qword ptr [rsp+130h+FileTime.dwLowDateTime], r12
0x180054029  lea     rcx, [rsi+rsi*2]
0x18005402d  shl     rcx, 4
0x180054031  mov     rax, [r15]
0x180054034  add     rax, 4
0x180054038  add     rcx, rax; lpSystemTime
0x18005403b  lea     rdx, [rsp+130h+FileTime]; lpFileTime
0x180054040  call    cs:__imp_SystemTimeToFileTime
0x180054046  test    eax, eax
0x180054048  jz      short loc_180054085
0x18005404a  mov     qword ptr [rsp+130h+FileTime2.dwLowDateTime], r12
0x18005404f  lea     rdx, [rsp+130h+FileTime2]; lpFileTime
0x180054054  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x180054058  call    cs:__imp_SystemTimeToFileTime
0x18005405e  test    eax, eax
0x180054060  jz      short loc_18005407E
0x180054062  lea     rdx, [rsp+130h+FileTime2]; lpFileTime2
0x180054067  lea     rcx, [rsp+130h+FileTime]; lpFileTime1
0x18005406c  call    cs:__imp_CompareFileTime
0x180054072  test    eax, eax
0x180054074  js      short loc_1800540C1
0x180054076  inc     r14d
0x180054079  inc     rsi
0x18005407c  jmp     short loc_18005401B
0x18005407e  mov     edx, 46h ; 'F'
0x180054083  jmp     short loc_18005408A
0x180054085  mov     edx, 42h ; 'B'; void *
0x18005408a  mov     ebx, 80004005h
0x18005408f  mov     r9d, ebx; char *
0x180054092  lea     r8, aOnecoreDrivers_19; "onecore\\drivers\\storage\\storsvc\\sto"...
0x180054099  mov     rcx, [rbp+5Fh]; this
0x18005409d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800540a2  mov     rcx, [rbp+5Fh]; this
0x1800540a6  mov     r9d, ebx; char *
0x1800540a9  lea     r8, aOnecoreDrivers_4; "onecore\\drivers\\storage\\storsvc\\sto"...
0x1800540b0  mov     edx, 8Dh; void *
0x1800540b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800540ba  mov     eax, ebx
0x1800540bc  jmp     loc_180054281
0x1800540c1  lea     rcx, [rbp+57h+var_D0]; this
0x1800540c5  call    ??0_SignalInfo@StorageHealth@@QEAA@XZ; StorageHealth::_SignalInfo::_SignalInfo(void)
0x1800540ca  nop
0x1800540cb  lea     rdx, aNactivedaysinw; "nActiveDaysInWindow"
0x1800540d2  lea     rcx, [rbp+57h+var_D0]
0x1800540d6  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800540db  lea     r15, aNonperiodic; "NonPeriodic"
0x1800540e2  mov     rdx, r15
0x1800540e5  lea     rcx, [rbp+57h+var_B0]
0x1800540e9  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800540ee  mov     rdx, [rbx+8]
0x1800540f2  lea     r8, [rbp+57h+var_D0]
0x1800540f6  cmp     rdx, [rbx+10h]
0x1800540fa  jz      short loc_180054108
0x1800540fc  call    ??$construct@U_SignalInfo@StorageHealth@@AEBU12@@?$_Default_allocator_traits@V?$allocator@U_SignalInfo@StorageHealth@@@std@@@std@@SAXAEAV?$allocator@U_SignalInfo@StorageHealth@@@1@QEAU_SignalInfo@StorageHealth@@AEBU34@@Z; std::_Default_allocator_traits<std::allocator<StorageHealth::_SignalInfo>>::construct<StorageHealth::_SignalInfo,StorageHealth::_SignalInfo const &>(std::allocator<StorageHealth::_SignalInfo> &,StorageHealth::_SignalInfo * const,StorageHealth::_SignalInfo const &)
0x180054101  add     qword ptr [rbx+8], 48h ; 'H'
0x180054106  jmp     short loc_180054110
0x180054108  mov     rcx, rbx
0x18005410b  call    ??$_Emplace_reallocate@AEBU_SignalInfo@StorageHealth@@@?$vector@U_SignalInfo@StorageHealth@@V?$allocator@U_SignalInfo@StorageHealth@@@std@@@std@@AEAAPEAU_SignalInfo@StorageHealth@@QEAU23@AEBU23@@Z; std::vector<StorageHealth::_SignalInfo>::_Emplace_reallocate<StorageHealth::_SignalInfo const &>(StorageHealth::_SignalInfo * const,StorageHealth::_SignalInfo const &)
0x180054110  mov     edx, r14d
0x180054113  lea     rcx, [rsp+130h+var_F8]
0x180054118  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@H@Z; std::to_wstring(int)
0x18005411d  nop
0x18005411e  mov     rdx, rax
0x180054121  mov     rcx, r13
0x180054124  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x180054129  nop
0x18005412a  lea     rcx, [rsp+130h+var_F8]
0x18005412f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180054134  lea     rdx, a01012000; "01/01/2000"
0x18005413b  lea     rcx, [rbp+57h+var_70]
0x18005413f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180054144  nop
0x180054145  mov     qword ptr [rsp+130h+FileTime.dwLowDateTime], r12
0x18005414a  mov     qword ptr [rsp+130h+FileTime2.dwLowDateTime], r12
0x18005414f  lea     rdx, [rbp+57h+var_70]
0x180054153  lea     rcx, [rsp+130h+var_F8]
0x180054158  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18005415d  lea     r9, [rsp+130h+FileTime2]
0x180054162  lea     r8, [rsp+130h+FileTime]
0x180054167  mov     rdx, rax
0x18005416a  call    ?GetDeviceAge@SignalAggregator@StorageHealth@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEA_K1@Z; StorageHealth::SignalAggregator::GetDeviceAge(std::wstring,unsigned __int64 &,unsigned __int64 &)
0x18005416f  test    eax, eax
0x180054171  js      short loc_18005419D
0x180054173  mov     rcx, 0C22E450672894AB7h
0x18005417d  mov     rax, rcx
0x180054180  mul     qword ptr [rsp+130h+FileTime.dwLowDateTime]
0x180054185  mov     rsi, rdx
0x180054188  shr     rsi, 10h
0x18005418c  mov     rax, rcx
0x18005418f  mul     qword ptr [rsp+130h+FileTime2.dwLowDateTime]
0x180054194  mov     rdi, rdx
0x180054197  shr     rdi, 10h
0x18005419b  jmp     short loc_1800541A3
0x18005419d  mov     rsi, r12
0x1800541a0  mov     rdi, r12
0x1800541a3  lea     rdx, aDeviceage; "DeviceAge"
0x1800541aa  lea     rcx, [rbp+57h+var_D0]
0x1800541ae  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800541b3  mov     rdx, r15
0x1800541b6  lea     rcx, [rbp+57h+var_B0]
0x1800541ba  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800541bf  mov     rdx, [rbx+8]
0x1800541c3  lea     r8, [rbp+57h+var_D0]
0x1800541c7  cmp     rdx, [rbx+10h]
0x1800541cb  jz      short loc_1800541D9
0x1800541cd  call    ??$construct@U_SignalInfo@StorageHealth@@AEBU12@@?$_Default_allocator_traits@V?$allocator@U_SignalInfo@StorageHealth@@@std@@@std@@SAXAEAV?$allocator@U_SignalInfo@StorageHealth@@@1@QEAU_SignalInfo@StorageHealth@@AEBU34@@Z; std::_Default_allocator_traits<std::allocator<StorageHealth::_SignalInfo>>::construct<StorageHealth::_SignalInfo,StorageHealth::_SignalInfo const &>(std::allocator<StorageHealth::_SignalInfo> &,StorageHealth::_SignalInfo * const,StorageHealth::_SignalInfo const &)
0x1800541d2  add     qword ptr [rbx+8], 48h ; 'H'
0x1800541d7  jmp     short loc_1800541E1
0x1800541d9  mov     rcx, rbx
0x1800541dc  call    ??$_Emplace_reallocate@AEBU_SignalInfo@StorageHealth@@@?$vector@U_SignalInfo@StorageHealth@@V?$allocator@U_SignalInfo@StorageHealth@@@std@@@std@@AEAAPEAU_SignalInfo@StorageHealth@@QEAU23@AEBU23@@Z; std::vector<StorageHealth::_SignalInfo>::_Emplace_reallocate<StorageHealth::_SignalInfo const &>(StorageHealth::_SignalInfo * const,StorageHealth::_SignalInfo const &)
0x1800541e1  mov     rdx, rsi
0x1800541e4  lea     rcx, [rsp+130h+var_F8]
0x1800541e9  call    ??$_Integral_to_string@G_K@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@_K@Z; std::_Integral_to_string<ushort,unsigned __int64>(unsigned __int64)
0x1800541ee  nop
0x1800541ef  lea     rdx, [rsp+130h+var_F8]
0x1800541f4  mov     rcx, r13
0x1800541f7  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x1800541fc  nop
0x1800541fd  lea     rcx, [rsp+130h+var_F8]
0x180054202  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180054207  lea     rdx, aDevicecreation; "DeviceCreationDateAge"
0x18005420e  lea     rcx, [rbp+57h+var_D0]
0x180054212  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180054217  mov     rdx, r15
0x18005421a  lea     rcx, [rbp+57h+var_B0]
0x18005421e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180054223  mov     rdx, [rbx+8]
0x180054227  lea     r8, [rbp+57h+var_D0]
0x18005422b  cmp     rdx, [rbx+10h]
0x18005422f  jz      short loc_18005423D
0x180054231  call    ??$construct@U_SignalInfo@StorageHealth@@AEBU12@@?$_Default_allocator_traits@V?$allocator@U_SignalInfo@StorageHealth@@@std@@@std@@SAXAEAV?$allocator@U_SignalInfo@StorageHealth@@@1@QEAU_SignalInfo@StorageHealth@@AEBU34@@Z; std::_Default_allocator_traits<std::allocator<StorageHealth::_SignalInfo>>::construct<StorageHealth::_SignalInfo,StorageHealth::_SignalInfo const &>(std::allocator<StorageHealth::_SignalInfo> &,StorageHealth::_SignalInfo * const,StorageHealth::_SignalInfo const &)
0x180054236  add     qword ptr [rbx+8], 48h ; 'H'
0x18005423b  jmp     short loc_180054245
0x18005423d  mov     rcx, rbx
0x180054240  call    ??$_Emplace_reallocate@AEBU_SignalInfo@StorageHealth@@@?$vector@U_SignalInfo@StorageHealth@@V?$allocator@U_SignalInfo@StorageHealth@@@std@@@std@@AEAAPEAU_SignalInfo@StorageHealth@@QEAU23@AEBU23@@Z; std::vector<StorageHealth::_SignalInfo>::_Emplace_reallocate<StorageHealth::_SignalInfo const &>(StorageHealth::_SignalInfo * const,StorageHealth::_SignalInfo const &)
0x180054245  mov     rdx, rdi
0x180054248  lea     rcx, [rsp+130h+var_F8]
0x18005424d  call    ??$_Integral_to_string@G_K@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@_K@Z; std::_Integral_to_string<ushort,unsigned __int64>(unsigned __int64)
0x180054252  nop
0x180054253  lea     rdx, [rsp+130h+var_F8]
0x180054258  mov     rcx, r13
0x18005425b  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x180054260  nop
0x180054261  lea     rcx, [rsp+130h+var_F8]
0x180054266  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005426b  nop
0x18005426c  lea     rcx, [rbp+57h+var_70]
0x180054270  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180054275  nop
0x180054276  lea     rcx, [rbp+57h+var_D0]; this
0x18005427a  call    ??1_SignalInfo@StorageHealth@@QEAA@XZ; StorageHealth::_SignalInfo::~_SignalInfo(void)
0x18005427f  xor     eax, eax
0x180054281  mov     rcx, [rbp+57h+var_50]
0x180054285  xor     rcx, rsp; StackCookie
0x180054288  call    __security_check_cookie
0x18005428d  add     rsp, 0F8h
0x180054294  pop     r15
0x180054296  pop     r14
0x180054298  pop     r13
0x18005429a  pop     r12
0x18005429c  pop     rdi
0x18005429d  pop     rsi
0x18005429e  pop     rbx
0x18005429f  pop     rbp
0x1800542a0  retn
```
