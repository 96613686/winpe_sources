# WinHttpClient::HttpClient::Connect(IMemObj *,WinHttpClient::HttpConnectionType,uint,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,char const *,uint,bool)

- ea: `0x10082f490`
- end: `0x10082f769`
- name: `?Connect@HttpClient@WinHttpClient@@UEAA?AUHttpOpResult@2@PEAVIMemObj@@W4HttpConnectionType@2@IPEB_W22222PEBDI_N@Z`
- size: `729`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path, service_task`

## callees

- `0x10082f490`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10082f50f`
- `KERNEL32!GetLastError` at `0x10082f5bd`
- `KERNEL32!GetLastError` at `0x10082f5dd`
- `KERNEL32!GetLastError` at `0x10082f631`
- `KERNEL32!GetLastError` at `0x10082f66b`
- `KERNEL32!GetLastError` at `0x10082f6f5`
- `KERNEL32!GetLastError` at `0x10082f730`
- `KERNEL32!GetLastError` at `0x10082f50f`
- `KERNEL32!GetLastError` at `0x10082f5bd`
- `KERNEL32!GetLastError` at `0x10082f5dd`
- `KERNEL32!GetLastError` at `0x10082f631`
- `KERNEL32!GetLastError` at `0x10082f66b`
- `KERNEL32!GetLastError` at `0x10082f6f5`
- `KERNEL32!GetLastError` at `0x10082f730`
- `WININET!InternetOpenW` at `0x10082f4f7`
- `WININET!InternetOpenW` at `0x10082f4f7`
- `WININET!InternetConnectW` at `0x10082f5a8`
- `WININET!InternetConnectW` at `0x10082f5a8`
- `WININET!InternetAttemptConnect` at `0x10082f5cd`
- `WININET!InternetAttemptConnect` at `0x10082f5cd`
- `WININET!InternetSetOptionW` at `0x10082f720`
- `WININET!InternetSetOptionW` at `0x10082f720`
- `WININET!HttpSendRequestW` at `0x10082f6eb`
- `WININET!HttpSendRequestW` at `0x10082f6eb`
- `WININET!HttpAddRequestHeadersW` at `0x10082f65b`
- `WININET!HttpAddRequestHeadersW` at `0x10082f65b`
- `WININET!HttpOpenRequestW` at `0x10082f61c`
- `WININET!HttpOpenRequestW` at `0x10082f61c`
- `WININET!InternetCloseHandle` at `0x10082f4b2`
- `WININET!InternetCloseHandle` at `0x10082f4c5`
- `WININET!InternetCloseHandle` at `0x10082f4d8`
- `WININET!InternetCloseHandle` at `0x10082f4b2`
- `WININET!InternetCloseHandle` at `0x10082f4c5`
- `WININET!InternetCloseHandle` at `0x10082f4d8`

## pseudocode

