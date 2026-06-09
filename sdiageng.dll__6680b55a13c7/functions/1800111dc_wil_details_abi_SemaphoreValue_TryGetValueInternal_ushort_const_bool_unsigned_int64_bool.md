# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800111dc`
- end: `0x180011451`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `629`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000988c`
- `0x180009c30`

## callees

- `0x18000ca30`
- `0x18000ff94`
- `0x18000ffb4`
- `0x180010e70`
- `0x1800111dc`
- `0x1800125b4`
- `0x1800298c0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800113a6`
- `KERNEL32!GetLastError` at `0x1800113a6`
- `KERNEL32!CloseHandle` at `0x1800112b9`
- `KERNEL32!CloseHandle` at `0x18001132a`
- `KERNEL32!CloseHandle` at `0x18001133b`
- `KERNEL32!CloseHandle` at `0x180011350`
- `KERNEL32!CloseHandle` at `0x180011375`
- `KERNEL32!CloseHandle` at `0x180011397`
- `KERNEL32!CloseHandle` at `0x1800112b9`
- `KERNEL32!CloseHandle` at `0x18001132a`
- `KERNEL32!CloseHandle` at `0x18001133b`
- `KERNEL32!CloseHandle` at `0x180011350`
- `KERNEL32!CloseHandle` at `0x180011375`
- `KERNEL32!CloseHandle` at `0x180011397`
- `KERNEL32!OpenSemaphoreW` at `0x180011273`
- `KERNEL32!OpenSemaphoreW` at `0x1800112ee`
- `KERNEL32!OpenSemaphoreW` at `0x180011273`
- `KERNEL32!OpenSemaphoreW` at `0x1800112ee`

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
  int v12; // r8d
  unsigned int LastError; // edi
  __int64 v14; // r8
  const char *v15; // r9
  HANDLE v17; // rax
  unsigned int v18; // r8d
  const char *v19; // r9
  void *v20; // rdi
  int v21; // eax
  int v22; // r8d
  unsigned int v23; // esi
  __int64 v24; // r8
  const char *v25; // r9
  __int64 v26; // r8
  const char *v27; // r9
  __int64 v28; // r8
  const char *v29; // r9
  __int64 v30; // r8
  const char *v31; // r9
  __int64 v32; // r8
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
  int v36; // [rsp+20h] [rbp-E0h] BYREF
  int v37[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v34, v35);
    return 0;
  }
  v37[0] = 0;
  v36 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v37);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v12, (const char *)(unsigned int)ValueFromSemaphore);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(Name, 0x104u, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v18, v19);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    return LastError;
  }
  v21 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v36);
  v23 = v21;
  if ( v21 >= 0 )
  {
    if ( !CloseHandle(v20) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    *a3 = v37[0] | (unsigned __int64)((__int64)v36 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v22, (const char *)(unsigned int)v21);
  if ( !CloseHandle(v20) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
  return v23;
}

```

## disassembly

