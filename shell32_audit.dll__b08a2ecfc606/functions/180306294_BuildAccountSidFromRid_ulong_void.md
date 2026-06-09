# BuildAccountSidFromRid(ulong,void * *)

- ea: `0x180306294`
- end: `0x180306416`
- name: `?BuildAccountSidFromRid@@YAKKPEAPEAX@Z`
- size: `386`
- prototype: `unsigned int __fastcall(unsigned int, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180306a6c`

## callees

- `0x180249490`
- `0x180306294`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180306318`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180306318`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803063cc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803063cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803063bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803063da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803063bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803063da`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180306305`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180306305`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x18030634e`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x18030634e`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x180306339`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x180306339`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180306375`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180306389`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1803063a4`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180306375`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180306389`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1803063a4`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1803062ee`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1803062ee`
- `samcli!NetUserModalsGet` at `0x1803062cf`
- `samcli!NetUserModalsGet` at `0x1803062cf`
- `netutils!NetApiBufferFree` at `0x1803063ed`
- `netutils!NetApiBufferFree` at `0x1803063ed`

## pseudocode

```c
__int64 __fastcall BuildAccountSidFromRid(__int64 a1, void **a2)
{
  DWORD LastError; // edi
  DWORD v4; // ebx
  DWORD SidLengthRequired; // eax
  HLOCAL v6; // rsi
  struct _SID_IDENTIFIER_AUTHORITY *SidIdentifierAuthority; // rax
  DWORD v8; // r14d
  DWORD v9; // ebp
  DWORD v10; // ebx
  PDWORD SidSubAuthority; // rax
  LPBYTE bufptr; // [rsp+20h] [rbp-48h] BYREF

  *a2 = 0;
  bufptr = 0;
  LastError = NetUserModalsGet(0, 2u, &bufptr);
  if ( !LastError )
  {
    v4 = *GetSidSubAuthorityCount(*((PSID *)bufptr + 1));
    SidLengthRequired = GetSidLengthRequired(v4 + 1);
    v6 = LocalAlloc(0x40u, SidLengthRequired);
    if ( v6 )
    {
      SidIdentifierAuthority = GetSidIdentifierAuthority(*((PSID *)bufptr + 1));
      if ( InitializeSid(v6, SidIdentifierAuthority, v4 + 1) )
      {
        LastError = 0;
        v8 = 0;
        v9 = v4;
        if ( (_BYTE)v4 )
        {
          do
          {
            v10 = *GetSidSubAuthority(*((PSID *)bufptr + 1), v8);
            SidSubAuthority = GetSidSubAuthority(v6, v8++);
            *SidSubAuthority = v10;
          }
          while ( v8 < v9 );
        }
        *GetSidSubAuthority(v6, v9) = 501;
        *a2 = v6;
      }
      else
      {
        LastError = GetLastError();
        LocalFree(v6);
      }
    }
    else
    {
      LastError = GetLastError();
    }
    NetApiBufferFree(bufptr);
  }
  return LastError;
}

