# CHungApp::_WriteHangEvent(ulong)

- ea: `0x18002b4ec`
- end: `0x18002bb9b`
- name: `?_WriteHangEvent@CHungApp@@AEAAJK@Z`
- size: `1711`
- prototype: `__int64 __fastcall(CHungApp *this, char)`
- caller_count: `4`
- callee_count: `11`
- tags: `file_ops, loader_planting`

## callers

- `0x18002710c`
- `0x180027460`
- `0x18002917c`
- `0x180029690`

## callees

- `0x180001e38`
- `0x1800029d0`
- `0x1800029f4`
- `0x180011ef8`
- `0x180026788`
- `0x1800267ec`
- `0x18002987c`
- `0x18002b4ec`
- `0x18002bd40`
- `0x18002ef78`
- `0x18002f0d4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x18002b5a4`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x18002b5a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b5c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b5c7`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x18002b7cd`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x18002b7cd`
- `ntdll!EtwCheckCoverage` at `0x18002b963`
- `ntdll!EtwCheckCoverage` at `0x18002b963`
- `ntdll!NtSetInformationProcess` at `0x18002b982`
- `ntdll!NtSetInformationProcess` at `0x18002b982`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18002b7de`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18002b7de`

## pseudocode

```c
__int64 __fastcall CHungApp::_WriteHangEvent(CHungApp *this, char a2)
{
  DWORD LastError; // eax
  char dwLowDateTime; // si
  __int64 v7; // rax
  int v8; // r15d
  unsigned int v9; // r11d
  __int64 v10; // rdx
  __int64 v11; // rdi
  __int64 v12; // r8
  char *v13; // rax
  __int64 v14; // r9
  __int64 v15; // rax
  char *v16; // r10
  __int64 v17; // rcx
  char *v18; // r8
  char v19; // r9
  char *v20; // rax
  const char *v21; // rax
  char *v22; // rcx
  char v23; // r8
  char *v24; // rax
  unsigned __int64 v25; // r14
  __int64 v26; // r12
  WORD wProcessorArchitecture; // si
  __int64 v28; // r8
  int ProcessAppSessionGuid; // eax
  int ProcessTelemetryTargetAppParams; // edi
  __int64 v31; // r9
  _BOOL8 v32; // rcx
  WORD v33[2]; // [rsp+C0h] [rbp-80h] BYREF
  WINBOOL Wow64Process; // [rsp+C4h] [rbp-7Ch] BYREF
  unsigned __int64 v35; // [rsp+C8h] [rbp-78h] BYREF
  unsigned __int64 v36; // [rsp+D0h] [rbp-70h] BYREF
  struct _FILETIME CreationTime; // [rsp+D8h] [rbp-68h] BYREF
  BOOL v38; // [rsp+E0h] [rbp-60h] BYREF
  struct _FILETIME ExitTime; // [rsp+E8h] [rbp-58h] BYREF
  void *v40; // [rsp+F0h] [rbp-50h]
  _WORD *v41; // [rsp+F8h] [rbp-48h]
  _WORD v42[8]; // [rsp+100h] [rbp-40h] BYREF
  void *v43; // [rsp+110h] [rbp-30h]
  _WORD *v44; // [rsp+118h] [rbp-28h]
  _WORD v45[8]; // [rsp+120h] [rbp-20h] BYREF
  unsigned __int64 v46; // [rsp+130h] [rbp-10h] BYREF
  int *v47; // [rsp+138h] [rbp-8h] BYREF
  int *v48; // [rsp+140h] [rbp+0h] BYREF
  struct _GUID *v49; // [rsp+148h] [rbp+8h] BYREF
  int *v50; // [rsp+150h] [rbp+10h] BYREF
  wchar_t *v51; // [rsp+158h] [rbp+18h] BYREF
  wchar_t *v52; // [rsp+160h] [rbp+20h] BYREF
  unsigned __int64 v53; // [rsp+168h] [rbp+28h] BYREF
  wchar_t *v54; // [rsp+170h] [rbp+30h] BYREF
  int *v55; // [rsp+178h] [rbp+38h] BYREF
  int *v56; // [rsp+180h] [rbp+40h] BYREF
  __int64 v57; // [rsp+188h] [rbp+48h] BYREF
  int *v58; // [rsp+190h] [rbp+50h] BYREF
  struct _FILETIME v59; // [rsp+198h] [rbp+58h] BYREF
  __int64 v60; // [rsp+1A0h] [rbp+60h] BYREF
  struct _SYSTEM_INFO SystemInfo; // [rsp+1A8h] [rbp+68h] BYREF
  struct _GUID v62; // [rsp+1D8h] [rbp+98h] BYREF
  char v63[40]; // [rsp+1E8h] [rbp+A8h] BYREF
  char v64; // [rsp+210h] [rbp+D0h] BYREF
  char v65[111]; // [rsp+211h] [rbp+D1h] BYREF
  wchar_t v66[64]; // [rsp+280h] [rbp+140h] BYREF
  wchar_t v67[72]; // [rsp+300h] [rbp+1C0h] BYREF
  wchar_t v68[128]; // [rsp+390h] [rbp+250h] BYREF

  if ( *((_DWORD *)this + 83) )
    return 1;
  StringCchPrintfA(
    v63,
    0x20u,
    "%u.%u.%u.%u",
    *((unsigned __int16 *)this + 920),
    *((unsigned __int16 *)this + 921),
    *((unsigned __int16 *)this + 922),
    *((unsigned __int16 *)this + 923));
  ExitTime = 0;
  CreationTime = 0;
  if ( GetProcessTimes(*((HANDLE *)this + 148), &CreationTime, &ExitTime, &ExitTime, &ExitTime) )
  {
    dwLowDateTime = CreationTime.dwLowDateTime;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_28e55efa1b5d3afdb4532fbb5bd9be34_Traceguids, LastError);
    }
    dwLowDateTime = 0;
    CreationTime = 0;
  }
  v7 = *((_QWORD *)this + 44);
  if ( v7 )
    v8 = *(_DWORD *)(v7 + 624);
  else
    v8 = *((_DWORD *)this + 84);
  v64 = 0;
  v9 = 0;
  v10 = 98;
  v11 = 2147483646;
  do
  {
    if ( (v8 & qword_180037BC0[2 * (int)v9]) != 0 )
    {
      v12 = 98;
      v13 = &v64;
      do
      {
        if ( !*v13 )
          break;
        ++v13;
        --v12;
      }
      while ( v12 );
      v14 = (98 - v12) & -(__int64)(v12 != 0);
      if ( v12 )
      {
        v15 = 2147483646;
        v16 = (char *)qword_180037BC0[2 * (int)v9 + 1];
        v17 = 98 - v14;
        v18 = &v65[v14 - 1];
        if ( v14 != 98 )
        {
          do
          {
            if ( !v15 )
              break;
            v19 = *v16;
            if ( !*v16 )
              break;
            ++v16;
            *v18++ = v19;
            --v15;
            --v17;
          }
          while ( v17 );
        }
        v20 = v18 - 1;
        if ( v17 )
          v20 = v18;
        *v20 = 0;
      }
    }
    ++v9;
  }
  while ( v9 < 7 );
  if ( !v64 )
  {
    v21 = ";Unknown";
    v22 = &v64;
    do
    {
      if ( !v11 )
        break;
      v23 = *v21;
      if ( !*v21 )
        break;
      ++v21;
      *v22++ = v23;
      --v11;
      --v10;
    }
    while ( v10 );
    v24 = v22 - 1;
    if ( v10 )
      v24 = v22;
    *v24 = 0;
  }
  if ( (Application_HangEnableBits & 1) != 0 )
    McTemplateU0zsdiqzzzzs_EventWriteTransfer(
      (_DWORD)this + 1848,
      (_DWORD)this + 2236,
      (_DWORD)this + 1192,
      (unsigned int)v63,
      *((_DWORD *)this + 12),
      dwLowDateTime,
      a2,
      (__int64)this + 1320,
      (__int64)this + 2236,
      (__int64)this + 1848,
      (__int64)this + 2104,
      (__int64)v65);
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  Wow64Process = 0;
  v25 = 0;
  v36 = 0;
  v35 = 0;
  v62 = 0;
  v43 = v45;
  v44 = v45;
  v45[0] = 0;
  v40 = v42;
  v41 = v42;
  v42[0] = 0;
  v26 = *((_QWORD *)this + 230);
  GetNativeSystemInfo(&SystemInfo);
  if ( IsWow64Process(*((HANDLE *)this + 148), &Wow64Process) && Wow64Process )
  {
    if ( SystemInfo.wProcessorArchitecture == 6 || SystemInfo.wProcessorArchitecture == 9 )
    {
      wProcessorArchitecture = 0;
    }
    else
    {
      wProcessorArchitecture = 0;
      if ( SystemInfo.wProcessorArchitecture == 12 )
        wProcessorArchitecture = 5;
    }
  }
  else
  {
    wProcessorArchitecture = SystemInfo.wProcessorArchitecture;
  }
  v28 = *((_QWORD *)this + 44);
  if ( v28 )
  {
    CHungApp::CaptureRemoteString(v68, 0x80u, (const wchar_t *)(v28 + 628), 0x80u);
    CHungApp::CaptureRemoteString(v66, 0x40u, (const wchar_t *)(*((_QWORD *)this + 44) + 884LL), 0x40u);
    CHungApp::CaptureRemoteString(v67, 0x42u, (const wchar_t *)(*((_QWORD *)this + 44) + 1012LL), 0x42u);
    CHungApp::CaptureRemoteULONG64(&v36, (unsigned __int64 *)(*((_QWORD *)this + 44) + 1144LL));
    v25 = v36;
  }
  else
  {
    v68[0] = 0;
    v67[0] = 0;
    v66[0] = 0;
  }
  ProcessAppSessionGuid = TelGetProcessAppSessionGuid(*((HANDLE *)this + 148), &v62, &v35);
  if ( ProcessAppSessionGuid < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      WPP_28e55efa1b5d3afdb4532fbb5bd9be34_Traceguids,
      (unsigned int)ProcessAppSessionGuid);
  }
  ProcessTelemetryTargetAppParams = UtilGetProcessTelemetryTargetAppParams(*((HANDLE *)this + 148));
  if ( ProcessTelemetryTargetAppParams < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      WPP_28e55efa1b5d3afdb4532fbb5bd9be34_Traceguids,
      (unsigned int)ProcessTelemetryTargetAppParams);
  }
  if ( (unsigned int)dword_180047144 < MEMORY[0x7FFE037C] && !(unsigned __int8)EtwCheckCoverage(&off_180047138) )
    NtSetInformationProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL, ProcessAffinityMask|0x40, &off_180047138, 0x18u);
  v32 = (*((_DWORD *)this + 85) & 8) == 0;
  if ( (unsigned int)dword_1800470C8 > 5
    && (qword_1800470D8 & 0x800000000000LL) != 0
    && (qword_1800470E0 & 0x800000000000LL) == qword_1800470E0 )
  {
    v38 = (*((_DWORD *)this + 85) & 8) == 0;
    v46 = v35;
    v47 = (int *)v40;
    v48 = (int *)v43;
    v49 = &v62;
    v50 = (int *)((char *)this + 2236);
    v33[0] = wProcessorArchitecture;
    v51 = v67;
    v52 = v68;
    v53 = v25;
    v54 = v66;
    v55 = (int *)((char *)this + 2104);
    v56 = (int *)((char *)this + 1848);
    v57 = v26;
    v58 = (int *)((char *)this + 1192);
    LODWORD(v35) = v8;
    v59 = CreationTime;
    LODWORD(v36) = *((_DWORD *)this + 12);
    v60 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<2>,_tlgWrapSz<wchar_t>,_tlgWrapperByRef<16>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v32,
      (__int64)&unk_18003FAB8,
      0x800000000000LL,
      v31,
      (__int64)&v60,
      (__int64)&v36,
      (__int64)&v59,
      (__int64)&v35,
      &v58,
      (__int64)&v57,
      &v56,
      &v55,
      (int **)&v54,
      (__int64)&v53,
      (int **)&v52,
      (int **)&v51,
      (__int64)v33,
      &v50,
      (__int64 *)&v49,
      &v48,
      &v47,
      (__int64)&v46,
      (__int64)&v38);
  }
  if ( v40 != v42 )
    operator delete(v40, (const struct std::nothrow_t *)&std::nothrow);
  if ( v43 != v45 )
    operator delete(v43, (const struct std::nothrow_t *)&std::nothrow);
  return (unsigned int)ProcessTelemetryTargetAppParams;
}

