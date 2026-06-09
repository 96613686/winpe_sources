# COplockFileHandle::_Initialize(FileHandleType,void *,ushort const *,ulong,ulong,ulong,ulong,MCFFLAGS,IOplockProvider *)

- ea: `0x1800238b8`
- end: `0x180023d2f`
- name: `?_Initialize@COplockFileHandle@@AEAAJW4FileHandleType@@PEAXPEBGKKKKW4MCFFLAGS@@PEAUIOplockProvider@@@Z`
- size: `1143`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001c3b0`
- `0x180023774`

## callees

- `0x18000ddd4`
- `0x18001c61c`
- `0x180023730`
- `0x1800238b8`
- `0x18002493c`
- `0x180024960`
- `0x180024a38`
- `0x180035720`
- `0x1800472ec`
- `0x180047a2c`
- `0x18004a7f0`
- `0x180068d9c`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800238e2`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800238e2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180023a86`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180023a86`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180023b0f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180023b0f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180023cd1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180023cd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023cb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023cb3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023c7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023c7a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall COplockFileHandle::_Initialize(
        __int64 a1,
        unsigned int a2,
        GUID *a3,
        __int64 a4,
        unsigned int a5,
        unsigned int a6,
        int a7,
        unsigned int a8,
        int a9,
        __int64 (__fastcall ***a10)(_QWORD, GUID *, __int64))
{
  HANDLE MutexW; // rax
  int Instance; // ebx
  unsigned int v14; // r12d
  int v15; // ebp
  __int64 v16; // r13
  __int64 v17; // rcx
  __int64 v18; // rdi
  __int64 (__fastcall ***v19)(_QWORD, GUID *, __int64); // r15
  unsigned int v20; // ebx
  __int64 v21; // rcx
  __int64 (__fastcall *v22)(_QWORD, GUID *, __int64); // rdi
  void *v23; // rdi
  DWORD v24; // r15d
  __int64 v25; // rdi
  void *v26; // rax
  __int64 v27; // rax
  int v29; // eax
  int v30; // eax
  int LastError; // eax
  LPVOID pv; // [rsp+A0h] [rbp+8h] BYREF
  unsigned int v33; // [rsp+A8h] [rbp+10h]
  GUID *v34; // [rsp+B0h] [rbp+18h]

  v34 = a3;
  v33 = a2;
  MutexW = CreateMutexW(0, 0, 0);
  *(_QWORD *)(a1 + 200) = MutexW;
  Instance = ResultFromWin32Bool(MutexW != 0);
  if ( Instance < 0 )
    return (unsigned int)Instance;
  v14 = 0;
  v15 = a9;
  v16 = a5;
  if ( (a9 & 1) != 0 )
  {
    LOBYTE(pv) = 1;
    if ( (a9 & 0x10) != 0 )
    {
      v29 = `COplockFileHandle::s_FCMPolitenessEnabled'::`2'::s_FCMPolitenessEnabled;
      if ( !`COplockFileHandle::s_FCMPolitenessEnabled'::`2'::s_FCMPolitenessEnabled )
      {
        if ( (unsigned int)SHRegSubKeyExistsW() )
        {
          `COplockFileHandle::s_FCMPolitenessEnabled'::`2'::s_FCMPolitenessEnabled = 2;
          goto LABEL_4;
        }
        v29 = 1;
        `COplockFileHandle::s_FCMPolitenessEnabled'::`2'::s_FCMPolitenessEnabled = 1;
      }
      if ( v29 == 1 )
      {
        v17 = a1;
LABEL_5:
        v18 = (v17 + 24) & -(__int64)(v17 != 0);
        v19 = a10;
        if ( v34 == (GUID *)-1LL )
        {
          v20 = a8;
          if ( (a8 & 0x40000000) != 0 && v18 )
          {
            Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(a1 + 184);
            Instance = CGenericFileHandle::s_CreateInstance(
                         v33,
                         -1,
                         a4,
                         (unsigned int)v16,
                         a6,
                         a7,
                         v20 | 0x40000,
                         v15,
                         a1 + 184);
            v14 = Instance;
            if ( Instance >= 0 )
            {
              pv = 0;
              (*(void (__fastcall **)(_QWORD, LPVOID *))(**(_QWORD **)(a1 + 184) + 24LL))(*(_QWORD *)(a1 + 184), &pv);
              Instance = (*v19)[5](v19, (GUID *)pv, v18);
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 184) + 32LL))(*(_QWORD *)(a1 + 184));
              LOBYTE(pv) = 0;
            }
LABEL_10:
            if ( Instance )
            {
              if ( Instance == 1 )
              {
                v15 = 0;
                goto LABEL_13;
              }
            }
            else
            {
              v22 = **v19;
              Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(a1 + 176);
              Instance = v22(v19, &GUID_3119d9ab_dc96_4508_bc7d_14fbb3cb05e2, a1 + 176);
            }
            if ( Instance < 0 )
            {
              if ( (byte_1800DF041 & 2) != 0 )
                McTemplateU0xz_EventWriteTransfer(
                  v21,
                  ShellOplocks_NotGranted_Info,
                  a6 | (unsigned __int64)(v16 << 32),
                  a4);
              return (unsigned int)Instance;
            }
LABEL_13:
            if ( !(_BYTE)pv )
              goto LABEL_20;
            goto LABEL_14;
          }
          v30 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), __int64, _QWORD, __int64))(*a10)[4])(
                  a10,
                  a4,
                  (a8 >> 21) & 1,
                  v18);
        }
        else
        {
          v30 = (*a10)[5](a10, v34, v18);
        }
        Instance = v30;
        goto LABEL_10;
      }
    }
