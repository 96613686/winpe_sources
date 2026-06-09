# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x140004074`
- end: `0x1400042a9`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `565`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140005738`

## callees

- `0x140002ac0`
- `0x140002ca0`
- `0x140003e74`
- `0x140003e94`
- `0x140003f00`
- `0x140004074`
- `0x14001aa60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140004113`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400041d6`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140004113`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400041d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004121`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004121`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004231`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004240`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004264`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004231`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004240`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004264`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const wchar_t *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rdx
  signed __int64 v5; // rcx
  __int64 v7; // r9
  WCHAR v8; // ax
  WCHAR *v9; // rax
  HANDLE v10; // rax
  void *v11; // rsi
  const char *v12; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v15; // rdx
  HANDLE v17; // rax
  const char *v18; // r9
  void *v19; // rdi
  int v20; // eax
  unsigned int v21; // r8d
  const char *v22; // r9
  unsigned int v23; // r8d
  const char *v24; // r9
  unsigned int v25; // r8d
  const char *v26; // r9
  int v27; // [rsp+28h] [rbp-E0h] BYREF
  int v28[3]; // [rsp+2Ch] [rbp-DCh] BYREF
  WCHAR Name[264]; // [rsp+38h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+270h] [rbp+168h]

  *a3 = 0;
  v4 = Name;
  v5 = (char *)a1 - (char *)Name;
  v7 = 260;
  do
  {
    if ( v7 == -2147483386 )
      break;
    v8 = *(WCHAR *)((char *)v4 + v5);
    if ( !v8 )
      break;
    *v4++ = v8;
    --v7;
  }
  while ( v7 );
  v9 = v4 - 1;
  if ( v7 )
    v9 = v4;
  *v9 = 0;
  StringCchCatW(Name, (unsigned __int64)v4, L"_p0");
  v10 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v11 = v10;
  if ( !v10 )
  {
    if ( GetLastError() == 2 )
      LastError = 0;
    else
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xCD, (unsigned int)"wil", v12);
LABEL_13:
    if ( !v11 )
      return LastError;
    goto LABEL_22;
  }
  v27 = 0;
  v28[0] = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v10, &v27);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD3,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v27);
    goto LABEL_13;
  }
  StringCchCatW(Name, v15, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v19 = v17;
  if ( v17 )
  {
    v20 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, v28);
    LastError = v20;
    if ( v20 >= 0 )
    {
      if ( !CloseHandle(v19) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v23, v24);
      LastError = 0;
      *a3 = v27 | (unsigned __int64)((__int64)v28[0] << 31);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDB,
        (unsigned int)"wil",
        (const char *)(unsigned int)v20,
        v27);
      if ( !CloseHandle(v19) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v21, v22);
    }
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD9, (unsigned int)"wil", v18);
  }
LABEL_22:
  if ( !CloseHandle(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v25, v26);
  return LastError;
}

```

## disassembly

