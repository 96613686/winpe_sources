# CThumbnailCacheDataFile::ShrinkFile(ulong)

- ea: `0x180045114`
- end: `0x180045239`
- name: `?ShrinkFile@CThumbnailCacheDataFile@@QEAAJK@Z`
- size: `293`
- prototype: `__int64 __fastcall(CThumbnailCacheDataFile *__hidden this, LONG lDistanceToMove)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x18002acdc`
- `0x1800416d0`

## callees

- `0x18000b3c0`
- `0x180010890`
- `0x180010aec`
- `0x180010b34`
- `0x180010ba0`
- `0x180011300`
- `0x180045114`
- `0x1800453c0`
- `0x1800454d8`
- `0x1800459fc`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800451fd`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800451fd`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180045154`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180045154`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800451e3`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800451e3`

## pseudocode

```c
__int64 __fastcall CThumbnailCacheDataFile::ShrinkFile(HANDLE *this, DWORD lDistanceToMove)
{
  int NextValidHeader; // ebx
  unsigned int v5; // ebp
  unsigned int i; // edx
  unsigned int v7; // r14d
  int Error; // eax
  unsigned int v10; // [rsp+60h] [rbp+8h] BYREF

  NextValidHeader = CNamedMutex::Acquire((CNamedMutex *)(this + 1), lDistanceToMove);
  if ( NextValidHeader >= 0 )
  {
    NextValidHeader = CThumbnailCacheDataFile::_CheckForCacheReset((CThumbnailCacheDataFile *)this);
    if ( NextValidHeader >= 0 )
    {
      if ( lDistanceToMove >= GetFileSize(this[52], 0) || lDistanceToMove < 0x100000 )
      {
        NextValidHeader = 1;
      }
      else
      {
        v5 = lDistanceToMove;
        v10 = 0;
        for ( i = lDistanceToMove - 0x100000; ; i = v10 + 56 )
        {
          NextValidHeader = CThumbnailCacheDataFile::_FindNextValidHeader((CThumbnailCacheDataFile *)this, i, &v10);
          if ( NextValidHeader < 0 )
            break;
          v7 = v5;
          v5 = v10;
          if ( v10 > lDistanceToMove )
          {
            NextValidHeader = CThumbnailCacheDataFile::_DeleteAllEntriesBeyondOffset(
                                (CThumbnailCacheDataFile *)this,
                                v7);
            if ( NextValidHeader >= 0 )
            {
              if ( *((_DWORD *)this[6] + 4) >= v7 )
                CThumbnailCacheDataFile::_SetNextReclaimOffset((CThumbnailCacheDataFile *)this, 0x18u);
              *((_DWORD *)this[6] + 5) = v7;
              if ( SetFilePointer(this[52], v7, 0, 0) == -1
                || (CThumbnailCacheDataFile::_CloseMapping((CThumbnailCacheDataFile *)this), !SetEndOfFile(this[52])) )
              {
                Error = ResultFromKnownLastError();
              }
              else
              {
                Error = CThumbnailCacheDataFile::_RemapOrGrowMapping((CThumbnailCacheDataFile *)this, 0);
              }
              NextValidHeader = Error;
            }
            break;
          }
        }
      }
    }
    CNamedMutex::Release((CNamedMutex *)(this + 1));
  }
  return (unsigned int)NextValidHeader;
}

```

## disassembly

