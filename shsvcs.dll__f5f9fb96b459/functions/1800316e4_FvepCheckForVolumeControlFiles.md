# FvepCheckForVolumeControlFiles

- ea: `0x1800316e4`
- end: `0x180031966`
- name: `FvepCheckForVolumeControlFiles`
- size: `642`
- prototype: `__int64 __fastcall(HANDLE hDevice)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800320fc`

## callees

- `0x180018328`
- `0x1800314e4`
- `0x180031578`
- `0x1800316e4`
- `0x1800324f0`
- `0x180032584`
- `0x180032c6a`
- `0x180032c90`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180031925`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180031925`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031794`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003192f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031794`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003192f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003193f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003193f`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18003178a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18003178a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800318e8`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180031903`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800318e8`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180031903`

## pseudocode

```c
__int64 __fastcall FvepCheckForVolumeControlFiles(HANDLE hDevice)
{
  size_t v2; // rdx
  const wchar_t *v3; // r8
  signed int LastError; // eax
  HRESULT v5; // ebx
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
0x1800316e4  push    rbp
0x1800316e6  push    rbx
0x1800316e7  push    rsi
0x1800316e8  push    rdi
0x1800316e9  push    r14
0x1800316eb  push    r15
0x1800316ed  lea     rbp, [rsp-5A8h]
0x1800316f5  sub     rsp, 6A8h
0x1800316fc  mov     rax, cs:__security_cookie
0x180031703  xor     rax, rsp
0x180031706  mov     [rbp+5D0h+var_40], rax
0x18003170d  mov     rbx, rcx
0x180031710  mov     [rsp+6D0h+var_680], 0
0x180031719  mov     edi, 20Eh
0x18003171e  lea     rcx, [rbp+5D0h+OutBuffer]; void *
0x180031725  mov     r8d, edi; Size
0x180031728  xor     edx, edx; Val
0x18003172a  call    memset_0
0x18003172f  xor     edx, edx; Val
0x180031731  mov     [rsp+6D0h+BytesReturned], 0
0x180031739  lea     r8d, [rdi-4]; Size
0x18003173d  lea     rcx, [rsp+6D0h+pszDest]; void *
0x180031742  call    memset_0
0x180031747  mov     [rsp+6D0h+lpOverlapped], 0; lpOverlapped
0x180031750  lea     rax, [rsp+6D0h+BytesReturned]
0x180031755  mov     [rsp+6D0h+lpBytesReturned], rax; lpBytesReturned
0x18003175a  xor     r9d, r9d; nInBufferSize
0x18003175d  lea     rax, [rbp+5D0h+OutBuffer]
0x180031764  mov     [rsp+6D0h+nOutBufferSize], edi; nOutBufferSize
0x180031768  xor     r8d, r8d; lpInBuffer
0x18003176b  mov     [rsp+6D0h+lpOutBuffer], rax; lpOutBuffer
0x180031770  mov     edx, 4D0008h; dwIoControlCode
0x180031775  mov     [rsp+6D0h+pcchLength], 0
0x18003177e  mov     rcx, rbx; hDevice
0x180031781  mov     [rsp+6D0h+Token], 0FFFFFFFFFFFFFFFFh
0x18003178a  call    cs:__imp_DeviceIoControl
0x180031790  test    eax, eax
0x180031792  jnz     short loc_1800317B2
0x180031794  call    cs:__imp_GetLastError
0x18003179a  mov     ebx, eax
0x18003179c  test    eax, eax
0x18003179e  jle     loc_180031945
0x1800317a4  movzx   ebx, ax
0x1800317a7  or      ebx, 80070000h
0x1800317ad  jmp     loc_180031945
0x1800317b2  lea     rcx, [rsp+6D0h+pszDest]; pszDest
0x1800317b7  call    StringCchCopyW
0x1800317bc  mov     ebx, eax
0x1800317be  test    eax, eax
0x1800317c0  js      loc_180031945
0x1800317c6  movzx   r9d, [rbp+5D0h+OutBuffer]
0x1800317ce  lea     r8, [rbp+5D0h+pszSrc]; pszSrc
0x1800317d5  shr     r9, 1; cchToAppend
0x1800317d8  lea     rcx, [rsp+6D0h+pszDest]; pszDest
0x1800317dd  call    StringCchCatNW
0x1800317e2  mov     ebx, eax
0x1800317e4  test    eax, eax
0x1800317e6  js      loc_180031945
0x1800317ec  mov     edi, 105h
0x1800317f1  lea     r8, aSystemVolumeIn_0; "\\System Volume Information\\FVE.{e40ad"...
0x1800317f8  mov     edx, edi; cchDest
0x1800317fa  lea     rcx, [rsp+6D0h+pszDest]; pszDest
0x1800317ff  call    StringCchCatW
0x180031804  mov     ebx, eax
0x180031806  test    eax, eax
0x180031808  js      loc_180031945
0x18003180e  lea     r8, [rsp+6D0h+pcchLength]; pcchLength
0x180031813  mov     edx, edi; cchMax
0x180031815  lea     rcx, [rsp+6D0h+pszDest]; psz
0x18003181a  call    StringCchLengthW
0x18003181f  mov     ebx, eax
0x180031821  test    eax, eax
0x180031823  js      loc_180031945
0x180031829  mov     r15, [rsp+6D0h+pcchLength]
0x18003182e  test    r15, r15
0x180031831  jz      loc_180031945
0x180031837  lea     rcx, [rbp+5D0h+psz]; pszDest
0x18003183e  call    StringCchCopyW
0x180031843  mov     ebx, eax
0x180031845  test    eax, eax
0x180031847  js      loc_180031945
0x18003184d  movzx   r9d, [rbp+5D0h+OutBuffer]
0x180031855  lea     r8, [rbp+5D0h+pszSrc]; pszSrc
0x18003185c  shr     r9, 1; cchToAppend
0x18003185f  lea     rcx, [rbp+5D0h+psz]; pszDest
0x180031866  call    StringCchCatNW
0x18003186b  mov     ebx, eax
0x18003186d  test    eax, eax
0x18003186f  js      loc_180031945
0x180031875  lea     r8, aSystemVolumeIn; "\\System Volume Information\\FVE2.{e40a"...
0x18003187c  mov     edx, edi; cchDest
0x18003187e  lea     rcx, [rbp+5D0h+psz]; pszDest
0x180031885  call    StringCchCatW
0x18003188a  mov     ebx, eax
0x18003188c  test    eax, eax
0x18003188e  js      loc_180031945
0x180031894  lea     r8, [rsp+6D0h+var_680]; pcchLength
0x180031899  mov     edx, edi; cchMax
0x18003189b  lea     rcx, [rbp+5D0h+psz]; psz
0x1800318a2  call    StringCchLengthW
0x1800318a7  mov     ebx, eax
0x1800318a9  test    eax, eax
0x1800318ab  js      loc_180031945
0x1800318b1  mov     r14, [rsp+6D0h+var_680]
0x1800318b6  test    r14, r14
0x1800318b9  jz      loc_180031945
0x1800318bf  lea     rdx, [rsp+6D0h+Token]
0x1800318c4  call    FvepAcquirePrivilege
0x1800318c9  mov     ebx, eax
0x1800318cb  test    eax, eax
0x1800318cd  js      short loc_180031915
0x1800318cf  xor     edi, edi
0x1800318d1  lea     ebx, [rdi+1]
0x1800318d4  cmp     di, 3
0x1800318d8  jnb     short loc_180031915
0x1800318da  lea     esi, [rdi+31h]
0x1800318dd  lea     rcx, [rsp+6D0h+pszDest]; lpFileName
0x1800318e2  mov     word ptr [rsp+r15*2+6D0h+Token+6], si
0x1800318e8  call    cs:__imp_GetFileAttributesW
0x1800318ee  cmp     eax, 0FFFFFFFFh
0x1800318f1  jnz     short loc_180031913
0x1800318f3  lea     rcx, [rbp+5D0h+psz]; lpFileName
0x1800318fa  mov     [rbp+r14*2+5D0h+var_462], si
0x180031903  call    cs:__imp_GetFileAttributesW
0x180031909  cmp     eax, 0FFFFFFFFh
0x18003190c  jnz     short loc_180031913
0x18003190e  add     di, bx
0x180031911  jmp     short loc_1800318D4
0x180031913  xor     ebx, ebx
0x180031915  mov     rdi, [rsp+6D0h+Token]
0x18003191a  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18003191e  jz      short loc_180031945
0x180031920  mov     rdx, rdi; Token
0x180031923  xor     ecx, ecx; Thread
0x180031925  call    cs:__imp_SetThreadToken
0x18003192b  test    eax, eax
0x18003192d  jnz     short loc_180031937
0x18003192f  call    cs:__imp_GetLastError
0x180031935  jmp     short loc_180031945
0x180031937  test    rdi, rdi
0x18003193a  jz      short loc_180031945
0x18003193c  mov     rcx, rdi; hObject
0x18003193f  call    cs:__imp_CloseHandle
0x180031945  mov     eax, ebx
0x180031947  mov     rcx, [rbp+5D0h+var_40]
0x18003194e  xor     rcx, rsp; StackCookie
0x180031951  call    __security_check_cookie
0x180031956  add     rsp, 6A8h
0x18003195d  pop     r15
0x18003195f  pop     r14
0x180031961  pop     rdi
0x180031962  pop     rsi
0x180031963  pop     rbx
0x180031964  pop     rbp
0x180031965  retn
```
