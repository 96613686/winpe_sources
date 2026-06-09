# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180038dfc`
- end: `0x1800390a7`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `683`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800345d8`
- `0x18003497c`

## callees

- `0x180004510`
- `0x180035ed4`
- `0x180037e84`
- `0x180037ea4`
- `0x1800388e8`
- `0x180038dfc`
- `0x1800396fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180038e90`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180038f05`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180038e90`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180038f05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038fcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038fcb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038ed6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038f41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038f52`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038f6a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038f8f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038fbc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038ed6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038f41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038f52`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038f6a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038f8f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038fbc`

## string_xrefs

- `0x180039018`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180039031`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18003904a`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180039063`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18003907c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180039095`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  const char *v15; // r9
  HANDLE v17; // rax
  const char *v18; // r9
  void *v19; // rdi
  int v20; // eax
  unsigned int v21; // r8d
  unsigned int v22; // esi
  const char *v23; // r9
  const char *v24; // r9
  const char *v25; // r9
  const char *v26; // r9
  const char *v27; // r9
  const char *v28; // r9
  int v29; // [rsp+20h] [rbp-E0h] BYREF
  int v30[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v28);
    return 0;
  }
  v30[0] = 0;
  v29 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v30);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v13, (const char *)(unsigned int)ValueFromSemaphore, v29);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v15);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v19 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v18);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v27);
    return LastError;
  }
  v20 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v29);
  v22 = v20;
  if ( v20 >= 0 )
  {
    if ( !CloseHandle(v19) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v25);
    *a3 = v30[0] | (unsigned __int64)((__int64)v29 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v26);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v21, (const char *)(unsigned int)v20, v29);
  if ( !CloseHandle(v19) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v23);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v24);
  return v22;
}

