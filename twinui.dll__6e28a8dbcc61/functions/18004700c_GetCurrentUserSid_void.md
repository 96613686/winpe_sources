# GetCurrentUserSid(void * *)

- ea: `0x18004700c`
- end: `0x180047196`
- name: `?GetCurrentUserSid@@YAJPEAPEAX@Z`
- size: `394`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180028a44`
- `0x180046ee0`

## callees

- `0x18004700c`
- `0x180047224`
- `0x18013d330`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180047046`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180047046`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180047061`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180047061`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004714b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004714b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004713b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004713b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800470fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800470fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047177`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047177`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800470d3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800470d3`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800470bf`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800470bf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180047090`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180047090`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800470e9`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800470e9`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800470b2`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800470b2`

## pseudocode

```c
__int64 __fastcall GetCurrentUserSid(void **a1)
{
  HANDLE CurrentThread; // rax
  void *v3; // rsi
  int Error; // ebx
  void *v5; // rcx
  DWORD LengthSid; // ebp
  HLOCAL v7; // rax
  void *v8; // rdi
  HANDLE CurrentProcess; // rax
  void *TokenHandle; // [rsp+30h] [rbp-98h] BYREF
  DWORD ReturnLength; // [rsp+38h] [rbp-90h] BYREF
  void *TokenInformation; // [rsp+40h] [rbp-88h] BYREF

  *a1 = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    goto LABEL_2;
  Error = ResultFromKnownLastError();
  if ( Error == -2147023888 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
      goto LABEL_2;
    Error = ResultFromKnownLastError();
  }
  if ( Error < 0 )
    return (unsigned int)Error;
LABEL_2:
  ReturnLength = 88;
  if ( !GetTokenInformation(TokenHandle, TokenUser, &TokenInformation, 0x58u, &ReturnLength) )
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
      goto LABEL_8;
  }
  v3 = TokenInformation;
  Error = -2147024809;
  v5 = TokenInformation;
  *a1 = 0;
  if ( !IsValidSid(v5) )
    goto LABEL_8;
  LengthSid = GetLengthSid(v3);
  Error = -2147024882;
  v7 = LocalAlloc(0x40u, LengthSid);
  v8 = v7;
  if ( !v7 )
    goto LABEL_8;
  if ( CopySid(LengthSid, v7, v3) )
  {
    Error = 0;
  }
  else
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
    {
      LocalFree(v8);
      goto LABEL_8;
    }
  }
  *a1 = v8;
LABEL_8:
  CloseHandle(TokenHandle);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18004700c  mov     [rsp+arg_8], rbx
0x180047011  mov     [rsp+arg_10], rbp
0x180047016  push    rsi
0x180047017  push    rdi
0x180047018  push    r14
0x18004701a  sub     rsp, 0B0h
0x180047021  mov     rax, cs:__security_cookie
0x180047028  xor     rax, rsp
0x18004702b  mov     [rsp+0C8h+var_28], rax
0x180047033  mov     r14, rcx
0x180047036  mov     qword ptr [rcx], 0
0x18004703d  mov     [rsp+0C8h+TokenHandle], 0
0x180047046  call    cs:__imp_GetCurrentThread
0x18004704c  mov     esi, 1
0x180047051  lea     r9, [rsp+0C8h+TokenHandle]; TokenHandle
0x180047056  mov     rcx, rax; ThreadHandle
0x180047059  mov     r8d, esi; OpenAsSelf
0x18004705c  lea     edi, [rsi+7]
0x18004705f  mov     edx, edi; DesiredAccess
0x180047061  call    cs:__imp_OpenThreadToken
0x180047067  test    eax, eax
0x180047069  jz      loc_18004712D
0x18004706f  mov     rcx, [rsp+0C8h+TokenHandle]; TokenHandle
0x180047074  lea     rax, [rsp+0C8h+var_90]
0x180047079  mov     r9d, 58h ; 'X'; TokenInformationLength
0x18004707f  mov     [rsp+0C8h+ReturnLength], rax; ReturnLength
0x180047084  lea     r8, [rsp+0C8h+TokenInformation]; TokenInformation
0x180047089  mov     [rsp+0C8h+var_90], r9d
0x18004708e  mov     edx, esi; TokenInformationClass
0x180047090  call    cs:__imp_GetTokenInformation
0x180047096  test    eax, eax
0x180047098  jz      loc_180047182
0x18004709e  mov     rsi, [rsp+0C8h+TokenInformation]
0x1800470a3  mov     ebx, 80070057h
0x1800470a8  mov     rcx, rsi; pSid
0x1800470ab  mov     qword ptr [r14], 0
0x1800470b2  call    cs:__imp_IsValidSid
0x1800470b8  test    eax, eax
0x1800470ba  jz      short loc_1800470F8
0x1800470bc  mov     rcx, rsi; pSid
0x1800470bf  call    cs:__imp_GetLengthSid
0x1800470c5  mov     edx, eax; uBytes
0x1800470c7  mov     ecx, 40h ; '@'; uFlags
0x1800470cc  mov     ebp, eax
0x1800470ce  mov     ebx, 8007000Eh
0x1800470d3  call    cs:__imp_LocalAlloc
0x1800470d9  mov     rdi, rax
0x1800470dc  test    rax, rax
0x1800470df  jz      short loc_1800470F8
0x1800470e1  mov     r8, rsi; pSourceSid
0x1800470e4  mov     rdx, rax; pDestinationSid
0x1800470e7  mov     ecx, ebp; nDestinationSidLength
0x1800470e9  call    cs:__imp_CopySid
0x1800470ef  test    eax, eax
0x1800470f1  jz      short loc_180047169
0x1800470f3  xor     ebx, ebx
0x1800470f5  mov     [r14], rdi
0x1800470f8  mov     rcx, [rsp+0C8h+TokenHandle]; hObject
0x1800470fd  call    cs:__imp_CloseHandle
0x180047103  mov     eax, ebx
0x180047105  mov     rcx, [rsp+0C8h+var_28]
0x18004710d  xor     rcx, rsp; StackCookie
0x180047110  call    __security_check_cookie
0x180047115  lea     r11, [rsp+0C8h+var_18]
0x18004711d  mov     rbx, [r11+28h]
0x180047121  mov     rbp, [r11+30h]
0x180047125  mov     rsp, r11
0x180047128  pop     r14
0x18004712a  pop     rdi
0x18004712b  pop     rsi
0x18004712c  retn
0x18004712d  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180047132  mov     ebx, eax
0x180047134  cmp     eax, 800703F0h
0x180047139  jnz     short loc_180047160
0x18004713b  call    cs:__imp_GetCurrentProcess
0x180047141  lea     r8, [rsp+0C8h+TokenHandle]; TokenHandle
0x180047146  mov     edx, edi; DesiredAccess
0x180047148  mov     rcx, rax; ProcessHandle
0x18004714b  call    cs:__imp_OpenProcessToken
0x180047151  test    eax, eax
0x180047153  jnz     loc_18004706F
0x180047159  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18004715e  mov     ebx, eax
0x180047160  test    ebx, ebx
0x180047162  js      short loc_180047103
0x180047164  jmp     loc_18004706F
0x180047169  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18004716e  mov     ebx, eax
0x180047170  test    eax, eax
0x180047172  jns     short loc_1800470F5
0x180047174  mov     rcx, rdi; hMem
0x180047177  call    cs:__imp_LocalFree
0x18004717d  jmp     loc_1800470F8
0x180047182  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180047187  mov     ebx, eax
0x180047189  test    eax, eax
0x18004718b  js      loc_1800470F8
0x180047191  jmp     loc_18004709E
```
