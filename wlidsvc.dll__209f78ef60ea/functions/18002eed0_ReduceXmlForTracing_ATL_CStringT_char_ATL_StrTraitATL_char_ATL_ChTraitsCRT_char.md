# ReduceXmlForTracing(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &)

- ea: `0x18002eed0`
- end: `0x18002f3b8`
- name: `?ReduceXmlForTracing@@YAJAEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@@Z`
- size: `1256`
- prototype: ``
- caller_count: `28`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18002e17c`
- `0x18005dc64`
- `0x180061390`
- `0x180065d40`
- `0x1800ca3e0`
- `0x1800caf80`
- `0x1800cb4f0`
- `0x1800cb9e0`
- `0x1800d1aa0`
- `0x1800d2000`
- `0x1800d9d70`
- `0x1800f24bc`
- `0x1800f29a4`
- `0x1800f2e20`
- `0x1800f6c30`
- `0x1800f77cc`
- `0x1800f8750`
- `0x1800f8dfc`
- `0x1800f91c0`
- `0x1800f96e4`
- `0x1800face0`
- `0x1800fb1c8`
- `0x1800fc1d0`
- `0x1800fd064`
- `0x1800fd438`
- `0x1800fd96c`
- `0x1800fdd88`
- `0x180100fd4`

## callees

- `0x18000cad0`
- `0x1800178e0`
- `0x180017e38`
- `0x18001b760`
- `0x18001b7c0`
- `0x18002eed0`
- `0x18002f3c0`
- `0x18007c408`
- `0x1800a3b60`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x18002f064`
- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x18002f064`
- `api-ms-win-crt-private-l1-1-0!_o__mbsstr` at `0x18002ef0f`
- `api-ms-win-crt-private-l1-1-0!_o__mbsstr` at `0x18002ef3f`
- `api-ms-win-crt-private-l1-1-0!_o__mbsstr` at `0x18002efc8`
- `api-ms-win-crt-private-l1-1-0!_o__mbsstr` at `0x18002f0b4`
- `api-ms-win-crt-private-l1-1-0!_o__mbsstr` at `0x18002ef0f`
- `api-ms-win-crt-private-l1-1-0!_o__mbsstr` at `0x18002ef3f`
- `api-ms-win-crt-private-l1-1-0!_o__mbsstr` at `0x18002efc8`
- `api-ms-win-crt-private-l1-1-0!_o__mbsstr` at `0x18002f0b4`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18002f108`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18002f108`

## string_xrefs

- `0x18002f0f9`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\rst.cpp`
- `0x18002f238`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\rst.cpp`
- `0x18002f284`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\rst.cpp`
- `0x18002f2d0`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\rst.cpp`
- `0x18002f31c`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\rst.cpp`
- `0x18002f368`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\rst.cpp`
- `0x18002f14b`: `ReduceXmlForTracing`
- `0x18002f257`: `ReduceXmlForTracing`
- `0x18002f2a3`: `ReduceXmlForTracing`
- `0x18002f2ef`: `ReduceXmlForTracing`
- `0x18002f33b`: `ReduceXmlForTracing`
- `0x18002f387`: `ReduceXmlForTracing`
- `0x18002ef08`: `<?xml`

## pseudocode

```c
__int64 __fastcall ReduceXmlForTracing(const unsigned __int8 **a1, const char *a2)
{
  const unsigned __int8 **v2; // rbp
  const unsigned __int8 *v3; // rcx
  int v4; // esi
  unsigned __int8 *v5; // rax
  int v6; // ebx
  int v7; // eax
  unsigned __int8 *v8; // rax
  int v9; // eax
  unsigned int v10; // r12d
  __int64 v11; // r15
  const unsigned __int8 *v12; // r13
  __int64 v13; // rcx
  char *v14; // rax
  int v15; // ebx
  unsigned __int8 *v16; // rax
  int v17; // edi
  int v18; // r14d
  const unsigned __int8 *v19; // rcx
  int v20; // ebp
  int v21; // r15d
  errno_t v22; // eax
  __int64 v23; // rcx
  unsigned __int8 *v24; // rax
  int v25; // eax
  const char *v26; // rbx
  char *v27; // rax
  __int64 v28; // rcx
  __int64 v29; // r8
  int v31; // eax
  unsigned int v33; // eax
  int v34; // ecx
  unsigned int v35; // eax
  int v36; // ecx
  unsigned int v37; // eax
  int v38; // ecx
  unsigned int v39; // eax
  int v40; // ecx
  unsigned int BaseFileName; // eax
  int v42; // ecx
  const unsigned __int8 **v43; // [rsp+40h] [rbp-C8h] BYREF
  int v44; // [rsp+48h] [rbp-C0h] BYREF
  char v45[16]; // [rsp+50h] [rbp-B8h] BYREF
  const char *v46; // [rsp+60h] [rbp-A8h]
  int v47; // [rsp+68h] [rbp-A0h]
  int v48; // [rsp+6Ch] [rbp-9Ch]
  const char *v49; // [rsp+70h] [rbp-98h]
  __int64 v50; // [rsp+78h] [rbp-90h]
  int *v51; // [rsp+80h] [rbp-88h]
  __int64 v52; // [rsp+88h] [rbp-80h]
  const char *v53; // [rsp+90h] [rbp-78h]
  __int64 v54; // [rsp+98h] [rbp-70h]
  const unsigned __int8 ***v55; // [rsp+A0h] [rbp-68h]
  __int64 v56; // [rsp+A8h] [rbp-60h]

  v2 = a1;
  v43 = a1;
  v3 = *a1;
  v4 = 0;
  if ( *((int *)v3 - 4) >= 0 )
  {
    v5 = _mbsstr(v3, "<?xml");
    if ( v5 )
    {
      v6 = (_DWORD)v5 - *(_DWORD *)v2;
      if ( v6 >= 0 )
      {
        v7 = v6 + 5;
        if ( v6 + 5 >= 0 )
        {
          a2 = (const char *)*v2;
          if ( v7 <= *((_DWORD *)*v2 - 4) )
          {
            v8 = _mbsstr((const unsigned __int8 *)&a2[v7], "?>");
            if ( v8 )
            {
              v9 = (_DWORD)v8 - *(_DWORD *)v2;
              if ( v9 >= 0 )
                ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::Delete(
                  v2,
                  (unsigned int)v6,
                  (unsigned int)(v9 - v6 + 2));
            }
          }
        }
      }
    }
  }
  v10 = 0;
  v11 = -1;
  while ( v10 < 0xF )
  {
    v12 = (const unsigned __int8 *)off_180130F40[v10];
    if ( !v12 )
    {
      v4 = -2147024809;
LABEL_42:
      switch ( dword_1801C3ABC )
      {
        case 4:
          if ( byte_1801C36C3 < 0 )
          {
            v26 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp";
            v27 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp", 92);
            if ( v27 )
              v26 = v27 + 1;
            LODWORD(v43) = v4;
            v44 = 8834;
            if ( v26 )
            {
              while ( v26[++v11] != 0 )
                ;
              v31 = v11 + 1;
            }
            else
            {
              v31 = 5;
              v26 = "NULL";
            }
            v47 = v31;
            v46 = v26;
            v49 = "ReduceXmlForTracing";
            v48 = 0;
            v51 = &v44;
            v53 = "hr = StringCchLengthA(strNamespace, STRSAFE_MAX_CCH, &namespaceLen)";
            v55 = &v43;
            v50 = 20;
            v52 = 4;
            v54 = 68;
            v56 = 4;
            McGenEventWrite_EventWriteTransfer(v28, WlidSvc_TraceFailure, v29, 6, v45);
          }
          break;
        case 5:
          if ( (byte_1801C36C5 & 0x10) != 0 )
          {
            BaseFileName = (unsigned int)MsaTracingInternal::GetBaseFileName(
                                           (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\sv"
                                                                 "ccommon\\rst.cpp",
                                           a2);
            McTemplateU0ssqsd_EventWriteTransfer(
              v42,
              (unsigned int)WlidModern_TraceFailure,
              BaseFileName,
              (unsigned int)"ReduceXmlForTracing",
              130,
              (__int64)"hr = StringCchLengthA(strNamespace, STRSAFE_MAX_CCH, &namespaceLen)",
              v4);
          }
          break;
        case 6:
          if ( (byte_1801C36C7 & 1) != 0 )
          {
            v39 = (unsigned int)MsaTracingInternal::GetBaseFileName(
                                  (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
                                  a2);
            McTemplateU0ssqsd_EventWriteTransfer(
              v40,
              (unsigned int)WlidCli_TraceFailure,
              v39,
              (unsigned int)"ReduceXmlForTracing",
              130,
              (__int64)"hr = StringCchLengthA(strNamespace, STRSAFE_MAX_CCH, &namespaceLen)",
              v4);
          }
          break;
        case 7:
          if ( (byte_1801C36C8 & 1) != 0 )
          {
            v37 = (unsigned int)MsaTracingInternal::GetBaseFileName(
                                  (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
                                  a2);
            McTemplateU0ssqsd_EventWriteTransfer(
              v38,
              (unsigned int)WlidProv_TraceFailure,
              v37,
              (unsigned int)"ReduceXmlForTracing",
              130,
              (__int64)"hr = StringCchLengthA(strNamespace, STRSAFE_MAX_CCH, &namespaceLen)",
              v4);
          }
          break;
        case 8:
          if ( (byte_1801C36C9 & 2) != 0 )
          {
            v35 = (unsigned int)MsaTracingInternal::GetBaseFileName(
                                  (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
                                  a2);
            McTemplateU0ssqsd_EventWriteTransfer(
              v36,
              (unsigned int)WlidBho_TraceFailure,
              v35,
              (unsigned int)"ReduceXmlForTracing",
              130,
              (__int64)"hr = StringCchLengthA(strNamespace, STRSAFE_MAX_CCH, &namespaceLen)",
              v4);
          }
          break;
        default:
          if ( dword_1801C3ABC == 9 && (byte_1801C36CA & 2) != 0 )
          {
            v33 = (unsigned int)MsaTracingInternal::GetBaseFileName(
                                  (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
                                  a2);
            McTemplateU0ssqsd_EventWriteTransfer(
              v34,
              (unsigned int)TokenProvider_TraceFailure,
              v33,
              (unsigned int)"ReduceXmlForTracing",
              130,
              (__int64)"hr = StringCchLengthA(strNamespace, STRSAFE_MAX_CCH, &namespaceLen)",
              v4);
          }
          break;
      }
      return (unsigned int)v4;
    }
    v13 = 0x7FFFFFFF;
    v14 = off_180130F40[v10];
    while ( *v14 )
    {
      ++v14;
      if ( !--v13 )
      {
        v15 = 0;
        v4 = -2147024809;
        goto LABEL_17;
      }
    }
    v15 = 0x7FFFFFFF - v13;
    v4 = 0;
LABEL_17:
    if ( v4 < 0 )
      goto LABEL_42;
    if ( *((int *)*v2 - 4) >= 0 )
    {
      v16 = _mbsstr(*v2, v12);
      v17 = v16 ? (_DWORD)v16 - *(_DWORD *)v2 : -1;
      if ( v17 >= 0 )
      {
        while ( 1 )
        {
          v18 = v15;
          if ( v15 < 0 )
            v18 = 0;
          if ( 0x7FFFFFFF - v18 < v17 )
            break;
          v19 = *v2;
          v20 = *((_DWORD *)*v2 - 4);
          if ( v18 + v17 > v20 )
            v18 = v20 - v17;
          if ( v18 <= 0 )
          {
            v2 = v43;
          }
          else
          {
            v21 = v20 - v18;
            if ( *((int *)v19 - 2) > 1 )
              ATL::CSimpleStringT<char,0>::Fork(v43, (unsigned int)v20);
            v22 = memmove_s((void *const)&(*v43)[v17], v20 - v18 - v17 + 1, &(*v43)[v18 + v17], v20 - v18 - v17 + 1);
            ATL::AtlCrtErrorCheck(v22);
            if ( v21 < 0 )
              break;
            v2 = v43;
            if ( v21 > *((_DWORD *)*v43 - 3) )
              break;
            *((_DWORD *)*v43 - 4) = v21;
            v23 = v21;
            v11 = -1;
            (*v2)[v23] = 0;
          }
          if ( *((int *)*v2 - 4) >= 0 )
          {
            v24 = _mbsstr(*v2, v12);
            v25 = v24 ? (_DWORD)v24 - *(_DWORD *)v2 : -1;
            v17 = v25;
            if ( v25 >= 0 )
              continue;
          }
          goto LABEL_22;
        }
        ATL::AtlThrowImpl(-2147024809);
      }
    }
LABEL_22:
    ++v10;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002eed0  push    rbx
0x18002eed2  push    rbp
0x18002eed3  push    rsi
0x18002eed4  push    rdi
0x18002eed5  push    r12
0x18002eed7  push    r13
0x18002eed9  push    r14
0x18002eedb  push    r15
0x18002eedd  sub     rsp, 0C8h
0x18002eee4  mov     rax, cs:__security_cookie
0x18002eeeb  xor     rax, rsp
0x18002eeee  mov     [rsp+108h+var_58], rax
0x18002eef6  mov     rbp, rcx
0x18002eef9  mov     [rsp+108h+var_C8], rcx
0x18002eefe  mov     rcx, [rcx]; Str
0x18002ef01  xor     esi, esi
0x18002ef03  cmp     [rcx-10h], esi
0x18002ef06  jl      short loc_18002EF5F
0x18002ef08  lea     rdx, Substr; "<?xml"
0x18002ef0f  call    cs:__imp__mbsstr
0x18002ef15  mov     rbx, rax
0x18002ef18  test    rax, rax
0x18002ef1b  jz      short loc_18002EF5F
0x18002ef1d  sub     ebx, [rbp+0]
0x18002ef20  js      short loc_18002EF5F
0x18002ef22  lea     eax, [rbx+5]
0x18002ef25  test    eax, eax
0x18002ef27  js      short loc_18002EF5F
0x18002ef29  mov     rdx, [rbp+0]
0x18002ef2d  cmp     eax, [rdx-10h]
0x18002ef30  jg      short loc_18002EF5F
0x18002ef32  movsxd  rcx, eax
0x18002ef35  add     rcx, rdx; Str
0x18002ef38  lea     rdx, asc_18013C714; "?>"
0x18002ef3f  call    cs:__imp__mbsstr
0x18002ef45  test    rax, rax
0x18002ef48  jz      short loc_18002EF5F
0x18002ef4a  sub     eax, [rbp+0]
0x18002ef4d  js      short loc_18002EF5F
0x18002ef4f  sub     eax, ebx
0x18002ef51  mov     edx, ebx
0x18002ef53  mov     rcx, rbp
0x18002ef56  lea     r8d, [rax+2]
0x18002ef5a  call    ?Delete@?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAAHHH@Z; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::Delete(int,int)
0x18002ef5f  xor     r12d, r12d
0x18002ef62  mov     r15, 0FFFFFFFFFFFFFFFFh
0x18002ef69  lea     rcx, off_180130F40; " xmlns:ds=\"http://www.w3.org/2000/09/x"...
0x18002ef70  cmp     r12d, 0Fh
0x18002ef74  jnb     loc_18002F1CF
0x18002ef7a  movsxd  rax, r12d
0x18002ef7d  mov     r13, [rcx+rax*8]
0x18002ef81  test    r13, r13
0x18002ef84  jz      loc_18002F200
0x18002ef8a  mov     ecx, 7FFFFFFFh
0x18002ef8f  mov     rax, r13
0x18002ef92  cmp     byte ptr [rax], 0
0x18002ef95  jz      short loc_18002EFA9
0x18002ef97  inc     rax
0x18002ef9a  sub     rcx, 1
0x18002ef9e  jnz     short loc_18002EF92
0x18002efa0  xor     ebx, ebx
0x18002efa2  mov     esi, 80070057h
0x18002efa7  jmp     short loc_18002EFB3
0x18002efa9  mov     ebx, 7FFFFFFFh
0x18002efae  sub     rbx, rcx
0x18002efb1  xor     esi, esi
0x18002efb3  test    esi, esi
0x18002efb5  js      loc_18002F0DD
0x18002efbb  mov     rcx, [rbp+0]; Str
0x18002efbf  cmp     dword ptr [rcx-10h], 0
0x18002efc3  jl      short loc_18002EFDD
0x18002efc5  mov     rdx, r13; Substr
0x18002efc8  call    cs:__imp__mbsstr
0x18002efce  mov     rdi, rax
0x18002efd1  test    rax, rax
0x18002efd4  jz      short loc_18002EFE2
0x18002efd6  sub     edi, [rbp+0]
0x18002efd9  test    edi, edi
0x18002efdb  jns     short loc_18002EFF0
0x18002efdd  inc     r12d
0x18002efe0  jmp     short loc_18002EF69
0x18002efe2  mov     edi, r15d
0x18002efe5  jmp     short loc_18002EFD9
0x18002eff0  xor     eax, eax
0x18002eff2  mov     r14d, ebx
0x18002eff5  test    ebx, ebx
0x18002eff7  cmovs   r14d, eax
0x18002effb  mov     eax, 7FFFFFFFh
0x18002f000  sub     eax, r14d
0x18002f003  cmp     eax, edi
0x18002f005  jl      loc_18002F1F5
0x18002f00b  mov     rcx, [rbp+0]
0x18002f00f  lea     eax, [r14+rdi]
0x18002f013  mov     ebp, [rcx-10h]
0x18002f016  cmp     eax, ebp
0x18002f018  jle     short loc_18002F020
0x18002f01a  mov     r14d, ebp
0x18002f01d  sub     r14d, edi
0x18002f020  test    r14d, r14d
0x18002f023  jle     loc_18002F0D6
0x18002f029  mov     r15d, ebp
0x18002f02c  sub     r15d, r14d
0x18002f02f  cmp     dword ptr [rcx-8], 1
0x18002f033  jle     short loc_18002F041
0x18002f035  mov     rcx, [rsp+108h+var_C8]
0x18002f03a  mov     edx, ebp
0x18002f03c  call    ?Fork@?$CSimpleStringT@D$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<char,0>::Fork(int)
0x18002f041  mov     rax, [rsp+108h+var_C8]
0x18002f046  sub     ebp, r14d
0x18002f049  sub     ebp, edi
0x18002f04b  movsxd  r8, r14d
0x18002f04e  inc     ebp
0x18002f050  movsxd  rdx, ebp; DestinationSize
0x18002f053  mov     rcx, [rax]
0x18002f056  mov     r9, rdx; SourceSize
0x18002f059  add     r8, rcx
0x18002f05c  mov     eax, edi
0x18002f05e  add     r8, rax; Source
0x18002f061  add     rcx, rax; Destination
0x18002f064  call    cs:__imp_memmove_s
0x18002f06a  mov     ecx, eax; int
0x18002f06c  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18002f071  test    r15d, r15d
0x18002f074  js      loc_18002F1F5
0x18002f07a  mov     rbp, [rsp+108h+var_C8]
0x18002f07f  mov     rax, [rbp+0]
0x18002f083  cmp     r15d, [rax-0Ch]
0x18002f087  jg      loc_18002F1F5
0x18002f08d  mov     [rax-10h], r15d
0x18002f091  mov     rax, [rbp+0]
0x18002f095  movsxd  rcx, r15d
0x18002f098  mov     r15, 0FFFFFFFFFFFFFFFFh
0x18002f09f  mov     byte ptr [rcx+rax], 0
0x18002f0a3  mov     rcx, [rbp+0]; Str
0x18002f0a7  cmp     dword ptr [rcx-10h], 0
0x18002f0ab  jl      loc_18002EFDD
0x18002f0b1  mov     rdx, r13; Substr
0x18002f0b4  call    cs:__imp__mbsstr
0x18002f0ba  test    rax, rax
0x18002f0bd  jz      short loc_18002F0D1
0x18002f0bf  sub     eax, [rbp+0]
0x18002f0c2  mov     edi, eax
0x18002f0c4  test    eax, eax
0x18002f0c6  js      loc_18002EFDD
0x18002f0cc  jmp     loc_18002EFF0
0x18002f0d1  mov     eax, r15d
0x18002f0d4  jmp     short loc_18002F0C2
0x18002f0d6  mov     rbp, [rsp+108h+var_C8]
0x18002f0db  jmp     short loc_18002F0A3
0x18002f0dd  mov     ecx, cs:dword_1801C3ABC
0x18002f0e3  cmp     ecx, 4
0x18002f0e6  jnz     loc_18002F20A
0x18002f0ec  cmp     cs:byte_1801C36C3, 0
0x18002f0f3  jge     loc_18002F1CF
0x18002f0f9  lea     rbx, aOnecoreuapDsEx_94; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18002f100  mov     edx, 5Ch ; '\'; Ch
0x18002f105  mov     rcx, rbx; Str
0x18002f108  call    cs:__imp_strrchr
0x18002f10e  test    rax, rax
0x18002f111  jz      short loc_18002F117
0x18002f113  lea     rbx, [rax+1]
0x18002f117  mov     dword ptr [rsp+108h+var_C8], esi
0x18002f11b  mov     [rsp+108h+var_C0], 2282h
0x18002f123  test    rbx, rbx
0x18002f126  jz      loc_18002F3A7
0x18002f12c  nop     dword ptr [rax+00h]
0x18002f130  cmp     byte ptr [rbx+r15+1], 0
0x18002f136  lea     r15, [r15+1]
0x18002f13a  jnz     short loc_18002F130
0x18002f13c  lea     eax, [r15+1]
0x18002f140  mov     [rsp+108h+var_A0], eax
0x18002f144  lea     rdx, WlidSvc_TraceFailure
0x18002f14b  lea     rax, aReducexmlfortr; "ReduceXmlForTracing"
0x18002f152  mov     [rsp+108h+var_A8], rbx
0x18002f157  mov     [rsp+108h+var_98], rax
0x18002f15c  mov     r9d, 6
0x18002f162  lea     rax, [rsp+108h+var_C0]
0x18002f167  mov     [rsp+108h+var_9C], 0
0x18002f16f  mov     [rsp+108h+var_88], rax
0x18002f177  lea     rax, aHrStringcchlen_3; "hr = StringCchLengthA(strNamespace, STR"...
0x18002f17e  mov     [rsp+108h+var_78], rax
0x18002f186  lea     rax, [rsp+108h+var_C8]
0x18002f18b  mov     [rsp+108h+var_68], rax
0x18002f193  lea     rax, [rsp+108h+var_B8]
0x18002f198  mov     [rsp+108h+var_E8], rax
0x18002f19d  mov     [rsp+108h+var_90], 14h
0x18002f1a6  mov     [rsp+108h+var_80], 4
0x18002f1b2  mov     [rsp+108h+var_70], 44h ; 'D'
0x18002f1be  mov     [rsp+108h+var_60], 4
0x18002f1ca  call    McGenEventWrite_EventWriteTransfer
0x18002f1cf  mov     eax, esi
0x18002f1d1  mov     rcx, [rsp+108h+var_58]
0x18002f1d9  xor     rcx, rsp; StackCookie
0x18002f1dc  call    __security_check_cookie
0x18002f1e1  add     rsp, 0C8h
0x18002f1e8  pop     r15
0x18002f1ea  pop     r14
0x18002f1ec  pop     r13
0x18002f1ee  pop     r12
0x18002f1f0  pop     rdi
0x18002f1f1  pop     rsi
0x18002f1f2  pop     rbp
0x18002f1f3  pop     rbx
0x18002f1f4  retn
0x18002f1f5  mov     ecx, 80070057h; int
0x18002f1fa  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002f200  mov     esi, 80070057h
0x18002f205  jmp     loc_18002F0DD
0x18002f20a  sub     ecx, 5
0x18002f20d  jz      loc_18002F35B
0x18002f213  sub     ecx, 1
0x18002f216  jz      loc_18002F30F
0x18002f21c  sub     ecx, 1
0x18002f21f  jz      loc_18002F2C3
0x18002f225  sub     ecx, 1
0x18002f228  jz      short loc_18002F277
0x18002f22a  cmp     ecx, 1
0x18002f22d  jnz     short loc_18002F1CF
0x18002f22f  test    cs:byte_1801C36CA, 2
0x18002f236  jz      short loc_18002F1CF
0x18002f238  lea     rcx, aOnecoreuapDsEx_94; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18002f23f  call    ?GetBaseFileName@MsaTracingInternal@@YAPEBDPEBD@Z; MsaTracingInternal::GetBaseFileName(char const *)
0x18002f244  mov     r8, rax
0x18002f247  mov     [rsp+108h+var_D8], esi
0x18002f24b  lea     rax, aHrStringcchlen_3; "hr = StringCchLengthA(strNamespace, STR"...
0x18002f252  mov     [rsp+108h+var_E0], rax
0x18002f257  lea     r9, aReducexmlfortr; "ReduceXmlForTracing"
0x18002f25e  lea     rdx, TokenProvider_TraceFailure
0x18002f265  mov     dword ptr [rsp+108h+var_E8], 2282h
0x18002f26d  call    McTemplateU0ssqsd_EventWriteTransfer
0x18002f272  jmp     loc_18002F1CF
0x18002f277  test    cs:byte_1801C36C9, 2
0x18002f27e  jz      loc_18002F1CF
0x18002f284  lea     rcx, aOnecoreuapDsEx_94; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18002f28b  call    ?GetBaseFileName@MsaTracingInternal@@YAPEBDPEBD@Z; MsaTracingInternal::GetBaseFileName(char const *)
0x18002f290  mov     r8, rax
0x18002f293  mov     [rsp+108h+var_D8], esi
0x18002f297  lea     rax, aHrStringcchlen_3; "hr = StringCchLengthA(strNamespace, STR"...
0x18002f29e  mov     [rsp+108h+var_E0], rax
0x18002f2a3  lea     r9, aReducexmlfortr; "ReduceXmlForTracing"
0x18002f2aa  lea     rdx, WlidBho_TraceFailure
0x18002f2b1  mov     dword ptr [rsp+108h+var_E8], 2282h
0x18002f2b9  call    McTemplateU0ssqsd_EventWriteTransfer
0x18002f2be  jmp     loc_18002F1CF
0x18002f2c3  test    cs:byte_1801C36C8, 1
0x18002f2ca  jz      loc_18002F1CF
0x18002f2d0  lea     rcx, aOnecoreuapDsEx_94; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18002f2d7  call    ?GetBaseFileName@MsaTracingInternal@@YAPEBDPEBD@Z; MsaTracingInternal::GetBaseFileName(char const *)
0x18002f2dc  mov     r8, rax
0x18002f2df  mov     [rsp+108h+var_D8], esi
0x18002f2e3  lea     rax, aHrStringcchlen_3; "hr = StringCchLengthA(strNamespace, STR"...
0x18002f2ea  mov     [rsp+108h+var_E0], rax
0x18002f2ef  lea     r9, aReducexmlfortr; "ReduceXmlForTracing"
0x18002f2f6  lea     rdx, WlidProv_TraceFailure
0x18002f2fd  mov     dword ptr [rsp+108h+var_E8], 2282h
0x18002f305  call    McTemplateU0ssqsd_EventWriteTransfer
0x18002f30a  jmp     loc_18002F1CF
0x18002f30f  test    cs:byte_1801C36C7, 1
0x18002f316  jz      loc_18002F1CF
0x18002f31c  lea     rcx, aOnecoreuapDsEx_94; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18002f323  call    ?GetBaseFileName@MsaTracingInternal@@YAPEBDPEBD@Z; MsaTracingInternal::GetBaseFileName(char const *)
0x18002f328  mov     r8, rax
0x18002f32b  mov     [rsp+108h+var_D8], esi
0x18002f32f  lea     rax, aHrStringcchlen_3; "hr = StringCchLengthA(strNamespace, STR"...
0x18002f336  mov     [rsp+108h+var_E0], rax
0x18002f33b  lea     r9, aReducexmlfortr; "ReduceXmlForTracing"
0x18002f342  lea     rdx, WlidCli_TraceFailure
0x18002f349  mov     dword ptr [rsp+108h+var_E8], 2282h
0x18002f351  call    McTemplateU0ssqsd_EventWriteTransfer
0x18002f356  jmp     loc_18002F1CF
0x18002f35b  test    cs:byte_1801C36C5, 10h
0x18002f362  jz      loc_18002F1CF
0x18002f368  lea     rcx, aOnecoreuapDsEx_94; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18002f36f  call    ?GetBaseFileName@MsaTracingInternal@@YAPEBDPEBD@Z; MsaTracingInternal::GetBaseFileName(char const *)
0x18002f374  mov     r8, rax
0x18002f377  mov     [rsp+108h+var_D8], esi
0x18002f37b  lea     rax, aHrStringcchlen_3; "hr = StringCchLengthA(strNamespace, STR"...
0x18002f382  mov     [rsp+108h+var_E0], rax
0x18002f387  lea     r9, aReducexmlfortr; "ReduceXmlForTracing"
0x18002f38e  lea     rdx, WlidModern_TraceFailure
0x18002f395  mov     dword ptr [rsp+108h+var_E8], 2282h
0x18002f39d  call    McTemplateU0ssqsd_EventWriteTransfer
0x18002f3a2  jmp     loc_18002F1CF
0x18002f3a7  mov     eax, 5
0x18002f3ac  lea     rbx, aNull_0; "NULL"
0x18002f3b3  jmp     loc_18002F140
```
