# CWorkspaceSilentSetupManager::SetupWorkspace(ushort const *,ushort *,int)

- ea: `0x180040774`
- end: `0x180040bca`
- name: `?SetupWorkspace@CWorkspaceSilentSetupManager@@QEAAJPEBGPEAGH@Z`
- size: `1110`
- prototype: `__int64 __fastcall(CWorkspaceSilentSetupManager *__hidden this, const unsigned __int16 *, unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180024bb0`
- `0x180040bd0`

## callees

- `0x18000b1d8`
- `0x18000ec54`
- `0x18000ec94`
- `0x18000ece0`
- `0x180019fb0`
- `0x180020b08`
- `0x1800298ac`
- `0x18002f810`
- `0x18003246c`
- `0x1800387e4`
- `0x180040774`
- `0x180078650`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040966`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800409a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040966`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800409a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800407e8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800407e8`
- `USER32!TranslateMessage` at `0x180040ab4`
- `USER32!TranslateMessage` at `0x180040ab4`
- `USER32!PostQuitMessage` at `0x180040af3`
- `USER32!PostQuitMessage` at `0x180040af3`
- `USER32!GetMessageW` at `0x180040a85`
- `USER32!GetMessageW` at `0x180040a85`
- `USER32!DispatchMessageW` at `0x180040abf`
- `USER32!DispatchMessageW` at `0x180040abf`
- `USER32!SetTimer` at `0x18004093a`
- `USER32!SetTimer` at `0x18004093a`
- `USER32!KillTimer` at `0x180040ba9`
- `USER32!KillTimer` at `0x180040ba9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWorkspaceSilentSetupManager::SetupWorkspace(
        CWorkspaceSilentSetupManager *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        int a4)
{
  UINT_PTR v7; // r14
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v9; // ecx
  int v10; // edi
  PVOID *v11; // rax
  CWorkspaceManager *v12; // rsi
  unsigned int v13; // eax
  CWorkspaceManager *Instance; // rax
  unsigned int v15; // eax
  unsigned int v16; // eax
  signed int LastError; // eax
  unsigned int v18; // ebx
  unsigned int v19; // eax
  signed int v20; // eax
  unsigned int v21; // eax
  int MessageW; // eax
  unsigned int v23; // eax
  int v24; // ebx
  unsigned int v25; // eax
  __int64 v27; // [rsp+28h] [rbp-B0h]
  struct tagMSG Msg; // [rsp+70h] [rbp-68h] BYREF

  memset(&Msg, 0, sizeof(Msg));
  v7 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      WPP_2706fdb90ddc34e0cc982f319c56b82d_Traceguids,
      CurrentThreadActivityIdPrefix);
  }
  *((_DWORD *)this + 5) = GetCurrentThreadId();
  if ( !(unsigned int)IsURLValid(a2) )
  {
    v10 = -2147220983;
    if ( (Microsoft_Windows_RemoteApp_and_Desktop_ConnectionsEnableBits & 1) != 0 )
      McTemplateU0zzqq_EventWriteTransfer(v9, (unsigned int)TSWORKSPACE_SETUP_CONNECTION_ERROR, 0, (_DWORD)a2, 9, 0);
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_64;
    v12 = 0;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_56;
    v13 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_2706fdb90ddc34e0cc982f319c56b82d_Traceguids, v13);
