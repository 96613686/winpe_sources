# FvepCheckForVolumeControlFiles

- ea: `0x1800320fc`
- end: `0x180032390`
- name: `FvepCheckForVolumeControlFiles`
- size: `660`
- prototype: `__int64 __fastcall(HANDLE hDevice)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180032b28`

## callees

- `0x180001580`
- `0x18000212c`
- `0x180007604`
- `0x180031e84`
- `0x180031f18`
- `0x180031f90`
- `0x1800320fc`
- `0x180032f1c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032369`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032369`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18003234f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18003234f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800321ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032359`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800321ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032359`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180032312`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003232d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180032312`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003232d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800321a2`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800321a2`

## pseudocode

```c
__int64 __fastcall FvepCheckForVolumeControlFiles(HANDLE hDevice)
{
  signed int LastError; // eax
  int v3; // ebx
  size_t v4; // rdx
  size_t v5; // r15
  size_t v6; // rdx
  __int64 v7; // rcx
  size_t v8; // r14
  unsigned __int16 v9; // di
  HANDLE v10; // rdi
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  size_t pcchLength; // [rsp+48h] [rbp-B8h] BYREF
  size_t v14; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE Token; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t pszDest[264]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t psz[264]; // [rsp+270h] [rbp+170h] BYREF
  unsigned __int16 OutBuffer; // [rsp+480h] [rbp+380h] BYREF
  wchar_t pszSrc[263]; // [rsp+482h] [rbp+382h] BYREF

  v14 = 0;
  memset_0(&OutBuffer, 0, 0x20Eu);
  BytesReturned = 0;
  memset_0(pszDest, 0, 0x20Au);
  pcchLength = 0;
  Token = (HANDLE)-1LL;
  if ( DeviceIoControl(hDevice, 0x4D0008u, 0, 0, &OutBuffer, 0x20Eu, &BytesReturned, 0) )
  {
    v3 = StringCchCopyW(pszDest, 0x105u, L"\\\\?\\GLOBALROOT");
    if ( v3 >= 0 )
    {
      v3 = StringCchCatNW(pszDest, v4, pszSrc, (unsigned __int64)OutBuffer >> 1);
      if ( v3 >= 0 )
      {
        v3 = StringCchCatW(
               pszDest,
               0x105u,
               L"\\System Volume Information\\FVE.{e40ad34d-dae9-4bc7-95bd-b16218c10f72}.X");
        if ( v3 >= 0 )
        {
          v3 = StringCchLengthW(pszDest, 0x105u, &pcchLength);
          if ( v3 >= 0 )
          {
            v5 = pcchLength;
            if ( pcchLength )
            {
              v3 = StringCchCopyW(psz, 0x105u, L"\\\\?\\GLOBALROOT");
              if ( v3 >= 0 )
              {
                v3 = StringCchCatNW(psz, v6, pszSrc, (unsigned __int64)OutBuffer >> 1);
                if ( v3 >= 0 )
                {
                  v3 = StringCchCatW(
                         psz,
                         0x105u,
                         L"\\System Volume Information\\FVE2.{e40ad34d-dae9-4bc7-95bd-b16218c10f72}.X");
                  if ( v3 >= 0 )
                  {
                    v3 = StringCchLengthW(psz, 0x105u, &v14);
                    if ( v3 >= 0 )
                    {
                      v8 = v14;
                      if ( v14 )
                      {
                        v3 = FvepAcquirePrivilege(v7, &Token);
                        if ( v3 >= 0 )
                        {
                          v9 = 0;
                          v3 = 1;
                          while ( v9 < 3u )
                          {
                            pszDest[v5 - 1] = v9 + 49;
                            if ( GetFileAttributesW(pszDest) != -1
                              || (pszDest[v8 + 263] = v9 + 49, GetFileAttributesW(psz) != -1) )
                            {
                              v3 = 0;
                              break;
                            }
                            ++v9;
                          }
                        }
                        v10 = Token;
                        if ( Token != (HANDLE)-1LL )
                        {
                          if ( SetThreadToken(0, Token) )
                          {
                            if ( v10 )
                              CloseHandle(v10);
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
    v3 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800320fc  push    rbp
0x1800320fe  push    rbx
0x1800320ff  push    rsi
0x180032100  push    rdi
0x180032101  push    r14
0x180032103  push    r15
0x180032105  lea     rbp, [rsp-5A8h]
0x18003210d  sub     rsp, 6A8h
0x180032114  mov     rax, cs:__security_cookie
0x18003211b  xor     rax, rsp
0x18003211e  mov     [rbp+5D0h+var_40], rax
0x180032125  mov     rbx, rcx
0x180032128  mov     [rsp+6D0h+var_680], 0
0x180032131  mov     edi, 20Eh
0x180032136  lea     rcx, [rbp+5D0h+OutBuffer]; void *
0x18003213d  mov     r8d, edi; Size
0x180032140  xor     edx, edx; Val
0x180032142  call    memset_0
0x180032147  xor     edx, edx; Val
0x180032149  mov     [rsp+6D0h+BytesReturned], 0
0x180032151  lea     r8d, [rdi-4]; Size
0x180032155  lea     rcx, [rsp+6D0h+pszDest]; void *
0x18003215a  call    memset_0
0x18003215f  mov     [rsp+6D0h+lpOverlapped], 0; lpOverlapped
0x180032168  lea     rax, [rsp+6D0h+BytesReturned]
0x18003216d  mov     [rsp+6D0h+lpBytesReturned], rax; lpBytesReturned
0x180032172  xor     r9d, r9d; nInBufferSize
0x180032175  lea     rax, [rbp+5D0h+OutBuffer]
0x18003217c  mov     [rsp+6D0h+nOutBufferSize], edi; nOutBufferSize
0x180032180  xor     r8d, r8d; lpInBuffer
0x180032183  mov     [rsp+6D0h+lpOutBuffer], rax; lpOutBuffer
0x180032188  mov     edx, 4D0008h; dwIoControlCode
0x18003218d  mov     [rsp+6D0h+pcchLength], 0
0x180032196  mov     rcx, rbx; hDevice
0x180032199  mov     [rsp+6D0h+Token], 0FFFFFFFFFFFFFFFFh
0x1800321a2  call    cs:__imp_DeviceIoControl
0x1800321a8  test    eax, eax
0x1800321aa  jnz     short loc_1800321CA
0x1800321ac  call    cs:__imp_GetLastError
0x1800321b2  mov     ebx, eax
0x1800321b4  test    eax, eax
0x1800321b6  jle     loc_18003236F
0x1800321bc  movzx   ebx, ax
0x1800321bf  or      ebx, 80070000h
0x1800321c5  jmp     loc_18003236F
0x1800321ca  mov     edi, 105h
0x1800321cf  lea     r8, aGlobalroot; "\\\\?\\GLOBALROOT"
0x1800321d6  mov     edx, edi; unsigned __int64
0x1800321d8  lea     rcx, [rsp+6D0h+pszDest]; unsigned __int16 *
0x1800321dd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800321e2  mov     ebx, eax
0x1800321e4  test    eax, eax
0x1800321e6  js      loc_18003236F
0x1800321ec  movzx   r9d, [rbp+5D0h+OutBuffer]
0x1800321f4  lea     r8, [rbp+5D0h+pszSrc]; pszSrc
0x1800321fb  shr     r9, 1; cchToAppend
0x1800321fe  lea     rcx, [rsp+6D0h+pszDest]; pszDest
0x180032203  call    StringCchCatNW
0x180032208  mov     ebx, eax
0x18003220a  test    eax, eax
0x18003220c  js      loc_18003236F
0x180032212  lea     r8, aSystemVolumeIn_0; "\\System Volume Information\\FVE.{e40ad"...
0x180032219  mov     edx, edi; cchDest
0x18003221b  lea     rcx, [rsp+6D0h+pszDest]; pszDest
0x180032220  call    StringCchCatW
0x180032225  mov     ebx, eax
0x180032227  test    eax, eax
0x180032229  js      loc_18003236F
0x18003222f  lea     r8, [rsp+6D0h+pcchLength]; pcchLength
0x180032234  mov     edx, edi; cchMax
0x180032236  lea     rcx, [rsp+6D0h+pszDest]; psz
0x18003223b  call    StringCchLengthW
0x180032240  mov     ebx, eax
0x180032242  test    eax, eax
0x180032244  js      loc_18003236F
0x18003224a  mov     r15, [rsp+6D0h+pcchLength]
0x18003224f  test    r15, r15
0x180032252  jz      loc_18003236F
0x180032258  lea     r8, aGlobalroot; "\\\\?\\GLOBALROOT"
0x18003225f  mov     edx, edi; unsigned __int64
0x180032261  lea     rcx, [rbp+5D0h+psz]; unsigned __int16 *
0x180032268  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003226d  mov     ebx, eax
0x18003226f  test    eax, eax
0x180032271  js      loc_18003236F
0x180032277  movzx   r9d, [rbp+5D0h+OutBuffer]
0x18003227f  lea     r8, [rbp+5D0h+pszSrc]; pszSrc
0x180032286  shr     r9, 1; cchToAppend
0x180032289  lea     rcx, [rbp+5D0h+psz]; pszDest
0x180032290  call    StringCchCatNW
0x180032295  mov     ebx, eax
0x180032297  test    eax, eax
0x180032299  js      loc_18003236F
0x18003229f  lea     r8, aSystemVolumeIn; "\\System Volume Information\\FVE2.{e40a"...
0x1800322a6  mov     edx, edi; cchDest
0x1800322a8  lea     rcx, [rbp+5D0h+psz]; pszDest
0x1800322af  call    StringCchCatW
0x1800322b4  mov     ebx, eax
0x1800322b6  test    eax, eax
0x1800322b8  js      loc_18003236F
0x1800322be  lea     r8, [rsp+6D0h+var_680]; pcchLength
0x1800322c3  mov     edx, edi; cchMax
0x1800322c5  lea     rcx, [rbp+5D0h+psz]; psz
0x1800322cc  call    StringCchLengthW
0x1800322d1  mov     ebx, eax
0x1800322d3  test    eax, eax
0x1800322d5  js      loc_18003236F
0x1800322db  mov     r14, [rsp+6D0h+var_680]
0x1800322e0  test    r14, r14
0x1800322e3  jz      loc_18003236F
0x1800322e9  lea     rdx, [rsp+6D0h+Token]
0x1800322ee  call    FvepAcquirePrivilege
0x1800322f3  mov     ebx, eax
0x1800322f5  test    eax, eax
0x1800322f7  js      short loc_18003233F
0x1800322f9  xor     edi, edi
0x1800322fb  lea     ebx, [rdi+1]
0x1800322fe  cmp     di, 3
0x180032302  jnb     short loc_18003233F
0x180032304  lea     esi, [rdi+31h]
0x180032307  lea     rcx, [rsp+6D0h+pszDest]; lpFileName
0x18003230c  mov     word ptr [rsp+r15*2+6D0h+Token+6], si
0x180032312  call    cs:__imp_GetFileAttributesW
0x180032318  cmp     eax, 0FFFFFFFFh
0x18003231b  jnz     short loc_18003233D
0x18003231d  lea     rcx, [rbp+5D0h+psz]; lpFileName
0x180032324  mov     [rbp+r14*2+5D0h+var_462], si
0x18003232d  call    cs:__imp_GetFileAttributesW
0x180032333  cmp     eax, 0FFFFFFFFh
0x180032336  jnz     short loc_18003233D
0x180032338  add     di, bx
0x18003233b  jmp     short loc_1800322FE
0x18003233d  xor     ebx, ebx
0x18003233f  mov     rdi, [rsp+6D0h+Token]
0x180032344  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180032348  jz      short loc_18003236F
0x18003234a  mov     rdx, rdi; Token
0x18003234d  xor     ecx, ecx; Thread
0x18003234f  call    cs:__imp_SetThreadToken
0x180032355  test    eax, eax
0x180032357  jnz     short loc_180032361
0x180032359  call    cs:__imp_GetLastError
0x18003235f  jmp     short loc_18003236F
0x180032361  test    rdi, rdi
0x180032364  jz      short loc_18003236F
0x180032366  mov     rcx, rdi; hObject
0x180032369  call    cs:__imp_CloseHandle
0x18003236f  mov     eax, ebx
0x180032371  mov     rcx, [rbp+5D0h+var_40]
0x180032378  xor     rcx, rsp; StackCookie
0x18003237b  call    __security_check_cookie
0x180032380  add     rsp, 6A8h
0x180032387  pop     r15
0x180032389  pop     r14
0x18003238b  pop     rdi
0x18003238c  pop     rsi
0x18003238d  pop     rbx
0x18003238e  pop     rbp
0x18003238f  retn
```
