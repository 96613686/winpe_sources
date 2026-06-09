# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18003360c`
- end: `0x180033878`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18002def8`
- `0x18002e29c`

## callees

- `0x1800304d4`
- `0x180032844`
- `0x180032864`
- `0x180033150`
- `0x18003360c`
- `0x18003427c`
- `0x180056e30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800336a0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180033715`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800336a0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180033715`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800337cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800337cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800336e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033751`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033762`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033777`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003379c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800337be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800336e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033751`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033762`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033777`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003379c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800337be`

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
  unsigned int v13; // r8d
  unsigned int LastError; // edi
  __int64 v15; // r8
  const char *v16; // r9
  HANDLE v18; // rax
  unsigned int v19; // r8d
  const char *v20; // r9
  void *v21; // rdi
  int v22; // eax
  unsigned int v23; // r8d
  unsigned int v24; // esi
  __int64 v25; // r8
  const char *v26; // r9
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
  const char *v30; // r9
  __int64 v31; // r8
  const char *v32; // r9
  __int64 v33; // r8
  const char *v34; // r9
  unsigned int v35; // r8d
  const char *v36; // r9
  int v37; // [rsp+20h] [rbp-E0h] BYREF
  int v38[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v35, v36);
    return 0;
  }
  v38[0] = 0;
  v37 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v38);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v13, (const char *)(unsigned int)ValueFromSemaphore, v37);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v15, v16);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v18 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v21 = v18;
  if ( !v18 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v19, v20);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    return LastError;
  }
  v22 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v18, &v37);
  v24 = v22;
  if ( v22 >= 0 )
  {
    if ( !CloseHandle(v21) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    *a3 = v38[0] | (unsigned __int64)((__int64)v37 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v23, (const char *)(unsigned int)v22, v37);
  if ( !CloseHandle(v21) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
  return v24;
}

```

## disassembly

