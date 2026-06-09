# SrvRecordShutdownReason

- ea: `0x1800080b0`
- end: `0x180008a74`
- name: `SrvRecordShutdownReason`
- size: `2500`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800065d4`
- `0x180006a24`
- `0x180007890`
- `0x180007940`
- `0x1800080b0`
- `0x180008a7c`
- `0x18000a73c`
- `0x1800138c5`
- `0x1800138f0`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x1800083a0`
- `KERNELBASE!LocalAlloc` at `0x1800083b9`
- `KERNELBASE!LocalAlloc` at `0x1800083d6`
- `KERNELBASE!LocalAlloc` at `0x1800083ef`
- `KERNELBASE!LocalAlloc` at `0x180008441`
- `KERNELBASE!LocalAlloc` at `0x1800083a0`
- `KERNELBASE!LocalAlloc` at `0x1800083b9`
- `KERNELBASE!LocalAlloc` at `0x1800083d6`
- `KERNELBASE!LocalAlloc` at `0x1800083ef`
- `KERNELBASE!LocalAlloc` at `0x180008441`
- `ntdll!EvtIntReportEventAndSourceAsync` at `0x1800088ee`
- `ntdll!EvtIntReportEventAndSourceAsync` at `0x1800088ee`
- `ntdll!_wtoi` at `0x180008635`
- `ntdll!_wtoi` at `0x180008635`
- `ntdll!NtOpenThreadToken` at `0x180008141`
- `ntdll!NtOpenThreadToken` at `0x180008141`
- `ntdll!NtDeleteValueKey` at `0x180008793`
- `ntdll!NtDeleteValueKey` at `0x1800087bf`
- `ntdll!NtDeleteValueKey` at `0x1800087eb`
- `ntdll!NtDeleteValueKey` at `0x180008793`
- `ntdll!NtDeleteValueKey` at `0x1800087bf`
- `ntdll!NtDeleteValueKey` at `0x1800087eb`
- `ntdll!NtOpenKey` at `0x18000875f`
- `ntdll!NtOpenKey` at `0x18000875f`
- `ntdll!RtlInitUnicodeString` at `0x180008720`
- `ntdll!RtlInitUnicodeString` at `0x18000877e`
- `ntdll!RtlInitUnicodeString` at `0x1800087aa`
- `ntdll!RtlInitUnicodeString` at `0x1800087d6`
- `ntdll!RtlInitUnicodeString` at `0x180008720`
- `ntdll!RtlInitUnicodeString` at `0x18000877e`
- `ntdll!RtlInitUnicodeString` at `0x1800087aa`
- `ntdll!RtlInitUnicodeString` at `0x1800087d6`
- `ntdll!NtClose` at `0x1800081b6`
- `ntdll!NtClose` at `0x1800081dd`
- `ntdll!NtClose` at `0x1800087fc`
- `ntdll!NtClose` at `0x1800081b6`
- `ntdll!NtClose` at `0x1800081dd`
- `ntdll!NtClose` at `0x1800087fc`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18000890b`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18000890b`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000885d`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000885d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800089f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008a01`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008a11`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008a20`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008a30`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008a40`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800089f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008a01`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008a11`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008a20`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008a30`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008a40`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180008553`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180008553`
- `CSRSRV!CsrImpersonateClient` at `0x180008111`
- `CSRSRV!CsrImpersonateClient` at `0x1800089d1`
- `CSRSRV!CsrImpersonateClient` at `0x180008111`
- `CSRSRV!CsrImpersonateClient` at `0x1800089d1`
- `CSRSRV!CsrRevertToSelf` at `0x180008153`
- `CSRSRV!CsrRevertToSelf` at `0x180008197`
- `CSRSRV!CsrRevertToSelf` at `0x18000881f`
- `CSRSRV!CsrRevertToSelf` at `0x180008153`
- `CSRSRV!CsrRevertToSelf` at `0x180008197`
- `CSRSRV!CsrRevertToSelf` at `0x18000881f`
- `CSRSRV!CsrValidateMessageBuffer` at `0x180008221`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000826d`
- `CSRSRV!CsrValidateMessageBuffer` at `0x1800082da`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000830c`
- `CSRSRV!CsrValidateMessageBuffer` at `0x180008221`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000826d`
- `CSRSRV!CsrValidateMessageBuffer` at `0x1800082da`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000830c`
- `USER32!GetReasonTitleFromReasonCode` at `0x180008579`
- `USER32!GetReasonTitleFromReasonCode` at `0x180008579`
- `USER32!GetSystemMetrics` at `0x180008184`
- `USER32!GetSystemMetrics` at `0x180008184`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800084e4`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800084e4`

## string_xrefs

- `0x180008709`: `\Registry\Machine\Software\Microsoft\Windows\CurrentVersion\Reliability`

## pseudocode

```c
__int64 __fastcall SrvRecordShutdownReason(__int64 a1)
{
  NTSTATUS v3; // ebx
  int v4; // ebx
  int v5; // edi
  void *UserSid; // rbx
  __int64 v7; // rsi
  WCHAR *v8; // r12
  WCHAR *v9; // r13
  const wchar_t *v10; // r15
  __int64 v11; // r8
  signed __int32 v12; // eax
  __int64 v13; // r8
  __int64 v14; // r8
  bool v15; // zf
  WCHAR *v16; // r12
  HLOCAL v17; // rax
  LPWSTR v18; // rdi
  const wchar_t *v19; // r13
  unsigned __int64 v20; // rax
  _WORD *v21; // r8
  __int64 v22; // rcx
  _WORD *v23; // rdx
  _WORD *v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // rax
  const wchar_t *v27; // rbx
  const wchar_t *v28; // r13
  unsigned __int16 v29; // r12
  int v30; // r15d
  unsigned int v31; // eax
  unsigned __int64 v32; // rdx
  unsigned __int64 v33; // rax
  wchar_t v34; // ax
  unsigned __int64 v35; // rcx
  __int64 v36; // r8
  unsigned __int16 v37; // di
  unsigned __int16 v38; // bx
  __int64 v39; // rax
  unsigned __int16 v40; // di
  unsigned int v41; // eax
  __int64 v42; // rax
  WCHAR *v43; // [rsp+50h] [rbp-B0h]
  WCHAR *v44; // [rsp+58h] [rbp-A8h]
  DWORD cchReferencedDomainName; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cchName; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD nSize; // [rsp+68h] [rbp-98h] BYREF
  void *TokenHandle; // [rsp+70h] [rbp-90h] BYREF
  void *KeyHandle; // [rsp+78h] [rbp-88h] BYREF
  HLOCAL v50; // [rsp+80h] [rbp-80h]
  HLOCAL hMem; // [rsp+88h] [rbp-78h]
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-70h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+A0h] [rbp-60h] BYREF
  ULONGLONG RegHandle; // [rsp+A8h] [rbp-58h] BYREF
  PSID Sid; // [rsp+B0h] [rbp-50h]
  LPWSTR Name; // [rsp+B8h] [rbp-48h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C0h] [rbp-40h] BYREF
  HLOCAL v58; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR *v59; // [rsp+F8h] [rbp-8h]
  const wchar_t *v60; // [rsp+100h] [rbp+0h]
  _BYTE *v61; // [rsp+108h] [rbp+8h]
  __int64 v62; // [rsp+110h] [rbp+10h]
  const wchar_t *v63; // [rsp+118h] [rbp+18h]
  WCHAR *v64; // [rsp+120h] [rbp+20h]
  _BYTE v65[64]; // [rsp+130h] [rbp+30h] BYREF

  memset_0(&v58, 0, 0x40u);
  nSize = 16;
  cchName = 261;
  cchReferencedDomainName = 261;
  RegHandle = 0;
  peUse = 0;
  TokenHandle = 0;
  if ( !(unsigned __int8)CsrImpersonateClient(0) )
    return 3221225473LL;
  v3 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle);
  if ( v3 < 0 )
  {
    CsrRevertToSelf();
    return (unsigned int)v3;
  }
  if ( *(HANDLE *)(a1 + 8) == NtCurrentTeb()->ClientId.UniqueProcess
    || (v4 = *(_DWORD *)(a1 + 8), v5 = 0, v4 == GetSystemMetrics(93)) )
  {
    v5 = 1;
  }
  CsrRevertToSelf();
  if ( !(unsigned int)TestShutdownPrivilege(TokenHandle) )
  {
    NtClose(TokenHandle);
    return 3221225506LL;
  }
  UserSid = (void *)GetUserSid(TokenHandle);
  Sid = UserSid;
  NtClose(TokenHandle);
  if ( !UserSid )
    return 3221225495LL;
  v7 = a1 + 64;
  Name = 0;
  hMem = 0;
  v8 = 0;
  v50 = 0;
  v9 = 0;
  v10 = 0;
  if ( !(unsigned __int8)CsrValidateMessageBuffer(a1, a1 + 64, 32, 1) )
    goto LABEL_14;
  if ( *(_DWORD *)(a1 + 76) == 3 )
  {
    if ( *(_DWORD *)(a1 + 80) )
      goto LABEL_17;
  }
  else if ( *(_DWORD *)(a1 + 76) == 2 )
  {
    goto LABEL_17;
  }
  v13 = *(unsigned int *)(a1 + 84);
  if ( !(_DWORD)v13 )
    goto LABEL_14;
  if ( (unsigned int)(v13 - 1) > 0x104 )
    goto LABEL_14;
  if ( !(unsigned __int8)CsrValidateMessageBuffer(a1, a1 + 88, v13, 2) )
    goto LABEL_14;
  v14 = *(unsigned int *)(a1 + 96);
  if ( (unsigned int)(v14 - 1) > 0x1F || !(unsigned __int8)CsrValidateMessageBuffer(a1, a1 + 104, v14, 2) )
    goto LABEL_14;
  v10 = 0;
  *(_WORD *)(*(_QWORD *)(a1 + 88) + 2LL * (unsigned int)(*(_DWORD *)(a1 + 84) - 1)) = 0;
  *(_WORD *)(*(_QWORD *)(a1 + 104) + 2LL * (unsigned int)(*(_DWORD *)(a1 + 96) - 1)) = 0;
