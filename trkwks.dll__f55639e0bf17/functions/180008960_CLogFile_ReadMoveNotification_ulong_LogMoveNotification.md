# CLogFile::ReadMoveNotification(ulong,LogMoveNotification *)

- ea: `0x180008960`
- end: `0x180008cae`
- name: `?ReadMoveNotification@CLogFile@@QEAAXKPEAULogMoveNotification@@@Z`
- size: `846`
- prototype: `void __fastcall(CLogFile *__hidden this, unsigned int, struct LogMoveNotification *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x1800087c0`

## callees

- `0x1800028f0`
- `0x180008430`
- `0x180008960`
- `0x18000d038`

## import_xrefs

- `ntdll!NtWriteFile` at `0x180008bff`
- `ntdll!NtWriteFile` at `0x180008bff`
- `ntdll!NtWaitForSingleObject` at `0x180008ad7`
- `ntdll!NtWaitForSingleObject` at `0x180008c3f`
- `ntdll!NtWaitForSingleObject` at `0x180008ad7`
- `ntdll!NtWaitForSingleObject` at `0x180008c3f`
- `ntdll!NtReadFile` at `0x180008ac1`
- `ntdll!NtReadFile` at `0x180008ac1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008b3e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008b3e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008b78`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008b78`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180008b1e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180008b1e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008c53`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008c6d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008c93`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008ca7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008c53`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008c6d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008c93`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008ca7`

## pseudocode

