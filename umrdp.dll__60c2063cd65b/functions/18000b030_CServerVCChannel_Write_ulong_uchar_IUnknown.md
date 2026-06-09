# CServerVCChannel::Write(ulong,uchar *,IUnknown *)

- ea: `0x18000b030`
- end: `0x18000b3c7`
- name: `?Write@CServerVCChannel@@UEAAJKPEAEPEAUIUnknown@@@Z`
- size: `919`
- prototype: `__int64 __fastcall(CServerVCChannel *this, DWORD, unsigned __int8 *, struct IUnknown *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops`

## callees

- `0x180007da0`
- `0x18000b030`
- `0x18000b3d0`
- `0x18000b8f8`
- `0x18000b98c`
- `0x18000f79c`
- `0x180028640`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b0ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b1bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b1e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b2f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b0ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b1bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b1e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b2f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b3a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b3a6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000b1db`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000b1db`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000b09f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000b09f`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18000b2e0`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18000b2e0`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000b1a4`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000b1a4`

## pseudocode

```c
__int64 __fastcall CServerVCChannel::Write(CServerVCChannel *this, DWORD a2, unsigned __int8 *a3, struct IUnknown *a4)
{
  CTSCriticalSection *v4; // rbx
  HANDLE EventW; // rax
  signed int LastError; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v12; // edi
  unsigned int v13; // eax
  BOOL v14; // edi
  signed int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  BOOL OverlappedResult; // ebx
  unsigned int v19; // eax
  struct IUnknownVtbl *lpVtbl; // rax
  char *v21; // [rsp+30h] [rbp-30h] BYREF
  HANDLE hHandle; // [rsp+38h] [rbp-28h]
  struct _OVERLAPPED Overlapped; // [rsp+40h] [rbp-20h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+90h] [rbp+30h] BYREF
  LPCVOID lpBuffer; // [rsp+A0h] [rbp+40h]

  lpBuffer = a3;
  v4 = (CServerVCChannel *)((char *)this + 56);
  NumberOfBytesWritten = 0;
  v21 = (char *)this + 56;
  memset(&Overlapped, 0, sizeof(Overlapped));
  CTSCriticalSection::Lock((CServerVCChannel *)((char *)this + 56));
  if ( (*((_BYTE *)this + 36) & 4) != 0 )
  {
    CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v21);
    return 2147943076LL;
  }
  EventW = CreateEventW(0, 1, 0, 0);
  hHandle = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
        28,
        WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids,
        CurrentThreadActivityIdPrefix,
        LastError);
    }
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2147467259;
    CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v21);
    return (unsigned int)LastError;
  }
  Overlapped.hEvent = EventW;
  Overlapped.Pointer = 0;
  if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
    && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 5u )
  {
    v12 = dword_18005DE90++;
    v13 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Ddd(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      29,
      WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids,
      v13,
      v12,
      a2);
  }
  v14 = WriteFile(*((HANDLE *)this + 43), lpBuffer, a2, &NumberOfBytesWritten, &Overlapped);
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v21);
  if ( v14 )
    goto LABEL_43;
  if ( GetLastError() != 997 )
    goto LABEL_34;
  if ( !WaitForSingleObject(hHandle, 0xFFFFFFFF) )
    goto LABEL_27;
  v15 = GetLastError();
  LastError = v15;
  if ( v15 > 0 )
    LastError = (unsigned __int16)v15 | 0x80070000;
  if ( LastError >= 0 )
  {
LABEL_27:
    v21 = (char *)v4;
    CTSCriticalSection::Lock(v4);
    if ( (*((_BYTE *)this + 36) & 4) != 0 )
    {
      LastError = -2147024220;
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        v17 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
          31,
          (unsigned int)WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids,
          v17,
          (__int64)"ERROR_HANDLES_CLOSED",
          164);
      }
      CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v21);
      goto LABEL_47;
    }
    OverlappedResult = GetOverlappedResult(*((HANDLE *)this + 43), &Overlapped, &NumberOfBytesWritten, 0);
    CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v21);
    if ( !OverlappedResult )
    {
LABEL_34:
      LastError = GetLastError();
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        v19 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
          32,
          WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids,
          v19,
          LastError);
      }
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( LastError >= 0 )
        LastError = -2147467259;
      goto LABEL_47;
    }