```asm
0x140004074  mov     rax, rsp
0x140004077  mov     [rax+8], rbx
0x14000407b  mov     [rax+10h], rsi
0x14000407f  mov     [rax+20h], rdi
0x140004083  push    rbp
0x140004084  push    r14
0x140004086  push    r15
0x140004088  lea     rbp, [rax-168h]
0x14000408f  sub     rsp, 250h
0x140004096  mov     rax, cs:__security_cookie
0x14000409d  xor     rax, rsp
0x1400040a0  mov     [rbp+160h+var_20], rax
0x1400040a7  xor     r15d, r15d
0x1400040aa  lea     rax, [rsp+260h+Name]
0x1400040af  mov     [r8], r15
0x1400040b2  lea     rdx, [rsp+260h+Name]
0x1400040b7  sub     rcx, rax
0x1400040ba  mov     r14, r8
0x1400040bd  mov     r9d, 104h
0x1400040c3  lea     rax, [r9+7FFFFEFAh]
0x1400040ca  test    rax, rax
0x1400040cd  jz      short loc_1400040E5
0x1400040cf  movzx   eax, word ptr [rdx+rcx]
0x1400040d3  test    ax, ax
0x1400040d6  jz      short loc_1400040E5
0x1400040d8  mov     [rdx], ax
0x1400040db  add     rdx, 2; unsigned __int64
0x1400040df  sub     r9, 1
0x1400040e3  jnz     short loc_1400040C3
0x1400040e5  test    r9, r9
0x1400040e8  lea     rax, [rdx-2]
0x1400040ec  lea     r8, aP0; "_p0"
0x1400040f3  cmovnz  rax, rdx
0x1400040f7  lea     rcx, [rsp+260h+Name]; wchar_t *
0x1400040fc  mov     [rax], r15w
0x140004100  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x140004105  mov     edi, 1F0003h
0x14000410a  lea     r8, [rsp+260h+Name]; lpName
0x14000410f  mov     ecx, edi; dwDesiredAccess
0x140004111  xor     edx, edx; bInheritHandle
0x140004113  call    cs:__imp_OpenSemaphoreW
0x140004119  mov     rsi, rax
0x14000411c  test    rax, rax
0x14000411f  jnz     short loc_14000414D
0x140004121  call    cs:__imp_GetLastError
0x140004127  cmp     eax, 2
0x14000412a  jnz     short loc_140004131
0x14000412c  mov     ebx, r15d
0x14000412f  jmp     short loc_140004185
0x140004131  mov     rcx, [rbp+168h]; this
0x140004138  lea     r8, aWil; "wil"
0x14000413f  mov     edx, 0CDh; void *
0x140004144  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140004149  mov     ebx, eax
0x14000414b  jmp     short loc_140004185
0x14000414d  lea     rdx, [rsp+260h+var_240]; int *
0x140004152  mov     [rsp+260h+var_240], r15d; int
0x140004157  mov     rcx, rsi; hHandle
0x14000415a  mov     [rsp+260h+var_23C], r15d
0x14000415f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140004164  mov     ebx, eax
0x140004166  test    eax, eax
0x140004168  jns     short loc_1400041BC
0x14000416a  mov     rcx, [rbp+168h]; this
0x140004171  lea     r8, aWil; "wil"
0x140004178  mov     r9d, eax; char *
0x14000417b  mov     edx, 0D3h; void *
0x140004180  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004185  test    rsi, rsi
0x140004188  jnz     loc_140004261
0x14000418e  mov     eax, ebx
0x140004190  mov     rcx, [rbp+160h+var_20]
0x140004197  xor     rcx, rsp; StackCookie
0x14000419a  call    __security_check_cookie
0x14000419f  lea     r11, [rsp+260h+var_10]
0x1400041a7  mov     rbx, [r11+20h]
0x1400041ab  mov     rsi, [r11+28h]
0x1400041af  mov     rdi, [r11+38h]
0x1400041b3  mov     rsp, r11
0x1400041b6  pop     r15
0x1400041b8  pop     r14
0x1400041ba  pop     rbp
0x1400041bb  retn
0x1400041bc  lea     r8, asc_140024598; "h"
0x1400041c3  lea     rcx, [rsp+260h+Name]; wchar_t *
0x1400041c8  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1400041cd  lea     r8, [rsp+260h+Name]; lpName
0x1400041d2  xor     edx, edx; bInheritHandle
0x1400041d4  mov     ecx, edi; dwDesiredAccess
0x1400041d6  call    cs:__imp_OpenSemaphoreW
0x1400041dc  mov     rdi, rax
0x1400041df  test    rax, rax
0x1400041e2  jnz     short loc_140004200
0x1400041e4  mov     rcx, [rbp+168h]; this
0x1400041eb  lea     r8, aWil; "wil"
0x1400041f2  mov     edx, 0D9h; void *
0x1400041f7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400041fc  mov     ebx, eax
0x1400041fe  jmp     short loc_140004261
0x140004200  lea     rdx, [rsp+260h+var_23C]; int *
0x140004205  mov     rcx, rdi; hHandle
0x140004208  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000420d  mov     ebx, eax
0x14000420f  test    eax, eax
0x140004211  jns     short loc_14000423D
0x140004213  mov     rcx, [rbp+168h]; this
0x14000421a  lea     r8, aWil; "wil"
0x140004221  mov     r9d, eax; char *
0x140004224  mov     edx, 0DBh; void *
0x140004229  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000422e  mov     rcx, rdi; hObject
0x140004231  call    cs:__imp_CloseHandle
0x140004237  test    eax, eax
0x140004239  jz      short loc_140004285
0x14000423b  jmp     short loc_140004261
0x14000423d  mov     rcx, rdi; hObject
0x140004240  call    cs:__imp_CloseHandle
0x140004246  test    eax, eax
0x140004248  jz      short loc_140004273
0x14000424a  movsxd  rcx, [rsp+260h+var_23C]
0x14000424f  mov     ebx, r15d
0x140004252  movsxd  rax, [rsp+260h+var_240]
0x140004257  shl     rcx, 1Fh
0x14000425b  or      rcx, rax
0x14000425e  mov     [r14], rcx
0x140004261  mov     rcx, rsi; hObject
0x140004264  call    cs:__imp_CloseHandle
0x14000426a  test    eax, eax
0x14000426c  jz      short loc_140004297
0x14000426e  jmp     loc_14000418E
0x140004273  mov     rcx, [rbp+168h]; this
0x14000427a  mov     edx, 9D1h; void *
0x14000427f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004285  mov     rcx, [rbp+168h]; this
0x14000428c  mov     edx, 9D1h; void *
0x140004291  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004297  mov     rcx, [rbp+168h]; this
0x14000429e  mov     edx, 9D1h; void *
0x1400042a3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
