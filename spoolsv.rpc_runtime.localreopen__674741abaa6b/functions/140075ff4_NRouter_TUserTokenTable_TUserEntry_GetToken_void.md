# NRouter::TUserTokenTable::TUserEntry::GetToken(void * *)

- ea: `0x140075ff4`
- end: `0x140076109`
- name: `?GetToken@TUserEntry@TUserTokenTable@NRouter@@QEAAJPEAPEAX@Z`
- size: `277`
- prototype: `int(NRouter::TUserTokenTable::TUserEntry *__hidden this, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000fd70`
- `0x140075f0c`

## callees

- `0x1400087c8`
- `0x14000a724`
- `0x140015378`
- `0x140075ff4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x140076048`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x140076090`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x140076048`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x140076090`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400760b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400760cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400760b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400760cd`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x14007606e`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x14007606e`

## string_xrefs

- `0x1400760ea`: `NRouter::TUserTokenTable::TUserEntry::GetToken`

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
0x140075ff4  mov     [rsp+arg_0], rbx
0x140075ff9  mov     [rsp+arg_10], rsi
0x140075ffe  push    rdi
0x140075fff  sub     rsp, 20h
0x140076003  mov     [rsp+28h+Token], 0
0x14007600c  mov     rdi, rdx
0x14007600f  test    rdx, rdx
0x140076012  jnz     short loc_14007601E
0x140076014  mov     ebx, 80070057h
0x140076019  jmp     loc_1400760F6
0x14007601e  mov     qword ptr [rdx], 0
0x140076025  mov     rax, [rcx+30h]
0x140076029  lea     rcx, [rsp+28h+Token]; TokenHandle
0x14007602e  mov     rsi, [rax+10h]
0x140076032  call    ?GetThreadToken@@YAJPEAPEAX@Z; GetThreadToken(void * *)
0x140076037  mov     ebx, eax
0x140076039  test    eax, eax
0x14007603b  jns     short loc_140076043
0x14007603d  cmp     ax, 3F0h
0x140076041  jnz     short loc_1400760AB
0x140076043  mov     rdx, rsi; Token
0x140076046  xor     ecx, ecx; Thread
0x140076048  call    cs:__imp_SetThreadToken
0x14007604f  nop     dword ptr [rax+rax+00h]
0x140076054  test    eax, eax
0x140076056  jnz     short loc_140076063
0x140076058  call    GetLastErrorAsHResult
0x14007605d  mov     ebx, eax
0x14007605f  test    eax, eax
0x140076061  js      short loc_140076089
0x140076063  mov     r8, rdi; DuplicateTokenHandle
0x140076066  mov     edx, 2; ImpersonationLevel
0x14007606b  mov     rcx, rsi; ExistingTokenHandle
0x14007606e  call    cs:__imp_DuplicateToken
0x140076075  nop     dword ptr [rax+rax+00h]
0x14007607a  test    eax, eax
0x14007607c  jz      short loc_140076082
0x14007607e  xor     ebx, ebx
0x140076080  jmp     short loc_140076089
0x140076082  call    GetLastErrorAsHResult
0x140076087  mov     ebx, eax
0x140076089  mov     rdx, [rsp+28h+Token]; Token
0x14007608e  xor     ecx, ecx; Thread
0x140076090  call    cs:__imp_SetThreadToken
0x140076097  nop     dword ptr [rax+rax+00h]
0x14007609c  test    eax, eax
0x14007609e  jnz     short loc_1400760AB
0x1400760a0  test    ebx, ebx
0x1400760a2  js      short loc_1400760AB
0x1400760a4  call    GetLastErrorAsHResult
0x1400760a9  mov     ebx, eax
0x1400760ab  mov     rcx, [rsp+28h+Token]; hObject
0x1400760b0  test    rcx, rcx
0x1400760b3  jz      short loc_1400760C1
0x1400760b5  call    cs:__imp_CloseHandle
0x1400760bc  nop     dword ptr [rax+rax+00h]
0x1400760c1  test    ebx, ebx
0x1400760c3  jns     short loc_1400760F6
0x1400760c5  mov     rcx, [rdi]; hObject
0x1400760c8  test    rcx, rcx
0x1400760cb  jz      short loc_1400760F6
0x1400760cd  call    cs:__imp_CloseHandle
0x1400760d4  nop     dword ptr [rax+rax+00h]
0x1400760d9  mov     r8d, ebx
0x1400760dc  mov     qword ptr [rdi], 0
0x1400760e3  lea     rdx, aFailedErrorHr0_1; "Failed.  Error hr: 0x%x."
0x1400760ea  lea     rcx, aNrouterTuserto_5; "NRouter::TUserTokenTable::TUserEntry::G"...
0x1400760f1  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400760f6  mov     rsi, [rsp+28h+arg_10]
0x1400760fb  mov     eax, ebx
0x1400760fd  mov     rbx, [rsp+28h+arg_0]
0x140076102  add     rsp, 20h
0x140076106  pop     rdi
0x140076107  retn
```
