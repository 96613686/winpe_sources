# CPinnedList::ApplyReorderTaskbarLayout(TaskbarLayoutType,int)

- ea: `0x180354890`
- end: `0x180354cab`
- name: `?ApplyReorderTaskbarLayout@CPinnedList@@UEAAJW4TaskbarLayoutType@@H@Z`
- size: `1051`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800134f8`
- `0x1800237c8`
- `0x180031c70`
- `0x1801dfbe0`
- `0x1802789e0`
- `0x180354890`
- `0x180354cb4`
- `0x180355794`
- `0x180355b04`
- `0x180356360`
- `0x180356edc`
- `0x18067a084`
- `0x18067ceb8`
- `0x1806825dc`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180354971`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803549f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180354a35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180354bca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180354c0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180354c5d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180354971`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803549f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180354a35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180354bca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180354c0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180354c5d`
- `SHELL32!__imp_ILFree` at `0x180354a1a`
- `SHELL32!__imp_ILFree` at `0x180354bf0`
- `SHELL32!__imp_ILFree` at `0x180354c42`
- `SHELL32!__imp_ILFree` at `0x180354a1a`
- `SHELL32!__imp_ILFree` at `0x180354bf0`
- `SHELL32!__imp_ILFree` at `0x180354c42`

## string_xrefs

