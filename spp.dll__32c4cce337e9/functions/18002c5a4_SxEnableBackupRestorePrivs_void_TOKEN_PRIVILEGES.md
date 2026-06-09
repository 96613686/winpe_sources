# SxEnableBackupRestorePrivs(void *,_TOKEN_PRIVILEGES * *)

- ea: `0x18002c5a4`
- end: `0x18002c95d`
- name: `?SxEnableBackupRestorePrivs@@YAJPEAXPEAPEAU_TOKEN_PRIVILEGES@@@Z`
- size: `953`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, struct _TOKEN_PRIVILEGES **)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180016d80`
- `0x18002c08c`

## callees

- `0x1800216c8`
- `0x1800268b4`
- `0x1800269ac`
- `0x180027100`
- `0x18002c5a4`
- `0x18002cac4`
- `0x18002d6e8`
- `0x180035b9a`
- `0x180035bd0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002c82a`
- `KERNEL32!GetLastError` at `0x18002c82a`
- `KERNEL32!SetLastError` at `0x18002c802`
- `KERNEL32!SetLastError` at `0x18002c802`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c916`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c91f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c916`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c91f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002c69b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002c6d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002c69b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002c6d5`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18002c822`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18002c822`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002c8a7`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002c8a7`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002c84c`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002c84c`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18002c714`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18002c799`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18002c714`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18002c799`

## string_xrefs

- `0x18002c792`: `SeRestorePrivilege`
- `0x18002c6f9`: `SeBackupPrivilege`
- `0x18002c753`: `::LookupPrivilegeValue( NULL, SE_BACKUP_NAME, &pNewPrivs->Privileges[0].Luid )`
- `0x18002c7d8`: `::LookupPrivilegeValue( NULL, SE_RESTORE_NAME, &pNewPrivs->Privileges[1].Luid )`

## pseudocode

