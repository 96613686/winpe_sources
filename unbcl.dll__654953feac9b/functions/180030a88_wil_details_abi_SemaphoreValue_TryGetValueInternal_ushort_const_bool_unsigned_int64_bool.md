# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180030a88`
- end: `0x180030d0d`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `645`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180027620`

## callees

- `0x18002d5c0`
- `0x18002fc84`
- `0x18002fcac`
- `0x1800308c4`
- `0x180030a88`
- `0x180030f74`
- `0x180069020`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180030b71`
- `KERNEL32!CloseHandle` at `0x180030be2`
- `KERNEL32!CloseHandle` at `0x180030bfa`
- `KERNEL32!CloseHandle` at `0x180030c12`
- `KERNEL32!CloseHandle` at `0x180030c3e`
- `KERNEL32!CloseHandle` at `0x180030c60`
- `KERNEL32!CloseHandle` at `0x180030b71`
- `KERNEL32!CloseHandle` at `0x180030be2`
- `KERNEL32!CloseHandle` at `0x180030bfa`
- `KERNEL32!CloseHandle` at `0x180030c12`
- `KERNEL32!CloseHandle` at `0x180030c3e`
- `KERNEL32!CloseHandle` at `0x180030c60`
- `KERNEL32!OpenSemaphoreW` at `0x180030b25`
- `KERNEL32!OpenSemaphoreW` at `0x180030ba0`
- `KERNEL32!OpenSemaphoreW` at `0x180030b25`
- `KERNEL32!OpenSemaphoreW` at `0x180030ba0`
- `KERNEL32!GetLastError` at `0x180030c6f`
- `KERNEL32!GetLastError` at `0x180030c6f`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned __int64 v5; // rdx
  __int64 v6; // r9
  WCHAR *v7; // rax
  WCHAR v8; // r8
  WCHAR *v9; // rcx
  HANDLE v10; // rax
  void *v11; // rbx
  int ValueFromSemaphore; // eax
  unsigned __int64 v13; // rdx
  unsigned int v14; // r8d
  unsigned int LastError; // edi
  unsigned int v16; // r8d
  const char *v17; // r9
  HANDLE v19; // rax
  unsigned int v20; // r8d
  const char *v21; // r9
  void *v22; // rdi
  int v23; // eax
  unsigned int v24; // r8d
  unsigned int v25; // esi
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
  unsigned int v36; // r8d
  const char *v37; // r9
  int v38; // [rsp+20h] [rbp-E0h] BYREF
  int v39; // [rsp+24h] [rbp-DCh] BYREF
  __int64 v40; // [rsp+28h] [rbp-D8h]
  HANDLE v41; // [rsp+30h] [rbp-D0h]
  HANDLE v42; // [rsp+38h] [rbp-C8h]
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v40 = -2;
  *a3 = 0;
  v5 = 260;
  v6 = 2147483646;
  v7 = Name;
  do
  {
    if ( !v6 )
      break;
    v8 = *a1;
    if ( !*a1 )
      break;
    ++a1;
    *v7++ = v8;
    --v6;
    --v5;
  }
  while ( v5 );
  v9 = v7 - 1;
  if ( v5 )
    v9 = v7;
  *v9 = 0;
  StringCchCatW(Name, v5, L"_p0");
  v10 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v11 = v10;
  v41 = v10;
  if ( !v10 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v36, v37);
    return 0;
  }
  v39 = 0;
  v38 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v10, &v39);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v14, (const char *)(unsigned int)ValueFromSemaphore, v38);
    if ( !CloseHandle(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v16, v17);
    return LastError;
  }
  StringCchCatW(Name, v13, L"h");
  v19 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v22 = v19;
  v42 = v19;
  if ( !v19 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v20, v21);
    if ( !CloseHandle(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v34, v35);
    return LastError;
  }
  v23 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v19, &v38);
  v25 = v23;
  if ( v23 >= 0 )
  {
    if ( !CloseHandle(v22) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    *a3 = v39 | (unsigned __int64)((__int64)v38 << 31);
    if ( !CloseHandle(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v24, (const char *)(unsigned int)v23, v38);
  if ( !CloseHandle(v22) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
  if ( !CloseHandle(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
  return v25;
}

```

## disassembly

```asm
0x180030a88  push    rbp
0x180030a8a  push    rbx
0x180030a8b  push    rsi
0x180030a8c  push    rdi
0x180030a8d  push    r14
0x180030a8f  push    r15
0x180030a91  lea     rbp, [rsp-168h]
0x180030a99  sub     rsp, 268h
0x180030aa0  mov     [rsp+290h+var_268], 0FFFFFFFFFFFFFFFEh
0x180030aa9  mov     rax, cs:__security_cookie
0x180030ab0  xor     rax, rsp
0x180030ab3  mov     [rbp+190h+var_40], rax
0x180030aba  mov     r14, r8
0x180030abd  xor     r15d, r15d
0x180030ac0  mov     [r8], r15
0x180030ac3  mov     edx, 104h
0x180030ac8  mov     r9d, 7FFFFFFEh
0x180030ace  lea     rax, [rsp+290h+Name]
0x180030ad3  test    r9, r9
0x180030ad6  jz      short loc_180030AF7
0x180030ad8  movzx   r8d, word ptr [rcx]
0x180030adc  test    r8w, r8w
0x180030ae0  jz      short loc_180030AF7
0x180030ae2  add     rcx, 2
0x180030ae6  mov     [rax], r8w
0x180030aea  add     rax, 2
0x180030aee  dec     r9
0x180030af1  sub     rdx, 1; unsigned __int64
0x180030af5  jnz     short loc_180030AD3
0x180030af7  lea     rcx, [rax-2]
0x180030afb  test    rdx, rdx
0x180030afe  cmovnz  rcx, rax
0x180030b02  mov     [rcx], r15w
0x180030b06  lea     r8, aP0; "_p0"
0x180030b0d  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x180030b12  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180030b17  lea     r8, [rsp+290h+Name]; lpName
0x180030b1c  xor     edx, edx; bInheritHandle
0x180030b1e  mov     esi, 1F0003h
0x180030b23  mov     ecx, esi; dwDesiredAccess
0x180030b25  call    cs:__imp_OpenSemaphoreW
0x180030b2b  mov     rbx, rax
0x180030b2e  mov     [rsp+290h+var_260], rax
0x180030b33  test    rax, rax
0x180030b36  jz      loc_180030C6F
0x180030b3c  mov     [rsp+290h+var_26C], r15d
0x180030b41  mov     [rsp+290h+var_270], r15d; int
0x180030b46  lea     rdx, [rsp+290h+var_26C]; int *
0x180030b4b  mov     rcx, rax; hHandle
0x180030b4e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180030b53  mov     edi, eax
0x180030b55  test    eax, eax
0x180030b57  jns     short loc_180030B86
0x180030b59  mov     rcx, [rbp+198h]; this
0x180030b60  mov     r9d, eax; char *
0x180030b63  mov     edx, 0D6h; void *
0x180030b68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030b6d  nop
0x180030b6e  mov     rcx, rbx; hObject
0x180030b71  call    cs:__imp_CloseHandle
0x180030b77  test    eax, eax
0x180030b79  jz      loc_180030CDE
0x180030b7f  mov     eax, edi
0x180030b81  jmp     loc_180030C90
0x180030b86  lea     r8, asc_180080CB0; "h"
0x180030b8d  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x180030b92  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180030b97  lea     r8, [rsp+290h+Name]; lpName
0x180030b9c  xor     edx, edx; bInheritHandle
0x180030b9e  mov     ecx, esi; dwDesiredAccess
0x180030ba0  call    cs:__imp_OpenSemaphoreW
0x180030ba6  mov     rdi, rax
0x180030ba9  mov     [rsp+290h+var_258], rax
0x180030bae  test    rax, rax
0x180030bb1  jz      loc_180030C4A
0x180030bb7  lea     rdx, [rsp+290h+var_270]; int *
0x180030bbc  mov     rcx, rax; hHandle
0x180030bbf  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180030bc4  mov     esi, eax
0x180030bc6  test    eax, eax
0x180030bc8  jns     short loc_180030C0F
0x180030bca  mov     rcx, [rbp+198h]; this
0x180030bd1  mov     r9d, eax; char *
0x180030bd4  mov     edx, 0DEh; void *
0x180030bd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030bde  nop
0x180030bdf  mov     rcx, rdi; hObject
0x180030be2  call    cs:__imp_CloseHandle
0x180030be8  mov     rcx, [rbp+198h]; this
0x180030bef  test    eax, eax
0x180030bf1  jz      loc_180030CF0
0x180030bf7  mov     rcx, rbx; hObject
0x180030bfa  call    cs:__imp_CloseHandle
0x180030c00  test    eax, eax
0x180030c02  jz      loc_180030CFB
0x180030c08  mov     eax, esi
0x180030c0a  jmp     loc_180030C90
0x180030c0f  mov     rcx, rdi; hObject
0x180030c12  call    cs:__imp_CloseHandle
0x180030c18  mov     rcx, [rbp+198h]; this
0x180030c1f  test    eax, eax
0x180030c21  jz      loc_180030CAF
0x180030c27  movsxd  rcx, [rsp+290h+var_270]
0x180030c2c  shl     rcx, 1Fh
0x180030c30  movsxd  rax, [rsp+290h+var_26C]
0x180030c35  or      rcx, rax
0x180030c38  mov     [r14], rcx
0x180030c3b  mov     rcx, rbx; hObject
0x180030c3e  call    cs:__imp_CloseHandle
0x180030c44  test    eax, eax
0x180030c46  jz      short loc_180030CBA
0x180030c48  jmp     short loc_180030C7A
0x180030c4a  mov     rcx, [rbp+198h]; this
0x180030c51  mov     edx, 0DCh; void *
0x180030c56  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180030c5b  mov     edi, eax
0x180030c5d  mov     rcx, rbx; hObject
0x180030c60  call    cs:__imp_CloseHandle
0x180030c66  test    eax, eax
0x180030c68  jz      short loc_180030CCC
0x180030c6a  jmp     loc_180030B7F
0x180030c6f  call    cs:__imp_GetLastError
0x180030c75  cmp     eax, 2
0x180030c78  jnz     short loc_180030C7E
0x180030c7a  xor     eax, eax
0x180030c7c  jmp     short loc_180030C90
0x180030c7e  mov     rcx, [rbp+198h]; this
0x180030c85  mov     edx, 0D0h; void *
0x180030c8a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180030c8f  nop
0x180030c90  mov     rcx, [rbp+190h+var_40]
0x180030c97  xor     rcx, rsp; StackCookie
0x180030c9a  call    __security_check_cookie
0x180030c9f  add     rsp, 268h
0x180030ca6  pop     r15
0x180030ca8  pop     r14
0x180030caa  pop     rdi
0x180030cab  pop     rsi
0x180030cac  pop     rbx
0x180030cad  pop     rbp
0x180030cae  retn
0x180030caf  mov     edx, 0A0Bh; void *
0x180030cb4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180030cba  mov     rcx, [rbp+198h]; this
0x180030cc1  mov     edx, 0A0Bh; void *
0x180030cc6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180030ccc  mov     rcx, [rbp+198h]; this
0x180030cd3  mov     edx, 0A0Bh; void *
0x180030cd8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180030cde  mov     rcx, [rbp+198h]; this
0x180030ce5  mov     edx, 0A0Bh; void *
0x180030cea  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180030cf0  mov     edx, 0A0Bh; void *
0x180030cf5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180030cfb  mov     rcx, [rbp+198h]; this
0x180030d02  mov     edx, 0A0Bh; void *
0x180030d07  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
