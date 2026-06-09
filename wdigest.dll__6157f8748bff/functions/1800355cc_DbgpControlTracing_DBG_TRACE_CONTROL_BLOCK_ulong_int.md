# _DbgpControlTracing(_DBG_TRACE_CONTROL_BLOCK *,ulong,int)

- ea: `0x1800355cc`
- end: `0x180035c74`
- name: `?_DbgpControlTracing@@YAKPEAU_DBG_TRACE_CONTROL_BLOCK@@KH@Z`
- size: `1704`
- prototype: `unsigned int __fastcall(struct _DBG_TRACE_CONTROL_BLOCK *, unsigned int, int)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000fdf0`
- `0x180035c7c`

## callees

- `0x180012880`
- `0x1800132ec`
- `0x1800132f8`
- `0x180013304`
- `0x180013364`
- `0x1800355cc`
- `0x1800360ac`
- `0x180036618`
- `0x1800366ac`
- `0x180037750`
- `0x1800377bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800356b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800357d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035832`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035965`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035992`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035a53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800356b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800357d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035832`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035965`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035992`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035a53`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180035888`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180035888`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800356a6`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800356a6`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180035852`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180035852`
- `api-ms-win-core-processenvironment-l1-1-0!SetCurrentDirectoryW` at `0x1800356d5`
- `api-ms-win-core-processenvironment-l1-1-0!SetCurrentDirectoryW` at `0x180035988`
- `api-ms-win-core-processenvironment-l1-1-0!SetCurrentDirectoryW` at `0x1800356d5`
- `api-ms-win-core-processenvironment-l1-1-0!SetCurrentDirectoryW` at `0x180035988`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x180035958`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x180035958`
- `ntdll!RtlAllocateHeap` at `0x180035a9b`
- `ntdll!RtlAllocateHeap` at `0x180035a9b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800357c8`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180035828`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800357c8`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180035828`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x180035c0a`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x180035c0a`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x180035c4f`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x180035c4f`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180035bd8`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180035bd8`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180035a49`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180035a49`

## pseudocode

```c
__int64 __fastcall _DbgpControlTracing(struct _DBG_TRACE_CONTROL_BLOCK *a1, int a2, int a3)
{
  ULONG64 *v6; // r13
  PEVENT_TRACE_PROPERTIES *v7; // rsi
  int v8; // r15d
  int v9; // edx
  DWORD LastError; // ebx
  unsigned int v11; // ebx
  UINT WindowsDirectoryW; // eax
  PEVENT_TRACE_PROPERTIES v14; // r9
  ULONG LogFileMode; // r8d
  unsigned int v17; // edx
  __int64 v18; // rbx
  DWORD CurrentDirectoryW; // eax
  __int64 v20; // rbx
  WCHAR *v21; // r13
  unsigned int v22; // r14d
  LPCWSTR *v23; // r14
  struct _EVENT_TRACE_PROPERTIES *Heap; // rax
  char *v25; // rbx
  PEVENT_TRACE_PROPERTIES v26; // rax
  wchar_t *v27; // rbx
  PEVENT_TRACE_PROPERTIES v28; // rcx
  ULONG v29; // eax
  UCHAR v30; // r9
  TRACEHANDLE v31; // rcx
  ULONGLONG MatchAnyKeyword; // [rsp+20h] [rbp-E0h]
  DWORD nSize; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v34; // [rsp+88h] [rbp-78h]
  struct _ENABLE_TRACE_PARAMETERS EnableParameters; // [rsp+90h] [rbp-70h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v37; // [rsp+1D4h] [rbp+D4h]
  unsigned __int16 v38; // [rsp+1D6h] [rbp+D6h]
  unsigned __int16 v39; // [rsp+1D8h] [rbp+D8h]
  unsigned __int8 v40; // [rsp+1DAh] [rbp+DAh]
  wchar_t Destination[264]; // [rsp+1E0h] [rbp+E0h] BYREF
  WCHAR Buffer[264]; // [rsp+3F0h] [rbp+2F0h] BYREF
  WCHAR PathName[264]; // [rsp+600h] [rbp+500h] BYREF
  WCHAR v44[264]; // [rsp+810h] [rbp+710h] BYREF
  WCHAR NewFileName[264]; // [rsp+A20h] [rbp+920h] BYREF
  WCHAR ExistingFileName[264]; // [rsp+C30h] [rbp+B30h] BYREF
  unsigned __int16 v47[264]; // [rsp+E40h] [rbp+D40h] BYREF

  nSize = 0;
  memset_0(&VersionInformation, 0, 0x11Cu);
  memset_0(PathName, 0, 0x208u);
  v6 = (ULONG64 *)((char *)a1 + 72);
  v7 = (PEVENT_TRACE_PROPERTIES *)((char *)a1 + 88);
  memset(&EnableParameters, 0, sizeof(EnableParameters));
  if ( !*((_QWORD *)a1 + 9) || (v8 = 1, !*v7) )
    v8 = 0;
  v9 = a2 & 0xFFFFFFF;
  if ( a3 )
  {
    LastError = 0;
    *((_DWORD *)a1 + 27) = v9;
    if ( !v9 )
      goto LABEL_10;
  }
  else
  {
    LastError = 0;
    if ( v9 == *((_DWORD *)a1 + 27) )
    {
      if ( !v8 )
        goto LABEL_10;
      v14 = *v7;
      LogFileMode = (*v7)->LogFileMode;
      if ( (a2 >= 0 == ((LogFileMode & 0x80000) == 0) || !*((_BYTE *)DbgpGlobalControllerHeader + 56))
        && ((a2 & 0x40000000) == 0) == ((LogFileMode & 0x100) == 0)
        && ((a2 & 0x40000000) != 0 ? *((_DWORD *)a1 + 8) == v14->FlushTimer : v14->FlushTimer == 0) )
      {
        goto LABEL_10;
      }
    }
    *((_DWORD *)a1 + 27) = v9;
    if ( !v9 )
    {
      if ( v8 )
        goto LABEL_24;
      goto LABEL_7;
    }
  }
  if ( v8 )
  {
LABEL_49:
    Destination[0] = 0;
    goto LABEL_50;
  }
LABEL_7:
  if ( (a2 & 0x20000000) != 0 )
    goto LABEL_49;
  v11 = (*((unsigned __int16 *)a1 + 28) >> 1) + 10;
  WindowsDirectoryW = GetWindowsDirectoryW(Buffer, 260 - v11);
  nSize = WindowsDirectoryW;
  if ( !WindowsDirectoryW )
  {
LABEL_9:
    LastError = GetLastError();
    goto LABEL_10;
  }
  if ( WindowsDirectoryW > 260 - (unsigned __int64)v11 )
  {
    LastError = 122;
    goto LABEL_10;
  }
  wcscat_s(Buffer, 0x104u, L"\\tracing");
  if ( !CreateDirectoryW(Buffer, 0) )
  {
    LastError = GetLastError();
    if ( LastError != 183 )
      goto LABEL_10;
  }
  wcscat_s(Buffer, 0x103u, L"\\");
  wcscat_s(Buffer, 0x103u, *((const wchar_t **)a1 + 8));
  Buffer[259] = 0;
  if ( !CreateDirectoryW(Buffer, 0) )
  {
    LastError = GetLastError();
    if ( LastError != 183 )
      goto LABEL_10;
  }
  VersionInformation.dwOSVersionInfoSize = 284;
  if ( !GetVersionExW(&VersionInformation) )
    goto LABEL_9;
  _DbgpGetFileVersionString(*((LPCWSTR *)a1 + 6), v17, v47);
  nSize = 259;
  v44[259] = 0;
  if ( !GetComputerNameExW(ComputerNameNetBIOS, v44, &nSize) )
    goto LABEL_9;
  Destination[259] = 0;
  snwprintf_s(
    Destination,
    0x103u,
    0xFFu,
    L"%s_%wZ_%d_%d_%d_%d_%d_%d_%s_%x_%s",
    v44,
    (char *)a1 + 56,
    v40,
    VersionInformation.dwMajorVersion,
    VersionInformation.dwMinorVersion,
    VersionInformation.dwBuildNumber,
    v37,
    v38,
    VersionInformation.szCSDVersion,
    v39,
    v47);
  wcscat_s(Destination, 0x103u, L".etl");
  v18 = -1;
  do
    ++v18;
  while ( Destination[v18] );
  CurrentDirectoryW = GetCurrentDirectoryW(0x103u, PathName);
  if ( !CurrentDirectoryW )
    return GetLastError();
  if ( CurrentDirectoryW >= 0x103 )
    return 122;
  if ( !SetCurrentDirectoryW(Buffer) )
    goto LABEL_9;
  v20 = (unsigned int)(v18 - 4);
  v34 = &NewFileName[v20];
  v21 = &ExistingFileName[v20];
  memcpy_0(ExistingFileName, Destination, v20 * 2);
  memcpy_0(NewFileName, Destination, v20 * 2);
  v22 = 10;
  while ( v22 )
  {
    _DbgpSetExt(v22, v34);
    if ( v22 == 1 )
    {
      *(_QWORD *)v21 = *(_QWORD *)L".etl";
      v21[4] = aEtl[4];
    }
    else
    {
      _DbgpSetExt(v22 - 1, v21);
    }
    --v22;
    if ( !MoveFileExW(ExistingFileName, NewFileName, 1u) )
    {
      LastError = GetLastError();
      if ( LastError != 2 )
        goto LABEL_10;
    }
  }
  v6 = (ULONG64 *)((char *)a1 + 72);
LABEL_50:
  v23 = (LPCWSTR *)((char *)a1 + 64);
  if ( !v8 )
  {
    *((_DWORD *)a1 + 20) = 1160;
    Heap = (struct _EVENT_TRACE_PROPERTIES *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x488u);
    *v7 = Heap;
    if ( !Heap )
    {
      LastError = 14;
      goto LABEL_10;
    }
    memset_0(Heap, 0, *((unsigned int *)a1 + 20));
    (*v7)->Wnode.BufferSize = *((_DWORD *)a1 + 20);
    (*v7)->Wnode.Flags = 0x20000;
    (*v7)->LoggerNameOffset = 120;
    v25 = (char *)*v7 + (*v7)->LoggerNameOffset;
    o_wcsncpy_s_0(v25, 260, *v23);
    *((_WORD *)v25 + 259) = 0;
    v26 = *v7;
    if ( Destination[0] )
    {
      v26->MaximumFileSize = 1;
      (*v7)->LogFileNameOffset = 640;
      v27 = (wchar_t *)((char *)*v7 + (*v7)->LogFileNameOffset);
      snwprintf_s(v27, 0x103u, 0x103u, L"%s\\%s", Buffer, Destination);
      v27[259] = 0;
      (*v7)->LogFileMode |= 0x4002u;
    }
    else
    {
      v26->LogFileMode |= 0x8400u;
    }
  }
  if ( a2 < 0 && *((_BYTE *)DbgpGlobalControllerHeader + 56) )
    (*v7)->LogFileMode |= 0x80000u;
  else
    (*v7)->LogFileMode &= ~0x80000u;
  v28 = *v7;
  v29 = (*v7)->LogFileMode;
  if ( (a2 & 0x40000000) != 0 )
  {
    v28->LogFileMode = v29 | 0x100;
    (*v7)->FlushTimer = *((_DWORD *)a1 + 8);
  }
  else
  {
    v28->LogFileMode = v29 & 0xFFFFFEFF;
    (*v7)->FlushTimer = 0;
  }
  if ( !v8 )
  {
    LastError = ControlTraceW(0, *v23, *v7, 0);
    if ( LastError != 4201 || ((*v7)->EnableFlags = *((_DWORD *)a1 + 27), (LastError = StartTraceW(v6, *v23, *v7)) != 0) )
    {
LABEL_24:
      _DbgpStopTracing(a1);
      goto LABEL_10;
    }
  }
  v30 = *((_BYTE *)a1 + 104);
  v31 = *v6;
  MatchAnyKeyword = *((unsigned int *)a1 + 27);
  EnableParameters.Version = 1;
  LastError = EnableTraceEx2(v31, (LPCGUID)a1 + 7, 1u, v30, MatchAnyKeyword, 0, 0, &EnableParameters);
  if ( LastError )
  {
    if ( !v8 )
      goto LABEL_24;
  }
  else
  {
    LastError = 0;
  }
LABEL_10:
  if ( PathName[0] )
    SetCurrentDirectoryW(PathName);
  return LastError;
}

