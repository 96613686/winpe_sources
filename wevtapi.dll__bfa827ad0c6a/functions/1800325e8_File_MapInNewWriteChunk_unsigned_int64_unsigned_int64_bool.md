# File::MapInNewWriteChunk(unsigned __int64,unsigned __int64,bool)

- ea: `0x1800325e8`
- end: `0x1800326fd`
- name: `?MapInNewWriteChunk@File@@AEAAK_K0_N@Z`
- size: `277`
- prototype: `unsigned int(File *__hidden this, unsigned __int64, unsigned __int64, bool)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180031f14`
- `0x1800322f0`
- `0x180032a7c`

## callees

- `0x180023548`
- `0x180025514`
- `0x1800315a8`
- `0x1800325e8`
- `0x180033078`
- `0x180033c4c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180032686`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180032686`

## pseudocode

```c
__int64 __fastcall File::MapInNewWriteChunk(File *this, unsigned __int64 a2, unsigned __int64 a3, char a4)
{
  unsigned __int64 v4; // r10
  bool v6; // cf
  __int64 v7; // r8
  unsigned int v8; // edi

  v4 = a2;
  *((_QWORD *)this + 21) = (a3 << 16) + 4096;
  *((_QWORD *)this + 4) = a3;
  if ( a4 )
    *((_QWORD *)this + 3) = CalcNextChunkRaw(a3, *((_QWORD *)this + 7));
  InitializeChunkHeaderInfo(*((struct ChunkHeader **)this + 20), v4);
  memset_0(*((void **)this + 28), 0, 0x100u);
  memset_0(*((void **)this + 63), 0, 0x80u);
  v6 = ++*((_DWORD *)this + 205) < 0x190u;
  *((_BYTE *)this + 827) = 1;
  *((_DWORD *)this + 203) = 0;
  if ( v6 )
    return 0;
  FlushFileBuffers(*((HANDLE *)this + 84));
  LOBYTE(v7) = 1;
  v8 = File::WriteFileHeader(*((void **)this + 84), (__int64)this + 16, v7, 1);
  if ( !v8 )
  {
    *((_DWORD *)this + 205) = 0;
    return 0;
  }
  if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, v8);
  }
  return v8;
}

```

## disassembly

```asm
0x1800325e8  mov     [rsp+arg_0], rbx
0x1800325ed  push    rdi
0x1800325ee  sub     rsp, 30h
0x1800325f2  mov     rax, r8
0x1800325f5  mov     r10, rdx
0x1800325f8  shl     rax, 10h
0x1800325fc  mov     rbx, rcx
0x1800325ff  add     rax, 1000h
0x180032605  mov     [rcx+0A8h], rax
0x18003260c  mov     [rcx+20h], r8
0x180032610  test    r9b, r9b
0x180032613  jz      short loc_180032625
0x180032615  mov     rdx, [rcx+38h]; unsigned __int64
0x180032619  mov     rcx, r8; unsigned __int64
0x18003261c  call    ?CalcNextChunkRaw@@YA_K_K0@Z; CalcNextChunkRaw(unsigned __int64,unsigned __int64)
0x180032621  mov     [rbx+18h], rax
0x180032625  mov     rcx, [rbx+0A0h]; struct ChunkHeader *
0x18003262c  mov     rdx, r10; unsigned __int64
0x18003262f  call    ?InitializeChunkHeaderInfo@@YAXPEAUChunkHeader@@_K@Z; InitializeChunkHeaderInfo(ChunkHeader *,unsigned __int64)
0x180032634  mov     rcx, [rbx+0E0h]; void *
0x18003263b  xor     edx, edx; Val
0x18003263d  mov     r8d, 100h; Size
0x180032643  call    memset_0
0x180032648  mov     rcx, [rbx+1F8h]; void *
0x18003264f  xor     edx, edx; Val
0x180032651  mov     r8d, 80h; Size
0x180032657  call    memset_0
0x18003265c  inc     dword ptr [rbx+334h]
0x180032662  cmp     dword ptr [rbx+334h], 190h
0x18003266c  mov     byte ptr [rbx+33Bh], 1
0x180032673  mov     dword ptr [rbx+32Ch], 0
0x18003267d  jb      short loc_1800326F0
0x18003267f  mov     rcx, [rbx+2A0h]; hFile
0x180032686  call    cs:__imp_FlushFileBuffers
0x18003268c  mov     rcx, [rbx+2A0h]
0x180032693  lea     rdx, [rbx+10h]
0x180032697  mov     r9b, 1
0x18003269a  mov     r8b, r9b
0x18003269d  call    ?WriteFileHeader@File@@CAKPEAXPEAUFileHeader@@_N2W4FileModeFlags@@@Z; File::WriteFileHeader(void *,FileHeader *,bool,bool,FileModeFlags)
0x1800326a2  mov     edi, eax
0x1800326a4  test    eax, eax
0x1800326a6  jz      short loc_1800326E6
0x1800326a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800326af  lea     rax, WPP_GLOBAL_Control
0x1800326b6  cmp     rcx, rax
0x1800326b9  jz      short loc_1800326E2
0x1800326bb  test    dword ptr [rcx+1Ch], 8000h
0x1800326c2  jz      short loc_1800326E2
0x1800326c4  cmp     byte ptr [rcx+19h], 2
0x1800326c8  jb      short loc_1800326E2
0x1800326ca  mov     rcx, [rcx+10h]
0x1800326ce  lea     r8, WPP_d3d936efbc913e3641017ad303784371_Traceguids
0x1800326d5  mov     edx, 56h ; 'V'
0x1800326da  mov     r9d, edi
0x1800326dd  call    WPP_SF_D
0x1800326e2  mov     eax, edi
0x1800326e4  jmp     short loc_1800326F2
0x1800326e6  mov     dword ptr [rbx+334h], 0
0x1800326f0  xor     eax, eax
0x1800326f2  mov     rbx, [rsp+38h+arg_0]
0x1800326f7  add     rsp, 30h
0x1800326fb  pop     rdi
0x1800326fc  retn
```
