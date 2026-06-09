# WriteLog(ushort *)

- ea: `0x18002ebd4`
- end: `0x18002ed95`
- name: `?WriteLog@@YAXPEAG@Z`
- size: `449`
- prototype: `void __fastcall(LPCVOID lpBuffer)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18002e0f8`
- `0x18002e304`

## callees

- `0x18002ea44`
- `0x18002ebd4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ec1d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ec1d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ed77`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ed77`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18002ec8d`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18002ec8d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002ecd5`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002ed3e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002ecd5`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002ed3e`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002ec52`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002ecaa`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002ed00`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002ed64`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002ec52`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002ecaa`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002ed00`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002ed64`

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
0x18002ebd4  mov     [rsp-28h+arg_0], rbx
0x18002ebd9  push    rbp
0x18002ebda  push    rsi
0x18002ebdb  push    rdi
0x18002ebdc  push    r13
0x18002ebde  push    r14
0x18002ebe0  mov     rbp, rsp
0x18002ebe3  sub     rsp, 30h
0x18002ebe7  xor     r14d, r14d
0x18002ebea  mov     rdi, rcx
0x18002ebed  cmp     cs:?ghLog@@3PEAXEA, r14; void * ghLog
0x18002ebf4  jz      loc_18002ED83
0x18002ebfa  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002ebfe  mov     qword ptr [rbp+DistanceToMoveHigh], r14
0x18002ec02  mov     rax, rbx
0x18002ec05  mov     [rbp+NumberOfBytesWritten], r14d
0x18002ec09  inc     rax
0x18002ec0c  cmp     [rcx+rax*2], r14w
0x18002ec11  jnz     short loc_18002EC09
0x18002ec13  lea     rcx, ?gcsLogCritSection@@3VCStaticCritSec@@A; lpCriticalSection
0x18002ec1a  lea     esi, [rax+rax]
0x18002ec1d  call    cs:__imp_EnterCriticalSection
0x18002ec24  nop     dword ptr [rax+rax+00h]
0x18002ec29  lea     r13, Buffer
0x18002ec30  inc     rbx
0x18002ec33  cmp     [r13+rbx*2+0], r14w
0x18002ec39  jnz     short loc_18002EC30
0x18002ec3b  mov     rcx, cs:?ghLog@@3PEAXEA; hFile
0x18002ec42  lea     r8, [rbp+arg_14]; lpDistanceToMoveHigh
0x18002ec46  mov     r9d, 1; dwMoveMethod
0x18002ec4c  mov     qword ptr [rbp+DistanceToMoveHigh], r14
0x18002ec50  xor     edx, edx; lDistanceToMove
0x18002ec52  call    cs:__imp_SetFilePointer
0x18002ec59  nop     dword ptr [rax+rax+00h]
0x18002ec5e  mov     [rbp+DistanceToMoveHigh], eax
0x18002ec61  cmp     eax, 0FFFFFFFFh
0x18002ec64  jz      loc_18002ED70
0x18002ec6a  mov     rax, qword ptr [rbp+DistanceToMoveHigh]
0x18002ec6e  lea     ecx, [rsi+rbx*2]
0x18002ec71  add     rax, rcx
0x18002ec74  mov     ecx, cs:?gdwMaxLogSizeKB@@3KA; ulong gdwMaxLogSizeKB
0x18002ec7a  shl     ecx, 0Ah
0x18002ec7d  mov     qword ptr [rbp+DistanceToMoveHigh], rax
0x18002ec81  cmp     rax, rcx
0x18002ec84  jle     short loc_18002ECBF
0x18002ec86  mov     rcx, cs:?ghLog@@3PEAXEA; hFile
0x18002ec8d  call    cs:__imp_SetEndOfFile
0x18002ec94  nop     dword ptr [rax+rax+00h]
0x18002ec99  mov     rcx, cs:?ghLog@@3PEAXEA; hFile
0x18002eca0  xor     r9d, r9d; dwMoveMethod
0x18002eca3  xor     r8d, r8d; lpDistanceToMoveHigh
0x18002eca6  lea     edx, [r9+2]; lDistanceToMove
0x18002ecaa  call    cs:__imp_SetFilePointer
0x18002ecb1  nop     dword ptr [rax+rax+00h]
0x18002ecb6  cmp     eax, 0FFFFFFFFh
0x18002ecb9  jz      loc_18002ED70
0x18002ecbf  mov     rcx, cs:?ghLog@@3PEAXEA; hFile
0x18002ecc6  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18002ecca  mov     r8d, esi; nNumberOfBytesToWrite
0x18002eccd  mov     [rsp+30h+lpOverlapped], r14; lpOverlapped
0x18002ecd2  mov     rdx, rdi; lpBuffer
0x18002ecd5  call    cs:__imp_WriteFile
0x18002ecdc  nop     dword ptr [rax+rax+00h]
0x18002ece1  test    eax, eax
0x18002ece3  jz      loc_18002ED70
0x18002ece9  mov     rcx, cs:?ghLog@@3PEAXEA; hFile
0x18002ecf0  lea     r8, [rbp+arg_14]; lpDistanceToMoveHigh
0x18002ecf4  mov     r9d, 1; dwMoveMethod
0x18002ecfa  mov     qword ptr [rbp+DistanceToMoveHigh], r14
0x18002ecfe  xor     edx, edx; lDistanceToMove
0x18002ed00  call    cs:__imp_SetFilePointer
0x18002ed07  nop     dword ptr [rax+rax+00h]
0x18002ed0c  mov     [rbp+DistanceToMoveHigh], eax
0x18002ed0f  cmp     eax, 0FFFFFFFFh
0x18002ed12  jz      short loc_18002ED70
0x18002ed14  mov     r8d, cs:?gcbMostRecentEntryMarkerSize@@3KA; ulong gcbMostRecentEntryMarkerSize
0x18002ed1b  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18002ed1f  mov     rcx, cs:?ghLog@@3PEAXEA; hFile
0x18002ed26  cmp     r8d, 81h
0x18002ed2d  mov     eax, 80h
0x18002ed32  mov     [rsp+30h+lpOverlapped], r14; lpOverlapped
0x18002ed37  cmova   r8d, eax; nNumberOfBytesToWrite
0x18002ed3b  mov     rdx, r13; lpBuffer
0x18002ed3e  call    cs:__imp_WriteFile
0x18002ed45  nop     dword ptr [rax+rax+00h]
0x18002ed4a  test    eax, eax
0x18002ed4c  jz      short loc_18002ED70
0x18002ed4e  call    ?OverwriteRecordFragment@@YAXXZ; OverwriteRecordFragment(void)
0x18002ed53  mov     edx, [rbp+DistanceToMoveHigh]; lDistanceToMove
0x18002ed56  lea     r8, [rbp+arg_14]; lpDistanceToMoveHigh
0x18002ed5a  mov     rcx, cs:?ghLog@@3PEAXEA; hFile
0x18002ed61  xor     r9d, r9d; dwMoveMethod
0x18002ed64  call    cs:__imp_SetFilePointer
0x18002ed6b  nop     dword ptr [rax+rax+00h]
0x18002ed70  lea     rcx, ?gcsLogCritSection@@3VCStaticCritSec@@A; lpCriticalSection
0x18002ed77  call    cs:__imp_LeaveCriticalSection
0x18002ed7e  nop     dword ptr [rax+rax+00h]
0x18002ed83  mov     rbx, [rsp+30h+arg_0]
0x18002ed88  add     rsp, 30h
0x18002ed8c  pop     r14
0x18002ed8e  pop     r13
0x18002ed90  pop     rdi
0x18002ed91  pop     rsi
0x18002ed92  pop     rbp
0x18002ed93  retn
```
