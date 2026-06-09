# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x14000cfe0`
- end: `0x14000d196`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `438`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x14000c254`

## callees

- `0x14000c16c`
- `0x14000cfe0`
- `0x14000d19c`
- `0x14000d218`
- `0x14000d244`
- `0x14000d39c`
- `0x14000d3bc`
- `0x14000f7e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000d049`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000d0e3`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000d049`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000d0e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d057`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d057`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        STRSAFE_PCNZWCH pszSrc,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned __int64 v5; // rdx
  wil::details *v6; // rax
  wil::details *v7; // rdi
  const char *v8; // r9
  int ValueFromSemaphore; // eax
  unsigned __int64 v11; // rdx
  unsigned int LastError; // ebx
  void *v13; // rdx
  wil::details *v14; // rax
  const char *v15; // r9
  wil::details *v16; // rbx
  int v17; // eax
  void *v18; // rdx
  int v19; // esi
  void *v20; // rdx
  size_t v21; // [rsp+20h] [rbp-E0h]
  int v22; // [rsp+20h] [rbp-E0h]
  int v23; // [rsp+30h] [rbp-D0h] BYREF
  int v24[3]; // [rsp+34h] [rbp-CCh] BYREF
  wchar_t pszDest[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v21);
  StringCchCatW(pszDest, v5, L"_p0");
  v6 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v7 = v6;
  if ( v6 )
  {
    v24[0] = 0;
    v23 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, v24);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore >= 0 )
    {
      StringCchCatW(pszDest, v11, L"h");
      v14 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, pszDest);
      v16 = v14;
      if ( v14 )
      {
        v17 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v14, &v23);
        v19 = v17;
        if ( v17 >= 0 )
        {
          wil::details::CloseHandle(v16, v18);
          *a3 = v24[0] | (unsigned __int64)((__int64)v23 << 31);
          LastError = 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xDE,
            (unsigned int)"wil",
            (const char *)(unsigned int)v17,
            v22);
          wil::details::CloseHandle(v16, v20);
          LastError = v19;
        }
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v15);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v22);
    }
    wil::details::CloseHandle(v7, v13);
    return LastError;
  }
  else if ( GetLastError() == 2 )
  {
    return 0;
  }
  else
  {
    return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v8);
  }
}

```

## disassembly

```asm
0x14000cfe0  mov     [rsp-8+arg_8], rbx
0x14000cfe5  mov     [rsp-8+arg_18], rsi
0x14000cfea  push    rbp
0x14000cfeb  push    rdi
0x14000cfec  push    r14
0x14000cfee  lea     rbp, [rsp-160h]
0x14000cff6  sub     rsp, 260h
0x14000cffd  mov     rax, cs:__security_cookie
0x14000d004  xor     rax, rsp
0x14000d007  mov     [rbp+170h+var_20], rax
0x14000d00e  mov     r9, rcx; pszSrc
0x14000d011  mov     qword ptr [r8], 0
0x14000d018  lea     rcx, [rsp+270h+pszDest]; pszDest
0x14000d01d  mov     edx, 104h; cchDest
0x14000d022  mov     r14, r8
0x14000d025  call    StringCopyWorkerW
0x14000d02a  lea     r8, aP0; "_p0"
0x14000d031  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x14000d036  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000d03b  mov     esi, 1F0003h
0x14000d040  lea     r8, [rsp+270h+pszDest]; lpName
0x14000d045  mov     ecx, esi; dwDesiredAccess
0x14000d047  xor     edx, edx; bInheritHandle
0x14000d049  call    cs:__imp_OpenSemaphoreW
0x14000d04f  mov     rdi, rax
0x14000d052  test    rax, rax
0x14000d055  jnz     short loc_14000D086
0x14000d057  call    cs:__imp_GetLastError
0x14000d05d  cmp     eax, 2
0x14000d060  jnz     short loc_14000D069
0x14000d062  xor     eax, eax
0x14000d064  jmp     loc_14000D16F
0x14000d069  mov     rcx, [rbp+178h]; this
0x14000d070  lea     r8, aWil; "wil"
0x14000d077  mov     edx, 0D0h; void *
0x14000d07c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000d081  jmp     loc_14000D16F
0x14000d086  lea     rdx, [rsp+270h+var_23C]; int *
0x14000d08b  mov     [rsp+270h+var_23C], 0
0x14000d093  mov     rcx, rdi; hHandle
0x14000d096  mov     [rsp+270h+var_240], 0
0x14000d09e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000d0a3  mov     ebx, eax
0x14000d0a5  test    eax, eax
0x14000d0a7  jns     short loc_14000D0C9
0x14000d0a9  mov     rcx, [rbp+178h]; this
0x14000d0b0  lea     r8, aWil; "wil"
0x14000d0b7  mov     r9d, eax; char *
0x14000d0ba  mov     edx, 0D6h; void *
0x14000d0bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000d0c4  jmp     loc_14000D165
0x14000d0c9  lea     r8, asc_14006BB88; "h"
0x14000d0d0  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x14000d0d5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000d0da  lea     r8, [rsp+270h+pszDest]; lpName
0x14000d0df  xor     edx, edx; bInheritHandle
0x14000d0e1  mov     ecx, esi; dwDesiredAccess
0x14000d0e3  call    cs:__imp_OpenSemaphoreW
0x14000d0e9  mov     rbx, rax
0x14000d0ec  test    rax, rax
0x14000d0ef  jnz     short loc_14000D10D
0x14000d0f1  mov     rcx, [rbp+178h]; this
0x14000d0f8  lea     r8, aWil; "wil"
0x14000d0ff  mov     edx, 0DCh; void *
0x14000d104  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000d109  mov     ebx, eax
0x14000d10b  jmp     short loc_14000D165
0x14000d10d  lea     rdx, [rsp+270h+var_240]; int *
0x14000d112  mov     rcx, rbx; hHandle
0x14000d115  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000d11a  mov     esi, eax
0x14000d11c  test    eax, eax
0x14000d11e  jns     short loc_14000D147
0x14000d120  mov     rcx, [rbp+178h]; this
0x14000d127  lea     r8, aWil; "wil"
0x14000d12e  mov     r9d, eax; char *
0x14000d131  mov     edx, 0DEh; void *
0x14000d136  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000d13b  mov     rcx, rbx; this
0x14000d13e  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x14000d143  mov     ebx, esi
0x14000d145  jmp     short loc_14000D165
0x14000d147  mov     rcx, rbx; this
0x14000d14a  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x14000d14f  movsxd  rcx, [rsp+270h+var_240]
0x14000d154  movsxd  rax, [rsp+270h+var_23C]
0x14000d159  shl     rcx, 1Fh
0x14000d15d  or      rcx, rax
0x14000d160  mov     [r14], rcx
0x14000d163  xor     ebx, ebx
0x14000d165  mov     rcx, rdi; this
0x14000d168  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x14000d16d  mov     eax, ebx
0x14000d16f  mov     rcx, [rbp+170h+var_20]
0x14000d176  xor     rcx, rsp; StackCookie
0x14000d179  call    __security_check_cookie
0x14000d17e  lea     r11, [rsp+270h+var_10]
0x14000d186  mov     rbx, [r11+28h]
0x14000d18a  mov     rsi, [r11+38h]
0x14000d18e  mov     rsp, r11
0x14000d191  pop     r14
0x14000d193  pop     rdi
0x14000d194  pop     rbp
0x14000d195  retn
```
