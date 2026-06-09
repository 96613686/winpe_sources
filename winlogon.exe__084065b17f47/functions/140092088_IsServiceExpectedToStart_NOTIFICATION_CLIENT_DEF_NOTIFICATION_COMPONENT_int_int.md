# IsServiceExpectedToStart(_NOTIFICATION_CLIENT_DEF *,_NOTIFICATION_COMPONENT *,int *,int *)

- ea: `0x140092088`
- end: `0x140092444`
- name: `?IsServiceExpectedToStart@@YAKPEAU_NOTIFICATION_CLIENT_DEF@@PEAU_NOTIFICATION_COMPONENT@@PEAH2@Z`
- size: `956`
- prototype: `unsigned int __fastcall(struct _NOTIFICATION_CLIENT_DEF *, struct _NOTIFICATION_COMPONENT *, int *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140025d50`

## callees

- `0x14000faf8`
- `0x14000fb30`
- `0x140026970`
- `0x140053720`
- `0x140092088`
- `0x1400928ec`
- `0x140092acc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140092105`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400921a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400921de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140092257`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400923df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140092105`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400921a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400921de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140092257`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400923df`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400922a9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400922a9`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1400920ef`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1400920ef`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1400921a2`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x140092222`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1400921a2`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x140092222`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1400922c1`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1400922c1`

## pseudocode

```c
__int64 __fastcall IsServiceExpectedToStart(SC_HANDLE *a1, struct _NOTIFICATION_COMPONENT *a2, int *a3, int *a4)
{
  unsigned int v7; // edi
  SC_HANDLE v8; // rax
  LPCWSTR *v9; // rbx
  DWORD LastError; // r8d
  CUser *v11; // rcx
  int v12; // edx
  char v13; // al
  int v14; // edx
  struct _QUERY_SERVICE_CONFIGW *v15; // rax
  struct _QUERY_SERVICE_CONFIGW *v16; // r14
  DWORD pcbBytesNeeded; // [rsp+30h] [rbp-68h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+38h] [rbp-60h] BYREF

  v7 = -1;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  pcbBytesNeeded = 0;
  *a4 = 1;
  v8 = (SC_HANDLE)*((_QWORD *)a2 + 73);
  v9 = (LPCWSTR *)((char *)a2 + 576);
  if ( !v8 )
  {
    v8 = OpenServiceW(a1[4], *v9, 5u);
    *((_QWORD *)a2 + 73) = v8;
    if ( !v8 )
    {
      LastError = GetLastError();
      if ( LastError == 1060 )
      {
        v7 = 0;
        *a4 = 0;
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_c4e026e548883477c15208e9f0c6fcb8_Traceguids, *v9);
        }
        return v7;
      }
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
      {
        return v7;
      }
      v12 = 46;
LABEL_56:
      WPP_SF_Sl(
        *((_QWORD *)v11 + 2),
        v12,
        (unsigned int)WPP_c4e026e548883477c15208e9f0c6fcb8_Traceguids,
        (unsigned int)*v9,
        LastError);
      return v7;
    }
  }
  QueryServiceConfigW(v8, 0, 0, &pcbBytesNeeded);
  if ( GetLastError() != 122 )
  {
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
    {
      return v7;
    }
    v13 = GetLastError();
    v14 = 47;
    goto LABEL_17;
  }
  v15 = (struct _QUERY_SERVICE_CONFIGW *)NotifyAllocate(pcbBytesNeeded);
  v16 = v15;
  if ( !v15 )
    return v7;
  if ( !QueryServiceConfigW(*((SC_HANDLE *)a2 + 73), v15, pcbBytesNeeded, &pcbBytesNeeded) )
  {
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v7;
    }
    v13 = GetLastError();
    v14 = 48;
LABEL_17:
    WPP_SF_Sl(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v14,
      (unsigned int)WPP_c4e026e548883477c15208e9f0c6fcb8_Traceguids,
      (unsigned int)*v9,
      v13);
    return v7;
  }
  if ( v16->dwStartType == 2 )
  {
    *((_DWORD *)a2 + 148) = GetTickCount();
    if ( !QueryServiceStatus(*((SC_HANDLE *)a2 + 73), &ServiceStatus) )
    {
      LOBYTE(LastError) = GetLastError();
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
      {
        return v7;
      }
      v12 = 53;
      goto LABEL_56;
    }
    if ( ServiceStatus.dwCurrentState == 1 && ServiceStatus.dwWin32ExitCode == 1084 )
    {
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_Sll(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, 1084, (unsigned int)*v9, 1, 60);
      }
      v7 = 0;
      *a4 = 0;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinlogonNotifySubscriberRefactor>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WinlogonNotifySubscriberRefactor>::GetImpl'::`2'::impl) )
        *a3 = 1;
    }
    else if ( ServiceStatus.dwCurrentState == 3
           || ServiceStatus.dwCurrentState == 1 && ServiceStatus.dwWin32ExitCode != 1077 )
    {
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_Sll(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          51,
          (_DWORD)WPP_GLOBAL_Control,
          (unsigned int)*v9,
          ServiceStatus.dwCurrentState,
          ServiceStatus.dwWin32ExitCode);
      }
      v7 = 0;
      *a3 = 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_Sll(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          52,
          (_DWORD)WPP_GLOBAL_Control,
          (unsigned int)*v9,
          ServiceStatus.dwCurrentState,
          ServiceStatus.dwWin32ExitCode);
      }
      return 1;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_c4e026e548883477c15208e9f0c6fcb8_Traceguids, *v9);
    }
    return 0;
  }
  return v7;
}

