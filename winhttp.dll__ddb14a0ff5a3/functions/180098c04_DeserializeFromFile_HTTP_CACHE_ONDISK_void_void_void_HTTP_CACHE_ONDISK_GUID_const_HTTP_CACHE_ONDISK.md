# DeserializeFromFile<_HTTP_CACHE_ONDISK>(void *,void (*)(void *,_HTTP_CACHE_ONDISK *),_GUID const *,_HTTP_CACHE_ONDISK *)

- ea: `0x180098c04`
- end: `0x180098eb8`
- name: `??$DeserializeFromFile@U_HTTP_CACHE_ONDISK@@@@YAJPEAXP6AX0PEAU_HTTP_CACHE_ONDISK@@@ZPEBU_GUID@@1@Z`
- size: `692`
- prototype: `__int64 __fastcall(HANDLE hFile, __int64, __int64, _BYTE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800bbe9c`

## callees

- `0x18007e3dc`
- `0x18008cb40`
- `0x180098c04`
- `0x180098ec0`
- `0x180098ee8`
- `0x1800a1d10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098cb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098d7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098cb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098d7d`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180098cae`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180098cae`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180098d73`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180098d73`
- `RPCRT4!MesHandleFree` at `0x180098e7a`
- `RPCRT4!MesHandleFree` at `0x180098e7a`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x180098e17`
- `RPCRT4!MesDecodeBufferHandleCreate` at `0x180098e17`

## pseudocode

```c
__int64 __fastcall DeserializeFromFile<_HTTP_CACHE_ONDISK>(HANDLE hFile, __int64 a2, __int64 a3, _BYTE *a4)
{
  void *v4; // rdi
  __int64 v7; // rcx
  _BYTE *v8; // rax
  signed int v9; // ebx
  signed int v10; // eax
  DWORD LowPart; // ebx
  void *v12; // rax
  unsigned __int64 v13; // rsi
  unsigned int v14; // ecx
  signed int LastError; // eax
  __int64 v16; // rax
  unsigned int v17; // ebx
  RPC_STATUS v18; // eax
  int v19; // eax
  void *v21; // [rsp+38h] [rbp-28h] BYREF
  handle_t pHandle; // [rsp+40h] [rbp-20h] BYREF
  DWORD NumberOfBytesRead; // [rsp+48h] [rbp-18h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+50h] [rbp-10h] BYREF

  v4 = 0;
  pHandle = 0;
  FileSize.QuadPart = 0;
  v21 = 0;
  NumberOfBytesRead = 0;
  if ( a4 )
  {
    v7 = 720;
    v8 = a4;
    do
    {
      *v8++ = 0;
      --v7;
    }
    while ( v7 );
  }
  if ( hFile )
  {
    if ( hFile == (HANDLE)-1LL )
    {
      v9 = -2147024809;
    }
    else if ( a4 )
    {
      if ( GetFileSizeEx(hFile, &FileSize) )
      {
        LowPart = FileSize.LowPart;
        if ( FileSize.QuadPart < 0x4000000 )
        {
          if ( FileSize.QuadPart > 0x18uLL )
          {
            if ( FileSize.QuadPart > 0xFFFFFFFFuLL )
            {
              v9 = -2147024362;
            }
            else
            {
              v12 = MIDL_user_allocate(FileSize.LowPart + 7);
              if ( v12 )
              {
                v4 = v12;
                v21 = v12;
                v13 = ((unsigned __int64)v12 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
                if ( ReadFile(hFile, (LPVOID)v13, LowPart, &NumberOfBytesRead, 0) )
                {
                  if ( NumberOfBytesRead == LowPart )
                  {
                    v16 = *(_QWORD *)v13 - 0x48BE71742DABA8B6LL;
                    if ( *(_QWORD *)v13 == 0x48BE71742DABA8B6LL )
                      v16 = *(_QWORD *)(v13 + 8) - 0x769AF5365394FA96LL;
                    if ( v16 )
                    {
                      v9 = -2147024883;
                    }
                    else
                    {
                      v17 = LowPart - 24;
                      if ( *(_DWORD *)(v13 + 16) == ComputeCheckSum(v14, (unsigned __int8 *)(v13 + 24), v17) )
                      {
                        v18 = MesDecodeBufferHandleCreate((char *)(v13 + 24), v17, &pHandle);
                        v9 = v18;
                        if ( v18 > 0 )
                          v9 = (unsigned __int16)v18 | 0x80070000;
                        if ( v9 >= 0 )
                        {
                          v19 = InvokeCoder<_HTTP_CACHE_ONDISK>(pHandle, &HTTP_CACHE_ONDISK_Decode, a4);
                          v9 = v19;
                          if ( v19 > 0 )
                            v9 = (unsigned __int16)v19 | 0x80070000;
                        }
                      }
                      else
                      {
                        v9 = -2147024883;
                      }
                    }
                  }
                  else
                  {
                    v9 = -2147418113;
                  }
                }
                else
                {
                  LastError = GetLastError();
                  v9 = LastError;
                  if ( LastError > 0 )
                    v9 = (unsigned __int16)LastError | 0x80070000;
                  if ( v9 >= 0 )
                    v9 = -2147418113;
                }
              }
              else
              {
                v9 = -2147024882;
              }
            }
          }
          else
          {
            v9 = -2147024883;
          }
        }
        else
        {
          v9 = -2147024883;
        }
      }
      else
      {
        v10 = GetLastError();
        v9 = v10;
        if ( v10 > 0 )
          v9 = (unsigned __int16)v10 | 0x80070000;
        if ( v9 >= 0 )
          v9 = -2147418113;
      }
    }
    else
    {
      v9 = -2147024809;
    }
  }
  else
  {
    v9 = -2147024809;
  }
  if ( pHandle )
  {
    MesHandleFree(pHandle);
    pHandle = 0;
  }
  if ( v4 )
    MidlAllocator::Free(&v21);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180098c04  mov     [rsp-28h+arg_8], rbx
0x180098c09  push    rbp
0x180098c0a  push    rsi
0x180098c0b  push    rdi
0x180098c0c  push    r14
0x180098c0e  push    r15
0x180098c10  mov     rbp, rsp
0x180098c13  sub     rsp, 60h
0x180098c17  mov     rax, cs:__security_cookie
0x180098c1e  xor     rax, rsp
0x180098c21  mov     [rbp+var_8], rax
0x180098c25  xor     edi, edi
0x180098c27  mov     [rbp+var_2C], 0
0x180098c2e  mov     [rbp+pHandle], 0
0x180098c36  mov     r15, r9
0x180098c39  mov     qword ptr [rbp+FileSize], 0
0x180098c41  mov     r14, rcx
0x180098c44  mov     [rbp+var_28], rdi
0x180098c48  mov     [rbp+NumberOfBytesRead], edi
0x180098c4b  test    r9, r9
0x180098c4e  jz      short loc_180098C64
0x180098c50  mov     ecx, 2D0h
0x180098c55  mov     rax, r9
0x180098c58  mov     [rax], dil
0x180098c5b  inc     rax
0x180098c5e  sub     rcx, 1
0x180098c62  jnz     short loc_180098C58
0x180098c64  test    r14, r14
0x180098c67  jnz     short loc_180098C7A
0x180098c69  mov     ebx, 80070057h
0x180098c6e  mov     [rbp+var_2C], 9Ch
0x180098c75  jmp     loc_180098E71
0x180098c7a  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180098c7e  jnz     short loc_180098C91
0x180098c80  mov     ebx, 80070057h
0x180098c85  mov     [rbp+var_2C], 9Dh
0x180098c8c  jmp     loc_180098E71
0x180098c91  test    r15, r15
0x180098c94  jnz     short loc_180098CA7
0x180098c96  mov     ebx, 80070057h
0x180098c9b  mov     [rbp+var_2C], 0A0h
0x180098ca2  jmp     loc_180098E71
0x180098ca7  lea     rdx, [rbp+FileSize]; lpFileSize
0x180098cab  mov     rcx, r14; hFile
0x180098cae  call    cs:__imp_GetFileSizeEx
0x180098cb4  test    eax, eax
0x180098cb6  jnz     short loc_180098CE3
0x180098cb8  call    cs:__imp_GetLastError
0x180098cbe  mov     ebx, eax
0x180098cc0  test    eax, eax
0x180098cc2  jle     short loc_180098CCD
0x180098cc4  movzx   ebx, ax
0x180098cc7  or      ebx, 80070000h
0x180098ccd  test    ebx, ebx
0x180098ccf  mov     [rbp+var_2C], 0A6h
0x180098cd6  mov     eax, 8000FFFFh
0x180098cdb  cmovns  ebx, eax
0x180098cde  jmp     loc_180098E71
0x180098ce3  mov     rbx, qword ptr [rbp+FileSize]
0x180098ce7  cmp     rbx, 4000000h
0x180098cee  jl      short loc_180098D01
0x180098cf0  mov     ebx, 8007000Dh
0x180098cf5  mov     [rbp+var_2C], 0A7h
0x180098cfc  jmp     loc_180098E71
0x180098d01  cmp     rbx, 18h
0x180098d05  ja      short loc_180098D18
0x180098d07  mov     ebx, 8007000Dh
0x180098d0c  mov     [rbp+var_2C], 0A8h
0x180098d13  jmp     loc_180098E71
0x180098d18  mov     eax, 0FFFFFFFFh
0x180098d1d  cmp     rbx, rax
0x180098d20  ja      loc_180098E65
0x180098d26  lea     ecx, [rbx+7]; size
0x180098d29  mov     [rbp+var_2C], edi
0x180098d2c  call    MIDL_user_allocate
0x180098d31  test    rax, rax
0x180098d34  jnz     short loc_180098D4E
0x180098d36  mov     [rbp+var_2C], 34h ; '4'
0x180098d3d  mov     ebx, 8007000Eh
0x180098d42  mov     [rbp+var_2C], 0B1h
0x180098d49  jmp     loc_180098E71
0x180098d4e  mov     rdi, rax
0x180098d51  mov     [rbp+var_28], rax
0x180098d55  lea     rsi, [rax+7]
0x180098d59  mov     [rsp+60h+lpOverlapped], 0; lpOverlapped
0x180098d62  and     rsi, 0FFFFFFFFFFFFFFF8h
0x180098d66  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180098d6a  mov     rdx, rsi; lpBuffer
0x180098d6d  mov     r8d, ebx; nNumberOfBytesToRead
0x180098d70  mov     rcx, r14; hFile
0x180098d73  call    cs:__imp_ReadFile
0x180098d79  test    eax, eax
0x180098d7b  jnz     short loc_180098DA8
0x180098d7d  call    cs:__imp_GetLastError
0x180098d83  mov     ebx, eax
0x180098d85  test    eax, eax
0x180098d87  jle     short loc_180098D92
0x180098d89  movzx   ebx, ax
0x180098d8c  or      ebx, 80070000h
0x180098d92  test    ebx, ebx
0x180098d94  mov     [rbp+var_2C], 0B8h
0x180098d9b  mov     eax, 8000FFFFh
0x180098da0  cmovns  ebx, eax
0x180098da3  jmp     loc_180098E71
0x180098da8  cmp     [rbp+NumberOfBytesRead], ebx
0x180098dab  jz      short loc_180098DBE
0x180098dad  mov     ebx, 8000FFFFh
0x180098db2  mov     [rbp+var_2C], 0BAh
0x180098db9  jmp     loc_180098E71
0x180098dbe  mov     rax, [rsi]
0x180098dc1  sub     rax, qword ptr cs:xmmword_1800E82D8
0x180098dc8  jnz     short loc_180098DD5
0x180098dca  mov     rax, [rsi+8]
0x180098dce  sub     rax, qword ptr cs:xmmword_1800E82D8+8
0x180098dd5  test    rax, rax
0x180098dd8  jz      short loc_180098DEB
0x180098dda  mov     ebx, 8007000Dh
0x180098ddf  mov     [rbp+var_2C], 0C0h
0x180098de6  jmp     loc_180098E71
0x180098deb  add     ebx, 0FFFFFFE8h
0x180098dee  lea     rdx, [rsi+18h]; unsigned __int8 *
0x180098df2  mov     r8d, ebx; unsigned int
0x180098df5  call    ?ComputeCheckSum@@YAKKPEAEK@Z; ComputeCheckSum(ulong,uchar *,ulong)
0x180098dfa  cmp     [rsi+10h], eax
0x180098dfd  jz      short loc_180098E0D
0x180098dff  mov     ebx, 8007000Dh
0x180098e04  mov     [rbp+var_2C], 0C2h
0x180098e0b  jmp     short loc_180098E71
0x180098e0d  lea     r8, [rbp+pHandle]; pHandle
0x180098e11  mov     edx, ebx; BufferSize
0x180098e13  lea     rcx, [rsi+18h]; Buffer
0x180098e17  call    cs:__imp_MesDecodeBufferHandleCreate
0x180098e1d  mov     ebx, eax
0x180098e1f  mov     esi, 80070000h
0x180098e24  test    eax, eax
0x180098e26  jle     short loc_180098E2D
0x180098e28  movzx   ebx, ax
0x180098e2b  or      ebx, esi
0x180098e2d  test    ebx, ebx
0x180098e2f  jns     short loc_180098E3A
0x180098e31  mov     [rbp+var_2C], 0C7h
0x180098e38  jmp     short loc_180098E71
0x180098e3a  mov     rcx, [rbp+pHandle]
0x180098e3e  lea     rdx, HTTP_CACHE_ONDISK_Decode
0x180098e45  mov     r8, r15
0x180098e48  call    ??$InvokeCoder@U_HTTP_CACHE_ONDISK@@@@YAJPEAXP6AX0PEAU_HTTP_CACHE_ONDISK@@@Z1@Z; InvokeCoder<_HTTP_CACHE_ONDISK>(void *,void (*)(void *,_HTTP_CACHE_ONDISK *),_HTTP_CACHE_ONDISK *)
0x180098e4d  mov     ebx, eax
0x180098e4f  test    eax, eax
0x180098e51  jle     short loc_180098E58
0x180098e53  movzx   ebx, ax
0x180098e56  or      ebx, esi
0x180098e58  test    ebx, ebx
0x180098e5a  jns     short loc_180098E71
0x180098e5c  mov     [rbp+var_2C], 0C8h
0x180098e63  jmp     short loc_180098E71
0x180098e65  mov     ebx, 80070216h
0x180098e6a  mov     [rbp+var_2C], 0A9h
0x180098e71  mov     rcx, [rbp+pHandle]; Handle
0x180098e75  test    rcx, rcx
0x180098e78  jz      short loc_180098E88
0x180098e7a  call    cs:__imp_MesHandleFree
0x180098e80  mov     [rbp+pHandle], 0
0x180098e88  test    rdi, rdi
0x180098e8b  jz      short loc_180098E96
0x180098e8d  lea     rcx, [rbp+var_28]; void **
0x180098e91  call    ?Free@MidlAllocator@@SAXPEAPEAX@Z; MidlAllocator::Free(void * *)
0x180098e96  mov     eax, ebx
0x180098e98  mov     rcx, [rbp+var_8]
0x180098e9c  xor     rcx, rsp; StackCookie
0x180098e9f  call    __security_check_cookie
0x180098ea4  mov     rbx, [rsp+60h+arg_8]
0x180098eac  add     rsp, 60h
0x180098eb0  pop     r15
0x180098eb2  pop     r14
0x180098eb4  pop     rdi
0x180098eb5  pop     rsi
0x180098eb6  pop     rbp
0x180098eb7  retn
```
