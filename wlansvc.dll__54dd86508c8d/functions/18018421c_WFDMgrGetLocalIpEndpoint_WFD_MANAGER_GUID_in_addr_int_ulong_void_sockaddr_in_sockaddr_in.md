# WFDMgrGetLocalIpEndpoint(_WFD_MANAGER *,_GUID *,in_addr *,int,ulong,void *,sockaddr_in *,sockaddr_in *)

- ea: `0x18018421c`
- end: `0x18018485f`
- name: `?WFDMgrGetLocalIpEndpoint@@YAKPEAU_WFD_MANAGER@@PEAU_GUID@@PEAUin_addr@@HKPEAXPEAUsockaddr_in@@4@Z`
- size: `1603`
- prototype: `unsigned int(struct _WFD_MANAGER *, struct _GUID *, struct in_addr *, int, unsigned int, void *, struct sockaddr_in *, struct sockaddr_in *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180184a84`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x180106340`
- `0x180183dac`
- `0x18018421c`
- `0x180188cf8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801842e6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801842e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801842f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801844b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180184684`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801842f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801844b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180184684`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180184721`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180184721`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18018472a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18018472a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1801844a6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1801844a6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18018455f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180184715`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18018455f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180184715`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180184800`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180184800`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18018458e`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18018458e`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x18018434c`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x18018434c`
- `IPHLPAPI!NotifyUnicastIpAddressChange` at `0x1801843e9`
- `IPHLPAPI!NotifyUnicastIpAddressChange` at `0x1801843e9`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x1801847b7`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x1801847b7`

## pseudocode

