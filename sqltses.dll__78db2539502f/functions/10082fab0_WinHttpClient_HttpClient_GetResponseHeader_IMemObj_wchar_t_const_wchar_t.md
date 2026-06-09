# WinHttpClient::HttpClient::GetResponseHeader(IMemObj *,wchar_t const *,wchar_t * *)

- ea: `0x10082fab0`
- end: `0x10082fcd5`
- name: `?GetResponseHeader@HttpClient@WinHttpClient@@UEAA?AUHttpOpResult@2@PEAVIMemObj@@PEB_WPEAPEA_W@Z`
- size: `549`
- prototype: `struct WinHttpClient::HttpOpResult __high(struct IMemObj *, const wchar_t *, wchar_t **)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x10082fab0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10082fb96`
- `KERNEL32!GetLastError` at `0x10082fba9`
- `KERNEL32!GetLastError` at `0x10082fbc3`
- `KERNEL32!GetLastError` at `0x10082fc77`
- `KERNEL32!GetLastError` at `0x10082fc8b`
- `KERNEL32!GetLastError` at `0x10082fb96`
- `KERNEL32!GetLastError` at `0x10082fba9`
- `KERNEL32!GetLastError` at `0x10082fbc3`
- `KERNEL32!GetLastError` at `0x10082fc77`
- `KERNEL32!GetLastError` at `0x10082fc8b`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10082fb35`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10082fc0a`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10082fb35`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10082fc0a`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082fc1b`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082fcae`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082fc1b`
- `sqldk!??_V@YAXPEAX@Z` at `0x10082fcae`
- `WININET!HttpQueryInfoW` at `0x10082fb86`
- `WININET!HttpQueryInfoW` at `0x10082fc67`
- `WININET!HttpQueryInfoW` at `0x10082fb86`
- `WININET!HttpQueryInfoW` at `0x10082fc67`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x10082fb68`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x10082fc4b`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x10082fb68`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x10082fc4b`

## string_xrefs

- `0x10082fb22`: `Sql\Ntdbms\msql\security\src\httpclient.cpp`
- `0x10082fbf9`: `Sql\Ntdbms\msql\security\src\httpclient.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WinHttpClient::HttpClient::GetResponseHeader(
        __int64 a1,
        __int64 a2,
        struct IMemObj *a3,
        const wchar_t *a4,
        _QWORD *a5)
{
  __int64 v9; // rax
  unsigned __int64 v10; // r12
  unsigned __int64 v11; // rax
  void *v12; // rsi
  BOOL v13; // eax
  bool v14; // di
  void *v15; // rcx
  unsigned __int64 v16; // rax
  void *v17; // r14
  DWORD dwBufferLength; // [rsp+30h] [rbp-48h] BYREF
  void *v20; // [rsp+38h] [rbp-40h]
  __int64 v21; // [rsp+40h] [rbp-38h]

  v21 = -2;
  v9 = -1;
  do
    ++v9;
  while ( a4[v9] );
  dwBufferLength = 2 * (v9 + 1);
  v10 = (unsigned int)(v9 + 1);
  v11 = 2 * v10;
  if ( !is_mul_ok(v10, 2u) )
    v11 = -1;
  v12 = operator new[](v11, a3, 1, "Sql\\Ntdbms\\msql\\security\\src\\httpclient.cpp", 524, 6u);
  v20 = v12;
  if ( !v12 )
  {
    *(_QWORD *)a2 = 16;
LABEL_22:
    v15 = 0;
    goto LABEL_23;
  }
  memset(v12, 0, dwBufferLength);
  wcscpy_s((wchar_t *)v12, v10, a4);
  v13 = HttpQueryInfoW(*(HINTERNET *)(a1 + 8), 0xFFFFu, v12, &dwBufferLength, 0);
  v14 = v13;
  if ( v13 || GetLastError() != 12150 )
  {
    if ( v14 )
      goto LABEL_21;
    if ( GetLastError() != 122 )
    {
      *(_DWORD *)a2 = 19;
      *(_DWORD *)(a2 + 4) = GetLastError();
      v15 = v12;
      goto LABEL_23;
    }
    v16 = 2 * ((unsigned __int64)dwBufferLength >> 1);
    if ( !is_mul_ok((unsigned __int64)dwBufferLength >> 1, 2u) )
      v16 = -1;
    v17 = operator new[](v16, a3, 1, "Sql\\Ntdbms\\msql\\security\\src\\httpclient.cpp", 554, 6u);
    if ( v12 != v17 )
      operator delete[](v12);
    v12 = v17;
    v20 = v17;
    if ( !v17 )
    {
      *(_QWORD *)a2 = 17;
      goto LABEL_22;
    }
    memset(v17, 0, dwBufferLength);
    wcscpy_s((wchar_t *)v17, v10, a4);
    if ( HttpQueryInfoW(*(HINTERNET *)(a1 + 8), 0xFFFFu, v17, &dwBufferLength, 0) )
    {
LABEL_21:
      v20 = 0;
      *a5 = v12;
      *(_QWORD *)a2 = 0;
      goto LABEL_22;
    }
    *(_DWORD *)a2 = 15;
    *(_DWORD *)(a2 + 4) = GetLastError();
    v15 = v17;
  }
  else
  {
    *(_DWORD *)a2 = 18;
    *(_DWORD *)(a2 + 4) = GetLastError();
    v15 = v12;
  }
LABEL_23:
  operator delete[](v15);
  return a2;
}

