# SerializeToFile<_HTTP_CACHE_ONDISK>(void *,void (*)(void *,_HTTP_CACHE_ONDISK *),_GUID const *,_HTTP_CACHE_ONDISK *)

- ea: `0x18007e134`
- end: `0x18007e3d3`
- name: `??$SerializeToFile@U_HTTP_CACHE_ONDISK@@@@YAJPEAXP6AX0PEAU_HTTP_CACHE_ONDISK@@@ZPEBU_GUID@@1@Z`
- size: `671`
- prototype: `__int64 __fastcall(HANDLE hFile, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18005d988`
- `0x180093dac`
- `0x1800bbf54`

## callees

- `0x18001b480`
- `0x18007e134`
- `0x18007e3dc`
- `0x180098ec0`
- `0x1800a1d10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e267`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e2b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e314`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e346`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e267`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e2b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e314`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e346`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18007e2a9`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18007e30a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18007e2a9`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18007e30a`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18007e25c`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18007e25c`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18007e33c`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18007e33c`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18007e1de`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x18007e1de`
- `RPCRT4!MesHandleFree` at `0x18007e38c`
- `RPCRT4!MesHandleFree` at `0x18007e38c`

## pseudocode

```c
__int64 __fastcall SerializeToFile<_HTTP_CACHE_ONDISK>(HANDLE hFile, __int64 a2, __int64 a3, __int64 a4)
{
  signed int v6; // ebx
  RPC_STATUS v7; // eax
  int v8; // eax
  unsigned int v9; // ecx
  signed int LastError; // eax
  signed int v11; // eax
  signed int v12; // eax
  signed int v13; // eax
  char *v15; // [rsp+30h] [rbp-40h] BYREF
  handle_t pHandle; // [rsp+38h] [rbp-38h] BYREF
  char *pBuffer; // [rsp+40h] [rbp-30h] BYREF
  unsigned int pEncodedSize; // [rsp+48h] [rbp-28h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+4Ch] [rbp-24h] BYREF
  __int128 Buffer; // [rsp+50h] [rbp-20h] BYREF
  __int64 v21; // [rsp+60h] [rbp-10h]

  HIDWORD(v15) = 0;
  pBuffer = 0;
  pEncodedSize = 0;
  pHandle = 0;
  NumberOfBytesWritten = 0;
  v21 = 0;
  Buffer = 0;
  if ( hFile )
  {
    if ( hFile == (HANDLE)-1LL )
    {
      v6 = -2147024809;
      HIDWORD(v15) = 81;
    }
    else if ( a4 )
    {
      v7 = MesEncodeDynBufferHandleCreate(&pBuffer, &pEncodedSize, &pHandle);
      v6 = v7;
      if ( v7 > 0 )
        v6 = (unsigned __int16)v7 | 0x80070000;
      if ( v6 >= 0 )
      {
        v8 = InvokeCoder<_HTTP_CACHE_ONDISK>(pHandle, &HTTP_CACHE_ONDISK_Encode, a4);
        v6 = v8;
        if ( v8 > 0 )
          v6 = (unsigned __int16)v8 | 0x80070000;
        if ( v6 >= 0 )
        {
          Buffer = xmmword_1800E82D8;
          LODWORD(v21) = ComputeCheckSum(v9, (unsigned __int8 *)pBuffer, pEncodedSize);
          if ( SetFilePointer(hFile, 0, 0, 0) == -1 )
          {
            LastError = GetLastError();
            v6 = LastError;
            if ( LastError > 0 )
              v6 = (unsigned __int16)LastError | 0x80070000;
            HIDWORD(v15) = 102;
            if ( v6 >= 0 )
              v6 = -2147418113;
          }
          else if ( WriteFile(hFile, &Buffer, 0x18u, &NumberOfBytesWritten, 0) )
          {
            if ( NumberOfBytesWritten == 24 )
            {
              if ( WriteFile(hFile, pBuffer, pEncodedSize, &NumberOfBytesWritten, 0) )
              {
                if ( SetEndOfFile(hFile) )
                {
                  if ( NumberOfBytesWritten == pEncodedSize )
                  {
                    v6 = 0;
                  }
                  else
                  {
                    v6 = -2147418113;
                    HIDWORD(v15) = 115;
                  }
                }
                else
                {
                  v13 = GetLastError();
                  v6 = v13;
                  if ( v13 > 0 )
                    v6 = (unsigned __int16)v13 | 0x80070000;
                  HIDWORD(v15) = 112;
                  if ( v6 >= 0 )
                    v6 = -2147418113;
                }
              }
              else
              {
                v12 = GetLastError();
                v6 = v12;
                if ( v12 > 0 )
                  v6 = (unsigned __int16)v12 | 0x80070000;
                HIDWORD(v15) = 111;
                if ( v6 >= 0 )
                  v6 = -2147418113;
              }
            }
            else
            {
              v6 = -2147418113;
              HIDWORD(v15) = 105;
            }
          }
          else
          {
            v11 = GetLastError();
            v6 = v11;
            if ( v11 > 0 )
              v6 = (unsigned __int16)v11 | 0x80070000;
            HIDWORD(v15) = 103;
            if ( v6 >= 0 )
              v6 = -2147418113;
          }
        }
        else
        {
          HIDWORD(v15) = 90;
        }
      }
      else
      {
        HIDWORD(v15) = 89;
      }
    }
    else
    {
      v6 = -2147024809;
      HIDWORD(v15) = 84;
    }
  }
  else
  {
    v6 = -2147024809;
    HIDWORD(v15) = 80;
  }
  if ( pHandle )
  {
    MesHandleFree(pHandle);
    pHandle = 0;
  }
  if ( pBuffer )
  {
    v15 = pBuffer;
    WxFreeHeapEx(&v15);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18007e134  mov     [rsp-18h+arg_8], rbx
0x18007e139  mov     [rsp-18h+arg_10], rsi
0x18007e13e  push    rbp
0x18007e13f  push    rdi
0x18007e140  push    r15
0x18007e142  mov     rbp, rsp
0x18007e145  sub     rsp, 70h
0x18007e149  mov     rax, cs:__security_cookie
0x18007e150  xor     rax, rsp
0x18007e153  mov     [rbp+var_8], rax
0x18007e157  xor     eax, eax
0x18007e159  mov     dword ptr [rbp+var_40+4], 0
0x18007e160  mov     [rbp+pBuffer], 0
0x18007e168  xorps   xmm0, xmm0
0x18007e16b  mov     [rbp+pEncodedSize], 0
0x18007e172  mov     rsi, r9
0x18007e175  mov     [rbp+pHandle], 0
0x18007e17d  mov     rdi, rcx
0x18007e180  mov     [rbp+NumberOfBytesWritten], 0
0x18007e187  mov     [rbp+var_10], rax
0x18007e18b  movups  [rbp+Buffer], xmm0
0x18007e18f  test    rcx, rcx
0x18007e192  jnz     short loc_18007E1A5
0x18007e194  mov     ebx, 80070057h
0x18007e199  mov     dword ptr [rbp+var_40+4], 50h ; 'P'
0x18007e1a0  jmp     loc_18007E383
0x18007e1a5  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18007e1a9  jnz     short loc_18007E1BC
0x18007e1ab  mov     ebx, 80070057h
0x18007e1b0  mov     dword ptr [rbp+var_40+4], 51h ; 'Q'
0x18007e1b7  jmp     loc_18007E383
0x18007e1bc  test    rsi, rsi
0x18007e1bf  jnz     short loc_18007E1D2
0x18007e1c1  mov     ebx, 80070057h
0x18007e1c6  mov     dword ptr [rbp+var_40+4], 54h ; 'T'
0x18007e1cd  jmp     loc_18007E383
0x18007e1d2  lea     r8, [rbp+pHandle]; pHandle
0x18007e1d6  lea     rdx, [rbp+pEncodedSize]; pEncodedSize
0x18007e1da  lea     rcx, [rbp+pBuffer]; pBuffer
0x18007e1de  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x18007e1e4  mov     ebx, eax
0x18007e1e6  mov     r15d, 80070000h
0x18007e1ec  test    eax, eax
0x18007e1ee  jle     short loc_18007E1F6
0x18007e1f0  movzx   ebx, ax
0x18007e1f3  or      ebx, r15d
0x18007e1f6  test    ebx, ebx
0x18007e1f8  jns     short loc_18007E206
0x18007e1fa  mov     dword ptr [rbp+var_40+4], 59h ; 'Y'
0x18007e201  jmp     loc_18007E383
0x18007e206  mov     rcx, [rbp+pHandle]
0x18007e20a  lea     rdx, HTTP_CACHE_ONDISK_Encode
0x18007e211  mov     r8, rsi
0x18007e214  call    ??$InvokeCoder@U_HTTP_CACHE_ONDISK@@@@YAJPEAXP6AX0PEAU_HTTP_CACHE_ONDISK@@@Z1@Z; InvokeCoder<_HTTP_CACHE_ONDISK>(void *,void (*)(void *,_HTTP_CACHE_ONDISK *),_HTTP_CACHE_ONDISK *)
0x18007e219  mov     ebx, eax
0x18007e21b  test    eax, eax
0x18007e21d  jle     short loc_18007E225
0x18007e21f  movzx   ebx, ax
0x18007e222  or      ebx, r15d
0x18007e225  test    ebx, ebx
0x18007e227  jns     short loc_18007E235
0x18007e229  mov     dword ptr [rbp+var_40+4], 5Ah ; 'Z'
0x18007e230  jmp     loc_18007E383
0x18007e235  movups  xmm0, cs:xmmword_1800E82D8
0x18007e23c  mov     rdx, [rbp+pBuffer]; unsigned __int8 *
0x18007e240  mov     r8d, [rbp+pEncodedSize]; unsigned int
0x18007e244  movdqu  [rbp+Buffer], xmm0
0x18007e249  call    ?ComputeCheckSum@@YAKKPEAEK@Z; ComputeCheckSum(ulong,uchar *,ulong)
0x18007e24e  xor     r9d, r9d; dwMoveMethod
0x18007e251  mov     dword ptr [rbp+var_10], eax
0x18007e254  mov     rcx, rdi; hFile
0x18007e257  xor     r8d, r8d; lpDistanceToMoveHigh
0x18007e25a  xor     edx, edx; lDistanceToMove
0x18007e25c  call    cs:__imp_SetFilePointer
0x18007e262  cmp     eax, 0FFFFFFFFh
0x18007e265  jnz     short loc_18007E28F
0x18007e267  call    cs:__imp_GetLastError
0x18007e26d  mov     ebx, eax
0x18007e26f  test    eax, eax
0x18007e271  jle     short loc_18007E279
0x18007e273  movzx   ebx, ax
0x18007e276  or      ebx, r15d
0x18007e279  test    ebx, ebx
0x18007e27b  mov     dword ptr [rbp+var_40+4], 66h ; 'f'
0x18007e282  mov     eax, 8000FFFFh
0x18007e287  cmovns  ebx, eax
0x18007e28a  jmp     loc_18007E383
0x18007e28f  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18007e293  mov     [rsp+70h+lpOverlapped], 0; lpOverlapped
0x18007e29c  mov     r8d, 18h; nNumberOfBytesToWrite
0x18007e2a2  lea     rdx, [rbp+Buffer]; lpBuffer
0x18007e2a6  mov     rcx, rdi; hFile
0x18007e2a9  call    cs:__imp_WriteFile
0x18007e2af  test    eax, eax
0x18007e2b1  jnz     short loc_18007E2DB
0x18007e2b3  call    cs:__imp_GetLastError
0x18007e2b9  mov     ebx, eax
0x18007e2bb  test    eax, eax
0x18007e2bd  jle     short loc_18007E2C5
0x18007e2bf  movzx   ebx, ax
0x18007e2c2  or      ebx, r15d
0x18007e2c5  test    ebx, ebx
0x18007e2c7  mov     dword ptr [rbp+var_40+4], 67h ; 'g'
0x18007e2ce  mov     eax, 8000FFFFh
0x18007e2d3  cmovns  ebx, eax
0x18007e2d6  jmp     loc_18007E383
0x18007e2db  cmp     [rbp+NumberOfBytesWritten], 18h
0x18007e2df  jz      short loc_18007E2F2
0x18007e2e1  mov     ebx, 8000FFFFh
0x18007e2e6  mov     dword ptr [rbp+var_40+4], 69h ; 'i'
0x18007e2ed  jmp     loc_18007E383
0x18007e2f2  mov     r8d, [rbp+pEncodedSize]; nNumberOfBytesToWrite
0x18007e2f6  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18007e2fa  mov     rdx, [rbp+pBuffer]; lpBuffer
0x18007e2fe  mov     rcx, rdi; hFile
0x18007e301  mov     [rsp+70h+lpOverlapped], 0; lpOverlapped
0x18007e30a  call    cs:__imp_WriteFile
0x18007e310  test    eax, eax
0x18007e312  jnz     short loc_18007E339
0x18007e314  call    cs:__imp_GetLastError
0x18007e31a  mov     ebx, eax
0x18007e31c  test    eax, eax
0x18007e31e  jle     short loc_18007E326
0x18007e320  movzx   ebx, ax
0x18007e323  or      ebx, r15d
0x18007e326  test    ebx, ebx
0x18007e328  mov     dword ptr [rbp+var_40+4], 6Fh ; 'o'
0x18007e32f  mov     eax, 8000FFFFh
0x18007e334  cmovns  ebx, eax
0x18007e337  jmp     short loc_18007E383
0x18007e339  mov     rcx, rdi; hFile
0x18007e33c  call    cs:__imp_SetEndOfFile
0x18007e342  test    eax, eax
0x18007e344  jnz     short loc_18007E36B
0x18007e346  call    cs:__imp_GetLastError
0x18007e34c  mov     ebx, eax
0x18007e34e  test    eax, eax
0x18007e350  jle     short loc_18007E358
0x18007e352  movzx   ebx, ax
0x18007e355  or      ebx, r15d
0x18007e358  test    ebx, ebx
0x18007e35a  mov     dword ptr [rbp+var_40+4], 70h ; 'p'
0x18007e361  mov     eax, 8000FFFFh
0x18007e366  cmovns  ebx, eax
0x18007e369  jmp     short loc_18007E383
0x18007e36b  mov     eax, [rbp+pEncodedSize]
0x18007e36e  cmp     [rbp+NumberOfBytesWritten], eax
0x18007e371  jz      short loc_18007E381
0x18007e373  mov     ebx, 8000FFFFh
0x18007e378  mov     dword ptr [rbp+var_40+4], 73h ; 's'
0x18007e37f  jmp     short loc_18007E383
0x18007e381  xor     ebx, ebx
0x18007e383  mov     rcx, [rbp+pHandle]; Handle
0x18007e387  test    rcx, rcx
0x18007e38a  jz      short loc_18007E39A
0x18007e38c  call    cs:__imp_MesHandleFree
0x18007e392  mov     [rbp+pHandle], 0
0x18007e39a  mov     rax, [rbp+pBuffer]
0x18007e39e  test    rax, rax
0x18007e3a1  jz      short loc_18007E3B0
0x18007e3a3  lea     rcx, [rbp+var_40]
0x18007e3a7  mov     [rbp+var_40], rax
0x18007e3ab  call    WxFreeHeapEx
0x18007e3b0  mov     eax, ebx
0x18007e3b2  mov     rcx, [rbp+var_8]
0x18007e3b6  xor     rcx, rsp; StackCookie
0x18007e3b9  call    __security_check_cookie
0x18007e3be  lea     r11, [rsp+70h+var_s0]
0x18007e3c3  mov     rbx, [r11+28h]
0x18007e3c7  mov     rsi, [r11+30h]
0x18007e3cb  mov     rsp, r11
0x18007e3ce  pop     r15
0x18007e3d0  pop     rdi
0x18007e3d1  pop     rbp
0x18007e3d2  retn
```