LABEL_4:
    v17 = 0;
    goto LABEL_5;
  }
LABEL_14:
  v23 = *(void **)(a1 + 200);
  v24 = WaitForSingleObjectEx(v23, 0xFFFFFFFF, 0);
  if ( *(_DWORD *)(a1 + 168) )
  {
    Instance = -2147024093;
  }
  else
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(a1 + 184);
    Instance = CGenericFileHandle::s_CreateInstance(v33, v34, a4, (unsigned int)v16, a6, a7, a8, v15, a1 + 184);
    v14 = Instance;
  }
  if ( v23 && (v24 & 0xFFFFFF7F) == 0 && !ReleaseMutex(v23) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    RaiseException(LastError, 1u, 0, 0);
    __debugbreak();
  }
  if ( Instance < 0 )
    return (unsigned int)Instance;
LABEL_20:
  *(_DWORD *)(a1 + 208) = v15;
  *(_DWORD *)(a1 + 212) = v16;
  *(_DWORD *)(a1 + 220) = v33;
  if ( a4 )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &pv,
      a4);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      a1 + 192,
      &pv);
    if ( pv )
      CoTaskMemFree(pv);
    if ( !*(_QWORD *)(a1 + 192) )
      return (unsigned int)-2147024882;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileHashMap<EventRegistrationToken,int,XWinRT::PodTypeHash,EventRegistrationTokenEqualPredicate,XWinRT::PodLifetimeTraits,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<int>,0>>::InternalRelease(a1 + 264);
  *(_QWORD *)(a1 + 264) = 0;
  v25 = 0;
  v26 = operator new(0xC0u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v26
    && (v27 = Windows::Foundation::Collections::Internal::HashMap<EventRegistrationToken,int,XWinRT::PodTypeHash,EventRegistrationTokenEqualPredicate,XWinRT::PodLifetimeTraits,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<int>,Windows::Foundation::Collections::Internal::HashMapOptions<EventRegistrationToken,int,XWinRT::PodLifetimeTraits,0,1,0>>::HashMap<EventRegistrationToken,int,XWinRT::PodTypeHash,EventRegistrationTokenEqualPredicate,XWinRT::PodLifetimeTraits,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<int>,Windows::Foundation::Collections::Internal::HashMapOptions<EventRegistrationToken,int,XWinRT::PodLifetimeTraits,0,1,0>>(v26),
        (v25 = v27) != 0) )
  {
    Instance = Windows::Foundation::Collections::Internal::HashMap<EventRegistrationToken,int,XWinRT::PodTypeHash,EventRegistrationTokenEqualPredicate,XWinRT::PodLifetimeTraits,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<int>,Windows::Foundation::Collections::Internal::HashMapOptions<EventRegistrationToken,int,XWinRT::PodLifetimeTraits,0,1,0>>::Initialize(v27);
    if ( Instance >= 0 )
    {
      *(_QWORD *)(a1 + 264) = v25;
      v25 = 0;
    }
  }
  else
  {
    Instance = -2147024882;
  }
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  if ( Instance < 0 )
    return (unsigned int)Instance;
  return v14;
}

