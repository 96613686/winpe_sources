# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x180006084`
- end: `0x1800062c2`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `574`
- prototype: `__int64 __fastcall(const wchar_t *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180007654`

## callees

- `0x1800043e8`
- `0x180005e80`
- `0x180005ea4`
- `0x180005ec4`
- `0x180005f10`
- `0x180006084`
- `0x180010310`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006134`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006134`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006126`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800061ef`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006126`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800061ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000624a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006259`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000627d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000624a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006259`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000627d`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const wchar_t *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  __int64 v4; // r9
  WCHAR *v5; // rdx
  signed __int64 v6; // rcx
  WCHAR v8; // ax
  WCHAR *v9; // rax
  HANDLE v10; // rax
  void *v11; // rsi
  const char *v12; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  HANDLE v16; // rax
  const char *v17; // r9
  void *v18; // rdi
  int v19; // eax
  __int64 v20; // r8
  const char *v21; // r9
  __int64 v22; // r8
  const char *v23; // r9
  __int64 v24; // r8
  const char *v25; // r9
  int v26; // [rsp+28h] [rbp-E0h] BYREF
  int v27[3]; // [rsp+2Ch] [rbp-DCh] BYREF
  WCHAR Name[264]; // [rsp+38h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+270h] [rbp+168h]

  *a3 = 0;
  v4 = 260;
  v5 = Name;
  v6 = (char *)a1 - (char *)Name;
  do
  {
    if ( v4 == -2147483386 )
      break;
    v8 = *(WCHAR *)((char *)v5 + v6);
    if ( !v8 )
      break;
    *v5++ = v8;
    --v4;
  }
  while ( v4 );
  v9 = v5 - 1;
  if ( v4 )
    v9 = v5;
  *v9 = 0;
  StringCchCatW(Name, 0x104u, L"_p0");
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
  v26 = 0;
  v27[0] = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v10, &v26);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD3, (int)"wil", (const char *)(unsigned int)ValueFromSemaphore);
    goto LABEL_13;
  }
  StringCchCatW(Name, 0x104u, L"h");
  v16 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18 = v16;
  if ( v16 )
  {
    v19 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v16, v27);
    LastError = v19;
    if ( v19 >= 0 )
    {
      if ( !CloseHandle(v18) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v22, v23);
      LastError = 0;
      *a3 = v26 | (unsigned __int64)((__int64)v27[0] << 31);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDB, (int)"wil", (const char *)(unsigned int)v19);
      if ( !CloseHandle(v18) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v20, v21);
    }
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD9, (unsigned int)"wil", v17);
  }
LABEL_22:
  if ( !CloseHandle(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v24, v25);
  return LastError;
}

