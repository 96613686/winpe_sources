# CWwanManager::Initialize(tlx::shared_any<tlx::file_handle_traits>)

- ea: `0x180077224`
- end: `0x180077592`
- name: `?Initialize@CWwanManager@@QEAAKV?$shared_any@Ufile_handle_traits@tlx@@@tlx@@@Z`
- size: `878`
- prototype: `__int64 __fastcall(CWwanManager *this, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180014fe8`

## callees

- `0x180008abc`
- `0x1800094f4`
- `0x180012300`
- `0x180013004`
- `0x180014f1c`
- `0x18005c1f0`
- `0x18005c3f8`
- `0x180065b98`
- `0x180070f50`
- `0x180077224`
- `0x180078fd8`
- `0x18009439c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800774de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077520`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800774de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077520`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800774cf`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800774cf`

## string_xrefs

- `0x18007744b`: `succeeded to start listening WNF_SHEL_LOGON_COMPLETE`
- `0x18007745c`: `Failed to start listening WNF_SHEL_LOGON_COMPLETE (0x%x)`
- `0x18007752b`: `Failed to create NDIS handle (0x%x)`
- `0x1800774f0`: `CWwanResetRecoveryHelper::_CreateNdisHandle`
- `0x180077507`: `CWwanResetRecoveryHelper::_CreateNdisHandle`
- `0x1800774e7`: `CreateFile(NDIS) failed: %u`
- `0x1800774fe`: `NDIS handle created`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWwanManager::Initialize(CWwanManager *this, _QWORD *a2)
{
  __int64 v4; // rcx
  __int64 v5; // rax
  utl::_RefCountBase *v6; // rcx
  unsigned int v7; // ebp
  __int64 v8; // rax
  int v9; // eax
  __int64 v10; // rax
  int v11; // eax
  __int64 v12; // rax
  int v13; // eax
  __int64 v14; // rax
  int v15; // eax
  HANDLE FileW; // rbx
  DWORD LastError; // eax
  __int64 v18; // rbx
  utl::_RefCountBase *v19; // rcx
  utl::_RefCountBase *v21; // rcx
  _OWORD v22[6]; // [rsp+40h] [rbp-68h] BYREF
  wwan::WnfSubscribeHelper *v23; // [rsp+B0h] [rbp+8h] BYREF
  _QWORD *v24; // [rsp+B8h] [rbp+10h]

  v24 = a2;
  v4 = *a2;
  v5 = a2[1];
  if ( v5 )
    _InterlockedIncrement((volatile signed __int32 *)(v5 + 8));
  *((_QWORD *)this + 37) = v4;
  v6 = (utl::_RefCountBase *)*((_QWORD *)this + 38);
  *((_QWORD *)this + 38) = v5;
  if ( v6 )
    utl::_RefCountBase::_DecStrong(v6);
  *((_DWORD *)this + 55) = 1;
  *((_DWORD *)this + 54) = 0;
  *((_BYTE *)this + 224) = 0;
  v23 = this;
  v7 = ExecuteAndConvertAnyException__CWwanManager::Initialize_::_2_::_lambda_1___(&v23);
  *((_QWORD *)this + 30) = -1;
  v23 = (wwan::WnfSubscribeHelper *)operator new(0x50u);
  v8 = wwan::WnfSubscribeHelper::WnfSubscribeHelper(v23, &GUID_NULL, WNF_WCM_INTERFACE_CONNECTION_STATE);
  std::unique_ptr<wwan::WnfSubscribeHelper>::reset((char *)this + 336, v8);
  v9 = wwan::WnfSubscribeHelper::Start(*((wwan::WnfSubscribeHelper **)this + 42));
  if ( v9 < 0 )
    WwanLog::Error(
      "CWwanManager::Initialize",
      0,
      L"Failed to start listening WNF_WCM_INTERFACE_CONNECTION_STATE (0x%x)",
      (unsigned int)v9);
  else
    WwanLog::Info("CWwanManager::Initialize", 0, L"succeeded to start listening WNF_WCM_INTERFACE_CONNECTION_STATE");
  *((_DWORD *)this + 98) = 0;
  v23 = (wwan::WnfSubscribeHelper *)operator new(0x50u);
  v10 = wwan::WnfSubscribeHelper::WnfSubscribeHelper(v23, &GUID_NULL, WNF_PHN_CALL_STATUS);
  std::unique_ptr<wwan::WnfSubscribeHelper>::reset((char *)this + 384, v10);
  v11 = wwan::WnfSubscribeHelper::Start(*((wwan::WnfSubscribeHelper **)this + 48));
  if ( v11 < 0 )
    WwanLog::Error(
      "CWwanManager::Initialize",
      0,
      L"Failed to start listening WNF_PHN_CALL_STATUS (0x%x)",
      (unsigned int)v11);
  else
    WwanLog::Info("CWwanManager::Initialize", 0, L"succeeded to start listening WNF_PHN_CALL_STATUS");
  *((_DWORD *)this + 102) = 5;
  v23 = (wwan::WnfSubscribeHelper *)operator new(0x50u);
  v12 = wwan::WnfSubscribeHelper::WnfSubscribeHelper(v23, &GUID_NULL, WNF_CELL_POWER_STATE_MODEM0);
  std::unique_ptr<wwan::WnfSubscribeHelper>::reset((char *)this + 400, v12);
  v13 = wwan::WnfSubscribeHelper::Start(*((wwan::WnfSubscribeHelper **)this + 50));
  if ( v13 < 0 )
    WwanLog::Error(
      "CWwanManager::Initialize",
      0,
      L"Failed to start listening WNF_CELL_POWER_STATE_MODEM0 (0x%x)",
      (unsigned int)v13);
  else
    WwanLog::Info("CWwanManager::Initialize", 0, L"succeeded to start listening WNF_CELL_POWER_STATE_MODEM0");
  v23 = (wwan::WnfSubscribeHelper *)operator new(0x50u);
  v14 = wwan::WnfSubscribeHelper::WnfSubscribeHelper(v23, &GUID_NULL, WNF_SHEL_LOGON_COMPLETE);
  std::unique_ptr<wwan::WnfSubscribeHelper>::reset((char *)this + 488, v14);
  v15 = wwan::WnfSubscribeHelper::Start(*((wwan::WnfSubscribeHelper **)this + 61));
  if ( v15 < 0 )
    WwanLog::Error(
      "CWwanManager::Initialize",
      0,
      L"Failed to start listening WNF_SHEL_LOGON_COMPLETE (0x%x)",
      (unsigned int)v15);
  else
    WwanLog::Info("CWwanManager::Initialize", 0, L"succeeded to start listening WNF_SHEL_LOGON_COMPLETE");
  memset_0(v22, 0, 0x40u);
  *(_OWORD *)((char *)this + 412) = v22[0];
  *(_OWORD *)((char *)this + 428) = v22[1];
  *(_OWORD *)((char *)this + 444) = v22[2];
  *(_OWORD *)((char *)this + 460) = v22[3];
  CWwanResetRecoveryHelper::_ReadRnRPolicies((CWwanManager *)((char *)this + 412));
  FileW = CreateFileW(L"\\\\.\\NDIS", 0, 0, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    WwanLog::Error("CWwanResetRecoveryHelper::_CreateNdisHandle", 0, L"CreateFile(NDIS) failed: %u", LastError);
  }
  else
  {
    WwanLog::Info("CWwanResetRecoveryHelper::_CreateNdisHandle", 0, L"NDIS handle created");
  }
  *((_QWORD *)this + 60) = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    v18 = GetLastError();
    WwanLog::Error("CWwanManager::Initialize", 0, L"Failed to create NDIS handle (0x%x)", v18);
    v19 = (utl::_RefCountBase *)a2[1];
    if ( v19 )
      utl::_RefCountBase::_DecStrong(v19);
    return (unsigned int)v18;
  }
  else
  {
    *((_QWORD *)this + 63) = 0;
    CWwanManager::PowerSettingRegisterLpeNotification(this);
    *((_BYTE *)this + 236) = 1;
    v21 = (utl::_RefCountBase *)a2[1];
    if ( v21 )
      utl::_RefCountBase::_DecStrong(v21);
    return v7;
  }
}

```