LABEL_43:
    if ( a4 )
    {
      lpVtbl = a4->lpVtbl;
      v21 = 0;
      if ( ((int (__fastcall *)(struct IUnknown *, GUID *, char **))lpVtbl->QueryInterface)(
             a4,
             &IID_IWTSWriteCallback,
             &v21) >= 0 )
      {
        (*(void (__fastcall **)(char *, _QWORD))(*(_QWORD *)v21 + 24LL))(v21, 0);
        (*(void (__fastcall **)(char *))(*(_QWORD *)v21 + 16LL))(v21);
      }
    }
    LastError = 0;
    goto LABEL_47;
  }
  if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
    && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    v16 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      30,
      (unsigned int)WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids,
      v16,
      (__int64)"WaitForSingleObject",
      LastError);
  }
LABEL_47:
  CloseHandle(hHandle);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18000b030  mov     [rsp-28h+arg_8], rbx
0x18000b035  mov     [rsp-28h+arg_18], rsi
0x18000b03a  mov     [rsp-28h+lpBuffer], r8
0x18000b03f  push    rbp
0x18000b040  push    rdi
0x18000b041  push    r12
0x18000b043  push    r13
0x18000b045  push    r14
0x18000b047  mov     rbp, rsp
0x18000b04a  sub     rsp, 60h
0x18000b04e  lea     rbx, [rcx+38h]
0x18000b052  mov     [rbp+NumberOfBytesWritten], 0
0x18000b059  xorps   xmm0, xmm0
0x18000b05c  mov     [rbp+var_30], rbx
0x18000b060  mov     r13, rcx
0x18000b063  mov     r12, r9
0x18000b066  mov     rcx, rbx; this
0x18000b069  mov     r14d, edx
0x18000b06c  movups  xmmword ptr [rbp+Overlapped.Internal], xmm0
0x18000b070  movups  xmmword ptr [rbp+Overlapped.10h], xmm0
0x18000b074  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x18000b079  test    byte ptr [r13+24h], 4
0x18000b07e  jz      short loc_18000B093
0x18000b080  lea     rcx, [rbp+var_30]; this
0x18000b084  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x18000b089  mov     eax, 800702A4h
0x18000b08e  jmp     loc_18000B3AE
0x18000b093  xor     r9d, r9d; lpName
0x18000b096  xor     r8d, r8d; bInitialState
0x18000b099  xor     ecx, ecx; lpEventAttributes
0x18000b09b  lea     edx, [r9+1]; bManualReset
0x18000b09f  call    cs:__imp_CreateEventW
0x18000b0a5  mov     [rbp+hHandle], rax
0x18000b0a9  test    rax, rax
0x18000b0ac  jnz     short loc_18000B122
0x18000b0ae  call    cs:__imp_GetLastError
0x18000b0b4  mov     edi, eax
0x18000b0b6  mov     rax, cs:WPP_GLOBAL_Control
0x18000b0bd  lea     rsi, WPP_GLOBAL_Control
0x18000b0c4  cmp     rax, rsi
0x18000b0c7  jz      short loc_18000B0FD
0x18000b0c9  test    byte ptr [rax+1Ch], 8
0x18000b0cd  jz      short loc_18000B0FD
0x18000b0cf  cmp     byte ptr [rax+19h], 2
0x18000b0d3  jb      short loc_18000B0FD
0x18000b0d5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000b0da  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b0e1  lea     r8, WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids
0x18000b0e8  mov     edx, 1Ch
0x18000b0ed  mov     dword ptr [rsp+60h+lpOverlapped], edi
0x18000b0f1  mov     r9d, eax
0x18000b0f4  mov     rcx, [rcx+10h]
0x18000b0f8  call    WPP_SF_Dd
0x18000b0fd  test    edi, edi
0x18000b0ff  jle     short loc_18000B10A
0x18000b101  movzx   edi, di
0x18000b104  or      edi, 80070000h
0x18000b10a  test    edi, edi
0x18000b10c  lea     rcx, [rbp+var_30]; this
0x18000b110  mov     eax, 80004005h
0x18000b115  cmovns  edi, eax
0x18000b118  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x18000b11d  jmp     loc_18000B3AC
0x18000b122  mov     [rbp+Overlapped.hEvent], rax
0x18000b126  mov     qword ptr [rbp+Overlapped.10h], 0
0x18000b12e  mov     rax, cs:WPP_GLOBAL_Control
0x18000b135  lea     rsi, WPP_GLOBAL_Control
0x18000b13c  cmp     rax, rsi
0x18000b13f  jz      short loc_18000B189
0x18000b141  test    byte ptr [rax+1Ch], 1
0x18000b145  jz      short loc_18000B189
0x18000b147  cmp     byte ptr [rax+19h], 5
0x18000b14b  jb      short loc_18000B189
0x18000b14d  mov     edi, cs:dword_18005DE90
0x18000b153  lea     eax, [rdi+1]
0x18000b156  mov     cs:dword_18005DE90, eax
0x18000b15c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000b161  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b168  lea     r8, WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids
0x18000b16f  mov     edx, 1Dh
0x18000b174  mov     [rsp+60h+var_38], r14d
0x18000b179  mov     r9d, eax
0x18000b17c  mov     dword ptr [rsp+60h+lpOverlapped], edi
0x18000b180  mov     rcx, [rcx+10h]
0x18000b184  call    WPP_SF_Ddd
0x18000b189  mov     rdx, [rbp+lpBuffer]; lpBuffer
0x18000b18d  lea     rax, [rbp+Overlapped]
0x18000b191  mov     rcx, [r13+158h]; hFile
0x18000b198  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000b19c  mov     r8d, r14d; nNumberOfBytesToWrite
0x18000b19f  mov     [rsp+60h+lpOverlapped], rax; lpOverlapped
0x18000b1a4  call    cs:__imp_WriteFile
0x18000b1aa  lea     rcx, [rbp+var_30]; this
0x18000b1ae  mov     edi, eax
0x18000b1b0  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x18000b1b5  test    edi, edi
0x18000b1b7  jnz     loc_18000B353
0x18000b1bd  call    cs:__imp_GetLastError
0x18000b1c3  mov     r14d, 80070000h
0x18000b1c9  cmp     eax, 3E5h
0x18000b1ce  jnz     loc_18000B2F5
0x18000b1d4  mov     rcx, [rbp+hHandle]; hHandle
0x18000b1d8  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000b1db  call    cs:__imp_WaitForSingleObject
0x18000b1e1  test    eax, eax
0x18000b1e3  jz      short loc_18000B258
0x18000b1e5  call    cs:__imp_GetLastError
0x18000b1eb  mov     edi, eax
0x18000b1ed  test    eax, eax
0x18000b1ef  jle     short loc_18000B1F7
0x18000b1f1  movzx   edi, ax
0x18000b1f4  or      edi, r14d
0x18000b1f7  test    edi, edi
0x18000b1f9  jns     short loc_18000B258
0x18000b1fb  mov     rax, cs:WPP_GLOBAL_Control
0x18000b202  cmp     rax, rsi
0x18000b205  jz      loc_18000B3A2
0x18000b20b  test    byte ptr [rax+1Ch], 8
0x18000b20f  jz      loc_18000B3A2
0x18000b215  cmp     byte ptr [rax+19h], 2
0x18000b219  jb      loc_18000B3A2
0x18000b21f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000b224  lea     rcx, aWaitforsingleo_0; "WaitForSingleObject"
0x18000b22b  mov     [rsp+60h+var_38], edi
0x18000b22f  mov     [rsp+60h+lpOverlapped], rcx
0x18000b234  lea     r8, WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids
0x18000b23b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b242  mov     edx, 1Eh
0x18000b247  mov     r9d, eax
0x18000b24a  mov     rcx, [rcx+10h]
0x18000b24e  call    WPP_SF_DsD
0x18000b253  jmp     loc_18000B3A2
0x18000b258  mov     rcx, rbx; this
0x18000b25b  mov     [rbp+var_30], rbx
0x18000b25f  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x18000b264  test    byte ptr [r13+24h], 4
0x18000b269  jz      short loc_18000B2CE
0x18000b26b  mov     edi, 800702A4h
0x18000b270  mov     rax, cs:WPP_GLOBAL_Control
0x18000b277  cmp     rax, rsi
0x18000b27a  jz      short loc_18000B2C0
0x18000b27c  test    byte ptr [rax+1Ch], 8
0x18000b280  jz      short loc_18000B2C0
0x18000b282  cmp     byte ptr [rax+19h], 2
0x18000b286  jb      short loc_18000B2C0
0x18000b288  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000b28d  lea     rcx, aErrorHandlesCl; "ERROR_HANDLES_CLOSED"
0x18000b294  mov     [rsp+60h+var_38], 800702A4h
0x18000b29c  mov     [rsp+60h+lpOverlapped], rcx
0x18000b2a1  lea     r8, WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids
0x18000b2a8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b2af  mov     edx, 1Fh
0x18000b2b4  mov     r9d, eax
0x18000b2b7  mov     rcx, [rcx+10h]
0x18000b2bb  call    WPP_SF_DsD
0x18000b2c0  lea     rcx, [rbp+var_30]; this
0x18000b2c4  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x18000b2c9  jmp     loc_18000B3A2
0x18000b2ce  mov     rcx, [r13+158h]; hFile
0x18000b2d5  lea     r8, [rbp+NumberOfBytesWritten]; lpNumberOfBytesTransferred
0x18000b2d9  xor     r9d, r9d; bWait
0x18000b2dc  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x18000b2e0  call    cs:__imp_GetOverlappedResult
0x18000b2e6  lea     rcx, [rbp+var_30]; this
0x18000b2ea  mov     ebx, eax
0x18000b2ec  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x18000b2f1  test    ebx, ebx
0x18000b2f3  jnz     short loc_18000B353
0x18000b2f5  call    cs:__imp_GetLastError
0x18000b2fb  mov     edi, eax
0x18000b2fd  mov     rax, cs:WPP_GLOBAL_Control
0x18000b304  cmp     rax, rsi
0x18000b307  jz      short loc_18000B33D
0x18000b309  test    byte ptr [rax+1Ch], 8
0x18000b30d  jz      short loc_18000B33D
0x18000b30f  cmp     byte ptr [rax+19h], 2
0x18000b313  jb      short loc_18000B33D
0x18000b315  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000b31a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b321  lea     r8, WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids
0x18000b328  mov     edx, 20h ; ' '
0x18000b32d  mov     dword ptr [rsp+60h+lpOverlapped], edi
0x18000b331  mov     r9d, eax
0x18000b334  mov     rcx, [rcx+10h]
0x18000b338  call    WPP_SF_Dd
0x18000b33d  test    edi, edi
0x18000b33f  jle     short loc_18000B347
0x18000b341  movzx   edi, di
0x18000b344  or      edi, r14d
0x18000b347  test    edi, edi
0x18000b349  mov     eax, 80004005h
0x18000b34e  cmovns  edi, eax
0x18000b351  jmp     short loc_18000B3A2
0x18000b353  test    r12, r12
0x18000b356  jz      short loc_18000B3A0
0x18000b358  mov     rax, [r12]
0x18000b35c  lea     r8, [rbp+var_30]
0x18000b360  lea     rdx, IID_IWTSWriteCallback
0x18000b367  mov     [rbp+var_30], 0
0x18000b36f  mov     rcx, r12
0x18000b372  mov     rax, [rax]
0x18000b375  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b37a  test    eax, eax
0x18000b37c  js      short loc_18000B3A0
0x18000b37e  mov     rcx, [rbp+var_30]
0x18000b382  xor     edx, edx
0x18000b384  mov     rax, [rcx]
0x18000b387  mov     rax, [rax+18h]
0x18000b38b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b390  mov     rcx, [rbp+var_30]
0x18000b394  mov     rax, [rcx]
0x18000b397  mov     rax, [rax+10h]
0x18000b39b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3a0  xor     edi, edi
0x18000b3a2  mov     rcx, [rbp+hHandle]; hObject
0x18000b3a6  call    cs:__imp_CloseHandle
0x18000b3ac  mov     eax, edi
0x18000b3ae  lea     r11, [rsp+60h+var_s0]
0x18000b3b3  mov     rbx, [r11+38h]
0x18000b3b7  mov     rsi, [r11+48h]
0x18000b3bb  mov     rsp, r11
0x18000b3be  pop     r14
0x18000b3c0  pop     r13
0x18000b3c2  pop     r12
0x18000b3c4  pop     rdi
0x18000b3c5  pop     rbp
0x18000b3c6  retn
```
