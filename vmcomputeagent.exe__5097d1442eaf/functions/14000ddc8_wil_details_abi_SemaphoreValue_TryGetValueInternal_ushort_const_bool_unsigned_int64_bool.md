# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x14000ddc8`
- end: `0x14000e08a`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `706`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1400091b8`
- `0x140009598`

## callees

- `0x140005360`
- `0x14000aba4`
- `0x14000ced4`
- `0x14000cef4`
- `0x14000d944`
- `0x14000ddc8`
- `0x14000ea44`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000de5f`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000dee1`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000de5f`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000dee1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dfae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dfae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000deac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000df24`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000df35`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000df4d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000df72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000df9f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000deac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000df24`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000df35`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000df4d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000df72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000df9f`

## string_xrefs

- `0x14000dffb`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x14000e014`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x14000e02d`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x14000e046`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x14000e05f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x14000e078`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  const char *v13; // r9
  HANDLE v15; // rax
  const char *v16; // r9
  void *v17; // rdi
  int v18; // eax
  unsigned int v19; // esi
  const char *v20; // r9
  const char *v21; // r9
  const char *v22; // r9
  const char *v23; // r9
  const char *v24; // r9
  const char *v25; // r9
  int v26; // [rsp+20h] [rbp-E0h] BYREF
  int v27[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v25);
    return 0;
  }
  v27[0] = 0;
  v26 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v27);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v26);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v13);
    return LastError;
  }
  StringCchCatW(Name, 0x104u, L"h");
  v15 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v17 = v15;
  if ( !v15 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v16);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v24);
    return LastError;
  }
  v18 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v15, &v26);
  v19 = v18;
  if ( v18 >= 0 )
  {
    if ( !CloseHandle(v17) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v22);
    *a3 = v27[0] | (unsigned __int64)((__int64)v26 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v23);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v18, v26);
  if ( !CloseHandle(v17) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v20);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v21);
  return v19;
}

```

## disassembly

