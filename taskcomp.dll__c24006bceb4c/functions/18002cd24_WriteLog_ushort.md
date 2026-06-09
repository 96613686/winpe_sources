# WriteLog(ushort *)

- ea: `0x18002cd24`
- end: `0x18002ceaa`
- name: `?WriteLog@@YAXPEAG@Z`
- size: `390`
- prototype: `void __fastcall(LPCVOID lpBuffer)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18002c33c`
- `0x18002c520`

## callees

- `0x18002cbb0`
- `0x18002cd24`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002cd6d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002cd6d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ce93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ce93`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18002cdd1`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18002cdd1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002ce0d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002ce66`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002ce0d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002ce66`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002cd9c`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002cde8`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002ce2e`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002ce86`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002cd9c`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002cde8`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002ce2e`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002ce86`

## pseudocode

```c
void __fastcall WriteLog(_WORD *lpBuffer)
{
  __int64 v2; // rbx
  __int64 v3; // rax
  DWORD v4; // esi
  DWORD v5; // r8d
  DWORD NumberOfBytesWritten; // [rsp+68h] [rbp+38h] BYREF
  __int64 DistanceToMoveHigh; // [rsp+70h] [rbp+40h] BYREF

  if ( ghLog )
  {
    v2 = -1;
    DistanceToMoveHigh = 0;
    v3 = -1;
    NumberOfBytesWritten = 0;
    do
      ++v3;
    while ( lpBuffer[v3] );
    v4 = 2 * v3;
    EnterCriticalSection(&gcsLogCritSection);
    do
      ++v2;
    while ( *(&Buffer + v2) );
    DistanceToMoveHigh = 0;
    LODWORD(DistanceToMoveHigh) = SetFilePointer(ghLog, 0, (PLONG)&DistanceToMoveHigh + 1, 1u);
    if ( (_DWORD)DistanceToMoveHigh != -1 )
    {
      DistanceToMoveHigh += v4 + 2 * (_DWORD)v2;
      if ( DistanceToMoveHigh <= gdwMaxLogSizeKB << 10 || (SetEndOfFile(ghLog), SetFilePointer(ghLog, 2, 0, 0) != -1) )
      {
        if ( WriteFile(ghLog, lpBuffer, v4, &NumberOfBytesWritten, 0) )
        {
          DistanceToMoveHigh = 0;
          LODWORD(DistanceToMoveHigh) = SetFilePointer(ghLog, 0, (PLONG)&DistanceToMoveHigh + 1, 1u);
          if ( (_DWORD)DistanceToMoveHigh != -1 )
          {
            v5 = gcbMostRecentEntryMarkerSize;
            if ( gcbMostRecentEntryMarkerSize > 0x81 )
              v5 = 128;
            if ( WriteFile(ghLog, &Buffer, v5, &NumberOfBytesWritten, 0) )
            {
              OverwriteRecordFragment();
              SetFilePointer(ghLog, DistanceToMoveHigh, (PLONG)&DistanceToMoveHigh + 1, 0);
            }
          }
        }
      }
    }
    LeaveCriticalSection(&gcsLogCritSection);
  }
}

```

## disassembly