```

## disassembly

```asm
0x180038dfc  push    rbp
0x180038dfe  push    rbx
0x180038dff  push    rsi
0x180038e00  push    rdi
0x180038e01  push    r14
0x180038e03  push    r15
0x180038e05  lea     rbp, [rsp-158h]
0x180038e0d  sub     rsp, 258h
0x180038e14  mov     rax, cs:__security_cookie
0x180038e1b  xor     rax, rsp
0x180038e1e  mov     [rbp+180h+var_40], rax
0x180038e25  xor     r15d, r15d
0x180038e28  lea     rax, [rsp+280h+Name]
0x180038e2d  mov     [r8], r15
0x180038e30  mov     r14, r8
0x180038e33  mov     edx, 104h
0x180038e38  mov     r9d, 7FFFFFFEh
0x180038e3e  test    r9, r9
0x180038e41  jz      short loc_180038E62
0x180038e43  movzx   r8d, word ptr [rcx]
0x180038e47  test    r8w, r8w
0x180038e4b  jz      short loc_180038E62
0x180038e4d  mov     [rax], r8w
0x180038e51  add     rcx, 2
0x180038e55  add     rax, 2
0x180038e59  dec     r9
0x180038e5c  sub     rdx, 1; unsigned __int64
0x180038e60  jnz     short loc_180038E3E
0x180038e62  test    rdx, rdx
0x180038e65  lea     rcx, [rax-2]
0x180038e69  lea     r8, aP0; "_p0"
0x180038e70  cmovnz  rcx, rax
0x180038e74  mov     [rcx], r15w
0x180038e78  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180038e7d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180038e82  mov     esi, 1F0003h
0x180038e87  lea     r8, [rsp+280h+Name]; lpName
0x180038e8c  mov     ecx, esi; dwDesiredAccess
0x180038e8e  xor     edx, edx; bInheritHandle
0x180038e90  call    cs:__imp_OpenSemaphoreW
0x180038e96  mov     rbx, rax
0x180038e99  test    rax, rax
0x180038e9c  jz      loc_180038FCB
0x180038ea2  lea     rdx, [rsp+280h+var_25C]; int *
0x180038ea7  mov     [rsp+280h+var_25C], r15d
0x180038eac  mov     rcx, rax; hHandle
0x180038eaf  mov     [rsp+280h+var_260], r15d; int
0x180038eb4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180038eb9  mov     edi, eax
0x180038ebb  test    eax, eax
0x180038ebd  jns     short loc_180038EEB
0x180038ebf  mov     rcx, [rbp+188h]; this
0x180038ec6  mov     r9d, eax; char *
0x180038ec9  mov     edx, 0D6h; void *
0x180038ece  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038ed3  mov     rcx, rbx; hObject
0x180038ed6  call    cs:__imp_CloseHandle
0x180038edc  test    eax, eax
0x180038ede  jz      loc_18003905C
0x180038ee4  mov     eax, edi
0x180038ee6  jmp     loc_180038FF2
0x180038eeb  lea     r8, asc_1800A5370; "h"
0x180038ef2  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180038ef7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180038efc  lea     r8, [rsp+280h+Name]; lpName
0x180038f01  xor     edx, edx; bInheritHandle
0x180038f03  mov     ecx, esi; dwDesiredAccess
0x180038f05  call    cs:__imp_OpenSemaphoreW
0x180038f0b  mov     rdi, rax
0x180038f0e  test    rax, rax
0x180038f11  jz      loc_180038F9F
0x180038f17  lea     rdx, [rsp+280h+var_260]; int *
0x180038f1c  mov     rcx, rax; hHandle
0x180038f1f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180038f24  mov     esi, eax
0x180038f26  test    eax, eax
0x180038f28  jns     short loc_180038F67
0x180038f2a  mov     rcx, [rbp+188h]; this
0x180038f31  mov     r9d, eax; char *
0x180038f34  mov     edx, 0DEh; void *
0x180038f39  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038f3e  mov     rcx, rdi; hObject
0x180038f41  call    cs:__imp_CloseHandle
0x180038f47  test    eax, eax
0x180038f49  jz      loc_180039075
0x180038f4f  mov     rcx, rbx; hObject
0x180038f52  call    cs:__imp_CloseHandle
0x180038f58  test    eax, eax
0x180038f5a  jz      loc_18003908E
0x180038f60  mov     eax, esi
0x180038f62  jmp     loc_180038FF2
0x180038f67  mov     rcx, rdi; hObject
0x180038f6a  call    cs:__imp_CloseHandle
0x180038f70  test    eax, eax
0x180038f72  jz      loc_180039011
0x180038f78  movsxd  rax, [rsp+280h+var_25C]
0x180038f7d  movsxd  rcx, [rsp+280h+var_260]
0x180038f82  shl     rcx, 1Fh
0x180038f86  or      rcx, rax
0x180038f89  mov     [r14], rcx
0x180038f8c  mov     rcx, rbx; hObject
0x180038f8f  call    cs:__imp_CloseHandle
0x180038f95  test    eax, eax
0x180038f97  jz      loc_18003902A
0x180038f9d  jmp     short loc_180038FD6
0x180038f9f  mov     rcx, [rbp+188h]; this
0x180038fa6  lea     r8, aWil; "wil"
0x180038fad  mov     edx, 0DCh; void *
0x180038fb2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180038fb7  mov     rcx, rbx; hObject
0x180038fba  mov     edi, eax
0x180038fbc  call    cs:__imp_CloseHandle
0x180038fc2  test    eax, eax
0x180038fc4  jz      short loc_180039043
0x180038fc6  jmp     loc_180038EE4
0x180038fcb  call    cs:__imp_GetLastError
0x180038fd1  cmp     eax, 2
0x180038fd4  jnz     short loc_180038FDA
0x180038fd6  xor     eax, eax
0x180038fd8  jmp     short loc_180038FF2
0x180038fda  mov     rcx, [rbp+188h]; this
0x180038fe1  lea     r8, aWil; "wil"
0x180038fe8  mov     edx, 0D0h; void *
0x180038fed  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180038ff2  mov     rcx, [rbp+180h+var_40]
0x180038ff9  xor     rcx, rsp; StackCookie
0x180038ffc  call    __security_check_cookie
0x180039001  add     rsp, 258h
0x180039008  pop     r15
0x18003900a  pop     r14
0x18003900c  pop     rdi
0x18003900d  pop     rsi
0x18003900e  pop     rbx
0x18003900f  pop     rbp
0x180039010  retn
0x180039011  mov     rcx, [rbp+188h]; this
0x180039018  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003901f  mov     edx, 0A0Bh; void *
0x180039024  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18003902a  mov     rcx, [rbp+188h]; this
0x180039031  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180039038  mov     edx, 0A0Bh; void *
0x18003903d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180039043  mov     rcx, [rbp+188h]; this
0x18003904a  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180039051  mov     edx, 0A0Bh; void *
0x180039056  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18003905c  mov     rcx, [rbp+188h]; this
0x180039063  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003906a  mov     edx, 0A0Bh; void *
0x18003906f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180039075  mov     rcx, [rbp+188h]; this
0x18003907c  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180039083  mov     edx, 0A0Bh; void *
0x180039088  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18003908e  mov     rcx, [rbp+188h]; this
0x180039095  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003909c  mov     edx, 0A0Bh; void *
0x1800390a1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
