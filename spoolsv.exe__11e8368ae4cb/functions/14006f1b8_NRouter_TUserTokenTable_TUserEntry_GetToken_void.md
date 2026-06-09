# NRouter::TUserTokenTable::TUserEntry::GetToken(void * *)

- ea: `0x14006f1b8`
- end: `0x14006f2ae`
- name: `?GetToken@TUserEntry@TUserTokenTable@NRouter@@QEAAJPEAPEAX@Z`
- size: `246`
- prototype: `int(NRouter::TUserTokenTable::TUserEntry *__hidden this, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000eb40`
- `0x14006f0f8`

## callees

- `0x140007bdc`
- `0x140009958`
- `0x1400140cc`
- `0x14006f1b8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x14006f20c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x14006f248`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x14006f20c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x14006f248`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006f267`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006f279`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006f267`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006f279`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x14006f22c`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x14006f22c`

## string_xrefs

- `0x14006f290`: `NRouter::TUserTokenTable::TUserEntry::GetToken`

## pseudocode

```c
__int64 __fastcall NRouter::TUserTokenTable::TUserEntry::GetToken(
        NRouter::TUserTokenTable::TUserEntry *this,
        void **a2)
{
  int LastErrorAsHResult; // ebx
  void *v4; // rsi
  int ThreadToken; // eax
  HANDLE Token; // [rsp+38h] [rbp+10h] BYREF

  Token = 0;
  if ( a2 )
  {
    *a2 = 0;
    v4 = *(void **)(*((_QWORD *)this + 6) + 16LL);
    ThreadToken = GetThreadToken(&Token);
    LastErrorAsHResult = ThreadToken;
    if ( ThreadToken >= 0 || (_WORD)ThreadToken == 1008 )
    {
      if ( SetThreadToken(0, v4) || (LastErrorAsHResult = GetLastErrorAsHResult(), LastErrorAsHResult >= 0) )
      {
        if ( DuplicateToken(v4, SecurityImpersonation, a2) )
          LastErrorAsHResult = 0;
        else
          LastErrorAsHResult = GetLastErrorAsHResult();
      }
      if ( !SetThreadToken(0, Token) && LastErrorAsHResult >= 0 )
        LastErrorAsHResult = GetLastErrorAsHResult();
    }
    if ( Token )
      CloseHandle(Token);
    if ( LastErrorAsHResult < 0 && *a2 )
    {
      CloseHandle(*a2);
      *a2 = 0;
      PrvSpoolssTelemetry::WriteDbgTraceError(
        "NRouter::TUserTokenTable::TUserEntry::GetToken",
        L"Failed.  Error hr: 0x%x.",
        (unsigned int)LastErrorAsHResult);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)LastErrorAsHResult;
}

```

## disassembly

```asm
0x14006f1b8  mov     [rsp+arg_0], rbx
0x14006f1bd  mov     [rsp+arg_10], rsi
0x14006f1c2  push    rdi
0x14006f1c3  sub     rsp, 20h
0x14006f1c7  mov     [rsp+28h+Token], 0
0x14006f1d0  mov     rdi, rdx
0x14006f1d3  test    rdx, rdx
0x14006f1d6  jnz     short loc_14006F1E2
0x14006f1d8  mov     ebx, 80070057h
0x14006f1dd  jmp     loc_14006F29C
0x14006f1e2  mov     qword ptr [rdx], 0
0x14006f1e9  mov     rax, [rcx+30h]
0x14006f1ed  lea     rcx, [rsp+28h+Token]; TokenHandle
0x14006f1f2  mov     rsi, [rax+10h]
0x14006f1f6  call    ?GetThreadToken@@YAJPEAPEAX@Z; GetThreadToken(void * *)
0x14006f1fb  mov     ebx, eax
0x14006f1fd  test    eax, eax
0x14006f1ff  jns     short loc_14006F207
0x14006f201  cmp     ax, 3F0h
0x14006f205  jnz     short loc_14006F25D
0x14006f207  mov     rdx, rsi; Token
0x14006f20a  xor     ecx, ecx; Thread
0x14006f20c  call    cs:__imp_SetThreadToken
0x14006f212  test    eax, eax
0x14006f214  jnz     short loc_14006F221
0x14006f216  call    GetLastErrorAsHResult
0x14006f21b  mov     ebx, eax
0x14006f21d  test    eax, eax
0x14006f21f  js      short loc_14006F241
0x14006f221  mov     r8, rdi; DuplicateTokenHandle
0x14006f224  mov     edx, 2; ImpersonationLevel
0x14006f229  mov     rcx, rsi; ExistingTokenHandle
0x14006f22c  call    cs:__imp_DuplicateToken
0x14006f232  test    eax, eax
0x14006f234  jz      short loc_14006F23A
0x14006f236  xor     ebx, ebx
0x14006f238  jmp     short loc_14006F241
0x14006f23a  call    GetLastErrorAsHResult
0x14006f23f  mov     ebx, eax
0x14006f241  mov     rdx, [rsp+28h+Token]; Token
0x14006f246  xor     ecx, ecx; Thread
0x14006f248  call    cs:__imp_SetThreadToken
0x14006f24e  test    eax, eax
0x14006f250  jnz     short loc_14006F25D
0x14006f252  test    ebx, ebx
0x14006f254  js      short loc_14006F25D
0x14006f256  call    GetLastErrorAsHResult
0x14006f25b  mov     ebx, eax
0x14006f25d  mov     rcx, [rsp+28h+Token]; hObject
0x14006f262  test    rcx, rcx
0x14006f265  jz      short loc_14006F26D
0x14006f267  call    cs:__imp_CloseHandle
0x14006f26d  test    ebx, ebx
0x14006f26f  jns     short loc_14006F29C
0x14006f271  mov     rcx, [rdi]; hObject
0x14006f274  test    rcx, rcx
0x14006f277  jz      short loc_14006F29C
0x14006f279  call    cs:__imp_CloseHandle
0x14006f27f  mov     r8d, ebx
0x14006f282  mov     qword ptr [rdi], 0
0x14006f289  lea     rdx, aFailedErrorHr0_1; "Failed.  Error hr: 0x%x."
0x14006f290  lea     rcx, aNrouterTuserto_5; "NRouter::TUserTokenTable::TUserEntry::G"...
0x14006f297  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14006f29c  mov     rsi, [rsp+28h+arg_10]
0x14006f2a1  mov     eax, ebx
0x14006f2a3  mov     rbx, [rsp+28h+arg_0]
0x14006f2a8  add     rsp, 20h
0x14006f2ac  pop     rdi
0x14006f2ad  retn
```