- `0x1803548dd`: `TaskbarLayoutReorderActivity`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CPinnedList::ApplyReorderTaskbarLayout(__int64 a1, unsigned int a2, int a3)
{
  int PidlsFromTaskbarLayout; // eax
  unsigned int v7; // ebx
  __int64 (__fastcall *v8)(__int64, _QWORD *); // rbx
  int v9; // eax
  int v10; // edi
  struct _ITEMIDLIST *v11; // rcx
  unsigned int i; // ebx
  __int64 v14; // rax
  int v15; // ebx
  int PinSourceForPinnedItem; // eax
  __int64 v17; // rdx
  __int64 v18; // rbx
  __int64 v19; // rdi
  int v20; // eax
  wil::details::in1diag3 *v21; // rcx
  __int64 v22; // rdx
  struct _ITEMIDLIST *v23; // rcx
  unsigned int j; // ebx
  unsigned int k; // ebx
  int v26; // [rsp+20h] [rbp-E0h]
  int v27; // [rsp+30h] [rbp-D0h] BYREF
  struct _ITEMIDLIST **v28; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v29; // [rsp+40h] [rbp-C0h] BYREF
  char v30; // [rsp+48h] [rbp-B8h]
  LPVOID *v31; // [rsp+50h] [rbp-B0h]
  char v32; // [rsp+58h] [rbp-A8h]
  LPVOID pv[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v34; // [rsp+70h] [rbp-90h]
  struct _ITEMIDLIST *v35; // [rsp+80h] [rbp-80h] BYREF
  int v36; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v37[2]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v38[42]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]

  memset_0(v38, 0, sizeof(v38));
  wil::ActivityBase<TaskbarLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TaskbarLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v38);
  v38[0] = &TaskbarFlexibleLayoutTelemetry::TaskbarLayoutReorderActivity::`vftable';
  TaskbarFlexibleLayoutTelemetry::TaskbarLayoutReorderActivity::StartActivity(v38, a2);
  v36 = 0;
  pv[0] = 0;
  pv[1] = 0;
  v34 = 0u;
  PidlsFromTaskbarLayout = GetPidlsFromTaskbarLayout(a2, pv, &v36, 0);
  v7 = PidlsFromTaskbarLayout;
  if ( PidlsFromTaskbarLayout < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA4B,
      (unsigned int)"pcshell\\shell\\pinninglib\\lib\\PinnedList.cpp",
      (const char *)(unsigned int)PidlsFromTaskbarLayout,
      v26);
    if ( pv[0] )
    {
      CoTaskMemFree(pv[0]);
      pv[0] = 0;
    }
LABEL_13:
    pv[1] = 0;
    *((_QWORD *)&v34 + 1) = 0;
    TaskbarFlexibleLayoutTelemetry::TaskbarLayoutReorderActivity::~TaskbarLayoutReorderActivity((TaskbarFlexibleLayoutTelemetry::TaskbarLayoutReorderActivity *)v38);
    return v7;
  }
  v31 = pv;
  v32 = 1;
  if ( v36 )
  {
    v37[0] = 0;
    v35 = 0;
    v8 = *(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)a1 + 24LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v37);
    v9 = v8(a1, v37);
    v10 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA59,
        (unsigned int)"pcshell\\shell\\pinninglib\\lib\\PinnedList.cpp",
        (const char *)(unsigned int)v9,
        v26);
      v11 = v35;
      v35 = 0;
      if ( v11 )
        CoTaskMemFree(v11);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v37);
      for ( i = 0; (LPVOID)i < pv[1]; ++i )
        ILFree(*((LPITEMIDLIST *)pv[0] + i));
      if ( pv[0] )
      {
        CoTaskMemFree(pv[0]);
        pv[0] = 0;
      }
      v7 = v10;
      goto LABEL_13;
    }
    while ( 1 )
    {
      v14 = *(_QWORD *)v37[0];
      v28 = &v35;
      v29 = 0;
      v30 = 1;
      v15 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *))(v14 + 24))(v37[0], 1, &v29);
      wil::details::out_param_ptr_t<KnownGameList::GMRelatedProcess * *,wistd::unique_ptr<KnownGameList::GMRelatedProcess [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_ptr_t<KnownGameList::GMRelatedProcess * *,wistd::unique_ptr<KnownGameList::GMRelatedProcess [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v28);
      if ( v15 )
        break;
      v27 = 0;
      PinSourceForPinnedItem = GetPinSourceForPinnedItem(v35, (enum TaskbarPinningSource *)&v27);
      if ( PinSourceForPinnedItem < 0 )
      {
        v17 = 2655;
        goto LABEL_22;
      }
      if ( v27 && (v27 != 1 || !a2) )
      {
        v26 = 0;
        PinSourceForPinnedItem = CPinnedList::InternalModify(a1 - 16, v35, 0, 14);
        if ( PinSourceForPinnedItem < 0 )
        {
          v17 = 2660;
LABEL_22:
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)v17,
            (unsigned int)"pcshell\\shell\\pinninglib\\lib\\PinnedList.cpp",
            (const char *)(unsigned int)PinSourceForPinnedItem,
            v26);
        }
      }
    }
    if ( a3 )
    {
      v18 = (unsigned int)(LODWORD(pv[1]) - 1);
      if ( LODWORD(pv[1]) - 1 >= 0 )
      {
        do
        {
          v19 = *((_QWORD *)pv[0] + v18);
          if ( (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 72LL))(a1, v19) )
          {
            v20 = CPinnedList::InternalModify(a1 - 16, 0, v19, 14);
            v21 = retaddr;
            if ( v20 < 0 )
            {
              v22 = 2672;
LABEL_30:
              wil::details::in1diag3::_Log_Hr(
                v21,
                (void *)v22,
                (unsigned int)"pcshell\\shell\\pinninglib\\lib\\PinnedList.cpp",
                (const char *)(unsigned int)v20,
                0);
              goto LABEL_31;
            }
            v20 = CPinnedList::InternalModify(a1 - 16, v19, 1, 14);
            v21 = retaddr;
            if ( v20 < 0 )
            {
              v22 = 2674;
              goto LABEL_30;
            }
          }
LABEL_31:
          v18 = (unsigned int)(v18 - 1);
        }
        while ( (int)v18 >= 0 );
      }
    }
    wil::ActivityBase<TaskbarLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v38);
    v23 = v35;
    v35 = 0;
    if ( v23 )
      CoTaskMemFree(v23);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v37);
    for ( j = 0; (LPVOID)j < pv[1]; ++j )
      ILFree(*((LPITEMIDLIST *)pv[0] + j));
    if ( pv[0] )
    {
      CoTaskMemFree(pv[0]);
      pv[0] = 0;
    }
    pv[1] = 0;
    *((_QWORD *)&v34 + 1) = 0;
    TaskbarFlexibleLayoutTelemetry::TaskbarLayoutReorderActivity::~TaskbarLayoutReorderActivity((TaskbarFlexibleLayoutTelemetry::TaskbarLayoutReorderActivity *)v38);
    return 0;
  }
  else
  {
    for ( k = 0; (LPVOID)k < pv[1]; ++k )
      ILFree(*((LPITEMIDLIST *)pv[0] + k));
    if ( pv[0] )
    {
      CoTaskMemFree(pv[0]);
      pv[0] = 0;
    }
    pv[1] = 0;
    *((_QWORD *)&v34 + 1) = 0;
    TaskbarFlexibleLayoutTelemetry::TaskbarLayoutReorderActivity::~TaskbarLayoutReorderActivity((TaskbarFlexibleLayoutTelemetry::TaskbarLayoutReorderActivity *)v38);
    return 2147947423LL;
  }
}

```

