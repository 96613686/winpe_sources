# SxEnableBackupRestorePrivs(void *,_TOKEN_PRIVILEGES * *)

- ea: `0x18000ea60`
- end: `0x18000ee0c`
- name: `?SxEnableBackupRestorePrivs@@YAJPEAXPEAPEAU_TOKEN_PRIVILEGES@@@Z`
- size: `940`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, struct _TOKEN_PRIVILEGES **, __int64)`
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, service_task, installer_update`

## callers

- `0x18000c6e0`
- `0x18000cc20`
- `0x18000e554`

## callees

- `0x18000d348`
- `0x18000d43c`
- `0x18000da9c`
- `0x18000ea60`
- `0x18000ee14`
- `0x18000f154`
- `0x18000f2cc`
- `0x1800157be`
- `0x1800157f0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000ecd9`
- `KERNEL32!GetLastError` at `0x18000ecd9`
- `KERNEL32!SetLastError` at `0x18000ecb1`
- `KERNEL32!SetLastError` at `0x18000ecb1`
- `ADVAPI32!EqualSid` at `0x18000ed56`
- `ADVAPI32!EqualSid` at `0x18000ed56`
- `ADVAPI32!CreateWellKnownSid` at `0x18000ecfb`
- `ADVAPI32!CreateWellKnownSid` at `0x18000ecfb`
- `ADVAPI32!LookupPrivilegeValueW` at `0x18000ebc3`
- `ADVAPI32!LookupPrivilegeValueW` at `0x18000ec48`
- `ADVAPI32!LookupPrivilegeValueW` at `0x18000ebc3`
- `ADVAPI32!LookupPrivilegeValueW` at `0x18000ec48`
- `ADVAPI32!AdjustTokenPrivileges` at `0x18000ecd1`
- `ADVAPI32!AdjustTokenPrivileges` at `0x18000ecd1`
- `ole32!CoTaskMemAlloc` at `0x18000eb4a`
- `ole32!CoTaskMemAlloc` at `0x18000eb84`
- `ole32!CoTaskMemAlloc` at `0x18000eb4a`
- `ole32!CoTaskMemAlloc` at `0x18000eb84`
- `ole32!CoTaskMemFree` at `0x18000edc5`
- `ole32!CoTaskMemFree` at `0x18000edce`
- `ole32!CoTaskMemFree` at `0x18000edc5`
- `ole32!CoTaskMemFree` at `0x18000edce`

## string_xrefs

- `0x18000eba8`: `SeBackupPrivilege`
- `0x18000ec02`: `::LookupPrivilegeValue( NULL, SE_BACKUP_NAME, &pNewPrivs->Privileges[0].Luid )`
- `0x18000ec41`: `SeRestorePrivilege`
- `0x18000ec87`: `::LookupPrivilegeValue( NULL, SE_RESTORE_NAME, &pNewPrivs->Privileges[1].Luid )`

## pseudocode

