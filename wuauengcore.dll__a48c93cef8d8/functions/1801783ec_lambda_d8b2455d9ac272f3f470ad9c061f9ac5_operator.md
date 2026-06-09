# _lambda_d8b2455d9ac272f3f470ad9c061f9ac5_::operator()

- ea: `0x1801783ec`
- end: `0x180178892`
- name: `_lambda_d8b2455d9ac272f3f470ad9c061f9ac5_::operator()`
- size: `1190`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801782f0`

## callees

- `0x18012b618`
- `0x1801783ec`
- `0x1801832c8`
- `0x18018339c`
- `0x1801844a0`
- `0x1801844ec`
- `0x18018457c`
- `0x1801853f0`
- `0x180185430`
- `0x18018fef8`
- `0x1801900ec`
- `0x180238960`
- `0x180240d40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801784c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801784c0`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180178508`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180178508`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18017856b`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1801786e3`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18017856b`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1801786e3`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180178549`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180178549`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18017849b`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18017849b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801784d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801784d1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180178478`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180178478`
- `ESENT!JetMove` at `0x1801785e9`
- `ESENT!JetMove` at `0x180178704`
- `ESENT!JetMove` at `0x1801785e9`
- `ESENT!JetMove` at `0x180178704`

## string_xrefs

- `0x180178625`: `JetMove`
- `0x180178635`: `DS: 0x%08x: %hs failed. sesid: %Ix. tableid: %Ix`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall lambda_d8b2455d9ac272f3f470ad9c061f9ac5_::operator()(
        unsigned __int64 *a1,
        __int64 a2,
        __int64 a3,
        int a4)
{
  unsigned __int64 v5; // r14
  unsigned int v6; // ebx
  WELL_KNOWN_SID_TYPE *v7; // r15
  __int64 *v8; // rdi
  HLOCAL v9; // rax
  HLOCAL *v10; // rbx
  __int64 v11; // rdi
  int Data; // edi
  void *v13; // r13
  _DWORD *v14; // rax
  BOOL v15; // r15d
  int v16; // ebx
  unsigned int v17; // ebx
  JET_ERR v18; // eax
  int v19; // edx
  __int64 v20; // rcx
  int v21; // eax
  int v23; // [rsp+28h] [rbp-E0h]
  JET_TABLEID tableid[2]; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v25; // [rsp+68h] [rbp-A0h]
  int v26; // [rsp+70h] [rbp-98h] BYREF
  DWORD cbSid; // [rsp+74h] [rbp-94h] BYREF
  _QWORD v28[2]; // [rsp+78h] [rbp-90h] BYREF
  int v29; // [rsp+88h] [rbp-80h]
  __int64 v30; // [rsp+8Ch] [rbp-7Ch]
  int v31; // [rsp+94h] [rbp-74h]
  __int64 v32; // [rsp+98h] [rbp-70h]
  struct JET_RETRIEVECOLUMN v33[2]; // [rsp+A8h] [rbp-60h] BYREF
  _BYTE pSid2[1024]; // [rsp+108h] [rbp+0h] BYREF

  v5 = -1;
  tableid[0] = -1;
  tableid[1] = (JET_TABLEID)&CSusEseTransaction::`vftable';
  v25 = 0;
  v26 = 0;
  if ( !dword_18033A758 )
  {
    v6 = 0;
    v7 = (WELL_KNOWN_SID_TYPE *)&qword_18029F6D8;
    v8 = qword_18033A760;
    while ( 1 )
    {
      v9 = LocalAlloc(0, 0x400u);
      *v8 = (__int64)v9;
      if ( !v9 )
        break;
      cbSid = 1024;
      if ( !CreateWellKnownSid(*v7, 0, v9, &cbSid) )
      {
        GetLastError();
        break;
      }
      ++v6;
      ++v8;
      ++v7;
      if ( v6 >= 2 )
      {
        dword_18033A758 = 1;
        goto LABEL_11;
      }
    }
    v10 = (HLOCAL *)qword_18033A760;
    v11 = 2;
    do
    {
      LocalFree(*v10);
      *v10++ = 0;
      --v11;
    }
    while ( v11 );
    dword_18033A758 = 0;
  }
LABEL_11:
  Data = 0;
  v13 = *(void **)a1[2];
  v14 = (_DWORD *)a1[1];
  v15 = *v14 == 0;
  if ( *v14 )
  {
    if ( !IsValidSid(*(PSID *)a1[2]) || (v16 = *(_DWORD *)a1[1], v16 != GetLengthSid(v13)) )
    {
      Data = -2147024809;
      WUTrace(0, 0, 0x2000, 1, 0, L"Invalid arg");
      goto LABEL_44;
    }
    v17 = 0;
    do
    {
      if ( v17 >= 2 )
        break;
      if ( EqualSid(v13, (PSID)qword_18033A760[v17]) )
        goto LABEL_25;
      ++v17;
    }
    while ( !v15 );
  }
  if ( v15 )
  {
LABEL_25:
    **(_DWORD **)a1[4] = 0;
  }
  else
  {
    Data = CSusEseSession::OpenTable((CSusEseSession *)*a1, "tbLocalUserIds", tableid, a4, v23);
    if ( Data < 0
      || (Data = CSusEseTransaction::Begin(
                   (CSusEseTransaction *)&tableid[1],
                   (struct ISusEseSession *)((*a1 + 8) & ((unsigned __int128)-(__int128)*a1 >> 64))),
          Data < 0) )
    {
      v5 = tableid[0];
    }
    else
    {
      v5 = tableid[0];
      v18 = JetMove(*(_QWORD *)(*a1 + 128), tableid[0], 0x80000000, 0);
      if ( v18 )
      {
        if ( v18 != -1603 )
        {
LABEL_24:
          Data = JETErrToHRESULTAndAttemptRecovery(v18);
          WUTrace(
            0,
            0,
            0x2000,
            1,
            0,
            L"DS: 0x%08x: %hs failed. sesid: %Ix. tableid: %Ix",
            Data,
            "JetMove",
            *(_QWORD *)(*a1 + 128),
            v5);
          goto LABEL_44;
        }
      }
      else
      {
        do
        {
          memset(v33, 0, sizeof(v33));
          v33[0].columnid = dword_180338800;
          v33[0].pvData = &v26;
          v33[0].cbData = 4;
          v33[0].itagSequence = 1;
          v33[1].columnid = dword_180338804;
          v33[1].pvData = pSid2;
          v33[1].cbData = 1024;
          v33[1].itagSequence = 1;
          Data = DsqGetData(*(_QWORD *)(*a1 + 128), v5, v33, 2u);
          if ( Data < 0 )
          {
            if ( Data == -2145091577 )
              Data = -2145091576;
            goto LABEL_44;
          }
          if ( EqualSid(v13, pSid2) )
            goto LABEL_38;
          v18 = JetMove(*(_QWORD *)(*a1 + 128), v5, 1, 0);
        }
        while ( !v18 );
        if ( v18 != -1603 )
          goto LABEL_24;
      }
      if ( *(_DWORD *)a1[3] )
      {
        v30 = 0;
        v32 = 0;
        v19 = *(_DWORD *)a1[1];
        v20 = *(_QWORD *)a1[2];
        v28[0] = (unsigned int)dword_180338804;
        v28[1] = v20;
        v29 = v19;
        v31 = 1;
        Data = DsqSetData(*(_QWORD *)(*a1 + 128), v5, v28, 1, 0, 1);
        if ( Data >= 0 )
        {
          memset(v33, 0, sizeof(v33));
          v33[0].columnid = dword_180338800;
          v33[0].pvData = &v26;
          v33[0].cbData = 4;
          v33[0].itagSequence = 1;
          v21 = DsqGetData(*(_QWORD *)(*a1 + 128), v5, v33, 1u);
          Data = v21;
          if ( v21 >= 0 )
          {
            if ( (unsigned int)(v26 - 1) > 0xFFFFFFFD )
            {
              Data = -2145091582;
            }
            else
            {
              Data = CSusEseTransaction::Commit((CSusEseTransaction *)&tableid[1]);
              if ( Data >= 0 )
LABEL_38:
                **(_DWORD **)a1[4] = v26;
            }
          }
          else if ( v21 == -2145091577 )
          {
            Data = -2145091576;
          }
        }
      }
      else
      {
        **(_DWORD **)a1[4] = -1;
      }
    }
  }
LABEL_44:
  CSusEseSession::CloseTable((CSusEseSession *)*a1, v5);
  if ( Data < 0 )
    DSAttemptRecovery(Data);
  CSusEseTransaction::~CSusEseTransaction((CSusEseTransaction *)&tableid[1]);
  return (unsigned int)Data;
}

```

## disassembly

```asm
0x1801783ec  mov     rax, rsp
0x1801783ef  mov     [rax+10h], rbx
0x1801783f3  mov     [rax+18h], rsi
0x1801783f7  mov     [rax+20h], rdi
0x1801783fb  push    rbp
0x1801783fc  push    r12
0x1801783fe  push    r13
0x180178400  push    r14
0x180178402  push    r15
0x180178404  lea     rbp, [rax-438h]
0x18017840b  sub     rsp, 510h
0x180178412  mov     rax, cs:__security_cookie
0x180178419  xor     rax, rsp
0x18017841c  mov     [rbp+430h+var_30], rax
0x180178423  mov     rsi, rcx
0x180178426  or      r14, 0FFFFFFFFFFFFFFFFh
0x18017842a  mov     [rsp+530h+tableid], r14
0x18017842f  xorps   xmm0, xmm0
0x180178432  movups  xmmword ptr [rsp+530h+tableid+8], xmm0
0x180178437  lea     rax, ??_7CSusEseTransaction@@6B@; const CSusEseTransaction::`vftable'
0x18017843e  mov     [rsp+530h+tableid+8], rax
0x180178443  xor     r12d, r12d
0x180178446  mov     [rsp+530h+var_4D0], r12
0x18017844b  mov     [rsp+530h+var_4C8], r12d
0x180178450  lea     r13, qword_18033A760
0x180178457  cmp     cs:dword_18033A758, r12d
0x18017845e  jnz     loc_1801784EB
0x180178464  mov     ebx, r12d
0x180178467  lea     r15, qword_18029F6D8
0x18017846e  mov     rdi, r13
0x180178471  mov     edx, 400h; uBytes
0x180178476  xor     ecx, ecx; uFlags
0x180178478  call    cs:__imp_LocalAlloc
0x18017847e  mov     [rdi], rax
0x180178481  test    rax, rax
0x180178484  jz      short loc_1801784C6
0x180178486  mov     [rsp+530h+cbSid], 400h
0x18017848e  lea     r9, [rsp+530h+cbSid]; cbSid
0x180178493  mov     r8, rax; pSid
0x180178496  xor     edx, edx; DomainSid
0x180178498  mov     ecx, [r15]; WellKnownSidType
0x18017849b  call    cs:__imp_CreateWellKnownSid
0x1801784a1  test    eax, eax
0x1801784a3  jz      short loc_1801784C0
0x1801784a5  inc     ebx
0x1801784a7  add     rdi, 8
0x1801784ab  add     r15, 4
0x1801784af  cmp     ebx, 2
0x1801784b2  jb      short loc_180178471
0x1801784b4  mov     cs:dword_18033A758, 1
0x1801784be  jmp     short loc_1801784EB
0x1801784c0  call    cs:__imp_GetLastError
0x1801784c6  mov     rbx, r13
0x1801784c9  mov     edi, 2
0x1801784ce  mov     rcx, [rbx]; hMem
0x1801784d1  call    cs:__imp_LocalFree
0x1801784d7  mov     [rbx], r12
0x1801784da  lea     rbx, [rbx+8]
0x1801784de  sub     rdi, 1
0x1801784e2  jnz     short loc_1801784CE
0x1801784e4  mov     cs:dword_18033A758, r12d
0x1801784eb  mov     edi, r12d
0x1801784ee  mov     rax, [rsi+10h]
0x1801784f2  mov     r13, [rax]
0x1801784f5  mov     rax, [rsi+8]
0x1801784f9  mov     r15d, r12d
0x1801784fc  cmp     [rax], r12d
0x1801784ff  setz    r15b
0x180178503  jz      short loc_180178583
0x180178505  mov     rcx, r13; pSid
0x180178508  call    cs:__imp_IsValidSid
0x18017850e  test    eax, eax
0x180178510  jnz     short loc_180178540
0x180178512  mov     edi, 80070057h
0x180178517  lea     rax, aInvalidArg; "Invalid arg"
0x18017851e  mov     qword ptr [rsp+530h+var_508], rax
0x180178523  mov     [rsp+530h+var_510], r12
0x180178528  xor     edx, edx
0x18017852a  xor     ecx, ecx
0x18017852c  lea     r9d, [rdx+1]
0x180178530  mov     r8d, 2000h
0x180178536  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18017853b  jmp     loc_18017883F
0x180178540  mov     rax, [rsi+8]
0x180178544  mov     ebx, [rax]
0x180178546  mov     rcx, r13; pSid
0x180178549  call    cs:__imp_GetLengthSid
0x18017854f  cmp     ebx, eax
0x180178551  jnz     short loc_180178512
0x180178553  mov     ebx, r12d
0x180178556  cmp     ebx, 2
0x180178559  jnb     short loc_180178580
0x18017855b  mov     edx, ebx
0x18017855d  lea     rax, qword_18033A760
0x180178564  mov     rdx, [rax+rdx*8]; pSid2
0x180178568  mov     rcx, r13; pSid1
0x18017856b  call    cs:__imp_EqualSid
0x180178571  test    eax, eax
0x180178573  jnz     loc_18017865A
0x180178579  inc     ebx
0x18017857b  test    r15d, r15d
0x18017857e  jz      short loc_180178556
0x180178580  xor     r12d, r12d
0x180178583  test    r15d, r15d
0x180178586  jnz     loc_18017865D
0x18017858c  lea     r8, [rsp+530h+tableid]; unsigned __int64 *
0x180178591  lea     rdx, ?c_szTbLocalUserIds@@3QBDB; "tbLocalUserIds"
0x180178598  mov     rcx, [rsi]; this
0x18017859b  call    ?OpenTable@CSusEseSession@@QEAAJPEBDPEA_KHH@Z; CSusEseSession::OpenTable(char const *,unsigned __int64 *,int,int)
0x1801785a0  mov     edi, eax
0x1801785a2  test    eax, eax
0x1801785a4  js      loc_18017883A
0x1801785aa  mov     rax, [rsi]
0x1801785ad  lea     rcx, [rax+8]
0x1801785b1  neg     rax
0x1801785b4  sbb     rdx, rdx
0x1801785b7  and     rdx, rcx; struct ISusEseSession *
0x1801785ba  lea     rcx, [rsp+530h+tableid+8]; this
0x1801785bf  call    ?Begin@CSusEseTransaction@@QEAAJPEAUISusEseSession@@@Z; CSusEseTransaction::Begin(ISusEseSession *)
0x1801785c4  mov     edi, eax
0x1801785c6  test    eax, eax
0x1801785c8  js      loc_18017883A
0x1801785ce  mov     rcx, [rsi]
0x1801785d1  xor     r9d, r9d; grbit
0x1801785d4  mov     r8d, 80000000h; cRow
0x1801785da  mov     r14, [rsp+530h+tableid]
0x1801785df  mov     rdx, r14; tableid
0x1801785e2  mov     rcx, [rcx+80h]; sesid
0x1801785e9  call    cs:__imp_JetMove
0x1801785ef  mov     r15d, 60h ; '`'
0x1801785f5  test    eax, eax
0x1801785f7  jz      short loc_18017866C
0x1801785f9  cmp     eax, 0FFFFF9BDh
0x1801785fe  jz      loc_180178728
0x180178604  mov     ecx, eax; int
0x180178606  call    ?JETErrToHRESULTAndAttemptRecovery@@YAJJ@Z; JETErrToHRESULTAndAttemptRecovery(long)
0x18017860b  lea     r9d, [r15-5Fh]
0x18017860f  mov     edi, eax
0x180178611  mov     rax, [rsi]
0x180178614  mov     [rsp+530h+var_4E8], r14
0x180178619  mov     rax, [rax+80h]
0x180178620  mov     [rsp+530h+var_4F0], rax
0x180178625  lea     rax, aJetmove_0; "JetMove"
0x18017862c  mov     [rsp+530h+var_4F8], rax
0x180178631  mov     dword ptr [rsp+530h+var_500], edi
0x180178635  lea     rax, aDs0x08xHsFaile_0; "DS: 0x%08x: %hs failed. sesid: %Ix. tab"...
0x18017863c  xor     edx, edx
0x18017863e  mov     qword ptr [rsp+530h+var_508], rax
0x180178643  xor     ecx, ecx
0x180178645  mov     [rsp+530h+var_510], r12
0x18017864a  mov     r8d, 2000h
0x180178650  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180178655  jmp     loc_18017883F
0x18017865a  xor     r12d, r12d
0x18017865d  mov     rax, [rsi+20h]
0x180178661  mov     rcx, [rax]
0x180178664  mov     [rcx], r12d
0x180178667  jmp     loc_18017883F
0x18017866c  mov     ebx, 1
0x180178671  mov     r8, r15; Size
0x180178674  xor     edx, edx; Val
0x180178676  lea     rcx, [rbp+430h+var_490]; void *
0x18017867a  call    memset
0x18017867f  mov     eax, cs:dword_180338800
0x180178685  mov     [rbp+430h+var_490.columnid], eax
0x180178688  lea     rax, [rsp+530h+var_4C8]
0x18017868d  mov     [rbp+430h+var_490.pvData], rax
0x180178691  mov     [rbp+430h+var_490.cbData], 4
0x180178698  mov     [rbp+430h+var_490.itagSequence], ebx
0x18017869b  mov     eax, cs:dword_180338804
0x1801786a1  mov     [rbp+430h+var_460], eax
0x1801786a4  lea     rax, [rbp+430h+pSid2]
0x1801786a8  mov     [rbp+430h+var_458], rax
0x1801786ac  mov     [rbp+430h+var_450], 400h
0x1801786b3  mov     [rbp+430h+var_440], ebx
0x1801786b6  mov     rcx, [rsi]
0x1801786b9  mov     r9d, 2; unsigned int
0x1801786bf  lea     r8, [rbp+430h+var_490]; struct JET_RETRIEVECOLUMN *
0x1801786c3  mov     rdx, r14; unsigned __int64
0x1801786c6  mov     rcx, [rcx+80h]; unsigned __int64
0x1801786cd  call    ?DsqGetData@@YAJ_K0PEAUJET_RETRIEVECOLUMN@@K@Z; DsqGetData(unsigned __int64,unsigned __int64,JET_RETRIEVECOLUMN *,ulong)
0x1801786d2  mov     edi, eax
0x1801786d4  test    eax, eax
0x1801786d6  js      loc_18017882A
0x1801786dc  lea     rdx, [rbp+430h+pSid2]; pSid2
0x1801786e0  mov     rcx, r13; pSid1
0x1801786e3  call    cs:__imp_EqualSid
0x1801786e9  test    eax, eax
0x1801786eb  jnz     loc_180178814
0x1801786f1  mov     rcx, [rsi]
0x1801786f4  xor     r9d, r9d; grbit
0x1801786f7  mov     r8d, ebx; cRow
0x1801786fa  mov     rdx, r14; tableid
0x1801786fd  mov     rcx, [rcx+80h]; sesid
0x180178704  call    cs:__imp_JetMove
0x18017870a  test    eax, eax
0x18017870c  jz      loc_180178671
0x180178712  cmp     eax, 0FFFFF9BDh
0x180178717  jz      short loc_18017872D
0x180178719  mov     ecx, eax; int
0x18017871b  call    ?JETErrToHRESULTAndAttemptRecovery@@YAJJ@Z; JETErrToHRESULTAndAttemptRecovery(long)
0x180178720  mov     r9d, ebx
0x180178723  jmp     loc_18017860F
0x180178728  mov     ebx, 1
0x18017872d  mov     rax, [rsi+18h]
0x180178731  cmp     [rax], r12d
0x180178734  jnz     short loc_180178748
0x180178736  mov     rax, [rsi+20h]
0x18017873a  mov     rcx, [rax]
0x18017873d  mov     dword ptr [rcx], 0FFFFFFFFh
0x180178743  jmp     loc_18017883F
0x180178748  mov     dword ptr [rsp+530h+var_4C0+4], r12d
0x18017874d  mov     [rbp+430h+var_4AC], r12
0x180178751  mov     [rbp+430h+var_4A0], r12
0x180178755  mov     rax, [rsi+8]
0x180178759  mov     edx, [rax]
0x18017875b  mov     rax, [rsi+10h]
0x18017875f  mov     rcx, [rax]
0x180178762  mov     eax, cs:dword_180338804
0x180178768  mov     dword ptr [rsp+530h+var_4C0], eax
0x18017876c  mov     [rsp+530h+var_4B8], rcx
0x180178771  mov     [rbp+430h+var_4B0], edx
0x180178774  mov     [rbp+430h+var_4A4], ebx
0x180178777  mov     rcx, [rsi]
0x18017877a  mov     [rsp+530h+var_508], ebx
0x18017877e  mov     dword ptr [rsp+530h+var_510], r12d
0x180178783  mov     r9d, ebx
0x180178786  lea     r8, [rsp+530h+var_4C0]
0x18017878b  mov     rdx, r14
0x18017878e  mov     rcx, [rcx+80h]
0x180178795  call    ?DsqSetData@@YAJ_K0PEAUJET_SETCOLUMN@@KW4tagDsqUpdateMethod@@H@Z; DsqSetData(unsigned __int64,unsigned __int64,JET_SETCOLUMN *,ulong,tagDsqUpdateMethod,int)
0x18017879a  mov     edi, eax
0x18017879c  test    eax, eax
0x18017879e  js      loc_18017883F
0x1801787a4  mov     r8, r15; Size
0x1801787a7  xor     edx, edx; Val
0x1801787a9  lea     rcx, [rbp+430h+var_490]; void *
0x1801787ad  call    memset
0x1801787b2  mov     eax, cs:dword_180338800
0x1801787b8  mov     [rbp+430h+var_490.columnid], eax
0x1801787bb  lea     rax, [rsp+530h+var_4C8]
0x1801787c0  mov     [rbp+430h+var_490.pvData], rax
0x1801787c4  mov     [rbp+430h+var_490.cbData], 4
0x1801787cb  mov     [rbp+430h+var_490.itagSequence], ebx
0x1801787ce  mov     rcx, [rsi]
0x1801787d1  mov     r9d, ebx; unsigned int
0x1801787d4  lea     r8, [rbp+430h+var_490]; struct JET_RETRIEVECOLUMN *
0x1801787d8  mov     rdx, r14; unsigned __int64
0x1801787db  mov     rcx, [rcx+80h]; unsigned __int64
0x1801787e2  call    ?DsqGetData@@YAJ_K0PEAUJET_RETRIEVECOLUMN@@K@Z; DsqGetData(unsigned __int64,unsigned __int64,JET_RETRIEVECOLUMN *,ulong)
0x1801787e7  mov     edi, eax
0x1801787e9  test    eax, eax
0x1801787eb  jns     short loc_1801787F9
0x1801787ed  cmp     eax, 80248007h
0x1801787f2  jnz     short loc_18017883F
0x1801787f4  lea     edi, [rax+1]
0x1801787f7  jmp     short loc_18017883F
0x1801787f9  mov     eax, [rsp+530h+var_4C8]
0x1801787fd  dec     eax
0x1801787ff  cmp     eax, 0FFFFFFFDh
0x180178802  ja      short loc_180178823
0x180178804  lea     rcx, [rsp+530h+tableid+8]; this
0x180178809  call    ?Commit@CSusEseTransaction@@QEAAJXZ; CSusEseTransaction::Commit(void)
0x18017880e  mov     edi, eax
0x180178810  test    eax, eax
0x180178812  js      short loc_18017883F
0x180178814  mov     rax, [rsi+20h]
0x180178818  mov     rcx, [rax]
0x18017881b  mov     eax, [rsp+530h+var_4C8]
0x18017881f  mov     [rcx], eax
0x180178821  jmp     short loc_18017883F
0x180178823  mov     edi, 80248002h
0x180178828  jmp     short loc_18017883F
0x18017882a  mov     eax, 80248008h
0x18017882f  cmp     edi, 80248007h
0x180178835  cmovz   edi, eax
0x180178838  jmp     short loc_18017883F
0x18017883a  mov     r14, [rsp+530h+tableid]
0x18017883f  mov     rdx, r14; unsigned __int64
0x180178842  mov     rcx, [rsi]; this
0x180178845  call    ?CloseTable@CSusEseSession@@QEAAJ_K@Z; CSusEseSession::CloseTable(unsigned __int64)
0x18017884a  test    edi, edi
0x18017884c  jns     short loc_180178856
0x18017884e  mov     ecx, edi; int
0x180178850  call    ?DSAttemptRecovery@@YAXJ@Z; DSAttemptRecovery(long)
0x180178855  nop
0x180178856  lea     rcx, [rsp+530h+tableid+8]; this
0x18017885b  call    ??1CSusEseTransaction@@UEAA@XZ; CSusEseTransaction::~CSusEseTransaction(void)
0x180178860  mov     eax, edi
0x180178862  mov     rcx, [rbp+430h+var_30]
0x180178869  xor     rcx, rsp; StackCookie
0x18017886c  call    __security_check_cookie
0x180178871  lea     r11, [rsp+530h+var_20]
0x180178879  mov     rbx, [r11+38h]
0x18017887d  mov     rsi, [r11+40h]
0x180178881  mov     rdi, [r11+48h]
0x180178885  mov     rsp, r11
0x180178888  pop     r15
0x18017888a  pop     r14
0x18017888c  pop     r13
  ... truncated ...
```