## disassembly

```asm
0x180077224  mov     [rsp+arg_10], rbx
0x180077229  mov     [rsp+arg_8], rdx
0x18007722e  push    rbp
0x18007722f  push    rsi
0x180077230  push    rdi
0x180077231  push    r12
0x180077233  push    r14
0x180077235  sub     rsp, 80h
0x18007723c  mov     r14, rdx
0x18007723f  mov     rdi, rcx
0x180077242  mov     rcx, [rdx]
0x180077245  mov     rax, [rdx+8]
0x180077249  test    rax, rax
0x18007724c  jz      short loc_180077252
0x18007724e  lock inc dword ptr [rax+8]
0x180077252  mov     [rdi+128h], rcx
0x180077259  mov     rcx, [rdi+130h]; this
0x180077260  mov     [rdi+130h], rax
0x180077267  test    rcx, rcx
0x18007726a  jz      short loc_180077272
0x18007726c  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180077271  nop
0x180077272  mov     dword ptr [rdi+0DCh], 1
0x18007727c  mov     dword ptr [rdi+0D8h], 0
0x180077286  mov     byte ptr [rdi+0E0h], 0
0x18007728d  mov     [rsp+0A8h+arg_0], rdi
0x180077295  lea     rcx, [rsp+0A8h+arg_0]
0x18007729d  call    ExecuteAndConvertAnyException__CWwanManager__Initialize____2____lambda_1___
0x1800772a2  mov     ebp, eax
0x1800772a4  mov     qword ptr [rdi+0F0h], 0FFFFFFFFFFFFFFFFh
0x1800772af  lea     rbx, [rdi+150h]
0x1800772b6  mov     r12d, 50h ; 'P'
0x1800772bc  mov     ecx, r12d; Size
0x1800772bf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800772c4  mov     [rsp+0A8h+arg_0], rax
0x1800772cc  mov     r8, qword ptr cs:WNF_WCM_INTERFACE_CONNECTION_STATE.Data; struct _WNF_STATE_NAME
0x1800772d3  lea     rdx, GUID_NULL; struct _GUID *
0x1800772da  mov     rcx, rax; this
0x1800772dd  call    ??0WnfSubscribeHelper@wwan@@QEAA@AEBU_GUID@@U_WNF_STATE_NAME@@@Z; wwan::WnfSubscribeHelper::WnfSubscribeHelper(_GUID const &,_WNF_STATE_NAME)
0x1800772e2  mov     rdx, rax
0x1800772e5  mov     rcx, rbx
0x1800772e8  call    ?reset@?$unique_ptr@VWnfSubscribeHelper@wwan@@U?$default_delete@VWnfSubscribeHelper@wwan@@@std@@@std@@QEAAXPEAVWnfSubscribeHelper@wwan@@@Z; std::unique_ptr<wwan::WnfSubscribeHelper>::reset(wwan::WnfSubscribeHelper *)
0x1800772ed  mov     rcx, [rbx]; this
0x1800772f0  call    ?Start@WnfSubscribeHelper@wwan@@QEAAJXZ; wwan::WnfSubscribeHelper::Start(void)
0x1800772f5  xor     edx, edx; struct _GUID *
0x1800772f7  lea     rsi, aCwwanmanagerIn_1; "CWwanManager::Initialize"
0x1800772fe  mov     rcx, rsi; char *
0x180077301  test    eax, eax
0x180077303  js      short loc_180077313
0x180077305  lea     r8, aSucceededToSta_2; "succeeded to start listening WNF_WCM_IN"...
0x18007730c  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180077311  jmp     short loc_180077322
0x180077313  mov     r9d, eax
0x180077316  lea     r8, aFailedToStartL; "Failed to start listening WNF_WCM_INTER"...
0x18007731d  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x180077322  mov     dword ptr [rdi+188h], 0
0x18007732c  lea     rbx, [rdi+180h]
0x180077333  mov     rcx, r12; Size
0x180077336  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007733b  mov     [rsp+0A8h+arg_0], rax
0x180077343  mov     r8, qword ptr cs:WNF_PHN_CALL_STATUS.Data; struct _WNF_STATE_NAME
0x18007734a  lea     rdx, GUID_NULL; struct _GUID *
0x180077351  mov     rcx, rax; this
0x180077354  call    ??0WnfSubscribeHelper@wwan@@QEAA@AEBU_GUID@@U_WNF_STATE_NAME@@@Z; wwan::WnfSubscribeHelper::WnfSubscribeHelper(_GUID const &,_WNF_STATE_NAME)
0x180077359  mov     rdx, rax
0x18007735c  mov     rcx, rbx
0x18007735f  call    ?reset@?$unique_ptr@VWnfSubscribeHelper@wwan@@U?$default_delete@VWnfSubscribeHelper@wwan@@@std@@@std@@QEAAXPEAVWnfSubscribeHelper@wwan@@@Z; std::unique_ptr<wwan::WnfSubscribeHelper>::reset(wwan::WnfSubscribeHelper *)
0x180077364  mov     rcx, [rbx]; this
0x180077367  call    ?Start@WnfSubscribeHelper@wwan@@QEAAJXZ; wwan::WnfSubscribeHelper::Start(void)
0x18007736c  xor     edx, edx; struct _GUID *
0x18007736e  mov     rcx, rsi; char *
0x180077371  test    eax, eax
0x180077373  js      short loc_180077383
0x180077375  lea     r8, aSucceededToSta_0; "succeeded to start listening WNF_PHN_CA"...
0x18007737c  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180077381  jmp     short loc_180077392
0x180077383  mov     r9d, eax
0x180077386  lea     r8, aFailedToStartL_0; "Failed to start listening WNF_PHN_CALL_"...
0x18007738d  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x180077392  mov     dword ptr [rdi+198h], 5
0x18007739c  lea     rbx, [rdi+190h]
0x1800773a3  mov     rcx, r12; Size
0x1800773a6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800773ab  mov     [rsp+0A8h+arg_0], rax
0x1800773b3  mov     r8, qword ptr cs:WNF_CELL_POWER_STATE_MODEM0.Data; struct _WNF_STATE_NAME
0x1800773ba  lea     rdx, GUID_NULL; struct _GUID *
0x1800773c1  mov     rcx, rax; this
0x1800773c4  call    ??0WnfSubscribeHelper@wwan@@QEAA@AEBU_GUID@@U_WNF_STATE_NAME@@@Z; wwan::WnfSubscribeHelper::WnfSubscribeHelper(_GUID const &,_WNF_STATE_NAME)
0x1800773c9  mov     rdx, rax
0x1800773cc  mov     rcx, rbx
0x1800773cf  call    ?reset@?$unique_ptr@VWnfSubscribeHelper@wwan@@U?$default_delete@VWnfSubscribeHelper@wwan@@@std@@@std@@QEAAXPEAVWnfSubscribeHelper@wwan@@@Z; std::unique_ptr<wwan::WnfSubscribeHelper>::reset(wwan::WnfSubscribeHelper *)
0x1800773d4  mov     rcx, [rbx]; this
0x1800773d7  call    ?Start@WnfSubscribeHelper@wwan@@QEAAJXZ; wwan::WnfSubscribeHelper::Start(void)
0x1800773dc  xor     edx, edx; struct _GUID *
0x1800773de  mov     rcx, rsi; char *
0x1800773e1  test    eax, eax
0x1800773e3  js      short loc_1800773F3
0x1800773e5  lea     r8, aSucceededToSta; "succeeded to start listening WNF_CELL_P"...
0x1800773ec  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x1800773f1  jmp     short loc_180077402
0x1800773f3  mov     r9d, eax
0x1800773f6  lea     r8, aFailedToStartL_1; "Failed to start listening WNF_CELL_POWE"...
0x1800773fd  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x180077402  lea     rbx, [rdi+1E8h]
0x180077409  mov     rcx, r12; Size
0x18007740c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180077411  mov     [rsp+0A8h+arg_0], rax
0x180077419  mov     r8, qword ptr cs:WNF_SHEL_LOGON_COMPLETE.Data; struct _WNF_STATE_NAME
0x180077420  lea     rdx, GUID_NULL; struct _GUID *
0x180077427  mov     rcx, rax; this
0x18007742a  call    ??0WnfSubscribeHelper@wwan@@QEAA@AEBU_GUID@@U_WNF_STATE_NAME@@@Z; wwan::WnfSubscribeHelper::WnfSubscribeHelper(_GUID const &,_WNF_STATE_NAME)
0x18007742f  mov     rdx, rax
0x180077432  mov     rcx, rbx
0x180077435  call    ?reset@?$unique_ptr@VWnfSubscribeHelper@wwan@@U?$default_delete@VWnfSubscribeHelper@wwan@@@std@@@std@@QEAAXPEAVWnfSubscribeHelper@wwan@@@Z; std::unique_ptr<wwan::WnfSubscribeHelper>::reset(wwan::WnfSubscribeHelper *)
0x18007743a  mov     rcx, [rbx]; this
0x18007743d  call    ?Start@WnfSubscribeHelper@wwan@@QEAAJXZ; wwan::WnfSubscribeHelper::Start(void)
0x180077442  xor     edx, edx; struct _GUID *
0x180077444  mov     rcx, rsi; char *
0x180077447  test    eax, eax
0x180077449  js      short loc_180077459
0x18007744b  lea     r8, aSucceededToSta_1; "succeeded to start listening WNF_SHEL_L"...
0x180077452  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180077457  jmp     short loc_180077468
0x180077459  mov     r9d, eax
0x18007745c  lea     r8, aFailedToStartL_2; "Failed to start listening WNF_SHEL_LOGO"...
0x180077463  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x180077468  xor     edx, edx; Val
0x18007746a  lea     r8d, [rdx+40h]; Size
0x18007746e  lea     rcx, [rsp+0A8h+var_68]; void *
0x180077473  call    memset_0
0x180077478  lea     rcx, [rdi+19Ch]; struct WwanRnRPolicies *
0x18007747f  movaps  xmm0, [rsp+0A8h+var_68]
0x180077484  movups  xmmword ptr [rcx], xmm0
0x180077487  movaps  xmm1, [rsp+0A8h+var_58]
0x18007748c  movups  xmmword ptr [rcx+10h], xmm1
0x180077490  movaps  xmm0, [rsp+0A8h+var_48]
0x180077495  movups  xmmword ptr [rcx+20h], xmm0
0x180077499  movaps  xmm1, [rsp+0A8h+var_38]
0x18007749e  movups  xmmword ptr [rcx+30h], xmm1
0x1800774a2  call    ?_ReadRnRPolicies@CWwanResetRecoveryHelper@@SAXAEAUWwanRnRPolicies@@@Z; CWwanResetRecoveryHelper::_ReadRnRPolicies(WwanRnRPolicies &)
0x1800774a7  mov     [rsp+0A8h+hTemplateFile], 0; hTemplateFile
0x1800774b0  mov     [rsp+0A8h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800774b8  mov     [rsp+0A8h+dwCreationDisposition], 3; dwCreationDisposition
0x1800774c0  xor     r9d, r9d; lpSecurityAttributes
0x1800774c3  xor     r8d, r8d; dwShareMode
0x1800774c6  xor     edx, edx; dwDesiredAccess
0x1800774c8  lea     rcx, FileName; "\\\\.\\NDIS"
0x1800774cf  call    cs:__imp_CreateFileW
0x1800774d5  mov     rbx, rax
0x1800774d8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800774dc  jnz     short loc_1800774FE
0x1800774de  call    cs:__imp_GetLastError
0x1800774e4  mov     r9d, eax
0x1800774e7  lea     r8, aCreatefileNdis; "CreateFile(NDIS) failed: %u"
0x1800774ee  xor     edx, edx; struct _GUID *
0x1800774f0  lea     rcx, aCwwanresetreco_28; "CWwanResetRecoveryHelper::_CreateNdisHa"...
0x1800774f7  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800774fc  jmp     short loc_180077513
0x1800774fe  lea     r8, aNdisHandleCrea; "NDIS handle created"
0x180077505  xor     edx, edx; struct _GUID *
0x180077507  lea     rcx, aCwwanresetreco_28; "CWwanResetRecoveryHelper::_CreateNdisHa"...
0x18007750e  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180077513  mov     [rdi+1E0h], rbx
0x18007751a  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18007751e  jnz     short loc_180077550
0x180077520  call    cs:__imp_GetLastError
0x180077526  mov     ebx, eax
0x180077528  mov     r9d, eax
0x18007752b  lea     r8, aFailedToCreate_11; "Failed to create NDIS handle (0x%x)"
0x180077532  xor     edx, edx; struct _GUID *
0x180077534  mov     rcx, rsi; char *
0x180077537  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18007753c  nop
0x18007753d  mov     rcx, [r14+8]; this
0x180077541  test    rcx, rcx
0x180077544  jz      short loc_18007754C
0x180077546  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18007754b  nop
0x18007754c  mov     eax, ebx
0x18007754e  jmp     short loc_18007757B
0x180077550  mov     qword ptr [rdi+1F8h], 0
0x18007755b  mov     rcx, rdi; this
0x18007755e  call    ?PowerSettingRegisterLpeNotification@CWwanManager@@AEAAXXZ; CWwanManager::PowerSettingRegisterLpeNotification(void)
0x180077563  mov     byte ptr [rdi+0ECh], 1
0x18007756a  mov     rcx, [r14+8]; this
0x18007756e  test    rcx, rcx
0x180077571  jz      short loc_180077579
0x180077573  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180077578  nop
0x180077579  mov     eax, ebp
0x18007757b  mov     rbx, [rsp+0A8h+arg_10]
0x180077583  add     rsp, 80h
0x18007758a  pop     r14
0x18007758c  pop     r12
0x18007758e  pop     rdi
0x18007758f  pop     rsi
0x180077590  pop     rbp
0x180077591  retn
```
