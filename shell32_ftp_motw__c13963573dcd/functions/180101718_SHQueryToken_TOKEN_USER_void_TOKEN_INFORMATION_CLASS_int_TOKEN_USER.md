# SHQueryToken<_TOKEN_USER>(void *,_TOKEN_INFORMATION_CLASS,int,_TOKEN_USER * *)

- ea: `0x180101718`
- end: `0x18010192f`
- name: `??$SHQueryToken@U_TOKEN_USER@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@HPEAPEAU_TOKEN_USER@@@Z`
- size: `535`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180101698`
- `0x18051f238`
- `0x1805516bc`

## callees

- `0x180018e4c`
- `0x1800979b8`
- `0x180101718`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180101784`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180101784`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180101850`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801018c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180101850`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801018c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801018b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010191c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801018b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010191c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801017d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801017d4`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180101822`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180101822`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180101743`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180101877`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180101743`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180101877`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18010175f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180101892`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18010175f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180101892`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18010180d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18010180d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1801017b4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180101908`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1801017b4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180101908`

## pseudocode

```c
__int64 __fastcall SHQueryToken<_TOKEN_USER>(__int64 a1, DWORD a2, int a3, _QWORD *a4)
{
  HANDLE CurrentThread; // rax
  void *v7; // rsi
  void *v8; // rdi
  signed int v9; // ebx
  __int64 result; // rax
  HANDLE CurrentProcess; // rax
  HANDLE v12; // rax
  signed int LastError; // eax
  void *v14; // rcx
  int v15; // eax
  void *TokenHandle; // [rsp+60h] [rbp+30h] BYREF
  DWORD TokenInformationLength; // [rsp+68h] [rbp+38h] BYREF
  LPVOID TokenInformation; // [rsp+78h] [rbp+48h] BYREF

  TokenInformationLength = a2;
  *a4 = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
  {
    result = ResultFromKnownLastError();
    if ( (int)result < 0 )
    {
      if ( a3 && (_DWORD)result == -2147024891 )
      {
        v12 = GetCurrentThread();
        if ( OpenThreadToken(v12, 8u, 1, &TokenHandle) )
          goto LABEL_2;
        result = ResultFromKnownLastError();
      }
      if ( (_DWORD)result == -2147023888 )
      {
        CurrentProcess = GetCurrentProcess();
        if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
          goto LABEL_2;
        result = ResultFromKnownLastError();
      }
      if ( (int)result < 0 )
        return result;
    }
  }
LABEL_2:
  v7 = TokenHandle;
  TokenInformationLength = 2048;
  TokenInformation = LocalAlloc(0x40u, 0x800u);
  v8 = TokenInformation;
  if ( !TokenInformation )
  {
    v9 = -2147024882;
    goto LABEL_5;
  }
  v9 = 0;
  if ( !GetTokenInformation(v7, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError == 122 )
    {
      LocalFree(v8);
      v15 = CTLocalAllocPolicy::Alloc(v14, 0x40u, TokenInformationLength, &TokenInformation);
      v8 = TokenInformation;
      v9 = v15;
      if ( v15 < 0 )
        goto LABEL_17;
      if ( GetTokenInformation(v7, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
        goto LABEL_4;
      LastError = GetLastError();
      v9 = LastError;
    }
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( v9 >= 0 )
      goto LABEL_4;
LABEL_17:
    LocalFree(v8);
    goto LABEL_5;
  }
LABEL_4:
  *a4 = v8;
LABEL_5:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180101718  mov     [rsp-28h+TokenInformationLength], edx
0x18010171c  mov     [rsp-28h+TokenHandle], rcx
0x180101721  push    rbp
0x180101722  push    rbx
0x180101723  push    rsi
0x180101724  push    rdi
0x180101725  push    r14
0x180101727  mov     rbp, rsp
0x18010172a  sub     rsp, 30h
0x18010172e  mov     r14, r9
0x180101731  mov     qword ptr [r9], 0
0x180101738  mov     ebx, r8d
0x18010173b  mov     [rbp+TokenHandle], 0
0x180101743  call    cs:__imp_GetCurrentThread
0x18010174a  nop     dword ptr [rax+rax+00h]
0x18010174f  xor     r8d, r8d; OpenAsSelf
0x180101752  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180101756  mov     rcx, rax; ThreadHandle
0x180101759  lea     edi, [r8+8]
0x18010175d  mov     edx, edi; DesiredAccess
0x18010175f  call    cs:__imp_OpenThreadToken
0x180101766  nop     dword ptr [rax+rax+00h]
0x18010176b  test    eax, eax
0x18010176d  jz      loc_1801017F5
0x180101773  mov     rsi, [rbp+TokenHandle]
0x180101777  mov     edx, 800h; uBytes
0x18010177c  mov     ecx, 40h ; '@'; uFlags
0x180101781  mov     [rbp+TokenInformationLength], edx
0x180101784  call    cs:__imp_LocalAlloc
0x18010178b  nop     dword ptr [rax+rax+00h]
0x180101790  mov     [rbp+TokenInformation], rax
0x180101794  mov     rdi, rax
0x180101797  test    rax, rax
0x18010179a  jz      short loc_1801017EE
0x18010179c  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1801017a0  lea     rax, [rbp+TokenInformationLength]
0x1801017a4  xor     ebx, ebx
0x1801017a6  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1801017ab  mov     r8, rdi; TokenInformation
0x1801017ae  mov     rcx, rsi; TokenHandle
0x1801017b1  lea     edx, [rbx+1]; TokenInformationClass
0x1801017b4  call    cs:__imp_GetTokenInformation
0x1801017bb  nop     dword ptr [rax+rax+00h]
0x1801017c0  test    eax, eax
0x1801017c2  jz      loc_1801018B0
0x1801017c8  mov     [r14], rdi
0x1801017cb  mov     rcx, [rbp+TokenHandle]; hObject
0x1801017cf  test    rcx, rcx
0x1801017d2  jz      short loc_1801017E0
0x1801017d4  call    cs:__imp_CloseHandle
0x1801017db  nop     dword ptr [rax+rax+00h]
0x1801017e0  mov     eax, ebx
0x1801017e2  add     rsp, 30h
0x1801017e6  pop     r14
0x1801017e8  pop     rdi
0x1801017e9  pop     rsi
0x1801017ea  pop     rbx
0x1801017eb  pop     rbp
0x1801017ec  retn
0x1801017ee  mov     ebx, 8007000Eh
0x1801017f3  jmp     short loc_1801017CB
0x1801017f5  call    ResultFromKnownLastError
0x1801017fa  test    eax, eax
0x1801017fc  jns     loc_180101773
0x180101802  test    ebx, ebx
0x180101804  jnz     short loc_180101870
0x180101806  cmp     eax, 800703F0h
0x18010180b  jnz     short loc_18010183B
0x18010180d  call    cs:__imp_GetCurrentProcess
0x180101814  nop     dword ptr [rax+rax+00h]
0x180101819  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18010181d  mov     edx, edi; DesiredAccess
0x18010181f  mov     rcx, rax; ProcessHandle
0x180101822  call    cs:__imp_OpenProcessToken
0x180101829  nop     dword ptr [rax+rax+00h]
0x18010182e  test    eax, eax
0x180101830  jnz     loc_180101773
0x180101836  call    ResultFromKnownLastError
0x18010183b  test    eax, eax
0x18010183d  jns     loc_180101773
0x180101843  jmp     short loc_1801017E2
0x180101845  test    ebx, ebx
0x180101847  jns     loc_1801017C8
0x18010184d  mov     rcx, rdi; hMem
0x180101850  call    cs:__imp_LocalFree
0x180101857  nop     dword ptr [rax+rax+00h]
0x18010185c  jmp     loc_1801017CB
0x180101861  test    eax, eax
0x180101863  jle     short loc_180101845
0x180101865  movzx   ebx, ax
0x180101868  or      ebx, 80070000h
0x18010186e  jmp     short loc_180101845
0x180101870  cmp     eax, 80070005h
0x180101875  jnz     short loc_180101806
0x180101877  call    cs:__imp_GetCurrentThread
0x18010187e  nop     dword ptr [rax+rax+00h]
0x180101883  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180101887  mov     r8d, 1; OpenAsSelf
0x18010188d  mov     rcx, rax; ThreadHandle
0x180101890  mov     edx, edi; DesiredAccess
0x180101892  call    cs:__imp_OpenThreadToken
0x180101899  nop     dword ptr [rax+rax+00h]
0x18010189e  test    eax, eax
0x1801018a0  jnz     loc_180101773
0x1801018a6  call    ResultFromKnownLastError
0x1801018ab  jmp     loc_180101806
0x1801018b0  call    cs:__imp_GetLastError
0x1801018b7  nop     dword ptr [rax+rax+00h]
0x1801018bc  mov     ebx, eax
0x1801018be  cmp     eax, 7Ah ; 'z'
0x1801018c1  jnz     short loc_180101861
0x1801018c3  mov     rcx, rdi; hMem
0x1801018c6  call    cs:__imp_LocalFree
0x1801018cd  nop     dword ptr [rax+rax+00h]
0x1801018d2  mov     r8d, [rbp+TokenInformationLength]; unsigned __int64
0x1801018d6  lea     r9, [rbp+TokenInformation]; void **
0x1801018da  lea     edx, [rbx-3Ah]; unsigned int
0x1801018dd  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1801018e2  mov     rdi, [rbp+TokenInformation]
0x1801018e6  mov     ebx, eax
0x1801018e8  test    eax, eax
0x1801018ea  js      loc_18010184D
0x1801018f0  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1801018f4  lea     rax, [rbp+TokenInformationLength]
0x1801018f8  mov     r8, rdi; TokenInformation
0x1801018fb  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180101900  mov     edx, 1; TokenInformationClass
0x180101905  mov     rcx, rsi; TokenHandle
0x180101908  call    cs:__imp_GetTokenInformation
0x18010190f  nop     dword ptr [rax+rax+00h]
0x180101914  test    eax, eax
0x180101916  jnz     loc_1801017C8
0x18010191c  call    cs:__imp_GetLastError
0x180101923  nop     dword ptr [rax+rax+00h]
0x180101928  mov     ebx, eax
0x18010192a  jmp     loc_180101861
```
