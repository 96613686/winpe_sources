# DoesContainOnlyAllowedEmailCharacters(ushort const *)

- ea: `0x18005f80c`
- end: `0x18005f8b8`
- name: `?DoesContainOnlyAllowedEmailCharacters@@YA_NPEBG@Z`
- size: `172`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003ae80`
- `0x18003b870`

## callees

- `0x18005f80c`
- `0x18005fb64`

## import_xrefs

- `msvcrt!wcsspn` at `0x18005f860`
- `msvcrt!wcsspn` at `0x18005f87f`
- `msvcrt!wcsspn` at `0x18005f860`
- `msvcrt!wcsspn` at `0x18005f87f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005f893`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005f89c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005f893`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005f89c`

## pseudocode

```c
char __fastcall DoesContainOnlyAllowedEmailCharacters(const unsigned __int16 *a1)
{
  int v1; // eax
  wchar_t *v2; // rdi
  wchar_t *v3; // rbx
  __int64 v4; // rsi
  __int64 v5; // rbp
  bool v6; // zf
  char v7; // si
  wchar_t *String; // [rsp+48h] [rbp+10h] BYREF
  wchar_t *v10; // [rsp+50h] [rbp+18h] BYREF

  String = 0;
  v10 = 0;
  v1 = _UserNameAndDomainFromEmailAddress(a1, &String, (LPVOID *)&v10);
  v2 = String;
  v3 = v10;
  if ( v1 < 0 )
    goto LABEL_7;
  v4 = -1;
  v5 = -1;
  do
    ++v5;
  while ( String[v5] );
  if ( wcsspn(String, L"'-.0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZ_abcdefghijklmnopqrstuvwxyz") != v5 )
    goto LABEL_7;
  do
    ++v4;
  while ( v3[v4] );
  v6 = wcsspn(v3, L"-.0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz") == v4;
  v7 = 1;
  if ( !v6 )
LABEL_7:
    v7 = 0;
  CoTaskMemFree(v3);
  CoTaskMemFree(v2);
  return v7;
}

```

## disassembly

```asm
0x18005f80c  mov     rax, rsp
0x18005f80f  mov     [rax+8], rbx
0x18005f813  mov     [rax+20h], rbp
0x18005f817  push    rsi
0x18005f818  push    rdi
0x18005f819  push    r14
0x18005f81b  sub     rsp, 20h
0x18005f81f  xor     r14d, r14d
0x18005f822  lea     r8, [rax+18h]; unsigned __int16 **
0x18005f826  lea     rdx, [rax+10h]; unsigned __int16 **
0x18005f82a  mov     [rax+10h], r14
0x18005f82e  mov     [rax+18h], r14
0x18005f832  call    ?_UserNameAndDomainFromEmailAddress@@YAJPEBGPEAPEAG1@Z; _UserNameAndDomainFromEmailAddress(ushort const *,ushort * *,ushort * *)
0x18005f837  mov     rdi, [rsp+38h+String]
0x18005f83c  mov     rbx, [rsp+38h+arg_10]
0x18005f841  test    eax, eax
0x18005f843  js      short loc_18005F88D
0x18005f845  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18005f849  mov     rbp, rsi
0x18005f84c  inc     rbp
0x18005f84f  cmp     [rdi+rbp*2], r14w
0x18005f854  jnz     short loc_18005F84C
0x18005f856  lea     rdx, a0123456789abcd; "'-.0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZ"...
0x18005f85d  mov     rcx, rdi; String
0x18005f860  call    cs:__imp_wcsspn
0x18005f866  cmp     rax, rbp
0x18005f869  jnz     short loc_18005F88D
0x18005f86b  inc     rsi
0x18005f86e  cmp     [rbx+rsi*2], r14w
0x18005f873  jnz     short loc_18005F86B
0x18005f875  lea     rdx, a0123456789abcd_0; "-.0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZa"...
0x18005f87c  mov     rcx, rbx; String
0x18005f87f  call    cs:__imp_wcsspn
0x18005f885  cmp     rax, rsi
0x18005f888  mov     sil, 1
0x18005f88b  jz      short loc_18005F890
0x18005f88d  mov     sil, r14b
0x18005f890  mov     rcx, rbx; pv
0x18005f893  call    cs:__imp_CoTaskMemFree
0x18005f899  mov     rcx, rdi; pv
0x18005f89c  call    cs:__imp_CoTaskMemFree
0x18005f8a2  mov     rbx, [rsp+38h+arg_0]
0x18005f8a7  mov     al, sil
0x18005f8aa  mov     rbp, [rsp+38h+arg_18]
0x18005f8af  add     rsp, 20h
0x18005f8b3  pop     r14
0x18005f8b5  pop     rdi
0x18005f8b6  pop     rsi
0x18005f8b7  retn
```
