# CTpLogger::StartSession(wchar_t const *)

- ea: `0x180046730`
- end: `0x180046a4e`
- name: `?StartSession@CTpLogger@@QEAAJPEB_W@Z`
- size: `798`
- prototype: `__int64 __fastcall(CTpLogger *__hidden this, const wchar_t *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180024840`
- `0x1800863ec`

## callees

- `0x180018090`
- `0x180039344`
- `0x18003bb8c`
- `0x180046730`
- `0x180053300`
- `0x1800538d0`
- `0x1800a4f48`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wfopen` at `0x1800468e0`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen` at `0x18004694a`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen` at `0x1800469cf`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen` at `0x180046a05`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen` at `0x1800468e0`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen` at `0x18004694a`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen` at `0x1800469cf`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen` at `0x180046a05`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x1800467ac`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x1800467c5`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x1800467de`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x1800468f9`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x180046963`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x1800469e8`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x180046a1e`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x1800467ac`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x1800467c5`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x1800467de`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x1800468f9`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x180046963`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x1800469e8`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x180046a1e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18004688f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800468c5`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18004692b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800469b0`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18004688f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800468c5`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18004692b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800469b0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004677f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004677f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CTpLogger::StartSession(CTpLogger *this, const wchar_t *a2)
{
  unsigned int v5; // r8d
  int LoggingDirectory; // ebx
  FILE *v7; // rcx
  FILE *v8; // rcx
  FILE *v9; // rcx
  __int64 v10; // r14
  __int64 v11; // rsi
  __int64 v12; // rdx
  __int64 v13; // rbx
  unsigned __int64 v14; // rcx
  FILE *v15; // rax
  FILE *v16; // rcx
  FILE *v17; // rax
  FILE *v18; // rcx
  __int64 v19; // rdx
  FILE *v20; // rax
  FILE *v21; // rcx
  FILE *v22; // rax
  FILE *v23; // rcx
  char *v24; // [rsp+20h] [rbp-E0h] BYREF
  char v25; // [rsp+28h] [rbp-D8h]
  wchar_t v26[40]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t FileName[264]; // [rsp+80h] [rbp-80h] BYREF

  if ( !*((_DWORD *)this + 31) )
    return 1;
  v24 = (char *)this + 8;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v25 = 1;
  if ( *((_QWORD *)this + 12) )
  {
    LoggingDirectory = -2147023649;
LABEL_5:
    v7 = (FILE *)*((_QWORD *)this + 11);
    *((_QWORD *)this + 11) = 0;
    if ( v7 )
      fclose(v7);
    v8 = (FILE *)*((_QWORD *)this + 13);
    *((_QWORD *)this + 13) = 0;
    if ( v8 )
      fclose(v8);
    v9 = (FILE *)*((_QWORD *)this + 12);
    *((_QWORD *)this + 12) = 0;
    if ( v9 )
      fclose(v9);
    goto LABEL_11;
  }
  LoggingDirectory = CTpLogger::CreateLoggingDirectory(this, FileName, v5);
  if ( LoggingDirectory < 0 )
    goto LABEL_5;
  v10 = -1;
  v11 = -1;
  do
    ++v11;
  while ( FileName[v11] );
  if ( *((_DWORD *)this + 30) )
  {
    LoggingDirectory = UtilUuidCreateAsString(v26);
    if ( LoggingDirectory < 0 )
      goto LABEL_5;
    v13 = (unsigned int)v11;
    v14 = 2LL * (unsigned int)v11;
    if ( v14 >= 0x208 )
      goto LABEL_31;
    FileName[(unsigned int)v11] = 0;
    if ( (unsigned int)_o_wcscat_s(FileName, 260, v26) )
      goto LABEL_19;
    do
      ++v10;
    while ( FileName[v10] );
    if ( (unsigned int)_o_wcscat_s(FileName, 260, L".log") )
      goto LABEL_19;
    v15 = _wfopen(FileName, L"wt, ccs=UTF-8");
    v16 = (FILE *)*((_QWORD *)this + 12);
    *((_QWORD *)this + 12) = v15;
    if ( v16 )
      fclose(v16);
    if ( !*((_QWORD *)this + 12) )
      goto LABEL_19;
    v14 = 2LL * (unsigned int)v10;
    if ( v14 >= 0x208 )
LABEL_31:
      _report_rangecheckfailure(v14, v12);
    FileName[(unsigned int)v10] = 0;
    if ( (unsigned int)_o_wcscat_s(FileName, 260, L".raw") )
      goto LABEL_19;
    v17 = _wfopen(FileName, L"wb");
    v18 = (FILE *)*((_QWORD *)this + 13);
    *((_QWORD *)this + 13) = v17;
    if ( v18 )
      fclose(v18);
    if ( !*((_QWORD *)this + 13) )
    {
LABEL_19:
      LoggingDirectory = -2147467259;
      goto LABEL_5;
    }
  }
  else
  {
    v13 = (unsigned int)v11;
  }
  CTpLogger::RotateLogs(this);
  if ( (unsigned __int64)(2 * v13) >= 0x208 )
    _report_rangecheckfailure(2 * v13, v19);
  FileName[v13] = 0;
  if ( (unsigned int)_o_wcscat_s(FileName, 260, L"tpclient.al3") )
    goto LABEL_19;
  v20 = _wfopen(FileName, L"r+b");
  v21 = (FILE *)*((_QWORD *)this + 11);
  *((_QWORD *)this + 11) = v20;
  if ( v21 )
    fclose(v21);
  if ( !*((_QWORD *)this + 11) )
  {
    v22 = _wfopen(FileName, L"w+b");
    v23 = (FILE *)*((_QWORD *)this + 11);
    *((_QWORD *)this + 11) = v22;
    if ( v23 )
      fclose(v23);
    if ( !*((_QWORD *)this + 11) )
      goto LABEL_19;
  }
  *((_QWORD *)this + 10) = a2;
  *((_QWORD *)this + 14) = 1;
  LoggingDirectory = 0;
LABEL_11:
  utl::unique_lock<utl::recursive_mutex>::~unique_lock<utl::recursive_mutex>(&v24);
  return (unsigned int)LoggingDirectory;
}

