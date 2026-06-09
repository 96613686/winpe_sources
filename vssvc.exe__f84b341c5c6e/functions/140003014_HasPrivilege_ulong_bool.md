# HasPrivilege(ulong,bool)

- ea: `0x140003014`
- end: `0x140003317`
- name: `?HasPrivilege@@YA_NK_N@Z`
- size: `771`
- prototype: `bool __fastcall()`
- caller_count: `4`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001d54`
- `0x140001d90`
- `0x140002270`
- `0x140004690`

## callees

- `0x140003014`
- `0x140006020`
- `0x1400137c0`
- `0x1400138e0`
- `0x140013cb0`
- `0x140030e90`
- `0x140070fcc`
- `0x140091560`
- `0x1400921dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000320d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000320d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400032d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400032d3`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x140003203`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x140003203`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400030b6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400030b6`
- `VssTrace!__imp_VssTraceMessage` at `0x14000318e`
- `VssTrace!__imp_VssTraceMessage` at `0x14000318e`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140003105`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140003105`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x1400030f6`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x1400030f6`

## string_xrefs

- `0x140003046`: `HasPrivilege`
- `0x140003226`: `HasPrivilege`
- `0x14000326a`: `PrivilegeCheck`
- `0x14000303b`: `base\stor\vss\modules\sec\security.cxx`

## pseudocode

```c
bool __fastcall HasPrivilege()
{
  int v0; // eax
  __int64 v1; // rcx
  int v2; // ebx
  signed int LastError; // eax
  unsigned int v4; // ebx
  bool v5; // bl
  const wchar_t *v6; // rax
  WINBOOL pfResult; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v9; // [rsp+58h] [rbp-A8h] BYREF
  void **v10; // [rsp+60h] [rbp-A0h]
  HANDLE ClientToken; // [rsp+68h] [rbp-98h] BYREF
  _DWORD v12[4]; // [rsp+70h] [rbp-90h] BYREF
  const unsigned __int16 *v13; // [rsp+80h] [rbp-80h]
  const unsigned __int16 *v14; // [rsp+88h] [rbp-78h]
  unsigned int v15; // [rsp+90h] [rbp-70h]
  int v16; // [rsp+94h] [rbp-6Ch]
  const wchar_t *v17; // [rsp+98h] [rbp-68h]
  unsigned int v18; // [rsp+A0h] [rbp-60h]
  DWORD TickCount; // [rsp+A4h] [rbp-5Ch]
  int v20; // [rsp+A8h] [rbp-58h]
  __int128 v21; // [rsp+B0h] [rbp-50h]
  __int128 v22; // [rsp+C0h] [rbp-40h]
  __int64 v23; // [rsp+D0h] [rbp-30h]
  const unsigned __int16 *v24; // [rsp+E0h] [rbp-20h] BYREF
  const wchar_t *v25; // [rsp+E8h] [rbp-18h]
  const unsigned __int16 *v26; // [rsp+F0h] [rbp-10h]
  int v27; // [rsp+F8h] [rbp-8h]
  int v28; // [rsp+FCh] [rbp-4h]
  int v29; // [rsp+100h] [rbp+0h]
  _BYTE v30[120]; // [rsp+108h] [rbp+8h] BYREF
  int v31; // [rsp+180h] [rbp+80h]
  _PRIVILEGE_SET RequiredPrivileges; // [rsp+188h] [rbp+88h] BYREF

  v24 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
  v25 = L"HasPrivilege";
  v26 = L"SECSECRC";
  v27 = 335;
  v28 = 11;
  v29 = 255;
  v31 = 0x1000000;
  memset_0(v30, 0, sizeof(v30));
  v12[2] = 0;
  v17 = L"HasPrivilege";
  v13 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
  v14 = L"SECSECRC";
  v15 = 335;
  v16 = 11;
  TickCount = GetTickCount();
  v12[1] = -1;
  v20 = v29;
  v12[0] = 0;
  v23 = 0;
  v21 = 0;
  v22 = 0;
  v9 = 0;
  if ( (int)VssGetTracingContextPerThread(&v9) < 0 )
  {
    v1 = v23;
  }
  else
  {
    v0 = VssSetTracingContextPerThread(v12);
    v1 = v23;
    if ( v0 >= 0 )
      v1 = v9;
    v23 = v1;
  }
  if ( v1 )
    v18 = *(_DWORD *)(v1 + 48) + 1;
  else
    v18 = 0;
  v2 = 160;
  if ( v20 != 255 )
    v2 = v20;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)v12) )
    VssTraceMessage(v13, v14, v15, v18, v16, v17, L"ENTER", v2, 0);
  CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v24);
  v10 = &CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
  pfResult = 0;
  ClientToken = (HANDLE)-1LL;
  GetCurrentAccessToken(1, 0, &ClientToken);
  RequiredPrivileges.PrivilegeCount = 1;
  RequiredPrivileges.Control = 1;
  RequiredPrivileges.Privilege[0].Luid = (LUID)17LL;
  RequiredPrivileges.Privilege[0].Attributes = 2;
  if ( !PrivilegeCheck(ClientToken, &RequiredPrivileges, &pfResult) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    v24 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v25 = L"HasPrivilege";
    v26 = L"SECSECRC";
    v27 = 356;
    v28 = 11;
    v29 = 255;
    v31 = 0x1000000;
    memset_0(v30, 0, sizeof(v30));
    CVssFunctionTracer::TranslateError(v12, &v24, v4, L"PrivilegeCheck");
  }
  v5 = pfResult != 0;
  v6 = L"TRUE";
  if ( !pfResult )
    v6 = L"FALSE";
  CVssFunctionTracer::TraceInternalWithFormat((CVssFunctionTracer *)v12, L"RETURN", 0xAAu, L"Returning BOOL: %s", v6);
  v10 = &CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
  if ( ClientToken != (HANDLE)-1LL )
    CloseHandle(ClientToken);
  ClientToken = (HANDLE)-1LL;
  v10 = &CVssAutoGenericValue_Storage<unsigned char *,0,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),unsigned char * & (*)(unsigned char * &),&public: static unsigned char * & DTyper<unsigned char *>::Identity(unsigned char * &)>::`vftable';
  CVssFunctionTracer::~CVssFunctionTracer((CVssFunctionTracer *)v12);
  return v5;
}

