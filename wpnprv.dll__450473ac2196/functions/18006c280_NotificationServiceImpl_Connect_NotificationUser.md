# NotificationServiceImpl::Connect(_NotificationUser)

- ea: `0x18006c280`
- end: `0x18006c631`
- name: `?Connect@NotificationServiceImpl@@UEAAJU_NotificationUser@@@Z`
- size: `945`
- prototype: `__int64 __fastcall(__int64, __int128 *)`
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000ba54`
- `0x18000fddc`
- `0x18000fe54`
- `0x18000fe94`
- `0x18001c4bc`
- `0x18002f808`
- `0x18006c280`
- `0x18006d890`
- `0x18006f2d4`
- `0x18006f460`
- `0x180081bd8`
- `0x180085634`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006c3d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006c3d6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006c3c2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006c3c2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006c5d2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006c5d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006c5c4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006c5c4`

## string_xrefs

- `0x18006c36e`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x18006c4da`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x18006c57a`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`

## pseudocode

```c
__int64 __fastcall NotificationServiceImpl::Connect(__int64 a1, __int128 *a2)
{
  int v4; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  PVOID *v8; // rcx
  bool v9; // bl
  unsigned int v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  PVOID *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  int v17; // eax
  __int64 (__fastcall ***v18)(_QWORD, char *, LPVOID *, _QWORD); // rcx
  __int64 (__fastcall **v19)(_QWORD, char *, LPVOID *, _QWORD); // rax
  int v20; // ebx
  int v21; // eax
  void *v22; // rdi
  HANDLE ProcessHeap; // rax
  int v25; // [rsp+20h] [rbp-40h]
  struct IConnectionProviderEvents *v26[2]; // [rsp+30h] [rbp-30h] BYREF
  __int128 v27; // [rsp+40h] [rbp-20h] BYREF
  char v28; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  bool v30; // [rsp+A0h] [rbp+40h] BYREF
  LPVOID lpMem; // [rsp+A8h] [rbp+48h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    v25 = *((_DWORD *)a2 + 2);
    WPP_SF_Id(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, *(_QWORD *)a2);
  }
  v26[0] = 0;
  lpMem = 0;
  v30 = 0;
  v4 = IsMachineConnectedToInternet(&v30);
  if ( v4 >= 0 )
  {
    v9 = v30;
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        95,
        &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
        (unsigned int)v4);
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    v9 = 1;
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 8) != 0 && *((_BYTE *)v8 + 25) >= 5u )
  {
    LOBYTE(v7) = v9;
    WPP_SF_c(v8[2], 96, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v7);
  }
  if ( v9 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v26, v5, v6, v7);
    NotificationServiceImpl::GetConnectionProviderEvents((NotificationServiceImpl *)a1, v26);
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
    *(_DWORD *)(a1 + 216) = 7;
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
    v17 = (*(__int64 (__fastcall **)(struct IConnectionProviderEvents *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v26[0]
                                                                                                + 24LL))(
            v26[0],
            *(unsigned int *)(a1 + 216),
            0,
            0);
    if ( v17 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        98,
        &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
        (unsigned int)v17);
    }
    v18 = *(__int64 (__fastcall ****)(_QWORD, char *, LPVOID *, _QWORD))(a1 + 104);
    v19 = *v18;
    v27 = (unsigned __int64)(a1 + 208);
    v28 = 1;
    v20 = (*v19)(v18, (char *)&v27 + 8, &lpMem, 0);
    wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(&v27);
    if ( v20 >= 0 )
    {
      v27 = *a2;
      v21 = NotificationServiceImpl::OnAuthSuccess(a1, *(_QWORD *)(a1 + 208), lpMem, &v27);
      v10 = v21;
      if ( v21 >= 0 )
      {
LABEL_46:
        v14 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_47;
      }
      WpnSqmConnectionStatusUpdate(3, (unsigned int)v21);
      v10 = -2143420133;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          102,
          &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
          2151547163LL);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x4B6,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)0x803E011BLL,
        v25);
      v14 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v15 = 103;
        v16 = 2151547163LL;
        goto LABEL_45;
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
          99,
          &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
          (unsigned int)v20);
      }
      NotificationServiceImpl::OnAuthError((NotificationServiceImpl *)a1, v20);
      v10 = -2143420134;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          100,
          &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
          2151547162LL);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x4A9,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)0x803E011ALL,
        v25);
      v14 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v15 = 101;
        v16 = 2151547162LL;
        goto LABEL_45;
      }
    }
  }
  else
  {
    v10 = -2013002766;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x48F,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
      (const char *)0x880403F2LL,
      v25);
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v15 = 97;
      v16 = 2281964530LL;
