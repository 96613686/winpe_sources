# GetConnectedAccountUserInfo

- ea: `0x14008f814`
- end: `0x14008fd24`
- name: `GetConnectedAccountUserInfo`
- size: `1296`
- prototype: `__int64 __fastcall(unsigned __int16 *lpAccountName, _WORD *, _DWORD *, _DWORD *, int, PSID Sid)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14008fd2c`

## callees

- `0x1400057f4`
- `0x14000d4e0`
- `0x140041c34`
- `0x14004df08`
- `0x140053720`
- `0x1400544e0`
- `0x14005f18c`
- `0x14008ef4c`
- `0x14008f7e8`
- `0x14008f814`
- `0x1400902c0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14008f9a3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14008f9a3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14008f98d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14008f98d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008fae3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008fbe6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008fae3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008fbe6`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x14008fb26`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x14008fb26`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x14008fad9`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x14008fbdc`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x14008fad9`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x14008fbdc`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x14008fb40`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x14008fc5e`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x14008fb40`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x14008fc5e`

## pseudocode

```c
__int64 __fastcall GetConnectedAccountUserInfo(
        unsigned __int16 *lpAccountName,
        _WORD *a2,
        _DWORD *a3,
        _DWORD *a4,
        int a5,
        PSID Sid)
{
  __int64 v10; // r9
  __int64 v11; // rax
  __int64 v12; // rcx
  unsigned int v13; // ecx
  DWORD LastError; // ebx
  CUser *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rcx
  HANDLE ProcessHeap; // rax
  unsigned __int64 v19; // r14
  unsigned __int16 *v20; // rbx
  unsigned int v21; // eax
  PSID_IDENTIFIER_AUTHORITY SidIdentifierAuthority; // r14
  int v24; // eax
  CUser *v25; // rcx
  __int64 v26; // rdx
  DWORD cchReferencedDomainName; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v28; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int dwBytes; // [rsp+50h] [rbp-B0h] BYREF
  enum _SID_NAME_USE dwBytes_4; // [rsp+54h] [rbp-ACh] BYREF
  unsigned __int16 *v31; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cbSid; // [rsp+60h] [rbp-A0h] BYREF
  DWORD v33; // [rsp+68h] [rbp-98h] BYREF
  _DWORD *v34; // [rsp+70h] [rbp-90h]
  int Source2; // [rsp+78h] [rbp-88h] BYREF
  __int16 v36; // [rsp+7Ch] [rbp-84h]
  int v37; // [rsp+80h] [rbp-80h] BYREF
  __int16 v38; // [rsp+84h] [rbp-7Ch]
  WCHAR ReferencedDomainName[264]; // [rsp+90h] [rbp-70h] BYREF

  v34 = a4;
  cbSid = 68;
  v28 = 0;
  v31 = 0;
  memset_0(ReferencedDomainName, 0, 0x20Au);
  *a4 = 0;
  cchReferencedDomainName = 261;
  dwBytes_4 = 0;
  Source2 = 0;
  v36 = 2816;
  v37 = 0;
  v38 = 3072;
  v33 = 68;
  *a3 = 0;
  if ( !lpAccountName || !*lpAccountName )
  {
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_66;
    }
    v26 = 26;
    goto LABEL_65;
  }
  if ( a2 && *a2 )
  {
    v11 = -1;
    v12 = -1;
    do
      ++v12;
    while ( a2[v12] );
    v13 = v12 + 2;
    LastError = 534;
    if ( v13 < 2 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_53;
      }
      v16 = 27;
LABEL_52:
      WPP_SF_d(*((_QWORD *)v15 + 2), v16, WPP_8d12472ee3e0397472f1167aeb1d1409_Traceguids, LastError);
LABEL_53:
      CAutoPtr<unsigned short *,&void FreeHeap<unsigned short *>(unsigned short *)>::Free(&v31);
      CAutoPtr<unsigned short *,&void FreeHeap<unsigned short *>(unsigned short *)>::Free(&v28);
      return LastError;
    }
    do
      ++v11;
    while ( lpAccountName[v11] );
    v17 = (unsigned int)v11 + v13;
    if ( (unsigned int)v17 < (unsigned int)v11 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_53;
      }
      v16 = 28;
      goto LABEL_52;
    }
    dwBytes = v17;
    if ( (unsigned int)ULongLongToULong(2 * v17, &dwBytes) )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_53;
      }
      v16 = 29;
      goto LABEL_52;
    }
    ProcessHeap = GetProcessHeap();
    v19 = dwBytes;
    v20 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, dwBytes);
    CAutoPtr<unsigned short *,&void FreeHeap<unsigned short *>(unsigned short *)>::Free(&v31);
    v31 = v20;
    if ( !v20 )
    {
      v15 = WPP_GLOBAL_Control;
      LastError = 14;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_53;
      }
      v16 = 30;
      goto LABEL_52;
    }
    v21 = StringCchPrintfW(v20, v19 >> 1, L"%ws\\%ws", a2, lpAccountName);
    if ( v21 )
    {
      LastError = 1359;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_8d12472ee3e0397472f1167aeb1d1409_Traceguids, v21, 1359);
      }
      goto LABEL_53;
    }
  }
  else
  {
    v20 = lpAccountName;
  }
  if ( !LookupAccountNameW(0, v20, Sid, &cbSid, ReferencedDomainName, &cchReferencedDomainName, &dwBytes_4) )
  {
    LastError = GetLastError();
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_53;
    }
    v16 = 32;
    goto LABEL_52;
  }
  SidIdentifierAuthority = GetSidIdentifierAuthority(Sid);
  if ( RtlCompareMemory(SidIdentifierAuthority, &Source2, 6u) == 6 )
  {
    if ( v20 == lpAccountName )
    {
      CAutoPtr<unsigned short *,&void FreeHeap<unsigned short *>(unsigned short *)>::Free(&v28);
      LastError = CustomParseLookupName(v20, &v28);
      if ( LastError )
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_53;
        }
        v16 = 33;
        goto LABEL_52;
      }
      lpAccountName = v28;
    }
    cchReferencedDomainName = 261;
    if ( !LookupAccountNameW(0, lpAccountName, Sid, &v33, ReferencedDomainName, &cchReferencedDomainName, &dwBytes_4) )
    {
      LastError = GetLastError();
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_53;
      }
      v16 = 34;
      goto LABEL_52;
    }
    v24 = IsAdminAccountFromSid(Sid);
    *v34 = v24;
    goto LABEL_56;
  }
  if ( RtlCompareMemory(SidIdentifierAuthority, &v37, 6u) == 6 )
  {
LABEL_56:
    *a3 = 1;
    CAutoPtr<unsigned short *,&void FreeHeap<unsigned short *>(unsigned short *)>::Free(&v31);
    CAutoPtr<unsigned short *,&void FreeHeap<unsigned short *>(unsigned short *)>::Free(&v28);
    return 0;
  }
  v25 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v26 = 35;
LABEL_65:
    WPP_SF_(*((_QWORD *)v25 + 2), v26, WPP_8d12472ee3e0397472f1167aeb1d1409_Traceguids, v10);
  }
LABEL_66:
  CAutoPtr<unsigned short *,&void FreeHeap<unsigned short *>(unsigned short *)>::Free(&v31);
  CAutoPtr<unsigned short *,&void FreeHeap<unsigned short *>(unsigned short *)>::Free(&v28);
  return 1315;
}

```

