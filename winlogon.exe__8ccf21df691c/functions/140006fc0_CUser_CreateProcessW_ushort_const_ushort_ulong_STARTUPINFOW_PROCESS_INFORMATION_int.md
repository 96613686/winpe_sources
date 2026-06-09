# CUser::CreateProcessW(ushort const *,ushort *,ulong,_STARTUPINFOW *,_PROCESS_INFORMATION *,int)

- ea: `0x140006fc0`
- end: `0x1400074fe`
- name: `?CreateProcessW@CUser@@QEAAKPEBGPEAGKPEAU_STARTUPINFOW@@PEAU_PROCESS_INFORMATION@@H@Z`
- size: `1342`
- prototype: `__int64 __fastcall(CUser *this, LPCWSTR lpApplicationName, LPWSTR lpCommandLine, int, LPSTARTUPINFOW lpStartupInfo, LPPROCESS_INFORMATION lpProcessInformation, int)`
- caller_count: `8`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140006c3c`
- `0x140019df8`
- `0x140059928`
- `0x14006cb70`
- `0x140072420`
- `0x1400727a0`
- `0x1400772c8`
- `0x1400784e0`

## callees

- `0x1400057f4`
- `0x140006970`
- `0x140006fc0`
- `0x140007510`
- `0x140008bdc`
- `0x14000d4e0`
- `0x14001a200`
- `0x14004f03c`
- `0x14005ec90`
- `0x140083cd8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14000709c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400070b2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14000709c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400070b2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000716e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000716e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000748d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14009cea6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000748d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14009cea6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400071e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000726a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007417`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400071e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000726a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007417`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x14000744a`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x14000744a`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x14000740d`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x14000740d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1400071df`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x140007260`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1400071df`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x140007260`
- `ntdll!RtlDestroyEnvironment` at `0x14000746a`
- `ntdll!RtlDestroyEnvironment` at `0x14009ce71`
- `ntdll!RtlDestroyEnvironment` at `0x14000746a`
- `ntdll!RtlDestroyEnvironment` at `0x14009ce71`
- `ntdll!NtClose` at `0x14000724c`
- `ntdll!NtClose` at `0x14000724c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CUser::CreateProcessW(
        CUser *this,
        LPCWSTR lpApplicationName,
        LPWSTR lpCommandLine,
        int a4,
        LPSTARTUPINFOW lpStartupInfo,
        LPPROCESS_INFORMATION lpProcessInformation,
        int a7)
{
  int v10; // edi
  unsigned int InputDesktopName; // eax
  CUser *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rdx
  HDESK v15; // r8
  int v16; // ecx
  int v17; // ecx
  __int64 v18; // rax
  unsigned __int64 v19; // rbx
  WCHAR *v20; // rax
  DWORD v21; // edi
  void *v22; // rbx
  DWORD v23; // eax
  DWORD LastError; // eax
  __int64 v25; // rdx
  __int64 v26; // r9
  unsigned int UserEnvironment; // eax
  DWORD v28; // eax
  LPWSTR lpDesktop; // r8
  unsigned int v31; // [rsp+60h] [rbp-68h] BYREF
  int v32; // [rsp+64h] [rbp-64h]
  int v33; // [rsp+68h] [rbp-60h]
  DWORD v34; // [rsp+6Ch] [rbp-5Ch]
  unsigned __int16 *v35; // [rsp+70h] [rbp-58h] BYREF
  PWSTR Environment; // [rsp+78h] [rbp-50h] BYREF
  HANDLE Handle; // [rsp+80h] [rbp-48h]
  void *v38; // [rsp+88h] [rbp-40h]

  v31 = 0;
  Environment = 0;
  v33 = 0;
  v10 = 0;
  v32 = 0;
  v35 = 0;
  if ( lpStartupInfo->lpDesktop )
    goto LABEL_28;
  if ( *(_DWORD *)(*((_QWORD *)this + 9) + 144LL) != 2 )
  {
    lpStartupInfo->lpDesktop = L"Winsta0\\Default";
    goto LABEL_28;
  }
  InputDesktopName = GetInputDesktopNameEx(0, &v35);
  v31 = InputDesktopName;
  if ( InputDesktopName )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = 53;
LABEL_9:
      WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids, InputDesktopName);
      goto LABEL_68;
    }
    goto LABEL_68;
  }
  if ( (unsigned int)_o__wcsicmp(v35, L"Disconnected") && (unsigned int)_o__wcsicmp(v35, L"Winlogon") )
    goto LABEL_23;
  UHHeapFree(&v35);
  v14 = *((_QWORD *)this + 9);
  v15 = 0;
  v16 = *(_DWORD *)(v14 + 144);
  if ( v16 )
  {
    v17 = v16 - 1;
    if ( v17 )
    {
      if ( v17 == 1 )
        v15 = *(HDESK *)(v14 + 120);
    }
    else
    {
      v15 = *(HDESK *)(v14 + 112);
    }
  }
  else
  {
    v15 = *(HDESK *)(v14 + 128);
  }
  InputDesktopName = GetInputDesktopNameEx(v15, &v35);
  v31 = InputDesktopName;
  if ( !InputDesktopName )
  {
LABEL_23:
    v10 = 1;
    v32 = 1;
    v18 = -1;
    do
      ++v18;
    while ( v35[v18] );
    v19 = v18 + 9;
    v20 = (WCHAR *)HeapAlloc(*((HANDLE *)this + 1), 8u, 2 * (v18 + 9));
    lpStartupInfo->lpDesktop = v20;
    if ( !v20 )
    {
      v31 = 14;
      goto LABEL_68;
    }
    v31 = StringCchPrintfW(v20, v19, L"Winsta0\\%s", v35);
LABEL_28:
    v21 = 0;
    v34 = 0;
    v38 = (void *)*((_QWORD *)this + 17);
    v22 = v38;
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl) )
    {
      if ( !ImpersonateLoggedOnUser(v22) )
      {
        LastError = GetLastError();
        v21 = LastError;
        v34 = LastError;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
LABEL_43:
          v31 = v21;
          if ( v21 )
          {
            if ( v12 == (CUser *)&WPP_GLOBAL_Control || (*((_BYTE *)v12 + 28) & 0x20) == 0 || *((_BYTE *)v12 + 25) < 2u )
              goto LABEL_67;
            v25 = 55;
            v26 = v21;
          }
          else
          {
            v33 = 1;
            UserEnvironment = CUser::CreateUserEnvironment(this, a7, (void **)&Environment);
            v31 = UserEnvironment;
            if ( UserEnvironment )
            {
              v12 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  56,
                  WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids,
                  UserEnvironment);
                v12 = WPP_GLOBAL_Control;
              }
              if ( !*((_DWORD *)this + 38) )
                goto LABEL_67;
              v31 = 0;
            }
            else
            {
              v12 = WPP_GLOBAL_Control;
            }
            if ( v12 != (CUser *)&WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 0x20) != 0 && *((_BYTE *)v12 + 25) >= 4u )
              WPP_SF_SSS(
                *((_QWORD *)v12 + 2),
                57,
                (unsigned int)WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids,
                (_DWORD)lpApplicationName,
                (__int64)lpCommandLine,
                *((_QWORD *)this + 28));
            if ( CreateProcessAsUserW(
                   *((HANDLE *)this + 17),
                   lpApplicationName,
                   lpCommandLine,
                   0,
                   0,
                   0,
                   a4 | 0x404,
                   Environment,
                   *((LPCWSTR *)this + 28),
                   lpStartupInfo,
                   lpProcessInformation) )
            {
              ResumeThread(lpProcessInformation->hThread);
              goto LABEL_67;
            }
            v28 = GetLastError();
            v31 = v28;
            v12 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_67;
            }
            v25 = 58;
            v26 = v28;
          }
          WPP_SF_d(*((_QWORD *)v12 + 2), v25, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids, v26);
