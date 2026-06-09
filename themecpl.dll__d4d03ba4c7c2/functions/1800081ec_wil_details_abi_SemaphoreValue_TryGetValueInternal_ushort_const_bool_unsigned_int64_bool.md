# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800081ec`
- end: `0x1800084ad`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `705`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180005adc`
- `0x180011854`

## callees

- `0x180002280`
- `0x180006aa4`
- `0x180007804`
- `0x180007824`
- `0x180007fd8`
- `0x1800081ec`
- `0x1800086d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008283`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008311`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008283`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008311`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800083fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800083fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800082d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000835a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008371`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000838f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800083ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800083e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800082d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000835a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008371`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000838f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800083ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800083e6`

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
0x1800081ec  push    rbp
0x1800081ee  push    rbx
0x1800081ef  push    rsi
0x1800081f0  push    rdi
0x1800081f1  push    r14
0x1800081f3  push    r15
0x1800081f5  lea     rbp, [rsp-158h]
0x1800081fd  sub     rsp, 258h
0x180008204  mov     rax, cs:__security_cookie
0x18000820b  xor     rax, rsp
0x18000820e  mov     [rbp+180h+var_40], rax
0x180008215  xor     r15d, r15d
0x180008218  lea     rax, [rsp+280h+Name]
0x18000821d  mov     esi, 104h
0x180008222  mov     [r8], r15
0x180008225  mov     edx, esi
0x180008227  mov     r14, r8
0x18000822a  mov     r9d, 7FFFFFFEh
0x180008230  test    r9, r9
0x180008233  jz      short loc_180008254
0x180008235  movzx   r8d, word ptr [rcx]
0x180008239  test    r8w, r8w
0x18000823d  jz      short loc_180008254
0x18000823f  mov     [rax], r8w
0x180008243  add     rcx, 2
0x180008247  add     rax, 2
0x18000824b  dec     r9
0x18000824e  sub     rdx, 1
0x180008252  jnz     short loc_180008230
0x180008254  test    rdx, rdx
0x180008257  lea     rcx, [rax-2]
0x18000825b  lea     r8, aP0; "_p0"
0x180008262  mov     rdx, rsi; unsigned __int64
0x180008265  cmovnz  rcx, rax
0x180008269  mov     [rcx], r15w
0x18000826d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180008272  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008277  lea     r8, [rsp+280h+Name]; lpName
0x18000827c  xor     edx, edx; bInheritHandle
0x18000827e  mov     ecx, 1F0003h; dwDesiredAccess
0x180008283  call    cs:__imp_OpenSemaphoreW
0x18000828a  nop     dword ptr [rax+rax+00h]
0x18000828f  mov     rbx, rax
0x180008292  test    rax, rax
0x180008295  jz      loc_1800083FB
0x18000829b  lea     rdx, [rsp+280h+var_25C]; int *
0x1800082a0  mov     [rsp+280h+var_25C], r15d
0x1800082a5  mov     rcx, rax; hHandle
0x1800082a8  mov     [rsp+280h+var_260], r15d; int
0x1800082ad  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800082b2  mov     edi, eax
0x1800082b4  test    eax, eax
0x1800082b6  jns     short loc_1800082F1
0x1800082b8  mov     rcx, [rbp+188h]; this
0x1800082bf  lea     r8, aWil; "wil"
0x1800082c6  mov     r9d, eax; char *
0x1800082c9  mov     edx, 0D6h; void *
0x1800082ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800082d3  mov     rcx, rbx; hObject
0x1800082d6  call    cs:__imp_CloseHandle
0x1800082dd  nop     dword ptr [rax+rax+00h]
0x1800082e2  test    eax, eax
0x1800082e4  jz      loc_180008477
0x1800082ea  mov     eax, edi
0x1800082ec  jmp     loc_180008421
0x1800082f1  lea     r8, asc_18005D430; "h"
0x1800082f8  mov     rdx, rsi; unsigned __int64
0x1800082fb  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180008300  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008305  lea     r8, [rsp+280h+Name]; lpName
0x18000830a  xor     edx, edx; bInheritHandle
0x18000830c  mov     ecx, 1F0003h; dwDesiredAccess
0x180008311  call    cs:__imp_OpenSemaphoreW
0x180008318  nop     dword ptr [rax+rax+00h]
0x18000831d  mov     rdi, rax
0x180008320  test    rax, rax
0x180008323  jz      loc_1800083D0
0x180008329  lea     rdx, [rsp+280h+var_260]; int *
0x18000832e  mov     rcx, rax; hHandle
0x180008331  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180008336  mov     esi, eax
0x180008338  test    eax, eax
0x18000833a  jns     short loc_18000838C
0x18000833c  mov     rcx, [rbp+188h]; this
0x180008343  lea     r8, aWil; "wil"
0x18000834a  mov     r9d, eax; char *
0x18000834d  mov     edx, 0DEh; void *
0x180008352  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008357  mov     rcx, rdi; hObject
0x18000835a  call    cs:__imp_CloseHandle
0x180008361  nop     dword ptr [rax+rax+00h]
0x180008366  test    eax, eax
0x180008368  jz      loc_180008489
0x18000836e  mov     rcx, rbx; hObject
0x180008371  call    cs:__imp_CloseHandle
0x180008378  nop     dword ptr [rax+rax+00h]
0x18000837d  test    eax, eax
0x18000837f  jz      loc_18000849B
0x180008385  mov     eax, esi
0x180008387  jmp     loc_180008421
0x18000838c  mov     rcx, rdi; hObject
0x18000838f  call    cs:__imp_CloseHandle
0x180008396  nop     dword ptr [rax+rax+00h]
0x18000839b  test    eax, eax
0x18000839d  jz      loc_180008441
0x1800083a3  movsxd  rax, [rsp+280h+var_25C]
0x1800083a8  movsxd  rcx, [rsp+280h+var_260]
0x1800083ad  shl     rcx, 1Fh
0x1800083b1  or      rcx, rax
0x1800083b4  mov     [r14], rcx
0x1800083b7  mov     rcx, rbx; hObject
0x1800083ba  call    cs:__imp_CloseHandle
0x1800083c1  nop     dword ptr [rax+rax+00h]
0x1800083c6  test    eax, eax
0x1800083c8  jz      loc_180008453
0x1800083ce  jmp     short loc_18000840C
0x1800083d0  mov     rcx, [rbp+188h]; this
0x1800083d7  mov     edx, 0DCh; void *
0x1800083dc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800083e1  mov     rcx, rbx; hObject
0x1800083e4  mov     edi, eax
0x1800083e6  call    cs:__imp_CloseHandle
0x1800083ed  nop     dword ptr [rax+rax+00h]
0x1800083f2  test    eax, eax
0x1800083f4  jz      short loc_180008465
0x1800083f6  jmp     loc_1800082EA
0x1800083fb  call    cs:__imp_GetLastError
0x180008402  nop     dword ptr [rax+rax+00h]
0x180008407  cmp     eax, 2
0x18000840a  jnz     short loc_180008410
0x18000840c  xor     eax, eax
0x18000840e  jmp     short loc_180008421
0x180008410  mov     rcx, [rbp+188h]; this
0x180008417  mov     edx, 0D0h; void *
0x18000841c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008421  mov     rcx, [rbp+180h+var_40]
0x180008428  xor     rcx, rsp; StackCookie
0x18000842b  call    __security_check_cookie
0x180008430  add     rsp, 258h
0x180008437  pop     r15
0x180008439  pop     r14
0x18000843b  pop     rdi
0x18000843c  pop     rsi
0x18000843d  pop     rbx
0x18000843e  pop     rbp
0x18000843f  retn
0x180008441  mov     rcx, [rbp+188h]; this
0x180008448  mov     edx, 0A0Bh; void *
0x18000844d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008453  mov     rcx, [rbp+188h]; this
0x18000845a  mov     edx, 0A0Bh; void *
0x18000845f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008465  mov     rcx, [rbp+188h]; this
0x18000846c  mov     edx, 0A0Bh; void *
0x180008471  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008477  mov     rcx, [rbp+188h]; this
0x18000847e  mov     edx, 0A0Bh; void *
0x180008483  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008489  mov     rcx, [rbp+188h]; this
0x180008490  mov     edx, 0A0Bh; void *
0x180008495  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000849b  mov     rcx, [rbp+188h]; this
0x1800084a2  mov     edx, 0A0Bh; void *
0x1800084a7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
