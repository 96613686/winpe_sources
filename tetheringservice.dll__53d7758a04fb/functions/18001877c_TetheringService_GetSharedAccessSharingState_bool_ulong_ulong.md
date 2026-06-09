# TetheringService::GetSharedAccessSharingState(bool *,ulong *,ulong *)

- ea: `0x18001877c`
- end: `0x180018a58`
- name: `?GetSharedAccessSharingState@TetheringService@@AEAAJPEA_NPEAK1@Z`
- size: `732`
- prototype: `__int64 __fastcall(TetheringService *__hidden this, bool *, unsigned int *, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180015784`
- `0x18001afb4`

## callees

- `0x180002590`
- `0x18000bf4c`
- `0x18000bf74`
- `0x18001877c`
- `0x180021b18`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800187fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018868`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800188da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800187fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018868`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800188da`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800189f0`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180018a00`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800189f0`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180018a00`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001885a`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001885a`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800187f0`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800187f0`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800188d0`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800188d0`
- `HNetCfgClient!HNetCfgGetPrivateIndex` at `0x180018979`
- `HNetCfgClient!HNetCfgGetPrivateIndex` at `0x180018979`
- `HNetCfgClient!HNetCfgGetPublicIndex` at `0x1800189ab`
- `HNetCfgClient!HNetCfgGetPublicIndex` at `0x1800189ab`

## string_xrefs

- `0x180018850`: `SharedAccess`

## pseudocode

```c
__int64 __fastcall TetheringService::GetSharedAccessSharingState(
        TetheringService *this,
        bool *a2,
        unsigned int *a3,
        unsigned int *a4)
{
  bool v7; // di
  SC_HANDLE v8; // rax
  SC_HANDLE v9; // rbp
  signed int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  unsigned int PrivateIndex; // ebx
  TetheringServiceTelemetry *v14; // rcx
  SC_HANDLE v15; // rax
  SC_HANDLE v16; // rsi
  signed int LastError; // eax
  signed int v18; // eax
  TetheringServiceTelemetry *v19; // rcx
  __int64 v20; // rdx
  struct _SERVICE_STATUS ServiceStatus; // [rsp+40h] [rbp-68h] BYREF

  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  }
  *a2 = 0;
  v7 = 1;
  *a3 = -1;
  *a4 = -1;
  v8 = OpenSCManagerW(0, 0, 1u);
  v9 = v8;
  if ( v8 )
  {
    v15 = OpenServiceW(v8, L"SharedAccess", 0x135u);
    v16 = v15;
    if ( !v15 )
    {
      LastError = GetLastError();
      PrivateIndex = LastError;
      if ( LastError > 0 )
        PrivateIndex = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          103,
          &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids,
          PrivateIndex);
      }
      goto LABEL_39;
    }
    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
    if ( QueryServiceStatus(v15, &ServiceStatus) )
    {
      if ( ((ServiceStatus.dwCurrentState - 2) & 0xFFFFFFFD) != 0 )
      {
        PrivateIndex = 0;
        *a2 = 0;
        if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
        }
        goto LABEL_38;
      }
      PrivateIndex = HNetCfgGetPrivateIndex(a4);
      if ( (PrivateIndex & 0x80000000) == 0 )
      {
        PrivateIndex = HNetCfgGetPublicIndex(a3);
        if ( (PrivateIndex & 0x80000000) == 0 )
        {
          if ( *a3 == -1 )
            v7 = *a4 != -1;
          *a2 = v7;
          goto LABEL_38;
        }
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
LABEL_38:
          CloseServiceHandle(v16);
LABEL_39:
          CloseServiceHandle(v9);
          goto LABEL_40;
        }
        v20 = 107;
      }
      else
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_38;
        }
        v20 = 106;
      }
    }
    else
    {
      v18 = GetLastError();
      PrivateIndex = v18;
      if ( v18 > 0 )
        PrivateIndex = (unsigned __int16)v18 | 0x80070000;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_38;
      }
      v20 = 104;
    }
    WPP_SF_d(*((_QWORD *)v19 + 2), v20, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, PrivateIndex);
    goto LABEL_38;
  }
  v10 = GetLastError();
  PrivateIndex = v10;
  if ( v10 > 0 )
    PrivateIndex = (unsigned __int16)v10 | 0x80070000;
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
LABEL_41:
      if ( v14 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 8) != 0 )
        WPP_SF_dcdd(*((_QWORD *)v14 + 2), v11, v12, PrivateIndex, *a2, *a4, *a3);
      return PrivateIndex;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, PrivateIndex);
LABEL_40:
    v14 = WPP_GLOBAL_Control;
    goto LABEL_41;
  }
  return PrivateIndex;
}