```

## disassembly

```asm
0x140092088  push    rbx
0x14009208a  push    rsi
0x14009208b  push    rdi
0x14009208c  push    r12
0x14009208e  push    r13
0x140092090  push    r14
0x140092092  push    r15
0x140092094  sub     rsp, 60h
0x140092098  mov     rax, cs:__security_cookie
0x14009209f  xor     rax, rsp
0x1400920a2  mov     [rsp+98h+var_40], rax
0x1400920a7  mov     r15, r9
0x1400920aa  mov     r12, r8
0x1400920ad  mov     rsi, rdx
0x1400920b0  or      edi, 0FFFFFFFFh
0x1400920b3  xorps   xmm0, xmm0
0x1400920b6  xor     eax, eax
0x1400920b8  movups  xmmword ptr [rsp+98h+ServiceStatus.dwServiceType], xmm0
0x1400920bd  movups  xmmword ptr [rsp+98h+ServiceStatus.dwWin32ExitCode], xmm0
0x1400920c2  mov     [rsp+98h+pcbBytesNeeded], eax
0x1400920c6  lea     r13d, [rax+1]
0x1400920ca  mov     [r9], r13d
0x1400920cd  mov     rax, [rdx+248h]
0x1400920d4  lea     rbx, [rdx+240h]
0x1400920db  test    rax, rax
0x1400920de  jnz     loc_140092195
0x1400920e4  lea     r8d, [r13+4]; dwDesiredAccess
0x1400920e8  mov     rdx, [rbx]; lpServiceName
0x1400920eb  mov     rcx, [rcx+20h]; hSCManager
0x1400920ef  call    cs:__imp_OpenServiceW
0x1400920f5  mov     [rsi+248h], rax
0x1400920fc  test    rax, rax
0x1400920ff  jnz     loc_140092195
0x140092105  call    cs:__imp_GetLastError
0x14009210b  mov     r8d, eax
0x14009210e  cmp     eax, 424h
0x140092113  jnz     short loc_140092160
0x140092115  xor     edi, edi
0x140092117  mov     [r15], edi
0x14009211a  lea     rax, WPP_GLOBAL_Control
0x140092121  mov     rcx, cs:WPP_GLOBAL_Control
0x140092128  cmp     rcx, rax
0x14009212b  jz      loc_140092425
0x140092131  test    [rcx+1Ch], r13b
0x140092135  jz      loc_140092425
0x14009213b  cmp     byte ptr [rcx+19h], 3
0x14009213f  jb      loc_140092425
0x140092145  lea     edx, [rdi+2Dh]
0x140092148  mov     r9, [rbx]
0x14009214b  lea     r8, WPP_c4e026e548883477c15208e9f0c6fcb8_Traceguids
0x140092152  mov     rcx, [rcx+10h]
0x140092156  call    WPP_SF_S
0x14009215b  jmp     loc_140092425
0x140092160  lea     rax, WPP_GLOBAL_Control
0x140092167  mov     rcx, cs:WPP_GLOBAL_Control
0x14009216e  cmp     rcx, rax
0x140092171  jz      loc_140092425
0x140092177  test    [rcx+1Ch], r13b
0x14009217b  jz      loc_140092425
0x140092181  cmp     byte ptr [rcx+19h], 3
0x140092185  jb      loc_140092425
0x14009218b  mov     edx, 2Eh ; '.'
0x140092190  jmp     loc_14009240C
0x140092195  lea     r9, [rsp+98h+pcbBytesNeeded]; pcbBytesNeeded
0x14009219a  xor     r8d, r8d; cbBufSize
0x14009219d  xor     edx, edx; lpServiceConfig
0x14009219f  mov     rcx, rax; hService
0x1400921a2  call    cs:__imp_QueryServiceConfigW
0x1400921a8  call    cs:__imp_GetLastError
0x1400921ae  cmp     eax, 7Ah ; 'z'
0x1400921b1  jz      short loc_1400921F9
0x1400921b3  lea     rax, WPP_GLOBAL_Control
0x1400921ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400921c1  cmp     rcx, rax
0x1400921c4  jz      loc_140092425
0x1400921ca  test    [rcx+1Ch], r13b
0x1400921ce  jz      loc_140092425
0x1400921d4  cmp     byte ptr [rcx+19h], 3
0x1400921d8  jb      loc_140092425
0x1400921de  call    cs:__imp_GetLastError
0x1400921e4  mov     edx, 2Fh ; '/'
0x1400921e9  mov     [rsp+98h+var_78], eax
0x1400921ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1400921f4  jmp     loc_140092411
0x1400921f9  mov     ecx, [rsp+98h+pcbBytesNeeded]
0x1400921fd  call    NotifyAllocate
0x140092202  mov     r14, rax
0x140092205  test    rax, rax
0x140092208  jz      loc_140092425
0x14009220e  lea     r9, [rsp+98h+pcbBytesNeeded]; pcbBytesNeeded
0x140092213  mov     r8d, [rsp+98h+pcbBytesNeeded]; cbBufSize
0x140092218  mov     rdx, rax; lpServiceConfig
0x14009221b  mov     rcx, [rsi+248h]; hService
0x140092222  call    cs:__imp_QueryServiceConfigW
0x140092228  test    eax, eax
0x14009222a  jnz     short loc_140092264
0x14009222c  lea     rax, WPP_GLOBAL_Control
0x140092233  mov     rcx, cs:WPP_GLOBAL_Control
0x14009223a  cmp     rcx, rax
0x14009223d  jz      loc_140092425
0x140092243  test    [rcx+1Ch], r13b
0x140092247  jz      loc_140092425
0x14009224d  cmp     byte ptr [rcx+19h], 2
0x140092251  jb      loc_140092425
0x140092257  call    cs:__imp_GetLastError
0x14009225d  mov     edx, 30h ; '0'
0x140092262  jmp     short loc_1400921E9
0x140092264  cmp     dword ptr [r14+4], 2
0x140092269  jz      short loc_1400922A9
0x14009226b  lea     rax, WPP_GLOBAL_Control
0x140092272  mov     rcx, cs:WPP_GLOBAL_Control
0x140092279  cmp     rcx, rax
0x14009227c  jz      short loc_1400922A2
0x14009227e  test    [rcx+1Ch], r13b
0x140092282  jz      short loc_1400922A2
0x140092284  cmp     byte ptr [rcx+19h], 3
0x140092288  jb      short loc_1400922A2
0x14009228a  mov     edx, 31h ; '1'
0x14009228f  mov     r9, [rbx]
0x140092292  lea     r8, WPP_c4e026e548883477c15208e9f0c6fcb8_Traceguids
0x140092299  mov     rcx, [rcx+10h]
0x14009229d  call    WPP_SF_S
0x1400922a2  xor     edi, edi
0x1400922a4  jmp     loc_140092425
0x1400922a9  call    cs:__imp_GetTickCount
0x1400922af  mov     [rsi+250h], eax
0x1400922b5  lea     rdx, [rsp+98h+ServiceStatus]; lpServiceStatus
0x1400922ba  mov     rcx, [rsi+248h]; hService
0x1400922c1  call    cs:__imp_QueryServiceStatus
0x1400922c7  test    eax, eax
0x1400922c9  jz      loc_1400923DF
0x1400922cf  mov     ecx, [rsp+98h+ServiceStatus.dwCurrentState]
0x1400922d3  cmp     ecx, r13d
0x1400922d6  jnz     short loc_140092341
0x1400922d8  mov     r8d, 43Ch
0x1400922de  cmp     [rsp+98h+ServiceStatus.dwWin32ExitCode], r8d
0x1400922e3  jnz     short loc_140092341
0x1400922e5  lea     rax, WPP_GLOBAL_Control
0x1400922ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1400922f3  cmp     rcx, rax
0x1400922f6  jz      short loc_14009231F
0x1400922f8  test    [rcx+1Ch], r13b
0x1400922fc  jz      short loc_14009231F
0x1400922fe  cmp     byte ptr [rcx+19h], 3
0x140092302  jb      short loc_14009231F
0x140092304  mov     edx, 32h ; '2'
0x140092309  mov     [rsp+98h+var_70], r8d
0x14009230e  mov     [rsp+98h+var_78], r13d
0x140092313  mov     r9, [rbx]
0x140092316  mov     rcx, [rcx+10h]
0x14009231a  call    WPP_SF_Sll
0x14009231f  xor     edi, edi
0x140092321  mov     [r15], edi
0x140092324  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WinlogonNotifySubscriberRefactor@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WinlogonNotifySubscriberRefactor@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinlogonNotifySubscriberRefactor> `wil::Feature<__WilFeatureTraits_Feature_WinlogonNotifySubscriberRefactor>::GetImpl(void)'::`2'::impl
0x14009232b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WinlogonNotifySubscriberRefactor@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinlogonNotifySubscriberRefactor>::__private_IsEnabled(void)
0x140092330  test    al, al
0x140092332  jz      loc_140092425
0x140092338  mov     [r12], r13d
0x14009233c  jmp     loc_140092425
0x140092341  cmp     ecx, 3
0x140092344  jz      short loc_14009239A
0x140092346  cmp     ecx, r13d
0x140092349  jnz     short loc_140092355
0x14009234b  cmp     [rsp+98h+ServiceStatus.dwWin32ExitCode], 435h
0x140092353  jnz     short loc_14009239A
0x140092355  lea     rax, WPP_GLOBAL_Control
0x14009235c  mov     r8, cs:WPP_GLOBAL_Control
0x140092363  cmp     r8, rax
0x140092366  jz      short loc_140092392
0x140092368  test    [r8+1Ch], r13b
0x14009236c  jz      short loc_140092392
0x14009236e  cmp     byte ptr [r8+19h], 3
0x140092373  jb      short loc_140092392
0x140092375  mov     edx, 34h ; '4'
0x14009237a  mov     eax, [rsp+98h+ServiceStatus.dwWin32ExitCode]
0x14009237e  mov     [rsp+98h+var_70], eax
0x140092382  mov     [rsp+98h+var_78], ecx
0x140092386  mov     r9, [rbx]
0x140092389  mov     rcx, [r8+10h]
0x14009238d  call    WPP_SF_Sll
0x140092392  mov     edi, r13d
0x140092395  jmp     loc_140092425
0x14009239a  lea     rax, WPP_GLOBAL_Control
0x1400923a1  mov     r8, cs:WPP_GLOBAL_Control
0x1400923a8  cmp     r8, rax
0x1400923ab  jz      short loc_1400923D7
0x1400923ad  test    [r8+1Ch], r13b
0x1400923b1  jz      short loc_1400923D7
0x1400923b3  cmp     byte ptr [r8+19h], 3
0x1400923b8  jb      short loc_1400923D7
0x1400923ba  mov     edx, 33h ; '3'
0x1400923bf  mov     eax, [rsp+98h+ServiceStatus.dwWin32ExitCode]
0x1400923c3  mov     [rsp+98h+var_70], eax
0x1400923c7  mov     [rsp+98h+var_78], ecx
0x1400923cb  mov     r9, [rbx]
0x1400923ce  mov     rcx, [r8+10h]
0x1400923d2  call    WPP_SF_Sll
0x1400923d7  xor     edi, edi
0x1400923d9  mov     [r12], edi
0x1400923dd  jmp     short loc_140092425
0x1400923df  call    cs:__imp_GetLastError
0x1400923e5  mov     r8d, eax
0x1400923e8  lea     rax, WPP_GLOBAL_Control
0x1400923ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400923f6  cmp     rcx, rax
0x1400923f9  jz      short loc_140092425
0x1400923fb  test    [rcx+1Ch], r13b
0x1400923ff  jz      short loc_140092425
0x140092401  cmp     byte ptr [rcx+19h], 3
0x140092405  jb      short loc_140092425
0x140092407  mov     edx, 35h ; '5'
0x14009240c  mov     [rsp+98h+var_78], r8d
0x140092411  mov     r9, [rbx]
0x140092414  lea     r8, WPP_c4e026e548883477c15208e9f0c6fcb8_Traceguids
0x14009241b  mov     rcx, [rcx+10h]
0x14009241f  call    WPP_SF_Sl
0x140092424  nop
0x140092425  mov     eax, edi
0x140092427  mov     rcx, [rsp+98h+var_40]
0x14009242c  xor     rcx, rsp; StackCookie
0x14009242f  call    __security_check_cookie
0x140092434  add     rsp, 60h
0x140092438  pop     r15
0x14009243a  pop     r14
0x14009243c  pop     r13
0x14009243e  pop     r12
0x140092440  pop     rdi
0x140092441  pop     rsi
0x140092442  pop     rbx
0x140092443  retn
0x14009e9cf  push    rbp
0x14009e9d1  sub     rsp, 30h
0x14009e9d5  mov     rbp, rdx
0x14009e9d8  add     rsp, 30h
0x14009e9dc  pop     rbp
0x14009e9dd  retn
```
