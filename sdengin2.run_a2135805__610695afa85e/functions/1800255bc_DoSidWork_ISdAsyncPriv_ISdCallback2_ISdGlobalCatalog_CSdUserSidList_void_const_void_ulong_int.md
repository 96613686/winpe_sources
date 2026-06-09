# DoSidWork(ISdAsyncPriv *,ISdCallback2 *,ISdGlobalCatalog *,CSdUserSidList *,void * const,void *,ulong,int *)

- ea: `0x1800255bc`
- end: `0x180025c5f`
- name: `?DoSidWork@@YAJPEAUISdAsyncPriv@@PEAUISdCallback2@@PEAUISdGlobalCatalog@@PEAVCSdUserSidList@@QEAXPEAXKPEAH@Z`
- size: `1699`
- prototype: `__int64 __fastcall(struct ISdAsyncPriv *, struct ISdCallback2 *, struct ISdGlobalCatalog *, struct CSdUserSidList *, PSID pSid, void *, unsigned int, int *)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180023224`
- `0x180024f08`

## callees

- `0x180009d0c`
- `0x180015e70`
- `0x180015f90`
- `0x18001627c`
- `0x1800162fc`
- `0x180016710`
- `0x1800255bc`
- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`
- `0x18009e8e4`
- `0x18009f560`
- `0x1800cf56a`
- `0x1800cf5c0`
- `0x1800d1010`

## import_xrefs

- `msvcrt!wcschr` at `0x18002599a`
- `msvcrt!wcschr` at `0x18002599a`
- `KERNEL32!GetLastError` at `0x18002593e`
- `KERNEL32!GetLastError` at `0x180025951`
- `KERNEL32!GetLastError` at `0x180025a5c`
- `KERNEL32!GetLastError` at `0x180025a6f`
- `KERNEL32!GetLastError` at `0x18002593e`
- `KERNEL32!GetLastError` at `0x180025951`
- `KERNEL32!GetLastError` at `0x180025a5c`
- `KERNEL32!GetLastError` at `0x180025a6f`
- `KERNEL32!GetComputerNameW` at `0x1800259ba`
- `KERNEL32!GetComputerNameW` at `0x1800259ba`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18002578b`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180025804`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180025876`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180025b10`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180025b76`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18002578b`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180025804`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180025876`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180025b10`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180025b76`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180025ab7`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180025ab7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002574d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002574d`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180025719`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180025acf`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180025719`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180025acf`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180025a49`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180025a49`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18002592b`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18002592b`

## string_xrefs

- `0x18002561e`: `DoSidWork`

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
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, "DoSidWork", 0x3B0u, 1u);
  Str = 0;
  lpAccountName[0] = (LPCWSTR)qword_1800EE510;
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
0x1800255bc  mov     [rsp-8+arg_0], rbx
0x1800255c1  push    rbp
0x1800255c2  push    rsi
0x1800255c3  push    rdi
0x1800255c4  push    r12
0x1800255c6  push    r13
0x1800255c8  push    r14
0x1800255ca  push    r15
0x1800255cc  lea     rbp, [rsp-260h]
0x1800255d4  sub     rsp, 360h
0x1800255db  mov     rax, cs:__security_cookie
0x1800255e2  xor     rax, rsp
0x1800255e5  mov     [rbp+290h+var_40], rax
0x1800255ec  mov     r12, r9
0x1800255ef  mov     [rbp+290h+var_2C8], r8
0x1800255f3  mov     r13, rdx
0x1800255f6  mov     r15, rcx
0x1800255f9  mov     rsi, [rbp+290h+pSid]
0x180025600  mov     rax, [rbp+290h+arg_28]
0x180025607  mov     [rbp+290h+pDestinationSid], rax
0x18002560b  mov     rdi, [rbp+290h+arg_38]
0x180025612  mov     r9d, 1; unsigned __int16
0x180025618  mov     r8d, 3B0h; unsigned __int16
0x18002561e  lea     rdx, aDosidwork; "DoSidWork"
0x180025625  lea     rcx, [rsp+390h+var_348]; this
0x18002562a  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002562f  xor     ecx, ecx
0x180025631  mov     [rbp+290h+Str], rcx
0x180025635  lea     rax, qword_1800EE510
0x18002563c  mov     [rbp+290h+lpAccountName], rax
0x180025640  mov     [rbp+290h+var_2D8], rcx
0x180025644  mov     [rbp+290h+cbSid], 44h ; 'D'
0x18002564b  mov     [rbp+290h+SystemName], cx
0x18002564f  xorps   xmm0, xmm0
0x180025652  movups  xmmword ptr [rbp+290h+var_26E], xmm0
0x180025656  movups  xmmword ptr [rbp+290h+var_26E+0Eh], xmm0
0x18002565a  mov     [rsp+390h+nSize], 10h
0x180025662  mov     [rbp+290h+var_30C], ecx
0x180025665  mov     [rbp+290h+Name], cx
0x180025669  xor     edx, edx; Val
0x18002566b  mov     r8d, 208h; Size
0x180025671  lea     rcx, [rbp+290h+var_24E]; void *
0x180025675  call    memset_0
0x18002567a  mov     [rbp+290h+cchName], 105h
0x180025681  xor     ecx, ecx
0x180025683  mov     [rbp+290h+var_2E8], rcx
0x180025687  mov     r14d, ecx
0x18002568a  mov     [rbp+290h+var_300], rcx
0x18002568e  mov     ebx, ecx
0x180025690  mov     [rbp+290h+var_2F8], rcx
0x180025694  test    rdi, rdi
0x180025697  jz      short loc_18002569B
0x180025699  mov     [rdi], ecx
0x18002569b  mov     eax, 3CCh
0x1800256a0  test    r15, r15
0x1800256a3  jnz     short loc_1800256B7
0x1800256a5  mov     [rsp+390h+var_348], 80070057h
0x1800256ad  mov     [rsp+390h+var_342], ax
0x1800256b2  jmp     loc_180025BEA
0x1800256b7  mov     [rsp+390h+var_344], ax
0x1800256bc  mov     eax, 3CDh
0x1800256c1  test    r13, r13
0x1800256c4  jz      short loc_1800256A5
0x1800256c6  mov     [rsp+390h+var_344], ax
0x1800256cb  mov     eax, 3CEh
0x1800256d0  test    rsi, rsi
0x1800256d3  jz      short loc_1800256A5
0x1800256d5  mov     [rsp+390h+var_344], ax
0x1800256da  test    r12, r12
0x1800256dd  jnz     short loc_1800256E6
0x1800256df  mov     eax, 3CFh
0x1800256e4  jmp     short loc_1800256A5
0x1800256e6  mov     eax, 3D0h
0x1800256eb  mov     [rsp+390h+var_344], ax
0x1800256f0  mov     r13, [rbp+290h+pDestinationSid]
0x1800256f4  mov     eax, 3D1h
0x1800256f9  test    r13, r13
0x1800256fc  jz      short loc_1800256A5
0x1800256fe  mov     [rsp+390h+var_344], ax
0x180025703  mov     eax, 3D2h
0x180025708  test    rdi, rdi
0x18002570b  jz      short loc_1800256A5
0x18002570d  mov     [rsp+390h+var_348], ecx
0x180025711  mov     [rsp+390h+var_344], ax
0x180025716  mov     rcx, rsi; pSid
0x180025719  call    cs:__imp_IsValidSid
0x180025720  nop     dword ptr [rax+rax+00h]
0x180025725  test    eax, eax
0x180025727  jnz     short loc_18002573C
0x180025729  call    GetLastFailureAsHRESULT
0x18002572e  mov     [rsp+390h+var_348], eax
0x180025732  mov     eax, 3D4h
0x180025737  jmp     loc_1800256AD
0x18002573c  mov     [rsp+390h+var_348], ebx
0x180025740  mov     eax, 3D4h
0x180025745  mov     [rsp+390h+var_344], ax
0x18002574a  mov     rcx, rsi; pSid
0x18002574d  call    cs:__imp_GetLengthSid
0x180025754  nop     dword ptr [rax+rax+00h]
0x180025759  mov     r15d, eax
0x18002575c  lea     rcx, [rbp+290h+var_300]; struct CSdUserSidEntry **
0x180025760  call    ?CreateInstance@CSdUserSidEntry@@SAJPEAPEAV1@@Z; CSdUserSidEntry::CreateInstance(CSdUserSidEntry * *)
0x180025765  mov     [rsp+390h+var_348], eax
0x180025769  mov     r14, [rbp+290h+var_300]
0x18002576d  test    eax, eax
0x18002576f  mov     eax, 3D8h
0x180025774  js      loc_1800256AD
0x18002577a  mov     [rsp+390h+var_344], ax
0x18002577f  mov     r8, rsi; pSourceSid
0x180025782  mov     rdx, [r14+68h]; pDestinationSid
0x180025786  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x18002578b  call    cs:__imp_CopySid
0x180025792  nop     dword ptr [rax+rax+00h]
0x180025797  test    eax, eax
0x180025799  jnz     short loc_1800257AE
0x18002579b  call    GetLastFailureAsHRESULT
0x1800257a0  mov     [rsp+390h+var_348], eax
0x1800257a4  mov     eax, 3D9h
0x1800257a9  jmp     loc_1800256AD
0x1800257ae  mov     [rsp+390h+var_348], ebx
0x1800257b2  mov     eax, 3D9h
0x1800257b7  mov     [rsp+390h+var_344], ax
0x1800257bc  add     r12, 8
0x1800257c0  lea     r8, [rbp+290h+var_2E8]
0x1800257c4  mov     rdx, r14
0x1800257c7  mov     rcx, r12
0x1800257ca  call    ?Find@?$CSxList@VCSdUserSidList@@VCSdUserSidEntry@@@@QEAAJPEAVCSdUserSidEntry@@PEAPEAV2@@Z; CSxList<CSdUserSidList,CSdUserSidEntry>::Find(CSdUserSidEntry *,CSdUserSidEntry * *)
0x1800257cf  mov     ecx, eax
0x1800257d1  mov     [rsp+390h+var_348], eax
0x1800257d5  test    eax, eax
0x1800257d7  mov     eax, 3DBh
0x1800257dc  js      loc_1800256AD
0x1800257e2  mov     [rsp+390h+var_344], ax
0x1800257e7  test    ecx, ecx
0x1800257e9  jnz     short loc_180025847
0x1800257eb  mov     r8, [rbp+290h+var_2E8]
0x1800257ef  cmp     [r8+18h], ebx
0x1800257f3  jz      short loc_18002583B
0x1800257f5  mov     r8, [r8+0B8h]; pSourceSid
0x1800257fc  mov     rdx, r13; pDestinationSid
0x1800257ff  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x180025804  call    cs:__imp_CopySid
0x18002580b  nop     dword ptr [rax+rax+00h]
0x180025810  test    eax, eax
0x180025812  jnz     short loc_180025827
0x180025814  call    GetLastFailureAsHRESULT
0x180025819  mov     [rsp+390h+var_348], eax
0x18002581d  mov     eax, 3E1h
0x180025822  jmp     loc_1800256AD
0x180025827  mov     dword ptr [rdi], 1
0x18002582d  mov     [rsp+390h+var_348], ebx
0x180025831  mov     eax, 3E4h
0x180025836  jmp     loc_180025BE5
0x18002583b  mov     [rdi], ebx
0x18002583d  mov     eax, 3ECh
0x180025842  jmp     loc_180025BDD
0x180025847  lea     rcx, [rbp+290h+var_2F8]; struct CSdUserSidEntry **
0x18002584b  call    ?CreateInstance@CSdUserSidEntry@@SAJPEAPEAV1@@Z; CSdUserSidEntry::CreateInstance(CSdUserSidEntry * *)
0x180025850  mov     [rsp+390h+var_348], eax
0x180025854  mov     rbx, [rbp+290h+var_2F8]
0x180025858  test    eax, eax
0x18002585a  mov     eax, 3EFh
0x18002585f  js      loc_1800256AD
0x180025865  mov     [rsp+390h+var_344], ax
0x18002586a  mov     r8, rsi; pSourceSid
0x18002586d  mov     rdx, [rbx+68h]; pDestinationSid
0x180025871  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x180025876  call    cs:__imp_CopySid
0x18002587d  nop     dword ptr [rax+rax+00h]
0x180025882  test    eax, eax
0x180025884  jnz     short loc_180025899
0x180025886  call    GetLastFailureAsHRESULT
0x18002588b  mov     [rsp+390h+var_348], eax
0x18002588f  mov     eax, 3F0h
0x180025894  jmp     loc_1800256AD
0x180025899  mov     [rsp+390h+var_348], 0
0x1800258a1  mov     eax, 3F0h
0x1800258a6  mov     [rsp+390h+var_344], ax
0x1800258ab  mov     rcx, [rbp+290h+var_2C8]
0x1800258af  mov     rax, [rcx]
0x1800258b2  lea     r9, [rbp+290h+Str]
0x1800258b6  mov     r8d, r15d
0x1800258b9  mov     rdx, rsi
0x1800258bc  mov     rax, [rax+0C0h]
0x1800258c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800258c8  mov     ecx, eax
0x1800258ca  mov     [rsp+390h+var_348], eax
0x1800258ce  cmp     eax, 810000F0h
0x1800258d3  jz      loc_180025BAE
0x1800258d9  mov     eax, 403h
0x1800258de  test    ecx, ecx
0x1800258e0  js      loc_1800256AD
0x1800258e6  mov     [rsp+390h+var_344], ax
0x1800258eb  jnz     loc_180025BAE
0x1800258f1  mov     [rbp+290h+cchName], 105h
0x1800258f8  mov     [rsp+390h+nSize], 10h
0x180025900  lea     rax, [rbp+290h+var_30C]
0x180025904  mov     [rsp+390h+peUse], rax; peUse
0x180025909  lea     rax, [rsp+390h+nSize]
0x18002590e  mov     [rsp+390h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180025913  lea     rax, [rbp+290h+SystemName]
0x180025917  mov     [rsp+390h+ReferencedDomainName], rax; ReferencedDomainName
0x18002591c  lea     r9, [rbp+290h+cchName]; cchName
0x180025920  lea     r8, [rbp+290h+Name]; Name
0x180025924  mov     rdx, rsi; Sid
0x180025927  lea     rcx, [rbp+290h+SystemName]; lpSystemName
0x18002592b  call    cs:__imp_LookupAccountSidW
0x180025932  nop     dword ptr [rax+rax+00h]
0x180025937  mov     r15d, eax
0x18002593a  test    eax, eax
0x18002593c  jnz     short loc_180025977
0x18002593e  call    cs:__imp_GetLastError
0x180025945  nop     dword ptr [rax+rax+00h]
0x18002594a  cmp     eax, 534h
0x18002594f  jz      short loc_180025977
0x180025951  call    cs:__imp_GetLastError
0x180025958  nop     dword ptr [rax+rax+00h]
0x18002595d  cmp     eax, 6FDh
0x180025962  jz      short loc_180025977
0x180025964  call    GetLastFailureAsHRESULT
0x180025969  mov     [rsp+390h+var_348], eax
0x18002596d  mov     eax, 40Bh
0x180025972  jmp     loc_1800256AD
0x180025977  mov     [rsp+390h+var_348], 0
0x18002597f  mov     eax, 40Bh
0x180025984  mov     [rsp+390h+var_344], ax
0x180025989  test    r15d, r15d
0x18002598c  jnz     loc_180025BAE
0x180025992  lea     edx, [r15+5Ch]; Ch
0x180025996  mov     rcx, [rbp+290h+Str]; Str
0x18002599a  call    cs:__imp_wcschr
0x1800259a1  nop     dword ptr [rax+rax+00h]
0x1800259a6  mov     r15, rax
0x1800259a9  mov     [rsp+390h+nSize], 10h
0x1800259b1  lea     rdx, [rsp+390h+nSize]; nSize
0x1800259b6  lea     rcx, [rbp+290h+SystemName]; lpBuffer
0x1800259ba  call    cs:__imp_GetComputerNameW
0x1800259c1  nop     dword ptr [rax+rax+00h]
0x1800259c6  test    eax, eax
0x1800259c8  jnz     short loc_1800259DD
0x1800259ca  call    GetLastFailureAsHRESULT
0x1800259cf  mov     [rsp+390h+var_348], eax
0x1800259d3  mov     eax, 413h
0x1800259d8  jmp     loc_1800256AD
0x1800259dd  mov     [rsp+390h+var_348], 0
0x1800259e5  mov     eax, 413h
0x1800259ea  mov     [rsp+390h+var_344], ax
0x1800259ef  mov     r8, r15; unsigned __int16 *
0x1800259f2  lea     rdx, [rbp+290h+SystemName]; unsigned __int16 *
0x1800259f6  lea     rcx, [rbp+290h+lpAccountName]; this
0x1800259fa  call    ?Set@CBsString@@QEAAJPEBG0@Z; CBsString::Set(ushort const *,ushort const *)
0x1800259ff  mov     [rsp+390h+var_348], eax
0x180025a03  test    eax, eax
0x180025a05  mov     eax, 414h
0x180025a0a  js      loc_1800256AD
0x180025a10  mov     [rsp+390h+var_344], ax
0x180025a15  mov     [rsp+390h+nSize], 10h
0x180025a1d  lea     rax, [rbp+290h+var_30C]
0x180025a21  mov     [rsp+390h+peUse], rax; peUse
0x180025a26  lea     rax, [rsp+390h+nSize]
0x180025a2b  mov     [rsp+390h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180025a30  lea     rax, [rbp+290h+SystemName]
0x180025a34  mov     [rsp+390h+ReferencedDomainName], rax; ReferencedDomainName
0x180025a39  lea     r9, [rbp+290h+cbSid]; cbSid
0x180025a3d  lea     r8, [rbp+290h+Sid]; Sid
0x180025a41  mov     rdx, [rbp+290h+lpAccountName]; lpAccountName
0x180025a45  lea     rcx, [rbp+290h+SystemName]; lpSystemName
0x180025a49  call    cs:__imp_LookupAccountNameW
0x180025a50  nop     dword ptr [rax+rax+00h]
0x180025a55  mov     r15d, eax
0x180025a58  test    eax, eax
0x180025a5a  jnz     short loc_180025A95
0x180025a5c  call    cs:__imp_GetLastError
0x180025a63  nop     dword ptr [rax+rax+00h]
0x180025a68  cmp     eax, 534h
0x180025a6d  jz      short loc_180025A95
0x180025a6f  call    cs:__imp_GetLastError
0x180025a76  nop     dword ptr [rax+rax+00h]
0x180025a7b  cmp     eax, 6FDh
0x180025a80  jz      short loc_180025A95
0x180025a82  call    GetLastFailureAsHRESULT
0x180025a87  mov     [rsp+390h+var_348], eax
0x180025a8b  mov     eax, 418h
0x180025a90  jmp     loc_1800256AD
0x180025a95  mov     [rsp+390h+var_348], 0
0x180025a9d  mov     eax, 418h
0x180025aa2  mov     [rsp+390h+var_344], ax
0x180025aa7  test    r15d, r15d
0x180025aaa  jz      loc_180025BAE
0x180025ab0  lea     rdx, [rbp+290h+Sid]; pSid2
0x180025ab4  mov     rcx, rsi; pSid1
0x180025ab7  call    cs:__imp_EqualSid
0x180025abe  nop     dword ptr [rax+rax+00h]
0x180025ac3  test    eax, eax
0x180025ac5  jnz     loc_180025BAE
0x180025acb  lea     rcx, [rbp+290h+Sid]; pSid
0x180025acf  call    cs:__imp_IsValidSid
0x180025ad6  nop     dword ptr [rax+rax+00h]
0x180025adb  test    eax, eax
0x180025add  mov     eax, 421h
  ... truncated ...
```
