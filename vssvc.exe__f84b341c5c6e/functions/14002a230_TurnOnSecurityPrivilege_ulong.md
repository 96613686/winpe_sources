# TurnOnSecurityPrivilege(ulong)

- ea: `0x14002a230`
- end: `0x14002a71c`
- name: `?TurnOnSecurityPrivilege@@YAJK@Z`
- size: `1260`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140028d60`

## callees

- `0x1400137c0`
- `0x140013c60`
- `0x140015e38`
- `0x140028b48`
- `0x14002a230`
- `0x140091560`
- `0x1400921dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002a459`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002a459`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002a676`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002a676`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14002a42b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14002a42b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14002a418`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14002a418`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002a558`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002a558`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x14002a47e`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x14002a47e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002a31a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002a31a`
- `VssTrace!__imp_VssTraceMessage` at `0x14002a5f9`
- `VssTrace!__imp_VssTraceMessage` at `0x14002a5f9`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14002a517`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14002a517`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14002a36c`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14002a36c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002a4ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002a4ff`

## string_xrefs

- `0x14002a25f`: `base\stor\vss\modules\sec\security.cxx`
- `0x14002a26d`: `TurnOnSecurityPrivilege`
- `0x14002a4e5`: `AdjustTokenPrivileges`
- `0x14002a65d`: `OpenProcessToken`
- `0x14002a6e4`: `Fail to acquire the %lu privilege`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall TurnOnSecurityPrivilege(unsigned int a1)
{
  LUID v1; // rsi
  __int64 v2; // rax
  int v3; // ebx
  __int64 i; // rbx
  void *v5; // rcx
  HANDLE CurrentProcess; // rax
  unsigned int v7; // ebx
  PTOKEN_PRIVILEGES PreviousState; // [rsp+20h] [rbp-1C8h]
  __int64 v10; // [rsp+50h] [rbp-198h] BYREF
  void **v11; // [rsp+58h] [rbp-190h]
  void *TokenHandle; // [rsp+60h] [rbp-188h] BYREF
  unsigned __int64 v13; // [rsp+70h] [rbp-178h] BYREF
  unsigned int v14; // [rsp+78h] [rbp-170h]
  const unsigned __int16 *v15; // [rsp+80h] [rbp-168h]
  const unsigned __int16 *v16; // [rsp+88h] [rbp-160h]
  unsigned int v17; // [rsp+90h] [rbp-158h]
  unsigned int v18; // [rsp+94h] [rbp-154h]
  const unsigned __int16 *v19; // [rsp+98h] [rbp-150h]
  unsigned int v20; // [rsp+A0h] [rbp-148h]
  DWORD TickCount; // [rsp+A4h] [rbp-144h]
  int v22; // [rsp+A8h] [rbp-140h]
  __int128 v23; // [rsp+B0h] [rbp-138h]
  __int128 v24; // [rsp+C0h] [rbp-128h]
  __int64 v25; // [rsp+D0h] [rbp-118h]
  const unsigned __int16 *v26; // [rsp+E0h] [rbp-108h] BYREF
  const unsigned __int16 *v27; // [rsp+E8h] [rbp-100h]
  const unsigned __int16 *v28; // [rsp+F0h] [rbp-F8h]
  int v29; // [rsp+F8h] [rbp-F0h]
  int v30; // [rsp+FCh] [rbp-ECh]
  int v31; // [rsp+100h] [rbp-E8h]
  LPVOID pv[15]; // [rsp+108h] [rbp-E0h] BYREF
  int v33; // [rsp+180h] [rbp-68h]
  _TOKEN_PRIVILEGES NewState; // [rsp+1A0h] [rbp-48h] BYREF

  v1 = (LUID)a1;
  v26 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
  v27 = L"TurnOnSecurityPrivilege";
  v28 = L"SECSECRC";
  v29 = 805;
  v30 = 11;
  v31 = 255;
  v33 = 0x1000000;
  memset_0(pv, 0, sizeof(pv));
  v14 = 0;
  v19 = L"TurnOnSecurityPrivilege";
  v15 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
  v16 = L"SECSECRC";
  v17 = 805;
  v18 = 11;
  TickCount = GetTickCount();
  v22 = 255;
  v13 = 0xFFFFFFFF00000000uLL;
  v25 = 0;
  v23 = 0;
  v24 = 0;
  v10 = 0;
  if ( (int)VssGetTracingContextPerThread(&v10) < 0 || (int)VssSetTracingContextPerThread(&v13) < 0 )
  {
    v2 = v25;
  }
  else
  {
    v2 = v10;
    v25 = v10;
  }
  if ( v2 )
    v20 = *(_DWORD *)(v2 + 48) + 1;
  else
    v20 = 0;
  v3 = 160;
  if ( v22 != 255 )
    v3 = v22;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v13, v18) )
    VssTraceMessage(v15, v16, v17, v20, v18, v19, L"ENTER", v3, 0);
  if ( HIBYTE(v33) )
  {
    for ( i = 0; i != 15; ++i )
    {
      v5 = pv[i];
      if ( v5 )
      {
        CoTaskMemFree(v5);
        pv[i] = 0;
      }
    }
  }
  v11 = &CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
  NewState = 0;
  TokenHandle = (void *)-1LL;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x20u, &TokenHandle) )
  {
    v26 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v27 = L"TurnOnSecurityPrivilege";
    v28 = L"SECSECRC";
    v29 = 817;
    v30 = 11;
    v31 = 255;
    v33 = 0x1000000;
    memset_0(pv, 0, sizeof(pv));
    CVssFunctionTracer::TranslateWin32Error(&v13, &v26, L"OpenProcessToken");
  }
  NewState.PrivilegeCount = 1;
  NewState.Privileges[0].Luid = v1;
  NewState.Privileges[0].Attributes = 2;
  SetLastError(0);
  if ( !AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, 0, 0) )
  {
    v26 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v27 = L"TurnOnSecurityPrivilege";
    v28 = L"SECSECRC";
    v29 = 835;
    v30 = 11;
    v31 = 255;
    v33 = 0x1000000;
    memset_0(pv, 0, sizeof(pv));
    CVssFunctionTracer::TranslateWin32Error(&v13, &v26, L"AdjustTokenPrivileges");
  }
  if ( GetLastError() == 1300 )
  {
    v26 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v27 = L"TurnOnSecurityPrivilege";
    v28 = L"SECSECRC";
    v29 = 840;
    v30 = 11;
    v31 = 255;
    v33 = 0x1000000;
    memset_0(pv, 0, sizeof(pv));
    LODWORD(PreviousState) = v1.LowPart;
    CVssFunctionTracer::Throw(&v13, &v26, 2147943700LL, L"Fail to acquire the %lu privilege", PreviousState);
  }
  v7 = v14;
  v11 = &CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
  if ( TokenHandle != (void *)-1LL )
    CloseHandle(TokenHandle);
  TokenHandle = (void *)-1LL;
  v11 = &CVssAutoGenericValue_Storage<unsigned char *,0,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),unsigned char * & (*)(unsigned char * &),&public: static unsigned char * & DTyper<unsigned char *>::Identity(unsigned char * &)>::`vftable';
  CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v13);
  return v7;
}

```