LABEL_67:
          v10 = v32;
          goto LABEL_68;
        }
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids, LastError);
      }
LABEL_42:
      v12 = WPP_GLOBAL_Control;
      goto LABEL_43;
    }
    Handle = 0;
    if ( !ImpersonateLoggedOnUser(v22) )
    {
      v23 = GetLastError();
      v21 = v23;
      v34 = v23;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_35;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids, v23);
    }
    v12 = WPP_GLOBAL_Control;
LABEL_35:
    if ( !Handle )
      goto LABEL_43;
    NtClose(Handle);
    Handle = 0;
    goto LABEL_42;
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v13 = 54;
    goto LABEL_9;
  }
LABEL_68:
  if ( v33 == 1 )
    CUser::StopImpersonating(v12);
  if ( Environment )
    RtlDestroyEnvironment(Environment);
  if ( v10 )
  {
    UHHeapFree(&v35);
    lpDesktop = lpStartupInfo->lpDesktop;
    if ( lpDesktop )
    {
      HeapFree(*((HANDLE *)this + 1), 0, lpDesktop);
      lpStartupInfo->lpDesktop = 0;
    }
  }
  if ( v31 )
  {
    if ( !lpCommandLine )
      lpCommandLine = (LPWSTR)&pPassword;
    if ( !lpApplicationName )
      lpApplicationName = (LPCWSTR)&pPassword;
    CGlobalStore::ReportApplicationEvent(
      *((CGlobalStore **)this + 8),
      2u,
      0x80000FA6,
      4u,
      &v31,
      2u,
      lpApplicationName,
      lpCommandLine);
  }
  return v31;
}

