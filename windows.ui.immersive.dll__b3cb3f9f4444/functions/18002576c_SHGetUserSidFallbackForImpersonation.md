# SHGetUserSidFallbackForImpersonation

- ea: `0x18002576c`
- end: `0x1800259e6`
- name: `SHGetUserSidFallbackForImpersonation`
- size: `634`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180024904`
- `0x1800249e0`

## callees

- `0x180006800`
- `0x18002576c`
- `0x180032e68`
- `0x18003d244`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025899`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800258fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025899`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800258fb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800257b2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800257ed`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800257b2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800257ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180025796`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800257d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180025796`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800257d4`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180025821`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180025821`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002580c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002580c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002593e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002593e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800258af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002591d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800259c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800258af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002591d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800259c6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180025851`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180025851`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180025955`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180025955`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180025990`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180025990`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180025885`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800258eb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180025885`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800258eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800259b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800259b7`

## pseudocode

```c
__int64 __fastcall SHGetUserSidFallbackForImpersonation(__int64 a1, _QWORD *a2)
{
  HANDLE CurrentThread; // rax
  int Error; // eax
  signed int v5; // ebx
  HANDLE v6; // rax
  HANDLE CurrentProcess; // rax
  void *v8; // r14
  PSID *v9; // rsi
  void *v10; // rdi
  signed int LastError; // eax
  void *v12; // rcx
  int v13; // eax
  DWORD LengthSid; // eax
  DWORD v15; // r14d
  void *v16; // rcx
  void *v17; // rdi
  __int64 TokenInformationLength; // [rsp+60h] [rbp+30h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp+38h] BYREF
  LPVOID TokenInformation; // [rsp+70h] [rbp+40h] BYREF

  TokenInformationLength = a1;
  *a2 = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
  {
    Error = ResultFromKnownLastError();
    v5 = Error;
    if ( Error < 0 )
    {
      if ( Error == -2147024891 )
      {
        v6 = GetCurrentThread();
        if ( OpenThreadToken(v6, 8u, 1, &TokenHandle) )
          goto LABEL_10;
        v5 = ResultFromKnownLastError();
      }
      if ( v5 == -2147023888 )
      {
        CurrentProcess = GetCurrentProcess();
        if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
          goto LABEL_10;
        v5 = ResultFromKnownLastError();
      }
      if ( v5 < 0 )
        return (unsigned int)v5;
    }
  }
LABEL_10:
  v8 = TokenHandle;
  v9 = 0;
  LODWORD(TokenInformationLength) = 2048;
  TokenInformation = LocalAlloc(0x40u, 0x800u);
  v10 = TokenInformation;
  if ( TokenInformation )
  {
    v5 = 0;
    if ( !GetTokenInformation(v8, TokenUser, TokenInformation, TokenInformationLength, (PDWORD)&TokenInformationLength) )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError == 122 )
      {
        LocalFree(v10);
        v13 = CTLocalAllocPolicy::Alloc(v12, 0x40u, (unsigned int)TokenInformationLength, &TokenInformation);
        v10 = TokenInformation;
        v5 = v13;
        if ( v13 < 0 )
        {
LABEL_19:
          LocalFree(v10);
          goto LABEL_22;
        }
        if ( GetTokenInformation(
               v8,
               TokenUser,
               TokenInformation,
               TokenInformationLength,
               (PDWORD)&TokenInformationLength) )
        {
          goto LABEL_20;
        }
        LastError = GetLastError();
        v5 = LastError;
      }
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( v5 < 0 )
        goto LABEL_19;
    }
LABEL_20:
    v9 = (PSID *)v10;
    goto LABEL_22;
  }
  v5 = -2147024882;
LABEL_22:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v5 >= 0 )
  {
    LengthSid = GetLengthSid(*v9);
    TokenInformation = 0;
    v15 = LengthSid;
    v5 = CTCoAllocPolicy::Alloc(v16, 1u, LengthSid, &TokenInformation);
    if ( v5 < 0 )
    {
LABEL_31:
      LocalFree(v9);
      return (unsigned int)v5;
    }
    v17 = TokenInformation;
    if ( CopySid(v15, TokenInformation, *v9) )
    {
      v5 = 0;
    }
    else
    {
      v5 = ResultFromKnownLastError();
      if ( v5 < 0 )
      {
LABEL_30:
        CoTaskMemFree(v17);
        goto LABEL_31;
      }
    }
    *a2 = v17;
    v17 = 0;
    goto LABEL_30;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002576c  mov     [rsp-28h+arg_18], rbx
0x180025771  mov     [rsp-28h+TokenInformationLength], rcx
0x180025776  push    rbp
0x180025777  push    rsi
0x180025778  push    rdi
0x180025779  push    r14
0x18002577b  push    r15
0x18002577d  mov     rbp, rsp
0x180025780  sub     rsp, 30h
0x180025784  mov     r15, rdx
0x180025787  mov     qword ptr [rdx], 0
0x18002578e  mov     [rbp+TokenHandle], 0
0x180025796  call    cs:__imp_GetCurrentThread
0x18002579d  nop     dword ptr [rax+rax+00h]
0x1800257a2  xor     r8d, r8d; OpenAsSelf
0x1800257a5  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800257a9  mov     rcx, rax; ThreadHandle
0x1800257ac  lea     edi, [r8+8]
0x1800257b0  mov     edx, edi; DesiredAccess
0x1800257b2  call    cs:__imp_OpenThreadToken
0x1800257b9  nop     dword ptr [rax+rax+00h]
0x1800257be  test    eax, eax
0x1800257c0  jnz     short loc_180025840
0x1800257c2  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800257c7  mov     ebx, eax
0x1800257c9  test    eax, eax
0x1800257cb  jns     short loc_180025840
0x1800257cd  cmp     eax, 80070005h
0x1800257d2  jnz     short loc_180025804
0x1800257d4  call    cs:__imp_GetCurrentThread
0x1800257db  nop     dword ptr [rax+rax+00h]
0x1800257e0  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800257e4  mov     edx, edi; DesiredAccess
0x1800257e6  mov     rcx, rax; ThreadHandle
0x1800257e9  lea     r8d, [rdi-7]; OpenAsSelf
0x1800257ed  call    cs:__imp_OpenThreadToken
0x1800257f4  nop     dword ptr [rax+rax+00h]
0x1800257f9  test    eax, eax
0x1800257fb  jnz     short loc_180025840
0x1800257fd  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180025802  mov     ebx, eax
0x180025804  cmp     ebx, 800703F0h
0x18002580a  jnz     short loc_180025838
0x18002580c  call    cs:__imp_GetCurrentProcess
0x180025813  nop     dword ptr [rax+rax+00h]
0x180025818  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18002581c  mov     edx, edi; DesiredAccess
0x18002581e  mov     rcx, rax; ProcessHandle
0x180025821  call    cs:__imp_OpenProcessToken
0x180025828  nop     dword ptr [rax+rax+00h]
0x18002582d  test    eax, eax
0x18002582f  jnz     short loc_180025840
0x180025831  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180025836  mov     ebx, eax
0x180025838  test    ebx, ebx
0x18002583a  js      loc_1800259D2
0x180025840  mov     r14, [rbp+TokenHandle]
0x180025844  mov     edx, 800h; uBytes
0x180025849  xor     esi, esi
0x18002584b  mov     dword ptr [rbp+TokenInformationLength], edx
0x18002584e  lea     ecx, [rsi+40h]; uFlags
0x180025851  call    cs:__imp_LocalAlloc
0x180025858  nop     dword ptr [rax+rax+00h]
0x18002585d  mov     [rbp+TokenInformation], rax
0x180025861  mov     rdi, rax
0x180025864  test    rax, rax
0x180025867  jz      loc_180025930
0x18002586d  mov     r9d, dword ptr [rbp+TokenInformationLength]; TokenInformationLength
0x180025871  lea     rax, [rbp+TokenInformationLength]
0x180025875  mov     r8, rdi; TokenInformation
0x180025878  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18002587d  lea     edx, [rsi+1]; TokenInformationClass
0x180025880  mov     rcx, r14; TokenHandle
0x180025883  xor     ebx, ebx
0x180025885  call    cs:__imp_GetTokenInformation
0x18002588c  nop     dword ptr [rax+rax+00h]
0x180025891  test    eax, eax
0x180025893  jnz     loc_18002592B
0x180025899  call    cs:__imp_GetLastError
0x1800258a0  nop     dword ptr [rax+rax+00h]
0x1800258a5  mov     ebx, eax
0x1800258a7  cmp     eax, 7Ah ; 'z'
0x1800258aa  jnz     short loc_180025909
0x1800258ac  mov     rcx, rdi; hMem
0x1800258af  call    cs:__imp_LocalFree
0x1800258b6  nop     dword ptr [rax+rax+00h]
0x1800258bb  mov     r8d, dword ptr [rbp+TokenInformationLength]; unsigned __int64
0x1800258bf  lea     r9, [rbp+TokenInformation]; void **
0x1800258c3  lea     edx, [rsi+40h]; unsigned int
0x1800258c6  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800258cb  mov     rdi, [rbp+TokenInformation]
0x1800258cf  mov     ebx, eax
0x1800258d1  test    eax, eax
0x1800258d3  js      short loc_18002591A
0x1800258d5  mov     r9d, dword ptr [rbp+TokenInformationLength]; TokenInformationLength
0x1800258d9  lea     rax, [rbp+TokenInformationLength]
0x1800258dd  mov     r8, rdi; TokenInformation
0x1800258e0  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1800258e5  lea     edx, [rsi+1]; TokenInformationClass
0x1800258e8  mov     rcx, r14; TokenHandle
0x1800258eb  call    cs:__imp_GetTokenInformation
0x1800258f2  nop     dword ptr [rax+rax+00h]
0x1800258f7  test    eax, eax
0x1800258f9  jnz     short loc_18002592B
0x1800258fb  call    cs:__imp_GetLastError
0x180025902  nop     dword ptr [rax+rax+00h]
0x180025907  mov     ebx, eax
0x180025909  test    eax, eax
0x18002590b  jle     short loc_180025916
0x18002590d  movzx   ebx, ax
0x180025910  or      ebx, 80070000h
0x180025916  test    ebx, ebx
0x180025918  jns     short loc_18002592B
0x18002591a  mov     rcx, rdi; hMem
0x18002591d  call    cs:__imp_LocalFree
0x180025924  nop     dword ptr [rax+rax+00h]
0x180025929  jmp     short loc_180025935
0x18002592b  mov     rsi, rdi
0x18002592e  jmp     short loc_180025935
0x180025930  mov     ebx, 8007000Eh
0x180025935  mov     rcx, [rbp+TokenHandle]; hObject
0x180025939  test    rcx, rcx
0x18002593c  jz      short loc_18002594A
0x18002593e  call    cs:__imp_CloseHandle
0x180025945  nop     dword ptr [rax+rax+00h]
0x18002594a  test    ebx, ebx
0x18002594c  js      loc_1800259D2
0x180025952  mov     rcx, [rsi]; pSid
0x180025955  call    cs:__imp_GetLengthSid
0x18002595c  nop     dword ptr [rax+rax+00h]
0x180025961  lea     r9, [rbp+TokenInformation]; void **
0x180025965  mov     [rbp+TokenInformation], 0
0x18002596d  mov     r8d, eax; unsigned __int64
0x180025970  mov     edx, 1; unsigned int
0x180025975  mov     r14d, eax
0x180025978  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18002597d  mov     ebx, eax
0x18002597f  test    eax, eax
0x180025981  js      short loc_1800259C3
0x180025983  mov     rdi, [rbp+TokenInformation]
0x180025987  mov     ecx, r14d; nDestinationSidLength
0x18002598a  mov     r8, [rsi]; pSourceSid
0x18002598d  mov     rdx, rdi; pDestinationSid
0x180025990  call    cs:__imp_CopySid
0x180025997  nop     dword ptr [rax+rax+00h]
0x18002599c  test    eax, eax
0x18002599e  jz      short loc_1800259A4
0x1800259a0  xor     ebx, ebx
0x1800259a2  jmp     short loc_1800259AF
0x1800259a4  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800259a9  mov     ebx, eax
0x1800259ab  test    eax, eax
0x1800259ad  js      short loc_1800259B4
0x1800259af  mov     [r15], rdi
0x1800259b2  xor     edi, edi
0x1800259b4  mov     rcx, rdi; pv
0x1800259b7  call    cs:__imp_CoTaskMemFree
0x1800259be  nop     dword ptr [rax+rax+00h]
0x1800259c3  mov     rcx, rsi; hMem
0x1800259c6  call    cs:__imp_LocalFree
0x1800259cd  nop     dword ptr [rax+rax+00h]
0x1800259d2  mov     eax, ebx
0x1800259d4  mov     rbx, [rsp+30h+arg_18]
0x1800259d9  add     rsp, 30h
0x1800259dd  pop     r15
0x1800259df  pop     r14
0x1800259e1  pop     rdi
0x1800259e2  pop     rsi
0x1800259e3  pop     rbp
0x1800259e4  retn
```
