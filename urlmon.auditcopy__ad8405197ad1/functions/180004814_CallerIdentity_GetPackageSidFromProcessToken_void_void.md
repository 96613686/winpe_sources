# CallerIdentity::GetPackageSidFromProcessToken(void *,void * *)

- ea: `0x180004814`
- end: `0x180004998`
- name: `?GetPackageSidFromProcessToken@CallerIdentity@@YAJPEAXPEAPEAX@Z`
- size: `388`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, _QWORD *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800046f0`

## callees

- `0x180004814`
- `0x1800a4318`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004854`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000493b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004854`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000493b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004874`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800048d3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004874`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800048d3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004907`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004963`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004907`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004963`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800048ef`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800048ef`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800048be`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800048be`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004840`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800048a6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004840`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800048a6`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetPackageSidFromProcessToken(HANDLE TokenHandle, _QWORD *a2, void **a3)
{
  signed int LastError; // eax
  int Error; // ebx
  PSID *v7; // rdi
  DWORD LengthSid; // ebx
  HLOCAL v9; // rax
  void *v10; // rsi
  signed int v12; // eax
  DWORD TokenInformationLength; // [rsp+70h] [rbp+18h] BYREF

  TokenInformationLength = 0;
  if ( GetTokenInformation(TokenHandle, TokenAppContainerSid, 0, 0, &TokenInformationLength) )
  {
    return (unsigned int)-2147418113;
  }
  else
  {
    LastError = GetLastError();
    Error = LastError;
    if ( LastError == 122 )
      goto LABEL_3;
    if ( LastError > 0 )
      Error = (unsigned __int16)LastError | 0x80070000;
    if ( Error >= 0 )
    {
LABEL_3:
      v7 = (PSID *)LocalAlloc(0x40u, TokenInformationLength);
      if ( v7 )
      {
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
                *a2 = v10;
                Error = 0;
              }
              else
              {
                v12 = GetLastError();
                Error = v12;
                if ( v12 > 0 )
                  Error = (unsigned __int16)v12 | 0x80070000;
                if ( Error >= 0 )
                  Error = -2147467259;
                LocalFree(v10);
              }
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
          LocalFree(v7);
        }
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180004814  push    rbx
0x180004816  push    rsi
0x180004817  push    rdi
0x180004818  push    r14
0x18000481a  sub     rsp, 38h
0x18000481e  xor     r9d, r9d; TokenInformationLength
0x180004821  mov     [rsp+58h+TokenInformationLength], 0
0x180004829  mov     r14, rdx
0x18000482c  lea     rax, [rsp+58h+TokenInformationLength]
0x180004831  xor     r8d, r8d; TokenInformation
0x180004834  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180004839  mov     rsi, rcx
0x18000483c  lea     edx, [r9+1Fh]; TokenInformationClass
0x180004840  call    cs:__imp_GetTokenInformation
0x180004847  nop     dword ptr [rax+rax+00h]
0x18000484c  test    eax, eax
0x18000484e  jnz     loc_180004987
0x180004854  call    cs:__imp_GetLastError
0x18000485b  nop     dword ptr [rax+rax+00h]
0x180004860  mov     ebx, eax
0x180004862  cmp     eax, 7Ah ; 'z'
0x180004865  jnz     loc_180004971
0x18000486b  mov     edx, [rsp+58h+TokenInformationLength]; uBytes
0x18000486f  mov     ecx, 40h ; '@'; uFlags
0x180004874  call    cs:__imp_LocalAlloc
0x18000487b  nop     dword ptr [rax+rax+00h]
0x180004880  mov     rdi, rax
0x180004883  test    rax, rax
0x180004886  jz      loc_18000498E
0x18000488c  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x180004891  lea     rax, [rsp+58h+TokenInformationLength]
0x180004896  mov     r8, rdi; TokenInformation
0x180004899  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18000489e  mov     edx, 1Fh; TokenInformationClass
0x1800048a3  mov     rcx, rsi; TokenHandle
0x1800048a6  call    cs:__imp_GetTokenInformation
0x1800048ad  nop     dword ptr [rax+rax+00h]
0x1800048b2  test    eax, eax
0x1800048b4  jz      short loc_180004927
0x1800048b6  mov     rcx, [rdi]; pSid
0x1800048b9  test    rcx, rcx
0x1800048bc  jz      short loc_180004934
0x1800048be  call    cs:__imp_GetLengthSid
0x1800048c5  nop     dword ptr [rax+rax+00h]
0x1800048ca  mov     edx, eax; uBytes
0x1800048cc  mov     ecx, 40h ; '@'; uFlags
0x1800048d1  mov     ebx, eax
0x1800048d3  call    cs:__imp_LocalAlloc
0x1800048da  nop     dword ptr [rax+rax+00h]
0x1800048df  mov     rsi, rax
0x1800048e2  test    rax, rax
0x1800048e5  jz      short loc_180004920
0x1800048e7  mov     r8, [rdi]; pSourceSid
0x1800048ea  mov     rdx, rax; pDestinationSid
0x1800048ed  mov     ecx, ebx; nDestinationSidLength
0x1800048ef  call    cs:__imp_CopySid
0x1800048f6  nop     dword ptr [rax+rax+00h]
0x1800048fb  test    eax, eax
0x1800048fd  jz      short loc_18000493B
0x1800048ff  mov     [r14], rsi
0x180004902  xor     ebx, ebx
0x180004904  mov     rcx, rdi; hMem
0x180004907  call    cs:__imp_LocalFree
0x18000490e  nop     dword ptr [rax+rax+00h]
0x180004913  mov     eax, ebx
0x180004915  add     rsp, 38h
0x180004919  pop     r14
0x18000491b  pop     rdi
0x18000491c  pop     rsi
0x18000491d  pop     rbx
0x18000491e  retn
0x180004920  mov     ebx, 8007000Eh
0x180004925  jmp     short loc_180004904
0x180004927  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000492c  mov     ebx, eax
0x18000492e  test    eax, eax
0x180004930  js      short loc_180004913
0x180004932  jmp     short loc_1800048B6
0x180004934  mov     ebx, 80070490h
0x180004939  jmp     short loc_180004904
0x18000493b  call    cs:__imp_GetLastError
0x180004942  nop     dword ptr [rax+rax+00h]
0x180004947  mov     ebx, eax
0x180004949  test    eax, eax
0x18000494b  jle     short loc_180004956
0x18000494d  movzx   ebx, ax
0x180004950  or      ebx, 80070000h
0x180004956  test    ebx, ebx
0x180004958  mov     eax, 80004005h
0x18000495d  mov     rcx, rsi; hMem
0x180004960  cmovns  ebx, eax
0x180004963  call    cs:__imp_LocalFree
0x18000496a  nop     dword ptr [rax+rax+00h]
0x18000496f  jmp     short loc_180004904
0x180004971  test    eax, eax
0x180004973  jle     short loc_18000497E
0x180004975  movzx   ebx, ax
0x180004978  or      ebx, 80070000h
0x18000497e  test    ebx, ebx
0x180004980  js      short loc_180004913
0x180004982  jmp     loc_18000486B
0x180004987  mov     ebx, 8000FFFFh
0x18000498c  jmp     short loc_180004913
0x18000498e  mov     ebx, 8007000Eh
0x180004993  jmp     loc_180004913
```
