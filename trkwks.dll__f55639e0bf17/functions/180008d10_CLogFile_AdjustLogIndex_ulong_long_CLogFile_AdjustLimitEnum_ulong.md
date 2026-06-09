# CLogFile::AdjustLogIndex(ulong *,long,CLogFile::AdjustLimitEnum,ulong)

- ea: `0x180008d10`
- end: `0x18000908b`
- name: `?AdjustLogIndex@CLogFile@@QEAAXPEAKJW4AdjustLimitEnum@1@K@Z`
- size: `891`
- prototype: `const struct tagLogEntry *__fastcall(__int64, unsigned int *, int)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x180007f90`
- `0x1800087c0`
- `0x18000eac0`

## callees

- `0x1800028f0`
- `0x180007cb0`
- `0x180008430`
- `0x180008d10`
- `0x18000d038`

## import_xrefs

- `ntdll!NtWriteFile` at `0x180008fa9`
- `ntdll!NtWriteFile` at `0x180008fa9`
- `ntdll!NtWaitForSingleObject` at `0x180008e87`
- `ntdll!NtWaitForSingleObject` at `0x180008ff3`
- `ntdll!NtWaitForSingleObject` at `0x180008e87`
- `ntdll!NtWaitForSingleObject` at `0x180008ff3`
- `ntdll!NtReadFile` at `0x180008e6e`
- `ntdll!NtReadFile` at `0x180008e6e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008ee1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008ee1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008f15`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008f15`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180008ec1`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180008ec1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009007`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009041`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009055`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009070`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009084`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009007`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009041`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009055`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009070`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009084`

## pseudocode

