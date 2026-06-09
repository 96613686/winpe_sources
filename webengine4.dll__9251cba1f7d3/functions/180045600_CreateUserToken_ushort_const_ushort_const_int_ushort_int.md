# CreateUserToken(ushort const *,ushort const *,int,ushort *,int)

- ea: `0x180045600`
- end: `0x1800458ea`
- name: `?CreateUserToken@@YAPEAXPEBG0HPEAGH@Z`
- size: `746`
- prototype: `HANDLE __fastcall(const unsigned __int16 *, LPCWSTR lpString, int, LPWSTR lpBuffer, int nSize)`
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x180001ea4`
- `0x18000fd10`
- `0x1800234b4`

## callees

- `0x180044a48`
- `0x180044dc4`
- `0x1800450e8`
- `0x180045600`
- `0x180045bbc`
- `0x180046410`
- `0x180047214`
- `0x18004d030`
- `0x18004d350`
- `0x1800653c0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180045797`
- `KERNEL32!CloseHandle` at `0x1800457f1`
- `KERNEL32!CloseHandle` at `0x180045851`
- `KERNEL32!CloseHandle` at `0x18004588c`
- `KERNEL32!CloseHandle` at `0x180045797`
- `KERNEL32!CloseHandle` at `0x1800457f1`
- `KERNEL32!CloseHandle` at `0x180045851`
- `KERNEL32!CloseHandle` at `0x18004588c`
- `KERNEL32!lstrlenW` at `0x180045694`
- `KERNEL32!lstrlenW` at `0x1800456a8`
- `KERNEL32!lstrlenW` at `0x180045694`
- `KERNEL32!lstrlenW` at `0x1800456a8`
- `KERNEL32!FormatMessageW` at `0x1800458bf`
- `KERNEL32!FormatMessageW` at `0x1800458bf`
- `ucrtbase_clr0400!_wcsicmp` at `0x18004582d`
- `ucrtbase_clr0400!_wcsicmp` at `0x18004582d`
- `ADVAPI32!SetThreadToken` at `0x18004578a`
- `ADVAPI32!SetThreadToken` at `0x1800457df`
- `ADVAPI32!SetThreadToken` at `0x18004578a`
- `ADVAPI32!SetThreadToken` at `0x1800457df`

## pseudocode

```c
HANDLE __fastcall CreateUserToken(const unsigned __int16 *a1, LPCWSTR lpString, int a3, LPWSTR lpBuffer, int nSize)
{
  __int64 v9; // rdi
  DWORD UserName; // ebx
  signed __int64 v11; // rsi
  WCHAR *v12; // rcx
  WCHAR v13; // ax
  WCHAR *v14; // rax
  void *CurrentToken; // rdi
  HANDLE hObject; // [rsp+40h] [rbp-C0h] BYREF
  int v18; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR szPassword[256]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR szDomain[256]; // [rsp+250h] [rbp+150h] BYREF
  WCHAR szUsername[256]; // [rsp+450h] [rbp+350h] BYREF

  v18 = 1;
  hObject = 0;
  memset_0(szDomain, 0, sizeof(szDomain));
  memset_0(szUsername, 0, sizeof(szUsername));
  memset_0(szPassword, 0, sizeof(szPassword));
  if ( !a1 || !lpString || lstrlenW(a1) > 250 || lstrlenW(lpString) > 255 )
  {
    UserName = -2147024809;
    goto LABEL_34;
  }
  v9 = 256;
  UserName = ExtractUserName(a1, szUsername, 0x100u, szDomain, 0x100u);
  if ( UserName )
    goto LABEL_34;
  v11 = (char *)lpString - (char *)szPassword;
  v12 = szPassword;
  do
  {
    if ( v9 == -2147483390 )
      break;
    v13 = *(WCHAR *)((char *)v12 + v11);
    if ( !v13 )
      break;
    *v12++ = v13;
    --v9;
  }
  while ( v9 );
  v14 = v12 - 1;
  if ( v9 )
    v14 = v12;
  *v14 = 0;
  UserName = v9 == 0 ? 0x8007007A : 0;
  if ( !v9 )
    goto LABEL_34;
  UserName = CallLogonUser(szUsername, szDomain, szPassword, &hObject, &v18);
  if ( UserName == -2147024891 )
  {
    CurrentToken = GetCurrentToken();
    if ( !CurrentToken )
    {
      UserName = -2147024891;
      goto LABEL_34;
    }
    if ( !SetThreadToken(0, 0) )
    {
      CloseHandle(CurrentToken);
      UserName = GetLastWin32Error();
      if ( !UserName )
        return hObject;
LABEL_34:
      if ( hObject )
      {
        _InterlockedDecrement(&g_lNumTokensCreated);
        CloseHandle(hObject);
      }
      goto LABEL_36;
    }
    UserName = CallLogonUser(szUsername, szDomain, szPassword, &hObject, &v18);
    if ( !SetThreadToken(0, CurrentToken) )
      GetLastWin32Error();
    CloseHandle(CurrentToken);
  }
  if ( UserName )
    goto LABEL_34;
  if ( a3 )
  {
    if ( !v18 )
      goto LABEL_28;
  }
  else if ( v18 )
  {
    goto LABEL_28;
  }
  UserName = ChangeTokenType(&hObject, a3);
  if ( UserName )
    goto LABEL_34;
LABEL_28:
  if ( !_wcsicmp(a1, L"NT AUTHORITY\\ANONYMOUS") || !(unsigned int)IsTokenAnonymousUser(hObject) )
  {
    AddProcessSidToObjectDACL(hObject);
    return hObject;
  }
  _InterlockedDecrement(&g_lNumTokensCreated);
  CloseHandle(hObject);
  hObject = 0;
  UserName = -2147467259;
LABEL_36:
  if ( lpBuffer )
  {
    if ( nSize > 0 )
      FormatMessageW(0x1200u, 0, UserName, 0x800u, lpBuffer, nSize, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180045600  push    rbp
0x180045602  push    rbx
0x180045603  push    rsi
0x180045604  push    rdi
0x180045605  push    r12
0x180045607  push    r13
0x180045609  push    r14
0x18004560b  push    r15
0x18004560d  lea     rbp, [rsp-568h]
0x180045615  sub     rsp, 668h
0x18004561c  mov     rax, cs:__security_cookie
0x180045623  xor     rax, rsp
0x180045626  mov     [rbp+5A0h+var_50], rax
0x18004562d  mov     r15d, r8d
0x180045630  mov     [rsp+6A0h+var_658], 1
0x180045638  mov     rsi, rdx
0x18004563b  mov     r14, rcx
0x18004563e  mov     ebx, 200h
0x180045643  lea     rcx, [rbp+5A0h+szDomain]; void *
0x18004564a  xor     r13d, r13d
0x18004564d  mov     r8d, ebx; Size
0x180045650  xor     edx, edx; Val
0x180045652  mov     [rsp+6A0h+hObject], r13
0x180045657  mov     r12, r9
0x18004565a  call    memset_0
0x18004565f  mov     r8d, ebx; Size
0x180045662  lea     rcx, [rbp+5A0h+szUsername]; void *
0x180045669  xor     edx, edx; Val
0x18004566b  call    memset_0
0x180045670  mov     r8d, ebx; Size
0x180045673  lea     rcx, [rsp+6A0h+szPassword]; void *
0x180045678  xor     edx, edx; Val
0x18004567a  call    memset_0
0x18004567f  test    r14, r14
0x180045682  jz      loc_180045874
0x180045688  test    rsi, rsi
0x18004568b  jz      loc_180045874
0x180045691  mov     rcx, r14; lpString
0x180045694  call    cs:__imp_lstrlenW
0x18004569a  cmp     eax, 0FAh
0x18004569f  jg      loc_180045874
0x1800456a5  mov     rcx, rsi; lpString
0x1800456a8  call    cs:__imp_lstrlenW
0x1800456ae  cmp     eax, 0FFh
0x1800456b3  jg      loc_180045874
0x1800456b9  mov     edi, 100h
0x1800456be  lea     r9, [rbp+5A0h+szDomain]; unsigned __int16 *
0x1800456c5  mov     r8d, edi; unsigned int
0x1800456c8  mov     dword ptr [rsp+6A0h+lpBuffer], edi; unsigned int
0x1800456cc  lea     rdx, [rbp+5A0h+szUsername]; unsigned __int16 *
0x1800456d3  mov     rcx, r14; unsigned __int16 *
0x1800456d6  call    ?ExtractUserName@@YAJPEBGPEAGK1K@Z; ExtractUserName(ushort const *,ushort *,ulong,ushort *,ulong)
0x1800456db  mov     ebx, eax
0x1800456dd  test    eax, eax
0x1800456df  jnz     loc_180045879
0x1800456e5  lea     rax, [rsp+6A0h+szPassword]
0x1800456ea  sub     rsi, rax
0x1800456ed  lea     rcx, [rsp+6A0h+szPassword]
0x1800456f2  lea     rax, [rdi+7FFFFEFEh]
0x1800456f9  test    rax, rax
0x1800456fc  jz      short loc_180045714
0x1800456fe  movzx   eax, word ptr [rsi+rcx]
0x180045702  test    ax, ax
0x180045705  jz      short loc_180045714
0x180045707  mov     [rcx], ax
0x18004570a  add     rcx, 2
0x18004570e  sub     rdi, 1
0x180045712  jnz     short loc_1800456F2
0x180045714  test    rdi, rdi
0x180045717  lea     rax, [rcx-2]
0x18004571b  cmovnz  rax, rcx
0x18004571f  mov     [rax], r13w
0x180045723  mov     rax, rdi
0x180045726  neg     rax
0x180045729  sbb     ebx, ebx
0x18004572b  not     ebx
0x18004572d  and     ebx, 8007007Ah
0x180045733  test    rdi, rdi
0x180045736  jz      loc_180045879
0x18004573c  lea     rax, [rsp+6A0h+var_658]
0x180045741  lea     r9, [rsp+6A0h+hObject]; phToken
0x180045746  mov     [rsp+6A0h+lpBuffer], rax; int *
0x18004574b  lea     r8, [rsp+6A0h+szPassword]; lpszPassword
0x180045750  lea     rdx, [rbp+5A0h+szDomain]; lpszDomain
0x180045757  lea     rcx, [rbp+5A0h+szUsername]; lpszUsername
0x18004575e  call    ?CallLogonUser@@YAJPEAG00PEAPEAXPEAH@Z; CallLogonUser(ushort *,ushort *,ushort *,void * *,int *)
0x180045763  mov     esi, 80070005h
0x180045768  mov     ebx, eax
0x18004576a  cmp     eax, esi
0x18004576c  jnz     loc_1800457F7
0x180045772  call    ?GetCurrentToken@@YAPEAXXZ; GetCurrentToken(void)
0x180045777  mov     rdi, rax
0x18004577a  test    rax, rax
0x18004577d  jnz     short loc_180045786
0x18004577f  mov     ebx, esi
0x180045781  jmp     loc_180045879
0x180045786  xor     edx, edx; Token
0x180045788  xor     ecx, ecx; Thread
0x18004578a  call    cs:__imp_SetThreadToken
0x180045790  test    eax, eax
0x180045792  jnz     short loc_1800457B1
0x180045794  mov     rcx, rdi; hObject
0x180045797  call    cs:__imp_CloseHandle
0x18004579d  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x1800457a2  mov     ebx, eax
0x1800457a4  test    eax, eax
0x1800457a6  jnz     loc_180045879
0x1800457ac  jmp     loc_18004586D
0x1800457b1  lea     rax, [rsp+6A0h+var_658]
0x1800457b6  lea     r9, [rsp+6A0h+hObject]; phToken
0x1800457bb  mov     [rsp+6A0h+lpBuffer], rax; int *
0x1800457c0  lea     r8, [rsp+6A0h+szPassword]; lpszPassword
0x1800457c5  lea     rdx, [rbp+5A0h+szDomain]; lpszDomain
0x1800457cc  lea     rcx, [rbp+5A0h+szUsername]; lpszUsername
0x1800457d3  call    ?CallLogonUser@@YAJPEAG00PEAPEAXPEAH@Z; CallLogonUser(ushort *,ushort *,ushort *,void * *,int *)
0x1800457d8  mov     rdx, rdi; Token
0x1800457db  xor     ecx, ecx; Thread
0x1800457dd  mov     ebx, eax
0x1800457df  call    cs:__imp_SetThreadToken
0x1800457e5  test    eax, eax
0x1800457e7  jnz     short loc_1800457EE
0x1800457e9  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x1800457ee  mov     rcx, rdi; hObject
0x1800457f1  call    cs:__imp_CloseHandle
0x1800457f7  test    ebx, ebx
0x1800457f9  jnz     short loc_180045879
0x1800457fb  test    r15d, r15d
0x1800457fe  jz      short loc_180045809
0x180045800  cmp     [rsp+6A0h+var_658], r13d
0x180045805  jnz     short loc_180045810
0x180045807  jmp     short loc_180045823
0x180045809  cmp     [rsp+6A0h+var_658], r13d
0x18004580e  jnz     short loc_180045823
0x180045810  mov     edx, r15d; int
0x180045813  lea     rcx, [rsp+6A0h+hObject]; void **
0x180045818  call    ?ChangeTokenType@@YAJPEAPEAXH@Z; ChangeTokenType(void * *,int)
0x18004581d  mov     ebx, eax
0x18004581f  test    eax, eax
0x180045821  jnz     short loc_180045879
0x180045823  lea     rdx, aNtAuthorityAno; "NT AUTHORITY\\ANONYMOUS"
0x18004582a  mov     rcx, r14; String1
0x18004582d  call    cs:__imp__wcsicmp
0x180045833  test    eax, eax
0x180045835  jz      short loc_180045863
0x180045837  mov     rcx, [rsp+6A0h+hObject]; void *
0x18004583c  call    ?IsTokenAnonymousUser@@YAHPEAX@Z; IsTokenAnonymousUser(void *)
0x180045841  test    eax, eax
0x180045843  jz      short loc_180045863
0x180045845  lock dec cs:?g_lNumTokensCreated@@3JA; long g_lNumTokensCreated
0x18004584c  mov     rcx, [rsp+6A0h+hObject]; hObject
0x180045851  call    cs:__imp_CloseHandle
0x180045857  mov     [rsp+6A0h+hObject], r13
0x18004585c  mov     ebx, 80004005h
0x180045861  jmp     short loc_180045892
0x180045863  mov     rcx, [rsp+6A0h+hObject]; void *
0x180045868  call    ?AddProcessSidToObjectDACL@@YAJPEAX@Z; AddProcessSidToObjectDACL(void *)
0x18004586d  mov     rax, [rsp+6A0h+hObject]
0x180045872  jmp     short loc_1800458C7
0x180045874  mov     ebx, 80070057h
0x180045879  cmp     [rsp+6A0h+hObject], r13
0x18004587e  jz      short loc_180045892
0x180045880  lock dec cs:?g_lNumTokensCreated@@3JA; long g_lNumTokensCreated
0x180045887  mov     rcx, [rsp+6A0h+hObject]; hObject
0x18004588c  call    cs:__imp_CloseHandle
0x180045892  test    r12, r12
0x180045895  jz      short loc_1800458C5
0x180045897  mov     eax, [rbp+5A0h+arg_20]
0x18004589d  test    eax, eax
0x18004589f  jle     short loc_1800458C5
0x1800458a1  mov     [rsp+6A0h+Arguments], r13; Arguments
0x1800458a6  mov     r9d, 800h; dwLanguageId
0x1800458ac  mov     [rsp+6A0h+nSize], eax; nSize
0x1800458b0  mov     r8d, ebx; dwMessageId
0x1800458b3  xor     edx, edx; lpSource
0x1800458b5  mov     [rsp+6A0h+lpBuffer], r12; lpBuffer
0x1800458ba  mov     ecx, 1200h; dwFlags
0x1800458bf  call    cs:__imp_FormatMessageW
0x1800458c5  xor     eax, eax
0x1800458c7  mov     rcx, [rbp+5A0h+var_50]
0x1800458ce  xor     rcx, rsp; StackCookie
0x1800458d1  call    __security_check_cookie
0x1800458d6  add     rsp, 668h
0x1800458dd  pop     r15
0x1800458df  pop     r14
0x1800458e1  pop     r13
0x1800458e3  pop     r12
0x1800458e5  pop     rdi
0x1800458e6  pop     rsi
0x1800458e7  pop     rbx
0x1800458e8  pop     rbp
0x1800458e9  retn
```
