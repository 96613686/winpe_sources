# soundLoadFile

- ea: `0x180002ca0`
- end: `0x180002fe9`
- name: `soundLoadFile`
- size: `841`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180002b30`

## callees

- `0x180002ca0`
- `0x180003a2c`
- `0x180003ac4`
- `0x18000a02c`
- `0x18000b6d4`
- `0x180012cec`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002dbc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002dbc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002fb1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002fba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002fb1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002fba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002e29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002eaa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002e29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002eaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e79`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180002d0a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180002d0a`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180002e09`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180002e09`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180002d98`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180002d98`
- `api-ms-win-core-kernel32-private-l1-1-0!_lread` at `0x180002ddc`
- `api-ms-win-core-kernel32-private-l1-1-0!_lread` at `0x180002ddc`

## pseudocode

```c
char *__fastcall soundLoadFile(unsigned __int16 *a1)
{
  HANDLE FileW; // rbp
  unsigned __int16 *v4; // rax
  __int64 v5; // rdx
  unsigned __int64 v6; // r12
  unsigned __int64 v7; // r15
  DWORD FileSize; // eax
  unsigned int v9; // r14d
  unsigned int v10; // eax
  char *v11; // rax
  char *v12; // rsi
  unsigned __int8 *v13; // r15
  char LastError; // al
  void *v15; // rcx

  if ( !a1 || !*a1 )
  {
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_f484e89e41a13dc1f5fe6fa534a24b70_Traceguids);
    }
    return 0;
  }
  FileW = CreateFileW(a1, 0x80000000, 3u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        (unsigned int)WPP_f484e89e41a13dc1f5fe6fa534a24b70_Traceguids,
        (_DWORD)a1,
        LastError);
    }
    return 0;
  }
  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_f484e89e41a13dc1f5fe6fa534a24b70_Traceguids, a1);
  }
  v4 = a1;
  v5 = 0x7FFFFFFF;
  do
  {
    if ( !*v4 )
      break;
    ++v4;
    --v5;
  }
  while ( v5 );
  if ( v5 )
  {
    v6 = (0x7FFFFFFF - v5 + 2) & 0xFFFFFFFFFFFFFFFEuLL;
    v7 = 2 * v6 + 76;
    if ( v7 <= 0xFFFFFFFF )
    {
      FileSize = GetFileSize(FileW, 0);
      v9 = FileSize;
      if ( FileSize == -1 )
      {
        if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_f484e89e41a13dc1f5fe6fa534a24b70_Traceguids, a1);
        }
      }
      else
      {
        v10 = v7 + FileSize;
        if ( v10 >= (unsigned int)v7 )
        {
          v11 = (char *)LocalAlloc(0x40u, v10);
          v12 = v11;
          if ( v11 )
          {
            v13 = (unsigned __int8 *)&v11[(unsigned int)v7];
            if ( _lread((HFILE)FileW, v13, v9) == v9 )
            {
              *((_DWORD *)v12 + 16) = v9;
              *(_DWORD *)v12 = 1717857875;
              *((_DWORD *)v12 + 13) = 0;
              *((_QWORD *)v12 + 7) = 0;
              GetFileTime(FileW, 0, 0, (LPFILETIME)(v12 + 68));
              if ( (unsigned int)soundInitWavHdr((struct wavehdr_tag *)(v12 + 4), v13, v9) )
              {
                CloseHandle(FileW);
                if ( !StringCchCopyW((unsigned __int16 *)v12 + 38, v6, a1) )
                  return v12;
              }
              else if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
                     && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
                     && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_f484e89e41a13dc1f5fe6fa534a24b70_Traceguids);
              }
            }
            v15 = *(void **)(v12 + 20);
            if ( v15 )
              LocalFree(v15);
            LocalFree(v12);
          }
          else if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
                 && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_f484e89e41a13dc1f5fe6fa534a24b70_Traceguids);
          }
        }
      }
    }
  }
  CloseHandle(FileW);
  return 0;
}

