# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x180006620`
- end: `0x18000685e`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `574`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180007ad8`

## callees

- `0x1800047b4`
- `0x180006400`
- `0x180006424`
- `0x180006444`
- `0x1800064a0`
- `0x180006620`
- `0x1800427d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800066c2`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000678b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800066c2`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000678b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800066d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800066d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800067e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800067f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006819`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800067e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800067f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006819`

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
  unsigned int v20; // r8d
  const char *v21; // r9
  unsigned int v22; // r8d
  const char *v23; // r9
  unsigned int v24; // r8d
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
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD3,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v26);
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
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDB,
        (unsigned int)"wil",
        (const char *)(unsigned int)v19,
        v26);
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
0x180006620  mov     rax, rsp
0x180006623  mov     [rax+8], rbx
0x180006627  mov     [rax+10h], rsi
0x18000662b  mov     [rax+20h], rdi
0x18000662f  push    rbp
0x180006630  push    r14
0x180006632  push    r15
0x180006634  lea     rbp, [rax-168h]
0x18000663b  sub     rsp, 250h
0x180006642  mov     rax, cs:__security_cookie
0x180006649  xor     rax, rsp
0x18000664c  mov     [rbp+160h+var_20], rax
0x180006653  xor     r15d, r15d
0x180006656  lea     rax, [rsp+260h+Name]
0x18000665b  mov     edi, 104h
0x180006660  mov     [r8], r15
0x180006663  mov     r9d, edi
0x180006666  lea     rdx, [rsp+260h+Name]
0x18000666b  sub     rcx, rax
0x18000666e  mov     r14, r8
0x180006671  lea     rax, [r9+7FFFFEFAh]
0x180006678  test    rax, rax
0x18000667b  jz      short loc_180006693
0x18000667d  movzx   eax, word ptr [rdx+rcx]
0x180006681  test    ax, ax
0x180006684  jz      short loc_180006693
0x180006686  mov     [rdx], ax
0x180006689  add     rdx, 2
0x18000668d  sub     r9, 1
0x180006691  jnz     short loc_180006671
0x180006693  lea     rax, [rdx-2]
0x180006697  test    r9, r9
0x18000669a  lea     r8, aP0; "_p0"
0x1800066a1  cmovnz  rax, rdx
0x1800066a5  lea     rcx, [rsp+260h+Name]; wchar_t *
0x1800066aa  mov     rdx, rdi; unsigned __int64
0x1800066ad  mov     [rax], r15w
0x1800066b1  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800066b6  lea     r8, [rsp+260h+Name]; lpName
0x1800066bb  xor     edx, edx; bInheritHandle
0x1800066bd  mov     ecx, 1F0003h; dwDesiredAccess
0x1800066c2  call    cs:__imp_OpenSemaphoreW
0x1800066c8  mov     rsi, rax
0x1800066cb  test    rax, rax
0x1800066ce  jnz     short loc_1800066FC
0x1800066d0  call    cs:__imp_GetLastError
0x1800066d6  cmp     eax, 2
0x1800066d9  jnz     short loc_1800066E0
0x1800066db  mov     ebx, r15d
0x1800066de  jmp     short loc_180006734
0x1800066e0  mov     rcx, [rbp+168h]; this
0x1800066e7  lea     r8, aWil; "wil"
0x1800066ee  mov     edx, 0CDh; void *
0x1800066f3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800066f8  mov     ebx, eax
0x1800066fa  jmp     short loc_180006734
0x1800066fc  lea     rdx, [rsp+260h+var_240]; int *
0x180006701  mov     [rsp+260h+var_240], r15d; int
0x180006706  mov     rcx, rsi; hHandle
0x180006709  mov     [rsp+260h+var_23C], r15d
0x18000670e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006713  mov     ebx, eax
0x180006715  test    eax, eax
0x180006717  jns     short loc_18000676B
0x180006719  mov     rcx, [rbp+168h]; this
0x180006720  lea     r8, aWil; "wil"
0x180006727  mov     r9d, eax; char *
0x18000672a  mov     edx, 0D3h; void *
0x18000672f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006734  test    rsi, rsi
0x180006737  jnz     loc_180006816
0x18000673d  mov     eax, ebx
0x18000673f  mov     rcx, [rbp+160h+var_20]
0x180006746  xor     rcx, rsp; StackCookie
0x180006749  call    __security_check_cookie
0x18000674e  lea     r11, [rsp+260h+var_10]
0x180006756  mov     rbx, [r11+20h]
0x18000675a  mov     rsi, [r11+28h]
0x18000675e  mov     rdi, [r11+38h]
0x180006762  mov     rsp, r11
0x180006765  pop     r15
0x180006767  pop     r14
0x180006769  pop     rbp
0x18000676a  retn
0x18000676b  lea     r8, asc_18004FAB8; "h"
0x180006772  mov     rdx, rdi; unsigned __int64
0x180006775  lea     rcx, [rsp+260h+Name]; wchar_t *
0x18000677a  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000677f  lea     r8, [rsp+260h+Name]; lpName
0x180006784  xor     edx, edx; bInheritHandle
0x180006786  mov     ecx, 1F0003h; dwDesiredAccess
0x18000678b  call    cs:__imp_OpenSemaphoreW
0x180006791  mov     rdi, rax
0x180006794  test    rax, rax
0x180006797  jnz     short loc_1800067B5
0x180006799  mov     rcx, [rbp+168h]; this
0x1800067a0  lea     r8, aWil; "wil"
0x1800067a7  mov     edx, 0D9h; void *
0x1800067ac  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800067b1  mov     ebx, eax
0x1800067b3  jmp     short loc_180006816
0x1800067b5  lea     rdx, [rsp+260h+var_23C]; int *
0x1800067ba  mov     rcx, rdi; hHandle
0x1800067bd  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800067c2  mov     ebx, eax
0x1800067c4  test    eax, eax
0x1800067c6  jns     short loc_1800067F2
0x1800067c8  mov     rcx, [rbp+168h]; this
0x1800067cf  lea     r8, aWil; "wil"
0x1800067d6  mov     r9d, eax; char *
0x1800067d9  mov     edx, 0DBh; void *
0x1800067de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800067e3  mov     rcx, rdi; hObject
0x1800067e6  call    cs:__imp_CloseHandle
0x1800067ec  test    eax, eax
0x1800067ee  jz      short loc_18000683A
0x1800067f0  jmp     short loc_180006816
0x1800067f2  mov     rcx, rdi; hObject
0x1800067f5  call    cs:__imp_CloseHandle
0x1800067fb  test    eax, eax
0x1800067fd  jz      short loc_180006828
0x1800067ff  movsxd  rcx, [rsp+260h+var_23C]
0x180006804  mov     ebx, r15d
0x180006807  movsxd  rax, [rsp+260h+var_240]
0x18000680c  shl     rcx, 1Fh
0x180006810  or      rcx, rax
0x180006813  mov     [r14], rcx
0x180006816  mov     rcx, rsi; hObject
0x180006819  call    cs:__imp_CloseHandle
0x18000681f  test    eax, eax
0x180006821  jz      short loc_18000684C
0x180006823  jmp     loc_18000673D
0x180006828  mov     rcx, [rbp+168h]; this
0x18000682f  mov     edx, 9D1h; void *
0x180006834  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000683a  mov     rcx, [rbp+168h]; this
0x180006841  mov     edx, 9D1h; void *
0x180006846  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000684c  mov     rcx, [rbp+168h]; this
0x180006853  mov     edx, 9D1h; void *
0x180006858  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
