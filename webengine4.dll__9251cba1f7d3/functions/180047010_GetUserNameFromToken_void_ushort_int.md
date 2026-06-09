# GetUserNameFromToken(void *,ushort *,int)

- ea: `0x180047010`
- end: `0x1800471c2`
- name: `?GetUserNameFromToken@@YAHPEAXPEAGH@Z`
- size: `434`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, unsigned __int16 *, int)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x18000c030`
- `0x18001ffc4`
- `0x180046f70`

## callees

- `0x180002584`
- `0x180007824`
- `0x180047010`
- `0x18004d030`
- `0x18004d350`
- `0x18004d690`
- `0x18004d754`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x18004711b`
- `KERNEL32!lstrlenW` at `0x180047128`
- `KERNEL32!lstrlenW` at `0x18004711b`
- `KERNEL32!lstrlenW` at `0x180047128`
- `ADVAPI32!GetTokenInformation` at `0x18004707a`
- `ADVAPI32!GetTokenInformation` at `0x1800470bb`
- `ADVAPI32!GetTokenInformation` at `0x18004707a`
- `ADVAPI32!GetTokenInformation` at `0x1800470bb`
- `ADVAPI32!LookupAccountSidW` at `0x18004710a`
- `ADVAPI32!LookupAccountSidW` at `0x18004710a`

## pseudocode

```c
__int64 __fastcall GetUserNameFromToken(HANDLE TokenHandle, unsigned __int16 *a2, int a3)
{
  unsigned __int64 v3; // r14
  PSID *v4; // rsi
  int LastWin32Error; // edi
  unsigned int v7; // ebx
  int v9; // eax
  int v10; // ebx
  int v11; // ebx
  DWORD TokenInformationLength; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchReferencedDomainName; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cchName; // [rsp+48h] [rbp-B8h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+4Ch] [rbp-B4h] BYREF
  WCHAR ReferencedDomainName[256]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Name[256]; // [rsp+250h] [rbp+150h] BYREF
  _BYTE TokenInformation[2048]; // [rsp+450h] [rbp+350h] BYREF

  v3 = a3;
  cchName = 256;
  cchReferencedDomainName = 256;
  v4 = (PSID *)TokenInformation;
  LastWin32Error = 0;
  v7 = 0;
  TokenInformationLength = 0;
  if ( !GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x800u, &TokenInformationLength) )
  {
    if ( TokenInformationLength <= 0x800 )
    {
      LastWin32Error = GetLastWin32Error();
      goto LABEL_16;
    }
    v4 = (PSID *)MemAlloc(TokenInformationLength);
    if ( !v4 )
      return 0;
    if ( !GetTokenInformation(TokenHandle, TokenUser, v4, TokenInformationLength, &TokenInformationLength) )
      goto LABEL_5;
  }
  if ( LookupAccountSidW(0, *v4, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
  {
    v10 = lstrlenW(Name);
    v11 = lstrlenW(ReferencedDomainName) + v10 + 2;
    if ( v11 > (int)v3 )
    {
      v7 = -v11;
      goto LABEL_14;
    }
    v7 = 1;
    LastWin32Error = StringCchCopyW(a2, v3, ReferencedDomainName);
    if ( LastWin32Error )
      goto LABEL_14;
    LastWin32Error = StringCchCatW(a2, v3, L"\\");
    if ( LastWin32Error )
      goto LABEL_14;
    v9 = StringCchCatW(a2, v3, Name);
  }
  else
  {
LABEL_5:
    v9 = GetLastWin32Error();
  }
  LastWin32Error = v9;
LABEL_14:
  if ( v4 != (PSID *)TokenInformation )
    MemFree(v4);
LABEL_16:
  if ( !LastWin32Error )
    return v7;
  return 0;
}

```

## disassembly

