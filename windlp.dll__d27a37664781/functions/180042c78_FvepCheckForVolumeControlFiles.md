# FvepCheckForVolumeControlFiles

- ea: `0x180042c78`
- end: `0x180042fc2`
- name: `FvepCheckForVolumeControlFiles`
- size: `842`
- prototype: `__int64 __fastcall(HANDLE hDevice)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800437d4`

## callees

- `0x1800323e0`
- `0x180035b6c`
- `0x180042b0c`
- `0x180042c78`
- `0x18007ec9a`
- `0x18007ed40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180042f7d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180042f7d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180042f36`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180042f50`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180042f36`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180042f50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042d16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042f87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042d16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042f87`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042f97`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042f97`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180042d0c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180042d0c`

## pseudocode

```c
__int64 __fastcall FvepCheckForVolumeControlFiles(HANDLE hDevice)
{
  signed int LastError; // eax
  signed int v3; // ebx
  __int64 v4; // rsi
  const wchar_t *v5; // r14
  wchar_t *v6; // r8
  __int64 v7; // rax
  const wchar_t *v8; // rcx
  size_t v9; // rdx
  wchar_t *v10; // rcx
  __int64 v11; // rdx
  wchar_t *v12; // rax
  __int64 v13; // r15
  size_t v14; // rdx
  wchar_t *v15; // r8
  wchar_t *v16; // rcx
  __int64 v17; // rcx
  wchar_t *v18; // rax
  __int64 v19; // rsi
  __int16 v20; // bx
  HANDLE v21; // rdi
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE Token; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t FileName[264]; // [rsp+260h] [rbp+160h] BYREF
  unsigned __int16 OutBuffer; // [rsp+470h] [rbp+370h] BYREF
  wchar_t pszSrc[263]; // [rsp+472h] [rbp+372h] BYREF

  memset_0(&OutBuffer, 0, 0x20Eu);
  BytesReturned = 0;
  memset_0(pszDest, 0, 0x20Au);
  Token = (HANDLE)-1LL;
  if ( !DeviceIoControl(hDevice, 0x4D0008u, 0, 0, &OutBuffer, 0x20Eu, &BytesReturned, 0) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
    return (unsigned int)v3;
  }
  v4 = 2147483646;
  v5 = L"\\\\?\\GLOBALROOT";
  v6 = pszDest;
  v7 = 2147483646;
  v8 = L"\\\\?\\GLOBALROOT";
  v9 = 261;
  do
  {
    if ( !v7 )
      break;
    if ( !*v8 )
      break;
    *v6++ = *v8++;
    --v7;
    --v9;
  }
  while ( v9 );
  v10 = v6 - 1;
  v3 = v9 == 0 ? 0x8007007A : 0;
  if ( v9 )
    v10 = v6;
  *v10 = 0;
  if ( v9 )
  {
    v3 = StringCchCatNW(pszDest, v9, pszSrc, (unsigned __int64)OutBuffer >> 1);
    if ( v3 >= 0 )
    {
      v3 = StringCchCatW(pszDest, 0x105u, L"\\System Volume Information\\FVE.{e40ad34d-dae9-4bc7-95bd-b16218c10f72}.X");
      if ( v3 >= 0 )
      {
        v11 = 261;
        v12 = pszDest;
        do
        {
          if ( !*v12 )
            break;
          ++v12;
          --v11;
        }
        while ( v11 );
        v3 = v11 == 0 ? 0x80070057 : 0;
        v13 = (261 - v11) & -(__int64)(v11 != 0);
        if ( v11 )
        {
          if ( v13 )
          {
            v14 = 261;
            v15 = FileName;
            do
            {
              if ( !v4 )
                break;
              if ( !*v5 )
                break;
              *v15++ = *v5++;
              --v4;
              --v14;
            }
            while ( v14 );
            v16 = v15 - 1;
            v3 = v14 == 0 ? 0x8007007A : 0;
            if ( v14 )
              v16 = v15;
            *v16 = 0;
            if ( v14 )
            {
              v3 = StringCchCatNW(FileName, v14, pszSrc, (unsigned __int64)OutBuffer >> 1);
              if ( v3 < 0 )
                return (unsigned int)v3;
              v3 = StringCchCatW(
                     FileName,
                     0x105u,
                     L"\\System Volume Information\\FVE2.{e40ad34d-dae9-4bc7-95bd-b16218c10f72}.X");
              if ( v3 < 0 )
                return (unsigned int)v3;
              v17 = 261;
              v18 = FileName;
              do
              {
                if ( !*v18 )
                  break;
                ++v18;
                --v17;
              }
              while ( v17 );
              v3 = v17 == 0 ? 0x80070057 : 0;
              v19 = (261 - v17) & -(__int64)(v17 != 0);
              if ( !v17 || !v19 )
                return (unsigned int)v3;
              v3 = FvepAcquirePrivilege(v17, &Token);
              if ( v3 >= 0 )
              {
                v20 = 0;
                while ( 1 )
                {
                  pszDest[v13 - 1] = v20 + 49;
                  if ( GetFileAttributesW(pszDest) != -1 )
                    break;
                  pszDest[v19 + 263] = v20 + 49;
                  if ( GetFileAttributesW(FileName) != -1 )
                    break;
                  if ( (unsigned __int16)++v20 >= 3u )
                  {
                    v3 = 1;
                    goto LABEL_39;
                  }
                }
                v3 = 0;
              }
            }
LABEL_39:
            v21 = Token;
            if ( Token != (HANDLE)-1LL )
            {
              if ( SetThreadToken(0, Token) )
              {
                if ( v21 )
                  CloseHandle(v21);
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
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180042c78  push    rbp
0x180042c7a  push    rbx
0x180042c7b  push    rsi
0x180042c7c  push    rdi
0x180042c7d  push    r12
0x180042c7f  push    r13
0x180042c81  push    r14
0x180042c83  push    r15
0x180042c85  lea     rbp, [rsp-598h]
0x180042c8d  sub     rsp, 698h
0x180042c94  mov     rax, cs:__security_cookie
0x180042c9b  xor     rax, rsp
0x180042c9e  mov     [rbp+5D0h+var_50], rax
0x180042ca5  mov     rbx, rcx
0x180042ca8  mov     edi, 20Eh
0x180042cad  mov     r8d, edi; Size
0x180042cb0  lea     rcx, [rbp+5D0h+OutBuffer]; void *
0x180042cb7  xor     edx, edx; Val
0x180042cb9  call    memset_0
0x180042cbe  xor     r12d, r12d
0x180042cc1  lea     r8d, [rdi-4]; Size
0x180042cc5  xor     edx, edx; Val
0x180042cc7  mov     [rsp+6D0h+BytesReturned], r12d
0x180042ccc  lea     rcx, [rsp+6D0h+pszDest]; void *
0x180042cd1  call    memset_0
0x180042cd6  mov     [rsp+6D0h+lpOverlapped], r12; lpOverlapped
0x180042cdb  lea     rax, [rsp+6D0h+BytesReturned]
0x180042ce0  mov     [rsp+6D0h+lpBytesReturned], rax; lpBytesReturned
0x180042ce5  xor     r9d, r9d; nInBufferSize
0x180042ce8  lea     rax, [rbp+5D0h+OutBuffer]
0x180042cef  mov     [rsp+6D0h+nOutBufferSize], edi; nOutBufferSize
0x180042cf3  xor     r8d, r8d; lpInBuffer
0x180042cf6  mov     [rsp+6D0h+lpOutBuffer], rax; lpOutBuffer
0x180042cfb  mov     edx, 4D0008h; dwIoControlCode
0x180042d00  mov     [rsp+6D0h+Token], 0FFFFFFFFFFFFFFFFh
0x180042d09  mov     rcx, rbx; hDevice
0x180042d0c  call    cs:__imp_DeviceIoControl
0x180042d12  test    eax, eax
0x180042d14  jnz     short loc_180042D34
0x180042d16  call    cs:__imp_GetLastError
0x180042d1c  mov     ebx, eax
0x180042d1e  test    eax, eax
0x180042d20  jle     loc_180042F9D
0x180042d26  movzx   ebx, ax
0x180042d29  or      ebx, 80070000h
0x180042d2f  jmp     loc_180042F9D
0x180042d34  mov     esi, 7FFFFFFEh
0x180042d39  lea     r14, aGlobalroot; "\\\\?\\GLOBALROOT"
0x180042d40  mov     edi, 105h
0x180042d45  lea     r8, [rsp+6D0h+pszDest]
0x180042d4a  mov     eax, esi
0x180042d4c  mov     rcx, r14
0x180042d4f  mov     edx, edi
0x180042d51  mov     r13d, 1
0x180042d57  test    rax, rax
0x180042d5a  jz      short loc_180042D7A
0x180042d5c  movzx   r9d, word ptr [rcx]
0x180042d60  test    r9w, r9w
0x180042d64  jz      short loc_180042D7A
0x180042d66  mov     [r8], r9w
0x180042d6a  add     rcx, 2
0x180042d6e  add     r8, 2
0x180042d72  sub     rax, r13
0x180042d75  sub     rdx, r13; cchDest
0x180042d78  jnz     short loc_180042D57
0x180042d7a  mov     rax, rdx
0x180042d7d  lea     rcx, [r8-2]
0x180042d81  neg     rax
0x180042d84  sbb     ebx, ebx
0x180042d86  not     ebx
0x180042d88  and     ebx, 8007007Ah
0x180042d8e  test    rdx, rdx
0x180042d91  cmovnz  rcx, r8
0x180042d95  mov     [rcx], r12w
0x180042d99  jz      loc_180042F9D
0x180042d9f  movzx   r9d, [rbp+5D0h+OutBuffer]
0x180042da7  lea     r8, [rbp+5D0h+pszSrc]; pszSrc
0x180042dae  shr     r9, 1; cchToAppend
0x180042db1  lea     rcx, [rsp+6D0h+pszDest]; pszDest
0x180042db6  call    StringCchCatNW
0x180042dbb  mov     ebx, eax
0x180042dbd  test    eax, eax
0x180042dbf  js      loc_180042F9D
0x180042dc5  lea     r8, aSystemVolumeIn_1; "\\System Volume Information\\FVE.{e40ad"...
0x180042dcc  mov     rdx, rdi; cchDest
0x180042dcf  lea     rcx, [rsp+6D0h+pszDest]; pszDest
0x180042dd4  call    StringCchCatW
0x180042dd9  mov     ebx, eax
0x180042ddb  test    eax, eax
0x180042ddd  js      loc_180042F9D
0x180042de3  mov     rdx, rdi
0x180042de6  lea     rax, [rsp+6D0h+pszDest]
0x180042deb  cmp     [rax], r12w
0x180042def  jz      short loc_180042DFA
0x180042df1  add     rax, 2
0x180042df5  sub     rdx, r13
0x180042df8  jnz     short loc_180042DEB
0x180042dfa  mov     rax, rdx
0x180042dfd  mov     rcx, rdi
0x180042e00  neg     rax
0x180042e03  mov     rax, rdx
0x180042e06  sbb     ebx, ebx
0x180042e08  sub     rcx, rdx
0x180042e0b  not     ebx
0x180042e0d  and     ebx, 80070057h
0x180042e13  neg     rax
0x180042e16  sbb     r15, r15
0x180042e19  and     r15, rcx
0x180042e1c  test    rdx, rdx
0x180042e1f  jz      loc_180042F9D
0x180042e25  test    r15, r15
0x180042e28  jz      loc_180042F9D
0x180042e2e  mov     rdx, rdi
0x180042e31  lea     r8, [rbp+5D0h+FileName]
0x180042e38  test    rsi, rsi
0x180042e3b  jz      short loc_180042E5A
0x180042e3d  movzx   eax, word ptr [r14]
0x180042e41  test    ax, ax
0x180042e44  jz      short loc_180042E5A
0x180042e46  mov     [r8], ax
0x180042e4a  add     r14, 2
0x180042e4e  add     r8, 2
0x180042e52  sub     rsi, r13
0x180042e55  sub     rdx, r13; cchDest
0x180042e58  jnz     short loc_180042E38
0x180042e5a  mov     rax, rdx
0x180042e5d  lea     rcx, [r8-2]
0x180042e61  neg     rax
0x180042e64  sbb     ebx, ebx
0x180042e66  not     ebx
0x180042e68  and     ebx, 8007007Ah
0x180042e6e  test    rdx, rdx
0x180042e71  cmovnz  rcx, r8
0x180042e75  mov     [rcx], r12w
0x180042e79  jz      loc_180042F6D
0x180042e7f  movzx   r9d, [rbp+5D0h+OutBuffer]
0x180042e87  lea     r8, [rbp+5D0h+pszSrc]; pszSrc
0x180042e8e  shr     r9, 1; cchToAppend
0x180042e91  lea     rcx, [rbp+5D0h+FileName]; pszDest
0x180042e98  call    StringCchCatNW
0x180042e9d  mov     ebx, eax
0x180042e9f  test    eax, eax
0x180042ea1  js      loc_180042F9D
0x180042ea7  lea     r8, aSystemVolumeIn_0; "\\System Volume Information\\FVE2.{e40a"...
0x180042eae  mov     rdx, rdi; cchDest
0x180042eb1  lea     rcx, [rbp+5D0h+FileName]; pszDest
0x180042eb8  call    StringCchCatW
0x180042ebd  mov     ebx, eax
0x180042ebf  test    eax, eax
0x180042ec1  js      loc_180042F9D
0x180042ec7  mov     rcx, rdi
0x180042eca  lea     rax, [rbp+5D0h+FileName]
0x180042ed1  cmp     [rax], r12w
0x180042ed5  jz      short loc_180042EE0
0x180042ed7  add     rax, 2
0x180042edb  sub     rcx, r13
0x180042ede  jnz     short loc_180042ED1
0x180042ee0  mov     rax, rcx
0x180042ee3  neg     rax
0x180042ee6  mov     rax, rcx
0x180042ee9  sbb     ebx, ebx
0x180042eeb  sub     rdi, rcx
0x180042eee  not     ebx
0x180042ef0  and     ebx, 80070057h
0x180042ef6  neg     rax
0x180042ef9  sbb     rsi, rsi
0x180042efc  and     rsi, rdi
0x180042eff  test    rcx, rcx
0x180042f02  jz      loc_180042F9D
0x180042f08  test    rsi, rsi
0x180042f0b  jz      loc_180042F9D
0x180042f11  lea     rdx, [rsp+6D0h+Token]
0x180042f16  call    FvepAcquirePrivilege
0x180042f1b  mov     ebx, eax
0x180042f1d  test    eax, eax
0x180042f1f  js      short loc_180042F6D
0x180042f21  mov     ebx, r12d
0x180042f24  or      r14d, 0FFFFFFFFh
0x180042f28  lea     edi, [rbx+31h]
0x180042f2b  lea     rcx, [rsp+6D0h+pszDest]; lpFileName
0x180042f30  mov     word ptr [rsp+r15*2+6D0h+Token+6], di
0x180042f36  call    cs:__imp_GetFileAttributesW
0x180042f3c  cmp     eax, r14d
0x180042f3f  jnz     short loc_180042F6A
0x180042f41  lea     rcx, [rbp+5D0h+FileName]; lpFileName
0x180042f48  mov     [rbp+rsi*2+5D0h+var_472], di
0x180042f50  call    cs:__imp_GetFileAttributesW
0x180042f56  cmp     eax, r14d
0x180042f59  jnz     short loc_180042F6A
0x180042f5b  add     bx, r13w
0x180042f5f  cmp     bx, 3
0x180042f63  jb      short loc_180042F28
0x180042f65  mov     ebx, r13d
0x180042f68  jmp     short loc_180042F6D
0x180042f6a  mov     ebx, r12d
0x180042f6d  mov     rdi, [rsp+6D0h+Token]
0x180042f72  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180042f76  jz      short loc_180042F9D
0x180042f78  mov     rdx, rdi; Token
0x180042f7b  xor     ecx, ecx; Thread
0x180042f7d  call    cs:__imp_SetThreadToken
0x180042f83  test    eax, eax
0x180042f85  jnz     short loc_180042F8F
0x180042f87  call    cs:__imp_GetLastError
0x180042f8d  jmp     short loc_180042F9D
0x180042f8f  test    rdi, rdi
0x180042f92  jz      short loc_180042F9D
0x180042f94  mov     rcx, rdi; hObject
0x180042f97  call    cs:__imp_CloseHandle
0x180042f9d  mov     eax, ebx
0x180042f9f  mov     rcx, [rbp+5D0h+var_50]
0x180042fa6  xor     rcx, rsp; StackCookie
0x180042fa9  call    __security_check_cookie
0x180042fae  add     rsp, 698h
0x180042fb5  pop     r15
0x180042fb7  pop     r14
0x180042fb9  pop     r13
0x180042fbb  pop     r12
0x180042fbd  pop     rdi
0x180042fbe  pop     rsi
0x180042fbf  pop     rbx
0x180042fc0  pop     rbp
0x180042fc1  retn
```
