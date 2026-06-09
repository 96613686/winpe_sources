# CallerIdentity::GetPackageSidFromProcessToken(void *,void * *)

- ea: `0x18066aac8`
- end: `0x18066abf1`
- name: `?GetPackageSidFromProcessToken@CallerIdentity@@YAJPEAXPEAPEAX@Z`
- size: `297`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18066aa60`

## callees

- `0x1800290dc`
- `0x18066aac8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18066ab08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18066ab08`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18066abd6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18066abdf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18066abd6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18066abdf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18066ab33`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18066ab98`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18066ab33`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18066ab98`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18066abb5`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18066abb5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18066ab89`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18066ab89`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18066aaf4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18066ab65`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18066aaf4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18066ab65`

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
0x18066aac8  push    rbx
0x18066aaca  push    rsi
0x18066aacb  push    rdi
0x18066aacc  push    r14
0x18066aace  sub     rsp, 38h
0x18066aad2  xor     r9d, r9d; TokenInformationLength
0x18066aad5  mov     [rsp+58h+TokenInformationLength], 0
0x18066aadd  mov     r14, rdx
0x18066aae0  lea     rax, [rsp+58h+TokenInformationLength]
0x18066aae5  xor     r8d, r8d; TokenInformation
0x18066aae8  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18066aaed  mov     rsi, rcx
0x18066aaf0  lea     edx, [r9+1Fh]; TokenInformationClass
0x18066aaf4  call    cs:__imp_GetTokenInformation
0x18066aafa  test    eax, eax
0x18066aafc  jz      short loc_18066AB08
0x18066aafe  mov     ebx, 8000FFFFh
0x18066ab03  jmp     loc_18066ABE5
0x18066ab08  call    cs:__imp_GetLastError
0x18066ab0e  mov     ebx, eax
0x18066ab10  cmp     eax, 7Ah ; 'z'
0x18066ab13  jz      short loc_18066AB2A
0x18066ab15  test    eax, eax
0x18066ab17  jle     short loc_18066AB22
0x18066ab19  movzx   ebx, ax
0x18066ab1c  or      ebx, 80070000h
0x18066ab22  test    ebx, ebx
0x18066ab24  js      loc_18066ABE5
0x18066ab2a  mov     edx, [rsp+58h+TokenInformationLength]; uBytes
0x18066ab2e  mov     ecx, 40h ; '@'; uFlags
0x18066ab33  call    cs:__imp_LocalAlloc
0x18066ab39  mov     rdi, rax
0x18066ab3c  test    rax, rax
0x18066ab3f  jnz     short loc_18066AB4B
0x18066ab41  mov     ebx, 8007000Eh
0x18066ab46  jmp     loc_18066ABE5
0x18066ab4b  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x18066ab50  lea     rax, [rsp+58h+TokenInformationLength]
0x18066ab55  mov     r8, rdi; TokenInformation
0x18066ab58  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18066ab5d  mov     edx, 1Fh; TokenInformationClass
0x18066ab62  mov     rcx, rsi; TokenHandle
0x18066ab65  call    cs:__imp_GetTokenInformation
0x18066ab6b  test    eax, eax
0x18066ab6d  jnz     short loc_18066AB7A
0x18066ab6f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18066ab74  mov     ebx, eax
0x18066ab76  test    eax, eax
0x18066ab78  js      short loc_18066ABE5
0x18066ab7a  mov     rcx, [rdi]; pSid
0x18066ab7d  test    rcx, rcx
0x18066ab80  jnz     short loc_18066AB89
0x18066ab82  mov     ebx, 80070490h
0x18066ab87  jmp     short loc_18066ABDC
0x18066ab89  call    cs:__imp_GetLengthSid
0x18066ab8f  mov     edx, eax; uBytes
0x18066ab91  mov     ecx, 40h ; '@'; uFlags
0x18066ab96  mov     ebx, eax
0x18066ab98  call    cs:__imp_LocalAlloc
0x18066ab9e  mov     rsi, rax
0x18066aba1  test    rax, rax
0x18066aba4  jnz     short loc_18066ABAD
0x18066aba6  mov     ebx, 8007000Eh
0x18066abab  jmp     short loc_18066ABDC
0x18066abad  mov     r8, [rdi]; pSourceSid
0x18066abb0  mov     rdx, rsi; pDestinationSid
0x18066abb3  mov     ecx, ebx; nDestinationSidLength
0x18066abb5  call    cs:__imp_CopySid
0x18066abbb  test    eax, eax
0x18066abbd  jz      short loc_18066ABC3
0x18066abbf  xor     ebx, ebx
0x18066abc1  jmp     short loc_18066ABCE
0x18066abc3  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18066abc8  mov     ebx, eax
0x18066abca  test    eax, eax
0x18066abcc  js      short loc_18066ABD3
0x18066abce  mov     [r14], rsi
0x18066abd1  jmp     short loc_18066ABDC
0x18066abd3  mov     rcx, rsi; hMem
0x18066abd6  call    cs:__imp_LocalFree
0x18066abdc  mov     rcx, rdi; hMem
0x18066abdf  call    cs:__imp_LocalFree
0x18066abe5  mov     eax, ebx
0x18066abe7  add     rsp, 38h
0x18066abeb  pop     r14
0x18066abed  pop     rdi
0x18066abee  pop     rsi
0x18066abef  pop     rbx
0x18066abf0  retn
```
