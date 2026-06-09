# __crtCompareStringW

- ea: `0x1400622b0`
- end: `0x140062357`
- name: `__crtCompareStringW`
- size: `167`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpLocaleName@<rcx>, wchar_t *Source, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400521ec`

## callees

- `0x1400622b0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1400622cd`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1400622f0`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1400622cd`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1400622f0`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x140062330`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x140062330`

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
0x1400622b0  push    rbx
0x1400622b2  push    rbp
0x1400622b3  push    rsi
0x1400622b4  push    rdi
0x1400622b5  sub     rsp, 58h
0x1400622b9  movsxd  rbx, r9d
0x1400622bc  mov     rsi, r8
0x1400622bf  mov     rbp, rcx
0x1400622c2  test    r9d, r9d
0x1400622c5  jle     short loc_1400622D6
0x1400622c7  mov     rdx, rbx; MaxCount
0x1400622ca  mov     rcx, r8; Source
0x1400622cd  call    cs:__imp_wcsnlen
0x1400622d3  mov     rbx, rax
0x1400622d6  movsxd  rax, [rsp+78h+arg_28]
0x1400622de  mov     rdi, [rsp+78h+Source]
0x1400622e6  test    eax, eax
0x1400622e8  jle     short loc_1400622F6
0x1400622ea  mov     rdx, rax; MaxCount
0x1400622ed  mov     rcx, rdi; Source
0x1400622f0  call    cs:__imp_wcsnlen
0x1400622f6  test    ebx, ebx
0x1400622f8  jz      short loc_140062338
0x1400622fa  test    eax, eax
0x1400622fc  jz      short loc_140062338
0x1400622fe  mov     [rsp+78h+lParam], 0; lParam
0x140062307  mov     r9d, ebx; cchCount1
0x14006230a  mov     [rsp+78h+lpReserved], 0; lpReserved
0x140062313  mov     r8, rsi; lpString1
0x140062316  mov     [rsp+78h+lpVersionInformation], 0; lpVersionInformation
0x14006231f  mov     edx, 1000h; dwCmpFlags
0x140062324  mov     [rsp+78h+cchCount2], eax; cchCount2
0x140062328  mov     rcx, rbp; lpLocaleName
0x14006232b  mov     [rsp+78h+lpString2], rdi; lpString2
0x140062330  call    cs:__imp_CompareStringEx
0x140062336  jmp     short loc_14006234E
0x140062338  sub     ebx, eax
0x14006233a  jnz     short loc_140062341
0x14006233c  lea     eax, [rbx+2]
0x14006233f  jmp     short loc_14006234E
0x140062341  mov     eax, 3
0x140062346  test    ebx, ebx
0x140062348  lea     ecx, [rax-2]
0x14006234b  cmovs   eax, ecx
0x14006234e  add     rsp, 58h
0x140062352  pop     rdi
0x140062353  pop     rsi
0x140062354  pop     rbp
0x140062355  pop     rbx
0x140062356  retn
```