```asm
0x18002cd24  mov     [rsp-28h+arg_0], rbx
0x18002cd29  push    rbp
0x18002cd2a  push    rsi
0x18002cd2b  push    rdi
0x18002cd2c  push    r13
0x18002cd2e  push    r14
0x18002cd30  mov     rbp, rsp
0x18002cd33  sub     rsp, 30h
0x18002cd37  xor     r14d, r14d
0x18002cd3a  mov     rdi, rcx
0x18002cd3d  cmp     cs:?ghLog@@3PEAXEA, r14; void * ghLog
0x18002cd44  jz      loc_18002CE99
0x18002cd4a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002cd4e  mov     qword ptr [rbp+DistanceToMoveHigh], r14
0x18002cd52  mov     rax, rbx
0x18002cd55  mov     [rbp+NumberOfBytesWritten], r14d
0x18002cd59  inc     rax
0x18002cd5c  cmp     [rcx+rax*2], r14w
0x18002cd61  jnz     short loc_18002CD59
0x18002cd63  lea     rcx, ?gcsLogCritSection@@3VCStaticCritSec@@A; lpCriticalSection
0x18002cd6a  lea     esi, [rax+rax]
0x18002cd6d  call    cs:__imp_EnterCriticalSection
0x18002cd73  lea     r13, Buffer
0x18002cd7a  inc     rbx
0x18002cd7d  cmp     [r13+rbx*2+0], r14w
0x18002cd83  jnz     short loc_18002CD7A
0x18002cd85  mov     rcx, cs:?ghLog@@3PEAXEA; hFile
0x18002cd8c  lea     r8, [rbp+arg_14]; lpDistanceToMoveHigh
0x18002cd90  mov     r9d, 1; dwMoveMethod
0x18002cd96  mov     qword ptr [rbp+DistanceToMoveHigh], r14
0x18002cd9a  xor     edx, edx; lDistanceToMove
0x18002cd9c  call    cs:__imp_SetFilePointer
0x18002cda2  mov     [rbp+DistanceToMoveHigh], eax
0x18002cda5  cmp     eax, 0FFFFFFFFh
0x18002cda8  jz      loc_18002CE8C
0x18002cdae  mov     rax, qword ptr [rbp+DistanceToMoveHigh]
0x18002cdb2  lea     ecx, [rsi+rbx*2]
0x18002cdb5  add     rax, rcx
0x18002cdb8  mov     ecx, cs:?gdwMaxLogSizeKB@@3KA; ulong gdwMaxLogSizeKB
0x18002cdbe  shl     ecx, 0Ah
0x18002cdc1  mov     qword ptr [rbp+DistanceToMoveHigh], rax
0x18002cdc5  cmp     rax, rcx
0x18002cdc8  jle     short loc_18002CDF7
0x18002cdca  mov     rcx, cs:?ghLog@@3PEAXEA; hFile
0x18002cdd1  call    cs:__imp_SetEndOfFile
0x18002cdd7  mov     rcx, cs:?ghLog@@3PEAXEA; hFile
0x18002cdde  xor     r9d, r9d; dwMoveMethod
0x18002cde1  xor     r8d, r8d; lpDistanceToMoveHigh
0x18002cde4  lea     edx, [r9+2]; lDistanceToMove
0x18002cde8  call    cs:__imp_SetFilePointer
0x18002cdee  cmp     eax, 0FFFFFFFFh
0x18002cdf1  jz      loc_18002CE8C
0x18002cdf7  mov     rcx, cs:?ghLog@@3PEAXEA; hFile
0x18002cdfe  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18002ce02  mov     r8d, esi; nNumberOfBytesToWrite
0x18002ce05  mov     [rsp+30h+lpOverlapped], r14; lpOverlapped
0x18002ce0a  mov     rdx, rdi; lpBuffer
0x18002ce0d  call    cs:__imp_WriteFile
0x18002ce13  test    eax, eax
0x18002ce15  jz      short loc_18002CE8C
0x18002ce17  mov     rcx, cs:?ghLog@@3PEAXEA; hFile
0x18002ce1e  lea     r8, [rbp+arg_14]; lpDistanceToMoveHigh
0x18002ce22  mov     r9d, 1; dwMoveMethod
0x18002ce28  mov     qword ptr [rbp+DistanceToMoveHigh], r14
0x18002ce2c  xor     edx, edx; lDistanceToMove
0x18002ce2e  call    cs:__imp_SetFilePointer
0x18002ce34  mov     [rbp+DistanceToMoveHigh], eax
0x18002ce37  cmp     eax, 0FFFFFFFFh
0x18002ce3a  jz      short loc_18002CE8C
0x18002ce3c  mov     r8d, cs:?gcbMostRecentEntryMarkerSize@@3KA; ulong gcbMostRecentEntryMarkerSize
0x18002ce43  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18002ce47  mov     rcx, cs:?ghLog@@3PEAXEA; hFile
0x18002ce4e  cmp     r8d, 81h
0x18002ce55  mov     eax, 80h
0x18002ce5a  mov     [rsp+30h+lpOverlapped], r14; lpOverlapped
0x18002ce5f  cmova   r8d, eax; nNumberOfBytesToWrite
0x18002ce63  mov     rdx, r13; lpBuffer
0x18002ce66  call    cs:__imp_WriteFile
0x18002ce6c  test    eax, eax
0x18002ce6e  jz      short loc_18002CE8C
0x18002ce70  call    ?OverwriteRecordFragment@@YAXXZ; OverwriteRecordFragment(void)
0x18002ce75  mov     edx, [rbp+DistanceToMoveHigh]; lDistanceToMove
0x18002ce78  lea     r8, [rbp+arg_14]; lpDistanceToMoveHigh
0x18002ce7c  mov     rcx, cs:?ghLog@@3PEAXEA; hFile
0x18002ce83  xor     r9d, r9d; dwMoveMethod
0x18002ce86  call    cs:__imp_SetFilePointer
0x18002ce8c  lea     rcx, ?gcsLogCritSection@@3VCStaticCritSec@@A; lpCriticalSection
0x18002ce93  call    cs:__imp_LeaveCriticalSection
0x18002ce99  mov     rbx, [rsp+30h+arg_0]
0x18002ce9e  add     rsp, 30h
0x18002cea2  pop     r14
0x18002cea4  pop     r13
0x18002cea6  pop     rdi
0x18002cea7  pop     rsi
0x18002cea8  pop     rbp
0x18002cea9  retn
```
