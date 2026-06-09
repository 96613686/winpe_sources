# PersistenceManager::OpenMigrationMMF(ushort const *,ushort,WPN_MMF_HANDLE *)

- ea: `0x1800b7160`
- end: `0x1800b73d6`
- name: `?OpenMigrationMMF@PersistenceManager@@AEAAJPEBGGPEAUWPN_MMF_HANDLE@@@Z`
- size: `630`
- prototype: `int(PersistenceManager *__hidden this, const unsigned __int16 *, unsigned __int16, struct WPN_MMF_HANDLE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1800e58e0`

## callees

- `0x18002ee38`
- `0x1800a0b2c`
- `0x1800af0a4`
- `0x1800b7160`
- `0x1800e3cd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b71e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b7285`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b72ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b7347`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b71e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b7285`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b72ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b7347`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800b71d1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800b71d1`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800b7276`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800b7276`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800b7338`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800b7338`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800b72b8`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800b72b8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PersistenceManager::OpenMigrationMMF(
        PersistenceManager *this,
        const unsigned __int16 *a2,
        unsigned __int16 a3,
        struct WPN_MMF_HANDLE *a4)
{
  __int64 v5; // rdi
  HANDLE FileW; // rax
  void *v8; // rsi
  signed int LastError; // eax
  signed int v10; // ebx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  signed int v13; // eax
  HANDLE FileMappingW; // rax
  HANDLE v15; // r15
  signed int v16; // eax
  LPVOID v17; // rax
  signed int v18; // eax
  int dwCreationDisposition; // [rsp+20h] [rbp-40h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-40h]
  int dwCreationDispositionb; // [rsp+20h] [rbp-40h]
  __m128i si128; // [rsp+40h] [rbp-20h] BYREF
  LPVOID v24; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  __int64 FileInformation; // [rsp+90h] [rbp+30h] BYREF
  __int64 dwMaximumSizeHigh; // [rsp+98h] [rbp+38h]

  v5 = a3;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v24 = 0;
  FileInformation = 0;
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  FileW = CreateFileW(a2, 0xC0000000, 1u, 0, 4u, 0x80u, 0);
  v8 = FileW;
  si128.m128i_i64[0] = (__int64)FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    if ( v10 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xB9E,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\infra\\persistencemanager.cpp",
        (const char *)(unsigned int)v10,
        dwCreationDisposition);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v12 = 91;
LABEL_11:
      WPP_SF_d(v11[2], v12, WPP_ac3d69826ca03a16ae3e9918ed4e7821_Traceguids, (unsigned int)v10);
    }
  }
  else
  {
    v10 = 0;
    dwMaximumSizeHigh = 165104 * v5 + 32;
    FileInformation = dwMaximumSizeHigh;
    if ( !SetFileInformationByHandle(FileW, FileAllocationInfo, &FileInformation, 8u) )
    {
      v13 = GetLastError();
      v10 = v13;
      if ( v13 > 0 )
        v10 = (unsigned __int16)v13 | 0x80070000;
      if ( v10 < 0 )
        v10 = 0;
    }
    FileMappingW = CreateFileMappingW(v8, 0, 4u, HIDWORD(dwMaximumSizeHigh), 165104 * (int)v5 + 32, 0);
    v15 = FileMappingW;
    si128.m128i_i64[1] = (__int64)FileMappingW;
    if ( FileMappingW )
    {
      v17 = MapViewOfFile(FileMappingW, 2u, 0, 0, 0);
      v24 = v17;
      if ( v17 )
      {
        *(_QWORD *)a4 = v8;
        *((_QWORD *)a4 + 1) = v15;
        *((_QWORD *)a4 + 2) = v17;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        v24 = 0;
        goto LABEL_34;
      }
      v18 = GetLastError();
      v10 = v18;
      if ( v18 > 0 )
        v10 = (unsigned __int16)v18 | 0x80070000;
      if ( v10 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xBC6,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\infra\\persistencemanager.cpp",
          (const char *)(unsigned int)v10,
          dwCreationDispositionb);
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v12 = 94;
        goto LABEL_11;
      }
    }
    else
    {
      v16 = GetLastError();
      v10 = v16;
      if ( v16 > 0 )
        v10 = (unsigned __int16)v16 | 0x80070000;
      if ( v10 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xBBB,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\infra\\persistencemanager.cpp",
          (const char *)(unsigned int)v10,
          dwCreationDispositiona);
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v12 = 93;
        goto LABEL_11;
      }
    }
  }
LABEL_34:
  WPN_MMF_HANDLE::~WPN_MMF_HANDLE((WPN_MMF_HANDLE *)&si128);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800b7160  mov     [rsp-28h+arg_10], rbx
0x1800b7165  mov     [rsp-28h+FileInformation], rcx
0x1800b716a  push    rbp
0x1800b716b  push    rsi
0x1800b716c  push    rdi
0x1800b716d  push    r14
0x1800b716f  push    r15
0x1800b7171  mov     rbp, rsp
0x1800b7174  sub     rsp, 60h
0x1800b7178  mov     r14, r9
0x1800b717b  movzx   edi, r8w
0x1800b717f  mov     rbx, rdx
0x1800b7182  movdqa  xmm0, cs:__xmm@0000000000000000ffffffffffffffff
0x1800b718a  movdqu  [rbp+var_20], xmm0
0x1800b718f  mov     [rbp+var_10], 0
0x1800b7197  mov     [rbp+FileInformation], 0
0x1800b719f  test    rdx, rdx
0x1800b71a2  jnz     short loc_1800B71A9
0x1800b71a4  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "File != NULL")
0x1800b71a9  mov     [rsp+60h+hTemplateFile], 0; hTemplateFile
0x1800b71b2  mov     [rsp+60h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800b71ba  mov     [rsp+60h+dwCreationDisposition], 4; int
0x1800b71c2  xor     r9d, r9d; lpSecurityAttributes
0x1800b71c5  mov     edx, 0C0000000h; dwDesiredAccess
0x1800b71ca  lea     r8d, [r9+1]; dwShareMode
0x1800b71ce  mov     rcx, rbx; lpFileName
0x1800b71d1  call    cs:__imp_CreateFileW
0x1800b71d7  mov     rsi, rax
0x1800b71da  mov     qword ptr [rbp+var_20], rax
0x1800b71de  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800b71e2  jnz     short loc_1800B7253
0x1800b71e4  call    cs:__imp_GetLastError
0x1800b71ea  mov     ebx, eax
0x1800b71ec  test    eax, eax
0x1800b71ee  jle     short loc_1800B71F9
0x1800b71f0  movzx   ebx, ax
0x1800b71f3  or      ebx, 80070000h
0x1800b71f9  mov     rcx, [rbp+28h]; this
0x1800b71fd  test    ebx, ebx
0x1800b71ff  jns     short loc_1800B7215
0x1800b7201  mov     r9d, ebx; char *
0x1800b7204  lea     r8, aOnecoreuapBase_24; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800b720b  mov     edx, 0B9Eh; void *
0x1800b7210  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800b7215  lea     rax, WPP_GLOBAL_Control
0x1800b721c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b7223  cmp     rcx, rax
0x1800b7226  jz      loc_1800B73B7
0x1800b722c  test    byte ptr [rcx+1Ch], 80h
0x1800b7230  jz      loc_1800B73B7
0x1800b7236  mov     edx, 5Bh ; '['
0x1800b723b  mov     r9d, ebx
0x1800b723e  lea     r8, WPP_ac3d69826ca03a16ae3e9918ed4e7821_Traceguids
0x1800b7245  mov     rcx, [rcx+10h]
0x1800b7249  call    WPP_SF_d
0x1800b724e  jmp     loc_1800B73B7
0x1800b7253  xor     ebx, ebx
0x1800b7255  imul    r15, rdi, 284F0h
0x1800b725c  add     r15, 20h ; ' '
0x1800b7260  mov     [rbp+dwMaximumSizeHigh], r15
0x1800b7264  mov     [rbp+FileInformation], r15
0x1800b7268  lea     r9d, [rbx+8]; dwBufferSize
0x1800b726c  lea     r8, [rbp+FileInformation]; lpFileInformation
0x1800b7270  lea     edx, [rbx+5]; FileInformationClass
0x1800b7273  mov     rcx, rsi; hFile
0x1800b7276  call    cs:__imp_SetFileInformationByHandle
0x1800b727c  mov     edi, 80070000h
0x1800b7281  test    eax, eax
0x1800b7283  jnz     short loc_1800B729D
0x1800b7285  call    cs:__imp_GetLastError
0x1800b728b  mov     ebx, eax
0x1800b728d  test    eax, eax
0x1800b728f  jle     short loc_1800B7296
0x1800b7291  movzx   ebx, ax
0x1800b7294  or      ebx, edi
0x1800b7296  xor     eax, eax
0x1800b7298  test    ebx, ebx
0x1800b729a  cmovs   ebx, eax
0x1800b729d  mov     qword ptr [rsp+60h+dwFlagsAndAttributes], 0; lpName
0x1800b72a6  mov     [rsp+60h+dwCreationDisposition], r15d; int
0x1800b72ab  mov     r9d, dword ptr [rbp+dwMaximumSizeHigh+4]; dwMaximumSizeHigh
0x1800b72af  xor     edx, edx; lpFileMappingAttributes
0x1800b72b1  lea     r8d, [rdx+4]; flProtect
0x1800b72b5  mov     rcx, rsi; hFile
0x1800b72b8  call    cs:__imp_CreateFileMappingW
0x1800b72be  mov     r15, rax
0x1800b72c1  mov     qword ptr [rbp+var_20+8], rax
0x1800b72c5  test    rax, rax
0x1800b72c8  jnz     short loc_1800B7322
0x1800b72ca  call    cs:__imp_GetLastError
0x1800b72d0  mov     ebx, eax
0x1800b72d2  test    eax, eax
0x1800b72d4  jle     short loc_1800B72DB
0x1800b72d6  movzx   ebx, ax
0x1800b72d9  or      ebx, edi
0x1800b72db  mov     rcx, [rbp+28h]; this
0x1800b72df  test    ebx, ebx
0x1800b72e1  jns     short loc_1800B72F7
0x1800b72e3  mov     r9d, ebx; char *
0x1800b72e6  lea     r8, aOnecoreuapBase_24; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800b72ed  mov     edx, 0BBBh; void *
0x1800b72f2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800b72f7  lea     rax, WPP_GLOBAL_Control
0x1800b72fe  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b7305  cmp     rcx, rax
0x1800b7308  jz      loc_1800B73B7
0x1800b730e  test    byte ptr [rcx+1Ch], 80h
0x1800b7312  jz      loc_1800B73B7
0x1800b7318  mov     edx, 5Dh ; ']'
0x1800b731d  jmp     loc_1800B723B
0x1800b7322  mov     qword ptr [rsp+60h+dwCreationDisposition], 0; int
0x1800b732b  xor     r9d, r9d; dwFileOffsetLow
0x1800b732e  xor     r8d, r8d; dwFileOffsetHigh
0x1800b7331  lea     edx, [r9+2]; dwDesiredAccess
0x1800b7335  mov     rcx, r15; hFileMappingObject
0x1800b7338  call    cs:__imp_MapViewOfFile
0x1800b733e  mov     [rbp+var_10], rax
0x1800b7342  test    rax, rax
0x1800b7345  jnz     short loc_1800B7397
0x1800b7347  call    cs:__imp_GetLastError
0x1800b734d  mov     ebx, eax
0x1800b734f  test    eax, eax
0x1800b7351  jle     short loc_1800B7358
0x1800b7353  movzx   ebx, ax
0x1800b7356  or      ebx, edi
0x1800b7358  mov     rcx, [rbp+28h]; this
0x1800b735c  test    ebx, ebx
0x1800b735e  jns     short loc_1800B7374
0x1800b7360  mov     r9d, ebx; char *
0x1800b7363  lea     r8, aOnecoreuapBase_24; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800b736a  mov     edx, 0BC6h; void *
0x1800b736f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800b7374  lea     rax, WPP_GLOBAL_Control
0x1800b737b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b7382  cmp     rcx, rax
0x1800b7385  jz      short loc_1800B73B7
0x1800b7387  test    byte ptr [rcx+1Ch], 80h
0x1800b738b  jz      short loc_1800B73B7
0x1800b738d  mov     edx, 5Eh ; '^'
0x1800b7392  jmp     loc_1800B723B
0x1800b7397  mov     [r14], rsi
0x1800b739a  mov     [r14+8], r15
0x1800b739e  mov     [r14+10h], rax
0x1800b73a2  movdqa  xmm0, cs:__xmm@0000000000000000ffffffffffffffff
0x1800b73aa  movdqu  [rbp+var_20], xmm0
0x1800b73af  mov     [rbp+var_10], 0
0x1800b73b7  lea     rcx, [rbp+var_20]; this
0x1800b73bb  call    ??1WPN_MMF_HANDLE@@QEAA@XZ; WPN_MMF_HANDLE::~WPN_MMF_HANDLE(void)
0x1800b73c0  mov     eax, ebx
0x1800b73c2  mov     rbx, [rsp+60h+arg_10]
0x1800b73ca  add     rsp, 60h
0x1800b73ce  pop     r15
0x1800b73d0  pop     r14
0x1800b73d2  pop     rdi
0x1800b73d3  pop     rsi
0x1800b73d4  pop     rbp
0x1800b73d5  retn
```