```c
__int64 __fastcall SxEnableBackupRestorePrivs(HANDLE TokenHandle, struct _TOKEN_PRIVILEGES **a2)
{
  char *v4; // rsi
  _OWORD *PreviousState; // r14
  __int16 v6; // ax
  __int64 v7; // rcx
  int LastFailureAsHRESULT; // eax
  _QWORD *v9; // rcx
  int v10; // edx
  const char *v11; // r9
  __int64 v12; // rcx
  BOOL v13; // ebx
  DWORD LastError; // eax
  signed int v15; // edi
  __int64 v16; // rcx
  unsigned int v17; // r8d
  unsigned int v18; // ebx
  __int64 v19; // rdx
  __int64 v20; // r8
  int SidFromToken; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v23; // [rsp+34h] [rbp-CCh]
  __int16 v24; // [rsp+36h] [rbp-CAh]
  DWORD ReturnLength; // [rsp+68h] [rbp-98h] BYREF
  DWORD cbSid; // [rsp+6Ch] [rbp-94h] BYREF
  _BYTE pSid2[80]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE pSid[80]; // [rsp+C0h] [rbp-40h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids, a2);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&SidFromToken, "SxEnableBackupRestorePrivs", 1522, 1);
  v4 = 0;
  ReturnLength = 0;
  PreviousState = 0;
  memset_0(pSid, 0, 0x48u);
  cbSid = 68;
  memset_0(pSid2, 0, 0x48u);
  if ( a2 )
    *a2 = 0;
  v6 = 1539;
  if ( !TokenHandle || (v23 = 1539, v6 = 1540, !a2) )
  {
    SidFromToken = -2147024809;
LABEL_8:
    v24 = v6;
    goto LABEL_36;
  }
  SidFromToken = 0;
  v23 = 1540;
  v4 = (char *)CoTaskMemAlloc(0x28u);
  v6 = 1543;
  if ( !v4
    || (v23 = 1543,
        SidFromToken = 0,
        *(_OWORD *)v4 = 0,
        *((_OWORD *)v4 + 1) = 0,
        *((_QWORD *)v4 + 4) = 0,
        PreviousState = CoTaskMemAlloc(0x28u),
        v6 = 1547,
        !PreviousState) )
  {
    SidFromToken = -2147024882;
    goto LABEL_8;
  }
  v23 = 1547;
  SidFromToken = 0;
  *PreviousState = 0;
  PreviousState[1] = 0;
  *((_QWORD *)PreviousState + 4) = 0;
  if ( !LookupPrivilegeValueW(0, L"SeBackupPrivilege", (PLUID)(v4 + 4)) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v7);
    SidFromToken = LastFailureAsHRESULT;
    v24 = 1551;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
    {
      v10 = 43;
      v11 = "::LookupPrivilegeValue( NULL, SE_BACKUP_NAME, &pNewPrivs->Privileges[0].Luid )";
LABEL_17:
      WPP_SF_sd(
        v9[2],
        v10,
        (unsigned int)&WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids,
        (_DWORD)v11,
        LastFailureAsHRESULT);
      goto LABEL_36;
    }
    goto LABEL_36;
  }
  SidFromToken = 0;
  v23 = 1551;
  *((_DWORD *)v4 + 3) = 2;
  if ( LookupPrivilegeValueW(0, L"SeRestorePrivilege", (PLUID)v4 + 2) )
  {
    SidFromToken = 0;
    v23 = 1555;
    *((_DWORD *)v4 + 6) = 2;
    *(_DWORD *)v4 = 2;
    SetLastError(0);
    v13 = AdjustTokenPrivileges(
            TokenHandle,
            0,
            (PTOKEN_PRIVILEGES)v4,
            0x28u,
            (PTOKEN_PRIVILEGES)PreviousState,
            &ReturnLength);
    LastError = GetLastError();
    v15 = LastError;
    if ( v13 && !LastError )
      goto LABEL_35;
    if ( !CreateWellKnownSid(WinLocalSystemSid, 0, pSid, &cbSid) )
    {
      SidFromToken = GetLastFailureAsHRESULT(v16);
      v6 = 1576;
      goto LABEL_8;
    }
    SidFromToken = 0;
    v23 = 1576;
    SidFromToken = SxGetSidFromToken(TokenHandle, pSid2, v17);
    v6 = 1577;
    if ( SidFromToken < 0 )
      goto LABEL_8;
    v23 = 1577;
    if ( EqualSid(pSid, pSid2) )
    {
LABEL_35:
      *a2 = (struct _TOKEN_PRIVILEGES *)PreviousState;
      PreviousState = 0;
      goto LABEL_36;
    }
    if ( v15 )
    {
      if ( v15 <= 0 )
      {
LABEL_32:
        SidFromToken = v15;
        v24 = 1584;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            45,
            (unsigned int)&WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids,
            (unsigned int)"dwError",
            v15);
        goto LABEL_36;
      }
    }
    else
    {
      LOWORD(v15) = 5;
    }
    v15 = (unsigned __int16)v15 | 0x80070000;
    goto LABEL_32;
  }
  LastFailureAsHRESULT = GetLastFailureAsHRESULT(v12);
  SidFromToken = LastFailureAsHRESULT;
  v24 = 1555;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
  {
    v10 = 44;
    v11 = "::LookupPrivilegeValue( NULL, SE_RESTORE_NAME, &pNewPrivs->Privileges[1].Luid )";
    goto LABEL_17;
  }
LABEL_36:
  CoTaskMemFree(PreviousState);
  CoTaskMemFree(v4);
  v18 = SidFromToken;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&SidFromToken, v19, v20);
  return v18;
}

```

## disassembly

