# CLogFileSector::LoadSector(ulong)

- ea: `0x180008460`
- end: `0x180008712`
- name: `?LoadSector@CLogFileSector@@AEAAXK@Z`
- size: `690`
- prototype: `void __fastcall(CLogFileSector *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x180007f90`
- `0x18000833c`
- `0x1800087c0`

## callees

- `0x1800028f0`
- `0x180008430`
- `0x180008460`
- `0x18000d038`

## import_xrefs

- `ntdll!NtWriteFile` at `0x180008663`
- `ntdll!NtWriteFile` at `0x180008663`
- `ntdll!NtWaitForSingleObject` at `0x18000853c`
- `ntdll!NtWaitForSingleObject` at `0x1800086a3`
- `ntdll!NtWaitForSingleObject` at `0x18000853c`
- `ntdll!NtWaitForSingleObject` at `0x1800086a3`
- `ntdll!NtReadFile` at `0x180008526`
- `ntdll!NtReadFile` at `0x180008526`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000859a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000859a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800085d4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800085d4`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000857a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000857a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800086b7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800086d1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800086f7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000870b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800086b7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800086d1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800086f7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000870b`

## pseudocode

```c
void __fastcall CLogFileSector::LoadSector(CLogFileSector *this, unsigned int a2)
{
  int v2; // r8d
  int v3; // eax
  int v5; // eax
  unsigned int v7; // edx
  void *Buffer; // r9
  void *v9; // rcx
  ULONG Length; // ecx
  int v11; // ebp
  NTSTATUS Status; // eax
  struct CTrkWksSvc *v13; // r14
  __int16 v14; // di
  __int64 v15; // rdx
  __int64 v16; // rax
  int v17; // ebp
  ULONG v18; // r8d
  LARGE_INTEGER v19; // rax
  signed int v20; // eax
  struct _IO_STATUS_BLOCK v21; // [rsp+50h] [rbp-38h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-28h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+90h] [rbp+8h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+A0h] [rbp+18h] BYREF

  v2 = *(_DWORD *)this;
  v3 = *(_DWORD *)this;
  ByteOffset.QuadPart = 0;
  v5 = v3 << 31 >> 31;
  if ( !v5 || (v7 = *((_DWORD *)this + 7), a2 < v7) || a2 >= *((_DWORD *)this + 6) + v7 )
  {
    Buffer = (void *)*((_QWORD *)this + 4);
    IoStatusBlock = 0;
    if ( !Buffer || (v9 = (void *)*((_QWORD *)this + 1)) == 0 )
      TrkRaiseWin32Error(110);
    if ( !v5 || (v2 & 2) == 0 )
    {
LABEL_8:
      Length = *((_DWORD *)this + 5);
      v11 = a2 / *((_DWORD *)this + 6) + *((_DWORD *)this + 4);
      ByteOffset.QuadPart = Length * v11;
      Status = NtReadFile(*((HANDLE *)this + 1), 0, 0, 0, &IoStatusBlock, *((PVOID *)this + 4), Length, &ByteOffset, 0);
      if ( Status == 259 )
      {
        Status = NtWaitForSingleObject(*((HANDLE *)this + 1), 0, 0);
        if ( Status < 0 )
          goto LABEL_27;
        Status = IoStatusBlock.Status;
      }
      if ( Status >= 0 )
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
          v17 = *((_DWORD *)this + 6) * (v11 - *((_DWORD *)this + 4));
          *(_DWORD *)this |= 1u;
          *((_DWORD *)this + 7) = v17;
          return;
        }
LABEL_29:
        RaiseException(0x8DEAD001, 0, 0, 0);
        JUMPOUT(0x180008711LL);
      }
LABEL_27:
      if ( Status == -1073741202 )
      {
        RaiseException(0xC000026E, 0, 0, 0);
        __debugbreak();
      }
      goto LABEL_29;
    }
    v18 = *((_DWORD *)this + 5);
    v19.QuadPart = v18 * (*((_DWORD *)this + 4) + *((_DWORD *)this + 7) / *((_DWORD *)this + 6));
    v21 = 0;
    PerformanceCount = v19;
    v20 = NtWriteFile(v9, 0, 0, 0, &v21, Buffer, v18, &PerformanceCount, 0);
    if ( v20 == 259 )
    {
      v20 = NtWaitForSingleObject(*((HANDLE *)this + 1), 0, 0);
      if ( v20 < 0 )
        goto LABEL_24;
      v20 = v21.Status;
    }
    if ( v20 >= 0 )
    {
      if ( *((_DWORD *)this + 5) != v21.Information )
      {
        RaiseException(0x8DEAD001, 0, 0, 0);
        __debugbreak();
      }
      if ( g_ptrkwks )
        CEntropyRecorder::Put((struct CTrkWksSvc *)((char *)g_ptrkwks + 48));
      CLogFileSector::RaiseIfNotOpen(this);
      *(_DWORD *)this &= ~2u;
      goto LABEL_8;
    }
LABEL_24:
    RaiseException(v20, 0, 0, 0);
    __debugbreak();
  }
}

```