```c
__int64 __fastcall SxEnableBackupRestorePrivs(HANDLE TokenHandle, struct _TOKEN_PRIVILEGES **a2, __int64 a3)
{
  char *v5; // rsi
  _OWORD *PreviousState; // r14
  __int16 v7; // ax
  int LastFailureAsHRESULT; // eax
  _QWORD *v9; // rcx
  int v10; // edx
  const char *v11; // r9
  BOOL v12; // ebx
  DWORD LastError; // eax
  signed int v14; // edi
  unsigned int v15; // r8d
  unsigned int v16; // ebx
  __int64 v17; // rdx
  __int64 v18; // r8
  int SidFromToken; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v21; // [rsp+34h] [rbp-CCh]
  __int16 v22; // [rsp+36h] [rbp-CAh]
  DWORD ReturnLength; // [rsp+68h] [rbp-98h] BYREF
  DWORD cbSid; // [rsp+6Ch] [rbp-94h] BYREF
  _BYTE pSid2[80]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE pSid[80]; // [rsp+C0h] [rbp-40h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, a3, a2);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&SidFromToken, "SxEnableBackupRestorePrivs", 1522);
  v5 = 0;
  ReturnLength = 0;
  PreviousState = 0;
  memset_0(pSid, 0, 0x48u);
  cbSid = 68;
  memset_0(pSid2, 0, 0x48u);
  if ( a2 )
    *a2 = 0;
  v7 = 1539;
  if ( !TokenHandle || (v21 = 1539, v7 = 1540, !a2) )
  {
    SidFromToken = -2147024809;
LABEL_8:
    v22 = v7;
    goto LABEL_36;
  }
  SidFromToken = 0;
  v21 = 1540;
  v5 = (char *)CoTaskMemAlloc(0x28u);
  v7 = 1543;
  if ( !v5
    || (v21 = 1543,
        SidFromToken = 0,
        *(_OWORD *)v5 = 0,
        *((_OWORD *)v5 + 1) = 0,
        *((_QWORD *)v5 + 4) = 0,
        PreviousState = CoTaskMemAlloc(0x28u),
        v7 = 1547,
        !PreviousState) )
  {
    SidFromToken = -2147024882;
    goto LABEL_8;
  }
  v21 = 1547;
  SidFromToken = 0;
  *PreviousState = 0;
  PreviousState[1] = 0;
  *((_QWORD *)PreviousState + 4) = 0;
  if ( !LookupPrivilegeValueW(0, L"SeBackupPrivilege", (PLUID)(v5 + 4)) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT();
    SidFromToken = LastFailureAsHRESULT;
    v22 = 1551;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
    {
      v10 = 43;
      v11 = "::LookupPrivilegeValue( NULL, SE_BACKUP_NAME, &pNewPrivs->Privileges[0].Luid )";
LABEL_17:
      WPP_SF_sd(
        v9[2],
        v10,
        (unsigned int)WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids,
        (_DWORD)v11,
        LastFailureAsHRESULT);
      goto LABEL_36;
    }
    goto LABEL_36;
  }
  SidFromToken = 0;
  v21 = 1551;
  *((_DWORD *)v5 + 3) = 2;
  if ( LookupPrivilegeValueW(0, L"SeRestorePrivilege", (PLUID)v5 + 2) )
  {
    SidFromToken = 0;
    v21 = 1555;
    *((_DWORD *)v5 + 6) = 2;
    *(_DWORD *)v5 = 2;
    SetLastError(0);
    v12 = AdjustTokenPrivileges(
            TokenHandle,
            0,
            (PTOKEN_PRIVILEGES)v5,
            0x28u,
            (PTOKEN_PRIVILEGES)PreviousState,
            &ReturnLength);
    LastError = GetLastError();
    v14 = LastError;
    if ( v12 && !LastError )
      goto LABEL_35;
    if ( !CreateWellKnownSid(WinLocalSystemSid, 0, pSid, &cbSid) )
    {
      SidFromToken = GetLastFailureAsHRESULT();
      v7 = 1576;
      goto LABEL_8;
    }
    SidFromToken = 0;
    v21 = 1576;
    SidFromToken = SxGetSidFromToken(TokenHandle, pSid2, v15);
    v7 = 1577;
    if ( SidFromToken < 0 )
      goto LABEL_8;
    v21 = 1577;
    if ( EqualSid(pSid, pSid2) )
    {
LABEL_35:
      *a2 = (struct _TOKEN_PRIVILEGES *)PreviousState;
      PreviousState = 0;
      goto LABEL_36;
    }
    if ( v14 )
    {
      if ( v14 <= 0 )
      {
LABEL_32:
        SidFromToken = v14;
        v22 = 1584;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
        {
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            45,
            (unsigned int)WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids,
            (unsigned int)"dwError",
            v14);
        }
        goto LABEL_36;
      }
    }
    else
    {
      LOWORD(v14) = 5;
    }
    v14 = (unsigned __int16)v14 | 0x80070000;
    goto LABEL_32;
  }
  LastFailureAsHRESULT = GetLastFailureAsHRESULT();
  SidFromToken = LastFailureAsHRESULT;
  v22 = 1555;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
  {
    v10 = 44;
    v11 = "::LookupPrivilegeValue( NULL, SE_RESTORE_NAME, &pNewPrivs->Privileges[1].Luid )";
    goto LABEL_17;
  }
LABEL_36:
  CoTaskMemFree(PreviousState);
  CoTaskMemFree(v5);
  v16 = SidFromToken;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&SidFromToken, v17, v18);
  return v16;
}

```

## disassembly