```c
_DWORD *__fastcall WinHttpClient::HttpClient::Connect(
        __int64 a1,
        _DWORD *a2,
        __int64 a3,
        int a4,
        int a5,
        const WCHAR *lpszAgent,
        const WCHAR *lpszVerb,
        const WCHAR *lpszServerName,
        const WCHAR *lpszObjectName,
        const WCHAR *a10,
        const WCHAR *lpszHeaders,
        void *a12,
        DWORD a13,
        char a14)
{
  void *v15; // rcx
  void *v18; // rcx
  void *v19; // rcx
  HINTERNET v20; // rax
  void *v21; // r10
  INTERNET_PORT v23; // cx
  DWORD v24; // esi
  int v25; // eax
  HINTERNET v26; // rax
  void *v27; // rax
  char v28; // r14
  __int64 v29; // rax
  BOOL v30; // eax
  DWORD LastError; // eax
  void *v32; // r8

  v15 = *(void **)(a1 + 8);
  if ( v15 )
  {
    InternetCloseHandle(v15);
    *(_QWORD *)(a1 + 8) = 0;
  }
  v18 = *(void **)(a1 + 16);
  if ( v18 )
  {
    InternetCloseHandle(v18);
    *(_QWORD *)(a1 + 16) = 0;
  }
  v19 = *(void **)(a1 + 24);
  if ( v19 )
  {
    InternetCloseHandle(v19);
    *(_QWORD *)(a1 + 24) = 0;
  }
  v20 = InternetOpenW(lpszAgent, 0, 0, 0, 0);
  *(_QWORD *)(a1 + 24) = v20;
  v21 = v20;
  if ( !v20 )
  {
    *a2 = 2;
    a2[1] = GetLastError();
    return a2;
  }
  v23 = a5;
  v24 = -2076179968;
  if ( a5 )
  {
    v25 = -2076179968;
    if ( !a4 )
      v25 = -2067791360;
    v24 = v25;
LABEL_18:
    v26 = InternetConnectW(v21, lpszServerName, v23, 0, 0, 3u, 0x4400000u, 0);
    *(_QWORD *)(a1 + 16) = v26;
    if ( v26 )
    {
      if ( InternetAttemptConnect(0) )
      {
        *a2 = 4;
        a2[1] = GetLastError();
      }
      else
      {
        v27 = HttpOpenRequestW(*(HINTERNET *)(a1 + 16), lpszVerb, lpszObjectName, 0, 0, &lpszAcceptTypes, v24, 0);
        *(_QWORD *)(a1 + 8) = v27;
        if ( v27 )
        {
          if ( !lpszHeaders || HttpAddRequestHeadersW(v27, lpszHeaders, 0xFFFFFFFF, 0x20000000u) )
          {
            v28 = 1;
            if ( !*(_QWORD *)(a1 + 32) )
              v28 = a14;
            while ( 1 )
            {
              if ( a12 )
              {
                v29 = -1;
                do
                  ++v29;
                while ( a10[v29] );
                v30 = HttpSendRequestW(*(HINTERNET *)(a1 + 8), a10, v29, a12, a13);
              }
              else
              {
                v30 = HttpSendRequestW(*(HINTERNET *)(a1 + 8), 0, 0, 0, 0);
              }
              if ( v30 )
                break;
              LastError = GetLastError();
              if ( !v28 || LastError != 12044 )
              {
                *a2 = 7;
                a2[1] = LastError;
                return a2;
              }
              v32 = *(void **)(a1 + 32);
              v28 = 0;
              if ( v32 && !InternetSetOptionW(*(HINTERNET *)(a1 + 8), 0x54u, v32, 0x28u) )
              {
                *a2 = 24;
                a2[1] = GetLastError();
                return a2;
              }
            }
            *(_QWORD *)a2 = 0;
          }
          else
          {
            *a2 = 6;
            a2[1] = GetLastError();
          }
        }
        else
        {
          *a2 = 5;
          a2[1] = GetLastError();
        }
      }
    }
    else
    {
      *a2 = 3;
      a2[1] = GetLastError();
    }
    return a2;
  }
  if ( a4 == 1 )
  {
    v23 = 80;
    goto LABEL_18;
  }
  if ( !a4 )
  {
    v23 = 443;
    v24 = -2067791360;
    goto LABEL_18;
  }
  a2[1] = a4;
  *a2 = 1;
  return a2;
}

```

## disassembly

