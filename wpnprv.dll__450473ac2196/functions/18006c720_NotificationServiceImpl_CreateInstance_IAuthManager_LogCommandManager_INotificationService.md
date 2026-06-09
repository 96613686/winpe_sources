# NotificationServiceImpl::CreateInstance(IAuthManager *,LogCommandManager *,INotificationService * *)

- ea: `0x18006c720`
- end: `0x18006cc51`
- name: `?CreateInstance@NotificationServiceImpl@@SAJPEAVIAuthManager@@PEAVLogCommandManager@@PEAPEAVINotificationService@@@Z`
- size: `1329`
- prototype: `__int64 __fastcall(struct IAuthManager *, struct LogCommandManager *, struct INotificationService **)`
- caller_count: `1`
- callee_count: `20`
- tags: `service_task, broker_com_uri`

## callers

- `0x180066c7c`

## callees

- `0x180007464`
- `0x180009c5c`
- `0x18000ba54`
- `0x18000fddc`
- `0x18000fe0c`
- `0x18000fe2c`
- `0x18000fe54`
- `0x180020910`
- `0x180022cd8`
- `0x1800670fc`
- `0x18006a364`
- `0x18006a638`
- `0x18006a6f0`
- `0x18006c720`
- `0x18006cff8`
- `0x18006e52c`
- `0x18006e724`
- `0x1800742d4`
- `0x1800911e4`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006c8a7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006c8a7`

## string_xrefs

- `0x18006c820`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x18006c88a`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x18006c8c4`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x18006c93f`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x18006c9dc`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x18006ca51`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x18006cab8`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x18006cb1b`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x18006cb7e`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x18006cbe1`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall NotificationServiceImpl::CreateInstance(
        struct IAuthManager *a1,
        struct LogCommandManager *a2,
        struct INotificationService **a3)
{
  __int64 v6; // rax
  NotificationServiceImpl *v7; // rax
  NotificationServiceImpl *v8; // r14
  int v9; // eax
  HANDLE EventW; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  int WNPTransport; // eax
  PVOID *v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 (__fastcall ***v18)(_QWORD, GUID *, struct IWNPKeepAliveFeedbackProvider **); // rdi
  __int64 (__fastcall *v19)(_QWORD, GUID *, struct IWNPKeepAliveFeedbackProvider **); // rbx
  int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  int WNPKeepAliveDetector; // eax
  int Instance; // eax
  int inited; // eax
  int v27; // eax
  int v28; // eax
  unsigned int v29; // ebx
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // r9
  const char *v33; // r9
  __int64 result; // rax
  int v35[2]; // [rsp+20h] [rbp-48h] BYREF
  _BYTE v36[64]; // [rsp+28h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  int v38; // [rsp+80h] [rbp+18h] BYREF
  struct IWNPKeepAliveFeedbackProvider *v39; // [rsp+88h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 288, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids);
  }
  v38 = 0;
  v6 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(v35, &v38);
  wil::scope_exit__lambda_ab3ee63e91bc55d4963c85401982fcea___(v36, v6);
  *a3 = 0;
  v39 = 0;
  try
  {
    *(_QWORD *)v35 = operator new(0x168u);
    v7 = NotificationServiceImpl::NotificationServiceImpl(*(NotificationServiceImpl **)v35, a2);
    v8 = v7;
    *(_QWORD *)v35 = v7;
    if ( !v7 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          290,
          &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
          2147942414LL);
      }
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xBCB,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)0x8007000ELL,
        v35[0]);
    }
    v9 = NotificationServiceImpl::FinalConstruct(v7);
    v38 = v9;
    if ( v9 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        291,
        &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
        (unsigned int)v9);
      v9 = v38;
    }
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xBD0,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)(unsigned int)v9,
        v35[0]);
    EventW = CreateEventW(0, 1, 1, 0);
    *((_QWORD *)v8 + 17) = EventW;
    if ( !EventW )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xBD3,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)0x8007000ELL,
        v35[0]);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)v8 + 112, v11, v12, v13);
    WNPTransport = CWNPTransportImpl::CreateWNPTransport(0, a2, (char *)v8 + 112);
    v38 = WNPTransport;
    if ( WNPTransport < 0 )
    {
      v15 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          292,
          &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
          (unsigned int)WNPTransport);
        WNPTransport = v38;
      }
    }
    if ( WNPTransport < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xBDD,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)(unsigned int)WNPTransport,
        v35[0]);
    v18 = (__int64 (__fastcall ***)(_QWORD, GUID *, struct IWNPKeepAliveFeedbackProvider **))*((_QWORD *)v8 + 14);
    v19 = **v18;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39, v15, v16, v17);
    v20 = v19(v18, &GUID_7dbd6cab_a90c_4f2d_acb3_3b01de2edbee, &v39);
    v38 = v20;
    if ( v20 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        293,
        &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
        (unsigned int)v20);
      v20 = v38;
    }
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xBE1,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)(unsigned int)v20,
        v35[0]);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)v8 + 120, v21, v22, v23);
    WNPKeepAliveDetector = CreateWNPKeepAliveDetector(v39, (struct IWNPKeepAliveDetector **)v8 + 15);
    v38 = WNPKeepAliveDetector;
    if ( WNPKeepAliveDetector < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        294,
        &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
        (unsigned int)WNPKeepAliveDetector);
      WNPKeepAliveDetector = v38;
    }
    if ( WNPKeepAliveDetector < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xBE5,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)(unsigned int)WNPKeepAliveDetector,
        v35[0]);
    Instance = WNPMessageGenerator::CreateInstance((struct WNPMessageGenerator **)v8 + 16);
    v38 = Instance;
    if ( Instance < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        295,
        &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
        (unsigned int)Instance);
      Instance = v38;
    }
    if ( Instance < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xBE9,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)(unsigned int)Instance,
        v35[0]);
    inited = NotificationServiceImpl::InitKADetectorRegistrationTimer(v8);
    v38 = inited;
    if ( inited < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        296,
        &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
        (unsigned int)inited);
      inited = v38;
    }
    if ( inited < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xBEF,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)(unsigned int)inited,
        v35[0]);
    v27 = NotificationServiceImpl::ScheduleKADetectorRegistrationTimer(v8);
    v38 = v27;
    if ( v27 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        297,
        &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
        (unsigned int)v27);
      v27 = v38;
    }
    if ( v27 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xBF6,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)(unsigned int)v27,
        v35[0]);
    v28 = NotificationServiceImpl::InitDataDetectionInfo(v8);
    v38 = v28;
    if ( v28 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        298,
        &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
        (unsigned int)v28);
      v28 = v38;
    }
    if ( v28 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xBFA,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)(unsigned int)v28,
        v35[0]);
    *((_QWORD *)v8 + 13) = a1;
    *(_QWORD *)v35 = 0;
    *a3 = v8;
    v29 = v38;
    std::unique_ptr<NotificationServiceImpl>::~unique_ptr<NotificationServiceImpl>(v35);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39, v30, v31, v32);
    wil::details::lambda_call__lambda_3a918cb3a91e0cb4cf9217851a7ae01f___::_lambda_call__lambda_3a918cb3a91e0cb4cf9217851a7ae01f___(v36);
    result = v29;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xC01,
                           (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
                           v33);
  }
  return result;
}

