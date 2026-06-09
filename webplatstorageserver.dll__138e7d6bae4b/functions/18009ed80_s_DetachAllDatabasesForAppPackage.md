# s_DetachAllDatabasesForAppPackage

- ea: `0x18009ed80`
- end: `0x18009ef79`
- name: `s_DetachAllDatabasesForAppPackage`
- size: `505`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `loader_planting`

## callees

- `0x180006ed4`
- `0x1800169b0`
- `0x18001c800`
- `0x1800273f0`
- `0x18002d290`
- `0x18002ee6c`
- `0x18003d8a0`
- `0x18005f344`
- `0x18006191c`
- `0x180066010`
- `0x18006cf8c`
- `0x180080fb0`
- `0x18009d72c`
- `0x18009da04`
- `0x18009db70`
- `0x18009ed80`
- `0x1800a7888`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18009eee1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18009eee1`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18009eeec`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18009eeec`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18009ef3f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18009ef3f`

## string_xrefs

- `0x18009ee24`: `rundll32.exe`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall s_DetachAllDatabasesForAppPackage(__int64 a1, volatile signed __int64 *a2, char a3)
{
  char v5; // bl
  struct HangDetectionWatchDog *v6; // rdx
  _QWORD *ProcessName; // rax
  __int64 v8; // rdx
  char v9; // al
  int v10; // eax
  __int64 v11; // rcx
  unsigned int v12; // ebx
  __int64 Instance; // rax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, _BYTE *, __int64); // r14
  HANDLE CurrentProcess; // rax
  const char *v17; // r9
  volatile signed __int64 *v18; // rcx
  wil *v20; // rcx
  int v21; // [rsp+20h] [rbp-208h]
  volatile signed __int64 *v22[2]; // [rsp+30h] [rbp-1F8h] BYREF
  _BYTE v23[32]; // [rsp+40h] [rbp-1E8h] BYREF
  _BYTE v24[80]; // [rsp+60h] [rbp-1C8h] BYREF
  _BYTE v25[344]; // [rsp+B0h] [rbp-178h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+0h]

  v22[1] = a2;
  LOBYTE(v21) = a3;
  v5 = 0;
  SetThreadName((WCHAR *)L"RPC DetachAllDatabasesForAppPkg");
  HangDetectionWatchDog::Activity::Activity((HangDetectionWatchDog::Activity *)v22, v6);
  StorageManagementTraceLogging::SM_DetachAllDatabasesForAppPackage::SM_DetachAllDatabasesForAppPackage((StorageManagementTraceLogging::SM_DetachAllDatabasesForAppPackage *)v25);
  try
  {
    ClientIdentity::ClientIdentity((ClientIdentity *)v24);
    if ( !v24[64] )
      goto LABEL_7;
    ProcessName = (_QWORD *)ClientIdentity::s_GetProcessName((__int64)v23);
    v5 = 1;
    v8 = ProcessName[2];
    if ( ProcessName[3] > 7u )
      ProcessName = (_QWORD *)*ProcessName;
    if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(ProcessName, v8, L"rundll32.exe", 12) )
      v9 = 0;
    else
LABEL_7:
      v9 = 1;
    if ( v9 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x38,
        (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\clientmanager\\quotamanagerrpcapi.cxx",
        (const char *)0x80070005LL,
        v21);
    if ( (v5 & 1) != 0 )
      std::wstring::~wstring(v23);
    v10 = DetachAllIndexedDbDatabasesForAppPackage((const unsigned __int16 *)a2, a3 != 0);
    v12 = v10;
    if ( v10 )
    {
      if ( v10 < 0 )
        goto LABEL_16;
    }
    else
    {
      Instance = WebPlatStorageClientManager::GetInstance(v11);
      v14 = *(_QWORD *)Instance;
      v15 = *(__int64 (__fastcall **)(__int64, _BYTE *, __int64))(**(_QWORD **)Instance + 32LL);
      std::wstring::wstring(v23, a2);
      LOBYTE(v14) = v15(v14, v23, 10000);
      std::wstring::~wstring(v23);
      if ( !(_BYTE)v14 )
      {
        v12 = -2147023436;
LABEL_16:
        StorageManagementTraceLogging::SM_DetachAllDatabasesForAppPackage::LogFailedDelete(
          (StorageManagementTraceLogging::SM_DetachAllDatabasesForAppPackage *)v25,
          v12);
        CurrentProcess = GetCurrentProcess();
        TerminateProcess(CurrentProcess, 0);
      }
    }
    wil::ActivityBase<StorageServerProvider,0,70368744177920,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v25);
    ClientIdentity::~ClientIdentity((ClientIdentity *)v24);
    StorageManagementTraceLogging::SM_DetachAllDatabasesForAppPackage::~SM_DetachAllDatabasesForAppPackage((StorageManagementTraceLogging::SM_DetachAllDatabasesForAppPackage *)v25);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x50,
      (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\clientmanager\\quotamanagerrpcapi.cxx",
      v17);
    v12 = wil::ResultFromCaughtException(v20);
  }
  v18 = v22[0];
  if ( _InterlockedExchangeAdd64(v22[0], 0xFFFFFFFFFFFFFFFFuLL) == 1 )
    SetThreadpoolTimer(*((PTP_TIMER *)v18 + 1), 0, 0, 0);
  SetThreadName((WCHAR *)&word_1800D6108);
  return v12;
}

