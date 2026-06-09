# HostErrorReportingManager::CwchFormatAndPrint(SQLError *,int,uint,wchar_t const *,int,wchar_t *,void *,uint,EFormatType const *,char *)

- ea: `0x100417db0`
- end: `0x10041838f`
- name: `?CwchFormatAndPrint@HostErrorReportingManager@@UEAAHPEAVSQLError@@HIPEB_WHPEA_WPEAXIPEBW4EFormatType@@PEAD@Z`
- size: `1503`
- prototype: `__int64 __fastcall(HostErrorReportingManager *__hidden this, struct SQLError *, int, unsigned int, const wchar_t *, int, wchar_t *, void *, unsigned int, const enum EFormatType *, char *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x100416000`
- `0x1004168e0`
- `0x100417db0`
- `0x10045d510`

## import_xrefs

- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100418044`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100418044`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100417f51`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100417f51`
- `sqldk!??_V@YAXPEAX@Z` at `0x100417f10`
- `sqldk!??_V@YAXPEAX@Z` at `0x100417fc9`
- `sqldk!??_V@YAXPEAX@Z` at `0x100418324`
- `sqldk!??_V@YAXPEAX@Z` at `0x10041832e`
- `sqldk!??_V@YAXPEAX@Z` at `0x100417f10`
- `sqldk!??_V@YAXPEAX@Z` at `0x100417fc9`
- `sqldk!??_V@YAXPEAX@Z` at `0x100418324`
- `sqldk!??_V@YAXPEAX@Z` at `0x10041832e`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1004180ca`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10041831a`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1004180ca`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10041831a`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100417f00`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100417fb9`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100417f00`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100417fb9`
- `sqldk!SystemThread_TlsIndex` at `0x100417deb`
- `sqldk!SystemThread_TlsIndex` at `0x100417e1c`
- `sqldk!SystemThread_TlsIndex` at `0x100417e8a`
- `sqldk!SystemThread_TlsIndex` at `0x100417f62`
- `sqldk!SystemThread_TlsIndex` at `0x100417fe5`
- `sqldk!SystemThread_TlsOffset` at `0x100417df4`
- `sqldk!SystemThread_TlsOffset` at `0x100417e25`
- `sqldk!SystemThread_TlsOffset` at `0x100417e93`
- `sqldk!SystemThread_TlsOffset` at `0x100417f6b`
- `sqldk!SystemThread_TlsOffset` at `0x100417fee`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100417e0d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100417e40`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100417eae`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100417f86`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100418009`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100417e0d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100417e40`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100417eae`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100417f86`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100418009`

## string_xrefs

