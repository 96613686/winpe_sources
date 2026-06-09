# GetDetailedErrorCode(ulong *)

- ea: `0x1800fc150`
- end: `0x1800fc31d`
- name: `?GetDetailedErrorCode@@YAJPEAK@Z`
- size: `461`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task`

## callers

- `0x1800fc324`

## callees

- `0x18000def4`
- `0x18000df20`
- `0x1800fc150`
- `0x180238960`
- `0x180238984`
- `0x180239584`
- `0x180240d40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fc20d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fc20d`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800fc1c6`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800fc1c6`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800fc2e7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800fc2f5`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800fc2e7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800fc2f5`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800fc1a1`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800fc1a1`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1800fc1f7`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1800fc29c`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1800fc1f7`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x1800fc29c`

## string_xrefs

- `0x1800fc190`: `ServicesActive`
- `0x1800fc274`: `C:\__w\1\s\src\Client\Engine\Agent\bitsfixup.cpp`
- `0x1800fc2b0`: `C:\__w\1\s\src\Client\Engine\Agent\bitsfixup.cpp`

## pseudocode

```c
__int64 __fastcall GetDetailedErrorCode(unsigned int *a1)
{
  SC_HANDLE v1; // rsi
  SC_HANDLE v2; // rdi
  void *v3; // rbx
  unsigned int LastError; // ebp
  __int64 v6; // rdx
  SC_HANDLE v7; // rax
  const char *v8; // r9
  __int64 v9; // rdx
  DWORD v10; // r9d
  DWORD v11; // ebp
  void *v12; // rax
  const struct std::nothrow_t *v13; // rdx
  unsigned int v14; // eax
  int pcbBytesNeeded; // [rsp+20h] [rbp-38h]
  DWORD cbBufSize; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v1 = 0;
  v2 = 0;
  v3 = 0;
  if ( !a1 )
  {
    LastError = -2147467261;
    v6 = 130;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\bitsfixup.cpp",
      (const char *)LastError,
      pcbBytesNeeded);
    goto LABEL_24;
  }
  *a1 = 0;
  v7 = OpenSCManagerW(0, L"ServicesActive", 0x80000000);
  v1 = v7;
  if ( !v7 )
  {
    v9 = 136;
LABEL_20:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v9,
                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\bitsfixup.cpp",
                  v8);
    goto LABEL_24;
  }
  v2 = OpenServiceW(v7, L"BITS", 0x80000000);
  if ( !v2 )
  {
    v9 = 142;
    goto LABEL_20;
  }
  cbBufSize = 0;
  if ( QueryServiceStatusEx(v2, SC_STATUS_PROCESS_INFO, 0, 0, &cbBufSize) )
  {
    LastError = -2145120257;
    v6 = 147;
    goto LABEL_16;
  }
  if ( GetLastError() != 122 )
  {
    LastError = -2147019873;
    v6 = 148;
    goto LABEL_16;
  }
  v10 = cbBufSize;
  v11 = cbBufSize;
  if ( cbBufSize )
  {
    v12 = operator new[](cbBufSize, (const struct std::nothrow_t *)&std::nothrow);
    v3 = v12;
    if ( v12 )
      memset(v12, 0, v11);
    LastError = v3 == 0 ? 0x8007000E : 0;
    if ( !v3 )
    {
      v6 = 149;
      goto LABEL_16;
    }
    v10 = cbBufSize;
  }
  if ( !QueryServiceStatusEx(v2, SC_STATUS_PROCESS_INFO, (LPBYTE)v3, v10, &cbBufSize) )
  {
    v9 = 155;
    goto LABEL_20;
  }
  v14 = *((_DWORD *)v3 + 3);
  if ( v14 == 1066 )
    v14 = *((_DWORD *)v3 + 4);
  *a1 = v14;
  LastError = 0;
LABEL_24:
  if ( v3 )
    operator delete(v3, v13);
  if ( v2 )
    CloseServiceHandle(v2);
  if ( v1 )
    CloseServiceHandle(v1);
  return LastError;
}