LABEL_17:
  v11 = *(unsigned int *)(a1 + 112);
  if ( !(_DWORD)v11 )
    goto LABEL_21;
  if ( (unsigned int)v11 > 0x200 || !(unsigned __int8)CsrValidateMessageBuffer(a1, a1 + 120, v11, 2) )
  {
LABEL_14:
    v3 = -1073741811;
LABEL_117:
    LocalFree(Sid);
    LocalFree(v8);
    LocalFree(Name);
    LocalFree(v9);
    LocalFree(hMem);
    LocalFree(v50);
    return (unsigned int)v3;
  }
  *(_WORD *)(*(_QWORD *)(a1 + 120) + 2LL * (unsigned int)(*(_DWORD *)(a1 + 112) - 1)) = 0;
LABEL_21:
  if ( *(_DWORD *)(a1 + 76) == 4 )
  {
    v12 = _InterlockedCompareExchange(&g_DirtyShutdownMax, 0, 1);
LABEL_37:
    v15 = v12 == 0;
    goto LABEL_38;
  }
  if ( (*(_DWORD *)(a1 + 76) != 3 || !*(_DWORD *)(a1 + 80)) && *(_DWORD *)(a1 + 76) != 2 )
  {
    v12 = _InterlockedCompareExchange(&g_ShutdownState, 0, 1);
    goto LABEL_37;
  }
  if ( v5 )
  {
    _InterlockedExchange(&g_ShutdownState, 1);
LABEL_39:
    Name = (LPWSTR)LocalAlloc(0x40u, 2LL * cchName);
    v43 = (WCHAR *)LocalAlloc(0x40u, 2LL * cchReferencedDomainName);
    v16 = (WCHAR *)LocalAlloc(0x40u, 2LL * nSize);
    v44 = v16;
    v17 = LocalAlloc(0x40u, 0x80u);
    v18 = Name;
    hMem = v17;
    v19 = (const wchar_t *)v17;
    if ( Name && v43 && v16 && v17 )
    {
      if ( !*(_DWORD *)(a1 + 112) )
        goto LABEL_55;
      v50 = LocalAlloc(0x40u, 2LL * *(unsigned int *)(a1 + 112));
      v10 = (const wchar_t *)v50;
      if ( v50 )
      {
        v20 = *(unsigned int *)(a1 + 112);
        if ( *(_DWORD *)(a1 + 112) )
        {
          if ( v20 <= 0x7FFFFFFF )
          {
            v21 = *(_WORD **)(a1 + 120);
            v22 = 2147483646;
            v23 = v50;
            do
            {
              if ( !v22 )
                break;
              if ( !*v21 )
                break;
              *v23++ = *v21++;
              --v22;
              --v20;
            }
            while ( v20 );
            v19 = (const wchar_t *)hMem;
            v24 = v23 - 1;
            if ( v20 )
              v24 = v23;
            *v24 = 0;
          }
          else
          {
            *(_WORD *)v50 = 0;
          }
        }
LABEL_55:
        if ( LookupAccountSidLocalW(Sid, v18, &cchName, v43, &cchReferencedDomainName, &peUse) )
        {
          v18[260] = 0;
          v43[260] = 0;
          v25 = cchReferencedDomainName;
          if ( cchReferencedDomainName + cchName > 0x103 )
          {
            v3 = -1073741823;
LABEL_115:
            v8 = v43;
LABEL_116:
            v9 = v44;
            goto LABEL_117;
          }
          if ( cchReferencedDomainName )
            RtlStringCchCatW(v43, cchReferencedDomainName, L"\\");
          RtlStringCchCatW(v43, v25, v18);
        }
        else
        {
          *v43 = 0;
          *v18 = 0;
        }
        if ( !GetComputerNameW(v16, &nSize) )
          *v16 = 0;
        if ( !(unsigned int)GetReasonTitleFromReasonCode(*(unsigned int *)(*(_QWORD *)v7 + 8LL), v19, 64) )
        {
LABEL_65:
          v3 = -1073741811;
          goto LABEL_115;
        }
        *((_WORD *)v19 + 63) = 0;
        RtlStringCchPrintfW(v65, 32, L"0x%x", *(unsigned int *)(*(_QWORD *)v7 + 8LL));
        switch ( *(_DWORD *)(a1 + 76) )
        {
          case 1:
            v38 = 4;
            if ( (unsigned int)Feature_CriticalProcessShutdownLogsAsError__private_IsEnabledDeviceUsageNoInline()
              && *(_DWORD *)(*(_QWORD *)v7 + 8LL) == 327686 )
            {
              v38 = 1;
            }
            break;
          case 2:
            v58 = v16;
            v8 = v43;
            v38 = 2;
            v59 = v43;
            v40 = 2;
            goto LABEL_91;
          case 3:
            if ( *(_DWORD *)(a1 + 80) )
            {
              v38 = 2;
              v58 = v16;
              v8 = v43;
              v59 = v43;
              v60 = v10;
              v40 = 3;
              goto LABEL_91;
            }
            v38 = 4;
            break;
          case 4:
            KeyHandle = 0;
            v26 = 0;
            v27 = v10;
            DestinationString = 0;
            memset(&ObjectAttributes, 0, 44);
            if ( v10 )
            {
              v26 = -1;
              do
                ++v26;
              while ( v10[v26] );
            }
            v28 = &v10[v26];
            v29 = 2;
            v30 = 0;
            v58 = hMem;
            v59 = (WCHAR *)v65;
            while ( v27 < v28 )
            {
              v31 = _wtoi(v27);
              *v27 = 0;
              do
                ++v27;
              while ( v27 < v28 && *v27 != 10 );
              v32 = v31;
              v33 = -1;
              do
                ++v33;
              while ( v27[v33] );
              if ( v32 > v33 )
              {
                _InterlockedCompareExchange(&g_DirtyShutdownMax, 1, 0);
                goto LABEL_65;
              }
              v34 = *v27;
              v35 = (unsigned __int64)(v27 + 1);
              v36 = v29;
              v37 = v29 + 1;
              if ( *v27 )
                ++v27;
              v27 += v32;
              ++v29;
              ++v30;
              *(&v58 + v36) = (HLOCAL)(v35 & -(__int64)(v34 != 0));
              if ( v30 >= 3 )
              {
                v38 = 2;
                goto LABEL_88;
              }
            }
            memset_0(&v58 + v29, 0, 8LL * (3 - v30));
            v38 = 2;
            v37 = v29;
            do
            {
              ++v37;
              ++v30;
            }
            while ( v30 < 3 );
LABEL_88:
            v8 = v43;
            v39 = v37;
            v40 = v37 + 1;
            *(&v58 + v39) = v43;
            RtlInitUnicodeString(
              &DestinationString,
              L"\\Registry\\Machine\\Software\\Microsoft\\Windows\\CurrentVersion\\Reliability");
            ObjectAttributes.Length = 48;
            ObjectAttributes.ObjectName = &DestinationString;
            ObjectAttributes.Attributes = 64;
            ObjectAttributes.RootDirectory = 0;
            *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
            if ( NtOpenKey(&KeyHandle, 0xF003Fu, &ObjectAttributes) >= 0 )
            {
              RtlInitUnicodeString(&DestinationString, L"DirtyShutdown");
              NtDeleteValueKey(KeyHandle, &DestinationString);
              RtlInitUnicodeString(&DestinationString, L"DirtyShutdownTime");
              NtDeleteValueKey(KeyHandle, &DestinationString);
              RtlInitUnicodeString(&DestinationString, L"BugcheckString");
              NtDeleteValueKey(KeyHandle, &DestinationString);
              NtClose(KeyHandle);
            }
            v10 = (const wchar_t *)v50;
LABEL_91:
            if ( *(HANDLE *)(a1 + 8) == NtCurrentTeb()->ClientId.UniqueProcess )
              CsrRevertToSelf();
            if ( *(_DWORD *)(a1 + 76) == 1 || *(_DWORD *)(a1 + 76) == 3 && !*(_DWORD *)(a1 + 80) )
              WriteShutdownReasonToRegistry(*(unsigned int *)(*(_QWORD *)v7 + 8LL), v10);
            if ( EventRegister(&User32ControlGuid, 0, 0, &RegHandle) )
            {
              v3 = -1073741823;
            }
            else
            {
              v41 = 0;
              if ( v40 )
              {
                do
                {
                  if ( !*(&v58 + v41) )
                    *(&v58 + v41) = &qword_180017108;
                  ++v41;
                }
                while ( (int)v41 < v40 );
              }
              gVetoProcess = *(_DWORD *)(*(_QWORD *)v7 + 8LL);
              v3 = (unsigned int)EvtIntReportEventAndSourceAsync(
                                   RegHandle,
                                   L"User32",
                                   v38,
                                   0,
                                   *(_DWORD *)(a1 + 72),
                                   Sid,
                                   v40,
                                   40,
                                   &v58,
                                   &gVetoProcess) == 0
                 ? 0xC0000001
                 : 0;
              EventUnregister(RegHandle);
            }
            if ( *(HANDLE *)(a1 + 8) == NtCurrentTeb()->ClientId.UniqueProcess )
              CsrImpersonateClient(0);
            goto LABEL_116;
          default:
            goto LABEL_65;
        }
        v40 = 7;
        v58 = *(HLOCAL *)(a1 + 88);
        v61 = v65;
        v42 = *(_QWORD *)(a1 + 104);
        v59 = v16;
        v8 = v43;
        v62 = v42;
        v60 = v19;
        v63 = v10;
        v64 = v43;
        goto LABEL_91;
      }
    }
    v3 = -1073741801;
    goto LABEL_115;
  }
  v15 = _InterlockedCompareExchange(&g_ShutdownState, 1, 0) == 0;
