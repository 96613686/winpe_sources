# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800193fc`
- end: `0x180019694`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `664`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180014938`
- `0x180014d08`

## callees

- `0x180007660`
- `0x1800164f8`
- `0x1800183d4`
- `0x1800183f4`
- `0x180018e44`
- `0x1800193fc`
- `0x180019e48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180019493`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180019515`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180019493`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180019515`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800195e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800195e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800194e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019558`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019569`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019581`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800195a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800195d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800194e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019558`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019569`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019581`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800195a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800195d3`

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
  const char *v17; // r9
  void *v18; // rdi
  int v19; // eax
  unsigned int v20; // esi
  unsigned int v21; // r8d
  const char *v22; // r9
  unsigned int v23; // r8d
  const char *v24; // r9
  unsigned int v25; // r8d
  const char *v26; // r9
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  const char *v31; // r9
  int v32; // [rsp+20h] [rbp-E0h] BYREF
  int v33[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v31);
    return 0;
  }
  v33[0] = 0;
  v32 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v33);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v32);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v13, v14);
    return LastError;
  }
  StringCchCatW(Name, 0x104u, L"h");
  v16 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18 = v16;
  if ( !v16 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v17);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    return LastError;
  }
  v19 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v16, &v32);
  v20 = v19;
  if ( v19 >= 0 )
  {
    if ( !CloseHandle(v18) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
    *a3 = v33[0] | (unsigned __int64)((__int64)v32 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v19, v32);
  if ( !CloseHandle(v18) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v21, v22);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
  return v20;
}

```

## disassembly