```asm
0x14000ddc8  push    rbp
0x14000ddca  push    rbx
0x14000ddcb  push    rsi
0x14000ddcc  push    rdi
0x14000ddcd  push    r14
0x14000ddcf  push    r15
0x14000ddd1  lea     rbp, [rsp-158h]
0x14000ddd9  sub     rsp, 258h
0x14000dde0  mov     rax, cs:__security_cookie
0x14000dde7  xor     rax, rsp
0x14000ddea  mov     [rbp+180h+var_40], rax
0x14000ddf1  xor     r15d, r15d
0x14000ddf4  lea     rax, [rsp+280h+Name]
0x14000ddf9  mov     esi, 104h
0x14000ddfe  mov     [r8], r15
0x14000de01  mov     edx, esi
0x14000de03  mov     r14, r8
0x14000de06  mov     r9d, 7FFFFFFEh
0x14000de0c  test    r9, r9
0x14000de0f  jz      short loc_14000DE30
0x14000de11  movzx   r8d, word ptr [rcx]
0x14000de15  test    r8w, r8w
0x14000de19  jz      short loc_14000DE30
0x14000de1b  mov     [rax], r8w
0x14000de1f  add     rcx, 2
0x14000de23  add     rax, 2
0x14000de27  dec     r9
0x14000de2a  sub     rdx, 1
0x14000de2e  jnz     short loc_14000DE0C
0x14000de30  test    rdx, rdx
0x14000de33  lea     rcx, [rax-2]
0x14000de37  lea     r8, aP0; "_p0"
0x14000de3e  mov     rdx, rsi; unsigned __int64
0x14000de41  cmovnz  rcx, rax
0x14000de45  mov     [rcx], r15w
0x14000de49  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000de4e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000de53  lea     r8, [rsp+280h+Name]; lpName
0x14000de58  xor     edx, edx; bInheritHandle
0x14000de5a  mov     ecx, 1F0003h; dwDesiredAccess
0x14000de5f  call    cs:__imp_OpenSemaphoreW
0x14000de65  mov     rbx, rax
0x14000de68  test    rax, rax
0x14000de6b  jz      loc_14000DFAE
0x14000de71  lea     rdx, [rsp+280h+var_25C]; int *
0x14000de76  mov     [rsp+280h+var_25C], r15d
0x14000de7b  mov     rcx, rax; hHandle
0x14000de7e  mov     [rsp+280h+var_260], r15d; int
0x14000de83  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000de88  mov     edi, eax
0x14000de8a  test    eax, eax
0x14000de8c  jns     short loc_14000DEC1
0x14000de8e  mov     rcx, [rbp+188h]; this
0x14000de95  lea     r8, aWil; "wil"
0x14000de9c  mov     r9d, eax; char *
0x14000de9f  mov     edx, 0D6h; void *
0x14000dea4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000dea9  mov     rcx, rbx; hObject
0x14000deac  call    cs:__imp_CloseHandle
0x14000deb2  test    eax, eax
0x14000deb4  jz      loc_14000E03F
0x14000deba  mov     eax, edi
0x14000debc  jmp     loc_14000DFD5
0x14000dec1  lea     r8, asc_140116B28; "h"
0x14000dec8  mov     rdx, rsi; unsigned __int64
0x14000decb  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000ded0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000ded5  lea     r8, [rsp+280h+Name]; lpName
0x14000deda  xor     edx, edx; bInheritHandle
0x14000dedc  mov     ecx, 1F0003h; dwDesiredAccess
0x14000dee1  call    cs:__imp_OpenSemaphoreW
0x14000dee7  mov     rdi, rax
0x14000deea  test    rax, rax
0x14000deed  jz      loc_14000DF82
0x14000def3  lea     rdx, [rsp+280h+var_260]; int *
0x14000def8  mov     rcx, rax; hHandle
0x14000defb  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000df00  mov     esi, eax
0x14000df02  test    eax, eax
0x14000df04  jns     short loc_14000DF4A
0x14000df06  mov     rcx, [rbp+188h]; this
0x14000df0d  lea     r8, aWil; "wil"
0x14000df14  mov     r9d, eax; char *
0x14000df17  mov     edx, 0DEh; void *
0x14000df1c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000df21  mov     rcx, rdi; hObject
0x14000df24  call    cs:__imp_CloseHandle
0x14000df2a  test    eax, eax
0x14000df2c  jz      loc_14000E058
0x14000df32  mov     rcx, rbx; hObject
0x14000df35  call    cs:__imp_CloseHandle
0x14000df3b  test    eax, eax
0x14000df3d  jz      loc_14000E071
0x14000df43  mov     eax, esi
0x14000df45  jmp     loc_14000DFD5
0x14000df4a  mov     rcx, rdi; hObject
0x14000df4d  call    cs:__imp_CloseHandle
0x14000df53  test    eax, eax
0x14000df55  jz      loc_14000DFF4
0x14000df5b  movsxd  rax, [rsp+280h+var_25C]
0x14000df60  movsxd  rcx, [rsp+280h+var_260]
0x14000df65  shl     rcx, 1Fh
0x14000df69  or      rcx, rax
0x14000df6c  mov     [r14], rcx
0x14000df6f  mov     rcx, rbx; hObject
0x14000df72  call    cs:__imp_CloseHandle
0x14000df78  test    eax, eax
0x14000df7a  jz      loc_14000E00D
0x14000df80  jmp     short loc_14000DFB9
0x14000df82  mov     rcx, [rbp+188h]; this
0x14000df89  lea     r8, aWil; "wil"
0x14000df90  mov     edx, 0DCh; void *
0x14000df95  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000df9a  mov     rcx, rbx; hObject
0x14000df9d  mov     edi, eax
0x14000df9f  call    cs:__imp_CloseHandle
0x14000dfa5  test    eax, eax
0x14000dfa7  jz      short loc_14000E026
0x14000dfa9  jmp     loc_14000DEBA
0x14000dfae  call    cs:__imp_GetLastError
0x14000dfb4  cmp     eax, 2
0x14000dfb7  jnz     short loc_14000DFBD
0x14000dfb9  xor     eax, eax
0x14000dfbb  jmp     short loc_14000DFD5
0x14000dfbd  mov     rcx, [rbp+188h]; this
0x14000dfc4  lea     r8, aWil; "wil"
0x14000dfcb  mov     edx, 0D0h; void *
0x14000dfd0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000dfd5  mov     rcx, [rbp+180h+var_40]
0x14000dfdc  xor     rcx, rsp; StackCookie
0x14000dfdf  call    __security_check_cookie
0x14000dfe4  add     rsp, 258h
0x14000dfeb  pop     r15
0x14000dfed  pop     r14
0x14000dfef  pop     rdi
0x14000dff0  pop     rsi
0x14000dff1  pop     rbx
0x14000dff2  pop     rbp
0x14000dff3  retn
0x14000dff4  mov     rcx, [rbp+188h]; this
0x14000dffb  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000e002  mov     edx, 0A0Bh; void *
0x14000e007  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000e00d  mov     rcx, [rbp+188h]; this
0x14000e014  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000e01b  mov     edx, 0A0Bh; void *
0x14000e020  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000e026  mov     rcx, [rbp+188h]; this
0x14000e02d  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000e034  mov     edx, 0A0Bh; void *
0x14000e039  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000e03f  mov     rcx, [rbp+188h]; this
0x14000e046  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000e04d  mov     edx, 0A0Bh; void *
0x14000e052  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000e058  mov     rcx, [rbp+188h]; this
0x14000e05f  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000e066  mov     edx, 0A0Bh; void *
0x14000e06b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000e071  mov     rcx, [rbp+188h]; this
0x14000e078  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000e07f  mov     edx, 0A0Bh; void *
0x14000e084  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