## disassembly

```asm
0x14002a230  mov     r11, rsp
0x14002a233  mov     [r11+10h], rbx
0x14002a237  mov     [r11+18h], rsi
0x14002a23b  push    rdi
0x14002a23c  push    r12
0x14002a23e  push    r13
0x14002a240  push    r14
0x14002a242  push    r15
0x14002a244  sub     rsp, 1C0h
0x14002a24b  mov     rax, cs:__security_cookie
0x14002a252  xor     rax, rsp
0x14002a255  mov     [rsp+1E8h+var_38], rax
0x14002a25d  mov     esi, ecx
0x14002a25f  lea     r15, aBaseStorVssMod_24; "base\\stor\\vss\\modules\\sec\\security"...
0x14002a266  mov     [r11-108h], r15
0x14002a26d  lea     r12, aTurnonsecurity; "TurnOnSecurityPrivilege"
0x14002a274  mov     [r11-100h], r12
0x14002a27b  lea     r13, aSecsecrc; "SECSECRC"
0x14002a282  mov     [r11-0F8h], r13
0x14002a289  mov     [rsp+1E8h+var_F0], 325h
0x14002a294  mov     [rsp+1E8h+var_EC], 0Bh
0x14002a29f  mov     [rsp+1E8h+var_E8], 0FFh
0x14002a2aa  xor     r14d, r14d
0x14002a2ad  mov     dword ptr [r11-68h], 1000000h
0x14002a2b5  xor     edx, edx; Val
0x14002a2b7  mov     r8d, 78h ; 'x'; Size
0x14002a2bd  lea     rcx, [r11-0E0h]; void *
0x14002a2c4  call    memset_0
0x14002a2c9  mov     [rsp+1E8h+var_170], r14d
0x14002a2ce  mov     rax, [rsp+1E8h+var_100]
0x14002a2d6  mov     [rsp+1E8h+var_150], rax
0x14002a2de  mov     rax, [rsp+1E8h+var_108]
0x14002a2e6  mov     [rsp+1E8h+var_168], rax
0x14002a2ee  mov     rax, [rsp+1E8h+var_F8]
0x14002a2f6  mov     [rsp+1E8h+var_160], rax
0x14002a2fe  mov     eax, [rsp+1E8h+var_F0]
0x14002a305  mov     [rsp+1E8h+var_158], eax
0x14002a30c  mov     eax, [rsp+1E8h+var_EC]
0x14002a313  mov     [rsp+1E8h+var_154], eax
0x14002a31a  call    cs:__imp_GetTickCount
0x14002a320  mov     [rsp+1E8h+var_144], eax
0x14002a327  mov     [rsp+1E8h+var_174], 0FFFFFFFFh
0x14002a32f  mov     eax, [rsp+1E8h+var_E8]
0x14002a336  mov     [rsp+1E8h+var_140], eax
0x14002a33d  mov     [rsp+1E8h+var_178], r14d
0x14002a342  mov     [rsp+1E8h+var_118], r14
0x14002a34a  xorps   xmm0, xmm0
0x14002a34d  movdqa  [rsp+1E8h+var_138], xmm0
0x14002a356  xorps   xmm1, xmm1
0x14002a359  movdqa  [rsp+1E8h+var_128], xmm1
0x14002a362  mov     [rsp+1E8h+var_198], r14
0x14002a367  lea     rcx, [rsp+1E8h+var_198]
0x14002a36c  call    cs:__imp_VssGetTracingContextPerThread
0x14002a372  test    eax, eax
0x14002a374  jns     loc_14002A512
0x14002a37a  mov     rax, [rsp+1E8h+var_118]
0x14002a382  test    rax, rax
0x14002a385  jz      loc_14002A537
0x14002a38b  mov     eax, [rax+30h]
0x14002a38e  inc     eax
0x14002a390  mov     [rsp+1E8h+var_148], eax
0x14002a397  mov     ebx, 0A0h
0x14002a39c  cmp     [rsp+1E8h+var_140], 0FFh
0x14002a3a7  cmovnz  ebx, [rsp+1E8h+var_140]
0x14002a3af  mov     edx, [rsp+1E8h+var_154]; unsigned int
0x14002a3b6  lea     rcx, [rsp+1E8h+var_178]; this
0x14002a3bb  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHK@Z; CVssFunctionTracer::IsTracingEnabled(ulong)
0x14002a3c0  test    eax, eax
0x14002a3c2  jnz     loc_14002A5AC
0x14002a3c8  cmp     [rsp+1E8h+var_65], r14b
0x14002a3d0  jz      short loc_14002A3EF
0x14002a3d2  mov     rbx, r14
0x14002a3d5  mov     rcx, [rsp+rbx*8+1E8h+pv]; pv
0x14002a3dd  test    rcx, rcx
0x14002a3e0  jnz     loc_14002A4FF
0x14002a3e6  inc     rbx
0x14002a3e9  cmp     rbx, 0Fh
0x14002a3ed  jnz     short loc_14002A3D5
0x14002a3ef  mov     [rsp+1E8h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x14002a3f8  lea     rdi, ??_7?$CVssAuto@PEAXV?$CVssAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x14002a3ff  mov     [rsp+1E8h+var_190], rdi
0x14002a404  xorps   xmm0, xmm0
0x14002a407  movups  xmmword ptr [rsp+1E8h+NewState.PrivilegeCount], xmm0
0x14002a40f  mov     [rsp+1E8h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x14002a418  call    cs:__imp_GetCurrentProcess
0x14002a41e  lea     r8, [rsp+1E8h+TokenHandle]; TokenHandle
0x14002a423  mov     edx, 20h ; ' '; DesiredAccess
0x14002a428  mov     rcx, rax; ProcessHandle
0x14002a42b  call    cs:__imp_OpenProcessToken
0x14002a431  test    eax, eax
0x14002a433  jz      loc_14002A604
0x14002a439  mov     [rsp+1E8h+NewState.PrivilegeCount], 1
0x14002a444  mov     qword ptr [rsp+1E8h+NewState.Privileges.Luid.LowPart], rsi
0x14002a44c  mov     [rsp+1E8h+NewState.Privileges.Attributes], 2
0x14002a457  xor     ecx, ecx; dwErrCode
0x14002a459  call    cs:__imp_SetLastError
0x14002a45f  mov     [rsp+1E8h+ReturnLength], r14; ReturnLength
0x14002a464  mov     [rsp+1E8h+PreviousState], r14; PreviousState
0x14002a469  mov     r9d, 10h; BufferLength
0x14002a46f  lea     r8, [rsp+1E8h+NewState]; NewState
0x14002a477  xor     edx, edx; DisableAllPrivileges
0x14002a479  mov     rcx, [rsp+1E8h+TokenHandle]; TokenHandle
0x14002a47e  call    cs:__imp_AdjustTokenPrivileges
0x14002a484  test    eax, eax
0x14002a486  jnz     loc_14002A676
0x14002a48c  mov     [rsp+1E8h+var_108], r15
0x14002a494  mov     [rsp+1E8h+var_100], r12
0x14002a49c  mov     [rsp+1E8h+var_F8], r13
0x14002a4a4  mov     [rsp+1E8h+var_F0], 343h
0x14002a4af  mov     [rsp+1E8h+var_EC], 0Bh
0x14002a4ba  mov     [rsp+1E8h+var_E8], 0FFh
0x14002a4c5  mov     dword ptr [rsp+180h], 1000000h
0x14002a4d0  xor     edx, edx; Val
0x14002a4d2  mov     r8d, 78h ; 'x'; Size
0x14002a4d8  lea     rcx, [rsp+1E8h+pv]; void *
0x14002a4e0  call    memset_0
0x14002a4e5  lea     r8, aAdjusttokenpri; "AdjustTokenPrivileges"
0x14002a4ec  lea     rdx, [rsp+1E8h+var_108]
0x14002a4f4  lea     rcx, [rsp+1E8h+var_178]
0x14002a4f9  call    ?TranslateWin32Error@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::TranslateWin32Error(CVssDebugInfo,ushort const *,...)
0x14002a4ff  call    cs:__imp_CoTaskMemFree
0x14002a505  mov     [rsp+rbx*8+1E8h+pv], r14
0x14002a50d  jmp     loc_14002A3E6
0x14002a512  lea     rcx, [rsp+1E8h+var_178]
0x14002a517  call    cs:__imp_VssSetTracingContextPerThread
0x14002a51d  test    eax, eax
0x14002a51f  js      loc_14002A37A
0x14002a525  mov     rax, [rsp+1E8h+var_198]
0x14002a52a  mov     [rsp+1E8h+var_118], rax
0x14002a532  jmp     loc_14002A382
0x14002a537  mov     [rsp+1E8h+var_148], r14d
0x14002a53f  jmp     loc_14002A397
0x14002a544  mov     ebx, [rsp+1E8h+var_170]
0x14002a548  mov     [rsp+1E8h+var_190], rdi
0x14002a54d  mov     rcx, [rsp+1E8h+TokenHandle]; hObject
0x14002a552  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14002a556  jz      short loc_14002A55E
0x14002a558  call    cs:__imp_CloseHandle
0x14002a55e  mov     [rsp+1E8h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x14002a567  lea     rax, ??_7?$CVssAutoGenericValue_Storage@PEAE$0A@P6AKPEAX@Z$1?NetApiBufferFree@@YAK0@ZP6AAEAPEAEAEAPEAE@Z$1?Identity@?$DTyper@PEAE@@SAAEAPEAE1@Z@@6B@; const CVssAutoGenericValue_Storage<uchar *,0,ulong (*)(void *),&NetApiBufferFree(void *),uchar * & (*)(uchar * &),&DTyper<uchar *>::Identity(uchar * &)>::`vftable'
0x14002a56e  mov     [rsp+1E8h+var_190], rax
0x14002a573  lea     rcx, [rsp+1E8h+var_178]; this
0x14002a578  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x14002a57d  mov     eax, ebx
0x14002a57f  mov     rcx, [rsp+1E8h+var_38]
0x14002a587  xor     rcx, rsp; StackCookie
0x14002a58a  call    __security_check_cookie
0x14002a58f  lea     r11, [rsp+1E8h+var_28]
0x14002a597  mov     rbx, [r11+38h]
0x14002a59b  mov     rsi, [r11+40h]
0x14002a59f  mov     rsp, r11
0x14002a5a2  pop     r15
0x14002a5a4  pop     r14
0x14002a5a6  pop     r13
0x14002a5a8  pop     r12
0x14002a5aa  pop     rdi
0x14002a5ab  retn
0x14002a5ac  mov     [rsp+1E8h+var_1A8], r14
0x14002a5b1  mov     [rsp+1E8h+var_1B0], ebx
0x14002a5b5  lea     rax, aEnter; "ENTER"
0x14002a5bc  mov     [rsp+1E8h+var_1B8], rax
0x14002a5c1  mov     rax, [rsp+1E8h+var_150]
0x14002a5c9  mov     [rsp+1E8h+ReturnLength], rax
0x14002a5ce  mov     eax, [rsp+1E8h+var_154]
0x14002a5d5  mov     dword ptr [rsp+1E8h+PreviousState], eax
0x14002a5d9  mov     r9d, [rsp+1E8h+var_148]
0x14002a5e1  mov     r8d, [rsp+1E8h+var_158]
0x14002a5e9  mov     rdx, [rsp+1E8h+var_160]
0x14002a5f1  mov     rcx, [rsp+1E8h+var_168]
0x14002a5f9  call    cs:__imp_VssTraceMessage
0x14002a5ff  jmp     loc_14002A3C8
0x14002a604  mov     [rsp+1E8h+var_108], r15
0x14002a60c  mov     [rsp+1E8h+var_100], r12
0x14002a614  mov     [rsp+1E8h+var_F8], r13
0x14002a61c  mov     [rsp+1E8h+var_F0], 331h
0x14002a627  mov     [rsp+1E8h+var_EC], 0Bh
0x14002a632  mov     [rsp+1E8h+var_E8], 0FFh
0x14002a63d  mov     dword ptr [rsp+180h], 1000000h
0x14002a648  xor     edx, edx; Val
0x14002a64a  mov     r8d, 78h ; 'x'; Size
0x14002a650  lea     rcx, [rsp+1E8h+pv]; void *
0x14002a658  call    memset_0
0x14002a65d  lea     r8, aOpenprocesstok; "OpenProcessToken"
0x14002a664  lea     rdx, [rsp+1E8h+var_108]
0x14002a66c  lea     rcx, [rsp+1E8h+var_178]
0x14002a671  call    ?TranslateWin32Error@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::TranslateWin32Error(CVssDebugInfo,ushort const *,...)
0x14002a676  call    cs:__imp_GetLastError
0x14002a67c  cmp     eax, 514h
0x14002a681  jnz     loc_14002A704
0x14002a687  mov     [rsp+1E8h+var_108], r15
0x14002a68f  mov     [rsp+1E8h+var_100], r12
0x14002a697  mov     [rsp+1E8h+var_F8], r13
0x14002a69f  mov     [rsp+1E8h+var_F0], 348h
0x14002a6aa  mov     [rsp+1E8h+var_EC], 0Bh
0x14002a6b5  mov     [rsp+1E8h+var_E8], 0FFh
0x14002a6c0  mov     dword ptr [rsp+180h], 1000000h
0x14002a6cb  xor     edx, edx; Val
0x14002a6cd  mov     r8d, 78h ; 'x'; Size
0x14002a6d3  lea     rcx, [rsp+1E8h+pv]; void *
0x14002a6db  call    memset_0
0x14002a6e0  mov     dword ptr [rsp+1E8h+PreviousState], esi
0x14002a6e4  lea     r9, aFailToAcquireT; "Fail to acquire the %lu privilege"
0x14002a6eb  mov     r8d, 80070514h
0x14002a6f1  lea     rdx, [rsp+1E8h+var_108]
0x14002a6f9  lea     rcx, [rsp+1E8h+var_178]
0x14002a6fe  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x14002a704  jmp     loc_14002A544
0x14002a709  jmp     short loc_14002A70F
0x14002a70b  jmp     short loc_14002A70F
0x14002a70d  jmp     short $+2
0x14002a70f  lea     rdi, ??_7?$CVssAuto@PEAXV?$CVssAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x14002a716  jmp     loc_14002A544
```
