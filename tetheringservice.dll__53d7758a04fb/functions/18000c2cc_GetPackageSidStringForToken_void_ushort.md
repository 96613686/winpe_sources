# GetPackageSidStringForToken(void *,ushort * *)

- ea: `0x18000c2cc`
- end: `0x18000c3db`
- name: `?GetPackageSidStringForToken@@YAJPEAXPEAPEAG@Z`
- size: `271`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, LPWSTR *StringSid)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000c858`

## callees

- `0x18000c2cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c30c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c39b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c30c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c39b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000c38d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000c38d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c2fe`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c37d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c2fe`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c37d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c355`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c355`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c3bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c3bc`

## pseudocode

```c
__int64 __fastcall GetPackageSidStringForToken(HANDLE TokenHandle, LPWSTR *StringSid)
{
  signed int LastError; // eax
  signed int v5; // ebx
  PSID *v6; // rdi
  signed int v7; // eax
  bool v8; // sf
  DWORD TokenInformationLength; // [rsp+68h] [rbp+10h] BYREF

  *StringSid = 0;
  TokenInformationLength = 0;
  if ( GetTokenInformation(TokenHandle, TokenAppContainerSid, 0, 0, &TokenInformationLength) )
  {
    return (unsigned int)-2147418113;
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( v5 < 0 )
    {
      if ( v5 == -2147024774 )
      {
        if ( TokenInformationLength > 8 )
        {
          v6 = (PSID *)LocalAlloc(0x40u, TokenInformationLength);
          if ( v6 )
          {
            if ( GetTokenInformation(
                   TokenHandle,
                   TokenAppContainerSid,
                   v6,
                   TokenInformationLength,
                   &TokenInformationLength)
              && ConvertSidToStringSidW(*v6, StringSid) )
            {
              v5 = 0;
            }
            else
            {
              v7 = GetLastError();
              v8 = v7 < 0;
              if ( v7 > 0 )
              {
                v7 = (unsigned __int16)v7 | 0x80070000;
                v8 = v7 < 0;
              }
              if ( !v8 )
                v7 = -2147467259;
              v5 = v7;
            }
            LocalFree(v6);
          }
          else
          {
            return (unsigned int)-2147024882;
          }
        }
        else
        {
          return (unsigned int)-2147023728;
        }
      }
    }
    else
    {
      return (unsigned int)-2147467259;
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000c2cc  push    rbx
0x18000c2ce  push    rbp
0x18000c2cf  push    rsi
0x18000c2d0  push    rdi
0x18000c2d1  sub     rsp, 38h
0x18000c2d5  xor     r9d, r9d; TokenInformationLength
0x18000c2d8  mov     qword ptr [rdx], 0
0x18000c2df  mov     rsi, rdx
0x18000c2e2  mov     [rsp+58h+TokenInformationLength], 0
0x18000c2ea  lea     rax, [rsp+58h+TokenInformationLength]
0x18000c2ef  xor     r8d, r8d; TokenInformation
0x18000c2f2  mov     rbp, rcx
0x18000c2f5  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18000c2fa  lea     edx, [r9+1Fh]; TokenInformationClass
0x18000c2fe  call    cs:__imp_GetTokenInformation
0x18000c304  test    eax, eax
0x18000c306  jnz     loc_18000C3CB
0x18000c30c  call    cs:__imp_GetLastError
0x18000c312  mov     ebx, eax
0x18000c314  test    eax, eax
0x18000c316  jle     short loc_18000C321
0x18000c318  movzx   ebx, ax
0x18000c31b  or      ebx, 80070000h
0x18000c321  test    ebx, ebx
0x18000c323  js      short loc_18000C32F
0x18000c325  mov     ebx, 80004005h
0x18000c32a  jmp     loc_18000C3D0
0x18000c32f  cmp     ebx, 8007007Ah
0x18000c335  jnz     loc_18000C3D0
0x18000c33b  cmp     [rsp+58h+TokenInformationLength], 8
0x18000c340  ja      short loc_18000C34C
0x18000c342  mov     ebx, 80070490h
0x18000c347  jmp     loc_18000C3D0
0x18000c34c  mov     edx, [rsp+58h+TokenInformationLength]; uBytes
0x18000c350  mov     ecx, 40h ; '@'; uFlags
0x18000c355  call    cs:__imp_LocalAlloc
0x18000c35b  mov     rdi, rax
0x18000c35e  test    rax, rax
0x18000c361  jz      short loc_18000C3C4
0x18000c363  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x18000c368  lea     rax, [rsp+58h+TokenInformationLength]
0x18000c36d  mov     r8, rdi; TokenInformation
0x18000c370  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18000c375  mov     edx, 1Fh; TokenInformationClass
0x18000c37a  mov     rcx, rbp; TokenHandle
0x18000c37d  call    cs:__imp_GetTokenInformation
0x18000c383  test    eax, eax
0x18000c385  jz      short loc_18000C39B
0x18000c387  mov     rcx, [rdi]; Sid
0x18000c38a  mov     rdx, rsi; StringSid
0x18000c38d  call    cs:__imp_ConvertSidToStringSidW
0x18000c393  test    eax, eax
0x18000c395  jz      short loc_18000C39B
0x18000c397  xor     ebx, ebx
0x18000c399  jmp     short loc_18000C3B9
0x18000c39b  call    cs:__imp_GetLastError
0x18000c3a1  test    eax, eax
0x18000c3a3  jle     short loc_18000C3AF
0x18000c3a5  movzx   eax, ax
0x18000c3a8  or      eax, 80070000h
0x18000c3ad  test    eax, eax
0x18000c3af  mov     ebx, 80004005h
0x18000c3b4  cmovns  eax, ebx
0x18000c3b7  mov     ebx, eax
0x18000c3b9  mov     rcx, rdi; hMem
0x18000c3bc  call    cs:__imp_LocalFree
0x18000c3c2  jmp     short loc_18000C3D0
0x18000c3c4  mov     ebx, 8007000Eh
0x18000c3c9  jmp     short loc_18000C3D0
0x18000c3cb  mov     ebx, 8000FFFFh
0x18000c3d0  mov     eax, ebx
0x18000c3d2  add     rsp, 38h
0x18000c3d6  pop     rdi
0x18000c3d7  pop     rsi
0x18000c3d8  pop     rbp
0x18000c3d9  pop     rbx
0x18000c3da  retn
```
