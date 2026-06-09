# CLogFileSector::Flush(void)

- ea: `0x180008230`
- end: `0x180008336`
- name: `?Flush@CLogFileSector@@QEAAXXZ`
- size: `262`
- prototype: `void __fastcall(CLogFileSector *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x180007f90`
- `0x180009ce8`
- `0x18000d790`
- `0x18000eac0`

## callees

- `0x1800028f0`
- `0x180008230`
- `0x180008430`
- `0x18000d038`

## import_xrefs

- `ntdll!NtWriteFile` at `0x1800082b5`
- `ntdll!NtWriteFile` at `0x1800082b5`
- `ntdll!NtWaitForSingleObject` at `0x1800082f6`
- `ntdll!NtWaitForSingleObject` at `0x1800082f6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000830a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008324`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000830a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008324`

## pseudocode

```c
void __fastcall CLogFileSector::Flush(CLogFileSector *this)
{
  void *Buffer; // r9
  void *v3; // rcx
  ULONG Length; // r8d
  union _LARGE_INTEGER v5; // rax
  signed int Status; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-18h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+70h] [rbp+8h] BYREF

  Buffer = (void *)*((_QWORD *)this + 4);
  if ( !Buffer || (v3 = (void *)*((_QWORD *)this + 1)) == 0 )
    TrkRaiseWin32Error(110);
  if ( (*(_DWORD *)this & 1) != 0 && (*(_DWORD *)this & 2) != 0 )
  {
    Length = *((_DWORD *)this + 5);
    v5.QuadPart = Length * (*((_DWORD *)this + 4) + *((_DWORD *)this + 7) / *((_DWORD *)this + 6));
    IoStatusBlock = 0;
    ByteOffset = v5;
    Status = NtWriteFile(v3, 0, 0, 0, &IoStatusBlock, Buffer, Length, &ByteOffset, 0);
    if ( Status == 259 )
    {
      Status = NtWaitForSingleObject(*((HANDLE *)this + 1), 0, 0);
      if ( Status < 0 )
        goto LABEL_14;
      Status = IoStatusBlock.Status;
    }
    if ( Status >= 0 )
    {
      if ( *((_DWORD *)this + 5) != IoStatusBlock.Information )
      {
        RaiseException(0x8DEAD001, 0, 0, 0);
        __debugbreak();
      }
      if ( g_ptrkwks )
        CEntropyRecorder::Put((struct CTrkWksSvc *)((char *)g_ptrkwks + 48));
      CLogFileSector::RaiseIfNotOpen(this);
      *(_DWORD *)this &= ~2u;
      return;
    }
LABEL_14:
    RaiseException(Status, 0, 0, 0);
    __debugbreak();
  }
}

```

## disassembly

```asm
0x180008230  push    rbx
0x180008232  sub     rsp, 60h
0x180008236  mov     r9, [rcx+20h]
0x18000823a  mov     rbx, rcx
0x18000823d  test    r9, r9
0x180008240  jz      short loc_18000825B
0x180008242  mov     rcx, [rcx+8]; FileHandle
0x180008246  test    rcx, rcx
0x180008249  jz      short loc_18000825B
0x18000824b  mov     eax, [rbx]
0x18000824d  test    al, 1
0x18000824f  jz      short loc_180008255
0x180008251  test    al, 2
0x180008253  jnz     short loc_180008266
0x180008255  add     rsp, 60h
0x180008259  pop     rbx
0x18000825a  retn
0x18000825b  mov     ecx, 6Eh ; 'n'; int
0x180008260  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
0x180008266  mov     eax, [rbx+1Ch]
0x180008269  xor     edx, edx
0x18000826b  div     dword ptr [rbx+18h]
0x18000826e  mov     r8d, [rbx+14h]
0x180008272  xorps   xmm0, xmm0
0x180008275  add     eax, [rbx+10h]
0x180008278  xor     edx, edx; Event
0x18000827a  imul    eax, r8d
0x18000827e  mov     [rsp+68h+Key], 0; Key
0x180008287  movups  xmmword ptr [rsp+68h+var_18], xmm0
0x18000828c  mov     qword ptr [rsp+68h+arg_0], rax
0x180008291  lea     rax, [rsp+68h+arg_0]
0x180008296  mov     [rsp+68h+ByteOffset], rax; ByteOffset
0x18000829b  lea     rax, [rsp+68h+var_18]
0x1800082a0  mov     [rsp+68h+Length], r8d; Length
0x1800082a5  xor     r8d, r8d; ApcRoutine
0x1800082a8  mov     [rsp+68h+Buffer], r9; Buffer
0x1800082ad  xor     r9d, r9d; ApcContext
0x1800082b0  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x1800082b5  call    cs:__imp_NtWriteFile
0x1800082bb  cmp     eax, 103h
0x1800082c0  jz      short loc_1800082ED
0x1800082c2  test    eax, eax
0x1800082c4  js      short loc_180008300
0x1800082c6  mov     eax, [rbx+14h]
0x1800082c9  cmp     rax, [rsp+68h+var_18.Information]
0x1800082ce  jnz     short loc_180008317
0x1800082d0  mov     rcx, cs:?g_ptrkwks@@3PEAVCTrkWksSvc@@EA; CTrkWksSvc * g_ptrkwks
0x1800082d7  test    rcx, rcx
0x1800082da  jnz     short loc_18000832B
0x1800082dc  mov     rcx, rbx; this
0x1800082df  call    ?RaiseIfNotOpen@CLogFileSector@@AEBAXXZ; CLogFileSector::RaiseIfNotOpen(void)
0x1800082e4  and     dword ptr [rbx], 0FFFFFFFDh
0x1800082e7  add     rsp, 60h
0x1800082eb  pop     rbx
0x1800082ec  retn
0x1800082ed  mov     rcx, [rbx+8]; Handle
0x1800082f1  xor     r8d, r8d; Timeout
0x1800082f4  xor     edx, edx; Alertable
0x1800082f6  call    cs:__imp_NtWaitForSingleObject
0x1800082fc  test    eax, eax
0x1800082fe  jns     short loc_180008311
0x180008300  xor     r9d, r9d; lpArguments
0x180008303  xor     r8d, r8d; nNumberOfArguments
0x180008306  xor     edx, edx; dwExceptionFlags
0x180008308  mov     ecx, eax; dwExceptionCode
0x18000830a  call    cs:__imp_RaiseException
0x180008310  int     3; Trap to Debugger
0x180008311  mov     eax, dword ptr [rsp+68h+var_18]
0x180008315  jmp     short loc_1800082C2
0x180008317  xor     r9d, r9d; lpArguments
0x18000831a  xor     r8d, r8d; nNumberOfArguments
0x18000831d  xor     edx, edx; dwExceptionFlags
0x18000831f  mov     ecx, 8DEAD001h; dwExceptionCode
0x180008324  call    cs:__imp_RaiseException
0x18000832a  int     3; Trap to Debugger
0x18000832b  add     rcx, 30h ; '0'; this
0x18000832f  call    ?Put@CEntropyRecorder@@QEAAXXZ; CEntropyRecorder::Put(void)
0x180008334  jmp     short loc_1800082DC
```
