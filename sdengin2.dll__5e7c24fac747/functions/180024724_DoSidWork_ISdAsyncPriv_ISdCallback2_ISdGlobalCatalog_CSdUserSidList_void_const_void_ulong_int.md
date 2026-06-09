# DoSidWork(ISdAsyncPriv *,ISdCallback2 *,ISdGlobalCatalog *,CSdUserSidList *,void * const,void *,ulong,int *)

- ea: `0x180024724`
- end: `0x180024d60`
- name: `?DoSidWork@@YAJPEAUISdAsyncPriv@@PEAUISdCallback2@@PEAUISdGlobalCatalog@@PEAVCSdUserSidList@@QEAXPEAXKPEAH@Z`
- size: `1596`
- prototype: `__int64 __fastcall(struct ISdAsyncPriv *, struct ISdCallback2 *, struct ISdGlobalCatalog *, struct CSdUserSidList *, PSID pSid, void *, unsigned int, int *)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180022564`
- `0x1800240ac`

## callees

- `0x180009a98`
- `0x180015534`
- `0x180015654`
- `0x180015934`
- `0x1800159ac`
- `0x180015dac`
- `0x180024724`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`
- `0x18009a22c`
- `0x18009ae34`
- `0x1800c97da`
- `0x1800c9830`
- `0x1800cb010`

## import_xrefs

- `msvcrt!wcschr` at `0x180024ad2`
- `msvcrt!wcschr` at `0x180024ad2`
- `KERNEL32!GetLastError` at `0x180024a82`
- `KERNEL32!GetLastError` at `0x180024a8f`
- `KERNEL32!GetLastError` at `0x180024b82`
- `KERNEL32!GetLastError` at `0x180024b8f`
- `KERNEL32!GetLastError` at `0x180024a82`
- `KERNEL32!GetLastError` at `0x180024a8f`
- `KERNEL32!GetLastError` at `0x180024b82`
- `KERNEL32!GetLastError` at `0x180024b8f`
- `KERNEL32!GetComputerNameW` at `0x180024aec`
- `KERNEL32!GetComputerNameW` at `0x180024aec`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800248e7`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18002495a`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800249c6`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180024c1e`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180024c7e`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800248e7`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18002495a`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800249c6`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180024c1e`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180024c7e`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180024bd1`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180024bd1`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800248af`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800248af`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180024881`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180024be3`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180024881`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180024be3`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180024b75`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180024b75`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180024a75`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180024a75`

## string_xrefs

- `0x180024786`: `DoSidWork`

## pseudocode

```c
__int64 __fastcall DoSidWork(
        struct ISdAsyncPriv *a1,
        struct ISdCallback2 *a2,
        struct ISdGlobalCatalog *a3,
        struct CSdUserSidList *a4,
        PSID pSid,
        void *a6,
        unsigned int a7,
        int *a8)
{
  CSdUserSidEntry *v11; // r14
  struct CSdUserSidEntry *v12; // rbx
  __int16 v13; // ax
  PSID v14; // r13
  __int64 v15; // rcx
  DWORD LengthSid; // r15d
  __int64 v17; // rcx
  char *v18; // r12
  int v19; // ecx
  __int64 v20; // rcx
  __int16 v21; // ax
  __int64 v22; // rcx
  int v23; // ecx
  BOOL v24; // r15d
  __int64 v25; // rcx
  wchar_t *v26; // r15
  __int64 v27; // rcx
  BOOL v28; // r15d
  __int64 v29; // rcx
  bool v30; // zf
  __int64 v31; // rcx
  __int64 v32; // rcx
  unsigned int v33; // edi
  DWORD nSize; // [rsp+40h] [rbp-C0h] BYREF
  int LastFailureAsHRESULT; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v37; // [rsp+4Ch] [rbp-B4h]
  __int16 v38; // [rsp+4Eh] [rbp-B2h]
  DWORD cchName; // [rsp+80h] [rbp-80h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+84h] [rbp-7Ch] BYREF
  DWORD cbSid; // [rsp+88h] [rbp-78h] BYREF
  struct CSdUserSidEntry *v42; // [rsp+90h] [rbp-70h] BYREF
  struct CSdUserSidEntry *v43; // [rsp+98h] [rbp-68h] BYREF
  wchar_t *Str; // [rsp+A0h] [rbp-60h] BYREF
  CSdUserSidEntry *v45; // [rsp+A8h] [rbp-58h] BYREF
  LPCWSTR lpAccountName[2]; // [rsp+B0h] [rbp-50h] BYREF
  PSID pDestinationSid; // [rsp+C0h] [rbp-40h]
  struct ISdGlobalCatalog *v48; // [rsp+C8h] [rbp-38h]
  _BYTE Sid[80]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR SystemName[16]; // [rsp+120h] [rbp+20h] BYREF
  WCHAR Name; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v52[526]; // [rsp+142h] [rbp+42h] BYREF

  v48 = a3;
  pDestinationSid = a6;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, "DoSidWork", 944, 1);
  Str = 0;
  lpAccountName[0] = (LPCWSTR)qword_1800E8530;
  lpAccountName[1] = 0;
  cbSid = 68;
  memset(SystemName, 0, sizeof(SystemName));
  nSize = 16;
  peUse = 0;
  Name = 0;
  memset_0(v52, 0, 0x208u);
  cchName = 261;
  v45 = 0;
  v11 = 0;
  v42 = 0;
  v12 = 0;
  v43 = 0;
  if ( a8 )
    *a8 = 0;
  v13 = 972;
  if ( !a1 )
    goto LABEL_4;
  v37 = 972;
  v13 = 973;
  if ( !a2 )
    goto LABEL_4;
  v37 = 973;
  v13 = 974;
  if ( !pSid )
    goto LABEL_4;
  v37 = 974;
  if ( !a4 )
  {
    v13 = 975;
LABEL_4:
    LastFailureAsHRESULT = -2147024809;
LABEL_5:
    v38 = v13;
    goto LABEL_57;
  }
  v37 = 976;
  v14 = pDestinationSid;
  v13 = 977;
  if ( !pDestinationSid )
    goto LABEL_4;
  v37 = 977;
  v13 = 978;
  if ( !a8 )
    goto LABEL_4;
  LastFailureAsHRESULT = 0;
  v37 = 978;
  if ( !IsValidSid(pSid) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v15);
    v13 = 980;
    goto LABEL_5;
  }
  LastFailureAsHRESULT = 0;
  v37 = 980;
  LengthSid = GetLengthSid(pSid);
  LastFailureAsHRESULT = CSdUserSidEntry::CreateInstance(&v42);
  v11 = v42;
  v13 = 984;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_5;
  v37 = 984;
  if ( !CopySid(0x44u, *((PSID *)v42 + 13), pSid) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v17);
    v13 = 985;
    goto LABEL_5;
  }
  LastFailureAsHRESULT = 0;
  v37 = 985;
  v18 = (char *)a4 + 8;
  v19 = CSxList<CSdUserSidList,CSdUserSidEntry>::Find(v18, v11, &v45);
  LastFailureAsHRESULT = v19;
  v13 = 987;
  if ( v19 < 0 )
    goto LABEL_5;
  v37 = 987;
  if ( v19 )
  {
    LastFailureAsHRESULT = CSdUserSidEntry::CreateInstance(&v43);
    v12 = v43;
    v13 = 1007;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_5;
    v37 = 1007;
    if ( !CopySid(0x44u, *((PSID *)v43 + 13), pSid) )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v22);
      v13 = 1008;
      goto LABEL_5;
    }
    LastFailureAsHRESULT = 0;
    v37 = 1008;
    v23 = (*(__int64 (__fastcall **)(struct ISdGlobalCatalog *, PSID, _QWORD, wchar_t **))(*(_QWORD *)v48 + 192LL))(
            v48,
            pSid,
            LengthSid,
            &Str);
    LastFailureAsHRESULT = v23;
    if ( v23 != -2130706192 )
    {
      v13 = 1027;
      if ( v23 < 0 )
        goto LABEL_5;
      v37 = 1027;
      if ( !v23 )
      {
        cchName = 261;
        nSize = 16;
        v24 = LookupAccountSidW(SystemName, pSid, &Name, &cchName, SystemName, &nSize, &peUse);
        if ( !v24 && GetLastError() != 1332 && GetLastError() != 1789 )
        {
          LastFailureAsHRESULT = GetLastFailureAsHRESULT(v25);
          v13 = 1035;
          goto LABEL_5;
        }
        LastFailureAsHRESULT = 0;
        v37 = 1035;
        if ( !v24 )
        {
          v26 = wcschr(Str, 0x5Cu);
          nSize = 16;
          if ( !GetComputerNameW(SystemName, &nSize) )
          {
            LastFailureAsHRESULT = GetLastFailureAsHRESULT(v27);
            v13 = 1043;
            goto LABEL_5;
          }
          LastFailureAsHRESULT = 0;
          v37 = 1043;
          LastFailureAsHRESULT = CBsString::Set((CBsString *)lpAccountName, SystemName, v26);
          v13 = 1044;
          if ( LastFailureAsHRESULT < 0 )
            goto LABEL_5;
          v37 = 1044;
          nSize = 16;
          v28 = LookupAccountNameW(SystemName, lpAccountName[0], Sid, &cbSid, SystemName, &nSize, &peUse);
          if ( !v28 && GetLastError() != 1332 && GetLastError() != 1789 )
          {
            LastFailureAsHRESULT = GetLastFailureAsHRESULT(v29);
            v13 = 1048;
            goto LABEL_5;
          }
          LastFailureAsHRESULT = 0;
          v37 = 1048;
          if ( v28 )
          {
            if ( !EqualSid(pSid, Sid) )
            {
              v30 = !IsValidSid(Sid);
              v13 = 1057;
              if ( v30 )
              {
                LastFailureAsHRESULT = -2147467259;
                goto LABEL_5;
              }
              LastFailureAsHRESULT = 0;
              v37 = 1057;
              if ( !CopySid(0x44u, *((PSID *)v12 + 23), Sid) )
              {
                LastFailureAsHRESULT = GetLastFailureAsHRESULT(v31);
                v13 = 1060;
                goto LABEL_5;
              }
              LastFailureAsHRESULT = 0;
              v37 = 1060;
              *((_DWORD *)v12 + 6) = 1;
              LastFailureAsHRESULT = CSxList<CSdUserSidList,CSdUserSidEntry>::InsertHead(v18, v12);
              v13 = 1063;
              if ( LastFailureAsHRESULT < 0 )
                goto LABEL_5;
              v37 = 1063;
              if ( !CopySid(0x44u, v14, Sid) )
              {
                LastFailureAsHRESULT = GetLastFailureAsHRESULT(v32);
                v13 = 1065;
                goto LABEL_5;
              }
              *a8 = 1;
              LastFailureAsHRESULT = 0;
              v21 = 1068;
              goto LABEL_56;
            }
          }
        }
      }
    }
    *((_DWORD *)v12 + 6) = 0;
    LastFailureAsHRESULT = CSxList<CSdLCList,CSdLCEntry>::InsertTail(v18, v12);
    if ( LastFailureAsHRESULT < 0 )
    {
      v13 = 1084;
      goto LABEL_5;
    }
    *a8 = 0;
    v21 = 1087;
