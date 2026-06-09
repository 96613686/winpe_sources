# CallerIdentity::GetPackageSidFromProcessToken(void *,void * *)

- ea: `0x1800044b0`
- end: `0x1800045f4`
- name: `?GetPackageSidFromProcessToken@CallerIdentity@@YAJPEAXPEAPEAX@Z`
- size: `324`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004270`

## callees

- `0x1800044b0`
- `0x18009d920`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800044ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800045a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800044ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800045a6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004504`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004551`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004504`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004551`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004579`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800045c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004579`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800045c8`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180004567`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180004567`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180004542`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180004542`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800044dc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004530`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800044dc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004530`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetPackageSidFromProcessToken(HANDLE TokenHandle, _QWORD *a2, void **a3)
{
  signed int LastError; // eax
  signed int Error; // ebx
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
0x1800044b0  push    rbx
0x1800044b2  push    rsi
0x1800044b3  push    rdi
0x1800044b4  push    r14
0x1800044b6  sub     rsp, 38h
0x1800044ba  xor     r9d, r9d; TokenInformationLength
0x1800044bd  mov     [rsp+58h+TokenInformationLength], 0
0x1800044c5  mov     r14, rdx
0x1800044c8  lea     rax, [rsp+58h+TokenInformationLength]
0x1800044cd  xor     r8d, r8d; TokenInformation
0x1800044d0  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x1800044d5  mov     rsi, rcx
0x1800044d8  lea     edx, [r9+1Fh]; TokenInformationClass
0x1800044dc  call    cs:__imp_GetTokenInformation
0x1800044e2  test    eax, eax
0x1800044e4  jnz     loc_1800045E6
0x1800044ea  call    cs:__imp_GetLastError
0x1800044f0  mov     ebx, eax
0x1800044f2  cmp     eax, 7Ah ; 'z'
0x1800044f5  jnz     loc_1800045D0
0x1800044fb  mov     edx, [rsp+58h+TokenInformationLength]; uBytes
0x1800044ff  mov     ecx, 40h ; '@'; uFlags
0x180004504  call    cs:__imp_LocalAlloc
0x18000450a  mov     rdi, rax
0x18000450d  test    rax, rax
0x180004510  jz      loc_1800045ED
0x180004516  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x18000451b  lea     rax, [rsp+58h+TokenInformationLength]
0x180004520  mov     r8, rdi; TokenInformation
0x180004523  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180004528  mov     edx, 1Fh; TokenInformationClass
0x18000452d  mov     rcx, rsi; TokenHandle
0x180004530  call    cs:__imp_GetTokenInformation
0x180004536  test    eax, eax
0x180004538  jz      short loc_180004592
0x18000453a  mov     rcx, [rdi]; pSid
0x18000453d  test    rcx, rcx
0x180004540  jz      short loc_18000459F
0x180004542  call    cs:__imp_GetLengthSid
0x180004548  mov     edx, eax; uBytes
0x18000454a  mov     ecx, 40h ; '@'; uFlags
0x18000454f  mov     ebx, eax
0x180004551  call    cs:__imp_LocalAlloc
0x180004557  mov     rsi, rax
0x18000455a  test    rax, rax
0x18000455d  jz      short loc_18000458B
0x18000455f  mov     r8, [rdi]; pSourceSid
0x180004562  mov     rdx, rax; pDestinationSid
0x180004565  mov     ecx, ebx; nDestinationSidLength
0x180004567  call    cs:__imp_CopySid
0x18000456d  test    eax, eax
0x18000456f  jz      short loc_1800045A6
0x180004571  mov     [r14], rsi
0x180004574  xor     ebx, ebx
0x180004576  mov     rcx, rdi; hMem
0x180004579  call    cs:__imp_LocalFree
0x18000457f  mov     eax, ebx
0x180004581  add     rsp, 38h
0x180004585  pop     r14
0x180004587  pop     rdi
0x180004588  pop     rsi
0x180004589  pop     rbx
0x18000458a  retn
0x18000458b  mov     ebx, 8007000Eh
0x180004590  jmp     short loc_180004576
0x180004592  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180004597  mov     ebx, eax
0x180004599  test    eax, eax
0x18000459b  js      short loc_18000457F
0x18000459d  jmp     short loc_18000453A
0x18000459f  mov     ebx, 80070490h
0x1800045a4  jmp     short loc_180004576
0x1800045a6  call    cs:__imp_GetLastError
0x1800045ac  mov     ebx, eax
0x1800045ae  test    eax, eax
0x1800045b0  jle     short loc_1800045BB
0x1800045b2  movzx   ebx, ax
0x1800045b5  or      ebx, 80070000h
0x1800045bb  test    ebx, ebx
0x1800045bd  mov     eax, 80004005h
0x1800045c2  mov     rcx, rsi; hMem
0x1800045c5  cmovns  ebx, eax
0x1800045c8  call    cs:__imp_LocalFree
0x1800045ce  jmp     short loc_180004576
0x1800045d0  test    eax, eax
0x1800045d2  jle     short loc_1800045DD
0x1800045d4  movzx   ebx, ax
0x1800045d7  or      ebx, 80070000h
0x1800045dd  test    ebx, ebx
0x1800045df  js      short loc_18000457F
0x1800045e1  jmp     loc_1800044FB
0x1800045e6  mov     ebx, 8000FFFFh
0x1800045eb  jmp     short loc_18000457F
0x1800045ed  mov     ebx, 8007000Eh
0x1800045f2  jmp     short loc_18000457F
```