```

## disassembly

```asm
0x1800355cc  push    rbp
0x1800355ce  push    rbx
0x1800355cf  push    rsi
0x1800355d0  push    rdi
0x1800355d1  push    r12
0x1800355d3  push    r13
0x1800355d5  push    r14
0x1800355d7  push    r15
0x1800355d9  lea     rbp, [rsp-0F68h]
0x1800355e1  mov     eax, 1068h
0x1800355e6  call    _alloca_probe
0x1800355eb  sub     rsp, rax
0x1800355ee  mov     rax, cs:__security_cookie
0x1800355f5  xor     rax, rsp
0x1800355f8  mov     [rbp+0FA0h+var_50], rax
0x1800355ff  mov     ebx, r8d
0x180035602  mov     r12d, edx
0x180035605  mov     rdi, rcx
0x180035608  xor     r14d, r14d
0x18003560b  xor     edx, edx; Val
0x18003560d  mov     [rbp+0FA0h+nSize], r14d
0x180035611  mov     r8d, 11Ch; Size
0x180035617  lea     rcx, [rbp+0FA0h+VersionInformation]; void *
0x18003561b  call    memset_0
0x180035620  xor     edx, edx; Val
0x180035622  lea     rcx, [rbp+0FA0h+PathName]; void *
0x180035629  mov     r8d, 208h; Size
0x18003562f  call    memset_0
0x180035634  xorps   xmm0, xmm0
0x180035637  lea     r13, [rdi+48h]
0x18003563b  lea     rsi, [rdi+58h]
0x18003563f  movups  xmmword ptr [rbp+0FA0h+var_1010.Version], xmm0
0x180035643  movups  xmmword ptr [rbp+0FA0h+var_1010.SourceId.Data2], xmm0
0x180035647  movups  xmmword ptr [rbp+0FA0h+var_1010.EnableFilterDesc], xmm0
0x18003564b  cmp     [r13+0], r14
0x18003564f  jz      short loc_18003565A
0x180035651  lea     r15d, [r14+1]
0x180035655  cmp     [rsi], r14
0x180035658  jnz     short loc_18003565D
0x18003565a  mov     r15d, r14d
0x18003565d  mov     edx, r12d
0x180035660  and     edx, 0FFFFFFFh
0x180035666  test    ebx, ebx
0x180035668  jz      loc_180035700
0x18003566e  xor     ebx, ebx
0x180035670  mov     [rdi+6Ch], edx
0x180035673  test    edx, edx
0x180035675  jz      short loc_1800356C4
0x180035677  test    r15d, r15d
0x18003567a  jnz     loc_180035A6E
0x180035680  bt      r12d, 1Dh
0x180035685  jb      loc_180035A6E
0x18003568b  mov     edx, 104h
0x180035690  lea     r14, [rdi+38h]
0x180035694  movzx   ebx, word ptr [r14]
0x180035698  lea     rcx, [rbp+0FA0h+Buffer]; lpBuffer
0x18003569f  shr     ebx, 1
0x1800356a1  add     ebx, 0Ah
0x1800356a4  sub     edx, ebx; uSize
0x1800356a6  call    cs:__imp_GetWindowsDirectoryW
0x1800356ac  mov     edx, eax
0x1800356ae  mov     [rbp+0FA0h+nSize], edx
0x1800356b1  test    eax, eax
0x1800356b3  jnz     loc_18003578C
0x1800356b9  call    cs:__imp_GetLastError
0x1800356bf  mov     ebx, eax
0x1800356c1  xor     r14d, r14d
0x1800356c4  cmp     [rbp+0FA0h+PathName], r14w
0x1800356cc  jz      short loc_1800356DB
0x1800356ce  lea     rcx, [rbp+0FA0h+PathName]; lpPathName
0x1800356d5  call    cs:__imp_SetCurrentDirectoryW
0x1800356db  mov     eax, ebx
0x1800356dd  mov     rcx, [rbp+0FA0h+var_50]
0x1800356e4  xor     rcx, rsp; StackCookie
0x1800356e7  call    __security_check_cookie
0x1800356ec  add     rsp, 1068h
0x1800356f3  pop     r15
0x1800356f5  pop     r14
0x1800356f7  pop     r13
0x1800356f9  pop     r12
0x1800356fb  pop     rdi
0x1800356fc  pop     rsi
0x1800356fd  pop     rbx
0x1800356fe  pop     rbp
0x1800356ff  retn
0x180035700  xor     ebx, ebx
0x180035702  cmp     edx, [rdi+6Ch]
0x180035705  jnz     short loc_18003576B
0x180035707  test    r15d, r15d
0x18003570a  jz      short loc_1800356C4
0x18003570c  mov     r9, [rsi]
0x18003570f  mov     eax, r12d
0x180035712  not     eax
0x180035714  shr     eax, 1Fh
0x180035717  mov     r8d, [r9+40h]
0x18003571b  mov     ecx, r8d
0x18003571e  shr     ecx, 13h
0x180035721  not     ecx
0x180035723  and     ecx, 1
0x180035726  cmp     al, cl
0x180035728  jz      short loc_180035736
0x18003572a  mov     rax, cs:?DbgpGlobalControllerHeader@@3PEAU_DBG_TCB_HEADER@@EA; _DBG_TCB_HEADER * DbgpGlobalControllerHeader
0x180035731  cmp     [rax+38h], bl
0x180035734  jnz     short loc_18003576B
0x180035736  shr     r8d, 8
0x18003573a  mov     eax, ebx
0x18003573c  not     r8d
0x18003573f  mov     ecx, r12d
0x180035742  and     r8d, 1
0x180035746  and     ecx, 40000000h
0x18003574c  setz    al
0x18003574f  cmp     eax, r8d
0x180035752  jnz     short loc_18003576B
0x180035754  test    ecx, ecx
0x180035756  jz      short loc_180035761
0x180035758  mov     eax, [r9+44h]
0x18003575c  cmp     [rdi+20h], eax
0x18003575f  jmp     short loc_180035765
0x180035761  cmp     [r9+44h], ebx
0x180035765  jz      loc_1800356C4
0x18003576b  mov     [rdi+6Ch], edx
0x18003576e  test    edx, edx
0x180035770  jnz     loc_180035677
0x180035776  test    r15d, r15d
0x180035779  jz      loc_180035680
0x18003577f  mov     rcx, rdi; struct _DBG_TRACE_CONTROL_BLOCK *
0x180035782  call    ?_DbgpStopTracing@@YAXPEAU_DBG_TRACE_CONTROL_BLOCK@@@Z; _DbgpStopTracing(_DBG_TRACE_CONTROL_BLOCK *)
0x180035787  jmp     loc_1800356C4
0x18003578c  mov     r9d, 104h
0x180035792  mov     eax, ebx
0x180035794  mov     ecx, r9d
0x180035797  sub     rcx, rax
0x18003579a  cmp     rdx, rcx
0x18003579d  jbe     short loc_1800357A9
0x18003579f  mov     ebx, 7Ah ; 'z'
0x1800357a4  jmp     loc_1800356C1
0x1800357a9  lea     r8, aTracing; "\\tracing"
0x1800357b0  mov     rdx, r9; SizeInWords
0x1800357b3  lea     rcx, [rbp+0FA0h+Buffer]; Destination
0x1800357ba  call    wcscat_s
0x1800357bf  xor     edx, edx; lpSecurityAttributes
0x1800357c1  lea     rcx, [rbp+0FA0h+Buffer]; lpPathName
0x1800357c8  call    cs:__imp_CreateDirectoryW
0x1800357ce  xor     ebx, ebx
0x1800357d0  test    eax, eax
0x1800357d2  jnz     short loc_1800357E9
0x1800357d4  call    cs:__imp_GetLastError
0x1800357da  mov     ebx, eax
0x1800357dc  cmp     eax, 0B7h
0x1800357e1  jnz     loc_1800356C1
0x1800357e7  xor     ebx, ebx
0x1800357e9  mov     r13d, 103h
0x1800357ef  lea     r8, asc_18003BA30; "\\"
0x1800357f6  mov     edx, r13d; SizeInWords
0x1800357f9  lea     rcx, [rbp+0FA0h+Buffer]; Destination
0x180035800  call    wcscat_s
0x180035805  mov     r8, [rdi+40h]; Source
0x180035809  lea     rcx, [rbp+0FA0h+Buffer]; Destination
0x180035810  mov     edx, r13d; SizeInWords
0x180035813  call    wcscat_s
0x180035818  xor     edx, edx; lpSecurityAttributes
0x18003581a  mov     [rbp+0FA0h+var_AAA], bx
0x180035821  lea     rcx, [rbp+0FA0h+Buffer]; lpPathName
0x180035828  call    cs:__imp_CreateDirectoryW
0x18003582e  test    eax, eax
0x180035830  jnz     short loc_180035847
0x180035832  call    cs:__imp_GetLastError
0x180035838  mov     ebx, eax
0x18003583a  cmp     eax, 0B7h
0x18003583f  jnz     loc_1800356C1
0x180035845  xor     ebx, ebx
0x180035847  lea     rcx, [rbp+0FA0h+VersionInformation]; lpVersionInformation
0x18003584b  mov     [rbp+0FA0h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x180035852  call    cs:__imp_GetVersionExW
0x180035858  test    eax, eax
0x18003585a  jz      loc_1800356B9
0x180035860  mov     rcx, [rdi+30h]; lpwstrFilename
0x180035864  lea     r8, [rbp+0FA0h+var_260]; unsigned __int16 *
0x18003586b  call    ?_DbgpGetFileVersionString@@YAHPEAGK0@Z; _DbgpGetFileVersionString(ushort *,ulong,ushort *)
0x180035870  lea     r8, [rbp+0FA0h+nSize]; nSize
0x180035874  mov     [rbp+0FA0h+nSize], r13d
0x180035878  lea     rdx, [rbp+0FA0h+var_890]; lpBuffer
0x18003587f  mov     [rbp+0FA0h+var_68A], bx
0x180035886  xor     ecx, ecx; NameType
0x180035888  call    cs:__imp_GetComputerNameExW
0x18003588e  test    eax, eax
0x180035890  jz      loc_1800356B9
0x180035896  movzx   eax, [rbp+0FA0h+var_EC8]
0x18003589d  lea     r9, [rbp+0FA0h+var_260]
0x1800358a4  movzx   ecx, [rbp+0FA0h+var_ECA]
0x1800358ab  movzx   edx, [rbp+0FA0h+var_ECC]
0x1800358b2  movzx   r8d, [rbp+0FA0h+var_EC6]
0x1800358ba  mov     [rsp+10A0h+var_1030], r9
0x1800358bf  lea     r9, aSWzDDDDDDSXS; "%s_%wZ_%d_%d_%d_%d_%d_%d_%s_%x_%s"
0x1800358c6  mov     [rsp+10A0h+var_1038], eax
0x1800358ca  lea     rax, [rbp+0FA0h+VersionInformation.szCSDVersion]
0x1800358ce  mov     [rsp+10A0h+var_1040], rax
0x1800358d3  mov     eax, [rbp+0FA0h+VersionInformation.dwBuildNumber]
0x1800358d6  mov     [rsp+10A0h+var_1048], ecx
0x1800358da  lea     rcx, [rbp+0FA0h+Destination]; Buffer
0x1800358e1  mov     [rsp+10A0h+var_1050], edx
0x1800358e5  mov     rdx, r13; BufferCount
0x1800358e8  mov     [rsp+10A0h+var_1058], eax
0x1800358ec  mov     eax, [rbp+0FA0h+VersionInformation.dwMinorVersion]
0x1800358ef  mov     [rsp+10A0h+var_1060], eax
0x1800358f3  mov     eax, [rbp+0FA0h+VersionInformation.dwMajorVersion]
0x1800358f6  mov     dword ptr [rsp+10A0h+EnableParameters], eax
0x1800358fa  lea     rax, [rbp+0FA0h+var_890]
0x180035901  mov     [rsp+10A0h+Timeout], r8d
0x180035906  mov     r8d, 0FFh; MaxCount
0x18003590c  mov     [rsp+10A0h+MatchAllKeyword], r14
0x180035911  mov     [rsp+10A0h+MatchAnyKeyword], rax
0x180035916  mov     [rbp+0FA0h+var_CBA], bx
0x18003591d  call    _snwprintf_s
0x180035922  lea     r8, aEtl; ".etl"
0x180035929  mov     rdx, r13; SizeInWords
0x18003592c  lea     rcx, [rbp+0FA0h+Destination]; Destination
0x180035933  call    wcscat_s
0x180035938  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003593c  lea     rcx, [rbp+0FA0h+Destination]
0x180035943  xor     eax, eax
0x180035945  inc     rbx
0x180035948  cmp     [rcx+rbx*2], ax
0x18003594c  jnz     short loc_180035945
0x18003594e  lea     rdx, [rbp+0FA0h+PathName]; lpBuffer
0x180035955  mov     ecx, r13d; nBufferLength
0x180035958  call    cs:__imp_GetCurrentDirectoryW
0x18003595e  xor     r14d, r14d
0x180035961  test    eax, eax
0x180035963  jnz     short loc_180035972
0x180035965  call    cs:__imp_GetLastError
0x18003596b  mov     ebx, eax
0x18003596d  jmp     loc_1800356DB
0x180035972  cmp     eax, r13d
0x180035975  jb      short loc_180035981
0x180035977  mov     ebx, 7Ah ; 'z'
0x18003597c  jmp     loc_1800356DB
0x180035981  lea     rcx, [rbp+0FA0h+Buffer]; lpPathName
0x180035988  call    cs:__imp_SetCurrentDirectoryW
0x18003598e  test    eax, eax
0x180035990  jnz     short loc_18003599F
0x180035992  call    cs:__imp_GetLastError
0x180035998  mov     ebx, eax
0x18003599a  jmp     loc_1800356C4
0x18003599f  lea     eax, [rbx-4]
0x1800359a2  lea     rbx, [rax+rax]
0x1800359a6  lea     rax, [rbp+0FA0h+NewFileName]
0x1800359ad  mov     r8, rbx; Size
0x1800359b0  add     rax, rbx
0x1800359b3  lea     r13, [rbp+0FA0h+ExistingFileName]
0x1800359ba  lea     rdx, [rbp+0FA0h+Destination]; Src
0x1800359c1  mov     [rbp+0FA0h+var_1018], rax
0x1800359c5  lea     rcx, [rbp+0FA0h+ExistingFileName]; void *
0x1800359cc  add     r13, rbx
0x1800359cf  call    memcpy_0
0x1800359d4  mov     r8, rbx; Size
0x1800359d7  lea     rdx, [rbp+0FA0h+Destination]; Src
0x1800359de  lea     rcx, [rbp+0FA0h+NewFileName]; void *
0x1800359e5  call    memcpy_0
0x1800359ea  mov     r14d, 0Ah
0x1800359f0  cmp     r14d, 1
0x1800359f4  jb      short loc_180035A66
0x1800359f6  mov     rdx, [rbp+0FA0h+var_1018]; unsigned __int16 *
0x1800359fa  mov     ecx, r14d; unsigned int
0x1800359fd  call    ?_DbgpSetExt@@YAXKPEAG@Z; _DbgpSetExt(ulong,ushort *)
0x180035a02  lea     ebx, [r14-1]
0x180035a06  cmp     r14d, 1
0x180035a0a  jnz     short loc_180035A28
0x180035a0c  movsd   xmm0, qword ptr cs:aEtl; ".etl"
0x180035a14  movzx   eax, word ptr cs:aEtl+8; ""
0x180035a1b  movsd   qword ptr [r13+0], xmm0
0x180035a21  mov     [r13+8], ax
0x180035a26  jmp     short loc_180035A32
0x180035a28  mov     rdx, r13; unsigned __int16 *
0x180035a2b  mov     ecx, ebx; unsigned int
0x180035a2d  call    ?_DbgpSetExt@@YAXKPEAG@Z; _DbgpSetExt(ulong,ushort *)
0x180035a32  mov     r8d, 1; dwFlags
0x180035a38  lea     rdx, [rbp+0FA0h+NewFileName]; lpNewFileName
0x180035a3f  lea     rcx, [rbp+0FA0h+ExistingFileName]; lpExistingFileName
0x180035a46  mov     r14d, ebx
0x180035a49  call    cs:__imp_MoveFileExW
0x180035a4f  test    eax, eax
0x180035a51  jnz     short loc_1800359F0
0x180035a53  call    cs:__imp_GetLastError
0x180035a59  mov     ebx, eax
0x180035a5b  cmp     eax, 2
0x180035a5e  jnz     loc_1800356C1
0x180035a64  jmp     short loc_1800359F0
0x180035a66  lea     r13, [rdi+48h]
0x180035a6a  xor     ebx, ebx
0x180035a6c  jmp     short loc_180035A75
0x180035a6e  mov     [rbp+0FA0h+Destination], bx
0x180035a75  lea     r14, [rdi+40h]
0x180035a79  test    r15d, r15d
0x180035a7c  jnz     loc_180035B79
0x180035a82  mov     r8d, 488h; Size
0x180035a88  xor     edx, edx; Flags
0x180035a8a  mov     [rdi+50h], r8d
0x180035a8e  mov     rcx, gs:60h
0x180035a97  mov     rcx, [rcx+30h]; HeapHandle
  ... truncated ...
```