```

## disassembly

```asm
0x18002b4ec  mov     [rsp-8+arg_8], rbx
0x18002b4f1  mov     [rsp-8+arg_10], rsi
0x18002b4f6  push    rbp
0x18002b4f7  push    rdi
0x18002b4f8  push    r12
0x18002b4fa  push    r14
0x18002b4fc  push    r15
0x18002b4fe  lea     rbp, [rsp-360h]
0x18002b506  sub     rsp, 4A0h
0x18002b50d  mov     rax, cs:__security_cookie
0x18002b514  xor     rax, rsp
0x18002b517  mov     [rbp+380h+var_30], rax
0x18002b51e  mov     r14d, edx
0x18002b521  mov     rbx, rcx
0x18002b524  cmp     dword ptr [rcx+14Ch], 0
0x18002b52b  jz      short loc_18002B537
0x18002b52d  mov     eax, 1
0x18002b532  jmp     loc_18002BB70
0x18002b537  movzx   eax, word ptr [rcx+736h]
0x18002b53e  movzx   ecx, word ptr [rcx+734h]
0x18002b545  movzx   edx, word ptr [rbx+732h]
0x18002b54c  movzx   r9d, word ptr [rbx+730h]
0x18002b554  mov     dword ptr [rsp+4C0h+var_490], eax
0x18002b558  mov     dword ptr [rsp+4C0h+var_498], ecx
0x18002b55c  mov     dword ptr [rsp+4C0h+lpUserTime], edx
0x18002b560  lea     r8, aUUUU; "%u.%u.%u.%u"
0x18002b567  mov     edx, 20h ; ' '; unsigned __int64
0x18002b56c  lea     rcx, [rbp+380h+var_2D8]; char *
0x18002b573  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18002b578  mov     qword ptr [rbp+380h+ExitTime.dwLowDateTime], 0
0x18002b580  mov     qword ptr [rbp+380h+CreationTime.dwLowDateTime], 0
0x18002b588  lea     rax, [rbp+380h+ExitTime]
0x18002b58c  mov     [rsp+4C0h+lpUserTime], rax; lpUserTime
0x18002b591  lea     r9, [rbp+380h+ExitTime]; lpKernelTime
0x18002b595  lea     r8, [rbp+380h+ExitTime]; lpExitTime
0x18002b599  lea     rdx, [rbp+380h+CreationTime]; lpCreationTime
0x18002b59d  mov     rcx, [rbx+4A0h]; hProcess
0x18002b5a4  call    cs:__imp_GetProcessTimes
0x18002b5aa  lea     rcx, WPP_GLOBAL_Control
0x18002b5b1  test    eax, eax
0x18002b5b3  jnz     short loc_18002B5F4
0x18002b5b5  mov     rax, cs:WPP_GLOBAL_Control
0x18002b5bc  cmp     rax, rcx
0x18002b5bf  jz      short loc_18002B5EC
0x18002b5c1  test    byte ptr [rax+1Ch], 2
0x18002b5c5  jz      short loc_18002B5EC
0x18002b5c7  call    cs:__imp_GetLastError
0x18002b5cd  mov     edx, 10h
0x18002b5d2  mov     r9d, eax
0x18002b5d5  lea     r8, WPP_28e55efa1b5d3afdb4532fbb5bd9be34_Traceguids
0x18002b5dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b5e3  mov     rcx, [rcx+10h]
0x18002b5e7  call    WPP_SF_d
0x18002b5ec  xor     esi, esi
0x18002b5ee  mov     qword ptr [rbp+380h+CreationTime.dwLowDateTime], rsi
0x18002b5f2  jmp     short loc_18002B5F8
0x18002b5f4  mov     rsi, qword ptr [rbp+380h+CreationTime.dwLowDateTime]
0x18002b5f8  mov     rax, [rbx+160h]
0x18002b5ff  test    rax, rax
0x18002b602  jz      short loc_18002B60D
0x18002b604  mov     r15d, [rax+270h]
0x18002b60b  jmp     short loc_18002B614
0x18002b60d  mov     r15d, [rbx+150h]
0x18002b614  mov     [rbp+380h+var_2B0], 0
0x18002b61b  xor     r11d, r11d
0x18002b61e  lea     r12, qword_180037BC0
0x18002b625  lea     edx, [r11+62h]
0x18002b629  mov     edi, 7FFFFFFEh
0x18002b62e  movsxd  r10, r11d
0x18002b631  add     r10, r10
0x18002b634  test    [r12+r10*8], r15d
0x18002b638  jz      short loc_18002B6B1
0x18002b63a  mov     r8, rdx
0x18002b63d  lea     rax, [rbp+380h+var_2B0]
0x18002b644  cmp     byte ptr [rax], 0
0x18002b647  jz      short loc_18002B652
0x18002b649  inc     rax
0x18002b64c  sub     r8, 1
0x18002b650  jnz     short loc_18002B644
0x18002b652  mov     rax, r8
0x18002b655  mov     rcx, rdx
0x18002b658  sub     rcx, r8
0x18002b65b  neg     rax
0x18002b65e  sbb     r9, r9
0x18002b661  and     r9, rcx
0x18002b664  test    r8, r8
0x18002b667  jz      short loc_18002B6B1
0x18002b669  mov     rax, rdi
0x18002b66c  mov     r10, [r12+r10*8+8]
0x18002b671  mov     rcx, rdx
0x18002b674  sub     rcx, r9
0x18002b677  lea     r8, [rbp+380h+var_2B0]
0x18002b67e  lea     r8, [r8+r9]
0x18002b682  jz      short loc_18002B6A3
0x18002b684  test    rax, rax
0x18002b687  jz      short loc_18002B6A3
0x18002b689  mov     r9b, [r10]
0x18002b68c  test    r9b, r9b
0x18002b68f  jz      short loc_18002B6A3
0x18002b691  inc     r10
0x18002b694  mov     [r8], r9b
0x18002b697  inc     r8
0x18002b69a  dec     rax
0x18002b69d  sub     rcx, 1
0x18002b6a1  jnz     short loc_18002B684
0x18002b6a3  lea     rax, [r8-1]
0x18002b6a7  test    rcx, rcx
0x18002b6aa  cmovnz  rax, r8
0x18002b6ae  mov     byte ptr [rax], 0
0x18002b6b1  inc     r11d
0x18002b6b4  cmp     r11d, 7
0x18002b6b8  jb      loc_18002B62E
0x18002b6be  cmp     [rbp+380h+var_2B0], 0
0x18002b6c5  jnz     short loc_18002B702
0x18002b6c7  lea     rax, aUnknown_0; ";Unknown"
0x18002b6ce  lea     rcx, [rbp+380h+var_2B0]
0x18002b6d5  test    rdi, rdi
0x18002b6d8  jz      short loc_18002B6F4
0x18002b6da  mov     r8b, [rax]
0x18002b6dd  test    r8b, r8b
0x18002b6e0  jz      short loc_18002B6F4
0x18002b6e2  inc     rax
0x18002b6e5  mov     [rcx], r8b
0x18002b6e8  inc     rcx
0x18002b6eb  dec     rdi
0x18002b6ee  sub     rdx, 1
0x18002b6f2  jnz     short loc_18002B6D5
0x18002b6f4  lea     rax, [rcx-1]
0x18002b6f8  test    rdx, rdx
0x18002b6fb  cmovnz  rax, rcx
0x18002b6ff  mov     byte ptr [rax], 0
0x18002b702  test    cs:Application_HangEnableBits, 1
0x18002b709  jz      short loc_18002B76B
0x18002b70b  lea     rax, [rbx+838h]
0x18002b712  lea     rcx, [rbx+738h]
0x18002b719  lea     rdx, [rbx+8BCh]
0x18002b720  lea     r9, [rbx+528h]
0x18002b727  lea     r8, [rbx+4A8h]
0x18002b72e  lea     r10, [rbp+380h+var_2AF]
0x18002b735  mov     [rsp+4C0h+var_468], r10
0x18002b73a  mov     [rsp+4C0h+var_470], rax
0x18002b73f  mov     [rsp+4C0h+var_478], rcx
0x18002b744  mov     [rsp+4C0h+var_480], rdx
0x18002b749  mov     [rsp+4C0h+var_488], r9
0x18002b74e  mov     dword ptr [rsp+4C0h+var_490], r14d
0x18002b753  mov     [rsp+4C0h+var_498], rsi
0x18002b758  mov     eax, [rbx+30h]
0x18002b75b  mov     dword ptr [rsp+4C0h+lpUserTime], eax
0x18002b75f  lea     r9, [rbp+380h+var_2D8]
0x18002b766  call    McTemplateU0zsdiqzzzzs_EventWriteTransfer
0x18002b76b  xorps   xmm0, xmm0
0x18002b76e  movups  xmmword ptr [rbp+380h+SystemInfo], xmm0
0x18002b772  movups  xmmword ptr [rbp+380h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x18002b776  movups  xmmword ptr [rbp+380h+SystemInfo.dwNumberOfProcessors], xmm0
0x18002b77d  mov     [rbp+380h+Wow64Process], 0
0x18002b784  xor     r14d, r14d
0x18002b787  mov     [rbp+380h+var_3F0], r14
0x18002b78b  mov     [rbp+380h+var_3F8], r14
0x18002b78f  movups  xmmword ptr [rbp+380h+var_2E8.Data1], xmm0
0x18002b796  lea     rax, [rbp+380h+var_3A0]
0x18002b79a  mov     [rbp+380h+var_3B0], rax
0x18002b79e  lea     rax, [rbp+380h+var_3A0]
0x18002b7a2  mov     [rbp+380h+var_3A8], rax
0x18002b7a6  xor     eax, eax
0x18002b7a8  mov     [rbp+380h+var_3A0], ax
0x18002b7ac  lea     rax, [rbp+380h+var_3C0]
0x18002b7b0  mov     [rbp+380h+var_3D0], rax
0x18002b7b4  lea     rax, [rbp+380h+var_3C0]
0x18002b7b8  mov     [rbp+380h+var_3C8], rax
0x18002b7bc  xor     eax, eax
0x18002b7be  mov     [rbp+380h+var_3C0], ax
0x18002b7c2  mov     r12, [rbx+730h]
0x18002b7c9  lea     rcx, [rbp+380h+SystemInfo]; lpSystemInfo
0x18002b7cd  call    cs:__imp_GetNativeSystemInfo
0x18002b7d3  lea     rdx, [rbp+380h+Wow64Process]; Wow64Process
0x18002b7d7  mov     rcx, [rbx+4A0h]; hProcess
0x18002b7de  call    cs:__imp_IsWow64Process
0x18002b7e4  lea     ecx, [r14+5]
0x18002b7e8  test    eax, eax
0x18002b7ea  jz      short loc_18002B813
0x18002b7ec  cmp     [rbp+380h+Wow64Process], r14d
0x18002b7f0  jz      short loc_18002B813
0x18002b7f2  movzx   eax, word ptr [rbp+380h+SystemInfo]
0x18002b7f6  cmp     eax, 6
0x18002b7f9  jz      short loc_18002B80C
0x18002b7fb  cmp     eax, 9
0x18002b7fe  jz      short loc_18002B80C
0x18002b800  xor     esi, esi
0x18002b802  cmp     eax, 0Ch
0x18002b805  jnz     short loc_18002B817
0x18002b807  movzx   esi, cx
0x18002b80a  jmp     short loc_18002B817
0x18002b80c  xor     eax, eax
0x18002b80e  movzx   esi, ax
0x18002b811  jmp     short loc_18002B817
0x18002b813  movzx   esi, word ptr [rbp+380h+SystemInfo]
0x18002b817  mov     r8, [rbx+160h]
0x18002b81e  test    r8, r8
0x18002b821  jz      short loc_18002B89F
0x18002b823  add     r8, 274h; wchar_t *
0x18002b82a  mov     edx, 80h; unsigned int
0x18002b82f  mov     r9d, edx; unsigned int
0x18002b832  lea     rcx, [rbp+380h+var_130]; wchar_t *
0x18002b839  call    ?CaptureRemoteString@CHungApp@@CAJPEA_WKPEB_WK@Z; CHungApp::CaptureRemoteString(wchar_t *,ulong,wchar_t const *,ulong)
0x18002b83e  mov     r8, [rbx+160h]
0x18002b845  add     r8, 374h; wchar_t *
0x18002b84c  mov     edx, 40h ; '@'; unsigned int
0x18002b851  mov     r9d, edx; unsigned int
0x18002b854  lea     rcx, [rbp+380h+var_240]; wchar_t *
0x18002b85b  call    ?CaptureRemoteString@CHungApp@@CAJPEA_WKPEB_WK@Z; CHungApp::CaptureRemoteString(wchar_t *,ulong,wchar_t const *,ulong)
0x18002b860  mov     r8, [rbx+160h]
0x18002b867  add     r8, 3F4h; wchar_t *
0x18002b86e  mov     edx, 42h ; 'B'; unsigned int
0x18002b873  mov     r9d, edx; unsigned int
0x18002b876  lea     rcx, [rbp+380h+var_1C0]; wchar_t *
0x18002b87d  call    ?CaptureRemoteString@CHungApp@@CAJPEA_WKPEB_WK@Z; CHungApp::CaptureRemoteString(wchar_t *,ulong,wchar_t const *,ulong)
0x18002b882  mov     rdx, [rbx+160h]
0x18002b889  add     rdx, 478h; unsigned __int64 *
0x18002b890  lea     rcx, [rbp+380h+var_3F0]; unsigned __int64 *
0x18002b894  call    ?CaptureRemoteULONG64@CHungApp@@CAJPEA_K0@Z; CHungApp::CaptureRemoteULONG64(unsigned __int64 *,unsigned __int64 *)
0x18002b899  mov     r14, [rbp+380h+var_3F0]
0x18002b89d  jmp     short loc_18002B8B6
0x18002b89f  xor     eax, eax
0x18002b8a1  mov     [rbp+380h+var_130], ax
0x18002b8a8  mov     [rbp+380h+var_1C0], ax
0x18002b8af  mov     [rbp+380h+var_240], ax
0x18002b8b6  lea     r8, [rbp+380h+var_3F8]; unsigned __int64 *
0x18002b8ba  lea     rdx, [rbp+380h+var_2E8]; struct _GUID *
0x18002b8c1  mov     rcx, [rbx+4A0h]; ProcessHandle
0x18002b8c8  call    ?TelGetProcessAppSessionGuid@@YAJPEAXPEAU_GUID@@PEA_K@Z; TelGetProcessAppSessionGuid(void *,_GUID *,unsigned __int64 *)
0x18002b8cd  test    eax, eax
0x18002b8cf  jns     short loc_18002B902
0x18002b8d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b8d8  lea     rdx, WPP_GLOBAL_Control
0x18002b8df  cmp     rcx, rdx
0x18002b8e2  jz      short loc_18002B902
0x18002b8e4  test    byte ptr [rcx+1Ch], 2
0x18002b8e8  jz      short loc_18002B902
0x18002b8ea  mov     edx, 11h
0x18002b8ef  mov     r9d, eax
0x18002b8f2  lea     r8, WPP_28e55efa1b5d3afdb4532fbb5bd9be34_Traceguids
0x18002b8f9  mov     rcx, [rcx+10h]
0x18002b8fd  call    WPP_SF_d
0x18002b902  lea     r8, [rbp+380h+var_3D0]
0x18002b906  lea     rdx, [rbp+380h+var_3B0]
0x18002b90a  mov     rcx, [rbx+4A0h]; ProcessHandle
0x18002b911  call    ?UtilGetProcessTelemetryTargetAppParams@@YAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@1@Z; UtilGetProcessTelemetryTargetAppParams(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18002b916  mov     edi, eax
0x18002b918  test    eax, eax
0x18002b91a  jns     short loc_18002B94D
0x18002b91c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b923  lea     rax, WPP_GLOBAL_Control
0x18002b92a  cmp     rcx, rax
0x18002b92d  jz      short loc_18002B94D
0x18002b92f  test    byte ptr [rcx+1Ch], 2
0x18002b933  jz      short loc_18002B94D
0x18002b935  mov     edx, 12h
0x18002b93a  mov     r9d, edi
0x18002b93d  lea     r8, WPP_28e55efa1b5d3afdb4532fbb5bd9be34_Traceguids
0x18002b944  mov     rcx, [rcx+10h]
0x18002b948  call    WPP_SF_d
0x18002b94d  mov     eax, ds:7FFE037Ch
0x18002b954  cmp     cs:dword_180047144, eax
0x18002b95a  jnb     short loc_18002B988
0x18002b95c  lea     rcx, off_180047138; "WER_Report_AppHang"
0x18002b963  call    cs:__imp_EtwCheckCoverage
0x18002b969  test    al, al
0x18002b96b  jnz     short loc_18002B988
0x18002b96d  mov     r9d, 18h; ProcessInformationLength
0x18002b973  lea     r8, off_180047138; ProcessInformation
0x18002b97a  lea     edx, [r9+3Dh]; ProcessInformationClass
0x18002b97e  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18002b982  call    cs:__imp_NtSetInformationProcess
0x18002b988  mov     ecx, [rbx+154h]
0x18002b98e  shr     ecx, 3
0x18002b991  not     ecx
0x18002b993  and     ecx, 1
0x18002b996  mov     eax, cs:dword_1800470C8
0x18002b99c  cmp     eax, 5
0x18002b99f  jbe     loc_18002BB3B
0x18002b9a5  mov     rdx, cs:qword_1800470E0
0x18002b9ac  mov     rax, cs:qword_1800470D8
0x18002b9b3  mov     r8, 800000000000h
0x18002b9bd  test    r8, rax
0x18002b9c0  jz      loc_18002BB3B
0x18002b9c6  mov     rax, rdx
0x18002b9c9  and     rax, r8
0x18002b9cc  cmp     rax, rdx
0x18002b9cf  jnz     loc_18002BB3B
0x18002b9d5  mov     [rbp+380h+var_3E0], ecx
0x18002b9d8  mov     rax, [rbp+380h+var_3F8]
0x18002b9dc  mov     [rbp+380h+var_390], rax
0x18002b9e0  mov     rax, [rbp+380h+var_3D0]
0x18002b9e4  mov     [rbp+380h+var_388], rax
0x18002b9e8  mov     rax, [rbp+380h+var_3B0]
0x18002b9ec  mov     [rbp+380h+var_380], rax
0x18002b9f0  lea     rax, [rbp+380h+var_2E8]
0x18002b9f7  mov     [rbp+380h+var_378], rax
0x18002b9fb  lea     rax, [rbx+8BCh]
0x18002ba02  mov     [rbp+380h+var_370], rax
  ... truncated ...
```
