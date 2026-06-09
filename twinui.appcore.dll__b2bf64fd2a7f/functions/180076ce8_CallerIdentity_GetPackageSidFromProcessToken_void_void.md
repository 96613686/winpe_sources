# CallerIdentity::GetPackageSidFromProcessToken(void *,void * *)

- ea: `0x180076ce8`
- end: `0x180076e11`
- name: `?GetPackageSidFromProcessToken@CallerIdentity@@YAJPEAXPEAPEAX@Z`
- size: `297`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180025acc`

## callees

- `0x1800299c8`
- `0x180076ce8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076d28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076d28`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180076df6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180076dff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180076df6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180076dff`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180076d53`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180076db8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180076d53`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180076db8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180076da9`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180076da9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180076d14`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180076d85`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180076d14`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180076d85`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180076dd5`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180076dd5`

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
0x180076ce8  push    rbx
0x180076cea  push    rsi
0x180076ceb  push    rdi
0x180076cec  push    r14
0x180076cee  sub     rsp, 38h
0x180076cf2  xor     r9d, r9d; TokenInformationLength
0x180076cf5  mov     [rsp+58h+TokenInformationLength], 0
0x180076cfd  mov     r14, rdx
0x180076d00  lea     rax, [rsp+58h+TokenInformationLength]
0x180076d05  xor     r8d, r8d; TokenInformation
0x180076d08  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180076d0d  mov     rsi, rcx
0x180076d10  lea     edx, [r9+1Fh]; TokenInformationClass
0x180076d14  call    cs:__imp_GetTokenInformation
0x180076d1a  test    eax, eax
0x180076d1c  jz      short loc_180076D28
0x180076d1e  mov     ebx, 8000FFFFh
0x180076d23  jmp     loc_180076E05
0x180076d28  call    cs:__imp_GetLastError
0x180076d2e  mov     ebx, eax
0x180076d30  cmp     eax, 7Ah ; 'z'
0x180076d33  jz      short loc_180076D4A
0x180076d35  test    eax, eax
0x180076d37  jle     short loc_180076D42
0x180076d39  movzx   ebx, ax
0x180076d3c  or      ebx, 80070000h
0x180076d42  test    ebx, ebx
0x180076d44  js      loc_180076E05
0x180076d4a  mov     edx, [rsp+58h+TokenInformationLength]; uBytes
0x180076d4e  mov     ecx, 40h ; '@'; uFlags
0x180076d53  call    cs:__imp_LocalAlloc
0x180076d59  mov     rdi, rax
0x180076d5c  test    rax, rax
0x180076d5f  jnz     short loc_180076D6B
0x180076d61  mov     ebx, 8007000Eh
0x180076d66  jmp     loc_180076E05
0x180076d6b  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x180076d70  lea     rax, [rsp+58h+TokenInformationLength]
0x180076d75  mov     r8, rdi; TokenInformation
0x180076d78  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180076d7d  mov     edx, 1Fh; TokenInformationClass
0x180076d82  mov     rcx, rsi; TokenHandle
0x180076d85  call    cs:__imp_GetTokenInformation
0x180076d8b  test    eax, eax
0x180076d8d  jnz     short loc_180076D9A
0x180076d8f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180076d94  mov     ebx, eax
0x180076d96  test    eax, eax
0x180076d98  js      short loc_180076E05
0x180076d9a  mov     rcx, [rdi]; pSid
0x180076d9d  test    rcx, rcx
0x180076da0  jnz     short loc_180076DA9
0x180076da2  mov     ebx, 80070490h
0x180076da7  jmp     short loc_180076DFC
0x180076da9  call    cs:__imp_GetLengthSid
0x180076daf  mov     edx, eax; uBytes
0x180076db1  mov     ecx, 40h ; '@'; uFlags
0x180076db6  mov     ebx, eax
0x180076db8  call    cs:__imp_LocalAlloc
0x180076dbe  mov     rsi, rax
0x180076dc1  test    rax, rax
0x180076dc4  jnz     short loc_180076DCD
0x180076dc6  mov     ebx, 8007000Eh
0x180076dcb  jmp     short loc_180076DFC
0x180076dcd  mov     r8, [rdi]; pSourceSid
0x180076dd0  mov     rdx, rsi; pDestinationSid
0x180076dd3  mov     ecx, ebx; nDestinationSidLength
0x180076dd5  call    cs:__imp_CopySid
0x180076ddb  test    eax, eax
0x180076ddd  jz      short loc_180076DE3
0x180076ddf  xor     ebx, ebx
0x180076de1  jmp     short loc_180076DEE
0x180076de3  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180076de8  mov     ebx, eax
0x180076dea  test    eax, eax
0x180076dec  js      short loc_180076DF3
0x180076dee  mov     [r14], rsi
0x180076df1  jmp     short loc_180076DFC
0x180076df3  mov     rcx, rsi; hMem
0x180076df6  call    cs:__imp_LocalFree
0x180076dfc  mov     rcx, rdi; hMem
0x180076dff  call    cs:__imp_LocalFree
0x180076e05  mov     eax, ebx
0x180076e07  add     rsp, 38h
0x180076e0b  pop     r14
0x180076e0d  pop     rdi
0x180076e0e  pop     rsi
0x180076e0f  pop     rbx
0x180076e10  retn
```