```c
void __fastcall CLogFile::ReadMoveNotification(CLogFile *this, unsigned int a2, struct LogMoveNotification *a3)
{
  char *v3; // rbx
  void *Buffer; // r9
  void *v7; // r10
  int v8; // r8d
  int v9; // edx
  unsigned int v10; // r14d
  __int64 v11; // rdx
  ULONG Length; // ecx
  int v13; // r14d
  NTSTATUS v14; // eax
  struct CTrkWksSvc *v15; // r13
  __int16 v16; // si
  __int64 v17; // rdx
  __int64 v18; // rax
  ULONG v19; // r8d
  LARGE_INTEGER v20; // rax
  signed int Status; // eax
  struct _IO_STATUS_BLOCK v22; // [rsp+50h] [rbp-48h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-38h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+A0h] [rbp+8h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+B8h] [rbp+20h] BYREF

  v3 = (char *)this + 120;
  Buffer = (void *)*((_QWORD *)this + 19);
  if ( !Buffer || (v7 = (void *)*((_QWORD *)this + 16)) == 0 )
    TrkRaiseWin32Error(110);
  v8 = *(_DWORD *)v3;
  v9 = (int)(*(_DWORD *)v3 << 31) >> 31;
  ByteOffset.QuadPart = 0;
  if ( !v9 || (v10 = *((_DWORD *)this + 37), a2 < v10) || a2 >= v10 + *((_DWORD *)this + 36) )
  {
    IoStatusBlock = 0;
    if ( !v9 || (v8 & 2) == 0 )
      goto LABEL_10;
    v19 = *((_DWORD *)this + 35);
    v20.QuadPart = v19 * (*((_DWORD *)this + 34) + *((_DWORD *)this + 37) / *((_DWORD *)this + 36));
    v22 = 0;
    PerformanceCount = v20;
    Status = NtWriteFile(v7, 0, 0, 0, &v22, Buffer, v19, &PerformanceCount, 0);
    if ( Status == 259 )
    {
      Status = NtWaitForSingleObject(*((HANDLE *)v3 + 1), 0, 0);
      if ( Status < 0 )
        goto LABEL_25;
      Status = v22.Status;
    }
    if ( Status >= 0 )
    {
      if ( *((_DWORD *)v3 + 5) != v22.Information )
      {
        RaiseException(0x8DEAD001, 0, 0, 0);
        __debugbreak();
      }
      if ( g_ptrkwks )
        CEntropyRecorder::Put((struct CTrkWksSvc *)((char *)g_ptrkwks + 48));
      CLogFileSector::RaiseIfNotOpen((CLogFileSector *)v3);
      *(_DWORD *)v3 &= ~2u;
LABEL_10:
      Length = *((_DWORD *)v3 + 5);
      v13 = a2 / *((_DWORD *)v3 + 6) + *((_DWORD *)v3 + 4);
      ByteOffset.QuadPart = Length * v13;
      v14 = NtReadFile(*((HANDLE *)v3 + 1), 0, 0, 0, &IoStatusBlock, *((PVOID *)v3 + 4), Length, &ByteOffset, 0);
      if ( v14 == 259 )
      {
        v14 = NtWaitForSingleObject(*((HANDLE *)v3 + 1), 0, 0);
        if ( v14 < 0 )
          goto LABEL_28;
        v14 = IoStatusBlock.Status;
      }
      if ( v14 >= 0 )
      {
        v15 = g_ptrkwks;
        if ( g_ptrkwks )
        {
          PerformanceCount.QuadPart = 0;
          QueryPerformanceCounter(&PerformanceCount);
          v16 = LOWORD(PerformanceCount.LowPart)
              ^ WORD2(PerformanceCount.QuadPart)
              ^ ((PerformanceCount.LowPart ^ PerformanceCount.HighPart) >> 16);
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)v15 + 56));
          v17 = (unsigned __int8)*((_DWORD *)v15 + 24);
          *((_BYTE *)v15 + v17 + 104) ^= HIBYTE(v16);
          ++*((_DWORD *)v15 + 25);
          *((_DWORD *)v15 + 24) = v17 + 1;
          v18 = (unsigned __int8)(v17 + 1);
          *((_BYTE *)v15 + v18 + 104) ^= v16;
          ++*((_DWORD *)v15 + 25);
          *((_DWORD *)v15 + 24) = v18 + 1;
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v15 + 56));
        }
        if ( *((_DWORD *)v3 + 5) == IoStatusBlock.Information )
        {
          v10 = *((_DWORD *)v3 + 6) * (v13 - *((_DWORD *)v3 + 4));
          *(_DWORD *)v3 |= 1u;
          *((_DWORD *)v3 + 7) = v10;
          goto LABEL_6;
        }
LABEL_30:
        RaiseException(0x8DEAD001, 0, 0, 0);
        JUMPOUT(0x180008CADLL);
      }
LABEL_28:
      if ( v14 == -1073741202 )
      {
        RaiseException(0xC000026E, 0, 0, 0);
        __debugbreak();
      }
      goto LABEL_30;
    }
LABEL_25:
    RaiseException(Status, 0, 0, 0);
    __debugbreak();
  }
LABEL_6:
  v11 = *((_QWORD *)v3 + 4) + 124LL * (a2 - v10);
  *(_DWORD *)a3 = *(_DWORD *)(v11 + 8);
  *((_DWORD *)a3 + 1) = *(_DWORD *)(v11 + 12);
  *((_DWORD *)a3 + 2) = *(_DWORD *)(v11 + 16);
  *(_OWORD *)((char *)a3 + 12) = *(_OWORD *)(v11 + 20);
  *(_OWORD *)((char *)a3 + 28) = *(_OWORD *)(v11 + 36);
  *(_OWORD *)((char *)a3 + 44) = *(_OWORD *)(v11 + 52);
  *(_OWORD *)((char *)a3 + 60) = *(_OWORD *)(v11 + 68);
  *(_OWORD *)((char *)a3 + 76) = *(_OWORD *)(v11 + 84);
  *(_OWORD *)((char *)a3 + 92) = *(_OWORD *)(v11 + 100);
  *((_DWORD *)a3 + 27) = *(_DWORD *)(v11 + 116);
  *((_DWORD *)a3 + 28) = *(_DWORD *)(v11 + 120);
}

```

## disassembly

