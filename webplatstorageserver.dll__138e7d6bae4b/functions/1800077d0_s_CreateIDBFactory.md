# s_CreateIDBFactory

- ea: `0x1800077d0`
- end: `0x1800079d8`
- name: `s_CreateIDBFactory`
- size: `520`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: ``

## callees

- `0x180006e58`
- `0x180006e9c`
- `0x180006ed4`
- `0x1800077d0`
- `0x1800079e0`
- `0x180007bcc`
- `0x180007cbc`
- `0x18000e1c0`
- `0x18001f470`
- `0x1800273f0`
- `0x18002b480`
- `0x18002c9e0`
- `0x18002d290`
- `0x18002e8f4`
- `0x18003d8a0`
- `0x18006233c`
- `0x180080fb0`
- `0x1800814bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18000796e`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18000796e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007999`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007999`

## string_xrefs

- `0x18000781f`: `IDB_CreateIDBFactory`
- `0x1800077fe`: `RPC CreateIDBFactory`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall s_CreateIDBFactory(__int64 a1, __int64 a2, _QWORD *a3)
{
  struct HangDetectionWatchDog *v5; // rdx
  unsigned int v6; // esi
  __int64 v7; // rdi
  __int64 v8; // rcx
  __int64 v9; // rax
  void *v10; // rax
  volatile signed __int64 *v11; // rcx
  __int128 v13; // [rsp+20h] [rbp-218h] BYREF
  volatile signed __int64 *v14; // [rsp+30h] [rbp-208h] BYREF
  std::_Ref_count_base *v15[2]; // [rsp+38h] [rbp-200h] BYREF
  _BYTE v16[8]; // [rsp+48h] [rbp-1F0h] BYREF
  std::_Ref_count_base *v17; // [rsp+50h] [rbp-1E8h]
  _BYTE v18[24]; // [rsp+58h] [rbp-1E0h] BYREF
  _BYTE v19[80]; // [rsp+70h] [rbp-1C8h] BYREF
  _QWORD v20[43]; // [rsp+C0h] [rbp-178h] BYREF

  SetThreadName((WCHAR *)L"RPC CreateIDBFactory");
  HangDetectionWatchDog::Activity::Activity((HangDetectionWatchDog::Activity *)&v14, v5);
  *a3 = 0;
  v6 = 0;
  wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v20,
    "IDB_CreateIDBFactory");
  v20[0] = &IndexedDbTraceLogging::IDB_CreateIDBFactory::`vftable';
  IndexedDbTraceLogging::IDB_CreateIDBFactory::StartActivity(
    (IndexedDbTraceLogging::IDB_CreateIDBFactory *)v20,
    (const struct __MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0002 *)a2);
  *(_OWORD *)v15 = 0;
  if ( (*(_BYTE *)a2 & 0x40) != 0 )
  {
    ClientIdentity::ClientIdentity((ClientIdentity *)v19);
    v7 = *(_QWORD *)(a2 + 8);
    gsl::details::extent_type<-1>::extent_type<-1>(&v13, *(unsigned int *)(a2 + 4));
    *((_QWORD *)&v13 + 1) = v7;
    if ( (_QWORD)v13 == -1 || !v7 && (_QWORD)v13 )
    {
      _o_terminate(v8);
      v6 = v13;
      goto LABEL_12;
    }
    v13 = *(_OWORD *)gsl::span<unsigned char const,-1>::span<unsigned char const,-1>(v18, &v13);
    v9 = CreateQuotaSession(v16, v19, v19[65] != 0, &v13);
    std::shared_ptr<EseHelper::IDatabaseSession>::operator=(v15, v9);
    if ( v17 )
      std::_Ref_count_base::_Decref(v17);
    ClientIdentity::~ClientIdentity((ClientIdentity *)v19);
  }
  *(_QWORD *)&v13 = operator new(0x28u);
  v10 = (void *)IndexedDbFactorySession::IndexedDbFactorySession(v13, a2, v15);
  *a3 = v10;
  IndexedDbTraceLogging::IDB_CreateIDBFactory::Stop((IndexedDbTraceLogging::IDB_CreateIDBFactory *)v20, v10);
  if ( v15[1] )
    std::_Ref_count_base::_Decref(v15[1]);
  v20[0] = &IndexedDbTraceLogging::IDB_CreateIDBFactory::`vftable';
  wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v20);
  wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(v20);
