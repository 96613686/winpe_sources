# Public_WinStationQueryInformationW(void *,ulong,_WINSTATIONINFOCLASS,void *,ulong,ulong *)

- ea: `0x18000c820`
- end: `0x18000ce4c`
- name: `?Public_WinStationQueryInformationW@@YAEPEAXKW4_WINSTATIONINFOCLASS@@0KPEAK@Z`
- size: `1580`
- prototype: `unsigned __int8 __fastcall(CPublicBinding *this, unsigned int, enum _WINSTATIONINFOCLASS, struct _WINSTATIONLOADINDICATORDATA *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800142c0`

## callees

- `0x180003ba8`
- `0x180004554`
- `0x180004a30`
- `0x180005374`
- `0x180005fcc`
- `0x1800063e0`
- `0x180007890`
- `0x180007d10`
- `0x180008290`
- `0x180008340`
- `0x180008e30`
- `0x180009da0`
- `0x18000c820`
- `0x18000ce54`
- `0x18000d2e8`
- `0x18000d51c`
- `0x1800230b8`
- `0x1800230ec`
- `0x18002cd00`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000ce39`
- `ntdll!RtlNtStatusToDosError` at `0x18000ce39`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cae6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cb7c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cd89`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cdc9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ce29`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ce41`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cae6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cb7c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cd89`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cdc9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ce29`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ce41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c97f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cc04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ccab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ccb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cd42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c97f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cc04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ccab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ccb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cd42`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000c990`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000c990`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000c975`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000c975`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000c9a3`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000c9a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000c95c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000c95c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c9fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c9fa`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c9d3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c9d3`

## string_xrefs

