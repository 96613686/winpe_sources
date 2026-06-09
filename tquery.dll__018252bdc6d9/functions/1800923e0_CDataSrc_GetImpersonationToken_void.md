# CDataSrc::GetImpersonationToken(void)

- ea: `0x1800923e0`
- end: `0x180092490`
- name: `?GetImpersonationToken@CDataSrc@@SAPEAXXZ`
- size: `176`
- prototype: `static void *(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180092080`

## callees

- `0x180038f08`
- `0x1800923e0`
- `0x18015aa68`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092414`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092446`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092414`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092446`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180092421`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180092421`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800923ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800923ef`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18009240a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18009240a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180092431`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180092431`

## string_xrefs

- `0x18009244c`: `[Query] DupImpersonationToken failed to get token, %x\n`

## pseudocode

```c
void *CDataSrc::GetImpersonationToken(void)
{
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  const wchar_t *LastError; // rbx
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  void *TokenHandle; // [rsp+30h] [rbp+8h] BYREF

  TokenHandle = (void *)-1LL;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) )
  {
    if ( GetLastError() != 1008
      || (CurrentProcess = GetCurrentProcess(), !OpenProcessToken(CurrentProcess, 0xF01FFu, &TokenHandle)) )
    {
      LastError = (const wchar_t *)GetLastError();
      SearchIndexerDebug::Error(
        (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\tquery\\cidso\\datasrc.cxx",
        (const wchar_t *)0x223,
        (unsigned int)L"[Query] DupImpersonationToken failed to get token, %x\n",
        LastError);
      if ( (int)LastError > 0 )
        LODWORD(LastError) = (unsigned __int16)LastError | 0x80070000;
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x224,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cidso\\datasrc.cxx",
        (const char *)(unsigned int)LastError,
        v4);
    }
  }
  return TokenHandle;
}

```

## disassembly

```asm
0x1800923e0  push    rbx; int
0x1800923e2  sub     rsp, 20h
0x1800923e6  mov     [rsp+28h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x1800923ef  call    cs:__imp_GetCurrentThread
0x1800923f5  mov     ebx, 0F01FFh
0x1800923fa  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x1800923ff  mov     rcx, rax; ThreadHandle
0x180092402  mov     edx, ebx; DesiredAccess
0x180092404  mov     r8d, 1; OpenAsSelf
0x18009240a  call    cs:__imp_OpenThreadToken
0x180092410  test    eax, eax
0x180092412  jnz     short loc_18009243B
0x180092414  call    cs:__imp_GetLastError
0x18009241a  cmp     eax, 3F0h
0x18009241f  jnz     short loc_180092446
0x180092421  call    cs:__imp_GetCurrentProcess
0x180092427  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x18009242c  mov     edx, ebx; DesiredAccess
0x18009242e  mov     rcx, rax; ProcessHandle
0x180092431  call    cs:__imp_OpenProcessToken
0x180092437  test    eax, eax
0x180092439  jz      short loc_180092446
0x18009243b  mov     rax, [rsp+28h+TokenHandle]
0x180092440  add     rsp, 20h
0x180092444  pop     rbx
0x180092445  retn
0x180092446  call    cs:__imp_GetLastError
0x18009244c  lea     r8, aQueryDupimpers; "[Query] DupImpersonationToken failed to"...
0x180092453  mov     edx, 223h; wchar_t *
0x180092458  mov     r9d, eax; wchar_t *
0x18009245b  lea     rcx, aOnecoreuapBase_70; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x180092462  mov     ebx, eax
0x180092464  call    ?Error@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Error(wchar_t const *,uint,wchar_t const *,...)
0x180092469  test    ebx, ebx
0x18009246b  jle     short loc_180092476
0x18009246d  movzx   ebx, bx
0x180092470  or      ebx, 80070000h
0x180092476  mov     rcx, [rsp+28h]; this
0x18009247b  lea     r8, aOnecoreuapBase_171; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x180092482  mov     r9d, ebx; char *
0x180092485  mov     edx, 224h; void *
0x18009248a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