```asm
0x10082f490  mov     [rsp+arg_18], rbx
0x10082f495  push    rbp
0x10082f496  push    rdi
0x10082f497  push    r12
0x10082f499  sub     rsp, 40h
0x10082f49d  mov     rdi, rcx
0x10082f4a0  xor     r12d, r12d
0x10082f4a3  mov     rcx, [rcx+8]; hInternet
0x10082f4a7  mov     ebp, r9d
0x10082f4aa  mov     rbx, rdx
0x10082f4ad  test    rcx, rcx
0x10082f4b0  jz      short loc_10082F4BC
0x10082f4b2  call    cs:__imp_InternetCloseHandle
0x10082f4b8  mov     [rdi+8], r12
0x10082f4bc  mov     rcx, [rdi+10h]; hInternet
0x10082f4c0  test    rcx, rcx
0x10082f4c3  jz      short loc_10082F4CF
0x10082f4c5  call    cs:__imp_InternetCloseHandle
0x10082f4cb  mov     [rdi+10h], r12
0x10082f4cf  mov     rcx, [rdi+18h]; hInternet
0x10082f4d3  test    rcx, rcx
0x10082f4d6  jz      short loc_10082F4E2
0x10082f4d8  call    cs:__imp_InternetCloseHandle
0x10082f4de  mov     [rdi+18h], r12
0x10082f4e2  mov     rcx, [rsp+58h+lpszAgent]; lpszAgent
0x10082f4ea  xor     r9d, r9d; lpszProxyBypass
0x10082f4ed  xor     r8d, r8d; lpszProxy
0x10082f4f0  mov     [rsp+58h+dwFlags], r12d; dwFlags
0x10082f4f5  xor     edx, edx; dwAccessType
0x10082f4f7  call    cs:__imp_InternetOpenW
0x10082f4fd  mov     [rdi+18h], rax
0x10082f501  mov     r10, rax
0x10082f504  test    rax, rax
0x10082f507  jnz     short loc_10082F529
0x10082f509  mov     dword ptr [rbx], 2
0x10082f50f  call    cs:__imp_GetLastError
0x10082f515  mov     [rbx+4], eax
0x10082f518  mov     rax, rbx
0x10082f51b  mov     rbx, [rsp+58h+arg_18]
0x10082f520  add     rsp, 40h
0x10082f524  pop     r12
0x10082f526  pop     rdi
0x10082f527  pop     rbp
0x10082f528  retn
0x10082f529  mov     ecx, [rsp+58h+arg_20]
0x10082f530  mov     [rsp+58h+arg_0], rsi
0x10082f535  mov     esi, 84400200h
0x10082f53a  mov     [rsp+58h+arg_8], r14
0x10082f53f  test    ecx, ecx
0x10082f541  jnz     short loc_10082F56E
0x10082f543  cmp     ebp, 1
0x10082f546  jnz     short loc_10082F54D
0x10082f548  lea     ecx, [rbp+4Fh]
0x10082f54b  jmp     short loc_10082F57C
0x10082f54d  test    ebp, ebp
0x10082f54f  jnz     short loc_10082F55D
0x10082f551  mov     ecx, 1BBh
0x10082f556  mov     esi, 84C00200h
0x10082f55b  jmp     short loc_10082F57C
0x10082f55d  mov     r14d, 1
0x10082f563  mov     [rbx+4], ebp
0x10082f566  mov     [rbx], r14d
0x10082f569  jmp     loc_10082F74E
0x10082f56e  mov     eax, esi
0x10082f570  test    ebp, ebp
0x10082f572  mov     esi, 84C00200h
0x10082f577  cmovz   eax, esi
0x10082f57a  mov     esi, eax
0x10082f57c  mov     rdx, [rsp+58h+lpszServerName]; lpszServerName
0x10082f584  movzx   r8d, cx; nServerPort
0x10082f588  mov     [rsp+58h+dwContext], r12; dwContext
0x10082f58d  xor     r9d, r9d; lpszUserName
0x10082f590  mov     [rsp+58h+var_28], 4400000h; dwFlags
0x10082f598  mov     rcx, r10; hInternet
0x10082f59b  mov     [rsp+58h+dwService], 3; dwService
0x10082f5a3  mov     qword ptr [rsp+58h+dwFlags], r12; lpszPassword
0x10082f5a8  call    cs:__imp_InternetConnectW
0x10082f5ae  mov     [rdi+10h], rax
0x10082f5b2  test    rax, rax
0x10082f5b5  jnz     short loc_10082F5CB
0x10082f5b7  mov     dword ptr [rbx], 3
0x10082f5bd  call    cs:__imp_GetLastError
0x10082f5c3  mov     [rbx+4], eax
0x10082f5c6  jmp     loc_10082F74E
0x10082f5cb  xor     ecx, ecx; dwReserved
0x10082f5cd  call    cs:__imp_InternetAttemptConnect
0x10082f5d3  test    eax, eax
0x10082f5d5  jz      short loc_10082F5EB
0x10082f5d7  mov     dword ptr [rbx], 4
0x10082f5dd  call    cs:__imp_GetLastError
0x10082f5e3  mov     [rbx+4], eax
0x10082f5e6  jmp     loc_10082F74E
0x10082f5eb  mov     r8, [rsp+58h+lpszObjectName]; lpszObjectName
0x10082f5f3  lea     rax, lpszAcceptTypes
0x10082f5fa  mov     rdx, [rsp+58h+lpszVerb]; lpszVerb
0x10082f602  xor     r9d, r9d; lpszVersion
0x10082f605  mov     rcx, [rdi+10h]; hConnect
0x10082f609  mov     [rsp+58h+dwContext], r12; dwContext
0x10082f60e  mov     [rsp+58h+var_28], esi; dwFlags
0x10082f612  mov     qword ptr [rsp+58h+dwService], rax; lplpszAcceptTypes
0x10082f617  mov     qword ptr [rsp+58h+dwFlags], r12; lpszReferrer
0x10082f61c  call    cs:__imp_HttpOpenRequestW
0x10082f622  mov     [rdi+8], rax
0x10082f626  test    rax, rax
0x10082f629  jnz     short loc_10082F63F
0x10082f62b  mov     dword ptr [rbx], 5
0x10082f631  call    cs:__imp_GetLastError
0x10082f637  mov     [rbx+4], eax
0x10082f63a  jmp     loc_10082F74E
0x10082f63f  mov     rdx, [rsp+58h+lpszHeaders]; lpszHeaders
0x10082f647  test    rdx, rdx
0x10082f64a  jz      short loc_10082F679
0x10082f64c  mov     r9d, 20000000h; dwModifiers
0x10082f652  mov     r8d, 0FFFFFFFFh; dwHeadersLength
0x10082f658  mov     rcx, rax; hRequest
0x10082f65b  call    cs:__imp_HttpAddRequestHeadersW
0x10082f661  test    eax, eax
0x10082f663  jnz     short loc_10082F679
0x10082f665  mov     dword ptr [rbx], 6
0x10082f66b  call    cs:__imp_GetLastError
0x10082f671  mov     [rbx+4], eax
0x10082f674  jmp     loc_10082F74E
0x10082f679  cmp     [rdi+20h], r12
0x10082f67d  mov     r14d, 1
0x10082f683  movzx   eax, [rsp+58h+arg_68]
0x10082f68b  mov     rbp, [rsp+58h+arg_58]
0x10082f693  cmovz   r14d, eax
0x10082f697  mov     rsi, [rsp+58h+arg_48]
0x10082f69f  mov     [rsp+58h+arg_10], r15
0x10082f6a4  mov     r15d, [rsp+58h+arg_60]
0x10082f6ac  nop     dword ptr [rax+00h]
0x10082f6b0  test    rbp, rbp
0x10082f6b3  jz      short loc_10082F6DA
0x10082f6b5  mov     rax, 0FFFFFFFFFFFFFFFFh
0x10082f6bc  nop     dword ptr [rax+00h]
0x10082f6c0  inc     rax
0x10082f6c3  cmp     [rsi+rax*2], r12w
0x10082f6c8  jnz     short loc_10082F6C0
0x10082f6ca  mov     [rsp+58h+dwFlags], r15d
0x10082f6cf  mov     r9, rbp
0x10082f6d2  mov     r8d, eax
0x10082f6d5  mov     rdx, rsi
0x10082f6d8  jmp     short loc_10082F6E7
0x10082f6da  xor     r9d, r9d; lpOptional
0x10082f6dd  mov     [rsp+58h+dwFlags], r12d; dwOptionalLength
0x10082f6e2  xor     r8d, r8d; dwHeadersLength
0x10082f6e5  xor     edx, edx; lpszHeaders
0x10082f6e7  mov     rcx, [rdi+8]; hRequest
0x10082f6eb  call    cs:__imp_HttpSendRequestW
0x10082f6f1  test    eax, eax
0x10082f6f3  jnz     short loc_10082F746
0x10082f6f5  call    cs:__imp_GetLastError
0x10082f6fb  test    r14b, r14b
0x10082f6fe  jz      short loc_10082F73B
0x10082f700  cmp     eax, 2F0Ch
0x10082f705  jnz     short loc_10082F73B
0x10082f707  mov     r8, [rdi+20h]; lpBuffer
0x10082f70b  xor     r14b, r14b
0x10082f70e  test    r8, r8
0x10082f711  jz      short loc_10082F6B0
0x10082f713  mov     rcx, [rdi+8]; hInternet
0x10082f717  mov     edx, 54h ; 'T'; dwOption
0x10082f71c  lea     r9d, [rdx-2Ch]; dwBufferLength
0x10082f720  call    cs:__imp_InternetSetOptionW
0x10082f726  test    eax, eax
0x10082f728  jnz     short loc_10082F6B0
0x10082f72a  mov     dword ptr [rbx], 18h
0x10082f730  call    cs:__imp_GetLastError
0x10082f736  mov     [rbx+4], eax
0x10082f739  jmp     short loc_10082F749
0x10082f73b  mov     dword ptr [rbx], 7
0x10082f741  mov     [rbx+4], eax
0x10082f744  jmp     short loc_10082F749
0x10082f746  mov     [rbx], r12
0x10082f749  mov     r15, [rsp+58h+arg_10]
0x10082f74e  mov     rsi, [rsp+58h+arg_0]
0x10082f753  mov     rax, rbx
0x10082f756  mov     rbx, [rsp+58h+arg_18]
0x10082f75b  mov     r14, [rsp+58h+arg_8]
0x10082f760  add     rsp, 40h
0x10082f764  pop     r12
0x10082f766  pop     rdi
0x10082f767  pop     rbp
0x10082f768  retn
```