- `0x18000caf8`: `StringCchCopy failed: %x`
- `0x18000cc1c`: `GetTokenInformation failed: 0x%x`
- `0x18000ccce`: `OpenProcessToken failed: 0x%x`
- `0x18000cde9`: `Failed to open binding`
- `0x18000cd5a`: `OpenThreadToken failed: 0x%x`
- `0x18000cb27`: `GetCurrentSessionConfigData failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall Public_WinStationQueryInformationW(
        CPublicBinding *this,
        ULONG SessionId,
        unsigned int a3,
        struct _WINSTATIONINFORMATIONW *a4,
        unsigned int a5,
        unsigned int *a6)
{
  unsigned __int64 v7; // rsi
  CPublicBinding *v10; // rax
  CPublicBinding *v11; // rbx
  _WORD *v12; // rax
  _WORD *v13; // r9
  __int64 v14; // rcx
  int *v15; // rdx
  __int64 v16; // r10
  _WORD *v17; // rcx
  int v18; // edi
  __int64 v19; // rcx
  int v20; // edi
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  signed int v23; // ebp
  unsigned __int8 InformationW; // di
  unsigned int *v25; // r8
  int CurrentSessionInformation; // ebx
  int v28; // esi
  int v29; // esi
  DWORD v30; // eax
  signed int LastError; // eax
  signed int v32; // eax
  signed int v33; // eax
  DWORD v34; // eax
  DWORD v35; // eax
  ULONG v36; // eax
  void *TokenHandle; // [rsp+30h] [rbp-D8h] BYREF
  DWORD ReturnLength; // [rsp+38h] [rbp-D0h] BYREF
  unsigned __int16 v39[4]; // [rsp+40h] [rbp-C8h] BYREF
  CPublicBinding *v40; // [rsp+48h] [rbp-C0h]
  _BYTE v41[184]; // [rsp+50h] [rbp-B8h] BYREF
  int TokenInformation; // [rsp+110h] [rbp+8h] BYREF

  *(_QWORD *)v39 = 0;
  v7 = a3;
  if ( this )
  {
    v11 = this;
    v40 = this;
    if ( *(_WORD *)this && !*((_DWORD *)this + 12) )
      goto LABEL_58;
  }
  else
  {
    v10 = (CPublicBinding *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
    v11 = v10;
    if ( v10 )
    {
      *(_QWORD *)v10 = 0;
      *((_QWORD *)v10 + 1) = 0;
      *((_QWORD *)v10 + 2) = 0;
      *((_QWORD *)v10 + 3) = 0;
      *((_QWORD *)v10 + 4) = 0;
      *((_QWORD *)v10 + 5) = 0;
      *((_QWORD *)v10 + 6) = 1;
      *((_QWORD *)v10 + 7) = 0;
      v12 = operator new[](2u, (const struct std::nothrow_t *)&std::nothrow);
      *((_QWORD *)v11 + 5) = v12;
      v13 = v12;
      if ( v12 )
      {
        v14 = 2147483646;
        v15 = &dword_18003D0CC;
        v16 = 1;
        do
        {
          if ( !v14 )
            break;
          if ( !*(_WORD *)v15 )
            break;
          *v13 = *(_WORD *)v15;
          v15 = (int *)((char *)v15 + 2);
          ++v13;
          --v14;
          --v16;
        }
        while ( v16 );
        v17 = v13 - 1;
        v18 = -2147024774;
        if ( v16 )
        {
          v17 = v13;
          v18 = 0;
        }
        *v17 = 0;
        if ( v16 )
        {
          if ( !*((_QWORD *)v11 + 3) && !*((_DWORD *)v11 + 12) )
          {
            if ( (unsigned int)CPublicBinding::OpenSessionContextHandle((RPC_BINDING_HANDLE *)v11) == -2147023174 )
              *((_DWORD *)v11 + 13) = 1;
            CPublicBinding::CloseSessionContextHandle(v11);
          }
        }
        else
        {
          ConvertHRESULT2WIN32(v18);
          _DbgPrintMessage(8, "StringCchCopy failed: %x", v18);
        }
      }
      v40 = v11;
      *(_DWORD *)&v39[2] = 1;
    }
    else
    {
      v11 = 0;
      v40 = 0;
      SetLastError(0xEu);
      _DbgPrintMessage(8, "new CPublicBinding");
    }
  }
  if ( (unsigned int)v7 > 0x27 )
    goto LABEL_58;
  v19 = 0x8000000142LL;
  if ( !_bittest64(&v19, v7) )
    goto LABEL_58;
  TokenInformation = -1;
  TokenHandle = 0;
  ReturnLength = 0;
  if ( SessionId == -1 )
    goto LABEL_26;
  v20 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    goto LABEL_20;
  if ( GetLastError() == 1008 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    {
LABEL_20:
      if ( GetTokenInformation(TokenHandle, TokenSessionId, &TokenInformation, 4u, &ReturnLength) )
      {
        v23 = 0;
        LOBYTE(v20) = TokenInformation == SessionId;
      }
      else
      {
        LastError = GetLastError();
        v23 = LastError;
        if ( LastError > 0 )
          v23 = (unsigned __int16)LastError | 0x80070000;
        _DbgPrintMessage(8, "GetTokenInformation failed: 0x%x", v23);
      }
      goto LABEL_22;
    }
    v32 = GetLastError();
    v23 = v32;
    if ( v32 > 0 )
      v23 = (unsigned __int16)v32 | 0x80070000;
    _DbgPrintMessage(8, "OpenProcessToken failed: 0x%x", v23);
  }
  else
  {
    v33 = GetLastError();
    v23 = v33;
    if ( v33 > 0 )
      v23 = (unsigned __int16)v33 | 0x80070000;
    _DbgPrintMessage(8, "OpenThreadToken failed: 0x%x", v23);
  }
LABEL_22:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v23 < 0 )
  {
    _DbgPrintMessage(8, "CUtils::IsCurrentSession failed: 0x%x in %s", v23, "Public_WinStationQueryInformationW");
    v30 = ConvertHRESULT2WIN32(v23);
    SetLastError(v30);
    InformationW = 0;
    goto LABEL_36;
  }
  if ( v20 )
  {
LABEL_26:
    InformationW = 0;
    if ( a4 )
    {
      v25 = a6;
      if ( a6 )
      {
        *a6 = 0;
        if ( (_DWORD)v7 == 8 )
        {
          CurrentSessionInformation = GetCurrentSessionInformation(a4, a5, v25);
          if ( CurrentSessionInformation >= 0 )
          {
LABEL_30:
            InformationW = 1;
            goto LABEL_36;
          }
          _DbgPrintMessage(
            8,
            "GetCurrentSessionInformation failed: 0x%x in %s",
            (unsigned int)CurrentSessionInformation,
            "WinStationQueryCurrentSessionInformation");
LABEL_75:
          v34 = ConvertHRESULT2WIN32(CurrentSessionInformation);
          SetLastError(v34);
          goto LABEL_36;
        }
        v28 = v7 - 1;
        if ( !v28 )
        {
          CurrentSessionInformation = GetCurrentSessionConfigData((struct _WINSTATIONCONFIGW *)a4, a5, v25);
          if ( CurrentSessionInformation >= 0 )
            goto LABEL_30;
          _DbgPrintMessage(
            8,
            "GetCurrentSessionConfigData failed: 0x%x in %s",
            (unsigned int)CurrentSessionInformation,
            "WinStationQueryCurrentSessionInformation");
          goto LABEL_75;
        }
        v29 = v28 - 5;
        if ( !v29 )
        {
          CurrentSessionInformation = GetCurrentSessionClientData((struct _WINSTATIONCLIENTW *)a4, a5, v25);
          if ( CurrentSessionInformation >= 0 )
            goto LABEL_30;
          _DbgPrintMessage(
            8,
            "GetCurrentSessionClientData failed: 0x%x in %s",
            (unsigned int)CurrentSessionInformation,
            "WinStationQueryCurrentSessionInformation");
          goto LABEL_75;
        }
        if ( v29 == 33 )
        {
          CurrentSessionInformation = GetCurrentSessionWinStationType((unsigned int *)a4->Reserved2, a5, v25);
          if ( CurrentSessionInformation >= 0 )
            goto LABEL_30;
          _DbgPrintMessage(
            8,
            "GetCurrentSessionWinStationType failed: 0x%x in %s",
            (unsigned int)CurrentSessionInformation,
            "WinStationQueryCurrentSessionInformation");
          goto LABEL_75;
        }
      }
    }
LABEL_40:
    SetLastError(0x57u);
    goto LABEL_36;
  }
LABEL_58:
  InformationW = 0;
  if ( SessionId == -1 )
  {
    if ( !(unsigned int)IsLocalServer(this) )
    {
      _DbgPrintMessage(4, "LOGONID_CURRENT specified for a remote server!");
      goto LABEL_40;
    }
    SessionId = NtCurrentPeb()->SessionId;
  }
  if ( !CSmartPublicBinding::operator void *(v39) )
  {
    _DbgPrintMessage(8, "Failed to open binding");
    goto LABEL_36;
  }
  if ( !v11 || *((_DWORD *)v11 + 13) == 1 )
  {
    InformationW = Legacy_WinStationQueryInformationW(this, SessionId, (enum _WINSTATIONINFOCLASS)v7, a4, a5, a6);
    if ( !InformationW )
      GetLastError();
  }
  else
  {
    if ( SessionId >= 0x10000 )
    {
      InformationW = Listener_WinStationQueryInformationW(
                       this,
                       SessionId - 0x10000,
                       (enum _WINSTATIONINFOCLASS)v7,
                       a4,
                       a5,
                       a6);
      goto LABEL_36;
    }
    if ( (_DWORD)v7 == 25 )
    {
      if ( a5 < 0x48 )
      {
        v36 = RtlNtStatusToDosError(-1073741789);
        SetLastError(v36);
        goto LABEL_36;
      }
      CLoadBalancingMetrics::CLoadBalancingMetrics((CLoadBalancingMetrics *)v41);
      CLoadBalancingMetrics::GetData((CLoadBalancingMetrics *)v41, (struct _WINSTATIONLOADINDICATORDATA *)a4);
      *a6 = 72;
      goto LABEL_30;
    }
    if ( (_DWORD)v7 == 41 )
    {
      _DbgPrintMessage(
        8,
        "WinStationValidationInfo is not supported on win8 and above failed: 0x%x in %s",
        -2147467263,
        "Public_WinStationQueryInformationW");
      v35 = ConvertHRESULT2WIN32(-2147467263);
      SetLastError(v35);
    }
    else
    {
      InformationW = _tsrpcQuerySessionInfo(this, SessionId, (enum _WINSTATIONINFOCLASS)v7, a4, a5, a6);
    }
  }
LABEL_36:
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v39);
  return InformationW;
}

```