```c
const struct tagLogEntry *__fastcall CLogFile::AdjustLogIndex(__int64 a1, unsigned int *a2, int a3)
{
  const struct tagLogEntry *result; // rax
  unsigned int v4; // r14d
  void *Buffer; // r9
  void *v9; // r10
  int v10; // r8d
  unsigned int v11; // r15d
  unsigned int v12; // ecx
  ULONG Length; // ecx
  int v14; // r15d
  NTSTATUS v15; // eax
  struct CTrkWksSvc *v16; // rdi
  __int16 v17; // si
  __int64 v18; // rdx
  __int64 v19; // rax
  ULONG v20; // r8d
  union _LARGE_INTEGER v21; // rax
  signed int Status; // eax
  union _LARGE_INTEGER ByteOffset; // [rsp+50h] [rbp-58h] BYREF
  union _LARGE_INTEGER v24; // [rsp+58h] [rbp-50h] BYREF
  struct _IO_STATUS_BLOCK v25; // [rsp+60h] [rbp-48h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-38h] BYREF
  _UNKNOWN *retaddr; // [rsp+A8h] [rbp+0h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+B8h] [rbp+10h] BYREF

  result = (const struct tagLogEntry *)&retaddr;
  v4 = *a2;
  while ( a3 )
  {
    if ( a3 > 0 )
    {
      result = CLogFileSector::ReadLogEntry((CLogFileSector *)(a1 + 120), v4);
      --a3;
      v12 = *(_DWORD *)result;
    }
    else
    {
      Buffer = *(void **)(a1 + 152);
      if ( !Buffer || (v9 = *(void **)(a1 + 128)) == 0 )
        TrkRaiseWin32Error(110);
      v10 = *(_DWORD *)(a1 + 120);
      ByteOffset.QuadPart = 0;
      if ( (v10 & 1) == 0 || (v11 = *(_DWORD *)(a1 + 148), v4 < v11) || v4 >= v11 + *(_DWORD *)(a1 + 144) )
      {
        IoStatusBlock = 0;
        if ( (v10 & 1) != 0 && (v10 & 2) != 0 )
        {
          v20 = *(_DWORD *)(a1 + 140);
          v21.QuadPart = v20 * (*(_DWORD *)(a1 + 136) + *(_DWORD *)(a1 + 148) / *(_DWORD *)(a1 + 144));
          v25 = 0;
          v24 = v21;
          Status = NtWriteFile(v9, 0, 0, 0, &v25, Buffer, v20, &v24, 0);
          if ( Status == 259 )
          {
            Status = NtWaitForSingleObject(*(HANDLE *)(a1 + 128), 0, 0);
            if ( Status < 0 )
            {
LABEL_32:
              RaiseException(Status, 0, 0, 0);
              __debugbreak();
            }
            Status = v25.Status;
          }
          if ( Status < 0 )
            goto LABEL_32;
          if ( *(_DWORD *)(a1 + 140) != v25.Information )
          {
            RaiseException(0x8DEAD001, 0, 0, 0);
            __debugbreak();
          }
          if ( g_ptrkwks )
            CEntropyRecorder::Put((struct CTrkWksSvc *)((char *)g_ptrkwks + 48));
          CLogFileSector::RaiseIfNotOpen((CLogFileSector *)(a1 + 120));
          *(_DWORD *)(a1 + 120) &= ~2u;
        }
        Length = *(_DWORD *)(a1 + 140);
        v14 = v4 / *(_DWORD *)(a1 + 144) + *(_DWORD *)(a1 + 136);
        ByteOffset.QuadPart = Length * v14;
        v15 = NtReadFile(*(HANDLE *)(a1 + 128), 0, 0, 0, &IoStatusBlock, *(PVOID *)(a1 + 152), Length, &ByteOffset, 0);
        if ( v15 == 259 )
        {
          v15 = NtWaitForSingleObject(*(HANDLE *)(a1 + 128), 0, 0);
          if ( v15 < 0 )
            goto LABEL_37;
          v15 = IoStatusBlock.Status;
        }
        if ( v15 < 0 )
        {
LABEL_37:
          if ( v15 == -1073741202 )
          {
            RaiseException(0xC000026E, 0, 0, 0);
            __debugbreak();
          }
LABEL_39:
          RaiseException(0x8DEAD001, 0, 0, 0);
          JUMPOUT(0x18000908ALL);
        }
        v16 = g_ptrkwks;
        if ( g_ptrkwks )
        {
          PerformanceCount.QuadPart = 0;
          QueryPerformanceCounter(&PerformanceCount);
          v17 = LOWORD(PerformanceCount.LowPart)
              ^ WORD2(PerformanceCount.QuadPart)
              ^ ((PerformanceCount.LowPart ^ PerformanceCount.HighPart) >> 16);
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)v16 + 56));
          v18 = (unsigned __int8)*((_DWORD *)v16 + 24);
          *((_BYTE *)v16 + v18 + 104) ^= HIBYTE(v17);
          ++*((_DWORD *)v16 + 25);
          *((_DWORD *)v16 + 24) = v18 + 1;
          v19 = (unsigned __int8)(v18 + 1);
          *((_BYTE *)v16 + v19 + 104) ^= v17;
          ++*((_DWORD *)v16 + 25);
          *((_DWORD *)v16 + 24) = v19 + 1;
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v16 + 56));
        }
        if ( *(_DWORD *)(a1 + 140) != IoStatusBlock.Information )
          goto LABEL_39;
        v11 = *(_DWORD *)(a1 + 144) * (v14 - *(_DWORD *)(a1 + 136));
        *(_DWORD *)(a1 + 120) |= 1u;
        *(_DWORD *)(a1 + 148) = v11;
      }
      result = *(const struct tagLogEntry **)(a1 + 152);
      ++a3;
      v12 = *((_DWORD *)result + 31 * (v4 - v11) + 1);
    }
    if ( v12 >= *(_DWORD *)(a1 + 72) || v12 == v4 )
    {
      RaiseException(0x8DEAD001, 0, 0, 0);
      __debugbreak();
    }
    v4 = v12;
  }
  *a2 = v4;
  return result;
}

```

## disassembly

