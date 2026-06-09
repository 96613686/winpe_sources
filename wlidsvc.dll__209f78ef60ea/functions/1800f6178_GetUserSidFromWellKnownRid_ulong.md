# GetUserSidFromWellKnownRid(ulong)

- ea: `0x1800f6178`
- end: `0x1800f6271`
- name: `?GetUserSidFromWellKnownRid@@YAPEAXK@Z`
- size: `249`
- prototype: `void *__fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18009b1f0`

## callees

- `0x1800a48e8`
- `0x1800f6178`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800f61e6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800f61e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f61b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f61b4`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800f6229`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800f6236`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800f6249`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800f6229`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800f6236`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800f6249`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x1800f61d9`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x1800f61d9`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800f61c8`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800f61c8`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x1800f61fd`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x1800f61fd`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x1800f620c`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x1800f620c`
- `samcli!NetUserModalsGet` at `0x1800f6196`
- `samcli!NetUserModalsGet` at `0x1800f6196`
- `netutils!NetApiBufferFree` at `0x1800f625f`
- `netutils!NetApiBufferFree` at `0x1800f625f`

## pseudocode

```c
HLOCAL __fastcall GetUserSidFromWellKnownRid()
{
  DWORD v0; // eax
  DWORD v1; // ebx
  HLOCAL v2; // rdi
  DWORD v3; // ebx
  DWORD SidLengthRequired; // eax
  struct _SID_IDENTIFIER_AUTHORITY *SidIdentifierAuthority; // rax
  DWORD v6; // ebp
  DWORD v7; // esi
  DWORD v8; // ebx
  PDWORD SidSubAuthority; // rax
  LPBYTE bufptr; // [rsp+58h] [rbp+10h] BYREF

  bufptr = 0;
  v0 = NetUserModalsGet(0, 2u, &bufptr);
  v1 = v0;
  if ( v0 )
  {
    v2 = 0;
    printf("NetUserModalsGet failed with error code : [%d]\n", v0);
    SetLastError(v1);
  }
  else
  {
    v3 = *GetSidSubAuthorityCount(*((PSID *)bufptr + 1));
    SidLengthRequired = GetSidLengthRequired(v3 + 1);
    v2 = LocalAlloc(0x40u, SidLengthRequired);
    if ( v2 )
    {
      SidIdentifierAuthority = GetSidIdentifierAuthority(*((PSID *)bufptr + 1));
      if ( InitializeSid(v2, SidIdentifierAuthority, v3 + 1) )
      {
        v6 = 0;
        v7 = v3;
        if ( (_BYTE)v3 )
        {
          do
          {
            v8 = *GetSidSubAuthority(*((PSID *)bufptr + 1), v6);
            SidSubAuthority = GetSidSubAuthority(v2, v6++);
            *SidSubAuthority = v8;
          }
          while ( v6 < v7 );
        }
        *GetSidSubAuthority(v2, v7) = 501;
      }
    }
  }
  if ( bufptr )
    NetApiBufferFree(bufptr);
  return v2;
}

```

## disassembly

```asm
0x1800f6178  push    rbx
0x1800f617a  push    rbp
0x1800f617b  push    rsi
0x1800f617c  push    rdi
0x1800f617d  sub     rsp, 28h
0x1800f6181  lea     r8, [rsp+48h+bufptr]; bufptr
0x1800f6186  mov     [rsp+48h+bufptr], 0
0x1800f618f  mov     edx, 2; level
0x1800f6194  xor     ecx, ecx; servername
0x1800f6196  call    cs:__imp_NetUserModalsGet
0x1800f619c  mov     ebx, eax
0x1800f619e  test    eax, eax
0x1800f61a0  jz      short loc_1800F61BF
0x1800f61a2  mov     edx, eax
0x1800f61a4  lea     rcx, aNetusermodalsg_0; "NetUserModalsGet failed with error code"...
0x1800f61ab  xor     edi, edi
0x1800f61ad  call    printf
0x1800f61b2  mov     ecx, ebx; dwErrCode
0x1800f61b4  call    cs:__imp_SetLastError
0x1800f61ba  jmp     loc_1800F6255
0x1800f61bf  mov     rcx, [rsp+48h+bufptr]
0x1800f61c4  mov     rcx, [rcx+8]; pSid
0x1800f61c8  call    cs:__imp_GetSidSubAuthorityCount
0x1800f61ce  movzx   ebx, byte ptr [rax]
0x1800f61d1  lea     eax, [rbx+1]
0x1800f61d4  mov     cl, al; nSubAuthorityCount
0x1800f61d6  mov     sil, al
0x1800f61d9  call    cs:__imp_GetSidLengthRequired
0x1800f61df  mov     edx, eax; uBytes
0x1800f61e1  mov     ecx, 40h ; '@'; uFlags
0x1800f61e6  call    cs:__imp_LocalAlloc
0x1800f61ec  mov     rdi, rax
0x1800f61ef  test    rax, rax
0x1800f61f2  jz      short loc_1800F6255
0x1800f61f4  mov     rcx, [rsp+48h+bufptr]
0x1800f61f9  mov     rcx, [rcx+8]; pSid
0x1800f61fd  call    cs:__imp_GetSidIdentifierAuthority
0x1800f6203  mov     r8b, sil; nSubAuthorityCount
0x1800f6206  mov     rcx, rdi; Sid
0x1800f6209  mov     rdx, rax; pIdentifierAuthority
0x1800f620c  call    cs:__imp_InitializeSid
0x1800f6212  test    eax, eax
0x1800f6214  jz      short loc_1800F6255
0x1800f6216  xor     ebp, ebp
0x1800f6218  mov     esi, ebx
0x1800f621a  test    bl, bl
0x1800f621c  jz      short loc_1800F6244
0x1800f621e  mov     rcx, [rsp+48h+bufptr]
0x1800f6223  mov     edx, ebp; nSubAuthority
0x1800f6225  mov     rcx, [rcx+8]; pSid
0x1800f6229  call    cs:__imp_GetSidSubAuthority
0x1800f622f  mov     edx, ebp; nSubAuthority
0x1800f6231  mov     rcx, rdi; pSid
0x1800f6234  mov     ebx, [rax]
0x1800f6236  call    cs:__imp_GetSidSubAuthority
0x1800f623c  inc     ebp
0x1800f623e  mov     [rax], ebx
0x1800f6240  cmp     ebp, esi
0x1800f6242  jb      short loc_1800F621E
0x1800f6244  mov     edx, esi; nSubAuthority
0x1800f6246  mov     rcx, rdi; pSid
0x1800f6249  call    cs:__imp_GetSidSubAuthority
0x1800f624f  mov     dword ptr [rax], 1F5h
0x1800f6255  mov     rcx, [rsp+48h+bufptr]; Buffer
0x1800f625a  test    rcx, rcx
0x1800f625d  jz      short loc_1800F6265
0x1800f625f  call    cs:__imp_NetApiBufferFree
0x1800f6265  mov     rax, rdi
0x1800f6268  add     rsp, 28h
0x1800f626c  pop     rdi
0x1800f626d  pop     rsi
0x1800f626e  pop     rbp
0x1800f626f  pop     rbx
0x1800f6270  retn
```
