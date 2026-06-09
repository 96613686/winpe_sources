# UmpoFindNextCustomStringComponent

- ea: `0x18001207c`
- end: `0x1800120c4`
- name: `UmpoFindNextCustomStringComponent`
- size: `72`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800120cc`
- `0x180012ba8`

## callees

- `0x18001207c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18001209e`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18001209e`

## pseudocode

```c
__int64 __fastcall UmpoFindNextCustomStringComponent(__int64 a1, unsigned int a2, unsigned int a3)
{
  wchar_t *v5; // rax
  wchar_t *v6; // rax

  if ( a3 < a2 && (v5 = wcsstr((const wchar_t *)(a1 + 2LL * a3), L"\\")) != 0 && (v6 = v5 + 1) != 0 )
    return ((__int64)v6 - a1) >> 1;
  else
    return a2;
}

```

## disassembly

```asm
0x18001207c  mov     [rsp+arg_0], rbx
0x180012081  push    rdi
0x180012082  sub     rsp, 20h
0x180012086  mov     ebx, edx
0x180012088  mov     rdi, rcx
0x18001208b  cmp     r8d, edx
0x18001208e  jnb     short loc_1800120B7
0x180012090  mov     eax, r8d
0x180012093  lea     rdx, SubStr; "\\"
0x18001209a  lea     rcx, [rcx+rax*2]; Str
0x18001209e  call    cs:__imp_wcsstr
0x1800120a4  test    rax, rax
0x1800120a7  jz      short loc_1800120B7
0x1800120a9  add     rax, 2
0x1800120ad  jz      short loc_1800120B7
0x1800120af  sub     rax, rdi
0x1800120b2  sar     rax, 1
0x1800120b5  jmp     short loc_1800120B9
0x1800120b7  mov     eax, ebx
0x1800120b9  mov     rbx, [rsp+28h+arg_0]
0x1800120be  add     rsp, 20h
0x1800120c2  pop     rdi
0x1800120c3  retn
```