```asm
0x180047010  push    rbp
0x180047012  push    rbx
0x180047013  push    rsi
0x180047014  push    rdi
0x180047015  push    r12
0x180047017  push    r14
0x180047019  push    r15
0x18004701b  lea     rbp, [rsp-0B60h]
0x180047023  sub     rsp, 0C60h
0x18004702a  mov     rax, cs:__security_cookie
0x180047031  xor     rax, rsp
0x180047034  mov     [rbp+0B90h+var_40], rax
0x18004703b  mov     eax, 100h
0x180047040  movsxd  r14, r8d
0x180047043  mov     [rsp+0C90h+cchName], eax
0x180047047  lea     r8, [rbp+0B90h+TokenInformation]; TokenInformation
0x18004704e  mov     [rsp+0C90h+var_C4C], eax
0x180047052  lea     rsi, [rbp+0B90h+TokenInformation]
0x180047059  mov     r15, rdx
0x18004705c  lea     rax, [rsp+0C90h+TokenInformationLength]
0x180047061  xor     edi, edi
0x180047063  mov     [rsp+0C90h+ReturnLength], rax; ReturnLength
0x180047068  xor     ebx, ebx
0x18004706a  mov     r9d, 800h; TokenInformationLength
0x180047070  and     [rsp+0C90h+TokenInformationLength], ebx
0x180047074  mov     r12, rcx
0x180047077  lea     edx, [rdi+1]; TokenInformationClass
0x18004707a  call    cs:__imp_GetTokenInformation
0x180047080  test    eax, eax
0x180047082  jnz     short loc_1800470DB
0x180047084  cmp     [rsp+0C90h+TokenInformationLength], 800h
0x18004708c  jbe     short loc_1800470CF
0x18004708e  mov     ecx, [rsp+0C90h+TokenInformationLength]; unsigned __int64
0x180047092  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x180047097  mov     rsi, rax
0x18004709a  test    rax, rax
0x18004709d  jz      loc_18004719F
0x1800470a3  mov     r9d, [rsp+0C90h+TokenInformationLength]; TokenInformationLength
0x1800470a8  lea     rax, [rsp+0C90h+TokenInformationLength]
0x1800470ad  mov     r8, rsi; TokenInformation
0x1800470b0  mov     [rsp+0C90h+ReturnLength], rax; ReturnLength
0x1800470b5  lea     edx, [rdi+1]; TokenInformationClass
0x1800470b8  mov     rcx, r12; TokenHandle
0x1800470bb  call    cs:__imp_GetTokenInformation
0x1800470c1  test    eax, eax
0x1800470c3  jnz     short loc_1800470DB
0x1800470c5  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x1800470ca  jmp     loc_180047181
0x1800470cf  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x1800470d4  mov     edi, eax
0x1800470d6  jmp     loc_180047197
0x1800470db  mov     rdx, [rsi]; Sid
0x1800470de  lea     rax, [rsp+0C90h+var_C44]
0x1800470e3  mov     [rsp+0C90h+peUse], rax; peUse
0x1800470e8  lea     r9, [rsp+0C90h+cchName]; cchName
0x1800470ed  lea     rax, [rsp+0C90h+var_C4C]
0x1800470f2  xor     ecx, ecx; lpSystemName
0x1800470f4  mov     [rsp+0C90h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800470f9  lea     r8, [rbp+0B90h+Name]; Name
0x180047100  lea     rax, [rsp+0C90h+ReferencedDomainName]
0x180047105  mov     [rsp+0C90h+ReturnLength], rax; ReferencedDomainName
0x18004710a  call    cs:__imp_LookupAccountSidW
0x180047110  test    eax, eax
0x180047112  jz      short loc_1800470C5
0x180047114  lea     rcx, [rbp+0B90h+Name]; lpString
0x18004711b  call    cs:__imp_lstrlenW
0x180047121  lea     rcx, [rsp+0C90h+ReferencedDomainName]; lpString
0x180047126  mov     ebx, eax
0x180047128  call    cs:__imp_lstrlenW
0x18004712e  add     ebx, 2
0x180047131  add     ebx, eax
0x180047133  cmp     ebx, r14d
0x180047136  jle     short loc_18004713C
0x180047138  neg     ebx
0x18004713a  jmp     short loc_180047183
0x18004713c  lea     r8, [rsp+0C90h+ReferencedDomainName]; unsigned __int16 *
0x180047141  mov     rdx, r14; unsigned __int64
0x180047144  mov     rcx, r15; unsigned __int16 *
0x180047147  mov     ebx, 1
0x18004714c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180047151  mov     edi, eax
0x180047153  test    eax, eax
0x180047155  jnz     short loc_180047183
0x180047157  lea     r8, SubBlock; "\\"
0x18004715e  mov     rdx, r14; unsigned __int64
0x180047161  mov     rcx, r15; unsigned __int16 *
0x180047164  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180047169  mov     edi, eax
0x18004716b  test    eax, eax
0x18004716d  jnz     short loc_180047183
0x18004716f  lea     r8, [rbp+0B90h+Name]; unsigned __int16 *
0x180047176  mov     rdx, r14; unsigned __int64
0x180047179  mov     rcx, r15; unsigned __int16 *
0x18004717c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180047181  mov     edi, eax
0x180047183  lea     rax, [rbp+0B90h+TokenInformation]
0x18004718a  cmp     rsi, rax
0x18004718d  jz      short loc_180047197
0x18004718f  mov     rcx, rsi; lpMem
0x180047192  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x180047197  test    edi, edi
0x180047199  jnz     short loc_18004719F
0x18004719b  mov     eax, ebx
0x18004719d  jmp     short loc_1800471A1
0x18004719f  xor     eax, eax
0x1800471a1  mov     rcx, [rbp+0B90h+var_40]
0x1800471a8  xor     rcx, rsp; StackCookie
0x1800471ab  call    __security_check_cookie
0x1800471b0  add     rsp, 0C60h
0x1800471b7  pop     r15
0x1800471b9  pop     r14
0x1800471bb  pop     r12
0x1800471bd  pop     rdi
0x1800471be  pop     rsi
0x1800471bf  pop     rbx
0x1800471c0  pop     rbp
0x1800471c1  retn
```
