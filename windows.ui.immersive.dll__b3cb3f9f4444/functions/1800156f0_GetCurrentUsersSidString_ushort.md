# GetCurrentUsersSidString(ushort * *)

- ea: `0x1800156f0`
- end: `0x18001590b`
- name: `?GetCurrentUsersSidString@@YAJPEAPEAG@Z`
- size: `539`
- prototype: `__int64 __fastcall(LPWSTR *ppwsz)`
- caller_count: `7`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180014380`
- `0x180014b00`
- `0x180014e10`
- `0x180015550`
- `0x180015920`
- `0x1800ca1e0`
- `0x1800db630`

## callees

- `0x1800156f0`
- `0x180032e68`
- `0x18003d244`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800157e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015846`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800157e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015846`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180015731`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180015731`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180015715`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180015715`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001576c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001576c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180015757`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180015757`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015889`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015889`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800157fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015868`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800158dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800158eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800157fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015868`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800158dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800158eb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001579c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001579c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800157d0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180015836`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800157d0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180015836`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800158ca`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800158ca`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800158a8`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800158a8`

## pseudocode

```c
__int64 __fastcall GetCurrentUsersSidString(LPWSTR *ppwsz)
{
  HANDLE CurrentThread; // rax
  int Error; // eax
  int v4; // ebx
  HANDLE CurrentProcess; // rax
  void *v6; // r14
  void **v7; // rsi
  void *v8; // rdi
  signed int LastError; // eax
  void *v10; // rcx
  int v11; // eax
  void *v12; // rcx
  DWORD TokenInformationLength; // [rsp+60h] [rbp+30h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp+38h] BYREF
  LPVOID TokenInformation; // [rsp+70h] [rbp+40h] BYREF

  *ppwsz = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
  {
    Error = ResultFromKnownLastError();
    v4 = Error;
    if ( Error < 0 )
    {
      if ( Error != -2147023888 )
        return (unsigned int)v4;
      CurrentProcess = GetCurrentProcess();
      if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
      {
        v4 = ResultFromKnownLastError();
        if ( v4 < 0 )
          return (unsigned int)v4;
      }
    }
  }
  v6 = TokenHandle;
  v7 = 0;
  TokenInformationLength = 2048;
  TokenInformation = LocalAlloc(0x40u, 0x800u);
  v8 = TokenInformation;
  if ( !TokenInformation )
  {
    v4 = -2147024882;
    goto LABEL_18;
  }
  v4 = 0;
  if ( GetTokenInformation(v6, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
    goto LABEL_16;
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError != 122 )
    goto LABEL_12;
  LocalFree(v8);
  v11 = CTLocalAllocPolicy::Alloc(v10, 0x40u, TokenInformationLength, &TokenInformation);
  v8 = TokenInformation;
  v4 = v11;
  if ( v11 >= 0 )
  {
    if ( GetTokenInformation(v6, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
      goto LABEL_16;
    LastError = GetLastError();
    v4 = LastError;
LABEL_12:
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 < 0 )
      goto LABEL_15;
LABEL_16:
    v7 = (void **)v8;
    goto LABEL_18;
  }
LABEL_15:
  LocalFree(v8);
LABEL_18:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v4 >= 0 )
  {
    v12 = *v7;
    TokenInformation = 0;
    if ( ConvertSidToStringSidW(v12, (LPWSTR *)&TokenInformation) || (v4 = ResultFromKnownLastError(), v4 >= 0) )
    {
      v4 = SHStrDupW((LPCWSTR)TokenInformation, ppwsz);
      LocalFree(TokenInformation);
    }
    LocalFree(v7);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800156f0  mov     [rsp-28h+arg_18], rbx
0x1800156f5  push    rbp
0x1800156f6  push    rsi
0x1800156f7  push    rdi
0x1800156f8  push    r14
0x1800156fa  push    r15
0x1800156fc  mov     rbp, rsp
0x1800156ff  sub     rsp, 30h
0x180015703  mov     r15, rcx
0x180015706  mov     qword ptr [rcx], 0
0x18001570d  mov     [rbp+TokenHandle], 0
0x180015715  call    cs:__imp_GetCurrentThread
0x18001571c  nop     dword ptr [rax+rax+00h]
0x180015721  xor     r8d, r8d; OpenAsSelf
0x180015724  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180015728  mov     rcx, rax; ThreadHandle
0x18001572b  lea     edi, [r8+8]
0x18001572f  mov     edx, edi; DesiredAccess
0x180015731  call    cs:__imp_OpenThreadToken
0x180015738  nop     dword ptr [rax+rax+00h]
0x18001573d  test    eax, eax
0x18001573f  jnz     short loc_18001578B
0x180015741  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180015746  mov     ebx, eax
0x180015748  test    eax, eax
0x18001574a  jns     short loc_18001578B
0x18001574c  cmp     eax, 800703F0h
0x180015751  jnz     loc_1800158F7
0x180015757  call    cs:__imp_GetCurrentProcess
0x18001575e  nop     dword ptr [rax+rax+00h]
0x180015763  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180015767  mov     edx, edi; DesiredAccess
0x180015769  mov     rcx, rax; ProcessHandle
0x18001576c  call    cs:__imp_OpenProcessToken
0x180015773  nop     dword ptr [rax+rax+00h]
0x180015778  test    eax, eax
0x18001577a  jnz     short loc_18001578B
0x18001577c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180015781  mov     ebx, eax
0x180015783  test    eax, eax
0x180015785  js      loc_1800158F7
0x18001578b  mov     r14, [rbp+TokenHandle]
0x18001578f  mov     edx, 800h; uBytes
0x180015794  xor     esi, esi
0x180015796  mov     [rbp+TokenInformationLength], edx
0x180015799  lea     ecx, [rsi+40h]; uFlags
0x18001579c  call    cs:__imp_LocalAlloc
0x1800157a3  nop     dword ptr [rax+rax+00h]
0x1800157a8  mov     [rbp+TokenInformation], rax
0x1800157ac  mov     rdi, rax
0x1800157af  test    rax, rax
0x1800157b2  jz      loc_18001587B
0x1800157b8  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800157bc  lea     rax, [rbp+TokenInformationLength]
0x1800157c0  mov     r8, rdi; TokenInformation
0x1800157c3  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1800157c8  lea     edx, [rsi+1]; TokenInformationClass
0x1800157cb  mov     rcx, r14; TokenHandle
0x1800157ce  xor     ebx, ebx
0x1800157d0  call    cs:__imp_GetTokenInformation
0x1800157d7  nop     dword ptr [rax+rax+00h]
0x1800157dc  test    eax, eax
0x1800157de  jnz     loc_180015876
0x1800157e4  call    cs:__imp_GetLastError
0x1800157eb  nop     dword ptr [rax+rax+00h]
0x1800157f0  mov     ebx, eax
0x1800157f2  cmp     eax, 7Ah ; 'z'
0x1800157f5  jnz     short loc_180015854
0x1800157f7  mov     rcx, rdi; hMem
0x1800157fa  call    cs:__imp_LocalFree
0x180015801  nop     dword ptr [rax+rax+00h]
0x180015806  mov     r8d, [rbp+TokenInformationLength]; unsigned __int64
0x18001580a  lea     r9, [rbp+TokenInformation]; void **
0x18001580e  lea     edx, [rsi+40h]; unsigned int
0x180015811  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180015816  mov     rdi, [rbp+TokenInformation]
0x18001581a  mov     ebx, eax
0x18001581c  test    eax, eax
0x18001581e  js      short loc_180015865
0x180015820  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180015824  lea     rax, [rbp+TokenInformationLength]
0x180015828  mov     r8, rdi; TokenInformation
0x18001582b  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180015830  lea     edx, [rsi+1]; TokenInformationClass
0x180015833  mov     rcx, r14; TokenHandle
0x180015836  call    cs:__imp_GetTokenInformation
0x18001583d  nop     dword ptr [rax+rax+00h]
0x180015842  test    eax, eax
0x180015844  jnz     short loc_180015876
0x180015846  call    cs:__imp_GetLastError
0x18001584d  nop     dword ptr [rax+rax+00h]
0x180015852  mov     ebx, eax
0x180015854  test    eax, eax
0x180015856  jle     short loc_180015861
0x180015858  movzx   ebx, ax
0x18001585b  or      ebx, 80070000h
0x180015861  test    ebx, ebx
0x180015863  jns     short loc_180015876
0x180015865  mov     rcx, rdi; hMem
0x180015868  call    cs:__imp_LocalFree
0x18001586f  nop     dword ptr [rax+rax+00h]
0x180015874  jmp     short loc_180015880
0x180015876  mov     rsi, rdi
0x180015879  jmp     short loc_180015880
0x18001587b  mov     ebx, 8007000Eh
0x180015880  mov     rcx, [rbp+TokenHandle]; hObject
0x180015884  test    rcx, rcx
0x180015887  jz      short loc_180015895
0x180015889  call    cs:__imp_CloseHandle
0x180015890  nop     dword ptr [rax+rax+00h]
0x180015895  test    ebx, ebx
0x180015897  js      short loc_1800158F7
0x180015899  mov     rcx, [rsi]; Sid
0x18001589c  lea     rdx, [rbp+TokenInformation]; StringSid
0x1800158a0  mov     [rbp+TokenInformation], 0
0x1800158a8  call    cs:__imp_ConvertSidToStringSidW
0x1800158af  nop     dword ptr [rax+rax+00h]
0x1800158b4  test    eax, eax
0x1800158b6  jnz     short loc_1800158C3
0x1800158b8  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800158bd  mov     ebx, eax
0x1800158bf  test    eax, eax
0x1800158c1  js      short loc_1800158E8
0x1800158c3  mov     rcx, [rbp+TokenInformation]; psz
0x1800158c7  mov     rdx, r15; ppwsz
0x1800158ca  call    cs:__imp_SHStrDupW
0x1800158d1  nop     dword ptr [rax+rax+00h]
0x1800158d6  mov     rcx, [rbp+TokenInformation]; hMem
0x1800158da  mov     ebx, eax
0x1800158dc  call    cs:__imp_LocalFree
0x1800158e3  nop     dword ptr [rax+rax+00h]
0x1800158e8  mov     rcx, rsi; hMem
0x1800158eb  call    cs:__imp_LocalFree
0x1800158f2  nop     dword ptr [rax+rax+00h]
0x1800158f7  mov     eax, ebx
0x1800158f9  mov     rbx, [rsp+30h+arg_18]
0x1800158fe  add     rsp, 30h
0x180015902  pop     r15
0x180015904  pop     r14
0x180015906  pop     rdi
0x180015907  pop     rsi
0x180015908  pop     rbp
0x180015909  retn
```
