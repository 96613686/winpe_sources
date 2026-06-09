# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180011c60`
- end: `0x180011ee3`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `643`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180007590`

## callees

- `0x1800070e8`
- `0x180011c60`
- `0x180011eec`
- `0x18001203c`
- `0x18001b81c`
- `0x18001c1a0`
- `0x18001ff00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180011d26`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180011dd0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180011d26`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180011dd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011e2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011e2a`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        STRSAFE_PCNZWCH pszSrc,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  __int64 v4; // rbx
  wchar_t *v6; // rax
  __int64 v7; // r11
  __int64 v8; // rbp
  __int64 v9; // rcx
  _WORD *v10; // rdx
  const unsigned __int16 *v11; // r8
  _WORD *v12; // rcx
  wil::details *v13; // rax
  wil::details *v14; // rdi
  int ValueFromSemaphore; // eax
  unsigned int v16; // esi
  wchar_t *v17; // rax
  _WORD *v18; // r8
  const unsigned __int16 *v19; // rcx
  _WORD *v20; // rdx
  wil::details *v21; // rax
  unsigned int v22; // r8d
  const char *v23; // r9
  wil::details *v24; // rbx
  unsigned int LastError; // ebx
  void *v26; // rdx
  unsigned int v28; // r8d
  const char *v29; // r9
  int v30; // eax
  void *v31; // rdx
  void *v32; // rdx
  void *v33; // rdx
  void *v34; // rdx
  size_t v35; // [rsp+20h] [rbp-268h]
  int v36; // [rsp+20h] [rbp-268h]
  int v37; // [rsp+30h] [rbp-258h] BYREF
  int v38[3]; // [rsp+34h] [rbp-254h] BYREF
  wchar_t pszDest[260]; // [rsp+40h] [rbp-248h] BYREF
  _BYTE v40[8]; // [rsp+248h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  v4 = 260;
  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v35);
  v6 = pszDest;
  v7 = 260;
  while ( *v6 )
  {
    ++v6;
    if ( !--v7 )
    {
      v8 = 2147483646;
      goto LABEL_12;
    }
  }
  v8 = 2147483646;
  v9 = 2147483646;
  v10 = &v40[-2 * v7];
  v11 = L"_p0";
  do
  {
    if ( !v9 )
      break;
    if ( !*v11 )
      break;
    *v10++ = *v11++;
    --v9;
    --v7;
  }
  while ( v7 );
  v12 = v10 - 1;
  if ( v7 )
    v12 = v10;
  *v12 = 0;
LABEL_12:
  v13 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v14 = v13;
  if ( v13 )
  {
    v38[0] = 0;
    v37 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, v38);
    v16 = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v36);
    }
    else
    {
      v17 = pszDest;
      while ( *v17 )
      {
        ++v17;
        if ( !--v4 )
          goto LABEL_25;
      }
      v18 = &v40[-2 * v4];
      v19 = L"h";
      do
      {
        if ( !v8 )
          break;
        if ( !*v19 )
          break;
        *v18++ = *v19++;
        --v8;
        --v4;
      }
      while ( v4 );
      v20 = v18 - 1;
      if ( v4 )
        v20 = v18;
      *v20 = 0;
LABEL_25:
      v21 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, pszDest);
      v24 = v21;
      if ( !v21 )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v22, v23);
        wil::details::CloseHandle(v14, v26);
        return LastError;
      }
      v30 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v21, &v37);
      v16 = v30;
      if ( v30 >= 0 )
      {
        wil::details::CloseHandle(v24, v31);
        *a3 = v38[0] | (unsigned __int64)((__int64)v37 << 31);
        wil::details::CloseHandle(v14, v32);
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v30,
        v36);
      wil::details::CloseHandle(v24, v34);
    }
    wil::details::CloseHandle(v14, v33);
    return v16;
  }
  else if ( GetLastError() == 2 )
  {
    return 0;
  }
  else
  {
    return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v28, v29);
  }
}

```

## disassembly