```

## disassembly

```asm
0x180006084  mov     rax, rsp
0x180006087  mov     [rax+8], rbx
0x18000608b  mov     [rax+10h], rsi
0x18000608f  mov     [rax+20h], rdi
0x180006093  push    rbp
0x180006094  push    r14
0x180006096  push    r15
0x180006098  lea     rbp, [rax-168h]
0x18000609f  sub     rsp, 250h
0x1800060a6  mov     rax, cs:__security_cookie
0x1800060ad  xor     rax, rsp
0x1800060b0  mov     [rbp+160h+var_20], rax
0x1800060b7  xor     r15d, r15d
0x1800060ba  lea     rax, [rsp+260h+Name]
0x1800060bf  mov     edi, 104h
0x1800060c4  mov     [r8], r15
0x1800060c7  mov     r9d, edi
0x1800060ca  lea     rdx, [rsp+260h+Name]
0x1800060cf  sub     rcx, rax
0x1800060d2  mov     r14, r8
0x1800060d5  lea     rax, [r9+7FFFFEFAh]
0x1800060dc  test    rax, rax
0x1800060df  jz      short loc_1800060F7
0x1800060e1  movzx   eax, word ptr [rdx+rcx]
0x1800060e5  test    ax, ax
0x1800060e8  jz      short loc_1800060F7
0x1800060ea  mov     [rdx], ax
0x1800060ed  add     rdx, 2
0x1800060f1  sub     r9, 1
0x1800060f5  jnz     short loc_1800060D5
0x1800060f7  lea     rax, [rdx-2]
0x1800060fb  test    r9, r9
0x1800060fe  lea     r8, aP0; "_p0"
0x180006105  cmovnz  rax, rdx
0x180006109  lea     rcx, [rsp+260h+Name]; wchar_t *
0x18000610e  mov     rdx, rdi; unsigned __int64
0x180006111  mov     [rax], r15w
0x180006115  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000611a  lea     r8, [rsp+260h+Name]; lpName
0x18000611f  xor     edx, edx; bInheritHandle
0x180006121  mov     ecx, 1F0003h; dwDesiredAccess
0x180006126  call    cs:__imp_OpenSemaphoreW
0x18000612c  mov     rsi, rax
0x18000612f  test    rax, rax
0x180006132  jnz     short loc_180006160
0x180006134  call    cs:__imp_GetLastError
0x18000613a  cmp     eax, 2
0x18000613d  jnz     short loc_180006144
0x18000613f  mov     ebx, r15d
0x180006142  jmp     short loc_180006198
0x180006144  mov     rcx, [rbp+168h]; this
0x18000614b  lea     r8, aWil; "wil"
0x180006152  mov     edx, 0CDh; void *
0x180006157  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000615c  mov     ebx, eax
0x18000615e  jmp     short loc_180006198
0x180006160  lea     rdx, [rsp+260h+var_240]; int *
0x180006165  mov     [rsp+260h+var_240], r15d; int
0x18000616a  mov     rcx, rsi; hHandle
0x18000616d  mov     [rsp+260h+var_23C], r15d
0x180006172  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006177  mov     ebx, eax
0x180006179  test    eax, eax
0x18000617b  jns     short loc_1800061CF
0x18000617d  mov     rcx, [rbp+168h]; this
0x180006184  lea     r8, aWil; "wil"
0x18000618b  mov     r9d, eax; char *
0x18000618e  mov     edx, 0D3h; void *
0x180006193  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006198  test    rsi, rsi
0x18000619b  jnz     loc_18000627A
0x1800061a1  mov     eax, ebx
0x1800061a3  mov     rcx, [rbp+160h+var_20]
0x1800061aa  xor     rcx, rsp; StackCookie
0x1800061ad  call    __security_check_cookie
0x1800061b2  lea     r11, [rsp+260h+var_10]
0x1800061ba  mov     rbx, [r11+20h]
0x1800061be  mov     rsi, [r11+28h]
0x1800061c2  mov     rdi, [r11+38h]
0x1800061c6  mov     rsp, r11
0x1800061c9  pop     r15
0x1800061cb  pop     r14
0x1800061cd  pop     rbp
0x1800061ce  retn
0x1800061cf  lea     r8, asc_180018288; "h"
0x1800061d6  mov     rdx, rdi; unsigned __int64
0x1800061d9  lea     rcx, [rsp+260h+Name]; wchar_t *
0x1800061de  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800061e3  lea     r8, [rsp+260h+Name]; lpName
0x1800061e8  xor     edx, edx; bInheritHandle
0x1800061ea  mov     ecx, 1F0003h; dwDesiredAccess
0x1800061ef  call    cs:__imp_OpenSemaphoreW
0x1800061f5  mov     rdi, rax
0x1800061f8  test    rax, rax
0x1800061fb  jnz     short loc_180006219
0x1800061fd  mov     rcx, [rbp+168h]; this
0x180006204  lea     r8, aWil; "wil"
0x18000620b  mov     edx, 0D9h; void *
0x180006210  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006215  mov     ebx, eax
0x180006217  jmp     short loc_18000627A
0x180006219  lea     rdx, [rsp+260h+var_23C]; int *
0x18000621e  mov     rcx, rdi; hHandle
0x180006221  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006226  mov     ebx, eax
0x180006228  test    eax, eax
0x18000622a  jns     short loc_180006256
0x18000622c  mov     rcx, [rbp+168h]; this
0x180006233  lea     r8, aWil; "wil"
0x18000623a  mov     r9d, eax; char *
0x18000623d  mov     edx, 0DBh; void *
0x180006242  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006247  mov     rcx, rdi; hObject
0x18000624a  call    cs:__imp_CloseHandle
0x180006250  test    eax, eax
0x180006252  jz      short loc_18000629E
0x180006254  jmp     short loc_18000627A
0x180006256  mov     rcx, rdi; hObject
0x180006259  call    cs:__imp_CloseHandle
0x18000625f  test    eax, eax
0x180006261  jz      short loc_18000628C
0x180006263  movsxd  rcx, [rsp+260h+var_23C]
0x180006268  mov     ebx, r15d
0x18000626b  movsxd  rax, [rsp+260h+var_240]
0x180006270  shl     rcx, 1Fh
0x180006274  or      rcx, rax
0x180006277  mov     [r14], rcx
0x18000627a  mov     rcx, rsi; hObject
0x18000627d  call    cs:__imp_CloseHandle
0x180006283  test    eax, eax
0x180006285  jz      short loc_1800062B0
0x180006287  jmp     loc_1800061A1
0x18000628c  mov     rcx, [rbp+168h]; this
0x180006293  mov     edx, 9D1h; void *
0x180006298  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000629e  mov     rcx, [rbp+168h]; this
0x1800062a5  mov     edx, 9D1h; void *
0x1800062aa  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800062b0  mov     rcx, [rbp+168h]; this
0x1800062b7  mov     edx, 9D1h; void *
0x1800062bc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