- `0x100417eeb`: `Sql\Ntdbms\xdb\common\hosterrorreport.cpp`
- `0x100417fa0`: `Sql\Ntdbms\xdb\common\hosterrorreport.cpp`
- `0x100418032`: `Sql\Ntdbms\xdb\common\hosterrorreport.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall HostErrorReportingManager::CwchFormatAndPrint(
        HostErrorReportingManager *this,
        struct SQLError *a2,
        __int64 a3,
        char a4,
        const wchar_t *a5,
        int a6,
        wchar_t *a7,
        void *a8,
        unsigned int a9,
        const enum EFormatType *a10,
        char *a11)
{
  char v13; // r13
  int v14; // esi
  __int64 v15; // rbx
  __int64 v16; // rax
  int v18; // edi
  __int64 v19; // rbx
  __int64 v20; // r10
  unsigned __int64 v21; // rcx
  unsigned __int64 v22; // rax
  wchar_t *v23; // r15
  int v24; // r12d
  wchar_t *v25; // rbp
  __int64 v26; // rbx
  __int64 v27; // rdx
  __int64 v28; // rbx
  __int64 v29; // rdx
  struct CFormattedParams *v30; // rax
  struct CFormattedParams *v31; // rdi
  unsigned int v32; // ecx
  unsigned int v33; // r11d
  int v34; // r8d
  int v35; // r9d
  __int64 v36; // rcx
  __int64 v37; // r10
  unsigned int v38; // edx
  char *v39; // rcx
  __int64 v40; // rax
  unsigned __int8 v41; // bl
  int v42; // edx
  int v43; // r10d
  char *v44; // r11
  unsigned __int8 *v45; // r9
  signed __int64 v46; // r8
  __int16 v47; // ax
  int v48; // eax
  bool v49; // zf
  int v50; // ecx
  int v51; // edx
  wchar_t *v52; // rbx
  wchar_t *v53; // [rsp+20h] [rbp-B8h]
  int v54; // [rsp+70h] [rbp-68h] BYREF
  wchar_t *v55; // [rsp+78h] [rbp-60h]
  wchar_t *v56; // [rsp+80h] [rbp-58h]
  struct CFormattedParams *v57; // [rsp+88h] [rbp-50h]
  __int64 v58; // [rsp+90h] [rbp-48h]
  struct IMemObj *v59; // [rsp+98h] [rbp-40h]
  struct CFormattedParams *v60; // [rsp+A0h] [rbp-38h]

  v58 = -2;
  v13 = 1;
  v14 = 0;
  if ( !*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                  + SystemThread_TlsOffset
                  + 256LL) )
    SystemThread::MakeMiniSOSThread(0);
  v15 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v16 = *(_QWORD *)(v15 + 256);
  if ( !v16 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v16 = *(_QWORD *)(v15 + 256);
  }
  if ( (*(_BYTE *)(v16 + 616) & 0x40) != 0 )
    return 0;
  if ( *((_DWORD *)a2 + 4) == 1 )
    goto LABEL_72;
  v56 = 0;
  v55 = 0;
  v57 = 0;
  v18 = *((_DWORD *)a2 + 1);
  v19 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v20 = *(_QWORD *)(v19 + 256);
  if ( !v20 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v20 = *(_QWORD *)(v19 + 256);
  }
  v21 = 2085;
  if ( v18 > 10 )
    v21 = 4170;
  v22 = 2 * v21;
  if ( !is_mul_ok(v21, 2u) )
    v22 = -1;
  v23 = (wchar_t *)operator new[](
                     v22,
                     *(struct IMemObj **)(v20 + 1000),
                     1,
                     "Sql\\Ntdbms\\xdb\\common\\hosterrorreport.cpp",
                     260,
                     6u);
  if ( v23 )
    operator delete[](0);
  v56 = v23;
  v24 = a4 & 0x10;
  if ( v24 )
  {
    v25 = a7;
    if ( !a7 )
      utassert_fail(1u, "NULL != pwchOutMsg", "ErrorReportUtils.cpp", 263, 0);
  }
  else
  {
    v26 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v27 = *(_QWORD *)(v26 + 256);
    if ( !v27 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v27 = *(_QWORD *)(v26 + 256);
    }
    v25 = (wchar_t *)operator new[](
                       0x1000u,
                       *(struct IMemObj **)(v27 + 1000),
                       1,
                       "Sql\\Ntdbms\\xdb\\common\\hosterrorreport.cpp",
                       268,
                       6u);
    if ( v25 )
      operator delete[](0);
    v55 = v25;
  }
  v54 = 271;
  v28 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v29 = *(_QWORD *)(v28 + 256);
  if ( !v29 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v29 = *(_QWORD *)(v28 + 256);
  }
  v59 = *(struct IMemObj **)(v29 + 1000);
  v30 = (struct CFormattedParams *)operator new(
                                     0x1248u,
                                     v59,
                                     1,
                                     "Sql\\Ntdbms\\xdb\\common\\hosterrorreport.cpp",
                                     271,
                                     6u);
  v31 = v30;
  v60 = v30;
  if ( v30 )
  {
    *((_QWORD *)v30 + 525) = v30;
    *((_DWORD *)v30 + 1052) = 0;
    *((_QWORD *)v30 + 577) = 0;
    *((_QWORD *)v30 + 578) = 0;
    *((_QWORD *)v30 + 579) = 0;
    *((_QWORD *)v30 + 580) = 0;
    *((_QWORD *)v30 + 581) = 0;
    *((_QWORD *)v30 + 582) = 0;
    *((_QWORD *)v30 + 583) = 0;
    *((_WORD *)v30 + 2336) = 0;
  }
  else
  {
    v31 = 0;
  }
  if ( v31 )
    operator delete(0, 0x1248u);
  v57 = v31;
  if ( v23 && v25 && v31 )
  {
    v32 = *(_DWORD *)a2;
    if ( *((_DWORD *)a2 + 4) != 1 )
      v32 = (unsigned __int16)*(_DWORD *)a2;
    if ( v32 < 0xC350 )
    {
      v33 = (unsigned __int16)v32;
      v34 = 0;
      v35 = 15681;
      while ( v34 <= v35 )
      {
        v36 = (v35 + v34) / 2;
        v37 = v36;
        v38 = (unsigned __int16)word_1004EE890[3 * v36];
        if ( v33 >= v38 )
        {
          if ( v33 <= v38 )
          {
            v39 = (char *)v23;
            v40 = 3 * v37;
            v41 = byte_1004EE892[6 * v37] & 0x1F;
            v42 = 0;
            v43 = 0;
            v44 = &byte_1004EE893[2 * v40];
            if ( *v44 )
            {
              v45 = (unsigned __int8 *)qword_1004903F0 + (unsigned __int16)word_1004EE894[v40];
              do
              {
                if ( v42 < 2048 )
                {
                  v46 = (char *)off_100490C80[*v45] - v39;
                  do
                  {
                    v47 = *(_WORD *)&v39[v46];
                    if ( !v47 )
                      break;
                    *(_WORD *)v39 = v47;
                    ++v42;
                    v39 += 2;
                  }
                  while ( v42 < 2048 );
                }
                ++v43;
                ++v45;
              }
              while ( v43 < (unsigned __int8)*v44 );
              v13 = 1;
            }
            *((_DWORD *)a2 + 2) = v41;
            if ( *((_DWORD *)a2 + 1) == -1 )
              *((_DWORD *)a2 + 1) = v41;
            if ( (unsigned int)FFormatParams(v23, v42, 0, 0, 0, 0, 1, 1, 1, 0, v31, 0, a11) )
            {
              if ( *((_DWORD *)a2 + 4) == 1 )
              {
                v48 = *((_DWORD *)a2 + 2);
                v49 = v48 == 0;
                if ( v48 < 0 )
                {
                  v48 = *((_DWORD *)a2 + 1);
                  v49 = v48 == 0;
                }
                if ( v49 )
                {
                  v50 = 1073758884;
                }
                else
                {
                  v50 = -1073724761;
                  if ( v48 <= 10 )
                    v50 = 1073758885;
                }
              }
              else
              {
                v50 = *(_DWORD *)a2;
                if ( (*(_DWORD *)a2 & 0xFFFF0000) == 0 )
                {
                  v51 = *((_DWORD *)a2 + 2);
                  if ( v51 < 11 )
                  {
                    if ( v51 > 0 )
                      v50 |= 0x40000000u;
                  }
                  else
                  {
                    v50 |= 0xC0000000;
                  }
                }
              }
              v54 = v50;
              v14 = CwchCallFormatMessage(2048, 0, &v54, 1033, v25, 2048, 0, 0, v31, 1);
              if ( v14 > 0 )
              {
                v13 = 0;
                if ( !v24 )
                {
                  _mm_lfence();
                  v52 = v55;
                  SOSLogToErrorLog(L"%s", v55);
                  goto LABEL_71;
                }
              }
            }
            break;
          }
          v34 = v36 + 1;
        }
        else
        {
          v35 = v36 - 1;
        }
      }
    }
  }
  v52 = v55;
LABEL_71:
  operator delete(v31, 0x1248u);
  operator delete[](v52);
  operator delete[](v23);
  if ( v13 )
  {
LABEL_72:
    LODWORD(v53) = *((_DWORD *)a2 + 3);
    SOSLogToErrorLog(
      L"[CwchFormatAndPrint] SQLError: Major: %d, Minor: %d, Severity: %d, State: %d",
      (unsigned int)(*(_DWORD *)a2 / 100),
      (unsigned int)(*(_DWORD *)a2 % 100),
      *((unsigned int *)a2 + 1),
      v53);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x100417db0  mov     rax, rsp
0x100417db3  push    rdi
0x100417db4  push    r12
0x100417db6  push    r13
0x100417db8  push    r14
0x100417dba  push    r15
0x100417dbc  sub     rsp, 0B0h
0x100417dc3  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x100417dcb  mov     [rax+8], rbx
0x100417dcf  mov     [rax+10h], rbp
0x100417dd3  mov     [rax+18h], rsi
0x100417dd7  mov     r12d, r9d
0x100417dda  mov     r14, rdx
0x100417ddd  mov     r13b, 1
0x100417de0  xor     esi, esi
0x100417de2  mov     r10, gs:58h
0x100417deb  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100417df2  mov     ecx, [rax]
0x100417df4  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100417dfb  mov     r8d, [rax]
0x100417dfe  add     r8, [r10+rcx*8]
0x100417e02  cmp     [r8+100h], rsi
0x100417e09  jnz     short loc_100417E13
0x100417e0b  xor     ecx, ecx
0x100417e0d  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100417e13  mov     rdx, gs:58h
0x100417e1c  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100417e23  mov     ecx, [rax]
0x100417e25  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100417e2c  mov     ebx, [rax]
0x100417e2e  add     rbx, [rdx+rcx*8]
0x100417e32  mov     rax, [rbx+100h]
0x100417e39  test    rax, rax
0x100417e3c  jnz     short loc_100417E4D
0x100417e3e  xor     ecx, ecx
0x100417e40  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100417e46  mov     rax, [rbx+100h]
0x100417e4d  test    byte ptr [rax+268h], 40h
0x100417e54  jz      short loc_100417E5D
0x100417e56  xor     eax, eax
0x100417e58  jmp     loc_10041836E
0x100417e5d  cmp     dword ptr [r14+10h], 1
0x100417e62  jz      loc_100418339
0x100417e68  mov     [rsp+0D8h+var_58], rsi
0x100417e70  mov     [rsp+0D8h+var_60], rsi
0x100417e75  mov     [rsp+0D8h+var_50], rsi
0x100417e7d  mov     edi, [r14+4]
0x100417e81  mov     rdx, gs:58h
0x100417e8a  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100417e91  mov     ecx, [rax]
0x100417e93  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100417e9a  mov     ebx, [rax]
0x100417e9c  add     rbx, [rdx+rcx*8]
0x100417ea0  mov     r10, [rbx+100h]
0x100417ea7  test    r10, r10
0x100417eaa  jnz     short loc_100417EBB
0x100417eac  xor     ecx, ecx
0x100417eae  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100417eb4  mov     r10, [rbx+100h]
0x100417ebb  mov     ecx, 825h
0x100417ec0  mov     eax, 104Ah
0x100417ec5  cmp     edi, 0Ah
0x100417ec8  cmovg   ecx, eax
0x100417ecb  mov     eax, 2
0x100417ed0  mul     rcx
0x100417ed3  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x100417eda  cmovo   rax, rcx
0x100417ede  mov     byte ptr [rsp+0D8h+var_B0], 6
0x100417ee3  mov     dword ptr [rsp+0D8h+var_B8], 104h
0x100417eeb  lea     r9, aSqlNtdbmsXdbCo; "Sql\\Ntdbms\\xdb\\common\\hosterrorrepo"...
0x100417ef2  lea     r8d, [rcx+2]
0x100417ef6  mov     rdx, [r10+3E8h]
0x100417efd  mov     rcx, rax
0x100417f00  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x100417f06  mov     r15, rax
0x100417f09  test    rax, rax
0x100417f0c  jz      short loc_100417F16
0x100417f0e  xor     ecx, ecx
0x100417f10  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100417f16  mov     [rsp+0D8h+var_58], r15
0x100417f1e  and     r12d, 10h
0x100417f22  jz      short loc_100417F59
0x100417f24  mov     rbp, [rsp+0D8h+arg_30]
0x100417f2c  test    rbp, rbp
0x100417f2f  jnz     loc_100417FD4
0x100417f35  mov     [rsp+0D8h+var_B8], rsi
0x100417f3a  mov     r9d, 107h
0x100417f40  lea     r8, aErrorreportuti; "ErrorReportUtils.cpp"
0x100417f47  lea     rdx, aNullPwchoutmsg; "NULL != pwchOutMsg"
0x100417f4e  lea     ecx, [rbp+1]
0x100417f51  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x100417f57  jmp     short loc_100417FD4
0x100417f59  mov     rdx, gs:58h
0x100417f62  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100417f69  mov     ecx, [rax]
0x100417f6b  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100417f72  mov     ebx, [rax]
0x100417f74  add     rbx, [rdx+rcx*8]
0x100417f78  mov     rdx, [rbx+100h]
0x100417f7f  test    rdx, rdx
0x100417f82  jnz     short loc_100417F93
0x100417f84  xor     ecx, ecx
0x100417f86  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100417f8c  mov     rdx, [rbx+100h]
0x100417f93  mov     byte ptr [rsp+0D8h+var_B0], 6
0x100417f98  mov     dword ptr [rsp+0D8h+var_B8], 10Ch
0x100417fa0  lea     r9, aSqlNtdbmsXdbCo; "Sql\\Ntdbms\\xdb\\common\\hosterrorrepo"...
0x100417fa7  mov     r8d, 1
0x100417fad  mov     rdx, [rdx+3E8h]
0x100417fb4  mov     ecx, 1000h
0x100417fb9  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x100417fbf  mov     rbp, rax
0x100417fc2  test    rax, rax
0x100417fc5  jz      short loc_100417FCF
0x100417fc7  xor     ecx, ecx
0x100417fc9  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100417fcf  mov     [rsp+0D8h+var_60], rbp
0x100417fd4  mov     [rsp+0D8h+var_68], 10Fh
0x100417fdc  mov     rdx, gs:58h
0x100417fe5  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100417fec  mov     ecx, [rax]
0x100417fee  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100417ff5  mov     ebx, [rax]
0x100417ff7  add     rbx, [rdx+rcx*8]
0x100417ffb  mov     rdx, [rbx+100h]
0x100418002  test    rdx, rdx
0x100418005  jnz     short loc_100418016
0x100418007  xor     ecx, ecx
0x100418009  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10041800f  mov     rdx, [rbx+100h]
0x100418016  mov     rdx, [rdx+3E8h]
0x10041801d  mov     [rsp+0D8h+var_40], rdx
0x100418025  mov     byte ptr [rsp+0D8h+var_B0], 6
0x10041802a  mov     dword ptr [rsp+0D8h+var_B8], 10Fh
0x100418032  lea     r9, aSqlNtdbmsXdbCo; "Sql\\Ntdbms\\xdb\\common\\hosterrorrepo"...
0x100418039  mov     ecx, 1248h
0x10041803e  mov     r8d, 1
0x100418044  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10041804a  mov     rdi, rax
0x10041804d  mov     [rsp+0D8h+var_38], rax
0x100418055  test    rax, rax
0x100418058  jz      short loc_1004180BB
0x10041805a  mov     [rax+1068h], rax
0x100418061  mov     [rax+1070h], esi
0x100418067  mov     [rax+1208h], rsi
0x10041806e  mov     qword ptr [rax+1210h], 0
0x100418079  mov     qword ptr [rax+1218h], 0
0x100418084  mov     qword ptr [rax+1220h], 0
0x10041808f  mov     qword ptr [rax+1228h], 0
0x10041809a  mov     qword ptr [rax+1230h], 0
0x1004180a5  mov     qword ptr [rax+1238h], 0
0x1004180b0  mov     word ptr [rax+1240h], 0
0x1004180b9  jmp     short loc_1004180BE
0x1004180bb  mov     rdi, rsi
0x1004180be  test    rdi, rdi
0x1004180c1  jz      short loc_1004180D0
0x1004180c3  mov     edx, 1248h
0x1004180c8  xor     ecx, ecx
0x1004180ca  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1004180d0  mov     [rsp+0D8h+var_50], rdi
0x1004180d8  test    r15, r15
0x1004180db  jz      loc_10041830D
0x1004180e1  test    rbp, rbp
0x1004180e4  jz      loc_10041830D
0x1004180ea  test    rdi, rdi
0x1004180ed  jz      loc_10041830D
0x1004180f3  mov     ecx, [r14]
0x1004180f6  movzx   eax, cx
0x1004180f9  cmp     dword ptr [r14+10h], 1
0x1004180fe  cmovnz  ecx, eax
0x100418101  cmp     ecx, 0C350h
0x100418107  jnb     loc_10041830D
0x10041810d  movzx   r11d, cx
0x100418111  mov     r8d, esi
0x100418114  mov     r9d, 3D41h
0x10041811a  lea     rbx, cs:100400000h
0x100418121  cmp     r8d, r9d
0x100418124  jg      loc_10041830D
0x10041812a  lea     eax, [r9+r8]
0x10041812e  cdq
0x10041812f  sub     eax, edx
0x100418131  sar     eax, 1
0x100418133  movsxd  rcx, eax
0x100418136  mov     r10, rcx
0x100418139  lea     rax, [rcx+rcx*2]
0x10041813d  movzx   edx, rva word_1004EE890[rbx+rax*2]
0x100418145  cmp     r11d, edx
0x100418148  jnb     short loc_100418150
0x10041814a  lea     r9d, [rcx-1]
0x10041814e  jmp     short loc_100418121
0x100418150  jbe     short loc_100418158
0x100418152  lea     r8d, [rcx+1]
0x100418156  jmp     short loc_100418121
0x100418158  mov     rcx, r15
0x10041815b  lea     rax, [r10+r10*2]
0x10041815f  movzx   ebx, rva byte_1004EE892[rbx+rax*2]
0x100418167  and     bl, 1Fh
0x10041816a  mov     edx, esi
0x10041816c  mov     r10d, esi
0x10041816f  lea     r8, cs:100400000h
0x100418176  lea     r11, rva byte_1004EE893[r8]
0x10041817d  lea     r11, [r11+rax*2]
0x100418181  cmp     [r11], sil
0x100418184  jbe     short loc_1004181ED
0x100418186  lea     r13, cs:100400000h
0x10041818d  movzx   r9d, rva word_1004EE894[r13+rax*2]
0x100418196  lea     rax, qword_1004903F0
0x10041819d  add     r9, rax
0x1004181a0  cmp     edx, 800h
0x1004181a6  jge     short loc_1004181DB
0x1004181a8  movzx   eax, byte ptr [r9]
0x1004181ac  mov     r8, ds:rva off_100490C80[r13+rax*8]; "%I64X" ...
0x1004181b4  sub     r8, rcx
0x1004181b7  nop     word ptr [rax+rax+00000000h]
0x1004181c0  movzx   eax, word ptr [r8+rcx]
0x1004181c5  test    ax, ax
0x1004181c8  jz      short loc_1004181DB
0x1004181ca  mov     [rcx], ax
0x1004181cd  inc     edx; int
0x1004181cf  add     rcx, 2
0x1004181d3  cmp     edx, 800h
0x1004181d9  jl      short loc_1004181C0
0x1004181db  inc     r10d
0x1004181de  inc     r9
0x1004181e1  movzx   eax, byte ptr [r11]
0x1004181e5  cmp     r10d, eax
0x1004181e8  jl      short loc_1004181A0
0x1004181ea  mov     r13b, 1
0x1004181ed  movzx   eax, bl
0x1004181f0  mov     [r14+8], eax
0x1004181f4  cmp     dword ptr [r14+4], 0FFFFFFFFh
0x1004181f9  jnz     short loc_1004181FF
0x1004181fb  mov     [r14+4], eax
0x1004181ff  mov     rax, [rsp+0D8h+arg_50]
0x100418207  mov     [rsp+0D8h+var_78], rax; char *
0x10041820c  mov     [rsp+0D8h+var_80], rsi; enum EFormatType *
0x100418211  mov     [rsp+0D8h+var_88], rdi; struct CFormattedParams *
0x100418216  mov     [rsp+0D8h+var_90], esi; int
0x10041821a  mov     [rsp+0D8h+var_98], 1; int
0x100418222  mov     [rsp+0D8h+var_A0], 1; int
0x10041822a  mov     [rsp+0D8h+var_A8], 1; int
0x100418232  mov     [rsp+0D8h+var_B0], esi; int
0x100418236  mov     [rsp+0D8h+var_B8], rsi; wchar_t *
0x10041823b  xor     r9d, r9d; int
0x10041823e  xor     r8d, r8d; wchar_t *
0x100418241  mov     rcx, r15; wchar_t *
0x100418244  call    ?FFormatParams@@YAHPEB_WHPEA_WH1HHHHHPEAVCFormattedParams@@PEBW4EFormatType@@PEAD@Z; FFormatParams(wchar_t const *,int,wchar_t *,int,wchar_t *,int,int,int,int,int,CFormattedParams *,EFormatType const *,char *)
0x100418249  test    eax, eax
0x10041824b  jz      loc_10041830D
0x100418251  cmp     dword ptr [r14+10h], 1
0x100418256  jnz     short loc_100418281
0x100418258  mov     eax, [r14+8]
0x10041825c  test    eax, eax
0x10041825e  jns     short loc_100418266
0x100418260  mov     eax, [r14+4]
0x100418264  test    eax, eax
0x100418266  jnz     short loc_10041826F
0x100418268  mov     ecx, 400042A4h
0x10041826d  jmp     short loc_1004182A8
0x10041826f  mov     ecx, 0C00042A7h
0x100418274  mov     edx, 400042A5h
0x100418279  cmp     eax, 0Ah
0x10041827c  cmovle  ecx, edx
0x10041827f  jmp     short loc_1004182A8
0x100418281  mov     ecx, [r14]
0x100418284  test    ecx, 0FFFF0000h
0x10041828a  jnz     short loc_1004182A8
0x10041828c  mov     edx, [r14+8]
0x100418290  cmp     edx, 0Bh
0x100418293  jl      short loc_10041829D
0x100418295  or      ecx, 0C0000000h
0x10041829b  jmp     short loc_1004182A8
0x10041829d  mov     eax, ecx
0x10041829f  bts     eax, 1Eh
0x1004182a3  test    edx, edx
0x1004182a5  cmovg   ecx, eax
0x1004182a8  mov     [rsp+0D8h+var_68], ecx
0x1004182ac  mov     r9d, 409h
0x1004182b2  mov     [rsp+0D8h+var_90], 1
0x1004182ba  mov     qword ptr [rsp+0D8h+var_98], rdi
0x1004182bf  mov     [rsp+0D8h+var_A0], esi
0x1004182c3  mov     qword ptr [rsp+0D8h+var_A8], rsi
0x1004182c8  mov     [rsp+0D8h+var_B0], 800h
0x1004182d0  mov     [rsp+0D8h+var_B8], rbp
0x1004182d5  lea     r8, [rsp+0D8h+var_68]
0x1004182da  xor     edx, edx
0x1004182dc  mov     ecx, 800h
0x1004182e1  call    ?CwchCallFormatMessage@@YAHKPEAXPEBVCErrorEventId@@FPEA_WH2HPEAVCFormattedParams@@W4EFormatMethod@@@Z; CwchCallFormatMessage(ulong,void *,CErrorEventId const *,short,wchar_t *,int,wchar_t *,int,CFormattedParams *,EFormatMethod)
0x1004182e6  mov     esi, eax
0x1004182e8  test    eax, eax
0x1004182ea  jle     short loc_10041830D
0x1004182ec  xor     r13b, r13b
0x1004182ef  test    r12d, r12d
0x1004182f2  jnz     short loc_10041830D
0x1004182f4  lfence
0x1004182f7  mov     rbx, [rsp+0D8h+var_60]
0x1004182fc  mov     rdx, rbx
0x1004182ff  lea     rcx, aS_1; "%s"
0x100418306  call    ?SOSLogToErrorLog@@YAXPEB_WZZ; SOSLogToErrorLog(wchar_t const *,...)
0x10041830b  jmp     short loc_100418312
  ... truncated ...
```
