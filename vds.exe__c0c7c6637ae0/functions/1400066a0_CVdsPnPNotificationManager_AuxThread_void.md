# CVdsPnPNotificationManager::AuxThread(void *)

- ea: `0x1400066a0`
- end: `0x1400069e1`
- name: `?AuxThread@CVdsPnPNotificationManager@@CAKPEAX@Z`
- size: `833`
- prototype: `__int64 __fastcall(CVdsPnPNotificationManager *Parameter)`
- caller_count: `0`
- callee_count: `9`
- tags: `reparse_path, loader_planting, service_task`

## callees

- `0x1400066a0`
- `0x1400069e8`
- `0x140006a80`
- `0x14000cd7c`
- `0x14000fd1c`
- `0x14001b14c`
- `0x14003cb10`
- `0x14004fd50`
- `0x140052e80`

## import_xrefs

- `USER32!PeekMessageW` at `0x140006734`
- `USER32!PeekMessageW` at `0x140006734`
- `USER32!GetMessageW` at `0x14000674d`
- `USER32!GetMessageW` at `0x14000674d`
- `USER32!PostThreadMessageW` at `0x1400068ac`
- `USER32!PostThreadMessageW` at `0x1400068ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006971`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006971`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006805`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006805`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14000688a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14000688a`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x1400067fb`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x1400067fb`
- `vdsutil!VdsHeapFree` at `0x140006981`
- `vdsutil!VdsHeapFree` at `0x140006981`
- `vdsutil!VdsTraceEx` at `0x1400067e7`
- `vdsutil!VdsTraceEx` at `0x1400068cc`
- `vdsutil!VdsTraceEx` at `0x1400068e8`
- `vdsutil!VdsTraceEx` at `0x1400069d5`
- `vdsutil!VdsTraceEx` at `0x1400067e7`
- `vdsutil!VdsTraceEx` at `0x1400068cc`
- `vdsutil!VdsTraceEx` at `0x1400068e8`
- `vdsutil!VdsTraceEx` at `0x1400069d5`
- `vdsutil!AcquireRundownProtection` at `0x14000670e`
- `vdsutil!AcquireRundownProtection` at `0x14000670e`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140006700`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140006945`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140006700`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140006945`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000682f`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000695a`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000682f`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000695a`
- `vdsutil!ReleaseRundownProtection` at `0x140006823`
- `vdsutil!ReleaseRundownProtection` at `0x140006823`

## string_xrefs