LABEL_12:
  v11 = v14;
  if ( _InterlockedExchangeAdd64(v14, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
    SetThreadpoolTimer(*((PTP_TIMER *)v11 + 1), 0, 0, 0);
  SetThreadName((WCHAR *)&word_1800D6108);
  return v6;
}

```

## disassembly

```asm
0x1800077d0  mov     [rsp+arg_0], rbx
0x1800077d5  mov     [rsp+arg_18], rsi
0x1800077da  push    rdi
0x1800077db  push    r12
0x1800077dd  push    r14
0x1800077df  sub     rsp, 220h
0x1800077e6  mov     rax, cs:__security_cookie
0x1800077ed  xor     rax, rsp
0x1800077f0  mov     [rsp+238h+var_20], rax
0x1800077f8  mov     r14, r8
0x1800077fb  mov     rbx, rdx
0x1800077fe  lea     rcx, aRpcCreateidbfa; "RPC CreateIDBFactory"
0x180007805  call    SetThreadName
0x18000780a  nop
0x18000780b  lea     rcx, [rsp+238h+var_208]; this
0x180007810  call    ??0Activity@HangDetectionWatchDog@@QEAA@PEAV1@@Z; HangDetectionWatchDog::Activity::Activity(HangDetectionWatchDog *)
0x180007815  nop
0x180007816  mov     qword ptr [r14], 0
0x18000781d  xor     esi, esi
0x18000781f  lea     rdx, aIdbCreateidbfa; "IDB_CreateIDBFactory"
0x180007826  lea     rcx, [rsp+238h+var_178]
0x18000782e  call    ??0?$ActivityBase@VStorageServerProvider@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180007833  lea     r12, ??_7IDB_CreateIDBFactory@IndexedDbTraceLogging@@6B@; const IndexedDbTraceLogging::IDB_CreateIDBFactory::`vftable'
0x18000783a  mov     [rsp+238h+var_178], r12
0x180007842  mov     rdx, rbx; struct __MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0002 *
0x180007845  lea     rcx, [rsp+238h+var_178]; this
0x18000784d  call    ?StartActivity@IDB_CreateIDBFactory@IndexedDbTraceLogging@@QEAAXAEBU__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0002@@@Z; IndexedDbTraceLogging::IDB_CreateIDBFactory::StartActivity(__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0002 const &)
0x180007852  nop
0x180007853  xorps   xmm0, xmm0
0x180007856  movdqu  xmmword ptr [rsp+238h+var_200], xmm0
0x18000785c  test    byte ptr [rbx], 40h
0x18000785f  jz      loc_180007905
0x180007865  lea     rcx, [rsp+238h+var_1C8]; this
0x18000786a  call    ??0ClientIdentity@@QEAA@XZ; ClientIdentity::ClientIdentity(void)
0x18000786f  nop
0x180007870  mov     rdi, [rbx+8]
0x180007874  mov     edx, [rbx+4]
0x180007877  lea     rcx, [rsp+238h+var_218]
0x18000787c  call    ??0?$extent_type@$0?0@details@gsl@@QEAA@_K@Z; gsl::details::extent_type<-1>::extent_type<-1>(unsigned __int64)
0x180007881  mov     qword ptr [rsp+238h+var_218+8], rdi
0x180007886  mov     rax, qword ptr [rsp+238h+var_218]
0x18000788b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000788f  jz      loc_18000796E
0x180007895  test    rdi, rdi
0x180007898  jnz     short loc_1800078A3
0x18000789a  test    rax, rax
0x18000789d  jnz     loc_18000796E
0x1800078a3  lea     rdx, [rsp+238h+var_218]
0x1800078a8  lea     rcx, [rsp+238h+var_1E0]
0x1800078ad  call    ??$?0E$0?0$0?0$0A@@?$span@$$CBE$0?0@gsl@@QEAA@AEBV?$span@E$0?0@1@@Z; gsl::span<uchar const,-1>::span<uchar const,-1>(gsl::span<uchar,-1> const &)
0x1800078b2  xor     r8d, r8d
0x1800078b5  cmp     [rsp+238h+var_187], r8b
0x1800078bd  setnz   r8b
0x1800078c1  movups  xmm0, xmmword ptr [rax]
0x1800078c4  movdqu  [rsp+238h+var_218], xmm0
0x1800078ca  lea     r9, [rsp+238h+var_218]
0x1800078cf  lea     rdx, [rsp+238h+var_1C8]
0x1800078d4  lea     rcx, [rsp+238h+var_1F0]
0x1800078d9  call    ?CreateQuotaSession@@YA?AV?$shared_ptr@UIQuotaSession@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@W4WebPlatStorageHandlerType@@V?$span@$$CBE$0?0@gsl@@@Z; CreateQuotaSession(std::wstring const &,WebPlatStorageHandlerType,gsl::span<uchar const,-1>)
0x1800078de  mov     rdx, rax
0x1800078e1  lea     rcx, [rsp+238h+var_200]
0x1800078e6  call    ??4?$shared_ptr@UIDatabaseSession@EseHelper@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<EseHelper::IDatabaseSession>::operator=(std::shared_ptr<EseHelper::IDatabaseSession> &&)
0x1800078eb  mov     rcx, [rsp+238h+var_1E8]; this
0x1800078f0  test    rcx, rcx
0x1800078f3  jz      short loc_1800078FB
0x1800078f5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800078fa  nop
0x1800078fb  lea     rcx, [rsp+238h+var_1C8]; this
0x180007900  call    ??1ClientIdentity@@QEAA@XZ; ClientIdentity::~ClientIdentity(void)
0x180007905  mov     ecx, 28h ; '('; Size
0x18000790a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000790f  mov     qword ptr [rsp+238h+var_218], rax
0x180007914  lea     r8, [rsp+238h+var_200]
0x180007919  mov     rdx, rbx
0x18000791c  mov     rcx, rax
0x18000791f  call    ??0IndexedDbFactorySession@@QEAA@AEBU__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0002@@$$QEAV?$shared_ptr@UIQuotaSession@@@std@@@Z; IndexedDbFactorySession::IndexedDbFactorySession(__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0002 const &,std::shared_ptr<IQuotaSession> &&)
0x180007924  nop
0x180007925  mov     [r14], rax
0x180007928  mov     rdx, rax; void *
0x18000792b  lea     rcx, [rsp+238h+var_178]; this
0x180007933  call    ?Stop@IDB_CreateIDBFactory@IndexedDbTraceLogging@@QEAAXPEAX@Z; IndexedDbTraceLogging::IDB_CreateIDBFactory::Stop(void *)
0x180007938  nop
0x180007939  mov     rcx, [rsp+238h+var_200+8]; this
0x18000793e  test    rcx, rcx
0x180007941  jz      short loc_180007949
0x180007943  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180007948  nop
0x180007949  mov     [rsp+238h+var_178], r12
0x180007951  lea     rcx, [rsp+238h+var_178]
0x180007959  call    ?Destroy@?$ActivityBase@VStorageServerProvider@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18000795e  lea     rcx, [rsp+238h+var_178]
0x180007966  call    ??1?$ActivityBase@VStorageServerProvider@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000796b  nop
0x18000796c  jmp     short loc_180007979
0x18000796e  call    cs:__imp__o_terminate
0x180007974  nop
0x180007975  mov     esi, dword ptr [rsp+238h+var_218]
0x180007979  mov     rcx, [rsp+238h+var_208]
0x18000797e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007982  lock xadd [rcx], rax
0x180007987  cmp     rax, 1
0x18000798b  jnz     short loc_1800079A0
0x18000798d  xor     r9d, r9d; msWindowLength
0x180007990  xor     r8d, r8d; msPeriod
0x180007993  xor     edx, edx; pftDueTime
0x180007995  mov     rcx, [rcx+8]; pti
0x180007999  call    cs:__imp_SetThreadpoolTimer
0x18000799f  nop
0x1800079a0  lea     rcx, word_1800D6108; lpWideCharStr
0x1800079a7  call    SetThreadName
0x1800079ac  nop
0x1800079ad  mov     eax, esi
0x1800079af  mov     rcx, [rsp+238h+var_20]
0x1800079b7  xor     rcx, rsp; StackCookie
0x1800079ba  call    __security_check_cookie
0x1800079bf  lea     r11, [rsp+238h+var_18]
0x1800079c7  mov     rbx, [r11+20h]
0x1800079cb  mov     rsi, [r11+38h]
0x1800079cf  mov     rsp, r11
0x1800079d2  pop     r14
0x1800079d4  pop     r12
0x1800079d6  pop     rdi
0x1800079d7  retn
```
