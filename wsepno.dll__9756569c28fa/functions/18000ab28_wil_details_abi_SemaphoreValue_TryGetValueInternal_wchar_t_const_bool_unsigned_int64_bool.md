# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000ab28`
- end: `0x18000adab`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `643`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000558c`
- `0x18000595c`

## callees

- `0x180001770`
- `0x180007618`
- `0x18000a354`
- `0x18000a374`
- `0x18000a6bc`
- `0x18000ab28`
- `0x18000b4a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ad00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ad00`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000abbf`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ac41`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000abbf`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ac41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ac0c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ac84`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ac95`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000acaa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000accf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000acf1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ac0c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ac84`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ac95`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000acaa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000accf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000acf1`

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
0x18000ab28  push    rbp
0x18000ab2a  push    rbx
0x18000ab2b  push    rsi
0x18000ab2c  push    rdi
0x18000ab2d  push    r14
0x18000ab2f  push    r15
0x18000ab31  lea     rbp, [rsp-158h]
0x18000ab39  sub     rsp, 258h
0x18000ab40  mov     rax, cs:__security_cookie
0x18000ab47  xor     rax, rsp
0x18000ab4a  mov     [rbp+180h+var_40], rax
0x18000ab51  xor     r15d, r15d
0x18000ab54  lea     rax, [rsp+280h+Name]
0x18000ab59  mov     esi, 104h
0x18000ab5e  mov     [r8], r15
0x18000ab61  mov     edx, esi
0x18000ab63  mov     r14, r8
0x18000ab66  mov     r9d, 7FFFFFFEh
0x18000ab6c  test    r9, r9
0x18000ab6f  jz      short loc_18000AB90
0x18000ab71  movzx   r8d, word ptr [rcx]
0x18000ab75  test    r8w, r8w
0x18000ab79  jz      short loc_18000AB90
0x18000ab7b  mov     [rax], r8w
0x18000ab7f  add     rcx, 2
0x18000ab83  add     rax, 2
0x18000ab87  dec     r9
0x18000ab8a  sub     rdx, 1
0x18000ab8e  jnz     short loc_18000AB6C
0x18000ab90  test    rdx, rdx
0x18000ab93  lea     rcx, [rax-2]
0x18000ab97  lea     r8, aP0; "_p0"
0x18000ab9e  mov     rdx, rsi; unsigned __int64
0x18000aba1  cmovnz  rcx, rax
0x18000aba5  mov     [rcx], r15w
0x18000aba9  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18000abae  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000abb3  lea     r8, [rsp+280h+Name]; lpName
0x18000abb8  xor     edx, edx; bInheritHandle
0x18000abba  mov     ecx, 1F0003h; dwDesiredAccess
0x18000abbf  call    cs:__imp_OpenSemaphoreW
0x18000abc5  mov     rbx, rax
0x18000abc8  test    rax, rax
0x18000abcb  jz      loc_18000AD00
0x18000abd1  lea     rdx, [rsp+280h+var_25C]; int *
0x18000abd6  mov     [rsp+280h+var_25C], r15d
0x18000abdb  mov     rcx, rax; hHandle
0x18000abde  mov     [rsp+280h+var_260], r15d; int
0x18000abe3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000abe8  mov     edi, eax
0x18000abea  test    eax, eax
0x18000abec  jns     short loc_18000AC21
0x18000abee  mov     rcx, [rbp+188h]; this
0x18000abf5  lea     r8, aWil; "wil"
0x18000abfc  mov     r9d, eax; char *
0x18000abff  mov     edx, 0D6h; void *
0x18000ac04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ac09  mov     rcx, rbx; hObject
0x18000ac0c  call    cs:__imp_CloseHandle
0x18000ac12  test    eax, eax
0x18000ac14  jz      loc_18000AD75
0x18000ac1a  mov     eax, edi
0x18000ac1c  jmp     loc_18000AD20
0x18000ac21  lea     r8, asc_180010EC8; "h"
0x18000ac28  mov     rdx, rsi; unsigned __int64
0x18000ac2b  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18000ac30  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000ac35  lea     r8, [rsp+280h+Name]; lpName
0x18000ac3a  xor     edx, edx; bInheritHandle
0x18000ac3c  mov     ecx, 1F0003h; dwDesiredAccess
0x18000ac41  call    cs:__imp_OpenSemaphoreW
0x18000ac47  mov     rdi, rax
0x18000ac4a  test    rax, rax
0x18000ac4d  jz      loc_18000ACDB
0x18000ac53  lea     rdx, [rsp+280h+var_260]; int *
0x18000ac58  mov     rcx, rax; hHandle
0x18000ac5b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000ac60  mov     esi, eax
0x18000ac62  test    eax, eax
0x18000ac64  jns     short loc_18000ACA7
0x18000ac66  mov     rcx, [rbp+188h]; this
0x18000ac6d  lea     r8, aWil; "wil"
0x18000ac74  mov     r9d, eax; char *
0x18000ac77  mov     edx, 0DEh; void *
0x18000ac7c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ac81  mov     rcx, rdi; hObject
0x18000ac84  call    cs:__imp_CloseHandle
0x18000ac8a  test    eax, eax
0x18000ac8c  jz      loc_18000AD87
0x18000ac92  mov     rcx, rbx; hObject
0x18000ac95  call    cs:__imp_CloseHandle
0x18000ac9b  test    eax, eax
0x18000ac9d  jz      loc_18000AD99
0x18000aca3  mov     eax, esi
0x18000aca5  jmp     short loc_18000AD20
0x18000aca7  mov     rcx, rdi; hObject
0x18000acaa  call    cs:__imp_CloseHandle
0x18000acb0  test    eax, eax
0x18000acb2  jz      loc_18000AD3F
0x18000acb8  movsxd  rax, [rsp+280h+var_25C]
0x18000acbd  movsxd  rcx, [rsp+280h+var_260]
0x18000acc2  shl     rcx, 1Fh
0x18000acc6  or      rcx, rax
0x18000acc9  mov     [r14], rcx
0x18000accc  mov     rcx, rbx; hObject
0x18000accf  call    cs:__imp_CloseHandle
0x18000acd5  test    eax, eax
0x18000acd7  jz      short loc_18000AD51
0x18000acd9  jmp     short loc_18000AD0B
0x18000acdb  mov     rcx, [rbp+188h]; this
0x18000ace2  mov     edx, 0DCh; void *
0x18000ace7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000acec  mov     rcx, rbx; hObject
0x18000acef  mov     edi, eax
0x18000acf1  call    cs:__imp_CloseHandle
0x18000acf7  test    eax, eax
0x18000acf9  jz      short loc_18000AD63
0x18000acfb  jmp     loc_18000AC1A
0x18000ad00  call    cs:__imp_GetLastError
0x18000ad06  cmp     eax, 2
0x18000ad09  jnz     short loc_18000AD0F
0x18000ad0b  xor     eax, eax
0x18000ad0d  jmp     short loc_18000AD20
0x18000ad0f  mov     rcx, [rbp+188h]; this
0x18000ad16  mov     edx, 0D0h; void *
0x18000ad1b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000ad20  mov     rcx, [rbp+180h+var_40]
0x18000ad27  xor     rcx, rsp; StackCookie
0x18000ad2a  call    __security_check_cookie
0x18000ad2f  add     rsp, 258h
0x18000ad36  pop     r15
0x18000ad38  pop     r14
0x18000ad3a  pop     rdi
0x18000ad3b  pop     rsi
0x18000ad3c  pop     rbx
0x18000ad3d  pop     rbp
0x18000ad3e  retn
0x18000ad3f  mov     rcx, [rbp+188h]; this
0x18000ad46  mov     edx, 0A0Bh; void *
0x18000ad4b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ad51  mov     rcx, [rbp+188h]; this
0x18000ad58  mov     edx, 0A0Bh; void *
0x18000ad5d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ad63  mov     rcx, [rbp+188h]; this
0x18000ad6a  mov     edx, 0A0Bh; void *
0x18000ad6f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ad75  mov     rcx, [rbp+188h]; this
0x18000ad7c  mov     edx, 0A0Bh; void *
0x18000ad81  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ad87  mov     rcx, [rbp+188h]; this
0x18000ad8e  mov     edx, 0A0Bh; void *
0x18000ad93  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ad99  mov     rcx, [rbp+188h]; this
0x18000ada0  mov     edx, 0A0Bh; void *
0x18000ada5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