LABEL_55:
    v11 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_56;
  }
  Instance = CWorkspaceManager::GetInstance();
  v12 = Instance;
  if ( !Instance )
  {
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        WPP_2706fdb90ddc34e0cc982f319c56b82d_Traceguids,
        v15,
        -2147024882);
      v11 = (PVOID *)WPP_GLOBAL_Control;
    }
    v10 = -2147024882;
    goto LABEL_56;
  }
  if ( !CWorkspaceManager::IsUniqueWorkspaceUrl(Instance, a2) )
  {
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v16 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        WPP_2706fdb90ddc34e0cc982f319c56b82d_Traceguids,
        v16,
        -2147220975);
      v11 = (PVOID *)WPP_GLOBAL_Control;
    }
    v10 = -2147220975;
    goto LABEL_56;
  }
  v7 = SetTimer(0, 0, *((_DWORD *)this + 4), 0);
  if ( !v7 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      v18 = LastError;
      if ( LastError > 0 )
        v18 = (unsigned __int16)LastError | 0x80070000;
      v19 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_2706fdb90ddc34e0cc982f319c56b82d_Traceguids, v19, v18);
    }
    v20 = GetLastError();
    v10 = v20;
    if ( v20 > 0 )
      v10 = (unsigned __int16)v20 | 0x80070000;
    goto LABEL_55;
  }
  v10 = CWorkspaceManager::SetupWorkspace(v12, 0, a2, 0, 0, 0, 0, 1, 1u, a4, 0, 0, 0, this);
  if ( v10 < 0 )
  {
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_61;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_56;
    v21 = RdpWppGetCurrentThreadActivityIdPrefix();
    LODWORD(v27) = v10;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      (unsigned int)WPP_2706fdb90ddc34e0cc982f319c56b82d_Traceguids,
      v21,
      (__int64)"CWorkspaceManager::SetupWorkspaceEx failed.",
      v27);
    goto LABEL_55;
  }
  while ( 1 )
  {
    MessageW = GetMessageW(&Msg, 0, 0, 0);
    if ( !MessageW )
    {
      v10 = *((_DWORD *)this + 2);
      goto LABEL_55;
    }
    if ( MessageW == -1 )
      break;
    switch ( Msg.message )
    {
      case 0x113u:
        if ( v7 == Msg.wParam )
        {
          CWorkspaceManager::CancelSetupWorkspace(v12);
          *((_DWORD *)this + 2) = -2147023436;
LABEL_48:
          PostQuitMessage(0);
        }
        break;
      case 0x80CDu:
        goto LABEL_48;
      case 0x80CFu:
        CWorkspaceManager::CancelSetupWorkspace(v12);
        *((_DWORD *)this + 2) = -2147220972;
        goto LABEL_48;
      default:
        TranslateMessage(&Msg);
        DispatchMessageW(&Msg);
        break;
    }
  }
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v23 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      WPP_2706fdb90ddc34e0cc982f319c56b82d_Traceguids,
      v23,
      -2147467259);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  v10 = -2147467259;
LABEL_56:
  if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 && *((_BYTE *)v11 + 25) >= 4u )
  {
    v24 = *((_DWORD *)this + 3);
    v25 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DLD(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_2706fdb90ddc34e0cc982f319c56b82d_Traceguids, v25, v10, v24);
  }
  if ( v12 )
LABEL_61:
    CWorkspaceManager::CancelSetupWorkspace(v12);
  if ( v7 )
    KillTimer(0, v7);
LABEL_64:
  *((_DWORD *)this + 5) = 0;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180040774  mov     rax, rsp
