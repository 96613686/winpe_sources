# DockedUIEOrch::GetSRRUMHistoryForProvider(ulong,_SRU_PROVIDER_CLASS,ulong *,_SYSTEMTIME * *)

- ea: `0x18003c028`
- end: `0x18003c236`
- name: `?GetSRRUMHistoryForProvider@DockedUIEOrch@@AEAAJKW4_SRU_PROVIDER_CLASS@@PEAKPEAPEAU_SYSTEMTIME@@@Z`
- size: `526`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18003c240`
- `0x18003c290`

## callees

- `0x180007660`
- `0x1800183d4`
- `0x1800183f4`
- `0x180037440`
- `0x18003c028`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003c179`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003c179`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18003c092`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18003c092`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18003c0b1`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18003c0b1`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18003c111`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18003c111`
- `SrumAPI!SruQueryStats` at `0x18003c141`
- `SrumAPI!SruQueryStats` at `0x18003c141`
- `SrumAPI!SruFreeRecordSet` at `0x18003c1dd`
- `SrumAPI!SruFreeRecordSet` at `0x18003c20d`
- `SrumAPI!SruFreeRecordSet` at `0x18003c1dd`
- `SrumAPI!SruFreeRecordSet` at `0x18003c20d`

## string_xrefs

- `0x18003c064`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockeduieorch.cpp`
- `0x18003c0c2`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockeduieorch.cpp`
- `0x18003c14f`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockeduieorch.cpp`
- `0x18003c1eb`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockeduieorch.cpp`

## pseudocode

```c
__int64 __fastcall DockedUIEOrch::GetSRRUMHistoryForProvider(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int *a4,
        char **a5)
{
  __int64 v6; // rdi
  __int64 v8; // rdx
  unsigned int v9; // ebx
  const char *v10; // r9
  __int64 v11; // rdx
  __int64 v13; // rax
  unsigned int v14; // eax
  unsigned int v15; // edi
  SIZE_T v16; // rbx
  char *v17; // rax
  char *i; // rcx
  unsigned int j; // r10d
  unsigned __int64 v20; // r8
  __int64 v21; // r9
  unsigned int *v22; // rcx
  int v23; // [rsp+20h] [rbp-50h]
  struct _FILETIME FileTime; // [rsp+30h] [rbp-40h] BYREF
  unsigned int v25[2]; // [rsp+38h] [rbp-38h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+40h] [rbp-30h] BYREF
  SYSTEMTIME v27; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  v6 = a2;
  if ( !a4 )
  {
    v8 = 68;
LABEL_3:
    v9 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockeduieorch.cpp",
      (const char *)0x80004003LL,
      v23);
    return v9;
  }
  if ( !a5 )
  {
    v8 = 69;
    goto LABEL_3;
  }
  SystemTime = 0;
  GetSystemTime(&SystemTime);
  v27 = SystemTime;
  FileTime = 0;
  if ( !SystemTimeToFileTime(&v27, &FileTime) )
  {
    v11 = 78;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v11,
             (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockeduieorch.cpp",
             v10);
  }
  v13 = -864000000000LL * v6 + *(_QWORD *)&FileTime;
  FileTime.dwLowDateTime += -711573504 * v6;
  FileTime.dwHighDateTime = HIDWORD(v13);
  if ( !FileTimeToSystemTime(&FileTime, &v27) )
  {
    v11 = 81;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v11,
             (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockeduieorch.cpp",
             v10);
  }
  *(_QWORD *)v25 = 0;
  v14 = SruQueryStats(a3, &v27, &SystemTime, 2);
  if ( v14 )
  {
    v9 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x54,
           (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockeduieorch.cpp",
           (const char *)v14,
           (unsigned int)v25);
    goto LABEL_22;
  }
  v15 = **(_DWORD **)v25;
  v16 = 16LL * (unsigned int)**(_DWORD **)v25;
  v17 = (char *)CoTaskMemAlloc(v16);
  if ( !v17 )
  {
    v9 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x58,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockeduieorch.cpp",
      (const char *)0x8007000ELL,
      (int)v25);
