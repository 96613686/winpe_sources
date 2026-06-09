# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000b7e8`
- end: `0x18000ba6b`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `643`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180004b78`
- `0x180004f48`

## callees

- `0x180001e40`
- `0x180007234`
- `0x18000a824`
- `0x18000a844`
- `0x18000b288`
- `0x18000b7e8`
- `0x18000c568`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b87f`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b901`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b87f`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b901`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b9c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b9c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b8cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b944`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b955`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b96a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b98f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b9b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b8cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b944`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b955`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b96a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b98f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b9b1`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v5; // rdx
  __int64 v7; // r9
  WCHAR *v8; // rcx
  HANDLE v9; // rax
  void *v10; // rbx
  int ValueFromSemaphore; // eax
  unsigned int LastError; // edi
  unsigned int v13; // r8d
  const char *v14; // r9
  HANDLE v16; // rax
  unsigned int v17; // r8d
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
  unsigned int v32; // r8d
  const char *v33; // r9
  int v34; // [rsp+20h] [rbp-E0h] BYREF
  int v35[3]; // [rsp+24h] [rbp-DCh] BYREF
  WCHAR Name[264]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v4 = Name;
  *a3 = 0;
  v5 = 260;
  v7 = 2147483646;
  do
  {
    if ( !v7 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v7;
    --v5;
  }
  while ( v5 );
  v8 = v4 - 1;
  if ( v5 )
    v8 = v4;
  *v8 = 0;
  StringCchCatW(Name, 0x104u, L"_p0");
  v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v10 = v9;
  if ( !v9 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v32, v33);
    return 0;
  }
  v35[0] = 0;
  v34 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v35);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v34);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v13, v14);
    return LastError;
  }
  StringCchCatW(Name, 0x104u, L"h");
  v16 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v19 = v16;
  if ( !v16 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v17, v18);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    return LastError;
  }
  v20 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v16, &v34);
  v21 = v20;
  if ( v20 >= 0 )
  {
    if ( !CloseHandle(v19) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    *a3 = v35[0] | (unsigned __int64)((__int64)v34 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v20, v34);
  if ( !CloseHandle(v19) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v22, v23);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  return v21;
}

```

## disassembly

```asm
0x18000b7e8  push    rbp
0x18000b7ea  push    rbx
0x18000b7eb  push    rsi
0x18000b7ec  push    rdi
0x18000b7ed  push    r14
0x18000b7ef  push    r15
0x18000b7f1  lea     rbp, [rsp-158h]
0x18000b7f9  sub     rsp, 258h
0x18000b800  mov     rax, cs:__security_cookie
0x18000b807  xor     rax, rsp
0x18000b80a  mov     [rbp+180h+var_40], rax
0x18000b811  xor     r15d, r15d
0x18000b814  lea     rax, [rsp+280h+Name]
0x18000b819  mov     esi, 104h
0x18000b81e  mov     [r8], r15
0x18000b821  mov     edx, esi
0x18000b823  mov     r14, r8
0x18000b826  mov     r9d, 7FFFFFFEh
0x18000b82c  test    r9, r9
0x18000b82f  jz      short loc_18000B850
0x18000b831  movzx   r8d, word ptr [rcx]
0x18000b835  test    r8w, r8w
0x18000b839  jz      short loc_18000B850
0x18000b83b  mov     [rax], r8w
0x18000b83f  add     rcx, 2
0x18000b843  add     rax, 2
0x18000b847  dec     r9
0x18000b84a  sub     rdx, 1
0x18000b84e  jnz     short loc_18000B82C
0x18000b850  test    rdx, rdx
0x18000b853  lea     rcx, [rax-2]
0x18000b857  lea     r8, aP0; "_p0"
0x18000b85e  mov     rdx, rsi; unsigned __int64
0x18000b861  cmovnz  rcx, rax
0x18000b865  mov     [rcx], r15w
0x18000b869  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18000b86e  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000b873  lea     r8, [rsp+280h+Name]; lpName
0x18000b878  xor     edx, edx; bInheritHandle
0x18000b87a  mov     ecx, 1F0003h; dwDesiredAccess
0x18000b87f  call    cs:__imp_OpenSemaphoreW
0x18000b885  mov     rbx, rax
0x18000b888  test    rax, rax
0x18000b88b  jz      loc_18000B9C0
0x18000b891  lea     rdx, [rsp+280h+var_25C]; int *
0x18000b896  mov     [rsp+280h+var_25C], r15d
0x18000b89b  mov     rcx, rax; hHandle
0x18000b89e  mov     [rsp+280h+var_260], r15d; int
0x18000b8a3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000b8a8  mov     edi, eax
0x18000b8aa  test    eax, eax
0x18000b8ac  jns     short loc_18000B8E1
0x18000b8ae  mov     rcx, [rbp+188h]; this
0x18000b8b5  lea     r8, aWil; "wil"
0x18000b8bc  mov     r9d, eax; char *
0x18000b8bf  mov     edx, 0D6h; void *
0x18000b8c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b8c9  mov     rcx, rbx; hObject
0x18000b8cc  call    cs:__imp_CloseHandle
0x18000b8d2  test    eax, eax
0x18000b8d4  jz      loc_18000BA35
0x18000b8da  mov     eax, edi
0x18000b8dc  jmp     loc_18000B9E0
0x18000b8e1  lea     r8, asc_18001D3A8; "h"
0x18000b8e8  mov     rdx, rsi; unsigned __int64
0x18000b8eb  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18000b8f0  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000b8f5  lea     r8, [rsp+280h+Name]; lpName
0x18000b8fa  xor     edx, edx; bInheritHandle
0x18000b8fc  mov     ecx, 1F0003h; dwDesiredAccess
0x18000b901  call    cs:__imp_OpenSemaphoreW
0x18000b907  mov     rdi, rax
0x18000b90a  test    rax, rax
0x18000b90d  jz      loc_18000B99B
0x18000b913  lea     rdx, [rsp+280h+var_260]; int *
0x18000b918  mov     rcx, rax; hHandle
0x18000b91b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000b920  mov     esi, eax
0x18000b922  test    eax, eax
0x18000b924  jns     short loc_18000B967
0x18000b926  mov     rcx, [rbp+188h]; this
0x18000b92d  lea     r8, aWil; "wil"
0x18000b934  mov     r9d, eax; char *
0x18000b937  mov     edx, 0DEh; void *
0x18000b93c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b941  mov     rcx, rdi; hObject
0x18000b944  call    cs:__imp_CloseHandle
0x18000b94a  test    eax, eax
0x18000b94c  jz      loc_18000BA47
0x18000b952  mov     rcx, rbx; hObject
0x18000b955  call    cs:__imp_CloseHandle
0x18000b95b  test    eax, eax
0x18000b95d  jz      loc_18000BA59
0x18000b963  mov     eax, esi
0x18000b965  jmp     short loc_18000B9E0
0x18000b967  mov     rcx, rdi; hObject
0x18000b96a  call    cs:__imp_CloseHandle
0x18000b970  test    eax, eax
0x18000b972  jz      loc_18000B9FF
0x18000b978  movsxd  rax, [rsp+280h+var_25C]
0x18000b97d  movsxd  rcx, [rsp+280h+var_260]
0x18000b982  shl     rcx, 1Fh
0x18000b986  or      rcx, rax
0x18000b989  mov     [r14], rcx
0x18000b98c  mov     rcx, rbx; hObject
0x18000b98f  call    cs:__imp_CloseHandle
0x18000b995  test    eax, eax
0x18000b997  jz      short loc_18000BA11
0x18000b999  jmp     short loc_18000B9CB
0x18000b99b  mov     rcx, [rbp+188h]; this
0x18000b9a2  mov     edx, 0DCh; void *
0x18000b9a7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b9ac  mov     rcx, rbx; hObject
0x18000b9af  mov     edi, eax
0x18000b9b1  call    cs:__imp_CloseHandle
0x18000b9b7  test    eax, eax
0x18000b9b9  jz      short loc_18000BA23
0x18000b9bb  jmp     loc_18000B8DA
0x18000b9c0  call    cs:__imp_GetLastError
0x18000b9c6  cmp     eax, 2
0x18000b9c9  jnz     short loc_18000B9CF
0x18000b9cb  xor     eax, eax
0x18000b9cd  jmp     short loc_18000B9E0
0x18000b9cf  mov     rcx, [rbp+188h]; this
0x18000b9d6  mov     edx, 0D0h; void *
0x18000b9db  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b9e0  mov     rcx, [rbp+180h+var_40]
0x18000b9e7  xor     rcx, rsp; StackCookie
0x18000b9ea  call    __security_check_cookie
0x18000b9ef  add     rsp, 258h
0x18000b9f6  pop     r15
0x18000b9f8  pop     r14
0x18000b9fa  pop     rdi
0x18000b9fb  pop     rsi
0x18000b9fc  pop     rbx
0x18000b9fd  pop     rbp
0x18000b9fe  retn
0x18000b9ff  mov     rcx, [rbp+188h]; this
0x18000ba06  mov     edx, 0A0Bh; void *
0x18000ba0b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ba11  mov     rcx, [rbp+188h]; this
0x18000ba18  mov     edx, 0A0Bh; void *
0x18000ba1d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ba23  mov     rcx, [rbp+188h]; this
0x18000ba2a  mov     edx, 0A0Bh; void *
0x18000ba2f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ba35  mov     rcx, [rbp+188h]; this
0x18000ba3c  mov     edx, 0A0Bh; void *
0x18000ba41  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ba47  mov     rcx, [rbp+188h]; this
0x18000ba4e  mov     edx, 0A0Bh; void *
0x18000ba53  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ba59  mov     rcx, [rbp+188h]; this
0x18000ba60  mov     edx, 0A0Bh; void *
0x18000ba65  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
