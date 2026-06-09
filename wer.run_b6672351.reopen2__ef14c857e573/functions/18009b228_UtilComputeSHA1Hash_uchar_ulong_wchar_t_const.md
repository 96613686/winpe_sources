# UtilComputeSHA1Hash(uchar *,ulong,wchar_t * const)

- ea: `0x18009b228`
- end: `0x18009b60b`
- name: `?UtilComputeSHA1Hash@@YAJPEAEKQEA_W@Z`
- size: `995`
- prototype: `__int64 __fastcall(BYTE *pbData, DWORD dwDataLen, wchar_t *const)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180075254`

## callees

- `0x180004c64`
- `0x180020680`
- `0x180020e08`
- `0x180040bfc`
- `0x180053300`
- `0x18009b228`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b2a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b323`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b386`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b3f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b4a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b2a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b323`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b386`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b3f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b4a7`
- `CRYPTSP!CryptHashData` at `0x18009b376`
- `CRYPTSP!CryptHashData` at `0x18009b376`
- `CRYPTSP!CryptGetHashParam` at `0x18009b3e5`
- `CRYPTSP!CryptGetHashParam` at `0x18009b497`
- `CRYPTSP!CryptGetHashParam` at `0x18009b3e5`
- `CRYPTSP!CryptGetHashParam` at `0x18009b497`
- `CRYPTSP!CryptReleaseContext` at `0x18009b5aa`
- `CRYPTSP!CryptReleaseContext` at `0x18009b5aa`
- `CRYPTSP!CryptDestroyHash` at `0x18009b58b`
- `CRYPTSP!CryptDestroyHash` at `0x18009b58b`
- `CRYPTSP!CryptAcquireContextW` at `0x18009b292`
- `CRYPTSP!CryptAcquireContextW` at `0x18009b292`
- `CRYPTSP!CryptCreateHash` at `0x18009b313`
- `CRYPTSP!CryptCreateHash` at `0x18009b313`

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
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids);
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
    WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids, (unsigned int)v7);
    goto LABEL_50;
  }
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18009b228  mov     [rsp-18h+arg_18], rbx
0x18009b22d  push    rbp
0x18009b22e  push    rsi
0x18009b22f  push    r14
0x18009b231  mov     rbp, rsp
0x18009b234  sub     rsp, 70h
0x18009b238  mov     rax, cs:__security_cookie
0x18009b23f  xor     rax, rsp
0x18009b242  mov     [rbp+var_8], rax
0x18009b246  mov     [rbp+phProv], 0
0x18009b24e  mov     r14, r8
0x18009b251  mov     [rbp+phHash], 0
0x18009b259  mov     esi, edx
0x18009b25b  mov     [rbp+pdwDataLen], 0
0x18009b262  mov     rbx, rcx
0x18009b265  test    rcx, rcx
0x18009b268  jz      loc_18009B5BA
0x18009b26e  test    r8, r8
0x18009b271  jz      loc_18009B5BA
0x18009b277  mov     r9d, 1; dwProvType
0x18009b27d  mov     [rsp+70h+dwFlags], 0F0000000h; dwFlags
0x18009b285  lea     r8, szProvider; "Microsoft Base Cryptographic Provider v"...
0x18009b28c  xor     edx, edx; szContainer
0x18009b28e  lea     rcx, [rbp+phProv]; phProv
0x18009b292  call    cs:__imp_CryptAcquireContextW
0x18009b299  nop     dword ptr [rax+rax+00h]
0x18009b29e  test    eax, eax
0x18009b2a0  jnz     short loc_18009B2FB
0x18009b2a2  call    cs:__imp_GetLastError
0x18009b2a9  nop     dword ptr [rax+rax+00h]
0x18009b2ae  mov     ebx, eax
0x18009b2b0  test    eax, eax
0x18009b2b2  jle     short loc_18009B2BD
0x18009b2b4  movzx   ebx, ax
0x18009b2b7  or      ebx, 80070000h
0x18009b2bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18009b2c4  lea     rax, WPP_GLOBAL_Control
0x18009b2cb  cmp     rcx, rax
0x18009b2ce  jz      loc_18009B582
0x18009b2d4  test    byte ptr [rcx+1Ch], 1
0x18009b2d8  jz      loc_18009B582
0x18009b2de  mov     edx, 49h ; 'I'
0x18009b2e3  mov     rcx, [rcx+10h]
0x18009b2e7  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x18009b2ee  mov     r9d, ebx
0x18009b2f1  call    WPP_SF_d
0x18009b2f6  jmp     loc_18009B582
0x18009b2fb  mov     rcx, [rbp+phProv]; hProv
0x18009b2ff  lea     rax, [rbp+phHash]
0x18009b303  xor     r9d, r9d; dwFlags
0x18009b306  mov     qword ptr [rsp+70h+dwFlags], rax; phHash
0x18009b30b  xor     r8d, r8d; hKey
0x18009b30e  mov     edx, 8004h; Algid
0x18009b313  call    cs:__imp_CryptCreateHash
0x18009b31a  nop     dword ptr [rax+rax+00h]
0x18009b31f  test    eax, eax
0x18009b321  jnz     short loc_18009B369
0x18009b323  call    cs:__imp_GetLastError
0x18009b32a  nop     dword ptr [rax+rax+00h]
0x18009b32f  mov     ebx, eax
0x18009b331  test    eax, eax
0x18009b333  jle     short loc_18009B33E
0x18009b335  movzx   ebx, ax
0x18009b338  or      ebx, 80070000h
0x18009b33e  mov     rcx, cs:WPP_GLOBAL_Control
0x18009b345  lea     rax, WPP_GLOBAL_Control
0x18009b34c  cmp     rcx, rax
0x18009b34f  jz      loc_18009B582
0x18009b355  test    byte ptr [rcx+1Ch], 1
0x18009b359  jz      loc_18009B582
0x18009b35f  mov     edx, 4Ah ; 'J'
0x18009b364  jmp     loc_18009B2E3
0x18009b369  mov     rcx, [rbp+phHash]; hHash
0x18009b36d  xor     r9d, r9d; dwFlags
0x18009b370  mov     r8d, esi; dwDataLen
0x18009b373  mov     rdx, rbx; pbData
0x18009b376  call    cs:__imp_CryptHashData
0x18009b37d  nop     dword ptr [rax+rax+00h]
0x18009b382  test    eax, eax
0x18009b384  jnz     short loc_18009B3CC
0x18009b386  call    cs:__imp_GetLastError
0x18009b38d  nop     dword ptr [rax+rax+00h]
0x18009b392  mov     ebx, eax
0x18009b394  test    eax, eax
0x18009b396  jle     short loc_18009B3A1
0x18009b398  movzx   ebx, ax
0x18009b39b  or      ebx, 80070000h
0x18009b3a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18009b3a8  lea     rax, WPP_GLOBAL_Control
0x18009b3af  cmp     rcx, rax
0x18009b3b2  jz      loc_18009B582
0x18009b3b8  test    byte ptr [rcx+1Ch], 1
0x18009b3bc  jz      loc_18009B582
0x18009b3c2  mov     edx, 4Bh ; 'K'
0x18009b3c7  jmp     loc_18009B2E3
0x18009b3cc  mov     rcx, [rbp+phHash]; hHash
0x18009b3d0  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x18009b3d4  xor     r8d, r8d; pbData
0x18009b3d7  mov     [rsp+70h+dwFlags], 0; dwFlags
0x18009b3df  lea     ebx, [r8+2]
0x18009b3e3  mov     edx, ebx; dwParam
0x18009b3e5  call    cs:__imp_CryptGetHashParam
0x18009b3ec  nop     dword ptr [rax+rax+00h]
0x18009b3f1  test    eax, eax
0x18009b3f3  jnz     short loc_18009B43B
0x18009b3f5  call    cs:__imp_GetLastError
0x18009b3fc  nop     dword ptr [rax+rax+00h]
0x18009b401  mov     ebx, eax
0x18009b403  test    eax, eax
0x18009b405  jle     short loc_18009B410
0x18009b407  movzx   ebx, ax
0x18009b40a  or      ebx, 80070000h
0x18009b410  mov     rcx, cs:WPP_GLOBAL_Control
0x18009b417  lea     rax, WPP_GLOBAL_Control
0x18009b41e  cmp     rcx, rax
0x18009b421  jz      loc_18009B582
0x18009b427  test    byte ptr [rcx+1Ch], 1
0x18009b42b  jz      loc_18009B582
0x18009b431  mov     edx, 4Ch ; 'L'
0x18009b436  jmp     loc_18009B2E3
0x18009b43b  cmp     [rbp+pdwDataLen], 14h
0x18009b43f  jbe     short loc_18009B481
0x18009b441  mov     ebx, 8000FFFFh
0x18009b446  mov     rcx, cs:WPP_GLOBAL_Control
0x18009b44d  lea     rax, WPP_GLOBAL_Control
0x18009b454  cmp     rcx, rax
0x18009b457  jz      loc_18009B582
0x18009b45d  test    byte ptr [rcx+1Ch], 1
0x18009b461  jz      loc_18009B582
0x18009b467  mov     rcx, [rcx+10h]
0x18009b46b  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x18009b472  mov     edx, 4Dh ; 'M'
0x18009b477  call    WPP_SF_
0x18009b47c  jmp     loc_18009B582
0x18009b481  mov     rcx, [rbp+phHash]; hHash
0x18009b485  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x18009b489  lea     r8, [rbp+pbData]; pbData
0x18009b48d  mov     [rsp+70h+dwFlags], 0; dwFlags
0x18009b495  mov     edx, ebx; dwParam
0x18009b497  call    cs:__imp_CryptGetHashParam
0x18009b49e  nop     dword ptr [rax+rax+00h]
0x18009b4a3  test    eax, eax
0x18009b4a5  jnz     short loc_18009B4ED
0x18009b4a7  call    cs:__imp_GetLastError
0x18009b4ae  nop     dword ptr [rax+rax+00h]
0x18009b4b3  mov     ebx, eax
0x18009b4b5  test    eax, eax
0x18009b4b7  jle     short loc_18009B4C2
0x18009b4b9  movzx   ebx, ax
0x18009b4bc  or      ebx, 80070000h
0x18009b4c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18009b4c9  lea     rax, WPP_GLOBAL_Control
0x18009b4d0  cmp     rcx, rax
0x18009b4d3  jz      loc_18009B582
0x18009b4d9  test    byte ptr [rcx+1Ch], 1
0x18009b4dd  jz      loc_18009B582
0x18009b4e3  mov     edx, 4Eh ; 'N'
0x18009b4e8  jmp     loc_18009B2E3
0x18009b4ed  xor     eax, eax
0x18009b4ef  mov     [r14], ax
0x18009b4f3  xor     esi, esi
0x18009b4f5  cmp     esi, [rbp+pdwDataLen]
0x18009b4f8  jnb     loc_18009B580
0x18009b4fe  movzx   r9d, [rbp+rsi+pbData]
0x18009b504  lea     r8, asc_1800B9A20; "%x"
0x18009b50b  mov     edx, 3; unsigned __int64
0x18009b510  lea     rcx, [rbp+var_28]; wchar_t *
0x18009b514  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18009b519  mov     ebx, eax
0x18009b51b  test    eax, eax
0x18009b51d  js      short loc_18009B55D
0x18009b51f  lea     r8, [rbp+var_28]; wchar_t *
0x18009b523  mov     edx, 29h ; ')'; unsigned __int64
0x18009b528  mov     rcx, r14; wchar_t *
0x18009b52b  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18009b530  mov     ebx, eax
0x18009b532  test    eax, eax
0x18009b534  js      short loc_18009B53A
0x18009b536  inc     esi
0x18009b538  jmp     short loc_18009B4F5
0x18009b53a  mov     rcx, cs:WPP_GLOBAL_Control
0x18009b541  lea     rax, WPP_GLOBAL_Control
0x18009b548  cmp     rcx, rax
0x18009b54b  jz      short loc_18009B582
0x18009b54d  test    byte ptr [rcx+1Ch], 1
0x18009b551  jz      short loc_18009B582
0x18009b553  mov     edx, 50h ; 'P'
0x18009b558  jmp     loc_18009B2E3
0x18009b55d  mov     rcx, cs:WPP_GLOBAL_Control
0x18009b564  lea     rax, WPP_GLOBAL_Control
0x18009b56b  cmp     rcx, rax
0x18009b56e  jz      short loc_18009B582
0x18009b570  test    byte ptr [rcx+1Ch], 1
0x18009b574  jz      short loc_18009B582
0x18009b576  mov     edx, 4Fh ; 'O'
0x18009b57b  jmp     loc_18009B2E3
0x18009b580  xor     ebx, ebx
0x18009b582  mov     rcx, [rbp+phHash]; hHash
0x18009b586  test    rcx, rcx
0x18009b589  jz      short loc_18009B59F
0x18009b58b  call    cs:__imp_CryptDestroyHash
0x18009b592  nop     dword ptr [rax+rax+00h]
0x18009b597  mov     [rbp+phHash], 0
0x18009b59f  mov     rcx, [rbp+phProv]; hProv
0x18009b5a3  test    rcx, rcx
0x18009b5a6  jz      short loc_18009B5B6
0x18009b5a8  xor     edx, edx; dwFlags
0x18009b5aa  call    cs:__imp_CryptReleaseContext
0x18009b5b1  nop     dword ptr [rax+rax+00h]
0x18009b5b6  mov     eax, ebx
0x18009b5b8  jmp     short loc_18009B5ED
0x18009b5ba  mov     rcx, cs:WPP_GLOBAL_Control
0x18009b5c1  lea     rax, WPP_GLOBAL_Control
0x18009b5c8  cmp     rcx, rax
0x18009b5cb  jz      short loc_18009B5E8
0x18009b5cd  test    byte ptr [rcx+1Ch], 1
0x18009b5d1  jz      short loc_18009B5E8
0x18009b5d3  mov     rcx, [rcx+10h]
0x18009b5d7  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x18009b5de  mov     edx, 48h ; 'H'
0x18009b5e3  call    WPP_SF_
0x18009b5e8  mov     eax, 80070057h
0x18009b5ed  mov     rcx, [rbp+var_8]
0x18009b5f1  xor     rcx, rsp; StackCookie
0x18009b5f4  call    __security_check_cookie
0x18009b5f9  mov     rbx, [rsp+70h+arg_18]
0x18009b601  add     rsp, 70h
0x18009b605  pop     r14
0x18009b607  pop     rsi
0x18009b608  pop     rbp
0x18009b609  retn
```
