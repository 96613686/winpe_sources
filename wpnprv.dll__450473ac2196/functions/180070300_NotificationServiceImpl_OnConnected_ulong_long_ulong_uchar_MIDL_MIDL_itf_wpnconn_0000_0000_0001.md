# NotificationServiceImpl::OnConnected(ulong,long,ulong,uchar *,__MIDL___MIDL_itf_wpnconn_0000_0000_0001)

- ea: `0x180070300`
- end: `0x1800709c2`
- name: `?OnConnected@NotificationServiceImpl@@UEAAJKJKPEAEW4__MIDL___MIDL_itf_wpnconn_0000_0000_0001@@@Z`
- size: `1730`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned int, unsigned int, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `18`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180007440`
- `0x180008294`
- `0x18000ba54`
- `0x18000fddc`
- `0x18000fe54`
- `0x180010044`
- `0x18001bde4`
- `0x18002f27c`
- `0x18006d890`
- `0x18006e2b0`
- `0x18006e8dc`
- `0x180070300`
- `0x180071e6c`
- `0x180074654`
- `0x180076e0c`
- `0x18007862c`
- `0x180085634`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180070503`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180070827`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180070503`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180070827`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800704f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180070813`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800704f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180070813`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180070906`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180070930`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180070959`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180070906`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180070930`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180070959`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800708f8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180070922`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007094b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800708f8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180070922`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007094b`

## string_xrefs

- `0x18007048a`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x18007057a`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x18007061f`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x1800706bb`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x180070751`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x1800708a9`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`

## pseudocode