## disassembly

```asm
0x18000c820  push    rbx
0x18000c822  push    rbp
0x18000c823  push    rsi
0x18000c824  push    rdi
0x18000c825  push    r12
0x18000c827  push    r13
0x18000c829  push    r14
0x18000c82b  push    r15
0x18000c82d  sub     rsp, 0C8h
0x18000c834  xor     r13d, r13d
0x18000c837  mov     r12, r9
0x18000c83a  mov     qword ptr [rsp+108h+var_C8], r13
0x18000c83f  mov     esi, r8d
0x18000c842  mov     r15d, edx
0x18000c845  mov     r14, rcx
0x18000c848  test    rcx, rcx
0x18000c84b  jnz     loc_18000CC32
0x18000c851  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000c858  mov     ecx, 40h ; '@'; unsigned __int64
0x18000c85d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000c862  mov     rbx, rax
0x18000c865  test    rax, rax
0x18000c868  jz      loc_18000CD7C
0x18000c86e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000c875  mov     [rax], r13
0x18000c878  mov     ecx, 2; unsigned __int64
0x18000c87d  mov     [rax+8], r13
0x18000c881  mov     [rax+10h], r13
0x18000c885  mov     [rax+18h], r13
0x18000c889  mov     [rax+20h], r13
0x18000c88d  mov     [rax+28h], r13
0x18000c891  mov     qword ptr [rax+30h], 1
0x18000c899  mov     [rax+38h], r13
0x18000c89d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000c8a2  mov     [rbx+28h], rax
0x18000c8a6  mov     r9, rax
0x18000c8a9  test    rax, rax
0x18000c8ac  jz      short loc_18000C910
0x18000c8ae  mov     ecx, 7FFFFFFEh
0x18000c8b3  lea     rdx, dword_18003D0CC
0x18000c8ba  mov     r10d, 1
0x18000c8c0  test    rcx, rcx
0x18000c8c3  jz      short loc_18000C8E2
0x18000c8c5  movzx   eax, word ptr [rdx]
0x18000c8c8  test    ax, ax
0x18000c8cb  jz      short loc_18000C8E2
0x18000c8cd  mov     [r9], ax
0x18000c8d1  add     rdx, 2
0x18000c8d5  add     r9, 2
0x18000c8d9  dec     rcx
0x18000c8dc  sub     r10, 1
0x18000c8e0  jnz     short loc_18000C8C0
0x18000c8e2  test    r10, r10
0x18000c8e5  lea     rcx, [r9-2]
0x18000c8e9  mov     edi, 8007007Ah
0x18000c8ee  cmovnz  rcx, r9
0x18000c8f2  cmovnz  edi, r13d
0x18000c8f6  mov     [rcx], r13w
0x18000c8fa  jz      loc_18000CAEE
0x18000c900  cmp     [rbx+18h], r13
0x18000c904  jnz     short loc_18000C910
0x18000c906  cmp     [rbx+30h], r13d
0x18000c90a  jz      loc_18000CB8A
0x18000c910  mov     [rsp+108h+var_C0], rbx
0x18000c915  mov     dword ptr [rsp+108h+var_C8+4], 1
0x18000c91d  cmp     esi, 27h ; '''
0x18000c920  ja      loc_18000CC4E
0x18000c926  mov     rcx, 8000000142h
0x18000c930  bt      rcx, rsi
0x18000c934  jnb     loc_18000CC4E
0x18000c93a  mov     [rsp+108h+TokenInformation], 0FFFFFFFFh
0x18000c945  mov     [rsp+108h+TokenHandle], r13
0x18000c94a  mov     [rsp+108h+var_D0], r13d
0x18000c94f  cmp     r15d, 0FFFFFFFFh
0x18000c953  jz      loc_18000CA10
0x18000c959  mov     edi, r13d
0x18000c95c  call    cs:__imp_GetCurrentThread
0x18000c962  lea     r9, [rsp+108h+TokenHandle]; TokenHandle
0x18000c967  mov     edx, 8; DesiredAccess
0x18000c96c  mov     rcx, rax; ThreadHandle
0x18000c96f  mov     r8d, 1; OpenAsSelf
0x18000c975  call    cs:__imp_OpenThreadToken
0x18000c97b  test    eax, eax
0x18000c97d  jnz     short loc_18000C9B1
0x18000c97f  call    cs:__imp_GetLastError
0x18000c985  cmp     eax, 3F0h
0x18000c98a  jnz     loc_18000CD42
0x18000c990  call    cs:__imp_GetCurrentProcess
0x18000c996  lea     r8, [rsp+108h+TokenHandle]; TokenHandle
0x18000c99b  mov     edx, 8; DesiredAccess
0x18000c9a0  mov     rcx, rax; ProcessHandle
0x18000c9a3  call    cs:__imp_OpenProcessToken
0x18000c9a9  test    eax, eax
0x18000c9ab  jz      loc_18000CCB6
0x18000c9b1  mov     rcx, [rsp+108h+TokenHandle]; TokenHandle
0x18000c9b6  lea     rax, [rsp+108h+var_D0]
0x18000c9bb  mov     r9d, 4; TokenInformationLength
0x18000c9c1  mov     [rsp+108h+ReturnLength], rax; ReturnLength
0x18000c9c6  lea     r8, [rsp+108h+TokenInformation]; TokenInformation
0x18000c9ce  mov     edx, 0Ch; TokenInformationClass
0x18000c9d3  call    cs:__imp_GetTokenInformation
0x18000c9d9  test    eax, eax
0x18000c9db  jz      loc_18000CC04
0x18000c9e1  cmp     [rsp+108h+TokenInformation], r15d
0x18000c9e9  mov     ebp, r13d
0x18000c9ec  setz    dil
0x18000c9f0  mov     rcx, [rsp+108h+TokenHandle]; hObject
0x18000c9f5  test    rcx, rcx
0x18000c9f8  jz      short loc_18000CA00
0x18000c9fa  call    cs:__imp_CloseHandle
0x18000ca00  test    ebp, ebp
0x18000ca02  js      loc_18000CB58
0x18000ca08  test    edi, edi
0x18000ca0a  jz      loc_18000CC4E
0x18000ca10  xor     dil, dil
0x18000ca13  test    r12, r12
0x18000ca16  jz      loc_18000CAE1
0x18000ca1c  mov     r8, [rsp+108h+arg_28]; unsigned int *
0x18000ca24  test    r8, r8
0x18000ca27  jz      loc_18000CAE1
0x18000ca2d  mov     [r8], r13d
0x18000ca30  cmp     esi, 8
0x18000ca33  jnz     loc_18000CACE
0x18000ca39  mov     edx, [rsp+108h+arg_20]; unsigned int
0x18000ca40  mov     rcx, r12; struct _WINSTATIONINFORMATIONW *
0x18000ca43  call    ?GetCurrentSessionInformation@@YAJPEAU_WINSTATIONINFORMATIONW@@KPEAK@Z; GetCurrentSessionInformation(_WINSTATIONINFORMATIONW *,ulong,ulong *)
0x18000ca48  mov     ebx, eax
0x18000ca4a  test    eax, eax
0x18000ca4c  js      loc_18000CDA5
0x18000ca52  mov     dil, 1
0x18000ca55  jmp     short loc_18000CAAC
0x18000ca57  cmp     dword ptr [rbx+34h], 1
0x18000ca5b  jz      loc_18000CC77
0x18000ca61  cmp     r15d, 10000h
0x18000ca68  jnb     loc_18000CBCF
0x18000ca6e  cmp     esi, 19h
0x18000ca71  jz      loc_18000CCE4
0x18000ca77  cmp     esi, 29h ; ')'
0x18000ca7a  jz      loc_18000CDFF
0x18000ca80  mov     rax, [rsp+108h+arg_28]
0x18000ca88  mov     r9, r12; void *
0x18000ca8b  mov     [rsp+108h+var_E0], rax; unsigned int *
0x18000ca90  mov     r8d, esi; enum _WINSTATIONINFOCLASS
0x18000ca93  mov     eax, [rsp+108h+arg_20]
0x18000ca9a  mov     edx, r15d; unsigned int
0x18000ca9d  mov     rcx, r14; void *
0x18000caa0  mov     dword ptr [rsp+108h+ReturnLength], eax; unsigned int
0x18000caa4  call    ?_tsrpcQuerySessionInfo@@YAEPEAXKW4_WINSTATIONINFOCLASS@@0KPEAK@Z; _tsrpcQuerySessionInfo(void *,ulong,_WINSTATIONINFOCLASS,void *,ulong,ulong *)
0x18000caa9  movzx   edi, al
0x18000caac  lea     rcx, [rsp+108h+var_C8]; this
0x18000cab1  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18000cab6  movzx   eax, dil
0x18000caba  add     rsp, 0C8h
0x18000cac1  pop     r15
0x18000cac3  pop     r14
0x18000cac5  pop     r13
0x18000cac7  pop     r12
0x18000cac9  pop     rdi
0x18000caca  pop     rsi
0x18000cacb  pop     rbp
0x18000cacc  pop     rbx
0x18000cacd  retn
0x18000cace  sub     esi, 1
0x18000cad1  jz      short loc_18000CB0E
0x18000cad3  sub     esi, 5
0x18000cad6  jz      short loc_18000CB33
0x18000cad8  cmp     esi, 21h ; '!'
0x18000cadb  jz      loc_18000CBAA
0x18000cae1  mov     ecx, 57h ; 'W'; dwErrCode
0x18000cae6  call    cs:__imp_SetLastError
0x18000caec  jmp     short loc_18000CAAC
0x18000caee  mov     ecx, edi; int
0x18000caf0  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18000caf5  mov     r8d, edi
0x18000caf8  lea     rdx, aStringcchcopyF; "StringCchCopy failed: %x"
0x18000caff  mov     ecx, 8; int
0x18000cb04  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000cb09  jmp     loc_18000C910
0x18000cb0e  mov     edx, [rsp+108h+arg_20]; unsigned int
0x18000cb15  mov     rcx, r12; struct _WINSTATIONCONFIGW *
0x18000cb18  call    ?GetCurrentSessionConfigData@@YAJPEAU_WINSTATIONCONFIGW@@KPEAK@Z; GetCurrentSessionConfigData(_WINSTATIONCONFIGW *,ulong,ulong *)
0x18000cb1d  mov     ebx, eax
0x18000cb1f  test    eax, eax
0x18000cb21  jns     loc_18000CA52
0x18000cb27  lea     rdx, aGetcurrentsess; "GetCurrentSessionConfigData failed: 0x%"...
0x18000cb2e  jmp     loc_18000CDAC
0x18000cb33  mov     edx, [rsp+108h+arg_20]; unsigned int
0x18000cb3a  mov     rcx, r12; struct _WINSTATIONCLIENTW *
0x18000cb3d  call    ?GetCurrentSessionClientData@@YAJPEAU_WINSTATIONCLIENTW@@KPEAK@Z; GetCurrentSessionClientData(_WINSTATIONCLIENTW *,ulong,ulong *)
0x18000cb42  mov     ebx, eax
0x18000cb44  test    eax, eax
0x18000cb46  jns     loc_18000CA52
0x18000cb4c  lea     rdx, aGetcurrentsess_0; "GetCurrentSessionClientData failed: 0x%"...
0x18000cb53  jmp     loc_18000CDAC
0x18000cb58  lea     r9, aPublicWinstati; "Public_WinStationQueryInformationW"
0x18000cb5f  mov     r8d, ebp
0x18000cb62  lea     rdx, aCutilsIscurren; "CUtils::IsCurrentSession failed: 0x%x i"...
0x18000cb69  mov     ecx, 8; int
0x18000cb6e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000cb73  mov     ecx, ebp; int
0x18000cb75  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18000cb7a  mov     ecx, eax; dwErrCode
0x18000cb7c  call    cs:__imp_SetLastError
0x18000cb82  xor     dil, dil
0x18000cb85  jmp     loc_18000CAAC
0x18000cb8a  mov     rcx, rbx; this
0x18000cb8d  call    ?OpenSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::OpenSessionContextHandle(void)
0x18000cb92  cmp     eax, 800706BAh
0x18000cb97  jz      loc_18000CD70
0x18000cb9d  mov     rcx, rbx; this
0x18000cba0  call    ?CloseSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::CloseSessionContextHandle(void)
0x18000cba5  jmp     loc_18000C910
0x18000cbaa  mov     edx, [rsp+108h+arg_20]; unsigned int
0x18000cbb1  mov     rcx, r12; unsigned int *
0x18000cbb4  call    ?GetCurrentSessionWinStationType@@YAJPEAKK0@Z; GetCurrentSessionWinStationType(ulong *,ulong,ulong *)
0x18000cbb9  mov     ebx, eax
0x18000cbbb  test    eax, eax
0x18000cbbd  jns     loc_18000CA52
0x18000cbc3  lea     rdx, aGetcurrentsess_6; "GetCurrentSessionWinStationType failed:"...
0x18000cbca  jmp     loc_18000CDAC
0x18000cbcf  mov     rax, [rsp+108h+arg_28]
0x18000cbd7  lea     edx, [r15-10000h]; unsigned int
0x18000cbde  mov     [rsp+108h+var_E0], rax; unsigned int *
0x18000cbe3  mov     r9, r12; void *
0x18000cbe6  mov     eax, [rsp+108h+arg_20]
0x18000cbed  mov     r8d, esi; enum _WINSTATIONINFOCLASS
0x18000cbf0  mov     rcx, r14; this
0x18000cbf3  mov     dword ptr [rsp+108h+ReturnLength], eax; unsigned int
0x18000cbf7  call    ?Listener_WinStationQueryInformationW@@YAEPEAXKW4_WINSTATIONINFOCLASS@@0KPEAK@Z; Listener_WinStationQueryInformationW(void *,ulong,_WINSTATIONINFOCLASS,void *,ulong,ulong *)
0x18000cbfc  movzx   edi, al
0x18000cbff  jmp     loc_18000CAAC
0x18000cc04  call    cs:__imp_GetLastError
0x18000cc0a  mov     ebp, eax
0x18000cc0c  test    eax, eax
0x18000cc0e  jle     short loc_18000CC19
0x18000cc10  movzx   ebp, ax
0x18000cc13  or      ebp, 80070000h
0x18000cc19  mov     r8d, ebp
0x18000cc1c  lea     rdx, aGettokeninform_0; "GetTokenInformation failed: 0x%x"
0x18000cc23  mov     ecx, 8; int
0x18000cc28  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000cc2d  jmp     loc_18000C9F0
0x18000cc32  mov     rbx, r14
0x18000cc35  mov     [rsp+108h+var_C0], rbx
0x18000cc3a  cmp     r13w, [rcx]
0x18000cc3e  jz      loc_18000C91D
0x18000cc44  cmp     [rcx+30h], r13d
0x18000cc48  jnz     loc_18000C91D
0x18000cc4e  xor     dil, dil
0x18000cc51  cmp     r15d, 0FFFFFFFFh
0x18000cc55  jz      loc_18000CD1C
0x18000cc5b  lea     rcx, [rsp+108h+var_C8]; unsigned __int16 *
0x18000cc60  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18000cc65  test    rax, rax
0x18000cc68  jz      loc_18000CDE9
0x18000cc6e  test    rbx, rbx
0x18000cc71  jnz     loc_18000CA57
0x18000cc77  mov     rax, [rsp+108h+arg_28]
0x18000cc7f  mov     r9, r12; void *
0x18000cc82  mov     [rsp+108h+var_E0], rax; unsigned int *
0x18000cc87  mov     r8d, esi; enum _WINSTATIONINFOCLASS
0x18000cc8a  mov     eax, [rsp+108h+arg_20]
0x18000cc91  mov     edx, r15d; unsigned int
0x18000cc94  mov     rcx, r14; this
0x18000cc97  mov     dword ptr [rsp+108h+ReturnLength], eax; unsigned int
0x18000cc9b  call    ?Legacy_WinStationQueryInformationW@@YAEPEAXKW4_WINSTATIONINFOCLASS@@0KPEAK@Z; Legacy_WinStationQueryInformationW(void *,ulong,_WINSTATIONINFOCLASS,void *,ulong,ulong *)
0x18000cca0  movzx   edi, al
0x18000cca3  test    al, al
0x18000cca5  jnz     loc_18000CAAC
0x18000ccab  call    cs:__imp_GetLastError
0x18000ccb1  jmp     loc_18000CAAC
0x18000ccb6  call    cs:__imp_GetLastError
0x18000ccbc  mov     ebp, eax
0x18000ccbe  test    eax, eax
0x18000ccc0  jle     short loc_18000CCCB
0x18000ccc2  movzx   ebp, ax
0x18000ccc5  or      ebp, 80070000h
0x18000cccb  mov     r8d, ebp
0x18000ccce  lea     rdx, aOpenprocesstok_0; "OpenProcessToken failed: 0x%x"
0x18000ccd5  mov     ecx, 8; int
0x18000ccda  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000ccdf  jmp     loc_18000C9F0
0x18000cce4  cmp     [rsp+108h+arg_20], 48h ; 'H'
0x18000ccec  jb      loc_18000CE34
0x18000ccf2  lea     rcx, [rsp+108h+var_B8]; this
0x18000ccf7  call    ??0CLoadBalancingMetrics@@QEAA@XZ; CLoadBalancingMetrics::CLoadBalancingMetrics(void)
0x18000ccfc  mov     rdx, r12; struct _WINSTATIONLOADINDICATORDATA *
0x18000ccff  lea     rcx, [rsp+108h+var_B8]; this
0x18000cd04  call    ?GetData@CLoadBalancingMetrics@@QEAAKPEAU_WINSTATIONLOADINDICATORDATA@@@Z; CLoadBalancingMetrics::GetData(_WINSTATIONLOADINDICATORDATA *)
0x18000cd09  mov     rax, [rsp+108h+arg_28]
0x18000cd11  mov     dword ptr [rax], 48h ; 'H'
0x18000cd17  jmp     loc_18000CA52
0x18000cd1c  mov     rcx, r14; void *
0x18000cd1f  call    ?IsLocalServer@@YAHPEAX@Z; IsLocalServer(void *)
0x18000cd24  test    eax, eax
0x18000cd26  jnz     loc_18000CDD4
0x18000cd2c  lea     rdx, aLogonidCurrent; "LOGONID_CURRENT specified for a remote "...
0x18000cd33  mov     ecx, 4; int
0x18000cd38  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000cd3d  jmp     loc_18000CAE1
  ... truncated ...
```
