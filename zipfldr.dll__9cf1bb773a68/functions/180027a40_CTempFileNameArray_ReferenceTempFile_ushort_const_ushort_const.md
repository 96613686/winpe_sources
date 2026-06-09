# CTempFileNameArray::ReferenceTempFile(ushort const *,ushort const *)

- ea: `0x180027a40`
- end: `0x180027bea`
- name: `?ReferenceTempFile@CTempFileNameArray@@QEAAXPEBG0@Z`
- size: `426`
- prototype: `void __fastcall(CTempFileNameArray *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000d244`
- `0x1800278b0`
- `0x18004666c`
- `0x180059000`

## callees

- `0x18002024c`
- `0x180027a40`
- `0x180027c6c`
- `0x180036f50`
- `0x180037390`

## import_xrefs

- `SHLWAPI!PathRemoveFileSpecW` at `0x180027ba1`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180027ba1`
- `SHLWAPI!PathIsPrefixW` at `0x180027bb3`
- `SHLWAPI!PathIsPrefixW` at `0x180027bb3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027bc1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027bc1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027a7e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027a7e`
- `KERNEL32!lstrlenW` at `0x180027b4a`
- `KERNEL32!lstrlenW` at `0x180027b64`
- `KERNEL32!lstrlenW` at `0x180027b4a`
- `KERNEL32!lstrlenW` at `0x180027b64`

## pseudocode

```c
void __fastcall CTempFileNameArray::ReferenceTempFile(CTempFileNameArray *this, WCHAR *a2, WCHAR *a3)
{
  CTempFileNameArray *v3; // r15
  __int64 v6; // rsi
  WCHAR *v7; // rax
  __int64 v8; // rbx
  __int64 v9; // rcx
  __int64 v10; // r8
  WCHAR *v11; // rcx
  WCHAR v12; // cx
  WCHAR *v13; // rax
  WCHAR *v14; // rax
  WCHAR *v15; // rcx
  unsigned __int64 v16; // rcx
  WCHAR pszPath[264]; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR String[264]; // [rsp+230h] [rbp+130h] BYREF

  v3 = g_pCTFA;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_pCTFA + 8));
  v6 = 2147483646;
  v7 = pszPath;
  v8 = 260;
  v9 = 2147483646;
  v10 = 260;
  do
  {
    if ( !v9 )
      break;
    if ( !*a3 )
      break;
    *v7++ = *a3++;
    --v9;
    --v10;
  }
  while ( v10 );
  v11 = v7 - 1;
  if ( v10 )
    v11 = v7;
  *v11 = 0;
  v12 = pszPath[0];
  if ( pszPath[0] )
  {
    v13 = pszPath;
    do
    {
      if ( v12 == 47 )
        *v13 = 92;
      v12 = *++v13;
    }
    while ( *v13 );
  }
  CTempFileNameArray::_AddFile(v3, pszPath);
  v14 = String;
  do
  {
    if ( !v6 )
      break;
    if ( !*a2 )
      break;
    *v14++ = *a2++;
    --v6;
    --v8;
  }
  while ( v8 );
  v15 = v14 - 1;
  if ( v8 )
    v15 = v14;
  *v15 = 0;
  if ( String[0] && pszPath[lstrlenW(String) + 263] == 92 )
  {
    v16 = 2LL * lstrlenW(String) - 2;
    if ( v16 >= 0x208 )
      _report_rangecheckfailure();
    *(WCHAR *)((char *)String + v16) = 0;
  }
  while ( 1 )
  {
    PathRemoveFileSpecW(pszPath);
    if ( !PathIsPrefixW(String, pszPath) )
      break;
    CTempFileNameArray::_AddDir(v3, pszPath);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v3 + 8));
}