```c
__int64 __fastcall NotificationServiceImpl::OnConnected(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        unsigned __int8 *a5,
        unsigned int a6)
{
  unsigned int v9; // ebx
  int v10; // r13d
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // rcx
  __int64 v15; // r8
  unsigned int v16; // edi
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  PVOID *v21; // rcx
  __int64 v22; // rdx
  int v23; // eax
  int v24; // eax
  struct WNPMessageParser *v25; // rsi
  __int64 v26; // rdx
  int v27; // eax
  int v28; // eax
  int v29; // edi
  int v30; // eax
  NotificationServiceImpl *v31; // rcx
  int v32; // eax
  void *v33; // rdi
  HANDLE ProcessHeap; // rax
  void *v35; // rdi
  HANDLE v36; // rax
  void *v37; // rdi
  HANDLE v38; // rax
  int v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID lpMem; // [rsp+58h] [rbp-A8h] BYREF
  struct IConnectionProviderEvents *v43; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v44; // [rsp+68h] [rbp-98h]
  int v45; // [rsp+6Ch] [rbp-94h] BYREF
  int v46; // [rsp+70h] [rbp-90h] BYREF
  LPVOID v47; // [rsp+78h] [rbp-88h]
  LPVOID v48; // [rsp+80h] [rbp-80h]
  struct WNPMessageParser *v49; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int8 *v50; // [rsp+90h] [rbp-70h]
  int v51[6]; // [rsp+98h] [rbp-68h] BYREF
  int v52[132]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+218h]

  v50 = a5;
  v44 = a4;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    v40 = a3;
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids);
  }
  v43 = 0;
  v49 = 0;
  v9 = 0;
  lpMem = 0;
  v10 = 1;
  v41 = 0;
  v46 = 0;
  v45 = 0;
  memset_0(v52, 0, 0x202u);
  v47 = 0;
  v48 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43, v11, v12, v13);
  NotificationServiceImpl::GetConnectionProviderEvents((NotificationServiceImpl *)(a1 - 8), &v43);
  if ( (byte_1800AFD82 & 0x20) != 0 )
    McTemplateU0q_EventWriteTransfer(v14, WPNPRV_NOTSVC_ONCONNECTED, a3);
  if ( (byte_1800AFD84 & 0x20) != 0 )
    McGenEventWrite_EventWriteTransfer(&WPNCORE_PROVIDER_GUID_Context, WPNPRV_PERFTRACK_ON_CONNECTED, v15, 1, v51);
  if ( a3 == -2013002865 )
  {
    v16 = 2;
    goto LABEL_24;
  }
  if ( a3 != -2013002776 )
  {
    v16 = 1;
    if ( (a3 & 0x80000000) != 0 )
      v16 = 3;
LABEL_24:
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
    *(_DWORD *)(a1 + 208) = v16;
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
    *(_DWORD *)(a1 + 248) = a2;
    if ( v10 )
    {
      v23 = (*(__int64 (__fastcall **)(struct IConnectionProviderEvents *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v43 + 24LL))(
              v43,
              v16,
              a6,
              a3);
      v9 = v23;
      if ( v23 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            25,
            &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
            (unsigned int)v23);
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x146,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
          (const char *)v9,
          v40);
        v21 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        {
          v22 = 26;
          goto LABEL_20;
        }
        goto LABEL_81;
      }
      WpnSqmConnectionStatusUpdate(v16, a3);
    }
    if ( v16 != 1 )
      goto LABEL_80;
    v24 = WNPMessageParser::CreateInstance(v50, v44, &v49);
    v25 = v49;
    v9 = v24;
    if ( v24 >= 0 )
    {
      v27 = WNPMessageParser::ParseBND(v49, (char **)&lpMem);
      v9 = v27;
      if ( v27 >= 0 )
      {
        if ( !lpMem
          || (v28 = NotificationServiceImpl::SendChallengeResponse(
                      (WNPMessageGenerator **)(a1 - 8),
                      (const char *)lpMem),
              v9 = v28,
              v28 >= 0) )
        {
          v29 = (*(__int64 (__fastcall **)(_QWORD, int *, int *, int *))(**(_QWORD **)(a1 + 104) + 112LL))(
                  *(_QWORD *)(a1 + 104),
                  &v41,
                  &v46,
                  &v45);
          if ( v29 < 0
            && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              33,
              &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
              (unsigned int)v29);
          }
          v9 = 0;
          if ( v29 >= 0 )
            v9 = v29;
          EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
          *(_DWORD *)(a1 + 296) = v41;
          LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
          if ( *(_DWORD *)(a1 + 296) == 1026 )
          {
            v30 = NotificationServiceImpl::InitializeFastKADetectionOnWifi((void **)(a1 - 8));
            v9 = v30;
            if ( v30 < 0 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  35,
                  &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
                  (unsigned int)v30);
              }
              v9 = 0;
            }
          }
          NotificationServiceImpl::ProcessServerEndpointChange((NotificationServiceImpl *)(a1 - 8));
          v32 = NotificationServiceImpl::HandleDeviceVersionVariation(v31, *(char **)(a1 + 200));
          if ( v32 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x177,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
              (const char *)(unsigned int)v32,
              (int)v52);
          goto LABEL_77;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            31,
            &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
            (unsigned int)v28);
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x15D,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
          (const char *)v9,
          v40);
        v21 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
          goto LABEL_78;
        v26 = 32;
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            29,
            &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
            (unsigned int)v27);
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x156,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
          (const char *)v9,
          v40);
        v21 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
          goto LABEL_78;
        v26 = 30;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          27,
          &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
          (unsigned int)v24);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x152,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)v9,
        v40);
      v21 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_78;
      v26 = 28;
    }
    WPP_SF_d(v21[2], v26, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v9);
LABEL_77:
    v21 = (PVOID *)WPP_GLOBAL_Control;
LABEL_78:
    if ( !v25 )
      goto LABEL_81;
    (**(void (__fastcall ***)(struct WNPMessageParser *, __int64))v25)(v25, 1);
    goto LABEL_80;
  }
  v17 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1 + 40LL))(a1, a2);
  v9 = v17;
  if ( v17 >= 0 )
  {
    v10 = 0;
    v16 = 4;
    goto LABEL_24;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      23,
      &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
      (unsigned int)v17);
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x133,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
    (const char *)v9,
    v40);
  v21 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    v22 = 24;
LABEL_20:
    WPP_SF_d(v21[2], v22, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v9);
LABEL_80:
    v21 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_81:
  v33 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v33);
    v21 = (PVOID *)WPP_GLOBAL_Control;
    lpMem = 0;
  }
  v35 = v47;
  if ( v47 )
  {
    v36 = GetProcessHeap();
    HeapFree(v36, 0, v35);
    v21 = (PVOID *)WPP_GLOBAL_Control;
    v47 = 0;
  }
  v37 = v48;
  if ( v48 )
  {
    v38 = GetProcessHeap();
    HeapFree(v38, 0, v37);
    v21 = (PVOID *)WPP_GLOBAL_Control;
    v48 = 0;
  }
  if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 2) != 0 && *((_BYTE *)v21 + 25) >= 6u )
    WPP_SF_d(v21[2], 37, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v9);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43, v18, v19, v20);
  return v9;
}

```