```asm
0x180008960  mov     rax, rsp
0x180008963  push    rbx
0x180008964  push    rbp
0x180008965  push    r15
0x180008967  sub     rsp, 80h
0x18000896e  lea     rbx, [rcx+78h]
0x180008972  mov     r15, r8
0x180008975  mov     r9, [rbx+20h]
0x180008979  mov     ebp, edx
0x18000897b  test    r9, r9
0x18000897e  jz      loc_180008A4C
0x180008984  mov     r10, [rbx+8]
0x180008988  test    r10, r10
0x18000898b  jz      loc_180008A4C
0x180008991  mov     r8d, [rbx]
0x180008994  mov     edx, r8d
0x180008997  shl     edx, 1Fh
0x18000899a  mov     [rax+18h], rdi
0x18000899e  xor     edi, edi
0x1800089a0  sar     edx, 1Fh
0x1800089a3  mov     [rax-28h], r14
0x1800089a7  mov     [rax+20h], rdi
0x1800089ab  test    edx, edx
0x1800089ad  jz      loc_180008A57
0x1800089b3  mov     r14d, [rbx+1Ch]
0x1800089b7  cmp     ebp, r14d
0x1800089ba  jb      loc_180008A57
0x1800089c0  mov     ecx, [rbx+18h]
0x1800089c3  add     ecx, r14d
0x1800089c6  cmp     ebp, ecx
0x1800089c8  jnb     loc_180008A57
0x1800089ce  mov     rdi, [rsp+98h+arg_10]
0x1800089d6  sub     ebp, r14d
0x1800089d9  mov     r14, [rsp+98h+var_28]
0x1800089de  mov     eax, ebp
0x1800089e0  imul    rdx, rax, 7Ch ; '|'
0x1800089e4  add     rdx, [rbx+20h]
0x1800089e8  mov     eax, [rdx+8]
0x1800089eb  mov     [r15], eax
0x1800089ee  mov     eax, [rdx+0Ch]
0x1800089f1  mov     [r15+4], eax
0x1800089f5  mov     eax, [rdx+10h]
0x1800089f8  mov     [r15+8], eax
0x1800089fc  movups  xmm0, xmmword ptr [rdx+14h]
0x180008a00  movups  xmmword ptr [r15+0Ch], xmm0
0x180008a05  movups  xmm0, xmmword ptr [rdx+24h]
0x180008a09  movups  xmmword ptr [r15+1Ch], xmm0
0x180008a0e  movups  xmm0, xmmword ptr [rdx+34h]
0x180008a12  movups  xmmword ptr [r15+2Ch], xmm0
0x180008a17  movups  xmm0, xmmword ptr [rdx+44h]
0x180008a1b  movups  xmmword ptr [r15+3Ch], xmm0
0x180008a20  movups  xmm0, xmmword ptr [rdx+54h]
0x180008a24  movups  xmmword ptr [r15+4Ch], xmm0
0x180008a29  movups  xmm0, xmmword ptr [rdx+64h]
0x180008a2d  movups  xmmword ptr [r15+5Ch], xmm0
0x180008a32  mov     eax, [rdx+74h]
0x180008a35  mov     [r15+6Ch], eax
0x180008a39  mov     eax, [rdx+78h]
0x180008a3c  mov     [r15+70h], eax
0x180008a40  add     rsp, 80h
0x180008a47  pop     r15
0x180008a49  pop     rbp
0x180008a4a  pop     rbx
0x180008a4b  retn
0x180008a4c  mov     ecx, 6Eh ; 'n'; int
0x180008a51  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
0x180008a57  xorps   xmm0, xmm0
0x180008a5a  movups  xmmword ptr [rsp+98h+var_38], xmm0
0x180008a5f  test    edx, edx
0x180008a61  jz      short loc_180008A6D
0x180008a63  test    r8b, 2
0x180008a67  jnz     loc_180008BAE
0x180008a6d  mov     ecx, [rbx+14h]
0x180008a70  xor     edx, edx
0x180008a72  mov     r14d, [rbx+10h]
0x180008a76  mov     eax, ebp
0x180008a78  div     dword ptr [rbx+18h]
0x180008a7b  mov     [rsp+98h+Key], rdi; Key
0x180008a80  xor     r9d, r9d; ApcContext
0x180008a83  add     r14d, eax
0x180008a86  xor     r8d, r8d; ApcRoutine
0x180008a89  mov     eax, r14d
0x180008a8c  xor     edx, edx; Event
0x180008a8e  imul    eax, ecx
0x180008a91  mov     qword ptr [rsp+98h+arg_18], rax
0x180008a99  lea     rax, [rsp+98h+arg_18]
0x180008aa1  mov     [rsp+98h+ByteOffset], rax; ByteOffset
0x180008aa6  mov     rax, [rbx+20h]
0x180008aaa  mov     [rsp+98h+Length], ecx; Length
0x180008aae  mov     rcx, [rbx+8]; FileHandle
0x180008ab2  mov     [rsp+98h+Buffer], rax; Buffer
0x180008ab7  lea     rax, [rsp+98h+var_38]
0x180008abc  mov     [rsp+98h+IoStatusBlock], rax; IoStatusBlock
0x180008ac1  call    cs:__imp_NtReadFile
0x180008ac7  cmp     eax, 103h
0x180008acc  jnz     short loc_180008AE9
0x180008ace  mov     rcx, [rbx+8]; Handle
0x180008ad2  xor     r8d, r8d; Timeout
0x180008ad5  xor     edx, edx; Alertable
0x180008ad7  call    cs:__imp_NtWaitForSingleObject
0x180008add  test    eax, eax
0x180008adf  js      loc_180008C7F
0x180008ae5  mov     eax, dword ptr [rsp+98h+var_38]
0x180008ae9  test    eax, eax
0x180008aeb  js      loc_180008C7F
0x180008af1  mov     [rsp+98h+var_20], r13
0x180008af6  mov     r13, cs:?g_ptrkwks@@3PEAVCTrkWksSvc@@EA; CTrkWksSvc * g_ptrkwks
0x180008afd  test    r13, r13
0x180008b00  jz      loc_180008B86
0x180008b06  lea     rcx, [rsp+98h+PerformanceCount]; lpPerformanceCount
0x180008b0e  mov     [rsp+98h+arg_8], rsi
0x180008b16  mov     qword ptr [rsp+98h+PerformanceCount], rdi
0x180008b1e  call    cs:__imp_QueryPerformanceCounter
0x180008b24  mov     eax, dword ptr [rsp+98h+PerformanceCount+4]
0x180008b2b  lea     rcx, [r13+38h]; lpCriticalSection
0x180008b2f  xor     eax, dword ptr [rsp+98h+PerformanceCount]
0x180008b36  mov     esi, eax
0x180008b38  shr     esi, 10h
0x180008b3b  xor     si, ax
0x180008b3e  call    cs:__imp_EnterCriticalSection
0x180008b44  mov     eax, [r13+60h]
0x180008b48  lea     rcx, [r13+38h]; lpCriticalSection
0x180008b4c  movzx   edx, al
0x180008b4f  movzx   eax, si
0x180008b52  shr     ax, 8
0x180008b56  xor     [rdx+r13+68h], al
0x180008b5b  lea     eax, [rdx+1]
0x180008b5e  inc     dword ptr [r13+64h]
0x180008b62  mov     [r13+60h], eax
0x180008b66  movzx   eax, al
0x180008b69  xor     [rax+r13+68h], sil
0x180008b6e  inc     dword ptr [r13+64h]
0x180008b72  inc     eax
0x180008b74  mov     [r13+60h], eax
0x180008b78  call    cs:__imp_LeaveCriticalSection
0x180008b7e  mov     rsi, [rsp+98h+arg_8]
0x180008b86  mov     eax, [rbx+14h]
0x180008b89  mov     r13, [rsp+98h+var_20]
0x180008b8e  cmp     rax, [rsp+98h+var_38.Information]
0x180008b93  jnz     loc_180008C9A
0x180008b99  sub     r14d, [rbx+10h]
0x180008b9d  imul    r14d, [rbx+18h]
0x180008ba2  or      dword ptr [rbx], 1
0x180008ba5  mov     [rbx+1Ch], r14d
0x180008ba9  jmp     loc_1800089CE
0x180008bae  mov     eax, [rbx+1Ch]
0x180008bb1  xor     edx, edx
0x180008bb3  div     dword ptr [rbx+18h]
0x180008bb6  mov     r8d, [rbx+14h]
0x180008bba  xor     edx, edx; Event
0x180008bbc  add     eax, [rbx+10h]
0x180008bbf  mov     rcx, r10; FileHandle
0x180008bc2  imul    eax, r8d
0x180008bc6  mov     [rsp+98h+Key], rdi; Key
0x180008bcb  movups  xmmword ptr [rsp+98h+var_48], xmm0
0x180008bd0  mov     qword ptr [rsp+98h+PerformanceCount], rax
0x180008bd8  lea     rax, [rsp+98h+PerformanceCount]
0x180008be0  mov     [rsp+98h+ByteOffset], rax; ByteOffset
0x180008be5  lea     rax, [rsp+98h+var_48]
0x180008bea  mov     [rsp+98h+Length], r8d; Length
0x180008bef  xor     r8d, r8d; ApcRoutine
0x180008bf2  mov     [rsp+98h+Buffer], r9; Buffer
0x180008bf7  xor     r9d, r9d; ApcContext
0x180008bfa  mov     [rsp+98h+IoStatusBlock], rax; IoStatusBlock
0x180008bff  call    cs:__imp_NtWriteFile
0x180008c05  cmp     eax, 103h
0x180008c0a  jz      short loc_180008C36
0x180008c0c  test    eax, eax
0x180008c0e  js      short loc_180008C49
0x180008c10  mov     eax, [rbx+14h]
0x180008c13  cmp     rax, [rsp+98h+var_48.Information]
0x180008c18  jnz     short loc_180008C60
0x180008c1a  mov     rcx, cs:?g_ptrkwks@@3PEAVCTrkWksSvc@@EA; CTrkWksSvc * g_ptrkwks
0x180008c21  test    rcx, rcx
0x180008c24  jnz     short loc_180008C74
0x180008c26  mov     rcx, rbx; this
0x180008c29  call    ?RaiseIfNotOpen@CLogFileSector@@AEBAXXZ; CLogFileSector::RaiseIfNotOpen(void)
0x180008c2e  and     dword ptr [rbx], 0FFFFFFFDh
0x180008c31  jmp     loc_180008A6D
0x180008c36  mov     rcx, [rbx+8]; Handle
0x180008c3a  xor     r8d, r8d; Timeout
0x180008c3d  xor     edx, edx; Alertable
0x180008c3f  call    cs:__imp_NtWaitForSingleObject
0x180008c45  test    eax, eax
0x180008c47  jns     short loc_180008C5A
0x180008c49  xor     r9d, r9d; lpArguments
0x180008c4c  xor     r8d, r8d; nNumberOfArguments
0x180008c4f  xor     edx, edx; dwExceptionFlags
0x180008c51  mov     ecx, eax; dwExceptionCode
0x180008c53  call    cs:__imp_RaiseException
0x180008c59  int     3; Trap to Debugger
0x180008c5a  mov     eax, dword ptr [rsp+98h+var_48]
0x180008c5e  jmp     short loc_180008C0C
0x180008c60  xor     r9d, r9d; lpArguments
0x180008c63  xor     r8d, r8d; nNumberOfArguments
0x180008c66  xor     edx, edx; dwExceptionFlags
0x180008c68  mov     ecx, 8DEAD001h; dwExceptionCode
0x180008c6d  call    cs:__imp_RaiseException
0x180008c73  int     3; Trap to Debugger
0x180008c74  add     rcx, 30h ; '0'; this
0x180008c78  call    ?Put@CEntropyRecorder@@QEAAXXZ; CEntropyRecorder::Put(void)
0x180008c7d  jmp     short loc_180008C26
0x180008c7f  cmp     eax, 0C000026Eh
0x180008c84  jnz     short loc_180008C9A
0x180008c86  xor     r9d, r9d; lpArguments
0x180008c89  xor     r8d, r8d; nNumberOfArguments
0x180008c8c  xor     edx, edx; dwExceptionFlags
0x180008c8e  mov     ecx, 0C000026Eh; dwExceptionCode
0x180008c93  call    cs:__imp_RaiseException
0x180008c99  int     3; Trap to Debugger
0x180008c9a  xor     r9d, r9d; lpArguments
0x180008c9d  xor     r8d, r8d; nNumberOfArguments
0x180008ca0  xor     edx, edx; dwExceptionFlags
0x180008ca2  mov     ecx, 8DEAD001h; dwExceptionCode
0x180008ca7  call    cs:__imp_RaiseException
```
