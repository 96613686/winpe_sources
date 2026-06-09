# CRegAccount::GetGuestUserName(ushort *,ulong)

- ea: `0x18002422c`
- end: `0x180024468`
- name: `?GetGuestUserName@CRegAccount@@CAJPEAGK@Z`
- size: `572`
- prototype: `__int64 __fastcall(LPWSTR Name, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x180023164`

## callees

- `0x18002422c`
- `0x18004c3dd`
- `0x18004c425`
- `0x18004d030`
- `0x18004d350`
- `0x18004d6c8`
- `0x18004d754`
- `0x1800653c0`

## import_xrefs

- `ADVAPI32!IsValidSid` at `0x1800242e9`
- `ADVAPI32!IsValidSid` at `0x1800242e9`
- `ADVAPI32!GetSidIdentifierAuthority` at `0x18002433b`
- `ADVAPI32!GetSidIdentifierAuthority` at `0x18002433b`
- `ADVAPI32!GetSidLengthRequired` at `0x180024319`
- `ADVAPI32!GetSidLengthRequired` at `0x180024319`
- `ADVAPI32!GetSidSubAuthority` at `0x180024378`
- `ADVAPI32!GetSidSubAuthority` at `0x18002438c`
- `ADVAPI32!GetSidSubAuthority` at `0x1800243b2`
- `ADVAPI32!GetSidSubAuthority` at `0x180024378`
- `ADVAPI32!GetSidSubAuthority` at `0x18002438c`
- `ADVAPI32!GetSidSubAuthority` at `0x1800243b2`
- `ADVAPI32!GetSidSubAuthorityCount` at `0x1800242fa`
- `ADVAPI32!GetSidSubAuthorityCount` at `0x1800242fa`
- `ADVAPI32!InitializeSid` at `0x180024356`
- `ADVAPI32!InitializeSid` at `0x180024356`
- `ADVAPI32!LookupAccountSidW` at `0x1800243f1`
- `ADVAPI32!LookupAccountSidW` at `0x1800243f1`

## pseudocode

```c
__int64 __fastcall CRegAccount::GetGuestUserName(LPWSTR Name, DWORD a2)
{
  DWORD v2; // r14d
  WCHAR *v4; // r12
  void *v5; // r15
  signed int LastWin32Error; // ebx
  signed int v7; // eax
  void *v8; // rdi
  PUCHAR SidSubAuthorityCount; // rax
  PUCHAR v10; // rsi
  UCHAR v11; // al
  DWORD SidLengthRequired; // eax
  struct _SID_IDENTIFIER_AUTHORITY *SidIdentifierAuthority; // rax
  DWORD v14; // eax
  PDWORD SidSubAuthority; // r12
  PDWORD v16; // rax
  PDWORD v17; // rax
  LPBYTE bufptr; // [rsp+40h] [rbp-29h] BYREF
  DWORD cchReferencedDomainName; // [rsp+48h] [rbp-21h] BYREF
  DWORD cchName; // [rsp+4Ch] [rbp-1Dh] BYREF
  LPWSTR v22; // [rsp+50h] [rbp-19h]
  enum _SID_NAME_USE peUse; // [rsp+58h] [rbp-11h] BYREF
  WCHAR ReferencedDomainName[8]; // [rsp+60h] [rbp-9h] BYREF
  __int128 v25; // [rsp+70h] [rbp+7h]

  v2 = 0;
  v22 = Name;
  bufptr = 0;
  v4 = Name;
  cchReferencedDomainName = 16;
  v5 = 0;
  LastWin32Error = 0;
  *(_OWORD *)ReferencedDomainName = 0;
  v25 = 0;
  if ( !Name || !a2 )
  {
    LastWin32Error = -2147024809;
    goto LABEL_29;
  }
  memset_0(Name, 0, 2LL * a2);
  v7 = NetUserModalsGet_0(0, 2u, &bufptr);
  if ( v7 )
  {
    LastWin32Error = (unsigned __int16)v7 | 0x80070000;
    if ( v7 <= 0 )
      LastWin32Error = v7;
    goto LABEL_29;
  }
  if ( !bufptr )
  {
    LastWin32Error = -2147418113;
    goto LABEL_32;
  }
  v8 = (void *)*((_QWORD *)bufptr + 1);
  if ( !v8 )
    goto LABEL_27;
  if ( !IsValidSid(*((PSID *)bufptr + 1)) )
    goto LABEL_27;
  SidSubAuthorityCount = GetSidSubAuthorityCount(v8);
  v10 = SidSubAuthorityCount;
  if ( !SidSubAuthorityCount )
    goto LABEL_27;
  v11 = *SidSubAuthorityCount;
  if ( !v11 )
    goto LABEL_27;
  SidLengthRequired = GetSidLengthRequired(v11 + 1);
  v5 = MemAllocClear(SidLengthRequired);
  if ( !v5 )
  {
    LastWin32Error = -2147024882;
    goto LABEL_29;
  }
  SidIdentifierAuthority = GetSidIdentifierAuthority(v8);
  if ( !SidIdentifierAuthority )
  {
LABEL_27:
    LastWin32Error = -2147418113;
    goto LABEL_29;
  }
  if ( InitializeSid(v5, SidIdentifierAuthority, *v10 + 1) )
  {
    LOBYTE(v14) = *v10;
    if ( *v10 )
    {
      while ( 1 )
      {
        SidSubAuthority = GetSidSubAuthority(v8, v2);
        if ( !SidSubAuthority )
          break;
        v16 = GetSidSubAuthority(v5, v2);
        if ( !v16 )
          break;
        ++v2;
        *v16 = *SidSubAuthority;
        v14 = *v10;
        if ( v2 >= v14 )
        {
          v4 = v22;
          goto LABEL_23;
        }
      }
    }
    else
    {
LABEL_23:
      v17 = GetSidSubAuthority(v5, (unsigned __int8)v14);
      if ( v17 )
      {
        *v17 = 501;
        cchName = a2;
        if ( LookupAccountSidW(0, v5, v4, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
          goto LABEL_29;
      }
    }
  }
  LastWin32Error = GetLastWin32Error();
LABEL_29:
  if ( bufptr )
    NetApiBufferFree_0(bufptr);
  v4 = v22;
LABEL_32:
  MemFree(v5);
  if ( LastWin32Error >= 0 )
    v4[a2 - 1] = 0;
  return (unsigned int)LastWin32Error;
}

```