```

## disassembly

```asm
0x180306294  push    rbx
0x180306296  push    rbp
0x180306297  push    rsi
0x180306298  push    rdi
0x180306299  push    r14
0x18030629b  push    r15
0x18030629d  sub     rsp, 38h
0x1803062a1  mov     rax, cs:__security_cookie
0x1803062a8  xor     rax, rsp
0x1803062ab  mov     [rsp+68h+var_40], rax
0x1803062b0  mov     r15, rdx
0x1803062b3  mov     qword ptr [rdx], 0
0x1803062ba  mov     edx, 2; level
0x1803062bf  mov     [rsp+68h+bufptr], 0
0x1803062c8  lea     r8, [rsp+68h+bufptr]; bufptr
0x1803062cd  xor     ecx, ecx; servername
0x1803062cf  call    cs:__imp_NetUserModalsGet
0x1803062d6  nop     dword ptr [rax+rax+00h]
0x1803062db  mov     edi, eax
0x1803062dd  test    eax, eax
0x1803062df  jnz     loc_1803063F9
0x1803062e5  mov     rcx, [rsp+68h+bufptr]
0x1803062ea  mov     rcx, [rcx+8]; pSid
0x1803062ee  call    cs:__imp_GetSidSubAuthorityCount
0x1803062f5  nop     dword ptr [rax+rax+00h]
0x1803062fa  movzx   ebx, byte ptr [rax]
0x1803062fd  lea     eax, [rbx+1]
0x180306300  mov     cl, al; nSubAuthorityCount
0x180306302  mov     dil, al
0x180306305  call    cs:__imp_GetSidLengthRequired
0x18030630c  nop     dword ptr [rax+rax+00h]
0x180306311  mov     edx, eax; uBytes
0x180306313  mov     ecx, 40h ; '@'; uFlags
0x180306318  call    cs:__imp_LocalAlloc
0x18030631f  nop     dword ptr [rax+rax+00h]
0x180306324  mov     rsi, rax
0x180306327  test    rax, rax
0x18030632a  jz      loc_1803063DA
0x180306330  mov     rcx, [rsp+68h+bufptr]
0x180306335  mov     rcx, [rcx+8]; pSid
0x180306339  call    cs:__imp_GetSidIdentifierAuthority
0x180306340  nop     dword ptr [rax+rax+00h]
0x180306345  mov     r8b, dil; nSubAuthorityCount
0x180306348  mov     rcx, rsi; Sid
0x18030634b  mov     rdx, rax; pIdentifierAuthority
0x18030634e  call    cs:__imp_InitializeSid
0x180306355  nop     dword ptr [rax+rax+00h]
0x18030635a  test    eax, eax
0x18030635c  jz      short loc_1803063BB
0x18030635e  xor     edi, edi
0x180306360  xor     r14d, r14d
0x180306363  mov     ebp, ebx
0x180306365  test    bl, bl
0x180306367  jz      short loc_18030639F
0x180306369  mov     rcx, [rsp+68h+bufptr]
0x18030636e  mov     edx, r14d; nSubAuthority
0x180306371  mov     rcx, [rcx+8]; pSid
0x180306375  call    cs:__imp_GetSidSubAuthority
0x18030637c  nop     dword ptr [rax+rax+00h]
0x180306381  mov     edx, r14d; nSubAuthority
0x180306384  mov     rcx, rsi; pSid
0x180306387  mov     ebx, [rax]
0x180306389  call    cs:__imp_GetSidSubAuthority
0x180306390  nop     dword ptr [rax+rax+00h]
0x180306395  inc     r14d
0x180306398  mov     [rax], ebx
0x18030639a  cmp     r14d, ebp
0x18030639d  jb      short loc_180306369
0x18030639f  mov     edx, ebp; nSubAuthority
0x1803063a1  mov     rcx, rsi; pSid
0x1803063a4  call    cs:__imp_GetSidSubAuthority
0x1803063ab  nop     dword ptr [rax+rax+00h]
0x1803063b0  mov     dword ptr [rax], 1F5h
0x1803063b6  mov     [r15], rsi
0x1803063b9  jmp     short loc_1803063E8
0x1803063bb  call    cs:__imp_GetLastError
0x1803063c2  nop     dword ptr [rax+rax+00h]
0x1803063c7  mov     rcx, rsi; hMem
0x1803063ca  mov     edi, eax
0x1803063cc  call    cs:__imp_LocalFree
0x1803063d3  nop     dword ptr [rax+rax+00h]
0x1803063d8  jmp     short loc_1803063E8
0x1803063da  call    cs:__imp_GetLastError
0x1803063e1  nop     dword ptr [rax+rax+00h]
0x1803063e6  mov     edi, eax
0x1803063e8  mov     rcx, [rsp+68h+bufptr]; Buffer
0x1803063ed  call    cs:__imp_NetApiBufferFree
0x1803063f4  nop     dword ptr [rax+rax+00h]
0x1803063f9  mov     eax, edi
0x1803063fb  mov     rcx, [rsp+68h+var_40]
0x180306400  xor     rcx, rsp; StackCookie
0x180306403  call    __security_check_cookie
0x180306408  add     rsp, 38h
0x18030640c  pop     r15
0x18030640e  pop     r14
0x180306410  pop     rdi
0x180306411  pop     rsi
0x180306412  pop     rbp
0x180306413  pop     rbx
0x180306414  retn
```
