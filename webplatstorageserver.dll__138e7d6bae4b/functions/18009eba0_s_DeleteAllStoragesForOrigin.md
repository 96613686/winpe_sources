# s_DeleteAllStoragesForOrigin

- ea: `0x18009eba0`
- end: `0x18009ed72`
- name: `s_DeleteAllStoragesForOrigin`
- size: `466`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: ``

## callees

- `0x180006e9c`
- `0x18001c080`
- `0x18001c800`
- `0x18001f470`
- `0x1800273f0`
- `0x18002d290`
- `0x18002ee6c`
- `0x18005bb90`
- `0x18006ad24`
- `0x18006ad54`
- `0x180080fb0`
- `0x180084265`
- `0x18009d87c`
- `0x18009d9d8`
- `0x18009dfb4`
- `0x18009e1e8`
- `0x18009eba0`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18009ed6a`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18009ed6a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18009ed2b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18009ed2b`

## string_xrefs

- `0x18009ec16`: `SM_DeleteAllStoragesForOrigin`
- `0x18009ebcb`: `RPC DeleteAllStoragesForOrigin`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall s_DeleteAllStoragesForOrigin(__int64 a1, unsigned int a2, const void *a3)
{
  struct HangDetectionWatchDog *v5; // rdx
  unsigned int v6; // r14d
  size_t v7; // rdi
  __int64 v8; // rcx
  __int128 *v9; // rax
  __int64 v10; // rcx
  __int64 **Instance; // rax
  __int64 *v12; // r15
  __int64 v13; // r13
  char *v14; // rbx
  __int64 PackageName; // rax
  const char *v16; // r9
  volatile signed __int64 *v17; // rcx
  wil *v19; // rcx
  __int128 v20; // [rsp+20h] [rbp-1D8h] BYREF
  volatile signed __int64 *v21; // [rsp+30h] [rbp-1C8h] BYREF
  void *v22[2]; // [rsp+38h] [rbp-1C0h] BYREF
  __int64 v23; // [rsp+48h] [rbp-1B0h]
  _BYTE v24[32]; // [rsp+50h] [rbp-1A8h] BYREF
  _QWORD v25[43]; // [rsp+70h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+0h]

  SetThreadName((WCHAR *)L"RPC DeleteAllStoragesForOrigin");
  HangDetectionWatchDog::Activity::Activity((HangDetectionWatchDog::Activity *)&v21, v5);
  v6 = 0;
  v7 = a2;
  gsl::details::extent_type<-1>::extent_type<-1>(&v20, a2);
  *((_QWORD *)&v20 + 1) = a3;
  if ( (_QWORD)v20 == -1 || !a3 && (_QWORD)v20 )
  {
    _o_terminate(v8);
    __debugbreak();
    JUMPOUT(0x18009ED72LL);
  }
  wil::ActivityBase<StorageServerProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<StorageServerProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v25,
    "SM_DeleteAllStoragesForOrigin");
  v25[0] = &StorageManagementTraceLogging::SM_DeleteAllStoragesForOrigin::`vftable';
  v9 = (__int128 *)gsl::span<unsigned char const,-1>::span<unsigned char const,-1>(v22, &v20);
  try
  {
    v20 = *v9;
    StorageManagementTraceLogging::SM_DeleteAllStoragesForOrigin::StartActivity(v25, &v20);
    Instance = (__int64 **)WebPlatStorageClientManager::GetInstance(v10);
    v12 = *Instance;
    v13 = **Instance;
    *(_OWORD *)v22 = 0;
    v23 = 0;
    if ( a2 )
    {
      std::vector<unsigned char>::_Buy_nonzero(v22, a2);
      v14 = (char *)v22[0];
      memmove_0(v22[0], a3, v7);
      v22[1] = &v14[v7];
      *(_QWORD *)&v20 = 0;
      std::_Tidy_guard<std::vector<unsigned char>>::~_Tidy_guard<std::vector<unsigned char>>(&v20);
    }
    PackageName = ClientIdentity::s_GetPackageName((__int64)v24);
    (*(void (__fastcall **)(__int64 *, __int64, void **))(v13 + 24))(v12, PackageName, v22);
    std::wstring::~wstring(v24);
    std::vector<unsigned char>::_Tidy(v22);
    wil::ActivityBase<StorageServerProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v25);
    StorageManagementTraceLogging::SM_DeleteAllStoragesForOrigin::~SM_DeleteAllStoragesForOrigin((StorageManagementTraceLogging::SM_DeleteAllStoragesForOrigin *)v25);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x6B,
      (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\clientmanager\\quotamanagerrpcapi.cxx",
      v16);
    LODWORD(v20) = wil::ResultFromCaughtException(v19);
    v6 = v20;
  }
  v17 = v21;
  if ( _InterlockedExchangeAdd64(v21, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
    SetThreadpoolTimer(*((PTP_TIMER *)v17 + 1), 0, 0, 0);
  SetThreadName((WCHAR *)&word_1800D6108);
  return v6;
}

```

