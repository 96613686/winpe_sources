# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000d324`
- end: `0x18000d5b3`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `655`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000900c`
- `0x1800093dc`

## callees

- `0x1800029d0`
- `0x18000a968`
- `0x18000caf0`
- `0x18000cb10`
- `0x18000ce58`
- `0x18000d324`
- `0x18001141c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d501`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d501`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000d3b8`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000d434`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000d3b8`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000d434`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d405`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d477`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d488`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d4a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d4c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d4f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d405`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d477`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d488`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d4a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d4c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d4f2`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  unsigned __int64 v6; // rdx
  __int64 v7; // r9
  WCHAR *v8; // rcx
  HANDLE v9; // rax
  void *v10; // rbx
  int ValueFromSemaphore; // eax
  unsigned __int64 v12; // rdx
  unsigned int LastError; // edi
  unsigned int v14; // r8d
  const char *v15; // r9
  HANDLE v17; // rax
  const char *v18; // r9
  void *v19; // rdi
  int v20; // eax
  unsigned int v21; // esi
  unsigned int v22; // r8d
  const char *v23; // r9
  unsigned int v24; // r8d
  const char *v25; // r9
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  unsigned int v30; // r8d
  const char *v31; // r9
  const char *v32; // r9
  int v33; // [rsp+20h] [rbp-E0h] BYREF
  int v34[3]; // [rsp+24h] [rbp-DCh] BYREF
  WCHAR Name[264]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v4 = Name;
  *a3 = 0;
  v6 = 260;
  v7 = 2147483646;
  do
  {
    if ( !v7 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v7;
    --v6;
  }
  while ( v6 );
  v8 = v4 - 1;
  if ( v6 )
    v8 = v4;
  *v8 = 0;
  StringCchCatW(Name, v6, L"_p0");
  v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v10 = v9;
  if ( !v9 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v32);
    return 0;
  }
  v34[0] = 0;
  v33 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v34);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v33);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v19 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v18);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    return LastError;
  }
  v20 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v33);
  v21 = v20;
  if ( v20 >= 0 )
  {
    if ( !CloseHandle(v19) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    *a3 = v34[0] | (unsigned __int64)((__int64)v33 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v20, v33);
  if ( !CloseHandle(v19) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v22, v23);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  return v21;
}

```

## disassembly