```

## disassembly

```asm
0x18001877c  push    rbx
0x18001877e  push    rbp
0x18001877f  push    rsi
0x180018780  push    rdi
0x180018781  push    r12
0x180018783  push    r14
0x180018785  push    r15
0x180018787  sub     rsp, 70h
0x18001878b  mov     rax, cs:__security_cookie
0x180018792  xor     rax, rsp
0x180018795  mov     [rsp+0A8h+var_48], rax
0x18001879a  mov     r12, r9
0x18001879d  mov     r15, r8
0x1800187a0  mov     r14, rdx
0x1800187a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800187aa  lea     rsi, WPP_GLOBAL_Control
0x1800187b1  cmp     rcx, rsi
0x1800187b4  jz      short loc_1800187D1
0x1800187b6  test    byte ptr [rcx+1Ch], 8
0x1800187ba  jz      short loc_1800187D1
0x1800187bc  mov     rcx, [rcx+10h]
0x1800187c0  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x1800187c7  mov     edx, 65h ; 'e'
0x1800187cc  call    WPP_SF_
0x1800187d1  mov     byte ptr [r14], 0
0x1800187d5  mov     edi, 1
0x1800187da  mov     dword ptr [r15], 0FFFFFFFFh
0x1800187e1  mov     r8d, edi; dwDesiredAccess
0x1800187e4  xor     edx, edx; lpDatabaseName
0x1800187e6  mov     dword ptr [r12], 0FFFFFFFFh
0x1800187ee  xor     ecx, ecx; lpMachineName
0x1800187f0  call    cs:__imp_OpenSCManagerW
0x1800187f6  mov     rbp, rax
0x1800187f9  test    rax, rax
0x1800187fc  jnz     short loc_18001884A
0x1800187fe  call    cs:__imp_GetLastError
0x180018804  mov     ebx, eax
0x180018806  test    eax, eax
0x180018808  jle     short loc_180018813
0x18001880a  movzx   ebx, ax
0x18001880d  or      ebx, 80070000h
0x180018813  mov     rcx, cs:WPP_GLOBAL_Control
0x18001881a  cmp     rcx, rsi
0x18001881d  jz      loc_180018A3A
0x180018823  test    [rcx+1Ch], dil
0x180018827  jz      loc_180018A0D
0x18001882d  mov     rcx, [rcx+10h]
0x180018831  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x180018838  mov     edx, 66h ; 'f'
0x18001883d  mov     r9d, ebx
0x180018840  call    WPP_SF_d
0x180018845  jmp     loc_180018A06
0x18001884a  mov     r8d, 135h; dwDesiredAccess
0x180018850  lea     rdx, aSharedaccess; "SharedAccess"
0x180018857  mov     rcx, rbp; hSCManager
0x18001885a  call    cs:__imp_OpenServiceW
0x180018860  mov     rsi, rax
0x180018863  test    rax, rax
0x180018866  jnz     short loc_1800188BB
0x180018868  call    cs:__imp_GetLastError
0x18001886e  mov     ebx, eax
0x180018870  test    eax, eax
0x180018872  jle     short loc_18001887D
0x180018874  movzx   ebx, ax
0x180018877  or      ebx, 80070000h
0x18001887d  mov     rcx, cs:WPP_GLOBAL_Control
0x180018884  lea     rsi, WPP_GLOBAL_Control
0x18001888b  cmp     rcx, rsi
0x18001888e  jz      loc_1800189FD
0x180018894  test    [rcx+1Ch], dil
0x180018898  jz      loc_1800189FD
0x18001889e  mov     rcx, [rcx+10h]
0x1800188a2  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x1800188a9  mov     edx, 67h ; 'g'
0x1800188ae  mov     r9d, ebx
0x1800188b1  call    WPP_SF_d
0x1800188b6  jmp     loc_1800189FD
0x1800188bb  xorps   xmm0, xmm0
0x1800188be  lea     rdx, [rsp+0A8h+ServiceStatus]; lpServiceStatus
0x1800188c3  movups  xmmword ptr [rsp+0A8h+ServiceStatus.dwServiceType], xmm0
0x1800188c8  mov     rcx, rsi; hService
0x1800188cb  movups  xmmword ptr [rsp+0A8h+ServiceStatus.dwWin32ExitCode], xmm0
0x1800188d0  call    cs:__imp_QueryServiceStatus
0x1800188d6  test    eax, eax
0x1800188d8  jnz     short loc_18001892D
0x1800188da  call    cs:__imp_GetLastError
0x1800188e0  mov     ebx, eax
0x1800188e2  test    eax, eax
0x1800188e4  jle     short loc_1800188EF
0x1800188e6  movzx   ebx, ax
0x1800188e9  or      ebx, 80070000h
0x1800188ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800188f6  lea     rax, WPP_GLOBAL_Control
0x1800188fd  cmp     rcx, rax
0x180018900  jz      loc_1800189ED
0x180018906  test    [rcx+1Ch], dil
0x18001890a  jz      loc_1800189ED
0x180018910  mov     edx, 68h ; 'h'
0x180018915  mov     rcx, [rcx+10h]
0x180018919  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x180018920  mov     r9d, ebx
0x180018923  call    WPP_SF_d
0x180018928  jmp     loc_1800189ED
0x18001892d  mov     eax, [rsp+0A8h+ServiceStatus.dwCurrentState]
0x180018931  add     eax, 0FFFFFFFEh
0x180018934  test    eax, 0FFFFFFFDh
0x180018939  jz      short loc_180018976
0x18001893b  xor     ebx, ebx
0x18001893d  mov     [r14], bl
0x180018940  mov     rcx, cs:WPP_GLOBAL_Control
0x180018947  lea     rax, WPP_GLOBAL_Control
0x18001894e  cmp     rcx, rax
0x180018951  jz      loc_1800189ED
0x180018957  test    byte ptr [rcx+1Ch], 4
0x18001895b  jz      loc_1800189ED
0x180018961  mov     rcx, [rcx+10h]
0x180018965  lea     edx, [rbx+69h]
0x180018968  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001896f  call    WPP_SF_
0x180018974  jmp     short loc_1800189ED
0x180018976  mov     rcx, r12
0x180018979  call    cs:__imp_HNetCfgGetPrivateIndex
0x18001897f  mov     ebx, eax
0x180018981  test    eax, eax
0x180018983  jns     short loc_1800189A8
0x180018985  mov     rcx, cs:WPP_GLOBAL_Control
0x18001898c  lea     rax, WPP_GLOBAL_Control
0x180018993  cmp     rcx, rax
0x180018996  jz      short loc_1800189ED
0x180018998  test    [rcx+1Ch], dil
0x18001899c  jz      short loc_1800189ED
0x18001899e  mov     edx, 6Ah ; 'j'
0x1800189a3  jmp     loc_180018915
0x1800189a8  mov     rcx, r15
0x1800189ab  call    cs:__imp_HNetCfgGetPublicIndex
0x1800189b1  mov     ebx, eax
0x1800189b3  test    eax, eax
0x1800189b5  jns     short loc_1800189DA
0x1800189b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800189be  lea     rax, WPP_GLOBAL_Control
0x1800189c5  cmp     rcx, rax
0x1800189c8  jz      short loc_1800189ED
0x1800189ca  test    [rcx+1Ch], dil
0x1800189ce  jz      short loc_1800189ED
0x1800189d0  mov     edx, 6Bh ; 'k'
0x1800189d5  jmp     loc_180018915
0x1800189da  cmp     dword ptr [r15], 0FFFFFFFFh
0x1800189de  jnz     short loc_1800189EA
0x1800189e0  cmp     dword ptr [r12], 0FFFFFFFFh
0x1800189e5  jnz     short loc_1800189EA
0x1800189e7  xor     dil, dil
0x1800189ea  mov     [r14], dil
0x1800189ed  mov     rcx, rsi; hSCObject
0x1800189f0  call    cs:__imp_CloseServiceHandle
0x1800189f6  lea     rsi, WPP_GLOBAL_Control
0x1800189fd  mov     rcx, rbp; hSCObject
0x180018a00  call    cs:__imp_CloseServiceHandle
0x180018a06  mov     rcx, cs:WPP_GLOBAL_Control
0x180018a0d  cmp     rcx, rsi
0x180018a10  jz      short loc_180018A3A
0x180018a12  test    byte ptr [rcx+1Ch], 8
0x180018a16  jz      short loc_180018A3A
0x180018a18  mov     eax, [r15]
0x180018a1b  mov     r9d, ebx
0x180018a1e  mov     rcx, [rcx+10h]
0x180018a22  mov     [rsp+0A8h+var_78], eax
0x180018a26  mov     eax, [r12]
0x180018a2a  mov     [rsp+0A8h+var_80], eax
0x180018a2e  mov     al, [r14]
0x180018a31  mov     [rsp+0A8h+var_88], al
0x180018a35  call    WPP_SF_dcdd
0x180018a3a  mov     eax, ebx
0x180018a3c  mov     rcx, [rsp+0A8h+var_48]
0x180018a41  xor     rcx, rsp; StackCookie
0x180018a44  call    __security_check_cookie
0x180018a49  add     rsp, 70h
0x180018a4d  pop     r15
0x180018a4f  pop     r14
0x180018a51  pop     r12
0x180018a53  pop     rdi
0x180018a54  pop     rsi
0x180018a55  pop     rbp
0x180018a56  pop     rbx
0x180018a57  retn
```
