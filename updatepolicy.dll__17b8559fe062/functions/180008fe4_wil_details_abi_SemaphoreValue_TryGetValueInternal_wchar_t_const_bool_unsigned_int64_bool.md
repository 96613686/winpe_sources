# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x180008fe4`
- end: `0x180009219`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `565`
- prototype: `__int64 __fastcall(const wchar_t *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180009a28`

## callees

- `0x1800061b0`
- `0x180006858`
- `0x180007c98`
- `0x180008bf8`
- `0x180008e70`
- `0x180008fe4`
- `0x18000ed40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009091`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009091`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800091a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800091b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800091d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800091a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800091b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800091d4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009083`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009146`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009083`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009146`

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
  __int64 v21; // r8
  const char *v22; // r9
  __int64 v23; // r8
  const char *v24; // r9
  __int64 v25; // r8
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
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xCD, (int)"wil", v12);
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD3, (int)"wil", (const char *)(unsigned int)ValueFromSemaphore);
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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDB, (int)"wil", (const char *)(unsigned int)v20);
      if ( !CloseHandle(v19) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v21, v22);
    }
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD9, (int)"wil", v18);
  }
LABEL_22:
  if ( !CloseHandle(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v25, v26);
  return LastError;
}

```

## disassembly

```asm
0x180008fe4  mov     rax, rsp
0x180008fe7  mov     [rax+8], rbx
0x180008feb  mov     [rax+10h], rsi
0x180008fef  mov     [rax+20h], rdi
0x180008ff3  push    rbp
0x180008ff4  push    r14
0x180008ff6  push    r15
0x180008ff8  lea     rbp, [rax-168h]
0x180008fff  sub     rsp, 250h
0x180009006  mov     rax, cs:__security_cookie
0x18000900d  xor     rax, rsp
0x180009010  mov     [rbp+160h+var_20], rax
0x180009017  xor     r15d, r15d
0x18000901a  lea     rax, [rsp+260h+Name]
0x18000901f  mov     [r8], r15
0x180009022  lea     rdx, [rsp+260h+Name]
0x180009027  sub     rcx, rax
0x18000902a  mov     r14, r8
0x18000902d  mov     r9d, 104h
0x180009033  lea     rax, [r9+7FFFFEFAh]
0x18000903a  test    rax, rax
0x18000903d  jz      short loc_180009055
0x18000903f  movzx   eax, word ptr [rdx+rcx]
0x180009043  test    ax, ax
0x180009046  jz      short loc_180009055
0x180009048  mov     [rdx], ax
0x18000904b  add     rdx, 2; unsigned __int64
0x18000904f  sub     r9, 1
0x180009053  jnz     short loc_180009033
0x180009055  test    r9, r9
0x180009058  lea     rax, [rdx-2]
0x18000905c  lea     r8, aP0; "_p0"
0x180009063  cmovnz  rax, rdx
0x180009067  lea     rcx, [rsp+260h+Name]; wchar_t *
0x18000906c  mov     [rax], r15w
0x180009070  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180009075  mov     edi, 1F0003h
0x18000907a  lea     r8, [rsp+260h+Name]; lpName
0x18000907f  mov     ecx, edi; dwDesiredAccess
0x180009081  xor     edx, edx; bInheritHandle
0x180009083  call    cs:__imp_OpenSemaphoreW
0x180009089  mov     rsi, rax
0x18000908c  test    rax, rax
0x18000908f  jnz     short loc_1800090BD
0x180009091  call    cs:__imp_GetLastError
0x180009097  cmp     eax, 2
0x18000909a  jnz     short loc_1800090A1
0x18000909c  mov     ebx, r15d
0x18000909f  jmp     short loc_1800090F5
0x1800090a1  mov     rcx, [rbp+168h]; this
0x1800090a8  lea     r8, aWil; "wil"
0x1800090af  mov     edx, 0CDh; void *
0x1800090b4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800090b9  mov     ebx, eax
0x1800090bb  jmp     short loc_1800090F5
0x1800090bd  lea     rdx, [rsp+260h+var_240]; int *
0x1800090c2  mov     [rsp+260h+var_240], r15d; int
0x1800090c7  mov     rcx, rsi; hHandle
0x1800090ca  mov     [rsp+260h+var_23C], r15d
0x1800090cf  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800090d4  mov     ebx, eax
0x1800090d6  test    eax, eax
0x1800090d8  jns     short loc_18000912C
0x1800090da  mov     rcx, [rbp+168h]; this
0x1800090e1  lea     r8, aWil; "wil"
0x1800090e8  mov     r9d, eax; char *
0x1800090eb  mov     edx, 0D3h; void *
0x1800090f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800090f5  test    rsi, rsi
0x1800090f8  jnz     loc_1800091D1
0x1800090fe  mov     eax, ebx
0x180009100  mov     rcx, [rbp+160h+var_20]
0x180009107  xor     rcx, rsp; StackCookie
0x18000910a  call    __security_check_cookie
0x18000910f  lea     r11, [rsp+260h+var_10]
0x180009117  mov     rbx, [r11+20h]
0x18000911b  mov     rsi, [r11+28h]
0x18000911f  mov     rdi, [r11+38h]
0x180009123  mov     rsp, r11
0x180009126  pop     r15
0x180009128  pop     r14
0x18000912a  pop     rbp
0x18000912b  retn
0x18000912c  lea     r8, asc_180018490; "h"
0x180009133  lea     rcx, [rsp+260h+Name]; wchar_t *
0x180009138  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000913d  lea     r8, [rsp+260h+Name]; lpName
0x180009142  xor     edx, edx; bInheritHandle
0x180009144  mov     ecx, edi; dwDesiredAccess
0x180009146  call    cs:__imp_OpenSemaphoreW
0x18000914c  mov     rdi, rax
0x18000914f  test    rax, rax
0x180009152  jnz     short loc_180009170
0x180009154  mov     rcx, [rbp+168h]; this
0x18000915b  lea     r8, aWil; "wil"
0x180009162  mov     edx, 0D9h; void *
0x180009167  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000916c  mov     ebx, eax
0x18000916e  jmp     short loc_1800091D1
0x180009170  lea     rdx, [rsp+260h+var_23C]; int *
0x180009175  mov     rcx, rdi; hHandle
0x180009178  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000917d  mov     ebx, eax
0x18000917f  test    eax, eax
0x180009181  jns     short loc_1800091AD
0x180009183  mov     rcx, [rbp+168h]; this
0x18000918a  lea     r8, aWil; "wil"
0x180009191  mov     r9d, eax; char *
0x180009194  mov     edx, 0DBh; void *
0x180009199  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000919e  mov     rcx, rdi; hObject
0x1800091a1  call    cs:__imp_CloseHandle
0x1800091a7  test    eax, eax
0x1800091a9  jz      short loc_1800091F5
0x1800091ab  jmp     short loc_1800091D1
0x1800091ad  mov     rcx, rdi; hObject
0x1800091b0  call    cs:__imp_CloseHandle
0x1800091b6  test    eax, eax
0x1800091b8  jz      short loc_1800091E3
0x1800091ba  movsxd  rcx, [rsp+260h+var_23C]
0x1800091bf  mov     ebx, r15d
0x1800091c2  movsxd  rax, [rsp+260h+var_240]
0x1800091c7  shl     rcx, 1Fh
0x1800091cb  or      rcx, rax
0x1800091ce  mov     [r14], rcx
0x1800091d1  mov     rcx, rsi; hObject
0x1800091d4  call    cs:__imp_CloseHandle
0x1800091da  test    eax, eax
0x1800091dc  jz      short loc_180009207
0x1800091de  jmp     loc_1800090FE
0x1800091e3  mov     rcx, [rbp+168h]; this
0x1800091ea  mov     edx, 9D1h; void *
0x1800091ef  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800091f5  mov     rcx, [rbp+168h]; this
0x1800091fc  mov     edx, 9D1h; void *
0x180009201  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009207  mov     rcx, [rbp+168h]; this
0x18000920e  mov     edx, 9D1h; void *
0x180009213  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
