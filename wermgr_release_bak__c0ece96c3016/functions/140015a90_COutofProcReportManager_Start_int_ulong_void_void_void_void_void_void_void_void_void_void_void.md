# COutofProcReportManager::Start(int,ulong,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *,void *)

- ea: `0x140015a90`
- end: `0x140015d69`
- name: `?Start@COutofProcReportManager@@QEAAJHKPEAX0000000000@Z`
- size: `729`
- prototype: `__int64 __fastcall(COutofProcReportManager *this, int, int, void *, void *, void *, void *, void *, void *, void *, void *, void *, void *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000e49c`

## callees

- `0x14000e318`
- `0x14000e340`
- `0x140015604`
- `0x140015a90`
- `0x14001a504`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x140015cc5`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x140015cc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015ad0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015b93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015ad0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015b93`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140015c54`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140015c76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140015c98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140015c54`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140015c76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140015c98`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x140015ac2`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x140015b56`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x140015ac2`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x140015b56`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140015b3a`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140015cb2`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140015d52`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140015b3a`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140015cb2`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140015d52`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall COutofProcReportManager::Start(
        COutofProcReportManager *this,
        int a2,
        int a3,
        void *a4,
        void *a5,
        void *a6,
        void *a7,
        void *a8,
        void *a9,
        void *a10,
        void *a11,
        void *a12,
        void *a13,
        void *a14)
{
  unsigned int *v18; // rax
  unsigned int *v19; // rsi
  signed int LastError; // ebx
  __int64 v21; // rbp
  _QWORD *v22; // rax
  _QWORD *v23; // rdi
  signed int v24; // eax
  void *v25; // rcx
  void *v26; // rcx
  void *v27; // rcx
  const void *v28; // rcx

  v18 = (unsigned int *)MapViewOfFile(a4, 6u, 0, 0, 0xA40u);
  v19 = v18;
  if ( !v18 )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        25,
        WPP_2f836d2f54e236ce01cfea3a67c62b4c_Traceguids,
        (unsigned int)LastError);
    if ( LastError <= 0 )
      goto LABEL_8;
    LastError = (unsigned __int16)LastError;
LABEL_7:
    LastError |= 0x80070000;
LABEL_8:
    if ( LastError >= 0 )
      LastError = -2147467259;
    goto LABEL_37;
  }
  v21 = v18[652];
  if ( (unsigned int)(v21 - 1) > 0x3FFFFFF )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_2f836d2f54e236ce01cfea3a67c62b4c_Traceguids);
    LastError = -2147023604;
  }
  else
  {
    UnmapViewOfFile(v18);
    v22 = MapViewOfFile(a4, 6u, 0, 0, v21 + 2624);
    v23 = v22;
    v19 = (unsigned int *)v22;
    if ( !v22 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_2f836d2f54e236ce01cfea3a67c62b4c_Traceguids);
      v24 = GetLastError();
      LastError = v24;
      if ( v24 <= 0 )
        goto LABEL_8;
      LastError = (unsigned __int16)v24;
      goto LABEL_7;
    }
    v22[1] = a5;
    v22[2] = a6;
    v22[84] = a7;
    v22[85] = a8;
    v22[4] = a9;
    v22[5] = a10;
    v22[164] = a11;
    v22[165] = a12;
    v22[244] = a13;
    v22[245] = a14;
    *((_DWORD *)this + 2071) = a2;
    v25 = (void *)*((_QWORD *)this + 1032);
    *((_QWORD *)this + 1032) = a4;
    if ( (unsigned __int64)v25 + 1 > 1 )
      CloseHandle(v25);
    v26 = (void *)*((_QWORD *)this + 1031);
    *((_QWORD *)this + 1031) = v23[1];
    if ( (unsigned __int64)v26 + 1 > 1 )
      CloseHandle(v26);
    v27 = (void *)*((_QWORD *)this + 1030);
    *((_QWORD *)this + 1030) = v23[2];
    if ( (unsigned __int64)v27 + 1 > 1 )
      CloseHandle(v27);
    v19 = 0;
    v28 = (const void *)*((_QWORD *)this + 4);
    *((_QWORD *)this + 4) = v23;
    if ( v28 )
      UnmapViewOfFile(v28);
    *((_DWORD *)this + 2066) = v21;
    if ( a3 != GetProcessId(*((HANDLE *)this + 1030)) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    LastError = COutofProcReportManager::CreateAndSubmitReport(this);
    if ( LastError >= 0 )
    {
      LastError = 0;
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_2f836d2f54e236ce01cfea3a67c62b4c_Traceguids);
    }
  }
LABEL_37:
  if ( v19 )
    UnmapViewOfFile(v19);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x140015a90  push    rbx
0x140015a92  push    rbp
0x140015a93  push    rsi
0x140015a94  push    rdi
0x140015a95  push    r12
0x140015a97  push    r14
0x140015a99  push    r15
0x140015a9b  sub     rsp, 40h
0x140015a9f  mov     r14, r9
0x140015aa2  mov     r15d, r8d
0x140015aa5  mov     r12d, edx
0x140015aa8  mov     rbx, rcx
0x140015aab  mov     edi, 0A40h
0x140015ab0  mov     [rsp+78h+dwNumberOfBytesToMap], rdi; dwNumberOfBytesToMap
0x140015ab5  xor     r9d, r9d; dwFileOffsetLow
0x140015ab8  xor     r8d, r8d; dwFileOffsetHigh
0x140015abb  lea     edx, [r9+6]; dwDesiredAccess
0x140015abf  mov     rcx, r14; hFileMappingObject
0x140015ac2  call    cs:__imp_MapViewOfFile
0x140015ac8  mov     rsi, rax
0x140015acb  test    rax, rax
0x140015ace  jnz     short loc_140015B23
0x140015ad0  call    cs:__imp_GetLastError
0x140015ad6  mov     ebx, eax
0x140015ad8  lea     rax, WPP_GLOBAL_Control
0x140015adf  mov     rcx, cs:WPP_GLOBAL_Control
0x140015ae6  cmp     rcx, rax
0x140015ae9  jz      short loc_140015B07
0x140015aeb  test    byte ptr [rcx+1Ch], 1
0x140015aef  jz      short loc_140015B07
0x140015af1  lea     edx, [rsi+19h]
0x140015af4  mov     r9d, ebx
0x140015af7  lea     r8, WPP_2f836d2f54e236ce01cfea3a67c62b4c_Traceguids
0x140015afe  mov     rcx, [rcx+10h]
0x140015b02  call    WPP_SF_d
0x140015b07  test    ebx, ebx
0x140015b09  jle     short loc_140015B14
0x140015b0b  movzx   ebx, bx
0x140015b0e  or      ebx, 80070000h
0x140015b14  mov     eax, 80004005h
0x140015b19  test    ebx, ebx
0x140015b1b  cmovns  ebx, eax
0x140015b1e  jmp     loc_140015D4A
0x140015b23  mov     ebp, [rax+0A30h]
0x140015b29  lea     eax, [rbp-1]
0x140015b2c  cmp     eax, 3FFFFFFh
0x140015b31  ja      loc_140015D17
0x140015b37  mov     rcx, rsi; lpBaseAddress
0x140015b3a  call    cs:__imp_UnmapViewOfFile
0x140015b40  lea     rax, [rdi+rbp]
0x140015b44  mov     [rsp+78h+dwNumberOfBytesToMap], rax; dwNumberOfBytesToMap
0x140015b49  xor     r9d, r9d; dwFileOffsetLow
0x140015b4c  xor     r8d, r8d; dwFileOffsetHigh
0x140015b4f  lea     edx, [r9+6]; dwDesiredAccess
0x140015b53  mov     rcx, r14; hFileMappingObject
0x140015b56  call    cs:__imp_MapViewOfFile
0x140015b5c  mov     rdi, rax
0x140015b5f  mov     rsi, rax
0x140015b62  test    rax, rax
0x140015b65  jnz     short loc_140015BAB
0x140015b67  lea     rax, WPP_GLOBAL_Control
0x140015b6e  mov     rcx, cs:WPP_GLOBAL_Control
0x140015b75  cmp     rcx, rax
0x140015b78  jz      short loc_140015B93
0x140015b7a  test    byte ptr [rcx+1Ch], 1
0x140015b7e  jz      short loc_140015B93
0x140015b80  lea     edx, [rsi+1Bh]
0x140015b83  lea     r8, WPP_2f836d2f54e236ce01cfea3a67c62b4c_Traceguids
0x140015b8a  mov     rcx, [rcx+10h]
0x140015b8e  call    WPP_SF_
0x140015b93  call    cs:__imp_GetLastError
0x140015b99  mov     ebx, eax
0x140015b9b  test    eax, eax
0x140015b9d  jle     loc_140015B14
0x140015ba3  movzx   ebx, ax
0x140015ba6  jmp     loc_140015B0E
0x140015bab  mov     rax, [rsp+78h+arg_20]
0x140015bb3  mov     [rdi+8], rax
0x140015bb7  mov     rax, [rsp+78h+arg_28]
0x140015bbf  mov     [rdi+10h], rax
0x140015bc3  mov     rax, [rsp+78h+arg_30]
0x140015bcb  mov     [rdi+2A0h], rax
0x140015bd2  mov     rax, [rsp+78h+arg_38]
0x140015bda  mov     [rdi+2A8h], rax
0x140015be1  mov     rax, [rsp+78h+arg_40]
0x140015be9  mov     [rdi+20h], rax
0x140015bed  mov     rax, [rsp+78h+arg_48]
0x140015bf5  mov     [rdi+28h], rax
0x140015bf9  mov     rax, [rsp+78h+arg_50]
0x140015c01  mov     [rdi+520h], rax
0x140015c08  mov     rax, [rsp+78h+arg_58]
0x140015c10  mov     [rdi+528h], rax
0x140015c17  mov     rax, [rsp+78h+arg_60]
0x140015c1f  mov     [rdi+7A0h], rax
0x140015c26  mov     rax, [rsp+78h+arg_68]
0x140015c2e  mov     [rdi+7A8h], rax
0x140015c35  mov     [rbx+205Ch], r12d
0x140015c3c  mov     rcx, [rbx+2040h]; hObject
0x140015c43  mov     [rbx+2040h], r14
0x140015c4a  lea     rax, [rcx+1]
0x140015c4e  cmp     rax, 1
0x140015c52  jbe     short loc_140015C5A
0x140015c54  call    cs:__imp_CloseHandle
0x140015c5a  mov     rcx, [rbx+2038h]; hObject
0x140015c61  mov     rax, [rdi+8]
0x140015c65  mov     [rbx+2038h], rax
0x140015c6c  lea     rax, [rcx+1]
0x140015c70  cmp     rax, 1
0x140015c74  jbe     short loc_140015C7C
0x140015c76  call    cs:__imp_CloseHandle
0x140015c7c  mov     rcx, [rbx+2030h]; hObject
0x140015c83  mov     rax, [rdi+10h]
0x140015c87  mov     [rbx+2030h], rax
0x140015c8e  lea     rax, [rcx+1]
0x140015c92  cmp     rax, 1
0x140015c96  jbe     short loc_140015C9E
0x140015c98  call    cs:__imp_CloseHandle
0x140015c9e  xor     esi, esi
0x140015ca0  mov     [rsp+78h+var_48], rsi
0x140015ca5  mov     rcx, [rbx+20h]; lpBaseAddress
0x140015ca9  mov     [rbx+20h], rdi
0x140015cad  test    rcx, rcx
0x140015cb0  jz      short loc_140015CB8
0x140015cb2  call    cs:__imp_UnmapViewOfFile
0x140015cb8  mov     [rbx+2048h], ebp
0x140015cbe  mov     rcx, [rbx+2030h]; Process
0x140015cc5  call    cs:__imp_GetProcessId
0x140015ccb  cmp     r15d, eax
0x140015cce  jz      short loc_140015CD5
0x140015cd0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140015cd5  mov     rcx, rbx; this
0x140015cd8  call    ?CreateAndSubmitReport@COutofProcReportManager@@AEAAJXZ; COutofProcReportManager::CreateAndSubmitReport(void)
0x140015cdd  mov     ebx, eax
0x140015cdf  test    eax, eax
0x140015ce1  jns     short loc_140015D13
0x140015ce3  lea     rax, WPP_GLOBAL_Control
0x140015cea  mov     rcx, cs:WPP_GLOBAL_Control
0x140015cf1  cmp     rcx, rax
0x140015cf4  jz      short loc_140015D4A
0x140015cf6  test    byte ptr [rcx+1Ch], 1
0x140015cfa  jz      short loc_140015D4A
0x140015cfc  mov     edx, 1Ch
0x140015d01  lea     r8, WPP_2f836d2f54e236ce01cfea3a67c62b4c_Traceguids
0x140015d08  mov     rcx, [rcx+10h]
0x140015d0c  call    WPP_SF_
0x140015d11  jmp     short loc_140015D4A
0x140015d13  xor     ebx, ebx
0x140015d15  jmp     short loc_140015D4A
0x140015d17  lea     rax, WPP_GLOBAL_Control
0x140015d1e  mov     rcx, cs:WPP_GLOBAL_Control
0x140015d25  cmp     rcx, rax
0x140015d28  jz      short loc_140015D45
0x140015d2a  test    byte ptr [rcx+1Ch], 1
0x140015d2e  jz      short loc_140015D45
0x140015d30  mov     edx, 1Ah
0x140015d35  lea     r8, WPP_2f836d2f54e236ce01cfea3a67c62b4c_Traceguids
0x140015d3c  mov     rcx, [rcx+10h]
0x140015d40  call    WPP_SF_
0x140015d45  mov     ebx, 8007050Ch
0x140015d4a  test    rsi, rsi
0x140015d4d  jz      short loc_140015D58
0x140015d4f  mov     rcx, rsi; lpBaseAddress
0x140015d52  call    cs:__imp_UnmapViewOfFile
0x140015d58  mov     eax, ebx
0x140015d5a  add     rsp, 40h
0x140015d5e  pop     r15
0x140015d60  pop     r14
0x140015d62  pop     r12
0x140015d64  pop     rdi
0x140015d65  pop     rsi
0x140015d66  pop     rbp
0x140015d67  pop     rbx
0x140015d68  retn
```
