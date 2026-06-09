# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000993c`
- end: `0x180009bd4`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `664`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180005188`
- `0x18000555c`

## callees

- `0x180002590`
- `0x180006af4`
- `0x180008914`
- `0x180008934`
- `0x180009384`
- `0x18000993c`
- `0x18000a21c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800099d3`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009a55`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800099d3`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009a55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009b22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009b22`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009a20`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009a98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009aa9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009ac1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009ae6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009b13`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009a20`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009a98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009aa9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009ac1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009ae6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009b13`

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
  __int64 v13; // r8
  const char *v14; // r9
  HANDLE v16; // rax
  const char *v17; // r9
  void *v18; // rdi
  int v19; // eax
  unsigned int v20; // esi
  __int64 v21; // r8
  const char *v22; // r9
  __int64 v23; // r8
  const char *v24; // r9
  __int64 v25; // r8
  const char *v26; // r9
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, (int)"wil", (const char *)(unsigned int)ValueFromSemaphore);
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
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v19);
  if ( !CloseHandle(v18) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v21, v22);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
  return v20;
}

```

## disassembly

```asm
0x18000993c  push    rbp
0x18000993e  push    rbx
0x18000993f  push    rsi
0x180009940  push    rdi
0x180009941  push    r14
0x180009943  push    r15
0x180009945  lea     rbp, [rsp-158h]
0x18000994d  sub     rsp, 258h
0x180009954  mov     rax, cs:__security_cookie
0x18000995b  xor     rax, rsp
0x18000995e  mov     [rbp+180h+var_40], rax
0x180009965  xor     r15d, r15d
0x180009968  lea     rax, [rsp+280h+Name]
0x18000996d  mov     esi, 104h
0x180009972  mov     [r8], r15
0x180009975  mov     edx, esi
0x180009977  mov     r14, r8
0x18000997a  mov     r9d, 7FFFFFFEh
0x180009980  test    r9, r9
0x180009983  jz      short loc_1800099A4
0x180009985  movzx   r8d, word ptr [rcx]
0x180009989  test    r8w, r8w
0x18000998d  jz      short loc_1800099A4
0x18000998f  mov     [rax], r8w
0x180009993  add     rcx, 2
0x180009997  add     rax, 2
0x18000999b  dec     r9
0x18000999e  sub     rdx, 1
0x1800099a2  jnz     short loc_180009980
0x1800099a4  test    rdx, rdx
0x1800099a7  lea     rcx, [rax-2]
0x1800099ab  lea     r8, aP0; "_p0"
0x1800099b2  mov     rdx, rsi; unsigned __int64
0x1800099b5  cmovnz  rcx, rax
0x1800099b9  mov     [rcx], r15w
0x1800099bd  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800099c2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800099c7  lea     r8, [rsp+280h+Name]; lpName
0x1800099cc  xor     edx, edx; bInheritHandle
0x1800099ce  mov     ecx, 1F0003h; dwDesiredAccess
0x1800099d3  call    cs:__imp_OpenSemaphoreW
0x1800099d9  mov     rbx, rax
0x1800099dc  test    rax, rax
0x1800099df  jz      loc_180009B22
0x1800099e5  lea     rdx, [rsp+280h+var_25C]; int *
0x1800099ea  mov     [rsp+280h+var_25C], r15d
0x1800099ef  mov     rcx, rax; hHandle
0x1800099f2  mov     [rsp+280h+var_260], r15d; int
0x1800099f7  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800099fc  mov     edi, eax
0x1800099fe  test    eax, eax
0x180009a00  jns     short loc_180009A35
0x180009a02  mov     rcx, [rbp+188h]; this
0x180009a09  lea     r8, aWil; "wil"
0x180009a10  mov     r9d, eax; char *
0x180009a13  mov     edx, 0D6h; void *
0x180009a18  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009a1d  mov     rcx, rbx; hObject
0x180009a20  call    cs:__imp_CloseHandle
0x180009a26  test    eax, eax
0x180009a28  jz      loc_180009B9E
0x180009a2e  mov     eax, edi
0x180009a30  jmp     loc_180009B49
0x180009a35  lea     r8, asc_180036398; "h"
0x180009a3c  mov     rdx, rsi; unsigned __int64
0x180009a3f  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180009a44  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009a49  lea     r8, [rsp+280h+Name]; lpName
0x180009a4e  xor     edx, edx; bInheritHandle
0x180009a50  mov     ecx, 1F0003h; dwDesiredAccess
0x180009a55  call    cs:__imp_OpenSemaphoreW
0x180009a5b  mov     rdi, rax
0x180009a5e  test    rax, rax
0x180009a61  jz      loc_180009AF6
0x180009a67  lea     rdx, [rsp+280h+var_260]; int *
0x180009a6c  mov     rcx, rax; hHandle
0x180009a6f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009a74  mov     esi, eax
0x180009a76  test    eax, eax
0x180009a78  jns     short loc_180009ABE
0x180009a7a  mov     rcx, [rbp+188h]; this
0x180009a81  lea     r8, aWil; "wil"
0x180009a88  mov     r9d, eax; char *
0x180009a8b  mov     edx, 0DEh; void *
0x180009a90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009a95  mov     rcx, rdi; hObject
0x180009a98  call    cs:__imp_CloseHandle
0x180009a9e  test    eax, eax
0x180009aa0  jz      loc_180009BB0
0x180009aa6  mov     rcx, rbx; hObject
0x180009aa9  call    cs:__imp_CloseHandle
0x180009aaf  test    eax, eax
0x180009ab1  jz      loc_180009BC2
0x180009ab7  mov     eax, esi
0x180009ab9  jmp     loc_180009B49
0x180009abe  mov     rcx, rdi; hObject
0x180009ac1  call    cs:__imp_CloseHandle
0x180009ac7  test    eax, eax
0x180009ac9  jz      loc_180009B68
0x180009acf  movsxd  rax, [rsp+280h+var_25C]
0x180009ad4  movsxd  rcx, [rsp+280h+var_260]
0x180009ad9  shl     rcx, 1Fh
0x180009add  or      rcx, rax
0x180009ae0  mov     [r14], rcx
0x180009ae3  mov     rcx, rbx; hObject
0x180009ae6  call    cs:__imp_CloseHandle
0x180009aec  test    eax, eax
0x180009aee  jz      loc_180009B7A
0x180009af4  jmp     short loc_180009B2D
0x180009af6  mov     rcx, [rbp+188h]; this
0x180009afd  lea     r8, aWil; "wil"
0x180009b04  mov     edx, 0DCh; void *
0x180009b09  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009b0e  mov     rcx, rbx; hObject
0x180009b11  mov     edi, eax
0x180009b13  call    cs:__imp_CloseHandle
0x180009b19  test    eax, eax
0x180009b1b  jz      short loc_180009B8C
0x180009b1d  jmp     loc_180009A2E
0x180009b22  call    cs:__imp_GetLastError
0x180009b28  cmp     eax, 2
0x180009b2b  jnz     short loc_180009B31
0x180009b2d  xor     eax, eax
0x180009b2f  jmp     short loc_180009B49
0x180009b31  mov     rcx, [rbp+188h]; this
0x180009b38  lea     r8, aWil; "wil"
0x180009b3f  mov     edx, 0D0h; void *
0x180009b44  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009b49  mov     rcx, [rbp+180h+var_40]
0x180009b50  xor     rcx, rsp; StackCookie
0x180009b53  call    __security_check_cookie
0x180009b58  add     rsp, 258h
0x180009b5f  pop     r15
0x180009b61  pop     r14
0x180009b63  pop     rdi
0x180009b64  pop     rsi
0x180009b65  pop     rbx
0x180009b66  pop     rbp
0x180009b67  retn
0x180009b68  mov     rcx, [rbp+188h]; this
0x180009b6f  mov     edx, 0A0Bh; void *
0x180009b74  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009b7a  mov     rcx, [rbp+188h]; this
0x180009b81  mov     edx, 0A0Bh; void *
0x180009b86  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009b8c  mov     rcx, [rbp+188h]; this
0x180009b93  mov     edx, 0A0Bh; void *
0x180009b98  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009b9e  mov     rcx, [rbp+188h]; this
0x180009ba5  mov     edx, 0A0Bh; void *
0x180009baa  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009bb0  mov     rcx, [rbp+188h]; this
0x180009bb7  mov     edx, 0A0Bh; void *
0x180009bbc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009bc2  mov     rcx, [rbp+188h]; this
0x180009bc9  mov     edx, 0A0Bh; void *
0x180009bce  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