```

## disassembly

```asm
0x180027a40  push    rbp
0x180027a42  push    rbx
0x180027a43  push    rsi
0x180027a44  push    rdi
0x180027a45  push    r12
0x180027a47  push    r13
0x180027a49  push    r14
0x180027a4b  push    r15
0x180027a4d  lea     rbp, [rsp-358h]
0x180027a55  sub     rsp, 458h
0x180027a5c  mov     rax, cs:__security_cookie
0x180027a63  xor     rax, rsp
0x180027a66  mov     [rbp+390h+var_50], rax
0x180027a6d  mov     r15, cs:?g_pCTFA@@3PEAVCTempFileNameArray@@EA; CTempFileNameArray * g_pCTFA
0x180027a74  mov     rdi, r8
0x180027a77  mov     r14, rdx
0x180027a7a  lea     rcx, [r15+8]; lpCriticalSection
0x180027a7e  call    cs:__imp_EnterCriticalSection
0x180027a84  mov     esi, 7FFFFFFEh
0x180027a89  lea     rax, [rsp+490h+pszPath]
0x180027a8e  mov     ebx, 104h
0x180027a93  mov     ecx, esi
0x180027a95  mov     r8d, ebx
0x180027a98  xor     r13d, r13d
0x180027a9b  test    rcx, rcx
0x180027a9e  jz      short loc_180027ABC
0x180027aa0  movzx   edx, word ptr [rdi]
0x180027aa3  test    dx, dx
0x180027aa6  jz      short loc_180027ABC
0x180027aa8  mov     [rax], dx
0x180027aab  add     rdi, 2
0x180027aaf  add     rax, 2
0x180027ab3  dec     rcx
0x180027ab6  sub     r8, 1
0x180027aba  jnz     short loc_180027A9B
0x180027abc  test    r8, r8
0x180027abf  lea     rcx, [rax-2]
0x180027ac3  mov     edi, 5Ch ; '\'
0x180027ac8  cmovnz  rcx, rax
0x180027acc  mov     [rcx], r13w
0x180027ad0  movzx   ecx, [rsp+490h+pszPath]
0x180027ad5  test    cx, cx
0x180027ad8  jz      short loc_180027AF4
0x180027ada  lea     rax, [rsp+490h+pszPath]
0x180027adf  cmp     cx, 2Fh ; '/'
0x180027ae3  jnz     short loc_180027AE8
0x180027ae5  mov     [rax], di
0x180027ae8  add     rax, 2
0x180027aec  movzx   ecx, word ptr [rax]
0x180027aef  test    cx, cx
0x180027af2  jnz     short loc_180027ADF
0x180027af4  lea     rdx, [rsp+490h+pszPath]; unsigned __int16 *
0x180027af9  mov     rcx, r15; this
0x180027afc  call    ?_AddFile@CTempFileNameArray@@AEAAJPEBG@Z; CTempFileNameArray::_AddFile(ushort const *)
0x180027b01  lea     rax, [rbp+390h+String]
0x180027b08  test    rsi, rsi
0x180027b0b  jz      short loc_180027B2A
0x180027b0d  movzx   ecx, word ptr [r14]
0x180027b11  test    cx, cx
0x180027b14  jz      short loc_180027B2A
0x180027b16  mov     [rax], cx
0x180027b19  add     r14, 2
0x180027b1d  add     rax, 2
0x180027b21  dec     rsi
0x180027b24  sub     rbx, 1
0x180027b28  jnz     short loc_180027B08
0x180027b2a  test    rbx, rbx
0x180027b2d  lea     rcx, [rax-2]
0x180027b31  cmovnz  rcx, rax
0x180027b35  mov     [rcx], r13w
0x180027b39  cmp     [rbp+390h+String], r13w
0x180027b41  jz      short loc_180027B9C
0x180027b43  lea     rcx, [rbp+390h+String]; lpString
0x180027b4a  call    cs:__imp_lstrlenW
0x180027b50  movsxd  rcx, eax
0x180027b53  cmp     [rbp+rcx*2+390h+var_262], di
0x180027b5b  jnz     short loc_180027B9C
0x180027b5d  lea     rcx, [rbp+390h+String]; lpString
0x180027b64  call    cs:__imp_lstrlenW
0x180027b6a  movsxd  rcx, eax
0x180027b6d  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rcx*2]
0x180027b75  cmp     rcx, 208h
0x180027b7c  jnb     short loc_180027B89
0x180027b7e  mov     [rbp+rcx+390h+String], r13w
0x180027b87  jmp     short loc_180027B9C
0x180027b89  call    __report_rangecheckfailure
0x180027b8f  lea     rdx, [rsp+490h+pszPath]; unsigned __int16 *
0x180027b94  mov     rcx, r15; this
0x180027b97  call    ?_AddDir@CTempFileNameArray@@AEAAJPEBG@Z; CTempFileNameArray::_AddDir(ushort const *)
0x180027b9c  lea     rcx, [rsp+490h+pszPath]; pszPath
0x180027ba1  call    cs:__imp_PathRemoveFileSpecW
0x180027ba7  lea     rdx, [rsp+490h+pszPath]; pszPath
0x180027bac  lea     rcx, [rbp+390h+String]; pszPrefix
0x180027bb3  call    cs:__imp_PathIsPrefixW
0x180027bb9  test    eax, eax
0x180027bbb  jnz     short loc_180027B8F
0x180027bbd  lea     rcx, [r15+8]; lpCriticalSection
0x180027bc1  call    cs:__imp_LeaveCriticalSection
0x180027bc7  mov     rcx, [rbp+390h+var_50]
0x180027bce  xor     rcx, rsp; StackCookie
0x180027bd1  call    __security_check_cookie
0x180027bd6  add     rsp, 458h
0x180027bdd  pop     r15
0x180027bdf  pop     r14
0x180027be1  pop     r13
0x180027be3  pop     r12
0x180027be5  pop     rdi
0x180027be6  pop     rsi
0x180027be7  pop     rbx
0x180027be8  pop     rbp
0x180027be9  retn
```
