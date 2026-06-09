# MatchFile(_SoundFile *,ushort const *)

- ea: `0x180003258`
- end: `0x180003341`
- name: `?MatchFile@@YAHPEAU_SoundFile@@PEBG@Z`
- size: `233`
- prototype: `int(struct _SoundFile *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180002b30`

## callees

- `0x180003258`
- `0x18000b1f8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800032ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800032ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000331a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000331a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000328e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000328e`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800032fd`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800032fd`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x1800032cc`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x1800032cc`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800032b0`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800032b0`

## pseudocode

```c
__int64 __fastcall MatchFile(struct _SoundFile *a1, const unsigned __int16 *a2)
{
  struct _SoundFile *v2; // rbp
  unsigned int v3; // esi
  HANDLE FileW; // rax
  void *v5; // rdi
  int v7; // ebx
  DWORD LastError; // eax
  _FILETIME LastWriteTime; // [rsp+70h] [rbp+8h] BYREF

  LastWriteTime = (_FILETIME)a1;
  v2 = pCurrentSound;
  v3 = 0;
  FileW = CreateFileW(a2, 0x80000000, 3u, 0, 3u, 0x80u, 0);
  v5 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    v7 = *((_DWORD *)v2 + 16);
    if ( v7 == GetFileSize(FileW, 0) )
    {
      LastWriteTime = 0;
      if ( GetFileTime(v5, 0, 0, &LastWriteTime) )
      {
        LOBYTE(v3) = CompareFileTime(&LastWriteTime, (const FILETIME *)((char *)v2 + 68)) == 0;
      }
      else if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
             && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_79794a2bdab63312183cc3ecc20a3af0_Traceguids, LastError);
      }
    }
    CloseHandle(v5);
  }
  return v3;
}

```

## disassembly

```asm
0x180003258  mov     rax, rsp
0x18000325b  mov     [rax+8], rcx
0x18000325f  push    rbx
0x180003260  push    rbp
0x180003261  push    rsi
0x180003262  push    rdi
0x180003263  sub     rsp, 48h
0x180003267  mov     rbp, cs:?pCurrentSound@@3PEAU_SoundFile@@EA; _SoundFile * pCurrentSound
0x18000326e  xor     esi, esi
0x180003270  mov     [rax-38h], rsi
0x180003274  mov     rcx, rdx; lpFileName
0x180003277  mov     dword ptr [rax-40h], 80h
0x18000327e  xor     r9d, r9d; lpSecurityAttributes
0x180003281  mov     edx, 80000000h; dwDesiredAccess
0x180003286  lea     r8d, [rsi+3]; dwShareMode
0x18000328a  mov     [rax-48h], r8d
0x18000328e  call    cs:__imp_CreateFileW
0x180003294  mov     rdi, rax
0x180003297  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000329b  jnz     short loc_1800032A8
0x18000329d  mov     eax, esi
0x18000329f  add     rsp, 48h
0x1800032a3  pop     rdi
0x1800032a4  pop     rsi
0x1800032a5  pop     rbp
0x1800032a6  pop     rbx
0x1800032a7  retn
0x1800032a8  mov     ebx, [rbp+40h]
0x1800032ab  xor     edx, edx; lpFileSizeHigh
0x1800032ad  mov     rcx, rdi; hFile
0x1800032b0  call    cs:__imp_GetFileSize
0x1800032b6  cmp     ebx, eax
0x1800032b8  jnz     short loc_1800032E9
0x1800032ba  lea     r9, [rsp+68h+LastWriteTime]; lpLastWriteTime
0x1800032bf  mov     qword ptr [rsp+68h+LastWriteTime.dwLowDateTime], rsi
0x1800032c4  xor     r8d, r8d; lpLastAccessTime
0x1800032c7  xor     edx, edx; lpCreationTime
0x1800032c9  mov     rcx, rdi; hFile
0x1800032cc  call    cs:__imp_GetFileTime
0x1800032d2  test    eax, eax
0x1800032d4  jnz     short loc_1800032F4
0x1800032d6  mov     rax, cs:WPP_GLOBAL_Control
0x1800032dd  lea     rcx, WPP_GLOBAL_Control
0x1800032e4  cmp     rax, rcx
0x1800032e7  jnz     short loc_18000330B
0x1800032e9  mov     rcx, rdi; hObject
0x1800032ec  call    cs:__imp_CloseHandle
0x1800032f2  jmp     short loc_18000329D
0x1800032f4  lea     rdx, [rbp+44h]; lpFileTime2
0x1800032f8  lea     rcx, [rsp+68h+LastWriteTime]; lpFileTime1
0x1800032fd  call    cs:__imp_CompareFileTime
0x180003303  test    eax, eax
0x180003305  setz    sil
0x180003309  jmp     short loc_1800032E9
0x18000330b  test    dword ptr [rax+1Ch], 400000h
0x180003312  jz      short loc_1800032E9
0x180003314  cmp     byte ptr [rax+19h], 2
0x180003318  jb      short loc_1800032E9
0x18000331a  call    cs:__imp_GetLastError
0x180003320  mov     rcx, cs:WPP_GLOBAL_Control
0x180003327  lea     r8, WPP_79794a2bdab63312183cc3ecc20a3af0_Traceguids
0x18000332e  mov     edx, 1Bh
0x180003333  mov     r9d, eax
0x180003336  mov     rcx, [rcx+10h]
0x18000333a  call    WPP_SF_d
0x18000333f  jmp     short loc_1800032E9
```