```asm
0x18002c5a4  mov     [rsp-8+arg_10], rbx
0x18002c5a9  mov     [rsp-8+arg_18], rsi
0x18002c5ae  push    rbp
0x18002c5af  push    rdi
0x18002c5b0  push    r12
0x18002c5b2  push    r14
0x18002c5b4  push    r15
0x18002c5b6  lea     rbp, [rsp-20h]
0x18002c5bb  sub     rsp, 120h
0x18002c5c2  mov     rax, cs:__security_cookie
0x18002c5c9  xor     rax, rsp
0x18002c5cc  mov     [rbp+40h+var_30], rax
0x18002c5d0  mov     r15, rdx
0x18002c5d3  mov     r12, rcx
0x18002c5d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c5dd  lea     rdi, WPP_GLOBAL_Control
0x18002c5e4  cmp     rcx, rdi
0x18002c5e7  jz      short loc_18002C60A
0x18002c5e9  test    dword ptr [rcx+1Ch], 20000000h
0x18002c5f0  jz      short loc_18002C60A
0x18002c5f2  mov     rcx, [rcx+10h]
0x18002c5f6  lea     r8, WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids
0x18002c5fd  mov     edx, 2Ah ; '*'
0x18002c602  mov     r9, r15
0x18002c605  call    WPP_SF_q
0x18002c60a  mov     r9d, 1; unsigned __int16
0x18002c610  lea     rdx, aSxenablebackup; "SxEnableBackupRestorePrivs"
0x18002c617  mov     r8d, 5F2h; unsigned __int16
0x18002c61d  lea     rcx, [rsp+140h+var_110]; this
0x18002c622  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002c627  xor     esi, esi
0x18002c629  lea     rcx, [rbp+40h+pSid]; void *
0x18002c62d  xor     edx, edx; Val
0x18002c62f  mov     [rsp+140h+var_D8], esi
0x18002c633  xor     r14d, r14d
0x18002c636  lea     ebx, [rsi+48h]
0x18002c639  mov     r8d, ebx; Size
0x18002c63c  call    memset_0
0x18002c641  mov     r8d, ebx; Size
0x18002c644  mov     [rsp+140h+cbSid], 44h ; 'D'
0x18002c64c  xor     edx, edx; Val
0x18002c64e  lea     rcx, [rsp+140h+pSid2]; void *
0x18002c653  call    memset_0
0x18002c658  test    r15, r15
0x18002c65b  jz      short loc_18002C660
0x18002c65d  mov     [r15], rsi
0x18002c660  mov     eax, 603h
0x18002c665  test    r12, r12
0x18002c668  jnz     short loc_18002C67C
0x18002c66a  mov     [rsp+140h+var_110], 80070057h
0x18002c672  mov     [rsp+140h+var_10A], ax
0x18002c677  jmp     loc_18002C913
0x18002c67c  mov     [rsp+140h+var_10C], ax
0x18002c681  mov     eax, 604h
0x18002c686  test    r15, r15
0x18002c689  jz      short loc_18002C66A
0x18002c68b  mov     ebx, 28h ; '('
0x18002c690  mov     [rsp+140h+var_110], esi
0x18002c694  mov     ecx, ebx; cb
0x18002c696  mov     [rsp+140h+var_10C], ax
0x18002c69b  call    cs:__imp_CoTaskMemAlloc
0x18002c6a1  mov     rsi, rax
0x18002c6a4  test    rax, rax
0x18002c6a7  mov     eax, 607h
0x18002c6ac  jnz     short loc_18002C6B8
0x18002c6ae  mov     [rsp+140h+var_110], 8007000Eh
0x18002c6b6  jmp     short loc_18002C672
0x18002c6b8  mov     [rsp+140h+var_10C], ax
0x18002c6bd  xorps   xmm0, xmm0
0x18002c6c0  mov     [rsp+140h+var_110], r14d
0x18002c6c5  xor     eax, eax
0x18002c6c7  movups  xmmword ptr [rsi], xmm0
0x18002c6ca  mov     rcx, rbx; cb
0x18002c6cd  movups  xmmword ptr [rsi+10h], xmm0
0x18002c6d1  mov     [rsi+20h], rax
0x18002c6d5  call    cs:__imp_CoTaskMemAlloc
0x18002c6db  mov     r14, rax
0x18002c6de  test    rax, rax
0x18002c6e1  mov     eax, 60Bh
0x18002c6e6  jz      short loc_18002C6AE
0x18002c6e8  mov     [rsp+140h+var_10C], ax
0x18002c6ed  lea     r8, [rsi+4]; lpLuid
0x18002c6f1  mov     [rsp+140h+var_110], 0
0x18002c6f9  lea     rdx, aSebackupprivil; "SeBackupPrivilege"
0x18002c700  xorps   xmm0, xmm0
0x18002c703  xor     eax, eax
0x18002c705  movups  xmmword ptr [r14], xmm0
0x18002c709  xor     ecx, ecx; lpSystemName
0x18002c70b  movups  xmmword ptr [r14+10h], xmm0
0x18002c710  mov     [r14+20h], rax
0x18002c714  call    cs:__imp_LookupPrivilegeValueW
0x18002c71a  test    eax, eax
0x18002c71c  jnz     short loc_18002C773
0x18002c71e  call    GetLastFailureAsHRESULT
0x18002c723  mov     ecx, 60Fh
0x18002c728  mov     [rsp+140h+var_110], eax
0x18002c72c  mov     [rsp+140h+var_10A], cx
0x18002c731  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c738  cmp     rcx, rdi
0x18002c73b  jz      loc_18002C913
0x18002c741  test    dword ptr [rcx+1Ch], 2000000h
0x18002c748  jz      loc_18002C913
0x18002c74e  mov     edx, 2Bh ; '+'
0x18002c753  lea     r9, aLookupprivileg_0; "::LookupPrivilegeValue( NULL, SE_BACKUP"...
0x18002c75a  mov     dword ptr [rsp+140h+PreviousState], eax
0x18002c75e  mov     rcx, [rcx+10h]
0x18002c762  lea     r8, WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids
0x18002c769  call    WPP_SF_sd
0x18002c76e  jmp     loc_18002C913
0x18002c773  mov     ecx, 60Fh
0x18002c778  mov     [rsp+140h+var_110], 0
0x18002c780  mov     [rsp+140h+var_10C], cx
0x18002c785  lea     r8, [rsi+10h]; lpLuid
0x18002c789  xor     ecx, ecx; lpSystemName
0x18002c78b  mov     dword ptr [rsi+0Ch], 2
0x18002c792  lea     rdx, Name; "SeRestorePrivilege"
0x18002c799  call    cs:__imp_LookupPrivilegeValueW
0x18002c79f  test    eax, eax
0x18002c7a1  jnz     short loc_18002C7E4
0x18002c7a3  call    GetLastFailureAsHRESULT
0x18002c7a8  mov     ecx, 613h
0x18002c7ad  mov     [rsp+140h+var_110], eax
0x18002c7b1  mov     [rsp+140h+var_10A], cx
0x18002c7b6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c7bd  cmp     rcx, rdi
0x18002c7c0  jz      loc_18002C913
0x18002c7c6  test    dword ptr [rcx+1Ch], 2000000h
0x18002c7cd  jz      loc_18002C913
0x18002c7d3  mov     edx, 2Ch ; ','
0x18002c7d8  lea     r9, aLookupprivileg; "::LookupPrivilegeValue( NULL, SE_RESTOR"...
0x18002c7df  jmp     loc_18002C75A
0x18002c7e4  mov     ecx, 613h
0x18002c7e9  mov     [rsp+140h+var_110], 0
0x18002c7f1  mov     [rsp+140h+var_10C], cx
0x18002c7f6  mov     eax, 2
0x18002c7fb  xor     ecx, ecx; dwErrCode
0x18002c7fd  mov     [rsi+18h], eax
0x18002c800  mov     [rsi], eax
0x18002c802  call    cs:__imp_SetLastError
0x18002c808  lea     rax, [rsp+140h+var_D8]
0x18002c80d  mov     r9d, ebx; BufferLength
0x18002c810  mov     [rsp+140h+ReturnLength], rax; ReturnLength
0x18002c815  mov     r8, rsi; NewState
0x18002c818  xor     edx, edx; DisableAllPrivileges
0x18002c81a  mov     [rsp+140h+PreviousState], r14; PreviousState
0x18002c81f  mov     rcx, r12; TokenHandle
0x18002c822  call    cs:__imp_AdjustTokenPrivileges
0x18002c828  mov     ebx, eax
0x18002c82a  call    cs:__imp_GetLastError
0x18002c830  mov     edi, eax
0x18002c832  test    ebx, ebx
0x18002c834  jz      short loc_18002C83E
0x18002c836  test    eax, eax
0x18002c838  jz      loc_18002C90D
0x18002c83e  xor     edx, edx; DomainSid
0x18002c840  lea     r9, [rsp+140h+cbSid]; cbSid
0x18002c845  lea     r8, [rbp+40h+pSid]; pSid
0x18002c849  lea     ecx, [rdx+16h]; WellKnownSidType
0x18002c84c  call    cs:__imp_CreateWellKnownSid
0x18002c852  test    eax, eax
0x18002c854  jnz     short loc_18002C869
0x18002c856  call    GetLastFailureAsHRESULT
0x18002c85b  mov     [rsp+140h+var_110], eax
0x18002c85f  mov     eax, 628h
0x18002c864  jmp     loc_18002C672
0x18002c869  mov     eax, 628h
0x18002c86e  mov     [rsp+140h+var_110], 0
0x18002c876  lea     rdx, [rsp+140h+pSid2]; pDestinationSid
0x18002c87b  mov     [rsp+140h+var_10C], ax
0x18002c880  mov     rcx, r12; TokenHandle
0x18002c883  call    ?SxGetSidFromToken@@YAJPEAXPEAU_SID@@K@Z; SxGetSidFromToken(void *,_SID *,ulong)
0x18002c888  mov     [rsp+140h+var_110], eax
0x18002c88c  test    eax, eax
0x18002c88e  mov     eax, 629h
0x18002c893  js      loc_18002C672
0x18002c899  lea     rdx, [rsp+140h+pSid2]; pSid2
0x18002c89e  mov     [rsp+140h+var_10C], ax
0x18002c8a3  lea     rcx, [rbp+40h+pSid]; pSid1
0x18002c8a7  call    cs:__imp_EqualSid
0x18002c8ad  test    eax, eax
0x18002c8af  jnz     short loc_18002C90D
0x18002c8b1  test    edi, edi
0x18002c8b3  jnz     short loc_18002C8BA
0x18002c8b5  lea     edi, [rax+5]
0x18002c8b8  jmp     short loc_18002C8BC
0x18002c8ba  jle     short loc_18002C8C5
0x18002c8bc  movzx   edi, di
0x18002c8bf  or      edi, 80070000h
0x18002c8c5  mov     [rsp+140h+var_110], edi
0x18002c8c9  mov     eax, 630h
0x18002c8ce  test    edi, edi
0x18002c8d0  jns     short loc_18002C908
0x18002c8d2  mov     [rsp+140h+var_10A], ax
0x18002c8d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c8de  lea     rax, WPP_GLOBAL_Control
0x18002c8e5  cmp     rcx, rax
0x18002c8e8  jz      short loc_18002C913
0x18002c8ea  test    dword ptr [rcx+1Ch], 2000000h
0x18002c8f1  jz      short loc_18002C913
0x18002c8f3  mov     edx, 2Dh ; '-'
0x18002c8f8  mov     dword ptr [rsp+140h+PreviousState], edi
0x18002c8fc  lea     r9, aDwerror; "dwError"
0x18002c903  jmp     loc_18002C75E
0x18002c908  mov     [rsp+140h+var_10C], ax
0x18002c90d  mov     [r15], r14
0x18002c910  xor     r14d, r14d
0x18002c913  mov     rcx, r14; pv
0x18002c916  call    cs:__imp_CoTaskMemFree
0x18002c91c  mov     rcx, rsi; pv
0x18002c91f  call    cs:__imp_CoTaskMemFree
0x18002c925  mov     ebx, [rsp+140h+var_110]
0x18002c929  lea     rcx, [rsp+140h+var_110]; this
0x18002c92e  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18002c933  mov     eax, ebx
0x18002c935  mov     rcx, [rbp+40h+var_30]
0x18002c939  xor     rcx, rsp; StackCookie
0x18002c93c  call    __security_check_cookie
0x18002c941  lea     r11, [rsp+140h+var_20]
0x18002c949  mov     rbx, [r11+40h]
0x18002c94d  mov     rsi, [r11+48h]
0x18002c951  mov     rsp, r11
0x18002c954  pop     r15
0x18002c956  pop     r14
0x18002c958  pop     r12
0x18002c95a  pop     rdi
0x18002c95b  pop     rbp
0x18002c95c  retn
```
