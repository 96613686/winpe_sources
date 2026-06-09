# __crtCompareStringW

- ea: `0x140063f54`
- end: `0x14006400e`
- name: `__crtCompareStringW`
- size: `186`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpLocaleName@<rcx>, wchar_t *Source, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140053c00`

## callees

- `0x140063f54`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140063f71`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140063f9a`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140063f71`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140063f9a`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x140063fe0`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x140063fe0`

## pseudocode

```c
int __fastcall _crtCompareStringW(LPCWSTR lpLocaleName, __int64 a2, const wchar_t *a3, int a4, wchar_t *Source, int a6)
{
  int v6; // ebx
  int cchCount2; // eax
  int result; // eax
  int v11; // ebx

  v6 = a4;
  if ( a4 > 0 )
    v6 = wcsnlen(a3, a4);
  cchCount2 = a6;
  if ( a6 > 0 )
    cchCount2 = wcsnlen(Source, a6);
  if ( v6 && cchCount2 )
    return CompareStringEx(lpLocaleName, 0x1000u, a3, v6, Source, cchCount2, 0, 0, 0);
  v11 = v6 - cchCount2;
  if ( !v11 )
    return 2;
  result = 3;
  if ( v11 < 0 )
    return 1;
  return result;
}

```

## disassembly

```asm
0x140063f54  push    rbx
0x140063f56  push    rbp
0x140063f57  push    rsi
0x140063f58  push    rdi
0x140063f59  sub     rsp, 58h
0x140063f5d  movsxd  rbx, r9d
0x140063f60  mov     rsi, r8
0x140063f63  mov     rbp, rcx
0x140063f66  test    r9d, r9d
0x140063f69  jle     short loc_140063F80
0x140063f6b  mov     rdx, rbx; MaxCount
0x140063f6e  mov     rcx, r8; Source
0x140063f71  call    cs:__imp_wcsnlen
0x140063f78  nop     dword ptr [rax+rax+00h]
0x140063f7d  mov     rbx, rax
0x140063f80  movsxd  rax, [rsp+78h+arg_28]
0x140063f88  mov     rdi, [rsp+78h+Source]
0x140063f90  test    eax, eax
0x140063f92  jle     short loc_140063FA6
0x140063f94  mov     rdx, rax; MaxCount
0x140063f97  mov     rcx, rdi; Source
0x140063f9a  call    cs:__imp_wcsnlen
0x140063fa1  nop     dword ptr [rax+rax+00h]
0x140063fa6  test    ebx, ebx
0x140063fa8  jz      short loc_140063FEE
0x140063faa  test    eax, eax
0x140063fac  jz      short loc_140063FEE
0x140063fae  mov     [rsp+78h+lParam], 0; lParam
0x140063fb7  mov     r9d, ebx; cchCount1
0x140063fba  mov     [rsp+78h+lpReserved], 0; lpReserved
0x140063fc3  mov     r8, rsi; lpString1
0x140063fc6  mov     [rsp+78h+lpVersionInformation], 0; lpVersionInformation
0x140063fcf  mov     edx, 1000h; dwCmpFlags
0x140063fd4  mov     [rsp+78h+cchCount2], eax; cchCount2
0x140063fd8  mov     rcx, rbp; lpLocaleName
0x140063fdb  mov     [rsp+78h+lpString2], rdi; lpString2
0x140063fe0  call    cs:__imp_CompareStringEx
0x140063fe7  nop     dword ptr [rax+rax+00h]
0x140063fec  jmp     short loc_140064004
0x140063fee  sub     ebx, eax
0x140063ff0  jnz     short loc_140063FF7
0x140063ff2  lea     eax, [rbx+2]
0x140063ff5  jmp     short loc_140064004
0x140063ff7  mov     eax, 3
0x140063ffc  test    ebx, ebx
0x140063ffe  lea     ecx, [rax-2]
0x140064001  cmovs   eax, ecx
0x140064004  add     rsp, 58h
0x140064008  pop     rdi
0x140064009  pop     rsi
0x14006400a  pop     rbp
0x14006400b  pop     rbx
0x14006400c  retn
```
