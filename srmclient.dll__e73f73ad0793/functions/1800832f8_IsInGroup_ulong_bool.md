# IsInGroup(ulong,bool)

- ea: `0x1800832f8`
- end: `0x180083638`
- name: `?IsInGroup@@YA_NK_N@Z`
- size: `832`
- prototype: `bool __fastcall(unsigned int, bool)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180068e3c`
- `0x1800690b0`

## callees

- `0x1800020ba`
- `0x18006fe68`
- `0x18006febc`
- `0x1800700b8`
- `0x18007424c`
- `0x180075034`
- `0x180082f80`
- `0x1800832f8`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18008344a`
- `KERNEL32!CloseHandle` at `0x180083498`
- `KERNEL32!CloseHandle` at `0x1800834b2`
- `KERNEL32!CloseHandle` at `0x18008344a`
- `KERNEL32!CloseHandle` at `0x180083498`
- `KERNEL32!CloseHandle` at `0x1800834b2`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18008347b`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18008347b`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800834d9`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800834d9`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180083411`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180083411`

## string_xrefs

- `0x18008332e`: `base\fs\fsrm\utilities\security\srmsec.cpp`
- `0x180083604`: `CheckTokenMembership`
- `0x1800835b4`: `AllocateAndInitializeSid`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
bool __fastcall IsInGroup(__int64 a1, unsigned __int8 a2)
{
  int v2; // edi
  __int64 v3; // rdx
  HANDLE v4; // rcx
  const wchar_t *v5; // rax
  bool v6; // bl
  __int64 v8; // rax
  __int64 v9; // rax
  WINBOOL IsMember; // [rsp+60h] [rbp-278h] BYREF
  void **v11; // [rsp+68h] [rbp-270h]
  HANDLE hObject; // [rsp+70h] [rbp-268h] BYREF
  _BYTE *v13; // [rsp+78h] [rbp-260h]
  PSID SidToCheck; // [rsp+80h] [rbp-258h] BYREF
  int pExceptionObject; // [rsp+88h] [rbp-250h] BYREF
  int v16; // [rsp+8Ch] [rbp-24Ch] BYREF
  int v17; // [rsp+90h] [rbp-248h] BYREF
  _com_error *v18; // [rsp+98h] [rbp-240h] BYREF
  const exception *v19; // [rsp+A0h] [rbp-238h] BYREF
  _com_error *v20; // [rsp+A8h] [rbp-230h] BYREF
  const exception *v21; // [rsp+B0h] [rbp-228h] BYREF
  _QWORD v22[3]; // [rsp+B8h] [rbp-220h] BYREF
  int v23; // [rsp+D0h] [rbp-208h]
  int v24; // [rsp+D4h] [rbp-204h]
  int v25; // [rsp+D8h] [rbp-200h]
  _DWORD v26[26]; // [rsp+E0h] [rbp-1F8h] BYREF
  _BYTE v27[144]; // [rsp+148h] [rbp-190h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+1D8h] [rbp-100h] BYREF
  void **v29; // [rsp+1E0h] [rbp-F8h] BYREF
  int v30; // [rsp+1E8h] [rbp-F0h]
  unsigned int v31; // [rsp+20Ch] [rbp-CCh]

  v2 = a2;
  v13 = v22;
  v22[0] = L"base\\fs\\fsrm\\utilities\\security\\srmsec.cpp";
  v22[1] = L"IsInGroup";
  v22[2] = L"SECSECRC";
  v23 = 203;
  v24 = 17;
  v25 = 255;
  v26[24] = 0x1000000;
  memset_0(v26, 0, 0x60u);
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v29, (const struct CSrmDebugInfo *)v22, (__int64)L"IsInGroup");
  IsMember = 0;
  SidToCheck = 0;
  v30 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    v13 = v27;
    v8 = CSrmDebugInfo::CSrmDebugInfo(
           (__int64)v27,
           (__int64)L"base\\fs\\fsrm\\utilities\\security\\srmsec.cpp",
           (__int64)L"SECSECRC",
           (__int64)L"IsInGroup",
           232,
           17);
    CSrmFunctionTracer::TranslateWin32Error(&v29, v8, L"AllocateAndInitializeSid");
  }
  try
  {
    v11 = &CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
    hObject = (HANDLE)-1LL;
    if ( GetCurrentAccessToken(v2, v3, &hObject) )
      v4 = hObject;
    else
      v4 = 0;
    if ( !CheckTokenMembership(v4, SidToCheck, &IsMember) )
    {
      v13 = v27;
      v9 = CSrmDebugInfo::CSrmDebugInfo(
             (__int64)v27,
             (__int64)L"base\\fs\\fsrm\\utilities\\security\\srmsec.cpp",
             (__int64)L"SECSECRC",
             (__int64)L"IsInGroup",
             250,
             17);
      CSrmFunctionTracer::TranslateWin32Error(&v29, v9, L"CheckTokenMembership");
    }
    v11 = &CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
    if ( hObject != (HANDLE)-1LL )
      CloseHandle(hObject);
    v11 = &CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>::`vftable';
    hObject = (HANDLE)-1LL;
  }
  catch ( long v16 )
  {
    CSrmFunctionTracer::HandleHresultException(
      (CSrmFunctionTracer *)&v29,
      v16,
      L"base\\fs\\fsrm\\utilities\\security\\srmsec.cpp",
      L"SECSECRC",
      L"IsInGroup",
      0xFFu,
      v31);
  }
  catch ( _com_error *v18 )
  {
    CSrmFunctionTracer::HandleComException(
      (CSrmFunctionTracer *)&v29,
      v18,
      L"base\\fs\\fsrm\\utilities\\security\\srmsec.cpp",
      L"SECSECRC",
      L"IsInGroup",
      0xFFu,
      v31);
  }
  catch ( std::bad_alloc )
  {
    CSrmFunctionTracer::HandleStdBadAllocException(
      (CSrmFunctionTracer *)&v29,
      L"base\\fs\\fsrm\\utilities\\security\\srmsec.cpp",
      L"SECSECRC",
      L"IsInGroup",
      0xFFu,
      v31);
  }
  catch ( const exception *v19 )
  {
    CSrmFunctionTracer::HandleStdGenericException(
      (CSrmFunctionTracer *)&v29,
      v19,
      L"base\\fs\\fsrm\\utilities\\security\\srmsec.cpp",
      L"SECSECRC",
      L"IsInGroup",
      0xFFu,
      v31);
  }
  LODWORD(v13) = v30;
  try
  {
    if ( SidToCheck )
      FreeSid(SidToCheck);
  }
  catch ( long v17 )
  {
    CSrmFunctionTracer::HandleHresultException(
      (CSrmFunctionTracer *)&v29,
      v17,
      L"base\\fs\\fsrm\\utilities\\security\\srmsec.cpp",
      L"SECSECRC",
      L"IsInGroup",
      0x10Au,
      v31);
  }
  catch ( _com_error *v20 )
  {
    CSrmFunctionTracer::HandleComException(
      (CSrmFunctionTracer *)&v29,
      v20,
      L"base\\fs\\fsrm\\utilities\\security\\srmsec.cpp",
      L"SECSECRC",
      L"IsInGroup",
      0x10Au,
      v31);
  }
  catch ( std::bad_alloc )
  {
    CSrmFunctionTracer::HandleStdBadAllocException(
      (CSrmFunctionTracer *)&v29,
      L"base\\fs\\fsrm\\utilities\\security\\srmsec.cpp",
      L"SECSECRC",
      L"IsInGroup",
      0x10Au,
      v31);
  }
  catch ( const exception *v21 )
  {
    CSrmFunctionTracer::HandleStdGenericException(
      (CSrmFunctionTracer *)&v29,
      v21,
      L"base\\fs\\fsrm\\utilities\\security\\srmsec.cpp",
      L"SECSECRC",
      L"IsInGroup",
      0x10Au,
      v31);
  }
  if ( (int)v13 < 0 )
  {
    pExceptionObject = (int)v13;
    throw (long *)&pExceptionObject;
  }
  v5 = L"TRUE";
  if ( !IsMember )
    v5 = L"FALSE";
  CSrmFunctionTracerBase::TraceInternalWithFormat(
    (CSrmFunctionTracerBase *)&v29,
    L"RETURN",
    0xAAu,
    L"Returning BOOL: %s",
    v5);
  v6 = IsMember != 0;
  v29 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v29);
  return v6;
}