## disassembly

```asm
0x180354890  mov     [rsp-8+arg_10], rbx
0x180354895  mov     [rsp-8+arg_18], rsi
0x18035489a  push    rbp
0x18035489b  push    rdi
0x18035489c  push    r12
0x18035489e  push    r14
0x1803548a0  push    r15
0x1803548a2  lea     rbp, [rsp-100h]
0x1803548aa  sub     rsp, 200h
0x1803548b1  mov     rax, cs:__security_cookie
0x1803548b8  xor     rax, rsp
0x1803548bb  mov     [rbp+120h+var_30], rax
0x1803548c2  mov     r15d, r8d
0x1803548c5  mov     r14d, edx
0x1803548c8  mov     rsi, rcx
0x1803548cb  xor     edx, edx; Val
0x1803548cd  mov     r8d, 150h; Size
0x1803548d3  lea     rcx, [rbp+120h+var_180]; void *
0x1803548d7  call    memset_0
0x1803548dc  nop
0x1803548dd  lea     rdx, aTaskbarlayoutr; "TaskbarLayoutReorderActivity"
0x1803548e4  lea     rcx, [rbp+120h+var_180]; struct wil::details::IFailureCallback *
0x1803548e8  call    ??0?$ActivityBase@VTaskbarLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<TaskbarLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TaskbarLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1803548ed  lea     rax, ??_7TaskbarLayoutReorderActivity@TaskbarFlexibleLayoutTelemetry@@6B@; const TaskbarFlexibleLayoutTelemetry::TaskbarLayoutReorderActivity::`vftable'
0x1803548f4  mov     [rbp+120h+var_180], rax
0x1803548f8  mov     edx, r14d
0x1803548fb  lea     rcx, [rbp+120h+var_180]
0x1803548ff  call    ?StartActivity@TaskbarLayoutReorderActivity@TaskbarFlexibleLayoutTelemetry@@QEAAXW4TaskbarLayoutType@@@Z; TaskbarFlexibleLayoutTelemetry::TaskbarLayoutReorderActivity::StartActivity(TaskbarLayoutType)
0x180354904  nop
0x180354905  xor     r12d, r12d
0x180354908  mov     [rbp+120h+var_198], r12d
0x18035490c  xorps   xmm0, xmm0
0x18035490f  movups  xmmword ptr [rsp+220h+pv], xmm0
0x180354914  movups  [rsp+220h+var_1B0], xmm0
0x180354919  mov     [rsp+220h+pv], r12
0x18035491e  mov     [rsp+220h+pv+8], r12
0x180354923  mov     qword ptr [rsp+220h+var_1B0], r12
0x180354928  mov     qword ptr [rsp+220h+var_1B0+8], r12
0x18035492d  xor     r9d, r9d
0x180354930  lea     r8, [rbp+120h+var_198]
0x180354934  lea     rdx, [rsp+220h+pv]
0x180354939  mov     ecx, r14d
0x18035493c  call    GetPidlsFromTaskbarLayout
0x180354941  mov     ebx, eax
0x180354943  test    eax, eax
0x180354945  jns     short loc_180354981
0x180354947  mov     rcx, [rbp+128h]; this
0x18035494e  mov     r9d, eax; char *
0x180354951  lea     r8, aPcshellShellPi_0; "pcshell\\shell\\pinninglib\\lib\\Pinned"...
0x180354958  mov     edx, 0A4Bh; void *
0x18035495d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180354962  nop
0x180354963  mov     rcx, [rsp+220h+pv]; pv
0x180354968  test    rcx, rcx
0x18035496b  jz      loc_180354A42
0x180354971  call    cs:__imp_CoTaskMemFree
0x180354977  mov     [rsp+220h+pv], r12
0x18035497c  jmp     loc_180354A42
0x180354981  lea     rax, [rsp+220h+pv]
0x180354986  mov     [rsp+220h+var_1D0], rax
0x18035498b  mov     [rsp+220h+var_1C8], 1
0x180354990  cmp     [rbp+120h+var_198], r12d
0x180354994  jz      loc_180354C2D
0x18035499a  mov     [rbp+120h+var_190], r12
0x18035499e  mov     [rbp+120h+var_1A0], r12
0x1803549a2  mov     rax, [rsi]
0x1803549a5  mov     rbx, [rax+18h]
0x1803549a9  lea     rcx, [rbp+120h+var_190]
0x1803549ad  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1803549b2  lea     rdx, [rbp+120h+var_190]
0x1803549b6  mov     rcx, rsi
0x1803549b9  mov     rax, rbx
0x1803549bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803549c1  mov     edi, eax
0x1803549c3  test    eax, eax
0x1803549c5  jns     loc_180354A5C
0x1803549cb  mov     rcx, [rbp+128h]; this
0x1803549d2  mov     r9d, eax; char *
0x1803549d5  lea     r8, aPcshellShellPi_0; "pcshell\\shell\\pinninglib\\lib\\Pinned"...
0x1803549dc  mov     edx, 0A59h; void *
0x1803549e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1803549e6  nop
0x1803549e7  mov     rcx, [rbp+120h+var_1A0]; pv
0x1803549eb  mov     [rbp+120h+var_1A0], r12
0x1803549ef  test    rcx, rcx
0x1803549f2  jz      short loc_1803549FB
0x1803549f4  call    cs:__imp_CoTaskMemFree
0x1803549fa  nop
0x1803549fb  lea     rcx, [rbp+120h+var_190]
0x1803549ff  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180354a04  nop
0x180354a05  mov     ebx, r12d
0x180354a08  cmp     [rsp+220h+pv+8], r12
0x180354a0d  jbe     short loc_180354A2B
0x180354a0f  mov     eax, ebx
0x180354a11  mov     rcx, [rsp+220h+pv]
0x180354a16  mov     rcx, [rcx+rax*8]; pidl
0x180354a1a  call    cs:__imp_ILFree
0x180354a20  inc     ebx
0x180354a22  mov     eax, ebx
0x180354a24  cmp     rax, [rsp+220h+pv+8]
0x180354a29  jb      short loc_180354A0F
0x180354a2b  mov     rcx, [rsp+220h+pv]; pv
0x180354a30  test    rcx, rcx
0x180354a33  jz      short loc_180354A40
0x180354a35  call    cs:__imp_CoTaskMemFree
0x180354a3b  mov     [rsp+220h+pv], r12
0x180354a40  mov     ebx, edi
0x180354a42  mov     [rsp+220h+pv+8], r12
0x180354a47  mov     qword ptr [rsp+220h+var_1B0+8], r12
0x180354a4c  lea     rcx, [rbp+120h+var_180]; this
0x180354a50  call    ??1TaskbarLayoutReorderActivity@TaskbarFlexibleLayoutTelemetry@@QEAA@XZ; TaskbarFlexibleLayoutTelemetry::TaskbarLayoutReorderActivity::~TaskbarLayoutReorderActivity(void)
0x180354a55  mov     eax, ebx
0x180354a57  jmp     loc_180354C80
0x180354a5c  mov     rcx, [rbp+120h+var_190]
0x180354a60  mov     rax, [rcx]
0x180354a63  lea     rdx, [rbp+120h+var_1A0]
0x180354a67  mov     [rsp+220h+var_1E8], rdx
0x180354a6c  mov     [rsp+220h+var_1E0], r12
0x180354a71  mov     [rsp+220h+var_1D8], 1
0x180354a76  xor     r9d, r9d
0x180354a79  lea     r8, [rsp+220h+var_1E0]
0x180354a7e  lea     edx, [r9+1]
0x180354a82  mov     rax, [rax+18h]
0x180354a86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180354a8b  mov     ebx, eax
0x180354a8d  lea     rcx, [rsp+220h+var_1E8]
0x180354a92  call    ??1?$out_param_ptr_t@PEAPEAUGMRelatedProcess@KnownGameList@@V?$unique_ptr@$$BY0A@UGMRelatedProcess@KnownGameList@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<KnownGameList::GMRelatedProcess * *,wistd::unique_ptr<KnownGameList::GMRelatedProcess [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_ptr_t<KnownGameList::GMRelatedProcess * *,wistd::unique_ptr<KnownGameList::GMRelatedProcess [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180354a97  test    ebx, ebx
0x180354a99  jnz     short loc_180354B0E
0x180354a9b  mov     [rsp+220h+var_1F0], r12d
0x180354aa0  lea     rdx, [rsp+220h+var_1F0]; enum TaskbarPinningSource *
0x180354aa5  mov     rcx, [rbp+120h+var_1A0]; struct _ITEMIDLIST *
0x180354aa9  call    ?GetPinSourceForPinnedItem@@YAJPEFBU_ITEMIDLIST@@PEAW4TaskbarPinningSource@@@Z; GetPinSourceForPinnedItem(_ITEMIDLIST const *,TaskbarPinningSource *)
0x180354aae  test    eax, eax
0x180354ab0  jns     short loc_180354AB9
0x180354ab2  mov     edx, 0A5Fh
0x180354ab7  jmp     short loc_180354AF3
0x180354ab9  mov     eax, [rsp+220h+var_1F0]
0x180354abd  test    eax, eax
0x180354abf  jz      short loc_180354A5C
0x180354ac1  cmp     eax, 1
0x180354ac4  jnz     short loc_180354ACB
0x180354ac6  test    r14d, r14d
0x180354ac9  jnz     short loc_180354A5C
0x180354acb  lea     rcx, [rsi-10h]
0x180354acf  mov     [rsp+220h+var_200], r12d; int
0x180354ad4  mov     r9d, 0Eh
0x180354ada  xor     r8d, r8d
0x180354add  mov     rdx, [rbp+120h+var_1A0]
0x180354ae1  call    ?InternalModify@CPinnedList@@IEAAJPEFBU_ITEMIDLIST@@0W4PINNEDLISTMODIFYCALLER@@W4PinnedListModifyFlags@@@Z; CPinnedList::InternalModify(_ITEMIDLIST const *,_ITEMIDLIST const *,PINNEDLISTMODIFYCALLER,PinnedListModifyFlags)
0x180354ae6  test    eax, eax
0x180354ae8  jns     loc_180354A5C
0x180354aee  mov     edx, 0A64h; void *
0x180354af3  lea     r8, aPcshellShellPi_0; "pcshell\\shell\\pinninglib\\lib\\Pinned"...
0x180354afa  mov     r9d, eax; char *
0x180354afd  mov     rcx, [rbp+128h]; this
0x180354b04  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180354b09  jmp     loc_180354A5C
0x180354b0e  test    r15d, r15d
0x180354b11  jz      loc_180354BB3
0x180354b17  mov     ebx, dword ptr [rsp+220h+pv+8]
0x180354b1b  sub     ebx, 1
0x180354b1e  js      loc_180354BB3
0x180354b24  mov     r15d, 0Eh
0x180354b2a  mov     rax, [rsp+220h+pv]
0x180354b2f  mov     rdi, [rax+rbx*8]
0x180354b33  mov     rax, [rsi]
0x180354b36  mov     rdx, rdi
0x180354b39  mov     rcx, rsi
0x180354b3c  mov     rax, [rax+48h]
0x180354b40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180354b45  test    eax, eax
0x180354b47  jz      short loc_180354BAA
0x180354b49  mov     [rsp+220h+var_200], r12d
0x180354b4e  mov     r9d, r15d
0x180354b51  mov     r8, rdi
0x180354b54  xor     edx, edx
0x180354b56  lea     rcx, [rsi-10h]
0x180354b5a  call    ?InternalModify@CPinnedList@@IEAAJPEFBU_ITEMIDLIST@@0W4PINNEDLISTMODIFYCALLER@@W4PinnedListModifyFlags@@@Z; CPinnedList::InternalModify(_ITEMIDLIST const *,_ITEMIDLIST const *,PINNEDLISTMODIFYCALLER,PinnedListModifyFlags)
0x180354b5f  mov     rcx, [rbp+128h]
0x180354b66  test    eax, eax
0x180354b68  jns     short loc_180354B71
0x180354b6a  mov     edx, 0A70h
0x180354b6f  jmp     short loc_180354B9B
0x180354b71  mov     [rsp+220h+var_200], r12d; int
0x180354b76  mov     r9d, r15d
0x180354b79  mov     r8d, 1
0x180354b7f  mov     rdx, rdi
0x180354b82  lea     rcx, [rsi-10h]
0x180354b86  call    ?InternalModify@CPinnedList@@IEAAJPEFBU_ITEMIDLIST@@0W4PINNEDLISTMODIFYCALLER@@W4PinnedListModifyFlags@@@Z; CPinnedList::InternalModify(_ITEMIDLIST const *,_ITEMIDLIST const *,PINNEDLISTMODIFYCALLER,PinnedListModifyFlags)
0x180354b8b  mov     rcx, [rbp+128h]; this
0x180354b92  test    eax, eax
0x180354b94  jns     short loc_180354BAA
0x180354b96  mov     edx, 0A72h; void *
0x180354b9b  mov     r9d, eax; char *
0x180354b9e  lea     r8, aPcshellShellPi_0; "pcshell\\shell\\pinninglib\\lib\\Pinned"...
0x180354ba5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180354baa  sub     ebx, 1
0x180354bad  jns     loc_180354B2A
0x180354bb3  lea     rcx, [rbp+120h+var_180]
0x180354bb7  call    ?Stop@?$ActivityBase@VTaskbarLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<TaskbarLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180354bbc  nop
0x180354bbd  mov     rcx, [rbp+120h+var_1A0]; pv
0x180354bc1  mov     [rbp+120h+var_1A0], r12
0x180354bc5  test    rcx, rcx
0x180354bc8  jz      short loc_180354BD1
0x180354bca  call    cs:__imp_CoTaskMemFree
0x180354bd0  nop
0x180354bd1  lea     rcx, [rbp+120h+var_190]
0x180354bd5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180354bda  nop
0x180354bdb  mov     ebx, r12d
0x180354bde  cmp     [rsp+220h+pv+8], r12
0x180354be3  jbe     short loc_180354C01
0x180354be5  mov     eax, ebx
0x180354be7  mov     rcx, [rsp+220h+pv]
0x180354bec  mov     rcx, [rcx+rax*8]; pidl
0x180354bf0  call    cs:__imp_ILFree
0x180354bf6  inc     ebx
0x180354bf8  mov     eax, ebx
0x180354bfa  cmp     rax, [rsp+220h+pv+8]
0x180354bff  jb      short loc_180354BE5
0x180354c01  mov     rcx, [rsp+220h+pv]; pv
0x180354c06  test    rcx, rcx
0x180354c09  jz      short loc_180354C16
0x180354c0b  call    cs:__imp_CoTaskMemFree
0x180354c11  mov     [rsp+220h+pv], r12
0x180354c16  mov     [rsp+220h+pv+8], r12
0x180354c1b  mov     qword ptr [rsp+220h+var_1B0+8], r12
0x180354c20  lea     rcx, [rbp+120h+var_180]; this
0x180354c24  call    ??1TaskbarLayoutReorderActivity@TaskbarFlexibleLayoutTelemetry@@QEAA@XZ; TaskbarFlexibleLayoutTelemetry::TaskbarLayoutReorderActivity::~TaskbarLayoutReorderActivity(void)
0x180354c29  xor     eax, eax
0x180354c2b  jmp     short loc_180354C80
0x180354c2d  mov     ebx, r12d
0x180354c30  cmp     [rsp+220h+pv+8], r12
0x180354c35  jbe     short loc_180354C53
0x180354c37  mov     eax, ebx
0x180354c39  mov     rcx, [rsp+220h+pv]
0x180354c3e  mov     rcx, [rcx+rax*8]; pidl
0x180354c42  call    cs:__imp_ILFree
0x180354c48  inc     ebx
0x180354c4a  mov     eax, ebx
0x180354c4c  cmp     rax, [rsp+220h+pv+8]
0x180354c51  jb      short loc_180354C37
0x180354c53  mov     rcx, [rsp+220h+pv]; pv
0x180354c58  test    rcx, rcx
0x180354c5b  jz      short loc_180354C68
0x180354c5d  call    cs:__imp_CoTaskMemFree
0x180354c63  mov     [rsp+220h+pv], r12
0x180354c68  mov     [rsp+220h+pv+8], r12
0x180354c6d  mov     qword ptr [rsp+220h+var_1B0+8], r12
0x180354c72  lea     rcx, [rbp+120h+var_180]; this
0x180354c76  call    ??1TaskbarLayoutReorderActivity@TaskbarFlexibleLayoutTelemetry@@QEAA@XZ; TaskbarFlexibleLayoutTelemetry::TaskbarLayoutReorderActivity::~TaskbarLayoutReorderActivity(void)
0x180354c7b  mov     eax, 8007139Fh
0x180354c80  mov     rcx, [rbp+120h+var_30]
0x180354c87  xor     rcx, rsp; StackCookie
0x180354c8a  call    __security_check_cookie
0x180354c8f  lea     r11, [rsp+220h+var_20]
0x180354c97  mov     rbx, [r11+40h]
0x180354c9b  mov     rsi, [r11+48h]
0x180354c9f  mov     rsp, r11
0x180354ca2  pop     r15
0x180354ca4  pop     r14
0x180354ca6  pop     r12
0x180354ca8  pop     rdi
0x180354ca9  pop     rbp
0x180354caa  retn
```