```asm
0x18000d324  push    rbp
0x18000d326  push    rbx
0x18000d327  push    rsi
0x18000d328  push    rdi
0x18000d329  push    r14
0x18000d32b  push    r15
0x18000d32d  lea     rbp, [rsp-158h]
0x18000d335  sub     rsp, 258h
0x18000d33c  mov     rax, cs:__security_cookie
0x18000d343  xor     rax, rsp
0x18000d346  mov     [rbp+180h+var_40], rax
0x18000d34d  xor     r15d, r15d
0x18000d350  lea     rax, [rsp+280h+Name]
0x18000d355  mov     [r8], r15
0x18000d358  mov     r14, r8
0x18000d35b  mov     edx, 104h
0x18000d360  mov     r9d, 7FFFFFFEh
0x18000d366  test    r9, r9
0x18000d369  jz      short loc_18000D38A
0x18000d36b  movzx   r8d, word ptr [rcx]
0x18000d36f  test    r8w, r8w
0x18000d373  jz      short loc_18000D38A
0x18000d375  mov     [rax], r8w
0x18000d379  add     rcx, 2
0x18000d37d  add     rax, 2
0x18000d381  dec     r9
0x18000d384  sub     rdx, 1; unsigned __int64
0x18000d388  jnz     short loc_18000D366
0x18000d38a  test    rdx, rdx
0x18000d38d  lea     rcx, [rax-2]
0x18000d391  lea     r8, aP0; "_p0"
0x18000d398  cmovnz  rcx, rax
0x18000d39c  mov     [rcx], r15w
0x18000d3a0  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18000d3a5  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000d3aa  mov     esi, 1F0003h
0x18000d3af  lea     r8, [rsp+280h+Name]; lpName
0x18000d3b4  mov     ecx, esi; dwDesiredAccess
0x18000d3b6  xor     edx, edx; bInheritHandle
0x18000d3b8  call    cs:__imp_OpenSemaphoreW
0x18000d3be  mov     rbx, rax
0x18000d3c1  test    rax, rax
0x18000d3c4  jz      loc_18000D501
0x18000d3ca  lea     rdx, [rsp+280h+var_25C]; int *
0x18000d3cf  mov     [rsp+280h+var_25C], r15d
0x18000d3d4  mov     rcx, rax; hHandle
0x18000d3d7  mov     [rsp+280h+var_260], r15d; int
0x18000d3dc  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000d3e1  mov     edi, eax
0x18000d3e3  test    eax, eax
0x18000d3e5  jns     short loc_18000D41A
0x18000d3e7  mov     rcx, [rbp+188h]; this
0x18000d3ee  lea     r8, aWil; "wil"
0x18000d3f5  mov     r9d, eax; char *
0x18000d3f8  mov     edx, 0D6h; void *
0x18000d3fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d402  mov     rcx, rbx; hObject
0x18000d405  call    cs:__imp_CloseHandle
0x18000d40b  test    eax, eax
0x18000d40d  jz      loc_18000D57D
0x18000d413  mov     eax, edi
0x18000d415  jmp     loc_18000D528
0x18000d41a  lea     r8, asc_180039938; "h"
0x18000d421  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18000d426  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000d42b  lea     r8, [rsp+280h+Name]; lpName
0x18000d430  xor     edx, edx; bInheritHandle
0x18000d432  mov     ecx, esi; dwDesiredAccess
0x18000d434  call    cs:__imp_OpenSemaphoreW
0x18000d43a  mov     rdi, rax
0x18000d43d  test    rax, rax
0x18000d440  jz      loc_18000D4D5
0x18000d446  lea     rdx, [rsp+280h+var_260]; int *
0x18000d44b  mov     rcx, rax; hHandle
0x18000d44e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000d453  mov     esi, eax
0x18000d455  test    eax, eax
0x18000d457  jns     short loc_18000D49D
0x18000d459  mov     rcx, [rbp+188h]; this
0x18000d460  lea     r8, aWil; "wil"
0x18000d467  mov     r9d, eax; char *
0x18000d46a  mov     edx, 0DEh; void *
0x18000d46f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d474  mov     rcx, rdi; hObject
0x18000d477  call    cs:__imp_CloseHandle
0x18000d47d  test    eax, eax
0x18000d47f  jz      loc_18000D58F
0x18000d485  mov     rcx, rbx; hObject
0x18000d488  call    cs:__imp_CloseHandle
0x18000d48e  test    eax, eax
0x18000d490  jz      loc_18000D5A1
0x18000d496  mov     eax, esi
0x18000d498  jmp     loc_18000D528
0x18000d49d  mov     rcx, rdi; hObject
0x18000d4a0  call    cs:__imp_CloseHandle
0x18000d4a6  test    eax, eax
0x18000d4a8  jz      loc_18000D547
0x18000d4ae  movsxd  rax, [rsp+280h+var_25C]
0x18000d4b3  movsxd  rcx, [rsp+280h+var_260]
0x18000d4b8  shl     rcx, 1Fh
0x18000d4bc  or      rcx, rax
0x18000d4bf  mov     [r14], rcx
0x18000d4c2  mov     rcx, rbx; hObject
0x18000d4c5  call    cs:__imp_CloseHandle
0x18000d4cb  test    eax, eax
0x18000d4cd  jz      loc_18000D559
0x18000d4d3  jmp     short loc_18000D50C
0x18000d4d5  mov     rcx, [rbp+188h]; this
0x18000d4dc  lea     r8, aWil; "wil"
0x18000d4e3  mov     edx, 0DCh; void *
0x18000d4e8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000d4ed  mov     rcx, rbx; hObject
0x18000d4f0  mov     edi, eax
0x18000d4f2  call    cs:__imp_CloseHandle
0x18000d4f8  test    eax, eax
0x18000d4fa  jz      short loc_18000D56B
0x18000d4fc  jmp     loc_18000D413
0x18000d501  call    cs:__imp_GetLastError
0x18000d507  cmp     eax, 2
0x18000d50a  jnz     short loc_18000D510
0x18000d50c  xor     eax, eax
0x18000d50e  jmp     short loc_18000D528
0x18000d510  mov     rcx, [rbp+188h]; this
0x18000d517  lea     r8, aWil; "wil"
0x18000d51e  mov     edx, 0D0h; void *
0x18000d523  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000d528  mov     rcx, [rbp+180h+var_40]
0x18000d52f  xor     rcx, rsp; StackCookie
0x18000d532  call    __security_check_cookie
0x18000d537  add     rsp, 258h
0x18000d53e  pop     r15
0x18000d540  pop     r14
0x18000d542  pop     rdi
0x18000d543  pop     rsi
0x18000d544  pop     rbx
0x18000d545  pop     rbp
0x18000d546  retn
0x18000d547  mov     rcx, [rbp+188h]; this
0x18000d54e  mov     edx, 0A0Bh; void *
0x18000d553  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000d559  mov     rcx, [rbp+188h]; this
0x18000d560  mov     edx, 0A0Bh; void *
0x18000d565  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000d56b  mov     rcx, [rbp+188h]; this
0x18000d572  mov     edx, 0A0Bh; void *
0x18000d577  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000d57d  mov     rcx, [rbp+188h]; this
0x18000d584  mov     edx, 0A0Bh; void *
0x18000d589  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000d58f  mov     rcx, [rbp+188h]; this
0x18000d596  mov     edx, 0A0Bh; void *
0x18000d59b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000d5a1  mov     rcx, [rbp+188h]; this
0x18000d5a8  mov     edx, 0A0Bh; void *
0x18000d5ad  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
