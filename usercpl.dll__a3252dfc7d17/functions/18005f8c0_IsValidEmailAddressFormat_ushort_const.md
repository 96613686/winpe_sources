# IsValidEmailAddressFormat(ushort const *)

- ea: `0x18005f8c0`
- end: `0x18005f9e0`
- name: `?IsValidEmailAddressFormat@@YA_NPEBG@Z`
- size: `288`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003ae80`
- `0x18003b870`

## callees

- `0x18005f8c0`
- `0x18005fb64`

## import_xrefs

- `msvcrt!wcschr` at `0x18005f968`
- `msvcrt!wcschr` at `0x18005f97a`
- `msvcrt!wcschr` at `0x18005f968`
- `msvcrt!wcschr` at `0x18005f97a`
- `msvcrt!wcsstr` at `0x18005f93f`
- `msvcrt!wcsstr` at `0x18005f9ab`
- `msvcrt!wcsstr` at `0x18005f93f`
- `msvcrt!wcsstr` at `0x18005f9ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005f9be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005f9c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005f9be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005f9c7`

## pseudocode

```c
char __fastcall IsValidEmailAddressFormat(const unsigned __int16 *a1)
{
  int v1; // eax
  wchar_t *v2; // rsi
  wchar_t *v3; // rdi
  __int64 v4; // rbx
  __int64 v5; // rcx
  char v6; // bl
  wchar_t *Str; // [rsp+58h] [rbp+10h] BYREF
  wchar_t *v9; // [rsp+60h] [rbp+18h] BYREF

  Str = 0;
  v9 = 0;
  v1 = _UserNameAndDomainFromEmailAddress(a1, &Str, &v9);
  v2 = Str;
  v3 = v9;
  if ( v1 < 0 )
    goto LABEL_17;
  v4 = -1;
  v5 = -1;
  do
    ++v5;
  while ( Str[v5] );
  if ( (unsigned __int64)(v5 - 1) > 0x3F || *Str == 46 || Str[v5 - 1] == 46 || wcsstr(Str, L"..") )
    goto LABEL_17;
  do
    ++v4;
  while ( v3[v4] );
  if ( (unsigned __int64)(v4 - 3) > 0x2D
    || !wcschr(v3, 0x2Eu)
    || wcschr(v3, 0x40u)
    || *v3 == 46
    || v3[v4 - 1] == 46
    || *v3 == 45
    || v3[v4 - 1] == 45
    || (v6 = 1, wcsstr(v3, L"..")) )
  {
LABEL_17:
    v6 = 0;
  }
  CoTaskMemFree(v3);
  CoTaskMemFree(v2);
  return v6;
}

```

## disassembly

```asm
0x18005f8c0  mov     rax, rsp
0x18005f8c3  mov     [rax+8], rbx
0x18005f8c7  push    rbp
0x18005f8c8  push    rsi
0x18005f8c9  push    rdi
0x18005f8ca  push    r14
0x18005f8cc  push    r15
0x18005f8ce  sub     rsp, 20h
0x18005f8d2  xor     ebp, ebp
0x18005f8d4  lea     r8, [rax+18h]; unsigned __int16 **
0x18005f8d8  lea     rdx, [rax+10h]; unsigned __int16 **
0x18005f8dc  mov     [rax+10h], rbp
0x18005f8e0  mov     [rax+18h], rbp
0x18005f8e4  call    ?_UserNameAndDomainFromEmailAddress@@YAJPEBGPEAPEAG1@Z; _UserNameAndDomainFromEmailAddress(ushort const *,ushort * *,ushort * *)
0x18005f8e9  mov     rsi, [rsp+48h+Str]
0x18005f8ee  mov     rdi, [rsp+48h+arg_10]
0x18005f8f3  test    eax, eax
0x18005f8f5  js      loc_18005F9B8
0x18005f8fb  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18005f8ff  mov     rcx, rbx
0x18005f902  inc     rcx
0x18005f905  cmp     [rsi+rcx*2], bp
0x18005f909  jnz     short loc_18005F902
0x18005f90b  lea     rax, [rcx-1]
0x18005f90f  cmp     rax, 3Fh ; '?'
0x18005f913  ja      loc_18005F9B8
0x18005f919  mov     r14d, 2Eh ; '.'
0x18005f91f  cmp     [rsi], r14w
0x18005f923  jz      loc_18005F9B8
0x18005f929  cmp     [rsi+rcx*2-2], r14w
0x18005f92f  jz      loc_18005F9B8
0x18005f935  lea     rdx, SubStr; ".."
0x18005f93c  mov     rcx, rsi; Str
0x18005f93f  call    cs:__imp_wcsstr
0x18005f945  test    rax, rax
0x18005f948  jnz     short loc_18005F9B8
0x18005f94a  inc     rbx
0x18005f94d  cmp     [rdi+rbx*2], bp
0x18005f951  jnz     short loc_18005F94A
0x18005f953  lea     rax, [rbx-3]
0x18005f957  mov     r15d, 2Dh ; '-'
0x18005f95d  cmp     rax, r15
0x18005f960  ja      short loc_18005F9B8
0x18005f962  mov     edx, r14d; Ch
0x18005f965  mov     rcx, rdi; Str
0x18005f968  call    cs:__imp_wcschr
0x18005f96e  test    rax, rax
0x18005f971  jz      short loc_18005F9B8
0x18005f973  lea     edx, [r15+13h]; Ch
0x18005f977  mov     rcx, rdi; Str
0x18005f97a  call    cs:__imp_wcschr
0x18005f980  test    rax, rax
0x18005f983  jnz     short loc_18005F9B8
0x18005f985  cmp     [rdi], r14w
0x18005f989  jz      short loc_18005F9B8
0x18005f98b  cmp     [rdi+rbx*2-2], r14w
0x18005f991  jz      short loc_18005F9B8
0x18005f993  cmp     [rdi], r15w
0x18005f997  jz      short loc_18005F9B8
0x18005f999  cmp     [rdi+rbx*2-2], r15w
0x18005f99f  jz      short loc_18005F9B8
0x18005f9a1  lea     rdx, SubStr; ".."
0x18005f9a8  mov     rcx, rdi; Str
0x18005f9ab  call    cs:__imp_wcsstr
0x18005f9b1  mov     bl, 1
0x18005f9b3  test    rax, rax
0x18005f9b6  jz      short loc_18005F9BB
0x18005f9b8  mov     bl, bpl
0x18005f9bb  mov     rcx, rdi; pv
0x18005f9be  call    cs:__imp_CoTaskMemFree
0x18005f9c4  mov     rcx, rsi; pv
0x18005f9c7  call    cs:__imp_CoTaskMemFree
0x18005f9cd  mov     al, bl
0x18005f9cf  mov     rbx, [rsp+48h+arg_0]
0x18005f9d4  add     rsp, 20h
0x18005f9d8  pop     r15
0x18005f9da  pop     r14
0x18005f9dc  pop     rdi
0x18005f9dd  pop     rsi
0x18005f9de  pop     rbp
0x18005f9df  retn
```
