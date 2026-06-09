# CWakeTimer::StartWakeTimer(ulong,ulong,void *,void (*)(void *,_CBROKERED_EVENT_ID,void *,void *,ulong,ulong,_BI_ACTIVATION_STATUS *),void * *)

- ea: `0x180082a18`
- end: `0x18008306d`
- name: `?StartWakeTimer@CWakeTimer@@SAJKKPEAXP6AX0U_CBROKERED_EVENT_ID@@00KKPEAW4_BI_ACTIVATION_STATUS@@@ZPEAPEAX@Z`
- size: `1621`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, void *, void (__high *)(void *, struct _CBROKERED_EVENT_ID, void *, void *, unsigned int, unsigned int, enum _BI_ACTIVATION_STATUS *), void **)`
- caller_count: `4`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002d7a4`
- `0x1800742d4`
- `0x180082930`
- `0x18008f024`

## callees

- `0x180007440`
- `0x180007924`
- `0x180008294`
- `0x180008a9c`
- `0x18000fddc`
- `0x18000fe2c`
- `0x18000fe54`
- `0x180082a18`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082af8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082bbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082d12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082af8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082bbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082d12`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180082ad7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180082ad7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180082aea`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180082aea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180083002`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180083002`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180082e32`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180082e32`
- `EventAggregation!EaCreateAggregatedEvent` at `0x180082f3a`
- `EventAggregation!EaCreateAggregatedEvent` at `0x180082f3a`
- `ntdll!RtlNtStatusToDosError` at `0x180082f4a`
- `ntdll!RtlNtStatusToDosError` at `0x180082f4a`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180082da4`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180082da4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180082bb0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180082d04`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180082bb0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180082d04`

## string_xrefs

- `0x180082b4c`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\waketimerwrapper.cpp`
- `0x180082c17`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\waketimerwrapper.cpp`
- `0x180082caa`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\waketimerwrapper.cpp`
- `0x180082d69`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\waketimerwrapper.cpp`
- `0x180082def`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\waketimerwrapper.cpp`
- `0x180082fa1`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\waketimerwrapper.cpp`

## pseudocode

```c
__int64 __fastcall CWakeTimer::StartWakeTimer(
        unsigned int a1,
        unsigned int a2,
        void *a3,
        void (__high *a4)(void *, struct _CBROKERED_EVENT_ID, void *, void *, unsigned int, unsigned int, enum _BI_ACTIVATION_STATUS *),
        void **a5)
{
  __int64 v6; // r15
  unsigned int v8; // ebx
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  PVOID *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  signed int v14; // eax
  PSID *v15; // rax
  PSID *v16; // rdi
  signed int v17; // eax
  const struct std::nothrow_t *v18; // rdx
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // r9
  NTSTATUS AggregatedEvent; // eax
  signed int v23; // eax
  int ReturnLength; // [rsp+20h] [rbp-E0h]
  int ReturnLengtha; // [rsp+20h] [rbp-E0h]
  int ReturnLengthb; // [rsp+20h] [rbp-E0h]
  DWORD TokenInformationLength; // [rsp+50h] [rbp-B0h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp-A8h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+60h] [rbp-A0h] BYREF
  struct _FILETIME v31; // [rsp+68h] [rbp-98h]
  _QWORD v32[10]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v33[4]; // [rsp+C0h] [rbp-40h] BYREF
  const wchar_t *v34; // [rsp+E0h] [rbp-20h] BYREF
  _DWORD v35[6]; // [rsp+E8h] [rbp-18h] BYREF
  const wchar_t *v36; // [rsp+100h] [rbp+0h]
  int v37; // [rsp+108h] [rbp+8h]
  __int64 v38; // [rsp+110h] [rbp+10h]
  const wchar_t *v39; // [rsp+120h] [rbp+20h]
  int v40; // [rsp+128h] [rbp+28h]
  int v41; // [rsp+130h] [rbp+30h]
  const wchar_t *v42; // [rsp+140h] [rbp+40h]
  int v43; // [rsp+148h] [rbp+48h]
  unsigned int v44; // [rsp+150h] [rbp+50h]
  const wchar_t *v45; // [rsp+160h] [rbp+60h]
  int v46; // [rsp+168h] [rbp+68h]
  const wchar_t *v47; // [rsp+170h] [rbp+70h]
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  v6 = a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_03ea58026b6b32dbcd789d1e98aae4a4_Traceguids);
  }
  v8 = 0;
  TokenHandle = 0;
  TokenInformationLength = 0;
  SystemTimeAsFileTime = 0;
  memset_0(v32, 0, 0x48u);
  memset(v33, 0, sizeof(v33));
  v34 = 0;
  memset_0(v35, 0, 0x98u);
  *a5 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( (v8 & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_03ea58026b6b32dbcd789d1e98aae4a4_Traceguids, v8);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x25,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\waketimerwrapper.cpp",
        (const char *)v8,
        ReturnLength);
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v12 = 12;
LABEL_16:
        v13 = v8;