```

## disassembly

```asm
0x140006fc0  mov     rax, rsp
0x140006fc3  mov     [rax+20h], r9d
0x140006fc7  mov     [rax+18h], r8
0x140006fcb  mov     [rax+10h], rdx
0x140006fcf  mov     [rax+8], rcx
0x140006fd3  push    rbx
0x140006fd4  push    rsi
0x140006fd5  push    rdi
0x140006fd6  push    r12
0x140006fd8  push    r13
0x140006fda  push    r14
0x140006fdc  push    r15
0x140006fde  sub     rsp, 90h
0x140006fe5  mov     r12, r8
0x140006fe8  mov     r13, rdx
0x140006feb  mov     r14, rcx
0x140006fee  xor     ebx, ebx
0x140006ff0  mov     [rax-68h], ebx
0x140006ff3  mov     [rax-50h], rbx
0x140006ff7  mov     [rax-60h], ebx
0x140006ffa  mov     edi, ebx
0x140006ffc  mov     [rax-64h], ebx
0x140006fff  mov     [rax-58h], rbx
0x140007003  mov     r15, [rsp+0C8h+arg_20]
0x14000700b  lea     esi, [rbx+2]
0x14000700e  cmp     [r15+10h], rbx
0x140007012  jnz     loc_1400071A7
0x140007018  mov     rax, [rcx+48h]
0x14000701c  cmp     [rax+90h], esi
0x140007022  jz      short loc_140007034
0x140007024  lea     rax, aWinsta0Default; "Winsta0\\Default"
0x14000702b  mov     [r15+10h], rax
0x14000702f  jmp     loc_1400071A7
0x140007034  lea     rdx, [rsp+0C8h+var_58]; unsigned __int16 **
0x140007039  xor     ecx, ecx; hObj
0x14000703b  call    ?GetInputDesktopNameEx@@YAKPEAUHDESK__@@PEAPEAG@Z; GetInputDesktopNameEx(HDESK__ *,ushort * *)
0x140007040  mov     [rsp+0C8h+var_68], eax
0x140007044  test    eax, eax
0x140007046  jz      short loc_140007090
0x140007048  lea     rbx, WPP_GLOBAL_Control
0x14000704f  mov     rcx, cs:WPP_GLOBAL_Control
0x140007056  cmp     rcx, rbx
0x140007059  jz      loc_140007454
0x14000705f  test    byte ptr [rcx+1Ch], 20h
0x140007063  jz      loc_140007454
0x140007069  cmp     [rcx+19h], sil
0x14000706d  jb      loc_140007454
0x140007073  mov     edx, 35h ; '5'
0x140007078  mov     r9d, eax
0x14000707b  lea     r8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x140007082  mov     rcx, [rcx+10h]
0x140007086  call    WPP_SF_d
0x14000708b  jmp     loc_140007454
0x140007090  lea     rdx, aDisconnected; "Disconnected"
0x140007097  mov     rcx, [rsp+0C8h+var_58]
0x14000709c  call    cs:__imp__o__wcsicmp
0x1400070a2  test    eax, eax
0x1400070a4  jz      short loc_1400070C0
0x1400070a6  lea     rdx, aWinlogon_1; "Winlogon"
0x1400070ad  mov     rcx, [rsp+0C8h+var_58]
0x1400070b2  call    cs:__imp__o__wcsicmp
0x1400070b8  test    eax, eax
0x1400070ba  jnz     loc_140007142
0x1400070c0  lea     rcx, [rsp+0C8h+var_58]
0x1400070c5  call    UHHeapFree
0x1400070ca  mov     rdx, [r14+48h]
0x1400070ce  mov     r8, rbx
0x1400070d1  mov     ecx, [rdx+90h]
0x1400070d7  test    ecx, ecx
0x1400070d9  jz      short loc_1400070F1
0x1400070db  sub     ecx, 1
0x1400070de  jz      short loc_1400070EB
0x1400070e0  cmp     ecx, 1
0x1400070e3  jnz     short loc_1400070F8
0x1400070e5  mov     r8, [rdx+78h]
0x1400070e9  jmp     short loc_1400070F8
0x1400070eb  mov     r8, [rdx+70h]
0x1400070ef  jmp     short loc_1400070F8
0x1400070f1  mov     r8, [rdx+80h]
0x1400070f8  lea     rdx, [rsp+0C8h+var_58]; unsigned __int16 **
0x1400070fd  mov     rcx, r8; hObj
0x140007100  call    ?GetInputDesktopNameEx@@YAKPEAUHDESK__@@PEAPEAG@Z; GetInputDesktopNameEx(HDESK__ *,ushort * *)
0x140007105  mov     [rsp+0C8h+var_68], eax
0x140007109  test    eax, eax
0x14000710b  jz      short loc_140007142
0x14000710d  lea     rbx, WPP_GLOBAL_Control
0x140007114  mov     rcx, cs:WPP_GLOBAL_Control
0x14000711b  cmp     rcx, rbx
0x14000711e  jz      loc_140007454
0x140007124  test    byte ptr [rcx+1Ch], 20h
0x140007128  jz      loc_140007454
0x14000712e  cmp     [rcx+19h], sil
0x140007132  jb      loc_140007454
0x140007138  mov     edx, 36h ; '6'
0x14000713d  jmp     loc_140007078
0x140007142  mov     edi, 1
0x140007147  mov     [rsp+0C8h+var_64], edi
0x14000714b  mov     rcx, [rsp+0C8h+var_58]
0x140007150  or      rax, 0FFFFFFFFFFFFFFFFh
0x140007154  inc     rax
0x140007157  cmp     [rcx+rax*2], bx
0x14000715b  jnz     short loc_140007154
0x14000715d  lea     rbx, [rax+9]
0x140007161  lea     r8, [rbx+rbx]; dwBytes
0x140007165  mov     edx, 8; dwFlags
0x14000716a  mov     rcx, [r14+8]; hHeap
0x14000716e  call    cs:__imp_HeapAlloc
0x140007174  mov     [r15+10h], rax
0x140007178  test    rax, rax
0x14000717b  jnz     short loc_14000718A
0x14000717d  mov     [rsp+0C8h+var_68], 0Eh
0x140007185  jmp     loc_140007454
0x14000718a  mov     r9, [rsp+0C8h+var_58]
0x14000718f  lea     r8, aWinsta0S; "Winsta0\\%s"
0x140007196  mov     rdx, rbx; unsigned __int64
0x140007199  mov     rcx, rax; unsigned __int16 *
0x14000719c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400071a1  mov     [rsp+0C8h+var_68], eax
0x1400071a5  xor     ebx, ebx
0x1400071a7  mov     edi, ebx
0x1400071a9  mov     [rsp+0C8h+var_5C], ebx
0x1400071ad  mov     rbx, [r14+88h]
0x1400071b4  mov     [rsp+0C8h+var_40], rbx
0x1400071bc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x1400071c3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x1400071c8  mov     rcx, rbx; hToken
0x1400071cb  test    al, al
0x1400071cd  jz      loc_140007260
0x1400071d3  mov     [rsp+0C8h+Handle], 0
0x1400071df  call    cs:__imp_ImpersonateLoggedOnUser
0x1400071e5  test    eax, eax
0x1400071e7  jnz     short loc_14000722E
0x1400071e9  call    cs:__imp_GetLastError
0x1400071ef  mov     edi, eax
0x1400071f1  mov     [rsp+0C8h+var_5C], eax
0x1400071f5  lea     rbx, WPP_GLOBAL_Control
0x1400071fc  mov     rcx, cs:WPP_GLOBAL_Control
0x140007203  cmp     rcx, rbx
0x140007206  jz      short loc_14000723C
0x140007208  test    byte ptr [rcx+1Ch], 20h
0x14000720c  jz      short loc_14000723C
0x14000720e  cmp     [rcx+19h], sil
0x140007212  jb      short loc_14000723C
0x140007214  mov     edx, 19h
0x140007219  mov     r9d, eax
0x14000721c  lea     r8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x140007223  mov     rcx, [rcx+10h]
0x140007227  call    WPP_SF_d
0x14000722c  jmp     short loc_140007235
0x14000722e  lea     rbx, WPP_GLOBAL_Control
0x140007235  mov     rcx, cs:WPP_GLOBAL_Control
0x14000723c  mov     rax, [rsp+0C8h+Handle]
0x140007244  test    rax, rax
0x140007247  jz      short loc_1400072BD
0x140007249  mov     rcx, rax; Handle
0x14000724c  call    cs:__imp_NtClose
0x140007252  mov     [rsp+0C8h+Handle], 0
0x14000725e  jmp     short loc_1400072B6
0x140007260  call    cs:__imp_ImpersonateLoggedOnUser
0x140007266  test    eax, eax
0x140007268  jnz     short loc_1400072AF
0x14000726a  call    cs:__imp_GetLastError
0x140007270  mov     edi, eax
0x140007272  mov     [rsp+0C8h+var_5C], eax
0x140007276  lea     rbx, WPP_GLOBAL_Control
0x14000727d  mov     rcx, cs:WPP_GLOBAL_Control
0x140007284  cmp     rcx, rbx
0x140007287  jz      short loc_1400072BD
0x140007289  test    byte ptr [rcx+1Ch], 20h
0x14000728d  jz      short loc_1400072BD
0x14000728f  cmp     [rcx+19h], sil
0x140007293  jb      short loc_1400072BD
0x140007295  mov     edx, 1Bh
0x14000729a  mov     r9d, eax
0x14000729d  lea     r8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x1400072a4  mov     rcx, [rcx+10h]
0x1400072a8  call    WPP_SF_d
0x1400072ad  jmp     short loc_1400072B6
0x1400072af  lea     rbx, WPP_GLOBAL_Control
0x1400072b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400072bd  mov     [rsp+0C8h+var_68], edi
0x1400072c1  test    edi, edi
0x1400072c3  jz      short loc_1400072FF
0x1400072c5  cmp     rcx, rbx
0x1400072c8  jz      loc_140007450
0x1400072ce  test    byte ptr [rcx+1Ch], 20h
0x1400072d2  jz      loc_140007450
0x1400072d8  cmp     [rcx+19h], sil
0x1400072dc  jb      loc_140007450
0x1400072e2  mov     edx, 37h ; '7'
0x1400072e7  mov     r9d, edi
0x1400072ea  lea     r8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x1400072f1  mov     rcx, [rcx+10h]
0x1400072f5  call    WPP_SF_d
0x1400072fa  jmp     loc_140007450
0x1400072ff  mov     [rsp+0C8h+var_60], 1
0x140007307  lea     r8, [rsp+0C8h+Environment]; void **
0x14000730c  mov     edx, [rsp+0C8h+arg_30]; int
0x140007313  mov     rcx, r14; this
0x140007316  call    ?CreateUserEnvironment@CUser@@QEAAKHPEAPEAX@Z; CUser::CreateUserEnvironment(int,void * *)
0x14000731b  mov     [rsp+0C8h+var_68], eax
0x14000731f  test    eax, eax
0x140007321  jz      short loc_140007372
0x140007323  mov     rcx, cs:WPP_GLOBAL_Control
0x14000732a  cmp     rcx, rbx
0x14000732d  jz      short loc_14000735A
0x14000732f  test    byte ptr [rcx+1Ch], 20h
0x140007333  jz      short loc_14000735A
0x140007335  cmp     [rcx+19h], sil
0x140007339  jb      short loc_14000735A
0x14000733b  mov     edx, 38h ; '8'
0x140007340  mov     r9d, eax
0x140007343  lea     r8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x14000734a  mov     rcx, [rcx+10h]
0x14000734e  call    WPP_SF_d
0x140007353  mov     rcx, cs:WPP_GLOBAL_Control
0x14000735a  cmp     dword ptr [r14+98h], 0
0x140007362  jz      loc_140007450
0x140007368  mov     [rsp+0C8h+var_68], 0
0x140007370  jmp     short loc_140007379
0x140007372  mov     rcx, cs:WPP_GLOBAL_Control
0x140007379  cmp     rcx, rbx
0x14000737c  jz      short loc_1400073B3
0x14000737e  test    byte ptr [rcx+1Ch], 20h
0x140007382  jz      short loc_1400073B3
0x140007384  cmp     byte ptr [rcx+19h], 4
0x140007388  jb      short loc_1400073B3
0x14000738a  mov     edx, 39h ; '9'
0x14000738f  mov     rax, [r14+0E0h]
0x140007396  mov     qword ptr [rsp+0C8h+bInheritHandles], rax
0x14000739b  mov     [rsp+0C8h+lpThreadAttributes], r12
0x1400073a0  mov     r9, r13
0x1400073a3  lea     r8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x1400073aa  mov     rcx, [rcx+10h]
0x1400073ae  call    WPP_SF_SSS
0x1400073b3  mov     ecx, [rsp+0C8h+arg_18]
0x1400073ba  or      ecx, 404h
0x1400073c0  mov     rdi, [rsp+0C8h+arg_28]
0x1400073c8  mov     [rsp+0C8h+lpProcessInformation], rdi; lpProcessInformation
0x1400073cd  mov     [rsp+0C8h+lpStartupInfo], r15; lpStartupInfo
0x1400073d2  mov     rax, [r14+0E0h]
0x1400073d9  mov     [rsp+0C8h+lpCurrentDirectory], rax; lpCurrentDirectory
0x1400073de  mov     rax, [rsp+0C8h+Environment]
0x1400073e3  mov     [rsp+0C8h+lpEnvironment], rax; lpEnvironment
0x1400073e8  mov     [rsp+0C8h+dwCreationFlags], ecx; dwCreationFlags
0x1400073ec  mov     [rsp+0C8h+bInheritHandles], 0; bInheritHandles
0x1400073f4  mov     [rsp+0C8h+lpThreadAttributes], 0; lpThreadAttributes
0x1400073fd  xor     r9d, r9d; lpProcessAttributes
0x140007400  mov     r8, r12; lpCommandLine
0x140007403  mov     rdx, r13; lpApplicationName
0x140007406  mov     rcx, [r14+88h]; hToken
0x14000740d  call    cs:__imp_CreateProcessAsUserW
0x140007413  test    eax, eax
0x140007415  jnz     short loc_140007446
0x140007417  call    cs:__imp_GetLastError
0x14000741d  mov     [rsp+0C8h+var_68], eax
0x140007421  mov     rcx, cs:WPP_GLOBAL_Control
0x140007428  cmp     rcx, rbx
0x14000742b  jz      short loc_140007450
0x14000742d  test    byte ptr [rcx+1Ch], 20h
0x140007431  jz      short loc_140007450
0x140007433  cmp     [rcx+19h], sil
0x140007437  jb      short loc_140007450
0x140007439  mov     edx, 3Ah ; ':'
0x14000743e  mov     r9d, eax
0x140007441  jmp     loc_1400072EA
0x140007446  mov     rcx, [rdi+8]; hThread
0x14000744a  call    cs:__imp_ResumeThread
0x140007450  mov     edi, [rsp+0C8h+var_64]
0x140007454  cmp     [rsp+0C8h+var_60], 1
0x140007459  jnz     short loc_140007460
0x14000745b  call    ?StopImpersonating@CUser@@QEAAKXZ; CUser::StopImpersonating(void)
0x140007460  mov     rcx, [rsp+0C8h+Environment]; Environment
0x140007465  test    rcx, rcx
0x140007468  jz      short loc_140007470
0x14000746a  call    cs:__imp_RtlDestroyEnvironment
0x140007470  test    edi, edi
0x140007472  jz      short loc_14000749B
0x140007474  lea     rcx, [rsp+0C8h+var_58]
0x140007479  call    UHHeapFree
0x14000747e  mov     r8, [r15+10h]; lpMem
0x140007482  test    r8, r8
0x140007485  jz      short loc_14000749B
0x140007487  xor     edx, edx; dwFlags
0x140007489  mov     rcx, [r14+8]; hHeap
0x14000748d  call    cs:__imp_HeapFree
0x140007493  mov     qword ptr [r15+10h], 0
0x14000749b  cmp     [rsp+0C8h+var_68], 0
0x1400074a0  jz      short loc_1400074E7
0x1400074a2  lea     rax, pPassword
0x1400074a9  test    r12, r12
0x1400074ac  cmovz   r12, rax
0x1400074b0  test    r13, r13
0x1400074b3  cmovz   r13, rax
0x1400074b7  mov     [rsp+0C8h+lpEnvironment], r12
0x1400074bc  mov     qword ptr [rsp+0C8h+dwCreationFlags], r13
0x1400074c1  mov     [rsp+0C8h+bInheritHandles], esi; unsigned int
0x1400074c5  lea     rax, [rsp+0C8h+var_68]
0x1400074ca  mov     [rsp+0C8h+lpThreadAttributes], rax; void *
0x1400074cf  mov     r9d, 4; unsigned int
  ... truncated ...
```