```

## disassembly

```asm
0x180046730  push    rbp
0x180046732  push    rbx
0x180046733  push    rsi
0x180046734  push    rdi
0x180046735  push    r12
0x180046737  push    r13
0x180046739  push    r14
0x18004673b  push    r15
0x18004673d  lea     rbp, [rsp-1A8h]
0x180046745  sub     rsp, 2A8h
0x18004674c  mov     rax, cs:__security_cookie
0x180046753  xor     rax, rsp
0x180046756  mov     [rbp+1E0h+var_50], rax
0x18004675d  mov     r15, rdx
0x180046760  mov     rdi, rcx
0x180046763  xor     r12d, r12d
0x180046766  cmp     [rcx+7Ch], r12d
0x18004676a  jnz     short loc_180046776
0x18004676c  lea     eax, [r12+1]
0x180046771  jmp     loc_1800467F7
0x180046776  add     rcx, 8; lpCriticalSection
0x18004677a  mov     [rsp+2E0h+var_2C0], rcx
0x18004677f  call    cs:__imp_EnterCriticalSection
0x180046786  nop     dword ptr [rax+rax+00h]
0x18004678b  mov     [rsp+2E0h+var_2B8], 1
0x180046790  cmp     [rdi+60h], r12
0x180046794  jz      loc_18004681B
0x18004679a  mov     ebx, 800704DFh
0x18004679f  mov     rcx, [rdi+58h]; Stream
0x1800467a3  mov     [rdi+58h], r12
0x1800467a7  test    rcx, rcx
0x1800467aa  jz      short loc_1800467B8
0x1800467ac  call    cs:__imp_fclose
0x1800467b3  nop     dword ptr [rax+rax+00h]
0x1800467b8  mov     rcx, [rdi+68h]; Stream
0x1800467bc  mov     [rdi+68h], r12
0x1800467c0  test    rcx, rcx
0x1800467c3  jz      short loc_1800467D1
0x1800467c5  call    cs:__imp_fclose
0x1800467cc  nop     dword ptr [rax+rax+00h]
0x1800467d1  mov     rcx, [rdi+60h]; Stream
0x1800467d5  mov     [rdi+60h], r12
0x1800467d9  test    rcx, rcx
0x1800467dc  jz      short loc_1800467EB
0x1800467de  call    cs:__imp_fclose
0x1800467e5  nop     dword ptr [rax+rax+00h]
0x1800467ea  nop
0x1800467eb  lea     rcx, [rsp+2E0h+var_2C0]
0x1800467f0  call    ??1?$unique_lock@Vrecursive_mutex@utl@@@utl@@QEAA@XZ; utl::unique_lock<utl::recursive_mutex>::~unique_lock<utl::recursive_mutex>(void)
0x1800467f5  mov     eax, ebx
0x1800467f7  mov     rcx, [rbp+1E0h+var_50]
0x1800467fe  xor     rcx, rsp; StackCookie
0x180046801  call    __security_check_cookie
0x180046806  add     rsp, 2A8h
0x18004680d  pop     r15
0x18004680f  pop     r14
0x180046811  pop     r13
0x180046813  pop     r12
0x180046815  pop     rdi
0x180046816  pop     rsi
0x180046817  pop     rbx
0x180046818  pop     rbp
0x180046819  retn
0x18004681b  lea     rdx, [rbp+1E0h+FileName]; wchar_t *
0x18004681f  mov     rcx, rdi; this
0x180046822  call    ?CreateLoggingDirectory@CTpLogger@@AEAAJPEA_WK@Z; CTpLogger::CreateLoggingDirectory(wchar_t *,ulong)
0x180046827  mov     ebx, eax
0x180046829  test    eax, eax
0x18004682b  js      loc_18004679F
0x180046831  lea     rax, [rbp+1E0h+FileName]
0x180046835  or      r14, 0FFFFFFFFFFFFFFFFh
0x180046839  mov     rsi, r14
0x18004683c  inc     rsi
0x18004683f  cmp     [rax+rsi*2], r12w
0x180046844  jnz     short loc_18004683C
0x180046846  mov     r13d, 208h
0x18004684c  cmp     [rdi+78h], r12d
0x180046850  jbe     loc_180046980
0x180046856  lea     rcx, [rsp+2E0h+var_2B0]; wchar_t *
0x18004685b  call    ?UtilUuidCreateAsString@@YAJPEA_W@Z; UtilUuidCreateAsString(wchar_t *)
0x180046860  mov     ebx, eax
0x180046862  test    eax, eax
0x180046864  js      loc_18004679F
0x18004686a  mov     ebx, esi
0x18004686c  lea     rcx, [rbx+rbx]
0x180046870  cmp     rcx, r13
0x180046873  jnb     loc_18004697A
0x180046879  mov     [rbp+rcx+1E0h+FileName], r12w
0x18004687f  lea     r8, [rsp+2E0h+var_2B0]
0x180046884  mov     esi, 104h
0x180046889  mov     edx, esi
0x18004688b  lea     rcx, [rbp+1E0h+FileName]
0x18004688f  call    cs:__imp__o_wcscat_s
0x180046896  nop     dword ptr [rax+rax+00h]
0x18004689b  test    eax, eax
0x18004689d  jz      short loc_1800468A9
0x18004689f  mov     ebx, 80004005h
0x1800468a4  jmp     loc_18004679F
0x1800468a9  lea     rax, [rbp+1E0h+FileName]
0x1800468ad  inc     r14
0x1800468b0  cmp     [rax+r14*2], r12w
0x1800468b5  jnz     short loc_1800468AD
0x1800468b7  lea     r8, aLog; ".log"
0x1800468be  mov     rdx, rsi
0x1800468c1  lea     rcx, [rbp+1E0h+FileName]
0x1800468c5  call    cs:__imp__o_wcscat_s
0x1800468cc  nop     dword ptr [rax+rax+00h]
0x1800468d1  test    eax, eax
0x1800468d3  jnz     short loc_18004689F
0x1800468d5  lea     rdx, aWtCcsUtf8; "wt, ccs=UTF-8"
0x1800468dc  lea     rcx, [rbp+1E0h+FileName]; FileName
0x1800468e0  call    cs:__imp__wfopen
0x1800468e7  nop     dword ptr [rax+rax+00h]
0x1800468ec  mov     rcx, [rdi+60h]; Stream
0x1800468f0  mov     [rdi+60h], rax
0x1800468f4  test    rcx, rcx
0x1800468f7  jz      short loc_180046905
0x1800468f9  call    cs:__imp_fclose
0x180046900  nop     dword ptr [rax+rax+00h]
0x180046905  cmp     [rdi+60h], r12
0x180046909  jz      short loc_18004689F
0x18004690b  mov     eax, r14d
0x18004690e  lea     rcx, [rax+rax]
0x180046912  cmp     rcx, r13
0x180046915  jnb     short loc_18004697A
0x180046917  mov     [rbp+rcx+1E0h+FileName], r12w
0x18004691d  lea     r8, aRaw_0; ".raw"
0x180046924  mov     rdx, rsi
0x180046927  lea     rcx, [rbp+1E0h+FileName]
0x18004692b  call    cs:__imp__o_wcscat_s
0x180046932  nop     dword ptr [rax+rax+00h]
0x180046937  test    eax, eax
0x180046939  jnz     loc_18004689F
0x18004693f  lea     rdx, aWb; "wb"
0x180046946  lea     rcx, [rbp+1E0h+FileName]; FileName
0x18004694a  call    cs:__imp__wfopen
0x180046951  nop     dword ptr [rax+rax+00h]
0x180046956  mov     rcx, [rdi+68h]; Stream
0x18004695a  mov     [rdi+68h], rax
0x18004695e  test    rcx, rcx
0x180046961  jz      short loc_18004696F
0x180046963  call    cs:__imp_fclose
0x18004696a  nop     dword ptr [rax+rax+00h]
0x18004696f  cmp     [rdi+68h], r12
0x180046973  jnz     short loc_180046987
0x180046975  jmp     loc_18004689F
0x18004697a  call    __report_rangecheckfailure
0x180046980  mov     ebx, esi
0x180046982  mov     esi, 104h
0x180046987  mov     rcx, rdi; this
0x18004698a  call    ?RotateLogs@CTpLogger@@AEAAJXZ; CTpLogger::RotateLogs(void)
0x18004698f  lea     rcx, [rbx+rbx]
0x180046993  cmp     rcx, r13
0x180046996  jnb     loc_180046A48
0x18004699c  mov     [rbp+rcx+1E0h+FileName], r12w
0x1800469a2  lea     r8, aTpclientAl3; "tpclient.al3"
0x1800469a9  mov     rdx, rsi
0x1800469ac  lea     rcx, [rbp+1E0h+FileName]
0x1800469b0  call    cs:__imp__o_wcscat_s
0x1800469b7  nop     dword ptr [rax+rax+00h]
0x1800469bc  test    eax, eax
0x1800469be  jnz     loc_18004689F
0x1800469c4  lea     rdx, aRB; "r+b"
0x1800469cb  lea     rcx, [rbp+1E0h+FileName]; FileName
0x1800469cf  call    cs:__imp__wfopen
0x1800469d6  nop     dword ptr [rax+rax+00h]
0x1800469db  mov     rcx, [rdi+58h]; Stream
0x1800469df  mov     [rdi+58h], rax
0x1800469e3  test    rcx, rcx
0x1800469e6  jz      short loc_1800469F4
0x1800469e8  call    cs:__imp_fclose
0x1800469ef  nop     dword ptr [rax+rax+00h]
0x1800469f4  cmp     [rdi+58h], r12
0x1800469f8  jnz     short loc_180046A34
0x1800469fa  lea     rdx, aWB; "w+b"
0x180046a01  lea     rcx, [rbp+1E0h+FileName]; FileName
0x180046a05  call    cs:__imp__wfopen
0x180046a0c  nop     dword ptr [rax+rax+00h]
0x180046a11  mov     rcx, [rdi+58h]; Stream
0x180046a15  mov     [rdi+58h], rax
0x180046a19  test    rcx, rcx
0x180046a1c  jz      short loc_180046A2A
0x180046a1e  call    cs:__imp_fclose
0x180046a25  nop     dword ptr [rax+rax+00h]
0x180046a2a  cmp     [rdi+58h], r12
0x180046a2e  jz      loc_18004689F
0x180046a34  mov     [rdi+50h], r15
0x180046a38  mov     qword ptr [rdi+70h], 1
0x180046a40  mov     ebx, r12d
0x180046a43  jmp     loc_1800467EB
0x180046a48  call    __report_rangecheckfailure
```