```asm
0x1800193fc  push    rbp
0x1800193fe  push    rbx
0x1800193ff  push    rsi
0x180019400  push    rdi
0x180019401  push    r14
0x180019403  push    r15
0x180019405  lea     rbp, [rsp-158h]
0x18001940d  sub     rsp, 258h
0x180019414  mov     rax, cs:__security_cookie
0x18001941b  xor     rax, rsp
0x18001941e  mov     [rbp+180h+var_40], rax
0x180019425  xor     r15d, r15d
0x180019428  lea     rax, [rsp+280h+Name]
0x18001942d  mov     esi, 104h
0x180019432  mov     [r8], r15
0x180019435  mov     edx, esi
0x180019437  mov     r14, r8
0x18001943a  mov     r9d, 7FFFFFFEh
0x180019440  test    r9, r9
0x180019443  jz      short loc_180019464
0x180019445  movzx   r8d, word ptr [rcx]
0x180019449  test    r8w, r8w
0x18001944d  jz      short loc_180019464
0x18001944f  mov     [rax], r8w
0x180019453  add     rcx, 2
0x180019457  add     rax, 2
0x18001945b  dec     r9
0x18001945e  sub     rdx, 1
0x180019462  jnz     short loc_180019440
0x180019464  test    rdx, rdx
0x180019467  lea     rcx, [rax-2]
0x18001946b  lea     r8, aP0; "_p0"
0x180019472  mov     rdx, rsi; unsigned __int64
0x180019475  cmovnz  rcx, rax
0x180019479  mov     [rcx], r15w
0x18001947d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180019482  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180019487  lea     r8, [rsp+280h+Name]; lpName
0x18001948c  xor     edx, edx; bInheritHandle
0x18001948e  mov     ecx, 1F0003h; dwDesiredAccess
0x180019493  call    cs:__imp_OpenSemaphoreW
0x180019499  mov     rbx, rax
0x18001949c  test    rax, rax
0x18001949f  jz      loc_1800195E2
0x1800194a5  lea     rdx, [rsp+280h+var_25C]; int *
0x1800194aa  mov     [rsp+280h+var_25C], r15d
0x1800194af  mov     rcx, rax; hHandle
0x1800194b2  mov     [rsp+280h+var_260], r15d; int
0x1800194b7  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800194bc  mov     edi, eax
0x1800194be  test    eax, eax
0x1800194c0  jns     short loc_1800194F5
0x1800194c2  mov     rcx, [rbp+188h]; this
0x1800194c9  lea     r8, aWil; "wil"
0x1800194d0  mov     r9d, eax; char *
0x1800194d3  mov     edx, 0D6h; void *
0x1800194d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800194dd  mov     rcx, rbx; hObject
0x1800194e0  call    cs:__imp_CloseHandle
0x1800194e6  test    eax, eax
0x1800194e8  jz      loc_18001965E
0x1800194ee  mov     eax, edi
0x1800194f0  jmp     loc_180019609
0x1800194f5  lea     r8, asc_1800788F0; "h"
0x1800194fc  mov     rdx, rsi; unsigned __int64
0x1800194ff  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180019504  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180019509  lea     r8, [rsp+280h+Name]; lpName
0x18001950e  xor     edx, edx; bInheritHandle
0x180019510  mov     ecx, 1F0003h; dwDesiredAccess
0x180019515  call    cs:__imp_OpenSemaphoreW
0x18001951b  mov     rdi, rax
0x18001951e  test    rax, rax
0x180019521  jz      loc_1800195B6
0x180019527  lea     rdx, [rsp+280h+var_260]; int *
0x18001952c  mov     rcx, rax; hHandle
0x18001952f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180019534  mov     esi, eax
0x180019536  test    eax, eax
0x180019538  jns     short loc_18001957E
0x18001953a  mov     rcx, [rbp+188h]; this
0x180019541  lea     r8, aWil; "wil"
0x180019548  mov     r9d, eax; char *
0x18001954b  mov     edx, 0DEh; void *
0x180019550  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019555  mov     rcx, rdi; hObject
0x180019558  call    cs:__imp_CloseHandle
0x18001955e  test    eax, eax
0x180019560  jz      loc_180019670
0x180019566  mov     rcx, rbx; hObject
0x180019569  call    cs:__imp_CloseHandle
0x18001956f  test    eax, eax
0x180019571  jz      loc_180019682
0x180019577  mov     eax, esi
0x180019579  jmp     loc_180019609
0x18001957e  mov     rcx, rdi; hObject
0x180019581  call    cs:__imp_CloseHandle
0x180019587  test    eax, eax
0x180019589  jz      loc_180019628
0x18001958f  movsxd  rax, [rsp+280h+var_25C]
0x180019594  movsxd  rcx, [rsp+280h+var_260]
0x180019599  shl     rcx, 1Fh
0x18001959d  or      rcx, rax
0x1800195a0  mov     [r14], rcx
0x1800195a3  mov     rcx, rbx; hObject
0x1800195a6  call    cs:__imp_CloseHandle
0x1800195ac  test    eax, eax
0x1800195ae  jz      loc_18001963A
0x1800195b4  jmp     short loc_1800195ED
0x1800195b6  mov     rcx, [rbp+188h]; this
0x1800195bd  lea     r8, aWil; "wil"
0x1800195c4  mov     edx, 0DCh; void *
0x1800195c9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800195ce  mov     rcx, rbx; hObject
0x1800195d1  mov     edi, eax
0x1800195d3  call    cs:__imp_CloseHandle
0x1800195d9  test    eax, eax
0x1800195db  jz      short loc_18001964C
0x1800195dd  jmp     loc_1800194EE
0x1800195e2  call    cs:__imp_GetLastError
0x1800195e8  cmp     eax, 2
0x1800195eb  jnz     short loc_1800195F1
0x1800195ed  xor     eax, eax
0x1800195ef  jmp     short loc_180019609
0x1800195f1  mov     rcx, [rbp+188h]; this
0x1800195f8  lea     r8, aWil; "wil"
0x1800195ff  mov     edx, 0D0h; void *
0x180019604  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180019609  mov     rcx, [rbp+180h+var_40]
0x180019610  xor     rcx, rsp; StackCookie
0x180019613  call    __security_check_cookie
0x180019618  add     rsp, 258h
0x18001961f  pop     r15
0x180019621  pop     r14
0x180019623  pop     rdi
0x180019624  pop     rsi
0x180019625  pop     rbx
0x180019626  pop     rbp
0x180019627  retn
0x180019628  mov     rcx, [rbp+188h]; this
0x18001962f  mov     edx, 0A0Bh; void *
0x180019634  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001963a  mov     rcx, [rbp+188h]; this
0x180019641  mov     edx, 0A0Bh; void *
0x180019646  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001964c  mov     rcx, [rbp+188h]; this
0x180019653  mov     edx, 0A0Bh; void *
0x180019658  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001965e  mov     rcx, [rbp+188h]; this
0x180019665  mov     edx, 0A0Bh; void *
0x18001966a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180019670  mov     rcx, [rbp+188h]; this
0x180019677  mov     edx, 0A0Bh; void *
0x18001967c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180019682  mov     rcx, [rbp+188h]; this
0x180019689  mov     edx, 0A0Bh; void *
0x18001968e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