0x180040777  push    rbx
0x180040778  push    rbp
0x180040779  push    rsi
0x18004077a  push    rdi
0x18004077b  push    r12
0x18004077d  push    r13
0x18004077f  push    r14
0x180040781  sub     rsp, 0A0h
0x180040788  xorps   xmm0, xmm0
0x18004078b  mov     edi, r9d
0x18004078e  movups  xmmword ptr [rax-68h], xmm0
0x180040792  mov     rbx, rdx
0x180040795  mov     rbp, rcx
0x180040798  movups  xmmword ptr [rax-58h], xmm0
0x18004079c  xor     r14d, r14d
0x18004079f  movups  xmmword ptr [rax-48h], xmm0
0x1800407a3  mov     rax, cs:WPP_GLOBAL_Control
0x1800407aa  lea     r13, WPP_GLOBAL_Control
0x1800407b1  lea     r12, WPP_2706fdb90ddc34e0cc982f319c56b82d_Traceguids
0x1800407b8  cmp     rax, r13
0x1800407bb  jz      short loc_1800407E8
0x1800407bd  test    byte ptr [rax+1Ch], 1
0x1800407c1  jz      short loc_1800407E8
0x1800407c3  cmp     byte ptr [rax+19h], 4
0x1800407c7  jb      short loc_1800407E8
0x1800407c9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800407ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800407d5  lea     edx, [r14+0Bh]
0x1800407d9  mov     r9d, eax
0x1800407dc  mov     r8, r12
0x1800407df  mov     rcx, [rcx+10h]
0x1800407e3  call    WPP_SF_D
0x1800407e8  call    cs:__imp_GetCurrentThreadId
0x1800407ee  mov     rcx, rbx; unsigned __int16 *
0x1800407f1  mov     [rbp+14h], eax
0x1800407f4  call    ?IsURLValid@@YAHPEBG@Z; IsURLValid(ushort const *)
0x1800407f9  test    eax, eax
0x1800407fb  jnz     short loc_180040873
0x1800407fd  test    cs:Microsoft_Windows_RemoteApp_and_Desktop_ConnectionsEnableBits, 1
0x180040804  mov     edi, 80040209h
0x180040809  jz      short loc_18004082A
0x18004080b  mov     dword ptr [rsp+0D8h+var_B0], r14d
0x180040810  lea     rdx, TSWORKSPACE_SETUP_CONNECTION_ERROR
0x180040817  mov     r9, rbx
0x18004081a  mov     [rsp+0D8h+var_B8], 80040209h
0x180040822  xor     r8d, r8d
0x180040825  call    McTemplateU0zzqq_EventWriteTransfer
0x18004082a  mov     rax, cs:WPP_GLOBAL_Control
0x180040831  cmp     rax, r13
0x180040834  jz      loc_180040BAF
0x18004083a  xor     esi, esi
0x18004083c  test    byte ptr [rax+1Ch], 1
0x180040840  jz      loc_180040B56
0x180040846  cmp     byte ptr [rax+19h], 2
0x18004084a  jb      loc_180040B56
0x180040850  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180040855  mov     rcx, cs:WPP_GLOBAL_Control
0x18004085c  lea     edx, [rsi+0Ch]
0x18004085f  mov     r9d, eax
0x180040862  mov     r8, r12
0x180040865  mov     rcx, [rcx+10h]
0x180040869  call    WPP_SF_D
0x18004086e  jmp     loc_180040B4F
0x180040873  call    ?GetInstance@CWorkspaceManager@@SAPEAV1@XZ; CWorkspaceManager::GetInstance(void)
0x180040878  mov     rsi, rax
0x18004087b  test    rax, rax
0x18004087e  jnz     short loc_1800408CF
0x180040880  mov     rax, cs:WPP_GLOBAL_Control
0x180040887  cmp     rax, r13
0x18004088a  jz      short loc_1800408C5
0x18004088c  test    byte ptr [rax+1Ch], 8
0x180040890  jz      short loc_1800408C5
0x180040892  cmp     byte ptr [rax+19h], 2
0x180040896  jb      short loc_1800408C5
0x180040898  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18004089d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800408a4  lea     edx, [rsi+0Dh]
0x1800408a7  mov     r9d, eax
0x1800408aa  mov     [rsp+0D8h+var_B8], 8007000Eh
0x1800408b2  mov     r8, r12
0x1800408b5  mov     rcx, [rcx+10h]
0x1800408b9  call    WPP_SF_Dd
0x1800408be  mov     rax, cs:WPP_GLOBAL_Control
0x1800408c5  mov     edi, 8007000Eh
0x1800408ca  jmp     loc_180040B56
0x1800408cf  mov     rdx, rbx; unsigned __int16 *
0x1800408d2  mov     rcx, rsi; this
0x1800408d5  call    ?IsUniqueWorkspaceUrl@CWorkspaceManager@@QEAAHPEBG@Z; CWorkspaceManager::IsUniqueWorkspaceUrl(ushort const *)
0x1800408da  test    eax, eax
0x1800408dc  jnz     short loc_18004092F
0x1800408de  mov     rax, cs:WPP_GLOBAL_Control
0x1800408e5  cmp     rax, r13
0x1800408e8  jz      short loc_180040925
0x1800408ea  test    byte ptr [rax+1Ch], 8
0x1800408ee  jz      short loc_180040925
0x1800408f0  cmp     byte ptr [rax+19h], 2
0x1800408f4  jb      short loc_180040925
0x1800408f6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800408fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180040902  mov     edx, 0Eh
0x180040907  mov     r9d, eax
0x18004090a  mov     [rsp+0D8h+var_B8], 80040211h
0x180040912  mov     r8, r12
0x180040915  mov     rcx, [rcx+10h]
0x180040919  call    WPP_SF_Dd
0x18004091e  mov     rax, cs:WPP_GLOBAL_Control
0x180040925  mov     edi, 80040211h
0x18004092a  jmp     loc_180040B56
0x18004092f  mov     r8d, [rbp+10h]; uElapse
0x180040933  xor     r9d, r9d; lpTimerFunc
0x180040936  xor     edx, edx; nIDEvent
0x180040938  xor     ecx, ecx; hWnd
0x18004093a  call    cs:__imp_SetTimer
0x180040940  mov     r14, rax
0x180040943  test    rax, rax
0x180040946  jnz     short loc_1800409BE
0x180040948  mov     rcx, cs:WPP_GLOBAL_Control
0x18004094f  mov     r12d, 80070000h
0x180040955  cmp     rcx, r13
0x180040958  jz      short loc_1800409A0
0x18004095a  test    byte ptr [rcx+1Ch], 8
0x18004095e  jz      short loc_1800409A0
0x180040960  cmp     byte ptr [rcx+19h], 2
0x180040964  jb      short loc_1800409A0
0x180040966  call    cs:__imp_GetLastError
0x18004096c  mov     ebx, eax
0x18004096e  test    eax, eax
0x180040970  jle     short loc_180040978
0x180040972  movzx   ebx, ax
0x180040975  or      ebx, r12d
0x180040978  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18004097d  mov     rcx, cs:WPP_GLOBAL_Control
0x180040984  lea     r8, WPP_2706fdb90ddc34e0cc982f319c56b82d_Traceguids
0x18004098b  mov     edx, 0Fh
0x180040990  mov     [rsp+0D8h+var_B8], ebx
0x180040994  mov     r9d, eax
0x180040997  mov     rcx, [rcx+10h]
0x18004099b  call    WPP_SF_Dd
0x1800409a0  call    cs:__imp_GetLastError
0x1800409a6  mov     edi, eax
0x1800409a8  test    eax, eax
0x1800409aa  jle     short loc_1800409B2
0x1800409ac  movzx   edi, ax
0x1800409af  or      edi, r12d
0x1800409b2  lea     r12, WPP_2706fdb90ddc34e0cc982f319c56b82d_Traceguids
0x1800409b9  jmp     loc_180040B4F
0x1800409be  mov     [rsp+0D8h+var_70], rbp; struct ITSWorkspaceResult *
0x1800409c3  xor     r9d, r9d; unsigned __int16 *
0x1800409c6  mov     [rsp+0D8h+var_78], 0; struct CWorkspace *
0x1800409cf  mov     r8, rbx; unsigned __int16 *
0x1800409d2  mov     [rsp+0D8h+var_80], 0; int
0x1800409da  xor     edx, edx; HWND
0x1800409dc  mov     [rsp+0D8h+var_88], 0; unsigned __int16 *
0x1800409e5  mov     rcx, rsi; this
0x1800409e8  mov     [rsp+0D8h+var_90], edi; int
0x1800409ec  mov     [rsp+0D8h+var_98], 1; unsigned int
0x1800409f4  mov     [rsp+0D8h+var_A0], 1; int
0x1800409fc  mov     [rsp+0D8h+var_A8], 0; int
0x180040a04  mov     dword ptr [rsp+0D8h+var_B0], 0; unsigned int
0x180040a0c  mov     [rsp+0D8h+var_B8], 0; int
0x180040a14  call    ?SetupWorkspace@CWorkspaceManager@@QEAAJPEAUHWND__@@PEBG1JKHHKH1HPEAVCWorkspace@@PEAVITSWorkspaceResult@@@Z; CWorkspaceManager::SetupWorkspace(HWND__ *,ushort const *,ushort const *,long,ulong,int,int,ulong,int,ushort const *,int,CWorkspace *,ITSWorkspaceResult *)
0x180040a19  mov     edi, eax
0x180040a1b  test    eax, eax
0x180040a1d  jns     short loc_180040A78
0x180040a1f  mov     rax, cs:WPP_GLOBAL_Control
0x180040a26  cmp     rax, r13
0x180040a29  jz      loc_180040B97
0x180040a2f  test    byte ptr [rax+1Ch], 8
0x180040a33  jz      loc_180040B56
0x180040a39  cmp     byte ptr [rax+19h], 2
0x180040a3d  jb      loc_180040B56
0x180040a43  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180040a48  lea     rcx, aCworkspacemana; "CWorkspaceManager::SetupWorkspaceEx fai"...
0x180040a4f  mov     dword ptr [rsp+0D8h+var_B0], edi
0x180040a53  mov     qword ptr [rsp+0D8h+var_B8], rcx
0x180040a58  mov     edx, 10h
0x180040a5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180040a64  mov     r9d, eax
0x180040a67  mov     r8, r12
0x180040a6a  mov     rcx, [rcx+10h]
0x180040a6e  call    WPP_SF_DsD
0x180040a73  jmp     loc_180040B4F
0x180040a78  xor     r9d, r9d; wMsgFilterMax
0x180040a7b  lea     rcx, [rsp+0D8h+Msg]; lpMsg
0x180040a80  xor     r8d, r8d; wMsgFilterMin
0x180040a83  xor     edx, edx; hWnd
0x180040a85  call    cs:__imp_GetMessageW
0x180040a8b  test    eax, eax
0x180040a8d  jz      loc_180040B4C
0x180040a93  cmp     eax, 0FFFFFFFFh
0x180040a96  jz      short loc_180040AFE
0x180040a98  mov     eax, [rsp+0D8h+Msg.message]
0x180040a9c  sub     eax, 113h
0x180040aa1  jz      short loc_180040AD8
0x180040aa3  sub     eax, 7FBAh
0x180040aa8  jz      short loc_180040AF1
0x180040aaa  cmp     eax, 2
0x180040aad  jz      short loc_180040AC7
0x180040aaf  lea     rcx, [rsp+0D8h+Msg]; lpMsg
0x180040ab4  call    cs:__imp_TranslateMessage
0x180040aba  lea     rcx, [rsp+0D8h+Msg]; lpMsg
0x180040abf  call    cs:__imp_DispatchMessageW
0x180040ac5  jmp     short loc_180040A78
0x180040ac7  mov     rcx, rsi; this
0x180040aca  call    ?CancelSetupWorkspace@CWorkspaceManager@@QEAAXXZ; CWorkspaceManager::CancelSetupWorkspace(void)
0x180040acf  mov     dword ptr [rbp+8], 80040214h
0x180040ad6  jmp     short loc_180040AF1
0x180040ad8  cmp     r14, [rsp+0D8h+Msg.wParam]
0x180040ae0  jnz     short loc_180040A78
0x180040ae2  mov     rcx, rsi; this
0x180040ae5  call    ?CancelSetupWorkspace@CWorkspaceManager@@QEAAXXZ; CWorkspaceManager::CancelSetupWorkspace(void)
0x180040aea  mov     dword ptr [rbp+8], 800705B4h
0x180040af1  xor     ecx, ecx; nExitCode
0x180040af3  call    cs:__imp_PostQuitMessage
0x180040af9  jmp     loc_180040A78
0x180040afe  mov     rax, cs:WPP_GLOBAL_Control
0x180040b05  cmp     rax, r13
0x180040b08  jz      short loc_180040B45
0x180040b0a  test    byte ptr [rax+1Ch], 8
0x180040b0e  jz      short loc_180040B45
0x180040b10  cmp     byte ptr [rax+19h], 2
0x180040b14  jb      short loc_180040B45
0x180040b16  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180040b1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180040b22  mov     edx, 11h
0x180040b27  mov     r9d, eax
0x180040b2a  mov     [rsp+0D8h+var_B8], 80004005h
0x180040b32  mov     r8, r12
0x180040b35  mov     rcx, [rcx+10h]
0x180040b39  call    WPP_SF_Dd
0x180040b3e  mov     rax, cs:WPP_GLOBAL_Control
0x180040b45  mov     edi, 80004005h
0x180040b4a  jmp     short loc_180040B56
0x180040b4c  mov     edi, [rbp+8]
0x180040b4f  mov     rax, cs:WPP_GLOBAL_Control
0x180040b56  cmp     rax, r13
0x180040b59  jz      short loc_180040B92
0x180040b5b  test    byte ptr [rax+1Ch], 1
0x180040b5f  jz      short loc_180040B92
0x180040b61  cmp     byte ptr [rax+19h], 4
0x180040b65  jb      short loc_180040B92
0x180040b67  mov     ebx, [rbp+0Ch]
0x180040b6a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180040b6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180040b76  mov     edx, 12h
0x180040b7b  mov     dword ptr [rsp+0D8h+var_B0], ebx
0x180040b7f  mov     r9d, eax
0x180040b82  mov     r8, r12
0x180040b85  mov     [rsp+0D8h+var_B8], edi
0x180040b89  mov     rcx, [rcx+10h]
0x180040b8d  call    WPP_SF_DLD
0x180040b92  test    rsi, rsi
0x180040b95  jz      short loc_180040B9F
0x180040b97  mov     rcx, rsi; this
0x180040b9a  call    ?CancelSetupWorkspace@CWorkspaceManager@@QEAAXXZ; CWorkspaceManager::CancelSetupWorkspace(void)
0x180040b9f  test    r14, r14
0x180040ba2  jz      short loc_180040BAF
0x180040ba4  mov     rdx, r14; uIDEvent
0x180040ba7  xor     ecx, ecx; hWnd
0x180040ba9  call    cs:__imp_KillTimer
0x180040baf  mov     dword ptr [rbp+14h], 0
0x180040bb6  mov     eax, edi
0x180040bb8  add     rsp, 0A0h
0x180040bbf  pop     r14
0x180040bc1  pop     r13
0x180040bc3  pop     r12
0x180040bc5  pop     rdi
0x180040bc6  pop     rsi
0x180040bc7  pop     rbp
0x180040bc8  pop     rbx
0x180040bc9  retn
```