```asm
0x180011c60  push    rbx
0x180011c62  push    rdi
0x180011c63  push    r14
0x180011c65  push    r15
0x180011c67  sub     rsp, 268h
0x180011c6e  mov     rax, cs:__security_cookie
0x180011c75  xor     rax, rsp
0x180011c78  mov     [rsp+288h+var_38], rax
0x180011c80  xor     r15d, r15d
0x180011c83  mov     r9, rcx; pszSrc
0x180011c86  mov     ebx, 104h
0x180011c8b  mov     [r8], r15
0x180011c8e  mov     edx, ebx; cchDest
0x180011c90  lea     rcx, [rsp+288h+pszDest]; pszDest
0x180011c95  mov     r14, r8
0x180011c98  call    StringCopyWorkerW
0x180011c9d  lea     rax, [rsp+288h+pszDest]
0x180011ca2  mov     [rsp+288h+arg_8], rbp
0x180011caa  mov     r11d, ebx
0x180011cad  nop     dword ptr [rax]
0x180011cb0  cmp     [rax], r15w
0x180011cb4  jz      short loc_180011CC7
0x180011cb6  add     rax, 2
0x180011cba  sub     r11, 1
0x180011cbe  jnz     short loc_180011CB0
0x180011cc0  mov     ebp, 7FFFFFFEh
0x180011cc5  jmp     short loc_180011D1A
0x180011cc7  lea     rax, [r11+r11]
0x180011ccb  mov     ebp, 7FFFFFFEh
0x180011cd0  lea     rdx, [rsp+288h+var_40]
0x180011cd8  mov     ecx, ebp
0x180011cda  sub     rdx, rax
0x180011cdd  lea     r8, aP0; "_p0"
0x180011ce4  test    r11, r11
0x180011ce7  jz      short loc_180011D0B
0x180011ce9  test    rcx, rcx
0x180011cec  jz      short loc_180011D0B
0x180011cee  movzx   eax, word ptr [r8]
0x180011cf2  test    ax, ax
0x180011cf5  jz      short loc_180011D0B
0x180011cf7  mov     [rdx], ax
0x180011cfa  add     r8, 2
0x180011cfe  add     rdx, 2
0x180011d02  dec     rcx
0x180011d05  sub     r11, 1
0x180011d09  jnz     short loc_180011CE9
0x180011d0b  test    r11, r11
0x180011d0e  lea     rcx, [rdx-2]
0x180011d12  cmovnz  rcx, rdx
0x180011d16  mov     [rcx], r15w
0x180011d1a  lea     r8, [rsp+288h+pszDest]; lpName
0x180011d1f  xor     edx, edx; bInheritHandle
0x180011d21  mov     ecx, 1F0003h; dwDesiredAccess
0x180011d26  call    cs:__imp_OpenSemaphoreW
0x180011d2c  mov     rdi, rax
0x180011d2f  test    rax, rax
0x180011d32  jz      loc_180011E2A
0x180011d38  lea     rdx, [rsp+288h+var_254]; int *
0x180011d3d  mov     [rsp+288h+var_28], rsi
0x180011d45  mov     rcx, rax; hHandle
0x180011d48  mov     [rsp+288h+var_254], r15d
0x180011d4d  mov     [rsp+288h+var_258], r15d
0x180011d52  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180011d57  mov     esi, eax
0x180011d59  test    eax, eax
0x180011d5b  js      loc_180011E8B
0x180011d61  lea     rax, [rsp+288h+pszDest]
0x180011d66  cmp     [rax], r15w
0x180011d6a  jz      short loc_180011D78
0x180011d6c  add     rax, 2
0x180011d70  sub     rbx, 1
0x180011d74  jnz     short loc_180011D66
0x180011d76  jmp     short loc_180011DC4
0x180011d78  lea     rax, [rbx+rbx]
0x180011d7c  lea     r8, [rsp+288h+var_40]
0x180011d84  sub     r8, rax
0x180011d87  lea     rcx, asc_1800387D0; "h"
0x180011d8e  test    rbx, rbx
0x180011d91  jz      short loc_180011DB5
0x180011d93  test    rbp, rbp
0x180011d96  jz      short loc_180011DB5
0x180011d98  movzx   eax, word ptr [rcx]
0x180011d9b  test    ax, ax
0x180011d9e  jz      short loc_180011DB5
0x180011da0  mov     [r8], ax
0x180011da4  add     rcx, 2
0x180011da8  add     r8, 2
0x180011dac  dec     rbp
0x180011daf  sub     rbx, 1
0x180011db3  jnz     short loc_180011D93
0x180011db5  test    rbx, rbx
0x180011db8  lea     rdx, [r8-2]
0x180011dbc  cmovnz  rdx, r8
0x180011dc0  mov     [rdx], r15w
0x180011dc4  lea     r8, [rsp+288h+pszDest]; lpName
0x180011dc9  xor     edx, edx; bInheritHandle
0x180011dcb  mov     ecx, 1F0003h; dwDesiredAccess
0x180011dd0  call    cs:__imp_OpenSemaphoreW
0x180011dd6  mov     rbx, rax
0x180011dd9  test    rax, rax
0x180011ddc  jnz     short loc_180011E4D
0x180011dde  mov     rcx, [rsp+288h]; this
0x180011de6  mov     edx, 0DCh; void *
0x180011deb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180011df0  mov     rcx, rdi; this
0x180011df3  mov     ebx, eax
0x180011df5  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180011dfa  mov     eax, ebx
0x180011dfc  mov     rsi, [rsp+288h+var_28]
0x180011e04  mov     rbp, [rsp+288h+arg_8]
0x180011e0c  mov     rcx, [rsp+288h+var_38]
0x180011e14  xor     rcx, rsp; StackCookie
0x180011e17  call    __security_check_cookie
0x180011e1c  add     rsp, 268h
0x180011e23  pop     r15
0x180011e25  pop     r14
0x180011e27  pop     rdi
0x180011e28  pop     rbx
0x180011e29  retn
0x180011e2a  call    cs:__imp_GetLastError
0x180011e30  cmp     eax, 2
0x180011e33  jz      loc_180011EDC
0x180011e39  mov     rcx, [rsp+288h]; this
0x180011e41  mov     edx, 0D0h; void *
0x180011e46  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180011e4b  jmp     short loc_180011E04
0x180011e4d  lea     rdx, [rsp+288h+var_258]; int *
0x180011e52  mov     rcx, rbx; hHandle
0x180011e55  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180011e5a  mov     esi, eax
0x180011e5c  test    eax, eax
0x180011e5e  js      short loc_180011EB6
0x180011e60  mov     rcx, rbx; this
0x180011e63  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180011e68  movsxd  rax, [rsp+288h+var_254]
0x180011e6d  movsxd  rcx, [rsp+288h+var_258]
0x180011e72  shl     rcx, 1Fh
0x180011e76  or      rcx, rax
0x180011e79  mov     [r14], rcx
0x180011e7c  mov     rcx, rdi; this
0x180011e7f  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180011e84  xor     eax, eax
0x180011e86  jmp     loc_180011DFC
0x180011e8b  mov     rcx, [rsp+288h]; this
0x180011e93  lea     r8, aWil; "wil"
0x180011e9a  mov     r9d, esi; char *
0x180011e9d  mov     edx, 0D6h; void *
0x180011ea2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011ea7  mov     rcx, rdi; this
0x180011eaa  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180011eaf  mov     eax, esi
0x180011eb1  jmp     loc_180011DFC
0x180011eb6  mov     rcx, [rsp+288h]; this
0x180011ebe  lea     r8, aWil; "wil"
0x180011ec5  mov     r9d, esi; char *
0x180011ec8  mov     edx, 0DEh; void *
0x180011ecd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011ed2  mov     rcx, rbx; this
0x180011ed5  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180011eda  jmp     short loc_180011EA7
0x180011edc  xor     eax, eax
0x180011ede  jmp     loc_180011E04
```