LABEL_17:
        WPP_SF_d(v11[2], v12, WPP_03ea58026b6b32dbcd789d1e98aae4a4_Traceguids, v13);
LABEL_72:
        v11 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_73;
      }
      goto LABEL_73;
    }
  }
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
    goto LABEL_31;
  v14 = GetLastError();
  v8 = v14;
  if ( v14 == 122 )
  {
    v8 = 0;
    goto LABEL_31;
  }
  if ( v14 > 0 )
    v8 = (unsigned __int16)v14 | 0x80070000;
  if ( (v8 & 0x80000000) == 0 )
  {
LABEL_31:
    v15 = (PSID *)operator new[](TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
    v16 = v15;
    if ( !v15 )
    {
      v8 = -2147024882;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_03ea58026b6b32dbcd789d1e98aae4a4_Traceguids, 2147942414LL);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x3D,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\waketimerwrapper.cpp",
        (const char *)0x8007000ELL,
        ReturnLengtha);
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v12 = 16;
        v13 = 2147942414LL;
        goto LABEL_17;
      }
      goto LABEL_73;
    }
    if ( GetTokenInformation(TokenHandle, TokenUser, v15, TokenInformationLength, &TokenInformationLength) )
      goto LABEL_82;
    v17 = GetLastError();
    v8 = v17;
    if ( v17 > 0 )
      v8 = (unsigned __int16)v17 | 0x80070000;
    if ( (v8 & 0x80000000) == 0 )
    {
LABEL_82:
      if ( !IsValidSid(*v16) )
      {
        v8 = -2147467259;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            19,
            WPP_03ea58026b6b32dbcd789d1e98aae4a4_Traceguids,
            2147500037LL);
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x4D,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\waketimerwrapper.cpp",
          (const char *)0x80004005LL,
          ReturnLengthb);
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
          goto LABEL_71;
        v20 = 20;
        v21 = 2147500037LL;
        goto LABEL_70;
      }
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      v31 = SystemTimeAsFileTime;
      v34 = L"Type";
      v36 = L"InitialDueTime";
      v39 = L"WakeEnabled";
      v42 = L"WindowInSeconds";
      v37 = 1;
      v41 = 1;
      *(_QWORD *)((char *)v33 + 4) = *(_QWORD *)&GUID_TIME_BROKER.Data2;
      v45 = L"ClientId";
      HIDWORD(v33[1]) = *(_DWORD *)&GUID_TIME_BROKER.Data4[4];
      LOWORD(v33[2]) = 5;
      v38 = *(_QWORD *)&SystemTimeAsFileTime + 10000 * v6;
      v33[3] = &v34;
      v44 = a2 / 0x3E8;
      v47 = L"WnsClientConnectionProvider";
      v32[7] = L"WnsClientConnectionProvider";
      v32[0] = v33;
      v35[0] = 0;
      v35[2] = 4;
      v40 = 0;
      v43 = 0;
      v46 = 2;
      LODWORD(v33[0]) = -1244867089;
      v32[8] = *v16;
      AggregatedEvent = EaCreateAggregatedEvent(v32, 0, a4, 0);
      if ( AggregatedEvent >= 0 )
        goto LABEL_71;
      v23 = RtlNtStatusToDosError(AggregatedEvent);
      v8 = v23;
      if ( v23 > 0 )
        v8 = (unsigned __int16)v23 | 0x80070000;
      if ( (v8 & 0x80000000) == 0 )
        goto LABEL_71;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_03ea58026b6b32dbcd789d1e98aae4a4_Traceguids, v8);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x88,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\waketimerwrapper.cpp",
        (const char *)v8,
        0);
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_71;
      v20 = 22;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_03ea58026b6b32dbcd789d1e98aae4a4_Traceguids, v8);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x45,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\waketimerwrapper.cpp",
        (const char *)v8,
        ReturnLengthb);
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_71;
      v20 = 18;
    }
    v21 = v8;
