# PrivateGetFileSecurity

- ea: `0x18003b61c`
- end: `0x18003b720`
- name: `PrivateGetFileSecurity`
- size: `260`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, SECURITY_INFORMATION RequestedInformation, PSECURITY_DESCRIPTOR *, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180020240`

## callees

- `0x18003b61c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18003b657`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18003b6b7`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18003b657`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18003b6b7`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18003b6f9`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18003b6f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b66b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b6c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b703`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b66b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b6c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b703`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003b68f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003b68f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b6d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b6ee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b6d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b6ee`

## pseudocode

```c
__int64 __fastcall PrivateGetFileSecurity(
        LPCWSTR lpFileName,
        SECURITY_INFORMATION RequestedInformation,
        PSECURITY_DESCRIPTOR *a3,
        _DWORD *a4)
{
  DWORD LastError; // ebx
  unsigned int v9; // eax
  HLOCAL v10; // rax
  DWORD v11; // r9d
  SIZE_T uBytes; // [rsp+60h] [rbp+18h] BYREF

  LODWORD(uBytes) = 0;
  *a3 = 0;
  if ( GetFileSecurityW(lpFileName, RequestedInformation, 0, 0, (LPDWORD)&uBytes) )
  {
    return 87;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError == 122 )
    {
      v9 = uBytes;
      if ( (_DWORD)uBytes )
      {
        while ( 1 )
        {
          v10 = LocalAlloc(0x40u, v9);
          *a3 = v10;
          if ( !v10 )
            break;
          v11 = uBytes;
          *a4 = uBytes;
          if ( GetFileSecurityW(lpFileName, RequestedInformation, v10, v11, (LPDWORD)&uBytes) )
          {
            IsValidSecurityDescriptor(*a3);
            return 0;
          }
          LastError = GetLastError();
          if ( LastError != 122 || !(_DWORD)uBytes )
          {
            LocalFree(*a3);
            return LastError;
          }
          LocalFree(*a3);
          v9 = uBytes;
          *a3 = 0;
        }
        return GetLastError();
      }
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x18003b61c  mov     rax, rsp
0x18003b61f  mov     [rax+8], rbx
0x18003b623  mov     [rax+10h], rbp
0x18003b627  push    rsi
0x18003b628  push    rdi
0x18003b629  push    r14
0x18003b62b  sub     rsp, 30h
0x18003b62f  mov     dword ptr [rax+18h], 0
0x18003b636  lea     rax, [rax+18h]
0x18003b63a  mov     r14, r9
0x18003b63d  mov     qword ptr [r8], 0
0x18003b644  mov     rdi, r8
0x18003b647  mov     [rsp+48h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18003b64c  xor     r9d, r9d; nLength
0x18003b64f  xor     r8d, r8d; pSecurityDescriptor
0x18003b652  mov     esi, edx
0x18003b654  mov     rbp, rcx
0x18003b657  call    cs:__imp_GetFileSecurityW
0x18003b65d  test    eax, eax
0x18003b65f  jz      short loc_18003B66B
0x18003b661  mov     ebx, 57h ; 'W'
0x18003b666  jmp     loc_18003B70B
0x18003b66b  call    cs:__imp_GetLastError
0x18003b671  mov     ebx, eax
0x18003b673  cmp     eax, 7Ah ; 'z'
0x18003b676  jnz     loc_18003B70B
0x18003b67c  mov     eax, dword ptr [rsp+48h+uBytes]
0x18003b680  test    eax, eax
0x18003b682  jz      loc_18003B70B
0x18003b688  mov     edx, eax; uBytes
0x18003b68a  mov     ecx, 40h ; '@'; uFlags
0x18003b68f  call    cs:__imp_LocalAlloc
0x18003b695  mov     [rdi], rax
0x18003b698  test    rax, rax
0x18003b69b  jz      short loc_18003B703
0x18003b69d  mov     r9d, dword ptr [rsp+48h+uBytes]; nLength
0x18003b6a2  lea     rcx, [rsp+48h+uBytes]
0x18003b6a7  mov     [rsp+48h+lpnLengthNeeded], rcx; lpnLengthNeeded
0x18003b6ac  mov     r8, rax; pSecurityDescriptor
0x18003b6af  mov     rcx, rbp; lpFileName
0x18003b6b2  mov     [r14], r9d
0x18003b6b5  mov     edx, esi; RequestedInformation
0x18003b6b7  call    cs:__imp_GetFileSecurityW
0x18003b6bd  test    eax, eax
0x18003b6bf  jnz     short loc_18003B6F6
0x18003b6c1  call    cs:__imp_GetLastError
0x18003b6c7  mov     ebx, eax
0x18003b6c9  cmp     eax, 7Ah ; 'z'
0x18003b6cc  jnz     short loc_18003B6EB
0x18003b6ce  cmp     dword ptr [rsp+48h+uBytes], 0
0x18003b6d3  jbe     short loc_18003B6EB
0x18003b6d5  mov     rcx, [rdi]; hMem
0x18003b6d8  call    cs:__imp_LocalFree
0x18003b6de  mov     eax, dword ptr [rsp+48h+uBytes]
0x18003b6e2  mov     qword ptr [rdi], 0
0x18003b6e9  jmp     short loc_18003B688
0x18003b6eb  mov     rcx, [rdi]; hMem
0x18003b6ee  call    cs:__imp_LocalFree
0x18003b6f4  jmp     short loc_18003B70B
0x18003b6f6  mov     rcx, [rdi]; pSecurityDescriptor
0x18003b6f9  call    cs:__imp_IsValidSecurityDescriptor
0x18003b6ff  xor     ebx, ebx
0x18003b701  jmp     short loc_18003B70B
0x18003b703  call    cs:__imp_GetLastError
0x18003b709  mov     ebx, eax
0x18003b70b  mov     rbp, [rsp+48h+arg_8]
0x18003b710  mov     eax, ebx
0x18003b712  mov     rbx, [rsp+48h+arg_0]
0x18003b717  add     rsp, 30h
0x18003b71b  pop     r14
0x18003b71d  pop     rdi
0x18003b71e  pop     rsi
0x18003b71f  retn
```