LABEL_45:
      WPP_SF_d(v14[2], v15, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v16);
      goto LABEL_46;
    }
  }
LABEL_47:
  v22 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v22);
    lpMem = 0;
    v14 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 2) != 0 && *((_BYTE *)v14 + 25) >= 6u )
    WPP_SF_d(v14[2], 104, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v10);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v26, v11, v12, v13);
  return v10;
}

```

## disassembly

```asm
0x18006c280  mov     [rsp-28h+arg_0], rbx
0x18006c285  mov     [rsp-28h+arg_8], rsi
0x18006c28a  push    rbp
0x18006c28b  push    rdi
0x18006c28c  push    r12
0x18006c28e  push    r13
0x18006c290  push    r14
0x18006c292  mov     rbp, rsp
0x18006c295  sub     rsp, 60h
0x18006c299  mov     rsi, rdx
0x18006c29c  mov     rdi, rcx
0x18006c29f  lea     r12, WPP_GLOBAL_Control
0x18006c2a6  lea     r13, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006c2ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c2b4  cmp     rcx, r12
0x18006c2b7  jz      short loc_18006C2E0
0x18006c2b9  test    byte ptr [rcx+1Ch], 2
0x18006c2bd  jz      short loc_18006C2E0
0x18006c2bf  cmp     byte ptr [rcx+19h], 6
0x18006c2c3  jb      short loc_18006C2E0
0x18006c2c5  mov     edx, 5Eh ; '^'
0x18006c2ca  mov     eax, [rsi+8]
0x18006c2cd  mov     [rsp+60h+var_40], eax; int
0x18006c2d1  mov     r9, [rsi]
0x18006c2d4  mov     r8, r13
0x18006c2d7  mov     rcx, [rcx+10h]
0x18006c2db  call    WPP_SF_Id
0x18006c2e0  xor     ebx, ebx
0x18006c2e2  mov     [rbp+var_30], rbx
0x18006c2e6  mov     [rbp+lpMem], rbx
0x18006c2ea  mov     [rbp+arg_10], bl
0x18006c2ed  lea     rcx, [rbp+arg_10]; bool *
0x18006c2f1  call    ?IsMachineConnectedToInternet@@YAJPEA_N@Z; IsMachineConnectedToInternet(bool *)
0x18006c2f6  test    eax, eax
0x18006c2f8  jns     short loc_18006C32F
0x18006c2fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c301  cmp     rcx, r12
0x18006c304  jz      short loc_18006C32B
0x18006c306  test    byte ptr [rcx+1Ch], 8
0x18006c30a  jz      short loc_18006C32B
0x18006c30c  cmp     byte ptr [rcx+19h], 3
0x18006c310  jb      short loc_18006C32B
0x18006c312  lea     edx, [rbx+5Fh]
0x18006c315  mov     r9d, eax
0x18006c318  mov     r8, r13
0x18006c31b  mov     rcx, [rcx+10h]
0x18006c31f  call    WPP_SF_d
0x18006c324  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c32b  mov     bl, 1
0x18006c32d  jmp     short loc_18006C339
0x18006c32f  mov     bl, [rbp+arg_10]
0x18006c332  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c339  cmp     rcx, r12
0x18006c33c  jz      short loc_18006C35E
0x18006c33e  test    byte ptr [rcx+1Ch], 8
0x18006c342  jz      short loc_18006C35E
0x18006c344  cmp     byte ptr [rcx+19h], 5
0x18006c348  jb      short loc_18006C35E
0x18006c34a  mov     edx, 60h ; '`'
0x18006c34f  mov     r9b, bl
0x18006c352  mov     r8, r13
0x18006c355  mov     rcx, [rcx+10h]
0x18006c359  call    WPP_SF_c
0x18006c35e  test    bl, bl
0x18006c360  jnz     short loc_18006C3A9
0x18006c362  mov     ebx, 880403F2h
0x18006c367  mov     rcx, [rbp+28h]; this
0x18006c36b  mov     r9d, ebx; char *
0x18006c36e  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006c375  mov     edx, 48Fh; void *
0x18006c37a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006c37f  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c386  cmp     rcx, r12
0x18006c389  jz      loc_18006C5BB
0x18006c38f  test    byte ptr [rcx+1Ch], 80h
0x18006c393  jz      loc_18006C5BB
0x18006c399  mov     edx, 61h ; 'a'
0x18006c39e  mov     r9d, 880403F2h
0x18006c3a4  jmp     loc_18006C5A8
0x18006c3a9  lea     rcx, [rbp+var_30]
0x18006c3ad  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006c3b2  lea     rdx, [rbp+var_30]; struct IConnectionProviderEvents **
0x18006c3b6  mov     rcx, rdi; this
0x18006c3b9  call    ?GetConnectionProviderEvents@NotificationServiceImpl@@AEAAXPEAPEAUIConnectionProviderEvents@@@Z; NotificationServiceImpl::GetConnectionProviderEvents(IConnectionProviderEvents * *)
0x18006c3be  lea     rcx, [rdi+10h]; lpCriticalSection
0x18006c3c2  call    cs:__imp_EnterCriticalSection
0x18006c3c8  mov     dword ptr [rdi+0D8h], 7
0x18006c3d2  lea     rcx, [rdi+10h]; lpCriticalSection
0x18006c3d6  call    cs:__imp_LeaveCriticalSection
0x18006c3dc  mov     rcx, [rbp+var_30]
0x18006c3e0  mov     rax, [rcx]
0x18006c3e3  xor     r9d, r9d
0x18006c3e6  xor     r8d, r8d
0x18006c3e9  mov     edx, [rdi+0D8h]
0x18006c3ef  mov     rax, [rax+18h]
0x18006c3f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c3f8  test    eax, eax
0x18006c3fa  jns     short loc_18006C428
0x18006c3fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c403  cmp     rcx, r12
0x18006c406  jz      short loc_18006C428
0x18006c408  test    byte ptr [rcx+1Ch], 2
0x18006c40c  jz      short loc_18006C428
0x18006c40e  cmp     byte ptr [rcx+19h], 2
0x18006c412  jb      short loc_18006C428
0x18006c414  mov     edx, 62h ; 'b'
0x18006c419  mov     r9d, eax
0x18006c41c  mov     r8, r13
0x18006c41f  mov     rcx, [rcx+10h]
0x18006c423  call    WPP_SF_d
0x18006c428  mov     rcx, [rdi+68h]
0x18006c42c  mov     rax, [rcx]
0x18006c42f  lea     r14, [rdi+0D0h]
0x18006c436  mov     qword ptr [rbp+var_20], r14
0x18006c43a  mov     qword ptr [rbp+var_20+8], 0
0x18006c442  mov     [rbp+var_10], 1
0x18006c446  xor     r9d, r9d
0x18006c449  lea     r8, [rbp+lpMem]
0x18006c44d  lea     rdx, [rbp+var_20+8]
0x18006c451  mov     rax, [rax]
0x18006c454  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c459  mov     ebx, eax
0x18006c45b  lea     rcx, [rbp+var_20]
0x18006c45f  call    ??1?$out_param_t@V?$unique_ptr@DUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(void)
0x18006c464  test    ebx, ebx
0x18006c466  jns     loc_18006C515
0x18006c46c  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c473  cmp     rcx, r12
0x18006c476  jz      short loc_18006C498
0x18006c478  test    byte ptr [rcx+1Ch], 2
0x18006c47c  jz      short loc_18006C498
0x18006c47e  cmp     byte ptr [rcx+19h], 2
0x18006c482  jb      short loc_18006C498
0x18006c484  mov     edx, 63h ; 'c'
0x18006c489  mov     r9d, ebx
0x18006c48c  mov     r8, r13
0x18006c48f  mov     rcx, [rcx+10h]
0x18006c493  call    WPP_SF_d
0x18006c498  mov     edx, ebx; int
0x18006c49a  mov     rcx, rdi; this
0x18006c49d  call    ?OnAuthError@NotificationServiceImpl@@AEAAXJ@Z; NotificationServiceImpl::OnAuthError(long)
0x18006c4a2  mov     ebx, 803E011Ah
0x18006c4a7  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c4ae  cmp     rcx, r12
0x18006c4b1  jz      short loc_18006C4D3
0x18006c4b3  test    byte ptr [rcx+1Ch], 2
0x18006c4b7  jz      short loc_18006C4D3
0x18006c4b9  cmp     byte ptr [rcx+19h], 2
0x18006c4bd  jb      short loc_18006C4D3
0x18006c4bf  mov     edx, 64h ; 'd'
0x18006c4c4  mov     r9d, ebx
0x18006c4c7  mov     r8, r13
0x18006c4ca  mov     rcx, [rcx+10h]
0x18006c4ce  call    WPP_SF_d
0x18006c4d3  mov     rcx, [rbp+28h]; this
0x18006c4d7  mov     r9d, ebx; char *
0x18006c4da  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006c4e1  mov     edx, 4A9h; void *
0x18006c4e6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006c4eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c4f2  cmp     rcx, r12
0x18006c4f5  jz      loc_18006C5BB
0x18006c4fb  test    byte ptr [rcx+1Ch], 80h
0x18006c4ff  jz      loc_18006C5BB
0x18006c505  mov     edx, 65h ; 'e'
0x18006c50a  mov     r9d, 803E011Ah
0x18006c510  jmp     loc_18006C5A8
0x18006c515  movups  xmm0, xmmword ptr [rsi]
0x18006c518  movdqu  [rbp+var_20], xmm0
0x18006c51d  lea     r9, [rbp+var_20]
0x18006c521  mov     r8, [rbp+lpMem]
0x18006c525  mov     rdx, [r14]
0x18006c528  mov     rcx, rdi
0x18006c52b  call    ?OnAuthSuccess@NotificationServiceImpl@@AEAAJPEAD0U_NotificationUser@@@Z; NotificationServiceImpl::OnAuthSuccess(char *,char *,_NotificationUser)
0x18006c530  mov     ebx, eax
0x18006c532  test    eax, eax
0x18006c534  jns     short loc_18006C5B4
0x18006c536  mov     edx, eax
0x18006c538  mov     ecx, 3
0x18006c53d  call    ?WpnSqmConnectionStatusUpdate@@YAXW4_WpnSqmConnectionStatusType@@J@Z; WpnSqmConnectionStatusUpdate(_WpnSqmConnectionStatusType,long)
0x18006c542  mov     ebx, 803E011Bh
0x18006c547  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c54e  cmp     rcx, r12
0x18006c551  jz      short loc_18006C573
0x18006c553  test    byte ptr [rcx+1Ch], 2
0x18006c557  jz      short loc_18006C573
0x18006c559  cmp     byte ptr [rcx+19h], 2
0x18006c55d  jb      short loc_18006C573
0x18006c55f  mov     edx, 66h ; 'f'
0x18006c564  mov     r9d, ebx
0x18006c567  mov     r8, r13
0x18006c56a  mov     rcx, [rcx+10h]
0x18006c56e  call    WPP_SF_d
0x18006c573  mov     rcx, [rbp+28h]; this
0x18006c577  mov     r9d, ebx; char *
0x18006c57a  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006c581  mov     edx, 4B6h; void *
0x18006c586  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006c58b  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c592  cmp     rcx, r12
0x18006c595  jz      short loc_18006C5BB
0x18006c597  test    byte ptr [rcx+1Ch], 80h
0x18006c59b  jz      short loc_18006C5BB
0x18006c59d  mov     edx, 67h ; 'g'
0x18006c5a2  mov     r9d, 803E011Bh
0x18006c5a8  mov     r8, r13
0x18006c5ab  mov     rcx, [rcx+10h]
0x18006c5af  call    WPP_SF_d
0x18006c5b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c5bb  mov     rdi, [rbp+lpMem]
0x18006c5bf  test    rdi, rdi
0x18006c5c2  jz      short loc_18006C5E7
0x18006c5c4  call    cs:__imp_GetProcessHeap
0x18006c5ca  mov     r8, rdi; lpMem
0x18006c5cd  xor     edx, edx; dwFlags
0x18006c5cf  mov     rcx, rax; hHeap
0x18006c5d2  call    cs:__imp_HeapFree
0x18006c5d8  mov     [rbp+lpMem], 0
0x18006c5e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c5e7  cmp     rcx, r12
0x18006c5ea  jz      short loc_18006C60D
0x18006c5ec  test    byte ptr [rcx+1Ch], 2
0x18006c5f0  jz      short loc_18006C60D
0x18006c5f2  cmp     byte ptr [rcx+19h], 6
0x18006c5f6  jb      short loc_18006C60D
0x18006c5f8  mov     edx, 68h ; 'h'
0x18006c5fd  mov     r9d, ebx
0x18006c600  mov     r8, r13
0x18006c603  mov     rcx, [rcx+10h]
0x18006c607  call    WPP_SF_d
0x18006c60c  nop
0x18006c60d  lea     rcx, [rbp+var_30]
0x18006c611  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006c616  mov     eax, ebx
0x18006c618  lea     r11, [rsp+60h+var_s0]
0x18006c61d  mov     rbx, [r11+30h]
0x18006c621  mov     rsi, [r11+38h]
0x18006c625  mov     rsp, r11
0x18006c628  pop     r14
0x18006c62a  pop     r13
0x18006c62c  pop     r12
0x18006c62e  pop     rdi
0x18006c62f  pop     rbp
0x18006c630  retn
```
