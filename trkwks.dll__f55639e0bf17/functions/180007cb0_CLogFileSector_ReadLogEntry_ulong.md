# CLogFileSector::ReadLogEntry(ulong)

- ea: `0x180007cb0`
- end: `0x180007f8a`
- name: `?ReadLogEntry@CLogFileSector@@QEAAPEBUtagLogEntry@@K@Z`
- size: `730`
- prototype: `const struct tagLogEntry *__fastcall(CLogFileSector *__hidden this, unsigned int)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x180006bf0`
- `0x180007f90`
- `0x180008d10`
- `0x180009ce8`

## callees

- `0x1800028f0`
- `0x180007cb0`
- `0x180008430`
- `0x18000d038`

## import_xrefs

- `ntdll!NtWriteFile` at `0x180007edb`
- `ntdll!NtWriteFile` at `0x180007edb`
- `ntdll!NtWaitForSingleObject` at `0x180007db3`
- `ntdll!NtWaitForSingleObject` at `0x180007f1b`
- `ntdll!NtWaitForSingleObject` at `0x180007db3`
- `ntdll!NtWaitForSingleObject` at `0x180007f1b`
- `ntdll!NtReadFile` at `0x180007d9d`
- `ntdll!NtReadFile` at `0x180007d9d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007e1a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007e1a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007e54`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007e54`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180007dfa`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180007dfa`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180007f2f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180007f49`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180007f6f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180007f83`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180007f2f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180007f49`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180007f6f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180007f83`

## pseudocode

```c
const struct tagLogEntry *__fastcall CLogFileSector::ReadLogEntry(CLogFileSector *this, unsigned int a2)
{
  void *Buffer; // r9
  void *v5; // r10
  int v6; // r8d
  int v7; // edx
  unsigned int v8; // r14d
  ULONG Length; // ecx
  int v11; // r14d
  NTSTATUS v12; // eax
  struct CTrkWksSvc *v13; // r15
  __int16 v14; // si
  __int64 v15; // rdx
  __int64 v16; // rax
  ULONG v17; // r8d
  LARGE_INTEGER v18; // rax
  signed int Status; // eax
  struct _IO_STATUS_BLOCK v20; // [rsp+50h] [rbp-48h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-38h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+A0h] [rbp+8h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+B0h] [rbp+18h] BYREF

  Buffer = (void *)*((_QWORD *)this + 4);
  if ( !Buffer || (v5 = (void *)*((_QWORD *)this + 1)) == 0 )
    TrkRaiseWin32Error(110);
  v6 = *(_DWORD *)this;
  v7 = (int)(*(_DWORD *)this << 31) >> 31;
  ByteOffset.QuadPart = 0;
  if ( !v7 || (v8 = *((_DWORD *)this + 7), a2 < v8) || a2 >= v8 + *((_DWORD *)this + 6) )
  {
    IoStatusBlock = 0;
    if ( !v7 || (v6 & 2) == 0 )
      goto LABEL_10;
    v17 = *((_DWORD *)this + 5);
    v18.QuadPart = v17 * (*((_DWORD *)this + 4) + *((_DWORD *)this + 7) / *((_DWORD *)this + 6));
    v20 = 0;
    PerformanceCount = v18;
    Status = NtWriteFile(v5, 0, 0, 0, &v20, Buffer, v17, &PerformanceCount, 0);
    if ( Status == 259 )
    {
      Status = NtWaitForSingleObject(*((HANDLE *)this + 1), 0, 0);
      if ( Status < 0 )
        goto LABEL_25;
      Status = v20.Status;
    }
    if ( Status >= 0 )
    {
      if ( *((_DWORD *)this + 5) != v20.Information )
      {
        RaiseException(0x8DEAD001, 0, 0, 0);
        __debugbreak();
      }
      if ( g_ptrkwks )
        CEntropyRecorder::Put((struct CTrkWksSvc *)((char *)g_ptrkwks + 48));
      CLogFileSector::RaiseIfNotOpen(this);
      *(_DWORD *)this &= ~2u;
LABEL_10:
      Length = *((_DWORD *)this + 5);
      v11 = a2 / *((_DWORD *)this + 6) + *((_DWORD *)this + 4);
      ByteOffset.QuadPart = Length * v11;
      v12 = NtReadFile(*((HANDLE *)this + 1), 0, 0, 0, &IoStatusBlock, *((PVOID *)this + 4), Length, &ByteOffset, 0);
      if ( v12 == 259 )
      {
        v12 = NtWaitForSingleObject(*((HANDLE *)this + 1), 0, 0);
        if ( v12 < 0 )
          goto LABEL_28;
        v12 = IoStatusBlock.Status;
      }
      if ( v12 >= 0 )
      {
        v13 = g_ptrkwks;
        if ( g_ptrkwks )
        {
          PerformanceCount.QuadPart = 0;
          QueryPerformanceCounter(&PerformanceCount);
          v14 = LOWORD(PerformanceCount.LowPart)
              ^ WORD2(PerformanceCount.QuadPart)
              ^ ((PerformanceCount.LowPart ^ PerformanceCount.HighPart) >> 16);
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)v13 + 56));
          v15 = (unsigned __int8)*((_DWORD *)v13 + 24);
          *((_BYTE *)v13 + v15 + 104) ^= HIBYTE(v14);
          ++*((_DWORD *)v13 + 25);
          *((_DWORD *)v13 + 24) = v15 + 1;
          v16 = (unsigned __int8)(v15 + 1);
          *((_BYTE *)v13 + v16 + 104) ^= v14;
          ++*((_DWORD *)v13 + 25);
          *((_DWORD *)v13 + 24) = v16 + 1;
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v13 + 56));
        }
        if ( *((_DWORD *)this + 5) == IoStatusBlock.Information )
        {
          v8 = *((_DWORD *)this + 6) * (v11 - *((_DWORD *)this + 4));
          *(_DWORD *)this |= 1u;
          *((_DWORD *)this + 7) = v8;
          return (const struct tagLogEntry *)(*((_QWORD *)this + 4) + 124LL * (a2 - v8));
        }