- `0x1400066ef`: `CVdsPnPNotificationManager::AuxThread()`
- `0x1400068d7`: `CVdsPnPNotificationManager::AuxThread, 1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVdsPnPNotificationManager::AuxThread(CVdsPnPNotificationManager *Parameter)
{
  int MessageW; // esi
  __int64 v3; // rcx
  const wchar_t *v4; // rdx
  __int64 v5; // r9
  unsigned __int16 *v6; // r8
  wchar_t v7; // ax
  unsigned __int16 *v8; // rcx
  WPARAM wParam_low; // rdi
  DWORD LastError; // eax
  int VolumeId; // eax
  LPARAM v13; // r9
  struct _DEV_BROADCAST_HANDLE *lParam; // rbx
  HANDLE ProcessHeap; // rax
  int v16; // [rsp+30h] [rbp-D0h] BYREF
  tagMSG Msg; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v18[16]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v19[16]; // [rsp+78h] [rbp-88h] BYREF
  struct _GUID v20; // [rsp+88h] [rbp-78h] BYREF
  WCHAR DeviceName; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 v22[14]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR TargetPath[266]; // [rsp+BCh] [rbp-44h] BYREF

  memset(&Msg, 0, sizeof(Msg));
  v20 = 0;
  v16 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v18, 0x5Eu, "CVdsPnPNotificationManager::AuxThread()");
  if ( !(unsigned __int8)AcquireRundownProtection(&g_RundownRef) )
  {
    VdsTraceEx(94, 3, "CVdsPnPNotificationManager::AuxThread, 1");
    goto LABEL_16;
  }
  PeekMessageW(&Msg, 0, 0x400u, 0x400u, 0);
  do
  {
    MessageW = GetMessageW(&Msg, 0, 0, 0);
    if ( MessageW == -1 )
      continue;
    switch ( Msg.message )
    {
      case 0x401u:
        v3 = 2147483646;
        v4 = L"\\\\?\\GLOBALROOT";
        v5 = 274;
        v6 = v22;
        do
        {
          if ( !v3 )
            break;
          v7 = *v4;
          if ( !*v4 )
            break;
          ++v4;
          *v6++ = v7;
          --v3;
          --v5;
        }
        while ( v5 );
        v8 = v6 - 1;
        if ( v5 )
          v8 = v6;
        *v8 = 0;
        wParam_low = LOWORD(Msg.wParam);
        StringCchPrintfW(&DeviceName, 3u, L"%c:", LOWORD(Msg.wParam));
        VdsTraceEx(94, 2, "VDS(0X02040011): Drive letter arrives: %c", (unsigned int)wParam_low);
        if ( QueryDosDeviceW(&DeviceName, TargetPath, 0x104u) )
        {
          VolumeId = CVdsService::GetVolumeId(v22, &v20, &v16);
          if ( VolumeId < 0 )
          {
            VdsTraceEx(94, 1, "VDS(0X02040012): failed to get volume id for %S", &DeviceName);
          }
          else if ( VolumeId || v16 != 1 )
          {
            if ( Msg.lParam <= 600 )
            {
              Sleep(0x1F4u);
              v13 = Msg.lParam++;
              PostThreadMessageW(CVdsPnPNotificationManager::m_dwAuxThreadId, 0x401u, wParam_low, v13);
            }
          }
          else
          {
            CVdsService::SendDriveLetterNotification(0xCAu, wParam_low, &v20);
          }
        }
        else
        {
          LastError = GetLastError();
          if ( LastError != 2 )
            VdsTraceEx(94, 0, "VDS(0X02040013): QueryDosDevice failed(%S): %X", &DeviceName, LastError);
        }
        break;
      case 0x402u:
      case 0x403u:
        CVdsPnPNotificationManager::LabelMountPointsNotificationHandler(Parameter, Msg.message, (void *)Msg.lParam);
        break;
      case 0x404u:
        CVdsPnPNotificationManager::DiskNotificationHandler(0, Msg.wParam, Msg.lParam);
        goto LABEL_31;
      case 0x405u:
        lParam = (struct _DEV_BROADCAST_HANDLE *)Msg.lParam;
        CVdsCallTracer::CVdsCallTracer(
          (CVdsCallTracer *)v19,
          0x5Eu,
          "CVdsPnPNotificationManager::LayoutChangeNotificationHandler()");
        CVdsService::OnDiskLayoutChange(lParam);
        CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v19);
LABEL_31:
        ProcessHeap = GetProcessHeap();
        VdsHeapFree(ProcessHeap, 0, Msg.lParam);
        break;
      case 0x406u:
        CVdsPnPNotificationManager::VolumeChangeNotificationHandler(Parameter, (void *)Msg.lParam);
        break;
    }
  }
  while ( MessageW );
  ReleaseRundownProtection(&g_RundownRef);
LABEL_16:
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v18);
  return 0;
}

```

## disassembly