LABEL_22:
    if ( *(_QWORD *)v25 )
      SruFreeRecordSet();
    return v9;
  }
  for ( i = v17; i != &v17[v16]; i += 16 )
    *(_OWORD *)i = 0;
  for ( j = 0; j < v15; *(_OWORD *)&v17[16 * v21] = *(_OWORD *)(v20 + *(_QWORD *)(*(_QWORD *)v25 + 8LL)) )
  {
    v20 = (unsigned __int64)j << 6;
    v21 = j++;
  }
  v22 = *(unsigned int **)v25;
  *a4 = v15;
  *a5 = v17;
  if ( v22 )
    SruFreeRecordSet();
  return 0;
}

```

## disassembly

```asm
0x18003c028  mov     [rsp-18h+arg_0], rbx
0x18003c02d  mov     [rsp-18h+arg_8], rsi
0x18003c032  push    rbp
0x18003c033  push    rdi
0x18003c034  push    r14
0x18003c036  mov     rbp, rsp
0x18003c039  sub     rsp, 70h
0x18003c03d  mov     rax, cs:__security_cookie
0x18003c044  xor     rax, rsp
0x18003c047  mov     [rbp+var_10], rax
0x18003c04b  mov     rsi, [rbp+arg_20]
0x18003c04f  mov     r14, r9
0x18003c052  mov     edi, edx
0x18003c054  mov     ebx, r8d
0x18003c057  test    r9, r9
0x18003c05a  jnz     short loc_18003C07D
0x18003c05c  lea     edx, [r9+44h]; void *
0x18003c060  mov     rcx, [rbp+18h]; this
0x18003c064  lea     r8, aOnecoreEnduser_30; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18003c06b  mov     ebx, 80004003h
0x18003c070  mov     r9d, ebx; char *
0x18003c073  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c078  jmp     loc_18003C213
0x18003c07d  test    rsi, rsi
0x18003c080  jnz     short loc_18003C087
0x18003c082  lea     edx, [rsi+45h]
0x18003c085  jmp     short loc_18003C060
0x18003c087  xorps   xmm0, xmm0
0x18003c08a  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x18003c08e  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x18003c092  call    cs:__imp_GetSystemTime
0x18003c098  movaps  xmm0, xmmword ptr [rbp+SystemTime.wYear]
0x18003c09c  lea     rdx, [rbp+FileTime]; lpFileTime
0x18003c0a0  lea     rcx, [rbp+var_20]; lpSystemTime
0x18003c0a4  movdqa  xmmword ptr [rbp+var_20.wYear], xmm0
0x18003c0a9  mov     qword ptr [rbp+FileTime.dwLowDateTime], 0
0x18003c0b1  call    cs:__imp_SystemTimeToFileTime
0x18003c0b7  test    eax, eax
0x18003c0b9  jnz     short loc_18003C0D3
0x18003c0bb  lea     edx, [rax+4Eh]; void *
0x18003c0be  mov     rcx, [rbp+18h]; this
0x18003c0c2  lea     r8, aOnecoreEnduser_30; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18003c0c9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003c0ce  jmp     loc_18003C215
0x18003c0d3  mov     eax, [rbp+FileTime.dwLowDateTime]
0x18003c0d6  lea     rdx, [rbp+var_20]; lpSystemTime
0x18003c0da  mov     ecx, [rbp+FileTime.dwHighDateTime]
0x18003c0dd  mov     [rbp+FileTime.dwLowDateTime], eax
0x18003c0e0  mov     rax, 0FFFFFF36D5964000h
0x18003c0ea  mov     [rbp+FileTime.dwHighDateTime], ecx
0x18003c0ed  mov     rcx, rdi
0x18003c0f0  imul    rcx, rax
0x18003c0f4  mov     rax, qword ptr [rbp+FileTime.dwLowDateTime]
0x18003c0f8  add     rax, rcx
0x18003c0fb  lea     rcx, [rbp+FileTime]; lpFileTime
0x18003c0ff  mov     [rbp+FileTime.dwLowDateTime], eax
0x18003c102  shr     rax, 20h
0x18003c106  mov     [rbp+FileTime.dwHighDateTime], eax
0x18003c109  mov     rax, qword ptr [rbp+FileTime.dwLowDateTime]
0x18003c10d  mov     qword ptr [rbp+FileTime.dwLowDateTime], rax
0x18003c111  call    cs:__imp_FileTimeToSystemTime
0x18003c117  test    eax, eax
0x18003c119  jnz     short loc_18003C120
0x18003c11b  lea     edx, [rax+51h]
0x18003c11e  jmp     short loc_18003C0BE
0x18003c120  lea     rax, [rbp+var_38]
0x18003c124  mov     qword ptr [rbp+var_38], 0
0x18003c12c  mov     r9d, 2
0x18003c132  mov     qword ptr [rsp+70h+var_50], rax; int
0x18003c137  lea     r8, [rbp+SystemTime]
0x18003c13b  mov     ecx, ebx
0x18003c13d  lea     rdx, [rbp+var_20]
0x18003c141  call    cs:__imp_SruQueryStats
0x18003c147  test    eax, eax
0x18003c149  jz      short loc_18003C16A
0x18003c14b  mov     rcx, [rbp+18h]; this
0x18003c14f  lea     r8, aOnecoreEnduser_30; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18003c156  mov     r9d, eax; char *
0x18003c159  mov     edx, 54h ; 'T'; void *
0x18003c15e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003c163  mov     ebx, eax
0x18003c165  jmp     loc_18003C204
0x18003c16a  mov     rax, qword ptr [rbp+var_38]
0x18003c16e  mov     edi, [rax]
0x18003c170  mov     ebx, edi
0x18003c172  shl     rbx, 4
0x18003c176  mov     rcx, rbx; cb
0x18003c179  call    cs:__imp_CoTaskMemAlloc
0x18003c17f  test    rax, rax
0x18003c182  jz      short loc_18003C1E7
0x18003c184  lea     rdx, [rbx+rax]
0x18003c188  mov     rcx, rax
0x18003c18b  cmp     rax, rdx
0x18003c18e  jz      short loc_18003C19F
0x18003c190  xorps   xmm0, xmm0
0x18003c193  movups  xmmword ptr [rcx], xmm0
0x18003c196  add     rcx, 10h
0x18003c19a  cmp     rcx, rdx
0x18003c19d  jnz     short loc_18003C190
0x18003c19f  xor     r10d, r10d
0x18003c1a2  test    edi, edi
0x18003c1a4  jz      short loc_18003C1CE
0x18003c1a6  mov     rcx, qword ptr [rbp+var_38]
0x18003c1aa  mov     r8d, r10d
0x18003c1ad  shl     r8, 6
0x18003c1b1  mov     r9d, r10d
0x18003c1b4  inc     r10d
0x18003c1b7  mov     rdx, [rcx+8]
0x18003c1bb  add     r9, r9
0x18003c1be  movups  xmm0, xmmword ptr [r8+rdx]
0x18003c1c3  movdqu  xmmword ptr [rax+r9*8], xmm0
0x18003c1c9  cmp     r10d, edi
0x18003c1cc  jb      short loc_18003C1A6
0x18003c1ce  mov     rcx, qword ptr [rbp+var_38]
0x18003c1d2  mov     [r14], edi
0x18003c1d5  mov     [rsi], rax
0x18003c1d8  test    rcx, rcx
0x18003c1db  jz      short loc_18003C1E3
0x18003c1dd  call    cs:__imp_SruFreeRecordSet
0x18003c1e3  xor     eax, eax
0x18003c1e5  jmp     short loc_18003C215
0x18003c1e7  mov     rcx, [rbp+18h]; this
0x18003c1eb  lea     r8, aOnecoreEnduser_30; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18003c1f2  mov     ebx, 8007000Eh
0x18003c1f7  mov     edx, 58h ; 'X'; void *
0x18003c1fc  mov     r9d, ebx; char *
0x18003c1ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c204  mov     rcx, qword ptr [rbp+var_38]
0x18003c208  test    rcx, rcx
0x18003c20b  jz      short loc_18003C213
0x18003c20d  call    cs:__imp_SruFreeRecordSet
0x18003c213  mov     eax, ebx
0x18003c215  mov     rcx, [rbp+var_10]
0x18003c219  xor     rcx, rsp; StackCookie
0x18003c21c  call    __security_check_cookie
0x18003c221  lea     r11, [rsp+70h+var_s0]
0x18003c226  mov     rbx, [r11+20h]
0x18003c22a  mov     rsi, [r11+28h]
0x18003c22e  mov     rsp, r11
0x18003c231  pop     r14
0x18003c233  pop     rdi
0x18003c234  pop     rbp
0x18003c235  retn
```