```asm
0x18003360c  push    rbp
0x18003360e  push    rbx
0x18003360f  push    rsi
0x180033610  push    rdi
0x180033611  push    r14
0x180033613  push    r15
0x180033615  lea     rbp, [rsp-158h]
0x18003361d  sub     rsp, 258h
0x180033624  mov     rax, cs:__security_cookie
0x18003362b  xor     rax, rsp
0x18003362e  mov     [rbp+180h+var_40], rax
0x180033635  xor     r15d, r15d
0x180033638  lea     rax, [rsp+280h+Name]
0x18003363d  mov     [r8], r15
0x180033640  mov     r14, r8
0x180033643  mov     edx, 104h
0x180033648  mov     r9d, 7FFFFFFEh
0x18003364e  test    r9, r9
0x180033651  jz      short loc_180033672
0x180033653  movzx   r8d, word ptr [rcx]
0x180033657  test    r8w, r8w
0x18003365b  jz      short loc_180033672
0x18003365d  mov     [rax], r8w
0x180033661  add     rcx, 2
0x180033665  add     rax, 2
0x180033669  dec     r9
0x18003366c  sub     rdx, 1; unsigned __int64
0x180033670  jnz     short loc_18003364E
0x180033672  test    rdx, rdx
0x180033675  lea     rcx, [rax-2]
0x180033679  lea     r8, aP0; "_p0"
0x180033680  cmovnz  rcx, rax
0x180033684  mov     [rcx], r15w
0x180033688  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18003368d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180033692  mov     esi, 1F0003h
0x180033697  lea     r8, [rsp+280h+Name]; lpName
0x18003369c  mov     ecx, esi; dwDesiredAccess
0x18003369e  xor     edx, edx; bInheritHandle
0x1800336a0  call    cs:__imp_OpenSemaphoreW
0x1800336a6  mov     rbx, rax
0x1800336a9  test    rax, rax
0x1800336ac  jz      loc_1800337CD
0x1800336b2  lea     rdx, [rsp+280h+var_25C]; int *
0x1800336b7  mov     [rsp+280h+var_25C], r15d
0x1800336bc  mov     rcx, rax; hHandle
0x1800336bf  mov     [rsp+280h+var_260], r15d; int
0x1800336c4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800336c9  mov     edi, eax
0x1800336cb  test    eax, eax
0x1800336cd  jns     short loc_1800336FB
0x1800336cf  mov     rcx, [rbp+188h]; this
0x1800336d6  mov     r9d, eax; char *
0x1800336d9  mov     edx, 0D6h; void *
0x1800336de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800336e3  mov     rcx, rbx; hObject
0x1800336e6  call    cs:__imp_CloseHandle
0x1800336ec  test    eax, eax
0x1800336ee  jz      loc_180033842
0x1800336f4  mov     eax, edi
0x1800336f6  jmp     loc_1800337ED
0x1800336fb  lea     r8, asc_180066CD8; "h"
0x180033702  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180033707  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003370c  lea     r8, [rsp+280h+Name]; lpName
0x180033711  xor     edx, edx; bInheritHandle
0x180033713  mov     ecx, esi; dwDesiredAccess
0x180033715  call    cs:__imp_OpenSemaphoreW
0x18003371b  mov     rdi, rax
0x18003371e  test    rax, rax
0x180033721  jz      loc_1800337A8
0x180033727  lea     rdx, [rsp+280h+var_260]; int *
0x18003372c  mov     rcx, rax; hHandle
0x18003372f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180033734  mov     esi, eax
0x180033736  test    eax, eax
0x180033738  jns     short loc_180033774
0x18003373a  mov     rcx, [rbp+188h]; this
0x180033741  mov     r9d, eax; char *
0x180033744  mov     edx, 0DEh; void *
0x180033749  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003374e  mov     rcx, rdi; hObject
0x180033751  call    cs:__imp_CloseHandle
0x180033757  test    eax, eax
0x180033759  jz      loc_180033854
0x18003375f  mov     rcx, rbx; hObject
0x180033762  call    cs:__imp_CloseHandle
0x180033768  test    eax, eax
0x18003376a  jz      loc_180033866
0x180033770  mov     eax, esi
0x180033772  jmp     short loc_1800337ED
0x180033774  mov     rcx, rdi; hObject
0x180033777  call    cs:__imp_CloseHandle
0x18003377d  test    eax, eax
0x18003377f  jz      loc_18003380C
0x180033785  movsxd  rax, [rsp+280h+var_25C]
0x18003378a  movsxd  rcx, [rsp+280h+var_260]
0x18003378f  shl     rcx, 1Fh
0x180033793  or      rcx, rax
0x180033796  mov     [r14], rcx
0x180033799  mov     rcx, rbx; hObject
0x18003379c  call    cs:__imp_CloseHandle
0x1800337a2  test    eax, eax
0x1800337a4  jz      short loc_18003381E
0x1800337a6  jmp     short loc_1800337D8
0x1800337a8  mov     rcx, [rbp+188h]; this
0x1800337af  mov     edx, 0DCh; void *
0x1800337b4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800337b9  mov     rcx, rbx; hObject
0x1800337bc  mov     edi, eax
0x1800337be  call    cs:__imp_CloseHandle
0x1800337c4  test    eax, eax
0x1800337c6  jz      short loc_180033830
0x1800337c8  jmp     loc_1800336F4
0x1800337cd  call    cs:__imp_GetLastError
0x1800337d3  cmp     eax, 2
0x1800337d6  jnz     short loc_1800337DC
0x1800337d8  xor     eax, eax
0x1800337da  jmp     short loc_1800337ED
0x1800337dc  mov     rcx, [rbp+188h]; this
0x1800337e3  mov     edx, 0D0h; void *
0x1800337e8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800337ed  mov     rcx, [rbp+180h+var_40]
0x1800337f4  xor     rcx, rsp; StackCookie
0x1800337f7  call    __security_check_cookie
0x1800337fc  add     rsp, 258h
0x180033803  pop     r15
0x180033805  pop     r14
0x180033807  pop     rdi
0x180033808  pop     rsi
0x180033809  pop     rbx
0x18003380a  pop     rbp
0x18003380b  retn
0x18003380c  mov     rcx, [rbp+188h]; this
0x180033813  mov     edx, 0A0Bh; void *
0x180033818  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18003381e  mov     rcx, [rbp+188h]; this
0x180033825  mov     edx, 0A0Bh; void *
0x18003382a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180033830  mov     rcx, [rbp+188h]; this
0x180033837  mov     edx, 0A0Bh; void *
0x18003383c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180033842  mov     rcx, [rbp+188h]; this
0x180033849  mov     edx, 0A0Bh; void *
0x18003384e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180033854  mov     rcx, [rbp+188h]; this
0x18003385b  mov     edx, 0A0Bh; void *
0x180033860  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180033866  mov     rcx, [rbp+188h]; this
0x18003386d  mov     edx, 0A0Bh; void *
0x180033872  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