LABEL_30:
        RaiseException(0x8DEAD001, 0, 0, 0);
        JUMPOUT(0x180007F89LL);
      }
LABEL_28:
      if ( v12 == -1073741202 )
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
  return (const struct tagLogEntry *)(*((_QWORD *)this + 4) + 124LL * (a2 - v8));
}

```

## disassembly

```asm
0x180007cb0  mov     rax, rsp
0x180007cb3  push    rbx
0x180007cb4  push    rbp
0x180007cb5  sub     rsp, 88h
0x180007cbc  mov     r9, [rcx+20h]
0x180007cc0  mov     ebp, edx
0x180007cc2  mov     rbx, rcx
0x180007cc5  test    r9, r9
0x180007cc8  jz      short loc_180007D28
0x180007cca  mov     r10, [rcx+8]
0x180007cce  test    r10, r10
0x180007cd1  jz      short loc_180007D28
0x180007cd3  mov     r8d, [rcx]
0x180007cd6  mov     edx, r8d
0x180007cd9  shl     edx, 1Fh
0x180007cdc  mov     [rax-18h], rdi
0x180007ce0  xor     edi, edi
0x180007ce2  sar     edx, 1Fh
0x180007ce5  mov     [rax-20h], r14
0x180007ce9  mov     [rax+18h], rdi
0x180007ced  test    edx, edx
0x180007cef  jz      short loc_180007D33
0x180007cf1  mov     r14d, [rcx+1Ch]
0x180007cf5  cmp     ebp, r14d
0x180007cf8  jb      short loc_180007D33
0x180007cfa  mov     ecx, [rcx+18h]
0x180007cfd  add     ecx, r14d
0x180007d00  cmp     ebp, ecx
0x180007d02  jnb     short loc_180007D33
0x180007d04  mov     rdi, [rsp+98h+var_18]
0x180007d0c  sub     ebp, r14d
0x180007d0f  mov     r14, [rsp+98h+var_20]
0x180007d14  mov     eax, ebp
0x180007d16  imul    rax, 7Ch ; '|'
0x180007d1a  add     rax, [rbx+20h]
0x180007d1e  add     rsp, 88h
0x180007d25  pop     rbp
0x180007d26  pop     rbx
0x180007d27  retn
0x180007d28  mov     ecx, 6Eh ; 'n'; int
0x180007d2d  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
0x180007d33  xorps   xmm0, xmm0
0x180007d36  movups  xmmword ptr [rsp+98h+var_38], xmm0
0x180007d3b  test    edx, edx
0x180007d3d  jz      short loc_180007D49
0x180007d3f  test    r8b, 2
0x180007d43  jnz     loc_180007E8A
0x180007d49  mov     ecx, [rbx+14h]
0x180007d4c  xor     edx, edx
0x180007d4e  mov     r14d, [rbx+10h]
0x180007d52  mov     eax, ebp
0x180007d54  div     dword ptr [rbx+18h]
0x180007d57  mov     [rsp+98h+Key], rdi; Key
0x180007d5c  xor     r9d, r9d; ApcContext
0x180007d5f  add     r14d, eax
0x180007d62  xor     r8d, r8d; ApcRoutine
0x180007d65  mov     eax, r14d
0x180007d68  xor     edx, edx; Event
0x180007d6a  imul    eax, ecx
0x180007d6d  mov     qword ptr [rsp+98h+arg_10], rax
0x180007d75  lea     rax, [rsp+98h+arg_10]
0x180007d7d  mov     [rsp+98h+ByteOffset], rax; ByteOffset
0x180007d82  mov     rax, [rbx+20h]
0x180007d86  mov     [rsp+98h+Length], ecx; Length
0x180007d8a  mov     rcx, [rbx+8]; FileHandle
0x180007d8e  mov     [rsp+98h+Buffer], rax; Buffer
0x180007d93  lea     rax, [rsp+98h+var_38]
0x180007d98  mov     [rsp+98h+IoStatusBlock], rax; IoStatusBlock
0x180007d9d  call    cs:__imp_NtReadFile
0x180007da3  cmp     eax, 103h
0x180007da8  jnz     short loc_180007DC5
0x180007daa  mov     rcx, [rbx+8]; Handle
0x180007dae  xor     r8d, r8d; Timeout
0x180007db1  xor     edx, edx; Alertable
0x180007db3  call    cs:__imp_NtWaitForSingleObject
0x180007db9  test    eax, eax
0x180007dbb  js      loc_180007F5B
0x180007dc1  mov     eax, dword ptr [rsp+98h+var_38]
0x180007dc5  test    eax, eax
0x180007dc7  js      loc_180007F5B
0x180007dcd  mov     [rsp+98h+var_28], r15
0x180007dd2  mov     r15, cs:?g_ptrkwks@@3PEAVCTrkWksSvc@@EA; CTrkWksSvc * g_ptrkwks
0x180007dd9  test    r15, r15
0x180007ddc  jz      loc_180007E62
0x180007de2  lea     rcx, [rsp+98h+PerformanceCount]; lpPerformanceCount
0x180007dea  mov     [rsp+98h+arg_8], rsi
0x180007df2  mov     qword ptr [rsp+98h+PerformanceCount], rdi
0x180007dfa  call    cs:__imp_QueryPerformanceCounter
0x180007e00  mov     eax, dword ptr [rsp+98h+PerformanceCount+4]
0x180007e07  lea     rcx, [r15+38h]; lpCriticalSection
0x180007e0b  xor     eax, dword ptr [rsp+98h+PerformanceCount]
0x180007e12  mov     esi, eax
0x180007e14  shr     esi, 10h
0x180007e17  xor     si, ax
0x180007e1a  call    cs:__imp_EnterCriticalSection
0x180007e20  mov     eax, [r15+60h]
0x180007e24  lea     rcx, [r15+38h]; lpCriticalSection
0x180007e28  movzx   edx, al
0x180007e2b  movzx   eax, si
0x180007e2e  shr     ax, 8
0x180007e32  xor     [rdx+r15+68h], al
0x180007e37  lea     eax, [rdx+1]
0x180007e3a  inc     dword ptr [r15+64h]
0x180007e3e  mov     [r15+60h], eax
0x180007e42  movzx   eax, al
0x180007e45  xor     [rax+r15+68h], sil
0x180007e4a  inc     dword ptr [r15+64h]
0x180007e4e  inc     eax
0x180007e50  mov     [r15+60h], eax
0x180007e54  call    cs:__imp_LeaveCriticalSection
0x180007e5a  mov     rsi, [rsp+98h+arg_8]
0x180007e62  mov     eax, [rbx+14h]
0x180007e65  mov     r15, [rsp+98h+var_28]
0x180007e6a  cmp     rax, [rsp+98h+var_38.Information]
0x180007e6f  jnz     loc_180007F76
0x180007e75  sub     r14d, [rbx+10h]
0x180007e79  imul    r14d, [rbx+18h]
0x180007e7e  or      dword ptr [rbx], 1
0x180007e81  mov     [rbx+1Ch], r14d
0x180007e85  jmp     loc_180007D04
0x180007e8a  mov     eax, [rbx+1Ch]
0x180007e8d  xor     edx, edx
0x180007e8f  div     dword ptr [rbx+18h]
0x180007e92  mov     r8d, [rbx+14h]
0x180007e96  xor     edx, edx; Event
0x180007e98  add     eax, [rbx+10h]
0x180007e9b  mov     rcx, r10; FileHandle
0x180007e9e  imul    eax, r8d
0x180007ea2  mov     [rsp+98h+Key], rdi; Key
0x180007ea7  movups  xmmword ptr [rsp+98h+var_48], xmm0
0x180007eac  mov     qword ptr [rsp+98h+PerformanceCount], rax
0x180007eb4  lea     rax, [rsp+98h+PerformanceCount]
0x180007ebc  mov     [rsp+98h+ByteOffset], rax; ByteOffset
0x180007ec1  lea     rax, [rsp+98h+var_48]
0x180007ec6  mov     [rsp+98h+Length], r8d; Length
0x180007ecb  xor     r8d, r8d; ApcRoutine
0x180007ece  mov     [rsp+98h+Buffer], r9; Buffer
0x180007ed3  xor     r9d, r9d; ApcContext
0x180007ed6  mov     [rsp+98h+IoStatusBlock], rax; IoStatusBlock
0x180007edb  call    cs:__imp_NtWriteFile
0x180007ee1  cmp     eax, 103h
0x180007ee6  jz      short loc_180007F12
0x180007ee8  test    eax, eax
0x180007eea  js      short loc_180007F25
0x180007eec  mov     eax, [rbx+14h]
0x180007eef  cmp     rax, [rsp+98h+var_48.Information]
0x180007ef4  jnz     short loc_180007F3C
0x180007ef6  mov     rcx, cs:?g_ptrkwks@@3PEAVCTrkWksSvc@@EA; CTrkWksSvc * g_ptrkwks
0x180007efd  test    rcx, rcx
0x180007f00  jnz     short loc_180007F50
0x180007f02  mov     rcx, rbx; this
0x180007f05  call    ?RaiseIfNotOpen@CLogFileSector@@AEBAXXZ; CLogFileSector::RaiseIfNotOpen(void)
0x180007f0a  and     dword ptr [rbx], 0FFFFFFFDh
0x180007f0d  jmp     loc_180007D49
0x180007f12  mov     rcx, [rbx+8]; Handle
0x180007f16  xor     r8d, r8d; Timeout
0x180007f19  xor     edx, edx; Alertable
0x180007f1b  call    cs:__imp_NtWaitForSingleObject
0x180007f21  test    eax, eax
0x180007f23  jns     short loc_180007F36
0x180007f25  xor     r9d, r9d; lpArguments
0x180007f28  xor     r8d, r8d; nNumberOfArguments
0x180007f2b  xor     edx, edx; dwExceptionFlags
0x180007f2d  mov     ecx, eax; dwExceptionCode
0x180007f2f  call    cs:__imp_RaiseException
0x180007f35  int     3; Trap to Debugger
0x180007f36  mov     eax, dword ptr [rsp+98h+var_48]
0x180007f3a  jmp     short loc_180007EE8
0x180007f3c  xor     r9d, r9d; lpArguments
0x180007f3f  xor     r8d, r8d; nNumberOfArguments
0x180007f42  xor     edx, edx; dwExceptionFlags
0x180007f44  mov     ecx, 8DEAD001h; dwExceptionCode
0x180007f49  call    cs:__imp_RaiseException
0x180007f4f  int     3; Trap to Debugger
0x180007f50  add     rcx, 30h ; '0'; this
0x180007f54  call    ?Put@CEntropyRecorder@@QEAAXXZ; CEntropyRecorder::Put(void)
0x180007f59  jmp     short loc_180007F02
0x180007f5b  cmp     eax, 0C000026Eh
0x180007f60  jnz     short loc_180007F76
0x180007f62  xor     r9d, r9d; lpArguments
0x180007f65  xor     r8d, r8d; nNumberOfArguments
0x180007f68  xor     edx, edx; dwExceptionFlags
0x180007f6a  mov     ecx, 0C000026Eh; dwExceptionCode
0x180007f6f  call    cs:__imp_RaiseException
0x180007f75  int     3; Trap to Debugger
0x180007f76  xor     r9d, r9d; lpArguments
0x180007f79  xor     r8d, r8d; nNumberOfArguments
0x180007f7c  xor     edx, edx; dwExceptionFlags
0x180007f7e  mov     ecx, 8DEAD001h; dwExceptionCode
0x180007f83  call    cs:__imp_RaiseException
```