LABEL_38:
  if ( !v15 )
    goto LABEL_39;
  return 0;
}

```

## disassembly

```asm
0x1800080b0  push    rbp
0x1800080b2  push    rbx
0x1800080b3  push    rsi
0x1800080b4  push    rdi
0x1800080b5  push    r12
0x1800080b7  push    r13
0x1800080b9  push    r14
0x1800080bb  push    r15
0x1800080bd  lea     rbp, [rsp-88h]
0x1800080c5  sub     rsp, 188h
0x1800080cc  mov     rax, cs:__security_cookie
0x1800080d3  xor     rax, rsp
0x1800080d6  mov     [rbp+0C0h+var_50], rax
0x1800080da  xor     edx, edx; Val
0x1800080dc  mov     r14, rcx
0x1800080df  lea     rcx, [rbp+0C0h+var_D0]; void *
0x1800080e3  lea     r8d, [rdx+40h]; Size
0x1800080e7  call    memset_0
0x1800080ec  mov     eax, 105h
0x1800080f1  mov     [rsp+1C0h+nSize], 10h
0x1800080f9  xor     esi, esi
0x1800080fb  mov     [rsp+1C0h+cchName], eax
0x1800080ff  xor     ecx, ecx
0x180008101  mov     [rsp+1C0h+var_160], eax
0x180008105  mov     [rbp+0C0h+RegHandle], rsi
0x180008109  mov     [rbp+0C0h+var_120], esi
0x18000810c  mov     [rsp+1C0h+TokenHandle], rsi
0x180008111  call    cs:__imp_CsrImpersonateClient
0x180008118  nop     dword ptr [rax+rax+00h]
0x18000811d  test    al, al
0x18000811f  jnz     short loc_18000812B
0x180008121  mov     eax, 0C0000001h
0x180008126  jmp     loc_180008A53
0x18000812b  mov     r15d, 1
0x180008131  lea     r9, [rsp+1C0h+TokenHandle]; TokenHandle
0x180008136  mov     r8b, r15b; OpenAsSelf
0x180008139  lea     edx, [r15+7]; DesiredAccess
0x18000813d  lea     rcx, [r15-3]; ThreadHandle
0x180008141  call    cs:__imp_NtOpenThreadToken
0x180008148  nop     dword ptr [rax+rax+00h]
0x18000814d  mov     ebx, eax
0x18000814f  test    eax, eax
0x180008151  jns     short loc_180008166
0x180008153  call    cs:__imp_CsrRevertToSelf
0x18000815a  nop     dword ptr [rax+rax+00h]
0x18000815f  mov     eax, ebx
0x180008161  jmp     loc_180008A53
0x180008166  mov     rax, gs:30h
0x18000816f  mov     rcx, [rax+40h]
0x180008173  cmp     [r14+8], rcx
0x180008177  jz      short loc_180008194
0x180008179  mov     ebx, [r14+8]
0x18000817d  mov     ecx, 5Dh ; ']'; nIndex
0x180008182  mov     edi, esi
0x180008184  call    cs:__imp_GetSystemMetrics
0x18000818b  nop     dword ptr [rax+rax+00h]
0x180008190  cmp     ebx, eax
0x180008192  jnz     short loc_180008197
0x180008194  mov     edi, r15d
0x180008197  call    cs:__imp_CsrRevertToSelf
0x18000819e  nop     dword ptr [rax+rax+00h]
0x1800081a3  mov     rcx, [rsp+1C0h+TokenHandle]; TokenHandle
0x1800081a8  call    TestShutdownPrivilege
0x1800081ad  mov     rcx, [rsp+1C0h+TokenHandle]; TokenHandle
0x1800081b2  test    eax, eax
0x1800081b4  jnz     short loc_1800081CC
0x1800081b6  call    cs:__imp_NtClose
0x1800081bd  nop     dword ptr [rax+rax+00h]
0x1800081c2  mov     eax, 0C0000022h
0x1800081c7  jmp     loc_180008A53
0x1800081cc  call    GetUserSid
0x1800081d1  mov     rcx, [rsp+1C0h+TokenHandle]; Handle
0x1800081d6  mov     rbx, rax
0x1800081d9  mov     [rbp+0C0h+Sid], rax
0x1800081dd  call    cs:__imp_NtClose
0x1800081e4  nop     dword ptr [rax+rax+00h]
0x1800081e9  test    rbx, rbx
0x1800081ec  jnz     short loc_1800081F8
0x1800081ee  mov     eax, 0C0000017h
0x1800081f3  jmp     loc_180008A53
0x1800081f8  xor     ebx, ebx
0x1800081fa  lea     rsi, [r14+40h]
0x1800081fe  mov     rdx, rsi
0x180008201  mov     [rbp+0C0h+Name], rbx
0x180008205  mov     rcx, r14
0x180008208  mov     [rbp+0C0h+hMem], rbx
0x18000820c  mov     r12d, ebx
0x18000820f  mov     [rbp+0C0h+var_140], rbx
0x180008213  lea     r9d, [rbx+1]
0x180008217  mov     r13d, ebx
0x18000821a  lea     r8d, [rbx+20h]
0x18000821e  mov     r15d, ebx
0x180008221  call    cs:__imp_CsrValidateMessageBuffer
0x180008228  nop     dword ptr [rax+rax+00h]
0x18000822d  test    al, al
0x18000822f  jnz     short loc_18000823B
0x180008231  mov     ebx, 0C000000Dh
0x180008236  jmp     loc_1800089EE
0x18000823b  cmp     dword ptr [rsi+0Ch], 3
0x18000823f  mov     ecx, 2
0x180008244  jnz     short loc_1800082AF
0x180008246  cmp     [rsi+10h], ebx
0x180008249  jz      short loc_1800082B4
0x18000824b  mov     r10d, 1
0x180008251  mov     r8d, [rsi+30h]
0x180008255  test    r8d, r8d
0x180008258  jz      short loc_180008293
0x18000825a  cmp     r8d, 200h
0x180008261  ja      short loc_180008231
0x180008263  mov     r9d, ecx
0x180008266  lea     rdx, [rsi+38h]
0x18000826a  mov     rcx, r14
0x18000826d  call    cs:__imp_CsrValidateMessageBuffer
0x180008274  nop     dword ptr [rax+rax+00h]
0x180008279  test    al, al
0x18000827b  jz      short loc_180008231
0x18000827d  mov     eax, [rsi+30h]
0x180008280  mov     r10d, 1
0x180008286  mov     rcx, [rsi+38h]
0x18000828a  sub     eax, r10d
0x18000828d  xor     ebx, ebx
0x18000828f  mov     [rcx+rax*2], bx
0x180008293  cmp     dword ptr [rsi+0Ch], 4
0x180008297  jnz     loc_180008350
0x18000829d  mov     ecx, ebx
0x18000829f  mov     eax, r10d
0x1800082a2  lock cmpxchg cs:g_DirtyShutdownMax, ecx
0x1800082aa  jmp     loc_18000838A
0x1800082af  cmp     [rsi+0Ch], ecx
0x1800082b2  jz      short loc_18000824B
0x1800082b4  mov     r8d, [rsi+14h]
0x1800082b8  test    r8d, r8d
0x1800082bb  jz      loc_180008231
0x1800082c1  lea     eax, [r8-1]
0x1800082c5  cmp     eax, 104h
0x1800082ca  ja      loc_180008231
0x1800082d0  mov     r9d, ecx
0x1800082d3  lea     rdx, [rsi+18h]
0x1800082d7  mov     rcx, r14
0x1800082da  call    cs:__imp_CsrValidateMessageBuffer
0x1800082e1  nop     dword ptr [rax+rax+00h]
0x1800082e6  test    al, al
0x1800082e8  jz      loc_180008231
0x1800082ee  mov     r8d, [rsi+20h]
0x1800082f2  lea     eax, [r8-1]
0x1800082f6  cmp     eax, 1Fh
0x1800082f9  ja      loc_180008231
0x1800082ff  mov     r9d, 2
0x180008305  lea     rdx, [rsi+28h]
0x180008309  mov     rcx, r14
0x18000830c  call    cs:__imp_CsrValidateMessageBuffer
0x180008313  nop     dword ptr [rax+rax+00h]
0x180008318  xor     r9d, r9d
0x18000831b  test    al, al
0x18000831d  jz      loc_180008231
0x180008323  mov     eax, [rsi+14h]
0x180008326  lea     r10d, [r9+1]
0x18000832a  mov     rcx, [rsi+18h]
0x18000832e  sub     eax, r10d
0x180008331  mov     r15, rbx
0x180008334  mov     [rcx+rax*2], r9w
0x180008339  mov     eax, [rsi+20h]
0x18000833c  mov     rcx, [rsi+28h]
0x180008340  sub     eax, r10d
0x180008343  mov     [rcx+rax*2], bx
0x180008347  lea     ecx, [r9+2]
0x18000834b  jmp     loc_180008251
0x180008350  cmp     dword ptr [rsi+0Ch], 3
0x180008354  jnz     short loc_18000835B
0x180008356  cmp     [rsi+10h], ebx
0x180008359  jnz     short loc_180008361
0x18000835b  cmp     dword ptr [rsi+0Ch], 2
0x18000835f  jnz     short loc_18000837D
0x180008361  test    edi, edi
0x180008363  jz      short loc_180008370
0x180008365  mov     eax, r10d
0x180008368  xchg    eax, cs:g_ShutdownState
0x18000836e  jmp     short loc_180008392
0x180008370  xor     eax, eax
0x180008372  lock cmpxchg cs:g_ShutdownState, r10d
0x18000837b  jmp     short loc_18000838C
0x18000837d  mov     ecx, ebx
0x18000837f  mov     eax, r10d
0x180008382  lock cmpxchg cs:g_ShutdownState, ecx
0x18000838a  test    eax, eax
0x18000838c  jz      loc_180008A51
0x180008392  mov     edx, [rsp+1C0h+cchName]
0x180008396  mov     edi, 40h ; '@'
0x18000839b  add     rdx, rdx; uBytes
0x18000839e  mov     ecx, edi; uFlags
0x1800083a0  call    cs:__imp_LocalAlloc
0x1800083a7  nop     dword ptr [rax+rax+00h]
0x1800083ac  mov     edx, [rsp+1C0h+var_160]
0x1800083b0  mov     ecx, edi; uFlags
0x1800083b2  add     rdx, rdx; uBytes
0x1800083b5  mov     [rbp+0C0h+Name], rax
0x1800083b9  call    cs:__imp_LocalAlloc
0x1800083c0  nop     dword ptr [rax+rax+00h]
0x1800083c5  mov     edx, [rsp+1C0h+nSize]
0x1800083c9  mov     ecx, edi; uFlags
0x1800083cb  add     rdx, rdx; uBytes
0x1800083ce  mov     [rsp+1C0h+var_170], rax
0x1800083d3  mov     rbx, rax
0x1800083d6  call    cs:__imp_LocalAlloc
0x1800083dd  nop     dword ptr [rax+rax+00h]
0x1800083e2  lea     edx, [rdi+40h]; uBytes
0x1800083e5  mov     ecx, edi; uFlags
0x1800083e7  mov     r12, rax
0x1800083ea  mov     [rsp+1C0h+var_168], rax
0x1800083ef  call    cs:__imp_LocalAlloc
0x1800083f6  nop     dword ptr [rax+rax+00h]
0x1800083fb  mov     rdi, [rbp+0C0h+Name]
0x1800083ff  xor     r9d, r9d
0x180008402  mov     [rbp+0C0h+hMem], rax
0x180008406  mov     r13, rax
0x180008409  test    rdi, rdi
0x18000840c  jz      loc_1800089DF
0x180008412  test    rbx, rbx
0x180008415  jz      loc_1800089DF
0x18000841b  test    r12, r12
0x18000841e  jz      loc_1800089DF
0x180008424  test    rax, rax
0x180008427  jz      loc_1800089DF
0x18000842d  cmp     [rsi+30h], r9d
0x180008431  jbe     loc_1800084C2
0x180008437  mov     edx, [rsi+30h]
0x18000843a  lea     ecx, [r9+40h]; uFlags
0x18000843e  add     rdx, rdx; uBytes
0x180008441  call    cs:__imp_LocalAlloc
0x180008448  nop     dword ptr [rax+rax+00h]
0x18000844d  xor     r10d, r10d
0x180008450  mov     [rbp+0C0h+var_140], rax
0x180008454  mov     r15, rax
0x180008457  test    rax, rax
0x18000845a  jz      loc_1800089DF
0x180008460  mov     eax, [rsi+30h]
0x180008463  test    rax, rax
0x180008466  jz      short loc_1800084C2
0x180008468  cmp     rax, 7FFFFFFFh
0x18000846e  jbe     short loc_180008476
0x180008470  mov     [r15], r10w
0x180008474  jmp     short loc_1800084C2
0x180008476  mov     r8, [rsi+38h]
0x18000847a  mov     ecx, 7FFFFFFEh
0x18000847f  mov     rdx, r15
0x180008482  mov     r13d, 2
0x180008488  test    rcx, rcx
0x18000848b  jz      short loc_1800084AF
0x18000848d  movzx   r9d, word ptr [r8]
0x180008491  test    r9w, r9w
0x180008495  jz      short loc_1800084AF
0x180008497  mov     [rdx], r9w
0x18000849b  add     r8, r13
0x18000849e  mov     r9d, 1
0x1800084a4  add     rdx, r13
0x1800084a7  sub     rcx, r9
0x1800084aa  sub     rax, r9
0x1800084ad  jnz     short loc_180008488
0x1800084af  mov     r13, [rbp+0C0h+hMem]
0x1800084b3  lea     rcx, [rdx-2]
0x1800084b7  test    rax, rax
0x1800084ba  cmovnz  rcx, rdx
0x1800084be  mov     [rcx], r10w
0x1800084c2  mov     rcx, [rbp+0C0h+Sid]; Sid
0x1800084c6  lea     rax, [rbp+0C0h+var_120]
0x1800084ca  mov     [rsp+1C0h+peUse], rax; peUse
0x1800084cf  lea     r8, [rsp+1C0h+cchName]; cchName
0x1800084d4  lea     rax, [rsp+1C0h+var_160]
0x1800084d9  mov     r9, rbx; ReferencedDomainName
0x1800084dc  mov     rdx, rdi; Name
0x1800084df  mov     [rsp+1C0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800084e4  call    cs:__imp_LookupAccountSidLocalW
0x1800084eb  nop     dword ptr [rax+rax+00h]
0x1800084f0  xor     r8d, r8d
0x1800084f3  test    eax, eax
0x1800084f5  jnz     short loc_180008501
0x1800084f7  mov     [rbx], r8w
0x1800084fb  mov     [rdi], r8w
0x1800084ff  jmp     short loc_18000854B
0x180008501  mov     [rdi+208h], r8w
0x180008509  mov     [rbx+208h], r8w
0x180008511  mov     ecx, [rsp+1C0h+cchName]
0x180008515  mov     edx, [rsp+1C0h+var_160]
0x180008519  add     ecx, edx
0x18000851b  cmp     ecx, 103h
0x180008521  jbe     short loc_18000852D
0x180008523  mov     ebx, 0C0000001h
0x180008528  jmp     loc_1800089E4
0x18000852d  test    edx, edx
0x18000852f  jz      short loc_180008540
0x180008531  lea     r8, asc_180016630; "\\"
0x180008538  mov     rcx, rbx
0x18000853b  call    RtlStringCchCatW
0x180008540  mov     r8, rdi
0x180008543  mov     rcx, rbx
0x180008546  call    RtlStringCchCatW
0x18000854b  lea     rdx, [rsp+1C0h+nSize]; nSize
0x180008550  mov     rcx, r12; lpBuffer
0x180008553  call    cs:__imp_GetComputerNameW
0x18000855a  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
