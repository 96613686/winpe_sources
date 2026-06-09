# UtilComputeSHA1Hash(uchar *,ulong,wchar_t * const)

- ea: `0x180096f18`
- end: `0x1800972af`
- name: `?UtilComputeSHA1Hash@@YAJPEAEKQEA_W@Z`
- size: `919`
- prototype: `__int64 __fastcall(BYTE *pbData, DWORD dwDataLen, wchar_t *const)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180071f04`

## callees

- `0x180004bb4`
- `0x18001fe24`
- `0x180020430`
- `0x18003ec1c`
- `0x180050db0`
- `0x180096f18`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096f8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097001`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097055`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800970b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009715e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096f8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097001`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097055`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800970b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009715e`
- `CRYPTSP!CryptHashData` at `0x18009704b`
- `CRYPTSP!CryptHashData` at `0x18009704b`
- `CRYPTSP!CryptGetHashParam` at `0x1800970ae`
- `CRYPTSP!CryptGetHashParam` at `0x180097154`
- `CRYPTSP!CryptGetHashParam` at `0x1800970ae`
- `CRYPTSP!CryptGetHashParam` at `0x180097154`
- `CRYPTSP!CryptReleaseContext` at `0x180097255`
- `CRYPTSP!CryptReleaseContext` at `0x180097255`
- `CRYPTSP!CryptDestroyHash` at `0x18009723c`
- `CRYPTSP!CryptDestroyHash` at `0x18009723c`
- `CRYPTSP!CryptAcquireContextW` at `0x180096f82`
- `CRYPTSP!CryptAcquireContextW` at `0x180096f82`
- `CRYPTSP!CryptCreateHash` at `0x180096ff7`
- `CRYPTSP!CryptCreateHash` at `0x180096ff7`

## pseudocode

```c
__int64 __fastcall UtilComputeSHA1Hash(BYTE *pbData, DWORD dwDataLen, wchar_t *const a3)
{
  signed int v6; // eax
  signed int v7; // ebx
  wchar_t *v8; // rcx
  __int64 v9; // rdx
  signed int v10; // eax
  signed int v11; // eax
  signed int v12; // eax
  signed int LastError; // eax
  __int64 i; // rsi
  DWORD pdwDataLen; // [rsp+30h] [rbp-40h] BYREF
  HCRYPTHASH phHash; // [rsp+38h] [rbp-38h] BYREF
  HCRYPTPROV phProv; // [rsp+40h] [rbp-30h] BYREF
  wchar_t v19; // [rsp+48h] [rbp-28h] BYREF
  BYTE pbDataa[24]; // [rsp+50h] [rbp-20h] BYREF

  phProv = 0;
  phHash = 0;
  pdwDataLen = 0;
  if ( pbData && a3 )
  {
    if ( CryptAcquireContextW(&phProv, 0, L"Microsoft Base Cryptographic Provider v1.0", 1u, 0xF0000000) )
    {
      if ( CryptCreateHash(phProv, 0x8004u, 0, 0, &phHash) )
      {
        if ( CryptHashData(phHash, pbData, dwDataLen, 0) )
        {
          if ( CryptGetHashParam(phHash, 2u, 0, &pdwDataLen, 0) )
          {
            if ( pdwDataLen > 0x14 )
            {
              v7 = -2147418113;
              if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, &WPP_988ce82756cb3ec502560a762615dae0_Traceguids);
              goto LABEL_50;
            }
            if ( CryptGetHashParam(phHash, 2u, pbDataa, &pdwDataLen, 0) )
            {
              *a3 = 0;
              for ( i = 0; ; i = (unsigned int)(i + 1) )
              {
                if ( (unsigned int)i >= pdwDataLen )
                {
                  v7 = 0;
                  goto LABEL_50;
                }
                v7 = StringCchPrintfW(&v19, 3u, L"%x", pbDataa[i]);
                if ( v7 < 0 )
                  break;
                v7 = StringCchCatW(a3, 0x29u, &v19);
                if ( v7 < 0 )
                {
                  v8 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
                  {
                    v9 = 80;
                    goto LABEL_9;
                  }
                  goto LABEL_50;
                }
              }
              v8 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              {
                v9 = 79;
                goto LABEL_9;
              }
              goto LABEL_50;
            }
            LastError = GetLastError();
            v7 = LastError;
            if ( LastError > 0 )
              v7 = (unsigned __int16)LastError | 0x80070000;
            v8 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
            {
LABEL_50:
              if ( phHash )
              {
                CryptDestroyHash(phHash);
                phHash = 0;
              }
              if ( phProv )
                CryptReleaseContext(phProv, 0);
              return (unsigned int)v7;
            }
            v9 = 78;
          }
          else
          {
            v12 = GetLastError();
            v7 = v12;
            if ( v12 > 0 )
              v7 = (unsigned __int16)v12 | 0x80070000;
            v8 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
              goto LABEL_50;
            v9 = 76;
          }
        }
        else
        {
          v11 = GetLastError();
          v7 = v11;
          if ( v11 > 0 )
            v7 = (unsigned __int16)v11 | 0x80070000;
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
            goto LABEL_50;
          v9 = 75;
        }
      }
      else
      {
        v10 = GetLastError();
        v7 = v10;
        if ( v10 > 0 )
          v7 = (unsigned __int16)v10 | 0x80070000;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_50;
        v9 = 74;
      }
    }
    else
    {
      v6 = GetLastError();
      v7 = v6;
      if ( v6 > 0 )
        v7 = (unsigned __int16)v6 | 0x80070000;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_50;
      v9 = 73;
    }
LABEL_9:
    WPP_SF_d(*((_QWORD *)v8 + 2), v9, &WPP_988ce82756cb3ec502560a762615dae0_Traceguids, (unsigned int)v7);
    goto LABEL_50;
  }
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, &WPP_988ce82756cb3ec502560a762615dae0_Traceguids);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180096f18  mov     [rsp-18h+arg_18], rbx
0x180096f1d  push    rbp
0x180096f1e  push    rsi
0x180096f1f  push    r14
0x180096f21  mov     rbp, rsp
0x180096f24  sub     rsp, 70h
0x180096f28  mov     rax, cs:__security_cookie
0x180096f2f  xor     rax, rsp
0x180096f32  mov     [rbp+var_8], rax
0x180096f36  mov     [rbp+phProv], 0
0x180096f3e  mov     r14, r8
0x180096f41  mov     [rbp+phHash], 0
0x180096f49  mov     esi, edx
0x180096f4b  mov     [rbp+pdwDataLen], 0
0x180096f52  mov     rbx, rcx
0x180096f55  test    rcx, rcx
0x180096f58  jz      loc_18009725F
0x180096f5e  test    r8, r8
0x180096f61  jz      loc_18009725F
0x180096f67  mov     r9d, 1; dwProvType
0x180096f6d  mov     [rsp+70h+dwFlags], 0F0000000h; dwFlags
0x180096f75  lea     r8, szProvider; "Microsoft Base Cryptographic Provider v"...
0x180096f7c  xor     edx, edx; szContainer
0x180096f7e  lea     rcx, [rbp+phProv]; phProv
0x180096f82  call    cs:__imp_CryptAcquireContextW
0x180096f88  test    eax, eax
0x180096f8a  jnz     short loc_180096FDF
0x180096f8c  call    cs:__imp_GetLastError
0x180096f92  mov     ebx, eax
0x180096f94  test    eax, eax
0x180096f96  jle     short loc_180096FA1
0x180096f98  movzx   ebx, ax
0x180096f9b  or      ebx, 80070000h
0x180096fa1  mov     rcx, cs:WPP_GLOBAL_Control
0x180096fa8  lea     rax, WPP_GLOBAL_Control
0x180096faf  cmp     rcx, rax
0x180096fb2  jz      loc_180097233
0x180096fb8  test    byte ptr [rcx+1Ch], 1
0x180096fbc  jz      loc_180097233
0x180096fc2  mov     edx, 49h ; 'I'
0x180096fc7  mov     rcx, [rcx+10h]
0x180096fcb  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x180096fd2  mov     r9d, ebx
0x180096fd5  call    WPP_SF_d
0x180096fda  jmp     loc_180097233
0x180096fdf  mov     rcx, [rbp+phProv]; hProv
0x180096fe3  lea     rax, [rbp+phHash]
0x180096fe7  xor     r9d, r9d; dwFlags
0x180096fea  mov     qword ptr [rsp+70h+dwFlags], rax; phHash
0x180096fef  xor     r8d, r8d; hKey
0x180096ff2  mov     edx, 8004h; Algid
0x180096ff7  call    cs:__imp_CryptCreateHash
0x180096ffd  test    eax, eax
0x180096fff  jnz     short loc_18009703E
0x180097001  call    cs:__imp_GetLastError
0x180097007  mov     ebx, eax
0x180097009  test    eax, eax
0x18009700b  jle     short loc_180097016
0x18009700d  movzx   ebx, ax
0x180097010  or      ebx, 80070000h
0x180097016  mov     rcx, cs:WPP_GLOBAL_Control
0x18009701d  lea     rax, WPP_GLOBAL_Control
0x180097024  cmp     rcx, rax
0x180097027  jz      loc_180097233
0x18009702d  test    byte ptr [rcx+1Ch], 1
0x180097031  jz      loc_180097233
0x180097037  mov     edx, 4Ah ; 'J'
0x18009703c  jmp     short loc_180096FC7
0x18009703e  mov     rcx, [rbp+phHash]; hHash
0x180097042  xor     r9d, r9d; dwFlags
0x180097045  mov     r8d, esi; dwDataLen
0x180097048  mov     rdx, rbx; pbData
0x18009704b  call    cs:__imp_CryptHashData
0x180097051  test    eax, eax
0x180097053  jnz     short loc_180097095
0x180097055  call    cs:__imp_GetLastError
0x18009705b  mov     ebx, eax
0x18009705d  test    eax, eax
0x18009705f  jle     short loc_18009706A
0x180097061  movzx   ebx, ax
0x180097064  or      ebx, 80070000h
0x18009706a  mov     rcx, cs:WPP_GLOBAL_Control
0x180097071  lea     rax, WPP_GLOBAL_Control
0x180097078  cmp     rcx, rax
0x18009707b  jz      loc_180097233
0x180097081  test    byte ptr [rcx+1Ch], 1
0x180097085  jz      loc_180097233
0x18009708b  mov     edx, 4Bh ; 'K'
0x180097090  jmp     loc_180096FC7
0x180097095  mov     rcx, [rbp+phHash]; hHash
0x180097099  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x18009709d  xor     r8d, r8d; pbData
0x1800970a0  mov     [rsp+70h+dwFlags], 0; dwFlags
0x1800970a8  lea     ebx, [r8+2]
0x1800970ac  mov     edx, ebx; dwParam
0x1800970ae  call    cs:__imp_CryptGetHashParam
0x1800970b4  test    eax, eax
0x1800970b6  jnz     short loc_1800970F8
0x1800970b8  call    cs:__imp_GetLastError
0x1800970be  mov     ebx, eax
0x1800970c0  test    eax, eax
0x1800970c2  jle     short loc_1800970CD
0x1800970c4  movzx   ebx, ax
0x1800970c7  or      ebx, 80070000h
0x1800970cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800970d4  lea     rax, WPP_GLOBAL_Control
0x1800970db  cmp     rcx, rax
0x1800970de  jz      loc_180097233
0x1800970e4  test    byte ptr [rcx+1Ch], 1
0x1800970e8  jz      loc_180097233
0x1800970ee  mov     edx, 4Ch ; 'L'
0x1800970f3  jmp     loc_180096FC7
0x1800970f8  cmp     [rbp+pdwDataLen], 14h
0x1800970fc  jbe     short loc_18009713E
0x1800970fe  mov     ebx, 8000FFFFh
0x180097103  mov     rcx, cs:WPP_GLOBAL_Control
0x18009710a  lea     rax, WPP_GLOBAL_Control
0x180097111  cmp     rcx, rax
0x180097114  jz      loc_180097233
0x18009711a  test    byte ptr [rcx+1Ch], 1
0x18009711e  jz      loc_180097233
0x180097124  mov     rcx, [rcx+10h]
0x180097128  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18009712f  mov     edx, 4Dh ; 'M'
0x180097134  call    WPP_SF_
0x180097139  jmp     loc_180097233
0x18009713e  mov     rcx, [rbp+phHash]; hHash
0x180097142  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x180097146  lea     r8, [rbp+pbData]; pbData
0x18009714a  mov     [rsp+70h+dwFlags], 0; dwFlags
0x180097152  mov     edx, ebx; dwParam
0x180097154  call    cs:__imp_CryptGetHashParam
0x18009715a  test    eax, eax
0x18009715c  jnz     short loc_18009719E
0x18009715e  call    cs:__imp_GetLastError
0x180097164  mov     ebx, eax
0x180097166  test    eax, eax
0x180097168  jle     short loc_180097173
0x18009716a  movzx   ebx, ax
0x18009716d  or      ebx, 80070000h
0x180097173  mov     rcx, cs:WPP_GLOBAL_Control
0x18009717a  lea     rax, WPP_GLOBAL_Control
0x180097181  cmp     rcx, rax
0x180097184  jz      loc_180097233
0x18009718a  test    byte ptr [rcx+1Ch], 1
0x18009718e  jz      loc_180097233
0x180097194  mov     edx, 4Eh ; 'N'
0x180097199  jmp     loc_180096FC7
0x18009719e  xor     eax, eax
0x1800971a0  mov     [r14], ax
0x1800971a4  xor     esi, esi
0x1800971a6  cmp     esi, [rbp+pdwDataLen]
0x1800971a9  jnb     loc_180097231
0x1800971af  movzx   r9d, [rbp+rsi+pbData]
0x1800971b5  lea     r8, asc_1800B4A00; "%x"
0x1800971bc  mov     edx, 3; unsigned __int64
0x1800971c1  lea     rcx, [rbp+var_28]; wchar_t *
0x1800971c5  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800971ca  mov     ebx, eax
0x1800971cc  test    eax, eax
0x1800971ce  js      short loc_18009720E
0x1800971d0  lea     r8, [rbp+var_28]; wchar_t *
0x1800971d4  mov     edx, 29h ; ')'; unsigned __int64
0x1800971d9  mov     rcx, r14; wchar_t *
0x1800971dc  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800971e1  mov     ebx, eax
0x1800971e3  test    eax, eax
0x1800971e5  js      short loc_1800971EB
0x1800971e7  inc     esi
0x1800971e9  jmp     short loc_1800971A6
0x1800971eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800971f2  lea     rax, WPP_GLOBAL_Control
0x1800971f9  cmp     rcx, rax
0x1800971fc  jz      short loc_180097233
0x1800971fe  test    byte ptr [rcx+1Ch], 1
0x180097202  jz      short loc_180097233
0x180097204  mov     edx, 50h ; 'P'
0x180097209  jmp     loc_180096FC7
0x18009720e  mov     rcx, cs:WPP_GLOBAL_Control
0x180097215  lea     rax, WPP_GLOBAL_Control
0x18009721c  cmp     rcx, rax
0x18009721f  jz      short loc_180097233
0x180097221  test    byte ptr [rcx+1Ch], 1
0x180097225  jz      short loc_180097233
0x180097227  mov     edx, 4Fh ; 'O'
0x18009722c  jmp     loc_180096FC7
0x180097231  xor     ebx, ebx
0x180097233  mov     rcx, [rbp+phHash]; hHash
0x180097237  test    rcx, rcx
0x18009723a  jz      short loc_18009724A
0x18009723c  call    cs:__imp_CryptDestroyHash
0x180097242  mov     [rbp+phHash], 0
0x18009724a  mov     rcx, [rbp+phProv]; hProv
0x18009724e  test    rcx, rcx
0x180097251  jz      short loc_18009725B
0x180097253  xor     edx, edx; dwFlags
0x180097255  call    cs:__imp_CryptReleaseContext
0x18009725b  mov     eax, ebx
0x18009725d  jmp     short loc_180097292
0x18009725f  mov     rcx, cs:WPP_GLOBAL_Control
0x180097266  lea     rax, WPP_GLOBAL_Control
0x18009726d  cmp     rcx, rax
0x180097270  jz      short loc_18009728D
0x180097272  test    byte ptr [rcx+1Ch], 1
0x180097276  jz      short loc_18009728D
0x180097278  mov     rcx, [rcx+10h]
0x18009727c  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x180097283  mov     edx, 48h ; 'H'
0x180097288  call    WPP_SF_
0x18009728d  mov     eax, 80070057h
0x180097292  mov     rcx, [rbp+var_8]
0x180097296  xor     rcx, rsp; StackCookie
0x180097299  call    __security_check_cookie
0x18009729e  mov     rbx, [rsp+70h+arg_18]
0x1800972a6  add     rsp, 70h
0x1800972aa  pop     r14
0x1800972ac  pop     rsi
0x1800972ad  pop     rbp
0x1800972ae  retn
```