```asm
0x180008d10  mov     rax, rsp
0x180008d13  push    rbp
0x180008d14  push    rsi
0x180008d15  push    r12
0x180008d17  push    r13
0x180008d19  push    r14
0x180008d1b  sub     rsp, 80h
0x180008d22  mov     r14d, [rdx]
0x180008d25  mov     ebp, r8d
0x180008d28  mov     [rax+8], rbx
0x180008d2c  mov     r12, rdx
0x180008d2f  mov     [rax+18h], rdi
0x180008d33  mov     r13, rcx
0x180008d36  mov     [rax+20h], r15
0x180008d3a  xor     esi, esi
0x180008d3c  test    ebp, ebp
0x180008d3e  jnz     short loc_180008D6C
0x180008d40  mov     r15, [rsp+0A8h+arg_18]
0x180008d48  mov     rdi, [rsp+0A8h+arg_10]
0x180008d50  mov     rbx, [rsp+0A8h+arg_0]
0x180008d58  mov     [r12], r14d
0x180008d5c  add     rsp, 80h
0x180008d63  pop     r14
0x180008d65  pop     r13
0x180008d67  pop     r12
0x180008d69  pop     rsi
0x180008d6a  pop     rbp
0x180008d6b  retn
0x180008d6c  jg      loc_18000900E
0x180008d72  mov     r9, [r13+98h]
0x180008d79  test    r9, r9
0x180008d7c  jz      short loc_180008DED
0x180008d7e  mov     r10, [r13+80h]
0x180008d85  test    r10, r10
0x180008d88  jz      short loc_180008DED
0x180008d8a  mov     r8d, [r13+78h]
0x180008d8e  mov     edx, r8d
0x180008d91  shl     edx, 1Fh
0x180008d94  sar     edx, 1Fh
0x180008d97  mov     qword ptr [rsp+0A8h+var_58], rsi
0x180008d9c  test    edx, edx
0x180008d9e  jz      short loc_180008DF8
0x180008da0  mov     r15d, [r13+94h]
0x180008da7  cmp     r14d, r15d
0x180008daa  jb      short loc_180008DF8
0x180008dac  mov     ecx, [r13+90h]
0x180008db3  add     ecx, r15d
0x180008db6  cmp     r14d, ecx
0x180008db9  jnb     short loc_180008DF8
0x180008dbb  mov     eax, r14d
0x180008dbe  sub     eax, r15d
0x180008dc1  imul    rcx, rax, 7Ch ; '|'
0x180008dc5  mov     rax, [r13+98h]
0x180008dcc  inc     ebp
0x180008dce  mov     ecx, [rcx+rax+4]
0x180008dd2  cmp     ecx, [r13+48h]
0x180008dd6  jnb     loc_180009048
0x180008ddc  cmp     ecx, r14d
0x180008ddf  jz      loc_180009048
0x180008de5  mov     r14d, ecx
0x180008de8  jmp     loc_180008D3C
0x180008ded  mov     ecx, 6Eh ; 'n'; int
0x180008df2  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
0x180008df8  xorps   xmm0, xmm0
0x180008dfb  movups  xmmword ptr [rsp+0A8h+var_38], xmm0
0x180008e00  test    edx, edx
0x180008e02  jz      short loc_180008E0E
0x180008e04  test    r8b, 2
0x180008e08  jnz     loc_180008F4F
0x180008e0e  mov     ecx, [r13+8Ch]
0x180008e15  xor     edx, edx
0x180008e17  mov     r15d, [r13+88h]
0x180008e1e  mov     eax, r14d
0x180008e21  div     dword ptr [r13+90h]
0x180008e28  mov     [rsp+0A8h+Key], rsi; Key
0x180008e2d  xor     r9d, r9d; ApcContext
0x180008e30  add     r15d, eax
0x180008e33  xor     r8d, r8d; ApcRoutine
0x180008e36  mov     eax, r15d
0x180008e39  xor     edx, edx; Event
0x180008e3b  imul    eax, ecx
0x180008e3e  mov     qword ptr [rsp+0A8h+var_58], rax
0x180008e43  lea     rax, [rsp+0A8h+var_58]
0x180008e48  mov     [rsp+0A8h+ByteOffset], rax; ByteOffset
0x180008e4d  mov     rax, [r13+98h]
0x180008e54  mov     [rsp+0A8h+Length], ecx; Length
0x180008e58  mov     rcx, [r13+80h]; FileHandle
0x180008e5f  mov     [rsp+0A8h+Buffer], rax; Buffer
0x180008e64  lea     rax, [rsp+0A8h+var_38]
0x180008e69  mov     [rsp+0A8h+IoStatusBlock], rax; IoStatusBlock
0x180008e6e  call    cs:__imp_NtReadFile
0x180008e74  cmp     eax, 103h
0x180008e79  jnz     short loc_180008E99
0x180008e7b  mov     rcx, [r13+80h]; Handle
0x180008e82  xor     r8d, r8d; Timeout
0x180008e85  xor     edx, edx; Alertable
0x180008e87  call    cs:__imp_NtWaitForSingleObject
0x180008e8d  test    eax, eax
0x180008e8f  js      loc_18000905C
0x180008e95  mov     eax, dword ptr [rsp+0A8h+var_38]
0x180008e99  test    eax, eax
0x180008e9b  js      loc_18000905C
0x180008ea1  mov     rdi, cs:?g_ptrkwks@@3PEAVCTrkWksSvc@@EA; CTrkWksSvc * g_ptrkwks
0x180008ea8  test    rdi, rdi
0x180008eab  jz      short loc_180008F1D
0x180008ead  lea     rcx, [rsp+0A8h+PerformanceCount]; lpPerformanceCount
0x180008eb5  mov     qword ptr [rsp+0A8h+PerformanceCount], 0
0x180008ec1  call    cs:__imp_QueryPerformanceCounter
0x180008ec7  mov     eax, dword ptr [rsp+0A8h+PerformanceCount+4]
0x180008ece  lea     rcx, [rdi+38h]; lpCriticalSection
0x180008ed2  xor     eax, dword ptr [rsp+0A8h+PerformanceCount]
0x180008ed9  mov     esi, eax
0x180008edb  shr     esi, 10h
0x180008ede  xor     si, ax
0x180008ee1  call    cs:__imp_EnterCriticalSection
0x180008ee7  mov     eax, [rdi+60h]
0x180008eea  lea     rcx, [rdi+38h]; lpCriticalSection
0x180008eee  movzx   edx, al
0x180008ef1  movzx   eax, si
0x180008ef4  shr     ax, 8
0x180008ef8  xor     [rdx+rdi+68h], al
0x180008efc  lea     eax, [rdx+1]
0x180008eff  inc     dword ptr [rdi+64h]
0x180008f02  mov     [rdi+60h], eax
0x180008f05  movzx   eax, al
0x180008f08  xor     [rax+rdi+68h], sil
0x180008f0d  inc     dword ptr [rdi+64h]
0x180008f10  inc     eax
0x180008f12  mov     [rdi+60h], eax
0x180008f15  call    cs:__imp_LeaveCriticalSection
0x180008f1b  xor     esi, esi
0x180008f1d  mov     eax, [r13+8Ch]
0x180008f24  cmp     rax, [rsp+0A8h+var_38.Information]
0x180008f29  jnz     loc_180009077
0x180008f2f  sub     r15d, [r13+88h]
0x180008f36  imul    r15d, [r13+90h]
0x180008f3e  or      dword ptr [r13+78h], 1
0x180008f43  mov     [r13+94h], r15d
0x180008f4a  jmp     loc_180008DBB
0x180008f4f  mov     eax, [r13+94h]
0x180008f56  xor     edx, edx
0x180008f58  div     dword ptr [r13+90h]
0x180008f5f  mov     r8d, [r13+8Ch]
0x180008f66  xor     edx, edx; Event
0x180008f68  add     eax, [r13+88h]
0x180008f6f  mov     rcx, r10; FileHandle
0x180008f72  imul    eax, r8d
0x180008f76  mov     [rsp+0A8h+Key], rsi; Key
0x180008f7b  movups  xmmword ptr [rsp+0A8h+var_48], xmm0
0x180008f80  mov     qword ptr [rsp+0A8h+var_50], rax
0x180008f85  lea     rax, [rsp+0A8h+var_50]
0x180008f8a  mov     [rsp+0A8h+ByteOffset], rax; ByteOffset
0x180008f8f  lea     rax, [rsp+0A8h+var_48]
0x180008f94  mov     [rsp+0A8h+Length], r8d; Length
0x180008f99  xor     r8d, r8d; ApcRoutine
0x180008f9c  mov     [rsp+0A8h+Buffer], r9; Buffer
0x180008fa1  xor     r9d, r9d; ApcContext
0x180008fa4  mov     [rsp+0A8h+IoStatusBlock], rax; IoStatusBlock
0x180008fa9  call    cs:__imp_NtWriteFile
0x180008faf  cmp     eax, 103h
0x180008fb4  jz      short loc_180008FE7
0x180008fb6  test    eax, eax
0x180008fb8  js      short loc_180008FFD
0x180008fba  mov     eax, [r13+8Ch]
0x180008fc1  cmp     rax, [rsp+0A8h+var_48.Information]
0x180008fc6  jnz     short loc_180009034
0x180008fc8  mov     rcx, cs:?g_ptrkwks@@3PEAVCTrkWksSvc@@EA; CTrkWksSvc * g_ptrkwks
0x180008fcf  test    rcx, rcx
0x180008fd2  jnz     short loc_180009029
0x180008fd4  lea     rcx, [r13+78h]; this
0x180008fd8  call    ?RaiseIfNotOpen@CLogFileSector@@AEBAXXZ; CLogFileSector::RaiseIfNotOpen(void)
0x180008fdd  and     dword ptr [r13+78h], 0FFFFFFFDh
0x180008fe2  jmp     loc_180008E0E
0x180008fe7  mov     rcx, [r13+80h]; Handle
0x180008fee  xor     r8d, r8d; Timeout
0x180008ff1  xor     edx, edx; Alertable
0x180008ff3  call    cs:__imp_NtWaitForSingleObject
0x180008ff9  test    eax, eax
0x180008ffb  jns     short loc_180009023
0x180008ffd  xor     r9d, r9d; lpArguments
0x180009000  xor     r8d, r8d; nNumberOfArguments
0x180009003  xor     edx, edx; dwExceptionFlags
0x180009005  mov     ecx, eax; dwExceptionCode
0x180009007  call    cs:__imp_RaiseException
0x18000900d  int     3; Trap to Debugger
0x18000900e  mov     edx, r14d; unsigned int
0x180009011  lea     rcx, [r13+78h]; this
0x180009015  call    ?ReadLogEntry@CLogFileSector@@QEAAPEBUtagLogEntry@@K@Z; CLogFileSector::ReadLogEntry(ulong)
0x18000901a  dec     ebp
0x18000901c  mov     ecx, [rax]
0x18000901e  jmp     loc_180008DD2
0x180009023  mov     eax, dword ptr [rsp+0A8h+var_48]
0x180009027  jmp     short loc_180008FB6
0x180009029  add     rcx, 30h ; '0'; this
0x18000902d  call    ?Put@CEntropyRecorder@@QEAAXXZ; CEntropyRecorder::Put(void)
0x180009032  jmp     short loc_180008FD4
0x180009034  xor     r9d, r9d; lpArguments
0x180009037  xor     r8d, r8d; nNumberOfArguments
0x18000903a  xor     edx, edx; dwExceptionFlags
0x18000903c  mov     ecx, 8DEAD001h; dwExceptionCode
0x180009041  call    cs:__imp_RaiseException
0x180009047  int     3; Trap to Debugger
0x180009048  xor     r9d, r9d; lpArguments
0x18000904b  xor     r8d, r8d; nNumberOfArguments
0x18000904e  xor     edx, edx; dwExceptionFlags
0x180009050  mov     ecx, 8DEAD001h; dwExceptionCode
0x180009055  call    cs:__imp_RaiseException
0x18000905b  int     3; Trap to Debugger
0x18000905c  cmp     eax, 0C000026Eh
0x180009061  jnz     short loc_180009077
0x180009063  xor     r9d, r9d; lpArguments
0x180009066  xor     r8d, r8d; nNumberOfArguments
0x180009069  xor     edx, edx; dwExceptionFlags
0x18000906b  mov     ecx, 0C000026Eh; dwExceptionCode
0x180009070  call    cs:__imp_RaiseException
0x180009076  int     3; Trap to Debugger
0x180009077  xor     r9d, r9d; lpArguments
0x18000907a  xor     r8d, r8d; nNumberOfArguments
0x18000907d  xor     edx, edx; dwExceptionFlags
0x18000907f  mov     ecx, 8DEAD001h; dwExceptionCode
0x180009084  call    cs:__imp_RaiseException
```
