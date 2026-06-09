# FvepCheckForVolumeControlFiles

- ea: `0x140051ba4`
- end: `0x140051e26`
- name: `FvepCheckForVolumeControlFiles`
- size: `642`
- prototype: `__int64 __fastcall(HANDLE hDevice)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1400525bc`

## callees

- `0x14002e123`
- `0x14005192c`
- `0x1400519c0`
- `0x140051a38`
- `0x140051ba4`
- `0x1400529b0`
- `0x140052a44`
- `0x140052e80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140051c54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140051def`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140051c54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140051def`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x140051de5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x140051de5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140051dff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140051dff`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x140051da8`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x140051dc3`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x140051da8`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x140051dc3`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140051c4a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140051c4a`

## pseudocode

```c
__int64 __fastcall FvepCheckForVolumeControlFiles(HANDLE hDevice)
{
  size_t v2; // rdx
  const wchar_t *v3; // r8
  signed int LastError; // eax
  int v5; // ebx
  size_t v6; // rdx
  size_t v7; // rdx
  const wchar_t *v8; // r8
  size_t v9; // r15
  size_t v10; // rdx
  __int64 v11; // rcx
  size_t v12; // r14
  unsigned __int16 v13; // di
  HANDLE v14; // rdi
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  size_t pcchLength; // [rsp+48h] [rbp-B8h] BYREF
  size_t v18; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE Token; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t pszDest[264]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t psz[264]; // [rsp+270h] [rbp+170h] BYREF
  unsigned __int16 OutBuffer; // [rsp+480h] [rbp+380h] BYREF
  wchar_t pszSrc[263]; // [rsp+482h] [rbp+382h] BYREF

  v18 = 0;
  memset_0(&OutBuffer, 0, 0x20Eu);
  BytesReturned = 0;
  memset_0(pszDest, 0, 0x20Au);
  pcchLength = 0;
  Token = (HANDLE)-1LL;
  if ( DeviceIoControl(hDevice, 0x4D0008u, 0, 0, &OutBuffer, 0x20Eu, &BytesReturned, 0) )
  {
    v5 = StringCchCopyW(pszDest, v2, v3);
    if ( v5 >= 0 )
    {
      v5 = StringCchCatNW(pszDest, v6, pszSrc, (unsigned __int64)OutBuffer >> 1);
      if ( v5 >= 0 )
      {
        v5 = StringCchCatW(
               pszDest,
               0x105u,
               L"\\System Volume Information\\FVE.{e40ad34d-dae9-4bc7-95bd-b16218c10f72}.X");
        if ( v5 >= 0 )
        {
          v5 = StringCchLengthW(pszDest, 0x105u, &pcchLength);
          if ( v5 >= 0 )
          {
            v9 = pcchLength;
            if ( pcchLength )
            {
              v5 = StringCchCopyW(psz, v7, v8);
              if ( v5 >= 0 )
              {
                v5 = StringCchCatNW(psz, v10, pszSrc, (unsigned __int64)OutBuffer >> 1);
                if ( v5 >= 0 )
                {
                  v5 = StringCchCatW(
                         psz,
                         0x105u,
                         L"\\System Volume Information\\FVE2.{e40ad34d-dae9-4bc7-95bd-b16218c10f72}.X");
                  if ( v5 >= 0 )
                  {
                    v5 = StringCchLengthW(psz, 0x105u, &v18);
                    if ( v5 >= 0 )
                    {
                      v12 = v18;
                      if ( v18 )
                      {
                        v5 = FvepAcquirePrivilege(v11, &Token);
                        if ( v5 >= 0 )
                        {
                          v13 = 0;
                          v5 = 1;
                          while ( v13 < 3u )
                          {
                            pszDest[v9 - 1] = v13 + 49;
                            if ( GetFileAttributesW(pszDest) != -1
                              || (pszDest[v12 + 263] = v13 + 49, GetFileAttributesW(psz) != -1) )
                            {
                              v5 = 0;
                              break;
                            }
                            ++v13;
                          }
                        }
                        v14 = Token;
                        if ( Token != (HANDLE)-1LL )
                        {
                          if ( SetThreadToken(0, Token) )
                          {
                            if ( v14 )
                              CloseHandle(v14);
                          }
                          else
                          {
                            GetLastError();
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140051ba4  push    rbp
0x140051ba6  push    rbx
0x140051ba7  push    rsi
0x140051ba8  push    rdi
0x140051ba9  push    r14
0x140051bab  push    r15
0x140051bad  lea     rbp, [rsp-5A8h]
0x140051bb5  sub     rsp, 6A8h
0x140051bbc  mov     rax, cs:__security_cookie
0x140051bc3  xor     rax, rsp
0x140051bc6  mov     [rbp+5D0h+var_40], rax
0x140051bcd  mov     rbx, rcx
0x140051bd0  mov     [rsp+6D0h+var_680], 0
0x140051bd9  mov     edi, 20Eh
0x140051bde  lea     rcx, [rbp+5D0h+OutBuffer]; void *
0x140051be5  mov     r8d, edi; Size
0x140051be8  xor     edx, edx; Val
0x140051bea  call    memset_0
0x140051bef  xor     edx, edx; Val
0x140051bf1  mov     [rsp+6D0h+BytesReturned], 0
0x140051bf9  lea     r8d, [rdi-4]; Size
0x140051bfd  lea     rcx, [rsp+6D0h+pszDest]; void *
0x140051c02  call    memset_0
0x140051c07  mov     [rsp+6D0h+lpOverlapped], 0; lpOverlapped
0x140051c10  lea     rax, [rsp+6D0h+BytesReturned]
0x140051c15  mov     [rsp+6D0h+lpBytesReturned], rax; lpBytesReturned
0x140051c1a  xor     r9d, r9d; nInBufferSize
0x140051c1d  lea     rax, [rbp+5D0h+OutBuffer]
0x140051c24  mov     [rsp+6D0h+nOutBufferSize], edi; nOutBufferSize
0x140051c28  xor     r8d, r8d; lpInBuffer
0x140051c2b  mov     [rsp+6D0h+lpOutBuffer], rax; lpOutBuffer
0x140051c30  mov     edx, 4D0008h; dwIoControlCode
0x140051c35  mov     [rsp+6D0h+pcchLength], 0
0x140051c3e  mov     rcx, rbx; hDevice
0x140051c41  mov     [rsp+6D0h+Token], 0FFFFFFFFFFFFFFFFh
0x140051c4a  call    cs:__imp_DeviceIoControl
0x140051c50  test    eax, eax
0x140051c52  jnz     short loc_140051C72
0x140051c54  call    cs:__imp_GetLastError
0x140051c5a  mov     ebx, eax
0x140051c5c  test    eax, eax
0x140051c5e  jle     loc_140051E05
0x140051c64  movzx   ebx, ax
0x140051c67  or      ebx, 80070000h
0x140051c6d  jmp     loc_140051E05
0x140051c72  lea     rcx, [rsp+6D0h+pszDest]; pszDest
0x140051c77  call    StringCchCopyW
0x140051c7c  mov     ebx, eax
0x140051c7e  test    eax, eax
0x140051c80  js      loc_140051E05
0x140051c86  movzx   r9d, [rbp+5D0h+OutBuffer]
0x140051c8e  lea     r8, [rbp+5D0h+pszSrc]; pszSrc
0x140051c95  shr     r9, 1; cchToAppend
0x140051c98  lea     rcx, [rsp+6D0h+pszDest]; pszDest
0x140051c9d  call    StringCchCatNW
0x140051ca2  mov     ebx, eax
0x140051ca4  test    eax, eax
0x140051ca6  js      loc_140051E05
0x140051cac  mov     edi, 105h
0x140051cb1  lea     r8, aSystemVolumeIn_0; "\\System Volume Information\\FVE.{e40ad"...
0x140051cb8  mov     edx, edi; cchDest
0x140051cba  lea     rcx, [rsp+6D0h+pszDest]; pszDest
0x140051cbf  call    StringCchCatW
0x140051cc4  mov     ebx, eax
0x140051cc6  test    eax, eax
0x140051cc8  js      loc_140051E05
0x140051cce  lea     r8, [rsp+6D0h+pcchLength]; pcchLength
0x140051cd3  mov     edx, edi; cchMax
0x140051cd5  lea     rcx, [rsp+6D0h+pszDest]; psz
0x140051cda  call    StringCchLengthW
0x140051cdf  mov     ebx, eax
0x140051ce1  test    eax, eax
0x140051ce3  js      loc_140051E05
0x140051ce9  mov     r15, [rsp+6D0h+pcchLength]
0x140051cee  test    r15, r15
0x140051cf1  jz      loc_140051E05
0x140051cf7  lea     rcx, [rbp+5D0h+psz]; pszDest
0x140051cfe  call    StringCchCopyW
0x140051d03  mov     ebx, eax
0x140051d05  test    eax, eax
0x140051d07  js      loc_140051E05
0x140051d0d  movzx   r9d, [rbp+5D0h+OutBuffer]
0x140051d15  lea     r8, [rbp+5D0h+pszSrc]; pszSrc
0x140051d1c  shr     r9, 1; cchToAppend
0x140051d1f  lea     rcx, [rbp+5D0h+psz]; pszDest
0x140051d26  call    StringCchCatNW
0x140051d2b  mov     ebx, eax
0x140051d2d  test    eax, eax
0x140051d2f  js      loc_140051E05
0x140051d35  lea     r8, aSystemVolumeIn; "\\System Volume Information\\FVE2.{e40a"...
0x140051d3c  mov     edx, edi; cchDest
0x140051d3e  lea     rcx, [rbp+5D0h+psz]; pszDest
0x140051d45  call    StringCchCatW
0x140051d4a  mov     ebx, eax
0x140051d4c  test    eax, eax
0x140051d4e  js      loc_140051E05
0x140051d54  lea     r8, [rsp+6D0h+var_680]; pcchLength
0x140051d59  mov     edx, edi; cchMax
0x140051d5b  lea     rcx, [rbp+5D0h+psz]; psz
0x140051d62  call    StringCchLengthW
0x140051d67  mov     ebx, eax
0x140051d69  test    eax, eax
0x140051d6b  js      loc_140051E05
0x140051d71  mov     r14, [rsp+6D0h+var_680]
0x140051d76  test    r14, r14
0x140051d79  jz      loc_140051E05
0x140051d7f  lea     rdx, [rsp+6D0h+Token]
0x140051d84  call    FvepAcquirePrivilege
0x140051d89  mov     ebx, eax
0x140051d8b  test    eax, eax
0x140051d8d  js      short loc_140051DD5
0x140051d8f  xor     edi, edi
0x140051d91  lea     ebx, [rdi+1]
0x140051d94  cmp     di, 3
0x140051d98  jnb     short loc_140051DD5
0x140051d9a  lea     esi, [rdi+31h]
0x140051d9d  lea     rcx, [rsp+6D0h+pszDest]; lpFileName
0x140051da2  mov     word ptr [rsp+r15*2+6D0h+Token+6], si
0x140051da8  call    cs:__imp_GetFileAttributesW
0x140051dae  cmp     eax, 0FFFFFFFFh
0x140051db1  jnz     short loc_140051DD3
0x140051db3  lea     rcx, [rbp+5D0h+psz]; lpFileName
0x140051dba  mov     [rbp+r14*2+5D0h+var_462], si
0x140051dc3  call    cs:__imp_GetFileAttributesW
0x140051dc9  cmp     eax, 0FFFFFFFFh
0x140051dcc  jnz     short loc_140051DD3
0x140051dce  add     di, bx
0x140051dd1  jmp     short loc_140051D94
0x140051dd3  xor     ebx, ebx
0x140051dd5  mov     rdi, [rsp+6D0h+Token]
0x140051dda  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x140051dde  jz      short loc_140051E05
0x140051de0  mov     rdx, rdi; Token
0x140051de3  xor     ecx, ecx; Thread
0x140051de5  call    cs:__imp_SetThreadToken
0x140051deb  test    eax, eax
0x140051ded  jnz     short loc_140051DF7
0x140051def  call    cs:__imp_GetLastError
0x140051df5  jmp     short loc_140051E05
0x140051df7  test    rdi, rdi
0x140051dfa  jz      short loc_140051E05
0x140051dfc  mov     rcx, rdi; hObject
0x140051dff  call    cs:__imp_CloseHandle
0x140051e05  mov     eax, ebx
0x140051e07  mov     rcx, [rbp+5D0h+var_40]
0x140051e0e  xor     rcx, rsp; StackCookie
0x140051e11  call    __security_check_cookie
0x140051e16  add     rsp, 6A8h
0x140051e1d  pop     r15
0x140051e1f  pop     r14
0x140051e21  pop     rdi
0x140051e22  pop     rsi
0x140051e23  pop     rbx
0x140051e24  pop     rbp
0x140051e25  retn
```