## disassembly

```asm
0x18002422c  mov     [rsp-8+arg_10], rbx
0x180024231  push    rbp
0x180024232  push    rsi
0x180024233  push    rdi
0x180024234  push    r12
0x180024236  push    r13
0x180024238  push    r14
0x18002423a  push    r15
0x18002423c  lea     rbp, [rsp-27h]
0x180024241  sub     rsp, 90h
0x180024248  mov     rax, cs:__security_cookie
0x18002424f  xor     rax, rsp
0x180024252  mov     [rbp+57h+var_40], rax
0x180024256  xor     r14d, r14d
0x180024259  mov     r13d, edx
0x18002425c  mov     [rbp+57h+var_70], rcx
0x180024260  xorps   xmm0, xmm0
0x180024263  mov     [rbp+57h+bufptr], r14
0x180024267  mov     r12, rcx
0x18002426a  mov     [rbp+57h+var_78], 10h
0x180024271  mov     r15d, r14d
0x180024274  mov     ebx, r14d
0x180024277  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x18002427b  movups  [rbp+57h+var_50], xmm0
0x18002427f  test    rcx, rcx
0x180024282  jz      loc_180024413
0x180024288  cmp     r13d, 1
0x18002428c  jb      loc_180024413
0x180024292  mov     r8d, r13d
0x180024295  xor     edx, edx; Val
0x180024297  add     r8, r8; Size
0x18002429a  call    memset_0
0x18002429f  lea     r8, [rbp+57h+bufptr]; bufptr
0x1800242a3  xor     ecx, ecx; servername
0x1800242a5  lea     edx, [r14+2]; level
0x1800242a9  call    NetUserModalsGet_0
0x1800242ae  test    eax, eax
0x1800242b0  jz      short loc_1800242C5
0x1800242b2  movzx   ebx, ax
0x1800242b5  or      ebx, 80070000h
0x1800242bb  test    eax, eax
0x1800242bd  cmovle  ebx, eax
0x1800242c0  jmp     loc_180024418
0x1800242c5  cmp     [rbp+57h+bufptr], r14
0x1800242c9  jnz     short loc_1800242D5
0x1800242cb  mov     ebx, 8000FFFFh
0x1800242d0  jmp     loc_18002442A
0x1800242d5  mov     rax, [rbp+57h+bufptr]
0x1800242d9  mov     rdi, [rax+8]
0x1800242dd  test    rdi, rdi
0x1800242e0  jz      loc_18002440C
0x1800242e6  mov     rcx, rdi; pSid
0x1800242e9  call    cs:__imp_IsValidSid
0x1800242ef  test    eax, eax
0x1800242f1  jz      loc_18002440C
0x1800242f7  mov     rcx, rdi; pSid
0x1800242fa  call    cs:__imp_GetSidSubAuthorityCount
0x180024300  mov     rsi, rax
0x180024303  test    rax, rax
0x180024306  jz      loc_18002440C
0x18002430c  mov     al, [rax]
0x18002430e  test    al, al
0x180024310  jz      loc_18002440C
0x180024316  lea     ecx, [rax+1]; nSubAuthorityCount
0x180024319  call    cs:__imp_GetSidLengthRequired
0x18002431f  mov     ecx, eax; unsigned __int64
0x180024321  call    ?MemAllocClear@@YAPEAX_K@Z; MemAllocClear(unsigned __int64)
0x180024326  mov     r15, rax
0x180024329  test    rax, rax
0x18002432c  jnz     short loc_180024338
0x18002432e  mov     ebx, 8007000Eh
0x180024333  jmp     loc_180024418
0x180024338  mov     rcx, rdi; pSid
0x18002433b  call    cs:__imp_GetSidIdentifierAuthority
0x180024341  test    rax, rax
0x180024344  jz      loc_18002440C
0x18002434a  mov     r8b, [rsi]
0x18002434d  mov     rdx, rax; pIdentifierAuthority
0x180024350  inc     r8b; nSubAuthorityCount
0x180024353  mov     rcx, r15; Sid
0x180024356  call    cs:__imp_InitializeSid
0x18002435c  test    eax, eax
0x18002435e  jnz     short loc_18002436C
0x180024360  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180024365  mov     ebx, eax
0x180024367  jmp     loc_180024418
0x18002436c  mov     al, [rsi]
0x18002436e  test    al, al
0x180024370  jz      short loc_1800243AC
0x180024372  mov     edx, r14d; nSubAuthority
0x180024375  mov     rcx, rdi; pSid
0x180024378  call    cs:__imp_GetSidSubAuthority
0x18002437e  mov     r12, rax
0x180024381  test    rax, rax
0x180024384  jz      short loc_180024400
0x180024386  mov     edx, r14d; nSubAuthority
0x180024389  mov     rcx, r15; pSid
0x18002438c  call    cs:__imp_GetSidSubAuthority
0x180024392  test    rax, rax
0x180024395  jz      short loc_180024400
0x180024397  mov     ecx, [r12]
0x18002439b  inc     r14d
0x18002439e  mov     [rax], ecx
0x1800243a0  movzx   eax, byte ptr [rsi]
0x1800243a3  cmp     r14d, eax
0x1800243a6  jb      short loc_180024372
0x1800243a8  mov     r12, [rbp+57h+var_70]
0x1800243ac  movzx   edx, al; nSubAuthority
0x1800243af  mov     rcx, r15; pSid
0x1800243b2  call    cs:__imp_GetSidSubAuthority
0x1800243b8  xor     r14d, r14d
0x1800243bb  test    rax, rax
0x1800243be  jz      short loc_180024360
0x1800243c0  mov     dword ptr [rax], 1F5h
0x1800243c6  lea     r9, [rbp+57h+cchName]; cchName
0x1800243ca  lea     rax, [rbp+57h+var_68]
0x1800243ce  mov     [rbp+57h+cchName], r13d
0x1800243d2  mov     [rsp+0C0h+peUse], rax; peUse
0x1800243d7  mov     r8, r12; Name
0x1800243da  lea     rax, [rbp+57h+var_78]
0x1800243de  mov     rdx, r15; Sid
0x1800243e1  mov     [rsp+0C0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800243e6  xor     ecx, ecx; lpSystemName
0x1800243e8  lea     rax, [rbp+57h+var_60]
0x1800243ec  mov     [rsp+0C0h+ReferencedDomainName], rax; ReferencedDomainName
0x1800243f1  call    cs:__imp_LookupAccountSidW
0x1800243f7  test    eax, eax
0x1800243f9  jnz     short loc_180024418
0x1800243fb  jmp     loc_180024360
0x180024400  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180024405  mov     ebx, eax
0x180024407  xor     r14d, r14d
0x18002440a  jmp     short loc_180024418
0x18002440c  mov     ebx, 8000FFFFh
0x180024411  jmp     short loc_180024418
0x180024413  mov     ebx, 80070057h
0x180024418  mov     rcx, [rbp+57h+bufptr]; Buffer
0x18002441c  test    rcx, rcx
0x18002441f  jz      short loc_180024426
0x180024421  call    NetApiBufferFree_0
0x180024426  mov     r12, [rbp+57h+var_70]
0x18002442a  mov     rcx, r15; lpMem
0x18002442d  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x180024432  test    ebx, ebx
0x180024434  js      short loc_18002443F
0x180024436  lea     eax, [r13-1]
0x18002443a  mov     [r12+rax*2], r14w
0x18002443f  mov     eax, ebx
0x180024441  mov     rcx, [rbp+57h+var_40]
0x180024445  xor     rcx, rsp; StackCookie
0x180024448  call    __security_check_cookie
0x18002444d  mov     rbx, [rsp+0C0h+arg_10]
0x180024455  add     rsp, 90h
0x18002445c  pop     r15
0x18002445e  pop     r14
0x180024460  pop     r13
0x180024462  pop     r12
0x180024464  pop     rdi
0x180024465  pop     rsi
0x180024466  pop     rbp
0x180024467  retn
```