```asm
0x1800111dc  push    rbp
0x1800111de  push    rbx
0x1800111df  push    rsi
0x1800111e0  push    rdi
0x1800111e1  push    r14
0x1800111e3  push    r15
0x1800111e5  lea     rbp, [rsp-158h]
0x1800111ed  sub     rsp, 258h
0x1800111f4  mov     rax, cs:__security_cookie
0x1800111fb  xor     rax, rsp
0x1800111fe  mov     [rbp+180h+var_40], rax
0x180011205  xor     r15d, r15d
0x180011208  lea     rax, [rsp+280h+Name]
0x18001120d  mov     esi, 104h
0x180011212  mov     [r8], r15
0x180011215  mov     edx, esi
0x180011217  mov     r14, r8
0x18001121a  mov     r9d, 7FFFFFFEh
0x180011220  test    r9, r9
0x180011223  jz      short loc_180011244
0x180011225  movzx   r8d, word ptr [rcx]
0x180011229  test    r8w, r8w
0x18001122d  jz      short loc_180011244
0x18001122f  mov     [rax], r8w
0x180011233  add     rcx, 2
0x180011237  add     rax, 2
0x18001123b  dec     r9
0x18001123e  sub     rdx, 1
0x180011242  jnz     short loc_180011220
0x180011244  test    rdx, rdx
0x180011247  lea     rcx, [rax-2]
0x18001124b  lea     r8, aP0; "_p0"
0x180011252  mov     rdx, rsi; unsigned __int64
0x180011255  cmovnz  rcx, rax
0x180011259  mov     [rcx], r15w
0x18001125d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180011262  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180011267  lea     r8, [rsp+280h+Name]; lpName
0x18001126c  xor     edx, edx; bInheritHandle
0x18001126e  mov     ecx, 1F0003h; dwDesiredAccess
0x180011273  call    cs:__imp_OpenSemaphoreW
0x180011279  mov     rbx, rax
0x18001127c  test    rax, rax
0x18001127f  jz      loc_1800113A6
0x180011285  lea     rdx, [rsp+280h+var_25C]; int *
0x18001128a  mov     [rsp+280h+var_25C], r15d
0x18001128f  mov     rcx, rax; hHandle
0x180011292  mov     [rsp+280h+var_260], r15d; int
0x180011297  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001129c  mov     edi, eax
0x18001129e  test    eax, eax
0x1800112a0  jns     short loc_1800112CE
0x1800112a2  mov     rcx, [rbp+188h]; this
0x1800112a9  mov     r9d, eax; char *
0x1800112ac  mov     edx, 0D6h; void *
0x1800112b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800112b6  mov     rcx, rbx; hObject
0x1800112b9  call    cs:__imp_CloseHandle
0x1800112bf  test    eax, eax
0x1800112c1  jz      loc_18001141B
0x1800112c7  mov     eax, edi
0x1800112c9  jmp     loc_1800113C6
0x1800112ce  lea     r8, asc_18002E8A0; "h"
0x1800112d5  mov     rdx, rsi; unsigned __int64
0x1800112d8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800112dd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800112e2  lea     r8, [rsp+280h+Name]; lpName
0x1800112e7  xor     edx, edx; bInheritHandle
0x1800112e9  mov     ecx, 1F0003h; dwDesiredAccess
0x1800112ee  call    cs:__imp_OpenSemaphoreW
0x1800112f4  mov     rdi, rax
0x1800112f7  test    rax, rax
0x1800112fa  jz      loc_180011381
0x180011300  lea     rdx, [rsp+280h+var_260]; int *
0x180011305  mov     rcx, rax; hHandle
0x180011308  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001130d  mov     esi, eax
0x18001130f  test    eax, eax
0x180011311  jns     short loc_18001134D
0x180011313  mov     rcx, [rbp+188h]; this
0x18001131a  mov     r9d, eax; char *
0x18001131d  mov     edx, 0DEh; void *
0x180011322  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011327  mov     rcx, rdi; hObject
0x18001132a  call    cs:__imp_CloseHandle
0x180011330  test    eax, eax
0x180011332  jz      loc_18001142D
0x180011338  mov     rcx, rbx; hObject
0x18001133b  call    cs:__imp_CloseHandle
0x180011341  test    eax, eax
0x180011343  jz      loc_18001143F
0x180011349  mov     eax, esi
0x18001134b  jmp     short loc_1800113C6
0x18001134d  mov     rcx, rdi; hObject
0x180011350  call    cs:__imp_CloseHandle
0x180011356  test    eax, eax
0x180011358  jz      loc_1800113E5
0x18001135e  movsxd  rax, [rsp+280h+var_25C]
0x180011363  movsxd  rcx, [rsp+280h+var_260]
0x180011368  shl     rcx, 1Fh
0x18001136c  or      rcx, rax
0x18001136f  mov     [r14], rcx
0x180011372  mov     rcx, rbx; hObject
0x180011375  call    cs:__imp_CloseHandle
0x18001137b  test    eax, eax
0x18001137d  jz      short loc_1800113F7
0x18001137f  jmp     short loc_1800113B1
0x180011381  mov     rcx, [rbp+188h]; this
0x180011388  mov     edx, 0DCh; void *
0x18001138d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180011392  mov     rcx, rbx; hObject
0x180011395  mov     edi, eax
0x180011397  call    cs:__imp_CloseHandle
0x18001139d  test    eax, eax
0x18001139f  jz      short loc_180011409
0x1800113a1  jmp     loc_1800112C7
0x1800113a6  call    cs:__imp_GetLastError
0x1800113ac  cmp     eax, 2
0x1800113af  jnz     short loc_1800113B5
0x1800113b1  xor     eax, eax
0x1800113b3  jmp     short loc_1800113C6
0x1800113b5  mov     rcx, [rbp+188h]; this
0x1800113bc  mov     edx, 0D0h; void *
0x1800113c1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800113c6  mov     rcx, [rbp+180h+var_40]
0x1800113cd  xor     rcx, rsp; StackCookie
0x1800113d0  call    __security_check_cookie
0x1800113d5  add     rsp, 258h
0x1800113dc  pop     r15
0x1800113de  pop     r14
0x1800113e0  pop     rdi
0x1800113e1  pop     rsi
0x1800113e2  pop     rbx
0x1800113e3  pop     rbp
0x1800113e4  retn
0x1800113e5  mov     rcx, [rbp+188h]; this
0x1800113ec  mov     edx, 0A0Bh; void *
0x1800113f1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800113f7  mov     rcx, [rbp+188h]; this
0x1800113fe  mov     edx, 0A0Bh; void *
0x180011403  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180011409  mov     rcx, [rbp+188h]; this
0x180011410  mov     edx, 0A0Bh; void *
0x180011415  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001141b  mov     rcx, [rbp+188h]; this
0x180011422  mov     edx, 0A0Bh; void *
0x180011427  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001142d  mov     rcx, [rbp+188h]; this
0x180011434  mov     edx, 0A0Bh; void *
0x180011439  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001143f  mov     rcx, [rbp+188h]; this
0x180011446  mov     edx, 0A0Bh; void *
0x18001144b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