## disassembly

```asm
0x14008f814  push    rbp
0x14008f816  push    rbx
0x14008f817  push    rsi
0x14008f818  push    r12
0x14008f81a  push    r13
0x14008f81c  push    r14
0x14008f81e  push    r15
0x14008f820  lea     rbp, [rsp-1B0h]
0x14008f828  sub     rsp, 2B0h
0x14008f82f  mov     rax, cs:__security_cookie
0x14008f836  xor     rax, rsp
0x14008f839  mov     [rbp+1E0h+var_40], rax
0x14008f840  mov     r12, [rbp+1E0h+Sid]
0x14008f847  mov     rbx, r9
0x14008f84a  mov     r13, r8
0x14008f84d  mov     [rsp+2E0h+var_270], rbx
0x14008f852  mov     r15, rdx
0x14008f855  mov     [rsp+2E0h+cbSid], 44h ; 'D'
0x14008f85d  mov     rsi, rcx
0x14008f860  xor     r14d, r14d
0x14008f863  xor     edx, edx; Val
0x14008f865  mov     [rsp+2E0h+var_298], r14
0x14008f86a  mov     r8d, 20Ah; Size
0x14008f870  mov     [rsp+2E0h+var_288], r14
0x14008f875  lea     rcx, [rbp+1E0h+var_250]; void *
0x14008f879  call    memset_0
0x14008f87e  mov     [rbx], r14d
0x14008f881  mov     [rsp+2E0h+var_2A0], 105h
0x14008f889  mov     dword ptr [rsp+2E0h+dwBytes+4], r14d
0x14008f88e  mov     [rsp+2E0h+Source2], r14d
0x14008f893  mov     [rsp+2E0h+var_264], 0B00h
0x14008f89a  mov     [rbp+1E0h+var_260], r14d
0x14008f89e  mov     [rbp+1E0h+var_25C], 0C00h
0x14008f8a4  mov     [rsp+2E0h+var_278], 44h ; 'D'
0x14008f8ac  mov     [r13+0], r14d
0x14008f8b0  test    rsi, rsi
0x14008f8b3  jz      loc_14008FCB2
0x14008f8b9  cmp     r14w, [rsi]
0x14008f8bd  jz      loc_14008FCB2
0x14008f8c3  test    r15, r15
0x14008f8c6  jz      loc_14008FAAC
0x14008f8cc  cmp     r14w, [r15]
0x14008f8d0  jz      loc_14008FAAC
0x14008f8d6  or      rax, 0FFFFFFFFFFFFFFFFh
0x14008f8da  mov     rcx, rax
0x14008f8dd  inc     rcx
0x14008f8e0  cmp     [r15+rcx*2], r14w
0x14008f8e5  jnz     short loc_14008F8DD
0x14008f8e7  add     ecx, 2
0x14008f8ea  mov     ebx, 216h
0x14008f8ef  cmp     ecx, 2
0x14008f8f2  jnb     short loc_14008F92C
0x14008f8f4  mov     rcx, cs:WPP_GLOBAL_Control
0x14008f8fb  lea     rax, WPP_GLOBAL_Control
0x14008f902  cmp     rcx, rax
0x14008f905  jz      loc_14008FC28
0x14008f90b  test    dword ptr [rcx+1Ch], 1000h
0x14008f912  jz      loc_14008FC28
0x14008f918  cmp     byte ptr [rcx+19h], 2
0x14008f91c  jb      loc_14008FC28
0x14008f922  mov     edx, 1Bh
0x14008f927  jmp     loc_14008FC15
0x14008f92c  inc     rax
0x14008f92f  cmp     [rsi+rax*2], r14w
0x14008f934  jnz     short loc_14008F92C
0x14008f936  add     ecx, eax
0x14008f938  cmp     ecx, eax
0x14008f93a  jb      loc_14008FA74
0x14008f940  mov     dword ptr [rsp+2E0h+dwBytes], ecx
0x14008f944  lea     rdx, [rsp+2E0h+dwBytes]; unsigned int *
0x14008f949  add     rcx, rcx; unsigned __int64
0x14008f94c  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x14008f951  test    eax, eax
0x14008f953  jz      short loc_14008F98D
0x14008f955  mov     rcx, cs:WPP_GLOBAL_Control
0x14008f95c  lea     rax, WPP_GLOBAL_Control
0x14008f963  cmp     rcx, rax
0x14008f966  jz      loc_14008FC28
0x14008f96c  test    dword ptr [rcx+1Ch], 1000h
0x14008f973  jz      loc_14008FC28
0x14008f979  cmp     byte ptr [rcx+19h], 2
0x14008f97d  jb      loc_14008FC28
0x14008f983  mov     edx, 1Dh
0x14008f988  jmp     loc_14008FC15
0x14008f98d  call    cs:__imp_GetProcessHeap
0x14008f993  mov     r14d, dword ptr [rsp+2E0h+dwBytes]
0x14008f998  mov     edx, 8; dwFlags
0x14008f99d  mov     r8d, r14d; dwBytes
0x14008f9a0  mov     rcx, rax; hHeap
0x14008f9a3  call    cs:__imp_HeapAlloc
0x14008f9a9  lea     rcx, [rsp+2E0h+var_288]
0x14008f9ae  mov     rbx, rax
0x14008f9b1  call    ?Free@?$CAutoPtr@PEAG$1??$FreeHeap@PEAG@@YAXPEAG@Z@@AEAAXXZ; CAutoPtr<ushort *,&FreeHeap<ushort *>(ushort *)>::Free(void)
0x14008f9b6  mov     [rsp+2E0h+var_288], rbx
0x14008f9bb  test    rbx, rbx
0x14008f9be  jnz     short loc_14008F9FB
0x14008f9c0  mov     rcx, cs:WPP_GLOBAL_Control
0x14008f9c7  lea     rax, WPP_GLOBAL_Control
0x14008f9ce  mov     ebx, 0Eh
0x14008f9d3  cmp     rcx, rax
0x14008f9d6  jz      loc_14008FC28
0x14008f9dc  test    dword ptr [rcx+1Ch], 1000h
0x14008f9e3  jz      loc_14008FC28
0x14008f9e9  cmp     byte ptr [rcx+19h], 2
0x14008f9ed  jb      loc_14008FC28
0x14008f9f3  lea     edx, [rbx+10h]
0x14008f9f6  jmp     loc_14008FC15
0x14008f9fb  shr     r14, 1
0x14008f9fe  lea     r8, aWsWs; "%ws\\%ws"
0x14008fa05  mov     rdx, r14; unsigned __int64
0x14008fa08  mov     [rsp+2E0h+ReferencedDomainName], rsi
0x14008fa0d  mov     r9, r15
0x14008fa10  mov     rcx, rbx; unsigned __int16 *
0x14008fa13  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14008fa18  mov     r9d, eax
0x14008fa1b  test    eax, eax
0x14008fa1d  jz      loc_14008FAAF
0x14008fa23  mov     rcx, cs:WPP_GLOBAL_Control
0x14008fa2a  lea     rax, WPP_GLOBAL_Control
0x14008fa31  mov     ebx, 54Fh
0x14008fa36  cmp     rcx, rax
0x14008fa39  jz      loc_14008FC28
0x14008fa3f  test    dword ptr [rcx+1Ch], 1000h
0x14008fa46  jz      loc_14008FC28
0x14008fa4c  cmp     byte ptr [rcx+19h], 2
0x14008fa50  jb      loc_14008FC28
0x14008fa56  mov     rcx, [rcx+10h]
0x14008fa5a  lea     r8, WPP_8d12472ee3e0397472f1167aeb1d1409_Traceguids
0x14008fa61  mov     edx, 1Fh
0x14008fa66  mov     dword ptr [rsp+2E0h+ReferencedDomainName], ebx
0x14008fa6a  call    WPP_SF_DD
0x14008fa6f  jmp     loc_14008FC28
0x14008fa74  mov     rcx, cs:WPP_GLOBAL_Control
0x14008fa7b  lea     rax, WPP_GLOBAL_Control
0x14008fa82  cmp     rcx, rax
0x14008fa85  jz      loc_14008FC28
0x14008fa8b  test    dword ptr [rcx+1Ch], 1000h
0x14008fa92  jz      loc_14008FC28
0x14008fa98  cmp     byte ptr [rcx+19h], 2
0x14008fa9c  jb      loc_14008FC28
0x14008faa2  mov     edx, 1Ch
0x14008faa7  jmp     loc_14008FC15
0x14008faac  mov     rbx, rsi
0x14008faaf  lea     rax, [rsp+2E0h+dwBytes+4]
0x14008fab4  mov     r8, r12; Sid
0x14008fab7  mov     [rsp+2E0h+peUse], rax; peUse
0x14008fabc  lea     r9, [rsp+2E0h+cbSid]; cbSid
0x14008fac1  lea     rax, [rsp+2E0h+var_2A0]
0x14008fac6  mov     rdx, rbx; lpAccountName
0x14008fac9  mov     [rsp+2E0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x14008face  xor     ecx, ecx; lpSystemName
0x14008fad0  lea     rax, [rbp+1E0h+var_250]
0x14008fad4  mov     [rsp+2E0h+ReferencedDomainName], rax; ReferencedDomainName
0x14008fad9  call    cs:__imp_LookupAccountNameW
0x14008fadf  test    eax, eax
0x14008fae1  jnz     short loc_14008FB23
0x14008fae3  call    cs:__imp_GetLastError
0x14008fae9  mov     ebx, eax
0x14008faeb  mov     rcx, cs:WPP_GLOBAL_Control
0x14008faf2  lea     rax, WPP_GLOBAL_Control
0x14008faf9  cmp     rcx, rax
0x14008fafc  jz      loc_14008FC28
0x14008fb02  test    dword ptr [rcx+1Ch], 1000h
0x14008fb09  jz      loc_14008FC28
0x14008fb0f  cmp     byte ptr [rcx+19h], 2
0x14008fb13  jb      loc_14008FC28
0x14008fb19  mov     edx, 20h ; ' '
0x14008fb1e  jmp     loc_14008FC15
0x14008fb23  mov     rcx, r12; pSid
0x14008fb26  call    cs:__imp_GetSidIdentifierAuthority
0x14008fb2c  mov     r15d, 6
0x14008fb32  lea     rdx, [rsp+2E0h+Source2]; Source2
0x14008fb37  mov     r8d, r15d; Length
0x14008fb3a  mov     rcx, rax; Source1
0x14008fb3d  mov     r14, rax
0x14008fb40  call    cs:__imp_RtlCompareMemory
0x14008fb46  cmp     rax, r15
0x14008fb49  jnz     loc_14008FC54
0x14008fb4f  cmp     rbx, rsi
0x14008fb52  jnz     short loc_14008FBAA
0x14008fb54  lea     rcx, [rsp+2E0h+var_298]
0x14008fb59  call    ?Free@?$CAutoPtr@PEAG$1??$FreeHeap@PEAG@@YAXPEAG@Z@@AEAAXXZ; CAutoPtr<ushort *,&FreeHeap<ushort *>(ushort *)>::Free(void)
0x14008fb5e  lea     rdx, [rsp+2E0h+var_298]; unsigned __int16 **
0x14008fb63  mov     rcx, rbx; unsigned __int16 *
0x14008fb66  call    ?CustomParseLookupName@@YAKPEBGPEAPEAG@Z; CustomParseLookupName(ushort const *,ushort * *)
0x14008fb6b  mov     ebx, eax
0x14008fb6d  test    eax, eax
0x14008fb6f  jz      short loc_14008FBA5
0x14008fb71  mov     rcx, cs:WPP_GLOBAL_Control
0x14008fb78  lea     rax, WPP_GLOBAL_Control
0x14008fb7f  cmp     rcx, rax
0x14008fb82  jz      loc_14008FC28
0x14008fb88  test    dword ptr [rcx+1Ch], 1000h
0x14008fb8f  jz      loc_14008FC28
0x14008fb95  cmp     byte ptr [rcx+19h], 2
0x14008fb99  jb      loc_14008FC28
0x14008fb9f  lea     edx, [r15+1Bh]
0x14008fba3  jmp     short loc_14008FC15
0x14008fba5  mov     rsi, [rsp+2E0h+var_298]
0x14008fbaa  lea     rax, [rsp+2E0h+dwBytes+4]
0x14008fbaf  mov     [rsp+2E0h+var_2A0], 105h
0x14008fbb7  mov     [rsp+2E0h+peUse], rax; peUse
0x14008fbbc  lea     r9, [rsp+2E0h+var_278]; cbSid
0x14008fbc1  lea     rax, [rsp+2E0h+var_2A0]
0x14008fbc6  mov     r8, r12; Sid
0x14008fbc9  mov     [rsp+2E0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x14008fbce  mov     rdx, rsi; lpAccountName
0x14008fbd1  lea     rax, [rbp+1E0h+var_250]
0x14008fbd5  xor     ecx, ecx; lpSystemName
0x14008fbd7  mov     [rsp+2E0h+ReferencedDomainName], rax; ReferencedDomainName
0x14008fbdc  call    cs:__imp_LookupAccountNameW
0x14008fbe2  test    eax, eax
0x14008fbe4  jnz     short loc_14008FC43
0x14008fbe6  call    cs:__imp_GetLastError
0x14008fbec  mov     ebx, eax
0x14008fbee  mov     rcx, cs:WPP_GLOBAL_Control
0x14008fbf5  lea     rax, WPP_GLOBAL_Control
0x14008fbfc  cmp     rcx, rax
0x14008fbff  jz      short loc_14008FC28
0x14008fc01  test    dword ptr [rcx+1Ch], 1000h
0x14008fc08  jz      short loc_14008FC28
0x14008fc0a  cmp     byte ptr [rcx+19h], 2
0x14008fc0e  jb      short loc_14008FC28
0x14008fc10  mov     edx, 22h ; '"'
0x14008fc15  mov     rcx, [rcx+10h]
0x14008fc19  lea     r8, WPP_8d12472ee3e0397472f1167aeb1d1409_Traceguids
0x14008fc20  mov     r9d, ebx
0x14008fc23  call    WPP_SF_d
0x14008fc28  lea     rcx, [rsp+2E0h+var_288]
0x14008fc2d  call    ?Free@?$CAutoPtr@PEAG$1??$FreeHeap@PEAG@@YAXPEAG@Z@@AEAAXXZ; CAutoPtr<ushort *,&FreeHeap<ushort *>(ushort *)>::Free(void)
0x14008fc32  lea     rcx, [rsp+2E0h+var_298]
0x14008fc37  call    ?Free@?$CAutoPtr@PEAG$1??$FreeHeap@PEAG@@YAXPEAG@Z@@AEAAXXZ; CAutoPtr<ushort *,&FreeHeap<ushort *>(ushort *)>::Free(void)
0x14008fc3c  mov     eax, ebx
0x14008fc3e  jmp     loc_14008FD02
0x14008fc43  mov     rcx, r12; Sid
0x14008fc46  call    IsAdminAccountFromSid
0x14008fc4b  mov     rcx, [rsp+2E0h+var_270]
0x14008fc50  mov     [rcx], eax
0x14008fc52  jmp     short loc_14008FC69
0x14008fc54  mov     r8, r15; Length
0x14008fc57  lea     rdx, [rbp+1E0h+var_260]; Source2
0x14008fc5b  mov     rcx, r14; Source1
0x14008fc5e  call    cs:__imp_RtlCompareMemory
0x14008fc64  cmp     rax, r15
0x14008fc67  jnz     short loc_14008FC89
0x14008fc69  lea     rcx, [rsp+2E0h+var_288]
0x14008fc6e  mov     dword ptr [r13+0], 1
0x14008fc76  call    ?Free@?$CAutoPtr@PEAG$1??$FreeHeap@PEAG@@YAXPEAG@Z@@AEAAXXZ; CAutoPtr<ushort *,&FreeHeap<ushort *>(ushort *)>::Free(void)
0x14008fc7b  lea     rcx, [rsp+2E0h+var_298]
0x14008fc80  call    ?Free@?$CAutoPtr@PEAG$1??$FreeHeap@PEAG@@YAXPEAG@Z@@AEAAXXZ; CAutoPtr<ushort *,&FreeHeap<ushort *>(ushort *)>::Free(void)
0x14008fc85  xor     eax, eax
0x14008fc87  jmp     short loc_14008FD02
0x14008fc89  mov     rcx, cs:WPP_GLOBAL_Control
0x14008fc90  lea     rax, WPP_GLOBAL_Control
0x14008fc97  cmp     rcx, rax
0x14008fc9a  jz      short loc_14008FCE9
0x14008fc9c  test    dword ptr [rcx+1Ch], 1000h
0x14008fca3  jz      short loc_14008FCE9
0x14008fca5  cmp     byte ptr [rcx+19h], 2
0x14008fca9  jb      short loc_14008FCE9
0x14008fcab  mov     edx, 23h ; '#'
0x14008fcb0  jmp     short loc_14008FCD9
0x14008fcb2  mov     rcx, cs:WPP_GLOBAL_Control
0x14008fcb9  lea     rax, WPP_GLOBAL_Control
0x14008fcc0  cmp     rcx, rax
0x14008fcc3  jz      short loc_14008FCE9
0x14008fcc5  test    dword ptr [rcx+1Ch], 1000h
0x14008fccc  jz      short loc_14008FCE9
0x14008fcce  cmp     byte ptr [rcx+19h], 2
0x14008fcd2  jb      short loc_14008FCE9
0x14008fcd4  mov     edx, 1Ah
0x14008fcd9  mov     rcx, [rcx+10h]
0x14008fcdd  lea     r8, WPP_8d12472ee3e0397472f1167aeb1d1409_Traceguids
0x14008fce4  call    WPP_SF_
0x14008fce9  lea     rcx, [rsp+2E0h+var_288]
0x14008fcee  call    ?Free@?$CAutoPtr@PEAG$1??$FreeHeap@PEAG@@YAXPEAG@Z@@AEAAXXZ; CAutoPtr<ushort *,&FreeHeap<ushort *>(ushort *)>::Free(void)
0x14008fcf3  lea     rcx, [rsp+2E0h+var_298]
0x14008fcf8  call    ?Free@?$CAutoPtr@PEAG$1??$FreeHeap@PEAG@@YAXPEAG@Z@@AEAAXXZ; CAutoPtr<ushort *,&FreeHeap<ushort *>(ushort *)>::Free(void)
0x14008fcfd  mov     eax, 523h
0x14008fd02  mov     rcx, [rbp+1E0h+var_40]
0x14008fd09  xor     rcx, rsp; StackCookie
0x14008fd0c  call    __security_check_cookie
0x14008fd11  add     rsp, 2B0h
0x14008fd18  pop     r15
0x14008fd1a  pop     r14
0x14008fd1c  pop     r13
0x14008fd1e  pop     r12
0x14008fd20  pop     rsi
0x14008fd21  pop     rbx
0x14008fd22  pop     rbp
0x14008fd23  retn
```