```

## disassembly

```asm
0x1800238b8  mov     [rsp+arg_18], rbx
0x1800238bd  mov     [rsp+arg_10], r8
0x1800238c2  mov     [rsp+arg_8], edx
0x1800238c6  push    rbp
0x1800238c7  push    rsi
0x1800238c8  push    rdi
0x1800238c9  push    r12
0x1800238cb  push    r13
0x1800238cd  push    r14
0x1800238cf  push    r15
0x1800238d1  sub     rsp, 60h
0x1800238d5  mov     r14, r9
0x1800238d8  mov     rsi, rcx
0x1800238db  xor     r8d, r8d; lpName
0x1800238de  xor     edx, edx; bInitialOwner
0x1800238e0  xor     ecx, ecx; lpMutexAttributes
0x1800238e2  call    cs:__imp_CreateMutexW
0x1800238e8  mov     [rsi+0C8h], rax
0x1800238ef  xor     ecx, ecx
0x1800238f1  test    rax, rax
0x1800238f4  setnz   cl; int
0x1800238f7  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x1800238fc  mov     ebx, eax
0x1800238fe  test    eax, eax
0x180023900  js      loc_180023C33
0x180023906  xor     r12d, r12d
0x180023909  mov     ebp, [rsp+98h+arg_40]
0x180023910  mov     r13d, [rsp+98h+arg_20]
0x180023918  test    bpl, 1
0x18002391c  jz      loc_180023A76
0x180023922  mov     byte ptr [rsp+98h+pv], 1
0x18002392a  test    bpl, 10h
0x18002392e  jnz     loc_180023BD1
0x180023934  xor     ecx, ecx
0x180023936  lea     rax, [rcx+18h]
0x18002393a  neg     rcx
0x18002393d  sbb     rdi, rdi
0x180023940  and     rdi, rax
0x180023943  mov     r15, [rsp+98h+arg_48]
0x18002394b  mov     rcx, [rsp+98h+arg_10]
0x180023953  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180023957  jnz     loc_180023C9C
0x18002395d  mov     ebx, [rsp+98h+arg_38]
0x180023964  bt      ebx, 1Eh
0x180023968  jnb     loc_180023C3B
0x18002396e  test    rdi, rdi
0x180023971  jz      loc_180023C3B
0x180023977  lea     r12, [rsi+0B8h]
0x18002397e  mov     rcx, r12
0x180023981  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x180023986  mov     eax, ebx
0x180023988  bts     eax, 12h
0x18002398c  mov     [rsp+98h+var_58], r12
0x180023991  mov     [rsp+98h+var_60], ebp
0x180023995  mov     [rsp+98h+var_68], eax
0x180023999  mov     eax, [rsp+98h+arg_30]
0x1800239a0  mov     [rsp+98h+var_70], eax
0x1800239a4  mov     eax, [rsp+98h+arg_28]
0x1800239ab  mov     [rsp+98h+var_78], eax
0x1800239af  mov     r9d, r13d
0x1800239b2  mov     r8, r14
0x1800239b5  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800239b9  mov     ecx, [rsp+98h+arg_8]
0x1800239c0  call    ?s_CreateInstance@CGenericFileHandle@@SAJW4FileHandleType@@PEAXPEBGKKKKW4MCFFLAGS@@PEAPEAUIFileHandle@@@Z; CGenericFileHandle::s_CreateInstance(FileHandleType,void *,ushort const *,ulong,ulong,ulong,ulong,MCFFLAGS,IFileHandle * *)
0x1800239c5  mov     ebx, eax
0x1800239c7  mov     r12d, eax
0x1800239ca  test    eax, eax
0x1800239cc  js      short loc_180023A2C
0x1800239ce  mov     [rsp+98h+pv], 0
0x1800239da  mov     rcx, [rsi+0B8h]
0x1800239e1  mov     rax, [rcx]
0x1800239e4  lea     rdx, [rsp+98h+pv]
0x1800239ec  mov     rax, [rax+18h]
0x1800239f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800239f5  mov     rax, [r15]
0x1800239f8  mov     r8, rdi
0x1800239fb  mov     rdx, [rsp+98h+pv]
0x180023a03  mov     rcx, r15
0x180023a06  mov     rax, [rax+28h]
0x180023a0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023a0f  mov     ebx, eax
0x180023a11  mov     rcx, [rsi+0B8h]
0x180023a18  mov     rax, [rcx]
0x180023a1b  mov     rax, [rax+20h]
0x180023a1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023a24  mov     byte ptr [rsp+98h+pv], 0
0x180023a2c  test    ebx, ebx
0x180023a2e  jnz     loc_180023CD8
0x180023a34  mov     rax, [r15]
0x180023a37  mov     rdi, [rax]
0x180023a3a  lea     rbx, [rsi+0B0h]
0x180023a41  mov     rcx, rbx
0x180023a44  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x180023a49  mov     r8, rbx
0x180023a4c  lea     rdx, _GUID_3119d9ab_dc96_4508_bc7d_14fbb3cb05e2
0x180023a53  mov     rcx, r15
0x180023a56  mov     rax, rdi
0x180023a59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023a5e  mov     ebx, eax
0x180023a60  test    ebx, ebx
0x180023a62  js      loc_180023CE8
0x180023a68  cmp     byte ptr [rsp+98h+pv], 0
0x180023a70  jz      loc_180023B25
0x180023a76  mov     rdi, [rsi+0C8h]
0x180023a7d  xor     r8d, r8d; bAlertable
0x180023a80  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180023a83  mov     rcx, rdi; hHandle
0x180023a86  call    cs:__imp_WaitForSingleObjectEx
0x180023a8c  mov     r15d, eax
0x180023a8f  mov     [rsp+98h+var_48], eax
0x180023a93  mov     [rsp+98h+var_40], rdi
0x180023a98  mov     ecx, [rsi+0A8h]
0x180023a9e  test    ecx, ecx
0x180023aa0  jnz     loc_180023C92
0x180023aa6  lea     rbx, [rsi+0B8h]
0x180023aad  mov     rcx, rbx
0x180023ab0  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x180023ab5  mov     [rsp+98h+var_58], rbx
0x180023aba  mov     [rsp+98h+var_60], ebp
0x180023abe  mov     eax, [rsp+98h+arg_38]
0x180023ac5  mov     [rsp+98h+var_68], eax
0x180023ac9  mov     eax, [rsp+98h+arg_30]
0x180023ad0  mov     [rsp+98h+var_70], eax
0x180023ad4  mov     eax, [rsp+98h+arg_28]
0x180023adb  mov     [rsp+98h+var_78], eax
0x180023adf  mov     r9d, r13d
0x180023ae2  mov     r8, r14
0x180023ae5  mov     rdx, [rsp+98h+arg_10]
0x180023aed  mov     ecx, [rsp+98h+arg_8]
0x180023af4  call    ?s_CreateInstance@CGenericFileHandle@@SAJW4FileHandleType@@PEAXPEBGKKKKW4MCFFLAGS@@PEAPEAUIFileHandle@@@Z; CGenericFileHandle::s_CreateInstance(FileHandleType,void *,ushort const *,ulong,ulong,ulong,ulong,MCFFLAGS,IFileHandle * *)
0x180023af9  mov     ebx, eax
0x180023afb  mov     r12d, eax
0x180023afe  test    rdi, rdi
0x180023b01  jz      short loc_180023B1D
0x180023b03  test    r15d, 0FFFFFF7Fh
0x180023b0a  jnz     short loc_180023B1D
0x180023b0c  mov     rcx, rdi; hMutex
0x180023b0f  call    cs:__imp_ReleaseMutex
0x180023b15  test    eax, eax
0x180023b17  jz      loc_180023CB3
0x180023b1d  test    ebx, ebx
0x180023b1f  js      loc_180023C33
0x180023b25  mov     [rsi+0D0h], ebp
0x180023b2b  mov     [rsi+0D4h], r13d
0x180023b32  mov     eax, [rsp+98h+arg_8]
0x180023b39  mov     [rsi+0DCh], eax
0x180023b3f  test    r14, r14
0x180023b42  jnz     loc_180023BF0
0x180023b48  lea     rcx, [rsi+108h]
0x180023b4f  call    ?InternalRelease@?$ComPtr@V?$AgileHashMap@UEventRegistrationToken@@HUPodTypeHash@XWinRT@@UEventRegistrationTokenEqualPredicate@@UPodLifetimeTraits@3@U?$DefaultLifetimeTraits@H@Internal@Collections@Foundation@Windows@@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileHashMap<EventRegistrationToken,int,XWinRT::PodTypeHash,EventRegistrationTokenEqualPredicate,XWinRT::PodLifetimeTraits,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<int>,0>>::InternalRelease(void)
0x180023b54  mov     qword ptr [rsi+108h], 0
0x180023b5f  xor     edi, edi
0x180023b61  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180023b68  mov     ecx, 0C0h; unsigned __int64
0x180023b6d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180023b72  test    rax, rax
0x180023b75  jz      short loc_180023BCA
0x180023b77  mov     rcx, rax
0x180023b7a  call    ??0?$HashMap@UEventRegistrationToken@@HUPodTypeHash@XWinRT@@UEventRegistrationTokenEqualPredicate@@UPodLifetimeTraits@3@U?$DefaultLifetimeTraits@H@Internal@Collections@Foundation@Windows@@U?$HashMapOptions@UEventRegistrationToken@@HUPodLifetimeTraits@XWinRT@@$0A@$00$0A@@789Windows@@@Internal@Collections@Foundation@Windows@@QEAA@AEBUPodTypeHash@XWinRT@@AEBUEventRegistrationTokenEqualPredicate@@Upermission@01234@@Z; Windows::Foundation::Collections::Internal::HashMap<EventRegistrationToken,int,XWinRT::PodTypeHash,EventRegistrationTokenEqualPredicate,XWinRT::PodLifetimeTraits,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<int>,Windows::Foundation::Collections::Internal::HashMapOptions<EventRegistrationToken,int,XWinRT::PodLifetimeTraits,0,1,0>>::HashMap<EventRegistrationToken,int,XWinRT::PodTypeHash,EventRegistrationTokenEqualPredicate,XWinRT::PodLifetimeTraits,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<int>,Windows::Foundation::Collections::Internal::HashMapOptions<EventRegistrationToken,int,XWinRT::PodLifetimeTraits,0,1,0>>(XWinRT::PodTypeHash const &,EventRegistrationTokenEqualPredicate const &,Windows::Foundation::Collections::Internal::HashMap<EventRegistrationToken,int,XWinRT::PodTypeHash,EventRegistrationTokenEqualPredicate,XWinRT::PodLifetimeTraits,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<int>,Windows::Foundation::Collections::Internal::HashMapOptions<EventRegistrationToken,int,XWinRT::PodLifetimeTraits,0,1,0>>::permission)
0x180023b7f  mov     rdi, rax
0x180023b82  test    rax, rax
0x180023b85  jz      short loc_180023BCA
0x180023b87  mov     rcx, rax
0x180023b8a  call    ?Initialize@?$HashMap@UEventRegistrationToken@@HUPodTypeHash@XWinRT@@UEventRegistrationTokenEqualPredicate@@UPodLifetimeTraits@3@U?$DefaultLifetimeTraits@H@Internal@Collections@Foundation@Windows@@U?$HashMapOptions@UEventRegistrationToken@@HUPodLifetimeTraits@XWinRT@@$0A@$00$0A@@789Windows@@@Internal@Collections@Foundation@Windows@@AEAAJXZ; Windows::Foundation::Collections::Internal::HashMap<EventRegistrationToken,int,XWinRT::PodTypeHash,EventRegistrationTokenEqualPredicate,XWinRT::PodLifetimeTraits,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<int>,Windows::Foundation::Collections::Internal::HashMapOptions<EventRegistrationToken,int,XWinRT::PodLifetimeTraits,0,1,0>>::Initialize(void)
0x180023b8f  mov     ebx, eax
0x180023b91  test    eax, eax
0x180023b93  js      short loc_180023B9E
0x180023b95  mov     [rsi+108h], rdi
0x180023b9c  xor     edi, edi
0x180023b9e  test    rdi, rdi
0x180023ba1  jnz     loc_180023D1A
0x180023ba7  test    ebx, ebx
0x180023ba9  js      loc_180023C33
0x180023baf  mov     eax, r12d
0x180023bb2  mov     rbx, [rsp+98h+arg_18]
0x180023bba  add     rsp, 60h
0x180023bbe  pop     r15
0x180023bc0  pop     r14
0x180023bc2  pop     r13
0x180023bc4  pop     r12
0x180023bc6  pop     rdi
0x180023bc7  pop     rsi
0x180023bc8  pop     rbp
0x180023bc9  retn
0x180023bca  mov     ebx, 8007000Eh
0x180023bcf  jmp     short loc_180023B9E
0x180023bd1  mov     eax, cs:?s_FCMPolitenessEnabled@?1??0COplockFileHandle@@CA_NXZ@4W4TRIBIT@@A; TRIBIT `COplockFileHandle::s_FCMPolitenessEnabled(void)'::`2'::s_FCMPolitenessEnabled
0x180023bd7  test    eax, eax
0x180023bd9  jz      loc_180023C62
0x180023bdf  cmp     eax, 1
0x180023be2  jnz     loc_180023934
0x180023be8  mov     rcx, rsi
0x180023beb  jmp     loc_180023936
0x180023bf0  mov     rdx, r14
0x180023bf3  lea     rcx, [rsp+98h+pv]
0x180023bfb  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180023c00  lea     rbx, [rsi+0C0h]
0x180023c07  lea     rdx, [rsp+98h+pv]
0x180023c0f  mov     rcx, rbx
0x180023c12  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180023c17  mov     rcx, [rsp+98h+pv]; pv
0x180023c1f  test    rcx, rcx
0x180023c22  jnz     short loc_180023C7A
0x180023c24  cmp     qword ptr [rbx], 0
0x180023c28  jnz     loc_180023B48
0x180023c2e  mov     ebx, 8007000Eh
0x180023c33  mov     r12d, ebx
0x180023c36  jmp     loc_180023BAF
0x180023c3b  mov     rax, [r15]
0x180023c3e  mov     r8d, ebx
0x180023c41  shr     r8d, 15h
0x180023c45  and     r8d, 1
0x180023c49  mov     r9, rdi
0x180023c4c  mov     rdx, r14
0x180023c4f  mov     rcx, r15
0x180023c52  mov     rax, [rax+20h]
0x180023c56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023c5b  mov     ebx, eax
0x180023c5d  jmp     loc_180023A2C
0x180023c62  call    SHRegSubKeyExistsW
0x180023c67  test    eax, eax
0x180023c69  jz      short loc_180023C82
0x180023c6b  mov     cs:?s_FCMPolitenessEnabled@?1??0COplockFileHandle@@CA_NXZ@4W4TRIBIT@@A, 2; TRIBIT `COplockFileHandle::s_FCMPolitenessEnabled(void)'::`2'::s_FCMPolitenessEnabled
0x180023c75  jmp     loc_180023934
0x180023c7a  call    cs:__imp_CoTaskMemFree
0x180023c80  jmp     short loc_180023C24
0x180023c82  mov     eax, 1
0x180023c87  mov     cs:?s_FCMPolitenessEnabled@?1??0COplockFileHandle@@CA_NXZ@4W4TRIBIT@@A, eax; TRIBIT `COplockFileHandle::s_FCMPolitenessEnabled(void)'::`2'::s_FCMPolitenessEnabled
0x180023c8d  jmp     loc_180023BDF
0x180023c92  mov     ebx, 80070323h
0x180023c97  jmp     loc_180023AFE
0x180023c9c  mov     rax, [r15]
0x180023c9f  mov     r8, rdi
0x180023ca2  mov     rdx, rcx
0x180023ca5  mov     rcx, r15
0x180023ca8  mov     rax, [rax+28h]
0x180023cac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023cb1  jmp     short loc_180023C5B
0x180023cb3  call    cs:__imp_GetLastError
0x180023cb9  test    eax, eax
0x180023cbb  jle     short loc_180023CC5
0x180023cbd  movzx   eax, ax
0x180023cc0  or      eax, 80070000h
0x180023cc5  xor     r9d, r9d; lpArguments
0x180023cc8  xor     r8d, r8d; nNumberOfArguments
0x180023ccb  lea     edx, [r9+1]; dwExceptionFlags
0x180023ccf  mov     ecx, eax; dwExceptionCode
0x180023cd1  call    cs:__imp_RaiseException
0x180023cd7  int     3; Trap to Debugger
0x180023cd8  cmp     ebx, 1
0x180023cdb  jnz     loc_180023A60
0x180023ce1  xor     ebp, ebp
0x180023ce3  jmp     loc_180023A68
0x180023ce8  test    cs:byte_1800DF041, 2
0x180023cef  jz      loc_180023C33
0x180023cf5  mov     r8, r13
0x180023cf8  shl     r8, 20h
0x180023cfc  mov     eax, [rsp+98h+arg_28]
0x180023d03  or      r8, rax
0x180023d06  mov     r9, r14
0x180023d09  lea     rdx, ShellOplocks_NotGranted_Info
0x180023d10  call    McTemplateU0xz_EventWriteTransfer
0x180023d15  jmp     loc_180023C33
0x180023d1a  mov     rax, [rdi]
0x180023d1d  mov     rcx, rdi
0x180023d20  mov     rax, [rax+10h]
0x180023d24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d29  jmp     loc_180023BA7
```
