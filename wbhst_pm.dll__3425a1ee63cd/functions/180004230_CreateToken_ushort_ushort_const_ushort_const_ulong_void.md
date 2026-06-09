# CreateToken(ushort *,ushort const *,ushort const *,ulong,void * *)

- ea: `0x180004230`
- end: `0x1800042da`
- name: `?CreateToken@@YAJPEAGPEBG1KPEAPEAX@Z`
- size: `170`
- prototype: `signed int __fastcall(LPCWSTR lpszDomain, LPCWSTR lpszPassword, const unsigned __int16 *, __int64, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800043c8`

## callees

- `0x180004230`

## import_xrefs

- `msvcrt!wcspbrk` at `0x18000425a`
- `msvcrt!wcspbrk` at `0x18000425a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042a5`
- `api-ms-win-security-logon-l1-1-1!LogonUserW` at `0x18000429b`
- `api-ms-win-security-logon-l1-1-1!LogonUserW` at `0x18000429b`

## pseudocode

```c
signed int __fastcall CreateToken(
        LPCWSTR lpszDomain,
        LPCWSTR lpszPassword,
        const unsigned __int16 *a3,
        __int64 a4,
        void **a5)
{
  const WCHAR *v6; // rbx
  wchar_t *v7; // rcx
  const WCHAR *v8; // rdx
  signed int result; // eax
  HANDLE phToken; // [rsp+50h] [rbp+18h] BYREF

  phToken = 0;
  v6 = lpszDomain;
  if ( !lpszDomain )
    return -2147024809;
  v7 = wcspbrk(lpszDomain, L"/\\");
  if ( v7 )
  {
    v8 = v6;
    *v7 = 0;
    v6 = v7 + 1;
  }
  else
  {
    v8 = (const WCHAR *)&dword_180006EFC;
  }
  if ( LogonUserW(v6, v8, lpszPassword, 8u, 0, &phToken) )
  {
    *a5 = phToken;
    return 0;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180004230  mov     [rsp+arg_0], rbx
0x180004235  mov     [rsp+arg_10], r8
0x18000423a  push    rdi
0x18000423b  sub     rsp, 30h
0x18000423f  mov     [rsp+38h+arg_10], 0
0x180004248  mov     rdi, rdx
0x18000424b  mov     rbx, rcx
0x18000424e  test    rcx, rcx
0x180004251  jz      short loc_1800042CA
0x180004253  lea     rdx, Control; "/\\"
0x18000425a  call    cs:__imp_wcspbrk
0x180004260  mov     rcx, rax
0x180004263  test    rax, rax
0x180004266  jnz     short loc_180004271
0x180004268  lea     rdx, dword_180006EFC
0x18000426f  jmp     short loc_18000427D
0x180004271  xor     eax, eax
0x180004273  mov     rdx, rbx; lpszDomain
0x180004276  mov     [rcx], ax
0x180004279  lea     rbx, [rcx+2]
0x18000427d  lea     rax, [rsp+38h+arg_10]
0x180004282  mov     r9d, 8; dwLogonType
0x180004288  mov     [rsp+38h+phToken], rax; phToken
0x18000428d  mov     r8, rdi; lpszPassword
0x180004290  mov     rcx, rbx; lpszUsername
0x180004293  mov     [rsp+38h+dwLogonProvider], 0; dwLogonProvider
0x18000429b  call    cs:__imp_LogonUserW
0x1800042a1  test    eax, eax
0x1800042a3  jnz     short loc_1800042B9
0x1800042a5  call    cs:__imp_GetLastError
0x1800042ab  test    eax, eax
0x1800042ad  jle     short loc_1800042CF
0x1800042af  movzx   eax, ax
0x1800042b2  or      eax, 80070000h
0x1800042b7  jmp     short loc_1800042CF
0x1800042b9  mov     rax, [rsp+38h+arg_10]
0x1800042be  mov     rcx, [rsp+38h+arg_20]
0x1800042c3  mov     [rcx], rax
0x1800042c6  xor     eax, eax
0x1800042c8  jmp     short loc_1800042CF
0x1800042ca  mov     eax, 80070057h
0x1800042cf  mov     rbx, [rsp+38h+arg_0]
0x1800042d4  add     rsp, 30h
0x1800042d8  pop     rdi
0x1800042d9  retn
```