LABEL_55:
    LastFailureAsHRESULT = 1;
    goto LABEL_56;
  }
  if ( !*((_DWORD *)v45 + 6) )
  {
    *a8 = 0;
    v21 = 1004;
    goto LABEL_55;
  }
  if ( !CopySid(0x44u, v14, *((PSID *)v45 + 23)) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v20);
    v13 = 993;
    goto LABEL_5;
  }
  *a8 = 1;
  LastFailureAsHRESULT = 0;
  v21 = 996;
LABEL_56:
  v37 = v21;
LABEL_57:
  SdFreeString(&Str);
  v33 = LastFailureAsHRESULT;
  if ( v12 )
    CSdUserSidEntry::Release(v12);
  if ( v11 )
    CSdUserSidEntry::Release(v11);
  if ( v45 )
    CSdUserSidEntry::Release(v45);
  CBsString::_Release((CBsString *)lpAccountName);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v33;
}

```

## disassembly

```asm
0x180024724  mov     [rsp-8+arg_0], rbx
0x180024729  push    rbp
0x18002472a  push    rsi
0x18002472b  push    rdi
0x18002472c  push    r12
0x18002472e  push    r13
0x180024730  push    r14
0x180024732  push    r15
0x180024734  lea     rbp, [rsp-260h]
0x18002473c  sub     rsp, 360h
0x180024743  mov     rax, cs:__security_cookie
0x18002474a  xor     rax, rsp
0x18002474d  mov     [rbp+290h+var_40], rax
0x180024754  mov     r12, r9
0x180024757  mov     [rbp+290h+var_2C8], r8
0x18002475b  mov     r13, rdx
0x18002475e  mov     r15, rcx
0x180024761  mov     rsi, [rbp+290h+pSid]
0x180024768  mov     rax, [rbp+290h+arg_28]
0x18002476f  mov     [rbp+290h+pDestinationSid], rax
0x180024773  mov     rdi, [rbp+290h+arg_38]
0x18002477a  mov     r9d, 1; unsigned __int16
0x180024780  mov     r8d, 3B0h; unsigned __int16
0x180024786  lea     rdx, aDosidwork; "DoSidWork"
0x18002478d  lea     rcx, [rsp+390h+var_348]; this
0x180024792  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180024797  xor     ecx, ecx
0x180024799  mov     [rbp+290h+Str], rcx
0x18002479d  lea     rax, qword_1800E8530
0x1800247a4  mov     [rbp+290h+lpAccountName], rax
0x1800247a8  mov     [rbp+290h+var_2D8], rcx
0x1800247ac  mov     [rbp+290h+cbSid], 44h ; 'D'
0x1800247b3  mov     [rbp+290h+SystemName], cx
0x1800247b7  xorps   xmm0, xmm0
0x1800247ba  movups  xmmword ptr [rbp+290h+var_26E], xmm0
0x1800247be  movups  xmmword ptr [rbp+290h+var_26E+0Eh], xmm0
0x1800247c2  mov     [rsp+390h+nSize], 10h
0x1800247ca  mov     [rbp+290h+var_30C], ecx
0x1800247cd  mov     [rbp+290h+Name], cx
0x1800247d1  xor     edx, edx; Val
0x1800247d3  mov     r8d, 208h; Size
0x1800247d9  lea     rcx, [rbp+290h+var_24E]; void *
0x1800247dd  call    memset_0
0x1800247e2  mov     [rbp+290h+cchName], 105h
0x1800247e9  xor     ecx, ecx
0x1800247eb  mov     [rbp+290h+var_2E8], rcx
0x1800247ef  mov     r14d, ecx
0x1800247f2  mov     [rbp+290h+var_300], rcx
0x1800247f6  mov     ebx, ecx
0x1800247f8  mov     [rbp+290h+var_2F8], rcx
0x1800247fc  test    rdi, rdi
0x1800247ff  jz      short loc_180024803
0x180024801  mov     [rdi], ecx
0x180024803  mov     eax, 3CCh
0x180024808  test    r15, r15
0x18002480b  jnz     short loc_18002481F
0x18002480d  mov     [rsp+390h+var_348], 80070057h
0x180024815  mov     [rsp+390h+var_342], ax
0x18002481a  jmp     loc_180024CEC
0x18002481f  mov     [rsp+390h+var_344], ax
0x180024824  mov     eax, 3CDh
0x180024829  test    r13, r13
0x18002482c  jz      short loc_18002480D
0x18002482e  mov     [rsp+390h+var_344], ax
0x180024833  mov     eax, 3CEh
0x180024838  test    rsi, rsi
0x18002483b  jz      short loc_18002480D
0x18002483d  mov     [rsp+390h+var_344], ax
0x180024842  test    r12, r12
0x180024845  jnz     short loc_18002484E
0x180024847  mov     eax, 3CFh
0x18002484c  jmp     short loc_18002480D
0x18002484e  mov     eax, 3D0h
0x180024853  mov     [rsp+390h+var_344], ax
0x180024858  mov     r13, [rbp+290h+pDestinationSid]
0x18002485c  mov     eax, 3D1h
0x180024861  test    r13, r13
0x180024864  jz      short loc_18002480D
0x180024866  mov     [rsp+390h+var_344], ax
0x18002486b  mov     eax, 3D2h
0x180024870  test    rdi, rdi
0x180024873  jz      short loc_18002480D
0x180024875  mov     [rsp+390h+var_348], ecx
0x180024879  mov     [rsp+390h+var_344], ax
0x18002487e  mov     rcx, rsi; pSid
0x180024881  call    cs:__imp_IsValidSid
0x180024887  test    eax, eax
0x180024889  jnz     short loc_18002489E
0x18002488b  call    GetLastFailureAsHRESULT
0x180024890  mov     [rsp+390h+var_348], eax
0x180024894  mov     eax, 3D4h
0x180024899  jmp     loc_180024815
0x18002489e  mov     [rsp+390h+var_348], ebx
0x1800248a2  mov     eax, 3D4h
0x1800248a7  mov     [rsp+390h+var_344], ax
0x1800248ac  mov     rcx, rsi; pSid
0x1800248af  call    cs:__imp_GetLengthSid
0x1800248b5  mov     r15d, eax
0x1800248b8  lea     rcx, [rbp+290h+var_300]; struct CSdUserSidEntry **
0x1800248bc  call    ?CreateInstance@CSdUserSidEntry@@SAJPEAPEAV1@@Z; CSdUserSidEntry::CreateInstance(CSdUserSidEntry * *)
0x1800248c1  mov     [rsp+390h+var_348], eax
0x1800248c5  mov     r14, [rbp+290h+var_300]
0x1800248c9  test    eax, eax
0x1800248cb  mov     eax, 3D8h
0x1800248d0  js      loc_180024815
0x1800248d6  mov     [rsp+390h+var_344], ax
0x1800248db  mov     r8, rsi; pSourceSid
0x1800248de  mov     rdx, [r14+68h]; pDestinationSid
0x1800248e2  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x1800248e7  call    cs:__imp_CopySid
0x1800248ed  test    eax, eax
0x1800248ef  jnz     short loc_180024904
0x1800248f1  call    GetLastFailureAsHRESULT
0x1800248f6  mov     [rsp+390h+var_348], eax
0x1800248fa  mov     eax, 3D9h
0x1800248ff  jmp     loc_180024815
0x180024904  mov     [rsp+390h+var_348], ebx
0x180024908  mov     eax, 3D9h
0x18002490d  mov     [rsp+390h+var_344], ax
0x180024912  add     r12, 8
0x180024916  lea     r8, [rbp+290h+var_2E8]
0x18002491a  mov     rdx, r14
0x18002491d  mov     rcx, r12
0x180024920  call    ?Find@?$CSxList@VCSdUserSidList@@VCSdUserSidEntry@@@@QEAAJPEAVCSdUserSidEntry@@PEAPEAV2@@Z; CSxList<CSdUserSidList,CSdUserSidEntry>::Find(CSdUserSidEntry *,CSdUserSidEntry * *)
0x180024925  mov     ecx, eax
0x180024927  mov     [rsp+390h+var_348], eax
0x18002492b  test    eax, eax
0x18002492d  mov     eax, 3DBh
0x180024932  js      loc_180024815
0x180024938  mov     [rsp+390h+var_344], ax
0x18002493d  test    ecx, ecx
0x18002493f  jnz     short loc_180024997
0x180024941  mov     r8, [rbp+290h+var_2E8]
0x180024945  cmp     [r8+18h], ebx
0x180024949  jz      short loc_18002498B
0x18002494b  mov     r8, [r8+0B8h]; pSourceSid
0x180024952  mov     rdx, r13; pDestinationSid
0x180024955  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x18002495a  call    cs:__imp_CopySid
0x180024960  test    eax, eax
0x180024962  jnz     short loc_180024977
0x180024964  call    GetLastFailureAsHRESULT
0x180024969  mov     [rsp+390h+var_348], eax
0x18002496d  mov     eax, 3E1h
0x180024972  jmp     loc_180024815
0x180024977  mov     dword ptr [rdi], 1
0x18002497d  mov     [rsp+390h+var_348], ebx
0x180024981  mov     eax, 3E4h
0x180024986  jmp     loc_180024CE7
0x18002498b  mov     [rdi], ebx
0x18002498d  mov     eax, 3ECh
0x180024992  jmp     loc_180024CDF
0x180024997  lea     rcx, [rbp+290h+var_2F8]; struct CSdUserSidEntry **
0x18002499b  call    ?CreateInstance@CSdUserSidEntry@@SAJPEAPEAV1@@Z; CSdUserSidEntry::CreateInstance(CSdUserSidEntry * *)
0x1800249a0  mov     [rsp+390h+var_348], eax
0x1800249a4  mov     rbx, [rbp+290h+var_2F8]
0x1800249a8  test    eax, eax
0x1800249aa  mov     eax, 3EFh
0x1800249af  js      loc_180024815
0x1800249b5  mov     [rsp+390h+var_344], ax
0x1800249ba  mov     r8, rsi; pSourceSid
0x1800249bd  mov     rdx, [rbx+68h]; pDestinationSid
0x1800249c1  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x1800249c6  call    cs:__imp_CopySid
0x1800249cc  test    eax, eax
0x1800249ce  jnz     short loc_1800249E3
0x1800249d0  call    GetLastFailureAsHRESULT
0x1800249d5  mov     [rsp+390h+var_348], eax
0x1800249d9  mov     eax, 3F0h
0x1800249de  jmp     loc_180024815
0x1800249e3  mov     [rsp+390h+var_348], 0
0x1800249eb  mov     eax, 3F0h
0x1800249f0  mov     [rsp+390h+var_344], ax
0x1800249f5  mov     rcx, [rbp+290h+var_2C8]
0x1800249f9  mov     rax, [rcx]
0x1800249fc  lea     r9, [rbp+290h+Str]
0x180024a00  mov     r8d, r15d
0x180024a03  mov     rdx, rsi
0x180024a06  mov     rax, [rax+0C0h]
0x180024a0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a12  mov     ecx, eax
0x180024a14  mov     [rsp+390h+var_348], eax
0x180024a18  cmp     eax, 810000F0h
0x180024a1d  jz      loc_180024CB0
0x180024a23  mov     eax, 403h
0x180024a28  test    ecx, ecx
0x180024a2a  js      loc_180024815
0x180024a30  mov     [rsp+390h+var_344], ax
0x180024a35  jnz     loc_180024CB0
0x180024a3b  mov     [rbp+290h+cchName], 105h
0x180024a42  mov     [rsp+390h+nSize], 10h
0x180024a4a  lea     rax, [rbp+290h+var_30C]
0x180024a4e  mov     [rsp+390h+peUse], rax; peUse
0x180024a53  lea     rax, [rsp+390h+nSize]
0x180024a58  mov     [rsp+390h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180024a5d  lea     rax, [rbp+290h+SystemName]
0x180024a61  mov     [rsp+390h+ReferencedDomainName], rax; ReferencedDomainName
0x180024a66  lea     r9, [rbp+290h+cchName]; cchName
0x180024a6a  lea     r8, [rbp+290h+Name]; Name
0x180024a6e  mov     rdx, rsi; Sid
0x180024a71  lea     rcx, [rbp+290h+SystemName]; lpSystemName
0x180024a75  call    cs:__imp_LookupAccountSidW
0x180024a7b  mov     r15d, eax
0x180024a7e  test    eax, eax
0x180024a80  jnz     short loc_180024AAF
0x180024a82  call    cs:__imp_GetLastError
0x180024a88  cmp     eax, 534h
0x180024a8d  jz      short loc_180024AAF
0x180024a8f  call    cs:__imp_GetLastError
0x180024a95  cmp     eax, 6FDh
0x180024a9a  jz      short loc_180024AAF
0x180024a9c  call    GetLastFailureAsHRESULT
0x180024aa1  mov     [rsp+390h+var_348], eax
0x180024aa5  mov     eax, 40Bh
0x180024aaa  jmp     loc_180024815
0x180024aaf  mov     [rsp+390h+var_348], 0
0x180024ab7  mov     eax, 40Bh
0x180024abc  mov     [rsp+390h+var_344], ax
0x180024ac1  test    r15d, r15d
0x180024ac4  jnz     loc_180024CB0
0x180024aca  lea     edx, [r15+5Ch]; Ch
0x180024ace  mov     rcx, [rbp+290h+Str]; Str
0x180024ad2  call    cs:__imp_wcschr
0x180024ad8  mov     r15, rax
0x180024adb  mov     [rsp+390h+nSize], 10h
0x180024ae3  lea     rdx, [rsp+390h+nSize]; nSize
0x180024ae8  lea     rcx, [rbp+290h+SystemName]; lpBuffer
0x180024aec  call    cs:__imp_GetComputerNameW
0x180024af2  test    eax, eax
0x180024af4  jnz     short loc_180024B09
0x180024af6  call    GetLastFailureAsHRESULT
0x180024afb  mov     [rsp+390h+var_348], eax
0x180024aff  mov     eax, 413h
0x180024b04  jmp     loc_180024815
0x180024b09  mov     [rsp+390h+var_348], 0
0x180024b11  mov     eax, 413h
0x180024b16  mov     [rsp+390h+var_344], ax
0x180024b1b  mov     r8, r15; unsigned __int16 *
0x180024b1e  lea     rdx, [rbp+290h+SystemName]; unsigned __int16 *
0x180024b22  lea     rcx, [rbp+290h+lpAccountName]; this
0x180024b26  call    ?Set@CBsString@@QEAAJPEBG0@Z; CBsString::Set(ushort const *,ushort const *)
0x180024b2b  mov     [rsp+390h+var_348], eax
0x180024b2f  test    eax, eax
0x180024b31  mov     eax, 414h
0x180024b36  js      loc_180024815
0x180024b3c  mov     [rsp+390h+var_344], ax
0x180024b41  mov     [rsp+390h+nSize], 10h
0x180024b49  lea     rax, [rbp+290h+var_30C]
0x180024b4d  mov     [rsp+390h+peUse], rax; peUse
0x180024b52  lea     rax, [rsp+390h+nSize]
0x180024b57  mov     [rsp+390h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180024b5c  lea     rax, [rbp+290h+SystemName]
0x180024b60  mov     [rsp+390h+ReferencedDomainName], rax; ReferencedDomainName
0x180024b65  lea     r9, [rbp+290h+cbSid]; cbSid
0x180024b69  lea     r8, [rbp+290h+Sid]; Sid
0x180024b6d  mov     rdx, [rbp+290h+lpAccountName]; lpAccountName
0x180024b71  lea     rcx, [rbp+290h+SystemName]; lpSystemName
0x180024b75  call    cs:__imp_LookupAccountNameW
0x180024b7b  mov     r15d, eax
0x180024b7e  test    eax, eax
0x180024b80  jnz     short loc_180024BAF
0x180024b82  call    cs:__imp_GetLastError
0x180024b88  cmp     eax, 534h
0x180024b8d  jz      short loc_180024BAF
0x180024b8f  call    cs:__imp_GetLastError
0x180024b95  cmp     eax, 6FDh
0x180024b9a  jz      short loc_180024BAF
0x180024b9c  call    GetLastFailureAsHRESULT
0x180024ba1  mov     [rsp+390h+var_348], eax
0x180024ba5  mov     eax, 418h
0x180024baa  jmp     loc_180024815
0x180024baf  mov     [rsp+390h+var_348], 0
0x180024bb7  mov     eax, 418h
0x180024bbc  mov     [rsp+390h+var_344], ax
0x180024bc1  test    r15d, r15d
0x180024bc4  jz      loc_180024CB0
0x180024bca  lea     rdx, [rbp+290h+Sid]; pSid2
0x180024bce  mov     rcx, rsi; pSid1
0x180024bd1  call    cs:__imp_EqualSid
0x180024bd7  test    eax, eax
0x180024bd9  jnz     loc_180024CB0
0x180024bdf  lea     rcx, [rbp+290h+Sid]; pSid
0x180024be3  call    cs:__imp_IsValidSid
0x180024be9  test    eax, eax
0x180024beb  mov     eax, 421h
0x180024bf0  jnz     short loc_180024BFF
0x180024bf2  mov     [rsp+390h+var_348], 80004005h
0x180024bfa  jmp     loc_180024815
0x180024bff  mov     [rsp+390h+var_348], 0
0x180024c07  mov     [rsp+390h+var_344], ax
0x180024c0c  lea     r8, [rbp+290h+Sid]; pSourceSid
0x180024c10  mov     rdx, [rbx+0B8h]; pDestinationSid
0x180024c17  mov     esi, 44h ; 'D'
0x180024c1c  mov     ecx, esi; nDestinationSidLength
0x180024c1e  call    cs:__imp_CopySid
0x180024c24  test    eax, eax
0x180024c26  jnz     short loc_180024C3B
0x180024c28  call    GetLastFailureAsHRESULT
0x180024c2d  mov     [rsp+390h+var_348], eax
0x180024c31  mov     eax, 424h
  ... truncated ...
```