```

## disassembly

```asm
0x18009ed80  mov     [rsp+arg_0], rbx
0x18009ed85  push    rsi
0x18009ed86  push    rdi
0x18009ed87  push    r14
0x18009ed89  sub     rsp, 210h
0x18009ed90  mov     rax, cs:__security_cookie
0x18009ed97  xor     rax, rsp
0x18009ed9a  mov     [rsp+228h+var_20], rax
0x18009eda2  mov     dil, r8b
0x18009eda5  mov     rsi, rdx
0x18009eda8  mov     [rsp+228h+var_1F0], rdx
0x18009edad  mov     byte ptr [rsp+228h+var_208], r8b; int
0x18009edb2  xor     ebx, ebx
0x18009edb4  mov     [rsp+228h+var_200], ebx
0x18009edb8  lea     rcx, aRpcDetachallda; "RPC DetachAllDatabasesForAppPkg"
0x18009edbf  call    SetThreadName
0x18009edc4  nop
0x18009edc5  lea     rcx, [rsp+228h+var_1F8]; this
0x18009edca  call    ??0Activity@HangDetectionWatchDog@@QEAA@PEAV1@@Z; HangDetectionWatchDog::Activity::Activity(HangDetectionWatchDog *)
0x18009edcf  nop
0x18009edd0  lea     r9, [rsp+228h+var_208]
0x18009edd5  lea     r8, [rsp+228h+var_1F0]
0x18009edda  lea     rcx, [rsp+228h+var_178]; this
0x18009ede2  call    ??$?0AEAPEBGAEAE@SM_DetachAllDatabasesForAppPackage@StorageManagementTraceLogging@@AEAA@U?$integral_constant@D$0A@@wistd@@AEAPEBGAEAE@Z; StorageManagementTraceLogging::SM_DetachAllDatabasesForAppPackage::SM_DetachAllDatabasesForAppPackage(wistd::integral_constant<char,0>,ushort const * &,uchar &)
0x18009ede7  nop
0x18009ede8  lea     rcx, [rsp+228h+var_1C8]; this
0x18009eded  call    ??0ClientIdentity@@QEAA@XZ; ClientIdentity::ClientIdentity(void)
0x18009edf2  nop
0x18009edf3  cmp     [rsp+228h+var_188], bl
0x18009edfa  jz      short loc_18009EE3B
0x18009edfc  lea     rcx, [rsp+228h+var_1E8]
0x18009ee01  call    ?s_GetProcessName@ClientIdentity@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; ClientIdentity::s_GetProcessName(void)
0x18009ee06  nop
0x18009ee07  mov     ebx, 1
0x18009ee0c  mov     [rsp+228h+var_200], ebx
0x18009ee10  mov     rdx, [rax+10h]
0x18009ee14  cmp     qword ptr [rax+18h], 7
0x18009ee19  jbe     short loc_18009EE1E
0x18009ee1b  mov     rax, [rax]
0x18009ee1e  mov     r9d, 0Ch
0x18009ee24  lea     r8, aRundll32Exe; "rundll32.exe"
0x18009ee2b  mov     rcx, rax
0x18009ee2e  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18009ee33  test    al, al
0x18009ee35  jz      short loc_18009EE3B
0x18009ee37  xor     al, al
0x18009ee39  jmp     short loc_18009EE3D
0x18009ee3b  mov     al, 1
0x18009ee3d  mov     rcx, [rsp+228h]; this
0x18009ee45  test    al, al
0x18009ee47  jz      short loc_18009EE61
0x18009ee49  mov     r9d, 80070005h; char *
0x18009ee4f  lea     r8, aOnecoreuapInet_29; "onecoreuap\\inetcore\\webplatstorageser"...
0x18009ee56  mov     edx, 38h ; '8'; void *
0x18009ee5b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009ee61  test    bl, 1
0x18009ee64  jz      short loc_18009EE70
0x18009ee66  lea     rcx, [rsp+228h+var_1E8]; void *
0x18009ee6b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18009ee70  test    dil, dil
0x18009ee73  setnz   dl; bool
0x18009ee76  mov     rcx, rsi; unsigned __int16 *
0x18009ee79  call    ?DetachAllIndexedDbDatabasesForAppPackage@@YAJPEBG_N@Z; DetachAllIndexedDbDatabasesForAppPackage(ushort const *,bool)
0x18009ee7e  mov     ebx, eax
0x18009ee80  test    eax, eax
0x18009ee82  jnz     short loc_18009EED0
0x18009ee84  call    ?GetInstance@WebPlatStorageClientManager@@SAAEAV?$unique_ptr@VWebPlatStorageClientManager@@U?$default_delete@VWebPlatStorageClientManager@@@std@@@std@@XZ; WebPlatStorageClientManager::GetInstance(void)
0x18009ee89  mov     rdi, [rax]
0x18009ee8c  mov     rax, [rdi]
0x18009ee8f  mov     r14, [rax+20h]
0x18009ee93  mov     rdx, rsi
0x18009ee96  lea     rcx, [rsp+228h+var_1E8]
0x18009ee9b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009eea0  nop
0x18009eea1  mov     r8d, 2710h
0x18009eea7  lea     rdx, [rsp+228h+var_1E8]
0x18009eeac  mov     rcx, rdi
0x18009eeaf  mov     rax, r14
0x18009eeb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009eeb7  mov     dil, al
0x18009eeba  lea     rcx, [rsp+228h+var_1E8]; void *
0x18009eebf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18009eec4  test    dil, dil
0x18009eec7  jnz     short loc_18009EEF2
0x18009eec9  mov     ebx, 800705B4h
0x18009eece  jmp     short loc_18009EED2
0x18009eed0  jns     short loc_18009EEF2
0x18009eed2  mov     edx, ebx; int
0x18009eed4  lea     rcx, [rsp+228h+var_178]; this
0x18009eedc  call    ?LogFailedDelete@SM_DetachAllDatabasesForAppPackage@StorageManagementTraceLogging@@QEAAXJ@Z; StorageManagementTraceLogging::SM_DetachAllDatabasesForAppPackage::LogFailedDelete(long)
0x18009eee1  call    cs:__imp_GetCurrentProcess
0x18009eee7  mov     rcx, rax; hProcess
0x18009eeea  xor     edx, edx; uExitCode
0x18009eeec  call    cs:__imp_TerminateProcess
0x18009eef2  lea     rcx, [rsp+228h+var_178]
0x18009eefa  call    ?Stop@?$ActivityBase@VStorageServerProvider@@$0A@$0EAAAAAAAABAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<StorageServerProvider,0,70368744177920,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18009eeff  nop
0x18009ef00  lea     rcx, [rsp+228h+var_1C8]; this
0x18009ef05  call    ??1ClientIdentity@@QEAA@XZ; ClientIdentity::~ClientIdentity(void)
0x18009ef0a  nop
0x18009ef0b  lea     rcx, [rsp+228h+var_178]; this
0x18009ef13  call    ??1SM_DetachAllDatabasesForAppPackage@StorageManagementTraceLogging@@QEAA@XZ; StorageManagementTraceLogging::SM_DetachAllDatabasesForAppPackage::~SM_DetachAllDatabasesForAppPackage(void)
0x18009ef18  nop
0x18009ef19  jmp     short loc_18009EF1F
0x18009ef1b  mov     ebx, [rsp+228h+var_200]
0x18009ef1f  mov     rcx, [rsp+228h+var_1F8]
0x18009ef24  or      rax, 0FFFFFFFFFFFFFFFFh
0x18009ef28  lock xadd [rcx], rax
0x18009ef2d  cmp     rax, 1
0x18009ef31  jnz     short loc_18009EF46
0x18009ef33  xor     r9d, r9d; msWindowLength
0x18009ef36  xor     r8d, r8d; msPeriod
0x18009ef39  xor     edx, edx; pftDueTime
0x18009ef3b  mov     rcx, [rcx+8]; pti
0x18009ef3f  call    cs:__imp_SetThreadpoolTimer
0x18009ef45  nop
0x18009ef46  lea     rcx, word_1800D6108; lpWideCharStr
0x18009ef4d  call    SetThreadName
0x18009ef52  nop
0x18009ef53  mov     eax, ebx
0x18009ef55  mov     rcx, [rsp+228h+var_20]
0x18009ef5d  xor     rcx, rsp; StackCookie
0x18009ef60  call    __security_check_cookie
0x18009ef65  mov     rbx, [rsp+228h+arg_0]
0x18009ef6d  add     rsp, 210h
0x18009ef74  pop     r14
0x18009ef76  pop     rdi
0x18009ef77  pop     rsi
0x18009ef78  retn
```