## disassembly

```asm
0x180070300  push    rbp
0x180070302  push    rbx
0x180070303  push    rsi
0x180070304  push    rdi
0x180070305  push    r12
0x180070307  push    r13
0x180070309  push    r14
0x18007030b  push    r15
0x18007030d  lea     rbp, [rsp-1D8h]
0x180070315  sub     rsp, 2D8h
0x18007031c  mov     rax, cs:__security_cookie
0x180070323  xor     rax, rsp
0x180070326  mov     [rbp+210h+var_50], rax
0x18007032d  mov     rax, [rbp+210h+arg_20]
0x180070334  mov     esi, r8d
0x180070337  mov     [rbp+210h+var_280], rax
0x18007033b  mov     r12d, edx
0x18007033e  mov     [rsp+310h+var_2A8], r9d
0x180070343  mov     r14, rcx
0x180070346  mov     rcx, cs:WPP_GLOBAL_Control
0x18007034d  lea     r15, WPP_GLOBAL_Control
0x180070354  cmp     rcx, r15
0x180070357  jz      short loc_180070382
0x180070359  test    byte ptr [rcx+1Ch], 2
0x18007035d  jz      short loc_180070382
0x18007035f  cmp     byte ptr [rcx+19h], 6
0x180070363  jb      short loc_180070382
0x180070365  mov     rcx, [rcx+10h]
0x180070369  mov     edx, 16h
0x18007036e  mov     [rsp+310h+var_2F0], r8d
0x180070373  mov     r9d, r12d
0x180070376  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18007037d  call    WPP_SF_Dd
0x180070382  xor     edi, edi
0x180070384  lea     rcx, [rbp+210h+var_260]; void *
0x180070388  xor     edx, edx; Val
0x18007038a  mov     [rsp+310h+var_2B0], rdi
0x18007038f  mov     r8d, 202h; Size
0x180070395  mov     [rbp+210h+var_288], rdi
0x180070399  mov     ebx, edi
0x18007039b  mov     [rsp+310h+lpMem], rdi
0x1800703a0  lea     r13d, [rdi+1]
0x1800703a4  mov     [rsp+310h+var_2C0], edi
0x1800703a8  mov     [rsp+310h+var_2A0], edi
0x1800703ac  mov     [rsp+310h+var_2A4], edi
0x1800703b0  call    memset_0
0x1800703b5  lea     rcx, [rsp+310h+var_2B0]
0x1800703ba  mov     [rsp+310h+var_298], rdi
0x1800703bf  mov     [rbp+210h+var_290], rdi
0x1800703c3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800703c8  lea     rcx, [r14-8]; this
0x1800703cc  lea     rdx, [rsp+310h+var_2B0]; struct IConnectionProviderEvents **
0x1800703d1  call    ?GetConnectionProviderEvents@NotificationServiceImpl@@AEAAXPEAPEAUIConnectionProviderEvents@@@Z; NotificationServiceImpl::GetConnectionProviderEvents(IConnectionProviderEvents * *)
0x1800703d6  test    cs:byte_1800AFD82, 20h
0x1800703dd  jz      short loc_1800703EE
0x1800703df  mov     r8d, esi
0x1800703e2  lea     rdx, WPNPRV_NOTSVC_ONCONNECTED
0x1800703e9  call    McTemplateU0q_EventWriteTransfer
0x1800703ee  test    cs:byte_1800AFD84, 20h
0x1800703f5  jz      short loc_180070416
0x1800703f7  lea     rax, [rbp+210h+var_278]
0x1800703fb  mov     r9d, r13d
0x1800703fe  lea     rdx, WPNPRV_PERFTRACK_ON_CONNECTED
0x180070405  mov     qword ptr [rsp+310h+var_2F0], rax; int
0x18007040a  lea     rcx, WPNCORE_PROVIDER_GUID_Context
0x180070411  call    McGenEventWrite_EventWriteTransfer
0x180070416  cmp     esi, 8804038Fh
0x18007041c  jnz     short loc_180070428
0x18007041e  mov     edi, 2
0x180070423  jmp     loc_1800704EC
0x180070428  mov     r8d, 880403E8h
0x18007042e  cmp     esi, r8d
0x180070431  jnz     loc_1800704DF
0x180070437  mov     rax, [r14]
0x18007043a  mov     edx, r12d
0x18007043d  mov     rcx, r14
0x180070440  mov     rax, [rax+28h]
0x180070444  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070449  mov     ebx, eax
0x18007044b  test    eax, eax
0x18007044d  jns     loc_1800704D5
0x180070453  mov     rcx, cs:WPP_GLOBAL_Control
0x18007045a  cmp     rcx, r15
0x18007045d  jz      short loc_180070483
0x18007045f  test    byte ptr [rcx+1Ch], 2
0x180070463  jz      short loc_180070483
0x180070465  cmp     byte ptr [rcx+19h], 2
0x180070469  jb      short loc_180070483
0x18007046b  mov     rcx, [rcx+10h]
0x18007046f  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x180070476  mov     edx, 17h
0x18007047b  mov     r9d, eax
0x18007047e  call    WPP_SF_d
0x180070483  mov     rcx, [rbp+218h]; this
0x18007048a  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180070491  mov     r9d, ebx; char *
0x180070494  mov     edx, 133h; void *
0x180070499  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007049e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800704a5  cmp     rcx, r15
0x1800704a8  jz      loc_1800708EC
0x1800704ae  test    byte ptr [rcx+1Ch], 80h
0x1800704b2  jz      loc_1800708EC
0x1800704b8  mov     edx, 18h
0x1800704bd  mov     rcx, [rcx+10h]
0x1800704c1  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x1800704c8  mov     r9d, ebx
0x1800704cb  call    WPP_SF_d
0x1800704d0  jmp     loc_1800708E5
0x1800704d5  mov     r13d, edi
0x1800704d8  mov     edi, 4
0x1800704dd  jmp     short loc_1800704EC
0x1800704df  test    esi, esi
0x1800704e1  mov     edi, r13d
0x1800704e4  mov     eax, 3
0x1800704e9  cmovs   edi, eax
0x1800704ec  lea     r15, [r14+8]
0x1800704f0  mov     rcx, r15; lpCriticalSection
0x1800704f3  call    cs:__imp_EnterCriticalSection
0x1800704f9  mov     rcx, r15; lpCriticalSection
0x1800704fc  mov     [r14+0D0h], edi
0x180070503  call    cs:__imp_LeaveCriticalSection
0x180070509  mov     [r14+0F8h], r12d
0x180070510  test    r13d, r13d
0x180070513  jz      loc_1800705BB
0x180070519  mov     rcx, [rsp+310h+var_2B0]
0x18007051e  mov     r9d, esi
0x180070521  mov     r8d, [rbp+210h+arg_28]
0x180070528  mov     edx, edi
0x18007052a  mov     rax, [rcx]
0x18007052d  mov     rax, [rax+18h]
0x180070531  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070536  mov     ebx, eax
0x180070538  test    eax, eax
0x18007053a  jns     short loc_1800705B2
0x18007053c  mov     rcx, cs:WPP_GLOBAL_Control
0x180070543  lea     r15, WPP_GLOBAL_Control
0x18007054a  cmp     rcx, r15
0x18007054d  jz      short loc_180070573
0x18007054f  test    byte ptr [rcx+1Ch], 2
0x180070553  jz      short loc_180070573
0x180070555  cmp     byte ptr [rcx+19h], 2
0x180070559  jb      short loc_180070573
0x18007055b  mov     rcx, [rcx+10h]
0x18007055f  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x180070566  mov     edx, 19h
0x18007056b  mov     r9d, eax
0x18007056e  call    WPP_SF_d
0x180070573  mov     rcx, [rbp+218h]; this
0x18007057a  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180070581  mov     r9d, ebx; char *
0x180070584  mov     edx, 146h; void *
0x180070589  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007058e  mov     rcx, cs:WPP_GLOBAL_Control
0x180070595  cmp     rcx, r15
0x180070598  jz      loc_1800708EC
0x18007059e  test    byte ptr [rcx+1Ch], 80h
0x1800705a2  jz      loc_1800708EC
0x1800705a8  mov     edx, 1Ah
0x1800705ad  jmp     loc_1800704BD
0x1800705b2  mov     edx, esi
0x1800705b4  mov     ecx, edi
0x1800705b6  call    ?WpnSqmConnectionStatusUpdate@@YAXW4_WpnSqmConnectionStatusType@@J@Z; WpnSqmConnectionStatusUpdate(_WpnSqmConnectionStatusType,long)
0x1800705bb  cmp     edi, 1
0x1800705be  jnz     loc_1800708DE
0x1800705c4  mov     edx, [rsp+310h+var_2A8]; unsigned int
0x1800705c8  lea     r8, [rbp+210h+var_288]; struct WNPMessageParser **
0x1800705cc  mov     rcx, [rbp+210h+var_280]; unsigned __int8 *
0x1800705d0  call    ?CreateInstance@WNPMessageParser@@SAJPEAEKPEAPEAV1@@Z; WNPMessageParser::CreateInstance(uchar *,ulong,WNPMessageParser * *)
0x1800705d5  mov     rsi, [rbp+210h+var_288]
0x1800705d9  mov     ebx, eax
0x1800705db  test    eax, eax
0x1800705dd  jns     loc_18007066A
0x1800705e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800705ea  lea     r15, WPP_GLOBAL_Control
0x1800705f1  cmp     rcx, r15
0x1800705f4  jz      short loc_180070618
0x1800705f6  test    byte ptr [rcx+1Ch], 2
0x1800705fa  jz      short loc_180070618
0x1800705fc  cmp     byte ptr [rcx+19h], 2
0x180070600  jb      short loc_180070618
0x180070602  mov     rcx, [rcx+10h]
0x180070606  lea     edx, [rdi+1Ah]
0x180070609  mov     r9d, eax
0x18007060c  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x180070613  call    WPP_SF_d
0x180070618  mov     rcx, [rbp+218h]; this
0x18007061f  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180070626  mov     r9d, ebx; char *
0x180070629  mov     edx, 152h; void *
0x18007062e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180070633  mov     rcx, cs:WPP_GLOBAL_Control
0x18007063a  cmp     rcx, r15
0x18007063d  jz      loc_1800708C4
0x180070643  test    byte ptr [rcx+1Ch], 80h
0x180070647  jz      loc_1800708C4
0x18007064d  mov     edx, 1Ch
0x180070652  mov     rcx, [rcx+10h]
0x180070656  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18007065d  mov     r9d, ebx
0x180070660  call    WPP_SF_d
0x180070665  jmp     loc_1800708BD
0x18007066a  lea     rdx, [rsp+310h+lpMem]; char **
0x18007066f  mov     rcx, rsi; this
0x180070672  call    ?ParseBND@WNPMessageParser@@QEAAJPEAPEAD@Z; WNPMessageParser::ParseBND(char * *)
0x180070677  mov     ebx, eax
0x180070679  test    eax, eax
0x18007067b  jns     short loc_1800706F3
0x18007067d  mov     rcx, cs:WPP_GLOBAL_Control
0x180070684  lea     r15, WPP_GLOBAL_Control
0x18007068b  cmp     rcx, r15
0x18007068e  jz      short loc_1800706B4
0x180070690  test    byte ptr [rcx+1Ch], 2
0x180070694  jz      short loc_1800706B4
0x180070696  cmp     byte ptr [rcx+19h], 2
0x18007069a  jb      short loc_1800706B4
0x18007069c  mov     rcx, [rcx+10h]
0x1800706a0  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x1800706a7  mov     edx, 1Dh
0x1800706ac  mov     r9d, eax
0x1800706af  call    WPP_SF_d
0x1800706b4  mov     rcx, [rbp+218h]; this
0x1800706bb  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800706c2  mov     r9d, ebx; char *
0x1800706c5  mov     edx, 156h; void *
0x1800706ca  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800706cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800706d6  cmp     rcx, r15
0x1800706d9  jz      loc_1800708C4
0x1800706df  test    byte ptr [rcx+1Ch], 80h
0x1800706e3  jz      loc_1800708C4
0x1800706e9  mov     edx, 1Eh
0x1800706ee  jmp     loc_180070652
0x1800706f3  mov     rdx, [rsp+310h+lpMem]; char *
0x1800706f8  lea     r12, [r14-8]
0x1800706fc  test    rdx, rdx
0x1800706ff  jz      loc_180070789
0x180070705  mov     rcx, r12; this
0x180070708  call    ?SendChallengeResponse@NotificationServiceImpl@@AEAAJPEBD@Z; NotificationServiceImpl::SendChallengeResponse(char const *)
0x18007070d  mov     ebx, eax
0x18007070f  test    eax, eax
0x180070711  jns     short loc_180070789
0x180070713  mov     rcx, cs:WPP_GLOBAL_Control
0x18007071a  lea     r15, WPP_GLOBAL_Control
0x180070721  cmp     rcx, r15
0x180070724  jz      short loc_18007074A
0x180070726  test    byte ptr [rcx+1Ch], 2
0x18007072a  jz      short loc_18007074A
0x18007072c  cmp     byte ptr [rcx+19h], 2
0x180070730  jb      short loc_18007074A
0x180070732  mov     rcx, [rcx+10h]
0x180070736  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18007073d  mov     edx, 1Fh
0x180070742  mov     r9d, eax
0x180070745  call    WPP_SF_d
0x18007074a  mov     rcx, [rbp+218h]; this
0x180070751  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180070758  mov     r9d, ebx; char *
0x18007075b  mov     edx, 15Dh; void *
0x180070760  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180070765  mov     rcx, cs:WPP_GLOBAL_Control
0x18007076c  cmp     rcx, r15
0x18007076f  jz      loc_1800708C4
0x180070775  test    byte ptr [rcx+1Ch], 80h
0x180070779  jz      loc_1800708C4
0x18007077f  mov     edx, 20h ; ' '
0x180070784  jmp     loc_180070652
0x180070789  mov     rcx, [r14+68h]
0x18007078d  lea     rdx, [rbp+210h+var_290]
0x180070791  mov     [rsp+310h+var_2D8], rdx
0x180070796  lea     r9, [rsp+310h+var_2A4]
0x18007079b  lea     rdx, [rsp+310h+var_298]
0x1800707a0  mov     [rsp+310h+var_2E0], rdx
0x1800707a5  lea     r8, [rsp+310h+var_2A0]
0x1800707aa  mov     rax, [rcx]
0x1800707ad  lea     rdx, [rbp+210h+var_260]
0x1800707b1  mov     [rsp+310h+var_2E8], 101h
0x1800707b9  mov     qword ptr [rsp+310h+var_2F0], rdx; int
0x1800707be  lea     rdx, [rsp+310h+var_2C0]
0x1800707c3  mov     rax, [rax+70h]
0x1800707c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800707cc  mov     edi, eax
0x1800707ce  test    eax, eax
0x1800707d0  jns     short loc_180070809
0x1800707d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800707d9  lea     rax, WPP_GLOBAL_Control
0x1800707e0  cmp     rcx, rax
0x1800707e3  jz      short loc_180070809
0x1800707e5  test    byte ptr [rcx+1Ch], 8
0x1800707e9  jz      short loc_180070809
0x1800707eb  cmp     byte ptr [rcx+19h], 2
0x1800707ef  jb      short loc_180070809
0x1800707f1  mov     rcx, [rcx+10h]
0x1800707f5  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x1800707fc  mov     edx, 21h ; '!'
0x180070801  mov     r9d, edi
0x180070804  call    WPP_SF_d
0x180070809  xor     ebx, ebx
0x18007080b  mov     rcx, r15; lpCriticalSection
0x18007080e  test    edi, edi
  ... truncated ...
```
