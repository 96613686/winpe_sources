# CallerIdentity::GetPackageSidFromProcessToken(void *,void * *)

- ea: `0x1802082cc`
- end: `0x1802083f5`
- name: `?GetPackageSidFromProcessToken@CallerIdentity@@YAJPEAXPEAPEAX@Z`
- size: `297`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800f61a8`

## callees

- `0x1802082cc`
- `0x18020849c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18020830c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18020830c`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1802083b9`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1802083b9`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18020838d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18020838d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1802082f8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180208369`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1802082f8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180208369`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802083da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802083e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802083da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802083e3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180208337`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18020839c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180208337`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18020839c`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetPackageSidFromProcessToken(HANDLE TokenHandle, _QWORD *a2, void **a3)
{
  signed int Error; // ebx
  signed int LastError; // eax
  PSID *v7; // rdi
  DWORD LengthSid; // ebx
  HLOCAL v9; // rax
  void *v10; // rsi
  DWORD TokenInformationLength; // [rsp+70h] [rbp+18h] BYREF

  TokenInformationLength = 0;
  if ( GetTokenInformation(TokenHandle, TokenAppContainerSid, 0, 0, &TokenInformationLength) )
    return (unsigned int)-2147418113;
  LastError = GetLastError();
  Error = LastError;
  if ( LastError == 122 )
    goto LABEL_24;
  if ( LastError > 0 )
    Error = (unsigned __int16)LastError | 0x80070000;
  if ( Error >= 0 )
  {
LABEL_24:
    v7 = (PSID *)LocalAlloc(0x40u, TokenInformationLength);
    if ( !v7 )
      return (unsigned int)-2147024882;
    if ( GetTokenInformation(TokenHandle, TokenAppContainerSid, v7, TokenInformationLength, &TokenInformationLength)
      || (Error = ResultFromKnownLastError(), Error >= 0) )
    {
      if ( *v7 )
      {
        LengthSid = GetLengthSid(*v7);
        v9 = LocalAlloc(0x40u, LengthSid);
        v10 = v9;
        if ( v9 )
        {
          if ( CopySid(LengthSid, v9, *v7) )
          {
            Error = 0;
          }
          else
          {
            Error = ResultFromKnownLastError();
            if ( Error < 0 )
            {
              LocalFree(v10);
              goto LABEL_20;
            }
          }
          *a2 = v10;
        }
        else
        {
          Error = -2147024882;
        }
      }
      else
      {
        Error = -2147023728;
      }
LABEL_20:
      LocalFree(v7);
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1802082cc  push    rbx
0x1802082ce  push    rsi
0x1802082cf  push    rdi
0x1802082d0  push    r14
0x1802082d2  sub     rsp, 38h
0x1802082d6  xor     r9d, r9d; TokenInformationLength
0x1802082d9  mov     [rsp+58h+TokenInformationLength], 0
0x1802082e1  mov     r14, rdx
0x1802082e4  lea     rax, [rsp+58h+TokenInformationLength]
0x1802082e9  xor     r8d, r8d; TokenInformation
0x1802082ec  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x1802082f1  mov     rsi, rcx
0x1802082f4  lea     edx, [r9+1Fh]; TokenInformationClass
0x1802082f8  call    cs:__imp_GetTokenInformation
0x1802082fe  test    eax, eax
0x180208300  jz      short loc_18020830C
0x180208302  mov     ebx, 8000FFFFh
0x180208307  jmp     loc_1802083E9
0x18020830c  call    cs:__imp_GetLastError
0x180208312  mov     ebx, eax
0x180208314  cmp     eax, 7Ah ; 'z'
0x180208317  jz      short loc_18020832E
0x180208319  test    eax, eax
0x18020831b  jle     short loc_180208326
0x18020831d  movzx   ebx, ax
0x180208320  or      ebx, 80070000h
0x180208326  test    ebx, ebx
0x180208328  js      loc_1802083E9
0x18020832e  mov     edx, [rsp+58h+TokenInformationLength]; uBytes
0x180208332  mov     ecx, 40h ; '@'; uFlags
0x180208337  call    cs:__imp_LocalAlloc
0x18020833d  mov     rdi, rax
0x180208340  test    rax, rax
0x180208343  jnz     short loc_18020834F
0x180208345  mov     ebx, 8007000Eh
0x18020834a  jmp     loc_1802083E9
0x18020834f  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x180208354  lea     rax, [rsp+58h+TokenInformationLength]
0x180208359  mov     r8, rdi; TokenInformation
0x18020835c  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180208361  mov     edx, 1Fh; TokenInformationClass
0x180208366  mov     rcx, rsi; TokenHandle
0x180208369  call    cs:__imp_GetTokenInformation
0x18020836f  test    eax, eax
0x180208371  jnz     short loc_18020837E
0x180208373  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180208378  mov     ebx, eax
0x18020837a  test    eax, eax
0x18020837c  js      short loc_1802083E9
0x18020837e  mov     rcx, [rdi]; pSid
0x180208381  test    rcx, rcx
0x180208384  jnz     short loc_18020838D
0x180208386  mov     ebx, 80070490h
0x18020838b  jmp     short loc_1802083E0
0x18020838d  call    cs:__imp_GetLengthSid
0x180208393  mov     edx, eax; uBytes
0x180208395  mov     ecx, 40h ; '@'; uFlags
0x18020839a  mov     ebx, eax
0x18020839c  call    cs:__imp_LocalAlloc
0x1802083a2  mov     rsi, rax
0x1802083a5  test    rax, rax
0x1802083a8  jnz     short loc_1802083B1
0x1802083aa  mov     ebx, 8007000Eh
0x1802083af  jmp     short loc_1802083E0
0x1802083b1  mov     r8, [rdi]; pSourceSid
0x1802083b4  mov     rdx, rsi; pDestinationSid
0x1802083b7  mov     ecx, ebx; nDestinationSidLength
0x1802083b9  call    cs:__imp_CopySid
0x1802083bf  test    eax, eax
0x1802083c1  jz      short loc_1802083C7
0x1802083c3  xor     ebx, ebx
0x1802083c5  jmp     short loc_1802083D2
0x1802083c7  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1802083cc  mov     ebx, eax
0x1802083ce  test    eax, eax
0x1802083d0  js      short loc_1802083D7
0x1802083d2  mov     [r14], rsi
0x1802083d5  jmp     short loc_1802083E0
0x1802083d7  mov     rcx, rsi; hMem
0x1802083da  call    cs:__imp_LocalFree
0x1802083e0  mov     rcx, rdi; hMem
0x1802083e3  call    cs:__imp_LocalFree
0x1802083e9  mov     eax, ebx
0x1802083eb  add     rsp, 38h
0x1802083ef  pop     r14
0x1802083f1  pop     rdi
0x1802083f2  pop     rsi
0x1802083f3  pop     rbx
0x1802083f4  retn
```