```

## disassembly

```asm
0x18006c720  mov     [rsp+arg_0], rbx
0x18006c725  mov     [rsp+arg_8], rsi
0x18006c72a  push    rdi
0x18006c72b  push    r12
0x18006c72d  push    r13
0x18006c72f  push    r14
0x18006c731  push    r15
0x18006c733  sub     rsp, 40h
0x18006c737  mov     r12, r8
0x18006c73a  mov     rbx, rdx
0x18006c73d  mov     r13, rcx
0x18006c740  xor     edi, edi
0x18006c742  lea     rax, WPP_GLOBAL_Control
0x18006c749  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c750  mov     sil, 2
0x18006c753  cmp     rcx, rax
0x18006c756  jz      short loc_18006C77E
0x18006c758  test    [rcx+1Ch], sil
0x18006c75c  jz      short loc_18006C77E
0x18006c75e  cmp     byte ptr [rcx+19h], 6
0x18006c762  jb      short loc_18006C77E
0x18006c764  mov     edx, 120h
0x18006c769  lea     r15, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006c770  mov     r8, r15
0x18006c773  mov     rcx, [rcx+10h]
0x18006c777  call    WPP_SF_
0x18006c77c  jmp     short loc_18006C785
0x18006c77e  lea     r15, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006c785  mov     [rsp+68h+arg_10], edi
0x18006c78c  lea     rdx, [rsp+68h+arg_10]
0x18006c794  lea     rcx, [rsp+68h+var_48]
0x18006c799  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18006c79e  mov     rdx, rax
0x18006c7a1  lea     rcx, [rsp+68h+var_40]
0x18006c7a6  call    wil__scope_exit__lambda_ab3ee63e91bc55d4963c85401982fcea___
0x18006c7ab  nop
0x18006c7ac  mov     [r12], rdi
0x18006c7b0  mov     [rsp+68h+arg_18], rdi
0x18006c7b8  mov     ecx, 168h; Size
0x18006c7bd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006c7c2  mov     qword ptr [rsp+68h+var_48], rax
0x18006c7c7  mov     rdx, rbx; struct LogCommandManager *
0x18006c7ca  mov     rcx, rax; this
0x18006c7cd  call    ??0NotificationServiceImpl@@QEAA@PEAVLogCommandManager@@@Z; NotificationServiceImpl::NotificationServiceImpl(LogCommandManager *)
0x18006c7d2  mov     r14, rax
0x18006c7d5  mov     qword ptr [rsp+68h+var_48], rax; int
0x18006c7da  test    rax, rax
0x18006c7dd  jnz     short loc_18006C831
0x18006c7df  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c7e6  lea     rax, WPP_GLOBAL_Control
0x18006c7ed  cmp     rcx, rax
0x18006c7f0  jz      short loc_18006C815
0x18006c7f2  test    [rcx+1Ch], sil
0x18006c7f6  jz      short loc_18006C815
0x18006c7f8  cmp     [rcx+19h], sil
0x18006c7fc  jb      short loc_18006C815
0x18006c7fe  mov     edx, 122h
0x18006c803  mov     r9d, 8007000Eh
0x18006c809  mov     r8, r15
0x18006c80c  mov     rcx, [rcx+10h]
0x18006c810  call    WPP_SF_d
0x18006c815  mov     rcx, [rsp+68h]; this
0x18006c81a  mov     r9d, 8007000Eh; char *
0x18006c820  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006c827  mov     edx, 0BCBh; void *
0x18006c82c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006c831  mov     rcx, r14; this
0x18006c834  call    ?FinalConstruct@NotificationServiceImpl@@AEAAJXZ; NotificationServiceImpl::FinalConstruct(void)
0x18006c839  mov     [rsp+68h+arg_10], eax
0x18006c840  test    eax, eax
0x18006c842  jns     short loc_18006C87E
0x18006c844  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c84b  lea     rdx, WPP_GLOBAL_Control
0x18006c852  cmp     rcx, rdx
0x18006c855  jz      short loc_18006C87E
0x18006c857  test    byte ptr [rcx+1Ch], 4
0x18006c85b  jz      short loc_18006C87E
0x18006c85d  cmp     [rcx+19h], sil
0x18006c861  jb      short loc_18006C87E
0x18006c863  mov     edx, 123h
0x18006c868  mov     r9d, eax
0x18006c86b  mov     r8, r15
0x18006c86e  mov     rcx, [rcx+10h]
0x18006c872  call    WPP_SF_d
0x18006c877  mov     eax, [rsp+68h+arg_10]
0x18006c87e  mov     rcx, [rsp+68h]; this
0x18006c883  test    eax, eax
0x18006c885  jns     short loc_18006C89B
0x18006c887  mov     r9d, eax; char *
0x18006c88a  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006c891  mov     edx, 0BD0h; void *
0x18006c896  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006c89b  xor     r9d, r9d; lpName
0x18006c89e  lea     edx, [r9+1]; bManualReset
0x18006c8a2  mov     r8d, edx; bInitialState
0x18006c8a5  xor     ecx, ecx; lpEventAttributes
0x18006c8a7  call    cs:__imp_CreateEventW
0x18006c8ad  mov     [r14+88h], rax
0x18006c8b4  mov     rcx, [rsp+68h]; this
0x18006c8b9  test    rax, rax
0x18006c8bc  jnz     short loc_18006C8D5
0x18006c8be  mov     r9d, 8007000Eh; char *
0x18006c8c4  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006c8cb  mov     edx, 0BD3h; void *
0x18006c8d0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006c8d5  lea     rdi, [r14+70h]
0x18006c8d9  mov     rcx, rdi
0x18006c8dc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006c8e1  mov     r8, rdi
0x18006c8e4  mov     rdx, rbx
0x18006c8e7  xor     ecx, ecx
0x18006c8e9  call    ?CreateWNPTransport@CWNPTransportImpl@@SAJW4_WNP_TRANSPORT_FLAGS@@PEAVLogCommandManager@@PEAPEAUIWNPTransport@@@Z; CWNPTransportImpl::CreateWNPTransport(_WNP_TRANSPORT_FLAGS,LogCommandManager *,IWNPTransport * *)
0x18006c8ee  mov     [rsp+68h+arg_10], eax
0x18006c8f5  test    eax, eax
0x18006c8f7  jns     short loc_18006C933
0x18006c8f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c900  lea     rdx, WPP_GLOBAL_Control
0x18006c907  cmp     rcx, rdx
0x18006c90a  jz      short loc_18006C933
0x18006c90c  test    [rcx+1Ch], sil
0x18006c910  jz      short loc_18006C933
0x18006c912  cmp     [rcx+19h], sil
0x18006c916  jb      short loc_18006C933
0x18006c918  mov     edx, 124h
0x18006c91d  mov     r9d, eax
0x18006c920  mov     r8, r15
0x18006c923  mov     rcx, [rcx+10h]
0x18006c927  call    WPP_SF_d
0x18006c92c  mov     eax, [rsp+68h+arg_10]
0x18006c933  mov     rcx, [rsp+68h]; this
0x18006c938  test    eax, eax
0x18006c93a  jns     short loc_18006C951
0x18006c93c  mov     r9d, eax; char *
0x18006c93f  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006c946  mov     edx, 0BDDh; void *
0x18006c94b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006c951  mov     rdi, [rdi]
0x18006c954  mov     rax, [rdi]
0x18006c957  mov     rbx, [rax]
0x18006c95a  lea     rcx, [rsp+68h+arg_18]
0x18006c962  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006c967  lea     r8, [rsp+68h+arg_18]
0x18006c96f  lea     rdx, _GUID_7dbd6cab_a90c_4f2d_acb3_3b01de2edbee
0x18006c976  mov     rcx, rdi
0x18006c979  mov     rax, rbx
0x18006c97c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c981  nop
0x18006c982  mov     [rsp+68h+arg_10], eax
0x18006c989  test    eax, eax
0x18006c98b  jns     short loc_18006C9C9
0x18006c98d  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c994  lea     rdi, WPP_GLOBAL_Control
0x18006c99b  cmp     rcx, rdi
0x18006c99e  jz      short loc_18006C9D0
0x18006c9a0  test    [rcx+1Ch], sil
0x18006c9a4  jz      short loc_18006C9D0
0x18006c9a6  cmp     [rcx+19h], sil
0x18006c9aa  jb      short loc_18006C9D0
0x18006c9ac  mov     edx, 125h
0x18006c9b1  mov     r9d, eax
0x18006c9b4  mov     r8, r15
0x18006c9b7  mov     rcx, [rcx+10h]
0x18006c9bb  call    WPP_SF_d
0x18006c9c0  mov     eax, [rsp+68h+arg_10]
0x18006c9c7  jmp     short loc_18006C9D0
0x18006c9c9  lea     rdi, WPP_GLOBAL_Control
0x18006c9d0  mov     rcx, [rsp+68h]; this
0x18006c9d5  test    eax, eax
0x18006c9d7  jns     short loc_18006C9ED
0x18006c9d9  mov     r9d, eax; char *
0x18006c9dc  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006c9e3  mov     edx, 0BE1h; void *
0x18006c9e8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006c9ed  lea     rcx, [r14+78h]
0x18006c9f1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006c9f6  lea     rdx, [r14+78h]; struct IWNPKeepAliveDetector **
0x18006c9fa  mov     rcx, [rsp+68h+arg_18]; struct IWNPKeepAliveFeedbackProvider *
0x18006ca02  call    CreateWNPKeepAliveDetector
0x18006ca07  mov     [rsp+68h+arg_10], eax
0x18006ca0e  test    eax, eax
0x18006ca10  jns     short loc_18006CA45
0x18006ca12  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ca19  cmp     rcx, rdi
0x18006ca1c  jz      short loc_18006CA45
0x18006ca1e  test    [rcx+1Ch], sil
0x18006ca22  jz      short loc_18006CA45
0x18006ca24  cmp     [rcx+19h], sil
0x18006ca28  jb      short loc_18006CA45
0x18006ca2a  mov     edx, 126h
0x18006ca2f  mov     r9d, eax
0x18006ca32  mov     r8, r15
0x18006ca35  mov     rcx, [rcx+10h]
0x18006ca39  call    WPP_SF_d
0x18006ca3e  mov     eax, [rsp+68h+arg_10]
0x18006ca45  mov     rcx, [rsp+68h]; this
0x18006ca4a  test    eax, eax
0x18006ca4c  jns     short loc_18006CA62
0x18006ca4e  mov     r9d, eax; char *
0x18006ca51  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006ca58  mov     edx, 0BE5h; void *
0x18006ca5d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006ca62  lea     rcx, [r14+80h]; struct WNPMessageGenerator **
0x18006ca69  call    ?CreateInstance@WNPMessageGenerator@@SAJPEAPEAV1@@Z; WNPMessageGenerator::CreateInstance(WNPMessageGenerator * *)
0x18006ca6e  mov     [rsp+68h+arg_10], eax
0x18006ca75  test    eax, eax
0x18006ca77  jns     short loc_18006CAAC
0x18006ca79  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ca80  cmp     rcx, rdi
0x18006ca83  jz      short loc_18006CAAC
0x18006ca85  test    [rcx+1Ch], sil
0x18006ca89  jz      short loc_18006CAAC
0x18006ca8b  cmp     [rcx+19h], sil
0x18006ca8f  jb      short loc_18006CAAC
0x18006ca91  mov     edx, 127h
0x18006ca96  mov     r9d, eax
0x18006ca99  mov     r8, r15
0x18006ca9c  mov     rcx, [rcx+10h]
0x18006caa0  call    WPP_SF_d
0x18006caa5  mov     eax, [rsp+68h+arg_10]
0x18006caac  mov     rcx, [rsp+68h]; this
0x18006cab1  test    eax, eax
0x18006cab3  jns     short loc_18006CAC9
0x18006cab5  mov     r9d, eax; char *
0x18006cab8  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006cabf  mov     edx, 0BE9h; void *
0x18006cac4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006cac9  mov     rcx, r14; this
0x18006cacc  call    ?InitKADetectorRegistrationTimer@NotificationServiceImpl@@AEAAJXZ; NotificationServiceImpl::InitKADetectorRegistrationTimer(void)
0x18006cad1  mov     [rsp+68h+arg_10], eax
0x18006cad8  test    eax, eax
0x18006cada  jns     short loc_18006CB0F
0x18006cadc  mov     rcx, cs:WPP_GLOBAL_Control
0x18006cae3  cmp     rcx, rdi
0x18006cae6  jz      short loc_18006CB0F
0x18006cae8  test    [rcx+1Ch], sil
0x18006caec  jz      short loc_18006CB0F
0x18006caee  cmp     [rcx+19h], sil
0x18006caf2  jb      short loc_18006CB0F
0x18006caf4  mov     edx, 128h
0x18006caf9  mov     r9d, eax
0x18006cafc  mov     r8, r15
0x18006caff  mov     rcx, [rcx+10h]
0x18006cb03  call    WPP_SF_d
0x18006cb08  mov     eax, [rsp+68h+arg_10]
0x18006cb0f  mov     rcx, [rsp+68h]; this
0x18006cb14  test    eax, eax
0x18006cb16  jns     short loc_18006CB2C
0x18006cb18  mov     r9d, eax; char *
0x18006cb1b  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006cb22  mov     edx, 0BEFh; void *
0x18006cb27  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006cb2c  mov     rcx, r14; this
0x18006cb2f  call    ?ScheduleKADetectorRegistrationTimer@NotificationServiceImpl@@AEAAJXZ; NotificationServiceImpl::ScheduleKADetectorRegistrationTimer(void)
0x18006cb34  mov     [rsp+68h+arg_10], eax
0x18006cb3b  test    eax, eax
0x18006cb3d  jns     short loc_18006CB72
0x18006cb3f  mov     rcx, cs:WPP_GLOBAL_Control
0x18006cb46  cmp     rcx, rdi
0x18006cb49  jz      short loc_18006CB72
0x18006cb4b  test    [rcx+1Ch], sil
0x18006cb4f  jz      short loc_18006CB72
0x18006cb51  cmp     [rcx+19h], sil
0x18006cb55  jb      short loc_18006CB72
0x18006cb57  mov     edx, 129h
0x18006cb5c  mov     r9d, eax
0x18006cb5f  mov     r8, r15
0x18006cb62  mov     rcx, [rcx+10h]
0x18006cb66  call    WPP_SF_d
0x18006cb6b  mov     eax, [rsp+68h+arg_10]
0x18006cb72  mov     rcx, [rsp+68h]; this
0x18006cb77  test    eax, eax
0x18006cb79  jns     short loc_18006CB8F
0x18006cb7b  mov     r9d, eax; char *
0x18006cb7e  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006cb85  mov     edx, 0BF6h; void *
0x18006cb8a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006cb8f  mov     rcx, r14; this
0x18006cb92  call    ?InitDataDetectionInfo@NotificationServiceImpl@@AEAAJXZ; NotificationServiceImpl::InitDataDetectionInfo(void)
0x18006cb97  mov     [rsp+68h+arg_10], eax
0x18006cb9e  test    eax, eax
0x18006cba0  jns     short loc_18006CBD5
0x18006cba2  mov     rcx, cs:WPP_GLOBAL_Control
0x18006cba9  cmp     rcx, rdi
0x18006cbac  jz      short loc_18006CBD5
0x18006cbae  test    [rcx+1Ch], sil
0x18006cbb2  jz      short loc_18006CBD5
0x18006cbb4  cmp     [rcx+19h], sil
0x18006cbb8  jb      short loc_18006CBD5
0x18006cbba  mov     edx, 12Ah
0x18006cbbf  mov     r9d, eax
0x18006cbc2  mov     r8, r15
0x18006cbc5  mov     rcx, [rcx+10h]
0x18006cbc9  call    WPP_SF_d
0x18006cbce  mov     eax, [rsp+68h+arg_10]
0x18006cbd5  mov     rcx, [rsp+68h]; this
0x18006cbda  test    eax, eax
0x18006cbdc  jns     short loc_18006CBF2
0x18006cbde  mov     r9d, eax; char *
0x18006cbe1  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006cbe8  mov     edx, 0BFAh; void *
  ... truncated ...
```