```asm
0x180045114  push    rbx
0x180045116  push    rbp
0x180045117  push    rsi
0x180045118  push    rdi
0x180045119  push    r14
0x18004511b  push    r15
0x18004511d  sub     rsp, 28h
0x180045121  mov     rdi, rcx
0x180045124  mov     esi, edx
0x180045126  add     rcx, 8; this
0x18004512a  call    ?Acquire@CNamedMutex@@QEAAJK@Z; CNamedMutex::Acquire(ulong)
0x18004512f  mov     ebx, eax
0x180045131  test    eax, eax
0x180045133  js      loc_18004522A
0x180045139  mov     rcx, rdi; this
0x18004513c  call    ?_CheckForCacheReset@CThumbnailCacheDataFile@@AEAAJXZ; CThumbnailCacheDataFile::_CheckForCacheReset(void)
0x180045141  mov     ebx, eax
0x180045143  test    eax, eax
0x180045145  js      loc_180045221
0x18004514b  mov     rcx, [rdi+1A0h]; hFile
0x180045152  xor     edx, edx; lpFileSizeHigh
0x180045154  call    cs:__imp_GetFileSize
0x18004515a  cmp     esi, eax
0x18004515c  jnb     loc_18004521C
0x180045162  cmp     esi, 100000h
0x180045168  jb      loc_18004521C
0x18004516e  mov     ebp, esi
0x180045170  mov     [rsp+58h+arg_0], 0
0x180045178  lea     edx, [rsi-100000h]
0x18004517e  jmp     short loc_18004518E
0x180045180  mov     r14d, ebp
0x180045183  mov     ebp, [rsp+58h+arg_0]
0x180045187  cmp     ebp, esi
0x180045189  ja      short loc_1800451A3
0x18004518b  lea     edx, [rbp+38h]; unsigned int
0x18004518e  lea     r8, [rsp+58h+arg_0]; unsigned int *
0x180045193  mov     rcx, rdi; this
0x180045196  call    ?_FindNextValidHeader@CThumbnailCacheDataFile@@AEAAJKPEAK@Z; CThumbnailCacheDataFile::_FindNextValidHeader(ulong,ulong *)
0x18004519b  mov     ebx, eax
0x18004519d  test    eax, eax
0x18004519f  jns     short loc_180045180
0x1800451a1  jmp     short loc_180045221
0x1800451a3  mov     edx, r14d; unsigned int
0x1800451a6  mov     rcx, rdi; this
0x1800451a9  call    ?_DeleteAllEntriesBeyondOffset@CThumbnailCacheDataFile@@AEAAJK@Z; CThumbnailCacheDataFile::_DeleteAllEntriesBeyondOffset(ulong)
0x1800451ae  mov     ebx, eax
0x1800451b0  test    eax, eax
0x1800451b2  js      short loc_180045221
0x1800451b4  mov     rax, [rdi+30h]
0x1800451b8  cmp     [rax+10h], r14d
0x1800451bc  jb      short loc_1800451CB
0x1800451be  mov     edx, 18h; unsigned int
0x1800451c3  mov     rcx, rdi; this
0x1800451c6  call    ?_SetNextReclaimOffset@CThumbnailCacheDataFile@@AEAAXK@Z; CThumbnailCacheDataFile::_SetNextReclaimOffset(ulong)
0x1800451cb  mov     rax, [rdi+30h]
0x1800451cf  xor     r9d, r9d; dwMoveMethod
0x1800451d2  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800451d5  mov     edx, r14d; lDistanceToMove
0x1800451d8  mov     [rax+14h], r14d
0x1800451dc  mov     rcx, [rdi+1A0h]; hFile
0x1800451e3  call    cs:__imp_SetFilePointer
0x1800451e9  cmp     eax, 0FFFFFFFFh
0x1800451ec  jz      short loc_180045213
0x1800451ee  mov     rcx, rdi; this
0x1800451f1  call    ?_CloseMapping@CThumbnailCacheDataFile@@AEAAXXZ; CThumbnailCacheDataFile::_CloseMapping(void)
0x1800451f6  mov     rcx, [rdi+1A0h]; hFile
0x1800451fd  call    cs:__imp_SetEndOfFile
0x180045203  test    eax, eax
0x180045205  jz      short loc_180045213
0x180045207  xor     edx, edx; unsigned int
0x180045209  mov     rcx, rdi; this
0x18004520c  call    ?_RemapOrGrowMapping@CThumbnailCacheDataFile@@AEAAJK@Z; CThumbnailCacheDataFile::_RemapOrGrowMapping(ulong)
0x180045211  jmp     short loc_180045218
0x180045213  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180045218  mov     ebx, eax
0x18004521a  jmp     short loc_180045221
0x18004521c  mov     ebx, 1
0x180045221  lea     rcx, [rdi+8]; this
0x180045225  call    ?Release@CNamedMutex@@QEAAJXZ; CNamedMutex::Release(void)
0x18004522a  mov     eax, ebx
0x18004522c  add     rsp, 28h
0x180045230  pop     r15
0x180045232  pop     r14
0x180045234  pop     rdi
0x180045235  pop     rsi
0x180045236  pop     rbp
0x180045237  pop     rbx
0x180045238  retn
```
