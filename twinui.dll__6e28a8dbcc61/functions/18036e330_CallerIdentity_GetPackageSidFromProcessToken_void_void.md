# CallerIdentity::GetPackageSidFromProcessToken(void *,void * *)

- ea: `0x18036e330`
- end: `0x18036e459`
- name: `?GetPackageSidFromProcessToken@CallerIdentity@@YAJPEAXPEAPEAX@Z`
- size: `297`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180100598`
- `0x180389f70`

## callees

- `0x180047224`
- `0x18036e330`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18036e370`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18036e370`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18036e43e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18036e447`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18036e43e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18036e447`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18036e39b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18036e400`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18036e39b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18036e400`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18036e3f1`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18036e3f1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18036e35c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18036e3cd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18036e35c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18036e3cd`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18036e41d`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18036e41d`

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
0x18036e330  push    rbx
0x18036e332  push    rsi
0x18036e333  push    rdi
0x18036e334  push    r14
0x18036e336  sub     rsp, 38h
0x18036e33a  xor     r9d, r9d; TokenInformationLength
0x18036e33d  mov     [rsp+58h+TokenInformationLength], 0
0x18036e345  mov     r14, rdx
0x18036e348  lea     rax, [rsp+58h+TokenInformationLength]
0x18036e34d  xor     r8d, r8d; TokenInformation
0x18036e350  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18036e355  mov     rsi, rcx
0x18036e358  lea     edx, [r9+1Fh]; TokenInformationClass
0x18036e35c  call    cs:__imp_GetTokenInformation
0x18036e362  test    eax, eax
0x18036e364  jz      short loc_18036E370
0x18036e366  mov     ebx, 8000FFFFh
0x18036e36b  jmp     loc_18036E44D
0x18036e370  call    cs:__imp_GetLastError
0x18036e376  mov     ebx, eax
0x18036e378  cmp     eax, 7Ah ; 'z'
0x18036e37b  jz      short loc_18036E392
0x18036e37d  test    eax, eax
0x18036e37f  jle     short loc_18036E38A
0x18036e381  movzx   ebx, ax
0x18036e384  or      ebx, 80070000h
0x18036e38a  test    ebx, ebx
0x18036e38c  js      loc_18036E44D
0x18036e392  mov     edx, [rsp+58h+TokenInformationLength]; uBytes
0x18036e396  mov     ecx, 40h ; '@'; uFlags
0x18036e39b  call    cs:__imp_LocalAlloc
0x18036e3a1  mov     rdi, rax
0x18036e3a4  test    rax, rax
0x18036e3a7  jnz     short loc_18036E3B3
0x18036e3a9  mov     ebx, 8007000Eh
0x18036e3ae  jmp     loc_18036E44D
0x18036e3b3  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x18036e3b8  lea     rax, [rsp+58h+TokenInformationLength]
0x18036e3bd  mov     r8, rdi; TokenInformation
0x18036e3c0  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18036e3c5  mov     edx, 1Fh; TokenInformationClass
0x18036e3ca  mov     rcx, rsi; TokenHandle
0x18036e3cd  call    cs:__imp_GetTokenInformation
0x18036e3d3  test    eax, eax
0x18036e3d5  jnz     short loc_18036E3E2
0x18036e3d7  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18036e3dc  mov     ebx, eax
0x18036e3de  test    eax, eax
0x18036e3e0  js      short loc_18036E44D
0x18036e3e2  mov     rcx, [rdi]; pSid
0x18036e3e5  test    rcx, rcx
0x18036e3e8  jnz     short loc_18036E3F1
0x18036e3ea  mov     ebx, 80070490h
0x18036e3ef  jmp     short loc_18036E444
0x18036e3f1  call    cs:__imp_GetLengthSid
0x18036e3f7  mov     edx, eax; uBytes
0x18036e3f9  mov     ecx, 40h ; '@'; uFlags
0x18036e3fe  mov     ebx, eax
0x18036e400  call    cs:__imp_LocalAlloc
0x18036e406  mov     rsi, rax
0x18036e409  test    rax, rax
0x18036e40c  jnz     short loc_18036E415
0x18036e40e  mov     ebx, 8007000Eh
0x18036e413  jmp     short loc_18036E444
0x18036e415  mov     r8, [rdi]; pSourceSid
0x18036e418  mov     rdx, rsi; pDestinationSid
0x18036e41b  mov     ecx, ebx; nDestinationSidLength
0x18036e41d  call    cs:__imp_CopySid
0x18036e423  test    eax, eax
0x18036e425  jz      short loc_18036E42B
0x18036e427  xor     ebx, ebx
0x18036e429  jmp     short loc_18036E436
0x18036e42b  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18036e430  mov     ebx, eax
0x18036e432  test    eax, eax
0x18036e434  js      short loc_18036E43B
0x18036e436  mov     [r14], rsi
0x18036e439  jmp     short loc_18036E444
0x18036e43b  mov     rcx, rsi; hMem
0x18036e43e  call    cs:__imp_LocalFree
0x18036e444  mov     rcx, rdi; hMem
0x18036e447  call    cs:__imp_LocalFree
0x18036e44d  mov     eax, ebx
0x18036e44f  add     rsp, 38h
0x18036e453  pop     r14
0x18036e455  pop     rdi
0x18036e456  pop     rsi
0x18036e457  pop     rbx
0x18036e458  retn
```