## disassembly

```asm
0x18009eba0  mov     [rsp+arg_0], rbx
0x18009eba5  push    rsi
0x18009eba6  push    rdi
0x18009eba7  push    r13
0x18009eba9  push    r14
0x18009ebab  push    r15
0x18009ebad  sub     rsp, 1D0h
0x18009ebb4  mov     rax, cs:__security_cookie
0x18009ebbb  xor     rax, rsp
0x18009ebbe  mov     [rsp+1F8h+var_30], rax
0x18009ebc6  mov     rsi, r8
0x18009ebc9  mov     ebx, edx
0x18009ebcb  lea     rcx, aRpcDeleteallst_0; "RPC DeleteAllStoragesForOrigin"
0x18009ebd2  call    SetThreadName
0x18009ebd7  nop
0x18009ebd8  lea     rcx, [rsp+1F8h+var_1C8]; this
0x18009ebdd  call    ??0Activity@HangDetectionWatchDog@@QEAA@PEAV1@@Z; HangDetectionWatchDog::Activity::Activity(HangDetectionWatchDog *)
0x18009ebe2  nop
0x18009ebe3  xor     r14d, r14d
0x18009ebe6  mov     edi, ebx
0x18009ebe8  mov     edx, ebx
0x18009ebea  lea     rcx, [rsp+1F8h+var_1D8]
0x18009ebef  call    ??0?$extent_type@$0?0@details@gsl@@QEAA@_K@Z; gsl::details::extent_type<-1>::extent_type<-1>(unsigned __int64)
0x18009ebf4  mov     qword ptr [rsp+1F8h+var_1D8+8], rsi
0x18009ebf9  mov     rax, qword ptr [rsp+1F8h+var_1D8]
0x18009ebfe  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18009ec02  jz      loc_18009ED6A
0x18009ec08  test    rsi, rsi
0x18009ec0b  jnz     short loc_18009EC16
0x18009ec0d  test    rax, rax
0x18009ec10  jnz     loc_18009ED6A
0x18009ec16  lea     rdx, aSmDeleteallsto; "SM_DeleteAllStoragesForOrigin"
0x18009ec1d  lea     rcx, [rsp+1F8h+var_188]
0x18009ec22  call    ??0?$ActivityBase@VStorageServerProvider@@$0A@$0BAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<StorageServerProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<StorageServerProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18009ec27  lea     rax, ??_7SM_DeleteAllStoragesForOrigin@StorageManagementTraceLogging@@6B@; const StorageManagementTraceLogging::SM_DeleteAllStoragesForOrigin::`vftable'
0x18009ec2e  mov     [rsp+1F8h+var_188], rax
0x18009ec33  lea     rdx, [rsp+1F8h+var_1D8]
0x18009ec38  lea     rcx, [rsp+1F8h+var_1C0]
0x18009ec3d  call    ??$?0E$0?0$0?0$0A@@?$span@$$CBE$0?0@gsl@@QEAA@AEBV?$span@E$0?0@1@@Z; gsl::span<uchar const,-1>::span<uchar const,-1>(gsl::span<uchar,-1> const &)
0x18009ec42  movups  xmm0, xmmword ptr [rax]
0x18009ec45  movdqu  [rsp+1F8h+var_1D8], xmm0
0x18009ec4b  lea     rdx, [rsp+1F8h+var_1D8]
0x18009ec50  lea     rcx, [rsp+1F8h+var_188]
0x18009ec55  call    ?StartActivity@SM_DeleteAllStoragesForOrigin@StorageManagementTraceLogging@@QEAAXV?$span@$$CBE$0?0@gsl@@@Z; StorageManagementTraceLogging::SM_DeleteAllStoragesForOrigin::StartActivity(gsl::span<uchar const,-1>)
0x18009ec5a  nop
0x18009ec5b  call    ?GetInstance@WebPlatStorageClientManager@@SAAEAV?$unique_ptr@VWebPlatStorageClientManager@@U?$default_delete@VWebPlatStorageClientManager@@@std@@@std@@XZ; WebPlatStorageClientManager::GetInstance(void)
0x18009ec60  mov     r15, [rax]
0x18009ec63  mov     r13, [r15]
0x18009ec66  xorps   xmm0, xmm0
0x18009ec69  movdqu  xmmword ptr [rsp+1F8h+var_1C0], xmm0
0x18009ec6f  mov     [rsp+1F8h+var_1B0], 0
0x18009ec78  test    ebx, ebx
0x18009ec7a  jz      short loc_18009ECB9
0x18009ec7c  mov     rdx, rdi
0x18009ec7f  lea     rcx, [rsp+1F8h+var_1C0]
0x18009ec84  call    ?_Buy_nonzero@?$vector@EV?$allocator@E@std@@@std@@AEAAX_K@Z; std::vector<uchar>::_Buy_nonzero(unsigned __int64)
0x18009ec89  mov     rbx, [rsp+1F8h+var_1C0]
0x18009ec8e  mov     r8, rdi; Size
0x18009ec91  mov     rdx, rsi; Src
0x18009ec94  mov     rcx, rbx; void *
0x18009ec97  call    memmove_0
0x18009ec9c  lea     rax, [rdi+rbx]
0x18009eca0  mov     [rsp+1F8h+var_1C0+8], rax
0x18009eca5  mov     qword ptr [rsp+1F8h+var_1D8], 0
0x18009ecae  lea     rcx, [rsp+1F8h+var_1D8]
0x18009ecb3  call    ??1?$_Tidy_guard@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<uchar>>::~_Tidy_guard<std::vector<uchar>>(void)
0x18009ecb8  nop
0x18009ecb9  lea     rcx, [rsp+1F8h+var_1A8]
0x18009ecbe  call    ?s_GetPackageName@ClientIdentity@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; ClientIdentity::s_GetPackageName(void)
0x18009ecc3  nop
0x18009ecc4  lea     r8, [rsp+1F8h+var_1C0]
0x18009ecc9  mov     rdx, rax
0x18009eccc  mov     rcx, r15
0x18009eccf  mov     rax, [r13+18h]
0x18009ecd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ecd8  nop
0x18009ecd9  lea     rcx, [rsp+1F8h+var_1A8]; void *
0x18009ecde  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18009ece3  nop
0x18009ece4  lea     rcx, [rsp+1F8h+var_1C0]
0x18009ece9  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18009ecee  lea     rcx, [rsp+1F8h+var_188]
0x18009ecf3  call    ?Stop@?$ActivityBase@VStorageServerProvider@@$0A@$0BAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<StorageServerProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18009ecf8  nop
0x18009ecf9  lea     rcx, [rsp+1F8h+var_188]; this
0x18009ecfe  call    ??1SM_DeleteAllStoragesForOrigin@StorageManagementTraceLogging@@QEAA@XZ; StorageManagementTraceLogging::SM_DeleteAllStoragesForOrigin::~SM_DeleteAllStoragesForOrigin(void)
0x18009ed03  nop
0x18009ed04  jmp     short loc_18009ED0B
0x18009ed06  mov     r14d, dword ptr [rsp+1F8h+var_1D8]
0x18009ed0b  mov     rcx, [rsp+1F8h+var_1C8]
0x18009ed10  or      rax, 0FFFFFFFFFFFFFFFFh
0x18009ed14  lock xadd [rcx], rax
0x18009ed19  cmp     rax, 1
0x18009ed1d  jnz     short loc_18009ED32
0x18009ed1f  xor     r9d, r9d; msWindowLength
0x18009ed22  xor     r8d, r8d; msPeriod
0x18009ed25  xor     edx, edx; pftDueTime
0x18009ed27  mov     rcx, [rcx+8]; pti
0x18009ed2b  call    cs:__imp_SetThreadpoolTimer
0x18009ed31  nop
0x18009ed32  lea     rcx, word_1800D6108; lpWideCharStr
0x18009ed39  call    SetThreadName
0x18009ed3e  nop
0x18009ed3f  mov     eax, r14d
0x18009ed42  mov     rcx, [rsp+1F8h+var_30]
0x18009ed4a  xor     rcx, rsp; StackCookie
0x18009ed4d  call    __security_check_cookie
0x18009ed52  mov     rbx, [rsp+1F8h+arg_0]
0x18009ed5a  add     rsp, 1D0h
0x18009ed61  pop     r15
0x18009ed63  pop     r14
0x18009ed65  pop     r13
0x18009ed67  pop     rdi
0x18009ed68  pop     rsi
0x18009ed69  retn
0x18009ed6a  call    cs:__imp__o_terminate
0x18009ed70  nop
0x18009ed71  int     3; Trap to Debugger
```