```c
__int64 __fastcall WFDMgrGetLocalIpEndpoint(
        HANDLE *a1,
        struct _GUID *a2,
        struct in_addr *a3,
        unsigned int a4,
        unsigned int a5,
        void *a6,
        struct sockaddr_in *a7,
        struct sockaddr_in *a8)
{
  DWORD LastError; // eax
  unsigned int v13; // ebx
  PVOID *v14; // rcx
  __int64 v15; // rdx
  struct _TP_TIMER *v16; // rdi
  unsigned int v17; // eax
  DWORD v18; // eax
  DWORD v19; // eax
  __int64 v20; // rdx
  DWORD v21; // eax
  unsigned int v22; // eax
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp-59h] BYREF
  HANDLE NotificationHandle; // [rsp+38h] [rbp-51h] BYREF
  __int128 CallerContext; // [rsp+40h] [rbp-49h] BYREF
  NET_LUID InterfaceLuid[2]; // [rsp+50h] [rbp-39h] BYREF
  HANDLE hObject[2]; // [rsp+60h] [rbp-29h]
  HANDLE Handles[2]; // [rsp+70h] [rbp-19h] BYREF
  HANDLE v30; // [rsp+80h] [rbp-9h]

  CallerContext = 0;
  v30 = 0;
  *(_OWORD *)&InterfaceLuid[0].Value = 0;
  pftDueTime = 0;
  *(_OWORD *)hObject = 0;
  *(_OWORD *)Handles = 0;
  NotificationHandle = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 1336, &WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids);
  }
  *(_QWORD *)&CallerContext = a3;
  *a7 = 0;
  *((_QWORD *)&CallerContext + 1) = a7;
  InterfaceLuid[0].Value = (ULONG64)a8;
  hObject[1] = (HANDLE)__PAIR64__(a5, a4);
  *a8 = 0;
  hObject[0] = CreateEventW(0, 1, 0, 0);
  if ( !hObject[0] )
  {
    LastError = GetLastError();
    v13 = LastError;
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105)
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      v15 = 1337;
LABEL_10:
      WPP_SF_d(v14[12], v15, &WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids, LastError);
LABEL_81:
      v14 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_82;
    }
    goto LABEL_82;
  }
  LastError = ConvertInterfaceGuidToLuid(a2, &InterfaceLuid[1]);
  v13 = LastError;
  if ( LastError )
  {
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105)
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      v15 = 1338;
      goto LABEL_10;
    }
LABEL_82:
    if ( !a4 )
      goto LABEL_94;
    goto LABEL_83;
  }
  v16 = 0;
  if ( a4 )
  {
    if ( !(unsigned int)WFDMgrIsDhcpReady((struct _WFDMGR_INTERFACE_CHANGE_CALLBACK_CONTEXT *)&CallerContext)
      || WFDMgrGetIpAddrOnInitialNotification((struct _WFDMGR_INTERFACE_CHANGE_CALLBACK_CONTEXT *)&CallerContext) )
    {
      v16 = CreateThreadpoolTimer(WFDMgrGetIpAddrTimerCallback, &CallerContext, 0);
      if ( !v16 )
      {
        v18 = GetLastError();
        v13 = v18;
        v14 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 105)
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 1342, &WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids, v18);
          v14 = (PVOID *)WPP_GLOBAL_Control;
        }
LABEL_83:
        if ( v13 == 1460 )
        {
          if ( v14 != &WPP_GLOBAL_Control && *((_BYTE *)v14 + 105) >= 3u && (*((_BYTE *)v14 + 108) & 1) != 0 )
            WPP_SF_(v14[12], 1350, &WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids);
          if ( WFDMgrGetIpAddrOnInitialNotification((struct _WFDMGR_INTERFACE_CHANGE_CALLBACK_CONTEXT *)&CallerContext) )
            goto LABEL_93;
          v13 = 0;
          v14 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 2u
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 1351, &WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids);
LABEL_93:
            v14 = (PVOID *)WPP_GLOBAL_Control;
          }
        }
LABEL_94:
        if ( NotificationHandle )
        {
          v22 = CancelMibChangeNotify2(NotificationHandle);
          v14 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 105)
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 1352, &WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids, v22);
            v14 = (PVOID *)WPP_GLOBAL_Control;
          }
        }
        goto LABEL_99;
      }
      pftDueTime.dwHighDateTime = -1;
      pftDueTime.dwLowDateTime = -1000000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 1343, &WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids, 100);
      }
      SetThreadpoolTimer(v16, &pftDueTime, 0x64u, 0);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u
           && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 1341, &WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids);
    }
LABEL_43:
    Handles[0] = a1[1];
    Handles[1] = a6;
    v30 = hObject[0];
    v19 = WaitForMultipleObjects(3u, Handles, 0, 0x7530u);
    if ( v19 )
    {
      if ( v19 != 1 )
      {
        if ( v19 == 2 )
        {
          v14 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 105)
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 1346, &WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids);
            v14 = (PVOID *)WPP_GLOBAL_Control;
          }
          v13 = 0;
        }
        else if ( v19 == 258 )
        {
          v14 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 105)
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 1347, &WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids);
            v14 = (PVOID *)WPP_GLOBAL_Control;
          }
          v13 = 1460;
        }
        else
        {
          if ( v19 == -1 )
          {
            v21 = GetLastError();
            v13 = v21;
            v14 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 105)
              && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 12),
                1348,
                &WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids,
                v21);
              v14 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v13 )
              goto LABEL_79;
          }
          else
          {
            v14 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 105)
              && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 12),
                1349,
                &WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids,
                v19);
              v14 = (PVOID *)WPP_GLOBAL_Control;
            }
          }
          v13 = 774;
        }
LABEL_79:
        if ( !v16 )
          goto LABEL_82;
        SetThreadpoolTimer(v16, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(v16, 1);
        CloseThreadpoolTimer(v16);
        goto LABEL_81;
      }
      v14 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || !*((_BYTE *)WPP_GLOBAL_Control + 105)
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      {
LABEL_54:
        v13 = 1223;
        goto LABEL_79;
      }
      v20 = 1345;
    }
    else
    {
      v14 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || !*((_BYTE *)WPP_GLOBAL_Control + 105)
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      {
        goto LABEL_54;
      }
      v20 = 1344;
    }
    WPP_SF_(v14[12], v20, &WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids);
    v14 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_54;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 1339, &WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids);
  }
  v17 = NotifyUnicastIpAddressChange(2u, WFDMgrInterfaceChangeCallback, &CallerContext, 1u, &NotificationHandle);
  v13 = v17;
  if ( !v17 )
    goto LABEL_43;
  v14 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105)
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 1340, &WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids, v17);
    v14 = (PVOID *)WPP_GLOBAL_Control;
  }
  NotificationHandle = 0;
LABEL_99:
  if ( hObject[0] )
  {
    CloseHandle(hObject[0]);
    v14 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v14 != &WPP_GLOBAL_Control && *((_BYTE *)v14 + 105) >= 4u && (*((_BYTE *)v14 + 108) & 1) != 0 )
    WPP_SF_d(v14[12], 1353, &WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids, v13);
  return v13;
}

```