```asm
0x18000ea60  mov     [rsp-8+arg_10], rbx
0x18000ea65  mov     [rsp-8+arg_18], rsi
0x18000ea6a  push    rbp
0x18000ea6b  push    rdi
0x18000ea6c  push    r12
0x18000ea6e  push    r14
0x18000ea70  push    r15
0x18000ea72  lea     rbp, [rsp-20h]
0x18000ea77  sub     rsp, 120h
0x18000ea7e  mov     rax, cs:__security_cookie
0x18000ea85  xor     rax, rsp
0x18000ea88  mov     [rbp+40h+var_30], rax
0x18000ea8c  mov     r15, rdx
0x18000ea8f  mov     r12, rcx
0x18000ea92  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ea99  lea     rdi, WPP_GLOBAL_Control
0x18000eaa0  cmp     rcx, rdi
0x18000eaa3  jz      short loc_18000EABF
0x18000eaa5  test    dword ptr [rcx+1Ch], 20000000h
0x18000eaac  jz      short loc_18000EABF
0x18000eaae  mov     rcx, [rcx+10h]
0x18000eab2  mov     edx, 2Ah ; '*'
0x18000eab7  mov     r9, r15
0x18000eaba  call    WPP_SF_q
0x18000eabf  mov     r8d, 5F2h; unsigned __int16
0x18000eac5  lea     rdx, aSxenablebackup; "SxEnableBackupRestorePrivs"
0x18000eacc  lea     rcx, [rsp+140h+var_110]; this
0x18000ead1  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000ead6  xor     esi, esi
0x18000ead8  lea     rcx, [rbp+40h+pSid]; void *
0x18000eadc  xor     edx, edx; Val
0x18000eade  mov     [rsp+140h+var_D8], esi
0x18000eae2  xor     r14d, r14d
0x18000eae5  lea     ebx, [rsi+48h]
0x18000eae8  mov     r8d, ebx; Size
0x18000eaeb  call    memset_0
0x18000eaf0  mov     r8d, ebx; Size
0x18000eaf3  mov     [rsp+140h+cbSid], 44h ; 'D'
0x18000eafb  xor     edx, edx; Val
0x18000eafd  lea     rcx, [rsp+140h+pSid2]; void *
0x18000eb02  call    memset_0
0x18000eb07  test    r15, r15
0x18000eb0a  jz      short loc_18000EB0F
0x18000eb0c  mov     [r15], rsi
0x18000eb0f  mov     eax, 603h
0x18000eb14  test    r12, r12
0x18000eb17  jnz     short loc_18000EB2B
0x18000eb19  mov     [rsp+140h+var_110], 80070057h
0x18000eb21  mov     [rsp+140h+var_10A], ax
0x18000eb26  jmp     loc_18000EDC2
0x18000eb2b  mov     [rsp+140h+var_10C], ax
0x18000eb30  mov     eax, 604h
0x18000eb35  test    r15, r15
0x18000eb38  jz      short loc_18000EB19
0x18000eb3a  mov     ebx, 28h ; '('
0x18000eb3f  mov     [rsp+140h+var_110], esi
0x18000eb43  mov     ecx, ebx; cb
0x18000eb45  mov     [rsp+140h+var_10C], ax
0x18000eb4a  call    cs:__imp_CoTaskMemAlloc
0x18000eb50  mov     rsi, rax
0x18000eb53  test    rax, rax
0x18000eb56  mov     eax, 607h
0x18000eb5b  jnz     short loc_18000EB67
0x18000eb5d  mov     [rsp+140h+var_110], 8007000Eh
0x18000eb65  jmp     short loc_18000EB21
0x18000eb67  mov     [rsp+140h+var_10C], ax
0x18000eb6c  xorps   xmm0, xmm0
0x18000eb6f  mov     [rsp+140h+var_110], r14d
0x18000eb74  xor     eax, eax
0x18000eb76  movups  xmmword ptr [rsi], xmm0
0x18000eb79  mov     rcx, rbx; cb
0x18000eb7c  movups  xmmword ptr [rsi+10h], xmm0
0x18000eb80  mov     [rsi+20h], rax
0x18000eb84  call    cs:__imp_CoTaskMemAlloc
0x18000eb8a  mov     r14, rax
0x18000eb8d  test    rax, rax
0x18000eb90  mov     eax, 60Bh
0x18000eb95  jz      short loc_18000EB5D
0x18000eb97  mov     [rsp+140h+var_10C], ax
0x18000eb9c  lea     r8, [rsi+4]; lpLuid
0x18000eba0  mov     [rsp+140h+var_110], 0
0x18000eba8  lea     rdx, Name; "SeBackupPrivilege"
0x18000ebaf  xorps   xmm0, xmm0
0x18000ebb2  xor     eax, eax
0x18000ebb4  movups  xmmword ptr [r14], xmm0
0x18000ebb8  xor     ecx, ecx; lpSystemName
0x18000ebba  movups  xmmword ptr [r14+10h], xmm0
0x18000ebbf  mov     [r14+20h], rax
0x18000ebc3  call    cs:__imp_LookupPrivilegeValueW
0x18000ebc9  test    eax, eax
0x18000ebcb  jnz     short loc_18000EC22
0x18000ebcd  call    GetLastFailureAsHRESULT
0x18000ebd2  mov     ecx, 60Fh
0x18000ebd7  mov     [rsp+140h+var_110], eax
0x18000ebdb  mov     [rsp+140h+var_10A], cx
0x18000ebe0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ebe7  cmp     rcx, rdi
0x18000ebea  jz      loc_18000EDC2
0x18000ebf0  test    dword ptr [rcx+1Ch], 2000000h
0x18000ebf7  jz      loc_18000EDC2
0x18000ebfd  mov     edx, 2Bh ; '+'
0x18000ec02  lea     r9, aLookupprivileg_0; "::LookupPrivilegeValue( NULL, SE_BACKUP"...
0x18000ec09  mov     dword ptr [rsp+140h+PreviousState], eax
0x18000ec0d  mov     rcx, [rcx+10h]
0x18000ec11  lea     r8, WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids
0x18000ec18  call    WPP_SF_sd
0x18000ec1d  jmp     loc_18000EDC2
0x18000ec22  mov     ecx, 60Fh
0x18000ec27  mov     [rsp+140h+var_110], 0
0x18000ec2f  mov     [rsp+140h+var_10C], cx
0x18000ec34  lea     r8, [rsi+10h]; lpLuid
0x18000ec38  xor     ecx, ecx; lpSystemName
0x18000ec3a  mov     dword ptr [rsi+0Ch], 2
0x18000ec41  lea     rdx, aSerestoreprivi; "SeRestorePrivilege"
0x18000ec48  call    cs:__imp_LookupPrivilegeValueW
0x18000ec4e  test    eax, eax
0x18000ec50  jnz     short loc_18000EC93
0x18000ec52  call    GetLastFailureAsHRESULT
0x18000ec57  mov     ecx, 613h
0x18000ec5c  mov     [rsp+140h+var_110], eax
0x18000ec60  mov     [rsp+140h+var_10A], cx
0x18000ec65  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ec6c  cmp     rcx, rdi
0x18000ec6f  jz      loc_18000EDC2
0x18000ec75  test    dword ptr [rcx+1Ch], 2000000h
0x18000ec7c  jz      loc_18000EDC2
0x18000ec82  mov     edx, 2Ch ; ','
0x18000ec87  lea     r9, aLookupprivileg; "::LookupPrivilegeValue( NULL, SE_RESTOR"...
0x18000ec8e  jmp     loc_18000EC09
0x18000ec93  mov     ecx, 613h
0x18000ec98  mov     [rsp+140h+var_110], 0
0x18000eca0  mov     [rsp+140h+var_10C], cx
0x18000eca5  mov     eax, 2
0x18000ecaa  xor     ecx, ecx; dwErrCode
0x18000ecac  mov     [rsi+18h], eax
0x18000ecaf  mov     [rsi], eax
0x18000ecb1  call    cs:__imp_SetLastError
0x18000ecb7  lea     rax, [rsp+140h+var_D8]
0x18000ecbc  mov     r9d, ebx; BufferLength
0x18000ecbf  mov     [rsp+140h+ReturnLength], rax; ReturnLength
0x18000ecc4  mov     r8, rsi; NewState
0x18000ecc7  xor     edx, edx; DisableAllPrivileges
0x18000ecc9  mov     [rsp+140h+PreviousState], r14; PreviousState
0x18000ecce  mov     rcx, r12; TokenHandle
0x18000ecd1  call    cs:__imp_AdjustTokenPrivileges
0x18000ecd7  mov     ebx, eax
0x18000ecd9  call    cs:__imp_GetLastError
0x18000ecdf  mov     edi, eax
0x18000ece1  test    ebx, ebx
0x18000ece3  jz      short loc_18000ECED
0x18000ece5  test    eax, eax
0x18000ece7  jz      loc_18000EDBC
0x18000eced  xor     edx, edx; DomainSid
0x18000ecef  lea     r9, [rsp+140h+cbSid]; cbSid
0x18000ecf4  lea     r8, [rbp+40h+pSid]; pSid
0x18000ecf8  lea     ecx, [rdx+16h]; WellKnownSidType
0x18000ecfb  call    cs:__imp_CreateWellKnownSid
0x18000ed01  test    eax, eax
0x18000ed03  jnz     short loc_18000ED18
0x18000ed05  call    GetLastFailureAsHRESULT
0x18000ed0a  mov     [rsp+140h+var_110], eax
0x18000ed0e  mov     eax, 628h
0x18000ed13  jmp     loc_18000EB21
0x18000ed18  mov     eax, 628h
0x18000ed1d  mov     [rsp+140h+var_110], 0
0x18000ed25  lea     rdx, [rsp+140h+pSid2]; pDestinationSid
0x18000ed2a  mov     [rsp+140h+var_10C], ax
0x18000ed2f  mov     rcx, r12; TokenHandle
0x18000ed32  call    ?SxGetSidFromToken@@YAJPEAXPEAU_SID@@K@Z; SxGetSidFromToken(void *,_SID *,ulong)
0x18000ed37  mov     [rsp+140h+var_110], eax
0x18000ed3b  test    eax, eax
0x18000ed3d  mov     eax, 629h
0x18000ed42  js      loc_18000EB21
0x18000ed48  lea     rdx, [rsp+140h+pSid2]; pSid2
0x18000ed4d  mov     [rsp+140h+var_10C], ax
0x18000ed52  lea     rcx, [rbp+40h+pSid]; pSid1
0x18000ed56  call    cs:__imp_EqualSid
0x18000ed5c  test    eax, eax
0x18000ed5e  jnz     short loc_18000EDBC
0x18000ed60  test    edi, edi
0x18000ed62  jnz     short loc_18000ED69
0x18000ed64  lea     edi, [rax+5]
0x18000ed67  jmp     short loc_18000ED6B
0x18000ed69  jle     short loc_18000ED74
0x18000ed6b  movzx   edi, di
0x18000ed6e  or      edi, 80070000h
0x18000ed74  mov     [rsp+140h+var_110], edi
0x18000ed78  mov     eax, 630h
0x18000ed7d  test    edi, edi
0x18000ed7f  jns     short loc_18000EDB7
0x18000ed81  mov     [rsp+140h+var_10A], ax
0x18000ed86  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ed8d  lea     rax, WPP_GLOBAL_Control
0x18000ed94  cmp     rcx, rax
0x18000ed97  jz      short loc_18000EDC2
0x18000ed99  test    dword ptr [rcx+1Ch], 2000000h
0x18000eda0  jz      short loc_18000EDC2
0x18000eda2  mov     edx, 2Dh ; '-'
0x18000eda7  mov     dword ptr [rsp+140h+PreviousState], edi
0x18000edab  lea     r9, aDwerror; "dwError"
0x18000edb2  jmp     loc_18000EC0D
0x18000edb7  mov     [rsp+140h+var_10C], ax
0x18000edbc  mov     [r15], r14
0x18000edbf  xor     r14d, r14d
0x18000edc2  mov     rcx, r14; pv
0x18000edc5  call    cs:__imp_CoTaskMemFree
0x18000edcb  mov     rcx, rsi; pv
0x18000edce  call    cs:__imp_CoTaskMemFree
0x18000edd4  mov     ebx, [rsp+140h+var_110]
0x18000edd8  lea     rcx, [rsp+140h+var_110]; this
0x18000eddd  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000ede2  mov     eax, ebx
0x18000ede4  mov     rcx, [rbp+40h+var_30]
0x18000ede8  xor     rcx, rsp; StackCookie
0x18000edeb  call    __security_check_cookie
0x18000edf0  lea     r11, [rsp+140h+var_20]
0x18000edf8  mov     rbx, [r11+40h]
0x18000edfc  mov     rsi, [r11+48h]
0x18000ee00  mov     rsp, r11
0x18000ee03  pop     r15
0x18000ee05  pop     r14
0x18000ee07  pop     r12
0x18000ee09  pop     rdi
0x18000ee0a  pop     rbp
0x18000ee0b  retn
```