```

## disassembly

```asm
0x180002ca0  push    rbx
0x180002ca2  push    rbp
0x180002ca3  push    rdi
0x180002ca4  push    r13
0x180002ca6  sub     rsp, 48h
0x180002caa  mov     rbx, rcx
0x180002cad  test    rcx, rcx
0x180002cb0  jz      short loc_180002CB8
0x180002cb2  cmp     word ptr [rcx], 0
0x180002cb6  jnz     short loc_180002CE4
0x180002cb8  mov     rcx, cs:WPP_GLOBAL_Control; lpFileName
0x180002cbf  lea     rdi, WPP_GLOBAL_Control
0x180002cc6  cmp     rcx, rdi
0x180002cc9  jz      short loc_180002CD8
0x180002ccb  test    dword ptr [rcx+1Ch], 400000h
0x180002cd2  jnz     loc_180002FC5
0x180002cd8  xor     eax, eax
0x180002cda  add     rsp, 48h
0x180002cde  pop     r13
0x180002ce0  pop     rdi
0x180002ce1  pop     rbp
0x180002ce2  pop     rbx
0x180002ce3  retn
0x180002ce4  xor     r13d, r13d
0x180002ce7  xor     r9d, r9d; lpSecurityAttributes
0x180002cea  mov     [rsp+68h+hTemplateFile], r13; hTemplateFile
0x180002cef  mov     edx, 80000000h; dwDesiredAccess
0x180002cf4  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180002cfc  mov     r8d, 3; dwShareMode
0x180002d02  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x180002d0a  call    cs:__imp_CreateFileW
0x180002d10  mov     rbp, rax
0x180002d13  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180002d17  jz      loc_180002E4B
0x180002d1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d24  lea     rdi, WPP_GLOBAL_Control
0x180002d2b  cmp     rcx, rdi
0x180002d2e  jnz     loc_180002F00
0x180002d34  mov     ecx, 7FFFFFFFh
0x180002d39  mov     rax, rbx
0x180002d3c  mov     edx, ecx
0x180002d3e  cmp     [rax], r13w
0x180002d42  jz      short loc_180002D4E
0x180002d44  add     rax, 2
0x180002d48  sub     rdx, 1
0x180002d4c  jnz     short loc_180002D3E
0x180002d4e  mov     [rsp+68h+arg_0], rsi
0x180002d53  sub     rcx, rdx
0x180002d56  mov     [rsp+68h+arg_8], r12
0x180002d5b  test    rdx, rdx
0x180002d5e  mov     [rsp+68h+arg_10], r14
0x180002d66  cmovz   rcx, r13
0x180002d6a  mov     [rsp+68h+var_28], r15
0x180002d6f  jz      loc_180002EA7
0x180002d75  lea     r12, [rcx+2]
0x180002d79  mov     esi, 0FFFFFFFFh
0x180002d7e  and     r12, 0FFFFFFFFFFFFFFFEh
0x180002d82  lea     r15, ds:4Ch[r12*2]
0x180002d8a  cmp     r15, rsi
0x180002d8d  ja      loc_180002EA7
0x180002d93  xor     edx, edx; lpFileSizeHigh
0x180002d95  mov     rcx, rbp; hFile
0x180002d98  call    cs:__imp_GetFileSize
0x180002d9e  mov     r14d, eax
0x180002da1  cmp     eax, esi
0x180002da3  jz      loc_180002F34
0x180002da9  add     eax, r15d
0x180002dac  cmp     eax, r15d
0x180002daf  jb      loc_180002EA7
0x180002db5  mov     edx, eax; uBytes
0x180002db7  mov     ecx, 40h ; '@'; uFlags
0x180002dbc  call    cs:__imp_LocalAlloc
0x180002dc2  mov     rsi, rax
0x180002dc5  test    rax, rax
0x180002dc8  jz      loc_180002ECE
0x180002dce  mov     r15d, r15d
0x180002dd1  mov     ecx, ebp; hFile
0x180002dd3  add     r15, rax
0x180002dd6  mov     r8d, r14d; uBytes
0x180002dd9  mov     rdx, r15; lpBuffer
0x180002ddc  call    cs:__imp__lread
0x180002de2  cmp     eax, r14d
0x180002de5  jnz     loc_180002FA8
0x180002deb  lea     r9, [rsi+44h]; lpLastWriteTime
0x180002def  mov     [rsi+40h], r14d
0x180002df3  xor     r8d, r8d; lpLastAccessTime
0x180002df6  mov     dword ptr [rsi], 66646E53h
0x180002dfc  xor     edx, edx; lpCreationTime
0x180002dfe  mov     [rsi+34h], r13d
0x180002e02  mov     rcx, rbp; hFile
0x180002e05  mov     [rsi+38h], r13
0x180002e09  call    cs:__imp_GetFileTime
0x180002e0f  lea     rcx, [rsi+4]; struct wavehdr_tag *
0x180002e13  mov     r8d, r14d; unsigned int
0x180002e16  mov     rdx, r15; unsigned __int8 *
0x180002e19  call    ?soundInitWavHdr@@YAHPEAUwavehdr_tag@@PEAEK@Z; soundInitWavHdr(wavehdr_tag *,uchar *,ulong)
0x180002e1e  test    eax, eax
0x180002e20  jz      loc_180002F78
0x180002e26  mov     rcx, rbp; hObject
0x180002e29  call    cs:__imp_CloseHandle
0x180002e2f  lea     rcx, [rsi+4Ch]; unsigned __int16 *
0x180002e33  mov     r8, rbx; unsigned __int16 *
0x180002e36  mov     rdx, r12; unsigned __int64
0x180002e39  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180002e3e  test    eax, eax
0x180002e40  jnz     loc_180002FA8
0x180002e46  mov     rax, rsi
0x180002e49  jmp     short loc_180002EB2
0x180002e4b  mov     rax, cs:WPP_GLOBAL_Control
0x180002e52  lea     rdi, WPP_GLOBAL_Control
0x180002e59  cmp     rax, rdi
0x180002e5c  jz      loc_180002CD8
0x180002e62  test    dword ptr [rax+1Ch], 400000h
0x180002e69  jz      loc_180002CD8
0x180002e6f  cmp     byte ptr [rax+19h], 2
0x180002e73  jb      loc_180002CD8
0x180002e79  call    cs:__imp_GetLastError
0x180002e7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e86  lea     r8, WPP_f484e89e41a13dc1f5fe6fa534a24b70_Traceguids
0x180002e8d  mov     edx, 18h
0x180002e92  mov     [rsp+68h+dwCreationDisposition], eax
0x180002e96  mov     r9, rbx
0x180002e99  mov     rcx, [rcx+10h]
0x180002e9d  call    WPP_SF_Sd
0x180002ea2  jmp     loc_180002CD8
0x180002ea7  mov     rcx, rbp; hObject
0x180002eaa  call    cs:__imp_CloseHandle
0x180002eb0  xor     eax, eax
0x180002eb2  mov     r14, [rsp+68h+arg_10]
0x180002eba  mov     r12, [rsp+68h+arg_8]
0x180002ebf  mov     rsi, [rsp+68h+arg_0]
0x180002ec4  mov     r15, [rsp+68h+var_28]
0x180002ec9  jmp     loc_180002CDA
0x180002ece  mov     rcx, cs:WPP_GLOBAL_Control
0x180002ed5  cmp     rcx, rdi
0x180002ed8  jz      short loc_180002EA7
0x180002eda  test    dword ptr [rcx+1Ch], 400000h
0x180002ee1  jz      short loc_180002EA7
0x180002ee3  cmp     byte ptr [rcx+19h], 3
0x180002ee7  jb      short loc_180002EA7
0x180002ee9  mov     rcx, [rcx+10h]
0x180002eed  lea     r8, WPP_f484e89e41a13dc1f5fe6fa534a24b70_Traceguids
0x180002ef4  mov     edx, 1Bh
0x180002ef9  call    WPP_SF_
0x180002efe  jmp     short loc_180002EA7
0x180002f00  test    dword ptr [rcx+1Ch], 400000h
0x180002f07  jz      loc_180002D34
0x180002f0d  cmp     byte ptr [rcx+19h], 4
0x180002f11  jb      loc_180002D34
0x180002f17  mov     rcx, [rcx+10h]
0x180002f1b  lea     r8, WPP_f484e89e41a13dc1f5fe6fa534a24b70_Traceguids
0x180002f22  mov     edx, 19h
0x180002f27  mov     r9, rbx
0x180002f2a  call    WPP_SF_S
0x180002f2f  jmp     loc_180002D34
0x180002f34  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f3b  cmp     rcx, rdi
0x180002f3e  jz      loc_180002EA7
0x180002f44  test    dword ptr [rcx+1Ch], 400000h
0x180002f4b  jz      loc_180002EA7
0x180002f51  cmp     byte ptr [rcx+19h], 2
0x180002f55  jb      loc_180002EA7
0x180002f5b  mov     rcx, [rcx+10h]
0x180002f5f  lea     r8, WPP_f484e89e41a13dc1f5fe6fa534a24b70_Traceguids
0x180002f66  mov     edx, 1Ah
0x180002f6b  mov     r9, rbx
0x180002f6e  call    WPP_SF_S
0x180002f73  jmp     loc_180002EA7
0x180002f78  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f7f  cmp     rcx, rdi
0x180002f82  jz      short loc_180002FA8
0x180002f84  test    dword ptr [rcx+1Ch], 400000h
0x180002f8b  jz      short loc_180002FA8
0x180002f8d  cmp     byte ptr [rcx+19h], 2
0x180002f91  jb      short loc_180002FA8
0x180002f93  mov     rcx, [rcx+10h]
0x180002f97  lea     r8, WPP_f484e89e41a13dc1f5fe6fa534a24b70_Traceguids
0x180002f9e  mov     edx, 1Ch
0x180002fa3  call    WPP_SF_
0x180002fa8  mov     rcx, [rsi+14h]; hMem
0x180002fac  test    rcx, rcx
0x180002faf  jz      short loc_180002FB7
0x180002fb1  call    cs:__imp_LocalFree
0x180002fb7  mov     rcx, rsi; hMem
0x180002fba  call    cs:__imp_LocalFree
0x180002fc0  jmp     loc_180002EA7
0x180002fc5  cmp     byte ptr [rcx+19h], 4
0x180002fc9  jb      loc_180002CD8
0x180002fcf  mov     rcx, [rcx+10h]
0x180002fd3  lea     r8, WPP_f484e89e41a13dc1f5fe6fa534a24b70_Traceguids
0x180002fda  mov     edx, 17h
0x180002fdf  call    WPP_SF_
0x180002fe4  jmp     loc_180002CD8
```