```

## disassembly

```asm
0x140003014  push    rbp
0x140003016  push    rbx
0x140003017  push    r13
0x140003019  push    r15
0x14000301b  lea     rbp, [rsp-0B8h]
0x140003023  sub     rsp, 1B8h
0x14000302a  mov     rax, cs:__security_cookie
0x140003031  xor     rax, rsp
0x140003034  mov     [rbp+0D0h+var_28], rax
0x14000303b  lea     r13, aBaseStorVssMod_24; "base\\stor\\vss\\modules\\sec\\security"...
0x140003042  mov     [rbp+0D0h+var_F0], r13
0x140003046  lea     rax, aHasprivilege; "HasPrivilege"
0x14000304d  mov     [rbp+0D0h+var_E8], rax
0x140003051  lea     rax, aSecsecrc; "SECSECRC"
0x140003058  mov     [rbp+0D0h+var_E0], rax
0x14000305c  mov     [rbp+0D0h+var_D8], 14Fh
0x140003063  mov     [rbp+0D0h+var_D4], 0Bh
0x14000306a  mov     [rbp+0D0h+var_D0], 0FFh
0x140003071  mov     [rbp+0D0h+var_50], 1000000h
0x14000307b  xor     edx, edx; Val
0x14000307d  lea     r8d, [rdx+78h]; Size
0x140003081  lea     rcx, [rbp+0D0h+var_C8]; void *
0x140003085  call    memset_0
0x14000308a  mov     [rsp+1D0h+var_158], 0
0x140003092  mov     rax, [rbp+0D0h+var_E8]
0x140003096  mov     [rbp+0D0h+var_138], rax
0x14000309a  mov     rax, [rbp+0D0h+var_F0]
0x14000309e  mov     [rbp+0D0h+var_150], rax
0x1400030a2  mov     rax, [rbp+0D0h+var_E0]
0x1400030a6  mov     [rbp+0D0h+var_148], rax
0x1400030aa  mov     eax, [rbp+0D0h+var_D8]
0x1400030ad  mov     [rbp+0D0h+var_140], eax
0x1400030b0  mov     eax, [rbp+0D0h+var_D4]
0x1400030b3  mov     [rbp+0D0h+var_13C], eax
0x1400030b6  call    cs:__imp_GetTickCount
0x1400030bc  mov     [rbp+0D0h+var_12C], eax
0x1400030bf  mov     [rsp+1D0h+var_15C], 0FFFFFFFFh
0x1400030c7  mov     eax, [rbp+0D0h+var_D0]
0x1400030ca  mov     [rbp+0D0h+var_128], eax
0x1400030cd  mov     [rsp+1D0h+var_160], 0
0x1400030d5  mov     [rbp+0D0h+var_100], 0
0x1400030dd  xorps   xmm0, xmm0
0x1400030e0  movups  [rbp+0D0h+var_120], xmm0
0x1400030e4  movups  [rbp+0D0h+var_110], xmm0
0x1400030e8  mov     [rsp+1D0h+var_178], 0
0x1400030f1  lea     rcx, [rsp+1D0h+var_178]
0x1400030f6  call    cs:__imp_VssGetTracingContextPerThread
0x1400030fc  test    eax, eax
0x1400030fe  js      short loc_14000311D
0x140003100  lea     rcx, [rsp+1D0h+var_160]
0x140003105  call    cs:__imp_VssSetTracingContextPerThread
0x14000310b  mov     rcx, [rbp+0D0h+var_100]
0x14000310f  test    eax, eax
0x140003111  cmovns  rcx, [rsp+1D0h+var_178]
0x140003117  mov     [rbp+0D0h+var_100], rcx
0x14000311b  jmp     short loc_140003121
0x14000311d  mov     rcx, [rbp+0D0h+var_100]
0x140003121  test    rcx, rcx
0x140003124  jz      short loc_140003130
0x140003126  mov     eax, [rcx+30h]
0x140003129  inc     eax
0x14000312b  mov     [rbp+0D0h+var_130], eax
0x14000312e  jmp     short loc_140003137
0x140003130  mov     [rbp+0D0h+var_130], 0
0x140003137  mov     ebx, 0A0h
0x14000313c  cmp     [rbp+0D0h+var_128], 0FFh
0x140003143  cmovnz  ebx, [rbp+0D0h+var_128]
0x140003147  lea     rcx, [rsp+1D0h+var_160]; this
0x14000314c  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x140003151  test    eax, eax
0x140003153  jz      short loc_140003194
0x140003155  mov     [rsp+1D0h+var_190], 0
0x14000315e  mov     [rsp+1D0h+var_198], ebx
0x140003162  lea     rax, aEnter; "ENTER"
0x140003169  mov     [rsp+1D0h+var_1A0], rax
0x14000316e  mov     rax, [rbp+0D0h+var_138]
0x140003172  mov     [rsp+1D0h+var_1A8], rax
0x140003177  mov     eax, [rbp+0D0h+var_13C]
0x14000317a  mov     dword ptr [rsp+1D0h+var_1B0], eax
0x14000317e  mov     r9d, [rbp+0D0h+var_130]
0x140003182  mov     r8d, [rbp+0D0h+var_140]
0x140003186  mov     rdx, [rbp+0D0h+var_148]
0x14000318a  mov     rcx, [rbp+0D0h+var_150]
0x14000318e  call    cs:__imp_VssTraceMessage
0x140003194  lea     rcx, [rbp+0D0h+var_F0]; this
0x140003198  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x14000319d  nop
0x14000319e  lea     r15, ??_7?$CVssAuto@PEAXV?$CVssAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x1400031a5  mov     [rsp+1D0h+var_170], r15
0x1400031aa  mov     [rsp+1D0h+pfResult], 0
0x1400031b2  mov     [rsp+1D0h+ClientToken], 0FFFFFFFFFFFFFFFFh
0x1400031bb  lea     r8, [rsp+1D0h+ClientToken]; void **
0x1400031c0  xor     edx, edx; bool
0x1400031c2  mov     cl, 1; bool
0x1400031c4  call    ?GetCurrentAccessToken@@YA_N_N0PEAPEAX@Z; GetCurrentAccessToken(bool,bool,void * *)
0x1400031c9  mov     [rbp+0D0h+RequiredPrivileges.PrivilegeCount], 1
0x1400031d3  mov     [rbp+0D0h+RequiredPrivileges.Control], 1
0x1400031dd  mov     qword ptr [rbp+0D0h+RequiredPrivileges.Privilege.Luid.LowPart], 11h
0x1400031e8  mov     [rbp+0D0h+RequiredPrivileges.Privilege.Attributes], 2
0x1400031f2  lea     r8, [rsp+1D0h+pfResult]; pfResult
0x1400031f7  lea     rdx, [rbp+0D0h+RequiredPrivileges]; RequiredPrivileges
0x1400031fe  mov     rcx, [rsp+1D0h+ClientToken]; ClientToken
0x140003203  call    cs:__imp_PrivilegeCheck
0x140003209  test    eax, eax
0x14000320b  jnz     short loc_140003283
0x14000320d  call    cs:__imp_GetLastError
0x140003213  mov     ebx, eax
0x140003215  test    eax, eax
0x140003217  jle     short loc_140003222
0x140003219  movzx   ebx, ax
0x14000321c  or      ebx, 80070000h
0x140003222  mov     [rbp+0D0h+var_F0], r13
0x140003226  lea     rax, aHasprivilege; "HasPrivilege"
0x14000322d  mov     [rbp+0D0h+var_E8], rax
0x140003231  lea     rax, aSecsecrc; "SECSECRC"
0x140003238  mov     [rbp+0D0h+var_E0], rax
0x14000323c  mov     [rbp+0D0h+var_D8], 164h
0x140003243  mov     [rbp+0D0h+var_D4], 0Bh
0x14000324a  mov     [rbp+0D0h+var_D0], 0FFh
0x140003251  mov     [rbp+0D0h+var_50], 1000000h
0x14000325b  xor     edx, edx; Val
0x14000325d  lea     r8d, [rdx+78h]; Size
0x140003261  lea     rcx, [rbp+0D0h+var_C8]; void *
0x140003265  call    memset_0
0x14000326a  lea     r9, aPrivilegecheck; "PrivilegeCheck"
0x140003271  mov     r8d, ebx
0x140003274  lea     rdx, [rbp+0D0h+var_F0]
0x140003278  lea     rcx, [rsp+1D0h+var_160]
0x14000327d  call    ?TranslateError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBG@Z; CVssFunctionTracer::TranslateError(CVssDebugInfo,long,ushort const *)
0x140003283  cmp     [rsp+1D0h+pfResult], 0
0x140003288  setnz   bl
0x14000328b  lea     rcx, aFalse; "FALSE"
0x140003292  lea     rax, aTrue; "TRUE"
0x140003299  test    bl, bl
0x14000329b  cmovz   rax, rcx
0x14000329f  mov     [rsp+1D0h+var_1B0], rax
0x1400032a4  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x1400032ab  mov     r8d, 0AAh; unsigned int
0x1400032b1  lea     rdx, aReturn; "RETURN"
0x1400032b8  lea     rcx, [rsp+1D0h+var_160]; this
0x1400032bd  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x1400032c2  nop
0x1400032c3  mov     [rsp+1D0h+var_170], r15
0x1400032c8  mov     rcx, [rsp+1D0h+ClientToken]; hObject
0x1400032cd  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400032d1  jz      short loc_1400032D9
0x1400032d3  call    cs:__imp_CloseHandle
0x1400032d9  mov     [rsp+1D0h+ClientToken], 0FFFFFFFFFFFFFFFFh
0x1400032e2  lea     rax, ??_7?$CVssAutoGenericValue_Storage@PEAE$0A@P6AKPEAX@Z$1?NetApiBufferFree@@YAK0@ZP6AAEAPEAEAEAPEAE@Z$1?Identity@?$DTyper@PEAE@@SAAEAPEAE1@Z@@6B@; const CVssAutoGenericValue_Storage<uchar *,0,ulong (*)(void *),&NetApiBufferFree(void *),uchar * & (*)(uchar * &),&DTyper<uchar *>::Identity(uchar * &)>::`vftable'
0x1400032e9  mov     [rsp+1D0h+var_170], rax
0x1400032ee  lea     rcx, [rsp+1D0h+var_160]; this
0x1400032f3  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x1400032f8  mov     al, bl
0x1400032fa  mov     rcx, [rbp+0D0h+var_28]
0x140003301  xor     rcx, rsp; StackCookie
0x140003304  call    __security_check_cookie
0x140003309  add     rsp, 1B8h
0x140003310  pop     r15
0x140003312  pop     r13
0x140003314  pop     rbx
0x140003315  pop     rbp
0x140003316  retn
```
