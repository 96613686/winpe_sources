# CAgentServiceManager::ProcessServiceRegistration(tagServiceRegistrationRequest &,void *,CCallerIdentity const *,TraceLoggingCorrelationVector *,ISupportSusServiceExtendedResult *)

- ea: `0x18005ba58`
- end: `0x18005c1de`
- name: `?ProcessServiceRegistration@CAgentServiceManager@@AEAAJAEAUtagServiceRegistrationRequest@@PEAXPEBVCCallerIdentity@@PEAVTraceLoggingCorrelationVector@@PEAVISupportSusServiceExtendedResult@@@Z`
- size: `1926`
- prototype: `__int64 __fastcall(void **this, struct tagServiceRegistrationRequest *, void *, const struct CCallerIdentity *, struct TraceLoggingCorrelationVector *)`
- caller_count: `3`
- callee_count: `16`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x180047da0`
- `0x18005c694`
- `0x18005dfd0`

## callees

- `0x18003a6c4`
- `0x18005acd0`
- `0x18005ba58`
- `0x18005d56c`
- `0x18005ed8c`
- `0x18005edd0`
- `0x18005eeb4`
- `0x18011098c`
- `0x180113a10`
- `0x180113ae8`
- `0x18012b618`
- `0x18012d780`
- `0x18012d9d4`
- `0x180131a30`
- `0x180238960`
- `0x180240d40`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005bf31`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c06a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c163`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005bf31`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c06a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005c163`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18005bd9d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18005bd9d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005bca5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005be58`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005bca5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005be58`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005be89`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005beda`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005be89`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005beda`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18005c055`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18005c055`
- `RPCRT4!UuidFromStringW` at `0x18005bd61`
- `RPCRT4!UuidFromStringW` at `0x18005bd61`

## string_xrefs

- `0x18005bd34`: `Skipping bad service registration request`
- `0x18005bd72`: `Skipping bad service ID %ws`
- `0x18005bdb3`: `Failed to delete invalid deferred reg key`
- `0x18005c1a3`: `CAgentServiceManager::ProcessServiceRegistration`

## pseudocode

```c
__int64 __fastcall CAgentServiceManager::ProcessServiceRegistration(
        void **this,
        struct tagServiceRegistrationRequest *a2,
        void *a3,
        const struct CCallerIdentity *a4,
        struct TraceLoggingCorrelationVector *a5)
{
  char *v8; // r15
  signed int v9; // ebx
  int v10; // r12d
  const wchar_t *RegKeyPath; // rax
  __int64 v12; // r8
  __int64 v13; // rdx
  WCHAR *v14; // rax
  __int64 v15; // rdi
  DWORD v16; // r13d
  int v17; // r14d
  __int64 v18; // rcx
  const WCHAR *v19; // rax
  LSTATUS v20; // eax
  HKEY v21; // rcx
  __int64 v22; // rbx
  WCHAR *v23; // rdi
  DWORD v24; // edx
  LSTATUS v25; // eax
  int v26; // eax
  int v27; // ecx
  LSTATUS v28; // eax
  void *v29; // rax
  void *v30; // rcx
  signed int v31; // ecx
  void *v32; // rbx
  struct tagServiceRegistrationRequest *v33; // rdi
  unsigned int v34; // ebx
  __int64 v35; // r9
  LSTATUS v36; // eax
  struct tagServiceRegistrationRequest *v37; // rbx
  unsigned int v38; // edi
  __int64 v39; // r9
  int v40; // eax
  REGSAM samDesired; // [rsp+40h] [rbp-C0h] BYREF
  int v43; // [rsp+44h] [rbp-BCh]
  __int128 v44; // [rsp+48h] [rbp-B8h] BYREF
  void *v45[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v46; // [rsp+68h] [rbp-98h]
  __int64 v47; // [rsp+70h] [rbp-90h]
  void *v48; // [rsp+78h] [rbp-88h]
  WCHAR *v49; // [rsp+80h] [rbp-80h]
  struct TraceLoggingCorrelationVector *v50; // [rsp+88h] [rbp-78h]
  struct CCallerIdentity *v51; // [rsp+90h] [rbp-70h]
  CAgentServiceManager *v52; // [rsp+98h] [rbp-68h]
  DWORD cbData; // [rsp+A0h] [rbp-60h] BYREF
  HKEY phkResult; // [rsp+A8h] [rbp-58h] BYREF
  UUID Uuid; // [rsp+B0h] [rbp-50h] BYREF
  void *lpMem[2]; // [rsp+C0h] [rbp-40h]
  __int64 v57; // [rsp+D0h] [rbp-30h]
  HKEY hKey; // [rsp+D8h] [rbp-28h] BYREF
  DWORD Type; // [rsp+E0h] [rbp-20h] BYREF
  struct tagServiceRegistrationRequest *v60[2]; // [rsp+E8h] [rbp-18h] BYREF
  unsigned int v61[2]; // [rsp+F8h] [rbp-8h]
  DWORD cchName[4]; // [rsp+100h] [rbp+0h] BYREF
  WCHAR SubKey[264]; // [rsp+110h] [rbp+10h] BYREF

  v51 = a4;
  v48 = a3;
  v52 = (CAgentServiceManager *)this;
  v50 = a5;
  memset(SubKey, 0, 520);
  Uuid = 0;
  *(_OWORD *)lpMem = 0;
  v57 = 0;
  v8 = 0;
  phkResult = 0;
  v60[0] = (struct tagServiceRegistrationRequest *)&CSusArrayList<tagServiceRegistrationRequest,CSusArrayListItemOpForMyServiceRegistrationRequest>::`vftable';
  v60[1] = 0;
  *(_QWORD *)v61 = 0;
  v9 = CAgentServiceManager::DelayedInit((CAgentServiceManager *)this);
  if ( v9 < 0 )
    goto LABEL_94;
  v44 = 0;
  *(_OWORD *)v45 = 0;
  v46 = 0;
  *((_DWORD *)a2 + 8) = -2145124340;
  if ( (*((_DWORD *)a2 + 4) & 0xFFFFFFE0) != 0
    || *(_QWORD *)a2 == *(_QWORD *)&c_idSrvPolicyDriven.Data1
    && *((_QWORD *)a2 + 1) == *(_QWORD *)c_idSrvPolicyDriven.Data4
    || (*(_QWORD *)a2 == *(_QWORD *)&c_idSrvNone.Data1 && *((_QWORD *)a2 + 1) == *(_QWORD *)c_idSrvNone.Data4
     || *(_QWORD *)a2 == *(_QWORD *)&c_idSrvWU.Data1 && *((_QWORD *)a2 + 1) == *(_QWORD *)c_idSrvWU.Data4)
    && (*((_DWORD *)a2 + 4) & 0xFFFFFFEF) != 0 )
  {
    v9 = -2145124298;
    goto LABEL_90;
  }
  v43 = (*((_BYTE *)a2 + 16) & (unsigned __int8)~*((_BYTE *)a2 + 36) & 0x12) != 0;
  if ( *(_QWORD *)a2 == *(_QWORD *)&c_idSrvNone.Data1 && *((_QWORD *)a2 + 1) == *(_QWORD *)c_idSrvNone.Data4
    || *(_QWORD *)a2 == *(_QWORD *)&c_idSrvWU.Data1 && *((_QWORD *)a2 + 1) == *(_QWORD *)c_idSrvWU.Data4 )
  {
    v10 = 0;
    *((_DWORD *)a2 + 8) = 0;
  }
  else
  {
    v10 = 1;
  }
  if ( !a3 )
    v48 = this[3];
  RegKeyPath = (const wchar_t *)GetRegKeyPath(16, *(_QWORD *)&c_idSrvWU.Data1, *(_QWORD *)c_idSrvWU.Data4);
  StringCchCopyExW(SubKey, 0x104u, RegKeyPath, 0, 0, 0x100u);
  v13 = 260;
  v14 = SubKey;
  do
  {
    if ( !*v14 )
      break;
    ++v14;
    --v13;
  }
  while ( v13 );
  v9 = v13 == 0 ? 0x80070057 : 0;
  v15 = (260 - v13) & -(__int64)(v13 != 0);
  if ( v13 )
  {
    v16 = 0;
    if ( v10 )
    {
      v44 = *(_OWORD *)a2;
      v17 = *((_DWORD *)a2 + 4);
      LODWORD(v45[0]) = v17;
      v18 = *((_QWORD *)a2 + 3);
      if ( !v18 )
      {
LABEL_26:
        v19 = (const WCHAR *)GetRegKeyPath(16, v13, v12);
        v20 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v19, 0, 8u, &phkResult);
        if ( !v20 )
          goto LABEL_30;
        v9 = (unsigned __int16)v20 | 0x80070000;
        if ( v20 <= 0 )
          v9 = v20;
        if ( (unsigned int)(v20 - 2) <= 1 )
        {
LABEL_30:
          v21 = phkResult;
          if ( phkResult )
          {
            v22 = 260 - v15;
            v47 = 260 - v15;
            v23 = &SubKey[v15];
            v49 = v23;
            v24 = 0;
            while ( 1 )
            {
              *(_QWORD *)cchName = v22;
              v36 = RegEnumKeyExW(v21, v24, v23, cchName, 0, 0, 0, 0);
              if ( v36 == 259 || (unsigned int)(v36 - 2) <= 1 )
              {
                RegCloseKey(phkResult);
                phkResult = 0;
                break;
              }
              if ( v36 )
              {
                if ( v36 != 234 )
                {
                  v9 = (unsigned __int16)v36 | 0x80070000;
                  if ( v36 <= 0 )
                    v9 = v36;
                  goto LABEL_90;
                }
                ++v16;
                WUTrace(0, 0, 1, 3, 0, L"Skipping bad service registration request");
              }
              else
              {
                if ( !UuidFromStringW(v23, &Uuid) )
                {
                  ++v16;
                  v26 = RegQueryDwordValueWithDefaultAndRangeCheck(0, SubKey, L"RegisterWithAU", 0, 0, 1);
                  v27 = 9;
                  if ( v26 != 1 )
                    v27 = 1;
                  LODWORD(lpMem[0]) = v27;
                  Type = 0;
                  hKey = 0;
                  cbData = 0;
                  samDesired = 1;
                  lpMem[1] = 0;
                  if ( (int)SetRegistryType(1, &samDesired) < 0 )
                    goto LABEL_54;
                  v28 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, samDesired, &hKey);
                  if ( v28 )
                    goto LABEL_51;
                  v28 = RegQueryValueExW(hKey, L"ClientApplicationID", 0, &Type, 0, &cbData);
                  if ( v28 || !cbData )
                    goto LABEL_51;
                  if ( Type == 1 )
                  {
                    cbData += 2;
                    v29 = SusAlloc(cbData);
                    lpMem[1] = v29;
                    if ( v29 )
                    {
                      v28 = RegQueryValueExW(hKey, L"ClientApplicationID", 0, &Type, (LPBYTE)v29, &cbData);
                      if ( !v28 )
                      {
                        *(_WORD *)((char *)lpMem[1] + (cbData & 0xFFFFFFFE)) = 0;
                        goto LABEL_50;
                      }
LABEL_51:
                      v31 = (unsigned __int16)v28 | 0x80070000;
                      if ( v28 <= 0 )
                        v31 = v28;
                      if ( v31 < 0 )
                        goto LABEL_54;
LABEL_50:
                      v30 = lpMem[1];
LABEL_56:
                      if ( hKey )
                      {
                        RegCloseKey(hKey);
                        v30 = lpMem[1];
                      }
                      if ( *(_QWORD *)&Uuid.Data1 == *(_QWORD *)a2 && *(_QWORD *)Uuid.Data4 == *((_QWORD *)a2 + 1) )
                      {
                        if ( !v10 )
                          goto LABEL_68;
                        if ( (*((_BYTE *)a2 + 16) & (unsigned __int8)~*((_BYTE *)a2 + 36) & 8) != 0 )
                        {
                          v17 |= LODWORD(lpMem[0]);
                          LODWORD(v45[0]) = v17;
                          if ( !v45[1] )
                          {
                            v45[1] = v30;
LABEL_71:
                            Uuid = 0;
                            *(_OWORD *)lpMem = 0;
                            v57 = 0;
                            goto LABEL_72;
                          }
LABEL_68:
                          SusFree(v30);
                          goto LABEL_71;
                        }
                        LODWORD(lpMem[0]) |= v17;
                        v32 = v45[1];
                        if ( v45[1] )
                        {
                          SusFree(v30);
                          lpMem[1] = v32;
                          v45[1] = 0;
                        }
                        v9 = CSusArrayList<tagServiceRegistrationRequest,CSusArrayListItemOpForMyServiceRegistrationRequest>::Add(
                               v60,
                               &Uuid,
                               0);
                        if ( v9 < 0 )
                          goto LABEL_90;
                        v33 = v60[1];
                        v34 = v61[1];
                        v35 = v61[0];
                        v60[1] = 0;
                        *(_QWORD *)v61 = 0;
                        CSusArrayList<tagServiceRegistrationRequest,CSusArrayListItemOpForMyServiceRegistrationRequest>::Attach(
                          v60,
                          v33,
                          v34,
                          v35);
                        v8 = (char *)v33 + 40 * v34 - 40;
                        v23 = v49;
                      }
                      else
                      {
                        v9 = CSusArrayList<tagServiceRegistrationRequest,CSusArrayListItemOpForMyServiceRegistrationRequest>::Add(
                               v60,
                               &Uuid,
                               0);
                        if ( v9 < 0 )
                          goto LABEL_90;
                      }
                      v22 = v47;
                      goto LABEL_71;
                    }
                  }
                  else
                  {
LABEL_54:
                    v29 = lpMem[1];
                  }
                  SusFree(v29);
                  v30 = 0;
                  lpMem[1] = 0;
                  goto LABEL_56;
                }
                WUTrace(0, 0, 1, 3, 0, L"Skipping bad service ID %ws", v23);
                v25 = RegDeleteTreeW(HKEY_LOCAL_MACHINE, SubKey);
                if ( (v25 & 0xFFFFFFFC) != 0 || v25 == 1 )
                {
                  WUTrace(0, 0, 1, 5, 0, L"Failed to delete invalid deferred reg key");
                  ++v16;
                }
              }
LABEL_72:
              v24 = v16;
              v21 = phkResult;
            }
          }
          if ( v10 && !v8 )
          {
            v9 = CSusArrayList<tagServiceRegistrationRequest,CSusArrayListItemOpForMyServiceRegistrationRequest>::Add(
                   v60,
                   &v44,
                   0);
            if ( v9 < 0 )
              goto LABEL_90;
            v45[1] = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
          }
          v37 = v60[1];
          v38 = v61[1];
          v39 = v61[0];
          v60[1] = 0;
          *(_QWORD *)v61 = 0;
          CSusArrayList<tagServiceRegistrationRequest,CSusArrayListItemOpForMyServiceRegistrationRequest>::Attach(
            v60,
            v37,
            v38,
            v39);
          if ( v10 && !v8 )
            v8 = (char *)v37 + 40 * v38 - 40;
          v9 = CAgentServiceManager::ProcessServiceRegistrationHelper(v52, v43, v37, v38, v48, v51, v50, 0);
          if ( v8 )
          {
            v40 = *((_DWORD *)v8 + 9);
            *((_DWORD *)a2 + 9) = v40;
            if ( (~v40 & *((_DWORD *)a2 + 4)) != 0 )
              *((_DWORD *)a2 + 8) = *((_DWORD *)v8 + 8);
            else
              *((_DWORD *)a2 + 8) = 0;
          }
        }
        goto LABEL_90;
      }
      v9 = DuplicateString<wchar_t *,wchar_t *>(v18, &v45[1]);
      if ( v9 < 0 )
        goto LABEL_90;
    }
    v17 = (int)v45[0];
    goto LABEL_26;
  }
LABEL_90:
  if ( phkResult )
    RegCloseKey(phkResult);
  SusFree(lpMem[1]);
  lpMem[1] = 0;
  SusFree(v45[1]);
  if ( v9 < 0 )
    WUTrace("CAgentServiceManager::ProcessServiceRegistration", 1779, 1, 3, v9, L"Method failed");
LABEL_94:
  CSusArrayList<tagServiceRegistrationRequest,CSusArrayListItemOpForMyServiceRegistrationRequest>::~CSusArrayList<tagServiceRegistrationRequest,CSusArrayListItemOpForMyServiceRegistrationRequest>(v60);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18005ba58  push    rbp
0x18005ba5a  push    rbx
0x18005ba5b  push    rsi
0x18005ba5c  push    rdi
0x18005ba5d  push    r12
0x18005ba5f  push    r13
0x18005ba61  push    r14
0x18005ba63  push    r15
0x18005ba65  lea     rbp, [rsp-238h]
0x18005ba6d  sub     rsp, 338h
0x18005ba74  mov     rax, cs:__security_cookie
0x18005ba7b  xor     rax, rsp
0x18005ba7e  mov     [rbp+270h+var_50], rax
0x18005ba85  mov     [rbp+270h+var_2E0], r9
0x18005ba89  mov     r14, r8
0x18005ba8c  mov     [rsp+370h+var_2F8], r8
0x18005ba91  mov     rsi, rdx
0x18005ba94  mov     rdi, rcx
0x18005ba97  mov     [rbp+270h+var_2D8], rcx
0x18005ba9b  mov     rax, [rbp+270h+arg_20]
0x18005baa2  mov     [rbp+270h+var_2E8], rax
0x18005baa6  xor     ebx, ebx
0x18005baa8  mov     [rbp+270h+SubKey], bx
0x18005baac  xor     edx, edx; Val
0x18005baae  mov     r8d, 206h; Size
0x18005bab4  lea     rcx, [rbp+270h+var_25E]; void *
0x18005bab8  call    memset
0x18005babd  xorps   xmm0, xmm0
0x18005bac0  xor     eax, eax
0x18005bac2  movups  xmmword ptr [rbp+270h+Uuid.Data1], xmm0
0x18005bac6  movups  xmmword ptr [rbp+270h+lpMem], xmm0
0x18005baca  mov     [rbp+270h+var_2A0], rax
0x18005bace  mov     r15d, ebx
0x18005bad1  mov     [rbp+270h+var_2C8], rbx
0x18005bad5  movups  xmmword ptr [rbp+270h+var_288], xmm0
0x18005bad9  lea     rax, ??_7?$CSusArrayList@UtagServiceRegistrationRequest@@VCSusArrayListItemOpForMyServiceRegistrationRequest@@@@6B@; const CSusArrayList<tagServiceRegistrationRequest,CSusArrayListItemOpForMyServiceRegistrationRequest>::`vftable'
0x18005bae0  mov     [rbp+270h+var_288], rax
0x18005bae4  mov     [rbp+270h+var_288+8], rbx
0x18005bae8  mov     qword ptr [rbp+270h+var_278], rbx
0x18005baec  mov     rcx, rdi; this
0x18005baef  call    ?DelayedInit@CAgentServiceManager@@QEAAJXZ; CAgentServiceManager::DelayedInit(void)
0x18005baf4  mov     ebx, eax
0x18005baf6  xor     r10d, r10d
0x18005baf9  test    eax, eax
0x18005bafb  js      loc_18005C1B0
0x18005bb01  xorps   xmm0, xmm0
0x18005bb04  xor     eax, eax
0x18005bb06  movups  [rsp+370h+var_328], xmm0
0x18005bb0b  movups  xmmword ptr [rsp+370h+var_318], xmm0
0x18005bb10  mov     [rsp+370h+var_308], rax
0x18005bb15  mov     dword ptr [rsi+20h], 8024000Ch
0x18005bb1c  lea     r11d, [r15+1]
0x18005bb20  test    dword ptr [rsi+10h], 0FFFFFFE0h
0x18005bb27  jnz     loc_18005C155
0x18005bb2d  mov     rax, [rsi]
0x18005bb30  cmp     rax, qword ptr cs:c_idSrvPolicyDriven.Data1
0x18005bb37  jnz     short loc_18005BB4A
0x18005bb39  mov     rax, [rsi+8]
0x18005bb3d  cmp     rax, qword ptr cs:c_idSrvPolicyDriven.Data4
0x18005bb44  jz      loc_18005C155
0x18005bb4a  mov     r8, qword ptr cs:c_idSrvWU.Data4
0x18005bb51  mov     rdx, qword ptr cs:c_idSrvWU.Data1
0x18005bb58  mov     rcx, qword ptr cs:c_idSrvNone.Data4
0x18005bb5f  mov     r9, qword ptr cs:c_idSrvNone.Data1
0x18005bb66  cmp     [rsi], r9
0x18005bb69  jnz     short loc_18005BB71
0x18005bb6b  cmp     [rsi+8], rcx
0x18005bb6f  jz      short loc_18005BB7C
0x18005bb71  cmp     [rsi], rdx
0x18005bb74  jnz     short loc_18005BB89
0x18005bb76  cmp     [rsi+8], r8
0x18005bb7a  jnz     short loc_18005BB89
0x18005bb7c  test    dword ptr [rsi+10h], 0FFFFFFEFh
0x18005bb83  jnz     loc_18005C155
0x18005bb89  mov     eax, [rsi+24h]
0x18005bb8c  not     eax
0x18005bb8e  and     eax, [rsi+10h]
0x18005bb91  test    al, 12h
0x18005bb93  mov     eax, r10d
0x18005bb96  setnz   al
0x18005bb99  mov     [rsp+370h+var_32C], eax
0x18005bb9d  cmp     [rsi], r9
0x18005bba0  jnz     short loc_18005BBA8
0x18005bba2  cmp     [rsi+8], rcx
0x18005bba6  jz      short loc_18005BBB3
0x18005bba8  cmp     [rsi], rdx
0x18005bbab  jnz     short loc_18005BBBC
0x18005bbad  cmp     [rsi+8], r8
0x18005bbb1  jnz     short loc_18005BBBC
0x18005bbb3  mov     r12d, r10d
0x18005bbb6  mov     [rsi+20h], r10d
0x18005bbba  jmp     short loc_18005BBBF
0x18005bbbc  mov     r12d, r11d
0x18005bbbf  test    r14, r14
0x18005bbc2  jnz     short loc_18005BBCD
0x18005bbc4  mov     rax, [rdi+18h]
0x18005bbc8  mov     [rsp+370h+var_2F8], rax
0x18005bbcd  mov     ecx, 10h
0x18005bbd2  call    ?GetRegKeyPath@@YAPEB_WW4WURegKey@RegUtil@@@Z; GetRegKeyPath(RegUtil::WURegKey)
0x18005bbd7  mov     r8, rax; wchar_t *
0x18005bbda  mov     dword ptr [rsp+370h+lpcbData], 100h; unsigned int
0x18005bbe2  xor     ecx, ecx
0x18005bbe4  mov     [rsp+370h+phkResult], rcx; unsigned __int64 *
0x18005bbe9  xor     r9d, r9d; wchar_t **
0x18005bbec  mov     edi, 104h
0x18005bbf1  mov     edx, edi; unsigned __int64
0x18005bbf3  lea     rcx, [rbp+270h+SubKey]; wchar_t *
0x18005bbf7  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x18005bbfc  mov     edx, edi
0x18005bbfe  lea     rax, [rbp+270h+SubKey]
0x18005bc02  xor     r10d, r10d
0x18005bc05  lea     r11d, [r10+1]
0x18005bc09  cmp     [rax], r10w
0x18005bc0d  jz      short loc_18005BC18
0x18005bc0f  add     rax, 2
0x18005bc13  sub     rdx, r11
0x18005bc16  jnz     short loc_18005BC09
0x18005bc18  mov     rax, rdx
0x18005bc1b  neg     rax
0x18005bc1e  sbb     ebx, ebx
0x18005bc20  not     ebx
0x18005bc22  and     ebx, 80070057h
0x18005bc28  mov     rax, rdx
0x18005bc2b  mov     rcx, rdi
0x18005bc2e  sub     rcx, rdx
0x18005bc31  neg     rax
0x18005bc34  sbb     rdi, rdi
0x18005bc37  and     rdi, rcx
0x18005bc3a  test    rdx, rdx
0x18005bc3d  jz      loc_18005C15A
0x18005bc43  mov     r13d, r10d
0x18005bc46  test    r12d, r12d
0x18005bc49  jz      short loc_18005BC7A
0x18005bc4b  movups  xmm0, xmmword ptr [rsi]
0x18005bc4e  movdqu  [rsp+370h+var_328], xmm0
0x18005bc54  mov     r14d, [rsi+10h]
0x18005bc58  mov     dword ptr [rsp+370h+var_318], r14d
0x18005bc5d  mov     rcx, [rsi+18h]
0x18005bc61  test    rcx, rcx
0x18005bc64  jz      short loc_18005BC7F
0x18005bc66  lea     rdx, [rsp+370h+var_318+8]
0x18005bc6b  call    ??$DuplicateString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x18005bc70  mov     ebx, eax
0x18005bc72  test    eax, eax
0x18005bc74  js      loc_18005C15A
0x18005bc7a  mov     r14d, dword ptr [rsp+370h+var_318]
0x18005bc7f  mov     ecx, 10h
0x18005bc84  call    ?GetRegKeyPath@@YAPEB_WW4WURegKey@RegUtil@@@Z; GetRegKeyPath(RegUtil::WURegKey)
0x18005bc89  mov     rdx, rax; lpSubKey
0x18005bc8c  lea     rax, [rbp+270h+var_2C8]
0x18005bc90  mov     [rsp+370h+phkResult], rax; phkResult
0x18005bc95  mov     r9d, 8; samDesired
0x18005bc9b  xor     r8d, r8d; ulOptions
0x18005bc9e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005bca5  call    cs:__imp_RegOpenKeyExW
0x18005bcab  xor     r10d, r10d
0x18005bcae  test    eax, eax
0x18005bcb0  jz      short loc_18005BCCC
0x18005bcb2  movzx   ebx, ax
0x18005bcb5  or      ebx, 80070000h
0x18005bcbb  test    eax, eax
0x18005bcbd  cmovle  ebx, eax
0x18005bcc0  add     eax, 0FFFFFFFEh
0x18005bcc3  cmp     eax, 1
0x18005bcc6  ja      loc_18005C15A
0x18005bccc  mov     rcx, [rbp+270h+var_2C8]
0x18005bcd0  test    rcx, rcx
0x18005bcd3  jz      loc_18005C077
0x18005bcd9  mov     ebx, 104h
0x18005bcde  sub     rbx, rdi
0x18005bce1  mov     [rsp+370h+var_300], rbx
0x18005bce6  lea     rax, [rbp+270h+SubKey]
0x18005bcea  lea     rdi, [rax+rdi*2]
0x18005bcee  mov     [rbp+270h+var_2F0], rdi
0x18005bcf2  mov     [rsp+370h+lpftLastWriteTime], r10
0x18005bcf7  mov     [rsp+370h+lpcchClass], r10
0x18005bcfc  mov     [rsp+370h+lpcbData], r10
0x18005bd01  mov     [rsp+370h+phkResult], r10
0x18005bd06  xor     edx, edx
0x18005bd08  jmp     loc_18005C04A
0x18005bd0d  lea     ecx, [rax-2]
0x18005bd10  mov     r11d, 1
0x18005bd16  cmp     ecx, r11d
0x18005bd19  jbe     loc_18005C066
0x18005bd1f  xor     r10d, r10d
0x18005bd22  test    eax, eax
0x18005bd24  jz      short loc_18005BD5A
0x18005bd26  cmp     eax, 0EAh
0x18005bd2b  jnz     loc_18005C13F
0x18005bd31  add     r13d, r11d
0x18005bd34  lea     rax, aSkippingBadSer_0; "Skipping bad service registration reque"...
0x18005bd3b  mov     [rsp+370h+lpcbData], rax
0x18005bd40  mov     [rsp+370h+phkResult], r10
0x18005bd45  lea     r9d, [r11+2]
0x18005bd49  mov     r8d, r11d
0x18005bd4c  xor     edx, edx
0x18005bd4e  xor     ecx, ecx
0x18005bd50  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18005bd55  jmp     loc_18005C02D
0x18005bd5a  lea     rdx, [rbp+270h+Uuid]; Uuid
0x18005bd5e  mov     rcx, rdi; StringUuid
0x18005bd61  call    cs:__imp_UuidFromStringW
0x18005bd67  xor     ecx, ecx
0x18005bd69  test    eax, eax
0x18005bd6b  jz      short loc_18005BDDC
0x18005bd6d  mov     [rsp+370h+lpcchClass], rdi
0x18005bd72  lea     rax, aSkippingBadSer; "Skipping bad service ID %ws"
0x18005bd79  mov     [rsp+370h+lpcbData], rax
0x18005bd7e  mov     [rsp+370h+phkResult], rcx
0x18005bd83  xor     edx, edx
0x18005bd85  lea     r9d, [rcx+3]
0x18005bd89  lea     r8d, [rcx+1]
0x18005bd8d  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18005bd92  lea     rdx, [rbp+270h+SubKey]; lpSubKey
0x18005bd96  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005bd9d  call    cs:__imp_RegDeleteTreeW
0x18005bda3  test    eax, 0FFFFFFFCh
0x18005bda8  jnz     short loc_18005BDB3
0x18005bdaa  cmp     eax, 1
0x18005bdad  jnz     loc_18005C02D
0x18005bdb3  lea     rax, aFailedToDelete_2; "Failed to delete invalid deferred reg k"...
0x18005bdba  mov     [rsp+370h+lpcbData], rax
0x18005bdbf  xor     ecx, ecx
0x18005bdc1  mov     dword ptr [rsp+370h+phkResult], ecx
0x18005bdc5  xor     edx, edx
0x18005bdc7  lea     r9d, [rcx+5]
0x18005bdcb  lea     r8d, [rcx+1]
0x18005bdcf  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18005bdd4  inc     r13d
0x18005bdd7  jmp     loc_18005C02D
0x18005bddc  mov     eax, 1
0x18005bde1  add     r13d, eax
0x18005bde4  mov     dword ptr [rsp+370h+lpcbData], eax
0x18005bde8  mov     dword ptr [rsp+370h+phkResult], ecx
0x18005bdec  xor     r9d, r9d
0x18005bdef  lea     r8, ?c_szRegisterWithAURegValue@@3QB_WB; "RegisterWithAU"
0x18005bdf6  lea     rdx, [rbp+270h+SubKey]
0x18005bdfa  call    ?RegQueryDwordValueWithDefaultAndRangeCheck@@YAKPEAUHKEY__@@PEB_W1KKKW4RegistryHiveType@@@Z; RegQueryDwordValueWithDefaultAndRangeCheck(HKEY__ *,wchar_t const *,wchar_t const *,ulong,ulong,ulong,RegistryHiveType)
0x18005bdff  mov     ecx, 9
0x18005be04  lea     r8d, [rcx-8]
0x18005be08  cmp     eax, r8d
0x18005be0b  cmovnz  ecx, r8d
0x18005be0f  mov     dword ptr [rbp+270h+lpMem], ecx
0x18005be12  xor     eax, eax
0x18005be14  mov     [rbp+270h+Type], eax
0x18005be17  mov     [rbp+270h+hKey], rax
0x18005be1b  mov     [rbp+270h+cbData], eax
0x18005be1e  mov     [rsp+370h+samDesired], r8d
0x18005be23  mov     [rbp+270h+lpMem+8], rax
0x18005be27  lea     rdx, [rsp+370h+samDesired]
0x18005be2c  mov     ecx, r8d
0x18005be2f  call    ?SetRegistryType@@YAJW4RegistryHiveType@@PEAK@Z; SetRegistryType(RegistryHiveType,ulong *)
0x18005be34  test    eax, eax
0x18005be36  js      loc_18005BF0F
0x18005be3c  lea     rax, [rbp+270h+hKey]
0x18005be40  mov     [rsp+370h+phkResult], rax; phkResult
0x18005be45  mov     r9d, [rsp+370h+samDesired]; samDesired
0x18005be4a  xor     r8d, r8d; ulOptions
0x18005be4d  lea     rdx, [rbp+270h+SubKey]; lpSubKey
0x18005be51  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005be58  call    cs:__imp_RegOpenKeyExW
0x18005be5e  xor     r10d, r10d
0x18005be61  test    eax, eax
0x18005be63  jnz     loc_18005BEFD
0x18005be69  lea     rax, [rbp+270h+cbData]
0x18005be6d  mov     [rsp+370h+lpcbData], rax; lpcbData
0x18005be72  mov     [rsp+370h+phkResult], r10; lpData
0x18005be77  lea     r9, [rbp+270h+Type]; lpType
0x18005be7b  xor     r8d, r8d; lpReserved
0x18005be7e  lea     rdx, ?c_szClientApplicationIDRegValue@@3QB_WB; "ClientApplicationID"
0x18005be85  mov     rcx, [rbp+270h+hKey]; hKey
0x18005be89  call    cs:__imp_RegQueryValueExW
0x18005be8f  xor     r10d, r10d
0x18005be92  test    eax, eax
0x18005be94  jnz     short loc_18005BEFD
0x18005be96  mov     ecx, [rbp+270h+cbData]
0x18005be99  test    ecx, ecx
0x18005be9b  jz      short loc_18005BEFD
0x18005be9d  lea     eax, [r10+1]
0x18005bea1  cmp     [rbp+270h+Type], eax
0x18005bea4  jnz     short loc_18005BF0F
0x18005bea6  add     ecx, 2; unsigned __int64
0x18005bea9  mov     [rbp+270h+cbData], ecx
0x18005beac  call    ?SusAlloc@@YAPEAX_K@Z; SusAlloc(unsigned __int64)
0x18005beb1  mov     [rbp+270h+lpMem+8], rax
0x18005beb5  test    rax, rax
0x18005beb8  jz      short loc_18005BF13
0x18005beba  lea     rcx, [rbp+270h+cbData]
0x18005bebe  mov     [rsp+370h+lpcbData], rcx; lpcbData
0x18005bec3  mov     [rsp+370h+phkResult], rax; lpData
0x18005bec8  lea     r9, [rbp+270h+Type]; lpType
0x18005becc  xor     r8d, r8d; lpReserved
0x18005becf  lea     rdx, ?c_szClientApplicationIDRegValue@@3QB_WB; "ClientApplicationID"
0x18005bed6  mov     rcx, [rbp+270h+hKey]; hKey
0x18005beda  call    cs:__imp_RegQueryValueExW
0x18005bee0  xor     r10d, r10d
0x18005bee3  test    eax, eax
0x18005bee5  jnz     short loc_18005BEFD
0x18005bee7  mov     ecx, [rbp+270h+cbData]
0x18005beea  and     rcx, 0FFFFFFFFFFFFFFFEh
  ... truncated ...
```