## disassembly

```asm
0x180008460  push    rbx
0x180008462  push    rsi
0x180008463  push    rdi
0x180008464  sub     rsp, 70h
0x180008468  mov     r8d, [rcx]
0x18000846b  xor     edi, edi
0x18000846d  mov     eax, r8d
0x180008470  mov     qword ptr [rsp+88h+arg_10], rdi
0x180008478  shl     eax, 1Fh
0x18000847b  mov     ebx, edx
0x18000847d  sar     eax, 1Fh
0x180008480  mov     rsi, rcx
0x180008483  test    eax, eax
0x180008485  jz      short loc_18000849D
0x180008487  mov     edx, [rcx+1Ch]
0x18000848a  cmp     ebx, edx
0x18000848c  jb      short loc_18000849D
0x18000848e  add     edx, [rcx+18h]
0x180008491  cmp     ebx, edx
0x180008493  jnb     short loc_18000849D
0x180008495  add     rsp, 70h
0x180008499  pop     rdi
0x18000849a  pop     rsi
0x18000849b  pop     rbx
0x18000849c  retn
0x18000849d  mov     r9, [rcx+20h]
0x1800084a1  xorps   xmm0, xmm0
0x1800084a4  movups  xmmword ptr [rsp+88h+var_28], xmm0
0x1800084a9  test    r9, r9
0x1800084ac  jz      loc_18000860A
0x1800084b2  mov     rcx, [rcx+8]; FileHandle
0x1800084b6  test    rcx, rcx
0x1800084b9  jz      loc_18000860A
0x1800084bf  test    eax, eax
0x1800084c1  jz      short loc_1800084CD
0x1800084c3  test    r8b, 2
0x1800084c7  jnz     loc_180008615
0x1800084cd  mov     ecx, [rsi+14h]
0x1800084d0  xor     edx, edx
0x1800084d2  mov     eax, ebx
0x1800084d4  mov     [rsp+88h+Key], rdi; Key
0x1800084d9  div     dword ptr [rsi+18h]
0x1800084dc  mov     [rsp+88h+arg_8], rbp
0x1800084e4  xor     r9d, r9d; ApcContext
0x1800084e7  mov     ebp, [rsi+10h]
0x1800084ea  xor     r8d, r8d; ApcRoutine
0x1800084ed  add     ebp, eax
0x1800084ef  xor     edx, edx; Event
0x1800084f1  mov     eax, ebp
0x1800084f3  imul    eax, ecx
0x1800084f6  mov     qword ptr [rsp+88h+arg_10], rax
0x1800084fe  lea     rax, [rsp+88h+arg_10]
0x180008506  mov     [rsp+88h+ByteOffset], rax; ByteOffset
0x18000850b  mov     rax, [rsi+20h]
0x18000850f  mov     [rsp+88h+Length], ecx; Length
0x180008513  mov     rcx, [rsi+8]; FileHandle
0x180008517  mov     [rsp+88h+Buffer], rax; Buffer
0x18000851c  lea     rax, [rsp+88h+var_28]
0x180008521  mov     [rsp+88h+IoStatusBlock], rax; IoStatusBlock
0x180008526  call    cs:__imp_NtReadFile
0x18000852c  cmp     eax, 103h
0x180008531  jnz     short loc_18000854E
0x180008533  mov     rcx, [rsi+8]; Handle
0x180008537  xor     r8d, r8d; Timeout
0x18000853a  xor     edx, edx; Alertable
0x18000853c  call    cs:__imp_NtWaitForSingleObject
0x180008542  test    eax, eax
0x180008544  js      loc_1800086E3
0x18000854a  mov     eax, dword ptr [rsp+88h+var_28]
0x18000854e  test    eax, eax
0x180008550  js      loc_1800086E3
0x180008556  mov     [rsp+88h+arg_18], r14
0x18000855e  mov     r14, cs:?g_ptrkwks@@3PEAVCTrkWksSvc@@EA; CTrkWksSvc * g_ptrkwks
0x180008565  test    r14, r14
0x180008568  jz      short loc_1800085DA
0x18000856a  lea     rcx, [rsp+88h+PerformanceCount]; lpPerformanceCount
0x180008572  mov     qword ptr [rsp+88h+PerformanceCount], rdi
0x18000857a  call    cs:__imp_QueryPerformanceCounter
0x180008580  mov     eax, dword ptr [rsp+88h+PerformanceCount+4]
0x180008587  lea     rcx, [r14+38h]; lpCriticalSection
0x18000858b  xor     eax, dword ptr [rsp+88h+PerformanceCount]
0x180008592  mov     edi, eax
0x180008594  shr     edi, 10h
0x180008597  xor     di, ax
0x18000859a  call    cs:__imp_EnterCriticalSection
0x1800085a0  mov     eax, [r14+60h]
0x1800085a4  lea     rcx, [r14+38h]; lpCriticalSection
0x1800085a8  movzx   edx, al
0x1800085ab  movzx   eax, di
0x1800085ae  shr     ax, 8
0x1800085b2  xor     [rdx+r14+68h], al
0x1800085b7  lea     eax, [rdx+1]
0x1800085ba  inc     dword ptr [r14+64h]
0x1800085be  mov     [r14+60h], eax
0x1800085c2  movzx   eax, al
0x1800085c5  xor     [rax+r14+68h], dil
0x1800085ca  inc     dword ptr [r14+64h]
0x1800085ce  inc     eax
0x1800085d0  mov     [r14+60h], eax
0x1800085d4  call    cs:__imp_LeaveCriticalSection
0x1800085da  mov     eax, [rsi+14h]
0x1800085dd  mov     r14, [rsp+88h+arg_18]
0x1800085e5  cmp     rax, [rsp+88h+var_28.Information]
0x1800085ea  jnz     loc_1800086FE
0x1800085f0  sub     ebp, [rsi+10h]
0x1800085f3  imul    ebp, [rsi+18h]
0x1800085f7  or      dword ptr [rsi], 1
0x1800085fa  mov     [rsi+1Ch], ebp
0x1800085fd  mov     rbp, [rsp+88h+arg_8]
0x180008605  jmp     loc_180008495
0x18000860a  mov     ecx, 6Eh ; 'n'; int
0x18000860f  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
0x180008615  mov     eax, [rsi+1Ch]
0x180008618  xor     edx, edx
0x18000861a  div     dword ptr [rsi+18h]
0x18000861d  mov     r8d, [rsi+14h]
0x180008621  xor     edx, edx; Event
0x180008623  add     eax, [rsi+10h]
0x180008626  imul    eax, r8d
0x18000862a  mov     [rsp+88h+Key], rdi; Key
0x18000862f  movups  xmmword ptr [rsp+88h+var_38], xmm0
0x180008634  mov     qword ptr [rsp+88h+PerformanceCount], rax
0x18000863c  lea     rax, [rsp+88h+PerformanceCount]
0x180008644  mov     [rsp+88h+ByteOffset], rax; ByteOffset
0x180008649  lea     rax, [rsp+88h+var_38]
0x18000864e  mov     [rsp+88h+Length], r8d; Length
0x180008653  xor     r8d, r8d; ApcRoutine
0x180008656  mov     [rsp+88h+Buffer], r9; Buffer
0x18000865b  xor     r9d, r9d; ApcContext
0x18000865e  mov     [rsp+88h+IoStatusBlock], rax; IoStatusBlock
0x180008663  call    cs:__imp_NtWriteFile
0x180008669  cmp     eax, 103h
0x18000866e  jz      short loc_18000869A
0x180008670  test    eax, eax
0x180008672  js      short loc_1800086AD
0x180008674  mov     eax, [rsi+14h]
0x180008677  cmp     rax, [rsp+88h+var_38.Information]
0x18000867c  jnz     short loc_1800086C4
0x18000867e  mov     rcx, cs:?g_ptrkwks@@3PEAVCTrkWksSvc@@EA; CTrkWksSvc * g_ptrkwks
0x180008685  test    rcx, rcx
0x180008688  jnz     short loc_1800086D8
0x18000868a  mov     rcx, rsi; this
0x18000868d  call    ?RaiseIfNotOpen@CLogFileSector@@AEBAXXZ; CLogFileSector::RaiseIfNotOpen(void)
0x180008692  and     dword ptr [rsi], 0FFFFFFFDh
0x180008695  jmp     loc_1800084CD
0x18000869a  mov     rcx, [rsi+8]; Handle
0x18000869e  xor     r8d, r8d; Timeout
0x1800086a1  xor     edx, edx; Alertable
0x1800086a3  call    cs:__imp_NtWaitForSingleObject
0x1800086a9  test    eax, eax
0x1800086ab  jns     short loc_1800086BE
0x1800086ad  xor     r9d, r9d; lpArguments
0x1800086b0  xor     r8d, r8d; nNumberOfArguments
0x1800086b3  xor     edx, edx; dwExceptionFlags
0x1800086b5  mov     ecx, eax; dwExceptionCode
0x1800086b7  call    cs:__imp_RaiseException
0x1800086bd  int     3; Trap to Debugger
0x1800086be  mov     eax, dword ptr [rsp+88h+var_38]
0x1800086c2  jmp     short loc_180008670
0x1800086c4  xor     r9d, r9d; lpArguments
0x1800086c7  xor     r8d, r8d; nNumberOfArguments
0x1800086ca  xor     edx, edx; dwExceptionFlags
0x1800086cc  mov     ecx, 8DEAD001h; dwExceptionCode
0x1800086d1  call    cs:__imp_RaiseException
0x1800086d7  int     3; Trap to Debugger
0x1800086d8  add     rcx, 30h ; '0'; this
0x1800086dc  call    ?Put@CEntropyRecorder@@QEAAXXZ; CEntropyRecorder::Put(void)
0x1800086e1  jmp     short loc_18000868A
0x1800086e3  cmp     eax, 0C000026Eh
0x1800086e8  jnz     short loc_1800086FE
0x1800086ea  xor     r9d, r9d; lpArguments
0x1800086ed  xor     r8d, r8d; nNumberOfArguments
0x1800086f0  xor     edx, edx; dwExceptionFlags
0x1800086f2  mov     ecx, 0C000026Eh; dwExceptionCode
0x1800086f7  call    cs:__imp_RaiseException
0x1800086fd  int     3; Trap to Debugger
0x1800086fe  xor     r9d, r9d; lpArguments
0x180008701  xor     r8d, r8d; nNumberOfArguments
0x180008704  xor     edx, edx; dwExceptionFlags
0x180008706  mov     ecx, 8DEAD001h; dwExceptionCode
0x18000870b  call    cs:__imp_RaiseException
```