```

## disassembly

```asm
0x10082fab0  mov     rax, rsp
0x10082fab3  push    rdi
0x10082fab4  push    r12
0x10082fab6  push    r13
0x10082fab8  push    r14
0x10082faba  push    r15
0x10082fabc  sub     rsp, 50h
0x10082fac0  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x10082fac8  mov     [rax+8], rbx
0x10082facc  mov     [rax+10h], rbp
0x10082fad0  mov     [rax+18h], rsi
0x10082fad4  mov     r15, r9
0x10082fad7  mov     r14, r8
0x10082fada  mov     rbx, rdx
0x10082fadd  mov     r13, rcx
0x10082fae0  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x10082fae7  mov     rax, rdi
0x10082faea  nop     word ptr [rax+rax+00h]
0x10082faf0  lea     rax, [rax+1]
0x10082faf4  cmp     word ptr [r9+rax*2], 0
0x10082fafa  jnz     short loc_10082FAF0
0x10082fafc  lea     ecx, [rax+1]
0x10082faff  lea     eax, [rcx+rcx]
0x10082fb02  mov     [rsp+78h+dwBufferLength], eax
0x10082fb06  mov     r12d, ecx
0x10082fb09  mov     eax, 2
0x10082fb0e  mul     r12
0x10082fb11  cmovo   rax, rdi
0x10082fb15  mov     [rsp+78h+var_50], 6
0x10082fb1a  mov     dword ptr [rsp+78h+lpdwIndex], 20Ch
0x10082fb22  lea     r9, aSqlNtdbmsMsqlS_1; "Sql\\Ntdbms\\msql\\security\\src\\httpc"...
0x10082fb29  mov     r8d, 1
0x10082fb2f  mov     rdx, r14
0x10082fb32  mov     rcx, rax
0x10082fb35  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10082fb3b  mov     rsi, rax
0x10082fb3e  mov     [rsp+78h+var_40], rax
0x10082fb43  test    rax, rax
0x10082fb46  jnz     short loc_10082FB54
0x10082fb48  mov     qword ptr [rbx], 10h
0x10082fb4f  jmp     loc_10082FCAC
0x10082fb54  mov     ecx, [rsp+78h+dwBufferLength]
0x10082fb58  mov     rdi, rsi
0x10082fb5b  xor     eax, eax
0x10082fb5d  rep stosb
0x10082fb5f  mov     r8, r15; Source
0x10082fb62  mov     rdx, r12; SizeInWords
0x10082fb65  mov     rcx, rsi; Destination
0x10082fb68  call    cs:__imp_wcscpy_s
0x10082fb6e  xor     ebp, ebp
0x10082fb70  mov     [rsp+78h+lpdwIndex], rbp; lpdwIndex
0x10082fb75  lea     r9, [rsp+78h+dwBufferLength]; lpdwBufferLength
0x10082fb7a  mov     r8, rsi; lpBuffer
0x10082fb7d  mov     edx, 0FFFFh; dwInfoLevel
0x10082fb82  mov     rcx, [r13+8]; hRequest
0x10082fb86  call    cs:__imp_HttpQueryInfoW
0x10082fb8c  test    eax, eax
0x10082fb8e  setnz   dil
0x10082fb92  test    eax, eax
0x10082fb94  jnz     short loc_10082FBBA
0x10082fb96  call    cs:__imp_GetLastError
0x10082fb9c  cmp     eax, 2F76h
0x10082fba1  jnz     short loc_10082FBBA
0x10082fba3  mov     dword ptr [rbx], 12h
0x10082fba9  call    cs:__imp_GetLastError
0x10082fbaf  mov     [rbx+4], eax
0x10082fbb2  mov     rcx, rsi
0x10082fbb5  jmp     loc_10082FCAE
0x10082fbba  test    dil, dil
0x10082fbbd  jnz     loc_10082FC99
0x10082fbc3  call    cs:__imp_GetLastError
0x10082fbc9  cmp     eax, 7Ah ; 'z'
0x10082fbcc  jnz     loc_10082FC85
0x10082fbd2  mov     ecx, [rsp+78h+dwBufferLength]
0x10082fbd6  shr     rcx, 1
0x10082fbd9  mov     eax, 2
0x10082fbde  mul     rcx
0x10082fbe1  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10082fbe8  cmovo   rax, rcx
0x10082fbec  mov     [rsp+78h+var_50], 6
0x10082fbf1  mov     dword ptr [rsp+78h+lpdwIndex], 22Ah
0x10082fbf9  lea     r9, aSqlNtdbmsMsqlS_1; "Sql\\Ntdbms\\msql\\security\\src\\httpc"...
0x10082fc00  lea     r8d, [rcx+2]
0x10082fc04  mov     rdx, r14
0x10082fc07  mov     rcx, rax
0x10082fc0a  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10082fc10  mov     r14, rax
0x10082fc13  cmp     rsi, rax
0x10082fc16  jz      short loc_10082FC21
0x10082fc18  mov     rcx, rsi
0x10082fc1b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10082fc21  mov     rsi, r14
0x10082fc24  mov     [rsp+78h+var_40], r14
0x10082fc29  test    r14, r14
0x10082fc2c  jnz     short loc_10082FC37
0x10082fc2e  mov     qword ptr [rbx], 11h
0x10082fc35  jmp     short loc_10082FCAC
0x10082fc37  mov     ecx, [rsp+78h+dwBufferLength]
0x10082fc3b  mov     rdi, r14
0x10082fc3e  xor     eax, eax
0x10082fc40  rep stosb
0x10082fc42  mov     r8, r15; Source
0x10082fc45  mov     rdx, r12; SizeInWords
0x10082fc48  mov     rcx, r14; Destination
0x10082fc4b  call    cs:__imp_wcscpy_s
0x10082fc51  mov     [rsp+78h+lpdwIndex], rbp; lpdwIndex
0x10082fc56  lea     r9, [rsp+78h+dwBufferLength]; lpdwBufferLength
0x10082fc5b  mov     r8, r14; lpBuffer
0x10082fc5e  mov     edx, 0FFFFh; dwInfoLevel
0x10082fc63  mov     rcx, [r13+8]; hRequest
0x10082fc67  call    cs:__imp_HttpQueryInfoW
0x10082fc6d  test    eax, eax
0x10082fc6f  jnz     short loc_10082FC99
0x10082fc71  mov     dword ptr [rbx], 0Fh
0x10082fc77  call    cs:__imp_GetLastError
0x10082fc7d  mov     [rbx+4], eax
0x10082fc80  mov     rcx, r14
0x10082fc83  jmp     short loc_10082FCAE
0x10082fc85  mov     dword ptr [rbx], 13h
0x10082fc8b  call    cs:__imp_GetLastError
0x10082fc91  mov     [rbx+4], eax
0x10082fc94  mov     rcx, rsi
0x10082fc97  jmp     short loc_10082FCAE
0x10082fc99  mov     [rsp+78h+var_40], rbp
0x10082fc9e  mov     rax, [rsp+78h+arg_20]
0x10082fca6  mov     [rax], rsi
0x10082fca9  mov     [rbx], rbp
0x10082fcac  xor     ecx, ecx
0x10082fcae  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10082fcb4  mov     rax, rbx
0x10082fcb7  lea     r11, [rsp+78h+var_28]
0x10082fcbc  mov     rbx, [r11+30h]
0x10082fcc0  mov     rbp, [r11+38h]
0x10082fcc4  mov     rsi, [r11+40h]
0x10082fcc8  mov     rsp, r11
0x10082fccb  pop     r15
0x10082fccd  pop     r14
0x10082fccf  pop     r13
0x10082fcd1  pop     r12
0x10082fcd3  pop     rdi
0x10082fcd4  retn
```