```

## disassembly

```asm
0x1800fc150  mov     [rsp+arg_8], rbx
0x1800fc155  mov     [rsp+arg_10], rbp
0x1800fc15a  push    rsi
0x1800fc15b  push    rdi
0x1800fc15c  push    r14
0x1800fc15e  sub     rsp, 40h
0x1800fc162  mov     rax, cs:__security_cookie
0x1800fc169  xor     rax, rsp
0x1800fc16c  mov     [rsp+58h+var_20], rax
0x1800fc171  xor     esi, esi
0x1800fc173  xor     edi, edi
0x1800fc175  xor     ebx, ebx
0x1800fc177  mov     r14, rcx
0x1800fc17a  test    rcx, rcx
0x1800fc17d  jnz     short loc_1800FC18E
0x1800fc17f  mov     ebp, 80004003h
0x1800fc184  mov     edx, 82h
0x1800fc189  jmp     loc_1800FC26F
0x1800fc18e  mov     [rcx], ebx
0x1800fc190  lea     rdx, DatabaseName; "ServicesActive"
0x1800fc197  mov     ebp, 80000000h
0x1800fc19c  xor     ecx, ecx; lpMachineName
0x1800fc19e  mov     r8d, ebp; dwDesiredAccess
0x1800fc1a1  call    cs:__imp_OpenSCManagerW
0x1800fc1a7  mov     rsi, rax
0x1800fc1aa  test    rax, rax
0x1800fc1ad  jnz     short loc_1800FC1B9
0x1800fc1af  mov     edx, 88h
0x1800fc1b4  jmp     loc_1800FC2AB
0x1800fc1b9  mov     r8d, ebp; dwDesiredAccess
0x1800fc1bc  lea     rdx, ?c_szBitsService@@3QB_WB; "BITS"
0x1800fc1c3  mov     rcx, rax; hSCManager
0x1800fc1c6  call    cs:__imp_OpenServiceW
0x1800fc1cc  mov     rdi, rax
0x1800fc1cf  test    rax, rax
0x1800fc1d2  jnz     short loc_1800FC1DE
0x1800fc1d4  mov     edx, 8Eh
0x1800fc1d9  jmp     loc_1800FC2AB
0x1800fc1de  lea     rax, [rsp+58h+cbBufSize]
0x1800fc1e3  mov     [rsp+58h+cbBufSize], ebx
0x1800fc1e7  xor     r9d, r9d; cbBufSize
0x1800fc1ea  mov     qword ptr [rsp+58h+pcbBytesNeeded], rax; int
0x1800fc1ef  xor     r8d, r8d; lpBuffer
0x1800fc1f2  xor     edx, edx; InfoLevel
0x1800fc1f4  mov     rcx, rdi; hService
0x1800fc1f7  call    cs:__imp_QueryServiceStatusEx
0x1800fc1fd  test    eax, eax
0x1800fc1ff  jz      short loc_1800FC20D
0x1800fc201  mov     ebp, 80240FFFh
0x1800fc206  mov     edx, 93h
0x1800fc20b  jmp     short loc_1800FC26F
0x1800fc20d  call    cs:__imp_GetLastError
0x1800fc213  cmp     eax, 7Ah ; 'z'
0x1800fc216  jz      short loc_1800FC224
0x1800fc218  mov     ebp, 8007139Fh
0x1800fc21d  mov     edx, 94h
0x1800fc222  jmp     short loc_1800FC26F
0x1800fc224  mov     r9d, [rsp+58h+cbBufSize]
0x1800fc229  mov     ebp, r9d
0x1800fc22c  test    r9d, r9d
0x1800fc22f  jz      short loc_1800FC28A
0x1800fc231  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800fc238  mov     ecx, r9d; unsigned __int64
0x1800fc23b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800fc240  mov     rbx, rax
0x1800fc243  test    rax, rax
0x1800fc246  jz      short loc_1800FC255
0x1800fc248  mov     r8d, ebp; Size
0x1800fc24b  xor     edx, edx; Val
0x1800fc24d  mov     rcx, rax; void *
0x1800fc250  call    memset
0x1800fc255  mov     rax, rbx
0x1800fc258  neg     rax
0x1800fc25b  sbb     ebp, ebp
0x1800fc25d  not     ebp
0x1800fc25f  and     ebp, 8007000Eh
0x1800fc265  test    rbx, rbx
0x1800fc268  jnz     short loc_1800FC285
0x1800fc26a  mov     edx, 95h; void *
0x1800fc26f  mov     rcx, [rsp+58h]; this
0x1800fc274  lea     r8, aCW1SSrcClientE_82; "C:\\__w\\1\\s\\src\\Client\\Engine\\Age"...
0x1800fc27b  mov     r9d, ebp; char *
0x1800fc27e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fc283  jmp     short loc_1800FC2D2
0x1800fc285  mov     r9d, [rsp+58h+cbBufSize]; cbBufSize
0x1800fc28a  lea     rax, [rsp+58h+cbBufSize]
0x1800fc28f  mov     r8, rbx; lpBuffer
0x1800fc292  xor     edx, edx; InfoLevel
0x1800fc294  mov     qword ptr [rsp+58h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1800fc299  mov     rcx, rdi; hService
0x1800fc29c  call    cs:__imp_QueryServiceStatusEx
0x1800fc2a2  test    eax, eax
0x1800fc2a4  jnz     short loc_1800FC2C0
0x1800fc2a6  mov     edx, 9Bh; void *
0x1800fc2ab  mov     rcx, [rsp+58h]; this
0x1800fc2b0  lea     r8, aCW1SSrcClientE_82; "C:\\__w\\1\\s\\src\\Client\\Engine\\Age"...
0x1800fc2b7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800fc2bc  mov     ebp, eax
0x1800fc2be  jmp     short loc_1800FC2D2
0x1800fc2c0  mov     eax, [rbx+0Ch]
0x1800fc2c3  cmp     eax, 42Ah
0x1800fc2c8  jnz     short loc_1800FC2CD
0x1800fc2ca  mov     eax, [rbx+10h]
0x1800fc2cd  mov     [r14], eax
0x1800fc2d0  xor     ebp, ebp
0x1800fc2d2  test    rbx, rbx
0x1800fc2d5  jz      short loc_1800FC2DF
0x1800fc2d7  mov     rcx, rbx; void *
0x1800fc2da  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800fc2df  test    rdi, rdi
0x1800fc2e2  jz      short loc_1800FC2ED
0x1800fc2e4  mov     rcx, rdi; hSCObject
0x1800fc2e7  call    cs:__imp_CloseServiceHandle
0x1800fc2ed  test    rsi, rsi
0x1800fc2f0  jz      short loc_1800FC2FB
0x1800fc2f2  mov     rcx, rsi; hSCObject
0x1800fc2f5  call    cs:__imp_CloseServiceHandle
0x1800fc2fb  mov     eax, ebp
0x1800fc2fd  mov     rcx, [rsp+58h+var_20]
0x1800fc302  xor     rcx, rsp; StackCookie
0x1800fc305  call    __security_check_cookie
0x1800fc30a  mov     rbx, [rsp+58h+arg_8]
0x1800fc30f  mov     rbp, [rsp+58h+arg_10]
0x1800fc314  add     rsp, 40h
0x1800fc318  pop     r14
0x1800fc31a  pop     rdi
0x1800fc31b  pop     rsi
0x1800fc31c  retn
```