```asm
0x1400066a0  mov     [rsp-8+arg_8], rbx
0x1400066a5  mov     [rsp-8+arg_10], rsi
0x1400066aa  push    rbp
0x1400066ab  push    rdi
0x1400066ac  push    r14
0x1400066ae  lea     rbp, [rsp-1E0h]
0x1400066b6  sub     rsp, 2E0h
0x1400066bd  mov     rax, cs:__security_cookie
0x1400066c4  xor     rax, rsp
0x1400066c7  mov     [rbp+1F0h+var_20], rax
0x1400066ce  mov     r14, rcx
0x1400066d1  xorps   xmm0, xmm0
0x1400066d4  movups  xmmword ptr [rsp+2F0h+Msg.hwnd], xmm0
0x1400066d9  movups  xmmword ptr [rsp+2F0h+Msg.wParam], xmm0
0x1400066de  movups  xmmword ptr [rsp+2F0h+Msg.time], xmm0
0x1400066e3  movups  xmmword ptr [rbp+1F0h+var_268.Data1], xmm0
0x1400066e7  mov     [rsp+2F0h+var_2C0], 0
0x1400066ef  lea     r8, aCvdspnpnotific_35; "CVdsPnPNotificationManager::AuxThread()"
0x1400066f6  mov     edx, 5Eh ; '^'
0x1400066fb  lea     rcx, [rsp+2F0h+var_288]
0x140006700  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140006706  nop
0x140006707  lea     rcx, ?g_RundownRef@@3U_RUNDOWN_REF@@A; _RUNDOWN_REF g_RundownRef
0x14000670e  call    cs:__imp_AcquireRundownProtection
0x140006714  test    al, al
0x140006716  jz      loc_1400068D7
0x14000671c  mov     [rsp+2F0h+wRemoveMsg], 0; wRemoveMsg
0x140006724  xor     edx, edx; hWnd
0x140006726  mov     r9d, 400h; wMsgFilterMax
0x14000672c  mov     r8d, r9d; wMsgFilterMin
0x14000672f  lea     rcx, [rsp+2F0h+Msg]; lpMsg
0x140006734  call    cs:__imp_PeekMessageW
0x14000673a  nop     word ptr [rax+rax+00h]
0x140006740  xor     r9d, r9d; wMsgFilterMax
0x140006743  xor     r8d, r8d; wMsgFilterMin
0x140006746  xor     edx, edx; hWnd
0x140006748  lea     rcx, [rsp+2F0h+Msg]; lpMsg
0x14000674d  call    cs:__imp_GetMessageW
0x140006753  mov     esi, eax
0x140006755  cmp     eax, 0FFFFFFFFh
0x140006758  jz      loc_140006814
0x14000675e  mov     edx, [rsp+2F0h+Msg.message]; unsigned int
0x140006762  cmp     edx, 401h
0x140006768  jnz     loc_1400068F3
0x14000676e  mov     ecx, 7FFFFFFEh
0x140006773  lea     rdx, aGlobalroot; "\\\\?\\GLOBALROOT"
0x14000677a  mov     r9d, 112h
0x140006780  lea     r8, [rbp+1F0h+var_250]
0x140006784  test    rcx, rcx
0x140006787  jz      short loc_1400067A6
0x140006789  movzx   eax, word ptr [rdx]
0x14000678c  test    ax, ax
0x14000678f  jz      short loc_1400067A6
0x140006791  add     rdx, 2
0x140006795  mov     [r8], ax
0x140006799  add     r8, 2
0x14000679d  dec     rcx
0x1400067a0  sub     r9, 1
0x1400067a4  jnz     short loc_140006784
0x1400067a6  lea     rcx, [r8-2]
0x1400067aa  test    r9, r9
0x1400067ad  cmovnz  rcx, r8
0x1400067b1  xor     eax, eax
0x1400067b3  mov     [rcx], ax
0x1400067b6  movzx   edi, word ptr [rsp+2F0h+Msg.wParam]
0x1400067bb  mov     r9d, edi
0x1400067be  lea     r8, aC; "%c:"
0x1400067c5  mov     edx, 3; unsigned __int64
0x1400067ca  lea     rcx, [rbp+1F0h+DeviceName]; unsigned __int16 *
0x1400067ce  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400067d3  mov     r9d, edi
0x1400067d6  lea     r8, aVds0x02040011D; "VDS(0X02040011): Drive letter arrives: "...
0x1400067dd  mov     edx, 2
0x1400067e2  mov     ecx, 5Eh ; '^'
0x1400067e7  call    cs:__imp_VdsTraceEx
0x1400067ed  mov     r8d, 104h; ucchMax
0x1400067f3  lea     rdx, [rbp+1F0h+TargetPath]; lpTargetPath
0x1400067f7  lea     rcx, [rbp+1F0h+DeviceName]; lpDeviceName
0x1400067fb  call    cs:__imp_QueryDosDeviceW
0x140006801  test    eax, eax
0x140006803  jnz     short loc_14000685E
0x140006805  call    cs:__imp_GetLastError
0x14000680b  cmp     eax, 2
0x14000680e  jnz     loc_1400069BF
0x140006814  test    esi, esi
0x140006816  jnz     loc_140006740
0x14000681c  lea     rcx, ?g_RundownRef@@3U_RUNDOWN_REF@@A; _RUNDOWN_REF g_RundownRef
0x140006823  call    cs:__imp_ReleaseRundownProtection
0x140006829  nop
0x14000682a  lea     rcx, [rsp+2F0h+var_288]
0x14000682f  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140006835  xor     eax, eax
0x140006837  mov     rcx, [rbp+1F0h+var_20]
0x14000683e  xor     rcx, rsp; StackCookie
0x140006841  call    __security_check_cookie
0x140006846  lea     r11, [rsp+2F0h+var_10]
0x14000684e  mov     rbx, [r11+28h]
0x140006852  mov     rsi, [r11+30h]
0x140006856  mov     rsp, r11
0x140006859  pop     r14
0x14000685b  pop     rdi
0x14000685c  pop     rbp
0x14000685d  retn
0x14000685e  lea     r8, [rsp+2F0h+var_2C0]; int *
0x140006863  lea     rdx, [rbp+1F0h+var_268]; struct _GUID *
0x140006867  lea     rcx, [rbp+1F0h+var_250]; unsigned __int16 *
0x14000686b  call    ?GetVolumeId@CVdsService@@SAJPEAGPEAU_GUID@@PEAH@Z; CVdsService::GetVolumeId(ushort *,_GUID *,int *)
0x140006870  test    eax, eax
0x140006872  js      short loc_1400068B7
0x140006874  jz      loc_14000699E
0x14000687a  cmp     [rsp+2F0h+Msg.lParam], 258h
0x140006883  jg      short loc_140006814
0x140006885  mov     ecx, 1F4h; dwMilliseconds
0x14000688a  call    cs:__imp_Sleep
0x140006890  mov     r9, [rsp+2F0h+Msg.lParam]; lParam
0x140006895  lea     rax, [r9+1]
0x140006899  mov     [rsp+2F0h+Msg.lParam], rax
0x14000689e  mov     r8, rdi; wParam
0x1400068a1  mov     edx, 401h; Msg
0x1400068a6  mov     ecx, cs:?m_dwAuxThreadId@CVdsPnPNotificationManager@@0KA; idThread
0x1400068ac  call    cs:__imp_PostThreadMessageW
0x1400068b2  jmp     loc_140006814
0x1400068b7  lea     r9, [rbp+1F0h+DeviceName]
0x1400068bb  lea     r8, aVds0x02040012F; "VDS(0X02040012): failed to get volume i"...
0x1400068c2  mov     edx, 1
0x1400068c7  mov     ecx, 5Eh ; '^'
0x1400068cc  call    cs:__imp_VdsTraceEx
0x1400068d2  jmp     loc_140006814
0x1400068d7  lea     r8, aCvdspnpnotific_14; "CVdsPnPNotificationManager::AuxThread, "...
0x1400068de  mov     edx, 3
0x1400068e3  mov     ecx, 5Eh ; '^'
0x1400068e8  call    cs:__imp_VdsTraceEx
0x1400068ee  jmp     loc_14000682A
0x1400068f3  mov     ecx, edx
0x1400068f5  sub     ecx, 402h
0x1400068fb  jz      loc_14000698C
0x140006901  sub     ecx, 1
0x140006904  jz      loc_14000698C
0x14000690a  sub     ecx, 1; this
0x14000690d  jz      short loc_140006962
0x14000690f  sub     ecx, 1
0x140006912  jz      short loc_14000692F
0x140006914  cmp     ecx, 1
0x140006917  jnz     loc_140006814
0x14000691d  mov     rdx, [rsp+2F0h+Msg.lParam]; void *
0x140006922  mov     rcx, r14; this
0x140006925  call    ?VolumeChangeNotificationHandler@CVdsPnPNotificationManager@@AEAAXPEAX@Z; CVdsPnPNotificationManager::VolumeChangeNotificationHandler(void *)
0x14000692a  jmp     loc_140006814
0x14000692f  mov     rbx, [rsp+2F0h+Msg.lParam]
0x140006934  lea     r8, aCvdspnpnotific_16; "CVdsPnPNotificationManager::LayoutChang"...
0x14000693b  mov     edx, 5Eh ; '^'
0x140006940  lea     rcx, [rsp+2F0h+var_278]
0x140006945  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14000694b  nop
0x14000694c  mov     rcx, rbx; struct _DEV_BROADCAST_HANDLE *
0x14000694f  call    ?OnDiskLayoutChange@CVdsService@@SAXPEAU_DEV_BROADCAST_HANDLE@@@Z; CVdsService::OnDiskLayoutChange(_DEV_BROADCAST_HANDLE *)
0x140006954  nop
0x140006955  lea     rcx, [rsp+2F0h+var_278]
0x14000695a  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140006960  jmp     short loc_140006971
0x140006962  mov     r8, [rsp+2F0h+Msg.lParam]; __int64
0x140006967  mov     rdx, [rsp+2F0h+Msg.wParam]; unsigned __int64
0x14000696c  call    ?DiskNotificationHandler@CVdsPnPNotificationManager@@AEAAX_K_J@Z; CVdsPnPNotificationManager::DiskNotificationHandler(unsigned __int64,__int64)
0x140006971  call    cs:__imp_GetProcessHeap
0x140006977  mov     rcx, rax
0x14000697a  mov     r8, [rsp+2F0h+Msg.lParam]
0x14000697f  xor     edx, edx
0x140006981  call    cs:__imp_VdsHeapFree
0x140006987  jmp     loc_140006814
0x14000698c  mov     r8, [rsp+2F0h+Msg.lParam]; void *
0x140006991  mov     rcx, r14; this
0x140006994  call    ?LabelMountPointsNotificationHandler@CVdsPnPNotificationManager@@AEAAXIPEAX@Z; CVdsPnPNotificationManager::LabelMountPointsNotificationHandler(uint,void *)
0x140006999  jmp     loc_140006814
0x14000699e  cmp     [rsp+2F0h+var_2C0], 1
0x1400069a3  jnz     loc_14000687A
0x1400069a9  lea     r8, [rbp+1F0h+var_268]; struct _GUID *
0x1400069ad  movzx   edx, di; unsigned __int16
0x1400069b0  mov     ecx, 0CAh; unsigned int
0x1400069b5  call    ?SendDriveLetterNotification@CVdsService@@SAXKGAEAU_GUID@@@Z; CVdsService::SendDriveLetterNotification(ulong,ushort,_GUID &)
0x1400069ba  jmp     loc_140006814
0x1400069bf  mov     [rsp+2F0h+wRemoveMsg], eax
0x1400069c3  lea     r9, [rbp+1F0h+DeviceName]
0x1400069c7  lea     r8, aVds0x02040013Q; "VDS(0X02040013): QueryDosDevice failed("...
0x1400069ce  xor     edx, edx
0x1400069d0  mov     ecx, 5Eh ; '^'
0x1400069d5  call    cs:__imp_VdsTraceEx
0x1400069db  jmp     loc_140006814
```
