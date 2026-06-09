# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000d93c`
- end: `0x18000dbbf`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `643`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800061b8`
- `0x180006588`

## callees

- `0x180002810`
- `0x1800099d8`
- `0x18000c764`
- `0x18000c784`
- `0x18000d2f0`
- `0x18000d93c`
- `0x18000e444`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000d9d3`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000da55`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000d9d3`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000da55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000db14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000db14`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000da20`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000da98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000daa9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dabe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dae3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000db05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000da20`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000da98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000daa9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dabe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dae3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000db05`

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
0x18000d93c  push    rbp
0x18000d93e  push    rbx
0x18000d93f  push    rsi
0x18000d940  push    rdi
0x18000d941  push    r14
0x18000d943  push    r15
0x18000d945  lea     rbp, [rsp-158h]
0x18000d94d  sub     rsp, 258h
0x18000d954  mov     rax, cs:__security_cookie
0x18000d95b  xor     rax, rsp
0x18000d95e  mov     [rbp+180h+var_40], rax
0x18000d965  xor     r15d, r15d
0x18000d968  lea     rax, [rsp+280h+Name]
0x18000d96d  mov     esi, 104h
0x18000d972  mov     [r8], r15
0x18000d975  mov     edx, esi
0x18000d977  mov     r14, r8
0x18000d97a  mov     r9d, 7FFFFFFEh
0x18000d980  test    r9, r9
0x18000d983  jz      short loc_18000D9A4
0x18000d985  movzx   r8d, word ptr [rcx]
0x18000d989  test    r8w, r8w
0x18000d98d  jz      short loc_18000D9A4
0x18000d98f  mov     [rax], r8w
0x18000d993  add     rcx, 2
0x18000d997  add     rax, 2
0x18000d99b  dec     r9
0x18000d99e  sub     rdx, 1
0x18000d9a2  jnz     short loc_18000D980
0x18000d9a4  test    rdx, rdx
0x18000d9a7  lea     rcx, [rax-2]
0x18000d9ab  lea     r8, aP0; "_p0"
0x18000d9b2  mov     rdx, rsi; unsigned __int64
0x18000d9b5  cmovnz  rcx, rax
0x18000d9b9  mov     [rcx], r15w
0x18000d9bd  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000d9c2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000d9c7  lea     r8, [rsp+280h+Name]; lpName
0x18000d9cc  xor     edx, edx; bInheritHandle
0x18000d9ce  mov     ecx, 1F0003h; dwDesiredAccess
0x18000d9d3  call    cs:__imp_OpenSemaphoreW
0x18000d9d9  mov     rbx, rax
0x18000d9dc  test    rax, rax
0x18000d9df  jz      loc_18000DB14
0x18000d9e5  lea     rdx, [rsp+280h+var_25C]; int *
0x18000d9ea  mov     [rsp+280h+var_25C], r15d
0x18000d9ef  mov     rcx, rax; hHandle
0x18000d9f2  mov     [rsp+280h+var_260], r15d; int
0x18000d9f7  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000d9fc  mov     edi, eax
0x18000d9fe  test    eax, eax
0x18000da00  jns     short loc_18000DA35
0x18000da02  mov     rcx, [rbp+188h]; this
0x18000da09  lea     r8, aWil; "wil"
0x18000da10  mov     r9d, eax; char *
0x18000da13  mov     edx, 0D6h; void *
0x18000da18  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000da1d  mov     rcx, rbx; hObject
0x18000da20  call    cs:__imp_CloseHandle
0x18000da26  test    eax, eax
0x18000da28  jz      loc_18000DB89
0x18000da2e  mov     eax, edi
0x18000da30  jmp     loc_18000DB34
0x18000da35  lea     r8, asc_180082B30; "h"
0x18000da3c  mov     rdx, rsi; unsigned __int64
0x18000da3f  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000da44  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000da49  lea     r8, [rsp+280h+Name]; lpName
0x18000da4e  xor     edx, edx; bInheritHandle
0x18000da50  mov     ecx, 1F0003h; dwDesiredAccess
0x18000da55  call    cs:__imp_OpenSemaphoreW
0x18000da5b  mov     rdi, rax
0x18000da5e  test    rax, rax
0x18000da61  jz      loc_18000DAEF
0x18000da67  lea     rdx, [rsp+280h+var_260]; int *
0x18000da6c  mov     rcx, rax; hHandle
0x18000da6f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000da74  mov     esi, eax
0x18000da76  test    eax, eax
0x18000da78  jns     short loc_18000DABB
0x18000da7a  mov     rcx, [rbp+188h]; this
0x18000da81  lea     r8, aWil; "wil"
0x18000da88  mov     r9d, eax; char *
0x18000da8b  mov     edx, 0DEh; void *
0x18000da90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000da95  mov     rcx, rdi; hObject
0x18000da98  call    cs:__imp_CloseHandle
0x18000da9e  test    eax, eax
0x18000daa0  jz      loc_18000DB9B
0x18000daa6  mov     rcx, rbx; hObject
0x18000daa9  call    cs:__imp_CloseHandle
0x18000daaf  test    eax, eax
0x18000dab1  jz      loc_18000DBAD
0x18000dab7  mov     eax, esi
0x18000dab9  jmp     short loc_18000DB34
0x18000dabb  mov     rcx, rdi; hObject
0x18000dabe  call    cs:__imp_CloseHandle
0x18000dac4  test    eax, eax
0x18000dac6  jz      loc_18000DB53
0x18000dacc  movsxd  rax, [rsp+280h+var_25C]
0x18000dad1  movsxd  rcx, [rsp+280h+var_260]
0x18000dad6  shl     rcx, 1Fh
0x18000dada  or      rcx, rax
0x18000dadd  mov     [r14], rcx
0x18000dae0  mov     rcx, rbx; hObject
0x18000dae3  call    cs:__imp_CloseHandle
0x18000dae9  test    eax, eax
0x18000daeb  jz      short loc_18000DB65
0x18000daed  jmp     short loc_18000DB1F
0x18000daef  mov     rcx, [rbp+188h]; this
0x18000daf6  mov     edx, 0DCh; void *
0x18000dafb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000db00  mov     rcx, rbx; hObject
0x18000db03  mov     edi, eax
0x18000db05  call    cs:__imp_CloseHandle
0x18000db0b  test    eax, eax
0x18000db0d  jz      short loc_18000DB77
0x18000db0f  jmp     loc_18000DA2E
0x18000db14  call    cs:__imp_GetLastError
0x18000db1a  cmp     eax, 2
0x18000db1d  jnz     short loc_18000DB23
0x18000db1f  xor     eax, eax
0x18000db21  jmp     short loc_18000DB34
0x18000db23  mov     rcx, [rbp+188h]; this
0x18000db2a  mov     edx, 0D0h; void *
0x18000db2f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000db34  mov     rcx, [rbp+180h+var_40]
0x18000db3b  xor     rcx, rsp; StackCookie
0x18000db3e  call    __security_check_cookie
0x18000db43  add     rsp, 258h
0x18000db4a  pop     r15
0x18000db4c  pop     r14
0x18000db4e  pop     rdi
0x18000db4f  pop     rsi
0x18000db50  pop     rbx
0x18000db51  pop     rbp
0x18000db52  retn
0x18000db53  mov     rcx, [rbp+188h]; this
0x18000db5a  mov     edx, 0A0Bh; void *
0x18000db5f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000db65  mov     rcx, [rbp+188h]; this
0x18000db6c  mov     edx, 0A0Bh; void *
0x18000db71  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000db77  mov     rcx, [rbp+188h]; this
0x18000db7e  mov     edx, 0A0Bh; void *
0x18000db83  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000db89  mov     rcx, [rbp+188h]; this
0x18000db90  mov     edx, 0A0Bh; void *
0x18000db95  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000db9b  mov     rcx, [rbp+188h]; this
0x18000dba2  mov     edx, 0A0Bh; void *
0x18000dba7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000dbad  mov     rcx, [rbp+188h]; this
0x18000dbb4  mov     edx, 0A0Bh; void *
0x18000dbb9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