LABEL_70:
    WPP_SF_d(v19[2], v20, WPP_03ea58026b6b32dbcd789d1e98aae4a4_Traceguids, v21);
LABEL_71:
    operator delete(v16, v18);
    goto LABEL_72;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_03ea58026b6b32dbcd789d1e98aae4a4_Traceguids, v8);
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x30,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\waketimerwrapper.cpp",
    (const char *)v8,
    ReturnLengtha);
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    v12 = 14;
    goto LABEL_16;
  }
LABEL_73:
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    v11 = (PVOID *)WPP_GLOBAL_Control;
    TokenHandle = 0;
  }
  if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 8) != 0 && *((_BYTE *)v11 + 25) >= 6u )
    WPP_SF_d(v11[2], 23, WPP_03ea58026b6b32dbcd789d1e98aae4a4_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x180082a18  mov     [rsp-8+arg_0], rbx
0x180082a1d  push    rbp
0x180082a1e  push    rsi
0x180082a1f  push    rdi
0x180082a20  push    r12
0x180082a22  push    r13
0x180082a24  push    r14
0x180082a26  push    r15
0x180082a28  lea     rbp, [rsp-90h]
0x180082a30  sub     rsp, 190h
0x180082a37  mov     rax, cs:__security_cookie
0x180082a3e  xor     rax, rsp
0x180082a41  mov     [rbp+0C0h+var_40], rax
0x180082a48  mov     rsi, [rbp+0C0h+arg_20]
0x180082a4f  mov     r13, r9
0x180082a52  mov     r12, r8
0x180082a55  mov     r15d, ecx
0x180082a58  mov     r14d, edx
0x180082a5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180082a62  lea     rdi, WPP_GLOBAL_Control
0x180082a69  cmp     rcx, rdi
0x180082a6c  jz      short loc_180082A8F
0x180082a6e  test    byte ptr [rcx+1Ch], 8
0x180082a72  jz      short loc_180082A8F
0x180082a74  cmp     byte ptr [rcx+19h], 6
0x180082a78  jb      short loc_180082A8F
0x180082a7a  mov     rcx, [rcx+10h]
0x180082a7e  lea     r8, WPP_03ea58026b6b32dbcd789d1e98aae4a4_Traceguids
0x180082a85  mov     edx, 0Ah
0x180082a8a  call    WPP_SF_
0x180082a8f  xor     ebx, ebx
0x180082a91  lea     rcx, [rsp+1C0h+var_150]; void *
0x180082a96  xor     edx, edx; Val
0x180082a98  mov     [rsp+1C0h+TokenHandle], rbx
0x180082a9d  mov     [rsp+1C0h+TokenInformationLength], ebx
0x180082aa1  mov     qword ptr [rsp+1C0h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x180082aa6  lea     r8d, [rbx+48h]; Size
0x180082aaa  call    memset_0
0x180082aaf  xorps   xmm0, xmm0
0x180082ab2  mov     [rbp+0C0h+var_100], ebx
0x180082ab5  xor     eax, eax
0x180082ab7  lea     rcx, [rbp+0C0h+var_D8]; void *
0x180082abb  movups  [rbp+0C0h+var_FC], xmm0
0x180082abf  xor     edx, edx; Val
0x180082ac1  mov     [rbp+0C0h+var_E0], rax
0x180082ac5  mov     r8d, 98h; Size
0x180082acb  movups  [rbp+0C0h+var_FC+0Ch], xmm0
0x180082acf  call    memset_0
0x180082ad4  mov     [rsi], rbx
0x180082ad7  call    cs:__imp_GetCurrentProcess
0x180082add  lea     r8, [rsp+1C0h+TokenHandle]; TokenHandle
0x180082ae2  mov     edx, 20008h; DesiredAccess
0x180082ae7  mov     rcx, rax; ProcessHandle
0x180082aea  call    cs:__imp_OpenProcessToken
0x180082af0  test    eax, eax
0x180082af2  jnz     loc_180082B97
0x180082af8  call    cs:__imp_GetLastError
0x180082afe  mov     ebx, eax
0x180082b00  test    eax, eax
0x180082b02  jle     short loc_180082B0D
0x180082b04  movzx   ebx, ax
0x180082b07  or      ebx, 80070000h
0x180082b0d  test    ebx, ebx
0x180082b0f  jns     loc_180082B97
0x180082b15  mov     rcx, cs:WPP_GLOBAL_Control
0x180082b1c  cmp     rcx, rdi
0x180082b1f  jz      short loc_180082B45
0x180082b21  test    byte ptr [rcx+1Ch], 8
0x180082b25  jz      short loc_180082B45
0x180082b27  cmp     byte ptr [rcx+19h], 2
0x180082b2b  jb      short loc_180082B45
0x180082b2d  mov     rcx, [rcx+10h]
0x180082b31  lea     r8, WPP_03ea58026b6b32dbcd789d1e98aae4a4_Traceguids
0x180082b38  mov     edx, 0Bh
0x180082b3d  mov     r9d, ebx
0x180082b40  call    WPP_SF_d
0x180082b45  mov     rcx, [rbp+0C8h]; this
0x180082b4c  lea     r8, aOnecoreuapBase_30; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180082b53  mov     r9d, ebx; char *
0x180082b56  mov     edx, 25h ; '%'; void *
0x180082b5b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180082b60  mov     rcx, cs:WPP_GLOBAL_Control
0x180082b67  cmp     rcx, rdi
0x180082b6a  jz      loc_180082FF5
0x180082b70  test    byte ptr [rcx+1Ch], 80h
0x180082b74  jz      loc_180082FF5
0x180082b7a  mov     edx, 0Ch
0x180082b7f  mov     r9d, ebx
0x180082b82  mov     rcx, [rcx+10h]
0x180082b86  lea     r8, WPP_03ea58026b6b32dbcd789d1e98aae4a4_Traceguids
0x180082b8d  call    WPP_SF_d
0x180082b92  jmp     loc_180082FEE
0x180082b97  mov     rcx, [rsp+1C0h+TokenHandle]; TokenHandle
0x180082b9c  lea     rax, [rsp+1C0h+TokenInformationLength]
0x180082ba1  xor     r9d, r9d; TokenInformationLength
0x180082ba4  mov     [rsp+1C0h+ReturnLength], rax; int
0x180082ba9  xor     r8d, r8d; TokenInformation
0x180082bac  lea     edx, [r9+1]; TokenInformationClass
0x180082bb0  call    cs:__imp_GetTokenInformation
0x180082bb6  test    eax, eax
0x180082bb8  jnz     loc_180082C51
0x180082bbe  call    cs:__imp_GetLastError
0x180082bc4  mov     ebx, eax
0x180082bc6  cmp     eax, 7Ah ; 'z'
0x180082bc9  jz      loc_180082C4F
0x180082bcf  test    eax, eax
0x180082bd1  jle     short loc_180082BDC
0x180082bd3  movzx   ebx, ax
0x180082bd6  or      ebx, 80070000h
0x180082bdc  test    ebx, ebx
0x180082bde  jns     short loc_180082C51
0x180082be0  mov     rcx, cs:WPP_GLOBAL_Control
0x180082be7  cmp     rcx, rdi
0x180082bea  jz      short loc_180082C10
0x180082bec  test    byte ptr [rcx+1Ch], 8
0x180082bf0  jz      short loc_180082C10
0x180082bf2  cmp     byte ptr [rcx+19h], 2
0x180082bf6  jb      short loc_180082C10
0x180082bf8  mov     rcx, [rcx+10h]
0x180082bfc  lea     r8, WPP_03ea58026b6b32dbcd789d1e98aae4a4_Traceguids
0x180082c03  mov     edx, 0Dh
0x180082c08  mov     r9d, ebx
0x180082c0b  call    WPP_SF_d
0x180082c10  mov     rcx, [rbp+0C8h]; this
0x180082c17  lea     r8, aOnecoreuapBase_30; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180082c1e  mov     r9d, ebx; char *
0x180082c21  mov     edx, 30h ; '0'; void *
0x180082c26  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180082c2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180082c32  cmp     rcx, rdi
0x180082c35  jz      loc_180082FF5
0x180082c3b  test    byte ptr [rcx+1Ch], 80h
0x180082c3f  jz      loc_180082FF5
0x180082c45  mov     edx, 0Eh
0x180082c4a  jmp     loc_180082B7F
0x180082c4f  xor     ebx, ebx
0x180082c51  mov     ecx, [rsp+1C0h+TokenInformationLength]; unsigned __int64
0x180082c55  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180082c5c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180082c61  mov     rdi, rax
0x180082c64  test    rax, rax
0x180082c67  jnz     short loc_180082CE8
0x180082c69  mov     ebx, 8007000Eh
0x180082c6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180082c75  lea     rdi, WPP_GLOBAL_Control
0x180082c7c  cmp     rcx, rdi
0x180082c7f  jz      short loc_180082CA3
0x180082c81  test    byte ptr [rcx+1Ch], 8
0x180082c85  jz      short loc_180082CA3
0x180082c87  cmp     byte ptr [rcx+19h], 2
0x180082c8b  jb      short loc_180082CA3
0x180082c8d  mov     rcx, [rcx+10h]
0x180082c91  lea     edx, [rax+0Fh]
0x180082c94  mov     r9d, ebx
0x180082c97  lea     r8, WPP_03ea58026b6b32dbcd789d1e98aae4a4_Traceguids
0x180082c9e  call    WPP_SF_d
0x180082ca3  mov     rcx, [rbp+0C8h]; this
0x180082caa  lea     r8, aOnecoreuapBase_30; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180082cb1  mov     r9d, ebx; char *
0x180082cb4  mov     edx, 3Dh ; '='; void *
0x180082cb9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180082cbe  mov     rcx, cs:WPP_GLOBAL_Control
0x180082cc5  cmp     rcx, rdi
0x180082cc8  jz      loc_180082FF5
0x180082cce  test    byte ptr [rcx+1Ch], 80h
0x180082cd2  jz      loc_180082FF5
0x180082cd8  mov     edx, 10h
0x180082cdd  mov     r9d, 8007000Eh
0x180082ce3  jmp     loc_180082B82
0x180082ce8  mov     r9d, [rsp+1C0h+TokenInformationLength]; TokenInformationLength
0x180082ced  lea     rax, [rsp+1C0h+TokenInformationLength]
0x180082cf2  mov     rcx, [rsp+1C0h+TokenHandle]; TokenHandle
0x180082cf7  mov     r8, rdi; TokenInformation
0x180082cfa  mov     edx, 1; TokenInformationClass
0x180082cff  mov     [rsp+1C0h+ReturnLength], rax; int
0x180082d04  call    cs:__imp_GetTokenInformation
0x180082d0a  test    eax, eax
0x180082d0c  jnz     loc_180082DA1
0x180082d12  call    cs:__imp_GetLastError
0x180082d18  mov     ebx, eax
0x180082d1a  test    eax, eax
0x180082d1c  jle     short loc_180082D27
0x180082d1e  movzx   ebx, ax
0x180082d21  or      ebx, 80070000h
0x180082d27  test    ebx, ebx
0x180082d29  jns     short loc_180082DA1
0x180082d2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180082d32  lea     rsi, WPP_GLOBAL_Control
0x180082d39  cmp     rcx, rsi
0x180082d3c  jz      short loc_180082D62
0x180082d3e  test    byte ptr [rcx+1Ch], 8
0x180082d42  jz      short loc_180082D62
0x180082d44  cmp     byte ptr [rcx+19h], 2
0x180082d48  jb      short loc_180082D62
0x180082d4a  mov     rcx, [rcx+10h]
0x180082d4e  lea     r8, WPP_03ea58026b6b32dbcd789d1e98aae4a4_Traceguids
0x180082d55  mov     edx, 11h
0x180082d5a  mov     r9d, ebx
0x180082d5d  call    WPP_SF_d
0x180082d62  mov     rcx, [rbp+0C8h]; this
0x180082d69  lea     r8, aOnecoreuapBase_30; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180082d70  mov     r9d, ebx; char *
0x180082d73  mov     edx, 45h ; 'E'; void *
0x180082d78  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180082d7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180082d84  cmp     rcx, rsi
0x180082d87  jz      loc_180082FDF
0x180082d8d  test    byte ptr [rcx+1Ch], 80h
0x180082d91  jz      loc_180082FDF
0x180082d97  mov     edx, 12h
0x180082d9c  jmp     loc_180082FCC
0x180082da1  mov     rcx, [rdi]; pSid
0x180082da4  call    cs:__imp_IsValidSid
0x180082daa  test    eax, eax
0x180082dac  jnz     short loc_180082E2D
0x180082dae  mov     ebx, 80004005h
0x180082db3  mov     rcx, cs:WPP_GLOBAL_Control
0x180082dba  lea     rsi, WPP_GLOBAL_Control
0x180082dc1  cmp     rcx, rsi
0x180082dc4  jz      short loc_180082DE8
0x180082dc6  test    byte ptr [rcx+1Ch], 8
0x180082dca  jz      short loc_180082DE8
0x180082dcc  cmp     byte ptr [rcx+19h], 2
0x180082dd0  jb      short loc_180082DE8
0x180082dd2  mov     rcx, [rcx+10h]
0x180082dd6  lea     edx, [rax+13h]
0x180082dd9  mov     r9d, ebx
0x180082ddc  lea     r8, WPP_03ea58026b6b32dbcd789d1e98aae4a4_Traceguids
0x180082de3  call    WPP_SF_d
0x180082de8  mov     rcx, [rbp+0C8h]; this
0x180082def  lea     r8, aOnecoreuapBase_30; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180082df6  mov     r9d, ebx; char *
0x180082df9  mov     edx, 4Dh ; 'M'; void *
0x180082dfe  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180082e03  mov     rcx, cs:WPP_GLOBAL_Control
0x180082e0a  cmp     rcx, rsi
0x180082e0d  jz      loc_180082FDF
0x180082e13  test    byte ptr [rcx+1Ch], 80h
0x180082e17  jz      loc_180082FDF
0x180082e1d  mov     edx, 14h
0x180082e22  mov     r9d, 80004005h
0x180082e28  jmp     loc_180082FCF
0x180082e2d  lea     rcx, [rsp+1C0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180082e32  call    cs:__imp_GetSystemTimeAsFileTime
0x180082e38  mov     eax, [rsp+1C0h+SystemTimeAsFileTime.dwHighDateTime]
0x180082e3c  mov     edx, 1
0x180082e41  movsd   xmm0, qword ptr cs:GUID_TIME_BROKER.Data2
0x180082e49  xor     r9d, r9d
0x180082e4c  mov     dword ptr [rsp+1C0h+var_158+4], eax
0x180082e50  mov     r8, r13
0x180082e53  mov     eax, [rsp+1C0h+SystemTimeAsFileTime.dwLowDateTime]
0x180082e57  mov     dword ptr [rsp+1C0h+var_158], eax
0x180082e5b  lea     rax, aType; "Type"
0x180082e62  mov     [rbp+0C0h+var_E0], rax
0x180082e66  lea     rax, aInitialduetime; "InitialDueTime"
0x180082e6d  mov     [rbp+0C0h+var_C0], rax
0x180082e71  lea     rax, aWakeenabled; "WakeEnabled"
0x180082e78  mov     [rbp+0C0h+var_A0], rax
0x180082e7c  lea     rax, aWindowinsecond; "WindowInSeconds"
0x180082e83  mov     [rbp+0C0h+var_80], rax
0x180082e87  mov     eax, 10624DD3h
0x180082e8c  mov     [rbp+0C0h+var_B8], edx
0x180082e8f  mov     [rbp+0C0h+var_90], edx
0x180082e92  mul     r14d
0x180082e95  imul    rcx, r15, 2710h
0x180082e9c  movsd   qword ptr [rbp+0C0h+var_FC], xmm0
0x180082ea1  mov     [rsp+1C0h+var_180], rsi
0x180082ea6  lea     rax, aClientid; "ClientId"
0x180082ead  xor     r15d, r15d
0x180082eb0  mov     [rbp+0C0h+var_60], rax
0x180082eb4  mov     eax, dword ptr cs:GUID_TIME_BROKER.Data4+4
0x180082eba  mov     dword ptr [rbp+0C0h+var_FC+8], eax
0x180082ebd  shr     edx, 6
0x180082ec0  add     rcx, [rsp+1C0h+var_158]
0x180082ec5  lea     eax, [r15+5]
0x180082ec9  mov     word ptr [rbp+0C0h+var_FC+0Ch], ax
0x180082ecd  lea     rax, [rbp+0C0h+var_E0]
0x180082ed1  mov     [rbp+0C0h+var_B0], rcx
0x180082ed5  lea     rcx, aWnsclientconne; "WnsClientConnectionProvider"
0x180082edc  mov     [rbp+0C0h+var_E8], rax
0x180082ee0  lea     rax, [rbp+0C0h+var_100]
0x180082ee4  mov     [rbp+0C0h+var_70], edx
0x180082ee7  xor     edx, edx
0x180082ee9  mov     [rbp+0C0h+var_50], rcx
0x180082eed  mov     [rbp+0C0h+var_118], rcx
0x180082ef1  lea     rcx, [rsp+1C0h+var_150]
0x180082ef6  mov     [rsp+1C0h+var_188], r15d
0x180082efb  mov     [rsp+1C0h+var_150], rax
0x180082f00  mov     [rbp+0C0h+var_D8], 0
0x180082f07  mov     [rbp+0C0h+var_D0], 4
0x180082f0e  mov     [rbp+0C0h+var_98], r15d
0x180082f12  mov     [rbp+0C0h+var_78], r15d
0x180082f16  mov     [rbp+0C0h+var_58], 2
0x180082f1d  mov     [rbp+0C0h+var_100], 0B5CCD5EFh
0x180082f24  mov     rax, [rdi]
0x180082f27  mov     [rsp+1C0h+var_190], r12
0x180082f2c  mov     [rsp+1C0h+var_198], r15
0x180082f31  mov     [rbp+0C0h+var_110], rax
0x180082f35  mov     [rsp+1C0h+ReturnLength], r15; int
0x180082f3a  call    cs:__imp_EaCreateAggregatedEvent
  ... truncated ...
```