## disassembly

```asm
0x18018421c  mov     [rsp-8+arg_0], rbx
0x180184221  push    rbp
0x180184222  push    rsi
0x180184223  push    rdi
0x180184224  push    r12
0x180184226  push    r13
0x180184228  push    r14
0x18018422a  push    r15
0x18018422c  lea     rbp, [rsp-7]
0x180184231  sub     rsp, 90h
0x180184238  mov     rax, cs:__security_cookie
0x18018423f  xor     rax, rsp
0x180184242  mov     [rbp+37h+var_38], rax
0x180184246  mov     rdi, [rbp+37h+arg_30]
0x18018424a  xorps   xmm0, xmm0
0x18018424d  mov     rsi, [rbp+37h+arg_38]
0x180184251  xor     eax, eax
0x180184253  movups  [rbp+37h+CallerContext], xmm0
0x180184257  mov     [rbp+37h+var_40], rax
0x18018425b  mov     r12d, r9d
0x18018425e  movups  xmmword ptr [rbp+37h+InterfaceLuid], xmm0
0x180184262  mov     qword ptr [rbp+37h+pftDueTime.dwLowDateTime], rax
0x180184266  mov     r14, r8
0x180184269  movups  xmmword ptr [rbp+37h+hObject], xmm0
0x18018426d  mov     rbx, rdx
0x180184270  mov     r15, rcx
0x180184273  movups  xmmword ptr [rbp+37h+Handles], xmm0
0x180184277  mov     [rbp+37h+var_88], 0
0x18018427f  mov     rcx, cs:WPP_GLOBAL_Control
0x180184286  lea     rax, WPP_GLOBAL_Control
0x18018428d  mov     r13d, 1
0x180184293  cmp     rcx, rax
0x180184296  jz      short loc_1801842B9
0x180184298  cmp     byte ptr [rcx+69h], 4
0x18018429c  jb      short loc_1801842B9
0x18018429e  test    [rcx+6Ch], r13b
0x1801842a2  jz      short loc_1801842B9
0x1801842a4  mov     rcx, [rcx+60h]
0x1801842a8  lea     r8, WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids
0x1801842af  mov     edx, 538h
0x1801842b4  call    WPP_SF_
0x1801842b9  mov     eax, [rbp+37h+arg_20]
0x1801842bc  xorps   xmm0, xmm0
0x1801842bf  xorps   xmm1, xmm1
0x1801842c2  mov     qword ptr [rbp+37h+CallerContext], r14
0x1801842c6  movups  xmmword ptr [rdi], xmm0
0x1801842c9  xor     r9d, r9d; lpName
0x1801842cc  mov     qword ptr [rbp+37h+CallerContext+8], rdi
0x1801842d0  xor     r8d, r8d; bInitialState
0x1801842d3  mov     qword ptr [rbp+37h+InterfaceLuid], rsi
0x1801842d7  mov     edx, r13d; bManualReset
0x1801842da  mov     dword ptr [rbp+37h+hObject+8], r12d
0x1801842de  xor     ecx, ecx; lpEventAttributes
0x1801842e0  mov     dword ptr [rbp+37h+hObject+0Ch], eax
0x1801842e3  movups  xmmword ptr [rsi], xmm1
0x1801842e6  call    cs:__imp_CreateEventW
0x1801842ec  mov     [rbp+37h+hObject], rax
0x1801842f0  test    rax, rax
0x1801842f3  jnz     short loc_180184345
0x1801842f5  call    cs:__imp_GetLastError
0x1801842fb  mov     ebx, eax
0x1801842fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180184304  lea     rsi, WPP_GLOBAL_Control
0x18018430b  cmp     rcx, rsi
0x18018430e  jz      loc_180184737
0x180184314  cmp     [rcx+69h], r13b
0x180184318  jb      loc_180184737
0x18018431e  test    [rcx+6Ch], r13b
0x180184322  jz      loc_180184737
0x180184328  mov     edx, 539h
0x18018432d  mov     rcx, [rcx+60h]
0x180184331  lea     r8, WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids
0x180184338  mov     r9d, eax
0x18018433b  call    WPP_SF_d
0x180184340  jmp     loc_180184730
0x180184345  lea     rdx, [rbp+37h+InterfaceLuid+8]; InterfaceLuid
0x180184349  mov     rcx, rbx; InterfaceGuid
0x18018434c  call    cs:__imp_ConvertInterfaceGuidToLuid
0x180184352  mov     ebx, eax
0x180184354  test    eax, eax
0x180184356  jz      short loc_18018438A
0x180184358  mov     rcx, cs:WPP_GLOBAL_Control
0x18018435f  lea     rsi, WPP_GLOBAL_Control
0x180184366  cmp     rcx, rsi
0x180184369  jz      loc_180184737
0x18018436f  cmp     [rcx+69h], r13b
0x180184373  jb      loc_180184737
0x180184379  test    [rcx+6Ch], r13b
0x18018437d  jz      loc_180184737
0x180184383  mov     edx, 53Ah
0x180184388  jmp     short loc_18018432D
0x18018438a  xor     edi, edi
0x18018438c  or      r14d, 0FFFFFFFFh
0x180184390  test    r12d, r12d
0x180184393  jnz     loc_180184439
0x180184399  mov     rcx, cs:WPP_GLOBAL_Control
0x1801843a0  lea     rsi, WPP_GLOBAL_Control
0x1801843a7  cmp     rcx, rsi
0x1801843aa  jz      short loc_1801843CD
0x1801843ac  cmp     byte ptr [rcx+69h], 3
0x1801843b0  jb      short loc_1801843CD
0x1801843b2  test    [rcx+6Ch], r13b
0x1801843b6  jz      short loc_1801843CD
0x1801843b8  mov     rcx, [rcx+60h]
0x1801843bc  lea     r8, WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids
0x1801843c3  mov     edx, 53Bh
0x1801843c8  call    WPP_SF_
0x1801843cd  lea     rax, [rbp+37h+var_88]
0x1801843d1  mov     ecx, 2; Family
0x1801843d6  mov     r9b, r13b; InitialNotification
0x1801843d9  mov     [rsp+0C0h+NotificationHandle], rax; NotificationHandle
0x1801843de  lea     r8, [rbp+37h+CallerContext]; CallerContext
0x1801843e2  lea     rdx, ?WFDMgrInterfaceChangeCallback@@YAXPEAXPEAU_MIB_UNICASTIPADDRESS_ROW@@W4_MIB_NOTIFICATION_TYPE@@@Z; Callback
0x1801843e9  call    cs:__imp_NotifyUnicastIpAddressChange
0x1801843ef  mov     ebx, eax
0x1801843f1  test    eax, eax
0x1801843f3  jz      loc_180184565
0x1801843f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180184400  cmp     rcx, rsi
0x180184403  jz      short loc_180184430
0x180184405  cmp     [rcx+69h], r13b
0x180184409  jb      short loc_180184430
0x18018440b  test    [rcx+6Ch], r13b
0x18018440f  jz      short loc_180184430
0x180184411  mov     rcx, [rcx+60h]
0x180184415  lea     r8, WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids
0x18018441c  mov     edx, 53Ch
0x180184421  mov     r9d, eax
0x180184424  call    WPP_SF_d
0x180184429  mov     rcx, cs:WPP_GLOBAL_Control
0x180184430  mov     [rbp+37h+var_88], rdi
0x180184434  jmp     loc_1801847F4
0x180184439  lea     rcx, [rbp+37h+CallerContext]; struct _WFDMGR_INTERFACE_CHANGE_CALLBACK_CONTEXT *
0x18018443d  call    ?WFDMgrIsDhcpReady@@YAHPEAU_WFDMGR_INTERFACE_CHANGE_CALLBACK_CONTEXT@@@Z; WFDMgrIsDhcpReady(_WFDMGR_INTERFACE_CHANGE_CALLBACK_CONTEXT *)
0x180184442  test    eax, eax
0x180184444  jz      short loc_180184498
0x180184446  lea     rcx, [rbp+37h+CallerContext]; struct _WFDMGR_INTERFACE_CHANGE_CALLBACK_CONTEXT *
0x18018444a  call    ?WFDMgrGetIpAddrOnInitialNotification@@YAKPEAU_WFDMGR_INTERFACE_CHANGE_CALLBACK_CONTEXT@@@Z; WFDMgrGetIpAddrOnInitialNotification(_WFDMGR_INTERFACE_CHANGE_CALLBACK_CONTEXT *)
0x18018444f  test    eax, eax
0x180184451  jnz     short loc_180184498
0x180184453  mov     rcx, cs:WPP_GLOBAL_Control
0x18018445a  lea     rsi, WPP_GLOBAL_Control
0x180184461  cmp     rcx, rsi
0x180184464  jz      loc_180184565
0x18018446a  cmp     byte ptr [rcx+69h], 3
0x18018446e  jb      loc_180184565
0x180184474  test    [rcx+6Ch], r13b
0x180184478  jz      loc_180184565
0x18018447e  mov     rcx, [rcx+60h]
0x180184482  lea     r8, WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids
0x180184489  mov     edx, 53Dh
0x18018448e  call    WPP_SF_
0x180184493  jmp     loc_180184565
0x180184498  xor     r8d, r8d; pcbe
0x18018449b  lea     rdx, [rbp+37h+CallerContext]; pv
0x18018449f  lea     rcx, ?WFDMgrGetIpAddrTimerCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1801844a6  call    cs:__imp_CreateThreadpoolTimer
0x1801844ac  mov     rdi, rax
0x1801844af  test    rax, rax
0x1801844b2  jnz     short loc_18018450B
0x1801844b4  call    cs:__imp_GetLastError
0x1801844ba  mov     ebx, eax
0x1801844bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1801844c3  lea     rsi, WPP_GLOBAL_Control
0x1801844ca  cmp     rcx, rsi
0x1801844cd  jz      loc_18018473C
0x1801844d3  cmp     [rcx+69h], r13b
0x1801844d7  jb      loc_18018473C
0x1801844dd  test    [rcx+6Ch], r13b
0x1801844e1  jz      loc_18018473C
0x1801844e7  mov     rcx, [rcx+60h]
0x1801844eb  lea     r8, WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids
0x1801844f2  mov     edx, 53Eh
0x1801844f7  mov     r9d, eax
0x1801844fa  call    WPP_SF_d
0x1801844ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180184506  jmp     loc_18018473C
0x18018450b  mov     [rbp+37h+pftDueTime.dwHighDateTime], r14d
0x18018450f  mov     [rbp+37h+pftDueTime.dwLowDateTime], 0FFF0BDC0h
0x180184516  mov     rcx, cs:WPP_GLOBAL_Control
0x18018451d  lea     rsi, WPP_GLOBAL_Control
0x180184524  mov     ebx, 64h ; 'd'
0x180184529  cmp     rcx, rsi
0x18018452c  jz      short loc_180184552
0x18018452e  cmp     byte ptr [rcx+69h], 3
0x180184532  jb      short loc_180184552
0x180184534  test    [rcx+6Ch], r13b
0x180184538  jz      short loc_180184552
0x18018453a  mov     rcx, [rcx+60h]
0x18018453e  lea     r8, WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids
0x180184545  mov     edx, 53Fh
0x18018454a  mov     r9d, ebx
0x18018454d  call    WPP_SF_d
0x180184552  xor     r9d, r9d; msWindowLength
0x180184555  lea     rdx, [rbp+37h+pftDueTime]; pftDueTime
0x180184559  mov     r8d, ebx; msPeriod
0x18018455c  mov     rcx, rdi; pti
0x18018455f  call    cs:__imp_SetThreadpoolTimer
0x180184565  mov     rax, [r15+8]
0x180184569  lea     rdx, [rbp+37h+Handles]; lpHandles
0x18018456d  mov     [rbp+37h+Handles], rax
0x180184571  xor     r8d, r8d; bWaitAll
0x180184574  mov     rax, [rbp+37h+arg_28]
0x180184578  mov     r9d, 7530h; dwMilliseconds
0x18018457e  mov     [rbp+37h+Handles+8], rax
0x180184582  mov     rax, [rbp+37h+hObject]
0x180184586  lea     ecx, [r8+3]; nCount
0x18018458a  mov     [rbp+37h+var_40], rax
0x18018458e  call    cs:__imp_WaitForMultipleObjects
0x180184594  test    eax, eax
0x180184596  jnz     short loc_1801845B7
0x180184598  mov     rcx, cs:WPP_GLOBAL_Control
0x18018459f  cmp     rcx, rsi
0x1801845a2  jz      short loc_1801845F0
0x1801845a4  cmp     [rcx+69h], r13b
0x1801845a8  jb      short loc_1801845F0
0x1801845aa  test    [rcx+6Ch], r13b
0x1801845ae  jz      short loc_1801845F0
0x1801845b0  mov     edx, 540h
0x1801845b5  jmp     short loc_1801845D9
0x1801845b7  cmp     eax, r13d
0x1801845ba  jnz     short loc_1801845FA
0x1801845bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1801845c3  cmp     rcx, rsi
0x1801845c6  jz      short loc_1801845F0
0x1801845c8  cmp     [rcx+69h], r13b
0x1801845cc  jb      short loc_1801845F0
0x1801845ce  test    [rcx+6Ch], r13b
0x1801845d2  jz      short loc_1801845F0
0x1801845d4  mov     edx, 541h
0x1801845d9  mov     rcx, [rcx+60h]
0x1801845dd  lea     r8, WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids
0x1801845e4  call    WPP_SF_
0x1801845e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1801845f0  mov     ebx, 4C7h
0x1801845f5  jmp     loc_180184705
0x1801845fa  cmp     eax, 2
0x1801845fd  jnz     short loc_18018463A
0x1801845ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180184606  cmp     rcx, rsi
0x180184609  jz      short loc_180184633
0x18018460b  cmp     [rcx+69h], r13b
0x18018460f  jb      short loc_180184633
0x180184611  test    [rcx+6Ch], r13b
0x180184615  jz      short loc_180184633
0x180184617  mov     rcx, [rcx+60h]
0x18018461b  lea     r8, WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids
0x180184622  mov     edx, 542h
0x180184627  call    WPP_SF_
0x18018462c  mov     rcx, cs:WPP_GLOBAL_Control
0x180184633  xor     ebx, ebx
0x180184635  jmp     loc_180184705
0x18018463a  cmp     eax, 102h
0x18018463f  jnz     short loc_18018467F
0x180184641  mov     rcx, cs:WPP_GLOBAL_Control
0x180184648  cmp     rcx, rsi
0x18018464b  jz      short loc_180184675
0x18018464d  cmp     [rcx+69h], r13b
0x180184651  jb      short loc_180184675
0x180184653  test    [rcx+6Ch], r13b
0x180184657  jz      short loc_180184675
0x180184659  mov     rcx, [rcx+60h]
0x18018465d  lea     r8, WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids
0x180184664  mov     edx, 543h
0x180184669  call    WPP_SF_
0x18018466e  mov     rcx, cs:WPP_GLOBAL_Control
0x180184675  mov     ebx, 5B4h
0x18018467a  jmp     loc_180184705
0x18018467f  cmp     eax, r14d
0x180184682  jnz     short loc_1801846C9
0x180184684  call    cs:__imp_GetLastError
0x18018468a  mov     ebx, eax
0x18018468c  mov     rcx, cs:WPP_GLOBAL_Control
0x180184693  cmp     rcx, rsi
0x180184696  jz      short loc_1801846C3
0x180184698  cmp     [rcx+69h], r13b
0x18018469c  jb      short loc_1801846C3
0x18018469e  test    [rcx+6Ch], r13b
0x1801846a2  jz      short loc_1801846C3
0x1801846a4  mov     rcx, [rcx+60h]
0x1801846a8  lea     r8, WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids
0x1801846af  mov     edx, 544h
0x1801846b4  mov     r9d, eax
0x1801846b7  call    WPP_SF_d
0x1801846bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1801846c3  test    ebx, ebx
0x1801846c5  jnz     short loc_180184705
0x1801846c7  jmp     short loc_180184700
0x1801846c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1801846d0  cmp     rcx, rsi
0x1801846d3  jz      short loc_180184700
0x1801846d5  cmp     [rcx+69h], r13b
0x1801846d9  jb      short loc_180184700
0x1801846db  test    [rcx+6Ch], r13b
0x1801846df  jz      short loc_180184700
0x1801846e1  mov     rcx, [rcx+60h]
0x1801846e5  lea     r8, WPP_770d2a6ca85f3f6f822445dd5e88f798_Traceguids
0x1801846ec  mov     edx, 545h
0x1801846f1  mov     r9d, eax
0x1801846f4  call    WPP_SF_d
  ... truncated ...
```