```

## disassembly

```asm
0x1800832f8  mov     r11, rsp
0x1800832fb  push    rbx
0x1800832fc  push    rsi
0x1800832fd  push    rdi
0x1800832fe  push    r12
0x180083300  push    r13
0x180083302  push    r14
0x180083304  push    r15
0x180083306  sub     rsp, 2A0h
0x18008330d  mov     rax, cs:__security_cookie
0x180083314  xor     rax, rsp
0x180083317  mov     [rsp+2D8h+var_48], rax
0x18008331f  movzx   edi, dl
0x180083322  lea     rax, [r11-220h]
0x180083329  mov     [rsp+2D8h+var_260], rax
0x18008332e  lea     r13, aBaseFsFsrmUtil_11; "base\\fs\\fsrm\\utilities\\security\\sr"...
0x180083335  mov     [r11-220h], r13
0x18008333c  lea     r12, aIsingroup; "IsInGroup"
0x180083343  mov     [r11-218h], r12
0x18008334a  lea     rsi, aSecsecrc; "SECSECRC"
0x180083351  mov     [r11-210h], rsi
0x180083358  mov     [rsp+2D8h+var_208], 0CBh
0x180083363  mov     r14d, 11h
0x180083369  mov     [r11-204h], r14d
0x180083370  mov     [rsp+2D8h+var_200], 0FFh
0x18008337b  xor     ebx, ebx
0x18008337d  mov     [rsp+2D8h+var_198], 1000000h
0x180083388  xor     edx, edx; Val
0x18008338a  lea     r8d, [r14+4Fh]; Size
0x18008338e  lea     rcx, [r11-1F8h]; void *
0x180083395  call    memset_0
0x18008339a  nop
0x18008339b  mov     r8, r12
0x18008339e  lea     rdx, [rsp+2D8h+var_220]
0x1800833a6  lea     rcx, [rsp+2D8h+var_F8]
0x1800833ae  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x1800833b3  nop
0x1800833b4  mov     [rsp+2D8h+IsMember], ebx
0x1800833b8  mov     [rsp+2D8h+SidToCheck], rbx
0x1800833c0  mov     [rsp+2D8h+var_F0], ebx
0x1800833c7  mov     dword ptr [rsp+2D8h+pIdentifierAuthority.Value], ebx
0x1800833ce  mov     word ptr [rsp+2D8h+pIdentifierAuthority.Value+4], 500h
0x1800833d8  lea     rax, [rsp+2D8h+SidToCheck]
0x1800833e0  mov     [rsp+2D8h+pSid], rax; pSid
0x1800833e5  mov     [rsp+2D8h+nSubAuthority7], ebx; nSubAuthority7
0x1800833e9  mov     [rsp+2D8h+nSubAuthority6], ebx; nSubAuthority6
0x1800833ed  mov     [rsp+2D8h+nSubAuthority5], ebx; nSubAuthority5
0x1800833f1  mov     [rsp+2D8h+nSubAuthority4], ebx; nSubAuthority4
0x1800833f5  mov     [rsp+2D8h+nSubAuthority3], ebx; nSubAuthority3
0x1800833f9  mov     [rsp+2D8h+nSubAuthority2], ebx; nSubAuthority2
0x1800833fd  mov     r9d, 220h; nSubAuthority1
0x180083403  lea     r8d, [r14+0Fh]; nSubAuthority0
0x180083407  mov     dl, 2; nSubAuthorityCount
0x180083409  lea     rcx, [rsp+2D8h+pIdentifierAuthority]; pIdentifierAuthority
0x180083411  call    cs:__imp_AllocateAndInitializeSid
0x180083417  test    eax, eax
0x180083419  jz      loc_180083583
0x18008341f  lea     r15, ??_7?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@6B@; const CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>::`vftable'
0x180083426  mov     [rsp+2D8h+var_270], r15
0x18008342b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18008342f  mov     [rsp+2D8h+hObject], rsi
0x180083434  lea     r14, ??_7?$CSrmAuto@PEAXV?$CSrmAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CSrmAuto<void *,CSrmAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x18008343b  mov     [rsp+2D8h+var_270], r14
0x180083440  mov     rcx, [rsp+2D8h+hObject]; hObject
0x180083445  cmp     rcx, rsi
0x180083448  jz      short loc_180083450
0x18008344a  call    cs:__imp_CloseHandle
0x180083450  mov     [rsp+2D8h+hObject], rsi
0x180083455  mov     ecx, edi; int
0x180083457  lea     r8, [rsp+2D8h+hObject]; void **
0x18008345c  call    ?GetCurrentAccessToken@@YA_NHKPEAPEAX@Z; GetCurrentAccessToken(int,ulong,void * *)
0x180083461  lea     r8, [rsp+2D8h+IsMember]; IsMember
0x180083466  mov     rdx, [rsp+2D8h+SidToCheck]; SidToCheck
0x18008346e  test    al, al
0x180083470  jz      short loc_180083479
0x180083472  mov     rcx, [rsp+2D8h+hObject]
0x180083477  jmp     short loc_18008347B
0x180083479  xor     ecx, ecx; TokenHandle
0x18008347b  call    cs:__imp_CheckTokenMembership
0x180083481  test    eax, eax
0x180083483  jz      loc_1800835CC
0x180083489  mov     [rsp+2D8h+var_270], r14
0x18008348e  mov     rcx, [rsp+2D8h+hObject]; hObject
0x180083493  cmp     rcx, rsi
0x180083496  jz      short loc_18008349E
0x180083498  call    cs:__imp_CloseHandle
0x18008349e  mov     [rsp+2D8h+hObject], rsi
0x1800834a3  mov     [rsp+2D8h+var_270], r15
0x1800834a8  mov     rcx, [rsp+2D8h+hObject]; hObject
0x1800834ad  cmp     rcx, rsi
0x1800834b0  jz      short loc_1800834B8
0x1800834b2  call    cs:__imp_CloseHandle
0x1800834b8  mov     [rsp+2D8h+hObject], rsi
0x1800834bd  jmp     short loc_1800834C1
0x1800834bf  xor     ebx, ebx
0x1800834c1  mov     eax, [rsp+2D8h+var_F0]
0x1800834c8  mov     dword ptr [rsp+2D8h+var_260], eax
0x1800834cc  mov     rcx, [rsp+2D8h+SidToCheck]; pSid
0x1800834d4  test    rcx, rcx
0x1800834d7  jz      short loc_1800834E0
0x1800834d9  call    cs:__imp_FreeSid
0x1800834df  nop
0x1800834e0  jmp     short loc_1800834E8
0x1800834e2  jmp     short loc_1800834BF
0x1800834e4  jmp     short loc_1800834BF
0x1800834e6  xor     ebx, ebx
0x1800834e8  mov     eax, dword ptr [rsp+2D8h+var_260]
0x1800834ec  test    eax, eax
0x1800834ee  js      loc_18008361C
0x1800834f4  jmp     short loc_1800834FA
0x1800834f6  jmp     short loc_1800834E6
0x1800834f8  jmp     short loc_1800834E6
0x1800834fa  cmp     [rsp+2D8h+IsMember], ebx
0x1800834fe  setnz   cl
0x180083501  lea     rdx, aFalse; "FALSE"
0x180083508  lea     rax, aTrue_0; "TRUE"
0x18008350f  test    cl, cl
0x180083511  cmovz   rax, rdx
0x180083515  mov     qword ptr [rsp+2D8h+nSubAuthority2], rax
0x18008351a  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x180083521  mov     r8d, 0AAh; unsigned int
0x180083527  lea     rdx, aReturn; "RETURN"
0x18008352e  lea     rcx, [rsp+2D8h+var_F8]; this
0x180083536  call    ?TraceInternalWithFormat@CSrmFunctionTracerBase@@QEAAXPEBGK0ZZ; CSrmFunctionTracerBase::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x18008353b  cmp     [rsp+2D8h+IsMember], ebx
0x18008353f  setnz   bl
0x180083542  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180083549  mov     [rsp+2D8h+var_F8], rax
0x180083551  lea     rcx, [rsp+2D8h+var_F8]; this
0x180083559  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18008355e  mov     al, bl
0x180083560  mov     rcx, [rsp+2D8h+var_48]
0x180083568  xor     rcx, rsp; StackCookie
0x18008356b  call    __security_check_cookie
0x180083570  add     rsp, 2A0h
0x180083577  pop     r15
0x180083579  pop     r14
0x18008357b  pop     r13
0x18008357d  pop     r12
0x18008357f  pop     rdi
0x180083580  pop     rsi
0x180083581  pop     rbx
0x180083582  retn
0x180083583  lea     rax, [rsp+2D8h+var_190]
0x18008358b  mov     [rsp+2D8h+var_260], rax
0x180083590  mov     [rsp+2D8h+nSubAuthority3], r14d
0x180083595  mov     [rsp+2D8h+nSubAuthority2], 0E8h
0x18008359d  mov     r9, r12
0x1800835a0  mov     r8, rsi
0x1800835a3  mov     rdx, r13
0x1800835a6  lea     rcx, [rsp+2D8h+var_190]
0x1800835ae  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x1800835b3  nop
0x1800835b4  lea     r8, aAllocateandini; "AllocateAndInitializeSid"
0x1800835bb  mov     rdx, rax
0x1800835be  lea     rcx, [rsp+2D8h+var_F8]
0x1800835c6  call    ?TranslateWin32Error@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::TranslateWin32Error(CSrmDebugInfo,ushort const *,...)
0x1800835cc  lea     rax, [rsp+2D8h+var_190]
0x1800835d4  mov     [rsp+2D8h+var_260], rax
0x1800835d9  mov     [rsp+2D8h+nSubAuthority3], 11h
0x1800835e1  mov     [rsp+2D8h+nSubAuthority2], 0FAh
0x1800835e9  mov     r9, r12
0x1800835ec  lea     r8, aSecsecrc; "SECSECRC"
0x1800835f3  mov     rdx, r13
0x1800835f6  lea     rcx, [rsp+2D8h+var_190]
0x1800835fe  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x180083603  nop
0x180083604  lea     r8, aChecktokenmemb; "CheckTokenMembership"
0x18008360b  mov     rdx, rax
0x18008360e  lea     rcx, [rsp+2D8h+var_F8]
0x180083616  call    ?TranslateWin32Error@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::TranslateWin32Error(CSrmDebugInfo,ushort const *,...)
0x18008361c  mov     [rsp+2D8h+pExceptionObject], eax
0x180083623  lea     rdx, _TI1J; pThrowInfo
0x18008362a  lea     rcx, [rsp+2D8h+pExceptionObject]; pExceptionObject
0x180083632  call    _CxxThrowException_0
```
