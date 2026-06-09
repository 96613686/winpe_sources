# WusaGetUserSID(void *,uchar *,ulong)

- ea: `0x14000e4c4`
- end: `0x14000e5ed`
- name: `?WusaGetUserSID@@YAJPEAXPEAEK@Z`
- size: `297`
- prototype: `int(void *, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x140006fb8`

## callees

- `0x14000e280`
- `0x14000e4c4`
- `0x140013490`
- `0x140014910`

## import_xrefs

- `ADVAPI32!GetTokenInformation` at `0x14000e507`
- `ADVAPI32!GetTokenInformation` at `0x14000e507`
- `ADVAPI32!CopySid` at `0x14000e541`
- `ADVAPI32!CopySid` at `0x14000e541`
- `KERNEL32!LocalFree` at `0x14000e5c4`
- `KERNEL32!LocalFree` at `0x14000e5c4`
- `KERNEL32!GetLastError` at `0x14000e511`
- `KERNEL32!GetLastError` at `0x14000e54b`
- `KERNEL32!GetLastError` at `0x14000e511`
- `KERNEL32!GetLastError` at `0x14000e54b`

## string_xrefs

- `0x14000e52b`: `Failed: GetTokenInformation()`
- `0x14000e576`: `WusaGetUserSID`
- `0x14000e5b0`: `WusaGetUserSID`
- `0x14000e565`: `Failed: CopySid()`

## pseudocode

```c
__int64 __fastcall WusaGetUserSID(void *a1, unsigned __int8 *a2)
{
  signed int v3; // eax
  DWORD v4; // ebx
  __int64 v5; // rdx
  const char *v6; // r8
  signed int LastError; // eax
  HLOCAL v8; // rdi
  DWORD ReturnLength; // [rsp+30h] [rbp-88h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-80h] BYREF
  PSID TokenInformation[12]; // [rsp+40h] [rbp-78h] BYREF

  ReturnLength = 0;
  if ( GetTokenInformation(a1, TokenUser, TokenInformation, 0x58u, &ReturnLength) )
  {
    v4 = 0;
    if ( CopySid(0x48u, a2, TokenInformation[0]) )
      return v4;
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    v5 = 659;
    v6 = "Failed: CopySid()";
  }
  else
  {
    v3 = GetLastError();
    v4 = v3;
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
    v5 = 655;
    v6 = "Failed: GetTokenInformation()";
  }
  if ( (v4 & 0x80000000) == 0 )
    v4 = -2147467259;
  WusaLogDebugEventA(L"WusaGetUserSID", v5, v6);
  hMem = 0;
  WusaGetErrorMessage(v4, (unsigned __int16 **)&hMem);
  v8 = hMem;
  WusaLogDebugEventA(L"WusaGetUserSID", 663, "Exit with error code 0X%x (%ls)", v4, (const wchar_t *)hMem);
  if ( v8 )
    LocalFree(v8);
  return v4;
}

```

## disassembly

```asm
0x14000e4c4  mov     [rsp+arg_10], rbx
0x14000e4c9  push    rdi
0x14000e4ca  sub     rsp, 0B0h
0x14000e4d1  mov     rax, cs:__security_cookie
0x14000e4d8  xor     rax, rsp
0x14000e4db  mov     [rsp+0B8h+var_18], rax
0x14000e4e3  mov     r9d, 58h ; 'X'; TokenInformationLength
0x14000e4e9  mov     [rsp+0B8h+var_88], 0
0x14000e4f1  mov     rdi, rdx
0x14000e4f4  lea     rax, [rsp+0B8h+var_88]
0x14000e4f9  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x14000e4fe  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x14000e503  lea     edx, [r9-57h]; TokenInformationClass
0x14000e507  call    cs:__imp_GetTokenInformation
0x14000e50d  test    eax, eax
0x14000e50f  jnz     short loc_14000E534
0x14000e511  call    cs:__imp_GetLastError
0x14000e517  mov     ebx, eax
0x14000e519  test    eax, eax
0x14000e51b  jle     short loc_14000E526
0x14000e51d  movzx   ebx, ax
0x14000e520  or      ebx, 80070000h
0x14000e526  mov     edx, 28Fh
0x14000e52b  lea     r8, aFailedGettoken; "Failed: GetTokenInformation()"
0x14000e532  jmp     short loc_14000E56C
0x14000e534  mov     r8, [rsp+0B8h+TokenInformation]; pSourceSid
0x14000e539  xor     ebx, ebx
0x14000e53b  mov     rdx, rdi; pDestinationSid
0x14000e53e  lea     ecx, [rbx+48h]; nDestinationSidLength
0x14000e541  call    cs:__imp_CopySid
0x14000e547  test    eax, eax
0x14000e549  jnz     short loc_14000E5CA
0x14000e54b  call    cs:__imp_GetLastError
0x14000e551  mov     ebx, eax
0x14000e553  test    eax, eax
0x14000e555  jle     short loc_14000E560
0x14000e557  movzx   ebx, ax
0x14000e55a  or      ebx, 80070000h
0x14000e560  mov     edx, 293h
0x14000e565  lea     r8, aFailedCopysid; "Failed: CopySid()"
0x14000e56c  test    ebx, ebx
0x14000e56e  mov     eax, 80004005h
0x14000e573  cmovns  ebx, eax
0x14000e576  lea     rcx, aWusagetusersid; "WusaGetUserSID"
0x14000e57d  call    WusaLogDebugEventA
0x14000e582  lea     rdx, [rsp+0B8h+hMem]; unsigned __int16 **
0x14000e587  mov     [rsp+0B8h+hMem], 0
0x14000e590  mov     ecx, ebx; dwMessageId
0x14000e592  call    ?WusaGetErrorMessage@@YAJKPEAPEAG@Z; WusaGetErrorMessage(ulong,ushort * *)
0x14000e597  mov     rdi, [rsp+0B8h+hMem]
0x14000e59c  lea     r8, aExitWithErrorC; "Exit with error code 0X%x (%ls)"
0x14000e5a3  mov     r9d, ebx
0x14000e5a6  mov     [rsp+0B8h+ReturnLength], rdi
0x14000e5ab  mov     edx, 297h
0x14000e5b0  lea     rcx, aWusagetusersid; "WusaGetUserSID"
0x14000e5b7  call    WusaLogDebugEventA
0x14000e5bc  test    rdi, rdi
0x14000e5bf  jz      short loc_14000E5CA
0x14000e5c1  mov     rcx, rdi; hMem
0x14000e5c4  call    cs:__imp_LocalFree
0x14000e5ca  mov     eax, ebx
0x14000e5cc  mov     rcx, [rsp+0B8h+var_18]
0x14000e5d4  xor     rcx, rsp; StackCookie
0x14000e5d7  call    __security_check_cookie
0x14000e5dc  mov     rbx, [rsp+0B8h+arg_10]
0x14000e5e4  add     rsp, 0B0h
0x14000e5eb  pop     rdi
0x14000e5ec  retn
```
